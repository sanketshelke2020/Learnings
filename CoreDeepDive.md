# How Core Work

## Understand Program.cs
-  Host
- Setup Kestral in web app
- Services start 


## Flow
- Create Host => Add Services => Build
- Use Middleware => app.Run()

## What is middleware 
- Code that process HTTP Reqest or Responses in pipeline
- Log reqeust , Add Headers or even modify responses

## Custom Middleware
- Class
- Inline


-Class
```
public class RequestLoggingMiddleware
{
    private readonly RequestDelegate _next;

    // Constructor takes the next middleware in the pipeline
    public RequestLoggingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    // InvokeAsync processes the request
    public async Task InvokeAsync(HttpContext context)
    {
        // Log the request path
        Console.WriteLine($"Request Path: {context.Request.Path}");

        // Add a custom header to the response
        context.Response.Headers.Add("X-Custom-Header", "Hello from Middleware!");

        // Call the next middleware in the pipeline
        await _next(context);
    }
}

public static class RequestLoggingMiddlewareExtensions
{
    public static IApplicationBuilder UseRequestLogging(this IApplicationBuilder app)
    {
        return app.UseMiddleware<RequestLoggingMiddleware>();
    }
}

// Program.cs
app.UseRequestLogging()
```

- Inline

```
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

// Inline middleware
app.Use(async (context, next) =>
{
    Console.WriteLine($"Inline Middleware: {context.Request.Path}");
    await next(context); // Call the next middleware
});

app.MapGet("/", () => "Hello, World!");

app.Run();

```