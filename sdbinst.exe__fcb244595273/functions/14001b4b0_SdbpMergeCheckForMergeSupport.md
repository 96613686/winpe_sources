# SdbpMergeCheckForMergeSupport

- ea: `0x14001b4b0`
- end: `0x14001b7e0`
- name: `SdbpMergeCheckForMergeSupport`
- size: `816`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x140013cb8`
- `0x140013d54`
- `0x140014380`
- `0x1400143d8`
- `0x14001b4b0`
- `0x14002e3d6`

## string_xrefs

- `0x14001b63d`: `Failed to read original database guid from tagid`
- `0x14001b74f`: `Failed to read to-merge database guid from tagid`

## pseudocode

```c
__int64 __fastcall SdbpMergeCheckForMergeSupport(__int64 a1, __int64 a2, _DWORD *a3)
{
  int *v3; // rax
  _DWORD *v5; // r10
  int v7; // r9d
  unsigned int FirstTag; // eax
  unsigned int v10; // r15d
  int v11; // r13d
  unsigned int FirstTagBefore; // r12d
  BOOL v13; // r14d
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // r15d
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int128 Buf2; // [rsp+20h] [rbp-58h] BYREF
  __int128 v22; // [rsp+30h] [rbp-48h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-38h] BYREF
  __int128 v24; // [rsp+50h] [rbp-28h] BYREF

  v3 = *(int **)(a2 + 8);
  v5 = *(_DWORD **)(a1 + 8);
  Buf2 = 0;
  v7 = *v3;
  *a3 = 0;
  if ( *v5 != v7 )
  {
    AslLogCallPrintf(
      3,
      "SdbpMergeCheckForMergeSupport",
      2154,
      "Unable to merge SDB files with different versions",
      Buf2);
    return 3221225659LL;
  }
  FirstTag = SdbFindFirstTag(a1, 0, 28673);
  v10 = FirstTag;
  if ( !FirstTag )
  {
    AslLogCallPrintf(1, "SdbpMergeCheckForMergeSupport", 2164, "Failed to find TAG_DATABASE in original SDB", Buf2);
    return 3221225700LL;
  }
  v11 = 0;
  FirstTagBefore = SdbFindFirstTagBefore(a1, FirstTag, 36878);
  if ( !FirstTagBefore )
  {
    FirstTagBefore = SdbFindFirstTagBefore(a1, v10, 36871);
    if ( !FirstTagBefore )
    {
      AslLogCallPrintf(1, "SdbpMergeCheckForMergeSupport", 2173, "Failed to find the database ID in original SDB", Buf2);
      return 3221225816LL;
    }
    v11 = 1;
  }
  v13 = 0;
  v14 = SdbFindFirstTagBefore(a1, v10, 16478);
  if ( v14 )
  {
    if ( (unsigned int)SdbReadDWORDTag(a1, v14, 0) )
    {
      v15 = SdbFindFirstTagBefore(a1, v10, 16479);
      if ( v15 )
        v13 = SdbReadDWORDTag(a1, v15, 0) != 0;
    }
  }
  Buf1 = 0;
  Buf1 = *SdbReadGUIDTag(&v22, a1, FirstTagBefore, &Buf1);
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    AslLogCallPrintf(1, "SdbpMergeCheckForMergeSupport", 2202, "Failed to read original database guid from tagid", Buf2);
    return 3221225701LL;
  }
  v16 = SdbFindFirstTag(a2, 0, 28673);
  v17 = v16;
  if ( !v16 )
  {
    AslLogCallPrintf(1, "SdbpMergeCheckForMergeSupport", 2212, "Failed to find TAG_DATABASE in to-merge SDB", Buf2);
    return 3221225700LL;
  }
  v18 = SdbFindFirstTagBefore(a2, v16, 36878);
  if ( !v18 )
  {
    v18 = SdbFindFirstTagBefore(a2, v17, 36871);
    if ( !v18 )
    {
      AslLogCallPrintf(1, "SdbpMergeCheckForMergeSupport", 2221, "Failed to find the database ID in to-merge SDB", Buf2);
      return 3221225816LL;
    }
    v11 = 1;
  }
  v19 = SdbFindFirstTagBefore(a2, v17, 16478);
  if ( v19 )
  {
    if ( (unsigned int)SdbReadDWORDTag(a2, v19, 0) )
    {
      v20 = SdbFindFirstTagBefore(a2, v17, 16479);
      if ( v20 )
      {
        if ( (unsigned int)SdbReadDWORDTag(a2, v20, 0) )
          v13 = 1;
      }
    }
  }
  v22 = 0;
  v22 = *SdbReadGUIDTag(&v24, a2, v18, &v22);
  if ( !memcmp_0(&v22, &Buf2, 0x10u) )
  {
    AslLogCallPrintf(1, "SdbpMergeCheckForMergeSupport", 2250, "Failed to read to-merge database guid from tagid", Buf2);
    return 3221225701LL;
  }
  if ( !memcmp_0(&Buf1, &v22, 0x10u) )
  {
    if ( v11 )
    {
      if ( v13 )
        *a3 = 1;
    }
    AslLogCallPrintf(3, "SdbpMergeCheckForMergeSupport", 2263, "SdbMerge: Both databases have the same target ID", Buf2);
    return 0;
  }
  else
  {
    AslLogCallPrintf(3, "SdbpMergeCheckForMergeSupport", 2255, "Shim databases have different database ID values", Buf2);
    return 3221225508LL;
  }
}

```

## disassembly

```asm
0x14001b4b0  mov     [rsp-40h+arg_10], r8
0x14001b4b5  push    rbp
0x14001b4b6  push    rbx
0x14001b4b7  push    rsi
0x14001b4b8  push    rdi
0x14001b4b9  push    r12
0x14001b4bb  push    r13
0x14001b4bd  push    r14
0x14001b4bf  push    r15
0x14001b4c1  mov     rbp, rsp
0x14001b4c4  sub     rsp, 78h
0x14001b4c8  mov     rax, [rdx+8]
0x14001b4cc  mov     rsi, rdx
0x14001b4cf  mov     r10, [rcx+8]
0x14001b4d3  mov     rdi, rcx
0x14001b4d6  movaps  [rsp+78h+var_18], xmm6
0x14001b4db  xorps   xmm6, xmm6
0x14001b4de  movaps  [rbp+Buf2], xmm6
0x14001b4e2  mov     r9d, [rax]
0x14001b4e5  mov     dword ptr [r8], 0
0x14001b4ec  cmp     [r10], r9d
0x14001b4ef  jz      short loc_14001B519
0x14001b4f1  lea     r9, aUnableToMergeS; "Unable to merge SDB files with differen"...
0x14001b4f8  mov     r8d, 86Ah
0x14001b4fe  lea     rdx, aSdbpmergecheck; "SdbpMergeCheckForMergeSupport"
0x14001b505  mov     ecx, 3
0x14001b50a  call    AslLogCallPrintf
0x14001b50f  mov     eax, 0C00000BBh
0x14001b514  jmp     loc_14001B7CA
0x14001b519  xor     edx, edx
0x14001b51b  mov     r8d, 7001h
0x14001b521  call    SdbFindFirstTag
0x14001b526  mov     r15d, eax
0x14001b529  test    eax, eax
0x14001b52b  jnz     short loc_14001B553
0x14001b52d  lea     r9, aFailedToFindTa_4; "Failed to find TAG_DATABASE in original"...
0x14001b534  mov     r8d, 874h
0x14001b53a  lea     ecx, [rax+1]
0x14001b53d  lea     rdx, aSdbpmergecheck; "SdbpMergeCheckForMergeSupport"
0x14001b544  call    AslLogCallPrintf
0x14001b549  mov     eax, 0C00000E4h
0x14001b54e  jmp     loc_14001B7CA
0x14001b553  mov     r8d, 900Eh
0x14001b559  mov     edx, r15d
0x14001b55c  mov     rcx, rdi
0x14001b55f  xor     r13d, r13d
0x14001b562  call    SdbFindFirstTagBefore
0x14001b567  lea     ebx, [r13+1]
0x14001b56b  mov     r12d, eax
0x14001b56e  test    eax, eax
0x14001b570  jnz     short loc_14001B5B2
0x14001b572  mov     r8d, 9007h
0x14001b578  mov     edx, r15d
0x14001b57b  mov     rcx, rdi
0x14001b57e  call    SdbFindFirstTagBefore
0x14001b583  mov     r12d, eax
0x14001b586  test    eax, eax
0x14001b588  jnz     short loc_14001B5AF
0x14001b58a  lea     r9, aFailedToFindTh_2; "Failed to find the database ID in origi"...
0x14001b591  mov     r8d, 87Dh
0x14001b597  lea     rdx, aSdbpmergecheck; "SdbpMergeCheckForMergeSupport"
0x14001b59e  mov     ecx, ebx
0x14001b5a0  call    AslLogCallPrintf
0x14001b5a5  mov     eax, 0C0000158h
0x14001b5aa  jmp     loc_14001B7CA
0x14001b5af  mov     r13d, ebx
0x14001b5b2  mov     r8d, 405Eh
0x14001b5b8  mov     edx, r15d
0x14001b5bb  mov     rcx, rdi
0x14001b5be  xor     r14d, r14d
0x14001b5c1  call    SdbFindFirstTagBefore
0x14001b5c6  test    eax, eax
0x14001b5c8  jz      short loc_14001B603
0x14001b5ca  xor     r8d, r8d
0x14001b5cd  mov     edx, eax
0x14001b5cf  mov     rcx, rdi
0x14001b5d2  call    SdbReadDWORDTag
0x14001b5d7  test    eax, eax
0x14001b5d9  jz      short loc_14001B603
0x14001b5db  mov     r8d, 405Fh
0x14001b5e1  mov     edx, r15d
0x14001b5e4  mov     rcx, rdi
0x14001b5e7  call    SdbFindFirstTagBefore
0x14001b5ec  test    eax, eax
0x14001b5ee  jz      short loc_14001B603
0x14001b5f0  xor     r8d, r8d
0x14001b5f3  mov     edx, eax
0x14001b5f5  mov     rcx, rdi
0x14001b5f8  call    SdbReadDWORDTag
0x14001b5fd  test    eax, eax
0x14001b5ff  cmovnz  r14d, ebx
0x14001b603  lea     r9, [rbp+Buf1]
0x14001b607  movdqa  [rbp+Buf1], xmm6
0x14001b60c  mov     r8d, r12d
0x14001b60f  lea     rcx, [rbp+var_48]
0x14001b613  mov     rdx, rdi
0x14001b616  call    SdbReadGUIDTag
0x14001b61b  mov     r12d, 10h
0x14001b621  lea     rdx, [rbp+Buf2]; Buf2
0x14001b625  mov     r8d, r12d; Size
0x14001b628  lea     rcx, [rbp+Buf1]; Buf1
0x14001b62c  movups  xmm0, xmmword ptr [rax]
0x14001b62f  movdqu  [rbp+Buf1], xmm0
0x14001b634  call    memcmp_0
0x14001b639  test    eax, eax
0x14001b63b  jnz     short loc_14001B662
0x14001b63d  lea     r9, aFailedToReadOr; "Failed to read original database guid f"...
0x14001b644  mov     r8d, 89Ah
0x14001b64a  lea     rdx, aSdbpmergecheck; "SdbpMergeCheckForMergeSupport"
0x14001b651  mov     ecx, ebx
0x14001b653  call    AslLogCallPrintf
0x14001b658  mov     eax, 0C00000E5h
0x14001b65d  jmp     loc_14001B7CA
0x14001b662  xor     edx, edx
0x14001b664  mov     r8d, 7001h
0x14001b66a  mov     rcx, rsi
0x14001b66d  call    SdbFindFirstTag
0x14001b672  mov     edi, eax
0x14001b674  test    eax, eax
0x14001b676  jnz     short loc_14001B68C
0x14001b678  lea     r9, aFailedToFindTa_6; "Failed to find TAG_DATABASE in to-merge"...
0x14001b67f  mov     r8d, 8A4h
0x14001b685  mov     ecx, ebx
0x14001b687  jmp     loc_14001B53D
0x14001b68c  mov     r8d, 900Eh
0x14001b692  mov     edx, edi
0x14001b694  mov     rcx, rsi
0x14001b697  call    SdbFindFirstTagBefore
0x14001b69c  mov     r15d, eax
0x14001b69f  test    eax, eax
0x14001b6a1  jnz     short loc_14001B6CF
0x14001b6a3  mov     r8d, 9007h
0x14001b6a9  mov     edx, edi
0x14001b6ab  mov     rcx, rsi
0x14001b6ae  call    SdbFindFirstTagBefore
0x14001b6b3  mov     r15d, eax
0x14001b6b6  test    eax, eax
0x14001b6b8  jnz     short loc_14001B6CC
0x14001b6ba  lea     r9, aFailedToFindTh_1; "Failed to find the database ID in to-me"...
0x14001b6c1  mov     r8d, 8ADh
0x14001b6c7  jmp     loc_14001B597
0x14001b6cc  mov     r13d, ebx
0x14001b6cf  mov     r8d, 405Eh
0x14001b6d5  mov     edx, edi
0x14001b6d7  mov     rcx, rsi
0x14001b6da  call    SdbFindFirstTagBefore
0x14001b6df  test    eax, eax
0x14001b6e1  jz      short loc_14001B71B
0x14001b6e3  xor     r8d, r8d
0x14001b6e6  mov     edx, eax
0x14001b6e8  mov     rcx, rsi
0x14001b6eb  call    SdbReadDWORDTag
0x14001b6f0  test    eax, eax
0x14001b6f2  jz      short loc_14001B71B
0x14001b6f4  mov     r8d, 405Fh
0x14001b6fa  mov     edx, edi
0x14001b6fc  mov     rcx, rsi
0x14001b6ff  call    SdbFindFirstTagBefore
0x14001b704  test    eax, eax
0x14001b706  jz      short loc_14001B71B
0x14001b708  xor     r8d, r8d
0x14001b70b  mov     edx, eax
0x14001b70d  mov     rcx, rsi
0x14001b710  call    SdbReadDWORDTag
0x14001b715  test    eax, eax
0x14001b717  cmovnz  r14d, ebx
0x14001b71b  lea     r9, [rbp+var_48]
0x14001b71f  movdqa  [rbp+var_48], xmm6
0x14001b724  mov     r8d, r15d
0x14001b727  lea     rcx, [rbp+var_28]
0x14001b72b  mov     rdx, rsi
0x14001b72e  call    SdbReadGUIDTag
0x14001b733  mov     r8, r12; Size
0x14001b736  lea     rdx, [rbp+Buf2]; Buf2
0x14001b73a  lea     rcx, [rbp+var_48]; Buf1
0x14001b73e  movups  xmm0, xmmword ptr [rax]
0x14001b741  movdqu  [rbp+var_48], xmm0
0x14001b746  call    memcmp_0
0x14001b74b  test    eax, eax
0x14001b74d  jnz     short loc_14001B761
0x14001b74f  lea     r9, aFailedToReadTo; "Failed to read to-merge database guid f"...
0x14001b756  mov     r8d, 8CAh
0x14001b75c  jmp     loc_14001B64A
0x14001b761  mov     r8, r12; Size
0x14001b764  lea     rdx, [rbp+var_48]; Buf2
0x14001b768  lea     rcx, [rbp+Buf1]; Buf1
0x14001b76c  call    memcmp_0
0x14001b771  test    eax, eax
0x14001b773  jz      short loc_14001B79A
0x14001b775  lea     r9, aShimDatabasesH; "Shim databases have different database "...
0x14001b77c  mov     r8d, 8CFh
0x14001b782  lea     rdx, aSdbpmergecheck; "SdbpMergeCheckForMergeSupport"
0x14001b789  mov     ecx, 3
0x14001b78e  call    AslLogCallPrintf
0x14001b793  mov     eax, 0C0000024h
0x14001b798  jmp     short loc_14001B7CA
0x14001b79a  test    r13d, r13d
0x14001b79d  jz      short loc_14001B7AA
0x14001b79f  test    r14d, r14d
0x14001b7a2  jz      short loc_14001B7AA
0x14001b7a4  mov     rax, [rbp+arg_10]
0x14001b7a8  mov     [rax], ebx
0x14001b7aa  lea     r9, aSdbmergeBothDa; "SdbMerge: Both databases have the same "...
0x14001b7b1  mov     r8d, 8D7h
0x14001b7b7  lea     rdx, aSdbpmergecheck; "SdbpMergeCheckForMergeSupport"
0x14001b7be  mov     ecx, 3
0x14001b7c3  call    AslLogCallPrintf
0x14001b7c8  xor     eax, eax
0x14001b7ca  movaps  xmm6, [rsp+78h+var_18]
0x14001b7cf  add     rsp, 78h
0x14001b7d3  pop     r15
0x14001b7d5  pop     r14
0x14001b7d7  pop     r13
0x14001b7d9  pop     r12
0x14001b7db  pop     rdi
0x14001b7dc  pop     rsi
0x14001b7dd  pop     rbx
0x14001b7de  pop     rbp
0x14001b7df  retn
```
