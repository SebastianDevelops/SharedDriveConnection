# SharedDriveConnection NuGet Package

**SharedDriveConnection** is a simple .NET library that facilitates connecting to a network share with authentication. This library provides a `DriveConnect` class, allowing users to establish and manage network connections effortlessly.

## Getting Started

### Installation

To use this library, you can install it via NuGet Package Manager Console:

```bash
Install-Package SharedDriveConnection
```

### Usage

1. **Initialize DriveConnect:**

   ```csharp
   using SharedDriveConnection;
   ```

   ```csharp
   // Specify the network share path and credentials
   string networkPath = "\\server\\share";
   NetworkCredential credentials = new NetworkCredential("username", "password");

   // Create an instance of DriveConnect
   using (DriveConnect driveConnect = new DriveConnect(networkPath, credentials))
   {
       // Your code here
   }
   ```

2. **Dispose of the Connection:**

   The connection will be automatically disposed of when leaving the `using` block. However, you can manually dispose of it using the `Dispose` method:

   ```csharp
   driveConnect.Dispose();
   ```

## Documentation

### DriveConnect Class

#### Constructors

- `DriveConnect(string networkName, NetworkCredential credentials)`: Initializes a new instance of the `DriveConnect` class.

#### Events

- `Disposed`: Occurs when the instance has been disposed.

#### Methods

- `Dispose()`: Performs tasks associated with freeing, releasing, or resetting unmanaged resources.

#### Objects needed for Win32 functions

- `NetResource`: Represents details of the proposed connection.
- `ResourceScope`: Enumerates the resource scope.
- `ResourceType`: Enumerates the resource type.
- `ResourceDisplaytype`: Enumerates the resource display type.

## Example

```csharp
using SharedDriveConnection;

// Specify the network share path and credentials
string networkPath = "\\server\\share";
NetworkCredential credentials = new NetworkCredential("username", "password");

// Create an instance of DriveConnect
using (DriveConnect driveConnect = new DriveConnect(networkPath, credentials))
{
    // Your code here
}
```

For more details on the Win32 functions used, refer to the [Microsoft documentation](http://msdn.microsoft.com/en-us/library/aa385413%28VS.85%29.aspx).

## Contributions

Contributions are welcome! Feel free to submit issues or pull requests.

## License

This library is licensed under the [MIT License](LICENSE).