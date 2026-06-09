# ValidateOutputFile(void *,ushort const *,ushort const *)

- ea: `0x140060028`
- end: `0x1400602a7`
- name: `?ValidateOutputFile@@YAHPEAXPEBG1@Z`
- size: `639`
- prototype: `__int64 __fastcall(HANDLE hPrinter, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14005fec8`

## callees

- `0x140005c30`
- `0x14000a398`
- `0x140013fe8`
- `0x1400140cc`
- `0x140016d54`
- `0x14002bbcc`
- `0x140060028`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14006014b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14006014b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400600a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400600a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006027e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006027e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140060134`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14006017d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400601a6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140060134`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14006017d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400601a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400601f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140060229`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400601f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140060229`

## string_xrefs

- `0x140060269`: `Couldn't find %ws in the list of ports for %ws, but CreateFile succeeded so it's a valid port/file`
- `0x14006024c`: `CreateFile %ws failed, but it may not be a file port for %ws, so returning TRUE`
- `0x14006025d`: `Couldn't find %ws in the list of ports for %ws. CreateFile failed so it's an invalid port/file`

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
0x140060028  mov     [rsp-38h+arg_0], rbx
0x14006002d  push    rbp
0x14006002e  push    rsi
0x14006002f  push    rdi
0x140060030  push    r12
0x140060032  push    r13
0x140060034  push    r14
0x140060036  push    r15
0x140060038  mov     rbp, rsp
0x14006003b  sub     rsp, 40h
0x14006003f  xor     r12d, r12d
0x140060042  mov     rdi, r8
0x140060045  mov     rsi, rdx
0x140060048  mov     r15, rcx
0x14006004b  mov     ebx, 1
0x140060050  test    r8, r8
0x140060053  jz      loc_14006028D
0x140060059  mov     ecx, 400h; unsigned __int64
0x14006005e  mov     [rbp+cbBuf], ecx
0x140060061  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140060066  lea     rcx, [rbp+pPrinter]
0x14006006a  mov     [rbp+pPrinter], r12
0x14006006e  mov     r14, rax
0x140060071  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140060076  mov     r9d, [rbp+cbBuf]; cbBuf
0x14006007a  lea     rax, [rbp+cbBuf]
0x14006007e  mov     r8, r14; pPrinter
0x140060081  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x140060086  lea     edx, [rbx+4]; Level
0x140060089  mov     [rbp+pPrinter], r14
0x14006008d  mov     rcx, r15; hPrinter
0x140060090  call    GetPrinterW
0x140060095  lea     r13, aValidateoutput; "ValidateOutputFile"
0x14006009c  test    eax, eax
0x14006009e  jnz     short loc_140060104
0x1400600a0  call    cs:__imp_GetLastError
0x1400600a6  cmp     eax, 7Ah ; 'z'
0x1400600a9  jnz     loc_1400601CB
0x1400600af  lea     rcx, [rbp+pPrinter]
0x1400600b3  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1400600b8  mov     eax, [rbp+cbBuf]
0x1400600bb  add     eax, 64h ; 'd'
0x1400600be  mov     ecx, eax; unsigned __int64
0x1400600c0  mov     [rbp+cbBuf], eax
0x1400600c3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400600c8  mov     rdx, rax
0x1400600cb  lea     rcx, [rbp+pPrinter]
0x1400600cf  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x1400600d4  mov     r14, [rbp+pPrinter]
0x1400600d8  test    r14, r14
0x1400600db  jz      loc_1400601CB
0x1400600e1  mov     r9d, [rbp+cbBuf]; cbBuf
0x1400600e5  lea     rax, [rbp+cbBuf]
0x1400600e9  mov     r8, r14; pPrinter
0x1400600ec  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x1400600f1  lea     edx, [rbx+4]; Level
0x1400600f4  mov     rcx, r15; hPrinter
0x1400600f7  call    GetPrinterW
0x1400600fc  test    eax, eax
0x1400600fe  jz      loc_1400601CB
0x140060104  mov     r9, [r14+8]
0x140060108  lea     rdx, aPortListForWsI; "Port list for %ws is %ws"
0x14006010f  mov     r8, rsi
0x140060112  mov     rcx, r13; char *
0x140060115  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006011a  mov     r8, [r14+8]; lpString1
0x14006011e  xor     edx, edx; dwCmpFlags
0x140060120  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x140060128  or      r9d, 0FFFFFFFFh; cchCount1
0x14006012c  mov     [rsp+40h+pcbNeeded], rdi; lpString2
0x140060131  lea     ecx, [rdx+7Fh]; Locale
0x140060134  call    cs:__imp_CompareStringW
0x14006013a  cmp     eax, 2
0x14006013d  jz      short loc_1400601B1
0x14006013f  mov     r14, [r14+8]
0x140060143  mov     edx, 2Ch ; ','; Ch
0x140060148  mov     rcx, r14; Str
0x14006014b  call    cs:__imp_wcschr
0x140060151  test    rax, rax
0x140060154  jz      short loc_14006018D
0x140060156  lea     r15, [rax+2]
0x14006015a  cmp     [r15], r12w
0x14006015e  jz      short loc_14006018D
0x140060160  xor     edx, edx; dwCmpFlags
0x140060162  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x14006016a  or      r9d, 0FFFFFFFFh; cchCount1
0x14006016e  mov     [rax], r12w
0x140060172  mov     r8, r14; lpString1
0x140060175  mov     [rsp+40h+pcbNeeded], rdi; lpString2
0x14006017a  lea     ecx, [rdx+7Fh]; Locale
0x14006017d  call    cs:__imp_CompareStringW
0x140060183  cmp     eax, 2
0x140060186  jz      short loc_1400601B1
0x140060188  mov     r14, r15
0x14006018b  jmp     short loc_140060143
0x14006018d  xor     edx, edx; dwCmpFlags
0x14006018f  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x140060197  or      r9d, 0FFFFFFFFh; cchCount1
0x14006019b  mov     [rsp+40h+pcbNeeded], rdi; lpString2
0x1400601a0  mov     r8, r14; lpString1
0x1400601a3  lea     ecx, [rdx+7Fh]; Locale
0x1400601a6  call    cs:__imp_CompareStringW
0x1400601ac  cmp     eax, 2
0x1400601af  jnz     short loc_1400601CB
0x1400601b1  mov     r9, rsi
0x1400601b4  lea     rdx, aWsMatchesThePo; "%ws matches the port(s) assigned to %ws"...
0x1400601bb  mov     r8, rdi
0x1400601be  mov     rcx, r13; char *
0x1400601c1  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400601c6  jmp     loc_140060284
0x1400601cb  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1400601d0  mov     r15d, 40000000h
0x1400601d6  mov     edx, r15d; dwDesiredAccess
0x1400601d9  mov     [rsp+40h+cchCount2], 8000000h; dwFlagsAndAttributes
0x1400601e1  xor     r9d, r9d; lpSecurityAttributes
0x1400601e4  mov     dword ptr [rsp+40h+pcbNeeded], 3; dwCreationDisposition
0x1400601ec  mov     r8d, ebx; dwShareMode
0x1400601ef  mov     rcx, rdi; lpFileName
0x1400601f2  call    cs:__imp_CreateFileW
0x1400601f8  mov     r14, rax
0x1400601fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400601ff  jnz     short loc_140060266
0x140060201  call    cs:__imp_GetLastError
0x140060207  cmp     eax, 2
0x14006020a  jnz     short loc_140060238
0x14006020c  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x140060211  xor     r9d, r9d; lpSecurityAttributes
0x140060214  mov     [rsp+40h+cchCount2], 0C000100h; dwFlagsAndAttributes
0x14006021c  mov     r8d, ebx; dwShareMode
0x14006021f  mov     edx, r15d; dwDesiredAccess
0x140060222  mov     dword ptr [rsp+40h+pcbNeeded], ebx; dwCreationDisposition
0x140060226  mov     rcx, rdi; lpFileName
0x140060229  call    cs:__imp_CreateFileW
0x14006022f  mov     r14, rax
0x140060232  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140060236  jnz     short loc_140060266
0x140060238  call    cs:__imp_GetLastError
0x14006023e  mov     r9, rsi
0x140060241  mov     r8, rdi
0x140060244  mov     rcx, r13; char *
0x140060247  cmp     eax, 5
0x14006024a  jz      short loc_14006025A
0x14006024c  lea     rdx, aCreatefileWsFa; "CreateFile %ws failed, but it may not b"...
0x140060253  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140060258  jmp     short loc_140060284
0x14006025a  mov     ebx, r12d
0x14006025d  lea     rdx, aCouldnTFindWsI; "Couldn't find %ws in the list of ports "...
0x140060264  jmp     short loc_140060253
0x140060266  mov     r9, rsi
0x140060269  lea     rdx, aCouldnTFindWsI_0; "Couldn't find %ws in the list of ports "...
0x140060270  mov     r8, rdi
0x140060273  mov     rcx, r13; char *
0x140060276  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006027b  mov     rcx, r14; hObject
0x14006027e  call    cs:__imp_CloseHandle
0x140060284  lea     rcx, [rbp+pPrinter]
0x140060288  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x14006028d  mov     eax, ebx
0x14006028f  mov     rbx, [rsp+40h+arg_0]
0x140060297  add     rsp, 40h
0x14006029b  pop     r15
0x14006029d  pop     r14
0x14006029f  pop     r13
0x1400602a1  pop     r12
0x1400602a3  pop     rdi
0x1400602a4  pop     rsi
0x1400602a5  pop     rbp
0x1400602a6  retn
```
