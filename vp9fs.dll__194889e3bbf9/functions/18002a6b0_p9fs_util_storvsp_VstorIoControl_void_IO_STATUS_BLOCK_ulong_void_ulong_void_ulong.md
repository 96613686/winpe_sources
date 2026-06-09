# p9fs::util::storvsp::VstorIoControl(void *,_IO_STATUS_BLOCK *,ulong,void *,ulong,void *,ulong)

- ea: `0x18002a6b0`
- end: `0x18002a7b7`
- name: `?VstorIoControl@storvsp@util@p9fs@@YAJPEAXPEAU_IO_STATUS_BLOCK@@K0K0K@Z`
- size: `263`
- prototype: `__int64 __fastcall(HANDLE FileHandle, PIO_STATUS_BLOCK IoStatusBlock, ULONG IoControlCode, PVOID InputBuffer, ULONG, PVOID, ULONG, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002a16c`
- `0x18002a63c`

## callees

- `0x180004120`
- `0x18002a6b0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a777`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a777`
- `ntdll!NtCreateEvent` at `0x18002a701`
- `ntdll!NtCreateEvent` at `0x18002a701`
- `ntdll!NtClose` at `0x18002a71f`
- `ntdll!NtClose` at `0x18002a78e`
- `ntdll!NtDeviceIoControlFile` at `0x18002a760`
- `ntdll!NtDeviceIoControlFile` at `0x18002a760`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::util::storvsp::VstorIoControl(
        HANDLE FileHandle,
        PIO_STATUS_BLOCK IoStatusBlock,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  NTSTATUS Status; // ebx
  void *EventHandle; // [rsp+50h] [rbp-48h] BYREF

  EventHandle = 0;
  Status = NtCreateEvent(&EventHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
  if ( Status >= 0 )
  {
    Status = NtDeviceIoControlFile(
               FileHandle,
               EventHandle,
               0,
               0,
               IoStatusBlock,
               IoControlCode,
               InputBuffer,
               InputBufferLength,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventHandle, 0xFFFFFFFF);
      Status = IoStatusBlock->Status;
    }
    if ( (char *)EventHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      ((void (*)(void))NtClose)();
  }
  else if ( (char *)EventHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    ((void (__fastcall *)(void *))NtClose)(EventHandle);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x18002a6b0  push    rbx
0x18002a6b2  push    rbp
0x18002a6b3  push    rsi
0x18002a6b4  push    rdi
0x18002a6b5  push    r14
0x18002a6b7  push    r15
0x18002a6b9  sub     rsp, 68h
0x18002a6bd  mov     rax, cs:__security_cookie
0x18002a6c4  xor     rax, rsp
0x18002a6c7  mov     [rsp+98h+var_40], rax
0x18002a6cc  mov     r14, r9
0x18002a6cf  mov     ebp, r8d
0x18002a6d2  mov     rdi, rdx
0x18002a6d5  mov     rsi, rcx
0x18002a6d8  mov     r15, [rsp+98h+arg_28]
0x18002a6e0  mov     [rsp+98h+EventHandle], 0
0x18002a6e9  mov     [rsp+98h+InitialState], 0; InitialState
0x18002a6ee  mov     r9d, 1; EventType
0x18002a6f4  xor     r8d, r8d; ObjectAttributes
0x18002a6f7  mov     edx, 1F0003h; DesiredAccess
0x18002a6fc  lea     rcx, [rsp+98h+EventHandle]; EventHandle
0x18002a701  call    cs:__imp_NtCreateEvent
0x18002a707  mov     ebx, eax
0x18002a709  mov     rdx, [rsp+98h+EventHandle]; Event
0x18002a70e  test    eax, eax
0x18002a710  jns     short loc_18002A72E
0x18002a712  lea     rcx, [rdx-1]
0x18002a716  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002a71a  ja      short loc_18002A79B
0x18002a71c  mov     rcx, rdx
0x18002a71f  mov     rax, cs:__imp_NtClose
0x18002a726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a72b  nop
0x18002a72c  jmp     short loc_18002A79B
0x18002a72e  mov     eax, [rsp+98h+arg_30]
0x18002a735  mov     [rsp+98h+OutputBufferLength], eax; OutputBufferLength
0x18002a739  mov     [rsp+98h+OutputBuffer], r15; OutputBuffer
0x18002a73e  mov     eax, [rsp+98h+arg_20]
0x18002a745  mov     [rsp+98h+InputBufferLength], eax; InputBufferLength
0x18002a749  mov     [rsp+98h+InputBuffer], r14; InputBuffer
0x18002a74e  mov     [rsp+98h+IoControlCode], ebp; IoControlCode
0x18002a752  mov     qword ptr [rsp+98h+InitialState], rdi; IoStatusBlock
0x18002a757  xor     r9d, r9d; ApcContext
0x18002a75a  xor     r8d, r8d; ApcRoutine
0x18002a75d  mov     rcx, rsi; FileHandle
0x18002a760  call    cs:__imp_NtDeviceIoControlFile
0x18002a766  mov     ebx, eax
0x18002a768  cmp     eax, 103h
0x18002a76d  jnz     short loc_18002A77F
0x18002a76f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a772  mov     rcx, [rsp+98h+EventHandle]; hHandle
0x18002a777  call    cs:__imp_WaitForSingleObject
0x18002a77d  mov     ebx, [rdi]
0x18002a77f  mov     rcx, [rsp+98h+EventHandle]
0x18002a784  lea     rax, [rcx-1]
0x18002a788  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a78c  ja      short loc_18002A79B
0x18002a78e  mov     rax, cs:__imp_NtClose
0x18002a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a79a  nop
0x18002a79b  mov     eax, ebx
0x18002a79d  mov     rcx, [rsp+98h+var_40]
0x18002a7a2  xor     rcx, rsp; StackCookie
0x18002a7a5  call    __security_check_cookie
0x18002a7aa  add     rsp, 68h
0x18002a7ae  pop     r15
0x18002a7b0  pop     r14
0x18002a7b2  pop     rdi
0x18002a7b3  pop     rsi
0x18002a7b4  pop     rbp
0x18002a7b5  pop     rbx
0x18002a7b6  retn
```
