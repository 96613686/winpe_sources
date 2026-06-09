# I_MinCryptGetCommonName

- ea: `0x180016ee0`
- end: `0x180016f26`
- name: `I_MinCryptGetCommonName`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016f2c`

## callees

- `0x180016ee0`
- `0x18004c91c`

## pseudocode

```c
char __fastcall I_MinCryptGetCommonName(unsigned int *a1, __int64 a2)
{
  char result; // al
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  char v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  v4 = 0;
  result = MinAsn1ParseAndDecodeRDNComponent(a1, a2, &v5, (__int64)&v4);
  if ( result )
  {
    *(_BYTE *)(a2 + 10) = v5;
    *(_QWORD *)a2 = *((_QWORD *)&v4 + 1);
    *(_WORD *)(a2 + 8) = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180016ee0  mov     rax, rsp
0x180016ee3  push    rbx
0x180016ee4  sub     rsp, 30h
0x180016ee8  xorps   xmm0, xmm0
0x180016eeb  mov     byte ptr [rax+18h], 0
0x180016eef  lea     r9, [rax-18h]
0x180016ef3  mov     rbx, rdx
0x180016ef6  lea     r8, [rax+18h]
0x180016efa  movups  xmmword ptr [rax-18h], xmm0
0x180016efe  call    MinAsn1ParseAndDecodeRDNComponent
0x180016f03  test    al, al
0x180016f05  jz      short loc_180016F1F
0x180016f07  mov     cl, [rsp+38h+arg_10]
0x180016f0b  mov     [rbx+0Ah], cl
0x180016f0e  mov     rcx, [rsp+38h+var_10]
0x180016f13  mov     [rbx], rcx
0x180016f16  movzx   ecx, [rsp+38h+var_18]
0x180016f1b  mov     [rbx+8], cx
0x180016f1f  add     rsp, 30h
0x180016f23  pop     rbx
0x180016f24  retn
```
