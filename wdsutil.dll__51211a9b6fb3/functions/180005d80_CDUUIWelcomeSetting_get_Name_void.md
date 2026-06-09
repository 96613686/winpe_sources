# CDUUIWelcomeSetting::get_Name(void)

- ea: `0x180005d80`
- end: `0x180005d88`
- name: `?get_Name@CDUUIWelcomeSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CDUUIWelcomeSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x180005d80`: `SetupUI\DU\WelcomePage`

## pseudocode

```c
unsigned __int16 *__fastcall CDUUIWelcomeSetting::get_Name(CDUUIWelcomeSetting *this)
{
  return L"SetupUI\\DU\\WelcomePage";
}

```

## disassembly

```asm
0x180005d80  lea     rax, aSetupuiDuWelco; "SetupUI\\DU\\WelcomePage"
0x180005d87  retn
```
