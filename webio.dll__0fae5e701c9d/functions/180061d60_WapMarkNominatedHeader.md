# WapMarkNominatedHeader

- ea: `0x180061d60`
- end: `0x180061f82`
- name: `WapMarkNominatedHeader`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009dd8`

## callees

- `0x180061d60`
- `0x1800953fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180061e15`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180061efd`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180061e15`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180061efd`

## string_xrefs

- `0x180061e05`: `Cache-Control`

## pseudocode

```c
int __fastcall WapMarkNominatedHeader(__int64 a1, const char *a2, size_t a3)
{
  size_t v4; // rdx
  size_t v5; // rbx
  const char *v7; // r9
  unsigned int i; // r8d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rsi
  __int64 v16; // r14
  _QWORD *v17; // r13
  _QWORD *v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rax
  __int128 v23; // [rsp+20h] [rbp-18h] BYREF

  v4 = a3;
  v5 = a3;
  v7 = a2;
  for ( i = 296298159; v4; --v4 )
  {
    v9 = *(unsigned __int8 *)v7++;
    i = *((unsigned __int8 *)WaToLowerTable + v9) + 33 * i;
  }
  LODWORD(v10) = 93 * (i / 0x5D);
  v11 = i % 0x5D;
  if ( !byte_1800AF681[2 * v11]
    || (v10 = (unsigned __int8)WaHttpHeaderHashTable[2 * v11], v12 = 80 * v10, (dword_1800AC44C[20 * v10] & 4) != 0)
    || WaHttpHeaderMapTable[v12 / 8] != v5
    || (LODWORD(v10) = _strnicmp(&aCacheControl_1[v12], a2, v5), (_DWORD)v10) )
  {
    v17 = (_QWORD *)(a1 + 704);
    v18 = (_QWORD *)*v17;
    if ( (_QWORD *)*v17 == v17 )
      return v10;
    while ( 1 )
    {
      if ( v18[3] != v5 )
        goto LABEL_36;
      LODWORD(v10) = _strnicmp((const char *)v18[2], a2, v5);
      if ( (_DWORD)v10 )
        goto LABEL_36;
      if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
        break;
LABEL_35:
      *((_BYTE *)v18 + 48) = 1;
LABEL_36:
      v18 = (_QWORD *)*v18;
      if ( v18 == v17 )
        return v10;
    }
    v23 = (unsigned __int64)a2;
    if ( !a2 )
      goto LABEL_32;
    LODWORD(v21) = v5;
    if ( (_DWORD)v5 == -1 )
    {
      v21 = -1;
      do
        ++v21;
      while ( a2[v21] );
    }
    if ( (_DWORD)v21 )
    {
      if ( (unsigned int)v21 > 0xFFFF )
      {
        WORD4(v23) = -1;
LABEL_34:
        LODWORD(v10) = WPP_SF__COUNTEDSTRING_(v19, 11, v20, &v23);
        goto LABEL_35;
      }
    }
    else
    {
LABEL_32:
      LOWORD(v21) = 1;
      *(_QWORD *)&v23 = &byte_18009C4CF;
    }
    WORD4(v23) = v21;
    goto LABEL_34;
  }
  v15 = *(int *)&byte_1800AC448[v12];
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
  {
    v23 = (unsigned __int64)a2;
    if ( !a2 )
      goto LABEL_19;
    if ( (_DWORD)v5 == -1 )
    {
      v16 = -1;
      do
        ++v16;
      while ( a2[v16] );
      LODWORD(v5) = v16;
    }
    if ( (_DWORD)v5 )
    {
      if ( (unsigned int)v5 <= 0xFFFF )
        WORD4(v23) = v5;
      else
        WORD4(v23) = -1;
    }
    else
    {
LABEL_19:
      WORD4(v23) = 1;
      *(_QWORD *)&v23 = &byte_18009C4CF;
    }
    LODWORD(v10) = WPP_SF__COUNTEDSTRING_(v13, 10, v14, &v23);
  }
  *(_BYTE *)(v15 + a1 + 656) = 1;
  return v10;
}

```

## disassembly

```asm
0x180061d60  push    rbp
0x180061d62  push    rbx
0x180061d63  push    rsi
0x180061d64  push    rdi
0x180061d65  push    r12
0x180061d67  push    r13
0x180061d69  push    r14
0x180061d6b  push    r15
0x180061d6d  mov     rbp, rsp
0x180061d70  sub     rsp, 38h
0x180061d74  mov     rdi, rdx
0x180061d77  lea     r14, __ImageBase
0x180061d7e  mov     rdx, r8
0x180061d81  mov     rbx, r8
0x180061d84  mov     r13, rcx
0x180061d87  mov     r9, rdi
0x180061d8a  mov     r8d, 11A926AFh
0x180061d90  mov     r15d, 1
0x180061d96  test    rdx, rdx
0x180061d99  jz      short loc_180061DB7
0x180061d9b  movzx   eax, byte ptr [r9]
0x180061d9f  add     r9, r15
0x180061da2  imul    r8d, 21h ; '!'
0x180061da6  movzx   ecx, byte ptr [rax+r14+0AEDE0h]
0x180061daf  add     r8d, ecx
0x180061db2  sub     rdx, r15
0x180061db5  jnz     short loc_180061D9B
0x180061db7  mov     eax, 0B02C0B03h
0x180061dbc  mul     r8d
0x180061dbf  shr     edx, 6
0x180061dc2  imul    eax, edx, 5Dh ; ']'
0x180061dc5  sub     r8d, eax
0x180061dc8  cmp     rva byte_1800AF681[r14+r8*2], 0
0x180061dd1  jz      loc_180061EC8
0x180061dd7  movzx   eax, rva WaHttpHeaderHashTable[r14+r8*2]
0x180061de0  lea     rsi, [rax+rax*4]
0x180061de4  shl     rsi, 4
0x180061de8  test    byte ptr [rsi+r14+0AC44Ch], 4
0x180061df1  jnz     loc_180061EC8
0x180061df7  cmp     [rsi+r14+0AC400h], rbx
0x180061dff  jnz     loc_180061EC8
0x180061e05  lea     rcx, rva aCacheControl_1[r14]; "Cache-Control" ...
0x180061e0c  mov     r8, rbx; MaxCount
0x180061e0f  add     rcx, rsi; String1
0x180061e12  mov     rdx, rdi; String2
0x180061e15  call    cs:__imp__strnicmp
0x180061e1c  nop     dword ptr [rax+rax+00h]
0x180061e21  test    eax, eax
0x180061e23  jnz     loc_180061EC8
0x180061e29  movsxd  rsi, dword ptr [rsi+r14+0AC448h]
0x180061e31  test    byte ptr cs:xmmword_1800AD720+3, 4
0x180061e38  jnz     short loc_180061E54
0x180061e3a  mov     [rsi+r13+290h], r15b
0x180061e42  add     rsp, 38h
0x180061e46  pop     r15
0x180061e48  pop     r14
0x180061e4a  pop     r13
0x180061e4c  pop     r12
0x180061e4e  pop     rdi
0x180061e4f  pop     rsi
0x180061e50  pop     rbx
0x180061e51  pop     rbp
0x180061e52  retn
0x180061e54  xorps   xmm0, xmm0
0x180061e57  movups  [rbp+var_18], xmm0
0x180061e5b  mov     qword ptr [rbp+var_18], rdi
0x180061e5f  test    rdi, rdi
0x180061e62  jz      short loc_180061E9C
0x180061e64  cmp     ebx, 0FFFFFFFFh
0x180061e67  jnz     short loc_180061E7A
0x180061e69  or      r14, 0FFFFFFFFFFFFFFFFh
0x180061e6d  inc     r14
0x180061e70  cmp     byte ptr [rdi+r14], 0
0x180061e75  jnz     short loc_180061E6D
0x180061e77  mov     ebx, r14d
0x180061e7a  test    ebx, ebx
0x180061e7c  jz      short loc_180061E9C
0x180061e7e  mov     r15d, 0FFFFh
0x180061e84  cmp     ebx, r15d
0x180061e87  jbe     short loc_180061E90
0x180061e89  mov     word ptr [rbp+var_18+8], r15w
0x180061e8e  jmp     short loc_180061E94
0x180061e90  mov     word ptr [rbp+var_18+8], bx
0x180061e94  mov     r15d, 1
0x180061e9a  jmp     short loc_180061EAC
0x180061e9c  lea     r12, byte_18009C4CF
0x180061ea3  mov     word ptr [rbp+var_18+8], r15w
0x180061ea8  mov     qword ptr [rbp+var_18], r12
0x180061eac  movaps  xmm0, [rbp+var_18]
0x180061eb0  lea     r9, [rbp+var_18]
0x180061eb4  mov     edx, 0Ah
0x180061eb9  movdqa  [rbp+var_18], xmm0
0x180061ebe  call    WPP_SF__COUNTEDSTRING_
0x180061ec3  jmp     loc_180061E3A
0x180061ec8  add     r13, 2C0h
0x180061ecf  mov     rsi, [r13+0]
0x180061ed3  cmp     rsi, r13
0x180061ed6  jz      loc_180061E42
0x180061edc  or      r14, 0FFFFFFFFFFFFFFFFh
0x180061ee0  lea     r12, byte_18009C4CF
0x180061ee7  mov     r15d, 0FFFFh
0x180061eed  cmp     [rsi+18h], rbx
0x180061ef1  jnz     short loc_180061F71
0x180061ef3  mov     rcx, [rsi+10h]; String1
0x180061ef7  mov     r8, rbx; MaxCount
0x180061efa  mov     rdx, rdi; String2
0x180061efd  call    cs:__imp__strnicmp
0x180061f04  nop     dword ptr [rax+rax+00h]
0x180061f09  test    eax, eax
0x180061f0b  jnz     short loc_180061F71
0x180061f0d  test    byte ptr cs:xmmword_1800AD720+3, 4
0x180061f14  jz      short loc_180061F6D
0x180061f16  xorps   xmm0, xmm0
0x180061f19  movups  [rbp+var_18], xmm0
0x180061f1d  mov     qword ptr [rbp+var_18], rdi
0x180061f21  test    rdi, rdi
0x180061f24  jz      short loc_180061F49
0x180061f26  mov     eax, ebx
0x180061f28  cmp     ebx, 0FFFFFFFFh
0x180061f2b  jnz     short loc_180061F39
0x180061f2d  mov     rax, r14
0x180061f30  inc     rax
0x180061f33  cmp     byte ptr [rdi+rax], 0
0x180061f37  jnz     short loc_180061F30
0x180061f39  test    eax, eax
0x180061f3b  jz      short loc_180061F49
0x180061f3d  cmp     eax, r15d
0x180061f40  jbe     short loc_180061F52
0x180061f42  mov     word ptr [rbp+var_18+8], r15w
0x180061f47  jmp     short loc_180061F56
0x180061f49  mov     eax, 1
0x180061f4e  mov     qword ptr [rbp+var_18], r12
0x180061f52  mov     word ptr [rbp+var_18+8], ax
0x180061f56  movaps  xmm0, [rbp+var_18]
0x180061f5a  lea     r9, [rbp+var_18]
0x180061f5e  mov     edx, 0Bh
0x180061f63  movdqa  [rbp+var_18], xmm0
0x180061f68  call    WPP_SF__COUNTEDSTRING_
0x180061f6d  mov     byte ptr [rsi+30h], 1
0x180061f71  mov     rsi, [rsi]
0x180061f74  cmp     rsi, r13
0x180061f77  jnz     loc_180061EED
0x180061f7d  jmp     loc_180061E42
```
