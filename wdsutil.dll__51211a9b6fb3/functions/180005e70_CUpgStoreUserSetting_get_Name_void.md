# CUpgStoreUserSetting::get_Name(void)

- ea: `0x180005e70`
- end: `0x180005e78`
- name: `?get_Name@CUpgStoreUserSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CUpgStoreUserSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x180005e70`: `Upgrade Store Path`

## pseudocode

```c
unsigned __int16 *__fastcall CUpgStoreUserSetting::get_Name(CUpgStoreUserSetting *this)
{
  return L"Upgrade Store Path";
}

```

## disassembly

```asm
0x180005e70  lea     rax, aUpgradeStorePa; "Upgrade Store Path"
0x180005e77  retn
```
