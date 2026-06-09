# COOBEUIWelcomeSetting::get_Name(void)

- ea: `0x180005e10`
- end: `0x180005e18`
- name: `?get_Name@COOBEUIWelcomeSetting@@EEAAPEAGXZ`
- size: `8`
- prototype: `unsigned __int16 *__fastcall(COOBEUIWelcomeSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180005e10`: `OOBEUI\WelcomePage`

## pseudocode

```c
unsigned __int16 *__fastcall COOBEUIWelcomeSetting::get_Name(COOBEUIWelcomeSetting *this)
{
  return L"OOBEUI\\WelcomePage";
}

```

## disassembly

```asm
0x180005e10  lea     rax, aOobeuiWelcomep; "OOBEUI\\WelcomePage"
0x180005e17  retn
```
