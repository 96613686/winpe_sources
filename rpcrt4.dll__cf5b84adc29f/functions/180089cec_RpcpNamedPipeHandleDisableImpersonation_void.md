# RpcpNamedPipeHandleDisableImpersonation(void *)

- ea: `0x180089cec`
- end: `0x180089e0e`
- name: `?RpcpNamedPipeHandleDisableImpersonation@@YAJPEAX@Z`
- size: `290`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180089418`

## callees

- `0x180089cec`

## import_xrefs

- `ntdll!NtClose` at `0x180089dee`
- `ntdll!NtClose` at `0x180089dee`
- `ntdll!NtWaitForSingleObject` at `0x180089dc8`
- `ntdll!NtWaitForSingleObject` at `0x180089dc8`
- `ntdll!NtFsControlFile` at `0x180089dac`
- `ntdll!NtFsControlFile` at `0x180089dac`
- `ntdll!NtCreateEvent` at `0x180089d4a`
- `ntdll!NtCreateEvent` at `0x180089d4a`
- `ntdll!RtlNtStatusToDosError` at `0x180089d5c`
- `ntdll!RtlNtStatusToDosError` at `0x180089d5c`

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
0x180089cec  mov     [rsp-8+arg_0], rbx
0x180089cf1  push    rbp
0x180089cf2  lea     rbp, [rsp-57h]
0x180089cf7  sub     rsp, 90h
0x180089cfe  xorps   xmm0, xmm0
0x180089d01  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180089d09  mov     rbx, rcx
0x180089d0c  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x180089d14  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x180089d18  mov     [rbp+57h+EventHandle], 0
0x180089d20  xor     r9d, r9d; EventType
0x180089d23  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180089d2b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180089d2f  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180089d37  mov     edx, 1F0003h; DesiredAccess
0x180089d3c  mov     [rsp+90h+InitialState], 0; InitialState
0x180089d41  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180089d45  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180089d4a  call    cs:__imp_NtCreateEvent
0x180089d51  nop     dword ptr [rax+rax+00h]
0x180089d56  test    eax, eax
0x180089d58  jns     short loc_180089D6C
0x180089d5a  mov     ecx, eax; Status
0x180089d5c  call    cs:__imp_RtlNtStatusToDosError
0x180089d63  nop     dword ptr [rax+rax+00h]
0x180089d68  mov     ebx, eax
0x180089d6a  jmp     short loc_180089DE5
0x180089d6c  mov     rdx, [rbp+57h+EventHandle]; Event
0x180089d70  lea     rax, [rbp+57h+IoStatusBlock]
0x180089d74  mov     [rsp+90h+OutputBufferLength], 0; OutputBufferLength
0x180089d7c  xor     r9d, r9d; ApcContext
0x180089d7f  mov     [rsp+90h+OutputBuffer], 0; OutputBuffer
0x180089d88  xor     r8d, r8d; ApcRoutine
0x180089d8b  mov     [rsp+90h+InputBufferLength], 0; InputBufferLength
0x180089d93  mov     rcx, rbx; FileHandle
0x180089d96  mov     [rsp+90h+InputBuffer], 0; InputBuffer
0x180089d9f  mov     [rsp+90h+FsControlCode], 110044h; FsControlCode
0x180089da7  mov     qword ptr [rsp+90h+InitialState], rax; IoStatusBlock
0x180089dac  call    cs:__imp_NtFsControlFile
0x180089db3  nop     dword ptr [rax+rax+00h]
0x180089db8  cmp     eax, 103h
0x180089dbd  jnz     short loc_180089DDB
0x180089dbf  mov     rcx, [rbp+57h+EventHandle]; Handle
0x180089dc3  xor     r8d, r8d; Timeout
0x180089dc6  xor     edx, edx; Alertable
0x180089dc8  call    cs:__imp_NtWaitForSingleObject
0x180089dcf  nop     dword ptr [rax+rax+00h]
0x180089dd4  test    eax, eax
0x180089dd6  js      short loc_180089D5A
0x180089dd8  mov     eax, dword ptr [rbp+57h+IoStatusBlock]
0x180089ddb  test    eax, eax
0x180089ddd  js      loc_180089D5A
0x180089de3  xor     ebx, ebx
0x180089de5  mov     rcx, [rbp+57h+EventHandle]; Handle
0x180089de9  test    rcx, rcx
0x180089dec  jz      short loc_180089DFA
0x180089dee  call    cs:__imp_NtClose
0x180089df5  nop     dword ptr [rax+rax+00h]
0x180089dfa  mov     eax, ebx
0x180089dfc  mov     rbx, [rsp+90h+arg_0]
0x180089e04  add     rsp, 90h
0x180089e0b  pop     rbp
0x180089e0c  retn
```
