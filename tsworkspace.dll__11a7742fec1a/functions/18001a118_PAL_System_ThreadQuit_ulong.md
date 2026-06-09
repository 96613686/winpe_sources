# PAL_System_ThreadQuit(ulong)

- ea: `0x18001a118`
- end: `0x18001a24b`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800182c0`

## callees

- `0x180001180`
- `0x18001a118`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a150`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a1d4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a1d4`
- `USER32!PostThreadMessageW` at `0x18001a142`
- `USER32!PostThreadMessageW` at `0x18001a142`

## string_xrefs

- `0x18001a12f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001a128`: `PAL_System_ThreadQuit`
- `0x18001a179`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x18001a1e4`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadQuit(DWORD idThread)
{
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  const char *v8; // [rsp+50h] [rbp-10h] BYREF
  const char *v9; // [rsp+58h] [rbp-8h] BYREF
  int v10; // [rsp+98h] [rbp+38h] BYREF
  unsigned int v11; // [rsp+A0h] [rbp+40h] BYREF
  const char *v12; // [rsp+A8h] [rbp+48h] BYREF

  while ( 1 )
  {
    if ( PostThreadMessageW(idThread, 0x12u, 0, 0) )
      return 0;
    LastError = GetLastError();
    v6 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( LastError != 1816 )
      break;
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_1800CD014,
        v4,
        v5,
        (__int64)&v9,
        (__int64)&v11,
        (__int64)&v8,
        (__int64)&v10,
        (__int64)&v12);
    }
    Sleep(0x3E8u);
  }
  if ( (unsigned int)dword_1800EB958 > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)&word_1800CD10E,
      v4,
      v5,
      (__int64)&v8,
      (__int64)&v11,
      (__int64)&v9,
      (__int64)&v10,
      (__int64)&v12);
  }
  return v6;
}

```

## disassembly

```asm
0x18001a118  push    rbp
0x18001a11a  push    rbx
0x18001a11b  push    rsi
0x18001a11c  push    rdi
0x18001a11d  push    r14
0x18001a11f  mov     rbp, rsp
0x18001a122  sub     rsp, 60h
0x18001a126  mov     edi, ecx
0x18001a128  lea     rsi, aPalSystemThrea_6; "PAL_System_ThreadQuit"
0x18001a12f  lea     r14, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001a136  xor     r9d, r9d; lParam
0x18001a139  xor     r8d, r8d; wParam
0x18001a13c  mov     ecx, edi; idThread
0x18001a13e  lea     edx, [r9+12h]; Msg
0x18001a142  call    cs:__imp_PostThreadMessageW
0x18001a148  test    eax, eax
0x18001a14a  jnz     loc_18001A23C
0x18001a150  call    cs:__imp_GetLastError
0x18001a156  test    eax, eax
0x18001a158  jg      short loc_18001A15E
0x18001a15a  mov     ebx, eax
0x18001a15c  jmp     short loc_18001A167
0x18001a15e  movzx   ebx, ax
0x18001a161  or      ebx, 80070000h
0x18001a167  cmp     eax, 718h
0x18001a16c  mov     eax, cs:dword_1800EB958
0x18001a172  jnz     short loc_18001A1DF
0x18001a174  cmp     eax, 2
0x18001a177  jbe     short loc_18001A1CF
0x18001a179  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x18001a180  mov     [rbp+arg_18], rsi
0x18001a184  mov     [rbp+var_8], rax
0x18001a188  lea     rdx, dword_1800CD014
0x18001a18f  lea     rax, [rbp+arg_18]
0x18001a193  mov     [rbp+arg_8], 31Ch
0x18001a19a  mov     [rsp+60h+var_20], rax
0x18001a19f  lea     rax, [rbp+arg_8]
0x18001a1a3  mov     [rsp+60h+var_28], rax
0x18001a1a8  lea     rax, [rbp+var_10]
0x18001a1ac  mov     [rsp+60h+var_30], rax
0x18001a1b1  lea     rax, [rbp+arg_10]
0x18001a1b5  mov     [rsp+60h+var_38], rax
0x18001a1ba  lea     rax, [rbp+var_8]
0x18001a1be  mov     [rsp+60h+var_40], rax
0x18001a1c3  mov     [rbp+var_10], r14
0x18001a1c7  mov     [rbp+arg_10], ebx
0x18001a1ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a1cf  mov     ecx, 3E8h; dwMilliseconds
0x18001a1d4  call    cs:__imp_Sleep
0x18001a1da  jmp     loc_18001A136
0x18001a1df  cmp     eax, 2
0x18001a1e2  jbe     short loc_18001A23E
0x18001a1e4  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x18001a1eb  mov     [rbp+arg_18], rsi
0x18001a1ef  mov     [rbp+var_10], rax
0x18001a1f3  lea     rdx, word_1800CD10E
0x18001a1fa  lea     rax, [rbp+arg_18]
0x18001a1fe  mov     [rbp+arg_8], 31Fh
0x18001a205  mov     [rsp+60h+var_20], rax
0x18001a20a  lea     rax, [rbp+arg_8]
0x18001a20e  mov     [rsp+60h+var_28], rax
0x18001a213  lea     rax, [rbp+var_8]
0x18001a217  mov     [rsp+60h+var_30], rax
0x18001a21c  lea     rax, [rbp+arg_10]
0x18001a220  mov     [rsp+60h+var_38], rax
0x18001a225  lea     rax, [rbp+var_10]
0x18001a229  mov     [rsp+60h+var_40], rax
0x18001a22e  mov     [rbp+var_8], r14
0x18001a232  mov     [rbp+arg_10], ebx
0x18001a235  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a23a  jmp     short loc_18001A23E
0x18001a23c  xor     ebx, ebx
0x18001a23e  mov     eax, ebx
0x18001a240  add     rsp, 60h
0x18001a244  pop     r14
0x18001a246  pop     rdi
0x18001a247  pop     rsi
0x18001a248  pop     rbx
0x18001a249  pop     rbp
0x18001a24a  retn
```
