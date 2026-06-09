# WfpAleInsertProcessInformation

- ea: `0x1400c7840`
- end: `0x1400c7c3f`
- name: `WfpAleInsertProcessInformation`
- size: `1023`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017bae0`

## callees

- `0x140013140`
- `0x140014974`
- `0x140014a90`
- `0x1400ad6a0`
- `0x1400c7840`
- `0x1400c7c48`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400c7acb`
- `ntoskrnl!ObfReferenceObject` at `0x1400c7acb`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400c7a11`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400c7a11`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400c78b0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400c78b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c79bb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c7a3c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c79bb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c7a3c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c7981`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c7981`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c795d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c795d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400c799f`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400c799f`
- `NDIS!NdisReleaseRWLock` at `0x1400c7a6d`
- `NDIS!NdisReleaseRWLock` at `0x1400c7a6d`

## string_xrefs

- `0x1400c7b10`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400c7b9a`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400c7bbe`: `RtlCreateHashTable`

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
    PplpLazyInitializeLookasideList(processTableLookasideList, v10 + 64, a3, a4);
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
      WfpAleInitializeWaitRef_0((__int64)(v12 + 72), v17, v19, (__int64)v12);
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
      PplFreeToLookasideList(processTableLookasideList, v12);
    goto LABEL_23;
  }
  return v16;
}

```

## disassembly

```asm
0x1400c7840  mov     [rsp+arg_0], rcx
0x1400c7845  push    rbx
0x1400c7846  push    rbp
0x1400c7847  push    rsi
0x1400c7848  push    rdi
0x1400c7849  push    r12
0x1400c784b  push    r13
0x1400c784d  push    r14
0x1400c784f  push    r15
0x1400c7851  sub     rsp, 48h
0x1400c7855  mov     r14, [rsp+88h+arg_28]
0x1400c785d  xor     eax, eax
0x1400c785f  xor     r13d, r13d
0x1400c7862  mov     word ptr [rsp+88h+LockState.OldIrql], ax
0x1400c7867  mov     [rsp+88h+LockState.Flags], al
0x1400c786b  mov     rbp, r9
0x1400c786e  mov     r15, r8
0x1400c7871  mov     r12, rdx
0x1400c7874  mov     rdi, rcx
0x1400c7877  test    r14, r14
0x1400c787a  jz      short loc_1400C787F
0x1400c787c  mov     [r14], r13
0x1400c787f  mov     eax, gs:1A4h
0x1400c7887  mov     rcx, cs:processTableLookasideList
0x1400c788e  lea     ebx, [rax+1]
0x1400c7891  shl     rbx, 7
0x1400c7895  add     rbx, rcx
0x1400c7898  movzx   eax, byte ptr [rbx+0B0h]
0x1400c789f  test    al, al
0x1400c78a1  jnz     short loc_1400C78AC
0x1400c78a3  lea     rdx, [rbx+40h]
0x1400c78a7  call    PplpLazyInitializeLookasideList
0x1400c78ac  lea     rcx, [rbx+40h]; Lookaside
0x1400c78b0  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400c78b7  nop     dword ptr [rax+rax+00h]
0x1400c78bc  mov     rsi, rax
0x1400c78bf  test    rax, rax
0x1400c78c2  jz      loc_1400C7B0A
0x1400c78c8  lea     rcx, [rsi+8]; void *
0x1400c78cc  xor     edx, edx; Val
0x1400c78ce  mov     r8d, 78h ; 'x'; Size
0x1400c78d4  call    memset
0x1400c78d9  movzx   eax, dil
0x1400c78dd  imul    rcx, rax, 25h ; '%'
0x1400c78e1  movzx   eax, byte ptr [rsp+88h+arg_0+1]
0x1400c78e9  add     rcx, rax
0x1400c78ec  mov     [rsi], rdi
0x1400c78ef  movzx   eax, byte ptr [rsp+88h+arg_0+2]
0x1400c78f7  imul    rdx, rcx, 25h ; '%'
0x1400c78fb  add     rdx, rax
0x1400c78fe  movzx   eax, byte ptr [rsp+88h+arg_0+3]
0x1400c7906  imul    rcx, rdx, 25h ; '%'
0x1400c790a  add     rcx, rax
0x1400c790d  movzx   eax, byte ptr [rsp+88h+arg_0+4]
0x1400c7915  imul    rdx, rcx, 25h ; '%'
0x1400c7919  add     rdx, rax
0x1400c791c  movzx   eax, byte ptr [rsp+88h+arg_0+5]
0x1400c7924  imul    rcx, rdx, 25h ; '%'
0x1400c7928  add     rcx, rax
0x1400c792b  movzx   eax, byte ptr [rsp+88h+arg_0+6]
0x1400c7933  imul    rdx, rcx, 25h ; '%'
0x1400c7937  mov     ecx, cs:gAleNumHashEntryBits
0x1400c793d  add     rdx, rax
0x1400c7940  movzx   eax, byte ptr [rsp+88h+arg_0+7]
0x1400c7948  imul    rbx, rdx, 25h ; '%'
0x1400c794c  mov     rdx, r15; SourceString
0x1400c794f  add     rbx, rax
0x1400c7952  shl     rbx, cl
0x1400c7955  lea     rcx, [rsi+8]; DestinationString
0x1400c7959  or      rbx, 3
0x1400c795d  call    cs:__imp_RtlInitUnicodeString
0x1400c7964  nop     dword ptr [rax+rax+00h]
0x1400c7969  mov     rax, [rsp+88h+arg_20]
0x1400c7971  mov     [rsi+18h], rax
0x1400c7975  mov     [rsi+20h], r12
0x1400c7979  mov     [rsi+30h], rbp
0x1400c797d  mov     [rsi+78h], rbx
0x1400c7981  call    cs:__imp_KeGetCurrentIrql
0x1400c7988  nop     dword ptr [rax+rax+00h]
0x1400c798d  mov     rcx, cs:gAleHashtableLock; Lock
0x1400c7994  lea     rdx, [rsp+88h+LockState]; LockState
0x1400c7999  xor     r8d, r8d; Flags
0x1400c799c  movzx   ebx, al
0x1400c799f  call    cs:__imp_NdisAcquireRWLockWrite
0x1400c79a6  nop     dword ptr [rax+rax+00h]
0x1400c79ab  cmp     bl, 2
0x1400c79ae  jz      short loc_1400C79EC
0x1400c79b0  cmp     cs:gWfpPerProContext, r13
0x1400c79b7  jz      short loc_1400C79EC
0x1400c79b9  xor     ecx, ecx; ProcNumber
0x1400c79bb  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c79c2  nop     dword ptr [rax+rax+00h]
0x1400c79c7  lea     ecx, [rax+rax*8]
0x1400c79ca  mov     rax, cs:gWfpPerProContext
0x1400c79d1  shl     ecx, 3
0x1400c79d4  mov     rcx, [rcx+rax]
0x1400c79d8  mov     rax, ds:0FFFFF78000000008h
0x1400c79e2  mov     [rcx+8], rax
0x1400c79e6  mov     dword ptr [rcx], 4
0x1400c79ec  mov     r8, [rsi+78h]
0x1400c79f0  lea     rdx, [rsi+68h]; Entry
0x1400c79f4  mov     rbx, r13
0x1400c79f7  test    r8, r8
0x1400c79fa  jnz     short loc_1400C7A07
0x1400c79fc  mov     r8, 0FFFFFFFFFFFFFFFFh; Signature
0x1400c7a03  mov     [rdx+10h], r8
0x1400c7a07  xor     r9d, r9d; Context
0x1400c7a0a  lea     rcx, gAleMasterHashTable; HashTable
0x1400c7a11  call    cs:__imp_RtlInsertEntryHashTable
0x1400c7a18  nop     dword ptr [rax+rax+00h]
0x1400c7a1d  lea     rdi, WPP_GLOBAL_Control
0x1400c7a24  test    al, al
0x1400c7a26  jz      loc_1400C7BB8
0x1400c7a2c  test    rbx, rbx
0x1400c7a2f  jz      short loc_1400C7A97
0x1400c7a31  cmp     cs:gWfpPerProContext, r13
0x1400c7a38  jz      short loc_1400C7A61
0x1400c7a3a  xor     ecx, ecx; ProcNumber
0x1400c7a3c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c7a43  nop     dword ptr [rax+rax+00h]
0x1400c7a48  lea     ecx, [rax+rax*8]
0x1400c7a4b  mov     rax, cs:gWfpPerProContext
0x1400c7a52  shl     ecx, 3
0x1400c7a55  mov     rcx, [rcx+rax]
0x1400c7a59  cmp     dword ptr [rcx], 4
0x1400c7a5c  jnz     short loc_1400C7A61
0x1400c7a5e  mov     [rcx], r13d
0x1400c7a61  mov     rcx, cs:gAleHashtableLock; Lock
0x1400c7a68  lea     rdx, [rsp+88h+LockState]; LockState
0x1400c7a6d  call    cs:__imp_NdisReleaseRWLock
0x1400c7a74  nop     dword ptr [rax+rax+00h]
0x1400c7a79  test    rbx, rbx
0x1400c7a7c  jnz     loc_1400C7C22
0x1400c7a82  mov     rax, rbx
0x1400c7a85  add     rsp, 48h
0x1400c7a89  pop     r15
0x1400c7a8b  pop     r14
0x1400c7a8d  pop     r13
0x1400c7a8f  pop     r12
0x1400c7a91  pop     rdi
0x1400c7a92  pop     rsi
0x1400c7a93  pop     rbp
0x1400c7a94  pop     rbx
0x1400c7a95  retn
0x1400c7a97  lea     rbp, [rsi+48h]
0x1400c7a9b  mov     r9, rsi
0x1400c7a9e  mov     rcx, rbp
0x1400c7aa1  call    WfpAleInitializeWaitRef_0
0x1400c7aa6  mov     [rsp+88h+arg_28], rbp
0x1400c7aae  mov     r8, [rsp+88h+arg_28]
0x1400c7ab6  mov     eax, [r8]
0x1400c7ab9  lea     ecx, [rax+4]
0x1400c7abc  mov     edx, ecx
0x1400c7abe  xor     edx, eax
0x1400c7ac0  and     edx, 3
0x1400c7ac3  xor     edx, ecx
0x1400c7ac5  mov     [r8], edx
0x1400c7ac8  mov     rcx, [rsi]; Object
0x1400c7acb  call    cs:__imp_ObfReferenceObject
0x1400c7ad2  nop     dword ptr [rax+rax+00h]
0x1400c7ad7  test    r14, r14
0x1400c7ada  jz      loc_1400C7A31
0x1400c7ae0  mov     [rsp+88h+arg_28], rbp
0x1400c7ae8  mov     r8, [rsp+88h+arg_28]
0x1400c7af0  mov     eax, [r8]
0x1400c7af3  lea     ecx, [rax+4]
0x1400c7af6  mov     edx, ecx
0x1400c7af8  xor     edx, eax
0x1400c7afa  and     edx, 3
0x1400c7afd  xor     edx, ecx
0x1400c7aff  mov     [r8], edx
0x1400c7b02  mov     [r14], rsi
0x1400c7b05  jmp     loc_1400C7A31
0x1400c7b0a  mov     r8d, 0C0000017h
0x1400c7b10  lea     rdx, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400c7b17  call    WfpReportSysErrorAsNtStatus
0x1400c7b1c  mov     rbx, rax
0x1400c7b1f  test    rax, rax
0x1400c7b22  jz      loc_1400C78C8
0x1400c7b28  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7b2f  lea     rdi, WPP_GLOBAL_Control
0x1400c7b36  cmp     rcx, rdi
0x1400c7b39  jz      short loc_1400C7B41
0x1400c7b3b  cmp     byte ptr [rcx+29h], 2
0x1400c7b3f  jnb     short loc_1400C7B8D
0x1400c7b41  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7b48  cmp     rcx, rdi
0x1400c7b4b  jz      loc_1400C7A82
0x1400c7b51  cmp     byte ptr [rcx+29h], 2
0x1400c7b55  jb      loc_1400C7A82
0x1400c7b5b  test    dword ptr [rcx+2Ch], 1000h
0x1400c7b62  jz      loc_1400C7A82
0x1400c7b68  mov     rcx, [rcx+18h]
0x1400c7b6c  lea     r9, aWfpaleinsertpr; "WfpAleInsertProcessInformation"
0x1400c7b73  mov     edx, 0Fh
0x1400c7b78  mov     [rsp+88h+var_68], ebx
0x1400c7b7c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c7b83  call    WPP_SF_sd
0x1400c7b88  jmp     loc_1400C7A82
0x1400c7b8d  test    dword ptr [rcx+2Ch], 1000h
0x1400c7b94  jz      short loc_1400C7B41
0x1400c7b96  mov     rcx, [rcx+18h]
0x1400c7b9a  lea     r9, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400c7ba1  mov     edx, 0Fh
0x1400c7ba6  mov     [rsp+88h+var_68], eax
0x1400c7baa  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c7bb1  call    WPP_SF_sd
0x1400c7bb6  jmp     short loc_1400C7B41
0x1400c7bb8  mov     r8d, 0C0000017h
0x1400c7bbe  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x1400c7bc5  call    WfpReportSysErrorAsNtStatus
0x1400c7bca  mov     rbx, rax
0x1400c7bcd  test    rax, rax
0x1400c7bd0  jz      loc_1400C7A2C
0x1400c7bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7bdd  cmp     rcx, rdi
0x1400c7be0  jz      loc_1400C7A2C
0x1400c7be6  cmp     byte ptr [rcx+29h], 2
0x1400c7bea  jb      loc_1400C7A2C
0x1400c7bf0  test    dword ptr [rcx+2Ch], 1000h
0x1400c7bf7  jz      loc_1400C7A2C
0x1400c7bfd  mov     rcx, [rcx+18h]
0x1400c7c01  lea     r9, aWfphashtablein; "WfpHashtableInsert"
0x1400c7c08  mov     edx, 0Fh
0x1400c7c0d  mov     [rsp+88h+var_68], eax
0x1400c7c11  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c7c18  call    WPP_SF_sd
0x1400c7c1d  jmp     loc_1400C7A31
0x1400c7c22  test    rsi, rsi
0x1400c7c25  jz      loc_1400C7B41
0x1400c7c2b  mov     rcx, cs:processTableLookasideList
0x1400c7c32  mov     rdx, rsi
0x1400c7c35  call    PplFreeToLookasideList
0x1400c7c3a  jmp     loc_1400C7B41
```
