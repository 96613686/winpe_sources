# UpdateWatermarkState(ulong,uchar const *,ushort const *,ushort const *)

- ea: `0x18002ab90`
- end: `0x18002ace1`
- name: `?UpdateWatermarkState@@YAJKPEBEPEBG1@Z`
- size: `337`
- prototype: `__int64 __fastcall(DWORD nNumberOfBytesToWrite, LPCVOID lpBuffer, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x18002ace8`
- `0x18002ade4`
- `0x18002af60`

## callees

- `0x180008320`
- `0x180012ef0`
- `0x180021ec0`
- `0x180022a10`
- `0x18002a480`
- `0x18002ab90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acaa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ac75`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ac75`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ac30`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ac30`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall UpdateWatermarkState(
        DWORD nNumberOfBytesToWrite,
        LPCVOID lpBuffer,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned __int64 v8; // rdx
  signed int v9; // ebx
  HANDLE FileW; // rax
  void *v11; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-268h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-258h] BYREF

  memset_0(FileName, 0, 0x208u);
  if ( a4 )
  {
    v9 = StringCchCopyW(FileName, 0x104u, a4);
    if ( v9 < 0 )
      goto LABEL_15;
  }
  v9 = StringCchCatW(FileName, v8, a3);
  if ( v9 < 0 )
    goto LABEL_15;
  FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
    CloseHandle(v11);
    goto LABEL_14;
  }
  NumberOfBytesWritten = 0;
  if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
      v9 = 1;
  }
  else
  {
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( v11 )
    goto LABEL_13;
LABEL_14:
  if ( v9 < 0 )
LABEL_15:
    DeleteWatermarkState(a3, a4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002ab90  push    rbx
0x18002ab92  push    rbp
0x18002ab93  push    rsi
0x18002ab94  push    rdi
0x18002ab95  push    r14
0x18002ab97  push    r15
0x18002ab99  sub     rsp, 278h
0x18002aba0  mov     rax, cs:__security_cookie
0x18002aba7  xor     rax, rsp
0x18002abaa  mov     [rsp+2A8h+var_48], rax
0x18002abb2  mov     r14, r8
0x18002abb5  mov     r15, rdx
0x18002abb8  mov     ebp, ecx
0x18002abba  xor     edx, edx; Val
0x18002abbc  mov     r8d, 208h; Size
0x18002abc2  lea     rcx, [rsp+2A8h+FileName]; void *
0x18002abc7  mov     rsi, r9
0x18002abca  call    memset_0
0x18002abcf  test    rsi, rsi
0x18002abd2  jz      short loc_18002ABF0
0x18002abd4  mov     r8, rsi; unsigned __int16 *
0x18002abd7  lea     rcx, [rsp+2A8h+FileName]; unsigned __int16 *
0x18002abdc  mov     edx, 104h; unsigned __int64
0x18002abe1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002abe6  mov     ebx, eax
0x18002abe8  test    eax, eax
0x18002abea  js      loc_18002ACB4
0x18002abf0  mov     r8, r14; unsigned __int16 *
0x18002abf3  lea     rcx, [rsp+2A8h+FileName]; unsigned __int16 *
0x18002abf8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002abfd  mov     ebx, eax
0x18002abff  test    eax, eax
0x18002ac01  js      loc_18002ACB4
0x18002ac07  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x18002ac10  lea     rcx, [rsp+2A8h+FileName]; lpFileName
0x18002ac15  mov     [rsp+2A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002ac1d  xor     r9d, r9d; lpSecurityAttributes
0x18002ac20  xor     r8d, r8d; dwShareMode
0x18002ac23  mov     [rsp+2A8h+dwCreationDisposition], 2; dwCreationDisposition
0x18002ac2b  mov     edx, 40000000h; dwDesiredAccess
0x18002ac30  call    cs:__imp_CreateFileW
0x18002ac36  mov     rdi, rax
0x18002ac39  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ac3d  jnz     short loc_18002AC56
0x18002ac3f  call    cs:__imp_GetLastError
0x18002ac45  mov     ebx, eax
0x18002ac47  test    eax, eax
0x18002ac49  jle     short loc_18002ACA7
0x18002ac4b  movzx   ebx, ax
0x18002ac4e  or      ebx, 80070000h
0x18002ac54  jmp     short loc_18002ACA7
0x18002ac56  lea     r9, [rsp+2A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ac5b  mov     [rsp+2A8h+NumberOfBytesWritten], 0
0x18002ac63  mov     r8d, ebp; nNumberOfBytesToWrite
0x18002ac66  mov     qword ptr [rsp+2A8h+dwCreationDisposition], 0; lpOverlapped
0x18002ac6f  mov     rdx, r15; lpBuffer
0x18002ac72  mov     rcx, rdi; hFile
0x18002ac75  call    cs:__imp_WriteFile
0x18002ac7b  test    eax, eax
0x18002ac7d  jnz     short loc_18002AC96
0x18002ac7f  call    cs:__imp_GetLastError
0x18002ac85  mov     ebx, eax
0x18002ac87  test    eax, eax
0x18002ac89  jle     short loc_18002ACA2
0x18002ac8b  movzx   ebx, ax
0x18002ac8e  or      ebx, 80070000h
0x18002ac94  jmp     short loc_18002ACA2
0x18002ac96  cmp     [rsp+2A8h+NumberOfBytesWritten], ebp
0x18002ac9a  mov     eax, 1
0x18002ac9f  cmovnz  ebx, eax
0x18002aca2  test    rdi, rdi
0x18002aca5  jz      short loc_18002ACB0
0x18002aca7  mov     rcx, rdi; hObject
0x18002acaa  call    cs:__imp_CloseHandle
0x18002acb0  test    ebx, ebx
0x18002acb2  jns     short loc_18002ACBF
0x18002acb4  mov     rdx, rsi; unsigned __int16 *
0x18002acb7  mov     rcx, r14; unsigned __int16 *
0x18002acba  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002acbf  mov     eax, ebx
0x18002acc1  mov     rcx, [rsp+2A8h+var_48]
0x18002acc9  xor     rcx, rsp; StackCookie
0x18002accc  call    __security_check_cookie
0x18002acd1  add     rsp, 278h
0x18002acd8  pop     r15
0x18002acda  pop     r14
0x18002acdc  pop     rdi
0x18002acdd  pop     rsi
0x18002acde  pop     rbp
0x18002acdf  pop     rbx
0x18002ace0  retn
```
