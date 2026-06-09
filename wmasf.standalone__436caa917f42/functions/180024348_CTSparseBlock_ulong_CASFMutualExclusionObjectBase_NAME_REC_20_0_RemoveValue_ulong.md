# CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::RemoveValue(ulong)

- ea: `0x180024348`
- end: `0x1800244d2`
- name: `?RemoveValue@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023b70`

## callees

- `0x180024348`
- `0x180024790`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::RemoveValue(
        __int64 a1,
        unsigned int a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  int v6; // r12d
  int v7; // edx
  int v8; // r14d
  unsigned int v9; // edx
  int v10; // r15d
  unsigned int v11; // esi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r10
  char j; // r11
  unsigned __int8 v16; // si
  _OWORD v18[4]; // [rsp+20h] [rbp-48h] BYREF

  for ( i = a1; i; i = *(_QWORD *)(i + 360) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 368);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 376);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 376) = v7 - 1;
      else
        v6 = 1;
    }
  }
  v8 = 0;
  while ( i )
  {
    v9 = *(_DWORD *)(i + 8);
    if ( a2 < v9 )
    {
      v10 = 0;
      v11 = 0;
      if ( (*(_BYTE *)(i + 32)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::s_bSingleBitMasks) != 0 )
      {
        v18[0] = *(_OWORD *)(i + 40);
        v8 = CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::SetValue(a1, v9 - 1, v18);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 16LL * v11 + 40), (const void *)(i + 16LL * (v11 + 1) + 40), 16LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 32); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 32) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 32) < 0 )
        *(_BYTE *)(v13 + i + 32) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 32) &= *((_BYTE *)&qword_18004A2B8 - v16);
        *(_BYTE *)(v14 + 32) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::s_bLeftBitMasks
                                + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 360) == *(_QWORD *)(a1 + 368) )
    {
      *(_QWORD *)(a1 + 368) = i;
      *(_DWORD *)(a1 + 376) = 19;
    }
    i = *(_QWORD *)(i + 360);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024348  push    rbx
0x18002434a  push    rbp
0x18002434b  push    rsi
0x18002434c  push    rdi
0x18002434d  push    r12
0x18002434f  push    r14
0x180024351  push    r15
0x180024353  sub     rsp, 30h
0x180024357  mov     ebp, edx
0x180024359  mov     rdi, rcx
0x18002435c  mov     rbx, rcx
0x18002435f  test    rcx, rcx
0x180024362  jz      short loc_18002437A
0x180024364  mov     eax, [rbx+8]
0x180024367  add     eax, 14h
0x18002436a  cmp     ebp, eax
0x18002436c  jb      short loc_18002437A
0x18002436e  mov     rbx, [rbx+168h]
0x180024375  test    rbx, rbx
0x180024378  jnz     short loc_180024364
0x18002437a  mov     rax, [rcx+170h]
0x180024381  xor     r12d, r12d
0x180024384  test    rax, rax
0x180024387  jz      short loc_1800243AB
0x180024389  mov     edx, [rcx+178h]
0x18002438f  mov     ecx, [rax+8]
0x180024392  add     ecx, edx
0x180024394  cmp     ebp, ecx
0x180024396  jnb     short loc_1800243AB
0x180024398  test    edx, edx
0x18002439a  jnz     short loc_1800243A2
0x18002439c  lea     r12d, [rdx+1]
0x1800243a0  jmp     short loc_1800243AB
0x1800243a2  lea     eax, [rdx-1]
0x1800243a5  mov     [rdi+178h], eax
0x1800243ab  xor     r14d, r14d
0x1800243ae  jmp     loc_1800244B7
0x1800243b3  mov     edx, [rbx+8]
0x1800243b6  cmp     ebp, edx
0x1800243b8  jb      short loc_1800243C6
0x1800243ba  mov     esi, ebp
0x1800243bc  mov     r15d, 1
0x1800243c2  sub     esi, edx
0x1800243c4  jmp     short loc_1800243FA
0x1800243c6  mov     al, [rbx+20h]
0x1800243c9  xor     r15d, r15d
0x1800243cc  xor     esi, esi
0x1800243ce  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::s_bSingleBitMasks
0x1800243d4  jz      short loc_1800243FA
0x1800243d6  movups  xmm0, xmmword ptr [rbx+28h]
0x1800243da  dec     edx
0x1800243dc  lea     r8, [rsp+68h+var_48]
0x1800243e1  mov     rcx, rdi
0x1800243e4  movdqu  [rsp+68h+var_48], xmm0
0x1800243ea  call    ?SetValue@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJKUNAME_REC@CASFMutualExclusionObjectBase@@@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::SetValue(ulong,CASFMutualExclusionObjectBase::NAME_REC)
0x1800243ef  mov     r14d, eax
0x1800243f2  test    eax, eax
0x1800243f4  js      loc_1800244C0
0x1800243fa  mov     r8d, 13h
0x180024400  mov     ecx, esi
0x180024402  shl     rcx, 4
0x180024406  lea     edx, [rsi+1]
0x180024409  shl     rdx, 4
0x18002440d  add     rcx, 28h ; '('
0x180024411  add     rdx, 28h ; '('
0x180024415  sub     r8d, esi
0x180024418  add     rdx, rbx; Src
0x18002441b  shl     r8, 4; Size
0x18002441f  add     rcx, rbx; void *
0x180024422  call    memmove_0
0x180024427  mov     eax, esi
0x180024429  shr     eax, 3
0x18002442c  mov     edx, eax
0x18002442e  lea     r10, [rax+rbx]
0x180024432  mov     r11b, [r10+20h]
0x180024436  cmp     eax, 3
0x180024439  jnb     short loc_18002445A
0x18002443b  shl     byte ptr [rdx+rbx+20h], 1
0x18002443f  cmp     edx, 2
0x180024442  jnb     short loc_180024453
0x180024444  lea     eax, [rdx+1]
0x180024447  cmp     byte ptr [rax+rbx+20h], 0
0x18002444c  jge     short loc_180024453
0x18002444e  or      byte ptr [rdx+rbx+20h], 1
0x180024453  inc     edx
0x180024455  cmp     edx, 3
0x180024458  jb      short loc_18002443B
0x18002445a  test    r15d, r15d
0x18002445d  jz      short loc_18002448A
0x18002445f  and     sil, 7
0x180024463  jbe     short loc_18002448A
0x180024465  movzx   ecx, sil
0x180024469  lea     rax, qword_18004A2B8
0x180024470  sub     rax, rcx
0x180024473  mov     al, [rax]
0x180024475  and     [r10+20h], al
0x180024479  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::s_bLeftBitMasks
0x180024480  mov     al, [rcx+rax]
0x180024483  and     al, r11b
0x180024486  or      [r10+20h], al
0x18002448a  test    r12d, r12d
0x18002448d  jz      short loc_1800244B0
0x18002448f  mov     rax, [rdi+170h]
0x180024496  cmp     [rbx+168h], rax
0x18002449d  jnz     short loc_1800244B0
0x18002449f  mov     [rdi+170h], rbx
0x1800244a6  mov     dword ptr [rdi+178h], 13h
0x1800244b0  mov     rbx, [rbx+168h]
0x1800244b7  test    rbx, rbx
0x1800244ba  jnz     loc_1800243B3
0x1800244c0  mov     eax, r14d
0x1800244c3  add     rsp, 30h
0x1800244c7  pop     r15
0x1800244c9  pop     r14
0x1800244cb  pop     r12
0x1800244cd  pop     rdi
0x1800244ce  pop     rsi
0x1800244cf  pop     rbp
0x1800244d0  pop     rbx
0x1800244d1  retn
```
