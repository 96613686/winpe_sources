# CDrNotify::Initialize(void)

- ea: `0x18001a040`
- end: `0x18001a13b`
- name: `?Initialize@CDrNotify@@MEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(CDrNotify *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019edc`

## callees

- `0x18000adf8`
- `0x18001a040`
- `0x18001a524`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18001a108`
- `ntdll!NtCreateFile` at `0x18001a108`
- `ntdll!RtlInitUnicodeString` at `0x18001a091`
- `ntdll!RtlInitUnicodeString` at `0x18001a091`

## pseudocode

```c
__int64 __fastcall CDrNotify::Initialize(void **this)
{
  __int64 result; // rax
  NTSTATUS v3; // eax
  CDrNotify *v4; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( !(unsigned int)CTSCriticalSection::Initialize((CTSCriticalSection *)(this + 10)) )
    return 2147500037LL;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\RdpDr");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateFile(this + 6, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 3u, 4u, 0, 0);
  v4 = (CDrNotify *)(this - 1);
  if ( v3 >= 0 )
    return CDrNotify::NotifyStart(v4);
  result = v3 | 0x10000000u;
  *((_QWORD *)v4 + 7) = 0;
  if ( (int)result >= 0 )
    return CDrNotify::NotifyStart(v4);
  return result;
}

```

## disassembly

```asm
0x18001a040  mov     [rsp-8+arg_0], rbx
0x18001a045  push    rbp
0x18001a046  lea     rbp, [rsp-57h]
0x18001a04b  sub     rsp, 0B0h
0x18001a052  xorps   xmm1, xmm1
0x18001a055  xorps   xmm0, xmm0
0x18001a058  mov     rbx, rcx
0x18001a05b  add     rcx, 50h ; 'P'; this
0x18001a05f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001a063  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001a067  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18001a06b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001a06f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001a073  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18001a078  test    eax, eax
0x18001a07a  jnz     short loc_18001A086
0x18001a07c  mov     eax, 80004005h
0x18001a081  jmp     loc_18001A12A
0x18001a086  lea     rdx, SourceString; "\\Device\\RdpDr"
0x18001a08d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001a091  call    cs:__imp_RtlInitUnicodeString
0x18001a097  mov     [rsp+0B0h+EaLength], 0; EaLength
0x18001a09f  lea     rax, [rbp+57h+DestinationString]
0x18001a0a3  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x18001a0ac  lea     rcx, [rbx+30h]; FileHandle
0x18001a0b0  mov     [rsp+0B0h+CreateOptions], 4; CreateOptions
0x18001a0b8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001a0bc  mov     [rsp+0B0h+CreateDisposition], 3; CreateDisposition
0x18001a0c4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001a0c8  mov     [rsp+0B0h+ShareAccess], 0; ShareAccess
0x18001a0d0  xorps   xmm0, xmm0
0x18001a0d3  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x18001a0db  mov     edx, 0C0000000h; DesiredAccess
0x18001a0e0  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x18001a0e9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001a0f0  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001a0f8  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18001a0ff  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001a103  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a108  call    cs:__imp_NtCreateFile
0x18001a10e  lea     rcx, [rbx-8]; this
0x18001a112  test    eax, eax
0x18001a114  jns     short loc_18001A125
0x18001a116  or      eax, 10000000h
0x18001a11b  mov     qword ptr [rcx+38h], 0
0x18001a123  jl      short loc_18001A12A
0x18001a125  call    ?NotifyStart@CDrNotify@@QEAAJXZ; CDrNotify::NotifyStart(void)
0x18001a12a  mov     rbx, [rsp+0B0h+arg_0]
0x18001a132  add     rsp, 0B0h
0x18001a139  pop     rbp
0x18001a13a  retn
```
