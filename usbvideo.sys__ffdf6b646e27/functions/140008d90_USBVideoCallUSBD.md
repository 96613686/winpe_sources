# USBVideoCallUSBD

- ea: `0x140008d90`
- end: `0x140008f73`
- name: `USBVideoCallUSBD`
- size: `483`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008640`
- `0x140009b9c`
- `0x140038e90`

## callees

- `0x140008d90`
- `0x14001b15c`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140008e4f`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140008e4f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140008e15`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140008e15`
- `ntoskrnl!IoCancelIrp` at `0x140008eff`
- `ntoskrnl!IoCancelIrp` at `0x140008eff`
- `ntoskrnl!IofCompleteRequest` at `0x140008f3c`
- `ntoskrnl!IofCompleteRequest` at `0x140008f3c`
- `ntoskrnl!KeInitializeEvent` at `0x140008dce`
- `ntoskrnl!KeInitializeEvent` at `0x140008dce`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008eb8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008f1d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008eb8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008f1d`
- `ntoskrnl!IofCallDriver` at `0x140008e7b`
- `ntoskrnl!IofCallDriver` at `0x140008e7b`

## pseudocode

```c
__int64 __fastcall USBVideoCallUSBD(__int64 a1, ULONG_PTR a2, ULONG a3, ULONG_PTR a4)
{
  struct _DEVICE_OBJECT *v4; // rbp
  IRP *v9; // rax
  IRP *v10; // rbx
  int v11; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-58h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+C0h] [rbp+8h] BYREF

  v4 = *(struct _DEVICE_OBJECT **)(a1 + 40);
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  if ( !a3 )
    a3 = 2228227;
  v9 = IoBuildDeviceIoControlRequest(a3, v4, 0, 0, 0, 0, 1u, &Event, &IoStatusBlock);
  v10 = v9;
  if ( !v9 )
    return 3221225626LL;
  v11 = IoSetCompletionRoutineEx(*(PDEVICE_OBJECT *)(a1 + 24), v9, USBVideoCompleteSynch, &Event, 1u, 1u, 1u);
  if ( v11 < 0 )
    goto LABEL_13;
  if ( !a4 )
    a4 = a2;
  v10->Tail.Overlay.CurrentStackLocation[-1].Parameters.WMI.ProviderId = a4;
  v11 = IofCallDriver(v4, v10);
  if ( v11 == 259 )
  {
    Timeout.QuadPart = -50000000;
    if ( KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout) == 258 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v10);
      IoCancelIrp(v10);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      IoStatusBlock.Status = 258;
    }
  }
  else
  {
LABEL_13:
    IoStatusBlock.Status = v11;
  }
  IofCompleteRequest(v10, 0);
  return (unsigned int)IoStatusBlock.Status;
}

```

## disassembly

```asm
0x140008d90  push    rbx
0x140008d92  push    rbp
0x140008d93  push    rsi
0x140008d94  push    rdi
0x140008d95  push    r14
0x140008d97  push    r15
0x140008d99  sub     rsp, 88h
0x140008da0  mov     rbp, [rcx+28h]
0x140008da4  xorps   xmm0, xmm0
0x140008da7  mov     ebx, r8d
0x140008daa  mov     r14, rdx
0x140008dad  mov     rdi, rcx
0x140008db0  xor     eax, eax
0x140008db2  xor     r8d, r8d; State
0x140008db5  mov     [rsp+0B8h+Event.Header.WaitListHead.Blink], rax
0x140008dba  xor     edx, edx; Type
0x140008dbc  lea     rcx, [rsp+0B8h+Event]; Event
0x140008dc1  movups  xmmword ptr [rsp+0B8h+Event.Header], xmm0
0x140008dc6  mov     rsi, r9
0x140008dc9  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x140008dce  call    cs:__imp_KeInitializeEvent
0x140008dd5  nop     dword ptr [rax+rax+00h]
0x140008dda  mov     eax, 220003h
0x140008ddf  test    ebx, ebx
0x140008de1  mov     rdx, rbp; DeviceObject
0x140008de4  cmovz   ebx, eax
0x140008de7  lea     rax, [rsp+0B8h+var_68]
0x140008dec  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x140008df1  xor     r15d, r15d
0x140008df4  lea     rax, [rsp+0B8h+Event]
0x140008df9  xor     r9d, r9d; InputBufferLength
0x140008dfc  mov     [rsp+0B8h+var_80], rax; Event
0x140008e01  xor     r8d, r8d; InputBuffer
0x140008e04  mov     [rsp+0B8h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x140008e09  mov     ecx, ebx; IoControlCode
0x140008e0b  mov     [rsp+0B8h+OutputBufferLength], r15d; OutputBufferLength
0x140008e10  mov     [rsp+0B8h+OutputBuffer], r15; OutputBuffer
0x140008e15  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140008e1c  nop     dword ptr [rax+rax+00h]
0x140008e21  mov     rbx, rax
0x140008e24  test    rax, rax
0x140008e27  jz      loc_140008F5D
0x140008e2d  mov     rcx, [rdi+18h]; DeviceObject
0x140008e31  lea     r9, [rsp+0B8h+Event]; Context
0x140008e36  mov     [rsp+0B8h+InternalDeviceIoControl], 1; InvokeOnCancel
0x140008e3b  lea     r8, USBVideoCompleteSynch; CompletionRoutine
0x140008e42  mov     byte ptr [rsp+0B8h+OutputBufferLength], 1; InvokeOnError
0x140008e47  mov     rdx, rax; Irp
0x140008e4a  mov     byte ptr [rsp+0B8h+OutputBuffer], 1; InvokeOnSuccess
0x140008e4f  call    cs:__imp_IoSetCompletionRoutineEx
0x140008e56  nop     dword ptr [rax+rax+00h]
0x140008e5b  test    eax, eax
0x140008e5d  js      loc_140008F33
0x140008e63  mov     rax, [rbx+0B8h]
0x140008e6a  test    rsi, rsi
0x140008e6d  mov     rdx, rbx; Irp
0x140008e70  mov     rcx, rbp; DeviceObject
0x140008e73  cmovz   rsi, r14
0x140008e77  mov     [rax-40h], rsi
0x140008e7b  call    cs:__imp_IofCallDriver
0x140008e82  nop     dword ptr [rax+rax+00h]
0x140008e87  cmp     eax, 103h
0x140008e8c  jnz     loc_140008F33
0x140008e92  lea     rax, [rsp+0B8h+Timeout]
0x140008e9a  mov     qword ptr [rsp+0B8h+Timeout], 0FFFFFFFFFD050F80h
0x140008ea6  xor     r9d, r9d; Alertable
0x140008ea9  mov     [rsp+0B8h+OutputBuffer], rax; Timeout
0x140008eae  xor     r8d, r8d; WaitMode
0x140008eb1  lea     rcx, [rsp+0B8h+Event]; Object
0x140008eb6  xor     edx, edx; WaitReason
0x140008eb8  call    cs:__imp_KeWaitForSingleObject
0x140008ebf  nop     dword ptr [rax+rax+00h]
0x140008ec4  cmp     eax, 102h
0x140008ec9  jnz     short loc_140008F37
0x140008ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ed2  lea     rax, WPP_GLOBAL_Control
0x140008ed9  cmp     rcx, rax
0x140008edc  jz      short loc_140008EFC
0x140008ede  cmp     byte ptr [rcx+29h], 5
0x140008ee2  jb      short loc_140008EFC
0x140008ee4  mov     rcx, [rcx+18h]
0x140008ee8  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140008eef  mov     edx, 12h
0x140008ef4  mov     r9, rbx
0x140008ef7  call    WPP_SF_q
0x140008efc  mov     rcx, rbx; Irp
0x140008eff  call    cs:__imp_IoCancelIrp
0x140008f06  nop     dword ptr [rax+rax+00h]
0x140008f0b  xor     r9d, r9d; Alertable
0x140008f0e  mov     [rsp+0B8h+OutputBuffer], r15; Timeout
0x140008f13  xor     r8d, r8d; WaitMode
0x140008f16  lea     rcx, [rsp+0B8h+Event]; Object
0x140008f1b  xor     edx, edx; WaitReason
0x140008f1d  call    cs:__imp_KeWaitForSingleObject
0x140008f24  nop     dword ptr [rax+rax+00h]
0x140008f29  mov     dword ptr [rsp+0B8h+var_68], 102h
0x140008f31  jmp     short loc_140008F37
0x140008f33  mov     dword ptr [rsp+0B8h+var_68], eax
0x140008f37  xor     edx, edx; PriorityBoost
0x140008f39  mov     rcx, rbx; Irp
0x140008f3c  call    cs:__imp_IofCompleteRequest
0x140008f43  nop     dword ptr [rax+rax+00h]
0x140008f48  mov     eax, dword ptr [rsp+0B8h+var_68]
0x140008f4c  add     rsp, 88h
0x140008f53  pop     r15
0x140008f55  pop     r14
0x140008f57  pop     rdi
0x140008f58  pop     rsi
0x140008f59  pop     rbp
0x140008f5a  pop     rbx
0x140008f5b  retn
0x140008f5d  mov     eax, 0C000009Ah
0x140008f62  add     rsp, 88h
0x140008f69  pop     r15
0x140008f6b  pop     r14
0x140008f6d  pop     rdi
0x140008f6e  pop     rsi
0x140008f6f  pop     rbp
0x140008f70  pop     rbx
0x140008f71  retn
```
