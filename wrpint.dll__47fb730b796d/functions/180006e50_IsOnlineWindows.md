# IsOnlineWindows

- ea: `0x180006e50`
- end: `0x180006f7e`
- name: `IsOnlineWindows`
- size: `302`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800038e0`

## callees

- `0x180001de0`
- `0x180006e50`
- `0x180010de4`
- `0x180011248`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ed7`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180006ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180006ecd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006f20`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006f20`

## pseudocode

```c
__int64 __fastcall IsOnlineWindows(__int64 a1, _DWORD *a2)
{
  LPCWSTR v2; // rdi
  signed int v4; // ebx
  signed int LastError; // eax
  LPCWSTR lpString2; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpString1; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = 0;
  lpString1 = 0;
  lpString2 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = SczAllocFromSz(&lpString1, a1);
    if ( v4 >= 0 )
    {
      v4 = SczEnsureBackslashTerminated(&lpString1);
      if ( v4 >= 0 )
      {
        if ( GetWindowsDirectoryW(Buffer, 0x104u) )
        {
          v4 = SczAllocFromSz(&lpString2, Buffer);
          if ( v4 < 0 || (v4 = SczEnsureBackslashTerminated(&lpString2), v4 < 0) )
          {
            v2 = lpString2;
          }
          else
          {
            v2 = lpString2;
            if ( !lstrcmpiW(lpString1, lpString2) )
              *a2 = 1;
            v4 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    if ( lpString1 )
      operator delete((void *)(lpString1 - 4));
    if ( v2 )
      operator delete((void *)(v2 - 4));
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006e50  mov     [rsp-8+arg_10], rbx
0x180006e55  push    rbp
0x180006e56  push    rsi
0x180006e57  push    rdi
0x180006e58  lea     rbp, [rsp-150h]
0x180006e60  sub     rsp, 250h
0x180006e67  mov     rax, cs:__security_cookie
0x180006e6e  xor     rax, rsp
0x180006e71  mov     [rbp+160h+var_20], rax
0x180006e78  xor     edi, edi
0x180006e7a  mov     [rsp+260h+lpString1], 0
0x180006e83  mov     [rsp+260h+lpString2], rdi
0x180006e88  mov     rsi, rdx
0x180006e8b  test    rdx, rdx
0x180006e8e  jnz     short loc_180006E9A
0x180006e90  mov     ebx, 80070057h
0x180006e95  jmp     loc_180006F5A
0x180006e9a  mov     [rdx], edi
0x180006e9c  mov     rdx, rcx
0x180006e9f  lea     rcx, [rsp+260h+lpString1]
0x180006ea4  call    SczAllocFromSz
0x180006ea9  mov     ebx, eax
0x180006eab  test    eax, eax
0x180006ead  js      loc_180006F39
0x180006eb3  lea     rcx, [rsp+260h+lpString1]
0x180006eb8  call    SczEnsureBackslashTerminated
0x180006ebd  mov     ebx, eax
0x180006ebf  test    eax, eax
0x180006ec1  js      short loc_180006F39
0x180006ec3  mov     edx, 104h; uSize
0x180006ec8  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x180006ecd  call    cs:__imp_GetWindowsDirectoryW
0x180006ed3  test    eax, eax
0x180006ed5  jnz     short loc_180006EEE
0x180006ed7  call    cs:__imp_GetLastError
0x180006edd  mov     ebx, eax
0x180006edf  test    eax, eax
0x180006ee1  jle     short loc_180006F39
0x180006ee3  movzx   ebx, ax
0x180006ee6  or      ebx, 80070000h
0x180006eec  jmp     short loc_180006F39
0x180006eee  lea     rdx, [rsp+260h+Buffer]
0x180006ef3  lea     rcx, [rsp+260h+lpString2]
0x180006ef8  call    SczAllocFromSz
0x180006efd  mov     ebx, eax
0x180006eff  test    eax, eax
0x180006f01  js      short loc_180006F34
0x180006f03  lea     rcx, [rsp+260h+lpString2]
0x180006f08  call    SczEnsureBackslashTerminated
0x180006f0d  mov     ebx, eax
0x180006f0f  test    eax, eax
0x180006f11  js      short loc_180006F34
0x180006f13  mov     rdi, [rsp+260h+lpString2]
0x180006f18  mov     rcx, [rsp+260h+lpString1]; lpString1
0x180006f1d  mov     rdx, rdi; lpString2
0x180006f20  call    cs:__imp_lstrcmpiW
0x180006f26  test    eax, eax
0x180006f28  jnz     short loc_180006F30
0x180006f2a  mov     dword ptr [rsi], 1
0x180006f30  xor     ebx, ebx
0x180006f32  jmp     short loc_180006F39
0x180006f34  mov     rdi, [rsp+260h+lpString2]
0x180006f39  mov     rcx, [rsp+260h+lpString1]
0x180006f3e  test    rcx, rcx
0x180006f41  jz      short loc_180006F4C
0x180006f43  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180006f47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006f4c  test    rdi, rdi
0x180006f4f  jz      short loc_180006F5A
0x180006f51  lea     rcx, [rdi-8]; Block
0x180006f55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006f5a  mov     eax, ebx
0x180006f5c  mov     rcx, [rbp+160h+var_20]
0x180006f63  xor     rcx, rsp; StackCookie
0x180006f66  call    __security_check_cookie
0x180006f6b  mov     rbx, [rsp+260h+arg_10]
0x180006f73  add     rsp, 250h
0x180006f7a  pop     rdi
0x180006f7b  pop     rsi
0x180006f7c  pop     rbp
0x180006f7d  retn
```
