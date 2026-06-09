# CreateDesktopIni(ushort const *)

- ea: `0x18002c0a4`
- end: `0x18002c231`
- name: `?CreateDesktopIni@@YAJPEBG@Z`
- size: `397`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002c238`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x18002c0a4`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c1fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c1fe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c1c7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c1c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c133`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c133`

## string_xrefs

- `0x18002c169`: `[.ShellClassInfo]\nCLSID={d6277990-4c6a-11cf-8d87-00aa0060f5bf}\n`

## pseudocode

```c
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
0x18002c0a4  mov     [rsp-8+arg_8], rbx
0x18002c0a9  mov     [rsp-8+arg_10], rdi
0x18002c0ae  push    rbp
0x18002c0af  lea     rbp, [rsp-1C0h]
0x18002c0b7  sub     rsp, 2C0h
0x18002c0be  mov     rax, cs:__security_cookie
0x18002c0c5  xor     rax, rsp
0x18002c0c8  mov     [rbp+1C0h+var_10], rax
0x18002c0cf  mov     rbx, rcx
0x18002c0d2  xor     edx, edx; Val
0x18002c0d4  lea     rcx, [rbp+1C0h+FileName]; void *
0x18002c0d8  mov     r8d, 20Ah; Size
0x18002c0de  call    memset_0
0x18002c0e3  mov     r10d, 105h
0x18002c0e9  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18002c0ed  mov     edx, r10d; unsigned __int64
0x18002c0f0  mov     r8, rbx; unsigned __int16 *
0x18002c0f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c0f8  lea     r8, aDesktopIni; "\\desktop.ini"
0x18002c0ff  mov     edx, r10d; unsigned __int64
0x18002c102  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18002c106  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c10b  mov     r8d, 1; dwShareMode
0x18002c111  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18002c11a  mov     [rsp+2C0h+dwFlagsAndAttributes], 3; dwFlagsAndAttributes
0x18002c122  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18002c126  xor     r9d, r9d; lpSecurityAttributes
0x18002c129  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002c12e  mov     edx, 40000000h; dwDesiredAccess
0x18002c133  call    cs:__imp_CreateFileW
0x18002c13a  nop     dword ptr [rax+rax+00h]
0x18002c13f  mov     rdi, rax
0x18002c142  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c146  jnz     short loc_18002C169
0x18002c148  call    cs:__imp_GetLastError
0x18002c14f  nop     dword ptr [rax+rax+00h]
0x18002c154  test    eax, eax
0x18002c156  jle     loc_18002C20C
0x18002c15c  movzx   eax, ax
0x18002c15f  or      eax, 80070000h
0x18002c164  jmp     loc_18002C20C
0x18002c169  movaps  xmm0, xmmword ptr cs:aShellclassinfo; "[.ShellClassInfo]\r\nCLSID={d6277990-4c"...
0x18002c170  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002c175  movaps  xmm1, xmmword ptr cs:aShellclassinfo+10h; "]\r\nCLSID={d6277990-4c6a-11cf-8d87-00a"...
0x18002c17c  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x18002c181  movzx   eax, word ptr cs:aShellclassinfo+40h; "\n"
0x18002c188  mov     r8d, 41h ; 'A'; nNumberOfBytesToWrite
0x18002c18e  movaps  [rsp+2C0h+Buffer], xmm0
0x18002c193  mov     rcx, rdi; hFile
0x18002c196  movaps  xmm0, xmmword ptr cs:aShellclassinfo+20h; "90-4c6a-11cf-8d87-00aa0060f5bf}\r\n"
0x18002c19d  movaps  [rsp+2C0h+var_260], xmm1
0x18002c1a2  movaps  xmm1, xmmword ptr cs:aShellclassinfo+30h; "7-00aa0060f5bf}\r\n"
0x18002c1a9  movaps  [rsp+2C0h+var_250], xmm0
0x18002c1ae  movaps  [rbp+1C0h+var_240], xmm1
0x18002c1b2  mov     [rbp+1C0h+var_230], ax
0x18002c1b6  mov     [rsp+2C0h+NumberOfBytesWritten], 0
0x18002c1be  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x18002c1c7  call    cs:__imp_WriteFile
0x18002c1ce  nop     dword ptr [rax+rax+00h]
0x18002c1d3  test    eax, eax
0x18002c1d5  jz      short loc_18002C1E0
0x18002c1d7  xor     ebx, ebx
0x18002c1d9  cmp     [rsp+2C0h+NumberOfBytesWritten], 41h ; 'A'
0x18002c1de  jz      short loc_18002C1FB
0x18002c1e0  call    cs:__imp_GetLastError
0x18002c1e7  nop     dword ptr [rax+rax+00h]
0x18002c1ec  mov     ebx, eax
0x18002c1ee  test    eax, eax
0x18002c1f0  jle     short loc_18002C1FB
0x18002c1f2  movzx   ebx, ax
0x18002c1f5  or      ebx, 80070000h
0x18002c1fb  mov     rcx, rdi; hObject
0x18002c1fe  call    cs:__imp_CloseHandle
0x18002c205  nop     dword ptr [rax+rax+00h]
0x18002c20a  mov     eax, ebx
0x18002c20c  mov     rcx, [rbp+1C0h+var_10]
0x18002c213  xor     rcx, rsp; StackCookie
0x18002c216  call    __security_check_cookie
0x18002c21b  lea     r11, [rsp+2C0h+var_s0]
0x18002c223  mov     rbx, [r11+18h]
0x18002c227  mov     rdi, [r11+20h]
0x18002c22b  mov     rsp, r11
0x18002c22e  pop     rbp
0x18002c22f  retn
```
