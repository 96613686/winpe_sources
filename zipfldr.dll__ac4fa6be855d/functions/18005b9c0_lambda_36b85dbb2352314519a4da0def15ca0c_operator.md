# _lambda_36b85dbb2352314519a4da0def15ca0c_::operator()

- ea: `0x18005b9c0`
- end: `0x18005baaa`
- name: `_lambda_36b85dbb2352314519a4da0def15ca0c_::operator()`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180059d20`

## callees

- `0x180036f50`
- `0x18005b9c0`
- `0x18005de08`

## import_xrefs

- `archiveint!archive_set_error` at `0x18005ba83`
- `archiveint!archive_set_error` at `0x18005ba83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ba44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ba44`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005ba29`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005ba29`

## string_xrefs

- `0x18005ba76`: `Failed to write data to archive file`
- `0x18005ba5b`: `shell\ext\zip\archive\archivecreate.cpp`

## pseudocode

```c
__int64 __fastcall lambda_36b85dbb2352314519a4da0def15ca0c_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // rdi
  DWORD v10; // r8d
  void *v11; // rcx
  signed int LastError; // eax
  int lpOverlapped; // [rsp+20h] [rbp-48h]
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a5;
  v6 = 0;
  if ( a5 )
  {
    while ( 1 )
    {
      v10 = v5;
      if ( v5 >= 0xFFFFFFFF )
        v10 = -1;
      v11 = *(void **)(a3 + 32);
      NumberOfBytesWritten = 0;
      if ( !WriteFile(v11, a4, v10, &NumberOfBytesWritten, 0) )
        break;
      v6 += NumberOfBytesWritten;
      a4 += NumberOfBytesWritten;
      v5 -= NumberOfBytesWritten;
      if ( !v5 )
        return v6;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = -1;
    *(_DWORD *)(a3 + 124) = wil::details::in1diag3::Log_Hr(
                              retaddr,
                              (void *)0x76,
                              (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                              (const char *)(unsigned int)LastError,
                              lpOverlapped);
    archive_set_error(a2, 5, "Failed to write data to archive file");
  }
  return v6;
}

```

## disassembly

```asm
0x18005b9c0  mov     [rsp+arg_0], rbx
0x18005b9c5  push    rbp
0x18005b9c6  push    rsi
0x18005b9c7  push    rdi
0x18005b9c8  push    r14
0x18005b9ca  push    r15
0x18005b9cc  sub     rsp, 40h
0x18005b9d0  mov     rax, cs:__security_cookie
0x18005b9d7  xor     rax, rsp
0x18005b9da  mov     [rsp+68h+var_30], rax
0x18005b9df  mov     rbx, [rsp+68h+arg_20]
0x18005b9e7  xor     edi, edi
0x18005b9e9  mov     rsi, r9
0x18005b9ec  mov     rbp, r8
0x18005b9ef  mov     r14, rdx
0x18005b9f2  test    rbx, rbx
0x18005b9f5  jz      loc_18005BA89
0x18005b9fb  mov     r15d, 0FFFFFFFFh
0x18005ba01  mov     r8d, ebx
0x18005ba04  cmp     rbx, r15
0x18005ba07  jb      short loc_18005BA0C
0x18005ba09  mov     r8d, r15d; nNumberOfBytesToWrite
0x18005ba0c  mov     rcx, [rbp+20h]; hFile
0x18005ba10  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005ba15  mov     rdx, rsi; lpBuffer
0x18005ba18  mov     [rsp+68h+NumberOfBytesWritten], 0
0x18005ba20  mov     qword ptr [rsp+68h+lpOverlapped], 0; int
0x18005ba29  call    cs:__imp_WriteFile
0x18005ba2f  test    eax, eax
0x18005ba31  jz      short loc_18005BA44
0x18005ba33  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x18005ba37  add     rdi, rax
0x18005ba3a  add     rsi, rax
0x18005ba3d  sub     rbx, rax
0x18005ba40  jnz     short loc_18005BA01
0x18005ba42  jmp     short loc_18005BA89
0x18005ba44  call    cs:__imp_GetLastError
0x18005ba4a  test    eax, eax
0x18005ba4c  jle     short loc_18005BA56
0x18005ba4e  movzx   eax, ax
0x18005ba51  or      eax, 80070000h
0x18005ba56  mov     rcx, [rsp+68h]; this
0x18005ba5b  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005ba62  mov     r9d, eax; char *
0x18005ba65  mov     edx, 76h ; 'v'; void *
0x18005ba6a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18005ba6f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ba73  mov     [rbp+7Ch], eax
0x18005ba76  lea     r8, aFailedToWriteD; "Failed to write data to archive file"
0x18005ba7d  mov     rcx, r14
0x18005ba80  lea     edx, [rdi+6]
0x18005ba83  call    cs:__imp_archive_set_error
0x18005ba89  mov     rax, rdi
0x18005ba8c  mov     rcx, [rsp+68h+var_30]
0x18005ba91  xor     rcx, rsp; StackCookie
0x18005ba94  call    __security_check_cookie
0x18005ba99  mov     rbx, [rsp+68h+arg_0]
0x18005ba9e  add     rsp, 40h
0x18005baa2  pop     r15
0x18005baa4  pop     r14
0x18005baa6  pop     rdi
0x18005baa7  pop     rsi
0x18005baa8  pop     rbp
0x18005baa9  retn
```
