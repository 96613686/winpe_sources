# CTSparseBlock<ulong,CASFMarker::MARKER_NAME_REC,20,0>::RemoveValue(ulong)

- ea: `0x180029190`
- end: `0x18002931a`
- name: `?RemoveValue@?$CTSparseBlock@KUMARKER_NAME_REC@CASFMarker@@$0BE@$0A@@@QEAAJK@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028ebc`

## callees

- `0x180029190`
- `0x180029720`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFMarker::MARKER_NAME_REC,20,0>::RemoveValue(
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
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFMarker::MARKER_NAME_REC,20,0>::s_bSingleBitMasks) != 0 )
      {
        v18[0] = *(_OWORD *)(i + 40);
        v8 = CTSparseBlock<unsigned long,CASFMarker::MARKER_NAME_REC,20,0>::SetValue(a1, v9 - 1, v18);
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
        *(_BYTE *)(v14 + 32) &= *((_BYTE *)&qword_18004A370 - v16);
        *(_BYTE *)(v14 + 32) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFMarker::MARKER_NAME_REC,20,0>::s_bLeftBitMasks
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
0x180029190  push    rbx
0x180029192  push    rbp
0x180029193  push    rsi
0x180029194  push    rdi
0x180029195  push    r12
0x180029197  push    r14
0x180029199  push    r15
0x18002919b  sub     rsp, 30h
0x18002919f  mov     ebp, edx
0x1800291a1  mov     rdi, rcx
0x1800291a4  mov     rbx, rcx
0x1800291a7  test    rcx, rcx
0x1800291aa  jz      short loc_1800291C2
0x1800291ac  mov     eax, [rbx+8]
0x1800291af  add     eax, 14h
0x1800291b2  cmp     ebp, eax
0x1800291b4  jb      short loc_1800291C2
0x1800291b6  mov     rbx, [rbx+168h]
0x1800291bd  test    rbx, rbx
0x1800291c0  jnz     short loc_1800291AC
0x1800291c2  mov     rax, [rcx+170h]
0x1800291c9  xor     r12d, r12d
0x1800291cc  test    rax, rax
0x1800291cf  jz      short loc_1800291F3
0x1800291d1  mov     edx, [rcx+178h]
0x1800291d7  mov     ecx, [rax+8]
0x1800291da  add     ecx, edx
0x1800291dc  cmp     ebp, ecx
0x1800291de  jnb     short loc_1800291F3
0x1800291e0  test    edx, edx
0x1800291e2  jnz     short loc_1800291EA
0x1800291e4  lea     r12d, [rdx+1]
0x1800291e8  jmp     short loc_1800291F3
0x1800291ea  lea     eax, [rdx-1]
0x1800291ed  mov     [rdi+178h], eax
0x1800291f3  xor     r14d, r14d
0x1800291f6  jmp     loc_1800292FF
0x1800291fb  mov     edx, [rbx+8]
0x1800291fe  cmp     ebp, edx
0x180029200  jb      short loc_18002920E
0x180029202  mov     esi, ebp
0x180029204  mov     r15d, 1
0x18002920a  sub     esi, edx
0x18002920c  jmp     short loc_180029242
0x18002920e  mov     al, [rbx+20h]
0x180029211  xor     r15d, r15d
0x180029214  xor     esi, esi
0x180029216  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUMARKER_NAME_REC@CASFMarker@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFMarker::MARKER_NAME_REC,20,0>::s_bSingleBitMasks
0x18002921c  jz      short loc_180029242
0x18002921e  movups  xmm0, xmmword ptr [rbx+28h]
0x180029222  dec     edx
0x180029224  lea     r8, [rsp+68h+var_48]
0x180029229  mov     rcx, rdi
0x18002922c  movdqu  [rsp+68h+var_48], xmm0
0x180029232  call    ?SetValue@?$CTSparseBlock@KUMARKER_NAME_REC@CASFMarker@@$0BE@$0A@@@QEAAJKUMARKER_NAME_REC@CASFMarker@@@Z; CTSparseBlock<ulong,CASFMarker::MARKER_NAME_REC,20,0>::SetValue(ulong,CASFMarker::MARKER_NAME_REC)
0x180029237  mov     r14d, eax
0x18002923a  test    eax, eax
0x18002923c  js      loc_180029308
0x180029242  mov     r8d, 13h
0x180029248  mov     ecx, esi
0x18002924a  shl     rcx, 4
0x18002924e  lea     edx, [rsi+1]
0x180029251  shl     rdx, 4
0x180029255  add     rcx, 28h ; '('
0x180029259  add     rdx, 28h ; '('
0x18002925d  sub     r8d, esi
0x180029260  add     rdx, rbx; Src
0x180029263  shl     r8, 4; Size
0x180029267  add     rcx, rbx; void *
0x18002926a  call    memmove_0
0x18002926f  mov     eax, esi
0x180029271  shr     eax, 3
0x180029274  mov     edx, eax
0x180029276  lea     r10, [rax+rbx]
0x18002927a  mov     r11b, [r10+20h]
0x18002927e  cmp     eax, 3
0x180029281  jnb     short loc_1800292A2
0x180029283  shl     byte ptr [rdx+rbx+20h], 1
0x180029287  cmp     edx, 2
0x18002928a  jnb     short loc_18002929B
0x18002928c  lea     eax, [rdx+1]
0x18002928f  cmp     byte ptr [rax+rbx+20h], 0
0x180029294  jge     short loc_18002929B
0x180029296  or      byte ptr [rdx+rbx+20h], 1
0x18002929b  inc     edx
0x18002929d  cmp     edx, 3
0x1800292a0  jb      short loc_180029283
0x1800292a2  test    r15d, r15d
0x1800292a5  jz      short loc_1800292D2
0x1800292a7  and     sil, 7
0x1800292ab  jbe     short loc_1800292D2
0x1800292ad  movzx   ecx, sil
0x1800292b1  lea     rax, qword_18004A370
0x1800292b8  sub     rax, rcx
0x1800292bb  mov     al, [rax]
0x1800292bd  and     [r10+20h], al
0x1800292c1  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUMARKER_NAME_REC@CASFMarker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFMarker::MARKER_NAME_REC,20,0>::s_bLeftBitMasks
0x1800292c8  mov     al, [rcx+rax]
0x1800292cb  and     al, r11b
0x1800292ce  or      [r10+20h], al
0x1800292d2  test    r12d, r12d
0x1800292d5  jz      short loc_1800292F8
0x1800292d7  mov     rax, [rdi+170h]
0x1800292de  cmp     [rbx+168h], rax
0x1800292e5  jnz     short loc_1800292F8
0x1800292e7  mov     [rdi+170h], rbx
0x1800292ee  mov     dword ptr [rdi+178h], 13h
0x1800292f8  mov     rbx, [rbx+168h]
0x1800292ff  test    rbx, rbx
0x180029302  jnz     loc_1800291FB
0x180029308  mov     eax, r14d
0x18002930b  add     rsp, 30h
0x18002930f  pop     r15
0x180029311  pop     r14
0x180029313  pop     r12
0x180029315  pop     rdi
0x180029316  pop     rsi
0x180029317  pop     rbp
0x180029318  pop     rbx
0x180029319  retn
```
