# HbDrvSpeedTestCreateTestFile

- ea: `0x1800a62bc`
- end: `0x1800a6438`
- name: `HbDrvSpeedTestCreateTestFile`
- size: `380`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LARGE_INTEGER liDistanceToMove, HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a2aa0`
- `0x1800a5b88`

## callees

- `0x1800a62bc`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x1800a63c0`
- `ntdll!RtlRandomEx` at `0x1800a63c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a633e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a633e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6396`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a640d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a640d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a63a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a63a3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a6377`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a6377`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a632f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a632f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a63ef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a63ef`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a6357`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a638c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a6357`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a638c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6423`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a62ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a62ed`

## pseudocode

```c
__int64 __fastcall HbDrvSpeedTestCreateTestFile(LPCWSTR lpFileName, LARGE_INTEGER liDistanceToMove, HANDLE hFile)
{
  LARGE_INTEGER v4; // rsi
  void *v6; // r15
  DWORD LastError; // ebx
  int v8; // r14d
  HANDLE FileW; // rax
  unsigned int v10; // esi
  ULONG *v11; // rbx
  int v12; // ebp
  unsigned int i; // ebx
  ULONG Seed; // [rsp+88h] [rbp+10h] BYREF

  v4.QuadPart = liDistanceToMove.LowPart;
  Seed = 0;
  v6 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x100000u);
  if ( v6 )
  {
    v8 = 0;
    if ( hFile != (HANDLE)-1LL )
      goto LABEL_25;
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x20000000u, 0);
    hFile = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
LABEL_21:
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v6);
      return LastError;
    }
    if ( SetFilePointerEx(FileW, v4, 0, 0) && (v8 = 1, SetEndOfFile(hFile)) )
    {
LABEL_25:
      if ( SetFilePointerEx(hFile, 0, 0, 0) )
      {
        v10 = v4.LowPart >> 20;
        Seed = GetTickCount();
        v11 = (ULONG *)v6;
        v12 = 0x40000;
        do
        {
          *v11++ = RtlRandomEx(&Seed);
          --v12;
        }
        while ( v12 );
        for ( i = 0; i < v10; ++i )
        {
          if ( !WriteFile(hFile, v6, 0x100000u, 0, 0) )
            goto LABEL_10;
        }
        LastError = 0;
      }
      else
      {
LABEL_10:
        LastError = GetLastError();
      }
      if ( !v8 || hFile == (HANDLE)-1LL )
        goto LABEL_21;
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(hFile);
    goto LABEL_21;
  }
  return 8;
}

```

## disassembly

```asm
0x1800a62bc  mov     rax, rsp
0x1800a62bf  push    rbx
0x1800a62c0  push    rbp
0x1800a62c1  push    rsi
0x1800a62c2  push    rdi
0x1800a62c3  push    r14
0x1800a62c5  push    r15
0x1800a62c7  sub     rsp, 48h
0x1800a62cb  mov     rbx, rcx
0x1800a62ce  mov     esi, edx
0x1800a62d0  mov     rcx, cs:PfSvcGlobals
0x1800a62d7  mov     rdi, r8
0x1800a62da  xor     edx, edx; dwFlags
0x1800a62dc  mov     dword ptr [rax+10h], 0
0x1800a62e3  mov     r8d, 100000h; dwBytes
0x1800a62e9  mov     rcx, [rcx+58h]; hHeap
0x1800a62ed  call    cs:__imp_HeapAlloc
0x1800a62f3  mov     r15, rax
0x1800a62f6  test    rax, rax
0x1800a62f9  jnz     short loc_1800A6303
0x1800a62fb  lea     ebx, [rax+8]
0x1800a62fe  jmp     loc_1800A6429
0x1800a6303  xor     r14d, r14d
0x1800a6306  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a630a  jnz     short loc_1800A6381
0x1800a630c  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x1800a6311  xor     r9d, r9d; lpSecurityAttributes
0x1800a6314  mov     [rsp+78h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x1800a631c  xor     r8d, r8d; dwShareMode
0x1800a631f  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a6324  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x1800a632c  mov     rcx, rbx; lpFileName
0x1800a632f  call    cs:__imp_CreateFileW
0x1800a6335  mov     rdi, rax
0x1800a6338  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a633c  jnz     short loc_1800A634B
0x1800a633e  call    cs:__imp_GetLastError
0x1800a6344  mov     ebx, eax
0x1800a6346  jmp     loc_1800A6413
0x1800a634b  mov     rdx, rsi; liDistanceToMove
0x1800a634e  xor     r9d, r9d; dwMoveMethod
0x1800a6351  xor     r8d, r8d; lpNewFilePointer
0x1800a6354  mov     rcx, rdi; hFile
0x1800a6357  call    cs:__imp_SetFilePointerEx
0x1800a635d  test    eax, eax
0x1800a635f  jnz     short loc_1800A636E
0x1800a6361  call    cs:__imp_GetLastError
0x1800a6367  mov     ebx, eax
0x1800a6369  jmp     loc_1800A640A
0x1800a636e  mov     rcx, rdi; hFile
0x1800a6371  mov     r14d, 1
0x1800a6377  call    cs:__imp_SetEndOfFile
0x1800a637d  test    eax, eax
0x1800a637f  jz      short loc_1800A6361
0x1800a6381  xor     edx, edx; liDistanceToMove
0x1800a6383  xor     r9d, r9d; dwMoveMethod
0x1800a6386  xor     r8d, r8d; lpNewFilePointer
0x1800a6389  mov     rcx, rdi; hFile
0x1800a638c  call    cs:__imp_SetFilePointerEx
0x1800a6392  test    eax, eax
0x1800a6394  jnz     short loc_1800A63A0
0x1800a6396  call    cs:__imp_GetLastError
0x1800a639c  mov     ebx, eax
0x1800a639e  jmp     short loc_1800A63FF
0x1800a63a0  shr     esi, 14h
0x1800a63a3  call    cs:__imp_GetTickCount
0x1800a63a9  mov     [rsp+78h+Seed], eax
0x1800a63b0  mov     rbx, r15
0x1800a63b3  mov     ebp, 40000h
0x1800a63b8  lea     rcx, [rsp+78h+Seed]; Seed
0x1800a63c0  call    cs:__imp_RtlRandomEx
0x1800a63c6  mov     [rbx], eax
0x1800a63c8  lea     rbx, [rbx+4]
0x1800a63cc  add     ebp, 0FFFFFFFFh
0x1800a63cf  jnz     short loc_1800A63B8
0x1800a63d1  xor     ebx, ebx
0x1800a63d3  cmp     ebx, esi
0x1800a63d5  jnb     short loc_1800A63FD
0x1800a63d7  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800a63da  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x1800a63e3  mov     r8d, 100000h; nNumberOfBytesToWrite
0x1800a63e9  mov     rdx, r15; lpBuffer
0x1800a63ec  mov     rcx, rdi; hFile
0x1800a63ef  call    cs:__imp_WriteFile
0x1800a63f5  test    eax, eax
0x1800a63f7  jz      short loc_1800A6396
0x1800a63f9  inc     ebx
0x1800a63fb  jmp     short loc_1800A63D3
0x1800a63fd  xor     ebx, ebx
0x1800a63ff  test    r14d, r14d
0x1800a6402  jz      short loc_1800A6413
0x1800a6404  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a6408  jz      short loc_1800A6413
0x1800a640a  mov     rcx, rdi; hObject
0x1800a640d  call    cs:__imp_CloseHandle
0x1800a6413  mov     rcx, cs:PfSvcGlobals
0x1800a641a  mov     r8, r15; lpMem
0x1800a641d  xor     edx, edx; dwFlags
0x1800a641f  mov     rcx, [rcx+58h]; hHeap
0x1800a6423  call    cs:__imp_HeapFree
0x1800a6429  mov     eax, ebx
0x1800a642b  add     rsp, 48h
0x1800a642f  pop     r15
0x1800a6431  pop     r14
0x1800a6433  pop     rdi
0x1800a6434  pop     rsi
0x1800a6435  pop     rbp
0x1800a6436  pop     rbx
0x1800a6437  retn
```
