# FlPnpEvent

- ea: `0x14010f4bc`
- end: `0x14010f7d6`
- name: `FlPnpEvent`
- size: `794`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14010f430`
- `0x14010f460`
- `0x14010f490`
- `0x1401ac8e0`

## callees

- `0x1400c58b0`
- `0x1400c6538`
- `0x1400c68c0`
- `0x1400c74e4`
- `0x1400c7c64`
- `0x1400c7da4`
- `0x1400d6948`
- `0x14010f4bc`
- `0x1401143a4`
- `0x14011483c`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f50c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f73c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f50c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14010f73c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f775`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f7a6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f775`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14010f7a6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f570`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f5db`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f63c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f570`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f5db`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010f63c`
- `NDIS!NdisReleaseRWLock` at `0x14010f5af`
- `NDIS!NdisReleaseRWLock` at `0x14010f5f6`
- `NDIS!NdisReleaseRWLock` at `0x14010f657`
- `NDIS!NdisReleaseRWLock` at `0x14010f5af`
- `NDIS!NdisReleaseRWLock` at `0x14010f5f6`
- `NDIS!NdisReleaseRWLock` at `0x14010f657`

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
      (__int64)byte_1401DD2E3,
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
0x14010f4bc  mov     [rsp-8+arg_8], rbx
0x14010f4c1  mov     [rsp-8+arg_10], rsi
0x14010f4c6  push    rbp
0x14010f4c7  push    rdi
0x14010f4c8  push    r13
0x14010f4ca  push    r14
0x14010f4cc  push    r15
0x14010f4ce  lea     rbp, [rsp-37h]
0x14010f4d3  sub     rsp, 90h
0x14010f4da  xor     eax, eax
0x14010f4dc  xorps   xmm0, xmm0
0x14010f4df  mov     [rbp+57h+var_30], rax
0x14010f4e3  mov     rdi, rdx
0x14010f4e6  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14010f4ea  mov     rbx, rcx
0x14010f4ed  mov     [rbp+57h+LockState.Flags], al
0x14010f4f0  movups  [rbp+57h+var_50], xmm0
0x14010f4f4  movups  [rbp+57h+var_40], xmm0
0x14010f4f8  test    rcx, rcx
0x14010f4fb  jz      loc_14010F7B7
0x14010f501  mov     r13, [rcx+20h]
0x14010f505  lea     edx, [rax+1]; Count
0x14010f508  mov     rcx, [rcx+48h]; RunRefCacheAware
0x14010f50c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14010f513  nop     dword ptr [rax+rax+00h]
0x14010f518  test    al, al
0x14010f51a  jz      loc_14010F7B7
0x14010f520  lea     r14, [rdi+8]
0x14010f524  xor     r15d, r15d
0x14010f527  mov     ecx, [r14]
0x14010f52a  xor     dil, dil
0x14010f52d  xor     esi, esi
0x14010f52f  cmp     ecx, 7
0x14010f532  jg      loc_14010F5C2
0x14010f538  jz      short loc_14010F556
0x14010f53a  test    ecx, ecx
0x14010f53c  jz      short loc_14010F55E
0x14010f53e  sub     ecx, 1
0x14010f541  jz      short loc_14010F556
0x14010f543  sub     ecx, 1
0x14010f546  jz      short loc_14010F556
0x14010f548  sub     ecx, 1
0x14010f54b  jz      short loc_14010F556
0x14010f54d  cmp     ecx, 1
0x14010f550  jnz     loc_14010F6A4
0x14010f556  mov     dil, 1
0x14010f559  jmp     loc_14010F6A4
0x14010f55e  mov     rcx, [rbx+28h]; Lock
0x14010f562  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f566  mov     rsi, [r14+8]
0x14010f56a  xor     r8d, r8d; Flags
0x14010f56d  mov     dil, 1
0x14010f570  call    cs:__imp_NdisAcquireRWLockWrite
0x14010f577  nop     dword ptr [rax+rax+00h]
0x14010f57c  cmp     dword ptr [rsi], 1
0x14010f57f  mov     eax, [rbx+0C4h]
0x14010f585  jz      short loc_14010F592
0x14010f587  or      eax, 4
0x14010f58a  mov     [rbx+0C4h], eax
0x14010f590  jmp     short loc_14010F5A7
0x14010f592  and     eax, 0FFFFFFFBh
0x14010f595  lea     rdx, [rbp+57h+LockState]
0x14010f599  mov     rcx, rbx
0x14010f59c  mov     [rbx+0C4h], eax
0x14010f5a2  call    FlpFlushQueuedPmRemoveOidsUnderLock
0x14010f5a7  mov     rcx, [rbx+28h]; Lock
0x14010f5ab  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f5af  call    cs:__imp_NdisReleaseRWLock
0x14010f5b6  nop     dword ptr [rax+rax+00h]
0x14010f5bb  mov     esi, [rsi]
0x14010f5bd  jmp     loc_14010F6A4
0x14010f5c2  sub     ecx, 8
0x14010f5c5  jz      short loc_14010F631
0x14010f5c7  sub     ecx, 1
0x14010f5ca  jnz     loc_14010F548
0x14010f5d0  mov     rcx, [rbx+28h]; Lock
0x14010f5d4  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f5d8  xor     r8d, r8d; Flags
0x14010f5db  call    cs:__imp_NdisAcquireRWLockWrite
0x14010f5e2  nop     dword ptr [rax+rax+00h]
0x14010f5e7  mov     rcx, [rbx+28h]; Lock
0x14010f5eb  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f5ef  and     dword ptr [rbx+0C4h], 0FFFFFFFDh
0x14010f5f6  call    cs:__imp_NdisReleaseRWLock
0x14010f5fd  nop     dword ptr [rax+rax+00h]
0x14010f602  mov     rcx, rbx
0x14010f605  call    FlpReinitializePacketProviderInterface
0x14010f60a  mov     rdx, [r14+8]
0x14010f60e  test    rdx, rdx
0x14010f611  jz      short loc_14010F61B
0x14010f613  mov     rcx, rbx
0x14010f616  call    FlpRestartPnpEvent
0x14010f61b  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x14010f622  jz      loc_14010F6EC
0x14010f628  lea     rdx, FRAMING_NDIS_RESTART_V1
0x14010f62f  jmp     short loc_14010F67B
0x14010f631  mov     rcx, [rbx+28h]; Lock
0x14010f635  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f639  xor     r8d, r8d; Flags
0x14010f63c  call    cs:__imp_NdisAcquireRWLockWrite
0x14010f643  nop     dword ptr [rax+rax+00h]
0x14010f648  mov     rcx, [rbx+28h]; Lock
0x14010f64c  lea     rdx, [rbp+57h+LockState]; LockState
0x14010f650  or      dword ptr [rbx+0C4h], 2
0x14010f657  call    cs:__imp_NdisReleaseRWLock
0x14010f65e  nop     dword ptr [rax+rax+00h]
0x14010f663  mov     rcx, rbx
0x14010f666  call    FlpUninitializePacketProviderInterface
0x14010f66b  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x14010f672  jz      short loc_14010F6EC
0x14010f674  lea     rdx, FRAMING_NDIS_PAUSE_V1
0x14010f67b  mov     eax, [rbx+4A0h]
0x14010f681  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14010f688  mov     r9d, [rbx+498h]
0x14010f68f  mov     [rsp+0B0h+var_88], eax
0x14010f693  lea     rax, byte_1401DD2E3
0x14010f69a  mov     [rsp+0B0h+var_90], rax
0x14010f69f  call    McTemplateK0qsq_EtwWriteTransfer
0x14010f6a4  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x14010f6ab  jz      short loc_14010F6EC
0x14010f6ad  mov     eax, [r14]
0x14010f6b0  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x14010f6b7  movzx   edx, word ptr [r13+5Ch]
0x14010f6bc  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14010f6c3  mov     r9d, [rbx+498h]
0x14010f6ca  mov     [rsp+0B0h+var_78], esi
0x14010f6ce  mov     [rsp+0B0h+var_80], eax
0x14010f6d2  mov     eax, [rbx+4A0h]
0x14010f6d8  mov     [rsp+0B0h+var_88], eax
0x14010f6dc  mov     dword ptr [rsp+0B0h+var_90], edx
0x14010f6e0  lea     rdx, TCPIP_FRAMING_PNP_EVENT
0x14010f6e7  call    McTemplateK0qqqqq_EtwWriteTransfer
0x14010f6ec  test    dil, dil
0x14010f6ef  jz      loc_14010F79D
0x14010f6f5  lea     rax, FlPnpEventComplete
0x14010f6fc  mov     [rbp+57h+var_68], r14
0x14010f700  mov     [rbp+57h+var_70], rax
0x14010f704  lea     rdx, [rbp+57h+var_50]
0x14010f708  mov     rax, [rbx+128h]
0x14010f70f  mov     rcx, rbx
0x14010f712  mov     [rbp+57h+var_60], rax
0x14010f716  mov     rax, [rbx+508h]
0x14010f71d  mov     [rbp+57h+var_58], rax
0x14010f721  call    FlpGetFirstClientInterface
0x14010f726  jmp     short loc_14010F795
0x14010f728  mov     rcx, [rdi+88h]
0x14010f72f  mov     edx, 1; Count
0x14010f734  mov     [rbp+57h+var_60], rcx
0x14010f738  mov     rcx, [rdi+38h]; RunRefCacheAware
0x14010f73c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14010f743  nop     dword ptr [rax+rax+00h]
0x14010f748  test    al, al
0x14010f74a  jz      short loc_14010F781
0x14010f74c  mov     rax, [r13+0D8h]
0x14010f753  mov     rcx, [rax+8]
0x14010f757  mov     rax, [rcx+38h]
0x14010f75b  lea     rcx, [rbp+57h+var_70]
0x14010f75f  call    _guard_dispatch_icall
0x14010f764  cmp     byte ptr [rdi+50h], 0
0x14010f768  mov     edx, 1; Count
0x14010f76d  mov     rcx, [rdi+38h]; RunRef
0x14010f771  cmovnz  r15d, eax
0x14010f775  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14010f77c  nop     dword ptr [rax+rax+00h]
0x14010f781  mov     rcx, rdi
0x14010f784  call    FlpDereferenceClientInterface
0x14010f789  lea     rdx, [rbp+57h+var_50]
0x14010f78d  mov     rcx, rbx
0x14010f790  call    FlpGetNextClientInterface
0x14010f795  mov     rdi, rax
0x14010f798  test    rax, rax
0x14010f79b  jnz     short loc_14010F728
0x14010f79d  mov     rcx, [rbx+48h]; RunRef
0x14010f7a1  mov     edx, 1; Count
0x14010f7a6  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14010f7ad  nop     dword ptr [rax+rax+00h]
0x14010f7b2  mov     eax, r15d
0x14010f7b5  jmp     short loc_14010F7B9
0x14010f7b7  xor     eax, eax
0x14010f7b9  lea     r11, [rsp+0B0h+var_20]
0x14010f7c1  mov     rbx, [r11+38h]
0x14010f7c5  mov     rsi, [r11+40h]
0x14010f7c9  mov     rsp, r11
0x14010f7cc  pop     r15
0x14010f7ce  pop     r14
0x14010f7d0  pop     r13
0x14010f7d2  pop     rdi
0x14010f7d3  pop     rbp
0x14010f7d4  retn
```
