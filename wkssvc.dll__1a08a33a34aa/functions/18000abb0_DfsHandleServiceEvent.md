# DfsHandleServiceEvent

- ea: `0x18000abb0`
- end: `0x18000acda`
- name: `DfsHandleServiceEvent`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a920`
- `0x18000a9d0`

## callees

- `0x18000abb0`
- `0x18000b190`
- `0x18000b2dc`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000ac19`
- `ntdll!NtOpenFile` at `0x18000ac19`
- `ntdll!NtFsControlFile` at `0x18000ac88`
- `ntdll!NtFsControlFile` at `0x18000ac88`
- `ntdll!NtClose` at `0x18000aca5`
- `ntdll!NtClose` at `0x18000aca5`

## pseudocode

```c
NTSTATUS __fastcall DfsHandleServiceEvent(int a1)
{
  NTSTATUS result; // eax
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v5; // [rsp+60h] [rbp-38h] BYREF
  int InputBuffer; // [rsp+A8h] [rbp+10h] BYREF
  HANDLE FileHandle; // [rsp+B0h] [rbp+18h] BYREF

  FileHandle = 0;
  InputBuffer = 0;
  v5.RootDirectory = 0;
  v5.ObjectName = (PUNICODE_STRING)LocalDfsName;
  *(_QWORD *)&v5.Length = 48;
  *(_QWORD *)&v5.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&v5.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0x100002u, &v5, &IoStatusBlock, 7u, 0x20u);
  if ( result >= 0 )
  {
    result = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
    {
      InputBuffer = a1;
      IoStatusBlock = 0;
      Status = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x69FF4u, &InputBuffer, 4u, 0, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
      NtClose(FileHandle);
      if ( !Status && (unsigned int)WsInAWorkgroup() != 1 )
        WsRefreshDfsDomainCache();
      return Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000abb0  mov     r11, rsp
0x18000abb3  mov     [r11+8], rbx
0x18000abb7  push    rdi
0x18000abb8  sub     rsp, 90h
0x18000abbf  xor     edi, edi
0x18000abc1  mov     [rsp+98h+OpenOptions], 20h ; ' '; OpenOptions
0x18000abc9  xorps   xmm0, xmm0
0x18000abcc  mov     [r11+18h], rdi
0x18000abd0  mov     ebx, ecx
0x18000abd2  mov     [r11+10h], edi
0x18000abd6  lea     rax, LocalDfsName; "\"\""
0x18000abdd  mov     [r11-30h], rdi
0x18000abe1  lea     rcx, [r11+18h]; FileHandle
0x18000abe5  mov     [r11-28h], rax
0x18000abe9  lea     r9, [r11-48h]; IoStatusBlock
0x18000abed  mov     qword ptr [r11-38h], 30h ; '0'
0x18000abf5  lea     r8, [r11-38h]; ObjectAttributes
0x18000abf9  mov     qword ptr [r11-20h], 40h ; '@'
0x18000ac01  mov     edx, 100002h; DesiredAccess
0x18000ac06  mov     [rsp+98h+ShareAccess], 7; ShareAccess
0x18000ac0e  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x18000ac13  movdqu  xmmword ptr [r11-18h], xmm0
0x18000ac19  call    cs:__imp_NtOpenFile
0x18000ac20  nop     dword ptr [rax+rax+00h]
0x18000ac25  test    eax, eax
0x18000ac27  js      loc_18000ACC1
0x18000ac2d  mov     eax, dword ptr [rsp+98h+IoStatusBlock]
0x18000ac31  test    eax, eax
0x18000ac33  js      loc_18000ACC1
0x18000ac39  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x18000ac41  lea     rax, [rsp+98h+arg_8]
0x18000ac49  mov     [rsp+98h+OutputBufferLength], edi; OutputBufferLength
0x18000ac4d  xorps   xmm0, xmm0
0x18000ac50  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18000ac55  xor     r9d, r9d; ApcContext
0x18000ac58  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x18000ac60  xor     r8d, r8d; ApcRoutine
0x18000ac63  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x18000ac68  xor     edx, edx; Event
0x18000ac6a  lea     rax, [rsp+98h+IoStatusBlock]
0x18000ac6f  mov     [rsp+98h+OpenOptions], 69FF4h; FsControlCode
0x18000ac77  mov     qword ptr [rsp+98h+ShareAccess], rax; IoStatusBlock
0x18000ac7c  mov     [rsp+98h+arg_8], ebx
0x18000ac83  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x18000ac88  call    cs:__imp_NtFsControlFile
0x18000ac8f  nop     dword ptr [rax+rax+00h]
0x18000ac94  mov     rcx, [rsp+98h+FileHandle]; Handle
0x18000ac9c  test    eax, eax
0x18000ac9e  mov     ebx, eax
0x18000aca0  cmovns  ebx, dword ptr [rsp+98h+IoStatusBlock]
0x18000aca5  call    cs:__imp_NtClose
0x18000acac  nop     dword ptr [rax+rax+00h]
0x18000acb1  test    ebx, ebx
0x18000acb3  jnz     short loc_18000ACBF
0x18000acb5  call    WsInAWorkgroup
0x18000acba  cmp     eax, 1
0x18000acbd  jnz     short loc_18000ACD3
0x18000acbf  mov     eax, ebx
0x18000acc1  mov     rbx, [rsp+98h+arg_0]
0x18000acc9  add     rsp, 90h
0x18000acd0  pop     rdi
0x18000acd1  retn
0x18000acd3  call    WsRefreshDfsDomainCache
0x18000acd8  jmp     short loc_18000ACBF
```
