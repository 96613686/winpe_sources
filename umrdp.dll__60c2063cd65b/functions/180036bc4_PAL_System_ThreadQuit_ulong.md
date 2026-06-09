# PAL_System_ThreadQuit(ulong)

- ea: `0x180036bc4`
- end: `0x180036cf7`
- name: `?PAL_System_ThreadQuit@@YAJK@Z`
- size: `307`
- prototype: `__int64 __fastcall(DWORD idThread)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003ea10`

## callees

- `0x1800010b0`
- `0x180036bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bfc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036c80`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036c80`
- `USER32!PostThreadMessageW` at `0x180036bee`
- `USER32!PostThreadMessageW` at `0x180036bee`

## string_xrefs

- `0x180036bdb`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x180036bd4`: `PAL_System_ThreadQuit`
- `0x180036c25`: `Failed to Post Thread Message with WM_QUIT. Retrying..`
- `0x180036c90`: `Failed to Post Thread Message with WM_QUIT. Fatal!`

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
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v12 = "PAL_System_ThreadQuit";
      v9 = "Failed to Post Thread Message with WM_QUIT. Retrying..";
      v10 = 796;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&dword_180054964,
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
  if ( (unsigned int)dword_18005C008 > 2 )
  {
    v12 = "PAL_System_ThreadQuit";
    v8 = "Failed to Post Thread Message with WM_QUIT. Fatal!";
    v10 = 799;
    v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (unsigned int)&word_180054A5E,
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
0x180036bc4  push    rbp
0x180036bc6  push    rbx
0x180036bc7  push    rsi
0x180036bc8  push    rdi
0x180036bc9  push    r14
0x180036bcb  mov     rbp, rsp
0x180036bce  sub     rsp, 60h
0x180036bd2  mov     edi, ecx
0x180036bd4  lea     rsi, aPalSystemThrea_6; "PAL_System_ThreadQuit"
0x180036bdb  lea     r14, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180036be2  xor     r9d, r9d; lParam
0x180036be5  xor     r8d, r8d; wParam
0x180036be8  mov     ecx, edi; idThread
0x180036bea  lea     edx, [r9+12h]; Msg
0x180036bee  call    cs:__imp_PostThreadMessageW
0x180036bf4  test    eax, eax
0x180036bf6  jnz     loc_180036CE8
0x180036bfc  call    cs:__imp_GetLastError
0x180036c02  test    eax, eax
0x180036c04  jg      short loc_180036C0A
0x180036c06  mov     ebx, eax
0x180036c08  jmp     short loc_180036C13
0x180036c0a  movzx   ebx, ax
0x180036c0d  or      ebx, 80070000h
0x180036c13  cmp     eax, 718h
0x180036c18  mov     eax, cs:dword_18005C008
0x180036c1e  jnz     short loc_180036C8B
0x180036c20  cmp     eax, 2
0x180036c23  jbe     short loc_180036C7B
0x180036c25  lea     rax, aFailedToPostTh_1; "Failed to Post Thread Message with WM_Q"...
0x180036c2c  mov     [rbp+arg_18], rsi
0x180036c30  mov     [rbp+var_8], rax
0x180036c34  lea     rdx, dword_180054964
0x180036c3b  lea     rax, [rbp+arg_18]
0x180036c3f  mov     [rbp+arg_8], 31Ch
0x180036c46  mov     [rsp+60h+var_20], rax
0x180036c4b  lea     rax, [rbp+arg_8]
0x180036c4f  mov     [rsp+60h+var_28], rax
0x180036c54  lea     rax, [rbp+var_10]
0x180036c58  mov     [rsp+60h+var_30], rax
0x180036c5d  lea     rax, [rbp+arg_10]
0x180036c61  mov     [rsp+60h+var_38], rax
0x180036c66  lea     rax, [rbp+var_8]
0x180036c6a  mov     [rsp+60h+var_40], rax
0x180036c6f  mov     [rbp+var_10], r14
0x180036c73  mov     [rbp+arg_10], ebx
0x180036c76  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036c7b  mov     ecx, 3E8h; dwMilliseconds
0x180036c80  call    cs:__imp_Sleep
0x180036c86  jmp     loc_180036BE2
0x180036c8b  cmp     eax, 2
0x180036c8e  jbe     short loc_180036CEA
0x180036c90  lea     rax, aFailedToPostTh; "Failed to Post Thread Message with WM_Q"...
0x180036c97  mov     [rbp+arg_18], rsi
0x180036c9b  mov     [rbp+var_10], rax
0x180036c9f  lea     rdx, word_180054A5E
0x180036ca6  lea     rax, [rbp+arg_18]
0x180036caa  mov     [rbp+arg_8], 31Fh
0x180036cb1  mov     [rsp+60h+var_20], rax
0x180036cb6  lea     rax, [rbp+arg_8]
0x180036cba  mov     [rsp+60h+var_28], rax
0x180036cbf  lea     rax, [rbp+var_8]
0x180036cc3  mov     [rsp+60h+var_30], rax
0x180036cc8  lea     rax, [rbp+arg_10]
0x180036ccc  mov     [rsp+60h+var_38], rax
0x180036cd1  lea     rax, [rbp+var_10]
0x180036cd5  mov     [rsp+60h+var_40], rax
0x180036cda  mov     [rbp+var_8], r14
0x180036cde  mov     [rbp+arg_10], ebx
0x180036ce1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036ce6  jmp     short loc_180036CEA
0x180036ce8  xor     ebx, ebx
0x180036cea  mov     eax, ebx
0x180036cec  add     rsp, 60h
0x180036cf0  pop     r14
0x180036cf2  pop     rdi
0x180036cf3  pop     rsi
0x180036cf4  pop     rbx
0x180036cf5  pop     rbp
0x180036cf6  retn
```
