# SADatGetData(ushort const *,ulong,uchar * const,void * *)

- ea: `0x180017958`
- end: `0x180017af8`
- name: `?SADatGetData@@YAJPEBGKQEAEPEAPEAX@Z`
- size: `416`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int8 *const, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180017d84`

## callees

- `0x180017958`
- `0x180017b00`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ac5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180017a32`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180017a32`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180017a8c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180017a8c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800179da`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800179da`

## pseudocode

```c
signed int __fastcall SADatGetData(const unsigned __int16 *a1, __int64 a2, unsigned __int8 *const a3, void **a4)
{
  unsigned __int64 v7; // r8
  HANDLE FileW; // rax
  void *v9; // rdi
  signed int result; // eax
  signed int LastError; // eax
  signed int v12; // ebx
  signed int v13; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(FileName, 0, 0x20Au);
  SADatPath(a1, FileName, v7);
  FileW = CreateFileW(FileName, a4 != 0 ? -1073741824 : 0x80000000, 3u, 0, 3u, 2u, 0);
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    NumberOfBytesRead = 0;
    if ( ReadFile(FileW, a3, 6u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead != 6 )
        goto LABEL_12;
      v12 = 0;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( v12 < 0 )
        goto LABEL_18;
    }
    if ( (unsigned __int8)(a3[4] - 1) <= 1u )
    {
      if ( a4 )
      {
        if ( SetFilePointer(v9, 0, 0, 0) != -1 )
        {
          *a4 = v9;
          return v12;
        }
        v13 = GetLastError();
        v12 = v13;
        if ( v13 > 0 )
          v12 = (unsigned __int16)v13 | 0x80070000;
      }
LABEL_18:
      if ( v9 )
        CloseHandle(v9);
      return v12;
    }
LABEL_12:
    v12 = -2147418113;
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
0x180017958  mov     [rsp+arg_8], rbx
0x18001795d  push    rbp
0x18001795e  push    rdi
0x18001795f  push    r14
0x180017961  sub     rsp, 270h
0x180017968  mov     rax, cs:__security_cookie
0x18001796f  xor     rax, rsp
0x180017972  mov     [rsp+288h+var_28], rax
0x18001797a  mov     rbp, r8
0x18001797d  mov     rbx, rcx
0x180017980  mov     r8d, 20Ah; Size
0x180017986  lea     rcx, [rsp+288h+FileName]; void *
0x18001798b  xor     edx, edx; Val
0x18001798d  mov     r14, r9
0x180017990  call    memset_0
0x180017995  lea     rdx, [rsp+288h+FileName]; unsigned __int16 *
0x18001799a  mov     rcx, rbx; unsigned __int16 *
0x18001799d  call    ?SADatPath@@YAXPEBGPEAG_K@Z; SADatPath(ushort const *,ushort *,unsigned __int64)
0x1800179a2  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1800179ab  lea     rcx, [rsp+288h+FileName]; lpFileName
0x1800179b0  mov     r8d, 3; dwShareMode
0x1800179b6  mov     [rsp+288h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x1800179be  mov     rax, r14
0x1800179c1  mov     [rsp+288h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800179c6  neg     rax
0x1800179c9  sbb     edx, edx
0x1800179cb  xor     r9d, r9d; lpSecurityAttributes
0x1800179ce  and     edx, 40000000h
0x1800179d4  add     edx, 80000000h; dwDesiredAccess
0x1800179da  call    cs:__imp_CreateFileW
0x1800179e1  nop     dword ptr [rax+rax+00h]
0x1800179e6  mov     rdi, rax
0x1800179e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800179ed  jnz     short loc_180017A10
0x1800179ef  call    cs:__imp_GetLastError
0x1800179f6  nop     dword ptr [rax+rax+00h]
0x1800179fb  test    eax, eax
0x1800179fd  jle     loc_180017AD3
0x180017a03  movzx   eax, ax
0x180017a06  or      eax, 80070000h
0x180017a0b  jmp     loc_180017AD3
0x180017a10  lea     r9, [rsp+288h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180017a15  mov     [rsp+288h+NumberOfBytesRead], 0
0x180017a1d  mov     r8d, 6; nNumberOfBytesToRead
0x180017a23  mov     qword ptr [rsp+288h+dwCreationDisposition], 0; lpOverlapped
0x180017a2c  mov     rdx, rbp; lpBuffer
0x180017a2f  mov     rcx, rdi; hFile
0x180017a32  call    cs:__imp_ReadFile
0x180017a39  nop     dword ptr [rax+rax+00h]
0x180017a3e  test    eax, eax
0x180017a40  jnz     short loc_180017A63
0x180017a42  call    cs:__imp_GetLastError
0x180017a49  nop     dword ptr [rax+rax+00h]
0x180017a4e  mov     ebx, eax
0x180017a50  test    eax, eax
0x180017a52  jle     short loc_180017A5D
0x180017a54  movzx   ebx, ax
0x180017a57  or      ebx, 80070000h
0x180017a5d  test    ebx, ebx
0x180017a5f  js      short loc_180017ABD
0x180017a61  jmp     short loc_180017A6C
0x180017a63  cmp     [rsp+288h+NumberOfBytesRead], 6
0x180017a68  jnz     short loc_180017A75
0x180017a6a  xor     ebx, ebx
0x180017a6c  mov     al, [rbp+4]
0x180017a6f  dec     al
0x180017a71  cmp     al, 1
0x180017a73  jbe     short loc_180017A7C
0x180017a75  mov     ebx, 8000FFFFh
0x180017a7a  jmp     short loc_180017ABD
0x180017a7c  test    r14, r14
0x180017a7f  jz      short loc_180017ABD
0x180017a81  xor     r9d, r9d; dwMoveMethod
0x180017a84  xor     r8d, r8d; lpDistanceToMoveHigh
0x180017a87  xor     edx, edx; lDistanceToMove
0x180017a89  mov     rcx, rdi; hFile
0x180017a8c  call    cs:__imp_SetFilePointer
0x180017a93  nop     dword ptr [rax+rax+00h]
0x180017a98  cmp     eax, 0FFFFFFFFh
0x180017a9b  jz      short loc_180017AA2
0x180017a9d  mov     [r14], rdi
0x180017aa0  jmp     short loc_180017AD1
0x180017aa2  call    cs:__imp_GetLastError
0x180017aa9  nop     dword ptr [rax+rax+00h]
0x180017aae  mov     ebx, eax
0x180017ab0  test    eax, eax
0x180017ab2  jle     short loc_180017ABD
0x180017ab4  movzx   ebx, ax
0x180017ab7  or      ebx, 80070000h
0x180017abd  test    rdi, rdi
0x180017ac0  jz      short loc_180017AD1
0x180017ac2  mov     rcx, rdi; hObject
0x180017ac5  call    cs:__imp_CloseHandle
0x180017acc  nop     dword ptr [rax+rax+00h]
0x180017ad1  mov     eax, ebx
0x180017ad3  mov     rcx, [rsp+288h+var_28]
0x180017adb  xor     rcx, rsp; StackCookie
0x180017ade  call    __security_check_cookie
0x180017ae3  mov     rbx, [rsp+288h+arg_8]
0x180017aeb  add     rsp, 270h
0x180017af2  pop     r14
0x180017af4  pop     rdi
0x180017af5  pop     rbp
0x180017af6  retn
```
