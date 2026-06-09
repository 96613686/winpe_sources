# HbDrvGetSpeedTestFilePath

- ea: `0x1800a1ab0`
- end: `0x1800a1c79`
- name: `HbDrvGetSpeedTestFilePath`
- size: `457`
- prototype: `__int64 __fastcall(__int64, __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a5b88`

## callees

- `0x1800076c4`
- `0x180021e0c`
- `0x180049d6c`
- `0x1800a1ab0`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800a1c05`
- `ntdll!NtOpenFile` at `0x1800a1c05`
- `ntdll!RtlInitUnicodeString` at `0x1800a1baf`
- `ntdll!RtlInitUnicodeString` at `0x1800a1baf`
- `ntdll!RtlNtStatusToDosError` at `0x1800a1c11`
- `ntdll!RtlNtStatusToDosError` at `0x1800a1c11`
- `ntdll!NtClose` at `0x1800a1b41`
- `ntdll!NtClose` at `0x1800a1b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1c44`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a1c2c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800a1c2c`

## pseudocode

```c
__int64 __fastcall HbDrvGetSpeedTestFilePath(__int64 a1, __int64 a2, wchar_t *a3)
{
  bool v3; // zf
  unsigned int v5; // ebx
  int v7; // eax
  ULONG LastError; // eax
  DWORD FinalPathNameByHandleW; // eax
  HRESULT v10; // eax
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = (*(_BYTE *)(a1 + 36) & 1) == 0;
  Handle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !v3 )
  {
    StringCchPrintfW(a3, 0x104u, L"%ws\\%ws", *(_QWORD *)&PfSvcGlobals + 888LL, L"HybridDrivePerfTest.tmp");
LABEL_3:
    v5 = 0;
    goto LABEL_4;
  }
  PfScStringCopy(*(_QWORD *)&PfSvcGlobals + 96LL, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL), pszDest, 260);
  StringCbCatW(pszDest, 0x208u, L"\\");
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&Handle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( v7 < 0 )
  {
    LastError = RtlNtStatusToDosError(v7);
LABEL_9:
    v5 = LastError;
    goto LABEL_4;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(Handle, a3, 0x104u, 0);
  if ( FinalPathNameByHandleW <= 0x104 )
  {
    if ( !FinalPathNameByHandleW )
    {
      LastError = GetLastError();
      goto LABEL_9;
    }
    v10 = StringCchPrintfW(
            &a3[FinalPathNameByHandleW],
            260 - FinalPathNameByHandleW,
            L"%ws",
            L"HybridDrivePerfTest.tmp");
    if ( v10 >= 0 )
      goto LABEL_3;
    v5 = (unsigned __int16)v10;
  }
  else
  {
    v5 = 122;
  }
LABEL_4:
  if ( Handle )
    NtClose(Handle);
  return v5;
}

```

## disassembly

```asm
0x1800a1ab0  mov     [rsp-8+arg_8], rbx
0x1800a1ab5  mov     [rsp-8+arg_18], rdi
0x1800a1aba  push    rbp
0x1800a1abb  lea     rbp, [rsp-1B0h]
0x1800a1ac3  sub     rsp, 2B0h
0x1800a1aca  mov     rax, cs:__security_cookie
0x1800a1ad1  xor     rax, rsp
0x1800a1ad4  mov     [rbp+1B0h+var_10], rax
0x1800a1adb  xorps   xmm0, xmm0
0x1800a1ade  xor     eax, eax
0x1800a1ae0  test    byte ptr [rcx+24h], 1
0x1800a1ae4  mov     rdi, r8
0x1800a1ae7  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x1800a1aec  mov     [rsp+2B0h+Handle], rax
0x1800a1af1  movups  xmmword ptr [rsp+2B0h+ObjectAttributes+1Ch], xmm0
0x1800a1af6  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x1800a1afb  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x1800a1b00  movups  xmmword ptr [rsp+2B0h+IoStatusBlock], xmm0
0x1800a1b05  jz      short loc_1800A1B6D
0x1800a1b07  mov     r9, cs:PfSvcGlobals
0x1800a1b0e  lea     rax, aHybriddriveper_0; "HybridDrivePerfTest.tmp"
0x1800a1b15  add     r9, 378h
0x1800a1b1c  mov     qword ptr [rsp+2B0h+ShareAccess], rax
0x1800a1b21  lea     r8, aWsWs_0; "%ws\\%ws"
0x1800a1b28  mov     edx, 104h; cchDest
0x1800a1b2d  mov     rcx, rdi; pszDest
0x1800a1b30  call    StringCchPrintfW
0x1800a1b35  xor     ebx, ebx
0x1800a1b37  mov     rcx, [rsp+2B0h+Handle]; Handle
0x1800a1b3c  test    rcx, rcx
0x1800a1b3f  jz      short loc_1800A1B47
0x1800a1b41  call    cs:__imp_NtClose
0x1800a1b47  mov     eax, ebx
0x1800a1b49  mov     rcx, [rbp+1B0h+var_10]
0x1800a1b50  xor     rcx, rsp; StackCookie
0x1800a1b53  call    __security_check_cookie
0x1800a1b58  lea     r11, [rsp+2B0h+var_s0]
0x1800a1b60  mov     rbx, [r11+18h]
0x1800a1b64  mov     rdi, [r11+28h]
0x1800a1b68  mov     rsp, r11
0x1800a1b6b  pop     rbp
0x1800a1b6c  retn
0x1800a1b6d  mov     rdx, [rcx+8]
0x1800a1b71  lea     r8, [rbp+1B0h+pszDest]
0x1800a1b75  mov     rcx, cs:PfSvcGlobals
0x1800a1b7c  mov     ebx, 104h
0x1800a1b81  add     rcx, 60h ; '`'
0x1800a1b85  mov     r9d, ebx
0x1800a1b88  mov     rdx, [rdx+10h]
0x1800a1b8c  call    PfScStringCopy
0x1800a1b91  lea     r8, asc_1800BF1BC; "\\"
0x1800a1b98  mov     edx, 208h; cbDest
0x1800a1b9d  lea     rcx, [rbp+1B0h+pszDest]; pszDest
0x1800a1ba1  call    StringCbCatW
0x1800a1ba6  lea     rdx, [rbp+1B0h+pszDest]; SourceString
0x1800a1baa  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x1800a1baf  call    cs:__imp_RtlInitUnicodeString
0x1800a1bb5  lea     rax, [rsp+2B0h+DestinationString]
0x1800a1bba  mov     [rsp+2B0h+OpenOptions], 0; OpenOptions
0x1800a1bc2  xorps   xmm0, xmm0
0x1800a1bc5  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x1800a1bca  lea     r9, [rsp+2B0h+IoStatusBlock]; IoStatusBlock
0x1800a1bcf  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x1800a1bd7  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x1800a1bdc  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], 0
0x1800a1be5  mov     edx, 120089h; DesiredAccess
0x1800a1bea  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800a1bf2  lea     rcx, [rsp+2B0h+Handle]; FileHandle
0x1800a1bf7  mov     [rsp+2B0h+ShareAccess], 7; ShareAccess
0x1800a1bff  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a1c05  call    cs:__imp_NtOpenFile
0x1800a1c0b  test    eax, eax
0x1800a1c0d  jns     short loc_1800A1C1E
0x1800a1c0f  mov     ecx, eax; Status
0x1800a1c11  call    cs:__imp_RtlNtStatusToDosError
0x1800a1c17  mov     ebx, eax
0x1800a1c19  jmp     loc_1800A1B37
0x1800a1c1e  mov     rcx, [rsp+2B0h+Handle]; hFile
0x1800a1c23  xor     r9d, r9d; dwFlags
0x1800a1c26  mov     r8d, ebx; cchFilePath
0x1800a1c29  mov     rdx, rdi; lpszFilePath
0x1800a1c2c  call    cs:__imp_GetFinalPathNameByHandleW
0x1800a1c32  cmp     eax, ebx
0x1800a1c34  jbe     short loc_1800A1C40
0x1800a1c36  mov     ebx, 7Ah ; 'z'
0x1800a1c3b  jmp     loc_1800A1B37
0x1800a1c40  test    eax, eax
0x1800a1c42  jnz     short loc_1800A1C4C
0x1800a1c44  call    cs:__imp_GetLastError
0x1800a1c4a  jmp     short loc_1800A1C17
0x1800a1c4c  sub     ebx, eax
0x1800a1c4e  lea     r9, aHybriddriveper_0; "HybridDrivePerfTest.tmp"
0x1800a1c55  mov     eax, eax
0x1800a1c57  lea     r8, aWs; "%ws"
0x1800a1c5e  mov     edx, ebx; cchDest
0x1800a1c60  lea     rcx, [rdi+rax*2]; pszDest
0x1800a1c64  call    StringCchPrintfW
0x1800a1c69  test    eax, eax
0x1800a1c6b  jns     loc_1800A1B35
0x1800a1c71  movzx   ebx, ax
0x1800a1c74  jmp     loc_1800A1B37
```
