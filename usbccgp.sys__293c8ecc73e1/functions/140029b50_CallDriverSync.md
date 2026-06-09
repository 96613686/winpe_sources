# CallDriverSync

- ea: `0x140029b50`
- end: `0x140029da3`
- name: `CallDriverSync`
- size: `595`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `8`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140023414`
- `0x1400249d4`
- `0x140028440`
- `0x140028f7c`
- `0x14002977c`
- `0x14002990c`
- `0x140029a38`
- `0x140029b30`

## callees

- `0x140005940`
- `0x14000a6cc`
- `0x14000fa04`
- `0x140013d4c`
- `0x140029b50`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140029b88`
- `ntoskrnl!KeInitializeEvent` at `0x140029b88`
- `ntoskrnl!IofCallDriver` at `0x140029bbc`
- `ntoskrnl!IofCallDriver` at `0x140029bbc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029c00`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029c54`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029d92`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029c00`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029c54`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029d92`
- `ntoskrnl!DbgPrint` at `0x140029ce7`
- `ntoskrnl!DbgPrint` at `0x140029d43`
- `ntoskrnl!DbgPrint` at `0x140029ce7`
- `ntoskrnl!DbgPrint` at `0x140029d43`
- `ntoskrnl!IoCancelIrp` at `0x140029cf6`
- `ntoskrnl!IoCancelIrp` at `0x140029cf6`

## string_xrefs

- `0x140029c18`: `event (waiting for sent irp to complete)`
- `0x140029d16`: `event (waiting for canceled irp to complete)`
- `0x140029d34`: `\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes for %s to be signalled\n`

## pseudocode

```c
__int64 __fastcall CallDriverSync(PDEVICE_OBJECT DeviceObject, PIRP Irp, char a3, struct _DEVICE_OBJECT *a4)
{
  NTSTATUS v8; // ebx
  int v9; // r15d
  int v10; // ebx
  NTSTATUS i; // eax
  int v12; // edx
  int v13; // r8d
  int v15; // edx
  int v16; // edx
  int v17; // r8d
  int Timeout; // [rsp+20h] [rbp-50h]
  union _LARGE_INTEGER v19; // [rsp+40h] [rbp-30h] BYREF
  union _LARGE_INTEGER v20; // [rsp+48h] [rbp-28h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-20h] BYREF

  v19.QuadPart = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  SetCompletionRoutine(g_RecorderLog, a4, Irp, USBD_SyncCompletionRoutine, &Event);
  v8 = IofCallDriver(DeviceObject, Irp);
  if ( v8 != 259 )
    goto LABEL_9;
  if ( a3 )
  {
    v19.QuadPart = -50000000;
    v8 = KeWaitForSingleObject(&Event, Executive, 0, 0, &v19);
    if ( v8 == 258 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(g_RecorderLog, v15, 8, 10, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, 136);
      }
      DbgPrint("USBCCGP: CallDriverSync timed out after %d ms\n", 5000);
      if ( IoCancelIrp(Irp) )
      {
        v8 = -1073741823;
        Irp->IoStatus.Status = -1073741823;
      }
      WaitForSignal(&Event);
    }
LABEL_9:
    if ( v8 < 0 )
      return (unsigned int)v8;
    return (unsigned int)Irp->IoStatus.Status;
  }
  v9 = g_RecorderLog;
  v10 = 0;
  v20.QuadPart = -600000000;
  for ( i = KeWaitForSingleObject(&Event, Executive, 0, 0, &v20);
        i == 258;
        i = KeWaitForSingleObject(&Event, Executive, 0, 0, &v20) )
  {
    DbgPrint(
      "\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes for %s to be signalled\n",
      KeGetCurrentThread(),
      ++v10,
      "event (waiting for sent irp to complete)");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qds(
        v9,
        v16,
        v17,
        61,
        Timeout,
        (char)KeGetCurrentThread(),
        v10,
        (__int64)"event (waiting for sent irp to complete)");
  }
  if ( i < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dqs(
      v9,
      v12,
      v13,
      62,
      Timeout,
      i,
      (char)KeGetCurrentThread(),
      (__int64)"event (waiting for sent irp to complete)");
  return (unsigned int)Irp->IoStatus.Status;
}

```

## disassembly

```asm
0x140029b50  push    rbp
0x140029b52  push    rbx
0x140029b53  push    rsi
0x140029b54  push    rdi
0x140029b55  push    r12
0x140029b57  push    r14
0x140029b59  push    r15
0x140029b5b  mov     rbp, rsp
0x140029b5e  sub     rsp, 70h
0x140029b62  xor     eax, eax
0x140029b64  mov     sil, r8b
0x140029b67  mov     r14, rdx
0x140029b6a  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x140029b6e  mov     rdi, rcx
0x140029b71  mov     qword ptr [rbp+var_30], rax
0x140029b75  xorps   xmm0, xmm0
0x140029b78  lea     rcx, [rbp+Event]; Event
0x140029b7c  xor     r8d, r8d; State
0x140029b7f  xor     edx, edx; Type
0x140029b81  movups  xmmword ptr [rbp+Event.Header.___u0], xmm0
0x140029b85  mov     rbx, r9
0x140029b88  call    cs:__imp_KeInitializeEvent
0x140029b8f  nop     dword ptr [rax+rax+00h]
0x140029b94  mov     rcx, cs:g_RecorderLog
0x140029b9b  lea     rax, [rbp+Event]
0x140029b9f  lea     r9, USBD_SyncCompletionRoutine
0x140029ba6  mov     [rsp+70h+Timeout], rax
0x140029bab  mov     r8, r14
0x140029bae  mov     rdx, rbx
0x140029bb1  call    SetCompletionRoutine
0x140029bb6  mov     rdx, r14; Irp
0x140029bb9  mov     rcx, rdi; DeviceObject
0x140029bbc  call    cs:__imp_IofCallDriver
0x140029bc3  nop     dword ptr [rax+rax+00h]
0x140029bc8  mov     ebx, eax
0x140029bca  cmp     eax, 103h
0x140029bcf  jnz     loc_140029C6B
0x140029bd5  xor     r9d, r9d; Alertable
0x140029bd8  lea     rcx, [rbp+Event]; Object
0x140029bdc  xor     r8d, r8d; WaitMode
0x140029bdf  xor     edx, edx; WaitReason
0x140029be1  test    sil, sil
0x140029be4  jnz     short loc_140029C43
0x140029be6  mov     r15, cs:g_RecorderLog
0x140029bed  lea     rax, [rbp+var_28]
0x140029bf1  xor     ebx, ebx
0x140029bf3  mov     [rsp+70h+Timeout], rax; Timeout
0x140029bf8  mov     qword ptr [rbp+var_28], 0FFFFFFFFDC3CBA00h
0x140029c00  call    cs:__imp_KeWaitForSingleObject
0x140029c07  nop     dword ptr [rax+rax+00h]
0x140029c0c  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029c13  mov     esi, 102h
0x140029c18  lea     r12, aEventWaitingFo; "event (waiting for sent irp to complete"...
0x140029c1f  mov     ecx, eax
0x140029c21  cmp     eax, esi
0x140029c23  jz      loc_140029D2B
0x140029c29  test    eax, eax
0x140029c2b  js      short loc_140029C71
0x140029c2d  mov     ebx, [r14+30h]
0x140029c31  mov     eax, ebx
0x140029c33  add     rsp, 70h
0x140029c37  pop     r15
0x140029c39  pop     r14
0x140029c3b  pop     r12
0x140029c3d  pop     rdi
0x140029c3e  pop     rsi
0x140029c3f  pop     rbx
0x140029c40  pop     rbp
0x140029c41  retn
0x140029c43  lea     rax, [rbp+var_30]
0x140029c47  mov     qword ptr [rbp+var_30], 0FFFFFFFFFD050F80h
0x140029c4f  mov     [rsp+70h+Timeout], rax; Timeout
0x140029c54  call    cs:__imp_KeWaitForSingleObject
0x140029c5b  nop     dword ptr [rax+rax+00h]
0x140029c60  mov     esi, 102h
0x140029c65  mov     ebx, eax
0x140029c67  cmp     eax, esi
0x140029c69  jz      short loc_140029CA1
0x140029c6b  test    ebx, ebx
0x140029c6d  jns     short loc_140029C2D
0x140029c6f  jmp     short loc_140029C31
0x140029c71  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140029c78  jz      short loc_140029C2D
0x140029c7a  mov     rax, gs:188h
0x140029c83  mov     r9d, 3Eh ; '>'
0x140029c89  mov     [rsp+70h+var_38], r12
0x140029c8e  mov     [rsp+70h+var_40], rax
0x140029c93  mov     dword ptr [rsp+70h+var_48], ecx
0x140029c97  mov     rcx, r15
0x140029c9a  call    WPP_RECORDER_SF_dqs
0x140029c9f  jmp     short loc_140029C2D
0x140029ca1  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029ca8  mov     esi, 1388h
0x140029cad  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140029cb4  jz      short loc_140029CDE
0x140029cb6  mov     rcx, cs:g_RecorderLog
0x140029cbd  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140029cc4  mov     r9d, 0Ah
0x140029cca  mov     dword ptr [rsp+70h+var_48], esi
0x140029cce  mov     dl, 2
0x140029cd0  mov     [rsp+70h+Timeout], rax
0x140029cd5  lea     r8d, [r9-2]
0x140029cd9  call    WPP_RECORDER_SF_d
0x140029cde  mov     edx, esi
0x140029ce0  lea     rcx, aUsbccgpCalldri; "USBCCGP: CallDriverSync timed out after"...
0x140029ce7  call    cs:__imp_DbgPrint
0x140029cee  nop     dword ptr [rax+rax+00h]
0x140029cf3  mov     rcx, r14; Irp
0x140029cf6  call    cs:__imp_IoCancelIrp
0x140029cfd  nop     dword ptr [rax+rax+00h]
0x140029d02  test    al, al
0x140029d04  jz      short loc_140029D0F
0x140029d06  mov     ebx, 0C0000001h
0x140029d0b  mov     [r14+30h], ebx
0x140029d0f  mov     r8, cs:g_RecorderLog
0x140029d16  lea     rdx, aEventWaitingFo_1; "event (waiting for canceled irp to comp"...
0x140029d1d  lea     rcx, [rbp+Event]; Object
0x140029d21  call    WaitForSignal
0x140029d26  jmp     loc_140029C6B
0x140029d2b  mov     rdx, gs:188h
0x140029d34  lea     rcx, aUsbccgpWatchdo; "\nUSBCCGP Watchdog: Thread 0x%p has wai"...
0x140029d3b  inc     ebx
0x140029d3d  mov     r9, r12
0x140029d40  mov     r8d, ebx
0x140029d43  call    cs:__imp_DbgPrint
0x140029d4a  nop     dword ptr [rax+rax+00h]
0x140029d4f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140029d56  jz      short loc_140029D7D
0x140029d58  mov     rax, gs:188h
0x140029d61  mov     r9d, 3Dh ; '='
0x140029d67  mov     [rsp+70h+var_38], r12
0x140029d6c  mov     rcx, r15
0x140029d6f  mov     dword ptr [rsp+70h+var_40], ebx
0x140029d73  mov     [rsp+70h+var_48], rax
0x140029d78  call    WPP_RECORDER_SF_qds
0x140029d7d  lea     rax, [rbp+var_28]
0x140029d81  xor     r9d, r9d; Alertable
0x140029d84  xor     r8d, r8d; WaitMode
0x140029d87  mov     [rsp+70h+Timeout], rax; Timeout
0x140029d8c  xor     edx, edx; WaitReason
0x140029d8e  lea     rcx, [rbp+Event]; Object
0x140029d92  call    cs:__imp_KeWaitForSingleObject
0x140029d99  nop     dword ptr [rax+rax+00h]
0x140029d9e  jmp     loc_140029C1F
```
