# ReadHdmxValue

- ea: `0x1800033bc`
- end: `0x180003451`
- name: `ReadHdmxValue`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bd0`

## callees

- `0x1800033bc`
- `0x180003458`

## import_xrefs

- `msvcrt!longjmp` at `0x18000344a`
- `msvcrt!longjmp` at `0x18000344a`

## pseudocode

```c
__int64 __fastcall ReadHdmxValue(_QWORD *a1, __int64 a2, unsigned int *a3)
{
  unsigned __int16 i; // bx
  unsigned int v6; // r10d
  int v7; // eax
  int v8; // edx
  _BYTE *v9; // r8

  for ( i = 0; ; ++i )
  {
    v6 = *a3 + 1;
    v7 = (int)*a3 / 8;
    v8 = (int)*a3 % 8;
    *a3 = v6;
    v9 = (_BYTE *)(a2 + v7);
    if ( (unsigned __int64)(v9 + 1) > a1[3] || (unsigned __int64)v9 < a1[2] )
      longjmp((_JBTYPE *)(a1[12] + 48LL), 3362);
    if ( ((unsigned __int8)(1 << v8) & *v9) == 0 )
      break;
  }
  if ( i )
  {
    *a3 = v6 + 1;
    if ( (unsigned __int16)ReadBit(a1, a2, v6) )
      return (unsigned __int16)-i;
  }
  return i;
}

```

## disassembly

```asm
0x1800033bc  push    rbx
0x1800033be  push    rbp
0x1800033bf  push    rsi
0x1800033c0  push    rdi
0x1800033c1  sub     rsp, 28h
0x1800033c5  xor     esi, esi
0x1800033c7  mov     r11, r8
0x1800033ca  mov     rdi, rdx
0x1800033cd  mov     r9, rcx
0x1800033d0  mov     ebx, esi
0x1800033d2  lea     ebp, [rsi+1]
0x1800033d5  mov     eax, [r11]
0x1800033d8  mov     ecx, 8
0x1800033dd  lea     r10d, [rax+1]
0x1800033e1  cdq
0x1800033e2  idiv    ecx
0x1800033e4  mov     [r11], r10d
0x1800033e7  movsxd  r8, eax
0x1800033ea  add     r8, rdi
0x1800033ed  lea     rax, [r8+1]
0x1800033f1  cmp     rax, [r9+18h]
0x1800033f5  ja      short loc_18000343D
0x1800033f7  cmp     r8, [r9+10h]
0x1800033fb  jb      short loc_18000343D
0x1800033fd  mov     ecx, edx
0x1800033ff  mov     edx, ebp
0x180003401  shl     edx, cl
0x180003403  test    [r8], dl
0x180003406  jnz     short loc_180003438
0x180003408  test    bx, bx
0x18000340b  jnz     short loc_180003419
0x18000340d  movzx   eax, bx
0x180003410  add     rsp, 28h
0x180003414  pop     rdi
0x180003415  pop     rsi
0x180003416  pop     rbp
0x180003417  pop     rbx
0x180003418  retn
0x180003419  lea     ecx, [r10+1]
0x18000341d  mov     r8d, r10d
0x180003420  mov     [r11], ecx
0x180003423  mov     rdx, rdi
0x180003426  mov     rcx, r9
0x180003429  call    ReadBit
0x18000342e  test    ax, ax
0x180003431  jz      short loc_18000340D
0x180003433  neg     bx
0x180003436  jmp     short loc_18000340D
0x180003438  add     bx, bp
0x18000343b  jmp     short loc_1800033D5
0x18000343d  mov     rcx, [r9+60h]
0x180003441  mov     edx, 0D22h; Value
0x180003446  add     rcx, 30h ; '0'; Buf
0x18000344a  call    cs:__imp_longjmp
```
