# CSetupUIWelcomeSetting::get_Name(void)

- ea: `0x180005e50`
- end: `0x180005e58`
- name: `?get_Name@CSetupUIWelcomeSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CSetupUIWelcomeSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x180005e50`: `SetupUI\WelcomePage`

## pseudocode

```c
unsigned __int16 *__fastcall CSetupUIWelcomeSetting::get_Name(CSetupUIWelcomeSetting *this)
{
  return L"SetupUI\\WelcomePage";
}

```

## disassembly

```asm
0x180005e50  lea     rax, aSetupuiWelcome; "SetupUI\\WelcomePage"
0x180005e57  retn
```
