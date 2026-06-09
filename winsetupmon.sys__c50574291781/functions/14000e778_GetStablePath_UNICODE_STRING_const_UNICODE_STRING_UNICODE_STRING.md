# GetStablePath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14000e778`
- end: `0x14000eb03`
- name: `?GetStablePath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z`
- size: `907`
- prototype: `int(const struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x14000eb0c`

## callees

- `0x140008138`
- `0x14000e1d0`
- `0x14000e778`
- `0x14000f684`
- `0x14000f900`

## import_xrefs

- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000e851`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000e851`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ea0d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ea48`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ea0d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ea48`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e9f2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e9f2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ea96`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ea96`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eaab`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eac0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eaab`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eac0`
- `ntoskrnl!KeInitializeEvent` at `0x14000e891`
- `ntoskrnl!KeInitializeEvent` at `0x14000e891`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eada`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eada`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e9c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e9c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e92e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e92e`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000e878`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000e878`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000e8d4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000e8d4`
- `ntoskrnl!IofCallDriver` at `0x14000e904`
- `ntoskrnl!IofCallDriver` at `0x14000e904`
- `ntoskrnl!RtlStringFromGUID` at `0x14000e98b`
- `ntoskrnl!RtlStringFromGUID` at `0x14000e98b`

## string_xrefs

- `0x14000e7ff`: `WinSetupMon::GetStablePath: Failed GetNtPath [%wZ] (0x%08X)`
- `0x14000e867`: `WinSetupMon::GetStablePath: Failed IoGetDeviceObjectPointer [%wZ] (0x%08X)`
- `0x14000e8e5`: `WinSetupMon::GetStablePath: Failed IoBuildDeviceIoControlRequest`
- `0x14000e970`: `WinSetupMon::GetStablePath: Failed IoCallDriver (0x%08X)`
- `0x14000e9a0`: `WinSetupMon::GetStablePath: Failed RtlStringFromGUID (0x%08X)`
- `0x14000e9dc`: `WinSetupMon::GetStablePath: Failed to allocate StablePath buffer`
- `0x14000ea23`: `WinSetupMon::GetStablePath: Failed RtlAppendUnicodeStringToString [%wZ] (0x%08X)`

## pseudocode

```c
__int64 __fastcall GetStablePath(
        const struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  int NtPath; // eax
  NTSTATUS Status; // ebx
  NTSTATUS DeviceObjectPointer; // eax
  IRP *v9; // rax
  NTSTATUS v10; // eax
  unsigned __int16 v11; // ax
  wchar_t *PoolWithTag; // rax
  NTSTATUS appended; // eax
  UNICODE_STRING *p_Source; // r8
  unsigned __int16 Length; // ax
  wchar_t *Buffer; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-59h] BYREF
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-51h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+70h] [rbp-39h] BYREF
  PVOID P[2]; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+90h] [rbp-19h] BYREF
  struct _KEVENT Event; // [rsp+A0h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp+Fh] BYREF
  GUID Guid; // [rsp+C8h] [rbp+1Fh] BYREF

  FileObject = 0;
  DeviceObject = 0;
  a2->Buffer = 0;
  *(_OWORD *)P = 0;
  ObjectName = 0;
  Source = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  Guid = 0;
  GuidString = 0;
  NtPath = GetNtPath(a1, (PUNICODE_STRING)P, &ObjectName);
  Status = NtPath;
  if ( NtPath < 0 )
  {
    if ( NtPath != -1073741637 )
      WriteLog(0, "WinSetupMon::GetStablePath: Failed GetNtPath [%wZ] (0x%08X)", a1, (unsigned int)NtPath);
    goto LABEL_30;
  }
  Source.Length = LOWORD(P[0]) - ObjectName.Length;
  if ( LOWORD(P[0]) != ObjectName.Length )
  {
    Source.MaximumLength = WORD1(P[0]) - ObjectName.Length;
    Source.Buffer = (wchar_t *)((char *)P[1] + 2 * ((unsigned __int64)ObjectName.Length >> 1));
  }
  DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 0x80u, &FileObject, &DeviceObject);
  Status = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    WriteLog(
      0,
      "WinSetupMon::GetStablePath: Failed IoGetDeviceObjectPointer [%wZ] (0x%08X)",
      &ObjectName,
      (unsigned int)DeviceObjectPointer);
    goto LABEL_30;
  }
  DeviceObject = IoGetAttachedDeviceReference(FileObject->DeviceObject);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v9 = IoBuildDeviceIoControlRequest(0x4D0018u, DeviceObject, 0, 0, &Guid, 0x10u, 0, &Event, &IoStatusBlock);
  if ( !v9 )
  {
    WriteLog(0, "WinSetupMon::GetStablePath: Failed IoBuildDeviceIoControlRequest");
LABEL_11:
    Status = -1073741670;
    goto LABEL_30;
  }
  Status = IofCallDriver(DeviceObject, v9);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( (unsigned int)(Status + 0x3FFFFFFF) <= 1 || Status == -1073741808 )
  {
    Status = -1073741637;
    goto LABEL_30;
  }
  if ( Status < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( Status != -1073741637 )
      WriteLog(0, "WinSetupMon::GetStablePath: Failed IoCallDriver (0x%08X)", (unsigned int)Status);
    goto LABEL_30;
  }
  v10 = RtlStringFromGUID(&Guid, &GuidString);
  Status = v10;
  if ( v10 < 0 )
  {
    WriteLog(0, "WinSetupMon::GetStablePath: Failed RtlStringFromGUID (0x%08X)", (unsigned int)v10);
    goto LABEL_30;
  }
  v11 = Source.Length + GuidString.Length + 20;
  a2->MaximumLength = v11;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v11, 0x6E6D7377u);
  a2->Buffer = PoolWithTag;
  if ( !PoolWithTag )
  {
    WriteLog(0, "WinSetupMon::GetStablePath: Failed to allocate StablePath buffer");
    goto LABEL_11;
  }
  RtlCopyUnicodeString(a2, &String1);
  a2->Length -= 2;
  appended = RtlAppendUnicodeStringToString(a2, &GuidString);
  Status = appended;
  if ( appended >= 0 )
  {
    a3->Buffer = a2->Buffer;
    Length = a2->Length;
    a3->MaximumLength = a2->Length;
    a3->Length = Length;
    appended = RtlAppendUnicodeStringToString(a2, &Source);
    Status = appended;
    if ( appended >= 0 )
      goto LABEL_33;
    p_Source = &Source;
  }
  else
  {
    p_Source = &GuidString;
  }
  WriteLog(
    0,
    "WinSetupMon::GetStablePath: Failed RtlAppendUnicodeStringToString [%wZ] (0x%08X)",
    p_Source,
    (unsigned int)appended);
LABEL_30:
  Buffer = a2->Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0x6E6D7377u);
  *a2 = 0;
  *a3 = 0;
LABEL_33:
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( DeviceObject )
    ObfDereferenceObject(DeviceObject);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000e778  push    rbp
0x14000e77a  push    rbx
0x14000e77b  push    rsi
0x14000e77c  push    rdi
0x14000e77d  push    r14
0x14000e77f  lea     rbp, [rsp-37h]
0x14000e784  sub     rsp, 0E0h
0x14000e78b  mov     rax, cs:__security_cookie
0x14000e792  xor     rax, rsp
0x14000e795  mov     [rbp+57h+var_28], rax
0x14000e799  xorps   xmm0, xmm0
0x14000e79c  mov     [rbp+57h+FileObject], 0
0x14000e7a4  xor     eax, eax
0x14000e7a6  mov     [rbp+57h+DeviceObject], 0
0x14000e7ae  xorps   xmm1, xmm1
0x14000e7b1  mov     [rdx+8], rax
0x14000e7b5  mov     rsi, r8
0x14000e7b8  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14000e7bc  mov     rdi, rdx
0x14000e7bf  lea     r8, [rbp+57h+ObjectName]; struct _UNICODE_STRING *
0x14000e7c3  lea     rdx, [rbp+57h+P]; DestinationString
0x14000e7c7  mov     r14, rcx
0x14000e7ca  movups  xmmword ptr [rbp+57h+P], xmm0
0x14000e7ce  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm1
0x14000e7d2  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000e7d6  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14000e7da  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x14000e7de  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x14000e7e2  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x14000e7e6  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000e7eb  mov     ebx, eax
0x14000e7ed  test    eax, eax
0x14000e7ef  jns     short loc_14000E815
0x14000e7f1  cmp     eax, 0C00000BBh
0x14000e7f6  jz      loc_14000EA65
0x14000e7fc  mov     r8, r14
0x14000e7ff  lea     rdx, aWinsetupmonGet_7; "WinSetupMon::GetStablePath: Failed GetN"...
0x14000e806  mov     r9d, eax
0x14000e809  xor     ecx, ecx
0x14000e80b  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e810  jmp     loc_14000EA65
0x14000e815  movzx   eax, word ptr [rbp+57h+P]
0x14000e819  movzx   ecx, [rbp+57h+ObjectName.Length]
0x14000e81d  sub     ax, cx
0x14000e820  mov     [rbp+57h+Source.Length], ax
0x14000e824  jz      short loc_14000E840
0x14000e826  movzx   eax, word ptr [rbp+57h+P+2]
0x14000e82a  sub     ax, cx
0x14000e82d  mov     [rbp+57h+Source.MaximumLength], ax
0x14000e831  mov     rax, [rbp+57h+P+8]
0x14000e835  shr     rcx, 1
0x14000e838  lea     rcx, [rax+rcx*2]
0x14000e83c  mov     [rbp+57h+Source.Buffer], rcx
0x14000e840  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x14000e844  mov     edx, 80h; DesiredAccess
0x14000e849  lea     r8, [rbp+57h+FileObject]; FileObject
0x14000e84d  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x14000e851  call    cs:__imp_IoGetDeviceObjectPointer
0x14000e858  nop     dword ptr [rax+rax+00h]
0x14000e85d  mov     ebx, eax
0x14000e85f  test    eax, eax
0x14000e861  jns     short loc_14000E870
0x14000e863  lea     r8, [rbp+57h+ObjectName]
0x14000e867  lea     rdx, aWinsetupmonGet_4; "WinSetupMon::GetStablePath: Failed IoGe"...
0x14000e86e  jmp     short loc_14000E806
0x14000e870  mov     rcx, [rbp+57h+FileObject]
0x14000e874  mov     rcx, [rcx+8]; DeviceObject
0x14000e878  call    cs:__imp_IoGetAttachedDeviceReference
0x14000e87f  nop     dword ptr [rax+rax+00h]
0x14000e884  xor     r8d, r8d; State
0x14000e887  lea     rcx, [rbp+57h+Event]; Event
0x14000e88b  xor     edx, edx; Type
0x14000e88d  mov     [rbp+57h+DeviceObject], rax
0x14000e891  call    cs:__imp_KeInitializeEvent
0x14000e898  nop     dword ptr [rax+rax+00h]
0x14000e89d  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x14000e8a1  lea     rax, [rbp+57h+var_48]
0x14000e8a5  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x14000e8aa  xor     r9d, r9d; InputBufferLength
0x14000e8ad  lea     rax, [rbp+57h+Event]
0x14000e8b1  xor     r8d, r8d; InputBuffer
0x14000e8b4  mov     [rsp+100h+var_C8], rax; Event
0x14000e8b9  mov     ecx, 4D0018h; IoControlCode
0x14000e8be  mov     [rsp+100h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14000e8c3  lea     rax, [rbp+57h+Guid]
0x14000e8c7  mov     [rsp+100h+OutputBufferLength], 10h; OutputBufferLength
0x14000e8cf  mov     [rsp+100h+OutputBuffer], rax; OutputBuffer
0x14000e8d4  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000e8db  nop     dword ptr [rax+rax+00h]
0x14000e8e0  test    rax, rax
0x14000e8e3  jnz     short loc_14000E8FD
0x14000e8e5  lea     rdx, aWinsetupmonGet_10; "WinSetupMon::GetStablePath: Failed IoBu"...
0x14000e8ec  xor     ecx, ecx
0x14000e8ee  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e8f3  mov     ebx, 0C000009Ah
0x14000e8f8  jmp     loc_14000EA65
0x14000e8fd  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14000e901  mov     rdx, rax; Irp
0x14000e904  call    cs:__imp_IofCallDriver
0x14000e90b  nop     dword ptr [rax+rax+00h]
0x14000e910  mov     ebx, eax
0x14000e912  cmp     eax, 103h
0x14000e917  jnz     short loc_14000E93D
0x14000e919  xor     r9d, r9d; Alertable
0x14000e91c  mov     [rsp+100h+OutputBuffer], 0; Timeout
0x14000e925  xor     r8d, r8d; WaitMode
0x14000e928  lea     rcx, [rbp+57h+Event]; Object
0x14000e92c  xor     edx, edx; WaitReason
0x14000e92e  call    cs:__imp_KeWaitForSingleObject
0x14000e935  nop     dword ptr [rax+rax+00h]
0x14000e93a  mov     ebx, dword ptr [rbp+57h+var_48]
0x14000e93d  lea     eax, [rbx+3FFFFFFFh]
0x14000e943  cmp     eax, 1
0x14000e946  jbe     loc_14000EA60
0x14000e94c  cmp     ebx, 0C0000010h
0x14000e952  jz      loc_14000EA60
0x14000e958  test    ebx, ebx
0x14000e95a  jns     short loc_14000E983
0x14000e95c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000e961  cmp     ebx, 0C00000BBh
0x14000e967  jz      loc_14000EA65
0x14000e96d  mov     r8d, ebx
0x14000e970  lea     rdx, aWinsetupmonGet_1; "WinSetupMon::GetStablePath: Failed IoCa"...
0x14000e977  xor     ecx, ecx
0x14000e979  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000e97e  jmp     loc_14000EA65
0x14000e983  lea     rdx, [rbp+57h+GuidString]; GuidString
0x14000e987  lea     rcx, [rbp+57h+Guid]; Guid
0x14000e98b  call    cs:__imp_RtlStringFromGUID
0x14000e992  nop     dword ptr [rax+rax+00h]
0x14000e997  mov     ebx, eax
0x14000e999  test    eax, eax
0x14000e99b  jns     short loc_14000E9A9
0x14000e99d  mov     r8d, eax
0x14000e9a0  lea     rdx, aWinsetupmonGet_6; "WinSetupMon::GetStablePath: Failed RtlS"...
0x14000e9a7  jmp     short loc_14000E977
0x14000e9a9  movzx   eax, [rbp+57h+GuidString.Length]
0x14000e9ad  mov     ecx, 1; PoolType
0x14000e9b2  add     ax, 14h
0x14000e9b6  mov     r8d, 6E6D7377h; Tag
0x14000e9bc  add     ax, [rbp+57h+Source.Length]
0x14000e9c0  movzx   edx, ax; NumberOfBytes
0x14000e9c3  mov     [rdi+2], dx
0x14000e9c7  call    cs:__imp_ExAllocatePoolWithTag
0x14000e9ce  nop     dword ptr [rax+rax+00h]
0x14000e9d3  mov     [rdi+8], rax
0x14000e9d7  test    rax, rax
0x14000e9da  jnz     short loc_14000E9E8
0x14000e9dc  lea     rdx, aWinsetupmonGet_16; "WinSetupMon::GetStablePath: Failed to a"...
0x14000e9e3  jmp     loc_14000E8EC
0x14000e9e8  lea     rdx, String1; SourceString
0x14000e9ef  mov     rcx, rdi; DestinationString
0x14000e9f2  call    cs:__imp_RtlCopyUnicodeString
0x14000e9f9  nop     dword ptr [rax+rax+00h]
0x14000e9fe  mov     eax, 0FFFEh
0x14000ea03  lea     rdx, [rbp+57h+GuidString]; Source
0x14000ea07  add     [rdi], ax
0x14000ea0a  mov     rcx, rdi; Destination
0x14000ea0d  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000ea14  nop     dword ptr [rax+rax+00h]
0x14000ea19  mov     ebx, eax
0x14000ea1b  test    eax, eax
0x14000ea1d  jns     short loc_14000EA2F
0x14000ea1f  lea     r8, [rbp+57h+GuidString]
0x14000ea23  lea     rdx, aWinsetupmonGet_8; "WinSetupMon::GetStablePath: Failed RtlA"...
0x14000ea2a  jmp     loc_14000E806
0x14000ea2f  mov     rax, [rdi+8]
0x14000ea33  lea     rdx, [rbp+57h+Source]; Source
0x14000ea37  mov     [rsi+8], rax
0x14000ea3b  mov     rcx, rdi; Destination
0x14000ea3e  movzx   eax, word ptr [rdi]
0x14000ea41  mov     [rsi+2], ax
0x14000ea45  mov     [rsi], ax
0x14000ea48  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000ea4f  nop     dword ptr [rax+rax+00h]
0x14000ea54  mov     ebx, eax
0x14000ea56  test    eax, eax
0x14000ea58  jns     short loc_14000EA8B
0x14000ea5a  lea     r8, [rbp+57h+Source]
0x14000ea5e  jmp     short loc_14000EA23
0x14000ea60  mov     ebx, 0C00000BBh
0x14000ea65  mov     rcx, [rdi+8]; P
0x14000ea69  test    rcx, rcx
0x14000ea6c  jz      short loc_14000EA7F
0x14000ea6e  mov     edx, 6E6D7377h; Tag
0x14000ea73  call    cs:__imp_ExFreePoolWithTag
0x14000ea7a  nop     dword ptr [rax+rax+00h]
0x14000ea7f  xorps   xmm0, xmm0
0x14000ea82  xorps   xmm1, xmm1
0x14000ea85  movups  xmmword ptr [rdi], xmm0
0x14000ea88  movups  xmmword ptr [rsi], xmm1
0x14000ea8b  cmp     [rbp+57h+GuidString.Buffer], 0
0x14000ea90  jz      short loc_14000EAA2
0x14000ea92  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14000ea96  call    cs:__imp_RtlFreeUnicodeString
0x14000ea9d  nop     dword ptr [rax+rax+00h]
0x14000eaa2  mov     rcx, [rbp+57h+DeviceObject]; Object
0x14000eaa6  test    rcx, rcx
0x14000eaa9  jz      short loc_14000EAB7
0x14000eaab  call    cs:__imp_ObfDereferenceObject
0x14000eab2  nop     dword ptr [rax+rax+00h]
0x14000eab7  mov     rcx, [rbp+57h+FileObject]; Object
0x14000eabb  test    rcx, rcx
0x14000eabe  jz      short loc_14000EACC
0x14000eac0  call    cs:__imp_ObfDereferenceObject
0x14000eac7  nop     dword ptr [rax+rax+00h]
0x14000eacc  mov     rcx, [rbp+57h+P+8]; P
0x14000ead0  test    rcx, rcx
0x14000ead3  jz      short loc_14000EAE6
0x14000ead5  mov     edx, 6E6D7377h; Tag
0x14000eada  call    cs:__imp_ExFreePoolWithTag
0x14000eae1  nop     dword ptr [rax+rax+00h]
0x14000eae6  mov     eax, ebx
0x14000eae8  mov     rcx, [rbp+57h+var_28]
0x14000eaec  xor     rcx, rsp; StackCookie
0x14000eaef  call    __security_check_cookie
0x14000eaf4  add     rsp, 0E0h
0x14000eafb  pop     r14
0x14000eafd  pop     rdi
0x14000eafe  pop     rsi
0x14000eaff  pop     rbx
0x14000eb00  pop     rbp
0x14000eb01  retn
```
