# OncRpcConnMgrpWskListeningSocketOpen

- ea: `0x14001fc68`
- end: `0x1400201d4`
- name: `OncRpcConnMgrpWskListeningSocketOpen`
- size: `1388`
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
- `0x14001fc68`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001fcdd`
- `ntoskrnl!KeInitializeEvent` at `0x14001fcdd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fd92`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001feaa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ff98`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020057`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002011a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fd92`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001feaa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ff98`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020057`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002011a`
- `ntoskrnl!IoReuseIrp` at `0x14001fdfa`
- `ntoskrnl!IoReuseIrp` at `0x14001fef7`
- `ntoskrnl!IoReuseIrp` at `0x14001ffe5`
- `ntoskrnl!IoReuseIrp` at `0x1400200a4`
- `ntoskrnl!IoReuseIrp` at `0x140020168`
- `ntoskrnl!IoReuseIrp` at `0x14001fdfa`
- `ntoskrnl!IoReuseIrp` at `0x14001fef7`
- `ntoskrnl!IoReuseIrp` at `0x14001ffe5`
- `ntoskrnl!IoReuseIrp` at `0x1400200a4`
- `ntoskrnl!IoReuseIrp` at `0x140020168`
- `ntoskrnl!KeClearEvent` at `0x14001fe1f`
- `ntoskrnl!KeClearEvent` at `0x14001ff0f`
- `ntoskrnl!KeClearEvent` at `0x14001fffd`
- `ntoskrnl!KeClearEvent` at `0x1400200c5`
- `ntoskrnl!KeClearEvent` at `0x14001fe1f`
- `ntoskrnl!KeClearEvent` at `0x14001ff0f`
- `ntoskrnl!KeClearEvent` at `0x14001fffd`
- `ntoskrnl!KeClearEvent` at `0x1400200c5`
- `NETIO!WskReleaseProviderNPI` at `0x14002017f`
- `NETIO!WskReleaseProviderNPI` at `0x14002017f`
- `NETIO!WskCaptureProviderNPI` at `0x14001fcfb`
- `NETIO!WskCaptureProviderNPI` at `0x14001fcfb`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskListeningSocketOpen(_QWORD *a1, unsigned __int16 *a2)
{
  IRP *v2; // rdi
  NTSTATUS Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v7; // r14
  char v8; // r12
  __int64 *Information; // rax
  struct _IO_STACK_LOCATION *v10; // rax
  __int64 v11; // rcx
  struct _IO_STACK_LOCATION *v12; // rax
  __int64 v13; // rcx
  struct _IO_STACK_LOCATION *v14; // rax
  struct _IO_STACK_LOCATION *v15; // rax
  int v16; // eax
  struct _WSK_PROVIDER_NPI WskProviderNpi; // [rsp+60h] [rbp-19h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-9h] BYREF
  int v20; // [rsp+E0h] [rbp+67h] BYREF

  v2 = (IRP *)a1[13];
  v20 = 0;
  memset(&Event, 0, sizeof(Event));
  WskProviderNpi = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, a1);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Status = WskCaptureProviderNPI((PWSK_REGISTRATION)DeviceExtension + 3, 0xFFFFFFFF, &WskProviderNpi);
  if ( Status >= 0 )
  {
    CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    Status = ((__int64 (__fastcall *)(PWSK_CLIENT, _QWORD, __int64, __int64, int, _QWORD *, __int64 (__fastcall **)(int, int, int, int, __int64, __int64, __int64), _QWORD, _QWORD, _QWORD, IRP *))WskProviderNpi.Dispatch->WskSocket)(
               WskProviderNpi.Client,
               *a2,
               1,
               6,
               1,
               a1,
               &OncRpcConnMgrpWskListenSocketDispatch,
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
      v8 = 1;
      a1[12] = Information;
      v7 = *Information;
    }
    else
    {
      v7 = 0;
      v8 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, *a2, Status);
    }
    IoReuseIrp(v2, 259);
    if ( Status < 0 )
      goto LABEL_35;
    if ( a1[24] )
    {
      KeClearEvent(&Event);
      v10 = v2->Tail.Overlay.CurrentStackLocation;
      v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
      v10[-1].Context = &Event;
      v10[-1].Control = -32;
      v11 = a1[12];
      v20 = 1;
      Status = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, int *, _QWORD, _QWORD, _QWORD, IRP *))v7)(
                 v11,
                 0,
                 12290,
                 0xFFFF,
                 4,
                 &v20,
                 0,
                 0,
                 0,
                 v2);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = v2->IoStatus.Status;
      }
      if ( Status < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          54,
          WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
          (unsigned int)Status);
      }
      IoReuseIrp(v2, 259);
      if ( Status < 0 )
        goto LABEL_35;
    }
    KeClearEvent(&Event);
    v12 = v2->Tail.Overlay.CurrentStackLocation;
    v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    v12[-1].Context = &Event;
    v12[-1].Control = -32;
    v13 = a1[12];
    v20 = 1;
    Status = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, int *, _QWORD, _QWORD, _QWORD, IRP *))v7)(
               v13,
               0,
               8,
               0xFFFF,
               4,
               &v20,
               0,
               0,
               0,
               v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v2->IoStatus.Status;
    }
    if ( Status < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)Status);
    }
    IoReuseIrp(v2, 259);
    if ( Status < 0 )
      goto LABEL_35;
    KeClearEvent(&Event);
    v14 = v2->Tail.Overlay.CurrentStackLocation;
    v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
    v14[-1].Context = &Event;
    v14[-1].Control = -32;
    Status = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, IRP *))(v7 + 16))(a1[12], a2, 0, v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v2->IoStatus.Status;
    }
    if ( Status < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        56,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)Status);
    }
    IoReuseIrp(v2, 259);
    if ( Status < 0 )
    {
LABEL_35:
      if ( v8 )
      {
        KeClearEvent(&Event);
        v15 = v2->Tail.Overlay.CurrentStackLocation;
        v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&OncRpcConnMgrpWskSynchronousIrpCompletion;
        v15[-1].Context = &Event;
        v15[-1].Control = -32;
        v16 = (*(__int64 (__fastcall **)(_QWORD, IRP *))(v7 + 8))(a1[12], v2);
        if ( v16 == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        }
        else if ( v16 < 0
               && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            57,
            WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
            (unsigned int)v16);
        }
        a1[12] = 0;
        IoReuseIrp(v2, 259);
      }
    }
    WskReleaseProviderNPI((PWSK_REGISTRATION)DeviceExtension + 3);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      58,
      WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
      (unsigned int)Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001fc68  push    rbp
0x14001fc6a  push    rbx
0x14001fc6b  push    rsi
0x14001fc6c  push    rdi
0x14001fc6d  push    r12
0x14001fc6f  push    r13
0x14001fc71  push    r14
0x14001fc73  push    r15
0x14001fc75  lea     rbp, [rsp-1Fh]
0x14001fc7a  sub     rsp, 98h
0x14001fc81  mov     rdi, [rcx+68h]
0x14001fc85  xor     eax, eax
0x14001fc87  xorps   xmm0, xmm0
0x14001fc8a  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14001fc8e  xor     r13d, r13d
0x14001fc91  mov     r15, rdx
0x14001fc94  mov     [rbp+57h+arg_0], r13d
0x14001fc98  mov     rsi, rcx
0x14001fc9b  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14001fc9f  movups  xmmword ptr [rbp+57h+WskProviderNpi.Client], xmm0
0x14001fca3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcaa  lea     rax, WPP_GLOBAL_Control
0x14001fcb1  cmp     rcx, rax
0x14001fcb4  jz      short loc_14001FCD4
0x14001fcb6  mov     eax, [rcx+2Ch]
0x14001fcb9  test    al, 1
0x14001fcbb  jz      short loc_14001FCD4
0x14001fcbd  mov     rcx, [rcx+18h]
0x14001fcc1  lea     edx, [r13+34h]
0x14001fcc5  mov     r9, rsi
0x14001fcc8  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fccf  call    WPP_SF_q
0x14001fcd4  xor     r8d, r8d; State
0x14001fcd7  lea     rcx, [rbp+57h+Event]; Event
0x14001fcdb  xor     edx, edx; Type
0x14001fcdd  call    cs:__imp_KeInitializeEvent
0x14001fce4  nop     dword ptr [rax+rax+00h]
0x14001fce9  mov     rcx, cs:DeviceExtension
0x14001fcf0  lea     r8, [rbp+57h+WskProviderNpi]; WskProviderNpi
0x14001fcf4  add     rcx, 48h ; 'H'; WskRegistration
0x14001fcf8  or      edx, 0FFFFFFFFh; WaitTimeout
0x14001fcfb  call    cs:__imp_WskCaptureProviderNPI
0x14001fd02  nop     dword ptr [rax+rax+00h]
0x14001fd07  mov     ebx, eax
0x14001fd09  test    eax, eax
0x14001fd0b  js      loc_14002018B
0x14001fd11  mov     rax, [rdi+0B8h]
0x14001fd18  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001fd1f  mov     [rsp+0D0h+var_80], rdi
0x14001fd24  mov     r8d, 1
0x14001fd2a  mov     [rsp+0D0h+var_88], r13
0x14001fd2f  mov     [rsp+0D0h+var_90], r13
0x14001fd34  mov     [rax-10h], rcx
0x14001fd38  lea     rcx, [rbp+57h+Event]
0x14001fd3c  mov     [rax-8], rcx
0x14001fd40  lea     r9d, [r8+5]
0x14001fd44  mov     byte ptr [rax-45h], 0E0h
0x14001fd48  lea     rcx, OncRpcConnMgrpWskListenSocketDispatch
0x14001fd4f  mov     rax, [rbp+57h+WskProviderNpi.Dispatch]
0x14001fd53  movzx   edx, word ptr [r15]
0x14001fd57  mov     [rsp+0D0h+var_98], r13
0x14001fd5c  mov     [rsp+0D0h+var_A0], rcx
0x14001fd61  mov     rax, [rax+8]
0x14001fd65  mov     rcx, [rbp+57h+WskProviderNpi.Client]
0x14001fd69  mov     [rsp+0D0h+var_A8], rsi
0x14001fd6e  mov     dword ptr [rsp+0D0h+Timeout], r8d
0x14001fd73  call    _guard_dispatch_icall
0x14001fd78  mov     ebx, eax
0x14001fd7a  cmp     eax, 103h
0x14001fd7f  jnz     short loc_14001FDA1
0x14001fd81  xor     r9d, r9d; Alertable
0x14001fd84  mov     [rsp+0D0h+Timeout], r13; Timeout
0x14001fd89  xor     r8d, r8d; WaitMode
0x14001fd8c  lea     rcx, [rbp+57h+Event]; Object
0x14001fd90  xor     edx, edx; WaitReason
0x14001fd92  call    cs:__imp_KeWaitForSingleObject
0x14001fd99  nop     dword ptr [rax+rax+00h]
0x14001fd9e  mov     ebx, [rdi+30h]
0x14001fda1  test    ebx, ebx
0x14001fda3  jns     short loc_14001FDE4
0x14001fda5  mov     r14, r13
0x14001fda8  mov     r12b, r13b
0x14001fdab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fdb2  lea     rax, WPP_GLOBAL_Control
0x14001fdb9  cmp     rcx, rax
0x14001fdbc  jz      short loc_14001FDF2
0x14001fdbe  mov     eax, [rcx+2Ch]
0x14001fdc1  test    al, 10h
0x14001fdc3  jz      short loc_14001FDF2
0x14001fdc5  movzx   r9d, word ptr [r15]
0x14001fdc9  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fdd0  mov     rcx, [rcx+18h]
0x14001fdd4  mov     edx, 35h ; '5'
0x14001fdd9  mov     dword ptr [rsp+0D0h+Timeout], ebx
0x14001fddd  call    WPP_SF_Dd
0x14001fde2  jmp     short loc_14001FDF2
0x14001fde4  mov     rax, [rdi+38h]
0x14001fde8  mov     r12b, 1
0x14001fdeb  mov     [rsi+60h], rax
0x14001fdef  mov     r14, [rax]
0x14001fdf2  mov     edx, 103h; Iostatus
0x14001fdf7  mov     rcx, rdi; Irp
0x14001fdfa  call    cs:__imp_IoReuseIrp
0x14001fe01  nop     dword ptr [rax+rax+00h]
0x14001fe06  test    ebx, ebx
0x14001fe08  js      loc_1400200B8
0x14001fe0e  cmp     [rsi+0C0h], r13
0x14001fe15  jz      loc_14001FF0B
0x14001fe1b  lea     rcx, [rbp+57h+Event]; Event
0x14001fe1f  call    cs:__imp_KeClearEvent
0x14001fe26  nop     dword ptr [rax+rax+00h]
0x14001fe2b  mov     rax, [rdi+0B8h]
0x14001fe32  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001fe39  mov     [rsp+0D0h+var_88], rdi
0x14001fe3e  xor     edx, edx
0x14001fe40  mov     [rsp+0D0h+var_90], r13
0x14001fe45  mov     r9d, 0FFFFh
0x14001fe4b  mov     [rsp+0D0h+var_98], r13
0x14001fe50  mov     r8d, 3002h
0x14001fe56  mov     [rax-10h], rcx
0x14001fe5a  lea     rcx, [rbp+57h+Event]
0x14001fe5e  mov     [rax-8], rcx
0x14001fe62  lea     rcx, [rbp+57h+arg_0]
0x14001fe66  mov     byte ptr [rax-45h], 0E0h
0x14001fe6a  mov     [rsp+0D0h+var_A0], r13
0x14001fe6f  mov     [rsp+0D0h+var_A8], rcx
0x14001fe74  mov     rcx, [rsi+60h]
0x14001fe78  mov     [rbp+57h+arg_0], 1
0x14001fe7f  mov     rax, [r14]
0x14001fe82  mov     [rsp+0D0h+Timeout], 4
0x14001fe8b  call    _guard_dispatch_icall
0x14001fe90  mov     ebx, eax
0x14001fe92  cmp     eax, 103h
0x14001fe97  jnz     short loc_14001FEB9
0x14001fe99  xor     r9d, r9d; Alertable
0x14001fe9c  mov     [rsp+0D0h+Timeout], r13; Timeout
0x14001fea1  xor     r8d, r8d; WaitMode
0x14001fea4  lea     rcx, [rbp+57h+Event]; Object
0x14001fea8  xor     edx, edx; WaitReason
0x14001feaa  call    cs:__imp_KeWaitForSingleObject
0x14001feb1  nop     dword ptr [rax+rax+00h]
0x14001feb6  mov     ebx, [rdi+30h]
0x14001feb9  test    ebx, ebx
0x14001febb  jns     short loc_14001FEEF
0x14001febd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fec4  lea     rax, WPP_GLOBAL_Control
0x14001fecb  cmp     rcx, rax
0x14001fece  jz      short loc_14001FEEF
0x14001fed0  mov     eax, [rcx+2Ch]
0x14001fed3  test    al, 10h
0x14001fed5  jz      short loc_14001FEEF
0x14001fed7  mov     rcx, [rcx+18h]
0x14001fedb  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001fee2  mov     edx, 36h ; '6'
0x14001fee7  mov     r9d, ebx
0x14001feea  call    WPP_SF_d
0x14001feef  mov     edx, 103h; Iostatus
0x14001fef4  mov     rcx, rdi; Irp
0x14001fef7  call    cs:__imp_IoReuseIrp
0x14001fefe  nop     dword ptr [rax+rax+00h]
0x14001ff03  test    ebx, ebx
0x14001ff05  js      loc_1400200B8
0x14001ff0b  lea     rcx, [rbp+57h+Event]; Event
0x14001ff0f  call    cs:__imp_KeClearEvent
0x14001ff16  nop     dword ptr [rax+rax+00h]
0x14001ff1b  mov     rax, [rdi+0B8h]
0x14001ff22  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x14001ff29  mov     [rsp+0D0h+var_88], rdi
0x14001ff2e  xor     edx, edx
0x14001ff30  mov     [rsp+0D0h+var_90], r13
0x14001ff35  mov     r9d, 0FFFFh
0x14001ff3b  mov     [rsp+0D0h+var_98], r13
0x14001ff40  mov     [rax-10h], rcx
0x14001ff44  lea     rcx, [rbp+57h+Event]
0x14001ff48  mov     [rax-8], rcx
0x14001ff4c  lea     r8d, [rdx+8]
0x14001ff50  mov     byte ptr [rax-45h], 0E0h
0x14001ff54  lea     rcx, [rbp+57h+arg_0]
0x14001ff58  mov     [rsp+0D0h+var_A0], r13
0x14001ff5d  mov     [rsp+0D0h+var_A8], rcx
0x14001ff62  mov     rcx, [rsi+60h]
0x14001ff66  mov     [rbp+57h+arg_0], 1
0x14001ff6d  mov     rax, [r14]
0x14001ff70  mov     [rsp+0D0h+Timeout], 4
0x14001ff79  call    _guard_dispatch_icall
0x14001ff7e  mov     ebx, eax
0x14001ff80  cmp     eax, 103h
0x14001ff85  jnz     short loc_14001FFA7
0x14001ff87  xor     r9d, r9d; Alertable
0x14001ff8a  mov     [rsp+0D0h+Timeout], r13; Timeout
0x14001ff8f  xor     r8d, r8d; WaitMode
0x14001ff92  lea     rcx, [rbp+57h+Event]; Object
0x14001ff96  xor     edx, edx; WaitReason
0x14001ff98  call    cs:__imp_KeWaitForSingleObject
0x14001ff9f  nop     dword ptr [rax+rax+00h]
0x14001ffa4  mov     ebx, [rdi+30h]
0x14001ffa7  test    ebx, ebx
0x14001ffa9  jns     short loc_14001FFDD
0x14001ffab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ffb2  lea     rax, WPP_GLOBAL_Control
0x14001ffb9  cmp     rcx, rax
0x14001ffbc  jz      short loc_14001FFDD
0x14001ffbe  mov     eax, [rcx+2Ch]
0x14001ffc1  test    al, 10h
0x14001ffc3  jz      short loc_14001FFDD
0x14001ffc5  mov     rcx, [rcx+18h]
0x14001ffc9  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14001ffd0  mov     edx, 37h ; '7'
0x14001ffd5  mov     r9d, ebx
0x14001ffd8  call    WPP_SF_d
0x14001ffdd  mov     edx, 103h; Iostatus
0x14001ffe2  mov     rcx, rdi; Irp
0x14001ffe5  call    cs:__imp_IoReuseIrp
0x14001ffec  nop     dword ptr [rax+rax+00h]
0x14001fff1  test    ebx, ebx
0x14001fff3  js      loc_1400200B8
0x14001fff9  lea     rcx, [rbp+57h+Event]; Event
0x14001fffd  call    cs:__imp_KeClearEvent
0x140020004  nop     dword ptr [rax+rax+00h]
0x140020009  mov     rax, [rdi+0B8h]
0x140020010  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x140020017  mov     r9, rdi
0x14002001a  xor     r8d, r8d
0x14002001d  mov     rdx, r15
0x140020020  mov     [rax-10h], rcx
0x140020024  lea     rcx, [rbp+57h+Event]
0x140020028  mov     [rax-8], rcx
0x14002002c  mov     byte ptr [rax-45h], 0E0h
0x140020030  mov     rax, [r14+10h]
0x140020034  mov     rcx, [rsi+60h]
0x140020038  call    _guard_dispatch_icall
0x14002003d  mov     ebx, eax
0x14002003f  cmp     eax, 103h
0x140020044  jnz     short loc_140020066
0x140020046  xor     r9d, r9d; Alertable
0x140020049  mov     [rsp+0D0h+Timeout], r13; Timeout
0x14002004e  xor     r8d, r8d; WaitMode
0x140020051  lea     rcx, [rbp+57h+Event]; Object
0x140020055  xor     edx, edx; WaitReason
0x140020057  call    cs:__imp_KeWaitForSingleObject
0x14002005e  nop     dword ptr [rax+rax+00h]
0x140020063  mov     ebx, [rdi+30h]
0x140020066  test    ebx, ebx
0x140020068  jns     short loc_14002009C
0x14002006a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020071  lea     rax, WPP_GLOBAL_Control
0x140020078  cmp     rcx, rax
0x14002007b  jz      short loc_14002009C
0x14002007d  mov     eax, [rcx+2Ch]
0x140020080  test    al, 10h
0x140020082  jz      short loc_14002009C
0x140020084  mov     rcx, [rcx+18h]
0x140020088  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14002008f  mov     edx, 38h ; '8'
0x140020094  mov     r9d, ebx
0x140020097  call    WPP_SF_d
0x14002009c  mov     edx, 103h; Iostatus
0x1400200a1  mov     rcx, rdi; Irp
0x1400200a4  call    cs:__imp_IoReuseIrp
0x1400200ab  nop     dword ptr [rax+rax+00h]
0x1400200b0  test    ebx, ebx
0x1400200b2  jns     loc_140020174
0x1400200b8  test    r12b, r12b
0x1400200bb  jz      loc_140020174
0x1400200c1  lea     rcx, [rbp+57h+Event]; Event
0x1400200c5  call    cs:__imp_KeClearEvent
0x1400200cc  nop     dword ptr [rax+rax+00h]
0x1400200d1  mov     rax, [rdi+0B8h]
0x1400200d8  lea     rcx, OncRpcConnMgrpWskSynchronousIrpCompletion
0x1400200df  mov     rdx, rdi
0x1400200e2  mov     [rax-10h], rcx
0x1400200e6  lea     rcx, [rbp+57h+Event]
0x1400200ea  mov     [rax-8], rcx
0x1400200ee  mov     byte ptr [rax-45h], 0E0h
0x1400200f2  mov     rax, [r14+8]
0x1400200f6  mov     rcx, [rsi+60h]
0x1400200fa  call    _guard_dispatch_icall
0x1400200ff  mov     r9d, eax
0x140020102  cmp     eax, 103h
0x140020107  jnz     short loc_140020128
0x140020109  xor     r9d, r9d; Alertable
0x14002010c  mov     [rsp+0D0h+Timeout], r13; Timeout
0x140020111  xor     r8d, r8d; WaitMode
0x140020114  lea     rcx, [rbp+57h+Event]; Object
0x140020118  xor     edx, edx; WaitReason
0x14002011a  call    cs:__imp_KeWaitForSingleObject
0x140020121  nop     dword ptr [rax+rax+00h]
0x140020126  jmp     short loc_14002015C
0x140020128  test    r9d, r9d
0x14002012b  jns     short loc_14002015C
0x14002012d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020134  lea     rax, WPP_GLOBAL_Control
0x14002013b  cmp     rcx, rax
0x14002013e  jz      short loc_14002015C
0x140020140  mov     eax, [rcx+2Ch]
0x140020143  test    al, 10h
0x140020145  jz      short loc_14002015C
0x140020147  mov     rcx, [rcx+18h]
0x14002014b  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x140020152  mov     edx, 39h ; '9'
  ... truncated ...
```
