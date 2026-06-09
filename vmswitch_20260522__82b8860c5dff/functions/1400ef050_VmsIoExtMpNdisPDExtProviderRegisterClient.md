# VmsIoExtMpNdisPDExtProviderRegisterClient

- ea: `0x1400ef050`
- end: `0x1400ef390`
- name: `VmsIoExtMpNdisPDExtProviderRegisterClient`
- size: `832`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x14003a450`
- `0x14006b084`
- `0x1400ef050`
- `0x1400f012c`
- `0x14012c764`
- `0x14012caa4`
- `0x1401bbea0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ef26e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ef26e`
- `ntoskrnl!KeReleaseMutex` at `0x1400ef350`
- `ntoskrnl!KeReleaseMutex` at `0x1400ef350`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ef09b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ef09b`
- `NDIS!NdisReleaseRWLock` at `0x1400ef2ba`
- `NDIS!NdisReleaseRWLock` at `0x1400ef369`
- `NDIS!NdisReleaseRWLock` at `0x1400ef2ba`
- `NDIS!NdisReleaseRWLock` at `0x1400ef369`

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
0x1400ef050  mov     [rsp+arg_10], rbx
0x1400ef055  mov     [rsp+arg_8], rdx
0x1400ef05a  mov     [rsp+arg_0], rcx
0x1400ef05f  push    rbp
0x1400ef060  push    rsi
0x1400ef061  push    rdi
0x1400ef062  push    r12
0x1400ef064  push    r13
0x1400ef066  push    r14
0x1400ef068  push    r15
0x1400ef06a  sub     rsp, 70h
0x1400ef06e  xor     eax, eax
0x1400ef070  mov     r13, r9
0x1400ef073  mov     r12, r8
0x1400ef076  mov     word ptr [rsp+0A8h+LockState.OldIrql], ax
0x1400ef07b  mov     rbx, rcx
0x1400ef07e  mov     [rsp+0A8h+LockState.Flags], al
0x1400ef082  xor     esi, esi
0x1400ef084  lea     rcx, VmsOmIoctlMutex; Object
0x1400ef08b  xor     r9d, r9d; Alertable
0x1400ef08e  mov     [rsp+0A8h+Timeout], rsi; Timeout
0x1400ef093  xor     r8d, r8d; WaitMode
0x1400ef096  xor     edx, edx; WaitReason
0x1400ef098  mov     r15b, sil
0x1400ef09b  call    cs:__imp_KeWaitForSingleObject
0x1400ef0a2  nop     dword ptr [rax+rax+00h]
0x1400ef0a7  mov     rbp, [rsp+0A8h+arg_28]
0x1400ef0af  mov     r14, [rsp+0A8h+arg_20]
0x1400ef0b7  test    rbx, rbx
0x1400ef0ba  jnz     short loc_1400EF0F0
0x1400ef0bc  mov     eax, 0C000000Dh
0x1400ef0c1  mov     edi, eax
0x1400ef0c3  mov     rcx, cs:VmsIfrLog
0x1400ef0ca  lea     r8d, [rsi+14h]
0x1400ef0ce  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef0d2  mov     r9d, 0A4h
0x1400ef0d8  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef0df  mov     dl, 2
0x1400ef0e1  mov     [rsp+0A8h+Timeout], rax
0x1400ef0e6  call    WPP_RECORDER_SF_d
0x1400ef0eb  jmp     loc_1400EF308
0x1400ef0f0  test    r14, r14
0x1400ef0f3  jnz     short loc_1400EF129
0x1400ef0f5  mov     eax, 0C000000Dh
0x1400ef0fa  mov     edi, eax
0x1400ef0fc  mov     rcx, cs:VmsIfrLog
0x1400ef103  lea     r8d, [r14+14h]
0x1400ef107  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef10b  mov     r9d, 0A5h
0x1400ef111  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef118  mov     dl, 2
0x1400ef11a  mov     [rsp+0A8h+Timeout], rax
0x1400ef11f  call    WPP_RECORDER_SF_d
0x1400ef124  jmp     loc_1400EF308
0x1400ef129  test    rbp, rbp
0x1400ef12c  jnz     short loc_1400EF162
0x1400ef12e  mov     eax, 0C000000Dh
0x1400ef133  mov     edi, eax
0x1400ef135  mov     rcx, cs:VmsIfrLog
0x1400ef13c  lea     r8d, [rbp+14h]
0x1400ef140  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef144  mov     r9d, 0A6h
0x1400ef14a  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef151  mov     dl, 2
0x1400ef153  mov     [rsp+0A8h+Timeout], rax
0x1400ef158  call    WPP_RECORDER_SF_d
0x1400ef15d  jmp     loc_1400EF308
0x1400ef162  mov     r8d, 10h; Size
0x1400ef168  lea     rdx, VmsPDTestExtensionGuid; Buf2
0x1400ef16f  mov     rcx, r12; Buf1
0x1400ef172  call    memcmp
0x1400ef177  test    eax, eax
0x1400ef179  lea     rdx, [rsp+0A8h+LockState]
0x1400ef17e  mov     rcx, rbx
0x1400ef181  setz    dil
0x1400ef185  xor     r8d, r8d
0x1400ef188  call    VmsOmObjectLockExclusive
0x1400ef18d  mov     r15b, 1
0x1400ef190  cmp     [rbx+1460h], sil
0x1400ef197  jz      short loc_1400EF1D4
0x1400ef199  test    dil, dil
0x1400ef19c  jnz     short loc_1400EF1D4
0x1400ef19e  mov     eax, 0C0000718h
0x1400ef1a3  mov     edi, eax
0x1400ef1a5  mov     rcx, cs:VmsIfrLog
0x1400ef1ac  mov     r9d, 0A7h
0x1400ef1b2  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef1b6  mov     r8d, 14h
0x1400ef1bc  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef1c3  mov     dl, 2
0x1400ef1c5  mov     [rsp+0A8h+Timeout], rax
0x1400ef1ca  call    WPP_RECORDER_SF_d
0x1400ef1cf  jmp     loc_1400EF308
0x1400ef1d4  cmp     [rbx+1461h], sil
0x1400ef1db  jz      short loc_1400EF218
0x1400ef1dd  test    dil, dil
0x1400ef1e0  jz      short loc_1400EF21D
0x1400ef1e2  mov     eax, 0C0000718h
0x1400ef1e7  mov     edi, eax
0x1400ef1e9  mov     rcx, cs:VmsIfrLog
0x1400ef1f0  mov     r9d, 0A8h
0x1400ef1f6  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400ef1fa  mov     r8d, 14h
0x1400ef200  lea     rax, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x1400ef207  mov     dl, 2
0x1400ef209  mov     [rsp+0A8h+Timeout], rax
0x1400ef20e  call    WPP_RECORDER_SF_d
0x1400ef213  jmp     loc_1400EF308
0x1400ef218  test    dil, dil
0x1400ef21b  jnz     short loc_1400EF22B
0x1400ef21d  mov     [rbx+1460h], r15b
0x1400ef224  mov     edi, 1468h
0x1400ef229  jmp     short loc_1400EF237
0x1400ef22b  mov     [rbx+1461h], r15b
0x1400ef232  mov     edi, 16B8h
0x1400ef237  mov     rax, [rsp+0A8h+arg_8]
0x1400ef23f  lea     rcx, [rbx+18h]
0x1400ef243  mov     [rdi+rbx], rax
0x1400ef247  add     rcx, rdi; DestinationString
0x1400ef24a  movups  xmm0, xmmword ptr [r12]
0x1400ef24f  lea     rax, [rbx+28h]
0x1400ef253  mov     word ptr [rdi+rbx+1Ah], 200h
0x1400ef25a  add     rax, rdi
0x1400ef25d  mov     rdx, r13; SourceString
0x1400ef260  movdqu  xmmword ptr [rdi+rbx+8], xmm0
0x1400ef266  mov     [rdi+rbx+20h], rax
0x1400ef26b  mov     [rcx], si
0x1400ef26e  call    cs:__imp_RtlCopyUnicodeString
0x1400ef275  nop     dword ptr [rax+rax+00h]
0x1400ef27a  mov     rax, [r14]
0x1400ef27d  lea     rsi, [rbx+38h]
0x1400ef281  mov     [rdi+rbx+228h], rax
0x1400ef289  lea     rdx, [rsp+0A8h+LockState]; LockState
0x1400ef28e  movups  xmm0, xmmword ptr [rbp+0]
0x1400ef292  movups  xmmword ptr [rdi+rbx+230h], xmm0
0x1400ef29a  movups  xmm1, xmmword ptr [rbp+10h]
0x1400ef29e  movups  xmmword ptr [rdi+rbx+240h], xmm1
0x1400ef2a6  mov     ecx, [rbx+18E0h]
0x1400ef2ac  mov     edi, [rbx+1690h]
0x1400ef2b2  add     ecx, 58h ; 'X'
0x1400ef2b5  add     edi, ecx
0x1400ef2b7  mov     rcx, [rsi]; Lock
0x1400ef2ba  call    cs:__imp_NdisReleaseRWLock
0x1400ef2c1  nop     dword ptr [rax+rax+00h]
0x1400ef2c6  xor     r15b, r15b
0x1400ef2c9  cmp     dword ptr [rbx+22D4h], 1
0x1400ef2d0  jnz     short loc_1400EF345
0x1400ef2d2  mov     r8d, [rbx+18E4h]
0x1400ef2d9  mov     eax, 64h ; 'd'
0x1400ef2de  test    r8d, r8d
0x1400ef2e1  movzx   edx, di
0x1400ef2e4  mov     rcx, rbx
0x1400ef2e7  cmovz   r8d, eax
0x1400ef2eb  call    VmsPDSetupPDBuffersForAllECs
0x1400ef2f0  mov     edi, eax
0x1400ef2f2  test    eax, eax
0x1400ef2f4  jns     short loc_1400EF347
0x1400ef2f6  mov     rdx, [rbx+10A8h]
0x1400ef2fd  xor     r8d, r8d
0x1400ef300  mov     rcx, rbx
0x1400ef303  call    VmsPDSwitchDataPathMode
0x1400ef308  mov     [rsp+0A8h+var_50], edi
0x1400ef30c  lea     rax, [rsp+0A8h+arg_8]
0x1400ef314  mov     [rsp+0A8h+var_58], rbp
0x1400ef319  mov     [rsp+0A8h+var_60], r14
0x1400ef31e  mov     [rsp+0A8h+var_68], r13
0x1400ef323  mov     [rsp+0A8h+var_70], r12
0x1400ef328  mov     [rsp+0A8h+var_78], rax
0x1400ef32d  lea     rax, [rsp+0A8h+arg_0]
0x1400ef335  mov     [rsp+0A8h+var_80], rax
0x1400ef33a  call    WPP_RECORDER_SF_qq_guid_qqqd
0x1400ef33f  lea     rsi, [rbx+38h]
0x1400ef343  jmp     short loc_1400EF347
0x1400ef345  xor     edi, edi
0x1400ef347  xor     edx, edx; Wait
0x1400ef349  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400ef350  call    cs:__imp_KeReleaseMutex
0x1400ef357  nop     dword ptr [rax+rax+00h]
0x1400ef35c  test    r15b, r15b
0x1400ef35f  jz      short loc_1400EF375
0x1400ef361  mov     rcx, [rsi]; Lock
0x1400ef364  lea     rdx, [rsp+0A8h+LockState]; LockState
0x1400ef369  call    cs:__imp_NdisReleaseRWLock
0x1400ef370  nop     dword ptr [rax+rax+00h]
0x1400ef375  mov     rbx, [rsp+0A8h+arg_10]
0x1400ef37d  mov     eax, edi
0x1400ef37f  add     rsp, 70h
0x1400ef383  pop     r15
0x1400ef385  pop     r14
0x1400ef387  pop     r13
0x1400ef389  pop     r12
0x1400ef38b  pop     rdi
0x1400ef38c  pop     rsi
0x1400ef38d  pop     rbp
0x1400ef38e  retn
```
