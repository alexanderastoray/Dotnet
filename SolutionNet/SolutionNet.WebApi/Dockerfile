FROM mcr.microsoft.com/dotnet/aspnet:6.0-focal AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:6.0-focal AS build
WORKDIR /src
COPY ["SolutionNet.WebApi.csproj", "./"]
RUN dotnet restore "./SolutionNet.WebApi.csproj"

COPY . .
WORKDIR "/src/."
RUN dotnet build "SolutionNet.WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "SolutionNet.WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "SolutionNet.WebApi.dll"]