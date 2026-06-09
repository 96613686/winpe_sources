# PAL_System_ThreadSignalDestroy(void *)

- ea: `0x180036d00`
- end: `0x180036e23`
- name: `?PAL_System_ThreadSignalDestroy@@YAJPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003e9f0`

## callees

- `0x1800010b0`
- `0x180036d00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036e14`
- `USER32!DestroyWindow` at `0x180036d94`
- `USER32!DestroyWindow` at `0x180036d94`

## string_xrefs

- `0x180036d38`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x180036dc2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x180036d1f`: `PAL_System_ThreadSignalDestroy`
- `0x180036da9`: `PAL_System_ThreadSignalDestroy`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalDestroy(HWND *hMem, __int64 a2, int a3, int a4)
{
  HWND v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  _QWORD v10[3]; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF
  int v12; // [rsp+88h] [rbp+20h] BYREF
  const char *v13; // [rsp+90h] [rbp+28h] BYREF
  const char *v14; // [rsp+98h] [rbp+30h] BYREF

  if ( hMem )
  {
    v6 = *hMem;
    if ( v6 && !DestroyWindow(v6) && (unsigned int)dword_18005C008 > 2 )
    {
      v11 = 735;
      v13 = "PAL_System_ThreadSignalDestroy";
      v12 = -2147467259;
      v14 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v10[0] = "Failed to destroy window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)&dword_1800549D4,
        v8,
        v9,
        (__int64)v10,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v13);
    }
    LocalFree(hMem);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v11 = 724;
      v13 = "PAL_System_ThreadSignalDestroy";
      v12 = -2147467259;
      v14 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v10[0] = "NULL parameter passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)word_1800548CA,
        a3,
        a4,
        (__int64)v10,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v13);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180036d00  mov     r11, rsp
0x180036d03  push    rbp
0x180036d04  push    rbx
0x180036d05  mov     rbp, rsp
0x180036d08  sub     rsp, 68h
0x180036d0c  mov     rbx, rcx
0x180036d0f  test    rcx, rcx
0x180036d12  jnz     short loc_180036D8C
0x180036d14  mov     eax, cs:dword_18005C008
0x180036d1a  cmp     eax, 2
0x180036d1d  jbe     short loc_180036D82
0x180036d1f  lea     rax, aPalSystemThrea_7; "PAL_System_ThreadSignalDestroy"
0x180036d26  mov     [rbp+arg_0], 2D4h
0x180036d2d  mov     [rbp+arg_10], rax
0x180036d31  lea     rdx, word_1800548CA
0x180036d38  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180036d3f  mov     [rbp+arg_8], 80004005h
0x180036d46  mov     [rbp+arg_18], rax
0x180036d4a  lea     rax, aNullParameterP; "NULL parameter passed"
0x180036d51  mov     [rbp+var_18], rax
0x180036d55  lea     rax, [rbp+arg_10]
0x180036d59  mov     [r11-38h], rax
0x180036d5d  lea     rax, [rbp+arg_0]
0x180036d61  mov     [r11-40h], rax
0x180036d65  lea     rax, [rbp+arg_18]
0x180036d69  mov     [r11-48h], rax
0x180036d6d  lea     rax, [rbp+arg_8]
0x180036d71  mov     [r11-50h], rax
0x180036d75  lea     rax, [rbp+var_18]
0x180036d79  mov     [r11-58h], rax
0x180036d7d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036d82  mov     eax, 80070057h
0x180036d87  jmp     loc_180036E1C
0x180036d8c  mov     rcx, [rcx]; hWnd
0x180036d8f  test    rcx, rcx
0x180036d92  jz      short loc_180036E11
0x180036d94  call    cs:__imp_DestroyWindow
0x180036d9a  test    eax, eax
0x180036d9c  jnz     short loc_180036E11
0x180036d9e  mov     eax, cs:dword_18005C008
0x180036da4  cmp     eax, 2
0x180036da7  jbe     short loc_180036E11
0x180036da9  lea     rax, aPalSystemThrea_7; "PAL_System_ThreadSignalDestroy"
0x180036db0  mov     [rbp+arg_0], 2DFh
0x180036db7  mov     [rbp+arg_10], rax
0x180036dbb  lea     rdx, dword_1800549D4
0x180036dc2  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180036dc9  mov     [rbp+arg_8], 80004005h
0x180036dd0  mov     [rbp+arg_18], rax
0x180036dd4  lea     rax, aFailedToDestro; "Failed to destroy window"
0x180036ddb  mov     [rbp+var_18], rax
0x180036ddf  lea     rax, [rbp+arg_10]
0x180036de3  mov     [rsp+68h+var_28], rax
0x180036de8  lea     rax, [rbp+arg_0]
0x180036dec  mov     [rsp+68h+var_30], rax
0x180036df1  lea     rax, [rbp+arg_18]
0x180036df5  mov     [rsp+68h+var_38], rax
0x180036dfa  lea     rax, [rbp+arg_8]
0x180036dfe  mov     [rsp+68h+var_40], rax
0x180036e03  lea     rax, [rbp+var_18]
0x180036e07  mov     [rsp+68h+var_48], rax
0x180036e0c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036e11  mov     rcx, rbx; hMem
0x180036e14  call    cs:__imp_LocalFree
0x180036e1a  xor     eax, eax
0x180036e1c  add     rsp, 68h
0x180036e20  pop     rbx
0x180036e21  pop     rbp
0x180036e22  retn
```
