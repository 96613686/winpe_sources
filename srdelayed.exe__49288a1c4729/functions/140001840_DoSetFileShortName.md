# DoSetFileShortName

- ea: `0x140001840`
- end: `0x1400019cc`
- name: `DoSetFileShortName`
- size: `396`
- prototype: `__int64 __fastcall(const void **, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400028a4`

## callees

- `0x140001840`
- `0x14000371d`
- `0x140003770`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140001915`
- `ntdll!RtlAllocateHeap` at `0x140001915`
- `ntdll!NtSetInformationFile` at `0x140001956`
- `ntdll!NtSetInformationFile` at `0x14000197c`
- `ntdll!NtSetInformationFile` at `0x140001956`
- `ntdll!NtSetInformationFile` at `0x14000197c`
- `ntdll!NtClose` at `0x1400019a5`
- `ntdll!NtClose` at `0x1400019a5`
- `ntdll!NtQueryInformationFile` at `0x1400018ed`
- `ntdll!NtQueryInformationFile` at `0x1400018ed`
- `ntdll!RtlFreeHeap` at `0x140001996`
- `ntdll!RtlFreeHeap` at `0x140001996`
- `ntdll!NtOpenFile` at `0x1400018c3`
- `ntdll!NtOpenFile` at `0x1400018c3`

## pseudocode

```c
__int64 __fastcall DoSetFileShortName(const void **a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v3; // ebx
  ULONG v4; // ebx
  _DWORD *Heap; // rdi
  void *FileHandle; // [rsp+30h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-21h] BYREF
  _OWORD FileInformation[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v11; // [rsp+98h] [rbp+2Fh]

  ObjectAttributes.ObjectName = a2;
  FileHandle = 0;
  v11 = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenFile(&FileHandle, 0x110180u, &ObjectAttributes, &IoStatusBlock, 3u, 0x204020u);
  if ( v3 >= 0 )
  {
    v3 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v3 >= 0 )
    {
      v4 = *(unsigned __int16 *)a1 + 6;
      Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v4);
      if ( Heap )
      {
        *Heap = *(unsigned __int16 *)a1;
        memcpy_0(Heap + 1, a1[1], *(unsigned __int16 *)a1);
        v3 = NtSetInformationFile(FileHandle, &IoStatusBlock, Heap, v4, FileShortNameInformation);
        if ( v3 >= 0 )
          v3 = NtSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
      }
      else
      {
        v3 = -1073741801;
      }
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001840  mov     [rsp-8+arg_10], rbx
0x140001845  push    rbp
0x140001846  push    rsi
0x140001847  push    rdi
0x140001848  lea     rbp, [rsp-47h]
0x14000184d  sub     rsp, 0B0h
0x140001854  mov     rax, cs:__security_cookie
0x14000185b  xor     rax, rsp
0x14000185e  mov     [rbp+57h+var_20], rax
0x140001862  xorps   xmm0, xmm0
0x140001865  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x140001869  xorps   xmm1, xmm1
0x14000186c  mov     [rsp+0C0h+OpenOptions], 204020h; OpenOptions
0x140001874  xor     eax, eax
0x140001876  mov     [rbp+57h+FileHandle], 0
0x14000187e  mov     rsi, rcx
0x140001881  mov     [rbp+57h+var_28], rax
0x140001885  mov     edx, 110180h; DesiredAccess
0x14000188a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000188e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140001892  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000189a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000189e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400018a6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400018aa  mov     [rsp+0C0h+ShareAccess], 3; ShareAccess
0x1400018b2  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400018b6  movups  [rbp+57h+FileInformation], xmm1
0x1400018ba  movups  [rbp+57h+var_38], xmm1
0x1400018be  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400018c3  call    cs:__imp_NtOpenFile
0x1400018c9  mov     ebx, eax
0x1400018cb  test    eax, eax
0x1400018cd  js      loc_14000199C
0x1400018d3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400018d7  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400018db  mov     r9d, 28h ; '('; Length
0x1400018e1  mov     [rsp+0C0h+ShareAccess], 4; FileInformationClass
0x1400018e9  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400018ed  call    cs:__imp_NtQueryInformationFile
0x1400018f3  mov     ebx, eax
0x1400018f5  test    eax, eax
0x1400018f7  js      loc_14000199C
0x1400018fd  mov     rcx, gs:60h
0x140001906  xor     edx, edx; Flags
0x140001908  movzx   ebx, word ptr [rsi]
0x14000190b  add     ebx, 6
0x14000190e  mov     r8d, ebx; Size
0x140001911  mov     rcx, [rcx+30h]; HeapHandle
0x140001915  call    cs:__imp_RtlAllocateHeap
0x14000191b  mov     rdi, rax
0x14000191e  test    rax, rax
0x140001921  jnz     short loc_14000192A
0x140001923  mov     ebx, 0C0000017h
0x140001928  jmp     short loc_14000199C
0x14000192a  movzx   eax, word ptr [rsi]
0x14000192d  lea     rcx, [rdi+4]; void *
0x140001931  mov     [rdi], eax
0x140001933  movzx   r8d, word ptr [rsi]; MaxCount
0x140001937  mov     rdx, [rsi+8]; Src
0x14000193b  call    memcpy_0
0x140001940  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140001944  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140001948  mov     r9d, ebx; Length
0x14000194b  mov     [rsp+0C0h+ShareAccess], 28h ; '('; FileInformationClass
0x140001953  mov     r8, rdi; FileInformation
0x140001956  call    cs:__imp_NtSetInformationFile
0x14000195c  mov     ebx, eax
0x14000195e  test    eax, eax
0x140001960  js      short loc_140001984
0x140001962  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140001966  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000196a  mov     r9d, 28h ; '('; Length
0x140001970  mov     [rsp+0C0h+ShareAccess], 4; FileInformationClass
0x140001978  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000197c  call    cs:__imp_NtSetInformationFile
0x140001982  mov     ebx, eax
0x140001984  mov     rcx, gs:60h
0x14000198d  mov     r8, rdi; BaseAddress
0x140001990  xor     edx, edx; Flags
0x140001992  mov     rcx, [rcx+30h]; HeapHandle
0x140001996  call    cs:__imp_RtlFreeHeap
0x14000199c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400019a0  test    rcx, rcx
0x1400019a3  jz      short loc_1400019AB
0x1400019a5  call    cs:__imp_NtClose
0x1400019ab  mov     eax, ebx
0x1400019ad  mov     rcx, [rbp+57h+var_20]
0x1400019b1  xor     rcx, rsp; StackCookie
0x1400019b4  call    __security_check_cookie
0x1400019b9  mov     rbx, [rsp+0C0h+arg_10]
0x1400019c1  add     rsp, 0B0h
0x1400019c8  pop     rdi
0x1400019c9  pop     rsi
0x1400019ca  pop     rbp
0x1400019cb  retn
```
