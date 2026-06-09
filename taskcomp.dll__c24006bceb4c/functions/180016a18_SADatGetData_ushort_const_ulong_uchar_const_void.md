# SADatGetData(ushort const *,ulong,uchar * const,void * *)

- ea: `0x180016a18`
- end: `0x180016b8d`
- name: `?SADatGetData@@YAJPEBGKQEAEPEAPEAX@Z`
- size: `373`
- prototype: `signed int __fastcall(const unsigned __int16 *, __int64, unsigned __int8 *const, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180016dd8`

## callees

- `0x180016a18`
- `0x180016b94`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016b61`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016ae6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180016ae6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180016b34`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180016b34`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016a9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016a9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall SADatGetData(const unsigned __int16 *a1, __int64 a2, unsigned __int8 *const a3, void **a4)
{
  HANDLE FileW; // rax
  void *v8; // rdi
  signed int result; // eax
  signed int LastError; // eax
  signed int v11; // ebx
  signed int v12; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(FileName, 0, 0x20Au);
  SADatPath(a1, FileName);
  FileW = CreateFileW(FileName, a4 != 0 ? -1073741824 : 0x80000000, 3u, 0, 3u, 2u, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    NumberOfBytesRead = 0;
    if ( ReadFile(FileW, a3, 6u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead != 6 )
        goto LABEL_12;
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_18;
    }
    if ( (unsigned __int8)(a3[4] - 1) <= 1u )
    {
      if ( a4 )
      {
        if ( SetFilePointer(v8, 0, 0, 0) != -1 )
        {
          *a4 = v8;
          return v11;
        }
        v12 = GetLastError();
        v11 = v12;
        if ( v12 > 0 )
          v11 = (unsigned __int16)v12 | 0x80070000;
      }
LABEL_18:
      if ( v8 )
        CloseHandle(v8);
      return v11;
    }
LABEL_12:
    v11 = -2147418113;
    goto LABEL_18;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180016a18  mov     [rsp+arg_8], rbx
0x180016a1d  push    rbp
0x180016a1e  push    rdi
0x180016a1f  push    r14
0x180016a21  sub     rsp, 270h
0x180016a28  mov     rax, cs:__security_cookie
0x180016a2f  xor     rax, rsp
0x180016a32  mov     [rsp+288h+var_28], rax
0x180016a3a  mov     rbp, r8
0x180016a3d  mov     rbx, rcx
0x180016a40  mov     r8d, 20Ah; Size
0x180016a46  lea     rcx, [rsp+288h+FileName]; void *
0x180016a4b  xor     edx, edx; Val
0x180016a4d  mov     r14, r9
0x180016a50  call    memset_0
0x180016a55  lea     rdx, [rsp+288h+FileName]; unsigned __int16 *
0x180016a5a  mov     rcx, rbx; unsigned __int16 *
0x180016a5d  call    ?SADatPath@@YAXPEBGPEAG_K@Z; SADatPath(ushort const *,ushort *,unsigned __int64)
0x180016a62  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x180016a6b  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180016a70  mov     r8d, 3; dwShareMode
0x180016a76  mov     [rsp+288h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x180016a7e  mov     rax, r14
0x180016a81  mov     [rsp+288h+dwCreationDisposition], r8d; dwCreationDisposition
0x180016a86  neg     rax
0x180016a89  sbb     edx, edx
0x180016a8b  xor     r9d, r9d; lpSecurityAttributes
0x180016a8e  and     edx, 40000000h
0x180016a94  add     edx, 80000000h; dwDesiredAccess
0x180016a9a  call    cs:__imp_CreateFileW
0x180016aa0  mov     rdi, rax
0x180016aa3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016aa7  jnz     short loc_180016AC4
0x180016aa9  call    cs:__imp_GetLastError
0x180016aaf  test    eax, eax
0x180016ab1  jle     loc_180016B69
0x180016ab7  movzx   eax, ax
0x180016aba  or      eax, 80070000h
0x180016abf  jmp     loc_180016B69
0x180016ac4  lea     r9, [rsp+288h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180016ac9  mov     [rsp+288h+NumberOfBytesRead], 0
0x180016ad1  mov     r8d, 6; nNumberOfBytesToRead
0x180016ad7  mov     qword ptr [rsp+288h+dwCreationDisposition], 0; lpOverlapped
0x180016ae0  mov     rdx, rbp; lpBuffer
0x180016ae3  mov     rcx, rdi; hFile
0x180016ae6  call    cs:__imp_ReadFile
0x180016aec  test    eax, eax
0x180016aee  jnz     short loc_180016B0B
0x180016af0  call    cs:__imp_GetLastError
0x180016af6  mov     ebx, eax
0x180016af8  test    eax, eax
0x180016afa  jle     short loc_180016B05
0x180016afc  movzx   ebx, ax
0x180016aff  or      ebx, 80070000h
0x180016b05  test    ebx, ebx
0x180016b07  js      short loc_180016B59
0x180016b09  jmp     short loc_180016B14
0x180016b0b  cmp     [rsp+288h+NumberOfBytesRead], 6
0x180016b10  jnz     short loc_180016B1D
0x180016b12  xor     ebx, ebx
0x180016b14  mov     al, [rbp+4]
0x180016b17  dec     al
0x180016b19  cmp     al, 1
0x180016b1b  jbe     short loc_180016B24
0x180016b1d  mov     ebx, 8000FFFFh
0x180016b22  jmp     short loc_180016B59
0x180016b24  test    r14, r14
0x180016b27  jz      short loc_180016B59
0x180016b29  xor     r9d, r9d; dwMoveMethod
0x180016b2c  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016b2f  xor     edx, edx; lDistanceToMove
0x180016b31  mov     rcx, rdi; hFile
0x180016b34  call    cs:__imp_SetFilePointer
0x180016b3a  cmp     eax, 0FFFFFFFFh
0x180016b3d  jz      short loc_180016B44
0x180016b3f  mov     [r14], rdi
0x180016b42  jmp     short loc_180016B67
0x180016b44  call    cs:__imp_GetLastError
0x180016b4a  mov     ebx, eax
0x180016b4c  test    eax, eax
0x180016b4e  jle     short loc_180016B59
0x180016b50  movzx   ebx, ax
0x180016b53  or      ebx, 80070000h
0x180016b59  test    rdi, rdi
0x180016b5c  jz      short loc_180016B67
0x180016b5e  mov     rcx, rdi; hObject
0x180016b61  call    cs:__imp_CloseHandle
0x180016b67  mov     eax, ebx
0x180016b69  mov     rcx, [rsp+288h+var_28]
0x180016b71  xor     rcx, rsp; StackCookie
0x180016b74  call    __security_check_cookie
0x180016b79  mov     rbx, [rsp+288h+arg_8]
0x180016b81  add     rsp, 270h
0x180016b88  pop     r14
0x180016b8a  pop     rdi
0x180016b8b  pop     rbp
0x180016b8c  retn
```
