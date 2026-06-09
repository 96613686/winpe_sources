# _GetTempFilePath

- ea: `0x18003d25c`
- end: `0x18003d2df`
- name: `_GetTempFilePath`
- size: `131`
- prototype: `__int64 __fastcall(LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003d850`

## callees

- `0x18003d25c`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003d2a0`
- `KERNEL32!GetLastError` at `0x18003d2a0`
- `KERNEL32!GetTempPathW` at `0x18003d296`
- `KERNEL32!GetTempPathW` at `0x18003d296`
- `KERNEL32!GetTempFileNameW` at `0x18003d2ba`
- `KERNEL32!GetTempFileNameW` at `0x18003d2ba`

## pseudocode

```c
DWORD __fastcall GetTempFilePath(LPWSTR lpTempFileName)
{
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( GetTempPathW(0x104u, Buffer) && GetTempFileNameW(Buffer, L".contact", 0, lpTempFileName) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18003d25c  push    rbx
0x18003d25e  sub     rsp, 240h
0x18003d265  mov     rax, cs:__security_cookie
0x18003d26c  xor     rax, rsp
0x18003d26f  mov     [rsp+248h+var_18], rax
0x18003d277  mov     rbx, rcx
0x18003d27a  xor     edx, edx; Val
0x18003d27c  lea     rcx, [rsp+248h+Buffer]; void *
0x18003d281  mov     r8d, 208h; Size
0x18003d287  call    memset_0
0x18003d28c  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x18003d291  mov     ecx, 104h; nBufferLength
0x18003d296  call    cs:__imp_GetTempPathW
0x18003d29c  test    eax, eax
0x18003d29e  jnz     short loc_18003D2A8
0x18003d2a0  call    cs:__imp_GetLastError
0x18003d2a6  jmp     short loc_18003D2C6
0x18003d2a8  mov     r9, rbx; lpTempFileName
0x18003d2ab  lea     rdx, PrefixString; ".contact"
0x18003d2b2  xor     r8d, r8d; uUnique
0x18003d2b5  lea     rcx, [rsp+248h+Buffer]; lpPathName
0x18003d2ba  call    cs:__imp_GetTempFileNameW
0x18003d2c0  test    eax, eax
0x18003d2c2  jz      short loc_18003D2A0
0x18003d2c4  xor     eax, eax
0x18003d2c6  mov     rcx, [rsp+248h+var_18]
0x18003d2ce  xor     rcx, rsp; StackCookie
0x18003d2d1  call    __security_check_cookie
0x18003d2d6  add     rsp, 240h
0x18003d2dd  pop     rbx
0x18003d2de  retn
```
