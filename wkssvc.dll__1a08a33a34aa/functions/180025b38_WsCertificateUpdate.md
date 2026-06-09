# WsCertificateUpdate

- ea: `0x180025b38`
- end: `0x180025c3e`
- name: `WsCertificateUpdate`
- size: `262`
- prototype: `__int64 __fastcall(PVOID InputBuffer, ULONG InputBufferLength)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180021ea8`
- `0x180022510`
- `0x180023930`

## callees

- `0x180005df0`
- `0x180025b38`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180025bff`
- `ntdll!NtWaitForSingleObject` at `0x180025bff`
- `ntdll!NtCreateEvent` at `0x180025b86`
- `ntdll!NtCreateEvent` at `0x180025b86`
- `ntdll!NtFsControlFile` at `0x180025bdd`
- `ntdll!NtFsControlFile` at `0x180025bdd`
- `ntdll!NtClose` at `0x180025c13`
- `ntdll!NtClose` at `0x180025c13`

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
0x180025b38  mov     rax, rsp
0x180025b3b  mov     [rax+8], rbx
0x180025b3f  mov     [rax+10h], rsi
0x180025b43  push    rdi
0x180025b44  sub     rsp, 60h
0x180025b48  mov     qword ptr [rax+18h], 0
0x180025b50  xorps   xmm0, xmm0
0x180025b53  mov     edi, edx
0x180025b55  mov     rsi, rcx
0x180025b58  movups  xmmword ptr [rax-18h], xmm0
0x180025b5c  cmp     edx, 90h
0x180025b62  jnb     short loc_180025B6E
0x180025b64  mov     eax, 57h ; 'W'
0x180025b69  jmp     loc_180025C2D
0x180025b6e  xor     r9d, r9d; EventType
0x180025b71  mov     [rsp+68h+InitialState], 0; InitialState
0x180025b76  xor     r8d, r8d; ObjectAttributes
0x180025b79  lea     rcx, [rsp+68h+EventHandle]; EventHandle
0x180025b81  mov     edx, 1F01FFh; DesiredAccess
0x180025b86  call    cs:__imp_NtCreateEvent
0x180025b8d  nop     dword ptr [rax+rax+00h]
0x180025b92  mov     ebx, eax
0x180025b94  test    eax, eax
0x180025b96  js      loc_180025C26
0x180025b9c  mov     rdx, [rsp+68h+EventHandle]; Event
0x180025ba4  lea     rax, [rsp+68h+IoStatusBlock]
0x180025ba9  mov     rcx, cs:WsRedirDeviceHandle; FileHandle
0x180025bb0  xor     r9d, r9d; ApcContext
0x180025bb3  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x180025bbb  xor     r8d, r8d; ApcRoutine
0x180025bbe  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x180025bc7  mov     [rsp+68h+InputBufferLength], edi; InputBufferLength
0x180025bcb  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x180025bd0  mov     [rsp+68h+FsControlCode], 1403E0h; FsControlCode
0x180025bd8  mov     qword ptr [rsp+68h+InitialState], rax; IoStatusBlock
0x180025bdd  call    cs:__imp_NtFsControlFile
0x180025be4  nop     dword ptr [rax+rax+00h]
0x180025be9  mov     ebx, eax
0x180025beb  cmp     eax, 103h
0x180025bf0  jnz     short loc_180025C0B
0x180025bf2  mov     rcx, [rsp+68h+EventHandle]; Handle
0x180025bfa  xor     r8d, r8d; Timeout
0x180025bfd  xor     edx, edx; Alertable
0x180025bff  call    cs:__imp_NtWaitForSingleObject
0x180025c06  nop     dword ptr [rax+rax+00h]
0x180025c0b  mov     rcx, [rsp+68h+EventHandle]; Handle
0x180025c13  call    cs:__imp_NtClose
0x180025c1a  nop     dword ptr [rax+rax+00h]
0x180025c1f  test    ebx, ebx
0x180025c21  cmovns  ebx, dword ptr [rsp+68h+IoStatusBlock]
0x180025c26  mov     ecx, ebx
0x180025c28  call    WsMapStatus
0x180025c2d  mov     rbx, [rsp+68h+arg_0]
0x180025c32  mov     rsi, [rsp+68h+arg_8]
0x180025c37  add     rsp, 60h
0x180025c3b  pop     rdi
0x180025c3c  retn
```
