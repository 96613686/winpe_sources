# WsCertificateUpdate

- ea: `0x180024018`
- end: `0x180024101`
- name: `WsCertificateUpdate`
- size: `233`
- prototype: `__int64 __fastcall(PVOID InputBuffer, ULONG InputBufferLength)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800206ec`
- `0x180020d14`
- `0x180021ff0`

## callees

- `0x180005a60`
- `0x180024018`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1800240cf`
- `ntdll!NtWaitForSingleObject` at `0x1800240cf`
- `ntdll!NtCreateEvent` at `0x180024066`
- `ntdll!NtCreateEvent` at `0x180024066`
- `ntdll!NtFsControlFile` at `0x1800240b3`
- `ntdll!NtFsControlFile` at `0x1800240b3`
- `ntdll!NtClose` at `0x1800240dd`
- `ntdll!NtClose` at `0x1800240dd`

## pseudocode

```c
__int64 __fastcall WsCertificateUpdate(PVOID InputBuffer, ULONG InputBufferLength)
{
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+18h] BYREF

  EventHandle = 0;
  IoStatusBlock = 0;
  if ( InputBufferLength < 0x90 )
    return 87;
  Status = NtCreateEvent(&EventHandle, 0x1F01FFu, 0, NotificationEvent, 0);
  if ( Status >= 0 )
  {
    Status = NtFsControlFile(
               WsRedirDeviceHandle,
               EventHandle,
               0,
               0,
               &IoStatusBlock,
               0x1403E0u,
               InputBuffer,
               InputBufferLength,
               0,
               0);
    if ( Status == 259 )
      NtWaitForSingleObject(EventHandle, 0, 0);
    NtClose(EventHandle);
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
  }
  return WsMapStatus((unsigned int)Status);
}

```

## disassembly

```asm
0x180024018  mov     rax, rsp
0x18002401b  mov     [rax+8], rbx
0x18002401f  mov     [rax+10h], rsi
0x180024023  push    rdi
0x180024024  sub     rsp, 60h
0x180024028  mov     qword ptr [rax+18h], 0
0x180024030  xorps   xmm0, xmm0
0x180024033  mov     edi, edx
0x180024035  mov     rsi, rcx
0x180024038  movups  xmmword ptr [rax-18h], xmm0
0x18002403c  cmp     edx, 90h
0x180024042  jnb     short loc_18002404E
0x180024044  mov     eax, 57h ; 'W'
0x180024049  jmp     loc_1800240F1
0x18002404e  xor     r9d, r9d; EventType
0x180024051  mov     [rsp+68h+InitialState], 0; InitialState
0x180024056  xor     r8d, r8d; ObjectAttributes
0x180024059  lea     rcx, [rsp+68h+EventHandle]; EventHandle
0x180024061  mov     edx, 1F01FFh; DesiredAccess
0x180024066  call    cs:__imp_NtCreateEvent
0x18002406c  mov     ebx, eax
0x18002406e  test    eax, eax
0x180024070  js      short loc_1800240EA
0x180024072  mov     rdx, [rsp+68h+EventHandle]; Event
0x18002407a  lea     rax, [rsp+68h+IoStatusBlock]
0x18002407f  mov     rcx, cs:WsRedirDeviceHandle; FileHandle
0x180024086  xor     r9d, r9d; ApcContext
0x180024089  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x180024091  xor     r8d, r8d; ApcRoutine
0x180024094  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x18002409d  mov     [rsp+68h+InputBufferLength], edi; InputBufferLength
0x1800240a1  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x1800240a6  mov     [rsp+68h+FsControlCode], 1403E0h; FsControlCode
0x1800240ae  mov     qword ptr [rsp+68h+InitialState], rax; IoStatusBlock
0x1800240b3  call    cs:__imp_NtFsControlFile
0x1800240b9  mov     ebx, eax
0x1800240bb  cmp     eax, 103h
0x1800240c0  jnz     short loc_1800240D5
0x1800240c2  mov     rcx, [rsp+68h+EventHandle]; Handle
0x1800240ca  xor     r8d, r8d; Timeout
0x1800240cd  xor     edx, edx; Alertable
0x1800240cf  call    cs:__imp_NtWaitForSingleObject
0x1800240d5  mov     rcx, [rsp+68h+EventHandle]; Handle
0x1800240dd  call    cs:__imp_NtClose
0x1800240e3  test    ebx, ebx
0x1800240e5  cmovns  ebx, dword ptr [rsp+68h+IoStatusBlock]
0x1800240ea  mov     ecx, ebx
0x1800240ec  call    WsMapStatus
0x1800240f1  mov     rbx, [rsp+68h+arg_0]
0x1800240f6  mov     rsi, [rsp+68h+arg_8]
0x1800240fb  add     rsp, 60h
0x1800240ff  pop     rdi
0x180024100  retn
```
