# SeclLogonSecondaryUserIntoSessionW

- ea: `0x1800041b0`
- end: `0x1800041da`
- name: `SeclLogonSecondaryUserIntoSessionW`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall SeclLogonSecondaryUserIntoSessionW(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 result; // rax
  __int128 v4; // [rsp+0h] [rbp-28h]

  *((_QWORD *)&v4 + 1) = 50;
  result = 0;
  *(_QWORD *)&v4 = 0;
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x1800041b0  sub     rsp, 28h
0x1800041b4  mov     qword ptr [rsp+28h+var_28+8], 32h ; '2'
0x1800041bd  mov     [rsp+28h+var_10], 0
0x1800041c6  xor     eax, eax
0x1800041c8  mov     qword ptr [rsp+28h+var_28], rax
0x1800041cc  movups  xmm0, [rsp+28h+var_28]
0x1800041d0  movdqu  xmmword ptr [r8], xmm0
0x1800041d5  add     rsp, 28h
0x1800041d9  retn
```
