package main

import (
	"fmt"
	"net"
)

func handleConnection(conn net.Conn) {
	defer conn.Close()
	fmt.Println("New connection")
	buffer := make([]byte, 1024)
	for {
		n, err := conn.Read(buffer)
		if err != nil {
			break
		}
		fmt.Println("Received:", string(buffer[:n]))
		conn.Write(buffer[:n])
	}
}

func main() {
	ln, _ := net.Listen("tcp", ":8080")
	defer ln.Close()
	fmt.Println("Chat server running on port 8080")

	for {
		conn, _ := ln.Accept()
		go handleConnection(conn)
	}
}
