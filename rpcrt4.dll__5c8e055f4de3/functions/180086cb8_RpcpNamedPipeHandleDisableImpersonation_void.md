# RpcpNamedPipeHandleDisableImpersonation(void *)

- ea: `0x180086cb8`
- end: `0x180086db7`
- name: `?RpcpNamedPipeHandleDisableImpersonation@@YAJPEAX@Z`
- size: `255`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180086414`

## callees

- `0x180086cb8`

## import_xrefs

- `ntdll!NtClose` at `0x180086d9e`
- `ntdll!NtClose` at `0x180086d9e`
- `ntdll!NtWaitForSingleObject` at `0x180086d82`
- `ntdll!NtWaitForSingleObject` at `0x180086d82`
- `ntdll!NtFsControlFile` at `0x180086d6c`
- `ntdll!NtFsControlFile` at `0x180086d6c`
- `ntdll!NtCreateEvent` at `0x180086d16`
- `ntdll!NtCreateEvent` at `0x180086d16`
- `ntdll!RtlNtStatusToDosError` at `0x180086d22`
- `ntdll!RtlNtStatusToDosError` at `0x180086d22`

## pseudocode

```c
__int64 __fastcall RpcpNamedPipeHandleDisableImpersonation(HANDLE FileHandle)
{
  int Status; // eax
  ULONG v3; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  void *EventHandle; // [rsp+A8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  EventHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  IoStatusBlock = 0;
  Status = NtCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( Status < 0 )
    goto LABEL_2;
  Status = NtFsControlFile(FileHandle, EventHandle, 0, 0, &IoStatusBlock, 0x110044u, 0, 0, 0, 0);
  if ( Status == 259 )
  {
    Status = NtWaitForSingleObject(EventHandle, 0, 0);
    if ( Status < 0 )
    {
LABEL_2:
      v3 = RtlNtStatusToDosError(Status);
      goto LABEL_8;
    }
    Status = IoStatusBlock.Status;
  }
  if ( Status < 0 )
    goto LABEL_2;
  v3 = 0;
LABEL_8:
  if ( EventHandle )
    NtClose(EventHandle);
  return v3;
}

```

## disassembly

```asm
0x180086cb8  mov     [rsp-8+arg_0], rbx
0x180086cbd  push    rbp
0x180086cbe  lea     rbp, [rsp-57h]
0x180086cc3  sub     rsp, 90h
0x180086cca  xorps   xmm0, xmm0
0x180086ccd  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180086cd5  mov     rbx, rcx
0x180086cd8  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x180086ce0  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x180086ce4  mov     [rbp+57h+EventHandle], 0
0x180086cec  xor     r9d, r9d; EventType
0x180086cef  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180086cf7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180086cfb  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180086d03  mov     edx, 1F0003h; DesiredAccess
0x180086d08  mov     [rsp+90h+InitialState], 0; InitialState
0x180086d0d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180086d11  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180086d16  call    cs:__imp_NtCreateEvent
0x180086d1c  test    eax, eax
0x180086d1e  jns     short loc_180086D2C
0x180086d20  mov     ecx, eax; Status
0x180086d22  call    cs:__imp_RtlNtStatusToDosError
0x180086d28  mov     ebx, eax
0x180086d2a  jmp     short loc_180086D95
0x180086d2c  mov     rdx, [rbp+57h+EventHandle]; Event
0x180086d30  lea     rax, [rbp+57h+IoStatusBlock]
0x180086d34  mov     [rsp+90h+OutputBufferLength], 0; OutputBufferLength
0x180086d3c  xor     r9d, r9d; ApcContext
0x180086d3f  mov     [rsp+90h+OutputBuffer], 0; OutputBuffer
0x180086d48  xor     r8d, r8d; ApcRoutine
0x180086d4b  mov     [rsp+90h+InputBufferLength], 0; InputBufferLength
0x180086d53  mov     rcx, rbx; FileHandle
0x180086d56  mov     [rsp+90h+InputBuffer], 0; InputBuffer
0x180086d5f  mov     [rsp+90h+FsControlCode], 110044h; FsControlCode
0x180086d67  mov     qword ptr [rsp+90h+InitialState], rax; IoStatusBlock
0x180086d6c  call    cs:__imp_NtFsControlFile
0x180086d72  cmp     eax, 103h
0x180086d77  jnz     short loc_180086D8F
0x180086d79  mov     rcx, [rbp+57h+EventHandle]; Handle
0x180086d7d  xor     r8d, r8d; Timeout
0x180086d80  xor     edx, edx; Alertable
0x180086d82  call    cs:__imp_NtWaitForSingleObject
0x180086d88  test    eax, eax
0x180086d8a  js      short loc_180086D20
0x180086d8c  mov     eax, dword ptr [rbp+57h+IoStatusBlock]
0x180086d8f  test    eax, eax
0x180086d91  js      short loc_180086D20
0x180086d93  xor     ebx, ebx
0x180086d95  mov     rcx, [rbp+57h+EventHandle]; Handle
0x180086d99  test    rcx, rcx
0x180086d9c  jz      short loc_180086DA4
0x180086d9e  call    cs:__imp_NtClose
0x180086da4  mov     eax, ebx
0x180086da6  mov     rbx, [rsp+90h+arg_0]
0x180086dae  add     rsp, 90h
0x180086db5  pop     rbp
0x180086db6  retn
```
