# WimpFSFGetCngExtensions

- ea: `0x140029708`
- end: `0x140029871`
- name: `WimpFSFGetCngExtensions`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002e8cc`

## callees

- `0x140029708`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140029805`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029805`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400297bc`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400297bc`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002975a`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002975a`
- `ntoskrnl!IofCallDriver` at `0x1400297db`
- `ntoskrnl!IofCallDriver` at `0x1400297db`
- `ntoskrnl!KeInitializeEvent` at `0x140029779`
- `ntoskrnl!KeInitializeEvent` at `0x140029779`
- `ntoskrnl!ObfDereferenceObject` at `0x140029851`
- `ntoskrnl!ObfDereferenceObject` at `0x140029851`

## pseudocode

```c
__int64 WimpFSFGetCngExtensions()
{
  NTSTATUS DeviceObjectPointer; // ebx
  IRP *v1; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-30h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-20h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+90h] [rbp+10h] BYREF
  __int64 OutputBuffer; // [rsp+98h] [rbp+18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp+20h] BYREF

  DeviceObject = 0;
  FileObject = 0;
  OutputBuffer = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(
                          (PUNICODE_STRING)&g_CngDeviceName,
                          0x1F01FFu,
                          &FileObject,
                          &DeviceObject);
  if ( DeviceObjectPointer >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v1 = IoBuildDeviceIoControlRequest(0x390064u, DeviceObject, 0, 0, &OutputBuffer, 8u, 0, &Event, &IoStatusBlock);
    if ( !v1 )
    {
      DeviceObjectPointer = -1073741823;
      goto LABEL_14;
    }
    DeviceObjectPointer = IofCallDriver(DeviceObject, v1);
    if ( DeviceObjectPointer == 259 )
    {
      DeviceObjectPointer = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( DeviceObjectPointer < 0 )
        goto LABEL_14;
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer >= 0 )
    {
      if ( OutputBuffer && *(_DWORD *)OutputBuffer && *(_QWORD *)(OutputBuffer + 8) && *(_QWORD *)(OutputBuffer + 16) )
        g_WimIntegrityCngExtensions = OutputBuffer;
      else
        DeviceObjectPointer = -1073741637;
    }
  }
LABEL_14:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x140029708  mov     [rsp-8+arg_18], rbx
0x14002970d  mov     [rsp-8+DeviceObject], rcx
0x140029712  push    rbp
0x140029713  mov     rbp, rsp
0x140029716  sub     rsp, 80h
0x14002971d  xorps   xmm0, xmm0
0x140029720  mov     [rbp+DeviceObject], 0
0x140029728  xor     eax, eax
0x14002972a  mov     [rbp+FileObject], 0
0x140029732  lea     r9, [rbp+DeviceObject]; DeviceObject
0x140029736  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14002973a  lea     r8, [rbp+FileObject]; FileObject
0x14002973e  mov     [rbp+arg_8], 0
0x140029746  mov     edx, 1F01FFh; DesiredAccess
0x14002974b  lea     rcx, g_CngDeviceName; ObjectName
0x140029752  movups  xmmword ptr [rbp+Event.Header], xmm0
0x140029756  movups  xmmword ptr [rbp+var_30], xmm0
0x14002975a  call    cs:__imp_IoGetDeviceObjectPointer
0x140029761  nop     dword ptr [rax+rax+00h]
0x140029766  mov     ebx, eax
0x140029768  test    eax, eax
0x14002976a  js      loc_140029848
0x140029770  xor     r8d, r8d; State
0x140029773  lea     rcx, [rbp+Event]; Event
0x140029777  xor     edx, edx; Type
0x140029779  call    cs:__imp_KeInitializeEvent
0x140029780  nop     dword ptr [rax+rax+00h]
0x140029785  mov     rdx, [rbp+DeviceObject]; DeviceObject
0x140029789  lea     rax, [rbp+var_30]
0x14002978d  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x140029792  xor     r9d, r9d; InputBufferLength
0x140029795  lea     rax, [rbp+Event]
0x140029799  xor     r8d, r8d; InputBuffer
0x14002979c  mov     [rsp+80h+var_48], rax; Event
0x1400297a1  mov     ecx, 390064h; IoControlCode
0x1400297a6  mov     [rsp+80h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400297ab  lea     rax, [rbp+arg_8]
0x1400297af  mov     [rsp+80h+OutputBufferLength], 8; OutputBufferLength
0x1400297b7  mov     [rsp+80h+OutputBuffer], rax; OutputBuffer
0x1400297bc  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400297c3  nop     dword ptr [rax+rax+00h]
0x1400297c8  test    rax, rax
0x1400297cb  jnz     short loc_1400297D4
0x1400297cd  mov     ebx, 0C0000001h
0x1400297d2  jmp     short loc_140029848
0x1400297d4  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x1400297d8  mov     rdx, rax; Irp
0x1400297db  call    cs:__imp_IofCallDriver
0x1400297e2  nop     dword ptr [rax+rax+00h]
0x1400297e7  mov     ebx, eax
0x1400297e9  cmp     eax, 103h
0x1400297ee  jnz     short loc_14002981A
0x1400297f0  xor     r9d, r9d; Alertable
0x1400297f3  mov     [rsp+80h+OutputBuffer], 0; Timeout
0x1400297fc  xor     r8d, r8d; WaitMode
0x1400297ff  lea     rcx, [rbp+Event]; Object
0x140029803  xor     edx, edx; WaitReason
0x140029805  call    cs:__imp_KeWaitForSingleObject
0x14002980c  nop     dword ptr [rax+rax+00h]
0x140029811  mov     ebx, eax
0x140029813  test    eax, eax
0x140029815  js      short loc_140029848
0x140029817  mov     ebx, dword ptr [rbp+var_30]
0x14002981a  test    ebx, ebx
0x14002981c  js      short loc_140029848
0x14002981e  mov     rax, [rbp+arg_8]
0x140029822  test    rax, rax
0x140029825  jz      short loc_140029843
0x140029827  cmp     dword ptr [rax], 1
0x14002982a  jb      short loc_140029843
0x14002982c  cmp     qword ptr [rax+8], 0
0x140029831  jz      short loc_140029843
0x140029833  cmp     qword ptr [rax+10h], 0
0x140029838  jz      short loc_140029843
0x14002983a  mov     cs:g_WimIntegrityCngExtensions, rax
0x140029841  jmp     short loc_140029848
0x140029843  mov     ebx, 0C00000BBh
0x140029848  mov     rcx, [rbp+FileObject]; Object
0x14002984c  test    rcx, rcx
0x14002984f  jz      short loc_14002985D
0x140029851  call    cs:__imp_ObfDereferenceObject
0x140029858  nop     dword ptr [rax+rax+00h]
0x14002985d  mov     eax, ebx
0x14002985f  mov     rbx, [rsp+80h+arg_18]
0x140029867  add     rsp, 80h
0x14002986e  pop     rbp
0x14002986f  retn
```
