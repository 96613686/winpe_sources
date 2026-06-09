# ValidateOutputFile(void *,ushort const *,ushort const *)

- ea: `0x140065eb4`
- end: `0x140066174`
- name: `?ValidateOutputFile@@YAHPEAXPEBG1@Z`
- size: `704`
- prototype: `__int64 __fastcall(HANDLE hPrinter, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140065d38`

## callees

- `0x1400065e0`
- `0x14000b20c`
- `0x140015290`
- `0x140015378`
- `0x140018204`
- `0x14002e0dc`
- `0x140065eb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140065fe7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140065fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066144`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140065fc6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14006601f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14006604e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140065fc6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14006601f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14006604e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400660a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400660e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400660a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400660e3`

## string_xrefs

- `0x140066112`: `CreateFile %ws failed, but it may not be a file port for %ws, so returning TRUE`
- `0x140066123`: `Couldn't find %ws in the list of ports for %ws. CreateFile failed so it's an invalid port/file`
- `0x14006612f`: `Couldn't find %ws in the list of ports for %ws, but CreateFile succeeded so it's a valid port/file`

## pseudocode

```c
__int64 __fastcall ValidateOutputFile(HANDLE hPrinter, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  BYTE *v7; // rax
  LPBYTE v8; // r14
  void *v9; // rax
  const wchar_t *i; // r14
  wchar_t *v11; // rax
  const wchar_t *v12; // r15
  HANDLE FileW; // r14
  DWORD cbBuf; // [rsp+90h] [rbp+50h] BYREF
  LPBYTE pPrinter; // [rsp+98h] [rbp+58h] BYREF

  v6 = 1;
  if ( a3 )
  {
    cbBuf = 1024;
    v7 = (BYTE *)operator new[](0x400u);
    pPrinter = 0;
    v8 = v7;
    NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&pPrinter);
    pPrinter = v8;
    if ( !GetPrinterW(hPrinter, 5u, v8, cbBuf, &cbBuf) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_14;
      NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&pPrinter);
      cbBuf += 100;
      v9 = operator new[](cbBuf);
      NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(&pPrinter, v9);
      v8 = pPrinter;
      if ( !pPrinter || !GetPrinterW(hPrinter, 5u, pPrinter, cbBuf, &cbBuf) )
        goto LABEL_14;
    }
    PrvSpoolssTelemetry::WriteDbgTraceInfo("ValidateOutputFile", L"Port list for %ws is %ws", a2, *((_QWORD *)v8 + 1));
    if ( CompareStringW(0x7Fu, 0, *((PCNZWCH *)v8 + 1), -1, a3, -1) == 2 )
      goto LABEL_13;
    for ( i = (const wchar_t *)*((_QWORD *)v8 + 1); ; i = v12 )
    {
      v11 = wcschr(i, 0x2Cu);
      if ( !v11 )
        break;
      v12 = v11 + 1;
      if ( !v11[1] )
        break;
      *v11 = 0;
      if ( CompareStringW(0x7Fu, 0, i, -1, a3, -1) == 2 )
        goto LABEL_13;
    }
    if ( CompareStringW(0x7Fu, 0, i, -1, a3, -1) == 2 )
    {
LABEL_13:
      PrvSpoolssTelemetry::WriteDbgTraceInfo(
        "ValidateOutputFile",
        L"%ws matches the port(s) assigned to %ws, so it is a valid port/file string",
        a3,
        a2);
    }
    else
    {
LABEL_14:
      FileW = CreateFileW(a3, 0x40000000u, 1u, 0, 3u, 0x8000000u, 0);
      if ( FileW == (HANDLE)-1LL
        && (GetLastError() != 2
         || (FileW = CreateFileW(a3, 0x40000000u, 1u, 0, 1u, 0xC000100u, 0), FileW == (HANDLE)-1LL)) )
      {
        if ( GetLastError() == 5 )
        {
          v6 = 0;
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "ValidateOutputFile",
            L"Couldn't find %ws in the list of ports for %ws. CreateFile failed so it's an invalid port/file",
            a3,
            a2);
        }
        else
        {
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "ValidateOutputFile",
            L"CreateFile %ws failed, but it may not be a file port for %ws, so returning TRUE",
            a3,
            a2);
        }
      }
      else
      {
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "ValidateOutputFile",
          L"Couldn't find %ws in the list of ports for %ws, but CreateFile succeeded so it's a valid port/file",
          a3,
          a2);
        CloseHandle(FileW);
      }
    }
    NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&pPrinter);
  }
  return v6;
}

```

## disassembly

```asm
0x140065eb4  mov     [rsp-38h+arg_0], rbx
0x140065eb9  push    rbp
0x140065eba  push    rsi
0x140065ebb  push    rdi
0x140065ebc  push    r12
0x140065ebe  push    r13
0x140065ec0  push    r14
0x140065ec2  push    r15
0x140065ec4  mov     rbp, rsp
0x140065ec7  sub     rsp, 40h
0x140065ecb  xor     r12d, r12d
0x140065ece  mov     rdi, r8
0x140065ed1  mov     rsi, rdx
0x140065ed4  mov     r15, rcx
0x140065ed7  mov     ebx, 1
0x140065edc  test    r8, r8
0x140065edf  jz      loc_140066159
0x140065ee5  mov     ecx, 400h; unsigned __int64
0x140065eea  mov     [rbp+cbBuf], ecx
0x140065eed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140065ef2  lea     rcx, [rbp+pPrinter]
0x140065ef6  mov     [rbp+pPrinter], r12
0x140065efa  mov     r14, rax
0x140065efd  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140065f02  mov     r9d, [rbp+cbBuf]; cbBuf
0x140065f06  lea     rax, [rbp+cbBuf]
0x140065f0a  mov     r8, r14; pPrinter
0x140065f0d  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x140065f12  lea     edx, [rbx+4]; Level
0x140065f15  mov     [rbp+pPrinter], r14
0x140065f19  mov     rcx, r15; hPrinter
0x140065f1c  call    GetPrinterW
0x140065f21  lea     r13, aValidateoutput; "ValidateOutputFile"
0x140065f28  test    eax, eax
0x140065f2a  jnz     short loc_140065F96
0x140065f2c  call    cs:__imp_GetLastError
0x140065f33  nop     dword ptr [rax+rax+00h]
0x140065f38  cmp     eax, 7Ah ; 'z'
0x140065f3b  jnz     loc_140066079
0x140065f41  lea     rcx, [rbp+pPrinter]
0x140065f45  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140065f4a  mov     eax, [rbp+cbBuf]
0x140065f4d  add     eax, 64h ; 'd'
0x140065f50  mov     ecx, eax; unsigned __int64
0x140065f52  mov     [rbp+cbBuf], eax
0x140065f55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140065f5a  mov     rdx, rax
0x140065f5d  lea     rcx, [rbp+pPrinter]
0x140065f61  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x140065f66  mov     r14, [rbp+pPrinter]
0x140065f6a  test    r14, r14
0x140065f6d  jz      loc_140066079
0x140065f73  mov     r9d, [rbp+cbBuf]; cbBuf
0x140065f77  lea     rax, [rbp+cbBuf]
0x140065f7b  mov     r8, r14; pPrinter
0x140065f7e  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x140065f83  lea     edx, [rbx+4]; Level
0x140065f86  mov     rcx, r15; hPrinter
0x140065f89  call    GetPrinterW
0x140065f8e  test    eax, eax
0x140065f90  jz      loc_140066079
0x140065f96  mov     r9, [r14+8]
0x140065f9a  lea     rdx, aPortListForWsI; "Port list for %ws is %ws"
0x140065fa1  mov     r8, rsi
0x140065fa4  mov     rcx, r13; char *
0x140065fa7  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065fac  mov     r8, [r14+8]; lpString1
0x140065fb0  xor     edx, edx; dwCmpFlags
0x140065fb2  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x140065fba  or      r9d, 0FFFFFFFFh; cchCount1
0x140065fbe  mov     [rsp+40h+pcbNeeded], rdi; lpString2
0x140065fc3  lea     ecx, [rdx+7Fh]; Locale
0x140065fc6  call    cs:__imp_CompareStringW
0x140065fcd  nop     dword ptr [rax+rax+00h]
0x140065fd2  cmp     eax, 2
0x140065fd5  jz      loc_14006605F
0x140065fdb  mov     r14, [r14+8]
0x140065fdf  mov     edx, 2Ch ; ','; Ch
0x140065fe4  mov     rcx, r14; Str
0x140065fe7  call    cs:__imp_wcschr
0x140065fee  nop     dword ptr [rax+rax+00h]
0x140065ff3  test    rax, rax
0x140065ff6  jz      short loc_140066035
0x140065ff8  lea     r15, [rax+2]
0x140065ffc  cmp     [r15], r12w
0x140066000  jz      short loc_140066035
0x140066002  xor     edx, edx; dwCmpFlags
0x140066004  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x14006600c  or      r9d, 0FFFFFFFFh; cchCount1
0x140066010  mov     [rax], r12w
0x140066014  mov     r8, r14; lpString1
0x140066017  mov     [rsp+40h+pcbNeeded], rdi; lpString2
0x14006601c  lea     ecx, [rdx+7Fh]; Locale
0x14006601f  call    cs:__imp_CompareStringW
0x140066026  nop     dword ptr [rax+rax+00h]
0x14006602b  cmp     eax, 2
0x14006602e  jz      short loc_14006605F
0x140066030  mov     r14, r15
0x140066033  jmp     short loc_140065FDF
0x140066035  xor     edx, edx; dwCmpFlags
0x140066037  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x14006603f  or      r9d, 0FFFFFFFFh; cchCount1
0x140066043  mov     [rsp+40h+pcbNeeded], rdi; lpString2
0x140066048  mov     r8, r14; lpString1
0x14006604b  lea     ecx, [rdx+7Fh]; Locale
0x14006604e  call    cs:__imp_CompareStringW
0x140066055  nop     dword ptr [rax+rax+00h]
0x14006605a  cmp     eax, 2
0x14006605d  jnz     short loc_140066079
0x14006605f  mov     r9, rsi
0x140066062  lea     rdx, aWsMatchesThePo; "%ws matches the port(s) assigned to %ws"...
0x140066069  mov     r8, rdi
0x14006606c  mov     rcx, r13; char *
0x14006606f  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140066074  jmp     loc_140066150
0x140066079  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x14006607e  mov     r15d, 40000000h
0x140066084  mov     edx, r15d; dwDesiredAccess
0x140066087  mov     [rsp+40h+cchCount2], 8000000h; dwFlagsAndAttributes
0x14006608f  xor     r9d, r9d; lpSecurityAttributes
0x140066092  mov     dword ptr [rsp+40h+pcbNeeded], 3; dwCreationDisposition
0x14006609a  mov     r8d, ebx; dwShareMode
0x14006609d  mov     rcx, rdi; lpFileName
0x1400660a0  call    cs:__imp_CreateFileW
0x1400660a7  nop     dword ptr [rax+rax+00h]
0x1400660ac  mov     r14, rax
0x1400660af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400660b3  jnz     short loc_14006612C
0x1400660b5  call    cs:__imp_GetLastError
0x1400660bc  nop     dword ptr [rax+rax+00h]
0x1400660c1  cmp     eax, 2
0x1400660c4  jnz     short loc_1400660F8
0x1400660c6  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1400660cb  xor     r9d, r9d; lpSecurityAttributes
0x1400660ce  mov     [rsp+40h+cchCount2], 0C000100h; dwFlagsAndAttributes
0x1400660d6  mov     r8d, ebx; dwShareMode
0x1400660d9  mov     edx, r15d; dwDesiredAccess
0x1400660dc  mov     dword ptr [rsp+40h+pcbNeeded], ebx; dwCreationDisposition
0x1400660e0  mov     rcx, rdi; lpFileName
0x1400660e3  call    cs:__imp_CreateFileW
0x1400660ea  nop     dword ptr [rax+rax+00h]
0x1400660ef  mov     r14, rax
0x1400660f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400660f6  jnz     short loc_14006612C
0x1400660f8  call    cs:__imp_GetLastError
0x1400660ff  nop     dword ptr [rax+rax+00h]
0x140066104  mov     r9, rsi
0x140066107  mov     r8, rdi
0x14006610a  mov     rcx, r13; char *
0x14006610d  cmp     eax, 5
0x140066110  jz      short loc_140066120
0x140066112  lea     rdx, aCreatefileWsFa; "CreateFile %ws failed, but it may not b"...
0x140066119  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006611e  jmp     short loc_140066150
0x140066120  mov     ebx, r12d
0x140066123  lea     rdx, aCouldnTFindWsI; "Couldn't find %ws in the list of ports "...
0x14006612a  jmp     short loc_140066119
0x14006612c  mov     r9, rsi
0x14006612f  lea     rdx, aCouldnTFindWsI_0; "Couldn't find %ws in the list of ports "...
0x140066136  mov     r8, rdi
0x140066139  mov     rcx, r13; char *
0x14006613c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066141  mov     rcx, r14; hObject
0x140066144  call    cs:__imp_CloseHandle
0x14006614b  nop     dword ptr [rax+rax+00h]
0x140066150  lea     rcx, [rbp+pPrinter]
0x140066154  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140066159  mov     eax, ebx
0x14006615b  mov     rbx, [rsp+40h+arg_0]
0x140066163  add     rsp, 40h
0x140066167  pop     r15
0x140066169  pop     r14
0x14006616b  pop     r13
0x14006616d  pop     r12
0x14006616f  pop     rdi
0x140066170  pop     rsi
0x140066171  pop     rbp
0x140066172  retn
```
