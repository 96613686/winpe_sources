# Smb2ReadFile

- ea: `0x1400715fc`
- end: `0x140071771`
- name: `Smb2ReadFile`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE FileHandle, PVOID Buffer, ULONG Length, PLARGE_INTEGER ByteOffset, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140071778`
- `0x14007197c`
- `0x140072158`

## callees

- `0x1400224b8`
- `0x1400715fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140071722`
- `ntoskrnl!ZwClose` at `0x140071722`
- `ntoskrnl!ZwCreateEvent` at `0x14007165f`
- `ntoskrnl!ZwCreateEvent` at `0x14007165f`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140071700`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140071700`
- `ntoskrnl!ZwReadFile` at `0x1400716e2`
- `ntoskrnl!ZwReadFile` at `0x1400716e2`

## pseudocode

```c
__int64 __fastcall Smb2ReadFile(HANDLE FileHandle, PVOID Buffer, ULONG Length, PLARGE_INTEGER ByteOffset, _DWORD *a5)
{
  NTSTATUS Status; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  void *EventHandle; // [rsp+50h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-19h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  EventHandle = (void *)-1LL;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( Status < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v11 = 52;
LABEL_6:
      WPP_SF_d(v10->AttachedDevice, v11, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids, (unsigned int)Status);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  Status = ZwReadFile(FileHandle, EventHandle, 0, 0, &IoStatusBlock, Buffer, Length, ByteOffset, 0);
  if ( Status == 259 )
  {
    ZwWaitForSingleObject(EventHandle, 0, 0);
LABEL_9:
    Status = IoStatusBlock.Status;
    *a5 = IoStatusBlock.Information;
    goto LABEL_10;
  }
  if ( Status >= 0 )
    goto LABEL_9;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v11 = 53;
    goto LABEL_6;
  }
LABEL_10:
  if ( EventHandle != (void *)-1LL )
    ZwClose(EventHandle);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400715fc  push    rbp
0x1400715fe  push    rbx
0x1400715ff  push    rsi
0x140071600  push    rdi
0x140071601  push    r14
0x140071603  push    r15
0x140071605  lea     rbp, [rsp-27h]
0x14007160a  sub     rsp, 0A8h
0x140071611  xor     eax, eax
0x140071613  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14007161b  xorps   xmm0, xmm0
0x14007161e  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x140071622  mov     rdi, r9
0x140071625  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x140071629  mov     esi, r8d
0x14007162c  mov     [rsp+0D0h+InitialState], al; InitialState
0x140071630  mov     r14, rdx
0x140071633  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x14007163b  mov     r15, rcx
0x14007163e  mov     [rbp+4Fh+EventHandle], 0FFFFFFFFFFFFFFFFh
0x140071646  xor     r9d, r9d; EventType
0x140071649  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14007164d  mov     edx, 1F0003h; DesiredAccess
0x140071652  lea     rcx, [rbp+4Fh+EventHandle]; EventHandle
0x140071656  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x14007165a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14007165f  call    cs:__imp_ZwCreateEvent
0x140071666  nop     dword ptr [rax+rax+00h]
0x14007166b  mov     ebx, eax
0x14007166d  test    eax, eax
0x14007166f  jns     short loc_1400716B5
0x140071671  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071678  lea     rax, WPP_GLOBAL_Control
0x14007167f  cmp     rcx, rax
0x140071682  jz      loc_140071718
0x140071688  test    dword ptr [rcx+2Ch], 20000000h
0x14007168f  jz      loc_140071718
0x140071695  cmp     byte ptr [rcx+29h], 1
0x140071699  jb      short loc_140071718
0x14007169b  mov     edx, 34h ; '4'
0x1400716a0  mov     rcx, [rcx+18h]
0x1400716a4  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x1400716ab  mov     r9d, ebx
0x1400716ae  call    WPP_SF_d
0x1400716b3  jmp     short loc_140071718
0x1400716b5  mov     rdx, [rbp+4Fh+EventHandle]; Event
0x1400716b9  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1400716bd  mov     [rsp+0D0h+Key], 0; Key
0x1400716c6  xor     r9d, r9d; ApcContext
0x1400716c9  mov     [rsp+0D0h+ByteOffset], rdi; ByteOffset
0x1400716ce  xor     r8d, r8d; ApcRoutine
0x1400716d1  mov     [rsp+0D0h+Length], esi; Length
0x1400716d5  mov     rcx, r15; FileHandle
0x1400716d8  mov     [rsp+0D0h+Buffer], r14; Buffer
0x1400716dd  mov     qword ptr [rsp+0D0h+InitialState], rax; IoStatusBlock
0x1400716e2  call    cs:__imp_ZwReadFile
0x1400716e9  nop     dword ptr [rax+rax+00h]
0x1400716ee  mov     ebx, eax
0x1400716f0  cmp     eax, 103h
0x1400716f5  jnz     short loc_140071741
0x1400716f7  mov     rcx, [rbp+4Fh+EventHandle]; Handle
0x1400716fb  xor     r8d, r8d; Timeout
0x1400716fe  xor     edx, edx; Alertable
0x140071700  call    cs:__imp_ZwWaitForSingleObject
0x140071707  nop     dword ptr [rax+rax+00h]
0x14007170c  mov     rcx, [rbp+4Fh+arg_20]
0x140071710  mov     eax, dword ptr [rbp+4Fh+IoStatusBlock.Information]
0x140071713  mov     ebx, dword ptr [rbp+4Fh+IoStatusBlock]
0x140071716  mov     [rcx], eax
0x140071718  mov     rcx, [rbp+4Fh+EventHandle]; Handle
0x14007171c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140071720  jz      short loc_14007172E
0x140071722  call    cs:__imp_ZwClose
0x140071729  nop     dword ptr [rax+rax+00h]
0x14007172e  mov     eax, ebx
0x140071730  add     rsp, 0A8h
0x140071737  pop     r15
0x140071739  pop     r14
0x14007173b  pop     rdi
0x14007173c  pop     rsi
0x14007173d  pop     rbx
0x14007173e  pop     rbp
0x14007173f  retn
0x140071741  test    ebx, ebx
0x140071743  jns     short loc_14007170C
0x140071745  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007174c  lea     rax, WPP_GLOBAL_Control
0x140071753  cmp     rcx, rax
0x140071756  jz      short loc_140071718
0x140071758  test    dword ptr [rcx+2Ch], 20000000h
0x14007175f  jz      short loc_140071718
0x140071761  cmp     byte ptr [rcx+29h], 1
0x140071765  jb      short loc_140071718
0x140071767  mov     edx, 35h ; '5'
0x14007176c  jmp     loc_1400716A0
```
