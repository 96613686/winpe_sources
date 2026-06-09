# CDiskPartFileSystemUserSetting::get_Name(void)

- ea: `0x180005da0`
- end: `0x180005da8`
- name: `?get_Name@CDiskPartFileSystemUserSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CDiskPartFileSystemUserSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x180005da0`: `InstallDestination\DestinationFileSystem`

## pseudocode

```c
unsigned __int16 *__fastcall CDiskPartFileSystemUserSetting::get_Name(CDiskPartFileSystemUserSetting *this)
{
  return L"InstallDestination\\DestinationFileSystem";
}

```

## disassembly

```asm
0x180005da0  lea     rax, aInstalldestina; "InstallDestination\\DestinationFileSyst"...
0x180005da7  retn
```
