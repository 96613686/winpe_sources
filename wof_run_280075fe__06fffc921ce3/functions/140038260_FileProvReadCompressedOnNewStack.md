# FileProvReadCompressedOnNewStack

- ea: `0x140038260`
- end: `0x14003870a`
- name: `FileProvReadCompressedOnNewStack`
- size: `1194`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009600`

## callees

- `0x140004400`
- `0x140007a30`
- `0x140009aa8`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010078`
- `0x140011194`
- `0x140038260`
- `0x140038710`
- `0x140038ac0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400383e3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400383e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038524`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140038524`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400384b5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400384b5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003850d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003850d`

## pseudocode

```c
__int64 __fastcall FileProvReadCompressedOnNewStack(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rbp
  __int64 v4; // r14
  struct _PAGED_LOOKASIDE_LIST *v5; // r13
  __int64 v6; // rcx
  int Compressed; // edi
  __int64 *v8; // r15
  __int64 v9; // r15
  __int64 Alignment_low; // r8
  __int64 v11; // r12
  unsigned __int64 v12; // rbp
  int v13; // edi
  int v14; // ecx
  int v15; // edx
  SIZE_T v16; // rbx
  char *v17; // rax
  PVOID v18; // rbp
  char *PoolWithTag; // rdi
  __int64 v20; // rdx
  __int64 v22; // rcx
  SIZE_T NumberOfBytes; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+88h] [rbp+10h] BYREF
  __int64 ChunkOffset; // [rsp+90h] [rbp+18h] BYREF
  __int64 v26; // [rsp+98h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v3 = *(_QWORD *)(a1 + 24);
  v4 = *(unsigned int *)(a1 + 48);
  v5 = (struct _PAGED_LOOKASIDE_LIST *)FileProvCompressionScheme(v1);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  *(_DWORD *)(a1 + 52) = 0;
  v6 = *(_QWORD *)(v1 + 8);
  if ( v3 >= v6 )
    return 0;
  if ( (*(_DWORD *)v1 & 1) != 0 )
  {
    Compressed = 0;
    v8 = (__int64 *)(v1 + 32);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    v8 = (__int64 *)(v1 + 32);
    Compressed = FileProvBuildChunkTable(a1, v1, v1 + 32);
    if ( Compressed < 0 )
      goto LABEL_19;
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v1 - 64) + 32LL));
    v22 = *(_QWORD *)(v1 - 64);
    *(_DWORD *)v1 |= 1u;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v22 + 32));
    v6 = *(_QWORD *)(v1 + 8);
  }
  v9 = *v8;
  if ( v4 + v3 > v6 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v4,
        v6 - v3);
    LODWORD(v4) = *(_DWORD *)(v1 + 8) - v3;
  }
  if ( (_DWORD)v4 )
  {
    v26 = 0;
    LODWORD(NumberOfBytes) = 0;
    v24 = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v4);
    Alignment_low = LODWORD(v5->L.ListHead.Alignment);
    v11 = v3 / Alignment_low;
    v12 = (-Alignment_low & (v3 - 1 + Alignment_low + (unsigned __int64)(unsigned int)v4)) / Alignment_low;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v11,
        v12);
    if ( v9 )
    {
      ChunkOffset = FileProvGetChunkOffset(v9, (unsigned int)v11);
      v13 = ChunkOffset;
      v14 = FileProvGetChunkOffset(v9, (unsigned int)v12) - v13;
    }
    else
    {
      v14 = *(_DWORD *)(v1 + 16);
      ChunkOffset = 0;
    }
    v15 = v14 + 4;
    if ( *(_DWORD *)(v1 + 4) != 1 )
      v15 = v14;
    FileProvGetAlignedSizes(
      (unsigned int)&ChunkOffset,
      v15,
      Alignment_low,
      (unsigned int)&v26,
      (__int64)&NumberOfBytes,
      (__int64)&v24);
    v16 = (unsigned int)NumberOfBytes;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)NumberOfBytes,
        v5[2].L.ListEntry.Flink);
    if ( (unsigned int)v16 > LODWORD(v5[2].L.ListEntry.Flink) )
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v16, 0x44527066u);
      if ( PoolWithTag )
      {
        v18 = 0;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_3b099794e4b93327e327da255c047df6_Traceguids,
            (unsigned int)v16);
        goto LABEL_17;
      }
      Compressed = -1073741670;
    }
    else
    {
      v17 = (char *)ExAllocateFromPagedLookasideList(v5 + 3);
      v18 = v17;
      if ( v17 )
      {
        PoolWithTag = v17;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
LABEL_17:
        v20 = v24;
        *(_QWORD *)(a1 + 152) = FileProvReadCompressedOnNewStackExtendedCompletion;
        *(_QWORD *)(a1 + 160) = v9;
        *(_DWORD *)(a1 + 176) = v11;
        *(_QWORD *)(a1 + 184) = v18;
        *(_QWORD *)(a1 + 168) = &PoolWithTag[v20];
        *(_QWORD *)(a1 + 192) = PoolWithTag;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice);
        Compressed = FileProvReadCompressed(v26, PoolWithTag, (unsigned int)v16, a1 - 24);
        goto LABEL_19;
      }
      Compressed = -1073741670;
    }
  }
LABEL_19:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_3b099794e4b93327e327da255c047df6_Traceguids,
      (unsigned int)Compressed);
  return (unsigned int)Compressed;
}

```

## disassembly

```asm
0x140038260  push    rbx
0x140038262  push    rbp
0x140038263  push    rsi
0x140038264  push    r13
0x140038266  push    r14
0x140038268  sub     rsp, 50h
0x14003826c  mov     rbx, [rcx+20h]
0x140038270  mov     rsi, rcx
0x140038273  mov     rbp, [rcx+18h]
0x140038277  mov     r14d, [rcx+30h]
0x14003827b  mov     rcx, rbx
0x14003827e  call    FileProvCompressionScheme
0x140038283  mov     r13, rax
0x140038286  mov     rcx, cs:WPP_GLOBAL_Control
0x14003828d  mov     edx, [rcx+2Ch]
0x140038290  test    dl, 20h
0x140038293  jnz     loc_140038587
0x140038299  xor     r9d, r9d
0x14003829c  mov     [rsi+34h], r9d
0x1400382a0  mov     rcx, [rbx+8]
0x1400382a4  cmp     rbp, rcx
0x1400382a7  jge     loc_1400385AB
0x1400382ad  mov     eax, [rbx]
0x1400382af  mov     [rsp+78h+var_30], rdi
0x1400382b4  mov     [rsp+78h+var_40], r15
0x1400382b9  test    al, 1
0x1400382bb  jz      loc_1400384D7
0x1400382c1  mov     edi, r9d
0x1400382c4  lea     r15, [rbx+20h]
0x1400382c8  mov     r15, [r15]
0x1400382cb  lea     rax, [r14+rbp]
0x1400382cf  cmp     rax, rcx
0x1400382d2  jg      loc_1400385D6
0x1400382d8  test    r14d, r14d
0x1400382db  jz      loc_14003847C
0x1400382e1  mov     [rsp+78h+var_38], r12
0x1400382e6  mov     [rsp+78h+arg_18], r9
0x1400382ee  mov     dword ptr [rsp+78h+NumberOfBytes], r9d
0x1400382f6  mov     [rsp+78h+arg_8], r9d
0x1400382fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140038305  mov     eax, [rcx+2Ch]
0x140038308  test    al, 20h
0x14003830a  jnz     loc_140038619
0x140038310  mov     r8d, [r13+0]
0x140038314  mov     rax, rbp
0x140038317  cqo
0x140038319  dec     rbp
0x14003831c  idiv    r8
0x14003831f  mov     ecx, r8d
0x140038322  xor     edx, edx
0x140038324  mov     r12, rax
0x140038327  neg     rcx
0x14003832a  mov     eax, r14d
0x14003832d  add     rax, r8
0x140038330  add     rax, rbp
0x140038333  and     rax, rcx
0x140038336  div     r8
0x140038339  mov     rbp, rax
0x14003833c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038343  mov     edx, [rcx+2Ch]
0x140038346  test    dl, 20h
0x140038349  jnz     loc_140038643
0x14003834f  test    r15, r15
0x140038352  jz      loc_140038577
0x140038358  mov     edx, r12d
0x14003835b  mov     rcx, r15
0x14003835e  call    FileProvGetChunkOffset
0x140038363  mov     edx, ebp
0x140038365  mov     [rsp+78h+arg_10], rax
0x14003836d  mov     rcx, r15
0x140038370  mov     rdi, rax
0x140038373  call    FileProvGetChunkOffset
0x140038378  mov     rcx, rax
0x14003837b  sub     ecx, edi
0x14003837d  cmp     dword ptr [rbx+4], 1
0x140038381  lea     edx, [rcx+4]
0x140038384  lea     rax, [rsp+78h+arg_8]
0x14003838c  mov     [rsp+78h+var_50], rax
0x140038391  lea     r9, [rsp+78h+arg_18]
0x140038399  cmovnz  edx, ecx
0x14003839c  lea     rax, [rsp+78h+NumberOfBytes]
0x1400383a4  lea     rcx, [rsp+78h+arg_10]
0x1400383ac  mov     [rsp+78h+var_58], rax
0x1400383b1  call    FileProvGetAlignedSizes
0x1400383b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400383bd  mov     ebx, dword ptr [rsp+78h+NumberOfBytes]
0x1400383c4  mov     eax, [rcx+2Ch]
0x1400383c7  test    al, 20h
0x1400383c9  jnz     loc_140038671
0x1400383cf  cmp     ebx, [r13+140h]
0x1400383d6  ja      loc_1400384A7
0x1400383dc  lea     rcx, [r13+180h]; Lookaside
0x1400383e3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400383ea  nop     dword ptr [rax+rax+00h]
0x1400383ef  mov     rbp, rax
0x1400383f2  test    rax, rax
0x1400383f5  jz      loc_1400384D0
0x1400383fb  mov     rdi, rax
0x1400383fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140038405  mov     eax, [rcx+2Ch]
0x140038408  test    al, 20h
0x14003840a  jnz     loc_1400386A3
0x140038410  mov     edx, [rsp+78h+arg_8]
0x140038417  lea     rax, FileProvReadCompressedOnNewStackExtendedCompletion
0x14003841e  mov     [rsi+98h], rax
0x140038425  mov     [rsi+0A0h], r15
0x14003842c  mov     [rsi+0B0h], r12d
0x140038433  lea     r9, [rdi+rdx]
0x140038437  mov     [rsi+0B8h], rbp
0x14003843e  mov     [rsi+0A8h], r9
0x140038445  mov     [rsi+0C0h], rdi
0x14003844c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038453  mov     eax, [rcx+2Ch]
0x140038456  test    al, 20h
0x140038458  jnz     loc_1400386C7
0x14003845e  mov     rcx, [rsp+78h+arg_18]
0x140038466  lea     r9, [rsi-18h]
0x14003846a  mov     r8d, ebx
0x14003846d  mov     rdx, rdi
0x140038470  call    FileProvReadCompressed
0x140038475  mov     edi, eax
0x140038477  mov     r12, [rsp+78h+var_38]
0x14003847c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038483  mov     r15, [rsp+78h+var_40]
0x140038488  mov     eax, [rcx+2Ch]
0x14003848b  test    al, 20h
0x14003848d  jnz     loc_1400386E3
0x140038493  mov     eax, edi
0x140038495  mov     rdi, [rsp+78h+var_30]
0x14003849a  add     rsp, 50h
0x14003849e  pop     r14
0x1400384a0  pop     r13
0x1400384a2  pop     rsi
0x1400384a3  pop     rbp
0x1400384a4  pop     rbx
0x1400384a5  retn
0x1400384a7  mov     rdx, rbx; NumberOfBytes
0x1400384aa  mov     ecx, 1; PoolType
0x1400384af  mov     r8d, 44527066h; Tag
0x1400384b5  call    cs:__imp_ExAllocatePoolWithTag
0x1400384bc  nop     dword ptr [rax+rax+00h]
0x1400384c1  mov     rdi, rax
0x1400384c4  test    rax, rax
0x1400384c7  jnz     short loc_14003853C
0x1400384c9  mov     edi, 0C000009Ah
0x1400384ce  jmp     short loc_140038477
0x1400384d0  mov     edi, 0C000009Ah
0x1400384d5  jmp     short loc_140038477
0x1400384d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400384de  mov     eax, [rcx+2Ch]
0x1400384e1  test    al, 20h
0x1400384e3  jnz     loc_1400385B2
0x1400384e9  lea     r15, [rbx+20h]
0x1400384ed  mov     rdx, rbx
0x1400384f0  mov     r8, r15
0x1400384f3  mov     rcx, rsi
0x1400384f6  call    FileProvBuildChunkTable
0x1400384fb  mov     edi, eax
0x1400384fd  test    eax, eax
0x1400384ff  js      loc_14003847C
0x140038505  mov     rcx, [rbx-40h]
0x140038509  add     rcx, 20h ; ' '; FastMutex
0x14003850d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140038514  nop     dword ptr [rax+rax+00h]
0x140038519  mov     rcx, [rbx-40h]
0x14003851d  or      dword ptr [rbx], 1
0x140038520  add     rcx, 20h ; ' '; FastMutex
0x140038524  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003852b  nop     dword ptr [rax+rax+00h]
0x140038530  mov     rcx, [rbx+8]
0x140038534  xor     r9d, r9d
0x140038537  jmp     loc_1400382C8
0x14003853c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038543  xor     ebp, ebp
0x140038545  mov     eax, [rcx+2Ch]
0x140038548  test    al, 20h
0x14003854a  jz      loc_140038410
0x140038550  cmp     byte ptr [rcx+29h], 5
0x140038554  jb      loc_140038410
0x14003855a  mov     rcx, [rcx+18h]
0x14003855e  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038565  mov     edx, 1Ch
0x14003856a  mov     r9d, ebx
0x14003856d  call    WPP_SF_d
0x140038572  jmp     loc_140038410
0x140038577  mov     ecx, [rbx+10h]
0x14003857a  mov     [rsp+78h+arg_10], r9
0x140038582  jmp     loc_14003837D
0x140038587  cmp     byte ptr [rcx+29h], 4
0x14003858b  jb      loc_140038299
0x140038591  mov     rcx, [rcx+18h]
0x140038595  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x14003859c  mov     edx, 16h
0x1400385a1  call    WPP_SF_
0x1400385a6  jmp     loc_140038299
0x1400385ab  xor     eax, eax
0x1400385ad  jmp     loc_14003849A
0x1400385b2  cmp     byte ptr [rcx+29h], 5
0x1400385b6  jb      loc_1400384E9
0x1400385bc  mov     rcx, [rcx+18h]
0x1400385c0  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400385c7  mov     edx, 17h
0x1400385cc  call    WPP_SF_
0x1400385d1  jmp     loc_1400384E9
0x1400385d6  mov     r10, cs:WPP_GLOBAL_Control
0x1400385dd  mov     eax, [r10+2Ch]
0x1400385e1  test    al, 20h
0x1400385e3  jz      short loc_14003860D
0x1400385e5  cmp     byte ptr [r10+29h], 5
0x1400385ea  jb      short loc_14003860D
0x1400385ec  sub     ecx, ebp
0x1400385ee  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400385f5  mov     dword ptr [rsp+78h+var_58], ecx
0x1400385f9  mov     edx, 18h
0x1400385fe  mov     rcx, [r10+18h]
0x140038602  mov     r9d, r14d
0x140038605  call    WPP_SF_dd
0x14003860a  xor     r9d, r9d
0x14003860d  mov     r14d, [rbx+8]
0x140038611  sub     r14d, ebp
0x140038614  jmp     loc_1400382D8
0x140038619  cmp     byte ptr [rcx+29h], 5
0x14003861d  jb      loc_140038310
0x140038623  mov     rcx, [rcx+18h]
0x140038627  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x14003862e  mov     edx, 19h
0x140038633  mov     r9d, r14d
0x140038636  call    WPP_SF_d
0x14003863b  xor     r9d, r9d
0x14003863e  jmp     loc_140038310
0x140038643  cmp     byte ptr [rcx+29h], 5
0x140038647  jb      loc_14003834F
0x14003864d  mov     rcx, [rcx+18h]
0x140038651  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038658  mov     r9d, r12d
0x14003865b  mov     dword ptr [rsp+78h+var_58], ebp
0x14003865f  mov     edx, 1Ah
0x140038664  call    WPP_SF_dd
0x140038669  xor     r9d, r9d
0x14003866c  jmp     loc_14003834F
0x140038671  cmp     byte ptr [rcx+29h], 5
0x140038675  jb      loc_1400383CF
0x14003867b  mov     eax, [r13+140h]
0x140038682  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038689  mov     rcx, [rcx+18h]
0x14003868d  mov     edx, 1Bh
0x140038692  mov     r9d, ebx
0x140038695  mov     dword ptr [rsp+78h+var_58], eax
0x140038699  call    WPP_SF_dd
0x14003869e  jmp     loc_1400383CF
0x1400386a3  cmp     byte ptr [rcx+29h], 5
0x1400386a7  jb      loc_140038410
0x1400386ad  mov     rcx, [rcx+18h]
0x1400386b1  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400386b8  mov     edx, 1Dh
0x1400386bd  call    WPP_SF_
0x1400386c2  jmp     loc_140038410
0x1400386c7  cmp     byte ptr [rcx+29h], 5
0x1400386cb  jb      loc_14003845E
0x1400386d1  mov     rcx, [rcx+18h]
0x1400386d5  mov     dword ptr [rsp+78h+var_58], edx
0x1400386d9  call    WPP_SF_qD
0x1400386de  jmp     loc_14003845E
0x1400386e3  cmp     byte ptr [rcx+29h], 4
0x1400386e7  jb      loc_140038493
0x1400386ed  mov     rcx, [rcx+18h]
0x1400386f1  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400386f8  mov     edx, 1Fh
0x1400386fd  mov     r9d, edi
0x140038700  call    WPP_SF_d
0x140038705  jmp     loc_140038493
```
