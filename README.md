## Pkg

```bash
cd src/Pkg

dotnet build  --runtime rhel.7-x64
dotnet build  --runtime ubuntu-x64
dotnet build  --runtime win7-x64

dotnet rpm --framework netcoreapp2.1 --runtime rhel.7-x64
dotnet zip --framework netcoreapp2.1 --runtime rhel.7-x64
dotnet deb --framework netcoreapp2.1 --runtime ubuntu-x64
dotnet zip --framework netcoreapp2.1 --runtime win7-x64


dotnet msbuild /t:CreateZip /p:TargetFramework=netcoreapp2.1 /p:RuntimeIdentifier=win7-x64   /p:Configuration=Release /p:Version=0.1.1
dotnet msbuild /t:CreateRpm /p:TargetFramework=netcoreapp2.1 /p:RuntimeIdentifier=rhel.7-x64 /p:Configuration=Release /p:Version=0.1.1
```