# CDiskPartUserSetting::get_Name(void)

- ea: `0x180005dc0`
- end: `0x180005dc8`
- name: `?get_Name@CDiskPartUserSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CDiskPartUserSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x180005dc0`: `InstallDestination\Selection`

## pseudocode

```c
unsigned __int16 *__fastcall CDiskPartUserSetting::get_Name(CDiskPartUserSetting *this)
{
  return L"InstallDestination\\Selection";
}

```

## disassembly

```asm
0x180005dc0  lea     rax, aInstalldestina_2; "InstallDestination\\Selection"
0x180005dc7  retn
```
