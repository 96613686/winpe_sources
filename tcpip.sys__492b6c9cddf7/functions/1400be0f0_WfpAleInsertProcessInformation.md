# WfpAleInsertProcessInformation

- ea: `0x1400be0f0`
- end: `0x1400be4ef`
- name: `WfpAleInsertProcessInformation`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140179de0`

## callees

- `0x1400525d0`
- `0x140053e04`
- `0x140053f20`
- `0x14008a370`
- `0x1400be0f0`
- `0x1400be4f8`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400be37b`
- `ntoskrnl!ObfReferenceObject` at `0x1400be37b`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400be2c1`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400be2c1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400be160`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400be160`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be26b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be2ec`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be26b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be2ec`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400be231`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400be231`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be20d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be20d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400be24f`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400be24f`
- `NDIS!NdisReleaseRWLock` at `0x1400be31d`
- `NDIS!NdisReleaseRWLock` at `0x1400be31d`

## string_xrefs

- `0x1400be3c0`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400be44a`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400be46e`: `RtlCreateHashTable`

## pseudocode

```c
__int64 __fastcall WfpAleInsertProcessInformation(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  char *v10; // rbx
  __int64 v11; // rcx
  char *v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rcx
  ULONG_PTR v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  _DWORD *v20; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-58h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( a6 )
    *a6 = 0;
  v10 = (char *)processTableLookasideList + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
  if ( !v10[176] )
    PplpLazyInitializeLookasideList(processTableLookasideList, v10 + 64);
  v12 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64));
  if ( !v12 )
  {
    v22 = WfpReportSysErrorAsNtStatus(v11, "WfpAllocateFromPerProcessorLookasideList", 3221225495LL);
    v16 = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
          v22);
      }
LABEL_23:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAleInsertProcessInformation",
          v16);
      }
      return v16;
    }
  }
  memset(v12 + 8, 0, 0x78u);
  *(_QWORD *)v12 = a1;
  v13 = ((HIBYTE(a1)
        + 37
        * (BYTE6(a1)
         + 37
         * (BYTE5(a1)
          + 37 * (BYTE4(a1) + 37 * (BYTE3(a1) + 37 * (BYTE2(a1) + 37 * (BYTE1(a1) + 37LL * (unsigned __int8)a1))))))) << gAleNumHashEntryBits)
      | 3;
  RtlInitUnicodeString((PUNICODE_STRING)(v12 + 8), a3);
  *((_QWORD *)v12 + 3) = a5;
  *((_QWORD *)v12 + 4) = a2;
  *((_QWORD *)v12 + 6) = a4;
  *((_QWORD *)v12 + 15) = v13;
  LOBYTE(v13) = KeGetCurrentIrql();
  NdisAcquireRWLockWrite(gAleHashtableLock, &LockState, 0);
  if ( (_BYTE)v13 != 2 && gWfpPerProContext )
  {
    v14 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v14 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v14 = 4;
  }
  v15 = *((_QWORD *)v12 + 15);
  v16 = 0;
  if ( !v15 )
  {
    v15 = -1;
    *((_QWORD *)v12 + 15) = -1;
  }
  if ( RtlInsertEntryHashTable(&gAleMasterHashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v12 + 104), v15, 0)
    || (v23 = WfpReportSysErrorAsNtStatus(v18, "RtlCreateHashTable", 3221225495LL), (v16 = v23) == 0)
    || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
  {
    if ( !v16 )
    {
      WfpAleInitializeWaitRef_0(v12 + 72, v17, v19, v12);
      *((_DWORD *)v12 + 18) = (*((_DWORD *)v12 + 18) + 4)
                            ^ ((unsigned __int8)*((_DWORD *)v12 + 18)
                             ^ (unsigned __int8)(*((_DWORD *)v12 + 18) + 4))
                            & 3;
      ObfReferenceObject(*(PVOID *)v12);
      if ( a6 )
      {
        *((_DWORD *)v12 + 18) = (*((_DWORD *)v12 + 18) + 4)
                              ^ ((unsigned __int8)*((_DWORD *)v12 + 18)
                               ^ (unsigned __int8)(*((_DWORD *)v12 + 18) + 4))
                              & 3;
        *a6 = v12;
      }
    }
  }
  else
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpHashtableInsert",
      v23);
  }
  if ( gWfpPerProContext )
  {
    v20 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v20 == 4 )
      *v20 = 0;
  }
  NdisReleaseRWLock(gAleHashtableLock, &LockState);
  if ( v16 )
  {
    if ( v12 )
      PplFreeToLookasideList(processTableLookasideList);
    goto LABEL_23;
  }
  return v16;
}

```

## disassembly

```asm
0x1400be0f0  mov     [rsp+arg_0], rcx
0x1400be0f5  push    rbx
0x1400be0f6  push    rbp
0x1400be0f7  push    rsi
0x1400be0f8  push    rdi
0x1400be0f9  push    r12
0x1400be0fb  push    r13
0x1400be0fd  push    r14
0x1400be0ff  push    r15
0x1400be101  sub     rsp, 48h
0x1400be105  mov     r14, [rsp+88h+arg_28]
0x1400be10d  xor     eax, eax
0x1400be10f  xor     r13d, r13d
0x1400be112  mov     word ptr [rsp+88h+LockState.OldIrql], ax
0x1400be117  mov     [rsp+88h+LockState.Flags], al
0x1400be11b  mov     rbp, r9
0x1400be11e  mov     r15, r8
0x1400be121  mov     r12, rdx
0x1400be124  mov     rdi, rcx
0x1400be127  test    r14, r14
0x1400be12a  jz      short loc_1400BE12F
0x1400be12c  mov     [r14], r13
0x1400be12f  mov     eax, gs:1A4h
0x1400be137  mov     rcx, cs:processTableLookasideList
0x1400be13e  lea     ebx, [rax+1]
0x1400be141  shl     rbx, 7
0x1400be145  add     rbx, rcx
0x1400be148  movzx   eax, byte ptr [rbx+0B0h]
0x1400be14f  test    al, al
0x1400be151  jnz     short loc_1400BE15C
0x1400be153  lea     rdx, [rbx+40h]
0x1400be157  call    PplpLazyInitializeLookasideList
0x1400be15c  lea     rcx, [rbx+40h]; Lookaside
0x1400be160  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400be167  nop     dword ptr [rax+rax+00h]
0x1400be16c  mov     rsi, rax
0x1400be16f  test    rax, rax
0x1400be172  jz      loc_1400BE3BA
0x1400be178  lea     rcx, [rsi+8]; void *
0x1400be17c  xor     edx, edx; Val
0x1400be17e  mov     r8d, 78h ; 'x'; Size
0x1400be184  call    memset
0x1400be189  movzx   eax, dil
0x1400be18d  imul    rcx, rax, 25h ; '%'
0x1400be191  movzx   eax, byte ptr [rsp+88h+arg_0+1]
0x1400be199  add     rcx, rax
0x1400be19c  mov     [rsi], rdi
0x1400be19f  movzx   eax, byte ptr [rsp+88h+arg_0+2]
0x1400be1a7  imul    rdx, rcx, 25h ; '%'
0x1400be1ab  add     rdx, rax
0x1400be1ae  movzx   eax, byte ptr [rsp+88h+arg_0+3]
0x1400be1b6  imul    rcx, rdx, 25h ; '%'
0x1400be1ba  add     rcx, rax
0x1400be1bd  movzx   eax, byte ptr [rsp+88h+arg_0+4]
0x1400be1c5  imul    rdx, rcx, 25h ; '%'
0x1400be1c9  add     rdx, rax
0x1400be1cc  movzx   eax, byte ptr [rsp+88h+arg_0+5]
0x1400be1d4  imul    rcx, rdx, 25h ; '%'
0x1400be1d8  add     rcx, rax
0x1400be1db  movzx   eax, byte ptr [rsp+88h+arg_0+6]
0x1400be1e3  imul    rdx, rcx, 25h ; '%'
0x1400be1e7  mov     ecx, cs:gAleNumHashEntryBits
0x1400be1ed  add     rdx, rax
0x1400be1f0  movzx   eax, byte ptr [rsp+88h+arg_0+7]
0x1400be1f8  imul    rbx, rdx, 25h ; '%'
0x1400be1fc  mov     rdx, r15; SourceString
0x1400be1ff  add     rbx, rax
0x1400be202  shl     rbx, cl
0x1400be205  lea     rcx, [rsi+8]; DestinationString
0x1400be209  or      rbx, 3
0x1400be20d  call    cs:__imp_RtlInitUnicodeString
0x1400be214  nop     dword ptr [rax+rax+00h]
0x1400be219  mov     rax, [rsp+88h+arg_20]
0x1400be221  mov     [rsi+18h], rax
0x1400be225  mov     [rsi+20h], r12
0x1400be229  mov     [rsi+30h], rbp
0x1400be22d  mov     [rsi+78h], rbx
0x1400be231  call    cs:__imp_KeGetCurrentIrql
0x1400be238  nop     dword ptr [rax+rax+00h]
0x1400be23d  mov     rcx, cs:gAleHashtableLock; Lock
0x1400be244  lea     rdx, [rsp+88h+LockState]; LockState
0x1400be249  xor     r8d, r8d; Flags
0x1400be24c  movzx   ebx, al
0x1400be24f  call    cs:__imp_NdisAcquireRWLockWrite
0x1400be256  nop     dword ptr [rax+rax+00h]
0x1400be25b  cmp     bl, 2
0x1400be25e  jz      short loc_1400BE29C
0x1400be260  cmp     cs:gWfpPerProContext, r13
0x1400be267  jz      short loc_1400BE29C
0x1400be269  xor     ecx, ecx; ProcNumber
0x1400be26b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400be272  nop     dword ptr [rax+rax+00h]
0x1400be277  lea     ecx, [rax+rax*8]
0x1400be27a  mov     rax, cs:gWfpPerProContext
0x1400be281  shl     ecx, 3
0x1400be284  mov     rcx, [rcx+rax]
0x1400be288  mov     rax, ds:0FFFFF78000000008h
0x1400be292  mov     [rcx+8], rax
0x1400be296  mov     dword ptr [rcx], 4
0x1400be29c  mov     r8, [rsi+78h]
0x1400be2a0  lea     rdx, [rsi+68h]; Entry
0x1400be2a4  mov     rbx, r13
0x1400be2a7  test    r8, r8
0x1400be2aa  jnz     short loc_1400BE2B7
0x1400be2ac  mov     r8, 0FFFFFFFFFFFFFFFFh; Signature
0x1400be2b3  mov     [rdx+10h], r8
0x1400be2b7  xor     r9d, r9d; Context
0x1400be2ba  lea     rcx, gAleMasterHashTable; HashTable
0x1400be2c1  call    cs:__imp_RtlInsertEntryHashTable
0x1400be2c8  nop     dword ptr [rax+rax+00h]
0x1400be2cd  lea     rdi, WPP_GLOBAL_Control
0x1400be2d4  test    al, al
0x1400be2d6  jz      loc_1400BE468
0x1400be2dc  test    rbx, rbx
0x1400be2df  jz      short loc_1400BE347
0x1400be2e1  cmp     cs:gWfpPerProContext, r13
0x1400be2e8  jz      short loc_1400BE311
0x1400be2ea  xor     ecx, ecx; ProcNumber
0x1400be2ec  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400be2f3  nop     dword ptr [rax+rax+00h]
0x1400be2f8  lea     ecx, [rax+rax*8]
0x1400be2fb  mov     rax, cs:gWfpPerProContext
0x1400be302  shl     ecx, 3
0x1400be305  mov     rcx, [rcx+rax]
0x1400be309  cmp     dword ptr [rcx], 4
0x1400be30c  jnz     short loc_1400BE311
0x1400be30e  mov     [rcx], r13d
0x1400be311  mov     rcx, cs:gAleHashtableLock; Lock
0x1400be318  lea     rdx, [rsp+88h+LockState]; LockState
0x1400be31d  call    cs:__imp_NdisReleaseRWLock
0x1400be324  nop     dword ptr [rax+rax+00h]
0x1400be329  test    rbx, rbx
0x1400be32c  jnz     loc_1400BE4D2
0x1400be332  mov     rax, rbx
0x1400be335  add     rsp, 48h
0x1400be339  pop     r15
0x1400be33b  pop     r14
0x1400be33d  pop     r13
0x1400be33f  pop     r12
0x1400be341  pop     rdi
0x1400be342  pop     rsi
0x1400be343  pop     rbp
0x1400be344  pop     rbx
0x1400be345  retn
0x1400be347  lea     rbp, [rsi+48h]
0x1400be34b  mov     r9, rsi
0x1400be34e  mov     rcx, rbp
0x1400be351  call    WfpAleInitializeWaitRef_0
0x1400be356  mov     [rsp+88h+arg_28], rbp
0x1400be35e  mov     r8, [rsp+88h+arg_28]
0x1400be366  mov     eax, [r8]
0x1400be369  lea     ecx, [rax+4]
0x1400be36c  mov     edx, ecx
0x1400be36e  xor     edx, eax
0x1400be370  and     edx, 3
0x1400be373  xor     edx, ecx
0x1400be375  mov     [r8], edx
0x1400be378  mov     rcx, [rsi]; Object
0x1400be37b  call    cs:__imp_ObfReferenceObject
0x1400be382  nop     dword ptr [rax+rax+00h]
0x1400be387  test    r14, r14
0x1400be38a  jz      loc_1400BE2E1
0x1400be390  mov     [rsp+88h+arg_28], rbp
0x1400be398  mov     r8, [rsp+88h+arg_28]
0x1400be3a0  mov     eax, [r8]
0x1400be3a3  lea     ecx, [rax+4]
0x1400be3a6  mov     edx, ecx
0x1400be3a8  xor     edx, eax
0x1400be3aa  and     edx, 3
0x1400be3ad  xor     edx, ecx
0x1400be3af  mov     [r8], edx
0x1400be3b2  mov     [r14], rsi
0x1400be3b5  jmp     loc_1400BE2E1
0x1400be3ba  mov     r8d, 0C0000017h
0x1400be3c0  lea     rdx, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400be3c7  call    WfpReportSysErrorAsNtStatus
0x1400be3cc  mov     rbx, rax
0x1400be3cf  test    rax, rax
0x1400be3d2  jz      loc_1400BE178
0x1400be3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be3df  lea     rdi, WPP_GLOBAL_Control
0x1400be3e6  cmp     rcx, rdi
0x1400be3e9  jz      short loc_1400BE3F1
0x1400be3eb  cmp     byte ptr [rcx+29h], 2
0x1400be3ef  jnb     short loc_1400BE43D
0x1400be3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be3f8  cmp     rcx, rdi
0x1400be3fb  jz      loc_1400BE332
0x1400be401  cmp     byte ptr [rcx+29h], 2
0x1400be405  jb      loc_1400BE332
0x1400be40b  test    dword ptr [rcx+2Ch], 1000h
0x1400be412  jz      loc_1400BE332
0x1400be418  mov     rcx, [rcx+18h]
0x1400be41c  lea     r9, aWfpaleinsertpr; "WfpAleInsertProcessInformation"
0x1400be423  mov     edx, 0Fh
0x1400be428  mov     [rsp+88h+var_68], ebx
0x1400be42c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400be433  call    WPP_SF_sd
0x1400be438  jmp     loc_1400BE332
0x1400be43d  test    dword ptr [rcx+2Ch], 1000h
0x1400be444  jz      short loc_1400BE3F1
0x1400be446  mov     rcx, [rcx+18h]
0x1400be44a  lea     r9, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400be451  mov     edx, 0Fh
0x1400be456  mov     [rsp+88h+var_68], eax
0x1400be45a  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400be461  call    WPP_SF_sd
0x1400be466  jmp     short loc_1400BE3F1
0x1400be468  mov     r8d, 0C0000017h
0x1400be46e  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x1400be475  call    WfpReportSysErrorAsNtStatus
0x1400be47a  mov     rbx, rax
0x1400be47d  test    rax, rax
0x1400be480  jz      loc_1400BE2DC
0x1400be486  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be48d  cmp     rcx, rdi
0x1400be490  jz      loc_1400BE2DC
0x1400be496  cmp     byte ptr [rcx+29h], 2
0x1400be49a  jb      loc_1400BE2DC
0x1400be4a0  test    dword ptr [rcx+2Ch], 1000h
0x1400be4a7  jz      loc_1400BE2DC
0x1400be4ad  mov     rcx, [rcx+18h]
0x1400be4b1  lea     r9, aWfphashtablein; "WfpHashtableInsert"
0x1400be4b8  mov     edx, 0Fh
0x1400be4bd  mov     [rsp+88h+var_68], eax
0x1400be4c1  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400be4c8  call    WPP_SF_sd
0x1400be4cd  jmp     loc_1400BE2E1
0x1400be4d2  test    rsi, rsi
0x1400be4d5  jz      loc_1400BE3F1
0x1400be4db  mov     rcx, cs:processTableLookasideList
0x1400be4e2  mov     rdx, rsi
0x1400be4e5  call    PplFreeToLookasideList
0x1400be4ea  jmp     loc_1400BE3F1
```
