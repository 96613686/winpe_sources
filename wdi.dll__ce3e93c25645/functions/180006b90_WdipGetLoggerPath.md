# WdipGetLoggerPath

- ea: `0x180006b90`
- end: `0x180006e2b`
- name: `WdipGetLoggerPath`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180005000`

## callees

- `0x180002ba0`
- `0x180006b90`
- `0x1800072f0`
- `0x180009474`
- `0x18000d514`
- `0x18000f1c2`
- `0x18000f1f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006d0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dd5`

## string_xrefs

- `0x180006db5`: `WdipGetLoggerPath`
- `0x180006df7`: `WdipGetLoggerPath`

## pseudocode

```c
__int64 __fastcall WdipGetLoggerPath(__int64 a1, __int64 a2, unsigned __int16 *a3, unsigned int *a4, unsigned int a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  WCHAR *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  char *FileW; // rsi
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(FileName, 0, 0x208u);
  v9 = WdipVerifyDirectory(a1, a2, FileName, 0x104u);
  v10 = v9;
  if ( v9 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
      (int)L"WdipGetLoggerPath",
      206,
      (int)L"Error = %d",
      v9);
    return v10;
  }
  if ( a5 )
  {
    if ( a5 == 1 )
    {
      v11 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", FileName, L"ksnapshot.etl");
      v10 = v11;
      if ( v11 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
          (int)L"WdipGetLoggerPath",
          228,
          (int)L"Error = %d",
          v11);
        return v10;
      }
    }
  }
  else
  {
    v12 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", FileName, L"snapshot.etl");
    v10 = v12;
    if ( v12 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
        (int)L"WdipGetLoggerPath",
        217,
        (int)L"Error = %d",
        v12);
      return v10;
    }
  }
  v13 = FileName;
  v14 = 0x7FFFFFFF;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  v10 = -2147024809;
  if ( v14 )
    v10 = 0;
  v15 = 0x7FFFFFFF - v14;
  if ( !v14 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
      (int)L"WdipGetLoggerPath",
      237,
      (int)L"Error = %d",
      v10);
    return v10;
  }
  if ( v15 > 0xFFFFFFFF )
  {
    v10 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
      (int)L"WdipGetLoggerPath",
      240,
      (int)L"Error = %d",
      22);
    return v10;
  }
  v10 = 0;
  FileW = (char *)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  if ( FileW == (char *)-1LL )
  {
    if ( GetLastError() != 2 && GetLastError() != 3 )
      return v10;
    v17 = WdipSnapshotLogger(a5, FileName);
    v10 = v17;
    if ( v17 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
        (int)L"WdipGetLoggerPath",
        257,
        (int)L"Error = %d",
        v17);
      return v10;
    }
  }
  v18 = v15 + 1;
  if ( a3 )
  {
    if ( *a4 >= v18 )
    {
      v19 = StringCchPrintfW(a3, v18, L"%s", FileName);
      v10 = v19;
      if ( v19 < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
          (int)L"WdipGetLoggerPath",
          285,
          (int)L"Error = %d",
          v19);
    }
    else
    {
      *a4 = v18;
      v10 = -2147024662;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
        (int)L"WdipGetLoggerPath",
        277,
        (int)L"Error = %d",
        234);
    }
  }
  else
  {
    *a4 = v18;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v10;
}

```

## disassembly

```asm
0x180006b90  push    rbx
0x180006b92  push    rsi
0x180006b93  push    rdi
0x180006b94  push    r14
0x180006b96  push    r15
0x180006b98  sub     rsp, 260h
0x180006b9f  mov     rax, cs:__security_cookie
0x180006ba6  xor     rax, rsp
0x180006ba9  mov     [rsp+288h+var_38], rax
0x180006bb1  mov     r15, r8
0x180006bb4  mov     rdi, rdx
0x180006bb7  mov     rbx, rcx
0x180006bba  xor     edx, edx; Val
0x180006bbc  mov     r8d, 208h; Size
0x180006bc2  lea     rcx, [rsp+288h+FileName]; void *
0x180006bc7  mov     r14, r9
0x180006bca  call    memset_0
0x180006bcf  mov     r9d, 104h
0x180006bd5  lea     r8, [rsp+288h+FileName]
0x180006bda  mov     rdx, rdi
0x180006bdd  mov     rcx, rbx
0x180006be0  call    WdipVerifyDirectory
0x180006be5  mov     ebx, eax
0x180006be7  test    eax, eax
0x180006be9  jns     short loc_180006BFD
0x180006beb  movzx   ecx, ax
0x180006bee  mov     r8d, 0CEh
0x180006bf4  mov     [rsp+288h+dwCreationDisposition], ecx
0x180006bf8  jmp     loc_180006DF0
0x180006bfd  mov     ecx, [rsp+288h+arg_20]
0x180006c04  test    ecx, ecx
0x180006c06  jz      short loc_180006C4C
0x180006c08  cmp     ecx, 1
0x180006c0b  jnz     short loc_180006C8B
0x180006c0d  lea     rax, aKsnapshotEtl; "ksnapshot.etl"
0x180006c14  mov     edx, 104h; unsigned __int64
0x180006c19  lea     r9, [rsp+288h+FileName]
0x180006c1e  mov     qword ptr [rsp+288h+dwCreationDisposition], rax
0x180006c23  lea     r8, aSS; "%s\\%s"
0x180006c2a  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x180006c2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006c34  mov     ebx, eax
0x180006c36  test    eax, eax
0x180006c38  jns     short loc_180006C8B
0x180006c3a  movzx   eax, ax
0x180006c3d  mov     r8d, 0E4h
0x180006c43  mov     [rsp+288h+dwCreationDisposition], eax
0x180006c47  jmp     loc_180006DF0
0x180006c4c  lea     rax, aSnapshotEtl; "snapshot.etl"
0x180006c53  mov     edx, 104h; unsigned __int64
0x180006c58  lea     r9, [rsp+288h+FileName]
0x180006c5d  mov     qword ptr [rsp+288h+dwCreationDisposition], rax
0x180006c62  lea     r8, aSS; "%s\\%s"
0x180006c69  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x180006c6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006c73  mov     ebx, eax
0x180006c75  test    eax, eax
0x180006c77  jns     short loc_180006C8B
0x180006c79  movzx   eax, ax
0x180006c7c  mov     r8d, 0D9h
0x180006c82  mov     [rsp+288h+dwCreationDisposition], eax
0x180006c86  jmp     loc_180006DF0
0x180006c8b  mov     edi, 7FFFFFFFh
0x180006c90  lea     rax, [rsp+288h+FileName]
0x180006c95  mov     ecx, edi
0x180006c97  cmp     word ptr [rax], 0
0x180006c9b  jz      short loc_180006CA7
0x180006c9d  add     rax, 2
0x180006ca1  sub     rcx, 1
0x180006ca5  jnz     short loc_180006C97
0x180006ca7  xor     eax, eax
0x180006ca9  mov     ebx, 80070057h
0x180006cae  test    rcx, rcx
0x180006cb1  cmovnz  ebx, eax
0x180006cb4  sub     rdi, rcx
0x180006cb7  test    rcx, rcx
0x180006cba  cmovz   rdi, rax
0x180006cbe  jnz     short loc_180006CD2
0x180006cc0  movzx   eax, bx
0x180006cc3  mov     r8d, 0EDh
0x180006cc9  mov     [rsp+288h+dwCreationDisposition], eax
0x180006ccd  jmp     loc_180006DF0
0x180006cd2  mov     eax, 0FFFFFFFFh
0x180006cd7  cmp     rdi, rax
0x180006cda  ja      loc_180006DDD
0x180006ce0  xor     ebx, ebx
0x180006ce2  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180006ce7  mov     [rsp+288h+hTemplateFile], rbx; hTemplateFile
0x180006cec  xor     r9d, r9d; lpSecurityAttributes
0x180006cef  mov     [rsp+288h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180006cf7  mov     edx, 80000000h; dwDesiredAccess
0x180006cfc  mov     r8d, 1; dwShareMode
0x180006d02  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x180006d0a  call    cs:__imp_CreateFileW
0x180006d10  mov     rsi, rax
0x180006d13  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006d17  jnz     short loc_180006D5C
0x180006d19  call    cs:__imp_GetLastError
0x180006d1f  cmp     eax, 2
0x180006d22  jz      short loc_180006D33
0x180006d24  call    cs:__imp_GetLastError
0x180006d2a  cmp     eax, 3
0x180006d2d  jnz     loc_180006E0A
0x180006d33  mov     ecx, [rsp+288h+arg_20]
0x180006d3a  lea     rdx, [rsp+288h+FileName]
0x180006d3f  call    ?WdipSnapshotLogger@@YAJW4WDILOGGER@@QEAG@Z; WdipSnapshotLogger(WDILOGGER,ushort * const)
0x180006d44  mov     ebx, eax
0x180006d46  test    eax, eax
0x180006d48  jns     short loc_180006D5C
0x180006d4a  movzx   eax, ax
0x180006d4d  mov     r8d, 101h
0x180006d53  mov     [rsp+288h+dwCreationDisposition], eax
0x180006d57  jmp     loc_180006DF0
0x180006d5c  inc     edi
0x180006d5e  test    r15, r15
0x180006d61  jnz     short loc_180006D68
0x180006d63  mov     [r14], edi
0x180006d66  jmp     short loc_180006DC8
0x180006d68  cmp     [r14], edi
0x180006d6b  jnb     short loc_180006D85
0x180006d6d  mov     [r14], edi
0x180006d70  mov     ebx, 800700EAh
0x180006d75  mov     [rsp+288h+dwCreationDisposition], 0EAh
0x180006d7d  mov     r8d, 115h
0x180006d83  jmp     short loc_180006DAE
0x180006d85  mov     edx, edi; unsigned __int64
0x180006d87  lea     r9, [rsp+288h+FileName]
0x180006d8c  lea     r8, aS; "%s"
0x180006d93  mov     rcx, r15; unsigned __int16 *
0x180006d96  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d9b  mov     ebx, eax
0x180006d9d  test    eax, eax
0x180006d9f  jns     short loc_180006DC8
0x180006da1  movzx   eax, ax
0x180006da4  mov     r8d, 11Dh; int
0x180006daa  mov     [rsp+288h+dwCreationDisposition], eax; Args
0x180006dae  lea     r9, aErrorD_0; "Error = %d"
0x180006db5  lea     rdx, aWdipgetloggerp; "WdipGetLoggerPath"
0x180006dbc  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006dc3  call    WdipTraceError
0x180006dc8  lea     rax, [rsi-1]
0x180006dcc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006dd0  ja      short loc_180006E0A
0x180006dd2  mov     rcx, rsi; hObject
0x180006dd5  call    cs:__imp_CloseHandle
0x180006ddb  jmp     short loc_180006E0A
0x180006ddd  mov     ebx, 80070216h
0x180006de2  mov     [rsp+288h+dwCreationDisposition], 216h; Args
0x180006dea  mov     r8d, 0F0h; int
0x180006df0  lea     r9, aErrorD_0; "Error = %d"
0x180006df7  lea     rdx, aWdipgetloggerp; "WdipGetLoggerPath"
0x180006dfe  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006e05  call    WdipTraceError
0x180006e0a  mov     eax, ebx
0x180006e0c  mov     rcx, [rsp+288h+var_38]
0x180006e14  xor     rcx, rsp; StackCookie
0x180006e17  call    __security_check_cookie
0x180006e1c  add     rsp, 260h
0x180006e23  pop     r15
0x180006e25  pop     r14
0x180006e27  pop     rdi
0x180006e28  pop     rsi
0x180006e29  pop     rbx
0x180006e2a  retn
```
