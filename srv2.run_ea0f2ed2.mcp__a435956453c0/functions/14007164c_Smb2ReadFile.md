# Smb2ReadFile

- ea: `0x14007164c`
- end: `0x1400717c1`
- name: `Smb2ReadFile`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE FileHandle, PVOID Buffer, ULONG Length, PLARGE_INTEGER ByteOffset, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400717c8`
- `0x1400719cc`
- `0x1400721a8`

## callees

- `0x1400224b8`
- `0x14007164c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140071772`
- `ntoskrnl!ZwClose` at `0x140071772`
- `ntoskrnl!ZwCreateEvent` at `0x1400716af`
- `ntoskrnl!ZwCreateEvent` at `0x1400716af`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140071750`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140071750`
- `ntoskrnl!ZwReadFile` at `0x140071732`
- `ntoskrnl!ZwReadFile` at `0x140071732`

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
      WPP_SF_d(v10->AttachedDevice, v11, &WPP_8e7cd37454fb33500a68697303cffebe_Traceguids, (unsigned int)Status);
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
0x14007164c  push    rbp
0x14007164e  push    rbx
0x14007164f  push    rsi
0x140071650  push    rdi
0x140071651  push    r14
0x140071653  push    r15
0x140071655  lea     rbp, [rsp-27h]
0x14007165a  sub     rsp, 0A8h
0x140071661  xor     eax, eax
0x140071663  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14007166b  xorps   xmm0, xmm0
0x14007166e  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x140071672  mov     rdi, r9
0x140071675  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x140071679  mov     esi, r8d
0x14007167c  mov     [rsp+0D0h+InitialState], al; InitialState
0x140071680  mov     r14, rdx
0x140071683  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x14007168b  mov     r15, rcx
0x14007168e  mov     [rbp+4Fh+EventHandle], 0FFFFFFFFFFFFFFFFh
0x140071696  xor     r9d, r9d; EventType
0x140071699  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14007169d  mov     edx, 1F0003h; DesiredAccess
0x1400716a2  lea     rcx, [rbp+4Fh+EventHandle]; EventHandle
0x1400716a6  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1400716aa  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400716af  call    cs:__imp_ZwCreateEvent
0x1400716b6  nop     dword ptr [rax+rax+00h]
0x1400716bb  mov     ebx, eax
0x1400716bd  test    eax, eax
0x1400716bf  jns     short loc_140071705
0x1400716c1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400716c8  lea     rax, WPP_GLOBAL_Control
0x1400716cf  cmp     rcx, rax
0x1400716d2  jz      loc_140071768
0x1400716d8  test    dword ptr [rcx+2Ch], 20000000h
0x1400716df  jz      loc_140071768
0x1400716e5  cmp     byte ptr [rcx+29h], 1
0x1400716e9  jb      short loc_140071768
0x1400716eb  mov     edx, 34h ; '4'
0x1400716f0  mov     rcx, [rcx+18h]
0x1400716f4  lea     r8, WPP_8e7cd37454fb33500a68697303cffebe_Traceguids
0x1400716fb  mov     r9d, ebx
0x1400716fe  call    WPP_SF_d
0x140071703  jmp     short loc_140071768
0x140071705  mov     rdx, [rbp+4Fh+EventHandle]; Event
0x140071709  lea     rax, [rbp+4Fh+IoStatusBlock]
0x14007170d  mov     [rsp+0D0h+Key], 0; Key
0x140071716  xor     r9d, r9d; ApcContext
0x140071719  mov     [rsp+0D0h+ByteOffset], rdi; ByteOffset
0x14007171e  xor     r8d, r8d; ApcRoutine
0x140071721  mov     [rsp+0D0h+Length], esi; Length
0x140071725  mov     rcx, r15; FileHandle
0x140071728  mov     [rsp+0D0h+Buffer], r14; Buffer
0x14007172d  mov     qword ptr [rsp+0D0h+InitialState], rax; IoStatusBlock
0x140071732  call    cs:__imp_ZwReadFile
0x140071739  nop     dword ptr [rax+rax+00h]
0x14007173e  mov     ebx, eax
0x140071740  cmp     eax, 103h
0x140071745  jnz     short loc_140071791
0x140071747  mov     rcx, [rbp+4Fh+EventHandle]; Handle
0x14007174b  xor     r8d, r8d; Timeout
0x14007174e  xor     edx, edx; Alertable
0x140071750  call    cs:__imp_ZwWaitForSingleObject
0x140071757  nop     dword ptr [rax+rax+00h]
0x14007175c  mov     rcx, [rbp+4Fh+arg_20]
0x140071760  mov     eax, dword ptr [rbp+4Fh+IoStatusBlock.Information]
0x140071763  mov     ebx, dword ptr [rbp+4Fh+IoStatusBlock]
0x140071766  mov     [rcx], eax
0x140071768  mov     rcx, [rbp+4Fh+EventHandle]; Handle
0x14007176c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140071770  jz      short loc_14007177E
0x140071772  call    cs:__imp_ZwClose
0x140071779  nop     dword ptr [rax+rax+00h]
0x14007177e  mov     eax, ebx
0x140071780  add     rsp, 0A8h
0x140071787  pop     r15
0x140071789  pop     r14
0x14007178b  pop     rdi
0x14007178c  pop     rsi
0x14007178d  pop     rbx
0x14007178e  pop     rbp
0x14007178f  retn
0x140071791  test    ebx, ebx
0x140071793  jns     short loc_14007175C
0x140071795  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007179c  lea     rax, WPP_GLOBAL_Control
0x1400717a3  cmp     rcx, rax
0x1400717a6  jz      short loc_140071768
0x1400717a8  test    dword ptr [rcx+2Ch], 20000000h
0x1400717af  jz      short loc_140071768
0x1400717b1  cmp     byte ptr [rcx+29h], 1
0x1400717b5  jb      short loc_140071768
0x1400717b7  mov     edx, 35h ; '5'
0x1400717bc  jmp     loc_1400716F0
```
