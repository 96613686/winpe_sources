# SsOpenFileHandle

- ea: `0x18003b8fc`
- end: `0x18003baac`
- name: `SsOpenFileHandle`
- size: `432`
- prototype: `__int64 __fastcall(_WORD *Src, __int64, __int64, __int64, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005820`

## callees

- `0x18000ae90`
- `0x18001deb0`
- `0x18001def0`
- `0x18001e80c`
- `0x18001e8bc`
- `0x18003b8fc`
- `0x1800435f8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18003ba49`
- `ntdll!NtOpenFile` at `0x18003ba49`
- `ntdll!RtlInitUnicodeString` at `0x18003b9f9`
- `ntdll!RtlInitUnicodeString` at `0x18003b9f9`
- `ntdll!NtClose` at `0x18003ba6e`
- `ntdll!NtClose` at `0x18003ba6e`

## pseudocode

```c
__int64 __fastcall SsOpenFileHandle(_WORD *Src, __int64 a2, __int64 a3, __int64 a4, PHANDLE FileHandle)
{
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rsi
  int Status; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(Buffer, 0, 0x208u);
  DestinationString = 0;
  if ( !Src || !FileHandle )
    return 87;
  *FileHandle = 0;
  v6 = -1;
  do
    ++v6;
  while ( Src[v6] );
  if ( v6 > 4 && *Src == 92 && Src[1] == 63 && Src[2] == 63 && Src[3] == 92 )
  {
    v7 = v6;
    memcpy_0(Buffer, Src, 2 * v6);
    if ( v7 >= 260 )
      _report_rangecheckfailure();
    Buffer[v7] = 0;
  }
  else
  {
    swprintf_s(Buffer, 0x104u, L"\\??\\%s", Src);
  }
  RtlInitUnicodeString(&DestinationString, Buffer);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = NtOpenFile(FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x21u);
  if ( Status >= 0 )
  {
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
      return 0;
  }
  if ( (char *)*FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    NtClose(*FileHandle);
    *FileHandle = 0;
  }
  return NetpNtStatusToApiStatus(Status);
}

```

## disassembly

```asm
0x18003b8fc  mov     [rsp-8+arg_8], rbx
0x18003b901  mov     [rsp-8+arg_10], rsi
0x18003b906  push    rbp
0x18003b907  push    rdi
0x18003b908  push    r14
0x18003b90a  lea     rbp, [rsp-1A0h]
0x18003b912  sub     rsp, 2A0h
0x18003b919  mov     rax, cs:__security_cookie
0x18003b920  xor     rax, rsp
0x18003b923  mov     [rbp+1B0h+var_20], rax
0x18003b92a  mov     rdi, [rbp+1B0h+FileHandle]
0x18003b931  xorps   xmm1, xmm1
0x18003b934  mov     rbx, rcx
0x18003b937  xorps   xmm0, xmm0
0x18003b93a  lea     rcx, [rbp+1B0h+Buffer]; void *
0x18003b93e  xor     edx, edx; Val
0x18003b940  mov     r8d, 208h; Size
0x18003b946  movups  xmmword ptr [rsp+2B0h+IoStatusBlock], xmm0
0x18003b94b  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm1
0x18003b950  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm1
0x18003b955  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18003b95a  call    memset_0
0x18003b95f  xor     r14d, r14d
0x18003b962  xorps   xmm0, xmm0
0x18003b965  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18003b96a  test    rbx, rbx
0x18003b96d  jz      loc_18003BA80
0x18003b973  test    rdi, rdi
0x18003b976  jz      loc_18003BA80
0x18003b97c  mov     [rdi], r14
0x18003b97f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b983  inc     rax
0x18003b986  cmp     [rbx+rax*2], r14w
0x18003b98b  jnz     short loc_18003B983
0x18003b98d  cmp     rax, 4
0x18003b991  jbe     short loc_18003B9D8
0x18003b993  cmp     word ptr [rbx], 5Ch ; '\'
0x18003b997  jnz     short loc_18003B9D8
0x18003b999  cmp     word ptr [rbx+2], 3Fh ; '?'
0x18003b99e  jnz     short loc_18003B9D8
0x18003b9a0  cmp     word ptr [rbx+4], 3Fh ; '?'
0x18003b9a5  jnz     short loc_18003B9D8
0x18003b9a7  cmp     word ptr [rbx+6], 5Ch ; '\'
0x18003b9ac  jnz     short loc_18003B9D8
0x18003b9ae  lea     rsi, [rax+rax]
0x18003b9b2  mov     rdx, rbx; Src
0x18003b9b5  mov     r8, rsi; Size
0x18003b9b8  lea     rcx, [rbp+1B0h+Buffer]; void *
0x18003b9bc  call    memcpy_0
0x18003b9c1  cmp     rsi, 208h
0x18003b9c8  jnb     short loc_18003B9D2
0x18003b9ca  mov     [rbp+rsi+1B0h+Buffer], r14w
0x18003b9d0  jmp     short loc_18003B9F0
0x18003b9d2  call    __report_rangecheckfailure
0x18003b9d8  mov     r9, rbx
0x18003b9db  lea     r8, aS; "\\??\\%s"
0x18003b9e2  mov     edx, 104h; BufferCount
0x18003b9e7  lea     rcx, [rbp+1B0h+Buffer]; Buffer
0x18003b9eb  call    swprintf_s
0x18003b9f0  lea     rdx, [rbp+1B0h+Buffer]; SourceString
0x18003b9f4  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x18003b9f9  call    cs:__imp_RtlInitUnicodeString
0x18003b9ff  lea     rax, [rsp+2B0h+DestinationString]
0x18003ba04  mov     [rsp+2B0h+OpenOptions], 21h ; '!'; OpenOptions
0x18003ba0c  xorps   xmm0, xmm0
0x18003ba0f  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x18003ba14  lea     r9, [rsp+2B0h+IoStatusBlock]; IoStatusBlock
0x18003ba19  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x18003ba21  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x18003ba26  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], r14
0x18003ba2b  mov     edx, 100080h; DesiredAccess
0x18003ba30  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x18003ba38  mov     rcx, rdi; FileHandle
0x18003ba3b  mov     [rsp+2B0h+ShareAccess], 3; ShareAccess
0x18003ba43  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ba49  call    cs:__imp_NtOpenFile
0x18003ba4f  mov     ebx, eax
0x18003ba51  test    eax, eax
0x18003ba53  js      short loc_18003BA61
0x18003ba55  mov     ebx, dword ptr [rsp+2B0h+IoStatusBlock]
0x18003ba59  test    ebx, ebx
0x18003ba5b  js      short loc_18003BA61
0x18003ba5d  xor     eax, eax
0x18003ba5f  jmp     short loc_18003BA85
0x18003ba61  mov     rcx, [rdi]; Handle
0x18003ba64  lea     rax, [rcx-1]
0x18003ba68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ba6c  ja      short loc_18003BA77
0x18003ba6e  call    cs:__imp_NtClose
0x18003ba74  mov     [rdi], r14
0x18003ba77  mov     ecx, ebx; Status
0x18003ba79  call    NetpNtStatusToApiStatus
0x18003ba7e  jmp     short loc_18003BA85
0x18003ba80  mov     eax, 57h ; 'W'
0x18003ba85  mov     rcx, [rbp+1B0h+var_20]
0x18003ba8c  xor     rcx, rsp; StackCookie
0x18003ba8f  call    __security_check_cookie
0x18003ba94  lea     r11, [rsp+2B0h+var_10]
0x18003ba9c  mov     rbx, [r11+28h]
0x18003baa0  mov     rsi, [r11+30h]
0x18003baa4  mov     rsp, r11
0x18003baa7  pop     r14
0x18003baa9  pop     rdi
0x18003baaa  pop     rbp
0x18003baab  retn
```
