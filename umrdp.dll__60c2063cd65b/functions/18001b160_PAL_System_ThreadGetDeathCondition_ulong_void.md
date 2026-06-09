# PAL_System_ThreadGetDeathCondition(ulong,void * *)

- ea: `0x18001b160`
- end: `0x18001b245`
- name: `?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(DWORD dwThreadId, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800392d0`

## callees

- `0x1800012ec`
- `0x18001b160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1af`
- `KERNEL32!OpenThread` at `0x18001b18c`
- `KERNEL32!OpenThread` at `0x18001b18c`

## string_xrefs

- `0x18001b1cd`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001b1c2`: `PAL_System_ThreadGetDeathCondition`
- `0x18001b1d8`: `Failed to open thread %#x. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetDeathCondition(DWORD dwThreadId, void **a2)
{
  unsigned int v4; // ebx
  HANDLE v5; // rax
  DWORD LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+60h] [rbp-20h] BYREF
  const char *v12; // [rsp+68h] [rbp-18h] BYREF
  const char *v13; // [rsp+70h] [rbp-10h] BYREF
  const char *v14; // [rsp+78h] [rbp-8h] BYREF
  DWORD v15; // [rsp+A8h] [rbp+28h] BYREF
  DWORD v16; // [rsp+B0h] [rbp+30h] BYREF
  int v17; // [rsp+B8h] [rbp+38h] BYREF

  if ( a2 )
  {
    v5 = OpenThread(0x100000u, 0, dwThreadId);
    if ( v5 )
    {
      *a2 = v5;
      return 0;
    }
    else
    {
      v4 = -2147467259;
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        LastError = GetLastError();
        v16 = dwThreadId;
        v15 = LastError;
        v12 = "PAL_System_ThreadGetDeathCondition";
        v13 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v14 = "Failed to open thread %#x. GetLastError: 0x%x";
        v17 = 1522;
        v11 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)word_180054322,
          v8,
          v9,
          (__int64)&v14,
          (__int64)&v11,
          (__int64)&v13,
          (__int64)&v17,
          (__int64)&v12,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001b160  push    rbp
0x18001b162  push    rbx
0x18001b163  push    rdi
0x18001b164  mov     rbp, rsp
0x18001b167  sub     rsp, 80h
0x18001b16e  mov     rbx, rdx
0x18001b171  mov     edi, ecx
0x18001b173  test    rdx, rdx
0x18001b176  jnz     short loc_18001B182
0x18001b178  mov     ebx, 80070057h
0x18001b17d  jmp     loc_18001B238
0x18001b182  mov     r8d, edi; dwThreadId
0x18001b185  xor     edx, edx; bInheritHandle
0x18001b187  mov     ecx, 100000h; dwDesiredAccess
0x18001b18c  call    cs:__imp_OpenThread
0x18001b192  test    rax, rax
0x18001b195  jnz     loc_18001B233
0x18001b19b  mov     eax, cs:dword_18005C008
0x18001b1a1  mov     ebx, 80004005h
0x18001b1a6  cmp     eax, 2
0x18001b1a9  jbe     loc_18001B238
0x18001b1af  call    cs:__imp_GetLastError
0x18001b1b5  lea     rdx, word_180054322
0x18001b1bc  mov     [rbp+arg_10], edi
0x18001b1bf  mov     [rbp+arg_8], eax
0x18001b1c2  lea     rax, aPalSystemThrea_5; "PAL_System_ThreadGetDeathCondition"
0x18001b1c9  mov     [rbp+var_18], rax
0x18001b1cd  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001b1d4  mov     [rbp+var_10], rax
0x18001b1d8  lea     rax, aFailedToOpenTh; "Failed to open thread %#x. GetLastError"...
0x18001b1df  mov     [rbp+var_8], rax
0x18001b1e3  lea     rax, [rbp+arg_8]
0x18001b1e7  mov     [rsp+80h+var_30], rax
0x18001b1ec  lea     rax, [rbp+arg_10]
0x18001b1f0  mov     [rsp+80h+var_38], rax
0x18001b1f5  lea     rax, [rbp+var_18]
0x18001b1f9  mov     [rsp+80h+var_40], rax
0x18001b1fe  lea     rax, [rbp+arg_18]
0x18001b202  mov     [rsp+80h+var_48], rax
0x18001b207  lea     rax, [rbp+var_10]
0x18001b20b  mov     [rsp+80h+var_50], rax
0x18001b210  lea     rax, [rbp+var_20]
0x18001b214  mov     [rsp+80h+var_58], rax
0x18001b219  lea     rax, [rbp+var_8]
0x18001b21d  mov     [rsp+80h+var_60], rax
0x18001b222  mov     [rbp+arg_18], 5F2h
0x18001b229  mov     [rbp+var_20], ebx
0x18001b22c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b231  jmp     short loc_18001B238
0x18001b233  mov     [rbx], rax
0x18001b236  xor     ebx, ebx
0x18001b238  mov     eax, ebx
0x18001b23a  add     rsp, 80h
0x18001b241  pop     rdi
0x18001b242  pop     rbx
0x18001b243  pop     rbp
0x18001b244  retn
```
