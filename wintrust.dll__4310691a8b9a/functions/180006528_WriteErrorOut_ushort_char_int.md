# _WriteErrorOut(ushort *,char *,int)

- ea: `0x180006528`
- end: `0x1800066b3`
- name: `?_WriteErrorOut@@YAXPEAGPEADH@Z`
- size: `395`
- prototype: `void __fastcall(LPCWSTR lpSrc, LPCSTR lpOutputString, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004380`
- `0x180005d00`
- `0x1800067b0`
- `0x180025c04`

## callees

- `0x180006528`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180006681`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180006681`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800065f7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800065f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800065e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800065e3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006615`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006674`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006615`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006674`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180006641`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180006641`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000669d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000669d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000658f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000658f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000664a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000664a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006578`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800065ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006578`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800065ae`

## string_xrefs

- `0x180006565`: `%SystemRoot%\System32\CatRoot2\dberr.txt`

## pseudocode

```c
void __fastcall _WriteErrorOut(LPCWSTR lpSrc, LPCSTR lpOutputString, int a3)
{
  const WCHAR *v5; // rbp
  DWORD v6; // eax
  DWORD v7; // esi
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  __int64 v10; // rbx
  HANDLE FileW; // rax
  __int64 v12; // r8
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( g_fLogErrorsToDebugger && !a3 )
    OutputDebugStringA(lpOutputString);
  if ( g_fLogErrorsToFile )
  {
    v5 = L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt";
    if ( lpSrc )
      v5 = lpSrc;
    v6 = ExpandEnvironmentStringsW(v5, 0, 0);
    v7 = v6;
    if ( v6 )
    {
      v8 = (WCHAR *)LocalAlloc(0, 2LL * v6);
      v9 = v8;
      if ( v8 )
      {
        v10 = -1;
        if ( ExpandEnvironmentStringsW(v5, v8, v7) )
        {
          FileW = CreateFileW(v9, 0xC0000000, 0, 0, 4u, 0x80u, 0);
          v10 = (__int64)FileW;
          if ( FileW != (HANDLE)-1LL
            && (GetFileSize(FileW, 0) < 0x30D40
             || SetFilePointer((HANDLE)v10, 0, 0, 0) != -1 && SetEndOfFile((HANDLE)v10))
            && SetFilePointer((HANDLE)v10, 0, 0, 2u) != -1 )
          {
            v12 = -1;
            do
              ++v12;
            while ( lpOutputString[v12] );
            WriteFile((HANDLE)v10, lpOutputString, v12, &NumberOfBytesWritten, 0);
          }
        }
        LocalFree(v9);
        if ( v10 != -1 )
          CloseHandle((HANDLE)v10);
      }
    }
  }
}

```

## disassembly

```asm
0x180006528  mov     [rsp+arg_8], rbx
0x18000652d  mov     [rsp+arg_10], rbp
0x180006532  push    rsi
0x180006533  push    rdi
0x180006534  push    r14
0x180006536  sub     rsp, 40h
0x18000653a  cmp     cs:?g_fLogErrorsToDebugger@@3HA, 0; int g_fLogErrorsToDebugger
0x180006541  mov     r14, rdx
0x180006544  mov     rbx, rcx
0x180006547  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18000654f  jnz     loc_180006691
0x180006555  cmp     cs:?g_fLogErrorsToFile@@3HA, 0; int g_fLogErrorsToFile
0x18000655c  jz      loc_180006656
0x180006562  test    rbx, rbx
0x180006565  lea     rbp, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x18000656c  cmovnz  rbp, rbx
0x180006570  xor     r8d, r8d; nSize
0x180006573  mov     rcx, rbp; lpSrc
0x180006576  xor     edx, edx; lpDst
0x180006578  call    cs:__imp_ExpandEnvironmentStringsW
0x18000657e  mov     esi, eax
0x180006580  test    eax, eax
0x180006582  jz      loc_180006656
0x180006588  mov     edx, esi
0x18000658a  xor     ecx, ecx; uFlags
0x18000658c  add     rdx, rdx; uBytes
0x18000658f  call    cs:__imp_LocalAlloc
0x180006595  mov     rdi, rax
0x180006598  test    rax, rax
0x18000659b  jz      loc_180006656
0x1800065a1  mov     r8d, esi; nSize
0x1800065a4  mov     rdx, rax; lpDst
0x1800065a7  mov     rcx, rbp; lpSrc
0x1800065aa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800065ae  call    cs:__imp_ExpandEnvironmentStringsW
0x1800065b4  test    eax, eax
0x1800065b6  jz      loc_180006647
0x1800065bc  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800065c5  xor     r9d, r9d; lpSecurityAttributes
0x1800065c8  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800065d0  xor     r8d, r8d; dwShareMode
0x1800065d3  mov     edx, 0C0000000h; dwDesiredAccess
0x1800065d8  mov     [rsp+58h+dwCreationDisposition], 4; dwCreationDisposition
0x1800065e0  mov     rcx, rdi; lpFileName
0x1800065e3  call    cs:__imp_CreateFileW
0x1800065e9  mov     rbx, rax
0x1800065ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800065f0  jz      short loc_180006647
0x1800065f2  xor     edx, edx; lpFileSizeHigh
0x1800065f4  mov     rcx, rax; hFile
0x1800065f7  call    cs:__imp_GetFileSize
0x1800065fd  or      esi, 0FFFFFFFFh
0x180006600  cmp     eax, 30D40h
0x180006605  jnb     short loc_180006669
0x180006607  mov     r9d, 2; dwMoveMethod
0x18000660d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180006610  xor     edx, edx; lDistanceToMove
0x180006612  mov     rcx, rbx; hFile
0x180006615  call    cs:__imp_SetFilePointer
0x18000661b  cmp     eax, esi
0x18000661d  jz      short loc_180006647
0x18000661f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006623  inc     r8; nNumberOfBytesToWrite
0x180006626  cmp     byte ptr [r14+r8], 0
0x18000662b  jnz     short loc_180006623
0x18000662d  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006632  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x18000663b  mov     rdx, r14; lpBuffer
0x18000663e  mov     rcx, rbx; hFile
0x180006641  call    cs:__imp_WriteFile
0x180006647  mov     rcx, rdi; hMem
0x18000664a  call    cs:__imp_LocalFree
0x180006650  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180006654  jnz     short loc_1800066A8
0x180006656  mov     rbx, [rsp+58h+arg_8]
0x18000665b  mov     rbp, [rsp+58h+arg_10]
0x180006660  add     rsp, 40h
0x180006664  pop     r14
0x180006666  pop     rdi
0x180006667  pop     rsi
0x180006668  retn
0x180006669  xor     r9d, r9d; dwMoveMethod
0x18000666c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000666f  xor     edx, edx; lDistanceToMove
0x180006671  mov     rcx, rbx; hFile
0x180006674  call    cs:__imp_SetFilePointer
0x18000667a  cmp     eax, esi
0x18000667c  jz      short loc_180006647
0x18000667e  mov     rcx, rbx; hFile
0x180006681  call    cs:__imp_SetEndOfFile
0x180006687  test    eax, eax
0x180006689  jnz     loc_180006607
0x18000668f  jmp     short loc_180006647
0x180006691  test    r8d, r8d
0x180006694  jnz     loc_180006555
0x18000669a  mov     rcx, r14; lpOutputString
0x18000669d  call    cs:__imp_OutputDebugStringA
0x1800066a3  jmp     loc_180006555
0x1800066a8  mov     rcx, rbx; hObject
0x1800066ab  call    cs:__imp_CloseHandle
0x1800066b1  jmp     short loc_180006656
```
