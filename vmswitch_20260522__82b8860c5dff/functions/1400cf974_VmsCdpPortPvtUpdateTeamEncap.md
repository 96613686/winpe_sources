# VmsCdpPortPvtUpdateTeamEncap

- ea: `0x1400cf974`
- end: `0x1400cfbf6`
- name: `VmsCdpPortPvtUpdateTeamEncap`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400cfbfc`

## callees

- `0x14006b084`
- `0x1400cf974`
- `0x1400d311c`
- `0x1400d3258`
- `0x14015eb44`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400cfa51`
- `ntoskrnl!KeReleaseMutex` at `0x1400cfa51`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cfa1c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cfa1c`
- `NDIS!NdisReleaseRWLock` at `0x1400cfae7`
- `NDIS!NdisReleaseRWLock` at `0x1400cfb5b`
- `NDIS!NdisReleaseRWLock` at `0x1400cfb7d`
- `NDIS!NdisReleaseRWLock` at `0x1400cfae7`
- `NDIS!NdisReleaseRWLock` at `0x1400cfb5b`
- `NDIS!NdisReleaseRWLock` at `0x1400cfb7d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400cfa8c`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400cfa8c`

## pseudocode

```c
__int64 __fastcall VmsCdpPortPvtUpdateTeamEncap(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v7; // rdx
  __int64 v8; // r12
  int *v9; // r14
  __int64 v10; // rcx
  int v11; // r9d
  __int64 v12; // rcx
  int v13; // r13d
  struct _NDIS_RW_LOCK_EX *v14; // rcx
  int *v15; // r8
  __int16 v16; // r9
  unsigned int updated; // esi
  __int16 v18; // ax
  struct _NDIS_RW_LOCK_EX *v19; // rcx
  int Timeout; // [rsp+20h] [rbp-60h]
  struct _LOCK_STATE_EX v22; // [rsp+60h] [rbp-20h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+64h] [rbp-1Ch] BYREF
  __int16 v24; // [rsp+68h] [rbp-18h]
  __int16 v25; // [rsp+6Ah] [rbp-16h]
  int v26; // [rsp+6Ch] [rbp-14h] BYREF
  __int16 v27; // [rsp+70h] [rbp-10h]

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v22.OldIrql = 0;
  v22.Flags = 0;
  if ( a1 )
    v7 = *(_QWORD *)(a1 + 9096);
  else
    LODWORD(v7) = VmsIfrLog;
  v8 = a3 + 512;
  v9 = (int *)(a2 + 10865);
  WPP_RECORDER_SF_q_MAC_d_MAC_d(v7, v7, a3, a4);
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  v10 = *(_QWORD *)(a2 + 1256);
  if ( v10 )
  {
    v26 = *(_DWORD *)(v10 + 3342);
    v27 = *(_WORD *)(v10 + 3346);
  }
  KeReleaseMutex(&VmsOmIoctlMutex, 0);
  v12 = *(_QWORD *)(a1 + 9000);
  if ( !v12 || *(_DWORD *)(v12 + 256) == 5 )
  {
    updated = -1073741436;
LABEL_17:
    WPP_RECORDER_SF_q_MAC_d_MAC_dd(
      *(_QWORD *)(a1 + 9096),
      *(unsigned __int16 *)(a3 + 518),
      *(unsigned __int16 *)(a2 + 10872),
      v11,
      Timeout,
      a2,
      a2 + 10865,
      *(_WORD *)(a2 + 10872),
      v8,
      *(_WORD *)(a3 + 518),
      updated);
    return updated;
  }
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v12 + 16) + 1584LL), &LockState, 0);
  VmsOmObjectLockExclusive(a2, &v22, 0);
  v13 = *v9;
  v14 = *(struct _NDIS_RW_LOCK_EX **)(a2 + 56);
  v24 = *(_WORD *)(a2 + 10869);
  v25 = *(_WORD *)(a2 + 10872);
  *v9 = *(_DWORD *)v8;
  *(_WORD *)(a2 + 10869) = *(_WORD *)(v8 + 4);
  *(_WORD *)(a2 + 10872) = *(_WORD *)(a3 + 518);
  NdisReleaseRWLock(v14, &v22);
  if ( *v9 || *(_WORD *)(a2 + 10869) )
  {
    v16 = *(_WORD *)(a2 + 10872);
    v15 = (int *)(a2 + 10865);
  }
  else
  {
    v15 = &v26;
    v16 = 0;
  }
  updated = VmsTmUpdateVmsPortCfgMacVlan(*(_QWORD *)(a1 + 9000), *(_DWORD *)(a2 + 5920), (__int64)v15, v16);
  if ( updated )
  {
    VmsOmObjectLockExclusive(a2, &v22, 0);
    v18 = v24;
    v19 = *(struct _NDIS_RW_LOCK_EX **)(a2 + 56);
    *v9 = v13;
    *(_WORD *)(a2 + 10869) = v18;
    *(_WORD *)(a2 + 10872) = v25;
    NdisReleaseRWLock(v19, &v22);
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(*(_QWORD *)(a1 + 9000) + 16LL) + 1584LL), &LockState);
  if ( updated )
    goto LABEL_17;
  return updated;
}

```

## disassembly

```asm
0x1400cf974  mov     [rsp-38h+arg_18], rbx
0x1400cf979  push    rbp
0x1400cf97a  push    rsi
0x1400cf97b  push    rdi
0x1400cf97c  push    r12
0x1400cf97e  push    r13
0x1400cf980  push    r14
0x1400cf982  push    r15
0x1400cf984  mov     rbp, rsp
0x1400cf987  sub     rsp, 80h
0x1400cf98e  mov     rax, cs:__security_cookie
0x1400cf995  xor     rax, rsp
0x1400cf998  mov     [rbp+var_8], rax
0x1400cf99c  xor     eax, eax
0x1400cf99e  mov     r15, r8
0x1400cf9a1  mov     word ptr [rbp+LockState.OldIrql], ax
0x1400cf9a5  mov     rbx, rdx
0x1400cf9a8  mov     [rbp+LockState.Flags], al
0x1400cf9ab  mov     rdi, rcx
0x1400cf9ae  mov     word ptr [rbp+var_20.OldIrql], ax
0x1400cf9b2  mov     [rbp+var_20.Flags], al
0x1400cf9b5  xor     esi, esi
0x1400cf9b7  test    rcx, rcx
0x1400cf9ba  jz      short loc_1400CF9C5
0x1400cf9bc  mov     rdx, [rcx+2388h]
0x1400cf9c3  jmp     short loc_1400CF9CC
0x1400cf9c5  mov     rdx, cs:VmsIfrLog
0x1400cf9cc  movzx   ecx, word ptr [rbx+2A78h]
0x1400cf9d3  lea     r12, [r8+200h]
0x1400cf9da  movzx   eax, word ptr [r8+206h]
0x1400cf9e2  lea     r14, [rbx+2A71h]
0x1400cf9e9  mov     [rsp+80h+var_38], eax
0x1400cf9ed  mov     [rsp+80h+var_40], r12
0x1400cf9f2  mov     [rsp+80h+var_48], ecx
0x1400cf9f6  mov     rcx, rdx
0x1400cf9f9  mov     [rsp+80h+var_50], r14
0x1400cf9fe  mov     [rsp+80h+var_58], rbx
0x1400cfa03  call    WPP_RECORDER_SF_q_MAC_d_MAC_d
0x1400cfa08  xor     r9d, r9d; Alertable
0x1400cfa0b  mov     [rsp+80h+Timeout], rsi; Timeout
0x1400cfa10  xor     r8d, r8d; WaitMode
0x1400cfa13  lea     rcx, VmsOmIoctlMutex; Object
0x1400cfa1a  xor     edx, edx; WaitReason
0x1400cfa1c  call    cs:__imp_KeWaitForSingleObject
0x1400cfa23  nop     dword ptr [rax+rax+00h]
0x1400cfa28  mov     rcx, [rbx+4E8h]
0x1400cfa2f  test    rcx, rcx
0x1400cfa32  jz      short loc_1400CFA48
0x1400cfa34  mov     eax, [rcx+0D0Eh]
0x1400cfa3a  mov     [rbp+var_14], eax
0x1400cfa3d  movzx   eax, word ptr [rcx+0D12h]
0x1400cfa44  mov     [rbp+var_10], ax
0x1400cfa48  xor     edx, edx; Wait
0x1400cfa4a  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400cfa51  call    cs:__imp_KeReleaseMutex
0x1400cfa58  nop     dword ptr [rax+rax+00h]
0x1400cfa5d  mov     rcx, [rdi+2328h]
0x1400cfa64  test    rcx, rcx
0x1400cfa67  jz      loc_1400CFB8F
0x1400cfa6d  cmp     dword ptr [rcx+100h], 5
0x1400cfa74  jz      loc_1400CFB8F
0x1400cfa7a  mov     rcx, [rcx+10h]
0x1400cfa7e  lea     rdx, [rbp+LockState]; LockState
0x1400cfa82  xor     r8d, r8d; Flags
0x1400cfa85  mov     rcx, [rcx+630h]; Lock
0x1400cfa8c  call    cs:__imp_NdisAcquireRWLockWrite
0x1400cfa93  nop     dword ptr [rax+rax+00h]
0x1400cfa98  xor     r8d, r8d
0x1400cfa9b  lea     rdx, [rbp+var_20]
0x1400cfa9f  mov     rcx, rbx
0x1400cfaa2  call    VmsOmObjectLockExclusive
0x1400cfaa7  movzx   eax, word ptr [r14+4]
0x1400cfaac  lea     rdx, [rbp+var_20]; LockState
0x1400cfab0  mov     r13d, [r14]
0x1400cfab3  mov     rcx, [rbx+38h]; Lock
0x1400cfab7  mov     [rbp+var_18], ax
0x1400cfabb  movzx   eax, word ptr [rbx+2A78h]
0x1400cfac2  mov     [rbp+var_16], ax
0x1400cfac6  mov     eax, [r12]
0x1400cfaca  mov     [r14], eax
0x1400cfacd  movzx   eax, word ptr [r12+4]
0x1400cfad3  mov     [r14+4], ax
0x1400cfad8  movzx   eax, word ptr [r15+206h]
0x1400cfae0  mov     [rbx+2A78h], ax
0x1400cfae7  call    cs:__imp_NdisReleaseRWLock
0x1400cfaee  nop     dword ptr [rax+rax+00h]
0x1400cfaf3  cmp     [r14], esi
0x1400cfaf6  jnz     short loc_1400CFB0A
0x1400cfaf8  cmp     [rbx+2A75h], si
0x1400cfaff  jnz     short loc_1400CFB0A
0x1400cfb01  lea     r8, [rbp+var_14]
0x1400cfb05  mov     r9d, esi
0x1400cfb08  jmp     short loc_1400CFB15
0x1400cfb0a  movzx   r9d, word ptr [rbx+2A78h]
0x1400cfb12  mov     r8, r14
0x1400cfb15  mov     edx, [rbx+1720h]
0x1400cfb1b  mov     rcx, [rdi+2328h]
0x1400cfb22  call    VmsTmUpdateVmsPortCfgMacVlan
0x1400cfb27  mov     esi, eax
0x1400cfb29  test    eax, eax
0x1400cfb2b  jz      short loc_1400CFB67
0x1400cfb2d  xor     r8d, r8d
0x1400cfb30  lea     rdx, [rbp+var_20]
0x1400cfb34  mov     rcx, rbx
0x1400cfb37  call    VmsOmObjectLockExclusive
0x1400cfb3c  movzx   eax, [rbp+var_18]
0x1400cfb40  lea     rdx, [rbp+var_20]; LockState
0x1400cfb44  mov     rcx, [rbx+38h]; Lock
0x1400cfb48  mov     [r14], r13d
0x1400cfb4b  mov     [r14+4], ax
0x1400cfb50  movzx   eax, [rbp+var_16]
0x1400cfb54  mov     [rbx+2A78h], ax
0x1400cfb5b  call    cs:__imp_NdisReleaseRWLock
0x1400cfb62  nop     dword ptr [rax+rax+00h]
0x1400cfb67  mov     rax, [rdi+2328h]
0x1400cfb6e  lea     rdx, [rbp+LockState]; LockState
0x1400cfb72  mov     rcx, [rax+10h]
0x1400cfb76  mov     rcx, [rcx+630h]; Lock
0x1400cfb7d  call    cs:__imp_NdisReleaseRWLock
0x1400cfb84  nop     dword ptr [rax+rax+00h]
0x1400cfb89  test    esi, esi
0x1400cfb8b  jz      short loc_1400CFBCC
0x1400cfb8d  jmp     short loc_1400CFB94
0x1400cfb8f  mov     esi, 0C0000184h
0x1400cfb94  movzx   edx, word ptr [r15+206h]
0x1400cfb9c  movzx   r8d, word ptr [rbx+2A78h]
0x1400cfba4  mov     rcx, [rdi+2388h]
0x1400cfbab  mov     [rsp+80h+var_30], esi
0x1400cfbaf  mov     [rsp+80h+var_38], edx
0x1400cfbb3  mov     [rsp+80h+var_40], r12
0x1400cfbb8  mov     [rsp+80h+var_48], r8d
0x1400cfbbd  mov     [rsp+80h+var_50], r14
0x1400cfbc2  mov     [rsp+80h+var_58], rbx
0x1400cfbc7  call    WPP_RECORDER_SF_q_MAC_d_MAC_dd
0x1400cfbcc  mov     eax, esi
0x1400cfbce  mov     rcx, [rbp+var_8]
0x1400cfbd2  xor     rcx, rsp; StackCookie
0x1400cfbd5  call    __security_check_cookie
0x1400cfbda  mov     rbx, [rsp+80h+arg_18]
0x1400cfbe2  add     rsp, 80h
0x1400cfbe9  pop     r15
0x1400cfbeb  pop     r14
0x1400cfbed  pop     r13
0x1400cfbef  pop     r12
0x1400cfbf1  pop     rdi
0x1400cfbf2  pop     rsi
0x1400cfbf3  pop     rbp
0x1400cfbf4  retn
```
