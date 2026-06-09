# FlPnpEvent

- ea: `0x140118dfc`
- end: `0x140119116`
- name: `FlPnpEvent`
- size: `794`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140118d70`
- `0x140118da0`
- `0x140118dd0`
- `0x1401ae5e0`

## callees

- `0x1400ce888`
- `0x1400fa868`
- `0x1400fafe4`
- `0x1400fb124`
- `0x140103358`
- `0x1401036e0`
- `0x140103ac8`
- `0x140118dfc`
- `0x14011e3b4`
- `0x14011e920`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140118e4c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14011907c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140118e4c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14011907c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401190b5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401190e6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401190b5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401190e6`
- `NDIS!NdisAcquireRWLockWrite` at `0x140118eb0`
- `NDIS!NdisAcquireRWLockWrite` at `0x140118f1b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140118f7c`
- `NDIS!NdisAcquireRWLockWrite` at `0x140118eb0`
- `NDIS!NdisAcquireRWLockWrite` at `0x140118f1b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140118f7c`
- `NDIS!NdisReleaseRWLock` at `0x140118eef`
- `NDIS!NdisReleaseRWLock` at `0x140118f36`
- `NDIS!NdisReleaseRWLock` at `0x140118f97`
- `NDIS!NdisReleaseRWLock` at `0x140118eef`
- `NDIS!NdisReleaseRWLock` at `0x140118f36`
- `NDIS!NdisReleaseRWLock` at `0x140118f97`

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
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
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
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) == 0 )
      goto LABEL_25;
    v17 = FRAMING_NDIS_RESTART_V1;
    goto LABEL_22;
  }
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState, 0);
  v18 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 40);
  *(_DWORD *)(a1 + 196) |= 2u;
  NdisReleaseRWLock(v18, &LockState);
  FlpUninitializePacketProviderInterface(a1);
  if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
  {
    v17 = FRAMING_NDIS_PAUSE_V1;
LABEL_22:
    McTemplateK0qsq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (_DWORD)v17,
      v16,
      *(_DWORD *)(a1 + 1176),
      (__int64)byte_1401E115B,
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
0x140118dfc  mov     [rsp-8+arg_8], rbx
0x140118e01  mov     [rsp-8+arg_10], rsi
0x140118e06  push    rbp
0x140118e07  push    rdi
0x140118e08  push    r13
0x140118e0a  push    r14
0x140118e0c  push    r15
0x140118e0e  lea     rbp, [rsp-37h]
0x140118e13  sub     rsp, 90h
0x140118e1a  xor     eax, eax
0x140118e1c  xorps   xmm0, xmm0
0x140118e1f  mov     [rbp+57h+var_30], rax
0x140118e23  mov     rdi, rdx
0x140118e26  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140118e2a  mov     rbx, rcx
0x140118e2d  mov     [rbp+57h+LockState.Flags], al
0x140118e30  movups  [rbp+57h+var_50], xmm0
0x140118e34  movups  [rbp+57h+var_40], xmm0
0x140118e38  test    rcx, rcx
0x140118e3b  jz      loc_1401190F7
0x140118e41  mov     r13, [rcx+20h]
0x140118e45  lea     edx, [rax+1]; Count
0x140118e48  mov     rcx, [rcx+48h]; RunRefCacheAware
0x140118e4c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x140118e53  nop     dword ptr [rax+rax+00h]
0x140118e58  test    al, al
0x140118e5a  jz      loc_1401190F7
0x140118e60  lea     r14, [rdi+8]
0x140118e64  xor     r15d, r15d
0x140118e67  mov     ecx, [r14]
0x140118e6a  xor     dil, dil
0x140118e6d  xor     esi, esi
0x140118e6f  cmp     ecx, 7
0x140118e72  jg      loc_140118F02
0x140118e78  jz      short loc_140118E96
0x140118e7a  test    ecx, ecx
0x140118e7c  jz      short loc_140118E9E
0x140118e7e  sub     ecx, 1
0x140118e81  jz      short loc_140118E96
0x140118e83  sub     ecx, 1
0x140118e86  jz      short loc_140118E96
0x140118e88  sub     ecx, 1
0x140118e8b  jz      short loc_140118E96
0x140118e8d  cmp     ecx, 1
0x140118e90  jnz     loc_140118FE4
0x140118e96  mov     dil, 1
0x140118e99  jmp     loc_140118FE4
0x140118e9e  mov     rcx, [rbx+28h]; Lock
0x140118ea2  lea     rdx, [rbp+57h+LockState]; LockState
0x140118ea6  mov     rsi, [r14+8]
0x140118eaa  xor     r8d, r8d; Flags
0x140118ead  mov     dil, 1
0x140118eb0  call    cs:__imp_NdisAcquireRWLockWrite
0x140118eb7  nop     dword ptr [rax+rax+00h]
0x140118ebc  cmp     dword ptr [rsi], 1
0x140118ebf  mov     eax, [rbx+0C4h]
0x140118ec5  jz      short loc_140118ED2
0x140118ec7  or      eax, 4
0x140118eca  mov     [rbx+0C4h], eax
0x140118ed0  jmp     short loc_140118EE7
0x140118ed2  and     eax, 0FFFFFFFBh
0x140118ed5  lea     rdx, [rbp+57h+LockState]
0x140118ed9  mov     rcx, rbx
0x140118edc  mov     [rbx+0C4h], eax
0x140118ee2  call    FlpFlushQueuedPmRemoveOidsUnderLock
0x140118ee7  mov     rcx, [rbx+28h]; Lock
0x140118eeb  lea     rdx, [rbp+57h+LockState]; LockState
0x140118eef  call    cs:__imp_NdisReleaseRWLock
0x140118ef6  nop     dword ptr [rax+rax+00h]
0x140118efb  mov     esi, [rsi]
0x140118efd  jmp     loc_140118FE4
0x140118f02  sub     ecx, 8
0x140118f05  jz      short loc_140118F71
0x140118f07  sub     ecx, 1
0x140118f0a  jnz     loc_140118E88
0x140118f10  mov     rcx, [rbx+28h]; Lock
0x140118f14  lea     rdx, [rbp+57h+LockState]; LockState
0x140118f18  xor     r8d, r8d; Flags
0x140118f1b  call    cs:__imp_NdisAcquireRWLockWrite
0x140118f22  nop     dword ptr [rax+rax+00h]
0x140118f27  mov     rcx, [rbx+28h]; Lock
0x140118f2b  lea     rdx, [rbp+57h+LockState]; LockState
0x140118f2f  and     dword ptr [rbx+0C4h], 0FFFFFFFDh
0x140118f36  call    cs:__imp_NdisReleaseRWLock
0x140118f3d  nop     dword ptr [rax+rax+00h]
0x140118f42  mov     rcx, rbx
0x140118f45  call    FlpReinitializePacketProviderInterface
0x140118f4a  mov     rdx, [r14+8]
0x140118f4e  test    rdx, rdx
0x140118f51  jz      short loc_140118F5B
0x140118f53  mov     rcx, rbx
0x140118f56  call    FlpRestartPnpEvent
0x140118f5b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x140118f62  jz      loc_14011902C
0x140118f68  lea     rdx, FRAMING_NDIS_RESTART_V1
0x140118f6f  jmp     short loc_140118FBB
0x140118f71  mov     rcx, [rbx+28h]; Lock
0x140118f75  lea     rdx, [rbp+57h+LockState]; LockState
0x140118f79  xor     r8d, r8d; Flags
0x140118f7c  call    cs:__imp_NdisAcquireRWLockWrite
0x140118f83  nop     dword ptr [rax+rax+00h]
0x140118f88  mov     rcx, [rbx+28h]; Lock
0x140118f8c  lea     rdx, [rbp+57h+LockState]; LockState
0x140118f90  or      dword ptr [rbx+0C4h], 2
0x140118f97  call    cs:__imp_NdisReleaseRWLock
0x140118f9e  nop     dword ptr [rax+rax+00h]
0x140118fa3  mov     rcx, rbx
0x140118fa6  call    FlpUninitializePacketProviderInterface
0x140118fab  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x140118fb2  jz      short loc_14011902C
0x140118fb4  lea     rdx, FRAMING_NDIS_PAUSE_V1
0x140118fbb  mov     eax, [rbx+4A0h]
0x140118fc1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140118fc8  mov     r9d, [rbx+498h]
0x140118fcf  mov     [rsp+0B0h+var_88], eax
0x140118fd3  lea     rax, byte_1401E115B
0x140118fda  mov     [rsp+0B0h+var_90], rax
0x140118fdf  call    McTemplateK0qsq_EtwWriteTransfer
0x140118fe4  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x140118feb  jz      short loc_14011902C
0x140118fed  mov     eax, [r14]
0x140118ff0  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x140118ff7  movzx   edx, word ptr [r13+5Ch]
0x140118ffc  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140119003  mov     r9d, [rbx+498h]
0x14011900a  mov     [rsp+0B0h+var_78], esi
0x14011900e  mov     [rsp+0B0h+var_80], eax
0x140119012  mov     eax, [rbx+4A0h]
0x140119018  mov     [rsp+0B0h+var_88], eax
0x14011901c  mov     dword ptr [rsp+0B0h+var_90], edx
0x140119020  lea     rdx, TCPIP_FRAMING_PNP_EVENT
0x140119027  call    McTemplateK0qqqqq_EtwWriteTransfer
0x14011902c  test    dil, dil
0x14011902f  jz      loc_1401190DD
0x140119035  lea     rax, FlPnpEventComplete
0x14011903c  mov     [rbp+57h+var_68], r14
0x140119040  mov     [rbp+57h+var_70], rax
0x140119044  lea     rdx, [rbp+57h+var_50]
0x140119048  mov     rax, [rbx+128h]
0x14011904f  mov     rcx, rbx
0x140119052  mov     [rbp+57h+var_60], rax
0x140119056  mov     rax, [rbx+508h]
0x14011905d  mov     [rbp+57h+var_58], rax
0x140119061  call    FlpGetFirstClientInterface
0x140119066  jmp     short loc_1401190D5
0x140119068  mov     rcx, [rdi+88h]
0x14011906f  mov     edx, 1; Count
0x140119074  mov     [rbp+57h+var_60], rcx
0x140119078  mov     rcx, [rdi+38h]; RunRefCacheAware
0x14011907c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x140119083  nop     dword ptr [rax+rax+00h]
0x140119088  test    al, al
0x14011908a  jz      short loc_1401190C1
0x14011908c  mov     rax, [r13+0D8h]
0x140119093  mov     rcx, [rax+8]
0x140119097  mov     rax, [rcx+38h]
0x14011909b  lea     rcx, [rbp+57h+var_70]
0x14011909f  call    _guard_dispatch_icall
0x1401190a4  cmp     byte ptr [rdi+50h], 0
0x1401190a8  mov     edx, 1; Count
0x1401190ad  mov     rcx, [rdi+38h]; RunRef
0x1401190b1  cmovnz  r15d, eax
0x1401190b5  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401190bc  nop     dword ptr [rax+rax+00h]
0x1401190c1  mov     rcx, rdi
0x1401190c4  call    FlpDereferenceClientInterface
0x1401190c9  lea     rdx, [rbp+57h+var_50]
0x1401190cd  mov     rcx, rbx
0x1401190d0  call    FlpGetNextClientInterface
0x1401190d5  mov     rdi, rax
0x1401190d8  test    rax, rax
0x1401190db  jnz     short loc_140119068
0x1401190dd  mov     rcx, [rbx+48h]; RunRef
0x1401190e1  mov     edx, 1; Count
0x1401190e6  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401190ed  nop     dword ptr [rax+rax+00h]
0x1401190f2  mov     eax, r15d
0x1401190f5  jmp     short loc_1401190F9
0x1401190f7  xor     eax, eax
0x1401190f9  lea     r11, [rsp+0B0h+var_20]
0x140119101  mov     rbx, [r11+38h]
0x140119105  mov     rsi, [r11+40h]
0x140119109  mov     rsp, r11
0x14011910c  pop     r15
0x14011910e  pop     r14
0x140119110  pop     r13
0x140119112  pop     rdi
0x140119113  pop     rbp
0x140119114  retn
```
