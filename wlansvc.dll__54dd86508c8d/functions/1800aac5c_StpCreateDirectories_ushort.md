# StpCreateDirectories(ushort *)

- ea: `0x1800aac5c`
- end: `0x1800aad1b`
- name: `?StpCreateDirectories@@YAKPEAG@Z`
- size: `191`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1802016e0`

## callees

- `0x1800aac5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800aac87`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800aac87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aaca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aaca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacf8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aac9d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aacee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aac9d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aacee`

## pseudocode

```c
__int64 __fastcall StpCreateDirectories(LPCWSTR lpPathName)
{
  __int64 v1; // rdi
  wchar_t *v3; // rax
  wchar_t *v4; // rsi
  unsigned int v5; // ebx
  const WCHAR *v6; // rdi
  __int64 v7; // rax

  v1 = -1;
  do
    ++v1;
  while ( lpPathName[v1] );
  while ( 1 )
  {
    v3 = wcsrchr(lpPathName, 0x5Cu);
    v4 = v3;
    if ( !v3 )
      return 161;
    *v3 = 0;
    if ( CreateDirectoryW(lpPathName, 0) || GetLastError() == 183 )
      break;
    if ( GetLastError() != 3 )
      return GetLastError();
  }
  v5 = 0;
  v6 = &lpPathName[v1];
  while ( 1 )
  {
    *v4 = 92;
    v7 = -1;
    do
      ++v7;
    while ( v4[v7] );
    v4 += v7;
    if ( v4 >= v6 )
      break;
    if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
      return GetLastError();
  }
  return v5;
}

```

## disassembly

```asm
0x1800aac5c  push    rbx
0x1800aac5e  push    rbp
0x1800aac5f  push    rsi
0x1800aac60  push    rdi
0x1800aac61  push    r12
0x1800aac63  push    r14
0x1800aac65  sub     rsp, 28h
0x1800aac69  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800aac6d  mov     r14, rcx
0x1800aac70  xor     ebp, ebp
0x1800aac72  inc     rdi
0x1800aac75  cmp     [rcx+rdi*2], bp
0x1800aac79  jnz     short loc_1800AAC72
0x1800aac7b  mov     r12d, 5Ch ; '\'
0x1800aac81  mov     edx, r12d; Ch
0x1800aac84  mov     rcx, r14; Str
0x1800aac87  call    cs:__imp_wcsrchr
0x1800aac8d  mov     rsi, rax
0x1800aac90  test    rax, rax
0x1800aac93  jz      short loc_1800AAD07
0x1800aac95  xor     edx, edx; lpSecurityAttributes
0x1800aac97  mov     [rax], bp
0x1800aac9a  mov     rcx, r14; lpPathName
0x1800aac9d  call    cs:__imp_CreateDirectoryW
0x1800aaca3  test    eax, eax
0x1800aaca5  jnz     short loc_1800AACC9
0x1800aaca7  call    cs:__imp_GetLastError
0x1800aacad  cmp     eax, 0B7h
0x1800aacb2  jz      short loc_1800AACC9
0x1800aacb4  call    cs:__imp_GetLastError
0x1800aacba  cmp     eax, 3
0x1800aacbd  jz      short loc_1800AAC81
0x1800aacbf  call    cs:__imp_GetLastError
0x1800aacc5  mov     ebx, eax
0x1800aacc7  jmp     short loc_1800AAD0C
0x1800aacc9  mov     ebx, ebp
0x1800aaccb  lea     rdi, [r14+rdi*2]
0x1800aaccf  mov     [rsi], r12w
0x1800aacd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800aacd7  inc     rax
0x1800aacda  cmp     [rsi+rax*2], bp
0x1800aacde  jnz     short loc_1800AACD7
0x1800aace0  lea     rsi, [rsi+rax*2]
0x1800aace4  cmp     rsi, rdi
0x1800aace7  jnb     short loc_1800AAD0C
0x1800aace9  xor     edx, edx; lpSecurityAttributes
0x1800aaceb  mov     rcx, r14; lpPathName
0x1800aacee  call    cs:__imp_CreateDirectoryW
0x1800aacf4  test    eax, eax
0x1800aacf6  jnz     short loc_1800AACCF
0x1800aacf8  call    cs:__imp_GetLastError
0x1800aacfe  cmp     eax, 0B7h
0x1800aad03  jz      short loc_1800AACCF
0x1800aad05  jmp     short loc_1800AACBF
0x1800aad07  mov     ebx, 0A1h
0x1800aad0c  mov     eax, ebx
0x1800aad0e  add     rsp, 28h
0x1800aad12  pop     r14
0x1800aad14  pop     r12
0x1800aad16  pop     rdi
0x1800aad17  pop     rsi
0x1800aad18  pop     rbp
0x1800aad19  pop     rbx
0x1800aad1a  retn
```
