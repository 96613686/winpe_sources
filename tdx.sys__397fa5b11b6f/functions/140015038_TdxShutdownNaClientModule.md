# TdxShutdownNaClientModule

- ea: `0x140015038`
- end: `0x1400151c9`
- name: `TdxShutdownNaClientModule`
- size: `401`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001154c`
- `0x140014184`
- `0x1400145a0`

## callees

- `0x14000daa0`
- `0x140014ab0`
- `0x140015038`
- `0x1400182b4`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140015053`
- `ntoskrnl!KeCancelTimer` at `0x140015053`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140015063`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140015063`
- `ntoskrnl!IoFreeWorkItem` at `0x14001507d`
- `ntoskrnl!IoFreeWorkItem` at `0x14001507d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015122`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015122`
- `NETIO!NmrDeregisterClient` at `0x140015199`
- `NETIO!NmrDeregisterClient` at `0x140015199`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400151ac`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400151ac`
- `TDI!TdiDeregisterNetAddress` at `0x1400150f2`
- `TDI!TdiDeregisterNetAddress` at `0x1400150f2`
- `TDI!TdiDeregisterDeviceObject` at `0x14001510e`
- `TDI!TdiDeregisterDeviceObject` at `0x140015178`
- `TDI!TdiDeregisterDeviceObject` at `0x14001510e`
- `TDI!TdiDeregisterDeviceObject` at `0x140015178`

## pseudocode

```c
void TdxShutdownNaClientModule()
{
  __int64 v0; // rdi
  __int64 v1; // rax
  __int64 v2; // rbx
  void *v3; // rax
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  void *v7; // rax

  TdxNaDeregisterChangeHandler();
  if ( KeCancelTimer(&TdxProviderReadyContext) )
  {
    if ( qword_14001E500 )
    {
      IoFreeWorkItem(qword_14001E500);
      qword_14001E500 = 0;
    }
  }
  else
  {
    KeFlushQueuedDpcs();
  }
  if ( byte_14001E468 )
  {
    NetioShutdownWorkQueue(&WPP_MAIN_CB.Reserved + 1);
    NetioShutdownWorkQueue(&Context);
  }
  while ( 1 )
  {
    v0 = *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type;
    if ( *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.DeviceQueue.Type == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue )
      break;
    if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue
      || (v1 = **(_QWORD **)&WPP_MAIN_CB.DeviceQueue.Type,
          *(_QWORD *)(**(_QWORD **)&WPP_MAIN_CB.DeviceQueue.Type + 8LL) != *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type) )
    {
LABEL_18:
      __fastfail(3u);
    }
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = **(_QWORD **)&WPP_MAIN_CB.DeviceQueue.Type;
    *(_QWORD *)(v1 + 8) = &WPP_MAIN_CB.DeviceQueue;
    v2 = *(_QWORD *)(v0 + 32);
    TdiDeregisterNetAddress(*(HANDLE *)(v0 + 40));
    v3 = (void *)TdxDereferenceDeviceObjectContext(v2);
    if ( v3 )
      TdiDeregisterDeviceObject(v3);
    ExFreePoolWithTag((PVOID)v0, 0x6E786454u);
  }
  while ( 1 )
  {
    v4 = WPP_MAIN_CB.DeviceQueue.1;
    if ( (BOOLEAN *)WPP_MAIN_CB.DeviceQueue.32 == &WPP_MAIN_CB.DeviceQueue.Busy )
      break;
    if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
      goto LABEL_18;
    v5 = **(_QWORD **)&WPP_MAIN_CB.DeviceQueue.32;
    if ( *(_QWORD *)(**(_QWORD **)&WPP_MAIN_CB.DeviceQueue.32 + 8LL) != *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 )
      goto LABEL_18;
    WPP_MAIN_CB.DeviceQueue.1 = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&WPP_MAIN_CB.DeviceQueue.32;
    *(_QWORD *)(v5 + 8) = &WPP_MAIN_CB.DeviceQueue.1;
    v6 = *(_DWORD *)(*(_QWORD *)&v4 + 304LL);
    if ( (v6 & 8) == 0 )
    {
      *(_DWORD *)(*(_QWORD *)&v4 + 304LL) = v6 | 8;
      v7 = (void *)((__int64 (__fastcall *)(_QWORD))TdxDereferenceDeviceObjectContext)(v4);
      TdiDeregisterDeviceObject(v7);
    }
  }
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext )
  {
    NmrDeregisterClient(WPP_MAIN_CB.Queue.Wcb.DeviceContext);
    NmrWaitForClientDeregisterComplete(WPP_MAIN_CB.Queue.Wcb.DeviceContext);
  }
}

```

## disassembly

```asm
0x140015038  mov     [rsp+arg_0], rbx
0x14001503d  mov     [rsp+arg_8], rsi
0x140015042  push    rdi
0x140015043  sub     rsp, 20h
0x140015047  call    TdxNaDeregisterChangeHandler
0x14001504c  lea     rcx, TdxProviderReadyContext; PKTIMER
0x140015053  call    cs:__imp_KeCancelTimer
0x14001505a  nop     dword ptr [rax+rax+00h]
0x14001505f  test    al, al
0x140015061  jnz     short loc_140015071
0x140015063  call    cs:__imp_KeFlushQueuedDpcs
0x14001506a  nop     dword ptr [rax+rax+00h]
0x14001506f  jmp     short loc_140015094
0x140015071  mov     rcx, cs:qword_14001E500; IoWorkItem
0x140015078  test    rcx, rcx
0x14001507b  jz      short loc_140015094
0x14001507d  call    cs:__imp_IoFreeWorkItem
0x140015084  nop     dword ptr [rax+rax+00h]
0x140015089  mov     cs:qword_14001E500, 0
0x140015094  cmp     cs:byte_14001E468, 0
0x14001509b  jz      short loc_1400150B5
0x14001509d  lea     rcx, WPP_MAIN_CB+148h
0x1400150a4  call    NetioShutdownWorkQueue
0x1400150a9  lea     rcx, Context
0x1400150b0  call    NetioShutdownWorkQueue
0x1400150b5  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x1400150bc  mov     rdi, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x1400150c3  cmp     rdi, rsi
0x1400150c6  jz      short loc_140015130
0x1400150c8  cmp     [rdi+8], rsi
0x1400150cc  jnz     loc_140015186
0x1400150d2  mov     rax, [rdi]
0x1400150d5  cmp     [rax+8], rdi
0x1400150d9  jnz     loc_140015186
0x1400150df  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x1400150e6  mov     [rax+8], rsi
0x1400150ea  mov     rcx, [rdi+28h]; RegistrationHandle
0x1400150ee  mov     rbx, [rdi+20h]
0x1400150f2  call    cs:__imp_TdiDeregisterNetAddress
0x1400150f9  nop     dword ptr [rax+rax+00h]
0x1400150fe  mov     rcx, rbx
0x140015101  call    TdxDereferenceDeviceObjectContext
0x140015106  test    rax, rax
0x140015109  jz      short loc_14001511A
0x14001510b  mov     rcx, rax; RegistrationHandle
0x14001510e  call    cs:__imp_TdiDeregisterDeviceObject
0x140015115  nop     dword ptr [rax+rax+00h]
0x14001511a  mov     edx, 6E786454h; Tag
0x14001511f  mov     rcx, rdi; P
0x140015122  call    cs:__imp_ExFreePoolWithTag
0x140015129  nop     dword ptr [rax+rax+00h]
0x14001512e  jmp     short loc_1400150BC
0x140015130  lea     rbx, WPP_MAIN_CB.DeviceQueue.20h
0x140015137  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14001513e  cmp     rcx, rbx
0x140015141  jz      short loc_14001518D
0x140015143  cmp     [rcx+8], rbx
0x140015147  jnz     short loc_140015186
0x140015149  mov     rax, [rcx]
0x14001514c  cmp     [rax+8], rcx
0x140015150  jnz     short loc_140015186
0x140015152  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x140015159  mov     [rax+8], rbx
0x14001515d  mov     eax, [rcx+130h]
0x140015163  test    al, 8
0x140015165  jnz     short loc_140015137
0x140015167  or      eax, 8
0x14001516a  mov     [rcx+130h], eax
0x140015170  call    TdxDereferenceDeviceObjectContext
0x140015175  mov     rcx, rax; RegistrationHandle
0x140015178  call    cs:__imp_TdiDeregisterDeviceObject
0x14001517f  nop     dword ptr [rax+rax+00h]
0x140015184  jmp     short loc_140015137
0x140015186  mov     ecx, 3
0x14001518b  int     29h; Win8: RtlFailFast(ecx)
0x14001518d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; NmrClientHandle
0x140015194  test    rcx, rcx
0x140015197  jz      short loc_1400151B8
0x140015199  call    cs:__imp_NmrDeregisterClient
0x1400151a0  nop     dword ptr [rax+rax+00h]
0x1400151a5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; NmrClientHandle
0x1400151ac  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400151b3  nop     dword ptr [rax+rax+00h]
0x1400151b8  mov     rbx, [rsp+28h+arg_0]
0x1400151bd  mov     rsi, [rsp+28h+arg_8]
0x1400151c2  add     rsp, 20h
0x1400151c6  pop     rdi
0x1400151c7  retn
```
