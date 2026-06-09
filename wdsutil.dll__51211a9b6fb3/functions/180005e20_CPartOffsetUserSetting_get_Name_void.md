# CPartOffsetUserSetting::get_Name(void)

- ea: `0x180005e20`
- end: `0x180005e28`
- name: `?get_Name@CPartOffsetUserSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CPartOffsetUserSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x180005e20`: `InstallDestination\Partition OffSet`

## pseudocode

```c
unsigned __int16 *__fastcall CPartOffsetUserSetting::get_Name(CPartOffsetUserSetting *this)
{
  return L"InstallDestination\\Partition OffSet";
}

```

## disassembly

```asm
0x180005e20  lea     rax, aInstalldestina_0; "InstallDestination\\Partition OffSet"
0x180005e27  retn
```
