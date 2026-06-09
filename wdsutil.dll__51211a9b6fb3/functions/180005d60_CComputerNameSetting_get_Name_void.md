# CComputerNameSetting::get_Name(void)

- ea: `0x180005d60`
- end: `0x180005d68`
- name: `?get_Name@CComputerNameSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CComputerNameSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180005d60`: `UserData\ComputerName`

## pseudocode

```c
unsigned __int16 *__fastcall CComputerNameSetting::get_Name(CComputerNameSetting *this)
{
  return L"UserData\\ComputerName";
}

```

## disassembly

```asm
0x180005d60  lea     rax, aUserdataComput; "UserData\\ComputerName"
0x180005d67  retn
```
