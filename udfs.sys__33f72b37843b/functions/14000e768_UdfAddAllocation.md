# UdfAddAllocation

- ea: `0x14000e768`
- end: `0x14000eafe`
- name: `UdfAddAllocation`
- size: `918`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1400039fc`
- `0x14000eb04`

## callees

- `0x140009014`
- `0x14000c490`
- `0x14000e438`
- `0x14000e5d8`
- `0x14000e768`
- `0x14001093c`
- `0x140010d04`
- `0x14001992c`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14000e9ba`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14000e9ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eade`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d30d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eade`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d30d`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14000e825`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001d20d`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001d2a4`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14000e825`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001d20d`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001d2a4`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14000e958`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14001d247`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14000e958`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14001d247`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14000e979`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14000ea86`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14000e979`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14000ea86`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e9fe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e9fe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000ea3f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000ea3f`

## pseudocode

```c
void __fastcall UdfAddAllocation(__int64 a1, __int64 a2, LARGE_MCB *a3)
{
  int v5; // ebx
  __int64 v6; // rsi
  unsigned int v7; // r14d
  __int64 v8; // r12
  __int64 v9; // rcx
  LONGLONG v10; // rdi
  __int64 Lbn; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-70h]
  LONGLONG SectorCount; // [rsp+50h] [rbp-68h] BYREF
  __int64 Vbn; // [rsp+58h] [rbp-60h] BYREF
  unsigned int v15; // [rsp+60h] [rbp-58h] BYREF
  int v16; // [rsp+64h] [rbp-54h]
  int v17; // [rsp+68h] [rbp-50h] BYREF
  _DWORD v18[5]; // [rsp+6Ch] [rbp-4Ch]
  ULONG RunIndex; // [rsp+D8h] [rbp+20h] BYREF

  v5 = 0;
  Lbn = 0;
  Vbn = 0;
  SectorCount = 0;
  v15 = 0;
  RunIndex = 0;
  v17 = 0;
  v6 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)&v18[1] = v6;
  v7 = (*(_DWORD *)(a2 + 212) >> 27) & 1;
  v12 = v7;
  v8 = 200LL * v7;
  UdfAcquireResource(a1, v8 + v6 + 552, 0, 0);
  if ( v7 == 1 || *(_WORD *)a2 == 2356 )
    v5 = *(_DWORD *)(v8 + v6 + 496);
  v16 = v5;
  while ( FsRtlGetNextLargeMcbEntry(a3, RunIndex, &Vbn, &Lbn, &SectorCount) )
  {
    if ( (_DWORD)Lbn == -1 )
    {
      ++RunIndex;
    }
    else
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          59,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          (unsigned int)SectorCount,
          Vbn);
      }
      UdfFindFreeBitmapBlocks(a1, v7, SectorCount, v5, (__int64)&Lbn, (__int64)&v15);
      v10 = v15;
      if ( !v15 )
        UdfRaiseStatusEx(a1, 3221225701LL, 0);
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_DDDD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          60,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          v15,
          Lbn,
          v7,
          SectorCount - v15);
      }
      v18[0] = Lbn + *(_DWORD *)(v8 + *(_QWORD *)(a1 + 16) + 656);
      if ( (unsigned int)v10 < (unsigned int)SectorCount )
      {
        FsRtlRemoveLargeMcbEntry(a3, Vbn, v10);
        FsRtlAddLargeMcbEntry(a3, Vbn, Lbn, v10);
        FsRtlLookupLargeMcbEntry(a3, v10 + Vbn, 0, 0, 0, 0, &RunIndex);
        FsRtlChangeLargeMcbEntryLbn(a3, RunIndex--, 4294967294LL);
      }
      else
      {
        FsRtlChangeLargeMcbEntryLbn(a3, RunIndex, Lbn);
        LODWORD(v10) = SectorCount;
        v15 = SectorCount;
      }
      if ( (*(_DWORD *)(a2 + 212) & 0x2000) != 0 )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 1584));
        *(_QWORD *)(v6 + 1640) = KeGetCurrentThread();
        *(_DWORD *)(a2 + 328) -= v10;
        *(_DWORD *)(v8 + v6 + 672) -= v10;
        *(_DWORD *)(v8 + v6 + 668) -= v10;
        *(_QWORD *)(v6 + 1640) = 0;
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 1584));
      }
      UdfChangeOrVerifyBitmapRun(a1, v7, Lbn, v10, 0, 0, (__int64)&v17);
      FsRtlAddLargeMcbEntry((PLARGE_MCB)(a2 + 264), Vbn, v18[0], (unsigned int)v10);
      *(_DWORD *)(a2 + 324) += v10;
      v5 = v10 + Lbn;
      v16 = v10 + Lbn;
      ++RunIndex;
    }
  }
  if ( v7 == 1 || *(_WORD *)a2 == 2356 )
    *(_DWORD *)(v8 + v6 + 496) = v5;
  UdfUnpinCurrentBitmapPage(v9, v6, v7);
  ExReleaseResourceLite((PERESOURCE)(v8 + v6 + 552));
}

```

## disassembly

```asm
0x14000e768  mov     rax, rsp
0x14000e76b  mov     [rax+18h], r8
0x14000e76f  mov     [rax+10h], rdx
0x14000e773  mov     [rax+8], rcx
0x14000e777  push    rbx
0x14000e778  push    rsi
0x14000e779  push    rdi
0x14000e77a  push    r12
0x14000e77c  push    r13
0x14000e77e  push    r14
0x14000e780  push    r15
0x14000e782  sub     rsp, 80h
0x14000e789  mov     r15, rdx
0x14000e78c  mov     r13, rcx
0x14000e78f  xor     ebx, ebx
0x14000e791  mov     [rax-78h], rbx
0x14000e795  mov     [rax-60h], rbx
0x14000e799  mov     [rax-68h], rbx
0x14000e79d  mov     [rax-58h], ebx
0x14000e7a0  mov     [rax+20h], ebx
0x14000e7a3  mov     [rax-50h], ebx
0x14000e7a6  mov     rsi, [rcx+10h]
0x14000e7aa  mov     qword ptr [rsp+0B8h+var_4C+4], rsi
0x14000e7af  mov     r14d, [rdx+0D4h]
0x14000e7b6  shr     r14d, 1Bh
0x14000e7ba  and     r14d, 1
0x14000e7be  mov     [rsp+0B8h+var_70], r14d
0x14000e7c3  mov     eax, r14d
0x14000e7c6  imul    r12, rax, 0C8h
0x14000e7cd  lea     rdx, [rsi+228h]
0x14000e7d4  add     rdx, r12
0x14000e7d7  xor     r9d, r9d
0x14000e7da  xor     r8d, r8d
0x14000e7dd  call    UdfAcquireResource
0x14000e7e2  cmp     r14d, 1
0x14000e7e6  jz      short loc_14000E7F3
0x14000e7e8  mov     edi, 934h
0x14000e7ed  cmp     [r15], di
0x14000e7f1  jnz     short loc_14000E7FB
0x14000e7f3  mov     ebx, [r12+rsi+1F0h]
0x14000e7fb  mov     dword ptr [rsp+0B8h+var_58+4], ebx
0x14000e7ff  mov     rdi, [rsp+0B8h+Mcb]
0x14000e807  lea     rax, [rsp+0B8h+var_68]
0x14000e80c  mov     [rsp+0B8h+SectorCount], rax; SectorCount
0x14000e811  lea     r9, [rsp+0B8h+Lbn]; Lbn
0x14000e816  lea     r8, [rsp+0B8h+Vbn]; Vbn
0x14000e81b  mov     edx, [rsp+0B8h+RunIndex]; RunIndex
0x14000e822  mov     rcx, rdi; Mcb
0x14000e825  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x14000e82c  nop     dword ptr [rax+rax+00h]
0x14000e831  test    al, al
0x14000e833  jz      loc_14000EAB0
0x14000e839  cmp     dword ptr [rsp+0B8h+Lbn], 0FFFFFFFFh
0x14000e83e  jnz     short loc_14000E849
0x14000e840  inc     [rsp+0B8h+RunIndex]
0x14000e847  jmp     short loc_14000E807
0x14000e849  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e850  lea     rax, WPP_GLOBAL_Control
0x14000e857  cmp     rcx, rax
0x14000e85a  jz      short loc_14000E886
0x14000e85c  mov     eax, [rcx+2Ch]
0x14000e85f  test    al, 1
0x14000e861  jz      short loc_14000E886
0x14000e863  mov     edx, 3Bh ; ';'
0x14000e868  mov     rax, [rsp+0B8h+Vbn]
0x14000e86d  mov     dword ptr [rsp+0B8h+SectorCount], eax
0x14000e871  mov     r9d, dword ptr [rsp+0B8h+var_68]
0x14000e876  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14000e87d  mov     rcx, [rcx+18h]
0x14000e881  call    WPP_SF_dd
0x14000e886  lea     rax, [rsp+0B8h+var_58]
0x14000e88b  mov     [rsp+0B8h+SectorCountFromStartingLbn], rax
0x14000e890  lea     rax, [rsp+0B8h+Lbn]
0x14000e895  mov     [rsp+0B8h+SectorCount], rax
0x14000e89a  mov     r9d, ebx
0x14000e89d  mov     r8d, dword ptr [rsp+0B8h+var_68]
0x14000e8a2  mov     edx, r14d
0x14000e8a5  mov     rcx, r13
0x14000e8a8  call    UdfFindFreeBitmapBlocks
0x14000e8ad  mov     edi, dword ptr [rsp+0B8h+var_58]
0x14000e8b1  test    edi, edi
0x14000e8b3  jnz     short loc_14000E8C5
0x14000e8b5  xor     r8d, r8d
0x14000e8b8  mov     edx, 0C00000E5h
0x14000e8bd  mov     rcx, r13
0x14000e8c0  call    UdfRaiseStatusEx
0x14000e8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8cc  lea     rax, WPP_GLOBAL_Control
0x14000e8d3  cmp     rcx, rax
0x14000e8d6  jz      short loc_14000E910
0x14000e8d8  mov     eax, [rcx+2Ch]
0x14000e8db  test    al, 1
0x14000e8dd  jz      short loc_14000E910
0x14000e8df  mov     rax, [rsp+0B8h+var_68]
0x14000e8e4  sub     eax, edi
0x14000e8e6  mov     edx, 3Ch ; '<'
0x14000e8eb  mov     dword ptr [rsp+0B8h+Index], eax
0x14000e8ef  mov     dword ptr [rsp+0B8h+SectorCountFromStartingLbn], r14d
0x14000e8f4  mov     rax, [rsp+0B8h+Lbn]
0x14000e8f9  mov     dword ptr [rsp+0B8h+SectorCount], eax
0x14000e8fd  mov     r9d, edi
0x14000e900  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14000e907  mov     rcx, [rcx+18h]
0x14000e90b  call    WPP_SF_DDDD
0x14000e910  mov     rax, [r13+10h]
0x14000e914  mov     eax, [r12+rax+290h]
0x14000e91c  mov     r8, [rsp+0B8h+Lbn]
0x14000e921  add     eax, r8d
0x14000e924  mov     [rsp+0B8h+var_4C], eax
0x14000e928  mov     rcx, [rsp+0B8h+Mcb]; Mcb
0x14000e930  cmp     edi, dword ptr [rsp+0B8h+var_68]
0x14000e934  jb      short loc_14000E950
0x14000e936  mov     edx, [rsp+0B8h+RunIndex]
0x14000e93d  call    FsRtlChangeLargeMcbEntryLbn
0x14000e942  mov     rdi, [rsp+0B8h+var_68]
0x14000e947  mov     dword ptr [rsp+0B8h+var_58], edi
0x14000e94b  jmp     loc_14000E9E7
0x14000e950  mov     r8, rdi; SectorCount
0x14000e953  mov     rdx, [rsp+0B8h+Vbn]; Vbn
0x14000e958  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x14000e95f  nop     dword ptr [rax+rax+00h]
0x14000e964  mov     r9, rdi; SectorCount
0x14000e967  mov     r8, [rsp+0B8h+Lbn]; Lbn
0x14000e96c  mov     rdx, [rsp+0B8h+Vbn]; Vbn
0x14000e971  mov     rcx, [rsp+0B8h+Mcb]; Mcb
0x14000e979  call    cs:__imp_FsRtlAddLargeMcbEntry
0x14000e980  nop     dword ptr [rax+rax+00h]
0x14000e985  mov     rdx, [rsp+0B8h+Vbn]
0x14000e98a  add     rdx, rdi; Vbn
0x14000e98d  lea     rax, [rsp+0B8h+RunIndex]
0x14000e995  mov     [rsp+0B8h+Index], rax; Index
0x14000e99a  mov     [rsp+0B8h+SectorCountFromStartingLbn], 0; SectorCountFromStartingLbn
0x14000e9a3  mov     [rsp+0B8h+SectorCount], 0; StartingLbn
0x14000e9ac  xor     r9d, r9d; SectorCountFromLbn
0x14000e9af  xor     r8d, r8d; Lbn
0x14000e9b2  mov     rcx, [rsp+0B8h+Mcb]; Mcb
0x14000e9ba  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x14000e9c1  nop     dword ptr [rax+rax+00h]
0x14000e9c6  mov     r8d, 0FFFFFFFEh
0x14000e9cc  mov     edx, [rsp+0B8h+RunIndex]
0x14000e9d3  mov     rcx, [rsp+0B8h+Mcb]
0x14000e9db  call    FsRtlChangeLargeMcbEntryLbn
0x14000e9e0  dec     [rsp+0B8h+RunIndex]
0x14000e9e7  test    dword ptr [r15+0D4h], 2000h
0x14000e9f2  jz      short loc_14000EA4B
0x14000e9f4  lea     rbx, [rsi+630h]
0x14000e9fb  mov     rcx, rbx; FastMutex
0x14000e9fe  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000ea05  nop     dword ptr [rax+rax+00h]
0x14000ea0a  mov     rax, gs:188h
0x14000ea13  mov     [rsi+668h], rax
0x14000ea1a  sub     [r15+148h], edi
0x14000ea21  sub     [r12+rsi+2A0h], edi
0x14000ea29  sub     [r12+rsi+29Ch], edi
0x14000ea31  mov     qword ptr [rsi+668h], 0
0x14000ea3c  mov     rcx, rbx; FastMutex
0x14000ea3f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000ea46  nop     dword ptr [rax+rax+00h]
0x14000ea4b  lea     rax, [rsp+0B8h+var_50]
0x14000ea50  mov     [rsp+0B8h+Index], rax
0x14000ea55  mov     byte ptr [rsp+0B8h+SectorCountFromStartingLbn], 0
0x14000ea5a  mov     byte ptr [rsp+0B8h+SectorCount], 0
0x14000ea5f  mov     r9d, edi
0x14000ea62  mov     r8d, dword ptr [rsp+0B8h+Lbn]
0x14000ea67  mov     edx, r14d
0x14000ea6a  mov     rcx, r13
0x14000ea6d  call    UdfChangeOrVerifyBitmapRun
0x14000ea72  mov     r9d, edi; SectorCount
0x14000ea75  mov     r8d, [rsp+0B8h+var_4C]; Lbn
0x14000ea7a  lea     rcx, [r15+108h]; Mcb
0x14000ea81  mov     rdx, [rsp+0B8h+Vbn]; Vbn
0x14000ea86  call    cs:__imp_FsRtlAddLargeMcbEntry
0x14000ea8d  nop     dword ptr [rax+rax+00h]
0x14000ea92  add     [r15+144h], edi
0x14000ea99  mov     rbx, [rsp+0B8h+Lbn]
0x14000ea9e  add     ebx, edi
0x14000eaa0  mov     dword ptr [rsp+0B8h+var_58+4], ebx
0x14000eaa4  inc     [rsp+0B8h+RunIndex]
0x14000eaab  jmp     loc_14000E7FF
0x14000eab0  cmp     r14d, 1
0x14000eab4  jz      short loc_14000EAC1
0x14000eab6  mov     eax, 934h
0x14000eabb  cmp     [r15], ax
0x14000eabf  jnz     short loc_14000EAC9
0x14000eac1  mov     [r12+rsi+1F0h], ebx
0x14000eac9  mov     r8d, r14d
0x14000eacc  mov     rdx, rsi
0x14000eacf  call    UdfUnpinCurrentBitmapPage
0x14000ead4  lea     rcx, [rsi+228h]
0x14000eadb  add     rcx, r12; Resource
0x14000eade  call    cs:__imp_ExReleaseResourceLite
0x14000eae5  nop     dword ptr [rax+rax+00h]
0x14000eaea  add     rsp, 80h
0x14000eaf1  pop     r15
0x14000eaf3  pop     r14
0x14000eaf5  pop     r13
0x14000eaf7  pop     r12
0x14000eaf9  pop     rdi
0x14000eafa  pop     rsi
0x14000eafb  pop     rbx
0x14000eafc  retn
0x14001d1d7  push    rbx
0x14001d1d9  push    rbp
0x14001d1da  sub     rsp, 48h
0x14001d1de  mov     rbp, rdx
0x14001d1e1  test    cl, cl
0x14001d1e3  jz      loc_14001D2BA
0x14001d1e9  mov     dword ptr [rbp+0D8h], 0
0x14001d1f3  lea     rax, [rbp+50h]
0x14001d1f7  mov     [rsp+58h+var_38], rax; SectorCount
0x14001d1fc  lea     r9, [rbp+40h]; Lbn
0x14001d200  lea     r8, [rbp+58h]; Vbn
0x14001d204  xor     edx, edx; RunIndex
0x14001d206  mov     rcx, [rbp+0D0h]; Mcb
0x14001d20d  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x14001d214  nop     dword ptr [rax+rax+00h]
0x14001d219  test    al, al
0x14001d21b  jz      loc_14001D2EA
0x14001d221  mov     rbx, [rbp+0C8h]
0x14001d228  cmp     dword ptr [rbp+40h], 0FFFFFFFFh
0x14001d22c  jz      short loc_14001D27E
0x14001d22e  cmp     dword ptr [rbp+40h], 0FFFFFFFEh
0x14001d232  jz      loc_14001D2EA
0x14001d238  lea     rcx, [rbx+108h]; Mcb
0x14001d23f  mov     r8, [rbp+50h]; SectorCount
0x14001d243  mov     rdx, [rbp+58h]; Vbn
0x14001d247  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x14001d24e  nop     dword ptr [rax+rax+00h]
0x14001d253  lea     rax, [rbp+68h]
0x14001d257  mov     [rsp+58h+var_28], rax
0x14001d25c  mov     [rsp+58h+var_30], 0
0x14001d261  mov     byte ptr [rsp+58h+var_38], 1
0x14001d266  mov     r9d, [rbp+50h]
0x14001d26a  mov     r8d, [rbp+40h]
0x14001d26e  mov     edx, [rbp+48h]
0x14001d271  mov     rcx, [rbp+0C0h]
0x14001d278  call    UdfChangeOrVerifyBitmapRun
0x14001d27d  nop
0x14001d27e  mov     edx, [rbp+0D8h]
0x14001d284  inc     edx; RunIndex
0x14001d286  mov     [rbp+0D8h], edx
0x14001d28c  lea     rax, [rbp+50h]
0x14001d290  mov     [rsp+58h+var_38], rax; SectorCount
0x14001d295  lea     r9, [rbp+40h]; Lbn
0x14001d299  lea     r8, [rbp+58h]; Vbn
0x14001d29d  mov     rcx, [rbp+0D0h]; Mcb
0x14001d2a4  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x14001d2ab  nop     dword ptr [rax+rax+00h]
0x14001d2b0  test    al, al
0x14001d2b2  jnz     loc_14001D228
0x14001d2b8  jmp     short loc_14001D2EA
0x14001d2ba  cmp     dword ptr [rbp+48h], 1
0x14001d2be  jz      short loc_14001D2D1
0x14001d2c0  mov     ecx, 934h
0x14001d2c5  mov     rax, [rbp+0C8h]
0x14001d2cc  cmp     [rax], cx
0x14001d2cf  jnz     short loc_14001D2EA
0x14001d2d1  movsxd  rax, dword ptr [rbp+48h]
0x14001d2d5  imul    rdx, rax, 0C8h
0x14001d2dc  mov     ecx, [rbp+64h]
0x14001d2df  mov     rax, [rbp+70h]
0x14001d2e3  mov     [rdx+rax+1F0h], ecx
0x14001d2ea  mov     r8d, [rbp+48h]
0x14001d2ee  mov     rdx, [rbp+70h]
0x14001d2f2  call    UdfUnpinCurrentBitmapPage
0x14001d2f7  movsxd  rax, dword ptr [rbp+48h]
0x14001d2fb  imul    rcx, rax, 0C8h
0x14001d302  add     rcx, 228h
0x14001d309  add     rcx, [rbp+70h]; Resource
0x14001d30d  call    cs:__imp_ExReleaseResourceLite
0x14001d314  nop     dword ptr [rax+rax+00h]
0x14001d319  nop
0x14001d31a  add     rsp, 48h
0x14001d31e  pop     rbp
0x14001d31f  pop     rbx
0x14001d320  retn
```
