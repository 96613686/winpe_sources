# PfSvInitializePrefetchDirectory

- ea: `0x180081ff0`
- end: `0x180082196`
- name: `PfSvInitializePrefetchDirectory`
- size: `422`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180081b6c`

## callees

- `0x1800382e0`
- `0x180039f94`
- `0x18003bafc`
- `0x180081ff0`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180082107`
- `ntdll!NtCreateFile` at `0x180082107`
- `ntdll!RtlInitUnicodeString` at `0x18008208e`
- `ntdll!RtlInitUnicodeString` at `0x18008208e`
- `ntdll!RtlNtStatusToDosError` at `0x180082113`
- `ntdll!RtlNtStatusToDosError` at `0x180082113`
- `ntdll!NtClose` at `0x18008216e`
- `ntdll!NtClose` at `0x18008216e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008215c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008215c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008212d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008212d`

## pseudocode

```c
__int64 __fastcall PfSvInitializePrefetchDirectory(int a1)
{
  DWORD Value; // eax
  DWORD v2; // ebx
  int v3; // eax
  DWORD LastError; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t pszDest; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszSrc[260]; // [rsp+C8h] [rbp-38h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  Value = PfsRegQueryValue(a1, (unsigned int)L"PrefetchRoot", 1, 520, (__int64)&pszDest);
  v2 = Value;
  if ( Value == 2 )
  {
    StringCbPrintfW(&pszDest, 0x208u, L"\\SystemRoot\\Prefetch");
  }
  else if ( Value )
  {
    goto LABEL_10;
  }
  pszSrc[255] = 0;
  RtlInitUnicodeString(&DestinationString, &pszDest);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x204021u, 0, 0);
  if ( v3 >= 0 )
  {
    if ( GetFinalPathNameByHandleW(FileHandle, &pszDest, 0x104u, 0) - 1 <= 0x103 )
    {
      StringCbCopyW((STRSAFE_LPWSTR)(*(_QWORD *)&PfSvcGlobals + 888LL), 0x20Au, pszSrc);
      v2 = 0;
      goto LABEL_10;
    }
    LastError = GetLastError();
  }
  else
  {
    LastError = RtlNtStatusToDosError(v3);
  }
  v2 = LastError;
LABEL_10:
  if ( FileHandle )
    NtClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x180081ff0  mov     [rsp-8+arg_8], rbx
0x180081ff5  push    rbp
0x180081ff6  lea     rbp, [rsp-1E0h]
0x180081ffe  sub     rsp, 2E0h
0x180082005  mov     rax, cs:__security_cookie
0x18008200c  xor     rax, rsp
0x18008200f  mov     [rbp+1E0h+var_10], rax
0x180082016  xorps   xmm0, xmm0
0x180082019  lea     rdx, aPrefetchroot; "PrefetchRoot"
0x180082020  xor     eax, eax
0x180082022  mov     r9d, 208h
0x180082028  mov     [rsp+2E0h+FileHandle], rax
0x18008202d  mov     r8d, 1
0x180082033  lea     rax, [rbp+1E0h+pszDest]
0x180082037  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x18008203c  mov     [rsp+2E0h+AllocationSize], rax
0x180082041  movups  xmmword ptr [rbp+1E0h+IoStatusBlock], xmm0
0x180082045  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18008204a  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x18008204e  movups  xmmword ptr [rbp+1E0h+DestinationString.Length], xmm0
0x180082052  call    PfsRegQueryValue
0x180082057  mov     ebx, eax
0x180082059  cmp     eax, 2
0x18008205c  jnz     short loc_180082075
0x18008205e  lea     r8, aSystemrootPref; "\\SystemRoot\\Prefetch"
0x180082065  mov     edx, 208h; cbDest
0x18008206a  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x18008206e  call    StringCbPrintfW
0x180082073  jmp     short loc_18008207D
0x180082075  test    eax, eax
0x180082077  jnz     loc_180082164
0x18008207d  xor     eax, eax
0x18008207f  lea     rdx, [rbp+1E0h+pszDest]; SourceString
0x180082083  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x180082087  mov     [rbp+1E0h+var_1A], ax
0x18008208e  call    cs:__imp_RtlInitUnicodeString
0x180082094  mov     [rsp+2E0h+EaLength], 0; EaLength
0x18008209c  lea     rax, [rbp+1E0h+DestinationString]
0x1800820a0  mov     [rsp+2E0h+EaBuffer], 0; EaBuffer
0x1800820a9  lea     r9, [rbp+1E0h+IoStatusBlock]; IoStatusBlock
0x1800820ad  mov     [rsp+2E0h+CreateOptions], 204021h; CreateOptions
0x1800820b5  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x1800820ba  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x1800820bf  lea     rcx, [rsp+2E0h+FileHandle]; FileHandle
0x1800820c4  mov     eax, 3
0x1800820c9  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x1800820d1  mov     [rsp+2E0h+CreateDisposition], eax; CreateDisposition
0x1800820d5  xorps   xmm0, xmm0
0x1800820d8  mov     [rsp+2E0h+ShareAccess], eax; ShareAccess
0x1800820dc  mov     edx, 100001h; DesiredAccess
0x1800820e1  mov     [rsp+2E0h+FileAttributes], 80h; FileAttributes
0x1800820e9  mov     [rsp+2E0h+AllocationSize], 0; AllocationSize
0x1800820f2  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], 0
0x1800820fb  mov     [rbp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180082102  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180082107  call    cs:__imp_NtCreateFile
0x18008210d  test    eax, eax
0x18008210f  jns     short loc_18008211B
0x180082111  mov     ecx, eax; Status
0x180082113  call    cs:__imp_RtlNtStatusToDosError
0x180082119  jmp     short loc_180082162
0x18008211b  mov     rcx, [rsp+2E0h+FileHandle]; hFile
0x180082120  lea     rdx, [rbp+1E0h+pszDest]; lpszFilePath
0x180082124  xor     r9d, r9d; dwFlags
0x180082127  mov     r8d, 104h; cchFilePath
0x18008212d  call    cs:__imp_GetFinalPathNameByHandleW
0x180082133  dec     eax
0x180082135  cmp     eax, 103h
0x18008213a  ja      short loc_18008215C
0x18008213c  mov     rcx, cs:PfSvcGlobals
0x180082143  lea     r8, [rbp+1E0h+pszSrc]; pszSrc
0x180082147  add     rcx, 378h; pszDest
0x18008214e  mov     edx, 20Ah; cbDest
0x180082153  call    StringCbCopyW
0x180082158  xor     ebx, ebx
0x18008215a  jmp     short loc_180082164
0x18008215c  call    cs:__imp_GetLastError
0x180082162  mov     ebx, eax
0x180082164  mov     rcx, [rsp+2E0h+FileHandle]; Handle
0x180082169  test    rcx, rcx
0x18008216c  jz      short loc_180082174
0x18008216e  call    cs:__imp_NtClose
0x180082174  mov     eax, ebx
0x180082176  mov     rcx, [rbp+1E0h+var_10]
0x18008217d  xor     rcx, rsp; StackCookie
0x180082180  call    __security_check_cookie
0x180082185  mov     rbx, [rsp+2E0h+arg_8]
0x18008218d  add     rsp, 2E0h
0x180082194  pop     rbp
0x180082195  retn
```
