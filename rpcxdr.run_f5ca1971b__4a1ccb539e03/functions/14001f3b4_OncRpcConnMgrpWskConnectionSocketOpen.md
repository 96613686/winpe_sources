# OncRpcConnMgrpWskConnectionSocketOpen

- ea: `0x14001f3b4`
- end: `0x14001f8f8`
- name: `OncRpcConnMgrpWskConnectionSocketOpen`
- size: `1348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140007394`

## callees

- `0x1400020c0`
- `0x14000dc1c`
- `0x140015680`
- `0x14001f3b4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001f436`
- `ntoskrnl!KeInitializeEvent` at `0x14001f436`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f4c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f5de`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f69e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f75e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f836`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f4c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f5de`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f69e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f75e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f836`
- `ntoskrnl!IoReuseIrp` at `0x14001f534`
- `ntoskrnl!IoReuseIrp` at `0x14001f62b`
- `ntoskrnl!IoReuseIrp` at `0x14001f6eb`
- `ntoskrnl!IoReuseIrp` at `0x14001f7ab`
- `ntoskrnl!IoReuseIrp` at `0x14001f885`
- `ntoskrnl!IoReuseIrp` at `0x14001f534`
- `ntoskrnl!IoReuseIrp` at `0x14001f62b`
- `ntoskrnl!IoReuseIrp` at `0x14001f6eb`
- `ntoskrnl!IoReuseIrp` at `0x14001f7ab`
- `ntoskrnl!IoReuseIrp` at `0x14001f885`
- `ntoskrnl!KeClearEvent` at `0x14001f54c`
- `ntoskrnl!KeClearEvent` at `0x14001f643`
- `ntoskrnl!KeClearEvent` at `0x14001f703`
- `ntoskrnl!KeClearEvent` at `0x14001f7e0`
- `ntoskrnl!KeClearEvent` at `0x14001f54c`
- `ntoskrnl!KeClearEvent` at `0x14001f643`
- `ntoskrnl!KeClearEvent` at `0x14001f703`
- `ntoskrnl!KeClearEvent` at `0x14001f7e0`
- `NETIO!WskReleaseProviderNPI` at `0x14001f89c`
- `NETIO!WskReleaseProviderNPI` at `0x14001f89c`
- `NETIO!WskCaptureProviderNPI` at `0x14001f410`
- `NETIO!WskCaptureProviderNPI` at `0x14001f410`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskConnectionSocketOpen(_QWORD *a1, unsigned __int16 *a2, __int64 a3)
{
  IRP *v3; // rdi
  char v6; // r15
  NTSTATUS Status; // ebx
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v10; // r14
  _QWORD *v11; // rsi
  __int64 *Information; // rax
  struct _IO_STACK_LOCATION *v13; // rax
  __int64 v14; // rcx
  struct _IO_STACK_LOCATION *v15; // rax
  unsigned __int16 *v16; // rdx
  struct _IO_STACK_LOCATION *v17; // rax
  __int64 v18; // rdx
  struct _IO_STACK_LOCATION *v19; // rax
  struct _WSK_PROVIDER_NPI WskProviderNpi; // [rsp+68h] [rbp-9h] BYREF
  struct _KEVENT Event; // [rsp+78h] [rbp+7h] BYREF
  int v23; // [rsp+D8h] [rbp+67h] BYREF
  unsigned __int16 *v24; // [rsp+E0h] [rbp+6Fh]
  __int64 v25; // [rsp+E8h] [rbp+77h]

  v25 = a3;
  v24 = a2;
  v3 = (IRP *)a1[28];
  v6 = 0;
  v23 = 0;
  memset(&Event, 0, sizeof(Event));
  WskProviderNpi = 0;
  Status = WskCaptureProviderNPI((PWSK_REGISTRATION)DeviceExtension + 3, 0xFFFFFFFF, &WskProviderNpi);
  if ( Status >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&v3->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    Status = ((__int64 (__fastcall *)(PWSK_CLIENT, _QWORD, __int64, __int64, int, _QWORD *, __int64 (__fastcall **)(int, int, int, int, __int64), _QWORD, _QWORD, _QWORD, IRP *))WskProviderNpi.Dispatch->WskSocket)(
               WskProviderNpi.Client,
               *a2,
               1,
               6,
               2,
               a1,
               &OncRpcConnMgrpWskConnectionSocketDispatch,
               0,
               0,
               0,
               v3);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v3->IoStatus.Status;
    }
    if ( Status >= 0 )
    {
      Information = (__int64 *)v3->IoStatus.Information;
      v11 = a1 + 27;
      a1[27] = Information;
      v6 = 1;
      v10 = *Information;
    }
    else
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          66,
          WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
          (unsigned int)Status);
      v11 = a1 + 27;
    }
    IoReuseIrp(v3, 259);
    if ( Status < 0 )
      goto LABEL_34;
    KeClearEvent(&Event);
    v13 = p_CurrentStackLocation->CurrentStackLocation;
    v11 = a1 + 27;
    v13[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    v13[-1].Context = &Event;
    v13[-1].Control = -32;
    v14 = a1[27];
    v23 = 1;
    Status = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, int *, _QWORD, _QWORD, _QWORD, IRP *))v10)(
               v14,
               0,
               8,
               0xFFFF,
               4,
               &v23,
               0,
               0,
               0,
               v3);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v3->IoStatus.Status;
    }
    if ( Status < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        67,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)Status);
    }
    IoReuseIrp(v3, 259);
    if ( Status < 0 )
      goto LABEL_34;
    KeClearEvent(&Event);
    v15 = p_CurrentStackLocation->CurrentStackLocation;
    v16 = v24;
    v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    v15[-1].Context = &Event;
    v15[-1].Control = -32;
    Status = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, IRP *))(v10 + 16))(*v11, v16, 0, v3);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v3->IoStatus.Status;
    }
    if ( Status < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        68,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)Status);
    }
    IoReuseIrp(v3, 259);
    if ( Status < 0 )
      goto LABEL_34;
    KeClearEvent(&Event);
    v17 = p_CurrentStackLocation->CurrentStackLocation;
    v18 = v25;
    v17[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    v17[-1].Context = &Event;
    v17[-1].Control = -32;
    Status = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, IRP *))(v10 + 24))(*v11, v18, 0, v3);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v3->IoStatus.Status;
    }
    if ( Status < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        69,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)Status);
    }
    IoReuseIrp(v3, 259);
    if ( Status < 0 )
    {
LABEL_34:
      if ( v6 )
      {
        KeClearEvent(&Event);
        v19 = p_CurrentStackLocation->CurrentStackLocation;
        v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
        v19[-1].Context = &Event;
        v19[-1].Control = -32;
        if ( (*(unsigned int (__fastcall **)(_QWORD, IRP *))(v10 + 8))(*v11, v3) == 259 )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            70,
            WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
            (unsigned int)Status);
        }
        *v11 = 0;
        IoReuseIrp(v3, 259);
      }
    }
    else if ( a1[14] )
    {
      OncRpcConnMgrpWskEnableEvent(*v11);
    }
    WskReleaseProviderNPI((PWSK_REGISTRATION)DeviceExtension + 3);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      71,
      WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
      (unsigned int)Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001f3b4  mov     rax, rsp
0x14001f3b7  mov     [rax+20h], rbx
0x14001f3bb  mov     [rax+18h], r8
0x14001f3bf  mov     [rax+10h], rdx
0x14001f3c3  push    rbp
0x14001f3c4  push    rsi
0x14001f3c5  push    rdi
0x14001f3c6  push    r12
0x14001f3c8  push    r13
0x14001f3ca  push    r14
0x14001f3cc  push    r15
0x14001f3ce  lea     rbp, [rax-5Fh]
0x14001f3d2  sub     rsp, 90h
0x14001f3d9  mov     rdi, [rcx+0E0h]
0x14001f3e0  lea     r8, [rbp+57h+WskProviderNpi]; WskProviderNpi
0x14001f3e4  mov     r13, rcx
0x14001f3e7  xorps   xmm0, xmm0
0x14001f3ea  mov     rcx, cs:DeviceExtension
0x14001f3f1  mov     rsi, rdx
0x14001f3f4  xor     eax, eax
0x14001f3f6  xor     r15d, r15d
0x14001f3f9  add     rcx, 48h ; 'H'; WskRegistration
0x14001f3fd  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14001f401  or      edx, 0FFFFFFFFh; WaitTimeout
0x14001f404  mov     [rbp+57h+arg_0], r15d
0x14001f408  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14001f40c  movups  xmmword ptr [rbp+57h+WskProviderNpi.Client], xmm0
0x14001f410  call    cs:__imp_WskCaptureProviderNPI
0x14001f417  nop     dword ptr [rax+rax+00h]
0x14001f41c  mov     ebx, eax
0x14001f41e  lea     rax, WPP_GLOBAL_Control
0x14001f425  test    ebx, ebx
0x14001f427  js      loc_14001F8AF
0x14001f42d  xor     r8d, r8d; State
0x14001f430  lea     rcx, [rbp+57h+Event]; Event
0x14001f434  xor     edx, edx; Type
0x14001f436  call    cs:__imp_KeInitializeEvent
0x14001f43d  nop     dword ptr [rax+rax+00h]
0x14001f442  mov     [rsp+50h], rdi
0x14001f447  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001f44e  mov     [rsp+0C0h+var_78], r15
0x14001f453  lea     r12, [rdi+0B8h]
0x14001f45a  mov     rax, [r12]
0x14001f45e  lea     r8d, [r15+1]
0x14001f462  mov     [rsp+0C0h+var_80], r15
0x14001f467  lea     r9d, [r15+6]
0x14001f46b  mov     [rsp+0C0h+var_88], r15
0x14001f470  mov     [rax-10h], rcx
0x14001f474  lea     rcx, [rbp+57h+Event]
0x14001f478  mov     [rax-8], rcx
0x14001f47c  lea     rcx, OncRpcConnMgrpWskConnectionSocketDispatch
0x14001f483  mov     byte ptr [rax-45h], 0E0h
0x14001f487  mov     rax, [rbp+57h+WskProviderNpi.Dispatch]
0x14001f48b  movzx   edx, word ptr [rsi]
0x14001f48e  mov     [rsp+0C0h+var_90], rcx
0x14001f493  mov     rcx, [rbp+57h+WskProviderNpi.Client]
0x14001f497  mov     rax, [rax+8]
0x14001f49b  mov     [rsp+0C0h+var_98], r13
0x14001f4a0  mov     dword ptr [rsp+0C0h+Timeout], 2
0x14001f4a8  call    _guard_dispatch_icall
0x14001f4ad  mov     ebx, eax
0x14001f4af  cmp     eax, 103h
0x14001f4b4  jnz     short loc_14001F4D6
0x14001f4b6  xor     r9d, r9d; Alertable
0x14001f4b9  mov     [rsp+0C0h+Timeout], r15; Timeout
0x14001f4be  xor     r8d, r8d; WaitMode
0x14001f4c1  lea     rcx, [rbp+57h+Event]; Object
0x14001f4c5  xor     edx, edx; WaitReason
0x14001f4c7  call    cs:__imp_KeWaitForSingleObject
0x14001f4ce  nop     dword ptr [rax+rax+00h]
0x14001f4d3  mov     ebx, [rdi+30h]
0x14001f4d6  test    ebx, ebx
0x14001f4d8  jns     short loc_14001F518
0x14001f4da  mov     r14, r15
0x14001f4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f4e4  lea     rax, WPP_GLOBAL_Control
0x14001f4eb  cmp     rcx, rax
0x14001f4ee  jz      short loc_14001F50F
0x14001f4f0  mov     eax, [rcx+2Ch]
0x14001f4f3  test    al, 10h
0x14001f4f5  jz      short loc_14001F50F
0x14001f4f7  mov     rcx, [rcx+18h]
0x14001f4fb  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001f502  mov     edx, 42h ; 'B'
0x14001f507  mov     r9d, ebx
0x14001f50a  call    WPP_SF_d
0x14001f50f  lea     rsi, [r13+0D8h]
0x14001f516  jmp     short loc_14001F52C
0x14001f518  mov     rax, [rdi+38h]
0x14001f51c  lea     rsi, [r13+0D8h]
0x14001f523  mov     [rsi], rax
0x14001f526  mov     r15b, 1
0x14001f529  mov     r14, [rax]
0x14001f52c  mov     edx, 103h; Iostatus
0x14001f531  mov     rcx, rdi; Irp
0x14001f534  call    cs:__imp_IoReuseIrp
0x14001f53b  nop     dword ptr [rax+rax+00h]
0x14001f540  test    ebx, ebx
0x14001f542  js      loc_14001F7D3
0x14001f548  lea     rcx, [rbp+57h+Event]; Event
0x14001f54c  call    cs:__imp_KeClearEvent
0x14001f553  nop     dword ptr [rax+rax+00h]
0x14001f558  mov     rax, [r12]
0x14001f55c  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001f563  mov     [rsp+0C0h+var_78], rdi
0x14001f568  lea     rsi, [r13+0D8h]
0x14001f56f  xor     edx, edx
0x14001f571  mov     r9d, 0FFFFh
0x14001f577  mov     [rax-10h], rcx
0x14001f57b  lea     rcx, [rbp+57h+Event]
0x14001f57f  mov     [rax-8], rcx
0x14001f583  xor     ecx, ecx
0x14001f585  mov     [rsp+0C0h+var_80], rcx
0x14001f58a  lea     r8d, [rdx+8]
0x14001f58e  mov     [rsp+0C0h+var_88], rcx
0x14001f593  mov     [rsp+0C0h+var_90], rcx
0x14001f598  lea     rcx, [rbp+57h+arg_0]
0x14001f59c  mov     byte ptr [rax-45h], 0E0h
0x14001f5a0  mov     [rsp+0C0h+var_98], rcx
0x14001f5a5  mov     rcx, [rsi]
0x14001f5a8  mov     [rbp+57h+arg_0], 1
0x14001f5af  mov     rax, [r14]
0x14001f5b2  mov     [rsp+0C0h+Timeout], 4
0x14001f5bb  call    _guard_dispatch_icall
0x14001f5c0  mov     ebx, eax
0x14001f5c2  cmp     eax, 103h
0x14001f5c7  jnz     short loc_14001F5ED
0x14001f5c9  xor     r9d, r9d; Alertable
0x14001f5cc  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001f5d5  xor     r8d, r8d; WaitMode
0x14001f5d8  lea     rcx, [rbp+57h+Event]; Object
0x14001f5dc  xor     edx, edx; WaitReason
0x14001f5de  call    cs:__imp_KeWaitForSingleObject
0x14001f5e5  nop     dword ptr [rax+rax+00h]
0x14001f5ea  mov     ebx, [rdi+30h]
0x14001f5ed  test    ebx, ebx
0x14001f5ef  jns     short loc_14001F623
0x14001f5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5f8  lea     rax, WPP_GLOBAL_Control
0x14001f5ff  cmp     rcx, rax
0x14001f602  jz      short loc_14001F623
0x14001f604  mov     eax, [rcx+2Ch]
0x14001f607  test    al, 10h
0x14001f609  jz      short loc_14001F623
0x14001f60b  mov     rcx, [rcx+18h]
0x14001f60f  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001f616  mov     edx, 43h ; 'C'
0x14001f61b  mov     r9d, ebx
0x14001f61e  call    WPP_SF_d
0x14001f623  mov     edx, 103h; Iostatus
0x14001f628  mov     rcx, rdi; Irp
0x14001f62b  call    cs:__imp_IoReuseIrp
0x14001f632  nop     dword ptr [rax+rax+00h]
0x14001f637  test    ebx, ebx
0x14001f639  js      loc_14001F7D3
0x14001f63f  lea     rcx, [rbp+57h+Event]; Event
0x14001f643  call    cs:__imp_KeClearEvent
0x14001f64a  nop     dword ptr [rax+rax+00h]
0x14001f64f  mov     rax, [r12]
0x14001f653  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001f65a  mov     rdx, [rbp+57h+arg_8]
0x14001f65e  mov     r9, rdi
0x14001f661  xor     r8d, r8d
0x14001f664  mov     [rax-10h], rcx
0x14001f668  lea     rcx, [rbp+57h+Event]
0x14001f66c  mov     [rax-8], rcx
0x14001f670  mov     byte ptr [rax-45h], 0E0h
0x14001f674  mov     rax, [r14+10h]
0x14001f678  mov     rcx, [rsi]
0x14001f67b  call    _guard_dispatch_icall
0x14001f680  mov     ebx, eax
0x14001f682  cmp     eax, 103h
0x14001f687  jnz     short loc_14001F6AD
0x14001f689  xor     r9d, r9d; Alertable
0x14001f68c  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001f695  xor     r8d, r8d; WaitMode
0x14001f698  lea     rcx, [rbp+57h+Event]; Object
0x14001f69c  xor     edx, edx; WaitReason
0x14001f69e  call    cs:__imp_KeWaitForSingleObject
0x14001f6a5  nop     dword ptr [rax+rax+00h]
0x14001f6aa  mov     ebx, [rdi+30h]
0x14001f6ad  test    ebx, ebx
0x14001f6af  jns     short loc_14001F6E3
0x14001f6b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6b8  lea     rax, WPP_GLOBAL_Control
0x14001f6bf  cmp     rcx, rax
0x14001f6c2  jz      short loc_14001F6E3
0x14001f6c4  mov     eax, [rcx+2Ch]
0x14001f6c7  test    al, 10h
0x14001f6c9  jz      short loc_14001F6E3
0x14001f6cb  mov     rcx, [rcx+18h]
0x14001f6cf  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001f6d6  mov     edx, 44h ; 'D'
0x14001f6db  mov     r9d, ebx
0x14001f6de  call    WPP_SF_d
0x14001f6e3  mov     edx, 103h; Iostatus
0x14001f6e8  mov     rcx, rdi; Irp
0x14001f6eb  call    cs:__imp_IoReuseIrp
0x14001f6f2  nop     dword ptr [rax+rax+00h]
0x14001f6f7  test    ebx, ebx
0x14001f6f9  js      loc_14001F7D3
0x14001f6ff  lea     rcx, [rbp+57h+Event]; Event
0x14001f703  call    cs:__imp_KeClearEvent
0x14001f70a  nop     dword ptr [rax+rax+00h]
0x14001f70f  mov     rax, [r12]
0x14001f713  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001f71a  mov     rdx, [rbp+57h+arg_10]
0x14001f71e  mov     r9, rdi
0x14001f721  xor     r8d, r8d
0x14001f724  mov     [rax-10h], rcx
0x14001f728  lea     rcx, [rbp+57h+Event]
0x14001f72c  mov     [rax-8], rcx
0x14001f730  mov     byte ptr [rax-45h], 0E0h
0x14001f734  mov     rax, [r14+18h]
0x14001f738  mov     rcx, [rsi]
0x14001f73b  call    _guard_dispatch_icall
0x14001f740  mov     ebx, eax
0x14001f742  cmp     eax, 103h
0x14001f747  jnz     short loc_14001F76D
0x14001f749  xor     r9d, r9d; Alertable
0x14001f74c  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001f755  xor     r8d, r8d; WaitMode
0x14001f758  lea     rcx, [rbp+57h+Event]; Object
0x14001f75c  xor     edx, edx; WaitReason
0x14001f75e  call    cs:__imp_KeWaitForSingleObject
0x14001f765  nop     dword ptr [rax+rax+00h]
0x14001f76a  mov     ebx, [rdi+30h]
0x14001f76d  test    ebx, ebx
0x14001f76f  jns     short loc_14001F7A3
0x14001f771  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f778  lea     rax, WPP_GLOBAL_Control
0x14001f77f  cmp     rcx, rax
0x14001f782  jz      short loc_14001F7A3
0x14001f784  mov     eax, [rcx+2Ch]
0x14001f787  test    al, 10h
0x14001f789  jz      short loc_14001F7A3
0x14001f78b  mov     rcx, [rcx+18h]
0x14001f78f  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001f796  mov     edx, 45h ; 'E'
0x14001f79b  mov     r9d, ebx
0x14001f79e  call    WPP_SF_d
0x14001f7a3  mov     edx, 103h; Iostatus
0x14001f7a8  mov     rcx, rdi; Irp
0x14001f7ab  call    cs:__imp_IoReuseIrp
0x14001f7b2  nop     dword ptr [rax+rax+00h]
0x14001f7b7  test    ebx, ebx
0x14001f7b9  js      short loc_14001F7D3
0x14001f7bb  cmp     qword ptr [r13+70h], 0
0x14001f7c0  jz      loc_14001F891
0x14001f7c6  mov     rcx, [rsi]
0x14001f7c9  call    OncRpcConnMgrpWskEnableEvent
0x14001f7ce  jmp     loc_14001F891
0x14001f7d3  test    r15b, r15b
0x14001f7d6  jz      loc_14001F891
0x14001f7dc  lea     rcx, [rbp+57h+Event]; Event
0x14001f7e0  call    cs:__imp_KeClearEvent
0x14001f7e7  nop     dword ptr [rax+rax+00h]
0x14001f7ec  mov     rax, [r12]
0x14001f7f0  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001f7f7  mov     rdx, rdi
0x14001f7fa  mov     [rax-10h], rcx
0x14001f7fe  lea     rcx, [rbp+57h+Event]
0x14001f802  mov     [rax-8], rcx
0x14001f806  mov     byte ptr [rax-45h], 0E0h
0x14001f80a  mov     rax, [r14+8]
0x14001f80e  mov     rcx, [rsi]
0x14001f811  call    _guard_dispatch_icall
0x14001f816  mov     r14d, 103h
0x14001f81c  cmp     eax, r14d
0x14001f81f  jnz     short loc_14001F842
0x14001f821  xor     r9d, r9d; Alertable
0x14001f824  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001f82d  xor     r8d, r8d; WaitMode
0x14001f830  lea     rcx, [rbp+57h+Event]; Object
0x14001f834  xor     edx, edx; WaitReason
0x14001f836  call    cs:__imp_KeWaitForSingleObject
0x14001f83d  nop     dword ptr [rax+rax+00h]
0x14001f842  test    ebx, ebx
0x14001f844  jns     short loc_14001F878
0x14001f846  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f84d  lea     rax, WPP_GLOBAL_Control
0x14001f854  cmp     rcx, rax
0x14001f857  jz      short loc_14001F878
0x14001f859  mov     eax, [rcx+2Ch]
0x14001f85c  test    al, 10h
0x14001f85e  jz      short loc_14001F878
0x14001f860  mov     rcx, [rcx+18h]
0x14001f864  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001f86b  mov     edx, 46h ; 'F'
0x14001f870  mov     r9d, ebx
0x14001f873  call    WPP_SF_d
0x14001f878  mov     edx, r14d; Iostatus
0x14001f87b  mov     qword ptr [rsi], 0
0x14001f882  mov     rcx, rdi; Irp
0x14001f885  call    cs:__imp_IoReuseIrp
0x14001f88c  nop     dword ptr [rax+rax+00h]
0x14001f891  mov     rcx, cs:DeviceExtension
0x14001f898  add     rcx, 48h ; 'H'; WskRegistration
0x14001f89c  call    cs:__imp_WskReleaseProviderNPI
0x14001f8a3  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
