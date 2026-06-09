# OncRpcConnMgrpWskDatagramSocketOpen

- ea: `0x14001f900`
- end: `0x14001fc61`
- name: `OncRpcConnMgrpWskDatagramSocketOpen`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005dc8`

## callees

- `0x1400020c0`
- `0x140005830`
- `0x140006798`
- `0x140015680`
- `0x14001f900`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001f998`
- `ntoskrnl!KeInitializeEvent` at `0x14001f998`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fa38`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fb0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fbb9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fa38`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fb0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fbb9`
- `ntoskrnl!IoReuseIrp` at `0x14001fa9b`
- `ntoskrnl!IoReuseIrp` at `0x14001fb55`
- `ntoskrnl!IoReuseIrp` at `0x14001fbfe`
- `ntoskrnl!IoReuseIrp` at `0x14001fa9b`
- `ntoskrnl!IoReuseIrp` at `0x14001fb55`
- `ntoskrnl!IoReuseIrp` at `0x14001fbfe`
- `ntoskrnl!KeClearEvent` at `0x14001faab`
- `ntoskrnl!KeClearEvent` at `0x14001fb65`
- `ntoskrnl!KeClearEvent` at `0x14001faab`
- `ntoskrnl!KeClearEvent` at `0x14001fb65`
- `NETIO!WskReleaseProviderNPI` at `0x14001fc15`
- `NETIO!WskReleaseProviderNPI` at `0x14001fc15`
- `NETIO!WskCaptureProviderNPI` at `0x14001f979`
- `NETIO!WskCaptureProviderNPI` at `0x14001f979`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskDatagramSocketOpen(__int64 a1, unsigned __int16 *a2)
{
  IRP *v2; // rdi
  NTSTATUS Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 *Information; // rax
  __int64 v8; // r15
  struct _IO_STACK_LOCATION *v9; // rax
  struct _IO_STACK_LOCATION *v10; // rax
  struct _WSK_PROVIDER_NPI WskProviderNpi; // [rsp+60h] [rbp-9h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp+7h] BYREF

  v2 = *(IRP **)(a1 + 104);
  WskProviderNpi = 0;
  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, a1);
  Status = WskCaptureProviderNPI((PWSK_REGISTRATION)DeviceExtension + 3, 0xFFFFFFFF, &WskProviderNpi);
  if ( Status >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    Status = ((__int64 (__fastcall *)(PWSK_CLIENT, _QWORD, __int64, __int64, int, __int64, __int64 (__fastcall **)(), _QWORD, _QWORD, _QWORD, IRP *))WskProviderNpi.Dispatch->WskSocket)(
               WskProviderNpi.Client,
               *a2,
               2,
               17,
               4,
               a1,
               &OncRpcConnMgrpWskDatagramSocketDispatch,
               0,
               0,
               0,
               v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v2->IoStatus.Status;
    }
    if ( Status >= 0 )
    {
      Information = (__int64 *)v2->IoStatus.Information;
      *(_QWORD *)(a1 + 96) = Information;
      v8 = *Information;
      IoReuseIrp(v2, 259);
      KeClearEvent(&Event);
      v9 = v2->Tail.Overlay.CurrentStackLocation;
      v9[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
      v9[-1].Context = &Event;
      v9[-1].Control = -32;
      Status = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, IRP *))(v8 + 16))(
                 *(_QWORD *)(a1 + 96),
                 a2,
                 0,
                 v2);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = v2->IoStatus.Status;
      }
      if ( Status < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            61,
            WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
            (unsigned int)Status);
        }
        IoReuseIrp(v2, 259);
        KeClearEvent(&Event);
        v10 = v2->Tail.Overlay.CurrentStackLocation;
        v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
        v10[-1].Context = &Event;
        v10[-1].Control = -32;
        if ( (*(unsigned int (__fastcall **)(_QWORD, IRP *))(v8 + 8))(*(_QWORD *)(a1 + 96), v2) == 259 )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            62,
            WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
            (unsigned int)Status);
        }
        *(_QWORD *)(a1 + 96) = 0;
        IoReuseIrp(v2, 259);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, *a2, Status);
    }
    WskReleaseProviderNPI((PWSK_REGISTRATION)DeviceExtension + 3);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      63,
      WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
      (unsigned int)Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001f900  push    rbp
0x14001f902  push    rbx
0x14001f903  push    rsi
0x14001f904  push    rdi
0x14001f905  push    r13
0x14001f907  push    r14
0x14001f909  push    r15
0x14001f90b  lea     rbp, [rsp-27h]
0x14001f910  sub     rsp, 90h
0x14001f917  mov     rdi, [rcx+68h]
0x14001f91b  xorps   xmm0, xmm0
0x14001f91e  xorps   xmm1, xmm1
0x14001f921  xor     eax, eax
0x14001f923  movups  xmmword ptr [rbp+57h+WskProviderNpi.Client], xmm0
0x14001f927  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14001f92b  mov     r14, rdx
0x14001f92e  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x14001f932  mov     rsi, rcx
0x14001f935  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f93c  lea     r13, WPP_GLOBAL_Control
0x14001f943  cmp     rcx, r13
0x14001f946  jz      short loc_14001F967
0x14001f948  mov     eax, [rcx+2Ch]
0x14001f94b  test    al, 1
0x14001f94d  jz      short loc_14001F967
0x14001f94f  mov     rcx, [rcx+18h]
0x14001f953  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001f95a  mov     edx, 3Bh ; ';'
0x14001f95f  mov     r9, rsi
0x14001f962  call    WPP_SF_q
0x14001f967  mov     rcx, cs:DeviceExtension
0x14001f96e  lea     r8, [rbp+57h+WskProviderNpi]; WskProviderNpi
0x14001f972  add     rcx, 48h ; 'H'; WskRegistration
0x14001f976  or      edx, 0FFFFFFFFh; WaitTimeout
0x14001f979  call    cs:__imp_WskCaptureProviderNPI
0x14001f980  nop     dword ptr [rax+rax+00h]
0x14001f985  mov     ebx, eax
0x14001f987  test    eax, eax
0x14001f989  js      loc_14001FC21
0x14001f98f  xor     r8d, r8d; State
0x14001f992  lea     rcx, [rbp+57h+Event]; Event
0x14001f996  xor     edx, edx; Type
0x14001f998  call    cs:__imp_KeInitializeEvent
0x14001f99f  nop     dword ptr [rax+rax+00h]
0x14001f9a4  mov     rax, [rdi+0B8h]
0x14001f9ab  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001f9b2  mov     [rsp+0C0h+var_70], rdi
0x14001f9b7  mov     r8d, 2
0x14001f9bd  mov     [rsp+0C0h+var_78], 0
0x14001f9c6  mov     [rsp+0C0h+var_80], 0
0x14001f9cf  mov     [rax-10h], rcx
0x14001f9d3  lea     rcx, [rbp+57h+Event]
0x14001f9d7  mov     [rax-8], rcx
0x14001f9db  lea     r9d, [r8+0Fh]
0x14001f9df  mov     byte ptr [rax-45h], 0E0h
0x14001f9e3  lea     rcx, OncRpcConnMgrpWskDatagramSocketDispatch
0x14001f9ea  mov     rax, [rbp+57h+WskProviderNpi.Dispatch]
0x14001f9ee  movzx   edx, word ptr [r14]
0x14001f9f2  mov     [rsp+0C0h+var_88], 0
0x14001f9fb  mov     [rsp+0C0h+var_90], rcx
0x14001fa00  mov     rax, [rax+8]
0x14001fa04  mov     rcx, [rbp+57h+WskProviderNpi.Client]
0x14001fa08  mov     [rsp+0C0h+var_98], rsi
0x14001fa0d  mov     dword ptr [rsp+0C0h+Timeout], 4
0x14001fa15  call    _guard_dispatch_icall
0x14001fa1a  mov     ebx, eax
0x14001fa1c  cmp     eax, 103h
0x14001fa21  jnz     short loc_14001FA47
0x14001fa23  xor     r9d, r9d; Alertable
0x14001fa26  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001fa2f  xor     r8d, r8d; WaitMode
0x14001fa32  lea     rcx, [rbp+57h+Event]; Object
0x14001fa36  xor     edx, edx; WaitReason
0x14001fa38  call    cs:__imp_KeWaitForSingleObject
0x14001fa3f  nop     dword ptr [rax+rax+00h]
0x14001fa44  mov     ebx, [rdi+30h]
0x14001fa47  test    ebx, ebx
0x14001fa49  jns     short loc_14001FA88
0x14001fa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa52  cmp     rcx, r13
0x14001fa55  jz      loc_14001FC0A
0x14001fa5b  mov     eax, [rcx+2Ch]
0x14001fa5e  test    al, 10h
0x14001fa60  jz      loc_14001FC0A
0x14001fa66  movzx   r9d, word ptr [r14]
0x14001fa6a  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fa71  mov     rcx, [rcx+18h]
0x14001fa75  mov     edx, 3Ch ; '<'
0x14001fa7a  mov     dword ptr [rsp+0C0h+Timeout], ebx
0x14001fa7e  call    WPP_SF_Dd
0x14001fa83  jmp     loc_14001FC0A
0x14001fa88  mov     rax, [rdi+38h]
0x14001fa8c  mov     edx, 103h; Iostatus
0x14001fa91  mov     [rsi+60h], rax
0x14001fa95  mov     rcx, rdi; Irp
0x14001fa98  mov     r15, [rax]
0x14001fa9b  call    cs:__imp_IoReuseIrp
0x14001faa2  nop     dword ptr [rax+rax+00h]
0x14001faa7  lea     rcx, [rbp+57h+Event]; Event
0x14001faab  call    cs:__imp_KeClearEvent
0x14001fab2  nop     dword ptr [rax+rax+00h]
0x14001fab7  mov     rax, [rdi+0B8h]
0x14001fabe  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001fac5  mov     r9, rdi
0x14001fac8  xor     r8d, r8d
0x14001facb  mov     rdx, r14
0x14001face  mov     [rax-10h], rcx
0x14001fad2  lea     rcx, [rbp+57h+Event]
0x14001fad6  mov     [rax-8], rcx
0x14001fada  mov     byte ptr [rax-45h], 0E0h
0x14001fade  mov     rax, [r15+10h]
0x14001fae2  mov     rcx, [rsi+60h]
0x14001fae6  call    _guard_dispatch_icall
0x14001faeb  mov     r14d, 103h
0x14001faf1  mov     ebx, eax
0x14001faf3  cmp     eax, r14d
0x14001faf6  jnz     short loc_14001FB1C
0x14001faf8  xor     r9d, r9d; Alertable
0x14001fafb  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001fb04  xor     r8d, r8d; WaitMode
0x14001fb07  lea     rcx, [rbp+57h+Event]; Object
0x14001fb0b  xor     edx, edx; WaitReason
0x14001fb0d  call    cs:__imp_KeWaitForSingleObject
0x14001fb14  nop     dword ptr [rax+rax+00h]
0x14001fb19  mov     ebx, [rdi+30h]
0x14001fb1c  test    ebx, ebx
0x14001fb1e  jns     loc_14001FC0A
0x14001fb24  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb2b  cmp     rcx, r13
0x14001fb2e  jz      short loc_14001FB4F
0x14001fb30  mov     eax, [rcx+2Ch]
0x14001fb33  test    al, 10h
0x14001fb35  jz      short loc_14001FB4F
0x14001fb37  mov     rcx, [rcx+18h]
0x14001fb3b  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fb42  mov     edx, 3Dh ; '='
0x14001fb47  mov     r9d, ebx
0x14001fb4a  call    WPP_SF_d
0x14001fb4f  mov     edx, r14d; Iostatus
0x14001fb52  mov     rcx, rdi; Irp
0x14001fb55  call    cs:__imp_IoReuseIrp
0x14001fb5c  nop     dword ptr [rax+rax+00h]
0x14001fb61  lea     rcx, [rbp+57h+Event]; Event
0x14001fb65  call    cs:__imp_KeClearEvent
0x14001fb6c  nop     dword ptr [rax+rax+00h]
0x14001fb71  mov     rax, [rdi+0B8h]
0x14001fb78  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001fb7f  mov     rdx, rdi
0x14001fb82  mov     [rax-10h], rcx
0x14001fb86  lea     rcx, [rbp+57h+Event]
0x14001fb8a  mov     [rax-8], rcx
0x14001fb8e  mov     byte ptr [rax-45h], 0E0h
0x14001fb92  mov     rax, [r15+8]
0x14001fb96  mov     rcx, [rsi+60h]
0x14001fb9a  call    _guard_dispatch_icall
0x14001fb9f  cmp     eax, r14d
0x14001fba2  jnz     short loc_14001FBC5
0x14001fba4  xor     r9d, r9d; Alertable
0x14001fba7  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14001fbb0  xor     r8d, r8d; WaitMode
0x14001fbb3  lea     rcx, [rbp+57h+Event]; Object
0x14001fbb7  xor     edx, edx; WaitReason
0x14001fbb9  call    cs:__imp_KeWaitForSingleObject
0x14001fbc0  nop     dword ptr [rax+rax+00h]
0x14001fbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fbcc  cmp     rcx, r13
0x14001fbcf  jz      short loc_14001FBF0
0x14001fbd1  mov     eax, [rcx+2Ch]
0x14001fbd4  test    al, 10h
0x14001fbd6  jz      short loc_14001FBF0
0x14001fbd8  mov     rcx, [rcx+18h]
0x14001fbdc  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fbe3  mov     edx, 3Eh ; '>'
0x14001fbe8  mov     r9d, ebx
0x14001fbeb  call    WPP_SF_d
0x14001fbf0  mov     edx, r14d; Iostatus
0x14001fbf3  mov     qword ptr [rsi+60h], 0
0x14001fbfb  mov     rcx, rdi; Irp
0x14001fbfe  call    cs:__imp_IoReuseIrp
0x14001fc05  nop     dword ptr [rax+rax+00h]
0x14001fc0a  mov     rcx, cs:DeviceExtension
0x14001fc11  add     rcx, 48h ; 'H'; WskRegistration
0x14001fc15  call    cs:__imp_WskReleaseProviderNPI
0x14001fc1c  nop     dword ptr [rax+rax+00h]
0x14001fc21  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc28  cmp     rcx, r13
0x14001fc2b  jz      short loc_14001FC4C
0x14001fc2d  mov     eax, [rcx+2Ch]
0x14001fc30  test    al, 1
0x14001fc32  jz      short loc_14001FC4C
0x14001fc34  mov     rcx, [rcx+18h]
0x14001fc38  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fc3f  mov     edx, 3Fh ; '?'
0x14001fc44  mov     r9d, ebx
0x14001fc47  call    WPP_SF_d
0x14001fc4c  mov     eax, ebx
0x14001fc4e  add     rsp, 90h
0x14001fc55  pop     r15
0x14001fc57  pop     r14
0x14001fc59  pop     r13
0x14001fc5b  pop     rdi
0x14001fc5c  pop     rsi
0x14001fc5d  pop     rbx
0x14001fc5e  pop     rbp
0x14001fc5f  retn
```
