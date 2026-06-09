# CreateDesktopIni(ushort const *)

- ea: `0x18002a5c0`
- end: `0x18002a72e`
- name: `?CreateDesktopIni@@YAJPEBG@Z`
- size: `366`
- prototype: `signed int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002a734`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x18002a5c0`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a65e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a65e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a702`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a6d7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a6d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a64f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a64f`

## string_xrefs

- `0x18002a679`: `[.ShellClassInfo]\nCLSID={d6277990-4c6a-11cf-8d87-00aa0060f5bf}\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall CreateDesktopIni(const unsigned __int16 *a1)
{
  unsigned int v2; // r10d
  HANDLE FileW; // rdi
  signed int result; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD Buffer[5]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(FileName, 0, 0x20Au);
  StringCchCopyW(FileName, 0x105u, a1);
  StringCchCatW(FileName, v2, L"\\desktop.ini");
  FileW = CreateFileW(FileName, 0x40000000u, 1u, 0, 1u, 3u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    strcpy((char *)Buffer, "[.ShellClassInfo]\r\nCLSID={d6277990-4c6a-11cf-8d87-00aa0060f5bf}\r\n");
    NumberOfBytesWritten = 0;
    if ( !WriteFile(FileW, Buffer, 0x41u, &NumberOfBytesWritten, 0) || (v5 = 0, NumberOfBytesWritten != 65) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(FileW);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002a5c0  mov     [rsp-8+arg_8], rbx
0x18002a5c5  mov     [rsp-8+arg_10], rdi
0x18002a5ca  push    rbp
0x18002a5cb  lea     rbp, [rsp-1C0h]
0x18002a5d3  sub     rsp, 2C0h
0x18002a5da  mov     rax, cs:__security_cookie
0x18002a5e1  xor     rax, rsp
0x18002a5e4  mov     [rbp+1C0h+var_10], rax
0x18002a5eb  mov     rbx, rcx
0x18002a5ee  xor     edx, edx; Val
0x18002a5f0  lea     rcx, [rbp+1C0h+FileName]; void *
0x18002a5f4  mov     r8d, 20Ah; Size
0x18002a5fa  call    memset_0
0x18002a5ff  mov     r10d, 105h
0x18002a605  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18002a609  mov     edx, r10d; unsigned __int64
0x18002a60c  mov     r8, rbx; unsigned __int16 *
0x18002a60f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a614  lea     r8, aDesktopIni; "\\desktop.ini"
0x18002a61b  mov     edx, r10d; unsigned __int64
0x18002a61e  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18002a622  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a627  mov     r8d, 1; dwShareMode
0x18002a62d  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18002a636  mov     [rsp+2C0h+dwFlagsAndAttributes], 3; dwFlagsAndAttributes
0x18002a63e  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18002a642  xor     r9d, r9d; lpSecurityAttributes
0x18002a645  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002a64a  mov     edx, 40000000h; dwDesiredAccess
0x18002a64f  call    cs:__imp_CreateFileW
0x18002a655  mov     rdi, rax
0x18002a658  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a65c  jnz     short loc_18002A679
0x18002a65e  call    cs:__imp_GetLastError
0x18002a664  test    eax, eax
0x18002a666  jle     loc_18002A70A
0x18002a66c  movzx   eax, ax
0x18002a66f  or      eax, 80070000h
0x18002a674  jmp     loc_18002A70A
0x18002a679  movaps  xmm0, xmmword ptr cs:aShellclassinfo; "[.ShellClassInfo]\r\nCLSID={d6277990-4c"...
0x18002a680  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002a685  movaps  xmm1, xmmword ptr cs:aShellclassinfo+10h; "]\r\nCLSID={d6277990-4c6a-11cf-8d87-00a"...
0x18002a68c  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x18002a691  movzx   eax, word ptr cs:aShellclassinfo+40h; "\n"
0x18002a698  mov     r8d, 41h ; 'A'; nNumberOfBytesToWrite
0x18002a69e  movaps  [rsp+2C0h+Buffer], xmm0
0x18002a6a3  mov     rcx, rdi; hFile
0x18002a6a6  movaps  xmm0, xmmword ptr cs:aShellclassinfo+20h; "90-4c6a-11cf-8d87-00aa0060f5bf}\r\n"
0x18002a6ad  movaps  [rsp+2C0h+var_260], xmm1
0x18002a6b2  movaps  xmm1, xmmword ptr cs:aShellclassinfo+30h; "7-00aa0060f5bf}\r\n"
0x18002a6b9  movaps  [rsp+2C0h+var_250], xmm0
0x18002a6be  movaps  [rbp+1C0h+var_240], xmm1
0x18002a6c2  mov     [rbp+1C0h+var_230], ax
0x18002a6c6  mov     [rsp+2C0h+NumberOfBytesWritten], 0
0x18002a6ce  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x18002a6d7  call    cs:__imp_WriteFile
0x18002a6dd  test    eax, eax
0x18002a6df  jz      short loc_18002A6EA
0x18002a6e1  xor     ebx, ebx
0x18002a6e3  cmp     [rsp+2C0h+NumberOfBytesWritten], 41h ; 'A'
0x18002a6e8  jz      short loc_18002A6FF
0x18002a6ea  call    cs:__imp_GetLastError
0x18002a6f0  mov     ebx, eax
0x18002a6f2  test    eax, eax
0x18002a6f4  jle     short loc_18002A6FF
0x18002a6f6  movzx   ebx, ax
0x18002a6f9  or      ebx, 80070000h
0x18002a6ff  mov     rcx, rdi; hObject
0x18002a702  call    cs:__imp_CloseHandle
0x18002a708  mov     eax, ebx
0x18002a70a  mov     rcx, [rbp+1C0h+var_10]
0x18002a711  xor     rcx, rsp; StackCookie
0x18002a714  call    __security_check_cookie
0x18002a719  lea     r11, [rsp+2C0h+var_s0]
0x18002a721  mov     rbx, [r11+18h]
0x18002a725  mov     rdi, [r11+20h]
0x18002a729  mov     rsp, r11
0x18002a72c  pop     rbp
0x18002a72d  retn
```
