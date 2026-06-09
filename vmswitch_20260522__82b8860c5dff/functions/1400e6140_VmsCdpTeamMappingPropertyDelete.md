# VmsCdpTeamMappingPropertyDelete

- ea: `0x1400e6140`
- end: `0x1400e64d9`
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
- `0x1400dd060`
- `0x1400e6140`
- `0x1400fe6f0`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e62b6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e62ce`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e62b6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e62ce`
- `ntoskrnl!KeReleaseMutex` at `0x1400e63a2`
- `ntoskrnl!KeReleaseMutex` at `0x1400e63f3`
- `ntoskrnl!KeReleaseMutex` at `0x1400e63a2`
- `ntoskrnl!KeReleaseMutex` at `0x1400e63f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6261`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6261`
- `NDIS!NdisReleaseRWLock` at `0x1400e6309`
- `NDIS!NdisReleaseRWLock` at `0x1400e638d`
- `NDIS!NdisReleaseRWLock` at `0x1400e64bd`
- `NDIS!NdisReleaseRWLock` at `0x1400e6309`
- `NDIS!NdisReleaseRWLock` at `0x1400e638d`
- `NDIS!NdisReleaseRWLock` at `0x1400e64bd`

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
0x1400e6140  mov     [rsp-8+arg_18], rbx
0x1400e6145  push    rbp
0x1400e6146  push    rsi
0x1400e6147  push    rdi
0x1400e6148  push    r12
0x1400e614a  push    r13
0x1400e614c  push    r14
0x1400e614e  push    r15
0x1400e6150  lea     rbp, [rsp-80h]
0x1400e6155  sub     rsp, 180h
0x1400e615c  mov     rax, cs:__security_cookie
0x1400e6163  xor     rax, rsp
0x1400e6166  mov     [rbp+0B0h+var_40], rax
0x1400e616a  xor     eax, eax
0x1400e616c  mov     [rsp+1B0h+var_148], rdx
0x1400e6171  mov     r13, r8
0x1400e6174  mov     word ptr [rsp+1B0h+var_160.OldIrql], ax
0x1400e6179  mov     rbx, rdx
0x1400e617c  mov     [rsp+1B0h+var_160.Flags], al
0x1400e6180  mov     rsi, rcx
0x1400e6183  mov     word ptr [rsp+1B0h+LockState.OldIrql], ax
0x1400e6188  xor     edx, edx; Val
0x1400e618a  mov     [rsp+1B0h+LockState.Flags], al
0x1400e618e  mov     r8d, 0FEh; Size
0x1400e6194  lea     rcx, [rsp+1B0h+var_140]; void *
0x1400e6199  call    memset
0x1400e619e  xor     edi, edi
0x1400e61a0  mov     qword ptr [rsp+1B0h+SourceString.Length], 0FE0000h
0x1400e61a9  mov     [r13+0], edi
0x1400e61ad  lea     rax, [rsp+1B0h+var_140]
0x1400e61b2  mov     [rsp+1B0h+SourceString.Buffer], rax
0x1400e61b7  mov     r14d, edi
0x1400e61ba  mov     r15b, dil
0x1400e61bd  test    rbx, rbx
0x1400e61c0  jnz     short loc_1400E61F6
0x1400e61c2  mov     dword ptr [r13+0], 1
0x1400e61ca  mov     ebx, 0C000000Dh
0x1400e61cf  mov     rcx, cs:VmsIfrPortLog
0x1400e61d6  lea     r9d, [rdi+19h]
0x1400e61da  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e61e1  mov     dl, 2
0x1400e61e3  lea     r8d, [r14+14h]
0x1400e61e7  mov     [rsp+1B0h+Timeout], rdi
0x1400e61ec  call    WPP_RECORDER_SF_
0x1400e61f1  jmp     loc_1400E6479
0x1400e61f6  mov     eax, [rsi+2928h]
0x1400e61fc  movzx   ecx, ax
0x1400e61ff  sub     ecx, 2
0x1400e6202  cmp     ecx, 1
0x1400e6205  jbe     short loc_1400E624A
0x1400e6207  mov     dword ptr [r13+0], 4
0x1400e620f  mov     ebx, 0C000000Dh
0x1400e6214  mov     eax, [rsi+2928h]
0x1400e621a  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6221  movzx   ecx, ax
0x1400e6224  mov     r9d, 1Ah
0x1400e622a  mov     dword ptr [rsp+1B0h+var_188], ecx
0x1400e622e  mov     dl, 2
0x1400e6230  mov     rcx, cs:VmsIfrPortLog
0x1400e6237  mov     [rsp+1B0h+Timeout], rdi
0x1400e623c  lea     r8d, [r9-6]
0x1400e6240  call    WPP_RECORDER_SF_d
0x1400e6245  jmp     loc_1400E6479
0x1400e624a  xor     r9d, r9d; Alertable
0x1400e624d  mov     [rsp+1B0h+Timeout], rdi; Timeout
0x1400e6252  xor     r8d, r8d; WaitMode
0x1400e6255  lea     rcx, VmsOmIoctlMutex; Object
0x1400e625c  xor     edx, edx; WaitReason
0x1400e625e  mov     r12b, dil
0x1400e6261  call    cs:__imp_KeWaitForSingleObject
0x1400e6268  nop     dword ptr [rax+rax+00h]
0x1400e626d  xor     r8d, r8d
0x1400e6270  lea     rdx, [rsp+1B0h+LockState]
0x1400e6275  mov     rcx, rsi
0x1400e6278  mov     r15b, 1
0x1400e627b  call    VmsOmObjectLockExclusive
0x1400e6280  cmp     [rsi+2CA0h], rdi
0x1400e6287  jz      short loc_1400E6292
0x1400e6289  cmp     [rsi+2C9Ah], di
0x1400e6290  jnz     short loc_1400E62AA
0x1400e6292  lea     rax, [rsi+2CA8h]
0x1400e6299  mov     dword ptr [rsi+2C98h], 1000000h
0x1400e62a3  mov     [rsi+2CA0h], rax
0x1400e62aa  lea     rcx, [rsi+2C98h]; DestinationString
0x1400e62b1  lea     rdx, [rsp+1B0h+SourceString]; SourceString
0x1400e62b6  call    cs:__imp_RtlCopyUnicodeString
0x1400e62bd  nop     dword ptr [rax+rax+00h]
0x1400e62c2  lea     rcx, [rsi+2DA8h]; DestinationString
0x1400e62c9  lea     rdx, [rsp+1B0h+SourceString]; SourceString
0x1400e62ce  call    cs:__imp_RtlCopyUnicodeString
0x1400e62d5  nop     dword ptr [rax+rax+00h]
0x1400e62da  lea     rcx, [rsi+2A8Ch]; void *
0x1400e62e1  xor     edx, edx; Val
0x1400e62e3  mov     r8d, 208h; Size
0x1400e62e9  call    memset
0x1400e62ee  mov     rcx, [rsi+38h]; Lock
0x1400e62f2  lea     rdx, [rsp+1B0h+LockState]; LockState
0x1400e62f7  mov     [rsi+2A7Ah], di
0x1400e62fe  movups  xmm0, xmmword ptr [rbx]
0x1400e6301  movdqu  xmmword ptr [rsi+2A7Ch], xmm0
0x1400e6309  call    cs:__imp_NdisReleaseRWLock
0x1400e6310  nop     dword ptr [rax+rax+00h]
0x1400e6315  mov     r14, [rsi+4E8h]
0x1400e631c  test    r14, r14
0x1400e631f  jz      loc_1400E63DC
0x1400e6325  xor     r8d, r8d
0x1400e6328  lea     rdx, [rsp+1B0h+var_160]
0x1400e632d  mov     rcx, r14
0x1400e6330  call    VmsOmObjectLockExclusive
0x1400e6335  xor     edx, edx
0x1400e6337  mov     rcx, r14
0x1400e633a  lea     r8d, [rdx+2Dh]
0x1400e633e  call    VmsOmNicIncrementControlCount
0x1400e6343  mov     rdx, [r14+760h]
0x1400e634a  test    rdx, rdx
0x1400e634d  jz      loc_1400E643C
0x1400e6353  xor     ecx, ecx
0x1400e6355  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400e635a  test    al, al
0x1400e635c  jz      loc_1400E643C
0x1400e6362  mov     rbx, [r14+0FC8h]
0x1400e6369  xor     edx, edx
0x1400e636b  mov     rdi, [r14+760h]
0x1400e6372  mov     r8, rbx
0x1400e6375  mov     rcx, r14
0x1400e6378  mov     r12b, r15b
0x1400e637b  call    VmsOmNicCopyDataUnsafe
0x1400e6380  or      dword ptr [rbx+4], 4
0x1400e6384  lea     rdx, [rsp+1B0h+var_160]; LockState
0x1400e6389  mov     rcx, [r14+38h]; Lock
0x1400e638d  call    cs:__imp_NdisReleaseRWLock
0x1400e6394  nop     dword ptr [rax+rax+00h]
0x1400e6399  xor     edx, edx; Wait
0x1400e639b  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400e63a2  call    cs:__imp_KeReleaseMutex
0x1400e63a9  nop     dword ptr [rax+rax+00h]
0x1400e63ae  xor     eax, eax
0x1400e63b0  mov     r9d, 10294h; int
0x1400e63b6  mov     [rsp+1B0h+var_180], rax; __int64
0x1400e63bb  xor     r8d, r8d; int
0x1400e63be  mov     [rsp+1B0h+var_188], 1; __int64
0x1400e63c7  mov     rdx, rdi; int
0x1400e63ca  mov     rcx, r14; int
0x1400e63cd  mov     [rsp+1B0h+Timeout], rbx; Src
0x1400e63d2  mov     r15b, al
0x1400e63d5  call    VmsOmNicSendMultipleOids
0x1400e63da  xor     edi, edi
0x1400e63dc  mov     ebx, edi
0x1400e63de  mov     [rsi+2EB8h], dil
0x1400e63e5  test    r15b, r15b
0x1400e63e8  jz      short loc_1400E63FF
0x1400e63ea  xor     edx, edx; Wait
0x1400e63ec  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400e63f3  call    cs:__imp_KeReleaseMutex
0x1400e63fa  nop     dword ptr [rax+rax+00h]
0x1400e63ff  test    r12b, r12b
0x1400e6402  jz      short loc_1400E6412
0x1400e6404  xor     edx, edx
0x1400e6406  mov     rcx, r14
0x1400e6409  lea     r8d, [rdx+2Dh]
0x1400e640d  call    VmsOmNicDecrementControlCount
0x1400e6412  mov     eax, ebx
0x1400e6414  mov     rcx, [rbp+0B0h+var_40]
0x1400e6418  xor     rcx, rsp; StackCookie
0x1400e641b  call    __security_check_cookie
0x1400e6420  mov     rbx, [rsp+1B0h+arg_18]
0x1400e6428  add     rsp, 180h
0x1400e642f  pop     r15
0x1400e6431  pop     r14
0x1400e6433  pop     r13
0x1400e6435  pop     r12
0x1400e6437  pop     rdi
0x1400e6438  pop     rsi
0x1400e6439  pop     rbp
0x1400e643a  retn
0x1400e643c  mov     dword ptr [r13+0], 4
0x1400e6444  mov     ebx, 0C000000Dh
0x1400e6449  mov     rax, [r14+760h]
0x1400e6450  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6457  mov     rcx, cs:VmsIfrPortLog
0x1400e645e  mov     r9d, 1Bh
0x1400e6464  mov     [rsp+1B0h+var_188], rax
0x1400e6469  mov     dl, 2
0x1400e646b  mov     [rsp+1B0h+Timeout], rdi
0x1400e6470  lea     r8d, [r9-7]
0x1400e6474  call    WPP_RECORDER_SF_I
0x1400e6479  mov     eax, [r13+0]
0x1400e647d  mov     r9d, 1Ch
0x1400e6483  mov     rcx, cs:VmsIfrPortLog
0x1400e648a  mov     [rsp+1B0h+var_170], 0C000000Dh
0x1400e6492  mov     [rsp+1B0h+var_178], eax
0x1400e6496  mov     rax, [rsp+1B0h+var_148]
0x1400e649b  mov     [rsp+1B0h+var_180], rax
0x1400e64a0  mov     [rsp+1B0h+var_188], rsi
0x1400e64a5  mov     [rsp+1B0h+Timeout], rdi
0x1400e64aa  call    WPP_RECORDER_SF_q_guid_Ld
0x1400e64af  test    r15b, r15b
0x1400e64b2  jz      short loc_1400E64D1
0x1400e64b4  mov     rcx, [r14+38h]; Lock
0x1400e64b8  lea     rdx, [rsp+1B0h+var_160]; LockState
0x1400e64bd  call    cs:__imp_NdisReleaseRWLock
0x1400e64c4  nop     dword ptr [rax+rax+00h]
0x1400e64c9  mov     r12b, r15b
0x1400e64cc  jmp     loc_1400E63EA
0x1400e64d1  mov     r12b, r15b
0x1400e64d4  jmp     loc_1400E63E5
```
