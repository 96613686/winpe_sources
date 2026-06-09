# SsServerFsControlFile

- ea: `0x18000b300`
- end: `0x18000b3b3`
- name: `SsServerFsControlFile`
- size: `179`
- prototype: `NTSTATUS __fastcall(HANDLE FileHandle, PIO_STATUS_BLOCK IoStatusBlock, ULONG FsControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180020a50`
- `0x180020d74`
- `0x180022ff0`
- `0x18002b520`
- `0x18002e5a0`
- `0x180033f6c`

## callees

- `0x18000b300`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x18000b333`
- `ntdll!NtCreateEvent` at `0x18000b333`
- `ntdll!NtWaitForSingleObject` at `0x18000b3ab`
- `ntdll!NtWaitForSingleObject` at `0x18000b3ab`
- `ntdll!NtFsControlFile` at `0x18000b37c`
- `ntdll!NtFsControlFile` at `0x18000b37c`
- `ntdll!NtClose` at `0x18000b390`
- `ntdll!NtClose` at `0x18000b390`

## pseudocode

```c
NTSTATUS __fastcall SsServerFsControlFile(
        HANDLE FileHandle,
        PIO_STATUS_BLOCK IoStatusBlock,
        ULONG FsControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  NTSTATUS result; // eax
  NTSTATUS v12; // ebx
  void *EventHandle; // [rsp+50h] [rbp-38h] BYREF

  EventHandle = 0;
  result = NtCreateEvent(&EventHandle, 0x1F01FFu, 0, NotificationEvent, 0);
  if ( result >= 0 )
  {
    v12 = NtFsControlFile(
            FileHandle,
            EventHandle,
            0,
            0,
            IoStatusBlock,
            FsControlCode,
            InputBuffer,
            InputBufferLength,
            OutputBuffer,
            OutputBufferLength);
    if ( v12 == 259 )
      NtWaitForSingleObject(EventHandle, 0, 0);
    NtClose(EventHandle);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18000b300  push    rbx
0x18000b302  push    rbp
0x18000b303  push    rsi
0x18000b304  push    rdi
0x18000b305  sub     rsp, 68h
0x18000b309  mov     rbx, r9
0x18000b30c  mov     [rsp+88h+EventHandle], 0
0x18000b315  mov     edi, r8d
0x18000b318  mov     [rsp+88h+InitialState], 0; InitialState
0x18000b31d  mov     rsi, rdx
0x18000b320  mov     rbp, rcx
0x18000b323  xor     r9d, r9d; EventType
0x18000b326  lea     rcx, [rsp+88h+EventHandle]; EventHandle
0x18000b32b  xor     r8d, r8d; ObjectAttributes
0x18000b32e  mov     edx, 1F01FFh; DesiredAccess
0x18000b333  call    cs:__imp_NtCreateEvent
0x18000b339  test    eax, eax
0x18000b33b  js      short loc_18000B398
0x18000b33d  mov     eax, [rsp+88h+arg_30]
0x18000b344  xor     r9d, r9d; ApcContext
0x18000b347  mov     rdx, [rsp+88h+EventHandle]; Event
0x18000b34c  xor     r8d, r8d; ApcRoutine
0x18000b34f  mov     [rsp+88h+OutputBufferLength], eax; OutputBufferLength
0x18000b353  mov     rcx, rbp; FileHandle
0x18000b356  mov     rax, [rsp+88h+arg_28]
0x18000b35e  mov     [rsp+88h+OutputBuffer], rax; OutputBuffer
0x18000b363  mov     eax, [rsp+88h+arg_20]
0x18000b36a  mov     [rsp+88h+InputBufferLength], eax; InputBufferLength
0x18000b36e  mov     [rsp+88h+InputBuffer], rbx; InputBuffer
0x18000b373  mov     [rsp+88h+FsControlCode], edi; FsControlCode
0x18000b377  mov     qword ptr [rsp+88h+InitialState], rsi; IoStatusBlock
0x18000b37c  call    cs:__imp_NtFsControlFile
0x18000b382  mov     ebx, eax
0x18000b384  cmp     eax, 103h
0x18000b389  jz      short loc_18000B3A1
0x18000b38b  mov     rcx, [rsp+88h+EventHandle]; Handle
0x18000b390  call    cs:__imp_NtClose
0x18000b396  mov     eax, ebx
0x18000b398  add     rsp, 68h
0x18000b39c  pop     rdi
0x18000b39d  pop     rsi
0x18000b39e  pop     rbp
0x18000b39f  pop     rbx
0x18000b3a0  retn
0x18000b3a1  mov     rcx, [rsp+88h+EventHandle]; Handle
0x18000b3a6  xor     r8d, r8d; Timeout
0x18000b3a9  xor     edx, edx; Alertable
0x18000b3ab  call    cs:__imp_NtWaitForSingleObject
0x18000b3b1  jmp     short loc_18000B38B
```
