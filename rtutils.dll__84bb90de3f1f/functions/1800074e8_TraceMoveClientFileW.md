# TraceMoveClientFileW

- ea: `0x1800074e8`
- end: `0x18000765e`
- name: `TraceMoveClientFileW`
- size: `374`
- prototype: `HRESULT __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800078b0`

## callees

- `0x180003bb0`
- `0x180004a2c`
- `0x180005f3c`
- `0x180006c6c`
- `0x1800074e8`
- `0x180007798`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007614`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800075c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800075c9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180007525`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180007525`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800075ff`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800075ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000761c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000761c`

## pseudocode

```c
HRESULT __fastcall TraceMoveClientFileW(__int64 a1)
{
  DWORD FullPathNameW; // eax
  HRESULT result; // eax
  HANDLE FileW; // rax
  void *v5; // rdi
  DWORD LastError; // ebx
  char FileInformation[16]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  FullPathNameW = GetFullPathNameW((LPCWSTR)(a1 + 546), 0x104u, Buffer, 0);
  if ( !FullPathNameW )
    return GetLastError();
  if ( FullPathNameW >= 0x104 )
    return 161;
  result = StringCchCatW(Buffer, 0x104u, L"\\");
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW(Buffer, 0x104u, (STRSAFE_LPCWSTR)(a1 + 128));
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW(Buffer, 0x104u, L".LOG");
  if ( result < 0 )
    return (unsigned __int16)result;
  TraceCloseClientFileW(a1);
  FileW = CreateFileW(Buffer, 0x10000u, 3u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 2 )
      return TraceCreateClientFileW(a1);
  }
  else
  {
    LastError = TraceVerifyFileIsNotALinkW(FileW, (__int64)Buffer);
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
  return TraceCreateClientFileW(a1);
}

```

## disassembly

```asm
0x1800074e8  mov     [rsp+arg_8], rbx
0x1800074ed  mov     [rsp+arg_10], rsi
0x1800074f2  push    rdi
0x1800074f3  sub     rsp, 270h
0x1800074fa  mov     rax, cs:__security_cookie
0x180007501  xor     rax, rsp
0x180007504  mov     [rsp+278h+var_18], rax
0x18000750c  mov     rsi, rcx
0x18000750f  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x180007514  mov     ebx, 104h
0x180007519  add     rcx, 222h; lpFileName
0x180007520  mov     edx, ebx; nBufferLength
0x180007522  xor     r9d, r9d; lpFilePart
0x180007525  call    cs:__imp_GetFullPathNameW
0x18000752b  test    eax, eax
0x18000752d  jnz     short loc_18000753A
0x18000752f  call    cs:__imp_GetLastError
0x180007535  jmp     loc_180007639
0x18000753a  cmp     eax, ebx
0x18000753c  jb      short loc_180007548
0x18000753e  mov     eax, 0A1h
0x180007543  jmp     loc_180007639
0x180007548  lea     r8, asc_18000C888; "\\"
0x18000754f  mov     rdx, rbx; cchDest
0x180007552  lea     rcx, [rsp+278h+Buffer]; pszDest
0x180007557  call    StringCchCatW
0x18000755c  test    eax, eax
0x18000755e  jns     short loc_180007568
0x180007560  movzx   eax, ax
0x180007563  jmp     loc_180007639
0x180007568  lea     r8, [rsi+80h]; pszSrc
0x18000756f  mov     rdx, rbx; cchDest
0x180007572  lea     rcx, [rsp+278h+Buffer]; pszDest
0x180007577  call    StringCchCatW
0x18000757c  test    eax, eax
0x18000757e  js      short loc_180007560
0x180007580  lea     r8, aLog; ".LOG"
0x180007587  mov     rdx, rbx; cchDest
0x18000758a  lea     rcx, [rsp+278h+Buffer]; pszDest
0x18000758f  call    StringCchCatW
0x180007594  test    eax, eax
0x180007596  js      short loc_180007560
0x180007598  mov     rcx, rsi
0x18000759b  call    TraceCloseClientFileW
0x1800075a0  mov     r8d, 3; dwShareMode
0x1800075a6  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x1800075af  mov     [rsp+278h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800075b7  lea     rcx, [rsp+278h+Buffer]; lpFileName
0x1800075bc  xor     r9d, r9d; lpSecurityAttributes
0x1800075bf  mov     [rsp+278h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800075c4  mov     edx, 10000h; dwDesiredAccess
0x1800075c9  call    cs:__imp_CreateFileW
0x1800075cf  mov     rdi, rax
0x1800075d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800075d6  jz      short loc_18000761C
0x1800075d8  lea     rdx, [rsp+278h+Buffer]
0x1800075dd  mov     rcx, rax; hFile
0x1800075e0  call    TraceVerifyFileIsNotALinkW
0x1800075e5  mov     ebx, eax
0x1800075e7  test    eax, eax
0x1800075e9  jnz     short loc_180007611
0x1800075eb  lea     r9d, [rax+1]; dwBufferSize
0x1800075ef  mov     [rsp+278h+FileInformation], 1
0x1800075f4  lea     r8, [rsp+278h+FileInformation]; lpFileInformation
0x1800075f9  mov     rcx, rdi; hFile
0x1800075fc  lea     edx, [rax+4]; FileInformationClass
0x1800075ff  call    cs:__imp_SetFileInformationByHandle
0x180007605  test    eax, eax
0x180007607  jnz     short loc_180007611
0x180007609  call    cs:__imp_GetLastError
0x18000760f  mov     ebx, eax
0x180007611  mov     rcx, rdi; hObject
0x180007614  call    cs:__imp_CloseHandle
0x18000761a  jmp     short loc_180007629
0x18000761c  call    cs:__imp_GetLastError
0x180007622  mov     ebx, eax
0x180007624  cmp     eax, 2
0x180007627  jz      short loc_180007631
0x180007629  test    ebx, ebx
0x18000762b  jz      short loc_180007631
0x18000762d  mov     eax, ebx
0x18000762f  jmp     short loc_180007639
0x180007631  mov     rcx, rsi
0x180007634  call    TraceCreateClientFileW
0x180007639  mov     rcx, [rsp+278h+var_18]
0x180007641  xor     rcx, rsp; StackCookie
0x180007644  call    __security_check_cookie
0x180007649  lea     r11, [rsp+278h+var_8]
0x180007651  mov     rbx, [r11+18h]
0x180007655  mov     rsi, [r11+20h]
0x180007659  mov     rsp, r11
0x18000765c  pop     rdi
0x18000765d  retn
```
