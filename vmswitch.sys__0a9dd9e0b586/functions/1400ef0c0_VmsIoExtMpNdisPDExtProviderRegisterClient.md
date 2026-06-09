# VmsIoExtMpNdisPDExtProviderRegisterClient

- ea: `0x1400ef0c0`
- end: `0x1400ef400`
- name: `VmsIoExtMpNdisPDExtProviderRegisterClient`
- size: `832`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x14003a450`
- `0x14006b084`
- `0x1400ef0c0`
- `0x1400f019c`
- `0x14012c7d4`
- `0x14012cb14`
- `0x1401bbf20`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ef2de`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ef2de`
- `ntoskrnl!KeReleaseMutex` at `0x1400ef3c0`
- `ntoskrnl!KeReleaseMutex` at `0x1400ef3c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ef10b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ef10b`
- `NDIS!NdisReleaseRWLock` at `0x1400ef32a`
- `NDIS!NdisReleaseRWLock` at `0x1400ef3d9`
- `NDIS!NdisReleaseRWLock` at `0x1400ef32a`
- `NDIS!NdisReleaseRWLock` at `0x1400ef3d9`

## pseudocode

```c
__int64 __fastcall VmsIoExtMpNdisPDExtProviderRegisterClient(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        const UNICODE_STRING *a4,
        _QWORD *a5,
        _OWORD *a6)
{
  char v9; // r15
  int v10; // edx
  _OWORD *v11; // rbp
  _QWORD *v12; // r14
  int v13; // edi
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  bool v18; // di
  int v19; // edx
  __int64 v20; // rdi
  struct _UNICODE_STRING *v21; // rcx
  __int128 v22; // xmm0
  PNDIS_RW_LOCK_EX *v23; // rsi
  int v24; // edi
  __int64 v25; // r8
  int Timeout; // [rsp+20h] [rbp-88h]
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp-48h] BYREF
  __int64 v29; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+10h] BYREF

  v30 = a2;
  v29 = a1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v9 = 0;
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  v11 = a6;
  v12 = a5;
  if ( !a1 )
  {
    v13 = -1073741811;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v10, 20, 164, (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids, 13);
LABEL_21:
    WPP_RECORDER_SF_qq_guid_qqqd(
      v15,
      v14,
      v16,
      v17,
      Timeout,
      (char)&v29,
      (char)&v30,
      (__int64)a3,
      (char)a4,
      (char)v12,
      (char)v11,
      v13);
    v23 = (PNDIS_RW_LOCK_EX *)(a1 + 56);
    goto LABEL_23;
  }
  if ( !a5 )
  {
    v13 = -1073741811;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v10, 20, 165, (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids, 13);
    goto LABEL_21;
  }
  if ( !a6 )
  {
    v13 = -1073741811;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v10, 20, 166, (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids, 13);
    goto LABEL_21;
  }
  v18 = memcmp(a3, &VmsPDTestExtensionGuid, 0x10u) == 0;
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  v9 = 1;
  if ( *(_BYTE *)(a1 + 5216) && !v18 )
  {
    v13 = -1073740008;
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v19, 20, 167, (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids, 24);
    goto LABEL_21;
  }
  if ( *(_BYTE *)(a1 + 5217) )
  {
    if ( v18 )
    {
      v13 = -1073740008;
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v19, 20, 168, (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids, 24);
      goto LABEL_21;
    }
    goto LABEL_14;
  }
  if ( !v18 )
  {
LABEL_14:
    *(_BYTE *)(a1 + 5216) = 1;
    v20 = 5224;
    goto LABEL_16;
  }
  *(_BYTE *)(a1 + 5217) = 1;
  v20 = 5816;
LABEL_16:
  *(_QWORD *)(v20 + a1) = v30;
  v21 = (struct _UNICODE_STRING *)(v20 + a1 + 24);
  v22 = *a3;
  *(_WORD *)(v20 + a1 + 26) = 512;
  *(_OWORD *)(v20 + a1 + 8) = v22;
  *(_QWORD *)(v20 + a1 + 32) = v20 + a1 + 40;
  v21->Length = 0;
  RtlCopyUnicodeString(v21, a4);
  v23 = (PNDIS_RW_LOCK_EX *)(a1 + 56);
  *(_QWORD *)(v20 + a1 + 552) = *v12;
  *(_OWORD *)(v20 + a1 + 560) = *v11;
  *(_OWORD *)(v20 + a1 + 576) = v11[1];
  v24 = *(_DWORD *)(a1 + 6368) + 88 + *(_DWORD *)(a1 + 5776);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  v9 = 0;
  if ( *(_DWORD *)(a1 + 8916) == 1 )
  {
    v25 = *(unsigned int *)(a1 + 6372);
    if ( !(_DWORD)v25 )
      v25 = 100;
    v13 = VmsPDSetupPDBuffersForAllECs(a1, (unsigned __int16)v24, v25);
    if ( v13 < 0 )
    {
      VmsPDSwitchDataPathMode(a1, *(_QWORD *)(a1 + 4264), 0);
      goto LABEL_21;
    }
  }
  else
  {
    v13 = 0;
  }
LABEL_23:
  KeReleaseMutex(&VmsOmIoctlMutex, 0);
  if ( v9 )
    NdisReleaseRWLock(*v23, &LockState);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400ef0c0  mov     [rsp+arg_10], rbx
0x1400ef0c5  mov     [rsp+arg_8], rdx
0x1400ef0ca  mov     [rsp+arg_0], rcx
0x1400ef0cf  push    rbp
0x1400ef0d0  push    rsi
0x1400ef0d1  push    rdi
0x1400ef0d2  push    r12
0x1400ef0d4  push    r13
0x1400ef0d6  push    r14
0x1400ef0d8  push    r15
0x1400ef0da  sub     rsp, 70h
0x1400ef0de  xor     eax, eax
0x1400ef0e0  mov     r13, r9
0x1400ef0e3  mov     r12, r8
0x1400ef0e6  mov     word ptr [rsp+0A8h+LockState.OldIrql], ax
0x1400ef0eb  mov     rbx, rcx
0x1400ef0ee  mov     [rsp+0A8h+LockState.Flags], al
0x1400ef0f2  xor     esi, esi
0x1400ef0f4  lea     rcx, VmsOmIoctlMutex; Object
0x1400ef0fb  xor     r9d, r9d; Alertable
0x1400ef0fe  mov     [rsp+0A8h+Timeout], rsi; Timeout
0x1400ef103  xor     r8d, r8d; WaitMode
0x1400ef106  xor     edx, edx; WaitReason
0x1400ef108  mov     r15b, sil
0x1400ef10b  call    cs:__imp_KeWaitForSingleObject
0x1400ef112  nop     dword ptr [rax+rax+00h]
0x1400ef117  mov     rbp, [rsp+0A8h+arg_28]
0x1400ef11f  mov     r14, [rsp+0A8h+arg_20]
0x1400ef127  test    rbx, rbx
0x1400ef12a  jnz     short loc_1400EF160
0x1400ef12c  mov     eax, 0C000000Dh
0x1400ef131  mov     edi, eax
0x1400ef133  mov     rcx, cs:VmsIfrLog
0x1400ef13a  lea     r8d, [rsi+14h]
0x1400ef13e  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef142  mov     r9d, 0A4h
0x1400ef148  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef14f  mov     dl, 2
0x1400ef151  mov     [rsp+0A8h+Timeout], rax
0x1400ef156  call    WPP_RECORDER_SF_d
0x1400ef15b  jmp     loc_1400EF378
0x1400ef160  test    r14, r14
0x1400ef163  jnz     short loc_1400EF199
0x1400ef165  mov     eax, 0C000000Dh
0x1400ef16a  mov     edi, eax
0x1400ef16c  mov     rcx, cs:VmsIfrLog
0x1400ef173  lea     r8d, [r14+14h]
0x1400ef177  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef17b  mov     r9d, 0A5h
0x1400ef181  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef188  mov     dl, 2
0x1400ef18a  mov     [rsp+0A8h+Timeout], rax
0x1400ef18f  call    WPP_RECORDER_SF_d
0x1400ef194  jmp     loc_1400EF378
0x1400ef199  test    rbp, rbp
0x1400ef19c  jnz     short loc_1400EF1D2
0x1400ef19e  mov     eax, 0C000000Dh
0x1400ef1a3  mov     edi, eax
0x1400ef1a5  mov     rcx, cs:VmsIfrLog
0x1400ef1ac  lea     r8d, [rbp+14h]
0x1400ef1b0  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef1b4  mov     r9d, 0A6h
0x1400ef1ba  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef1c1  mov     dl, 2
0x1400ef1c3  mov     [rsp+0A8h+Timeout], rax
0x1400ef1c8  call    WPP_RECORDER_SF_d
0x1400ef1cd  jmp     loc_1400EF378
0x1400ef1d2  mov     r8d, 10h; Size
0x1400ef1d8  lea     rdx, VmsPDTestExtensionGuid; Buf2
0x1400ef1df  mov     rcx, r12; Buf1
0x1400ef1e2  call    memcmp
0x1400ef1e7  test    eax, eax
0x1400ef1e9  lea     rdx, [rsp+0A8h+LockState]
0x1400ef1ee  mov     rcx, rbx
0x1400ef1f1  setz    dil
0x1400ef1f5  xor     r8d, r8d
0x1400ef1f8  call    VmsOmObjectLockExclusive
0x1400ef1fd  mov     r15b, 1
0x1400ef200  cmp     [rbx+1460h], sil
0x1400ef207  jz      short loc_1400EF244
0x1400ef209  test    dil, dil
0x1400ef20c  jnz     short loc_1400EF244
0x1400ef20e  mov     eax, 0C0000718h
0x1400ef213  mov     edi, eax
0x1400ef215  mov     rcx, cs:VmsIfrLog
0x1400ef21c  mov     r9d, 0A7h
0x1400ef222  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef226  mov     r8d, 14h
0x1400ef22c  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef233  mov     dl, 2
0x1400ef235  mov     [rsp+0A8h+Timeout], rax
0x1400ef23a  call    WPP_RECORDER_SF_d
0x1400ef23f  jmp     loc_1400EF378
0x1400ef244  cmp     [rbx+1461h], sil
0x1400ef24b  jz      short loc_1400EF288
0x1400ef24d  test    dil, dil
0x1400ef250  jz      short loc_1400EF28D
0x1400ef252  mov     eax, 0C0000718h
0x1400ef257  mov     edi, eax
0x1400ef259  mov     rcx, cs:VmsIfrLog
0x1400ef260  mov     r9d, 0A8h
0x1400ef266  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef26a  mov     r8d, 14h
0x1400ef270  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef277  mov     dl, 2
0x1400ef279  mov     [rsp+0A8h+Timeout], rax
0x1400ef27e  call    WPP_RECORDER_SF_d
0x1400ef283  jmp     loc_1400EF378
0x1400ef288  test    dil, dil
0x1400ef28b  jnz     short loc_1400EF29B
0x1400ef28d  mov     [rbx+1460h], r15b
0x1400ef294  mov     edi, 1468h
0x1400ef299  jmp     short loc_1400EF2A7
0x1400ef29b  mov     [rbx+1461h], r15b
0x1400ef2a2  mov     edi, 16B8h
0x1400ef2a7  mov     rax, [rsp+0A8h+arg_8]
0x1400ef2af  lea     rcx, [rbx+18h]
0x1400ef2b3  mov     [rdi+rbx], rax
0x1400ef2b7  add     rcx, rdi; DestinationString
0x1400ef2ba  movups  xmm0, xmmword ptr [r12]
0x1400ef2bf  lea     rax, [rbx+28h]
0x1400ef2c3  mov     word ptr [rdi+rbx+1Ah], 200h
0x1400ef2ca  add     rax, rdi
0x1400ef2cd  mov     rdx, r13; SourceString
0x1400ef2d0  movdqu  xmmword ptr [rdi+rbx+8], xmm0
0x1400ef2d6  mov     [rdi+rbx+20h], rax
0x1400ef2db  mov     [rcx], si
0x1400ef2de  call    cs:__imp_RtlCopyUnicodeString
0x1400ef2e5  nop     dword ptr [rax+rax+00h]
0x1400ef2ea  mov     rax, [r14]
0x1400ef2ed  lea     rsi, [rbx+38h]
0x1400ef2f1  mov     [rdi+rbx+228h], rax
0x1400ef2f9  lea     rdx, [rsp+0A8h+LockState]; LockState
0x1400ef2fe  movups  xmm0, xmmword ptr [rbp+0]
0x1400ef302  movups  xmmword ptr [rdi+rbx+230h], xmm0
0x1400ef30a  movups  xmm1, xmmword ptr [rbp+10h]
0x1400ef30e  movups  xmmword ptr [rdi+rbx+240h], xmm1
0x1400ef316  mov     ecx, [rbx+18E0h]
0x1400ef31c  mov     edi, [rbx+1690h]
0x1400ef322  add     ecx, 58h ; 'X'
0x1400ef325  add     edi, ecx
0x1400ef327  mov     rcx, [rsi]; Lock
0x1400ef32a  call    cs:__imp_NdisReleaseRWLock
0x1400ef331  nop     dword ptr [rax+rax+00h]
0x1400ef336  xor     r15b, r15b
0x1400ef339  cmp     dword ptr [rbx+22D4h], 1
0x1400ef340  jnz     short loc_1400EF3B5
0x1400ef342  mov     r8d, [rbx+18E4h]
0x1400ef349  mov     eax, 64h ; 'd'
0x1400ef34e  test    r8d, r8d
0x1400ef351  movzx   edx, di
0x1400ef354  mov     rcx, rbx
0x1400ef357  cmovz   r8d, eax
0x1400ef35b  call    VmsPDSetupPDBuffersForAllECs
0x1400ef360  mov     edi, eax
0x1400ef362  test    eax, eax
0x1400ef364  jns     short loc_1400EF3B7
0x1400ef366  mov     rdx, [rbx+10A8h]
0x1400ef36d  xor     r8d, r8d
0x1400ef370  mov     rcx, rbx
0x1400ef373  call    VmsPDSwitchDataPathMode
0x1400ef378  mov     [rsp+0A8h+var_50], edi
0x1400ef37c  lea     rax, [rsp+0A8h+arg_8]
0x1400ef384  mov     [rsp+0A8h+var_58], rbp
0x1400ef389  mov     [rsp+0A8h+var_60], r14
0x1400ef38e  mov     [rsp+0A8h+var_68], r13
0x1400ef393  mov     [rsp+0A8h+var_70], r12
0x1400ef398  mov     [rsp+0A8h+var_78], rax
0x1400ef39d  lea     rax, [rsp+0A8h+arg_0]
0x1400ef3a5  mov     [rsp+0A8h+var_80], rax
0x1400ef3aa  call    WPP_RECORDER_SF_qq_guid_qqqd
0x1400ef3af  lea     rsi, [rbx+38h]
0x1400ef3b3  jmp     short loc_1400EF3B7
0x1400ef3b5  xor     edi, edi
0x1400ef3b7  xor     edx, edx; Wait
0x1400ef3b9  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400ef3c0  call    cs:__imp_KeReleaseMutex
0x1400ef3c7  nop     dword ptr [rax+rax+00h]
0x1400ef3cc  test    r15b, r15b
0x1400ef3cf  jz      short loc_1400EF3E5
0x1400ef3d1  mov     rcx, [rsi]; Lock
0x1400ef3d4  lea     rdx, [rsp+0A8h+LockState]; LockState
0x1400ef3d9  call    cs:__imp_NdisReleaseRWLock
0x1400ef3e0  nop     dword ptr [rax+rax+00h]
0x1400ef3e5  mov     rbx, [rsp+0A8h+arg_10]
0x1400ef3ed  mov     eax, edi
0x1400ef3ef  add     rsp, 70h
0x1400ef3f3  pop     r15
0x1400ef3f5  pop     r14
0x1400ef3f7  pop     r13
0x1400ef3f9  pop     r12
0x1400ef3fb  pop     rdi
0x1400ef3fc  pop     rsi
0x1400ef3fd  pop     rbp
0x1400ef3fe  retn
```
