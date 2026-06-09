# VmsCdpPortPvtUpdateTeamEncap

- ea: `0x1400cf9e4`
- end: `0x1400cfc66`
- name: `VmsCdpPortPvtUpdateTeamEncap`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400cfc6c`

## callees

- `0x14006b084`
- `0x1400cf9e4`
- `0x1400d318c`
- `0x1400d32c8`
- `0x14015ebb4`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400cfac1`
- `ntoskrnl!KeReleaseMutex` at `0x1400cfac1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cfa8c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400cfa8c`
- `NDIS!NdisReleaseRWLock` at `0x1400cfb57`
- `NDIS!NdisReleaseRWLock` at `0x1400cfbcb`
- `NDIS!NdisReleaseRWLock` at `0x1400cfbed`
- `NDIS!NdisReleaseRWLock` at `0x1400cfb57`
- `NDIS!NdisReleaseRWLock` at `0x1400cfbcb`
- `NDIS!NdisReleaseRWLock` at `0x1400cfbed`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400cfafc`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400cfafc`

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
0x1400cf9e4  mov     [rsp-38h+arg_18], rbx
0x1400cf9e9  push    rbp
0x1400cf9ea  push    rsi
0x1400cf9eb  push    rdi
0x1400cf9ec  push    r12
0x1400cf9ee  push    r13
0x1400cf9f0  push    r14
0x1400cf9f2  push    r15
0x1400cf9f4  mov     rbp, rsp
0x1400cf9f7  sub     rsp, 80h
0x1400cf9fe  mov     rax, cs:__security_cookie
0x1400cfa05  xor     rax, rsp
0x1400cfa08  mov     [rbp+var_8], rax
0x1400cfa0c  xor     eax, eax
0x1400cfa0e  mov     r15, r8
0x1400cfa11  mov     word ptr [rbp+LockState.OldIrql], ax
0x1400cfa15  mov     rbx, rdx
0x1400cfa18  mov     [rbp+LockState.Flags], al
0x1400cfa1b  mov     rdi, rcx
0x1400cfa1e  mov     word ptr [rbp+var_20.OldIrql], ax
0x1400cfa22  mov     [rbp+var_20.Flags], al
0x1400cfa25  xor     esi, esi
0x1400cfa27  test    rcx, rcx
0x1400cfa2a  jz      short loc_1400CFA35
0x1400cfa2c  mov     rdx, [rcx+2388h]
0x1400cfa33  jmp     short loc_1400CFA3C
0x1400cfa35  mov     rdx, cs:VmsIfrLog
0x1400cfa3c  movzx   ecx, word ptr [rbx+2A78h]
0x1400cfa43  lea     r12, [r8+200h]
0x1400cfa4a  movzx   eax, word ptr [r8+206h]
0x1400cfa52  lea     r14, [rbx+2A71h]
0x1400cfa59  mov     [rsp+80h+var_38], eax
0x1400cfa5d  mov     [rsp+80h+var_40], r12
0x1400cfa62  mov     [rsp+80h+var_48], ecx
0x1400cfa66  mov     rcx, rdx
0x1400cfa69  mov     [rsp+80h+var_50], r14
0x1400cfa6e  mov     [rsp+80h+var_58], rbx
0x1400cfa73  call    WPP_RECORDER_SF_q_MAC_d_MAC_d
0x1400cfa78  xor     r9d, r9d; Alertable
0x1400cfa7b  mov     [rsp+80h+Timeout], rsi; Timeout
0x1400cfa80  xor     r8d, r8d; WaitMode
0x1400cfa83  lea     rcx, VmsOmIoctlMutex; Object
0x1400cfa8a  xor     edx, edx; WaitReason
0x1400cfa8c  call    cs:__imp_KeWaitForSingleObject
0x1400cfa93  nop     dword ptr [rax+rax+00h]
0x1400cfa98  mov     rcx, [rbx+4E8h]
0x1400cfa9f  test    rcx, rcx
0x1400cfaa2  jz      short loc_1400CFAB8
0x1400cfaa4  mov     eax, [rcx+0D0Eh]
0x1400cfaaa  mov     [rbp+var_14], eax
0x1400cfaad  movzx   eax, word ptr [rcx+0D12h]
0x1400cfab4  mov     [rbp+var_10], ax
0x1400cfab8  xor     edx, edx; Wait
0x1400cfaba  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400cfac1  call    cs:__imp_KeReleaseMutex
0x1400cfac8  nop     dword ptr [rax+rax+00h]
0x1400cfacd  mov     rcx, [rdi+2328h]
0x1400cfad4  test    rcx, rcx
0x1400cfad7  jz      loc_1400CFBFF
0x1400cfadd  cmp     dword ptr [rcx+100h], 5
0x1400cfae4  jz      loc_1400CFBFF
0x1400cfaea  mov     rcx, [rcx+10h]
0x1400cfaee  lea     rdx, [rbp+LockState]; LockState
0x1400cfaf2  xor     r8d, r8d; Flags
0x1400cfaf5  mov     rcx, [rcx+630h]; Lock
0x1400cfafc  call    cs:__imp_NdisAcquireRWLockWrite
0x1400cfb03  nop     dword ptr [rax+rax+00h]
0x1400cfb08  xor     r8d, r8d
0x1400cfb0b  lea     rdx, [rbp+var_20]
0x1400cfb0f  mov     rcx, rbx
0x1400cfb12  call    VmsOmObjectLockExclusive
0x1400cfb17  movzx   eax, word ptr [r14+4]
0x1400cfb1c  lea     rdx, [rbp+var_20]; LockState
0x1400cfb20  mov     r13d, [r14]
0x1400cfb23  mov     rcx, [rbx+38h]; Lock
0x1400cfb27  mov     [rbp+var_18], ax
0x1400cfb2b  movzx   eax, word ptr [rbx+2A78h]
0x1400cfb32  mov     [rbp+var_16], ax
0x1400cfb36  mov     eax, [r12]
0x1400cfb3a  mov     [r14], eax
0x1400cfb3d  movzx   eax, word ptr [r12+4]
0x1400cfb43  mov     [r14+4], ax
0x1400cfb48  movzx   eax, word ptr [r15+206h]
0x1400cfb50  mov     [rbx+2A78h], ax
0x1400cfb57  call    cs:__imp_NdisReleaseRWLock
0x1400cfb5e  nop     dword ptr [rax+rax+00h]
0x1400cfb63  cmp     [r14], esi
0x1400cfb66  jnz     short loc_1400CFB7A
0x1400cfb68  cmp     [rbx+2A75h], si
0x1400cfb6f  jnz     short loc_1400CFB7A
0x1400cfb71  lea     r8, [rbp+var_14]
0x1400cfb75  mov     r9d, esi
0x1400cfb78  jmp     short loc_1400CFB85
0x1400cfb7a  movzx   r9d, word ptr [rbx+2A78h]
0x1400cfb82  mov     r8, r14
0x1400cfb85  mov     edx, [rbx+1720h]
0x1400cfb8b  mov     rcx, [rdi+2328h]
0x1400cfb92  call    VmsTmUpdateVmsPortCfgMacVlan
0x1400cfb97  mov     esi, eax
0x1400cfb99  test    eax, eax
0x1400cfb9b  jz      short loc_1400CFBD7
0x1400cfb9d  xor     r8d, r8d
0x1400cfba0  lea     rdx, [rbp+var_20]
0x1400cfba4  mov     rcx, rbx
0x1400cfba7  call    VmsOmObjectLockExclusive
0x1400cfbac  movzx   eax, [rbp+var_18]
0x1400cfbb0  lea     rdx, [rbp+var_20]; LockState
0x1400cfbb4  mov     rcx, [rbx+38h]; Lock
0x1400cfbb8  mov     [r14], r13d
0x1400cfbbb  mov     [r14+4], ax
0x1400cfbc0  movzx   eax, [rbp+var_16]
0x1400cfbc4  mov     [rbx+2A78h], ax
0x1400cfbcb  call    cs:__imp_NdisReleaseRWLock
0x1400cfbd2  nop     dword ptr [rax+rax+00h]
0x1400cfbd7  mov     rax, [rdi+2328h]
0x1400cfbde  lea     rdx, [rbp+LockState]; LockState
0x1400cfbe2  mov     rcx, [rax+10h]
0x1400cfbe6  mov     rcx, [rcx+630h]; Lock
0x1400cfbed  call    cs:__imp_NdisReleaseRWLock
0x1400cfbf4  nop     dword ptr [rax+rax+00h]
0x1400cfbf9  test    esi, esi
0x1400cfbfb  jz      short loc_1400CFC3C
0x1400cfbfd  jmp     short loc_1400CFC04
0x1400cfbff  mov     esi, 0C0000184h
0x1400cfc04  movzx   edx, word ptr [r15+206h]
0x1400cfc0c  movzx   r8d, word ptr [rbx+2A78h]
0x1400cfc14  mov     rcx, [rdi+2388h]
0x1400cfc1b  mov     [rsp+80h+var_30], esi
0x1400cfc1f  mov     [rsp+80h+var_38], edx
0x1400cfc23  mov     [rsp+80h+var_40], r12
0x1400cfc28  mov     [rsp+80h+var_48], r8d
0x1400cfc2d  mov     [rsp+80h+var_50], r14
0x1400cfc32  mov     [rsp+80h+var_58], rbx
0x1400cfc37  call    WPP_RECORDER_SF_q_MAC_d_MAC_dd
0x1400cfc3c  mov     eax, esi
0x1400cfc3e  mov     rcx, [rbp+var_8]
0x1400cfc42  xor     rcx, rsp; StackCookie
0x1400cfc45  call    __security_check_cookie
0x1400cfc4a  mov     rbx, [rsp+80h+arg_18]
0x1400cfc52  add     rsp, 80h
0x1400cfc59  pop     r15
0x1400cfc5b  pop     r14
0x1400cfc5d  pop     r13
0x1400cfc5f  pop     r12
0x1400cfc61  pop     rdi
0x1400cfc62  pop     rsi
0x1400cfc63  pop     rbp
0x1400cfc64  retn
```
