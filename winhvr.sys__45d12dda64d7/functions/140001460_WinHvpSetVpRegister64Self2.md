# WinHvpSetVpRegister64Self2

- ea: `0x140001460`
- end: `0x14000149f`
- name: `WinHvpSetVpRegister64Self2`
- size: `63`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010e8`
- `0x1400011c0`
- `0x140004510`
- `0x1400061c0`
- `0x140006254`
- `0x140006590`
- `0x140006824`
- `0x1400068c0`
- `0x140006998`
- `0x14000bcd0`

## callees

- `0x140001460`
- `0x1400014a8`

## pseudocode

```c
__int64 __fastcall WinHvpSetVpRegister64Self2(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int MsrNameFromRegisterName; // ecx
  unsigned __int64 v5; // r10
  char v6; // r9
  char v8; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(a4) = a3;
  MsrNameFromRegisterName = WinHvpGetMsrNameFromRegisterName(a1, &v8, a3, a4);
  if ( v6 )
    return 3224698885LL;
  __writemsr(MsrNameFromRegisterName, v5);
  return 0;
}

```

## disassembly

```asm
0x140001460  sub     rsp, 28h
0x140001464  mov     r9b, r8b
0x140001467  mov     r10, rdx
0x14000146a  lea     rdx, [rsp+28h+arg_10]
0x14000146f  call    WinHvpGetMsrNameFromRegisterName
0x140001474  mov     ecx, eax
0x140001476  test    r9b, r9b
0x140001479  jnz     short loc_140001498
0x14000147b  xor     r8d, r8d
0x14000147e  mov     rdx, r10
0x140001481  mov     rax, r10
0x140001484  shr     rdx, 20h
0x140001488  wrmsr
0x14000148a  jmp     short loc_14000148F
0x14000148c  mov     r8d, eax
0x14000148f  mov     eax, r8d
0x140001492  add     rsp, 28h
0x140001496  retn
0x140001498  mov     eax, 0C0350005h
0x14000149d  jmp     short loc_140001492
```
