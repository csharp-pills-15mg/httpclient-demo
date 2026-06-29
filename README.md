# HttpClient Demo

## 1) Overview

This solution demonstrates different approaches to configuring and using `HttpClient` in .NET 8 applications with custom HTTP message handlers (`DelegatingHandler`s).

The project showcases three different implementation patterns:

- manual configuration
- Microsoft Dependency Injection
- Autofac dependency injection

### Key Concepts Demonstrated

1. **HTTP Message Handler Pipeline**: Shows how to configure and chained message handlers
2. **Dependency Injection Patterns**: Compares different DI approaches for `HttpClient` configuration (including message handlers)

## 2) Getting Started

1. Clone the repository
2. Open the solution in Visual Studio
3. Start the server application (WebApi)
4. Run one of the client projects (Right click -> Debug -> Start New Instance)

Each client application is:

- adding two custom `DelegatingHandler`s to the `HttpClient` instance
- calls the  `https://localhost:7033/Demo` endpoint.

## 3) Solution Structure

### Client Applications

#### 1. **Clients.Simple** (No Dependency Injection)

- **Type**: Console Application (.NET 8)
- **Purpose**: Demonstrates manual `HttpClient` configuration with message handlers, without dependency injection

#### 2. **Clients.WithDependencyInjection**

- **Type**: Console Application (.NET 8)
- **Purpose**: Shows `HttpClient` configuration using Microsoft's built-in dependency injection

#### 3. **Clients.WithAutofac**

- **Type**: Console Application (.NET 8)
- **Purpose**: Illustrates `HttpClient` setup with Autofac dependency injection container

### Helper Projects

#### 4. **Common**

- **Type**: Class Library (.NET 8)
- **Purpose**: Provides a class that calls the server API. 
- **Components**:
  - `Dummy1Handler`: Demonstration handler (part of handler pipeline)
  - `Dummy2Handler`: Demonstration handler (part of handler pipeline)

#### 5. **HttpClientDemo.WebApiAccess**

- **Type**: Class Library (.NET 8)
- **Purpose**: Provides functionality to access the Web API.

### Server Application

#### 6. HttpClientDemo.WebApi

- **Type**: Web App (.NET 8)
- **Purpose**: Provides a dummy Web API endpoint:
  - `GET /Dummy`

