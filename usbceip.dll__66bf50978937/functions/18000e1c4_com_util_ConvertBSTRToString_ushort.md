# _com_util::ConvertBSTRToString(ushort *)

- ea: `0x18000e1c4`
- end: `0x18000e24b`
- name: `?ConvertBSTRToString@_com_util@@YAPEADPEAG@Z`
- size: `135`
- prototype: `char *__fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004344`

## callees

- `0x18000246c`
- `0x18000e190`
- `0x18000e1c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e225`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e21b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e21b`

## pseudocode

```c
char *__fastcall _com_util::ConvertBSTRToString(LPCWCH lpWideCharStr)
{
  __int64 v3; // rbx
  int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rax
  CHAR *v6; // rsi
  signed int LastError; // eax
  struct IErrorInfo *v8; // rdx

  if ( !lpWideCharStr )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( lpWideCharStr[v3] );
  cbMultiByte = 2 * v3 + 2;
  lpMultiByteStr = (CHAR *)operator new(cbMultiByte);
  *lpMultiByteStr = 0;
  v6 = lpMultiByteStr;
  if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _com_issue_error(LastError, v8);
  }
  return v6;
}

```

## disassembly

```asm
0x18000e1c4  push    rbx
0x18000e1c6  push    rbp
0x18000e1c7  push    rsi
0x18000e1c8  push    rdi
0x18000e1c9  sub     rsp, 48h
0x18000e1cd  xor     ebp, ebp
0x18000e1cf  mov     rdi, rcx
0x18000e1d2  test    rcx, rcx
0x18000e1d5  jnz     short loc_18000E1DB
0x18000e1d7  xor     eax, eax
0x18000e1d9  jmp     short loc_18000E242
0x18000e1db  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e1df  inc     rbx
0x18000e1e2  cmp     [rcx+rbx*2], bp
0x18000e1e6  jnz     short loc_18000E1DF
0x18000e1e8  lea     ebx, ds:2[rbx*2]
0x18000e1ef  movsxd  rcx, ebx; Size
0x18000e1f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e1f7  mov     [rsp+68h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18000e1fc  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000e200  mov     [rsp+68h+lpDefaultChar], rbp; lpDefaultChar
0x18000e205  mov     r8, rdi; lpWideCharStr
0x18000e208  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x18000e20c  xor     edx, edx; dwFlags
0x18000e20e  xor     ecx, ecx; CodePage
0x18000e210  mov     [rax], bpl
0x18000e213  mov     rsi, rax
0x18000e216  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x18000e21b  call    cs:__imp_WideCharToMultiByte
0x18000e221  test    eax, eax
0x18000e223  jnz     short loc_18000E23F
0x18000e225  call    cs:__imp_GetLastError
0x18000e22b  test    eax, eax
0x18000e22d  jle     short loc_18000E237
0x18000e22f  movzx   eax, ax
0x18000e232  or      eax, 80070000h
0x18000e237  mov     ecx, eax; int
0x18000e239  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000e23f  mov     rax, rsi
0x18000e242  add     rsp, 48h
0x18000e246  pop     rdi
0x18000e247  pop     rsi
0x18000e248  pop     rbp
0x18000e249  pop     rbx
0x18000e24a  retn
```
