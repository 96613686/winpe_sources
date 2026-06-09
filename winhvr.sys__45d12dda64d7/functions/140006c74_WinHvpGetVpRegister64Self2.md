# WinHvpGetVpRegister64Self2

- ea: `0x140006c74`
- end: `0x140006cb6`
- name: `WinHvpGetVpRegister64Self2`
- size: `66`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140006618`
- `0x140006824`
- `0x1400068c0`
- `0x140006998`
- `0x140006af0`
- `0x140006c5c`
- `0x140007210`

## callees

- `0x1400014a8`
- `0x140006c74`

## pseudocode

```c
__int64 __fastcall WinHvpGetVpRegister64Self2(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int MsrNameFromRegisterName; // eax
  _QWORD *v4; // r10
  unsigned int v5; // r9d
  char v7; // [rsp+40h] [rbp+18h] BYREF

  MsrNameFromRegisterName = WinHvpGetMsrNameFromRegisterName(a1, &v7, a3, 0);
  *v4 = __readmsr(MsrNameFromRegisterName);
  return v5;
}

```

## disassembly

```asm
0x140006c74  mov     [rsp+arg_8], rdx
0x140006c79  sub     rsp, 28h
0x140006c7d  mov     r10, rdx
0x140006c80  xor     r9d, r9d
0x140006c83  lea     rdx, [rsp+28h+arg_10]
0x140006c88  call    WinHvpGetMsrNameFromRegisterName
0x140006c8d  nop
0x140006c8e  mov     ecx, eax
0x140006c90  rdmsr
0x140006c92  shl     rdx, 20h
0x140006c96  or      rax, rdx
0x140006c99  mov     [r10], rax
0x140006c9c  jmp     short loc_140006CAD
0x140006c9e  mov     r9d, eax
0x140006ca1  mov     rcx, [rsp+28h+arg_8]
0x140006ca6  mov     qword ptr [rcx], 0
0x140006cad  mov     eax, r9d
0x140006cb0  add     rsp, 28h
0x140006cb4  retn
```
