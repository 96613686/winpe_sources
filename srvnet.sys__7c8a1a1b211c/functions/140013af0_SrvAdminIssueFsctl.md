# SrvAdminIssueFsctl

- ea: `0x140013af0`
- end: `0x140013c4a`
- name: `SrvAdminIssueFsctl`
- size: `346`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140014284`
- `0x1400220a8`
- `0x1400221a0`
- `0x1400227cc`
- `0x140022e38`
- `0x140022f28`
- `0x140023134`
- `0x140025028`
- `0x1400251a0`
- `0x140026e90`
- `0x14004ca10`

## callees

- `0x140013af0`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140013b5c`
- `ntoskrnl!ZwOpenFile` at `0x140013b5c`
- `ntoskrnl!ZwCreateEvent` at `0x140013ba8`
- `ntoskrnl!ZwCreateEvent` at `0x140013ba8`
- `ntoskrnl!ZwFsControlFile` at `0x140013beb`
- `ntoskrnl!ZwFsControlFile` at `0x140013beb`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140013c09`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140013c09`
- `ntoskrnl!ZwClose` at `0x140013c1b`
- `ntoskrnl!ZwClose` at `0x140013c2b`
- `ntoskrnl!ZwClose` at `0x140013c1b`
- `ntoskrnl!ZwClose` at `0x140013c2b`

## pseudocode

```c
__int64 __fastcall SrvAdminIssueFsctl(
        struct _UNICODE_STRING *a1,
        ULONG a2,
        void *a3,
        ULONG a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PIO_STATUS_BLOCK IoStatusBlock,
        void *FileHandle)
{
  struct _IO_STATUS_BLOCK *v8; // rdi
  NTSTATUS Status; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES v15; // [rsp+80h] [rbp-29h] BYREF
  void *EventHandle; // [rsp+F0h] [rbp+47h] BYREF

  v8 = IoStatusBlock;
  ObjectAttributes.ObjectName = a1;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  EventHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwOpenFile(&FileHandle, 0x10000000u, &ObjectAttributes, IoStatusBlock, 7u, 0);
  if ( !Status )
  {
    *(_QWORD *)&v15.Length = 48;
    v15.RootDirectory = 0;
    v15.ObjectName = 0;
    *(_QWORD *)&v15.Attributes = 512;
    *(_OWORD *)&v15.SecurityDescriptor = 0;
    Status = ZwCreateEvent(&EventHandle, 0x10000000u, &v15, NotificationEvent, 0);
    if ( Status >= 0 )
    {
      Status = ZwFsControlFile(FileHandle, EventHandle, 0, 0, v8, a2, a3, a4, OutputBuffer, OutputBufferLength);
      if ( Status == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        Status = v8->Status;
      }
      ZwClose(EventHandle);
    }
    ZwClose(FileHandle);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140013af0  push    rbp
0x140013af2  push    rbx
0x140013af3  push    rsi
0x140013af4  push    rdi
0x140013af5  push    r14
0x140013af7  push    r15
0x140013af9  lea     rbp, [rsp-0Fh]
0x140013afe  sub     rsp, 0B8h
0x140013b05  mov     rdi, [rbp+37h+IoStatusBlock]
0x140013b09  xor     eax, eax
0x140013b0b  mov     esi, r9d
0x140013b0e  mov     [rbp+37h+ObjectAttributes.ObjectName], rcx
0x140013b12  mov     r14, r8
0x140013b15  mov     [rsp+0E0h+OpenOptions], eax; OpenOptions
0x140013b19  mov     r15d, edx
0x140013b1c  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140013b24  xorps   xmm0, xmm0
0x140013b27  mov     [rbp+37h+FileHandle], 0
0x140013b2f  mov     r9, rdi; IoStatusBlock
0x140013b32  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x140013b3a  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x140013b3e  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 240h
0x140013b46  mov     edx, 10000000h; DesiredAccess
0x140013b4b  mov     [rbp+37h+EventHandle], rax
0x140013b4f  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x140013b53  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x140013b57  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013b5c  call    cs:__imp_ZwOpenFile
0x140013b63  nop     dword ptr [rax+rax+00h]
0x140013b68  mov     ebx, eax
0x140013b6a  test    eax, eax
0x140013b6c  jnz     loc_140013C37
0x140013b72  xor     eax, eax
0x140013b74  mov     qword ptr [rbp+37h+var_60.Length], 30h ; '0'
0x140013b7c  xorps   xmm0, xmm0
0x140013b7f  mov     [rbp+37h+var_60.RootDirectory], rax
0x140013b83  xor     r9d, r9d; EventType
0x140013b86  mov     [rbp+37h+var_60.ObjectName], rax
0x140013b8a  lea     r8, [rbp+37h+var_60]; ObjectAttributes
0x140013b8e  mov     byte ptr [rsp+0E0h+ShareAccess], al; InitialState
0x140013b92  mov     edx, 10000000h; DesiredAccess
0x140013b97  mov     qword ptr [rbp+37h+var_60.Attributes], 200h
0x140013b9f  lea     rcx, [rbp+37h+EventHandle]; EventHandle
0x140013ba3  movdqu  xmmword ptr [rbp+37h+var_60.SecurityDescriptor], xmm0
0x140013ba8  call    cs:__imp_ZwCreateEvent
0x140013baf  nop     dword ptr [rax+rax+00h]
0x140013bb4  mov     ebx, eax
0x140013bb6  test    eax, eax
0x140013bb8  js      short loc_140013C27
0x140013bba  mov     eax, [rbp+37h+arg_28]
0x140013bbd  xor     r9d, r9d; ApcContext
0x140013bc0  mov     rdx, [rbp+37h+EventHandle]; Event
0x140013bc4  xor     r8d, r8d; ApcRoutine
0x140013bc7  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x140013bcb  mov     [rsp+0E0h+OutputBufferLength], eax; OutputBufferLength
0x140013bcf  mov     rax, [rbp+37h+arg_20]
0x140013bd3  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x140013bd8  mov     [rsp+0E0h+InputBufferLength], esi; InputBufferLength
0x140013bdc  mov     [rsp+0E0h+InputBuffer], r14; InputBuffer
0x140013be1  mov     [rsp+0E0h+OpenOptions], r15d; FsControlCode
0x140013be6  mov     qword ptr [rsp+0E0h+ShareAccess], rdi; IoStatusBlock
0x140013beb  call    cs:__imp_ZwFsControlFile
0x140013bf2  nop     dword ptr [rax+rax+00h]
0x140013bf7  mov     ebx, eax
0x140013bf9  cmp     eax, 103h
0x140013bfe  jnz     short loc_140013C17
0x140013c00  mov     rcx, [rbp+37h+EventHandle]; Handle
0x140013c04  xor     r8d, r8d; Timeout
0x140013c07  xor     edx, edx; Alertable
0x140013c09  call    cs:__imp_ZwWaitForSingleObject
0x140013c10  nop     dword ptr [rax+rax+00h]
0x140013c15  mov     ebx, [rdi]
0x140013c17  mov     rcx, [rbp+37h+EventHandle]; Handle
0x140013c1b  call    cs:__imp_ZwClose
0x140013c22  nop     dword ptr [rax+rax+00h]
0x140013c27  mov     rcx, [rbp+37h+FileHandle]; Handle
0x140013c2b  call    cs:__imp_ZwClose
0x140013c32  nop     dword ptr [rax+rax+00h]
0x140013c37  mov     eax, ebx
0x140013c39  add     rsp, 0B8h
0x140013c40  pop     r15
0x140013c42  pop     r14
0x140013c44  pop     rdi
0x140013c45  pop     rsi
0x140013c46  pop     rbx
0x140013c47  pop     rbp
0x140013c48  retn
```
