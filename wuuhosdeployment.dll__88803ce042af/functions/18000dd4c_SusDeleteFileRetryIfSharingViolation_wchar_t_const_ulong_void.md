# SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)

- ea: `0x18000dd4c`
- end: `0x18000dee5`
- name: `?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z`
- size: `409`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, unsigned int, void *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c714`
- `0x180019330`
- `0x18001a094`
- `0x18001a868`
- `0x18003b800`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000d9e8`
- `0x18000dd4c`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de68`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000de3c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000de3c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000de59`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000de59`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dd96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dd96`

## string_xrefs

- `0x18000dea5`: `Failed to delete file %ls`

## pseudocode

```c
__int64 __fastcall SusDeleteFileRetryIfSharingViolation(PCNZWCH lpString1, int a2, void *a3)
{
  int v3; // esi
  HANDLE FileW; // rax
  void *v7; // rbx
  signed int v8; // eax
  signed int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // r9
  signed int LastError; // eax
  int v14; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-48h]
  char FileInformation[4]; // [rsp+44h] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = 0;
  FileW = CreateFileW(lpString1, 0x80010000, 1u, 0, 3u, 0x200000u, 0);
  v7 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v11 = VerifyFinalFilePath(FileW, lpString1);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v10 = 1763;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v12,
        dwCreationDisposition);
      goto LABEL_27;
    }
    while ( 1 )
    {
      FileInformation[0] = 1;
      if ( SetFileInformationByHandle(v7, FileDispositionInfo, FileInformation, 1u) )
      {
        v9 = 0;
        goto LABEL_20;
      }
      LastError = GetLastError();
      v9 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v9 = LastError;
      if ( v9 >= 0 )
        break;
      if ( v9 != -2147024891 && v9 != -2147024864 )
        goto LABEL_24;
      v14 = v3++;
      if ( a2 == v14 )
      {
        v10 = 1809;
        goto LABEL_25;
      }
      Sleep(0x1F4u);
    }
    v9 = -2147418113;
LABEL_24:
    dwCreationDisposition = v9;
    WUTrace(0, 0, 32, 3);
    v10 = 1794;
LABEL_25:
    v12 = (unsigned int)v9;
    goto LABEL_26;
  }
  v8 = GetLastError();
  v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v9 = v8;
  if ( v9 >= 0 )
  {
    v9 = -2147418113;
LABEL_8:
    v10 = 1760;
    goto LABEL_25;
  }
  if ( v9 != -2147024894 && v9 != -2147024893 )
    goto LABEL_8;
LABEL_27:
  if ( v7 != (void *)-1LL )
LABEL_20:
    CloseHandle(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000dd4c  mov     [rsp+arg_8], rbx
0x18000dd51  mov     [rsp+arg_10], rbp
0x18000dd56  push    rsi
0x18000dd57  push    rdi
0x18000dd58  push    r14
0x18000dd5a  sub     rsp, 50h
0x18000dd5e  mov     rax, cs:__security_cookie
0x18000dd65  xor     rax, rsp
0x18000dd68  mov     [rsp+68h+var_20], rax
0x18000dd6d  xor     esi, esi
0x18000dd6f  mov     r14d, edx
0x18000dd72  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x18000dd77  xor     r9d, r9d; lpSecurityAttributes
0x18000dd7a  mov     [rsp+68h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x18000dd82  mov     edx, 80010000h; dwDesiredAccess
0x18000dd87  mov     rbp, rcx
0x18000dd8a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000dd92  lea     r8d, [rsi+1]; dwShareMode
0x18000dd96  call    cs:__imp_CreateFileW
0x18000dd9c  mov     rbx, rax
0x18000dd9f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dda3  jnz     short loc_18000DDE7
0x18000dda5  call    cs:__imp_GetLastError
0x18000ddab  movzx   edi, ax
0x18000ddae  or      edi, 80070000h
0x18000ddb4  test    eax, eax
0x18000ddb6  cmovle  edi, eax
0x18000ddb9  test    edi, edi
0x18000ddbb  js      short loc_18000DDC4
0x18000ddbd  mov     edi, 8000FFFFh
0x18000ddc2  jmp     short loc_18000DDDD
0x18000ddc4  mov     eax, edi
0x18000ddc6  cmp     edi, 80070002h
0x18000ddcc  jz      loc_18000DEDD
0x18000ddd2  cmp     eax, 80070003h
0x18000ddd7  jz      loc_18000DEDD
0x18000dddd  mov     edx, 6E0h
0x18000dde2  jmp     loc_18000DEC9
0x18000dde7  mov     rdx, rbp; lpString1
0x18000ddea  mov     rcx, rbx; hFile
0x18000dded  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x18000ddf2  mov     edi, eax
0x18000ddf4  test    eax, eax
0x18000ddf6  jns     short loc_18000DE42
0x18000ddf8  mov     r9d, eax
0x18000ddfb  mov     edx, 6E3h
0x18000de00  jmp     loc_18000DECC
0x18000de05  call    cs:__imp_GetLastError
0x18000de0b  movzx   edi, ax
0x18000de0e  or      edi, 80070000h
0x18000de14  test    eax, eax
0x18000de16  cmovle  edi, eax
0x18000de19  test    edi, edi
0x18000de1b  jns     short loc_18000DE99
0x18000de1d  mov     eax, edi
0x18000de1f  cmp     edi, 80070005h
0x18000de25  jz      short loc_18000DE2E
0x18000de27  cmp     eax, 80070020h
0x18000de2c  jnz     short loc_18000DE9E
0x18000de2e  mov     eax, esi
0x18000de30  inc     esi
0x18000de32  cmp     r14d, eax
0x18000de35  jz      short loc_18000DE92
0x18000de37  mov     ecx, 1F4h; dwMilliseconds
0x18000de3c  call    cs:__imp_Sleep
0x18000de42  mov     r9d, 1; dwBufferSize
0x18000de48  mov     [rsp+68h+FileInformation], 1
0x18000de4d  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x18000de52  mov     rcx, rbx; hFile
0x18000de55  lea     edx, [r9+3]; FileInformationClass
0x18000de59  call    cs:__imp_SetFileInformationByHandle
0x18000de5f  test    eax, eax
0x18000de61  jz      short loc_18000DE05
0x18000de63  xor     edi, edi
0x18000de65  mov     rcx, rbx; hObject
0x18000de68  call    cs:__imp_CloseHandle
0x18000de6e  mov     eax, edi
0x18000de70  mov     rcx, [rsp+68h+var_20]
0x18000de75  xor     rcx, rsp; StackCookie
0x18000de78  call    __security_check_cookie
0x18000de7d  lea     r11, [rsp+68h+var_18]
0x18000de82  mov     rbx, [r11+28h]
0x18000de86  mov     rbp, [r11+30h]
0x18000de8a  mov     rsp, r11
0x18000de8d  pop     r14
0x18000de8f  pop     rdi
0x18000de90  pop     rsi
0x18000de91  retn
0x18000de92  mov     edx, 711h
0x18000de97  jmp     short loc_18000DEC9
0x18000de99  mov     edi, 8000FFFFh
0x18000de9e  xor     edx, edx
0x18000dea0  mov     [rsp+68h+hTemplateFile], rbp
0x18000dea5  lea     rax, aFailedToDelete; "Failed to delete file %ls"
0x18000deac  xor     ecx, ecx
0x18000deae  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rax
0x18000deb3  mov     [rsp+68h+dwCreationDisposition], edi; int
0x18000deb7  lea     r9d, [rdx+3]
0x18000debb  lea     r8d, [rdx+20h]
0x18000debf  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000dec4  mov     edx, 702h; void *
0x18000dec9  mov     r9d, edi; char *
0x18000decc  mov     rcx, [rsp+68h]; this
0x18000ded1  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000ded8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dedd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000dee1  jz      short loc_18000DE6E
0x18000dee3  jmp     short loc_18000DE65
```
