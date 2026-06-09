# OncRpcConnMgrpRemoteAddressCompare

- ea: `0x140006650`
- end: `0x1400066b0`
- name: `OncRpcConnMgrpRemoteAddressCompare`
- size: `96`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006650`
- `0x140015720`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpRemoteAddressCompare(
        struct _RTL_AVL_TABLE *Table,
        char *FirstStruct,
        char *SecondStruct)
{
  __int16 v3; // ax
  unsigned int v4; // ebx
  char *v6; // rdx
  size_t v7; // r8
  char *v8; // rcx
  int v9; // eax

  v3 = *(_WORD *)SecondStruct;
  v4 = 2;
  if ( *(_WORD *)FirstStruct == 2 )
  {
    if ( v3 != 2 )
    {
      v9 = -1;
      goto LABEL_8;
    }
    v6 = SecondStruct + 4;
    v7 = 4;
    v8 = FirstStruct + 4;
  }
  else
  {
    if ( v3 != 23 )
      return 1;
    v6 = SecondStruct + 8;
    v7 = 16;
    v8 = FirstStruct + 8;
  }
  v9 = memcmp(v8, v6, v7);
LABEL_8:
  if ( v9 )
    return v9 >= 0;
  return v4;
}

```

## disassembly

```asm
0x140006650  push    rbx
0x140006652  sub     rsp, 20h
0x140006656  movzx   eax, word ptr [r8]
0x14000665a  mov     ebx, 2
0x14000665f  mov     r9, rdx
0x140006662  cmp     [rdx], bx
0x140006665  jnz     short loc_14000667F
0x140006667  cmp     ax, bx
0x14000666a  jnz     short loc_14000667A
0x14000666c  lea     rdx, [r8+4]
0x140006670  lea     r8d, [rbx+2]
0x140006674  lea     rcx, [r9+4]
0x140006678  jmp     short loc_140006693
0x14000667a  or      eax, 0FFFFFFFFh
0x14000667d  jmp     short loc_140006698
0x14000667f  cmp     ax, 17h
0x140006683  jnz     short loc_1400066A2
0x140006685  lea     rdx, [r8+8]; Buf2
0x140006689  mov     r8d, 10h; Size
0x14000668f  lea     rcx, [r9+8]; Buf1
0x140006693  call    memcmp
0x140006698  test    eax, eax
0x14000669a  jz      short loc_1400066A7
0x14000669c  jns     short loc_1400066A2
0x14000669e  xor     ebx, ebx
0x1400066a0  jmp     short loc_1400066A7
0x1400066a2  mov     ebx, 1
0x1400066a7  mov     eax, ebx
0x1400066a9  add     rsp, 20h
0x1400066ad  pop     rbx
0x1400066ae  retn
```
