# TmpFindProtocolHeader

- ea: `0x1400193ac`
- end: `0x14001944c`
- name: `TmpFindProtocolHeader`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001904c`

## callees

- `0x1400193ac`

## pseudocode

```c
__int64 __fastcall TmpFindProtocolHeader(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r11
  unsigned int v4; // r10d
  __int64 v5; // rdi
  unsigned int v6; // r9d
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx

  v2 = *(_QWORD *)(a2 + 360);
  v4 = *(_DWORD *)(v2 + 8);
  if ( !v4 )
    return 0;
  v5 = *(unsigned int *)(a2 + 352);
  v6 = 0;
  v7 = 16;
  if ( *(_DWORD *)(a2 + 88) != 0x10000 )
    v7 = 188;
  v8 = v2 + v7;
  while ( v6 < v4 )
  {
    if ( v8 + 32 > (unsigned __int64)(v2 + v5) )
      return 0;
    v9 = *(unsigned int *)(v8 + 16);
    if ( v8 + v9 + 32 > (unsigned __int64)(v2 + v5) || (unsigned int)v9 > 0x7FFFFFFF )
      return 0;
    v10 = *(_QWORD *)v8 - *a1;
    if ( *(_QWORD *)v8 == *a1 )
      v10 = *(_QWORD *)(v8 + 8) - a1[1];
    if ( !v10 )
      return v8;
    v8 += v9 + 32;
    ++v6;
  }
  if ( v6 == v4 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x1400193ac  mov     [rsp+arg_0], rbx
0x1400193b1  mov     [rsp+arg_8], rdi
0x1400193b6  mov     r11, [rdx+168h]
0x1400193bd  mov     rbx, rcx
0x1400193c0  mov     r10d, [r11+8]
0x1400193c4  cmp     r10d, 1
0x1400193c8  jb      short loc_14001943E
0x1400193ca  mov     edi, [rdx+160h]
0x1400193d0  xor     r9d, r9d
0x1400193d3  cmp     dword ptr [rdx+58h], 10000h
0x1400193da  mov     eax, 0BCh
0x1400193df  lea     r8d, [r9+10h]
0x1400193e3  cmovnz  r8d, eax
0x1400193e7  add     r8, r11
0x1400193ea  cmp     r9d, r10d
0x1400193ed  jnb     short loc_140019430
0x1400193ef  lea     rcx, [r11+rdi]
0x1400193f3  lea     rax, [r8+20h]
0x1400193f7  cmp     rax, rcx
0x1400193fa  ja      short loc_14001943E
0x1400193fc  mov     eax, [r8+10h]
0x140019400  lea     rdx, [rax+20h]
0x140019404  add     rdx, r8
0x140019407  cmp     rdx, rcx
0x14001940a  ja      short loc_14001943E
0x14001940c  cmp     eax, 7FFFFFFFh
0x140019411  ja      short loc_14001943E
0x140019413  mov     rcx, [r8]
0x140019416  sub     rcx, [rbx]
0x140019419  jnz     short loc_140019423
0x14001941b  mov     rcx, [r8+8]
0x14001941f  sub     rcx, [rbx+8]
0x140019423  test    rcx, rcx
0x140019426  jz      short loc_140019439
0x140019428  mov     r8, rdx
0x14001942b  inc     r9d
0x14001942e  jmp     short loc_1400193EA
0x140019430  xor     eax, eax
0x140019432  cmp     r9d, r10d
0x140019435  cmovz   r8, rax
0x140019439  mov     rax, r8
0x14001943c  jmp     short loc_140019440
0x14001943e  xor     eax, eax
0x140019440  mov     rbx, [rsp+arg_0]
0x140019445  mov     rdi, [rsp+arg_8]
0x14001944a  retn
```
