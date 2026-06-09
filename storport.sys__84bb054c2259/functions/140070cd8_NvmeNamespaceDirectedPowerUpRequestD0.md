# NvmeNamespaceDirectedPowerUpRequestD0

- ea: `0x140070cd8`
- end: `0x140070e96`
- name: `NvmeNamespaceDirectedPowerUpRequestD0`
- size: `446`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14013cbd0`

## callees

- `0x140033454`
- `0x14003348c`
- `0x140070cd8`
- `0x1400712a0`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140070e0b`
- `ntoskrnl!PoFxIdleComponent` at `0x140070e37`
- `ntoskrnl!PoFxIdleComponent` at `0x140070e0b`
- `ntoskrnl!PoFxIdleComponent` at `0x140070e37`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140070d08`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140070d08`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x140070e51`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x140070e51`
- `ntoskrnl!PoRequestPowerIrp` at `0x140070d6c`
- `ntoskrnl!PoRequestPowerIrp` at `0x140070d6c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070d30`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070d84`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070dbc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070d30`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070d84`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070dbc`

## pseudocode

```c
_QWORD *__fastcall NvmeNamespaceDirectedPowerUpRequestD0(char *Context)
{
  KSPIN_LOCK *v2; // rcx
  __int64 v3; // rax
  _DWORD *v4; // rcx
  _QWORD *v5; // rsi
  _QWORD *result; // rax
  __int64 v7; // rbp
  __int64 v8; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v2 = (KSPIN_LOCK *)(*((_QWORD *)Context + 16) + 88LL);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock(v2, &LockHandle);
  v3 = *((_QWORD *)Context + 16);
  v4 = (_DWORD *)(v3 + 80);
  if ( *(_DWORD *)(v3 + 72) != 1 || (*v4 & 4) != 0 )
  {
    *v4 |= 2u;
    v5 = Context + 8;
    if ( PoRequestPowerIrp(
           *((PDEVICE_OBJECT *)Context + 1),
           2u,
           (POWER_STATE)1,
           NvmeNamespaceDirectedPowerUpCompletion,
           Context,
           0) == 259 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return (_QWORD *)(unsigned int)_InterlockedExchange((volatile __int32 *)(*((_QWORD *)Context + 16) + 180LL), 0);
    }
    *(_DWORD *)(*((_QWORD *)Context + 16) + 80LL) &= ~2u;
    ++*(_DWORD *)(*((_QWORD *)Context + 16) + 168LL);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( _InterlockedCompareExchange(
           (volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)Context + 16) + 8LL) + 36LL),
           0,
           1) )
    {
      v7 = *(_QWORD *)(*((_QWORD *)Context + 2) + 128LL);
      if ( (unsigned __int8)NvmeNamespaceCheckAndAcquirePoFx(Context) )
      {
        PoFxIdleComponent(**(_QWORD **)(*((_QWORD *)Context + 16) + 8LL), 0, 0);
        NvmeNamespaceReleasePoFx(Context);
      }
      v8 = *(_QWORD *)(v7 + 168);
      if ( *(_BYTE *)v8 == 1 )
        PoFxIdleComponent(**(_QWORD **)(v8 + 8), 0, 0);
    }
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v5 = Context + 8;
  }
  PoFxReportDevicePoweredOn(**(_QWORD **)(*((_QWORD *)Context + 16) + 8LL));
  *(_BYTE *)(*(_QWORD *)(*((_QWORD *)Context + 16) + 8LL) + 41LL) = 0;
  result = (_QWORD *)(*((_QWORD *)Context + 16) + 104LL);
  if ( (_QWORD *)*result != result )
    return (_QWORD *)RaFlushDFxQueue(*v5);
  return result;
}

```

## disassembly

```asm
0x140070cd8  mov     r11, rsp
0x140070cdb  mov     [r11+8], rbp
0x140070cdf  mov     [r11+10h], rsi
0x140070ce3  push    rdi
0x140070ce4  sub     rsp, 50h
0x140070ce8  mov     rdi, rcx
0x140070ceb  lea     rdx, [r11-28h]; LockHandle
0x140070cef  mov     rcx, [rcx+80h]
0x140070cf6  xorps   xmm0, xmm0
0x140070cf9  xor     eax, eax
0x140070cfb  add     rcx, 58h ; 'X'; SpinLock
0x140070cff  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140070d04  mov     [r11-18h], rax
0x140070d08  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140070d0f  nop     dword ptr [rax+rax+00h]
0x140070d14  mov     rax, [rdi+80h]
0x140070d1b  cmp     dword ptr [rax+48h], 1
0x140070d1f  lea     rcx, [rax+50h]
0x140070d23  jnz     short loc_140070D45
0x140070d25  mov     eax, [rcx]
0x140070d27  test    al, 4
0x140070d29  jnz     short loc_140070D45
0x140070d2b  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140070d30  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070d37  nop     dword ptr [rax+rax+00h]
0x140070d3c  lea     rsi, [rdi+8]
0x140070d40  jmp     loc_140070E43
0x140070d45  or      dword ptr [rcx], 2
0x140070d48  lea     rsi, [rdi+8]
0x140070d4c  mov     rcx, [rsi]; DeviceObject
0x140070d4f  lea     r9, NvmeNamespaceDirectedPowerUpCompletion; CompletionFunction
0x140070d56  mov     [rsp+58h+Irp], 0; Irp
0x140070d5f  mov     r8d, 1; PowerState
0x140070d65  mov     dl, 2; MinorFunction
0x140070d67  mov     [rsp+58h+Context], rdi; Context
0x140070d6c  call    cs:__imp_PoRequestPowerIrp
0x140070d73  nop     dword ptr [rax+rax+00h]
0x140070d78  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140070d7d  cmp     eax, 103h
0x140070d82  jnz     short loc_140070DA4
0x140070d84  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070d8b  nop     dword ptr [rax+rax+00h]
0x140070d90  mov     rcx, [rdi+80h]
0x140070d97  xor     eax, eax
0x140070d99  xchg    eax, [rcx+0B4h]
0x140070d9f  jmp     loc_140070E85
0x140070da4  mov     rax, [rdi+80h]
0x140070dab  and     dword ptr [rax+50h], 0FFFFFFFDh
0x140070daf  mov     rax, [rdi+80h]
0x140070db6  inc     dword ptr [rax+0A8h]
0x140070dbc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070dc3  nop     dword ptr [rax+rax+00h]
0x140070dc8  mov     rax, [rdi+80h]
0x140070dcf  xor     ecx, ecx
0x140070dd1  mov     rdx, [rax+8]
0x140070dd5  lea     eax, [rcx+1]
0x140070dd8  lock cmpxchg [rdx+24h], ecx
0x140070ddd  test    eax, eax
0x140070ddf  jz      short loc_140070E43
0x140070de1  mov     rax, [rdi+10h]
0x140070de5  mov     rcx, rdi
0x140070de8  mov     rbp, [rax+80h]
0x140070def  call    NvmeNamespaceCheckAndAcquirePoFx
0x140070df4  test    al, al
0x140070df6  jz      short loc_140070E1F
0x140070df8  mov     rax, [rdi+80h]
0x140070dff  xor     r8d, r8d
0x140070e02  xor     edx, edx
0x140070e04  mov     rcx, [rax+8]
0x140070e08  mov     rcx, [rcx]
0x140070e0b  call    cs:__imp_PoFxIdleComponent
0x140070e12  nop     dword ptr [rax+rax+00h]
0x140070e17  mov     rcx, rdi
0x140070e1a  call    NvmeNamespaceReleasePoFx
0x140070e1f  mov     rcx, [rbp+0A8h]
0x140070e26  cmp     byte ptr [rcx], 1
0x140070e29  jnz     short loc_140070E43
0x140070e2b  mov     rcx, [rcx+8]
0x140070e2f  xor     r8d, r8d
0x140070e32  xor     edx, edx
0x140070e34  mov     rcx, [rcx]
0x140070e37  call    cs:__imp_PoFxIdleComponent
0x140070e3e  nop     dword ptr [rax+rax+00h]
0x140070e43  mov     rax, [rdi+80h]
0x140070e4a  mov     rcx, [rax+8]
0x140070e4e  mov     rcx, [rcx]
0x140070e51  call    cs:__imp_PoFxReportDevicePoweredOn
0x140070e58  nop     dword ptr [rax+rax+00h]
0x140070e5d  mov     rax, [rdi+80h]
0x140070e64  mov     rdx, [rax+8]
0x140070e68  xor     eax, eax
0x140070e6a  xchg    al, [rdx+29h]
0x140070e6d  mov     rax, [rdi+80h]
0x140070e74  add     rax, 68h ; 'h'
0x140070e78  cmp     [rax], rax
0x140070e7b  jz      short loc_140070E85
0x140070e7d  mov     rcx, [rsi]
0x140070e80  call    RaFlushDFxQueue
0x140070e85  mov     rbp, [rsp+58h+arg_0]
0x140070e8a  mov     rsi, [rsp+58h+arg_8]
0x140070e8f  add     rsp, 50h
0x140070e93  pop     rdi
0x140070e94  retn
```
