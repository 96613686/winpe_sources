# PAL_System_ThreadSignalPulse(void *)

- ea: `0x180036e2c`
- end: `0x180036ef6`
- name: `?PAL_System_ThreadSignalPulse@@YAJPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003ea00`

## callees

- `0x1800011c8`
- `0x180036e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e73`
- `USER32!PostMessageW` at `0x180036e55`
- `USER32!PostMessageW` at `0x180036e55`

## string_xrefs

- `0x180036e95`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x180036e8a`: `PAL_System_ThreadSignalPulse`
- `0x180036ea0`: `Failed to post thread message. Error %d`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalPulse(void *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  const char *v7; // [rsp+50h] [rbp-18h] BYREF
  const char *v8; // [rsp+58h] [rbp-10h] BYREF
  DWORD v9; // [rsp+80h] [rbp+18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF
  int v11; // [rsp+90h] [rbp+28h] BYREF
  const char *v12; // [rsp+98h] [rbp+30h] BYREF

  if ( a1 )
  {
    if ( PostMessageW(*(HWND *)a1, 0x413u, *((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2)) )
    {
      return 0;
    }
    else
    {
      v1 = -2147467259;
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        LastError = GetLastError();
        v10 = 683;
        v9 = LastError;
        v12 = "PAL_System_ThreadSignalPulse";
        v7 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        v8 = "Failed to post thread message. Error %d";
        v11 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v3,
          (unsigned int)&byte_18005490F,
          v4,
          v5,
          (__int64)&v8,
          (__int64)&v11,
          (__int64)&v7,
          (__int64)&v10,
          (__int64)&v12,
          (__int64)&v9);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x180036e2c  push    rbp
0x180036e2e  push    rbx
0x180036e2f  mov     rbp, rsp
0x180036e32  sub     rsp, 68h
0x180036e36  test    rcx, rcx
0x180036e39  jnz     short loc_180036E45
0x180036e3b  mov     ebx, 80070057h
0x180036e40  jmp     loc_180036EED
0x180036e45  mov     r9, [rcx+10h]; lParam
0x180036e49  mov     edx, 413h; Msg
0x180036e4e  mov     r8, [rcx+8]; wParam
0x180036e52  mov     rcx, [rcx]; hWnd
0x180036e55  call    cs:__imp_PostMessageW
0x180036e5b  test    eax, eax
0x180036e5d  jnz     loc_180036EEB
0x180036e63  mov     eax, cs:dword_18005C008
0x180036e69  mov     ebx, 80004005h
0x180036e6e  cmp     eax, 2
0x180036e71  jbe     short loc_180036EED
0x180036e73  call    cs:__imp_GetLastError
0x180036e79  lea     rdx, byte_18005490F
0x180036e80  mov     [rbp+arg_8], 2ABh
0x180036e87  mov     [rbp+arg_0], eax
0x180036e8a  lea     rax, aPalSystemThrea_1; "PAL_System_ThreadSignalPulse"
0x180036e91  mov     [rbp+arg_18], rax
0x180036e95  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180036e9c  mov     [rbp+var_18], rax
0x180036ea0  lea     rax, aFailedToPostTh_0; "Failed to post thread message. Error %d"
0x180036ea7  mov     [rbp+var_10], rax
0x180036eab  lea     rax, [rbp+arg_0]
0x180036eaf  mov     [rsp+68h+var_20], rax
0x180036eb4  lea     rax, [rbp+arg_18]
0x180036eb8  mov     [rsp+68h+var_28], rax
0x180036ebd  lea     rax, [rbp+arg_8]
0x180036ec1  mov     [rsp+68h+var_30], rax
0x180036ec6  lea     rax, [rbp+var_18]
0x180036eca  mov     [rsp+68h+var_38], rax
0x180036ecf  lea     rax, [rbp+arg_10]
0x180036ed3  mov     [rsp+68h+var_40], rax
0x180036ed8  lea     rax, [rbp+var_10]
0x180036edc  mov     [rsp+68h+var_48], rax
0x180036ee1  mov     [rbp+arg_10], ebx
0x180036ee4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180036ee9  jmp     short loc_180036EED
0x180036eeb  xor     ebx, ebx
0x180036eed  mov     eax, ebx
0x180036eef  add     rsp, 68h
0x180036ef3  pop     rbx
0x180036ef4  pop     rbp
0x180036ef5  retn
```
