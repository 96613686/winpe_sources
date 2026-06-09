# TpmEnsureWindowsAIKDirExists(ushort const *,ushort const *,void *)

- ea: `0x14001647c`
- end: `0x14001661f`
- name: `?TpmEnsureWindowsAIKDirExists@@YAJPEBG0PEAX@Z`
- size: `419`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001a95c`

## callees

- `0x14001647c`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400164df`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14001653b`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400164df`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14001653b`
- `ntoskrnl!ZwCreateFile` at `0x1400165d9`
- `ntoskrnl!ZwCreateFile` at `0x1400165d9`
- `ntoskrnl!ZwClose` at `0x1400165f0`
- `ntoskrnl!ZwClose` at `0x1400165f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016558`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016558`

## pseudocode

```c
__int64 __fastcall TpmEnsureWindowsAIKDirExists(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  WCHAR *v3; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  unsigned __int64 retaddr; // [rsp+F8h] [rbp+5Fh]
  unsigned __int64 v14; // [rsp+118h] [rbp+7Fh] BYREF

  v3 = 0;
  FileHandle = 0;
  LODWORD(v14) = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(a2, 0, a1, 1, 0, 0, &v14);
  if ( PersistedStateLocation == -2147483643 )
  {
    v3 = (WCHAR *)TpmAlloc(1, (unsigned int)v14, retaddr);
    if ( v3 )
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(a2, 0, a1, 1, v3, v14, &v14);
      if ( PersistedStateLocation >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, v3);
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 704;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.SecurityDescriptor = a3;
        ObjectAttributes.SecurityQualityOfService = 0;
        PersistedStateLocation = ZwCreateFile(
                                   &FileHandle,
                                   0xC0000u,
                                   &ObjectAttributes,
                                   &IoStatusBlock,
                                   0,
                                   0x80u,
                                   0,
                                   3u,
                                   1u,
                                   0,
                                   0);
      }
    }
    else
    {
      PersistedStateLocation = -1073741670;
    }
  }
  if ( FileHandle )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  TpmFree(v3);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x14001647c  push    rbp
0x14001647e  push    rbx
0x14001647f  push    rsi
0x140016480  push    rdi
0x140016481  push    r14
0x140016483  push    r15
0x140016485  lea     rbp, [rsp-2Fh]
0x14001648a  sub     rsp, 0C8h
0x140016491  xor     edi, edi
0x140016493  mov     [rbp+57h+FileHandle], 0
0x14001649b  xorps   xmm1, xmm1
0x14001649e  mov     dword ptr [rbp+57h+arg_18], edi
0x1400164a1  mov     rsi, rdx
0x1400164a4  lea     rax, [rbp+57h+arg_18]
0x1400164a8  xorps   xmm0, xmm0
0x1400164ab  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x1400164b0  mov     r15, r8
0x1400164b3  mov     [rsp+0F0h+FileAttributes], edi
0x1400164b7  mov     r14, rcx
0x1400164ba  mov     [rsp+0F0h+AllocationSize], rdi
0x1400164bf  mov     r8, rcx
0x1400164c2  lea     r9d, [rdi+1]
0x1400164c6  xor     edx, edx
0x1400164c8  mov     rcx, rsi
0x1400164cb  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400164cf  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400164d3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400164d7  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400164db  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400164df  call    cs:__imp_RtlGetPersistedStateLocation
0x1400164e6  nop     dword ptr [rax+rax+00h]
0x1400164eb  mov     ebx, eax
0x1400164ed  cmp     eax, 80000005h
0x1400164f2  jnz     loc_1400165E7
0x1400164f8  mov     r8, [rbp+5Fh]; unsigned __int64
0x1400164fc  mov     cl, 1; bool
0x1400164fe  mov     edx, dword ptr [rbp+57h+arg_18]; unsigned __int64
0x140016501  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140016506  mov     rdi, rax
0x140016509  test    rax, rax
0x14001650c  jnz     short loc_140016518
0x14001650e  mov     ebx, 0C000009Ah
0x140016513  jmp     loc_1400165E7
0x140016518  lea     rax, [rbp+57h+arg_18]
0x14001651c  mov     r9d, 1
0x140016522  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x140016527  mov     r8, r14
0x14001652a  mov     eax, dword ptr [rbp+57h+arg_18]
0x14001652d  xor     edx, edx
0x14001652f  mov     [rsp+0F0h+FileAttributes], eax
0x140016533  mov     rcx, rsi
0x140016536  mov     [rsp+0F0h+AllocationSize], rdi
0x14001653b  call    cs:__imp_RtlGetPersistedStateLocation
0x140016542  nop     dword ptr [rax+rax+00h]
0x140016547  mov     ebx, eax
0x140016549  test    eax, eax
0x14001654b  js      loc_1400165E7
0x140016551  mov     rdx, rdi; SourceString
0x140016554  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140016558  call    cs:__imp_RtlInitUnicodeString
0x14001655f  nop     dword ptr [rax+rax+00h]
0x140016564  mov     [rsp+0F0h+EaLength], 0; EaLength
0x14001656c  lea     rax, [rbp+57h+DestinationString]
0x140016570  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x140016579  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001657d  mov     [rsp+0F0h+CreateOptions], 1; CreateOptions
0x140016585  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016589  mov     [rsp+0F0h+CreateDisposition], 3; CreateDisposition
0x140016591  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140016595  mov     [rsp+0F0h+ShareAccess], 0; ShareAccess
0x14001659d  mov     edx, 0C0000h; DesiredAccess
0x1400165a2  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x1400165aa  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x1400165b3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400165ba  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400165c2  mov     [rbp+57h+ObjectAttributes.Attributes], 2C0h
0x1400165c9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400165cd  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r15
0x1400165d1  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x1400165d9  call    cs:__imp_ZwCreateFile
0x1400165e0  nop     dword ptr [rax+rax+00h]
0x1400165e5  mov     ebx, eax
0x1400165e7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400165eb  test    rcx, rcx
0x1400165ee  jz      short loc_140016604
0x1400165f0  call    cs:__imp_ZwClose
0x1400165f7  nop     dword ptr [rax+rax+00h]
0x1400165fc  mov     [rbp+57h+FileHandle], 0
0x140016604  mov     rcx, rdi; void *
0x140016607  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14001660c  mov     eax, ebx
0x14001660e  add     rsp, 0C8h
0x140016615  pop     r15
0x140016617  pop     r14
0x140016619  pop     rdi
0x14001661a  pop     rsi
0x14001661b  pop     rbx
0x14001661c  pop     rbp
0x14001661d  retn
```
