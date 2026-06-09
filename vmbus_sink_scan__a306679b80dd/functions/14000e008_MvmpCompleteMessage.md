# MvmpCompleteMessage

- ea: `0x14000e008`
- end: `0x14000e04a`
- name: `MvmpCompleteMessage`
- size: `66`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000dc20`
- `0x14000e880`

## callees

- `0x14000e008`
- `0x14000eaa8`

## pseudocode

```c
char __fastcall MvmpCompleteMessage(__int64 a1, int a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r8
  char result; // al
  signed __int32 v5[8]; // [rsp+0h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a1 + 32);
  v3 = (unsigned __int64)*(unsigned int *)(a1 + 92) << 8;
  *(_DWORD *)(v3 + v2) = 0;
  _InterlockedOr(v5, 0);
  result = *(_BYTE *)(v3 + v2 + 5);
  if ( (result & 1) != 0 )
    return MvmpSetVpRegister(a1, a2, 1073741956, 0, 2);
  return result;
}

```

## disassembly

```asm
0x14000e008  sub     rsp, 38h
0x14000e00c  mov     r8d, [rcx+5Ch]
0x14000e010  mov     rax, [rcx+20h]
0x14000e014  shl     r8, 8
0x14000e018  mov     dword ptr [r8+rax], 0
0x14000e020  lock or [rsp+38h+var_38], 0
0x14000e025  mov     al, [r8+rax+5]
0x14000e02a  test    al, 1
0x14000e02c  jz      short loc_14000E044
0x14000e02e  xor     r9d, r9d
0x14000e031  mov     [rsp+38h+var_18], 2
0x14000e039  mov     r8d, 40000084h
0x14000e03f  call    MvmpSetVpRegister
0x14000e044  add     rsp, 38h
0x14000e048  retn
```
