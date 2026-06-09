# TraceMoveClientFileA

- ea: `0x180006514`
- end: `0x180006687`
- name: `TraceMoveClientFileA`
- size: `371`
- prototype: `HRESULT __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180006794`

## callees

- `0x180002830`
- `0x180003bb0`
- `0x180005f3c`
- `0x180005f70`
- `0x180006514`
- `0x180006690`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000663d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000663d`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800065f2`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800065f2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180006628`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180006628`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180006551`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180006551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006645`

## pseudocode

```c
HRESULT __fastcall TraceMoveClientFileA(__int64 a1)
{
  DWORD FullPathNameA; // eax
  HRESULT result; // eax
  HANDLE FileA; // rax
  void *v5; // rdi
  DWORD LastError; // ebx
  char FileInformation[16]; // [rsp+40h] [rbp-138h] BYREF
  CHAR Buffer[272]; // [rsp+50h] [rbp-128h] BYREF

  FullPathNameA = GetFullPathNameA((LPCSTR)(a1 + 284), 0x104u, Buffer, 0);
  if ( !FullPathNameA )
    return GetLastError();
  if ( FullPathNameA >= 0x104 )
    return 161;
  result = StringCchCatA(Buffer, 0x104u, "\\");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatA(Buffer, 0x104u, (STRSAFE_LPCSTR)(a1 + 64));
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatA(Buffer, 0x104u, ".LOG");
  if ( result < 0 )
    return (unsigned __int16)result;
  TraceCloseClientFileW(a1);
  FileA = CreateFileA(Buffer, 0x10000u, 3u, 0, 3u, 0, 0);
  v5 = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 2 )
      return TraceCreateClientFileA(a1);
  }
  else
  {
    LastError = TraceVerifyFileIsNotALinkA(FileA, Buffer);
    if ( !LastError )
    {
      FileInformation[0] = 1;
      if ( !SetFileInformationByHandle(v5, FileDispositionInfo, FileInformation, 1u) )
        LastError = GetLastError();
    }
    CloseHandle(v5);
  }
  if ( LastError )
    return LastError;
  return TraceCreateClientFileA(a1);
}

```

## disassembly

```asm
0x180006514  mov     [rsp+arg_8], rbx
0x180006519  mov     [rsp+arg_10], rsi
0x18000651e  push    rdi
0x18000651f  sub     rsp, 170h
0x180006526  mov     rax, cs:__security_cookie
0x18000652d  xor     rax, rsp
0x180006530  mov     [rsp+178h+var_18], rax
0x180006538  mov     rsi, rcx
0x18000653b  lea     r8, [rsp+178h+Buffer]; lpBuffer
0x180006540  mov     ebx, 104h
0x180006545  add     rcx, 11Ch; lpFileName
0x18000654c  mov     edx, ebx; nBufferLength
0x18000654e  xor     r9d, r9d; lpFilePart
0x180006551  call    cs:__imp_GetFullPathNameA
0x180006557  test    eax, eax
0x180006559  jnz     short loc_180006566
0x18000655b  call    cs:__imp_GetLastError
0x180006561  jmp     loc_180006662
0x180006566  cmp     eax, ebx
0x180006568  jb      short loc_180006574
0x18000656a  mov     eax, 0A1h
0x18000656f  jmp     loc_180006662
0x180006574  lea     r8, pszSrc; "\\"
0x18000657b  mov     rdx, rbx; cchDest
0x18000657e  lea     rcx, [rsp+178h+Buffer]; pszDest
0x180006583  call    StringCchCatA
0x180006588  test    eax, eax
0x18000658a  jns     short loc_180006594
0x18000658c  movzx   eax, ax
0x18000658f  jmp     loc_180006662
0x180006594  lea     r8, [rsi+40h]; pszSrc
0x180006598  mov     rdx, rbx; cchDest
0x18000659b  lea     rcx, [rsp+178h+Buffer]; pszDest
0x1800065a0  call    StringCchCatA
0x1800065a5  test    eax, eax
0x1800065a7  js      short loc_18000658C
0x1800065a9  lea     r8, aLog_0; ".LOG"
0x1800065b0  mov     rdx, rbx; cchDest
0x1800065b3  lea     rcx, [rsp+178h+Buffer]; pszDest
0x1800065b8  call    StringCchCatA
0x1800065bd  test    eax, eax
0x1800065bf  js      short loc_18000658C
0x1800065c1  mov     rcx, rsi
0x1800065c4  call    TraceCloseClientFileW
0x1800065c9  mov     r8d, 3; dwShareMode
0x1800065cf  mov     [rsp+178h+hTemplateFile], 0; hTemplateFile
0x1800065d8  mov     [rsp+178h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800065e0  lea     rcx, [rsp+178h+Buffer]; lpFileName
0x1800065e5  xor     r9d, r9d; lpSecurityAttributes
0x1800065e8  mov     [rsp+178h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800065ed  mov     edx, 10000h; dwDesiredAccess
0x1800065f2  call    cs:__imp_CreateFileA
0x1800065f8  mov     rdi, rax
0x1800065fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800065ff  jz      short loc_180006645
0x180006601  lea     rdx, [rsp+178h+Buffer]; String1
0x180006606  mov     rcx, rax; hFile
0x180006609  call    TraceVerifyFileIsNotALinkA
0x18000660e  mov     ebx, eax
0x180006610  test    eax, eax
0x180006612  jnz     short loc_18000663A
0x180006614  lea     r9d, [rax+1]; dwBufferSize
0x180006618  mov     [rsp+178h+FileInformation], 1
0x18000661d  lea     r8, [rsp+178h+FileInformation]; lpFileInformation
0x180006622  mov     rcx, rdi; hFile
0x180006625  lea     edx, [rax+4]; FileInformationClass
0x180006628  call    cs:__imp_SetFileInformationByHandle
0x18000662e  test    eax, eax
0x180006630  jnz     short loc_18000663A
0x180006632  call    cs:__imp_GetLastError
0x180006638  mov     ebx, eax
0x18000663a  mov     rcx, rdi; hObject
0x18000663d  call    cs:__imp_CloseHandle
0x180006643  jmp     short loc_180006652
0x180006645  call    cs:__imp_GetLastError
0x18000664b  mov     ebx, eax
0x18000664d  cmp     eax, 2
0x180006650  jz      short loc_18000665A
0x180006652  test    ebx, ebx
0x180006654  jz      short loc_18000665A
0x180006656  mov     eax, ebx
0x180006658  jmp     short loc_180006662
0x18000665a  mov     rcx, rsi
0x18000665d  call    TraceCreateClientFileA
0x180006662  mov     rcx, [rsp+178h+var_18]
0x18000666a  xor     rcx, rsp; StackCookie
0x18000666d  call    __security_check_cookie
0x180006672  lea     r11, [rsp+178h+var_8]
0x18000667a  mov     rbx, [r11+18h]
0x18000667e  mov     rsi, [r11+20h]
0x180006682  mov     rsp, r11
0x180006685  pop     rdi
0x180006686  retn
```
