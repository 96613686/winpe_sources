# ResourceStringCoAllocFormatMessage

- ea: `0x180063d40`
- end: `0x180063e6c`
- name: `ResourceStringCoAllocFormatMessage`
- size: `300`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e03c`
- `0x18003eb50`
- `0x18003f5f0`
- `0x180069578`

## callees

- `0x180006eb8`
- `0x180063bc8`
- `0x180063d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e3c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180063db6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180063db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063e59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063e59`

## pseudocode

```c
__int64 ResourceStringCoAllocFormatMessage(HMODULE a1, __int64 a2, _QWORD *a3, ...)
{
  int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  void *v8; // r11
  DWORD LastError; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-40h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-20h] BYREF
  LPCVOID lpSource; // [rsp+48h] [rbp-18h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-10h] BYREF
  va_list va; // [rsp+A8h] [rbp+48h] BYREF

  va_start(va, a3);
  va_copy(Arguments, va);
  lpSource = 0;
  v4 = TResourceStringAllocCopyEx<unsigned short *>(
         a1,
         a2,
         (__int64)a3,
         (__int64 (__fastcall *)(_QWORD, size_t, char **))ResourceStringAllocCopyExLocalAlloc,
         lpBuffer,
         (char *)&lpSource);
  if ( v4 >= 0 )
  {
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(0x500u, lpSource, 0, 0, Buffer, 0, &Arguments) )
    {
      v4 = -2147024882;
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v5) );
      v6 = (unsigned int)(v5 + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      if ( v7 )
      {
        v4 = StringCchCopyW(v7, (unsigned int)v6, *(const unsigned __int16 **)Buffer);
        if ( v4 >= 0 )
        {
          *a3 = v8;
          v8 = 0;
        }
        CoTaskMemFree(v8);
      }
      LocalFree(*(HLOCAL *)Buffer);
    }
    else if ( (GetLastError() & 0x80000000) == 0 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LOWORD(LastError) = 1;
      v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = GetLastError();
      if ( !v4 )
        v4 = 1;
    }
    LocalFree((HLOCAL)lpSource);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180063d40  mov     [rsp-28h+arg_10], r8
0x180063d45  mov     [rsp-28h+arg_18], r9
0x180063d4a  push    rbp
0x180063d4b  push    rbx
0x180063d4c  push    rsi
0x180063d4d  push    rdi
0x180063d4e  push    r14
0x180063d50  mov     rbp, rsp
0x180063d53  sub     rsp, 60h
0x180063d57  xor     r14d, r14d
0x180063d5a  lea     rax, [rbp+arg_18]
0x180063d5e  mov     [rbp+var_10], r14
0x180063d62  lea     r9, _ResourceStringAllocCopyExLocalAlloc; int
0x180063d69  mov     [rbp+var_10], rax
0x180063d6d  mov     rsi, r8
0x180063d70  lea     rax, [rbp+lpSource]
0x180063d74  mov     [rbp+lpSource], r14
0x180063d78  mov     qword ptr [rsp+60h+nSize], rax; void *
0x180063d7d  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180063d82  mov     ebx, eax
0x180063d84  test    eax, eax
0x180063d86  js      loc_180063E5F
0x180063d8c  mov     rdx, [rbp+lpSource]; lpSource
0x180063d90  lea     rax, [rbp+var_10]
0x180063d94  mov     [rsp+60h+Arguments], rax; Arguments
0x180063d99  xor     r9d, r9d; dwLanguageId
0x180063d9c  lea     rax, [rbp+Buffer]
0x180063da0  mov     [rsp+60h+nSize], r14d; nSize
0x180063da5  xor     r8d, r8d; dwMessageId
0x180063da8  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x180063dad  mov     ecx, 500h; dwFlags
0x180063db2  mov     qword ptr [rbp+Buffer], r14
0x180063db6  call    cs:__imp_FormatMessageW
0x180063dbc  test    eax, eax
0x180063dbe  jz      short loc_180063E1C
0x180063dc0  mov     rcx, qword ptr [rbp+Buffer]
0x180063dc4  mov     ebx, 8007000Eh
0x180063dc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063dcd  inc     rax
0x180063dd0  cmp     [rcx+rax*2], r14w
0x180063dd5  jnz     short loc_180063DCD
0x180063dd7  inc     eax
0x180063dd9  mov     edi, eax
0x180063ddb  lea     rcx, [rax+rax]; cb
0x180063ddf  call    cs:__imp_CoTaskMemAlloc
0x180063de5  mov     r11, rax
0x180063de8  test    rax, rax
0x180063deb  jz      short loc_180063E10
0x180063ded  mov     r8, qword ptr [rbp+Buffer]; unsigned __int16 *
0x180063df1  mov     edx, edi; unsigned __int64
0x180063df3  mov     rcx, rax; unsigned __int16 *
0x180063df6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063dfb  mov     ebx, eax
0x180063dfd  test    eax, eax
0x180063dff  js      short loc_180063E07
0x180063e01  mov     [rsi], r11
0x180063e04  mov     r11, r14
0x180063e07  mov     rcx, r11; pv
0x180063e0a  call    cs:__imp_CoTaskMemFree
0x180063e10  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x180063e14  call    cs:__imp_LocalFree
0x180063e1a  jmp     short loc_180063E55
0x180063e1c  call    cs:__imp_GetLastError
0x180063e22  test    eax, eax
0x180063e24  jz      short loc_180063E3C
0x180063e26  jg      short loc_180063E3C
0x180063e28  call    cs:__imp_GetLastError
0x180063e2e  test    eax, eax
0x180063e30  mov     ebx, eax
0x180063e32  mov     ecx, 1
0x180063e37  cmovz   ebx, ecx
0x180063e3a  jmp     short loc_180063E55
0x180063e3c  call    cs:__imp_GetLastError
0x180063e42  test    eax, eax
0x180063e44  mov     ecx, 1
0x180063e49  cmovz   eax, ecx
0x180063e4c  movzx   ebx, ax
0x180063e4f  or      ebx, 80070000h
0x180063e55  mov     rcx, [rbp+lpSource]; hMem
0x180063e59  call    cs:__imp_LocalFree
0x180063e5f  mov     eax, ebx
0x180063e61  add     rsp, 60h
0x180063e65  pop     r14
0x180063e67  pop     rdi
0x180063e68  pop     rsi
0x180063e69  pop     rbx
0x180063e6a  pop     rbp
0x180063e6b  retn
```
