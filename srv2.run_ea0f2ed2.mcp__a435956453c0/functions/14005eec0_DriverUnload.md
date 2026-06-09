# DriverUnload

- ea: `0x14005eec0`
- end: `0x14005efe4`
- name: `DriverUnload`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x14002019c`
- `0x1400235c4`
- `0x140038490`
- `0x14005da48`
- `0x14005eec0`
- `0x14005f440`
- `0x14005f8a4`
- `0x14005fdac`
- `0x140072b84`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14005efc4`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005efc4`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005eee7`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005eee7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005ef40`
- `ntoskrnl!ObfDereferenceObject` at `0x14005ef40`
- `ntoskrnl!IoDeleteDevice` at `0x14005ef8f`
- `ntoskrnl!IoDeleteDevice` at `0x14005ef8f`
- `ntoskrnl!KeStackAttachProcess` at `0x14005ef07`
- `ntoskrnl!KeStackAttachProcess` at `0x14005ef07`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14005ef28`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14005ef28`

## pseudocode

```c
NTSTATUS DriverUnload()
{
  struct _KPROCESS *CurrentProcess; // rax
  PRKPROCESS v1; // rcx
  struct _KPROCESS *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _KAPC_STATE ApcState; // [rsp+20h] [rbp-48h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  CurrentProcess = IoGetCurrentProcess();
  v1 = Srv2ServerProcess;
  v2 = CurrentProcess;
  if ( CurrentProcess != Srv2ServerProcess )
    KeStackAttachProcess(Srv2ServerProcess, &ApcState);
  LOBYTE(v1) = 1;
  Srv2ShutdownDriver(v1);
  if ( v2 != Srv2ServerProcess )
    KeUnstackDetachProcess(&ApcState);
  Srv2UnregisterPerfCounterProvider(v4, v3, v5, v6, ApcState.ApcListHead[0].Flink, ApcState.ApcListHead[0].Blink);
  ObfDereferenceObject(Srv2HighNonPagedPoolConditionEvent);
  Srv2HighNonPagedPoolConditionEvent = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids);
  }
  IoDeleteDevice((PDEVICE_OBJECT)Srv2DeviceObject);
  Srv2DeviceObject = 0;
  Srv2ServerProcess = 0;
  wil_UninitializeFeatureStaging();
  TlgUnregisterAggregateProvider();
  WppCleanupKm();
  McGenEventUnregister_EtwUnregister();
  return ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
}

```

## disassembly

```asm
0x14005eec0  push    rbx
0x14005eec2  sub     rsp, 60h
0x14005eec6  mov     rax, cs:__security_cookie
0x14005eecd  xor     rax, rsp
0x14005eed0  mov     [rsp+68h+var_18], rax
0x14005eed5  xorps   xmm0, xmm0
0x14005eed8  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink], xmm0
0x14005eedd  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink+10h], xmm0
0x14005eee2  movups  xmmword ptr [rsp+68h+ApcState.Process], xmm0
0x14005eee7  call    cs:__imp_IoGetCurrentProcess
0x14005eeee  nop     dword ptr [rax+rax+00h]
0x14005eef3  mov     rcx, cs:Srv2ServerProcess; PROCESS
0x14005eefa  mov     rbx, rax
0x14005eefd  cmp     rax, rcx
0x14005ef00  jz      short loc_14005EF13
0x14005ef02  lea     rdx, [rsp+68h+ApcState]; ApcState
0x14005ef07  call    cs:__imp_KeStackAttachProcess
0x14005ef0e  nop     dword ptr [rax+rax+00h]
0x14005ef13  mov     cl, 1
0x14005ef15  call    Srv2ShutdownDriver
0x14005ef1a  cmp     rbx, cs:Srv2ServerProcess
0x14005ef21  jz      short loc_14005EF34
0x14005ef23  lea     rcx, [rsp+68h+ApcState]; ApcState
0x14005ef28  call    cs:__imp_KeUnstackDetachProcess
0x14005ef2f  nop     dword ptr [rax+rax+00h]
0x14005ef34  call    Srv2UnregisterPerfCounterProvider
0x14005ef39  mov     rcx, cs:Srv2HighNonPagedPoolConditionEvent; Object
0x14005ef40  call    cs:__imp_ObfDereferenceObject
0x14005ef47  nop     dword ptr [rax+rax+00h]
0x14005ef4c  xor     ebx, ebx
0x14005ef4e  mov     cs:Srv2HighNonPagedPoolConditionEvent, rbx
0x14005ef55  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ef5c  lea     rax, WPP_GLOBAL_Control
0x14005ef63  cmp     rcx, rax
0x14005ef66  jz      short loc_14005EF88
0x14005ef68  mov     eax, [rcx+2Ch]
0x14005ef6b  test    al, 8
0x14005ef6d  jz      short loc_14005EF88
0x14005ef6f  cmp     byte ptr [rcx+29h], 2
0x14005ef73  jb      short loc_14005EF88
0x14005ef75  mov     rcx, [rcx+18h]
0x14005ef79  lea     edx, [rbx+1Ah]
0x14005ef7c  lea     r8, WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids
0x14005ef83  call    WPP_SF_
0x14005ef88  mov     rcx, cs:Srv2DeviceObject; DeviceObject
0x14005ef8f  call    cs:__imp_IoDeleteDevice
0x14005ef96  nop     dword ptr [rax+rax+00h]
0x14005ef9b  mov     cs:Srv2DeviceObject, rbx
0x14005efa2  mov     cs:Srv2ServerProcess, rbx
0x14005efa9  call    wil_UninitializeFeatureStaging
0x14005efae  call    TlgUnregisterAggregateProvider
0x14005efb3  call    WppCleanupKm
0x14005efb8  call    McGenEventUnregister_EtwUnregister
0x14005efbd  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Resource
0x14005efc4  call    cs:__imp_ExDeleteResourceLite
0x14005efcb  nop     dword ptr [rax+rax+00h]
0x14005efd0  mov     rcx, [rsp+68h+var_18]
0x14005efd5  xor     rcx, rsp; StackCookie
0x14005efd8  call    __security_check_cookie
0x14005efdd  add     rsp, 60h
0x14005efe1  pop     rbx
0x14005efe2  retn
```
