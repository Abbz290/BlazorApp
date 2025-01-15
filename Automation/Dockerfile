## Build stage
#FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
#WORKDIR /app
#COPY . ./
#RUN dotnet restore
#RUN dotnet publish -c Release -o /out
#
## Runtime stage
#FROM nginx:alpine
#WORKDIR /usr/share/nginx/html
#COPY --from=build /out/wwwroot .
#EXPOSE 80
#CMD ["nginx", "-g", "daemon off;"]
# Build stage
# Use a base image
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /app
EXPOSE 80

# Copy the app to the container
COPY . .

# Set the entrypoint for the application
ENTRYPOINT ["dotnet", "MyBlazorApp.dll"]