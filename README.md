## Pkg

```bash
cd src/Pkg

for val in rhel-x64 ubuntu-x64 win7-x64 osx-x64
    dotnet build --runtime $val src/Pkg
end

dotnet rpm --framework netcoreapp2.1 --runtime rhel.7-x64
dotnet zip --framework netcoreapp2.1 --runtime rhel.7-x64
dotnet deb --framework netcoreapp2.1 --runtime ubuntu-x64
dotnet zip --framework netcoreapp2.1 --runtime win7-x64

dotnet msbuild /t:CreateZip /p:TargetFramework=netcoreapp2.2 \
    /p:RuntimeIdentifier=osx-x64    /p:Configuration=Release /p:Version=0.1.1 src/Pkg

dotnet msbuild /t:CreateZip /p:TargetFramework=netcoreapp2.2 \
    /p:RuntimeIdentifier=win7-x64   /p:Configuration=Release /p:Version=0.1.1 src/Pkg

dotnet msbuild /t:CreateRpm /p:TargetFramework=netcoreapp2.2 \
    /p:RuntimeIdentifier=rhel.7-x64 /p:Configuration=Release /p:Version=0.1.1 src/Pkg
```