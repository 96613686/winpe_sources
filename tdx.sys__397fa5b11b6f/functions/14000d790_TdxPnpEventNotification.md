# TdxPnpEventNotification

- ea: `0x14000d790`
- end: `0x14000da9a`
- name: `TdxPnpEventNotification`
- size: `778`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000d790`
- `0x14000daa0`
- `0x14001570c`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000d891`
- `ntoskrnl!KeReleaseMutex` at `0x14000da0c`
- `ntoskrnl!KeReleaseMutex` at `0x14000d891`
- `ntoskrnl!KeReleaseMutex` at `0x14000da0c`
- `ntoskrnl!RtlCompareMemory` at `0x14000d850`
- `ntoskrnl!RtlCompareMemory` at `0x14000d850`
- `ntoskrnl!ExAllocatePool2` at `0x14000d900`
- `ntoskrnl!ExAllocatePool2` at `0x14000d900`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d997`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d997`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d7fa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d7fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d8a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d8a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d948`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d9c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d948`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d9c3`
- `TDI!TdiDeregisterDeviceObject` at `0x14000da89`
- `TDI!TdiDeregisterDeviceObject` at `0x14000da89`
- `TDI!TdiPnPPowerRequest` at `0x14000d981`
- `TDI!TdiPnPPowerRequest` at `0x14000d981`

## pseudocode

```c
__int64 __fastcall TdxPnpEventNotification(int *a1)
{
  int v2; // edi
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v3; // rbx
  int v4; // edi
  KIRQL v5; // al
  struct _DEVICE_OBJECT *v6; // r8
  KIRQL v7; // r14
  bool v8; // zf
  int v9; // eax
  __int16 v10; // bp
  __int64 Pool2; // rax
  TDI_PNP_CONTEXT *v12; // rsi
  _DWORD *v13; // r8
  struct _DEVICE_OBJECT *v14; // rdx
  struct _NET_PNP_EVENT *v15; // rdx
  unsigned int v16; // edi
  void *v17; // rax
  struct _DEVICE_OBJECT *v19; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // rax
  __int64 Source2; // [rsp+30h] [rbp-58h] BYREF
  TDI_PNP_CONTEXT Context2; // [rsp+38h] [rbp-50h] BYREF

  *(_QWORD *)(*((_QWORD *)a1 + 3) + 72LL) = *a1;
  *(_QWORD *)(*((_QWORD *)a1 + 3) + 80LL) = *((_QWORD *)a1 + 4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qdI(WPP_GLOBAL_Control->AttachedDevice);
  }
  KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
  v2 = *a1;
  v3 = WPP_MAIN_CB.DeviceQueue.1;
  Source2 = *((_QWORD *)a1 + 1);
  while ( 1 )
  {
    if ( *(struct _DEVICE_OBJECT **)&v3 == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
      goto LABEL_21;
    if ( *(_DWORD *)(*(_QWORD *)&v3 + 20LL) == v2
      && (*(_DWORD *)(*(_QWORD *)&v3 + 304LL) & 8) == 0
      && RtlCompareMemory((const void *)(*(_QWORD *)&v3 + 24LL), &Source2, 8u) == 8 )
    {
      break;
    }
    v3 = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&v3;
  }
  if ( !*(_QWORD *)&v3 )
  {
LABEL_21:
    KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
    return 0;
  }
  v4 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v3 + 16LL));
  KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
  v6 = *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.DeviceQueue.Type;
  v7 = v5;
  if ( *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.DeviceQueue.Type == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue )
    goto LABEL_20;
  do
  {
    v8 = v6->CurrentIrp == *(struct _IRP **)&v3;
    v9 = v4 + 1;
    v6 = *(struct _DEVICE_OBJECT **)&v6->Type;
    if ( !v8 )
      v9 = v4;
    v4 = v9;
  }
  while ( v6 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue );
  if ( v9
    && (v10 = 22 * v9 + 12,
        Pool2 = ExAllocatePool2(64, (unsigned int)(22 * v9 + 20), 544760916),
        (v12 = (TDI_PNP_CONTEXT *)Pool2) != 0) )
  {
    *(_WORD *)Pool2 = v10;
    *(_WORD *)(Pool2 + 2) = 2;
    v13 = (_DWORD *)(Pool2 + 12);
    *(_DWORD *)(Pool2 + 8) = v4;
    v14 = *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.DeviceQueue.Type;
    while ( v14 != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue )
    {
      if ( !v4 )
        break;
      v19 = v14;
      v14 = *(struct _DEVICE_OBJECT **)&v14->Type;
      if ( v19->CurrentIrp == *(struct _IRP **)&v3 )
      {
        AttachedDevice = v19->AttachedDevice;
        *v13 = 131086;
        *(_DWORD *)((char *)v13 + 6) = AttachedDevice->DriverObject;
        v13 = (_DWORD *)((char *)v13 + 22);
        --v4;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v7);
    v15 = (struct _NET_PNP_EVENT *)*((_QWORD *)a1 + 3);
    *(_QWORD *)Context2.ContextData = *((_QWORD *)a1 + 2);
    *(_DWORD *)&Context2.ContextSize = 196616;
    v16 = TdiPnPPowerRequest((PUNICODE_STRING)(*(_QWORD *)&v3 + 40LL), v15, v12, &Context2, TdxPnpPowerComplete);
    ExFreePoolWithTag(v12, 0x20786454u);
    v17 = (void *)((__int64 (__fastcall *)(_QWORD))TdxDereferenceDeviceObjectContext)(v3);
    if ( v17 )
      TdiDeregisterDeviceObject(v17);
    return v16;
  }
  else
  {
LABEL_20:
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v7);
    return 0;
  }
}

```

## disassembly

```asm
0x14000d790  push    rbx
0x14000d792  push    rsi
0x14000d793  push    rdi
0x14000d794  push    r13
0x14000d796  push    r15
0x14000d798  sub     rsp, 60h
0x14000d79c  mov     rax, cs:__security_cookie
0x14000d7a3  xor     rax, rsp
0x14000d7a6  mov     [rsp+88h+var_38], rax
0x14000d7ab  mov     rax, [rcx+18h]
0x14000d7af  mov     r15, rcx
0x14000d7b2  movsxd  rdx, dword ptr [rcx]
0x14000d7b5  mov     [rax+48h], rdx
0x14000d7b9  mov     rdx, [rcx+18h]
0x14000d7bd  mov     rax, [rcx+20h]
0x14000d7c1  mov     [rdx+50h], rax
0x14000d7c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7cc  lea     rax, WPP_GLOBAL_Control
0x14000d7d3  cmp     rcx, rax
0x14000d7d6  jz      short loc_14000D7E2
0x14000d7d8  cmp     byte ptr [rcx+29h], 3
0x14000d7dc  jnb     loc_14000DA57
0x14000d7e2  xor     r9d, r9d; Alertable
0x14000d7e5  mov     [rsp+88h+Timeout], 0; Timeout
0x14000d7ee  xor     r8d, r8d; WaitMode
0x14000d7f1  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000d7f8  xor     edx, edx; WaitReason
0x14000d7fa  call    cs:__imp_KeWaitForSingleObject
0x14000d801  nop     dword ptr [rax+rax+00h]
0x14000d806  mov     rax, [r15+8]
0x14000d80a  lea     rsi, WPP_MAIN_CB.DeviceQueue.20h
0x14000d811  mov     edi, [r15]
0x14000d814  mov     r13d, 8
0x14000d81a  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000d821  mov     [rsp+88h+Source2], rax
0x14000d826  cmp     rbx, rsi
0x14000d829  jz      loc_14000DA03
0x14000d82f  cmp     [rbx+14h], edi
0x14000d832  jnz     short loc_14000D83F
0x14000d834  mov     eax, [rbx+130h]
0x14000d83a  test    r13b, al
0x14000d83d  jz      short loc_14000D844
0x14000d83f  mov     rbx, [rbx]
0x14000d842  jmp     short loc_14000D826
0x14000d844  lea     rcx, [rbx+18h]; Source1
0x14000d848  mov     r8, r13; Length
0x14000d84b  lea     rdx, [rsp+88h+Source2]; Source2
0x14000d850  call    cs:__imp_RtlCompareMemory
0x14000d857  nop     dword ptr [rax+rax+00h]
0x14000d85c  cmp     rax, r13
0x14000d85f  jnz     short loc_14000D83F
0x14000d861  test    rbx, rbx
0x14000d864  jz      loc_14000DA03
0x14000d86a  mov     [rsp+88h+arg_10], r12
0x14000d872  xor     edi, edi
0x14000d874  mov     [rsp+88h+arg_18], r14
0x14000d87c  mov     [rsp+88h+arg_8], rbp
0x14000d884  lock inc dword ptr [rbx+10h]
0x14000d888  xor     edx, edx; Wait
0x14000d88a  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000d891  call    cs:__imp_KeReleaseMutex
0x14000d898  nop     dword ptr [rax+rax+00h]
0x14000d89d  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000d8a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d8ab  nop     dword ptr [rax+rax+00h]
0x14000d8b0  mov     r8, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x14000d8b7  lea     r12, WPP_MAIN_CB.DeviceQueue
0x14000d8be  movzx   r14d, al
0x14000d8c2  cmp     r8, r12
0x14000d8c5  jz      loc_14000D9B8
0x14000d8cb  nop     dword ptr [rax+rax+00h]
0x14000d8d0  cmp     [r8+20h], rbx
0x14000d8d4  lea     eax, [rdi+1]
0x14000d8d7  mov     r8, [r8]
0x14000d8da  cmovnz  eax, edi
0x14000d8dd  mov     edi, eax
0x14000d8df  cmp     r8, r12
0x14000d8e2  jnz     short loc_14000D8D0
0x14000d8e4  test    eax, eax
0x14000d8e6  jz      loc_14000D9B8
0x14000d8ec  imul    ebp, edi, 16h
0x14000d8ef  mov     ecx, 40h ; '@'
0x14000d8f4  mov     r8d, 20786454h
0x14000d8fa  add     ebp, 0Ch
0x14000d8fd  lea     edx, [rbp+8]
0x14000d900  call    cs:__imp_ExAllocatePool2
0x14000d907  nop     dword ptr [rax+rax+00h]
0x14000d90c  mov     rsi, rax
0x14000d90f  test    rax, rax
0x14000d912  jz      loc_14000D9B8
0x14000d918  mov     r9d, 2
0x14000d91e  mov     [rax], bp
0x14000d921  mov     [rax+2], r9w
0x14000d926  lea     r8, [rax+0Ch]
0x14000d92a  mov     [rax+8], edi
0x14000d92d  mov     rdx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x14000d934  cmp     rdx, r12
0x14000d937  jnz     loc_14000DA20
0x14000d93d  movzx   edx, r14b; NewIrql
0x14000d941  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000d948  call    cs:__imp_KeReleaseSpinLock
0x14000d94f  nop     dword ptr [rax+rax+00h]
0x14000d954  mov     rax, [r15+10h]
0x14000d958  lea     rcx, [rbx+28h]; DeviceName
0x14000d95c  mov     rdx, [r15+18h]; PowerEvent
0x14000d960  lea     r9, [rsp+88h+Context2]; Context2
0x14000d965  mov     qword ptr [rsp+88h+Context2.ContextData], rax
0x14000d96a  mov     r8, rsi; Context1
0x14000d96d  lea     rax, TdxPnpPowerComplete
0x14000d974  mov     dword ptr [rsp+88h+Context2.ContextSize], 30008h
0x14000d97c  mov     [rsp+88h+Timeout], rax; ProtocolCompletionHandler
0x14000d981  call    cs:__imp_TdiPnPPowerRequest
0x14000d988  nop     dword ptr [rax+rax+00h]
0x14000d98d  mov     edx, 20786454h; Tag
0x14000d992  mov     rcx, rsi; P
0x14000d995  mov     edi, eax
0x14000d997  call    cs:__imp_ExFreePoolWithTag
0x14000d99e  nop     dword ptr [rax+rax+00h]
0x14000d9a3  mov     rcx, rbx
0x14000d9a6  call    TdxDereferenceDeviceObjectContext
0x14000d9ab  test    rax, rax
0x14000d9ae  jnz     loc_14000DA86
0x14000d9b4  mov     eax, edi
0x14000d9b6  jmp     short loc_14000D9D1
0x14000d9b8  movzx   edx, r14b; NewIrql
0x14000d9bc  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000d9c3  call    cs:__imp_KeReleaseSpinLock
0x14000d9ca  nop     dword ptr [rax+rax+00h]
0x14000d9cf  xor     eax, eax
0x14000d9d1  mov     rbp, [rsp+88h+arg_8]
0x14000d9d9  mov     r12, [rsp+88h+arg_10]
0x14000d9e1  mov     r14, [rsp+88h+arg_18]
0x14000d9e9  mov     rcx, [rsp+88h+var_38]
0x14000d9ee  xor     rcx, rsp; StackCookie
0x14000d9f1  call    __security_check_cookie
0x14000d9f6  add     rsp, 60h
0x14000d9fa  pop     r15
0x14000d9fc  pop     r13
0x14000d9fe  pop     rdi
0x14000d9ff  pop     rsi
0x14000da00  pop     rbx
0x14000da01  retn
0x14000da03  xor     edx, edx; Wait
0x14000da05  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000da0c  call    cs:__imp_KeReleaseMutex
0x14000da13  nop     dword ptr [rax+rax+00h]
0x14000da18  xor     eax, eax
0x14000da1a  jmp     short loc_14000D9E9
0x14000da20  test    edi, edi
0x14000da22  jz      loc_14000D93D
0x14000da28  mov     rax, rdx
0x14000da2b  mov     rdx, [rdx]
0x14000da2e  cmp     [rax+20h], rbx
0x14000da32  jnz     short loc_14000DA4C
0x14000da34  mov     rax, [rax+18h]
0x14000da38  mov     dword ptr [r8], 2000Eh
0x14000da3f  mov     eax, [rax+8]
0x14000da42  mov     [r8+6], eax
0x14000da46  add     r8, 16h
0x14000da4a  dec     edi
0x14000da4c  cmp     rdx, r12
0x14000da4f  jz      loc_14000D93D
0x14000da55  jmp     short loc_14000DA20
0x14000da57  test    dword ptr [rcx+2Ch], 200h
0x14000da5e  jz      loc_14000D7E2
0x14000da64  mov     rax, [r15+8]
0x14000da68  mov     r9, [r15+18h]
0x14000da6c  mov     rcx, [rcx+18h]
0x14000da70  mov     [rsp+88h+var_60], rax
0x14000da75  mov     eax, [r9]
0x14000da78  mov     dword ptr [rsp+88h+Timeout], eax
0x14000da7c  call    WPP_SF_qdI
0x14000da81  jmp     loc_14000D7E2
0x14000da86  mov     rcx, rax; RegistrationHandle
0x14000da89  call    cs:__imp_TdiDeregisterDeviceObject
0x14000da90  nop     dword ptr [rax+rax+00h]
0x14000da95  jmp     loc_14000D9B4
```
