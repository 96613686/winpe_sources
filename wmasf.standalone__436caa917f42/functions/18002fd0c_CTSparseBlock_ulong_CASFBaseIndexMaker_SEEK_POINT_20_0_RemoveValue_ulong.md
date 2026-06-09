# CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::RemoveValue(ulong)

- ea: `0x18002fd0c`
- end: `0x18002fea4`
- name: `?RemoveValue@?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@QEAAJK@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002fcb0`

## callees

- `0x18002fd0c`
- `0x18002feac`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::RemoveValue(
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
  __int64 v12; // xmm1_8
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r10
  char j; // r11
  unsigned __int8 v17; // si
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-48h]

  for ( i = a1; i; i = *(_QWORD *)(i + 528) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 536);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 544);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 544) = v7 - 1;
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
      if ( (*(_BYTE *)(i + 40)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::s_bSingleBitMasks) != 0 )
      {
        v12 = *(_QWORD *)(i + 64);
        v19 = *(_OWORD *)(i + 48);
        v20 = v12;
        v8 = CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::SetValue(a1, v9 - 1, &v19);
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 24 * (v11 + 2LL)), (const void *)(i + 24 * (v11 + 1 + 2LL)), 24LL * (19 - v11));
    v13 = v11 >> 3;
    v14 = v13;
    v15 = v13 + i;
    for ( j = *(_BYTE *)(v13 + i + 40); (unsigned int)v14 < 3; v14 = (unsigned int)(v14 + 1) )
    {
      *(_BYTE *)(v14 + i + 40) *= 2;
      if ( (unsigned int)v14 < 2 && *(char *)((unsigned int)(v14 + 1) + i + 40) < 0 )
        *(_BYTE *)(v14 + i + 40) |= 1u;
    }
    if ( v10 )
    {
      v17 = v11 & 7;
      if ( v17 )
      {
        *(_BYTE *)(v15 + 40) &= *((_BYTE *)&qword_18004A408 - v17);
        *(_BYTE *)(v15 + 40) |= j
                              & CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::s_bLeftBitMasks[v17];
      }
    }
    if ( v6 && *(_QWORD *)(i + 528) == *(_QWORD *)(a1 + 536) )
    {
      *(_QWORD *)(a1 + 536) = i;
      *(_DWORD *)(a1 + 544) = 19;
    }
    i = *(_QWORD *)(i + 528);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002fd0c  push    rbx
0x18002fd0e  push    rbp
0x18002fd0f  push    rsi
0x18002fd10  push    rdi
0x18002fd11  push    r12
0x18002fd13  push    r14
0x18002fd15  push    r15
0x18002fd17  sub     rsp, 40h
0x18002fd1b  mov     ebp, edx
0x18002fd1d  mov     rdi, rcx
0x18002fd20  mov     rbx, rcx
0x18002fd23  test    rcx, rcx
0x18002fd26  jz      short loc_18002FD3E
0x18002fd28  mov     eax, [rbx+8]
0x18002fd2b  add     eax, 14h
0x18002fd2e  cmp     ebp, eax
0x18002fd30  jb      short loc_18002FD3E
0x18002fd32  mov     rbx, [rbx+210h]
0x18002fd39  test    rbx, rbx
0x18002fd3c  jnz     short loc_18002FD28
0x18002fd3e  mov     rax, [rcx+218h]
0x18002fd45  xor     r12d, r12d
0x18002fd48  test    rax, rax
0x18002fd4b  jz      short loc_18002FD6F
0x18002fd4d  mov     edx, [rcx+220h]
0x18002fd53  mov     ecx, [rax+8]
0x18002fd56  add     ecx, edx
0x18002fd58  cmp     ebp, ecx
0x18002fd5a  jnb     short loc_18002FD6F
0x18002fd5c  test    edx, edx
0x18002fd5e  jnz     short loc_18002FD66
0x18002fd60  lea     r12d, [rdx+1]
0x18002fd64  jmp     short loc_18002FD6F
0x18002fd66  lea     eax, [rdx-1]
0x18002fd69  mov     [rdi+220h], eax
0x18002fd6f  xor     r14d, r14d
0x18002fd72  jmp     loc_18002FE89
0x18002fd77  mov     edx, [rbx+8]
0x18002fd7a  cmp     ebp, edx
0x18002fd7c  jb      short loc_18002FD8A
0x18002fd7e  mov     esi, ebp
0x18002fd80  mov     r15d, 1
0x18002fd86  sub     esi, edx
0x18002fd88  jmp     short loc_18002FDC8
0x18002fd8a  mov     al, [rbx+28h]
0x18002fd8d  xor     r15d, r15d
0x18002fd90  xor     esi, esi
0x18002fd92  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::s_bSingleBitMasks
0x18002fd98  jz      short loc_18002FDC8
0x18002fd9a  movups  xmm0, xmmword ptr [rbx+30h]
0x18002fd9e  lea     r8, [rsp+78h+var_58]
0x18002fda3  dec     edx
0x18002fda5  movsd   xmm1, qword ptr [rbx+40h]
0x18002fdaa  mov     rcx, rdi
0x18002fdad  movaps  [rsp+78h+var_58], xmm0
0x18002fdb2  movsd   [rsp+78h+var_48], xmm1
0x18002fdb8  call    ?SetValue@?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@QEAAJKUSEEK_POINT@CASFBaseIndexMaker@@@Z; CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::SetValue(ulong,CASFBaseIndexMaker::SEEK_POINT)
0x18002fdbd  mov     r14d, eax
0x18002fdc0  test    eax, eax
0x18002fdc2  js      loc_18002FE92
0x18002fdc8  mov     eax, 13h
0x18002fdcd  lea     ecx, [rsi+1]
0x18002fdd0  sub     eax, esi
0x18002fdd2  lea     rcx, [rcx+2]
0x18002fdd6  lea     r8, [rax+rax*2]
0x18002fdda  lea     rax, [rcx+rcx*2]
0x18002fdde  shl     r8, 3; Size
0x18002fde2  lea     rdx, [rbx+rax*8]; Src
0x18002fde6  mov     eax, esi
0x18002fde8  add     rax, 2
0x18002fdec  lea     rax, [rax+rax*2]
0x18002fdf0  lea     rcx, [rbx+rax*8]; void *
0x18002fdf4  call    memmove_0
0x18002fdf9  mov     eax, esi
0x18002fdfb  shr     eax, 3
0x18002fdfe  mov     edx, eax
0x18002fe00  lea     r10, [rax+rbx]
0x18002fe04  mov     r11b, [r10+28h]
0x18002fe08  cmp     eax, 3
0x18002fe0b  jnb     short loc_18002FE2C
0x18002fe0d  shl     byte ptr [rdx+rbx+28h], 1
0x18002fe11  cmp     edx, 2
0x18002fe14  jnb     short loc_18002FE25
0x18002fe16  lea     eax, [rdx+1]
0x18002fe19  cmp     byte ptr [rax+rbx+28h], 0
0x18002fe1e  jge     short loc_18002FE25
0x18002fe20  or      byte ptr [rdx+rbx+28h], 1
0x18002fe25  inc     edx
0x18002fe27  cmp     edx, 3
0x18002fe2a  jb      short loc_18002FE0D
0x18002fe2c  test    r15d, r15d
0x18002fe2f  jz      short loc_18002FE5C
0x18002fe31  and     sil, 7
0x18002fe35  jbe     short loc_18002FE5C
0x18002fe37  movzx   ecx, sil
0x18002fe3b  lea     rax, qword_18004A408
0x18002fe42  sub     rax, rcx
0x18002fe45  mov     al, [rax]
0x18002fe47  and     [r10+28h], al
0x18002fe4b  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::s_bLeftBitMasks
0x18002fe52  mov     al, [rcx+rax]
0x18002fe55  and     al, r11b
0x18002fe58  or      [r10+28h], al
0x18002fe5c  test    r12d, r12d
0x18002fe5f  jz      short loc_18002FE82
0x18002fe61  mov     rax, [rdi+218h]
0x18002fe68  cmp     [rbx+210h], rax
0x18002fe6f  jnz     short loc_18002FE82
0x18002fe71  mov     [rdi+218h], rbx
0x18002fe78  mov     dword ptr [rdi+220h], 13h
0x18002fe82  mov     rbx, [rbx+210h]
0x18002fe89  test    rbx, rbx
0x18002fe8c  jnz     loc_18002FD77
0x18002fe92  mov     eax, r14d
0x18002fe95  add     rsp, 40h
0x18002fe99  pop     r15
0x18002fe9b  pop     r14
0x18002fe9d  pop     r12
0x18002fe9f  pop     rdi
0x18002fea0  pop     rsi
0x18002fea1  pop     rbp
0x18002fea2  pop     rbx
0x18002fea3  retn
```
