# CabWriter::FciFileWrite(__int64,void *,uint,int *,void *)

- ea: `0x180069b10`
- end: `0x180069d5e`
- name: `?FciFileWrite@CabWriter@@CAI_JPEAXIPEAH1@Z`
- size: `590`
- prototype: `UINT __cdecl(INT_PTR hf, void *memory, UINT cb, int *err, void *pv)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x180036300`
- `0x180069b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069c5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069bf1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069bf1`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180069ba8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180069ba8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069c1e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069d39`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069c1e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069d39`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180069c40`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180069c40`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180069b7b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180069b7b`

## pseudocode

```c
__int64 __fastcall CabWriter::FciFileWrite(INT_PTR hf, void *memory, UINT cb, DWORD *err)
{
  bool v4; // zf
  DWORD v6; // esi
  int v9; // ecx
  unsigned int TempPath2W; // eax
  UINT TempFileNameW; // eax
  int Error; // ebx
  HANDLE FileW; // rax
  LONG v14; // ebx
  unsigned int v16; // ecx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-468h] BYREF
  WCHAR PathName[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR TempFileName[264]; // [rsp+260h] [rbp-248h] BYREF

  v4 = (*(_BYTE *)hf & 1) == 0;
  v6 = cb;
  NumberOfBytesWritten = 0;
  if ( !v4 )
  {
    v9 = *(_DWORD *)(hf + 16);
    if ( v9 + cb < cb )
      return 0;
    if ( v9 + cb > *(_DWORD *)(hf + 24) )
    {
      if ( (*(_BYTE *)hf & 2) == 0 )
      {
        v6 = *(_DWORD *)(hf + 24) - v9;
        goto LABEL_23;
      }
      TempPath2W = GetTempPath2W(260, PathName);
      if ( TempPath2W && TempPath2W < 0x104 )
      {
        TempFileNameW = GetTempFileNameW(PathName, L"SD_", 0, TempFileName);
        Error = -2147467259;
        if ( TempFileNameW )
        {
          FileW = CreateFileW(TempFileName, 0xC0000000, 0, 0, 2u, 0x4000100u, 0);
          *(_QWORD *)(hf + 32) = FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            if ( WriteFile(FileW, *(LPCVOID *)(hf + 8), *(_DWORD *)(hf + 20), &NumberOfBytesWritten, 0) )
            {
              if ( NumberOfBytesWritten == *(_DWORD *)(hf + 20) )
              {
                v14 = *(_DWORD *)(hf + 16);
                if ( SetFilePointer(*(HANDLE *)(hf + 32), v14, 0, 0) == v14 )
                {
                  Error = 0;
LABEL_14:
                  CoTaskMemFree(*(LPVOID *)(hf + 8));
                  *(_DWORD *)hf &= ~1u;
                  *(_QWORD *)(hf + 8) = 0;
                  goto LABEL_19;
                }
              }
            }
            Error = ResultFromKnownLastError();
            if ( Error >= 0 )
              goto LABEL_14;
            CloseHandle(*(HANDLE *)(hf + 32));
          }
        }
        else
        {
          Error = -2147467259;
        }
      }
      else
      {
        Error = -2147467259;
        *err = 122;
      }
      *err = GetLastError();
LABEL_19:
      if ( Error < 0 )
        return 0;
    }
  }
LABEL_23:
  if ( (*(_BYTE *)hf & 1) != 0 )
  {
    if ( memcpy_s_1(
           (void *const)(*(_QWORD *)(hf + 8) + *(int *)(hf + 16)),
           *(_DWORD *)(hf + 24) - *(_DWORD *)(hf + 16),
           memory,
           v6) )
    {
      *err = GetLastError();
      return 0;
    }
    v16 = v6 + *(_DWORD *)(hf + 16);
    if ( v16 >= v6 )
    {
      if ( v16 <= 0x7FFFFFFF )
      {
        *(_DWORD *)(hf + 16) = v16;
        if ( *(_DWORD *)(hf + 20) < (signed int)v16 )
          *(_DWORD *)(hf + 20) = v16;
        return v6;
      }
      *(_DWORD *)(hf + 16) = -1;
    }
    *err = 87;
    return 0;
  }
  if ( !WriteFile(*(HANDLE *)(hf + 32), memory, v6, &NumberOfBytesWritten, 0) && (int)ResultFromKnownLastError() < 0 )
    *err = GetLastError();
  return NumberOfBytesWritten;
}

```

## disassembly

```asm
0x180069b10  push    rbx
0x180069b12  push    rbp
0x180069b13  push    rsi
0x180069b14  push    rdi
0x180069b15  push    r14
0x180069b17  sub     rsp, 480h
0x180069b1e  mov     rax, cs:__security_cookie
0x180069b25  xor     rax, rsp
0x180069b28  mov     [rsp+4A8h+var_38], rax
0x180069b30  test    byte ptr [rcx], 1
0x180069b33  mov     r14, r9
0x180069b36  mov     esi, r8d
0x180069b39  mov     [rsp+4A8h+NumberOfBytesWritten], 0
0x180069b41  mov     rbp, rdx
0x180069b44  mov     rdi, rcx
0x180069b47  jz      loc_180069CC0
0x180069b4d  mov     ecx, [rcx+10h]
0x180069b50  lea     eax, [rcx+r8]
0x180069b54  cmp     eax, r8d
0x180069b57  jb      loc_180069C99
0x180069b5d  cmp     eax, [rdi+18h]
0x180069b60  jbe     loc_180069CC0
0x180069b66  test    byte ptr [rdi], 2
0x180069b69  jz      loc_180069CBB
0x180069b6f  mov     ebx, 104h
0x180069b74  lea     rdx, [rsp+4A8h+PathName]
0x180069b79  mov     ecx, ebx
0x180069b7b  call    cs:__imp_GetTempPath2W
0x180069b81  test    eax, eax
0x180069b83  jz      loc_180069C80
0x180069b89  cmp     eax, ebx
0x180069b8b  jnb     loc_180069C80
0x180069b91  lea     r9, [rsp+4A8h+TempFileName]; lpTempFileName
0x180069b99  xor     r8d, r8d; uUnique
0x180069b9c  lea     rdx, PrefixString; "SD_"
0x180069ba3  lea     rcx, [rsp+4A8h+PathName]; lpPathName
0x180069ba8  call    cs:__imp_GetTempFileNameW
0x180069bae  mov     ecx, eax
0x180069bb0  mov     ebx, 80004005h
0x180069bb5  neg     ecx
0x180069bb7  sbb     edx, edx
0x180069bb9  not     edx
0x180069bbb  and     edx, ebx
0x180069bbd  test    eax, eax
0x180069bbf  jz      loc_180069C7C
0x180069bc5  mov     [rsp+4A8h+hTemplateFile], 0; hTemplateFile
0x180069bce  lea     rcx, [rsp+4A8h+TempFileName]; lpFileName
0x180069bd6  mov     [rsp+4A8h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180069bde  xor     r9d, r9d; lpSecurityAttributes
0x180069be1  xor     r8d, r8d; dwShareMode
0x180069be4  mov     [rsp+4A8h+dwCreationDisposition], 2; dwCreationDisposition
0x180069bec  mov     edx, 0C0000000h; dwDesiredAccess
0x180069bf1  call    cs:__imp_CreateFileW
0x180069bf7  mov     [rdi+20h], rax
0x180069bfb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069bff  jz      loc_180069C8C
0x180069c05  mov     r8d, [rdi+14h]; nNumberOfBytesToWrite
0x180069c09  lea     r9, [rsp+4A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180069c0e  mov     rdx, [rdi+8]; lpBuffer
0x180069c12  mov     rcx, rax; hFile
0x180069c15  mov     qword ptr [rsp+4A8h+dwCreationDisposition], 0; lpOverlapped
0x180069c1e  call    cs:__imp_WriteFile
0x180069c24  test    eax, eax
0x180069c26  jz      short loc_180069C4E
0x180069c28  mov     eax, [rdi+14h]
0x180069c2b  cmp     [rsp+4A8h+NumberOfBytesWritten], eax
0x180069c2f  jnz     short loc_180069C4E
0x180069c31  mov     ebx, [rdi+10h]
0x180069c34  xor     r9d, r9d; dwMoveMethod
0x180069c37  mov     rcx, [rdi+20h]; hFile
0x180069c3b  mov     edx, ebx; lDistanceToMove
0x180069c3d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180069c40  call    cs:__imp_SetFilePointer
0x180069c46  cmp     eax, ebx
0x180069c48  jnz     short loc_180069C4E
0x180069c4a  xor     ebx, ebx
0x180069c4c  jmp     short loc_180069C59
0x180069c4e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180069c53  mov     ebx, eax
0x180069c55  test    eax, eax
0x180069c57  js      short loc_180069C70
0x180069c59  mov     rcx, [rdi+8]; pv
0x180069c5d  call    cs:__imp_CoTaskMemFree
0x180069c63  and     dword ptr [rdi], 0FFFFFFFEh
0x180069c66  mov     qword ptr [rdi+8], 0
0x180069c6e  jmp     short loc_180069C95
0x180069c70  mov     rcx, [rdi+20h]; hObject
0x180069c74  call    cs:__imp_CloseHandle
0x180069c7a  jmp     short loc_180069C8C
0x180069c7c  mov     ebx, edx
0x180069c7e  jmp     short loc_180069C8C
0x180069c80  mov     ebx, 80004005h
0x180069c85  mov     dword ptr [r14], 7Ah ; 'z'
0x180069c8c  call    cs:__imp_GetLastError
0x180069c92  mov     [r14], eax
0x180069c95  test    ebx, ebx
0x180069c97  jns     short loc_180069CC0
0x180069c99  xor     esi, esi
0x180069c9b  mov     eax, esi
0x180069c9d  mov     rcx, [rsp+4A8h+var_38]
0x180069ca5  xor     rcx, rsp; StackCookie
0x180069ca8  call    __security_check_cookie
0x180069cad  add     rsp, 480h
0x180069cb4  pop     r14
0x180069cb6  pop     rdi
0x180069cb7  pop     rsi
0x180069cb8  pop     rbp
0x180069cb9  pop     rbx
0x180069cba  retn
0x180069cbb  mov     esi, [rdi+18h]
0x180069cbe  sub     esi, ecx
0x180069cc0  test    byte ptr [rdi], 1
0x180069cc3  jz      short loc_180069D21
0x180069cc5  mov     eax, [rdi+18h]
0x180069cc8  mov     r8, rbp; Source
0x180069ccb  sub     eax, [rdi+10h]
0x180069cce  movsxd  rcx, dword ptr [rdi+10h]
0x180069cd2  add     rcx, [rdi+8]; Destination
0x180069cd6  movsxd  rdx, eax; DestinationSize
0x180069cd9  mov     r9d, esi; SourceSize
0x180069cdc  call    memcpy_s_1
0x180069ce1  test    eax, eax
0x180069ce3  jnz     short loc_180069D13
0x180069ce5  mov     ecx, [rdi+10h]
0x180069ce8  add     ecx, esi
0x180069cea  cmp     ecx, esi
0x180069cec  jb      short loc_180069D0A
0x180069cee  cmp     ecx, 7FFFFFFFh
0x180069cf4  ja      short loc_180069D03
0x180069cf6  mov     [rdi+10h], ecx
0x180069cf9  cmp     [rdi+14h], ecx
0x180069cfc  jge     short loc_180069C9B
0x180069cfe  mov     [rdi+14h], ecx
0x180069d01  jmp     short loc_180069C9B
0x180069d03  mov     dword ptr [rdi+10h], 0FFFFFFFFh
0x180069d0a  mov     dword ptr [r14], 57h ; 'W'
0x180069d11  jmp     short loc_180069C99
0x180069d13  call    cs:__imp_GetLastError
0x180069d19  mov     [r14], eax
0x180069d1c  jmp     loc_180069C99
0x180069d21  mov     rcx, [rdi+20h]; hFile
0x180069d25  lea     r9, [rsp+4A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180069d2a  mov     r8d, esi; nNumberOfBytesToWrite
0x180069d2d  mov     qword ptr [rsp+4A8h+dwCreationDisposition], 0; lpOverlapped
0x180069d36  mov     rdx, rbp; lpBuffer
0x180069d39  call    cs:__imp_WriteFile
0x180069d3f  test    eax, eax
0x180069d41  jnz     short loc_180069D55
0x180069d43  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180069d48  test    eax, eax
0x180069d4a  jns     short loc_180069D55
0x180069d4c  call    cs:__imp_GetLastError
0x180069d52  mov     [r14], eax
0x180069d55  mov     esi, [rsp+4A8h+NumberOfBytesWritten]
0x180069d59  jmp     loc_180069C9B
```
