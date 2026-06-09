# UdfAllocateBlockForIcb

- ea: `0x1400300ec`
- end: `0x140030731`
- name: `UdfAllocateBlockForIcb`
- size: `1605`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1400050d8`
- `0x140030818`

## callees

- `0x140009014`
- `0x140009380`
- `0x14000b2b0`
- `0x14000ca54`
- `0x14000cad4`
- `0x14000e438`
- `0x14000e5d8`
- `0x1400103d8`
- `0x140010918`
- `0x140010990`
- `0x140010d04`
- `0x1400193f0`
- `0x14001bd80`
- `0x14001c080`
- `0x1400300ec`
- `0x140039ff4`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003050a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003070a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b3cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b3ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b4c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003050a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003070a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b3cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b3ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b4c9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003069f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005b421`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003069f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005b421`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003059b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400306cd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b474`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003059b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400306cd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b474`
- `ntoskrnl!CcSetFileSizes` at `0x140030319`
- `ntoskrnl!CcSetFileSizes` at `0x140030337`
- `ntoskrnl!CcSetFileSizes` at `0x140030319`
- `ntoskrnl!CcSetFileSizes` at `0x140030337`
- `ntoskrnl!CcPinRead` at `0x1400303cd`
- `ntoskrnl!CcPinRead` at `0x1400303cd`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x140030407`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x140030407`

## pseudocode

```c
__int64 __fastcall UdfAllocateBlockForIcb(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r10
  unsigned int v8; // r8d
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  DWORD LowPart; // edx
  __int64 v12; // rcx
  unsigned int v13; // edi
  unsigned __int64 v14; // rsi
  __int64 v15; // rbx
  char *v16; // rcx
  struct _ERESOURCE *v17; // rcx
  __int64 v18; // r15
  int v19; // r9d
  __int64 v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-78h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp-70h] BYREF
  __int64 v24; // [rsp+50h] [rbp-68h]
  PVOID BcbVoid[2]; // [rsp+58h] [rbp-60h] BYREF
  __int128 v26; // [rsp+68h] [rbp-50h]
  __int64 v27; // [rsp+78h] [rbp-40h]
  unsigned int v28; // [rsp+D0h] [rbp+18h] BYREF
  int v29; // [rsp+D8h] [rbp+20h] BYREF

  v2 = (int)a2;
  v24 = *(_QWORD *)(a1 + 16);
  v4 = v24;
  v28 = 0;
  v29 = 0;
  v22 = 0;
  FileOffset.QuadPart = 0;
  *(_OWORD *)BcbVoid = 0;
  v26 = 0;
  v27 = 0;
  if ( *(_QWORD *)(v24 + 352) )
  {
    UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v24 + 344) + 136LL) + 80LL) + 8LL, 0, 0);
    UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v24 + 344) + 16LL), 0, 0);
    if ( (unsigned int)((*(_QWORD *)(*(_QWORD *)(v24 + 344) + 32LL)
                       - (unsigned __int64)(unsigned int)UdfVatHeaderTailSize(v24)) >> 2) == *(_DWORD *)(v24 + 476) )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 69, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
      }
      v5 = *(unsigned int *)(v24 + 68);
      v6 = (unsigned int)(v5 - 1);
      v7 = *(_QWORD *)(v24 + 344);
      v8 = *(_DWORD *)(v7 + 32);
      if ( (v8 & (unsigned int)v6) != 0 )
      {
        if ( (*(_DWORD *)(v7 + 212) & 2) != 0 )
        {
          v9 = (unsigned int)(v5 - *(_DWORD *)(v7 + 224));
          if ( v8 >= (unsigned int)v9 )
          {
            UdfDeEmbedFileData(v9, *(struct _CC_FILE_SIZES **)(v24 + 344), *(struct _FILE_OBJECT **)(v7 + 504), 1);
            *(_DWORD *)(*(_QWORD *)(v24 + 344) + 212LL) &= ~0x80000u;
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                70,
                WPP_3702783af02333f5d52357996bb663b1_Traceguids);
            }
            *(_QWORD *)(*(_QWORD *)(v4 + 344) + 32LL) = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 68) - 1)
                                                      & ((unsigned int)(*(_DWORD *)(v4 + 68) - 1)
                                                       + *(_QWORD *)(*(_QWORD *)(v4 + 344) + 32LL));
          }
          else
          {
            *(_QWORD *)(v7 + 32) = (unsigned int)v9;
          }
        }
        else
        {
          *(_QWORD *)(v7 + 32) = ~v6 & (v6 + *(_QWORD *)(v7 + 32));
        }
      }
      else
      {
        *(_QWORD *)(v7 + 32) += v5;
      }
      *(_QWORD *)(*(_QWORD *)(v4 + 344) + 40LL) = *(_QWORD *)(*(_QWORD *)(v4 + 344) + 32LL);
      *(_QWORD *)(*(_QWORD *)(v4 + 344) + 24LL) = *(_QWORD *)(*(_QWORD *)(v4 + 344) + 40LL);
      v10 = *(unsigned int *)(v4 + 68)
          * ((*(_QWORD *)(*(_QWORD *)(v4 + 344) + 32LL) - (unsigned __int64)(unsigned int)UdfVatHeaderTailSize(v4)) >> 2);
      *(_QWORD *)(*(_QWORD *)(v4 + 352) + 40LL) = v10;
      *(_QWORD *)(*(_QWORD *)(v4 + 352) + 24LL) = v10;
      *(_QWORD *)(*(_QWORD *)(v4 + 352) + 32LL) = v10;
      CcSetFileSizes(*(PFILE_OBJECT *)(*(_QWORD *)(v4 + 344) + 504LL), (PCC_FILE_SIZES)(*(_QWORD *)(v4 + 344) + 24LL));
      CcSetFileSizes(*(PFILE_OBJECT *)(*(_QWORD *)(v4 + 352) + 504LL), (PCC_FILE_SIZES)(*(_QWORD *)(v4 + 352) + 24LL));
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_q(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          71,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v4 + 344) + 32LL));
      }
      *(_OWORD *)BcbVoid = 0;
      LowPart = *(_DWORD *)(v4 + 472) + 4 * *(_DWORD *)(v4 + 476);
      FileOffset.QuadPart = *(unsigned int *)(v4 + 472) + 4LL * *(unsigned int *)(v4 + 476);
      while ( 1 )
      {
        CcPinRead(
          *(PFILE_OBJECT *)(*(_QWORD *)(v4 + 344) + 504LL),
          &FileOffset,
          *(_DWORD *)(v4 + 68) - (LowPart & (*(_DWORD *)(v4 + 68) - 1)),
          1u,
          &BcbVoid[1],
          BcbVoid);
        *(_BYTE *)BcbVoid[0] = 0;
        memset(BcbVoid[0], 255, *(_DWORD *)(v4 + 68) - (FileOffset.LowPart & (*(_DWORD *)(v4 + 68) - 1)));
        CcSetDirtyPinnedData(BcbVoid[1], 0);
        FileOffset.QuadPart = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 68) - 1)
                            & ((unsigned int)(*(_DWORD *)(v4 + 68) - 1) + FileOffset.QuadPart + 4);
        v12 = *(_QWORD *)(v4 + 344);
        if ( FileOffset.QuadPart >= *(_QWORD *)(v12 + 32) )
          break;
        UdfUnpinData(v12, &BcbVoid[1]);
        BcbVoid[0] = 0;
        LowPart = FileOffset.LowPart;
      }
      if ( *(_WORD *)(v4 + 2136) != 10 )
      {
        v13 = *(_DWORD *)(v4 + 68);
        v14 = (unsigned __int64)BcbVoid[0] & -(__int64)v13;
        if ( (*(_DWORD *)(v12 + 32) & (v13 - 1)) != 0 )
          v13 = *(_DWORD *)(v12 + 32) & (v13 - 1);
        v15 = v13 - (unsigned int)UdfVatHeaderTailSize(v4);
        *(_BYTE *)(v15 + v14) = 0;
        v16 = (char *)(v15 + v14 + 1);
        *(_OWORD *)v16 = 0;
        *(_QWORD *)(v16 + 15) = 0;
        memmove(v16, Src, (unsigned __int16)UdfVatTableIdentifier);
        *(_WORD *)(v15 + v14 + 26) = 6;
        *(_WORD *)(v15 + v14 + 24) = *(_WORD *)(v4 + 2138);
        *(_DWORD *)(v15 + v14 + 28) = 0;
        v12 = v13 - 4;
        *(_DWORD *)(v12 + v14) = *(_DWORD *)(*(_QWORD *)(v4 + 464) + 12LL);
      }
      UdfUnpinData(v12, &BcbVoid[1]);
    }
    v28 = *(_DWORD *)(v4 + 476);
    *(_DWORD *)(v4 + 476) = v28 + 1;
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v4 + 344) + 16LL));
    v17 = (struct _ERESOURCE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 344) + 136LL) + 80LL) + 8LL);
LABEL_44:
    ExReleaseResourceLite(v17);
    return v28;
  }
  if ( (*(_DWORD *)(v24 + 48) & 0x20000000) == 0 )
  {
    UdfPrepareForAllocationChange(a1, v24, a2, 1);
    v18 = 200 * v2;
    --*(_DWORD *)(200 * v2 + v24 + 668);
    *(_QWORD *)(v4 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 1584));
    UdfAcquireResource(a1, 200 * v2 + v4 + 552, 0, 0);
    if ( (_DWORD)v2 == 1 )
      v19 = *(_DWORD *)(v18 + v4 + 496);
    else
      v19 = 0;
    UdfFindFreeBitmapBlocks(a1, v2, 1, v19, (__int64)&v28, (__int64)&v22);
    if ( !v22 )
      UdfRaiseStatusEx(a1, 3221225701LL, 0);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
    {
      WPP_SF_DDD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        72,
        WPP_3702783af02333f5d52357996bb663b1_Traceguids,
        v22,
        v28,
        v2);
    }
    UdfVmcbCheckForNoOpRead(a1, v4, (unsigned int)v2, v28);
    UdfChangeOrVerifyBitmapRun(a1, v2, v28, 1, 0, 0, (__int64)&v29);
    if ( v29 )
    {
      if ( (_DWORD)v2 == 1 )
        *(_DWORD *)(v18 + v4 + 496) = v28 + 1;
    }
    else
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 1584));
      *(_QWORD *)(v4 + 1640) = KeGetCurrentThread();
      ++*(_DWORD *)(v18 + v4 + 668);
      *(_QWORD *)(v4 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 1584));
    }
    UdfUnpinCurrentBitmapPage(v20, *(_QWORD *)(a1 + 16), (unsigned int)v2);
    v17 = (struct _ERESOURCE *)(v18 + *(_QWORD *)(a1 + 16) + 552LL);
    goto LABEL_44;
  }
  if ( (int)UdfPowReserveMetaDataBlocks(a1, v24, a2, 1, (__int64)&v28) < 0 )
    return 0;
  return v28;
}

```

## disassembly

```asm
0x1400300ec  mov     rax, rsp
0x1400300ef  mov     [rax+10h], edx
0x1400300f2  mov     [rax+8], rcx
0x1400300f6  push    rbx
0x1400300f7  push    rsi
0x1400300f8  push    rdi
0x1400300f9  push    r12
0x1400300fb  push    r13
0x1400300fd  push    r14
0x1400300ff  push    r15
0x140030101  sub     rsp, 80h
0x140030108  movsxd  rsi, edx
0x14003010b  mov     rdi, rcx
0x14003010e  mov     r14, [rcx+10h]
0x140030112  mov     [rsp+0B8h+var_68], r14
0x140030117  xor     r13d, r13d
0x14003011a  mov     [rax+18h], r13d
0x14003011e  mov     [rax+20h], r13d
0x140030122  mov     [rax-78h], r13d
0x140030126  mov     [rax-70h], r13
0x14003012a  xorps   xmm0, xmm0
0x14003012d  xor     eax, eax
0x14003012f  movups  xmmword ptr [rsp+0B8h+BcbVoid], xmm0
0x140030134  movups  [rsp+0B8h+var_50], xmm0
0x140030139  mov     [rsp+0B8h+var_40], rax
0x14003013e  cmp     [r14+160h], r13
0x140030145  jz      loc_140030531
0x14003014b  mov     rax, [r14+158h]
0x140030152  mov     rcx, [rax+88h]
0x140030159  mov     rdx, [rcx+50h]
0x14003015d  add     rdx, 8
0x140030161  xor     r9d, r9d
0x140030164  xor     r8d, r8d
0x140030167  mov     rcx, rdi
0x14003016a  call    UdfAcquireResource
0x14003016f  mov     rdx, [r14+158h]
0x140030176  xor     r9d, r9d
0x140030179  xor     r8d, r8d
0x14003017c  mov     rdx, [rdx+10h]
0x140030180  mov     rcx, rdi
0x140030183  call    UdfAcquireResource
0x140030188  mov     rcx, r14
0x14003018b  call    UdfVatHeaderTailSize
0x140030190  mov     ecx, eax
0x140030192  mov     rax, [r14+158h]
0x140030199  mov     rdx, [rax+20h]
0x14003019d  sub     rdx, rcx
0x1400301a0  shr     rdx, 2
0x1400301a4  cmp     edx, [r14+1DCh]
0x1400301ab  jnz     loc_1400304E8
0x1400301b1  lea     r12, WPP_GLOBAL_Control
0x1400301b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400301bf  lea     ebx, [r13+1]
0x1400301c3  cmp     rcx, r12
0x1400301c6  jz      short loc_1400301E2
0x1400301c8  mov     eax, [rcx+2Ch]
0x1400301cb  test    bl, al
0x1400301cd  jz      short loc_1400301E2
0x1400301cf  lea     edx, [rbx+44h]
0x1400301d2  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x1400301d9  mov     rcx, [rcx+18h]
0x1400301dd  call    WPP_SF_
0x1400301e2  mov     ecx, [r14+44h]
0x1400301e6  lea     edx, [rcx-1]
0x1400301e9  mov     r10, [r14+158h]
0x1400301f0  mov     r8d, [r10+20h]
0x1400301f4  test    edx, r8d
0x1400301f7  jz      loc_1400302A0
0x1400301fd  mov     eax, [r10+0D4h]
0x140030204  test    al, 2
0x140030206  jz      loc_14003028D
0x14003020c  sub     ecx, [r10+0E0h]
0x140030213  cmp     r8d, ecx
0x140030216  jnb     short loc_140030223
0x140030218  mov     eax, ecx
0x14003021a  mov     [r10+20h], rax
0x14003021e  jmp     loc_1400302A4
0x140030223  mov     r9b, bl
0x140030226  mov     r8, [r10+1F8h]
0x14003022d  mov     rdx, r10
0x140030230  call    UdfDeEmbedFileData
0x140030235  mov     rax, [r14+158h]
0x14003023c  btr     dword ptr [rax+0D4h], 13h
0x140030244  mov     rcx, cs:WPP_GLOBAL_Control
0x14003024b  cmp     rcx, r12
0x14003024e  jz      short loc_14003026C
0x140030250  mov     eax, [rcx+2Ch]
0x140030253  test    bl, al
0x140030255  jz      short loc_14003026C
0x140030257  mov     edx, 46h ; 'F'
0x14003025c  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x140030263  mov     rcx, [rcx+18h]
0x140030267  call    WPP_SF_
0x14003026c  mov     r8d, [r14+44h]
0x140030270  sub     r8d, ebx
0x140030273  mov     rdx, [r14+158h]
0x14003027a  mov     rcx, [rdx+20h]
0x14003027e  add     rcx, r8
0x140030281  not     r8
0x140030284  and     rcx, r8
0x140030287  mov     [rdx+20h], rcx
0x14003028b  jmp     short loc_1400302A4
0x14003028d  mov     rcx, [r10+20h]
0x140030291  add     rcx, rdx
0x140030294  not     rdx
0x140030297  and     rcx, rdx
0x14003029a  mov     [r10+20h], rcx
0x14003029e  jmp     short loc_1400302A4
0x1400302a0  add     [r10+20h], rcx
0x1400302a4  mov     rcx, [r14+158h]
0x1400302ab  mov     rax, [rcx+20h]
0x1400302af  mov     [rcx+28h], rax
0x1400302b3  mov     rcx, [r14+158h]
0x1400302ba  mov     rax, [rcx+28h]
0x1400302be  mov     [rcx+18h], rax
0x1400302c2  mov     rcx, r14
0x1400302c5  call    UdfVatHeaderTailSize
0x1400302ca  mov     ecx, eax
0x1400302cc  mov     rax, [r14+158h]
0x1400302d3  mov     rdx, [rax+20h]
0x1400302d7  sub     rdx, rcx
0x1400302da  shr     rdx, 2
0x1400302de  mov     eax, [r14+44h]
0x1400302e2  imul    rdx, rax
0x1400302e6  mov     rax, [r14+160h]
0x1400302ed  mov     [rax+28h], rdx
0x1400302f1  mov     rax, [r14+160h]
0x1400302f8  mov     [rax+18h], rdx
0x1400302fc  mov     rax, [r14+160h]
0x140030303  mov     [rax+20h], rdx
0x140030307  mov     rcx, [r14+158h]
0x14003030e  lea     rdx, [rcx+18h]; FileSizes
0x140030312  mov     rcx, [rcx+1F8h]; FileObject
0x140030319  call    cs:__imp_CcSetFileSizes
0x140030320  nop     dword ptr [rax+rax+00h]
0x140030325  mov     rcx, [r14+160h]
0x14003032c  lea     rdx, [rcx+18h]; FileSizes
0x140030330  mov     rcx, [rcx+1F8h]; FileObject
0x140030337  call    cs:__imp_CcSetFileSizes
0x14003033e  nop     dword ptr [rax+rax+00h]
0x140030343  mov     rcx, cs:WPP_GLOBAL_Control
0x14003034a  cmp     rcx, r12
0x14003034d  jz      short loc_140030376
0x14003034f  mov     eax, [rcx+2Ch]
0x140030352  test    bl, al
0x140030354  jz      short loc_140030376
0x140030356  mov     r9, [r14+158h]
0x14003035d  mov     edx, 47h ; 'G'
0x140030362  mov     r9, [r9+20h]
0x140030366  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14003036d  mov     rcx, [rcx+18h]
0x140030371  call    WPP_SF_q
0x140030376  xorps   xmm0, xmm0
0x140030379  movdqu  xmmword ptr [rsp+0B8h+BcbVoid], xmm0
0x14003037f  mov     ecx, [r14+1D8h]
0x140030386  mov     eax, [r14+1DCh]
0x14003038d  lea     rdx, [rcx+rax*4]
0x140030391  mov     qword ptr [rsp+0B8h+FileOffset], rdx
0x140030396  mov     r8d, [r14+44h]
0x14003039a  lea     eax, [r8-1]
0x14003039e  and     eax, edx
0x1400303a0  sub     r8d, eax; Length
0x1400303a3  mov     rcx, [r14+158h]
0x1400303aa  lea     rax, [rsp+0B8h+BcbVoid]
0x1400303af  mov     [rsp+0B8h+Buffer], rax; Buffer
0x1400303b4  lea     rax, [rsp+0B8h+BcbVoid+8]
0x1400303b9  mov     [rsp+0B8h+Bcb], rax; Bcb
0x1400303be  mov     r9d, ebx; Flags
0x1400303c1  lea     rdx, [rsp+0B8h+FileOffset]; FileOffset
0x1400303c6  mov     rcx, [rcx+1F8h]; FileObject
0x1400303cd  call    cs:__imp_CcPinRead
0x1400303d4  nop     dword ptr [rax+rax+00h]
0x1400303d9  mov     rax, [rsp+0B8h+BcbVoid]
0x1400303de  mov     [rax], r13b
0x1400303e1  mov     ecx, [r14+44h]
0x1400303e5  lea     eax, [rcx-1]
0x1400303e8  and     eax, dword ptr [rsp+0B8h+FileOffset]
0x1400303ec  sub     ecx, eax
0x1400303ee  mov     r8d, ecx; Size
0x1400303f1  mov     edx, 0FFh; Val
0x1400303f6  mov     rcx, [rsp+0B8h+BcbVoid]; void *
0x1400303fb  call    memset
0x140030400  xor     edx, edx; Lsn
0x140030402  mov     rcx, [rsp+0B8h+BcbVoid+8]; BcbVoid
0x140030407  call    cs:__imp_CcSetDirtyPinnedData
0x14003040e  nop     dword ptr [rax+rax+00h]
0x140030413  mov     ecx, [r14+44h]
0x140030417  sub     ecx, ebx
0x140030419  mov     rdx, qword ptr [rsp+0B8h+FileOffset]
0x14003041e  add     rdx, 4
0x140030422  add     rdx, rcx
0x140030425  not     rcx
0x140030428  and     rdx, rcx
0x14003042b  mov     qword ptr [rsp+0B8h+FileOffset], rdx
0x140030430  mov     rcx, [r14+158h]
0x140030437  cmp     rdx, [rcx+20h]
0x14003043b  jge     short loc_140030456
0x14003043d  lea     rdx, [rsp+0B8h+BcbVoid+8]
0x140030442  call    UdfUnpinData
0x140030447  mov     [rsp+0B8h+BcbVoid], r13
0x14003044c  mov     rdx, qword ptr [rsp+0B8h+FileOffset]
0x140030451  jmp     loc_140030396
0x140030456  mov     eax, 0Ah
0x14003045b  cmp     ax, [r14+858h]
0x140030463  jz      short loc_1400304DE
0x140030465  mov     edi, [r14+44h]
0x140030469  mov     esi, edi
0x14003046b  neg     rsi
0x14003046e  and     rsi, [rsp+0B8h+BcbVoid]
0x140030473  lea     eax, [rdi-1]
0x140030476  and     eax, [rcx+20h]
0x140030479  cmovnz  edi, eax
0x14003047c  mov     rcx, r14
0x14003047f  call    UdfVatHeaderTailSize
0x140030484  mov     ecx, edi
0x140030486  sub     ecx, eax
0x140030488  mov     ebx, ecx
0x14003048a  mov     [rcx+rsi], r13b
0x14003048e  lea     rcx, [rsi+1]
0x140030492  add     rcx, rbx; void *
0x140030495  xorps   xmm0, xmm0
0x140030498  xor     eax, eax
0x14003049a  movups  xmmword ptr [rcx], xmm0
0x14003049d  mov     [rcx+0Fh], rax
0x1400304a1  movzx   r8d, cs:UdfVatTableIdentifier; Size
0x1400304a9  mov     rdx, cs:Src; Src
0x1400304b0  call    memmove
0x1400304b5  mov     word ptr [rbx+rsi+1Ah], 6
0x1400304bc  movzx   eax, word ptr [r14+85Ah]
0x1400304c4  mov     [rbx+rsi+18h], ax
0x1400304c9  mov     [rbx+rsi+1Ch], r13d
0x1400304ce  mov     rdx, [r14+1D0h]
0x1400304d5  lea     ecx, [rdi-4]
0x1400304d8  mov     eax, [rdx+0Ch]
0x1400304db  mov     [rcx+rsi], eax
0x1400304de  lea     rdx, [rsp+0B8h+BcbVoid+8]
0x1400304e3  call    UdfUnpinData
0x1400304e8  mov     eax, [r14+1DCh]
0x1400304ef  mov     [rsp+0B8h+arg_10], eax
0x1400304f6  inc     eax
0x1400304f8  mov     [r14+1DCh], eax
0x1400304ff  mov     rcx, [r14+158h]
0x140030506  mov     rcx, [rcx+10h]; Resource
0x14003050a  call    cs:__imp_ExReleaseResourceLite
0x140030511  nop     dword ptr [rax+rax+00h]
0x140030516  mov     rax, [r14+158h]
0x14003051d  mov     rcx, [rax+88h]
0x140030524  mov     rcx, [rcx+50h]
0x140030528  add     rcx, 8
0x14003052c  jmp     loc_14003070A
0x140030531  mov     r8d, esi
0x140030534  mov     rdx, r14
0x140030537  test    dword ptr [r14+30h], 20000000h
0x14003053f  jz      short loc_14003056E
0x140030541  lea     rax, [rsp+0B8h+arg_10]
0x140030549  mov     [rsp+0B8h+Bcb], rax
0x14003054e  mov     r9d, 1
0x140030554  call    UdfPowReserveMetaDataBlocks
0x140030559  test    eax, eax
0x14003055b  jns     loc_140030716
0x140030561  mov     [rsp+0B8h+arg_10], r13d
0x140030569  jmp     loc_140030716
0x14003056e  mov     ebx, 1
0x140030573  mov     r9d, ebx
0x140030576  call    UdfPrepareForAllocationChange
0x14003057b  imul    r15, rsi, 0C8h
0x140030582  dec     dword ptr [r15+r14+29Ch]
0x14003058a  mov     [r14+668h], r13
0x140030591  lea     r13, [r14+630h]
0x140030598  mov     rcx, r13; FastMutex
0x14003059b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400305a2  nop     dword ptr [rax+rax+00h]
0x1400305a7  lea     rdx, [r14+228h]
0x1400305ae  add     rdx, r15
0x1400305b1  xor     r9d, r9d
0x1400305b4  xor     r8d, r8d
0x1400305b7  mov     rcx, rdi
0x1400305ba  call    UdfAcquireResource
0x1400305bf  cmp     esi, ebx
0x1400305c1  jnz     short loc_1400305CD
0x1400305c3  mov     r9d, [r15+r14+1F0h]
0x1400305cb  jmp     short loc_1400305D0
0x1400305cd  xor     r9d, r9d
0x1400305d0  lea     rax, [rsp+0B8h+var_78]
0x1400305d5  mov     [rsp+0B8h+Buffer], rax
0x1400305da  lea     rax, [rsp+0B8h+arg_10]
0x1400305e2  mov     [rsp+0B8h+Bcb], rax
0x1400305e7  mov     r8d, ebx
0x1400305ea  mov     edx, esi
0x1400305ec  mov     rcx, rdi
0x1400305ef  call    UdfFindFreeBitmapBlocks
0x1400305f4  mov     r9d, [rsp+0B8h+var_78]
0x1400305f9  test    r9d, r9d
0x1400305fc  jnz     short loc_14003060E
0x1400305fe  xor     r8d, r8d
0x140030601  mov     edx, 0C00000E5h
0x140030606  mov     rcx, rdi
0x140030609  call    UdfRaiseStatusEx
0x14003060e  lea     r12, WPP_GLOBAL_Control
0x140030615  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
