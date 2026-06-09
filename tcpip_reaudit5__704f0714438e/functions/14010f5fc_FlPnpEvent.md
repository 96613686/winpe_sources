# FlPnpEvent

- ea: `0x14010f5fc`
- end: `0x14010f916`
- name: `FlPnpEvent`
- size: `794`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14010f570`
- `0x14010f5a0`
- `0x14010f5d0`
- `0x1401aca20`

## callees

- `0x1400c5690`
- `0x1400c6318`
- `0x1400c66a0`
- `0x1400c72c4`
- `0x1400c7a44`
- `0x1400c7b84`
- `0x1400d6728`
- `0x14010f5fc`
- `0x1401144e4`
- `0x14011497c`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f8b5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f8e6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f8b5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f8e6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f64c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f87c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f64c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f87c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f6b0`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f71b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f77c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f6b0`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f71b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f77c`
- `NDIS!NdisReleaseRWLock` at `0x14010f6ef`
- `NDIS!NdisReleaseRWLock` at `0x14010f736`
- `NDIS!NdisReleaseRWLock` at `0x14010f797`
- `NDIS!NdisReleaseRWLock` at `0x14010f6ef`
- `NDIS!NdisReleaseRWLock` at `0x14010f736`
- `NDIS!NdisReleaseRWLock` at `0x14010f797`

## pseudocode

```c
__int64 __fastcall FlPnpEvent(__int64 a1, __int64 a2)
{
  __int64 v4; // r13
  __int64 v5; // r14
  unsigned int v6; // r15d
  int v7; // ecx
  char v8; // di
  int v9; // esi
  int v10; // ecx
  int v11; // ecx
  int *v12; // rsi
  int v13; // eax
  int v14; // ecx
  struct _NDIS_RW_LOCK_EX *v15; // rcx
  int v16; // r8d
  __int64 *v17; // rdx
  struct _NDIS_RW_LOCK_EX *v18; // rcx
  __int64 i; // rax
  unsigned int v20; // eax
  __int64 v21; // rdi
  _QWORD v23[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v24; // [rsp+50h] [rbp-9h]
  __int64 v25; // [rsp+58h] [rbp-1h]
  _OWORD v26[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v27; // [rsp+80h] [rbp+27h]
  struct _LOCK_STATE_EX LockState; // [rsp+C0h] [rbp+67h] BYREF

  v27 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(v26, 0, sizeof(v26));
  if ( !a1 )
    return 0;
  v4 = *(_QWORD *)(a1 + 32);
  if ( !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 72), 1u) )
    return 0;
  v5 = a2 + 8;
  v6 = 0;
  v7 = *(_DWORD *)(a2 + 8);
  v8 = 0;
  LOBYTE(v9) = 0;
  if ( v7 <= 7 )
  {
    if ( v7 == 7 )
      goto LABEL_9;
    if ( v7 )
    {
      v10 = v7 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
LABEL_8:
          if ( (unsigned int)(v11 - 1) > 1 )
            goto LABEL_23;
        }
      }
LABEL_9:
      v8 = 1;
      goto LABEL_23;
    }
    v12 = *(int **)(v5 + 8);
    v8 = 1;
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState, 0);
    v13 = *(_DWORD *)(a1 + 196);
    if ( *v12 == 1 )
    {
      *(_DWORD *)(a1 + 196) = v13 & 0xFFFFFFFB;
      FlpFlushQueuedPmRemoveOidsUnderLock(a1, &LockState);
    }
    else
    {
      *(_DWORD *)(a1 + 196) = v13 | 4;
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState);
    v9 = *v12;
LABEL_23:
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
      McTemplateK0qqqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_FRAMING_PNP_EVENT,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        *(_DWORD *)(a1 + 1176),
        *(_WORD *)(v4 + 92),
        *(_DWORD *)(a1 + 1184),
        *(_DWORD *)v5,
        v9);
    goto LABEL_25;
  }
  v14 = v7 - 8;
  if ( v14 )
  {
    v11 = v14 - 1;
    if ( v11 )
      goto LABEL_8;
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState, 0);
    v15 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 40);
    *(_DWORD *)(a1 + 196) &= ~2u;
    NdisReleaseRWLock(v15, &LockState);
    FlpReinitializePacketProviderInterface(a1);
    if ( *(_QWORD *)(v5 + 8) )
      FlpRestartPnpEvent(a1);
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) == 0 )
      goto LABEL_25;
    v17 = FRAMING_NDIS_RESTART_V1;
    goto LABEL_22;
  }
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState, 0);
  v18 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 40);
  *(_DWORD *)(a1 + 196) |= 2u;
  NdisReleaseRWLock(v18, &LockState);
  FlpUninitializePacketProviderInterface(a1);
  if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
  {
    v17 = FRAMING_NDIS_PAUSE_V1;
LABEL_22:
    McTemplateK0qsq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (_DWORD)v17,
      v16,
      *(_DWORD *)(a1 + 1176),
      (__int64)byte_1401DD293,
      *(_DWORD *)(a1 + 1184));
    goto LABEL_23;
  }
LABEL_25:
  if ( v8 )
  {
    v23[1] = v5;
    v23[0] = FlPnpEventComplete;
    v24 = *(_QWORD *)(a1 + 296);
    v25 = *(_QWORD *)(a1 + 1288);
    for ( i = FlpGetFirstClientInterface(a1, v26); ; i = FlpGetNextClientInterface(a1, v26) )
    {
      v21 = i;
      if ( !i )
        break;
      v24 = *(_QWORD *)(i + 136);
      if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(i + 56), 1u) )
      {
        v20 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(*(_QWORD *)(v4 + 216) + 8LL) + 56LL))(v23);
        if ( *(_BYTE *)(v21 + 80) )
          v6 = v20;
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v21 + 56), 1u);
      }
      FlpDereferenceClientInterface(v21);
    }
  }
  ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 72), 1u);
  return v6;
}

```

## disassembly

```asm
0x14010f5fc  mov     [rsp-8+arg_8], rbx
0x14010f601  mov     [rsp-8+arg_10], rsi
0x14010f606  push    rbp
0x14010f607  push    rdi
0x14010f608  push    r13
0x14010f60a  push    r14
0x14010f60c  push    r15
0x14010f60e  lea     rbp, [rsp-37h]
0x14010f613  sub     rsp, 90h
0x14010f61a  xor     eax, eax
0x14010f61c  xorps   xmm0, xmm0
0x14010f61f  mov     [rbp+57h+var_30], rax
0x14010f623  mov     rdi, rdx
0x14010f626  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14010f62a  mov     rbx, rcx
0x14010f62d  mov     [rbp+57h+LockState.Flags], al
0x14010f630  movups  [rbp+57h+var_50], xmm0
0x14010f634  movups  [rbp+57h+var_40], xmm0
0x14010f638  test    rcx, rcx
0x14010f63b  jz      loc_14010F8F7
0x14010f641  mov     r13, [rcx+20h]
0x14010f645  lea     edx, [rax+1]; Count
0x14010f648  mov     rcx, [rcx+48h]; RunRefCacheAware
0x14010f64c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14010f653  nop     dword ptr [rax+rax+00h]
0x14010f658  test    al, al
0x14010f65a  jz      loc_14010F8F7
0x14010f660  lea     r14, [rdi+8]
0x14010f664  xor     r15d, r15d
0x14010f667  mov     ecx, [r14]
0x14010f66a  xor     dil, dil
0x14010f66d  xor     esi, esi
0x14010f66f  cmp     ecx, 7
0x14010f672  jg      loc_14010F702
0x14010f678  jz      short loc_14010F696
0x14010f67a  test    ecx, ecx
0x14010f67c  jz      short loc_14010F69E
0x14010f67e  sub     ecx, 1
0x14010f681  jz      short loc_14010F696
0x14010f683  sub     ecx, 1
0x14010f686  jz      short loc_14010F696
0x14010f688  sub     ecx, 1
0x14010f68b  jz      short loc_14010F696
0x14010f68d  cmp     ecx, 1
0x14010f690  jnz     loc_14010F7E4
0x14010f696  mov     dil, 1
0x14010f699  jmp     loc_14010F7E4
0x14010f69e  mov     rcx, [rbx+28h]; Lock
0x14010f6a2  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f6a6  mov     rsi, [r14+8]
0x14010f6aa  xor     r8d, r8d; Flags
0x14010f6ad  mov     dil, 1
0x14010f6b0  call    cs:__imp_NdisAcquireRWLockWrite
0x14010f6b7  nop     dword ptr [rax+rax+00h]
0x14010f6bc  cmp     dword ptr [rsi], 1
0x14010f6bf  mov     eax, [rbx+0C4h]
0x14010f6c5  jz      short loc_14010F6D2
0x14010f6c7  or      eax, 4
0x14010f6ca  mov     [rbx+0C4h], eax
0x14010f6d0  jmp     short loc_14010F6E7
0x14010f6d2  and     eax, 0FFFFFFFBh
0x14010f6d5  lea     rdx, [rbp+57h+LockState]
0x14010f6d9  mov     rcx, rbx
0x14010f6dc  mov     [rbx+0C4h], eax
0x14010f6e2  call    FlpFlushQueuedPmRemoveOidsUnderLock
0x14010f6e7  mov     rcx, [rbx+28h]; Lock
0x14010f6eb  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f6ef  call    cs:__imp_NdisReleaseRWLock
0x14010f6f6  nop     dword ptr [rax+rax+00h]
0x14010f6fb  mov     esi, [rsi]
0x14010f6fd  jmp     loc_14010F7E4
0x14010f702  sub     ecx, 8
0x14010f705  jz      short loc_14010F771
0x14010f707  sub     ecx, 1
0x14010f70a  jnz     loc_14010F688
0x14010f710  mov     rcx, [rbx+28h]; Lock
0x14010f714  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f718  xor     r8d, r8d; Flags
0x14010f71b  call    cs:__imp_NdisAcquireRWLockWrite
0x14010f722  nop     dword ptr [rax+rax+00h]
0x14010f727  mov     rcx, [rbx+28h]; Lock
0x14010f72b  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f72f  and     dword ptr [rbx+0C4h], 0FFFFFFFDh
0x14010f736  call    cs:__imp_NdisReleaseRWLock
0x14010f73d  nop     dword ptr [rax+rax+00h]
0x14010f742  mov     rcx, rbx
0x14010f745  call    FlpReinitializePacketProviderInterface
0x14010f74a  mov     rdx, [r14+8]
0x14010f74e  test    rdx, rdx
0x14010f751  jz      short loc_14010F75B
0x14010f753  mov     rcx, rbx
0x14010f756  call    FlpRestartPnpEvent
0x14010f75b  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x14010f762  jz      loc_14010F82C
0x14010f768  lea     rdx, FRAMING_NDIS_RESTART_V1
0x14010f76f  jmp     short loc_14010F7BB
0x14010f771  mov     rcx, [rbx+28h]; Lock
0x14010f775  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f779  xor     r8d, r8d; Flags
0x14010f77c  call    cs:__imp_NdisAcquireRWLockWrite
0x14010f783  nop     dword ptr [rax+rax+00h]
0x14010f788  mov     rcx, [rbx+28h]; Lock
0x14010f78c  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f790  or      dword ptr [rbx+0C4h], 2
0x14010f797  call    cs:__imp_NdisReleaseRWLock
0x14010f79e  nop     dword ptr [rax+rax+00h]
0x14010f7a3  mov     rcx, rbx
0x14010f7a6  call    FlpUninitializePacketProviderInterface
0x14010f7ab  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x14010f7b2  jz      short loc_14010F82C
0x14010f7b4  lea     rdx, FRAMING_NDIS_PAUSE_V1
0x14010f7bb  mov     eax, [rbx+4A0h]
0x14010f7c1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14010f7c8  mov     r9d, [rbx+498h]
0x14010f7cf  mov     [rsp+0B0h+var_88], eax
0x14010f7d3  lea     rax, byte_1401DD293
0x14010f7da  mov     [rsp+0B0h+var_90], rax
0x14010f7df  call    McTemplateK0qsq_EtwWriteTransfer
0x14010f7e4  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x14010f7eb  jz      short loc_14010F82C
0x14010f7ed  mov     eax, [r14]
0x14010f7f0  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x14010f7f7  movzx   edx, word ptr [r13+5Ch]
0x14010f7fc  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14010f803  mov     r9d, [rbx+498h]
0x14010f80a  mov     [rsp+0B0h+var_78], esi
0x14010f80e  mov     [rsp+0B0h+var_80], eax
0x14010f812  mov     eax, [rbx+4A0h]
0x14010f818  mov     [rsp+0B0h+var_88], eax
0x14010f81c  mov     dword ptr [rsp+0B0h+var_90], edx
0x14010f820  lea     rdx, TCPIP_FRAMING_PNP_EVENT
0x14010f827  call    McTemplateK0qqqqq_EtwWriteTransfer
0x14010f82c  test    dil, dil
0x14010f82f  jz      loc_14010F8DD
0x14010f835  lea     rax, FlPnpEventComplete
0x14010f83c  mov     [rbp+57h+var_68], r14
0x14010f840  mov     [rbp+57h+var_70], rax
0x14010f844  lea     rdx, [rbp+57h+var_50]
0x14010f848  mov     rax, [rbx+128h]
0x14010f84f  mov     rcx, rbx
0x14010f852  mov     [rbp+57h+var_60], rax
0x14010f856  mov     rax, [rbx+508h]
0x14010f85d  mov     [rbp+57h+var_58], rax
0x14010f861  call    FlpGetFirstClientInterface
0x14010f866  jmp     short loc_14010F8D5
0x14010f868  mov     rcx, [rdi+88h]
0x14010f86f  mov     edx, 1; Count
0x14010f874  mov     [rbp+57h+var_60], rcx
0x14010f878  mov     rcx, [rdi+38h]; RunRefCacheAware
0x14010f87c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14010f883  nop     dword ptr [rax+rax+00h]
0x14010f888  test    al, al
0x14010f88a  jz      short loc_14010F8C1
0x14010f88c  mov     rax, [r13+0D8h]
0x14010f893  mov     rcx, [rax+8]
0x14010f897  mov     rax, [rcx+38h]
0x14010f89b  lea     rcx, [rbp+57h+var_70]
0x14010f89f  call    _guard_dispatch_icall
0x14010f8a4  cmp     byte ptr [rdi+50h], 0
0x14010f8a8  mov     edx, 1; Count
0x14010f8ad  mov     rcx, [rdi+38h]; RunRef
0x14010f8b1  cmovnz  r15d, eax
0x14010f8b5  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14010f8bc  nop     dword ptr [rax+rax+00h]
0x14010f8c1  mov     rcx, rdi
0x14010f8c4  call    FlpDereferenceClientInterface
0x14010f8c9  lea     rdx, [rbp+57h+var_50]
0x14010f8cd  mov     rcx, rbx
0x14010f8d0  call    FlpGetNextClientInterface
0x14010f8d5  mov     rdi, rax
0x14010f8d8  test    rax, rax
0x14010f8db  jnz     short loc_14010F868
0x14010f8dd  mov     rcx, [rbx+48h]; RunRef
0x14010f8e1  mov     edx, 1; Count
0x14010f8e6  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14010f8ed  nop     dword ptr [rax+rax+00h]
0x14010f8f2  mov     eax, r15d
0x14010f8f5  jmp     short loc_14010F8F9
0x14010f8f7  xor     eax, eax
0x14010f8f9  lea     r11, [rsp+0B0h+var_20]
0x14010f901  mov     rbx, [r11+38h]
0x14010f905  mov     rsi, [r11+40h]
0x14010f909  mov     rsp, r11
0x14010f90c  pop     r15
0x14010f90e  pop     r14
0x14010f910  pop     r13
0x14010f912  pop     rdi
0x14010f913  pop     rbp
0x14010f914  retn
```
