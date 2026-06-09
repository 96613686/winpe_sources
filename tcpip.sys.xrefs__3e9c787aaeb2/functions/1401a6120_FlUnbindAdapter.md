# FlUnbindAdapter

- ea: `0x1401a6120`
- end: `0x1401a6467`
- name: `FlUnbindAdapter`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140063720`
- `0x1400fb124`
- `0x1401017b0`
- `0x1401020f0`
- `0x14010223c`
- `0x140103488`
- `0x140103a80`
- `0x140103de4`
- `0x1401048d0`
- `0x1401195d4`
- `0x14011e8f4`
- `0x140124bf8`
- `0x14014b574`
- `0x14014bb58`
- `0x1401a6120`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a620b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a620b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a627f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a6377`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a627f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a6377`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1401a63f3`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1401a63f3`
- `NDIS!NdisCloseAdapterEx` at `0x1401a6348`
- `NDIS!NdisCloseAdapterEx` at `0x1401a6348`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a6191`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a6191`
- `NDIS!NdisReleaseRWLock` at `0x1401a61b5`
- `NDIS!NdisReleaseRWLock` at `0x1401a61b5`

## pseudocode

```c
__int64 __fastcall FlUnbindAdapter(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  int v4; // esi
  NDIS_STATUS v5; // ecx
  __int64 v6; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF
  int v9; // [rsp+60h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a2 + 32);
  v4 = *(_DWORD *)(a2 + 1176);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
    McTemplateK0qqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCPIP_FRAMING_BIND_PROGRESS,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      v4,
      *(_WORD *)(v2 + 92),
      2,
      0);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a2 + 40), &LockState, 0);
  *(_DWORD *)(a2 + 196) |= 8u;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a2 + 40), &LockState);
  FlpSerializedNdisRequest((PVOID)a2, 0, 0);
  if ( (*(_DWORD *)(a2 + 976) & 1) != 0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a2 + 32) + 632LL))(a2, 8);
  ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a2 + 72));
  if ( *(_BYTE *)(v2 + 656) )
    FlpDisableVirtualInterfaceConfiguration(a2);
  FlpDeleteInterface(*(PRTL_DYNAMIC_HASH_TABLE_ENTRY *)(a2 + 288));
  FlpDereferenceClientInterface(*(_QWORD *)(a2 + 288));
  FlpFlushQueuedPmRemoveOids(a2);
  if ( *(_DWORD *)(a2 + 860) != 1 && _InterlockedDecrement((volatile signed __int32 *)(a2 + 860)) != 1 )
    KeWaitForSingleObject((PVOID)(a2 + 864), UserRequest, 0, 0, 0);
  FlpCleanupWolPatternEntries(a2);
  if ( *(_DWORD *)(a2 + 912) )
  {
    v9 = *(_DWORD *)(a2 + 912);
    FlpNdisRequest(a2, 0, 1, -50265845, (__int64)&v9, 4, 0);
    *(_DWORD *)(a2 + 912) = 0;
  }
  if ( *(_DWORD *)(a2 + 916) )
  {
    v9 = *(_DWORD *)(a2 + 916);
    FlpNdisRequest(a2, 0, 1, -50265845, (__int64)&v9, 4, 0);
    *(_DWORD *)(a2 + 916) = 0;
  }
  FlpCleanupPortCoalescedWakePatterns(a2);
  FlpCleanupL2UnicastWakePatterns(a2);
  FlpTraceWakeStatistics(a2);
  FlpUninitializeProviderInterfaces(a2);
  v5 = NdisCloseAdapterEx(*(NDIS_HANDLE *)(a2 + 1280));
  if ( v5 == 259 )
  {
    KeWaitForSingleObject((PVOID)(a2 + 168), UserRequest, 0, 0, 0);
    v5 = *(_DWORD *)(a2 + 192);
  }
  if ( v5 < 0 )
  {
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_FRAMING_BIND_PROGRESS,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v4,
        *(_WORD *)(v2 + 92),
        10,
        v5);
  }
  else if ( *(_DWORD *)(a2 + 312) == 15 )
  {
    v6 = *(_QWORD *)(a2 + 32);
    if ( *(_WORD *)(v6 + 92) == 23 )
      (*(void (__fastcall **)(__int64))(v6 + 400))(a2);
  }
  NetioDeregisterTriageDumpDataCallback(a2 + 1088);
  FlpRemoveInterface(v2 + 440, a2);
  FlpDereferenceInterface(a2);
  if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
    McTemplateK0qqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCPIP_FRAMING_BIND_PROGRESS,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      v4,
      *(_WORD *)(v2 + 92),
      3,
      0);
  return 0;
}

```

## disassembly

```asm
0x1401a6120  mov     [rsp+arg_0], rbx
0x1401a6125  mov     [rsp+arg_18], rsi
0x1401a612a  push    rdi
0x1401a612b  sub     rsp, 40h
0x1401a612f  mov     rdi, [rdx+20h]
0x1401a6133  xor     eax, eax
0x1401a6135  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x1401a613c  mov     rbx, rdx
0x1401a613f  mov     esi, [rdx+498h]
0x1401a6145  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1401a614a  mov     [rsp+48h+LockState.Flags], al
0x1401a614e  jz      short loc_1401A6185
0x1401a6150  movzx   eax, word ptr [rdi+5Ch]
0x1401a6154  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a615b  mov     dword ptr [rsp+48h+var_18], 0
0x1401a6163  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a616a  mov     dword ptr [rsp+48h+var_20], 2
0x1401a6172  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a6179  mov     r9d, esi
0x1401a617c  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a6180  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a6185  mov     rcx, [rbx+28h]; Lock
0x1401a6189  lea     rdx, [rsp+48h+LockState]; LockState
0x1401a618e  xor     r8d, r8d; Flags
0x1401a6191  call    cs:__imp_NdisAcquireRWLockWrite
0x1401a6198  nop     dword ptr [rax+rax+00h]
0x1401a619d  mov     eax, [rbx+0C4h]
0x1401a61a3  lea     rdx, [rsp+48h+LockState]; LockState
0x1401a61a8  or      eax, 8
0x1401a61ab  mov     [rbx+0C4h], eax
0x1401a61b1  mov     rcx, [rbx+28h]; Lock
0x1401a61b5  call    cs:__imp_NdisReleaseRWLock
0x1401a61bc  nop     dword ptr [rax+rax+00h]
0x1401a61c1  xor     r9d, r9d
0x1401a61c4  mov     [rsp+48h+var_20], 0; __int64
0x1401a61cd  lea     rdx, FlpSerializedNdisResetFiltersWorker
0x1401a61d4  mov     [rsp+48h+Timeout], 0; __int64
0x1401a61dd  mov     rcx, rbx; Context
0x1401a61e0  call    FlpSerializedNdisRequest
0x1401a61e5  mov     eax, [rbx+3D0h]
0x1401a61eb  test    al, 1
0x1401a61ed  jz      short loc_1401A6207
0x1401a61ef  mov     rax, [rbx+20h]
0x1401a61f3  mov     edx, 8
0x1401a61f8  mov     rcx, rbx
0x1401a61fb  mov     rax, [rax+278h]
0x1401a6202  call    _guard_dispatch_icall
0x1401a6207  mov     rcx, [rbx+48h]; RunRef
0x1401a620b  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401a6212  nop     dword ptr [rax+rax+00h]
0x1401a6217  cmp     byte ptr [rdi+290h], 0
0x1401a621e  jz      short loc_1401A6228
0x1401a6220  mov     rcx, rbx
0x1401a6223  call    FlpDisableVirtualInterfaceConfiguration
0x1401a6228  mov     rcx, [rbx+120h]; Entry
0x1401a622f  call    FlpDeleteInterface
0x1401a6234  mov     rcx, [rbx+120h]
0x1401a623b  call    FlpDereferenceClientInterface
0x1401a6240  mov     rcx, rbx
0x1401a6243  call    FlpFlushQueuedPmRemoveOids
0x1401a6248  mov     eax, [rbx+35Ch]
0x1401a624e  cmp     eax, 1
0x1401a6251  jz      short loc_1401A628B
0x1401a6253  or      eax, 0FFFFFFFFh
0x1401a6256  lock xadd [rbx+35Ch], eax
0x1401a625e  dec     eax
0x1401a6260  cmp     eax, 1
0x1401a6263  jz      short loc_1401A628B
0x1401a6265  xor     r9d, r9d; Alertable
0x1401a6268  mov     [rsp+48h+Timeout], 0; Timeout
0x1401a6271  lea     rcx, [rbx+360h]; Object
0x1401a6278  xor     r8d, r8d; WaitMode
0x1401a627b  lea     edx, [r9+6]; WaitReason
0x1401a627f  call    cs:__imp_KeWaitForSingleObject
0x1401a6286  nop     dword ptr [rax+rax+00h]
0x1401a628b  mov     rcx, rbx
0x1401a628e  call    FlpCleanupWolPatternEntries
0x1401a6293  mov     eax, [rbx+390h]
0x1401a6299  test    eax, eax
0x1401a629b  jz      short loc_1401A62DA
0x1401a629d  xor     edx, edx
0x1401a629f  mov     [rsp+48h+arg_10], eax
0x1401a62a3  mov     [rsp+48h+var_18], 0
0x1401a62ac  lea     rax, [rsp+48h+arg_10]
0x1401a62b1  mov     dword ptr [rsp+48h+var_20], 4
0x1401a62b9  mov     r9d, 0FD01010Bh
0x1401a62bf  mov     rcx, rbx
0x1401a62c2  mov     [rsp+48h+Timeout], rax
0x1401a62c7  lea     r8d, [rdx+1]
0x1401a62cb  call    FlpNdisRequest
0x1401a62d0  mov     dword ptr [rbx+390h], 0
0x1401a62da  mov     eax, [rbx+394h]
0x1401a62e0  test    eax, eax
0x1401a62e2  jz      short loc_1401A6321
0x1401a62e4  xor     edx, edx
0x1401a62e6  mov     [rsp+48h+arg_10], eax
0x1401a62ea  mov     [rsp+48h+var_18], 0
0x1401a62f3  lea     rax, [rsp+48h+arg_10]
0x1401a62f8  mov     dword ptr [rsp+48h+var_20], 4
0x1401a6300  mov     r9d, 0FD01010Bh
0x1401a6306  mov     rcx, rbx
0x1401a6309  mov     [rsp+48h+Timeout], rax
0x1401a630e  lea     r8d, [rdx+1]
0x1401a6312  call    FlpNdisRequest
0x1401a6317  mov     dword ptr [rbx+394h], 0
0x1401a6321  mov     rcx, rbx
0x1401a6324  call    FlpCleanupPortCoalescedWakePatterns
0x1401a6329  mov     rcx, rbx
0x1401a632c  call    FlpCleanupL2UnicastWakePatterns
0x1401a6331  mov     rcx, rbx
0x1401a6334  call    FlpTraceWakeStatistics
0x1401a6339  mov     rcx, rbx
0x1401a633c  call    FlpUninitializeProviderInterfaces
0x1401a6341  mov     rcx, [rbx+500h]; NdisBindingHandle
0x1401a6348  call    cs:__imp_NdisCloseAdapterEx
0x1401a634f  nop     dword ptr [rax+rax+00h]
0x1401a6354  mov     ecx, eax
0x1401a6356  cmp     eax, 103h
0x1401a635b  jnz     short loc_1401A6389
0x1401a635d  xor     r9d, r9d; Alertable
0x1401a6360  mov     [rsp+48h+Timeout], 0; Timeout
0x1401a6369  lea     rcx, [rbx+0A8h]; Object
0x1401a6370  xor     r8d, r8d; WaitMode
0x1401a6373  lea     edx, [r9+6]; WaitReason
0x1401a6377  call    cs:__imp_KeWaitForSingleObject
0x1401a637e  nop     dword ptr [rax+rax+00h]
0x1401a6383  mov     ecx, [rbx+0C0h]
0x1401a6389  test    ecx, ecx
0x1401a638b  js      short loc_1401A63B2
0x1401a638d  cmp     dword ptr [rbx+138h], 0Fh
0x1401a6394  jnz     short loc_1401A63EC
0x1401a6396  mov     rax, [rbx+20h]
0x1401a639a  cmp     word ptr [rax+5Ch], 17h
0x1401a639f  jnz     short loc_1401A63EC
0x1401a63a1  mov     rax, [rax+190h]
0x1401a63a8  mov     rcx, rbx
0x1401a63ab  call    _guard_dispatch_icall
0x1401a63b0  jmp     short loc_1401A63EC
0x1401a63b2  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x1401a63b9  jz      short loc_1401A63EC
0x1401a63bb  movzx   eax, word ptr [rdi+5Ch]
0x1401a63bf  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a63c6  mov     dword ptr [rsp+48h+var_18], ecx
0x1401a63ca  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a63d1  mov     dword ptr [rsp+48h+var_20], 0Ah
0x1401a63d9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a63e0  mov     r9d, esi
0x1401a63e3  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a63e7  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a63ec  lea     rcx, [rbx+440h]
0x1401a63f3  call    cs:__imp_NetioDeregisterTriageDumpDataCallback
0x1401a63fa  nop     dword ptr [rax+rax+00h]
0x1401a63ff  lea     rcx, [rdi+1B8h]
0x1401a6406  mov     rdx, rbx
0x1401a6409  call    FlpRemoveInterface
0x1401a640e  mov     rcx, rbx
0x1401a6411  call    FlpDereferenceInterface
0x1401a6416  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x1401a641d  jz      short loc_1401A6454
0x1401a641f  movzx   eax, word ptr [rdi+5Ch]
0x1401a6423  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401a642a  mov     dword ptr [rsp+48h+var_18], 0
0x1401a6432  lea     rdx, TCPIP_FRAMING_BIND_PROGRESS
0x1401a6439  mov     dword ptr [rsp+48h+var_20], 3
0x1401a6441  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401a6448  mov     r9d, esi
0x1401a644b  mov     dword ptr [rsp+48h+Timeout], eax
0x1401a644f  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401a6454  mov     rbx, [rsp+48h+arg_0]
0x1401a6459  xor     eax, eax
0x1401a645b  mov     rsi, [rsp+48h+arg_18]
0x1401a6460  add     rsp, 40h
0x1401a6464  pop     rdi
0x1401a6465  retn
```
