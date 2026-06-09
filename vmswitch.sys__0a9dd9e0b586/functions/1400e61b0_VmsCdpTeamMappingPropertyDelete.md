# VmsCdpTeamMappingPropertyDelete

- ea: `0x1400e61b0`
- end: `0x1400e6549`
- name: `VmsCdpTeamMappingPropertyDelete`
- size: `921`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x14003a450`
- `0x14003c378`
- `0x140046e5c`
- `0x14004f5d8`
- `0x14006b084`
- `0x1400893c8`
- `0x140089a04`
- `0x14008c82c`
- `0x1400dd0d0`
- `0x1400e61b0`
- `0x1400fe760`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6326`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e633e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6326`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e633e`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6412`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6463`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6412`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6463`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e62d1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e62d1`
- `NDIS!NdisReleaseRWLock` at `0x1400e6379`
- `NDIS!NdisReleaseRWLock` at `0x1400e63fd`
- `NDIS!NdisReleaseRWLock` at `0x1400e652d`
- `NDIS!NdisReleaseRWLock` at `0x1400e6379`
- `NDIS!NdisReleaseRWLock` at `0x1400e63fd`
- `NDIS!NdisReleaseRWLock` at `0x1400e652d`

## pseudocode

```c
__int64 __fastcall VmsCdpTeamMappingPropertyDelete(__int64 a1, _OWORD *a2, _DWORD *a3)
{
  int v6; // edx
  __int64 v7; // r14
  char v8; // r15
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // r8d
  char v12; // r12
  struct _NDIS_RW_LOCK_EX *v13; // rcx
  __int64 v14; // rdx
  _DWORD *v15; // rbx
  __int64 v16; // rdi
  struct _LOCK_STATE_EX v18; // [rsp+50h] [rbp-B0h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+54h] [rbp-ACh] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD *v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[256]; // [rsp+70h] [rbp-90h] BYREF

  v21 = a2;
  *(_WORD *)&v18.OldIrql = 0;
  v18.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(v22, 0, 0xFEu);
  *(_QWORD *)&SourceString.Length = 16646144;
  *a3 = 0;
  SourceString.Buffer = (wchar_t *)v22;
  v7 = 0;
  v8 = 0;
  if ( !a2 )
  {
    *a3 = 1;
    v9 = -1073741811;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_(VmsIfrPortLog, v6, 20, 25, (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids);
    goto LABEL_19;
  }
  if ( (unsigned int)(unsigned __int16)*(_DWORD *)(a1 + 10536) - 2 > 1 )
  {
    *a3 = 4;
    v9 = -1073741811;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      VmsIfrPortLog,
      v6,
      20,
      26,
      (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
      *(_DWORD *)(a1 + 10536));
    goto LABEL_19;
  }
  v12 = 0;
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  v8 = 1;
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  if ( !*(_QWORD *)(a1 + 11424) || !*(_WORD *)(a1 + 11418) )
  {
    *(_DWORD *)(a1 + 11416) = 0x1000000;
    *(_QWORD *)(a1 + 11424) = a1 + 11432;
  }
  RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 11416), &SourceString);
  RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 11688), &SourceString);
  memset((void *)(a1 + 10892), 0, 0x208u);
  v13 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 56);
  *(_WORD *)(a1 + 10874) = 0;
  *(_OWORD *)(a1 + 10876) = *a2;
  NdisReleaseRWLock(v13, &LockState);
  v7 = *(_QWORD *)(a1 + 1256);
  if ( !v7 )
  {
LABEL_12:
    v9 = 0;
    *(_BYTE *)(a1 + 11960) = 0;
    goto LABEL_13;
  }
  VmsOmObjectLockExclusive(*(_QWORD *)(a1 + 1256), &v18, 0);
  VmsOmNicIncrementControlCount(v7, 0, 45);
  v14 = *(_QWORD *)(v7 + 1888);
  if ( v14 && (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(0, v14) )
  {
    v15 = *(_DWORD **)(v7 + 4040);
    v16 = *(_QWORD *)(v7 + 1888);
    v12 = 1;
    VmsOmNicCopyDataUnsafe(v7, 0, v15);
    v15[1] |= 4u;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 56), &v18);
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
    v8 = 0;
    VmsOmNicSendMultipleOids(v7, v16, 0, 66196, v15, 1, 0);
    goto LABEL_12;
  }
  *a3 = 4;
  v9 = -1073741811;
  LOBYTE(v14) = 2;
  WPP_RECORDER_SF_I(
    VmsIfrPortLog,
    v14,
    20,
    27,
    (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
    *(_QWORD *)(v7 + 1888));
LABEL_19:
  WPP_RECORDER_SF_q_guid_Ld(
    VmsIfrPortLog,
    v10,
    v11,
    28,
    (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
    a1,
    (__int64)v21,
    *a3,
    13);
  if ( !v8 )
  {
    v12 = 0;
LABEL_13:
    if ( !v8 )
      goto LABEL_15;
    goto LABEL_14;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 56), &v18);
  v12 = v8;
LABEL_14:
  KeReleaseMutex(&VmsOmIoctlMutex, 0);
LABEL_15:
  if ( v12 )
    VmsOmNicDecrementControlCount(v7, 0, 45);
  return v9;
}

```

## disassembly

```asm
0x1400e61b0  mov     [rsp-8+arg_18], rbx
0x1400e61b5  push    rbp
0x1400e61b6  push    rsi
0x1400e61b7  push    rdi
0x1400e61b8  push    r12
0x1400e61ba  push    r13
0x1400e61bc  push    r14
0x1400e61be  push    r15
0x1400e61c0  lea     rbp, [rsp-80h]
0x1400e61c5  sub     rsp, 180h
0x1400e61cc  mov     rax, cs:__security_cookie
0x1400e61d3  xor     rax, rsp
0x1400e61d6  mov     [rbp+0B0h+var_40], rax
0x1400e61da  xor     eax, eax
0x1400e61dc  mov     [rsp+1B0h+var_148], rdx
0x1400e61e1  mov     r13, r8
0x1400e61e4  mov     word ptr [rsp+1B0h+var_160.OldIrql], ax
0x1400e61e9  mov     rbx, rdx
0x1400e61ec  mov     [rsp+1B0h+var_160.Flags], al
0x1400e61f0  mov     rsi, rcx
0x1400e61f3  mov     word ptr [rsp+1B0h+LockState.OldIrql], ax
0x1400e61f8  xor     edx, edx; Val
0x1400e61fa  mov     [rsp+1B0h+LockState.Flags], al
0x1400e61fe  mov     r8d, 0FEh; Size
0x1400e6204  lea     rcx, [rsp+1B0h+var_140]; void *
0x1400e6209  call    memset
0x1400e620e  xor     edi, edi
0x1400e6210  mov     qword ptr [rsp+1B0h+SourceString.Length], 0FE0000h
0x1400e6219  mov     [r13+0], edi
0x1400e621d  lea     rax, [rsp+1B0h+var_140]
0x1400e6222  mov     [rsp+1B0h+SourceString.Buffer], rax
0x1400e6227  mov     r14d, edi
0x1400e622a  mov     r15b, dil
0x1400e622d  test    rbx, rbx
0x1400e6230  jnz     short loc_1400E6266
0x1400e6232  mov     dword ptr [r13+0], 1
0x1400e623a  mov     ebx, 0C000000Dh
0x1400e623f  mov     rcx, cs:VmsIfrPortLog
0x1400e6246  lea     r9d, [rdi+19h]
0x1400e624a  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6251  mov     dl, 2
0x1400e6253  lea     r8d, [r14+14h]
0x1400e6257  mov     [rsp+1B0h+Timeout], rdi
0x1400e625c  call    WPP_RECORDER_SF_
0x1400e6261  jmp     loc_1400E64E9
0x1400e6266  mov     eax, [rsi+2928h]
0x1400e626c  movzx   ecx, ax
0x1400e626f  sub     ecx, 2
0x1400e6272  cmp     ecx, 1
0x1400e6275  jbe     short loc_1400E62BA
0x1400e6277  mov     dword ptr [r13+0], 4
0x1400e627f  mov     ebx, 0C000000Dh
0x1400e6284  mov     eax, [rsi+2928h]
0x1400e628a  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6291  movzx   ecx, ax
0x1400e6294  mov     r9d, 1Ah
0x1400e629a  mov     dword ptr [rsp+1B0h+var_188], ecx
0x1400e629e  mov     dl, 2
0x1400e62a0  mov     rcx, cs:VmsIfrPortLog
0x1400e62a7  mov     [rsp+1B0h+Timeout], rdi
0x1400e62ac  lea     r8d, [r9-6]
0x1400e62b0  call    WPP_RECORDER_SF_d
0x1400e62b5  jmp     loc_1400E64E9
0x1400e62ba  xor     r9d, r9d; Alertable
0x1400e62bd  mov     [rsp+1B0h+Timeout], rdi; Timeout
0x1400e62c2  xor     r8d, r8d; WaitMode
0x1400e62c5  lea     rcx, VmsOmIoctlMutex; Object
0x1400e62cc  xor     edx, edx; WaitReason
0x1400e62ce  mov     r12b, dil
0x1400e62d1  call    cs:__imp_KeWaitForSingleObject
0x1400e62d8  nop     dword ptr [rax+rax+00h]
0x1400e62dd  xor     r8d, r8d
0x1400e62e0  lea     rdx, [rsp+1B0h+LockState]
0x1400e62e5  mov     rcx, rsi
0x1400e62e8  mov     r15b, 1
0x1400e62eb  call    VmsOmObjectLockExclusive
0x1400e62f0  cmp     [rsi+2CA0h], rdi
0x1400e62f7  jz      short loc_1400E6302
0x1400e62f9  cmp     [rsi+2C9Ah], di
0x1400e6300  jnz     short loc_1400E631A
0x1400e6302  lea     rax, [rsi+2CA8h]
0x1400e6309  mov     dword ptr [rsi+2C98h], 1000000h
0x1400e6313  mov     [rsi+2CA0h], rax
0x1400e631a  lea     rcx, [rsi+2C98h]; DestinationString
0x1400e6321  lea     rdx, [rsp+1B0h+SourceString]; SourceString
0x1400e6326  call    cs:__imp_RtlCopyUnicodeString
0x1400e632d  nop     dword ptr [rax+rax+00h]
0x1400e6332  lea     rcx, [rsi+2DA8h]; DestinationString
0x1400e6339  lea     rdx, [rsp+1B0h+SourceString]; SourceString
0x1400e633e  call    cs:__imp_RtlCopyUnicodeString
0x1400e6345  nop     dword ptr [rax+rax+00h]
0x1400e634a  lea     rcx, [rsi+2A8Ch]; void *
0x1400e6351  xor     edx, edx; Val
0x1400e6353  mov     r8d, 208h; Size
0x1400e6359  call    memset
0x1400e635e  mov     rcx, [rsi+38h]; Lock
0x1400e6362  lea     rdx, [rsp+1B0h+LockState]; LockState
0x1400e6367  mov     [rsi+2A7Ah], di
0x1400e636e  movups  xmm0, xmmword ptr [rbx]
0x1400e6371  movdqu  xmmword ptr [rsi+2A7Ch], xmm0
0x1400e6379  call    cs:__imp_NdisReleaseRWLock
0x1400e6380  nop     dword ptr [rax+rax+00h]
0x1400e6385  mov     r14, [rsi+4E8h]
0x1400e638c  test    r14, r14
0x1400e638f  jz      loc_1400E644C
0x1400e6395  xor     r8d, r8d
0x1400e6398  lea     rdx, [rsp+1B0h+var_160]
0x1400e639d  mov     rcx, r14
0x1400e63a0  call    VmsOmObjectLockExclusive
0x1400e63a5  xor     edx, edx
0x1400e63a7  mov     rcx, r14
0x1400e63aa  lea     r8d, [rdx+2Dh]
0x1400e63ae  call    VmsOmNicIncrementControlCount
0x1400e63b3  mov     rdx, [r14+760h]
0x1400e63ba  test    rdx, rdx
0x1400e63bd  jz      loc_1400E64AC
0x1400e63c3  xor     ecx, ecx
0x1400e63c5  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400e63ca  test    al, al
0x1400e63cc  jz      loc_1400E64AC
0x1400e63d2  mov     rbx, [r14+0FC8h]
0x1400e63d9  xor     edx, edx
0x1400e63db  mov     rdi, [r14+760h]
0x1400e63e2  mov     r8, rbx
0x1400e63e5  mov     rcx, r14
0x1400e63e8  mov     r12b, r15b
0x1400e63eb  call    VmsOmNicCopyDataUnsafe
0x1400e63f0  or      dword ptr [rbx+4], 4
0x1400e63f4  lea     rdx, [rsp+1B0h+var_160]; LockState
0x1400e63f9  mov     rcx, [r14+38h]; Lock
0x1400e63fd  call    cs:__imp_NdisReleaseRWLock
0x1400e6404  nop     dword ptr [rax+rax+00h]
0x1400e6409  xor     edx, edx; Wait
0x1400e640b  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400e6412  call    cs:__imp_KeReleaseMutex
0x1400e6419  nop     dword ptr [rax+rax+00h]
0x1400e641e  xor     eax, eax
0x1400e6420  mov     r9d, 10294h; int
0x1400e6426  mov     [rsp+1B0h+var_180], rax; __int64
0x1400e642b  xor     r8d, r8d; int
0x1400e642e  mov     [rsp+1B0h+var_188], 1; __int64
0x1400e6437  mov     rdx, rdi; int
0x1400e643a  mov     rcx, r14; int
0x1400e643d  mov     [rsp+1B0h+Timeout], rbx; Src
0x1400e6442  mov     r15b, al
0x1400e6445  call    VmsOmNicSendMultipleOids
0x1400e644a  xor     edi, edi
0x1400e644c  mov     ebx, edi
0x1400e644e  mov     [rsi+2EB8h], dil
0x1400e6455  test    r15b, r15b
0x1400e6458  jz      short loc_1400E646F
0x1400e645a  xor     edx, edx; Wait
0x1400e645c  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400e6463  call    cs:__imp_KeReleaseMutex
0x1400e646a  nop     dword ptr [rax+rax+00h]
0x1400e646f  test    r12b, r12b
0x1400e6472  jz      short loc_1400E6482
0x1400e6474  xor     edx, edx
0x1400e6476  mov     rcx, r14
0x1400e6479  lea     r8d, [rdx+2Dh]
0x1400e647d  call    VmsOmNicDecrementControlCount
0x1400e6482  mov     eax, ebx
0x1400e6484  mov     rcx, [rbp+0B0h+var_40]
0x1400e6488  xor     rcx, rsp; StackCookie
0x1400e648b  call    __security_check_cookie
0x1400e6490  mov     rbx, [rsp+1B0h+arg_18]
0x1400e6498  add     rsp, 180h
0x1400e649f  pop     r15
0x1400e64a1  pop     r14
0x1400e64a3  pop     r13
0x1400e64a5  pop     r12
0x1400e64a7  pop     rdi
0x1400e64a8  pop     rsi
0x1400e64a9  pop     rbp
0x1400e64aa  retn
0x1400e64ac  mov     dword ptr [r13+0], 4
0x1400e64b4  mov     ebx, 0C000000Dh
0x1400e64b9  mov     rax, [r14+760h]
0x1400e64c0  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e64c7  mov     rcx, cs:VmsIfrPortLog
0x1400e64ce  mov     r9d, 1Bh
0x1400e64d4  mov     [rsp+1B0h+var_188], rax
0x1400e64d9  mov     dl, 2
0x1400e64db  mov     [rsp+1B0h+Timeout], rdi
0x1400e64e0  lea     r8d, [r9-7]
0x1400e64e4  call    WPP_RECORDER_SF_I
0x1400e64e9  mov     eax, [r13+0]
0x1400e64ed  mov     r9d, 1Ch
0x1400e64f3  mov     rcx, cs:VmsIfrPortLog
0x1400e64fa  mov     [rsp+1B0h+var_170], 0C000000Dh
0x1400e6502  mov     [rsp+1B0h+var_178], eax
0x1400e6506  mov     rax, [rsp+1B0h+var_148]
0x1400e650b  mov     [rsp+1B0h+var_180], rax
0x1400e6510  mov     [rsp+1B0h+var_188], rsi
0x1400e6515  mov     [rsp+1B0h+Timeout], rdi
0x1400e651a  call    WPP_RECORDER_SF_q_guid_Ld
0x1400e651f  test    r15b, r15b
0x1400e6522  jz      short loc_1400E6541
0x1400e6524  mov     rcx, [r14+38h]; Lock
0x1400e6528  lea     rdx, [rsp+1B0h+var_160]; LockState
0x1400e652d  call    cs:__imp_NdisReleaseRWLock
0x1400e6534  nop     dword ptr [rax+rax+00h]
0x1400e6539  mov     r12b, r15b
0x1400e653c  jmp     loc_1400E645A
0x1400e6541  mov     r12b, r15b
0x1400e6544  jmp     loc_1400E6455
```
