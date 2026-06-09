# CDiskNumUserSetting::get_Name(void)

- ea: `0x180005d90`
- end: `0x180005d98`
- name: `?get_Name@CDiskNumUserSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CDiskNumUserSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x180005d90`: `InstallDestination\DiskNumber`

## pseudocode

```c
unsigned __int16 *__fastcall CDiskNumUserSetting::get_Name(CDiskNumUserSetting *this)
{
  return L"InstallDestination\\DiskNumber";
}

```

## disassembly

```asm
0x180005d90  lea     rax, aInstalldestina_1; "InstallDestination\\DiskNumber"
0x180005d97  retn
```
