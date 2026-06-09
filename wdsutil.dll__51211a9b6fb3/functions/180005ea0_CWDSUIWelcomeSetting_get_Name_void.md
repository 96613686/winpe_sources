# CWDSUIWelcomeSetting::get_Name(void)

- ea: `0x180005ea0`
- end: `0x180005ea8`
- name: `?get_Name@CWDSUIWelcomeSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(CWDSUIWelcomeSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180005ea0`: `WdsClient\UI\WelcomePage`

## pseudocode

```c
unsigned __int16 *__fastcall CWDSUIWelcomeSetting::get_Name(CWDSUIWelcomeSetting *this)
{
  return L"WdsClient\\UI\\WelcomePage";
}

```

## disassembly

```asm
0x180005ea0  lea     rax, aWdsclientUiWel; "WdsClient\\UI\\WelcomePage"
0x180005ea7  retn
```
