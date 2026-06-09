# SrvNetWskOpenListenSocket

- ea: `0x140045788`
- end: `0x140045da7`
- name: `SrvNetWskOpenListenSocket`
- size: `1567`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140042864`

## callees

- `0x140018a50`
- `0x1400198d4`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x1400456b8`
- `0x140045788`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x1400457ee`
- `ntoskrnl!IoAllocateIrp` at `0x1400457ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400458c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400459a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045a57`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045b0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045ba6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045c5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045d0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400458c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400459a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045a57`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045b0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045ba6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045c5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045d0d`
- `ntoskrnl!KeInitializeEvent` at `0x14004582a`
- `ntoskrnl!KeInitializeEvent` at `0x140045919`
- `ntoskrnl!KeInitializeEvent` at `0x1400459d0`
- `ntoskrnl!KeInitializeEvent` at `0x140045a87`
- `ntoskrnl!KeInitializeEvent` at `0x140045b41`
- `ntoskrnl!KeInitializeEvent` at `0x140045bd6`
- `ntoskrnl!KeInitializeEvent` at `0x140045c86`
- `ntoskrnl!KeInitializeEvent` at `0x14004582a`
- `ntoskrnl!KeInitializeEvent` at `0x140045919`
- `ntoskrnl!KeInitializeEvent` at `0x1400459d0`
- `ntoskrnl!KeInitializeEvent` at `0x140045a87`
- `ntoskrnl!KeInitializeEvent` at `0x140045b41`
- `ntoskrnl!KeInitializeEvent` at `0x140045bd6`
- `ntoskrnl!KeInitializeEvent` at `0x140045c86`

## pseudocode

```c
__int64 __fastcall SrvNetWskOpenListenSocket(__int64 a1, unsigned __int16 *a2)
{
  PIRP v2; // rdi
  PIRP Irp; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int Status; // ebx
  int *v9; // r14
  __int64 *Information; // r15
  __int64 (__fastcall *v11)(__int64 *, __int64, __int64, __int64, __int64, int *, __int64, char *, _QWORD, PIRP); // r13
  struct _IO_STACK_LOCATION *v12; // rax
  struct _IO_STACK_LOCATION *v13; // rax
  struct _IO_STACK_LOCATION *v14; // rax
  int v15; // eax
  struct _IO_STACK_LOCATION *v16; // rax
  struct _IO_STACK_LOCATION *v17; // rax
  struct _IO_STACK_LOCATION *v18; // rdx
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  char v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+68h] [rbp-98h] BYREF
  struct _KEVENT Event; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  int v26; // [rsp+94h] [rbp-6Ch] BYREF
  int v27; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-60h]
  WCHAR S[72]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = *(PIRP *)(a1 + 40);
  v26 = 0;
  v22[0] = 0;
  v25 = 1;
  v27 = 1;
  v23 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( !v2 )
  {
    Irp = IoAllocateIrp(1, 0);
    *(_QWORD *)(a1 + 40) = Irp;
    v2 = Irp;
    if ( !Irp )
      return 3221225626LL;
  }
  LODWORD(v23) = 259;
  *((_QWORD *)&v23 + 1) = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
  CurrentStackLocation[-1].Control = -32;
  CurrentStackLocation[-1].Context = &v23;
  Status = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, __int64, __int64 (__fastcall **)(int, int, int, int, __int64, __int64, __int64), _QWORD, _QWORD, _QWORD, PIRP))(*(_QWORD *)(SrvNetWskProviderNpi + 8) + 8LL))(
             *(_QWORD *)SrvNetWskProviderNpi,
             *a2,
             1,
             6,
             1,
             a1,
             &SrvNetWskListenDispatch,
             0,
             0,
             0,
             v2);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
    v9 = (int *)&v2->IoStatus.0;
    Status = v2->IoStatus.Status;
  }
  else
  {
    v9 = (int *)&v2->IoStatus.0;
  }
  if ( Status >= 0 )
  {
    Information = (__int64 *)v2->IoStatus.Information;
    *(_QWORD *)(a1 + 32) = Information;
    *(_DWORD *)(a1 + 124) = 1;
    v28 = *Information;
    v11 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64, int *, __int64, char *, _QWORD, PIRP))v28;
    LODWORD(v23) = 259;
    *((_QWORD *)&v23 + 1) = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v12 = v2->Tail.Overlay.CurrentStackLocation;
    v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
    v12[-1].Context = &v23;
    v12[-1].Control = -32;
    Status = v11(Information, 0, 27, 41, 4, &v26, 0, 0, 0, v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      Status = *v9;
    }
    if ( Status < 0 )
      goto LABEL_27;
    LODWORD(v23) = 259;
    *((_QWORD *)&v23 + 1) = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v13 = v2->Tail.Overlay.CurrentStackLocation;
    v13[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
    v13[-1].Context = &v23;
    v13[-1].Control = -32;
    Status = v11(Information, 0, 1, 6, 4, &v27, 0, 0, 0, v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      Status = *v9;
    }
    if ( Status < 0 )
      goto LABEL_27;
    LODWORD(v23) = 259;
    *((_QWORD *)&v23 + 1) = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v14 = v2->Tail.Overlay.CurrentStackLocation;
    v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
    v14[-1].Context = &v23;
    v14[-1].Control = -32;
    v15 = v11(Information, 2, 1476395218, 0xFFFF, 0, 0, 1, v22, 0, v2);
    if ( v15 == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      v15 = *v9;
    }
    if ( v15 >= 0 )
      RssScalabilityEnabled = v22[0];
    LODWORD(v23) = 259;
    *((_QWORD *)&v23 + 1) = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v16 = v2->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
    v16[-1].Context = &v23;
    v16[-1].Control = -32;
    Status = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *, _QWORD, PIRP))(v28 + 16))(Information, a2, 0, v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      Status = *v9;
    }
    if ( Status < 0 )
      goto LABEL_27;
    LODWORD(v23) = 259;
    *((_QWORD *)&v23 + 1) = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v17 = v2->Tail.Overlay.CurrentStackLocation;
    v17[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
    v17[-1].Context = &v23;
    v17[-1].Control = -32;
    Status = v11(Information, 0, 28, 0, 4, &v25, 0, 0, 0, v2);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      Status = *v9;
    }
    LODWORD(v23) = 259;
    *((_QWORD *)&v23 + 1) = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v18 = v2->Tail.Overlay.CurrentStackLocation;
    v18[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SrvNetUxTlSynchronousIrpComplete;
    v18[-1].Context = &v23;
    v18[-1].Control = -32;
    v19 = v11(Information, 0, 28, 41, 4, &v25, 0, 0, 0, v2);
    if ( v19 == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      v19 = *v9;
    }
    if ( Status < 0 )
    {
      Status = v19;
      if ( v19 < 0 )
LABEL_27:
        SrvNetWskCloseListenSocket(a1);
    }
  }
  if ( (unsigned __int16)SrvNetHostAddressAndPortToStringW(S)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qSD(WPP_GLOBAL_Control->AttachedDevice, v20, v21, a1, (__int64)S, Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140045788  mov     [rsp-8+arg_10], rbx
0x14004578d  push    rbp
0x14004578e  push    rsi
0x14004578f  push    rdi
0x140045790  push    r12
0x140045792  push    r13
0x140045794  push    r14
0x140045796  push    r15
0x140045798  lea     rbp, [rsp-50h]
0x14004579d  sub     rsp, 150h
0x1400457a4  mov     rax, cs:__security_cookie
0x1400457ab  xor     rax, rsp
0x1400457ae  mov     [rbp+80h+var_40], rax
0x1400457b2  mov     rdi, [rcx+28h]
0x1400457b6  xor     eax, eax
0x1400457b8  xor     ebx, ebx
0x1400457ba  mov     [rbp+80h+Event.Header.WaitListHead.Blink], rax
0x1400457be  mov     [rbp+80h+var_EC], ebx
0x1400457c1  xorps   xmm0, xmm0
0x1400457c4  mov     [rsp+180h+var_120], bl
0x1400457c8  mov     r12, rdx
0x1400457cb  lea     r15d, [rax+1]
0x1400457cf  mov     rsi, rcx
0x1400457d2  mov     [rbp+80h+var_F0], r15d
0x1400457d6  mov     [rbp+80h+var_E8], r15d
0x1400457da  movups  [rsp+180h+var_118], xmm0
0x1400457df  movups  xmmword ptr [rsp+180h+Event.Header], xmm0
0x1400457e4  test    rdi, rdi
0x1400457e7  jnz     short loc_140045810
0x1400457e9  xor     edx, edx; ChargeQuota
0x1400457eb  mov     cl, r15b; StackSize
0x1400457ee  call    cs:__imp_IoAllocateIrp
0x1400457f5  nop     dword ptr [rax+rax+00h]
0x1400457fa  mov     [rsi+28h], rax
0x1400457fe  mov     rdi, rax
0x140045801  test    rax, rax
0x140045804  jnz     short loc_140045810
0x140045806  mov     eax, 0C000009Ah
0x14004580b  jmp     loc_140045D7F
0x140045810  xor     r8d, r8d; State
0x140045813  mov     dword ptr [rsp+180h+var_118], 103h
0x14004581b  xor     edx, edx; Type
0x14004581d  mov     qword ptr [rsp+180h+var_118+8], rbx
0x140045822  lea     rcx, [rsp+180h+Event]; Event
0x140045827  mov     r14, rdi
0x14004582a  call    cs:__imp_KeInitializeEvent
0x140045831  nop     dword ptr [rax+rax+00h]
0x140045836  mov     rax, [rdi+0B8h]
0x14004583d  lea     rdx, SrvNetWskListenDispatch
0x140045844  mov     [rsp+180h+var_130], rdi
0x140045849  lea     rcx, SrvNetUxTlSynchronousIrpComplete
0x140045850  mov     [rsp+180h+var_138], rbx
0x140045855  mov     r13d, 6
0x14004585b  mov     [rsp+180h+var_140], rbx
0x140045860  mov     r8d, r15d
0x140045863  mov     [rax-10h], rcx
0x140045867  mov     r9d, r13d
0x14004586a  mov     byte ptr [rax-45h], 0E0h
0x14004586e  lea     rcx, [rsp+180h+var_118]
0x140045873  mov     [rax-8], rcx
0x140045877  mov     rcx, cs:SrvNetWskProviderNpi
0x14004587e  mov     [rsp+180h+var_148], rbx
0x140045883  mov     [rsp+180h+var_150], rdx
0x140045888  movzx   edx, word ptr [r12]
0x14004588d  mov     rax, [rcx+8]
0x140045891  mov     rcx, [rcx]
0x140045894  mov     [rsp+180h+var_158], rsi
0x140045899  mov     dword ptr [rsp+180h+Timeout], r15d
0x14004589e  mov     rax, [rax+8]
0x1400458a2  call    _guard_dispatch_icall
0x1400458a7  mov     ebx, eax
0x1400458a9  cmp     eax, 103h
0x1400458ae  jnz     short loc_1400458DB
0x1400458b0  xor     r15d, r15d
0x1400458b3  lea     rcx, [rsp+180h+Event]; Object
0x1400458b8  xor     r9d, r9d; Alertable
0x1400458bb  mov     [rsp+180h+Timeout], r15; Timeout
0x1400458c0  xor     r8d, r8d; WaitMode
0x1400458c3  mov     edx, r13d; WaitReason
0x1400458c6  call    cs:__imp_KeWaitForSingleObject
0x1400458cd  nop     dword ptr [rax+rax+00h]
0x1400458d2  lea     r14, [rdi+30h]
0x1400458d6  mov     ebx, [r14]
0x1400458d9  jmp     short loc_1400458DF
0x1400458db  add     r14, 30h ; '0'
0x1400458df  test    ebx, ebx
0x1400458e1  js      loc_140045D2E
0x1400458e7  mov     r15, [rdi+38h]
0x1400458eb  lea     rcx, [rsp+180h+Event]; Event
0x1400458f0  mov     [rsi+20h], r15
0x1400458f4  xor     ebx, ebx
0x1400458f6  mov     dword ptr [rsi+7Ch], 1
0x1400458fd  xor     r8d, r8d; State
0x140045900  xor     edx, edx; Type
0x140045902  mov     rax, [r15]
0x140045905  mov     [rbp+80h+var_E0], rax
0x140045909  mov     r13, [rax]
0x14004590c  mov     dword ptr [rsp+180h+var_118], 103h
0x140045914  mov     qword ptr [rsp+180h+var_118+8], rbx
0x140045919  call    cs:__imp_KeInitializeEvent
0x140045920  nop     dword ptr [rax+rax+00h]
0x140045925  mov     rax, [rdi+0B8h]
0x14004592c  lea     rcx, SrvNetUxTlSynchronousIrpComplete
0x140045933  mov     [rsp+180h+var_138], rdi
0x140045938  lea     r9d, [rbx+29h]
0x14004593c  mov     [rsp+180h+var_140], rbx
0x140045941  lea     r8d, [rbx+1Bh]
0x140045945  mov     [rsp+180h+var_148], rbx
0x14004594a  xor     edx, edx
0x14004594c  mov     [rax-10h], rcx
0x140045950  lea     rcx, [rsp+180h+var_118]
0x140045955  mov     [rax-8], rcx
0x140045959  mov     rcx, r15
0x14004595c  mov     byte ptr [rax-45h], 0E0h
0x140045960  lea     rax, [rbp+80h+var_EC]
0x140045964  mov     [rsp+180h+var_150], rbx
0x140045969  mov     [rsp+180h+var_158], rax
0x14004596e  mov     rax, r13
0x140045971  mov     [rsp+180h+Timeout], 4
0x14004597a  call    _guard_dispatch_icall
0x14004597f  mov     ebx, eax
0x140045981  cmp     eax, 103h
0x140045986  jnz     short loc_1400459AF
0x140045988  xor     r9d, r9d; Alertable
0x14004598b  mov     [rsp+180h+Timeout], 0; Timeout
0x140045994  xor     r8d, r8d; WaitMode
0x140045997  lea     rcx, [rsp+180h+Event]; Object
0x14004599c  lea     edx, [r9+6]; WaitReason
0x1400459a0  call    cs:__imp_KeWaitForSingleObject
0x1400459a7  nop     dword ptr [rax+rax+00h]
0x1400459ac  mov     ebx, [r14]
0x1400459af  test    ebx, ebx
0x1400459b1  js      loc_140045D26
0x1400459b7  xor     ebx, ebx
0x1400459b9  mov     dword ptr [rsp+180h+var_118], 103h
0x1400459c1  xor     r8d, r8d; State
0x1400459c4  mov     qword ptr [rsp+180h+var_118+8], rbx
0x1400459c9  xor     edx, edx; Type
0x1400459cb  lea     rcx, [rsp+180h+Event]; Event
0x1400459d0  call    cs:__imp_KeInitializeEvent
0x1400459d7  nop     dword ptr [rax+rax+00h]
0x1400459dc  mov     rax, [rdi+0B8h]
0x1400459e3  lea     rcx, SrvNetUxTlSynchronousIrpComplete
0x1400459ea  mov     [rsp+180h+var_138], rdi
0x1400459ef  lea     r9d, [rbx+6]
0x1400459f3  mov     [rsp+180h+var_140], rbx
0x1400459f8  lea     r8d, [rbx+1]
0x1400459fc  mov     [rsp+180h+var_148], rbx
0x140045a01  xor     edx, edx
0x140045a03  mov     [rax-10h], rcx
0x140045a07  lea     rcx, [rsp+180h+var_118]
0x140045a0c  mov     [rax-8], rcx
0x140045a10  mov     rcx, r15
0x140045a13  mov     byte ptr [rax-45h], 0E0h
0x140045a17  lea     rax, [rbp+80h+var_E8]
0x140045a1b  mov     [rsp+180h+var_150], rbx
0x140045a20  mov     [rsp+180h+var_158], rax
0x140045a25  mov     rax, r13
0x140045a28  mov     [rsp+180h+Timeout], 4
0x140045a31  call    _guard_dispatch_icall
0x140045a36  mov     ebx, eax
0x140045a38  cmp     eax, 103h
0x140045a3d  jnz     short loc_140045A66
0x140045a3f  xor     r9d, r9d; Alertable
0x140045a42  mov     [rsp+180h+Timeout], 0; Timeout
0x140045a4b  xor     r8d, r8d; WaitMode
0x140045a4e  lea     rcx, [rsp+180h+Event]; Object
0x140045a53  lea     edx, [r9+6]; WaitReason
0x140045a57  call    cs:__imp_KeWaitForSingleObject
0x140045a5e  nop     dword ptr [rax+rax+00h]
0x140045a63  mov     ebx, [r14]
0x140045a66  test    ebx, ebx
0x140045a68  js      loc_140045D26
0x140045a6e  xor     ebx, ebx
0x140045a70  mov     dword ptr [rsp+180h+var_118], 103h
0x140045a78  xor     r8d, r8d; State
0x140045a7b  mov     qword ptr [rsp+180h+var_118+8], rbx
0x140045a80  xor     edx, edx; Type
0x140045a82  lea     rcx, [rsp+180h+Event]; Event
0x140045a87  call    cs:__imp_KeInitializeEvent
0x140045a8e  nop     dword ptr [rax+rax+00h]
0x140045a93  mov     rax, [rdi+0B8h]
0x140045a9a  lea     rcx, SrvNetUxTlSynchronousIrpComplete
0x140045aa1  mov     [rsp+180h+var_138], rdi
0x140045aa6  lea     edx, [rbx+2]
0x140045aa9  mov     [rsp+180h+var_140], rbx
0x140045aae  mov     r9d, 0FFFFh
0x140045ab4  mov     r8d, 580000D2h
0x140045aba  mov     [rax-10h], rcx
0x140045abe  lea     rcx, [rsp+180h+var_118]
0x140045ac3  mov     [rax-8], rcx
0x140045ac7  mov     rcx, r15
0x140045aca  mov     byte ptr [rax-45h], 0E0h
0x140045ace  lea     rax, [rsp+180h+var_120]
0x140045ad3  mov     [rsp+180h+var_148], rax
0x140045ad8  mov     rax, r13
0x140045adb  mov     [rsp+180h+var_150], 1
0x140045ae4  mov     [rsp+180h+var_158], rbx
0x140045ae9  mov     [rsp+180h+Timeout], rbx
0x140045aee  call    _guard_dispatch_icall
0x140045af3  cmp     eax, 103h
0x140045af8  jnz     short loc_140045B1C
0x140045afa  xor     r9d, r9d; Alertable
0x140045afd  mov     [rsp+180h+Timeout], rbx; Timeout
0x140045b02  xor     r8d, r8d; WaitMode
0x140045b05  lea     edx, [rbx+6]; WaitReason
0x140045b08  lea     rcx, [rsp+180h+Event]; Object
0x140045b0d  call    cs:__imp_KeWaitForSingleObject
0x140045b14  nop     dword ptr [rax+rax+00h]
0x140045b19  mov     eax, [r14]
0x140045b1c  test    eax, eax
0x140045b1e  js      short loc_140045B2A
0x140045b20  mov     al, [rsp+180h+var_120]
0x140045b24  mov     cs:RssScalabilityEnabled, al
0x140045b2a  xor     r8d, r8d; State
0x140045b2d  mov     dword ptr [rsp+180h+var_118], 103h
0x140045b35  xor     edx, edx; Type
0x140045b37  mov     qword ptr [rsp+180h+var_118+8], rbx
0x140045b3c  lea     rcx, [rsp+180h+Event]; Event
0x140045b41  call    cs:__imp_KeInitializeEvent
0x140045b48  nop     dword ptr [rax+rax+00h]
0x140045b4d  mov     rax, [rdi+0B8h]
0x140045b54  lea     rcx, SrvNetUxTlSynchronousIrpComplete
0x140045b5b  mov     r9, rdi
0x140045b5e  xor     r8d, r8d
0x140045b61  mov     rdx, r12
0x140045b64  mov     [rax-10h], rcx
0x140045b68  lea     rcx, [rsp+180h+var_118]
0x140045b6d  mov     [rax-8], rcx
0x140045b71  mov     rcx, r15
0x140045b74  mov     byte ptr [rax-45h], 0E0h
0x140045b78  mov     rax, [rbp+80h+var_E0]
0x140045b7c  mov     rax, [rax+10h]
0x140045b80  call    _guard_dispatch_icall
0x140045b85  mov     ebx, eax
0x140045b87  cmp     eax, 103h
0x140045b8c  jnz     short loc_140045BB5
0x140045b8e  xor     r9d, r9d; Alertable
0x140045b91  mov     [rsp+180h+Timeout], 0; Timeout
0x140045b9a  xor     r8d, r8d; WaitMode
0x140045b9d  lea     rcx, [rsp+180h+Event]; Object
0x140045ba2  lea     edx, [r9+6]; WaitReason
0x140045ba6  call    cs:__imp_KeWaitForSingleObject
0x140045bad  nop     dword ptr [rax+rax+00h]
0x140045bb2  mov     ebx, [r14]
0x140045bb5  test    ebx, ebx
0x140045bb7  js      loc_140045D26
0x140045bbd  xor     ebx, ebx
0x140045bbf  mov     dword ptr [rsp+180h+var_118], 103h
0x140045bc7  xor     r8d, r8d; State
0x140045bca  mov     qword ptr [rsp+180h+var_118+8], rbx
0x140045bcf  xor     edx, edx; Type
0x140045bd1  lea     rcx, [rsp+180h+Event]; Event
0x140045bd6  call    cs:__imp_KeInitializeEvent
0x140045bdd  nop     dword ptr [rax+rax+00h]
0x140045be2  mov     rax, [rdi+0B8h]
0x140045be9  lea     rcx, SrvNetUxTlSynchronousIrpComplete
0x140045bf0  mov     [rsp+180h+var_138], rdi
0x140045bf5  lea     r8d, [rbx+1Ch]
0x140045bf9  mov     [rsp+180h+var_140], rbx
0x140045bfe  xor     r9d, r9d
0x140045c01  mov     [rsp+180h+var_148], rbx
0x140045c06  xor     edx, edx
0x140045c08  mov     [rax-10h], rcx
0x140045c0c  lea     rcx, [rsp+180h+var_118]
0x140045c11  mov     [rax-8], rcx
0x140045c15  mov     rcx, r15
0x140045c18  mov     byte ptr [rax-45h], 0E0h
0x140045c1c  lea     rax, [rbp+80h+var_F0]
0x140045c20  mov     [rsp+180h+var_150], rbx
0x140045c25  mov     [rsp+180h+var_158], rax
0x140045c2a  mov     rax, r13
0x140045c2d  mov     [rsp+180h+Timeout], 4
0x140045c36  call    _guard_dispatch_icall
0x140045c3b  mov     ebx, eax
0x140045c3d  cmp     eax, 103h
0x140045c42  jnz     short loc_140045C6B
0x140045c44  xor     r9d, r9d; Alertable
0x140045c47  mov     [rsp+180h+Timeout], 0; Timeout
0x140045c50  xor     r8d, r8d; WaitMode
0x140045c53  lea     rcx, [rsp+180h+Event]; Object
0x140045c58  lea     edx, [r9+6]; WaitReason
0x140045c5c  call    cs:__imp_KeWaitForSingleObject
0x140045c63  nop     dword ptr [rax+rax+00h]
0x140045c68  mov     ebx, [r14]
0x140045c6b  xor     r8d, r8d; State
0x140045c6e  mov     dword ptr [rsp+180h+var_118], 103h
0x140045c76  xor     edx, edx; Type
0x140045c78  mov     qword ptr [rsp+180h+var_118+8], 0
0x140045c81  lea     rcx, [rsp+180h+Event]; Event
0x140045c86  call    cs:__imp_KeInitializeEvent
0x140045c8d  nop     dword ptr [rax+rax+00h]
0x140045c92  mov     rdx, [rdi+0B8h]
0x140045c99  lea     rax, SrvNetUxTlSynchronousIrpComplete
0x140045ca0  mov     [rsp+180h+var_138], rdi
0x140045ca5  mov     rcx, r15
0x140045ca8  mov     [rdx-10h], rax
0x140045cac  lea     rax, [rsp+180h+var_118]
0x140045cb1  mov     [rdx-8], rax
0x140045cb5  xor     eax, eax
  ... truncated ...
```
