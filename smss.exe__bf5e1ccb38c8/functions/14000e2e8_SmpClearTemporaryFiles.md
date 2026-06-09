# SmpClearTemporaryFiles

- ea: `0x14000e2e8`
- end: `0x14000e4d9`
- name: `SmpClearTemporaryFiles`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140015ae8`

## callees

- `0x140004e30`
- `0x14000e2e8`
- `0x14001426c`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000e3b2`
- `ntdll!RtlInitUnicodeString` at `0x14000e407`
- `ntdll!RtlInitUnicodeString` at `0x14000e3b2`
- `ntdll!RtlInitUnicodeString` at `0x14000e407`
- `ntdll!NtOpenFile` at `0x14000e371`
- `ntdll!NtOpenFile` at `0x14000e371`
- `ntdll!NtClose` at `0x14000e4b8`
- `ntdll!NtClose` at `0x14000e4b8`
- `ntdll!RtlAllocateHeap` at `0x14000e394`
- `ntdll!RtlAllocateHeap` at `0x14000e394`
- `ntdll!RtlFreeHeap` at `0x14000e4a8`
- `ntdll!RtlFreeHeap` at `0x14000e4a8`
- `ntdll!NtQueryDirectoryFile` at `0x14000e467`
- `ntdll!NtQueryDirectoryFile` at `0x14000e467`
- `ntdll!RtlDeleteRegistryValue` at `0x14000e48b`
- `ntdll!RtlDeleteRegistryValue` at `0x14000e48b`

## string_xrefs

- `0x14000e478`: `ClearTempFiles`

## pseudocode

```c
char SmpClearTemporaryFiles()
{
  char *Heap; // rbx
  NTSTATUS i; // eax
  _DWORD *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  char result; // al
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v9; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  wchar_t pszDest[264]; // [rsp+D0h] [rbp-30h] BYREF

  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &SmpTempFilesDir;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  Heap = 0;
  IoStatusBlock = 0;
  v9 = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u) >= 0 )
  {
    Heap = (char *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, 0x8A8u);
    if ( Heap )
    {
      RtlInitUnicodeString(&DestinationString, L"SMSS-PFRO*.tmp");
      for ( i = NtQueryDirectoryFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  Heap,
                  0x8A8u,
                  FileNamesInformation,
                  0,
                  &DestinationString,
                  1u);
            i >= 0;
            i = NtQueryDirectoryFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  Heap,
                  0x8A8u,
                  FileNamesInformation,
                  0,
                  &DestinationString,
                  0) )
      {
        v2 = Heap;
        if ( Heap < Heap + 2216 )
        {
          do
          {
            if ( RtlStringCbPrintfW(pszDest, 0x20Au, L"%s\\%s", SmpTempFilesDir.Buffer, v2 + 3) >= 0 )
            {
              RtlInitUnicodeString(&v9, pszDest);
              LOBYTE(v3) = 1;
              SmpForceDeleteTargetFile(&v9, v3, v4);
            }
            if ( !*v2 )
              break;
            v2 = (_DWORD *)((char *)v2 + (unsigned int)*v2);
          }
          while ( v2 < (_DWORD *)Heap + 554 );
        }
      }
    }
  }
  result = RtlDeleteRegistryValue(2u, L"Session Manager", L"ClearTempFiles");
  if ( Heap )
    result = RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
  if ( FileHandle )
    return NtClose(FileHandle);
  return result;
}

```

## disassembly

```asm
0x14000e2e8  push    rbp
0x14000e2ea  push    rbx
0x14000e2eb  push    rsi
0x14000e2ec  push    rdi
0x14000e2ed  lea     rbp, [rsp-1F8h]
0x14000e2f5  sub     rsp, 2F8h
0x14000e2fc  mov     rax, cs:__security_cookie
0x14000e303  xor     rax, rsp
0x14000e306  mov     [rbp+210h+var_30], rax
0x14000e30d  xor     eax, eax
0x14000e30f  mov     [rsp+310h+OpenOptions], 4021h; OpenOptions
0x14000e317  xorps   xmm0, xmm0
0x14000e31a  mov     [rsp+310h+FileHandle], rax
0x14000e31f  mov     [rbp+210h+ObjectAttributes.RootDirectory], rax
0x14000e323  lea     r9, [rsp+310h+IoStatusBlock]; IoStatusBlock
0x14000e328  lea     rax, SmpTempFilesDir
0x14000e32f  mov     qword ptr [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x14000e337  xorps   xmm1, xmm1
0x14000e33a  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x14000e33e  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x14000e342  mov     qword ptr [rbp+210h+ObjectAttributes.Attributes], 40h ; '@'
0x14000e34a  mov     edx, 100001h; DesiredAccess
0x14000e34f  mov     [rsp+310h+ShareAccess], 3; ShareAccess
0x14000e357  lea     rcx, [rsp+310h+FileHandle]; FileHandle
0x14000e35c  xor     ebx, ebx
0x14000e35e  movups  xmmword ptr [rsp+310h+IoStatusBlock], xmm0
0x14000e363  movups  xmmword ptr [rbp+210h+var_288.Length], xmm1
0x14000e367  movups  xmmword ptr [rsp+310h+DestinationString.Length], xmm0
0x14000e36c  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e371  call    cs:__imp_NtOpenFile
0x14000e377  test    eax, eax
0x14000e379  js      loc_14000E478
0x14000e37f  mov     rcx, gs:60h
0x14000e388  xor     edx, edx; Flags
0x14000e38a  mov     r8d, 8A8h; Size
0x14000e390  mov     rcx, [rcx+30h]; HeapHandle
0x14000e394  call    cs:__imp_RtlAllocateHeap
0x14000e39a  mov     rbx, rax
0x14000e39d  test    rax, rax
0x14000e3a0  jz      loc_14000E478
0x14000e3a6  lea     rdx, aSmssPfroTmp; "SMSS-PFRO*.tmp"
0x14000e3ad  lea     rcx, [rsp+310h+DestinationString]; DestinationString
0x14000e3b2  call    cs:__imp_RtlInitUnicodeString
0x14000e3b8  mov     [rsp+310h+RestartScan], 1
0x14000e3bd  jmp     short loc_14000E42C
0x14000e3bf  test    eax, eax
0x14000e3c1  js      loc_14000E478
0x14000e3c7  lea     rsi, [rbx+8A8h]
0x14000e3ce  mov     rdi, rbx
0x14000e3d1  cmp     rbx, rsi
0x14000e3d4  jnb     short loc_14000E427
0x14000e3d6  mov     r9, cs:SmpTempFilesDir.Buffer
0x14000e3dd  lea     rax, [rdi+0Ch]
0x14000e3e1  lea     r8, aSS; "%s\\%s"
0x14000e3e8  mov     qword ptr [rsp+310h+ShareAccess], rax
0x14000e3ed  mov     edx, 20Ah; cbDest
0x14000e3f2  lea     rcx, [rbp+210h+pszDest]; pszDest
0x14000e3f6  call    RtlStringCbPrintfW
0x14000e3fb  test    eax, eax
0x14000e3fd  js      short loc_14000E418
0x14000e3ff  lea     rdx, [rbp+210h+pszDest]; SourceString
0x14000e403  lea     rcx, [rbp+210h+var_288]; DestinationString
0x14000e407  call    cs:__imp_RtlInitUnicodeString
0x14000e40d  mov     dl, 1
0x14000e40f  lea     rcx, [rbp+210h+var_288]
0x14000e413  call    SmpForceDeleteTargetFile
0x14000e418  cmp     dword ptr [rdi], 0
0x14000e41b  jz      short loc_14000E427
0x14000e41d  mov     eax, [rdi]
0x14000e41f  add     rdi, rax
0x14000e422  cmp     rdi, rsi
0x14000e425  jb      short loc_14000E3D6
0x14000e427  mov     [rsp+310h+RestartScan], 0; RestartScan
0x14000e42c  mov     rcx, [rsp+310h+FileHandle]; FileHandle
0x14000e431  lea     rax, [rsp+310h+DestinationString]
0x14000e436  mov     [rsp+310h+FileName], rax; FileName
0x14000e43b  xor     r9d, r9d; ApcContext
0x14000e43e  mov     [rsp+310h+ReturnSingleEntry], 0; ReturnSingleEntry
0x14000e443  lea     rax, [rsp+310h+IoStatusBlock]
0x14000e448  mov     [rsp+310h+FileInformationClass], 0Ch; FileInformationClass
0x14000e450  xor     r8d, r8d; ApcRoutine
0x14000e453  mov     [rsp+310h+Length], 8A8h; Length
0x14000e45b  xor     edx, edx; Event
0x14000e45d  mov     qword ptr [rsp+310h+OpenOptions], rbx; FileInformation
0x14000e462  mov     qword ptr [rsp+310h+ShareAccess], rax; IoStatusBlock
0x14000e467  call    cs:__imp_NtQueryDirectoryFile
0x14000e46d  cmp     eax, 0C000000Fh
0x14000e472  jnz     loc_14000E3BF
0x14000e478  lea     r8, aCleartempfiles; "ClearTempFiles"
0x14000e47f  mov     ecx, 2; RelativeTo
0x14000e484  lea     rdx, Path; "Session Manager"
0x14000e48b  call    cs:__imp_RtlDeleteRegistryValue
0x14000e491  test    rbx, rbx
0x14000e494  jz      short loc_14000E4AE
0x14000e496  mov     rcx, gs:60h
0x14000e49f  mov     r8, rbx; BaseAddress
0x14000e4a2  xor     edx, edx; Flags
0x14000e4a4  mov     rcx, [rcx+30h]; HeapHandle
0x14000e4a8  call    cs:__imp_RtlFreeHeap
0x14000e4ae  mov     rcx, [rsp+310h+FileHandle]; Handle
0x14000e4b3  test    rcx, rcx
0x14000e4b6  jz      short loc_14000E4BE
0x14000e4b8  call    cs:__imp_NtClose
0x14000e4be  mov     rcx, [rbp+210h+var_30]
0x14000e4c5  xor     rcx, rsp; StackCookie
0x14000e4c8  call    __security_check_cookie
0x14000e4cd  add     rsp, 2F8h
0x14000e4d4  pop     rdi
0x14000e4d5  pop     rsi
0x14000e4d6  pop     rbx
0x14000e4d7  pop     rbp
0x14000e4d8  retn
```
