# WfpAleInsertProcessInformation

- ea: `0x1400be120`
- end: `0x1400be51f`
- name: `WfpAleInsertProcessInformation`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140179f20`

## callees

- `0x140052870`
- `0x1400540a4`
- `0x1400541c0`
- `0x14008b220`
- `0x1400be120`
- `0x1400be528`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400be3ab`
- `ntoskrnl!ObfReferenceObject` at `0x1400be3ab`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400be2f1`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400be2f1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400be190`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400be190`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be29b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be31c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be29b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400be31c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400be261`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400be261`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be23d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be23d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400be27f`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400be27f`
- `NDIS!NdisReleaseRWLock` at `0x1400be34d`
- `NDIS!NdisReleaseRWLock` at `0x1400be34d`

## string_xrefs

- `0x1400be3f0`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400be47a`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400be49e`: `RtlCreateHashTable`

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
          (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
          (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
      (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
0x1400be120  mov     [rsp+arg_0], rcx
0x1400be125  push    rbx
0x1400be126  push    rbp
0x1400be127  push    rsi
0x1400be128  push    rdi
0x1400be129  push    r12
0x1400be12b  push    r13
0x1400be12d  push    r14
0x1400be12f  push    r15
0x1400be131  sub     rsp, 48h
0x1400be135  mov     r14, [rsp+88h+arg_28]
0x1400be13d  xor     eax, eax
0x1400be13f  xor     r13d, r13d
0x1400be142  mov     word ptr [rsp+88h+LockState.OldIrql], ax
0x1400be147  mov     [rsp+88h+LockState.Flags], al
0x1400be14b  mov     rbp, r9
0x1400be14e  mov     r15, r8
0x1400be151  mov     r12, rdx
0x1400be154  mov     rdi, rcx
0x1400be157  test    r14, r14
0x1400be15a  jz      short loc_1400BE15F
0x1400be15c  mov     [r14], r13
0x1400be15f  mov     eax, gs:1A4h
0x1400be167  mov     rcx, cs:processTableLookasideList
0x1400be16e  lea     ebx, [rax+1]
0x1400be171  shl     rbx, 7
0x1400be175  add     rbx, rcx
0x1400be178  movzx   eax, byte ptr [rbx+0B0h]
0x1400be17f  test    al, al
0x1400be181  jnz     short loc_1400BE18C
0x1400be183  lea     rdx, [rbx+40h]
0x1400be187  call    PplpLazyInitializeLookasideList
0x1400be18c  lea     rcx, [rbx+40h]; Lookaside
0x1400be190  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400be197  nop     dword ptr [rax+rax+00h]
0x1400be19c  mov     rsi, rax
0x1400be19f  test    rax, rax
0x1400be1a2  jz      loc_1400BE3EA
0x1400be1a8  lea     rcx, [rsi+8]; void *
0x1400be1ac  xor     edx, edx; Val
0x1400be1ae  mov     r8d, 78h ; 'x'; Size
0x1400be1b4  call    memset
0x1400be1b9  movzx   eax, dil
0x1400be1bd  imul    rcx, rax, 25h ; '%'
0x1400be1c1  movzx   eax, byte ptr [rsp+88h+arg_0+1]
0x1400be1c9  add     rcx, rax
0x1400be1cc  mov     [rsi], rdi
0x1400be1cf  movzx   eax, byte ptr [rsp+88h+arg_0+2]
0x1400be1d7  imul    rdx, rcx, 25h ; '%'
0x1400be1db  add     rdx, rax
0x1400be1de  movzx   eax, byte ptr [rsp+88h+arg_0+3]
0x1400be1e6  imul    rcx, rdx, 25h ; '%'
0x1400be1ea  add     rcx, rax
0x1400be1ed  movzx   eax, byte ptr [rsp+88h+arg_0+4]
0x1400be1f5  imul    rdx, rcx, 25h ; '%'
0x1400be1f9  add     rdx, rax
0x1400be1fc  movzx   eax, byte ptr [rsp+88h+arg_0+5]
0x1400be204  imul    rcx, rdx, 25h ; '%'
0x1400be208  add     rcx, rax
0x1400be20b  movzx   eax, byte ptr [rsp+88h+arg_0+6]
0x1400be213  imul    rdx, rcx, 25h ; '%'
0x1400be217  mov     ecx, cs:gAleNumHashEntryBits
0x1400be21d  add     rdx, rax
0x1400be220  movzx   eax, byte ptr [rsp+88h+arg_0+7]
0x1400be228  imul    rbx, rdx, 25h ; '%'
0x1400be22c  mov     rdx, r15; SourceString
0x1400be22f  add     rbx, rax
0x1400be232  shl     rbx, cl
0x1400be235  lea     rcx, [rsi+8]; DestinationString
0x1400be239  or      rbx, 3
0x1400be23d  call    cs:__imp_RtlInitUnicodeString
0x1400be244  nop     dword ptr [rax+rax+00h]
0x1400be249  mov     rax, [rsp+88h+arg_20]
0x1400be251  mov     [rsi+18h], rax
0x1400be255  mov     [rsi+20h], r12
0x1400be259  mov     [rsi+30h], rbp
0x1400be25d  mov     [rsi+78h], rbx
0x1400be261  call    cs:__imp_KeGetCurrentIrql
0x1400be268  nop     dword ptr [rax+rax+00h]
0x1400be26d  mov     rcx, cs:gAleHashtableLock; Lock
0x1400be274  lea     rdx, [rsp+88h+LockState]; LockState
0x1400be279  xor     r8d, r8d; Flags
0x1400be27c  movzx   ebx, al
0x1400be27f  call    cs:__imp_NdisAcquireRWLockWrite
0x1400be286  nop     dword ptr [rax+rax+00h]
0x1400be28b  cmp     bl, 2
0x1400be28e  jz      short loc_1400BE2CC
0x1400be290  cmp     cs:gWfpPerProContext, r13
0x1400be297  jz      short loc_1400BE2CC
0x1400be299  xor     ecx, ecx; ProcNumber
0x1400be29b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400be2a2  nop     dword ptr [rax+rax+00h]
0x1400be2a7  lea     ecx, [rax+rax*8]
0x1400be2aa  mov     rax, cs:gWfpPerProContext
0x1400be2b1  shl     ecx, 3
0x1400be2b4  mov     rcx, [rcx+rax]
0x1400be2b8  mov     rax, ds:0FFFFF78000000008h
0x1400be2c2  mov     [rcx+8], rax
0x1400be2c6  mov     dword ptr [rcx], 4
0x1400be2cc  mov     r8, [rsi+78h]
0x1400be2d0  lea     rdx, [rsi+68h]; Entry
0x1400be2d4  mov     rbx, r13
0x1400be2d7  test    r8, r8
0x1400be2da  jnz     short loc_1400BE2E7
0x1400be2dc  mov     r8, 0FFFFFFFFFFFFFFFFh; Signature
0x1400be2e3  mov     [rdx+10h], r8
0x1400be2e7  xor     r9d, r9d; Context
0x1400be2ea  lea     rcx, gAleMasterHashTable; HashTable
0x1400be2f1  call    cs:__imp_RtlInsertEntryHashTable
0x1400be2f8  nop     dword ptr [rax+rax+00h]
0x1400be2fd  lea     rdi, WPP_GLOBAL_Control
0x1400be304  test    al, al
0x1400be306  jz      loc_1400BE498
0x1400be30c  test    rbx, rbx
0x1400be30f  jz      short loc_1400BE377
0x1400be311  cmp     cs:gWfpPerProContext, r13
0x1400be318  jz      short loc_1400BE341
0x1400be31a  xor     ecx, ecx; ProcNumber
0x1400be31c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400be323  nop     dword ptr [rax+rax+00h]
0x1400be328  lea     ecx, [rax+rax*8]
0x1400be32b  mov     rax, cs:gWfpPerProContext
0x1400be332  shl     ecx, 3
0x1400be335  mov     rcx, [rcx+rax]
0x1400be339  cmp     dword ptr [rcx], 4
0x1400be33c  jnz     short loc_1400BE341
0x1400be33e  mov     [rcx], r13d
0x1400be341  mov     rcx, cs:gAleHashtableLock; Lock
0x1400be348  lea     rdx, [rsp+88h+LockState]; LockState
0x1400be34d  call    cs:__imp_NdisReleaseRWLock
0x1400be354  nop     dword ptr [rax+rax+00h]
0x1400be359  test    rbx, rbx
0x1400be35c  jnz     loc_1400BE502
0x1400be362  mov     rax, rbx
0x1400be365  add     rsp, 48h
0x1400be369  pop     r15
0x1400be36b  pop     r14
0x1400be36d  pop     r13
0x1400be36f  pop     r12
0x1400be371  pop     rdi
0x1400be372  pop     rsi
0x1400be373  pop     rbp
0x1400be374  pop     rbx
0x1400be375  retn
0x1400be377  lea     rbp, [rsi+48h]
0x1400be37b  mov     r9, rsi
0x1400be37e  mov     rcx, rbp
0x1400be381  call    WfpAleInitializeWaitRef_0
0x1400be386  mov     [rsp+88h+arg_28], rbp
0x1400be38e  mov     r8, [rsp+88h+arg_28]
0x1400be396  mov     eax, [r8]
0x1400be399  lea     ecx, [rax+4]
0x1400be39c  mov     edx, ecx
0x1400be39e  xor     edx, eax
0x1400be3a0  and     edx, 3
0x1400be3a3  xor     edx, ecx
0x1400be3a5  mov     [r8], edx
0x1400be3a8  mov     rcx, [rsi]; Object
0x1400be3ab  call    cs:__imp_ObfReferenceObject
0x1400be3b2  nop     dword ptr [rax+rax+00h]
0x1400be3b7  test    r14, r14
0x1400be3ba  jz      loc_1400BE311
0x1400be3c0  mov     [rsp+88h+arg_28], rbp
0x1400be3c8  mov     r8, [rsp+88h+arg_28]
0x1400be3d0  mov     eax, [r8]
0x1400be3d3  lea     ecx, [rax+4]
0x1400be3d6  mov     edx, ecx
0x1400be3d8  xor     edx, eax
0x1400be3da  and     edx, 3
0x1400be3dd  xor     edx, ecx
0x1400be3df  mov     [r8], edx
0x1400be3e2  mov     [r14], rsi
0x1400be3e5  jmp     loc_1400BE311
0x1400be3ea  mov     r8d, 0C0000017h
0x1400be3f0  lea     rdx, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400be3f7  call    WfpReportSysErrorAsNtStatus
0x1400be3fc  mov     rbx, rax
0x1400be3ff  test    rax, rax
0x1400be402  jz      loc_1400BE1A8
0x1400be408  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be40f  lea     rdi, WPP_GLOBAL_Control
0x1400be416  cmp     rcx, rdi
0x1400be419  jz      short loc_1400BE421
0x1400be41b  cmp     byte ptr [rcx+29h], 2
0x1400be41f  jnb     short loc_1400BE46D
0x1400be421  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be428  cmp     rcx, rdi
0x1400be42b  jz      loc_1400BE362
0x1400be431  cmp     byte ptr [rcx+29h], 2
0x1400be435  jb      loc_1400BE362
0x1400be43b  test    dword ptr [rcx+2Ch], 1000h
0x1400be442  jz      loc_1400BE362
0x1400be448  mov     rcx, [rcx+18h]
0x1400be44c  lea     r9, aWfpaleinsertpr; "WfpAleInsertProcessInformation"
0x1400be453  mov     edx, 0Fh
0x1400be458  mov     [rsp+88h+var_68], ebx
0x1400be45c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400be463  call    WPP_SF_sd
0x1400be468  jmp     loc_1400BE362
0x1400be46d  test    dword ptr [rcx+2Ch], 1000h
0x1400be474  jz      short loc_1400BE421
0x1400be476  mov     rcx, [rcx+18h]
0x1400be47a  lea     r9, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400be481  mov     edx, 0Fh
0x1400be486  mov     [rsp+88h+var_68], eax
0x1400be48a  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400be491  call    WPP_SF_sd
0x1400be496  jmp     short loc_1400BE421
0x1400be498  mov     r8d, 0C0000017h
0x1400be49e  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x1400be4a5  call    WfpReportSysErrorAsNtStatus
0x1400be4aa  mov     rbx, rax
0x1400be4ad  test    rax, rax
0x1400be4b0  jz      loc_1400BE30C
0x1400be4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be4bd  cmp     rcx, rdi
0x1400be4c0  jz      loc_1400BE30C
0x1400be4c6  cmp     byte ptr [rcx+29h], 2
0x1400be4ca  jb      loc_1400BE30C
0x1400be4d0  test    dword ptr [rcx+2Ch], 1000h
0x1400be4d7  jz      loc_1400BE30C
0x1400be4dd  mov     rcx, [rcx+18h]
0x1400be4e1  lea     r9, aWfphashtablein; "WfpHashtableInsert"
0x1400be4e8  mov     edx, 0Fh
0x1400be4ed  mov     [rsp+88h+var_68], eax
0x1400be4f1  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400be4f8  call    WPP_SF_sd
0x1400be4fd  jmp     loc_1400BE311
0x1400be502  test    rsi, rsi
0x1400be505  jz      loc_1400BE421
0x1400be50b  mov     rcx, cs:processTableLookasideList
0x1400be512  mov     rdx, rsi
0x1400be515  call    PplFreeToLookasideList
0x1400be51a  jmp     loc_1400BE421
```
