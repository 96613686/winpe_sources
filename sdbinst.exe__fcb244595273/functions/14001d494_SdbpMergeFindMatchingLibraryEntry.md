# SdbpMergeFindMatchingLibraryEntry

- ea: `0x14001d494`
- end: `0x14001d800`
- name: `SdbpMergeFindMatchingLibraryEntry`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x140013cb8`
- `0x140014380`
- `0x14001443c`
- `0x140016148`
- `0x14001b2f0`
- `0x14001d494`

## string_xrefs

- `0x14001d5ed`: `Failed to read the tagid contained in the source TAGID ref`

## pseudocode

```c
__int64 __fastcall SdbpMergeFindMatchingLibraryEntry(__int64 **a1, unsigned int *a2, unsigned int *a3, _WORD *a4)
{
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // ecx
  __int64 *v12; // r14
  unsigned __int16 TagFromTagID; // r9
  unsigned int v14; // esi
  int v15; // eax
  __int16 *v16; // rdi
  unsigned int DWORDTag; // eax
  unsigned __int16 v18; // ax
  int v19; // edx
  unsigned int v20; // edx
  __int64 v21; // r13
  unsigned int v22; // ebp
  unsigned __int64 i; // rbx
  __int16 v24; // r8
  unsigned int NextTag; // ebx
  unsigned int v26; // eax
  unsigned int FirstTag; // [rsp+80h] [rbp+8h]

  if ( !a1 )
    return 3221225711LL;
  if ( !a2 )
    return 3221225712LL;
  v9 = *a2;
  if ( !(_DWORD)v9 || !a2[2] )
    return 3221225712LL;
  if ( !a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  v10 = (int)(a2[1] << 28) >> 28;
  *a3 = 0;
  *a4 = 0;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
      {
LABEL_17:
        AslLogCallPrintf(
          1,
          "SdbpMergeFindMatchingLibraryEntry",
          579,
          "RefSource was invalid. Failed to find the lookup source context.");
        return 3221227787LL;
      }
      v12 = a1[2];
    }
    else
    {
      v12 = a1[1];
    }
  }
  else
  {
    v12 = *a1;
  }
  if ( !v12 )
    goto LABEL_17;
  TagFromTagID = SdbGetTagFromTagID(*v12, v9);
  if ( (int)(a2[1] << 24) >> 28 == 1 )
  {
    DWORDTag = SdbReadDWORDTag(*v12, *a2, 0x20000000u);
    v14 = DWORDTag;
    if ( DWORDTag == 0x20000000 )
    {
      AslLogCallPrintf(
        1,
        "SdbpMergeFindMatchingLibraryEntry",
        596,
        "Failed to read the tagid contained in the source TAGID ref");
      return 3221225816LL;
    }
    if ( !DWORDTag )
    {
      AslLogCallPrintf(
        1,
        "SdbpMergeFindMatchingLibraryEntry",
        601,
        "TAGID source reference contained a TAGID_NULL value");
      return 3221226021LL;
    }
    v18 = SdbGetTagFromTagID(*v12, DWORDTag);
    TagFromTagID = v18;
    v19 = 0;
    while ( 1 )
    {
      v16 = (__int16 *)&qword_1400362C0[2 * v19];
      if ( *v16 == v18 )
        break;
      if ( (unsigned int)++v19 >= 0xD )
      {
LABEL_36:
        v16 = 0;
        break;
      }
    }
  }
  else
  {
    if ( (int)(a2[1] << 24) >> 28 != 2 )
    {
      AslLogCallPrintf(
        1,
        "SdbpMergeFindMatchingLibraryEntry",
        617,
        "Unknown reference kind encountered in TAGID 'ref to fix': %d",
        (int)(a2[1] << 24) >> 28);
      return 3221227787LL;
    }
    v14 = 0;
    v15 = 0;
    while ( WORD1(qword_1400362C0[2 * v15]) != TagFromTagID )
    {
      if ( (unsigned int)++v15 >= 0xD )
        goto LABEL_36;
    }
    v16 = (__int16 *)&qword_1400362C0[2 * v15];
  }
  if ( !v16 )
  {
    AslLogCallPrintf(
      1,
      "SdbpMergeFindMatchingLibraryEntry",
      625,
      "Failed to find the merge info from the source ref/def (tag '0x%04X' kind '%d') source TAGID: 0x%08X",
      TagFromTagID,
      (int)(a2[1] << 24) >> 28,
      *a2);
    return 3221227787LL;
  }
  v20 = v14;
  if ( !v14 )
    v20 = *a2;
  FirstTag = SdbFindFirstTag(*v12, v20, *(__int16 *)((char *)v16 + (-(__int64)(v14 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 8));
  if ( !FirstTag )
  {
    AslLogCallPrintf(
      1,
      "SdbpMergeFindMatchingLibraryEntry",
      642,
      "The source ref/def did not have the expected search-for tag (TAG_NAME)");
    return 3221225816LL;
  }
  *a4 = v16[2];
  v21 = *a1[2];
  v22 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v24 = v16[i + 5];
    if ( !v24 )
      break;
    v22 = SdbFindFirstTag(v21, v22, v24);
    if ( !v22 )
      goto LABEL_48;
  }
  if ( !v22 )
  {
LABEL_48:
    AslLogCallPrintf(
      3,
      "SdbpMergeFindMatchingLibraryEntry",
      655,
      "Failed to find the parent tagid that should hold the definition that is being sought after");
LABEL_49:
    *a3 = (unsigned __int16)v16[2];
    *a4 = 16477;
    return 3221226021LL;
  }
  NextTag = SdbFindFirstTag(*a1[2], v22, *v16);
  if ( !NextTag )
    goto LABEL_49;
  while ( 1 )
  {
    v26 = SdbFindFirstTag(*a1[2], NextTag, v16[3]);
    if ( v26 )
    {
      if ( SdbpMergeAreTagValuesEqual(*a1[2], v26, *v12, FirstTag, v14 != 0) )
        break;
    }
    NextTag = SdbFindNextTag(*a1[2], v22, NextTag);
    if ( !NextTag )
      goto LABEL_49;
  }
  *a3 = NextTag;
  return 0;
}

```

## disassembly

```asm
0x14001d494  mov     [rsp+arg_8], rbx
0x14001d499  mov     [rsp+arg_18], r9
0x14001d49e  push    rbp
0x14001d49f  push    rsi
0x14001d4a0  push    rdi
0x14001d4a1  push    r12
0x14001d4a3  push    r13
0x14001d4a5  push    r14
0x14001d4a7  push    r15
0x14001d4a9  sub     rsp, 40h
0x14001d4ad  xor     r13d, r13d
0x14001d4b0  mov     rbp, r9
0x14001d4b3  mov     r12, r8
0x14001d4b6  mov     rbx, rdx
0x14001d4b9  mov     r15, rcx
0x14001d4bc  test    rcx, rcx
0x14001d4bf  jnz     short loc_14001D4CB
0x14001d4c1  mov     eax, 0C00000EFh
0x14001d4c6  jmp     loc_14001D7E8
0x14001d4cb  test    rbx, rbx
0x14001d4ce  jz      loc_14001D7E3
0x14001d4d4  mov     edx, [rdx]
0x14001d4d6  test    edx, edx
0x14001d4d8  jz      loc_14001D7E3
0x14001d4de  cmp     [rbx+8], r13d
0x14001d4e2  jz      loc_14001D7E3
0x14001d4e8  test    r12, r12
0x14001d4eb  jnz     short loc_14001D4F7
0x14001d4ed  mov     eax, 0C00000F1h
0x14001d4f2  jmp     loc_14001D7E8
0x14001d4f7  test    rbp, rbp
0x14001d4fa  jnz     short loc_14001D506
0x14001d4fc  mov     eax, 0C00000F2h
0x14001d501  jmp     loc_14001D7E8
0x14001d506  mov     ecx, [rbx+4]
0x14001d509  shl     ecx, 1Ch
0x14001d50c  sar     ecx, 1Ch
0x14001d50f  mov     [r8], r13d
0x14001d512  mov     [r9], r13w
0x14001d516  test    ecx, ecx
0x14001d518  jz      short loc_14001D530
0x14001d51a  sub     ecx, 1
0x14001d51d  jz      short loc_14001D52A
0x14001d51f  cmp     ecx, 1
0x14001d522  jnz     short loc_14001D538
0x14001d524  mov     r14, [r15+10h]
0x14001d528  jmp     short loc_14001D533
0x14001d52a  mov     r14, [r15+8]
0x14001d52e  jmp     short loc_14001D533
0x14001d530  mov     r14, [r15]
0x14001d533  test    r14, r14
0x14001d536  jnz     short loc_14001D560
0x14001d538  lea     r9, aRefsourceWasIn; "RefSource was invalid. Failed to find t"...
0x14001d53f  mov     r8d, 243h
0x14001d545  lea     rdx, aSdbpmergefindm; "SdbpMergeFindMatchingLibraryEntry"
0x14001d54c  mov     ecx, 1
0x14001d551  call    AslLogCallPrintf
0x14001d556  mov     eax, 0C000090Bh
0x14001d55b  jmp     loc_14001D7E8
0x14001d560  mov     rcx, [r14]
0x14001d563  call    SdbGetTagFromTagID
0x14001d568  mov     ecx, [rbx+4]
0x14001d56b  movzx   r9d, ax
0x14001d56f  shl     ecx, 18h
0x14001d572  sar     ecx, 1Ch
0x14001d575  mov     edx, ecx
0x14001d577  sub     edx, 1
0x14001d57a  jz      short loc_14001D5D5
0x14001d57c  cmp     edx, 1
0x14001d57f  jz      short loc_14001D5A5
0x14001d581  mov     [rsp+78h+var_58], ecx
0x14001d585  lea     r9, aUnknownReferen; "Unknown reference kind encountered in T"...
0x14001d58c  mov     ecx, 1
0x14001d591  lea     rdx, aSdbpmergefindm; "SdbpMergeFindMatchingLibraryEntry"
0x14001d598  mov     r8d, 269h
0x14001d59e  call    AslLogCallPrintf
0x14001d5a3  jmp     short loc_14001D556
0x14001d5a5  mov     esi, r13d
0x14001d5a8  lea     r8, qword_1400362C0
0x14001d5af  mov     eax, r13d
0x14001d5b2  movsxd  rcx, eax
0x14001d5b5  add     rcx, rcx
0x14001d5b8  cmp     [r8+rcx*8+2], r9w
0x14001d5be  jz      short loc_14001D5CC
0x14001d5c0  inc     eax
0x14001d5c2  cmp     eax, 0Dh
0x14001d5c5  jb      short loc_14001D5B2
0x14001d5c7  jmp     loc_14001D66D
0x14001d5cc  lea     rdi, [r8+rcx*8]
0x14001d5d0  jmp     loc_14001D670
0x14001d5d5  mov     edx, [rbx]
0x14001d5d7  mov     edi, 20000000h
0x14001d5dc  mov     rcx, [r14]
0x14001d5df  mov     r8d, edi
0x14001d5e2  call    SdbReadDWORDTag
0x14001d5e7  mov     esi, eax
0x14001d5e9  cmp     eax, edi
0x14001d5eb  jnz     short loc_14001D615
0x14001d5ed  lea     r9, aFailedToReadTh_0; "Failed to read the tagid contained in t"...
0x14001d5f4  mov     r8d, 254h
0x14001d5fa  lea     rdx, aSdbpmergefindm; "SdbpMergeFindMatchingLibraryEntry"
0x14001d601  mov     ecx, 1
0x14001d606  call    AslLogCallPrintf
0x14001d60b  mov     eax, 0C0000158h
0x14001d610  jmp     loc_14001D7E8
0x14001d615  test    eax, eax
0x14001d617  jnz     short loc_14001D63F
0x14001d619  lea     r9, aTagidSourceRef; "TAGID source reference contained a TAGI"...
0x14001d620  mov     r8d, 259h
0x14001d626  lea     rdx, aSdbpmergefindm; "SdbpMergeFindMatchingLibraryEntry"
0x14001d62d  lea     ecx, [rax+1]
0x14001d630  call    AslLogCallPrintf
0x14001d635  mov     eax, 0C0000225h
0x14001d63a  jmp     loc_14001D7E8
0x14001d63f  mov     rcx, [r14]
0x14001d642  mov     edx, eax
0x14001d644  call    SdbGetTagFromTagID
0x14001d649  movzx   r9d, ax
0x14001d64d  lea     r8, qword_1400362C0
0x14001d654  mov     edx, r13d
0x14001d657  movsxd  rdi, edx
0x14001d65a  shl     rdi, 4
0x14001d65e  add     rdi, r8
0x14001d661  cmp     [rdi], ax
0x14001d664  jz      short loc_14001D670
0x14001d666  inc     edx
0x14001d668  cmp     edx, 0Dh
0x14001d66b  jb      short loc_14001D657
0x14001d66d  mov     rdi, r13
0x14001d670  test    rdi, rdi
0x14001d673  jnz     short loc_14001D6B1
0x14001d675  mov     edx, [rbx+4]
0x14001d678  mov     r8d, 271h
0x14001d67e  mov     eax, [rbx]
0x14001d680  movzx   ecx, r9w
0x14001d684  lea     r9, aFailedToFindTh_0; "Failed to find the merge info from the "...
0x14001d68b  shl     edx, 18h
0x14001d68e  sar     edx, 1Ch
0x14001d691  mov     [rsp+78h+var_48], eax
0x14001d695  mov     [rsp+78h+var_50], edx
0x14001d699  lea     rdx, aSdbpmergefindm; "SdbpMergeFindMatchingLibraryEntry"
0x14001d6a0  mov     [rsp+78h+var_58], ecx
0x14001d6a4  lea     ecx, [rdi+1]
0x14001d6a7  call    AslLogCallPrintf
0x14001d6ac  jmp     loc_14001D556
0x14001d6b1  mov     edx, esi
0x14001d6b3  test    esi, esi
0x14001d6b5  jnz     short loc_14001D6B9
0x14001d6b7  mov     edx, [rbx]
0x14001d6b9  mov     rcx, [r14]
0x14001d6bc  mov     eax, esi
0x14001d6be  neg     eax
0x14001d6c0  sbb     r8, r8
0x14001d6c3  and     r8, 0FFFFFFFFFFFFFFFEh
0x14001d6c7  movzx   r8d, word ptr [r8+rdi+8]
0x14001d6cd  call    SdbFindFirstTag
0x14001d6d2  mov     [rsp+78h+arg_0], eax
0x14001d6d9  test    eax, eax
0x14001d6db  jnz     short loc_14001D6EF
0x14001d6dd  lea     r9, aTheSourceRefDe; "The source ref/def did not have the exp"...
0x14001d6e4  mov     r8d, 282h
0x14001d6ea  jmp     loc_14001D5FA
0x14001d6ef  movzx   eax, word ptr [rdi+4]
0x14001d6f3  mov     [rbp+0], ax
0x14001d6f7  mov     rax, [r15+10h]
0x14001d6fb  mov     r13, [rax]
0x14001d6fe  xor     eax, eax
0x14001d700  mov     ebp, eax
0x14001d702  mov     ebx, eax
0x14001d704  movzx   r8d, word ptr [rdi+rbx*2+0Ah]
0x14001d70a  test    r8w, r8w
0x14001d70e  jz      short loc_14001D729
0x14001d710  mov     edx, ebp
0x14001d712  mov     rcx, r13
0x14001d715  call    SdbFindFirstTag
0x14001d71a  mov     ebp, eax
0x14001d71c  test    eax, eax
0x14001d71e  jz      short loc_14001D72D
0x14001d720  inc     rbx
0x14001d723  cmp     rbx, 2
0x14001d727  jb      short loc_14001D704
0x14001d729  test    ebp, ebp
0x14001d72b  jnz     short loc_14001D765
0x14001d72d  lea     r9, aFailedToFindTh; "Failed to find the parent tagid that sh"...
0x14001d734  mov     r8d, 28Fh
0x14001d73a  lea     rdx, aSdbpmergefindm; "SdbpMergeFindMatchingLibraryEntry"
0x14001d741  mov     ecx, 3
0x14001d746  call    AslLogCallPrintf
0x14001d74b  movzx   eax, word ptr [rdi+4]
0x14001d74f  mov     [r12], eax
0x14001d753  mov     rax, [rsp+78h+arg_18]
0x14001d75b  mov     word ptr [rax], 405Dh
0x14001d760  jmp     loc_14001D635
0x14001d765  mov     rcx, [r15+10h]
0x14001d769  mov     edx, ebp
0x14001d76b  movzx   r8d, word ptr [rdi]
0x14001d76f  mov     rcx, [rcx]
0x14001d772  call    SdbFindFirstTag
0x14001d777  mov     ebx, eax
0x14001d779  test    eax, eax
0x14001d77b  jz      short loc_14001D74B
0x14001d77d  mov     r13d, [rsp+78h+arg_0]
0x14001d785  mov     rcx, [r15+10h]
0x14001d789  mov     edx, ebx
0x14001d78b  movzx   r8d, word ptr [rdi+6]
0x14001d790  mov     rcx, [rcx]
0x14001d793  call    SdbFindFirstTag
0x14001d798  test    eax, eax
0x14001d79a  jz      short loc_14001D7BF
0x14001d79c  mov     rcx, [r15+10h]
0x14001d7a0  xor     edx, edx
0x14001d7a2  mov     r8, [r14]
0x14001d7a5  test    esi, esi
0x14001d7a7  mov     r9d, r13d
0x14001d7aa  setnz   dl
0x14001d7ad  mov     rcx, [rcx]
0x14001d7b0  mov     [rsp+78h+var_58], edx
0x14001d7b4  mov     edx, eax
0x14001d7b6  call    SdbpMergeAreTagValuesEqual
0x14001d7bb  test    eax, eax
0x14001d7bd  jnz     short loc_14001D7DB
0x14001d7bf  mov     rcx, [r15+10h]
0x14001d7c3  mov     r8d, ebx
0x14001d7c6  mov     edx, ebp
0x14001d7c8  mov     rcx, [rcx]
0x14001d7cb  call    SdbFindNextTag
0x14001d7d0  mov     ebx, eax
0x14001d7d2  test    eax, eax
0x14001d7d4  jnz     short loc_14001D785
0x14001d7d6  jmp     loc_14001D74B
0x14001d7db  mov     [r12], ebx
0x14001d7df  xor     eax, eax
0x14001d7e1  jmp     short loc_14001D7E8
0x14001d7e3  mov     eax, 0C00000F0h
0x14001d7e8  mov     rbx, [rsp+78h+arg_8]
0x14001d7f0  add     rsp, 40h
0x14001d7f4  pop     r15
0x14001d7f6  pop     r14
0x14001d7f8  pop     r13
0x14001d7fa  pop     r12
0x14001d7fc  pop     rdi
0x14001d7fd  pop     rsi
0x14001d7fe  pop     rbp
0x14001d7ff  retn
```
