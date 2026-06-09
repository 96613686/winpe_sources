# SeclLogoffSecondaryUserFromSessionW

- ea: `0x180004180`
- end: `0x1800041a1`
- name: `SeclLogoffSecondaryUserFromSessionW`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall SeclLogoffSecondaryUserFromSessionW(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 result; // rax
  __int128 v4; // [rsp+0h] [rbp-18h]

  *((_QWORD *)&v4 + 1) = 50;
  result = 0;
  *(_QWORD *)&v4 = 0;
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x180004180  sub     rsp, 18h
0x180004184  mov     qword ptr [rsp+18h+var_18+8], 32h ; '2'
0x18000418d  xor     eax, eax
0x18000418f  mov     qword ptr [rsp+18h+var_18], rax
0x180004193  movups  xmm0, [rsp+18h+var_18]
0x180004197  movdqu  xmmword ptr [r8], xmm0
0x18000419c  add     rsp, 18h
0x1800041a0  retn
```
