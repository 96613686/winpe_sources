# PAL_System_CritSecInit

- ea: `0x180009410`
- end: `0x180009586`
- name: `PAL_System_CritSecInit`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005694`
- `0x18000adf8`
- `0x180035fc4`

## callees

- `0x1800010b0`
- `0x180009410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800094e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800094e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009433`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009433`

## string_xrefs

- `0x180009464`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x180009518`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CritSecInit(struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v3; // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  const char *v7; // [rsp+50h] [rbp-18h] BYREF
  int v8; // [rsp+70h] [rbp+8h] BYREF
  int v9; // [rsp+78h] [rbp+10h] BYREF
  const char *v10; // [rsp+80h] [rbp+18h] BYREF
  const char *v11; // [rsp+88h] [rbp+20h] BYREF

  if ( !a1 )
    return 2147942487LL;
  v3 = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0x40u, 0x28u);
  if ( v3 )
  {
    LODWORD(v10) = -2147467259;
    *a1 = v3;
    InitializeCriticalSection(v3);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v10 = "PAL_System_CritSecInit";
      v8 = 698;
      v11 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v9 = -2147467259;
      v7 = "Failed to allocate CRITICAL_SECTION";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)&word_1800541FE,
        v5,
        v6,
        (__int64)&v7,
        (__int64)&v9,
        (__int64)&v11,
        (__int64)&v8,
        (__int64)&v10);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180009410  push    rbx
0x180009412  sub     rsp, 60h
0x180009416  mov     rbx, rcx
0x180009419  test    rcx, rcx
0x18000941c  jnz     short loc_180009429
0x18000941e  mov     eax, 80070057h
0x180009423  add     rsp, 60h
0x180009427  pop     rbx
0x180009428  retn
0x180009429  mov     edx, 28h ; '('; uBytes
0x18000942e  mov     ecx, 40h ; '@'; uFlags
0x180009433  call    cs:__imp_LocalAlloc
0x180009439  test    rax, rax
0x18000943c  jnz     loc_1800094D6
0x180009442  mov     eax, cs:dword_18005C008
0x180009448  cmp     eax, 2
0x18000944b  jbe     short loc_1800094CB
0x18000944d  lea     rax, aPalSystemCrits; "PAL_System_CritSecInit"
0x180009454  mov     [rsp+68h+arg_10], rax
0x18000945c  mov     [rsp+68h+arg_0], 2BAh
0x180009464  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18000946b  mov     [rsp+68h+arg_18], rax
0x180009473  mov     [rsp+68h+arg_8], 80004005h
0x18000947b  lea     rax, aFailedToAlloca_0; "Failed to allocate CRITICAL_SECTION"
0x180009482  mov     [rsp+68h+var_18], rax
0x180009487  lea     rax, [rsp+68h+arg_10]
0x18000948f  mov     [rsp+68h+var_28], rax
0x180009494  lea     rax, [rsp+68h+arg_0]
0x180009499  mov     [rsp+68h+var_30], rax
0x18000949e  lea     rax, [rsp+68h+arg_18]
0x1800094a6  mov     [rsp+68h+var_38], rax
0x1800094ab  lea     rax, [rsp+68h+arg_8]
0x1800094b0  mov     [rsp+68h+var_40], rax
0x1800094b5  lea     rax, [rsp+68h+var_18]
0x1800094ba  mov     [rsp+68h+var_48], rax
0x1800094bf  lea     rdx, word_1800541FE
0x1800094c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800094cb  mov     eax, 8007000Eh
0x1800094d0  add     rsp, 60h
0x1800094d4  pop     rbx
0x1800094d5  retn
0x1800094d6  mov     dword ptr [rsp+68h+arg_10], 80004005h
0x1800094e1  mov     [rbx], rax
0x1800094e4  mov     rcx, rax; lpCriticalSection
0x1800094e7  call    cs:__imp_InitializeCriticalSection
0x1800094ed  nop
0x1800094ee  xor     eax, eax
0x1800094f0  add     rsp, 60h
0x1800094f4  pop     rbx
0x1800094f5  retn
0x1800094f6  mov     eax, cs:dword_18005C008
0x1800094fc  cmp     eax, 2
0x1800094ff  jbe     short loc_180009579
0x180009501  lea     rax, aPalSystemCrits; "PAL_System_CritSecInit"
0x180009508  mov     [rsp+68h+arg_18], rax
0x180009510  mov     [rsp+68h+arg_0], 2C5h
0x180009518  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18000951f  mov     [rsp+68h+var_18], rax
0x180009524  mov     [rsp+68h+arg_8], 80004005h
0x18000952c  lea     rax, aFailToInitialz; "Fail to initialzie critical section"
0x180009533  mov     [rsp+68h+var_10], rax
0x180009538  lea     rax, [rsp+68h+arg_18]
0x180009540  mov     [rsp+68h+var_28], rax
0x180009545  lea     rax, [rsp+68h+arg_0]
0x18000954a  mov     [rsp+68h+var_30], rax
0x18000954f  lea     rax, [rsp+68h+var_18]
0x180009554  mov     [rsp+68h+var_38], rax
0x180009559  lea     rax, [rsp+68h+arg_8]
0x18000955e  mov     [rsp+68h+var_40], rax
0x180009563  lea     rax, [rsp+68h+var_10]
0x180009568  mov     [rsp+68h+var_48], rax
0x18000956d  lea     rdx, byte_18005449D
0x180009574  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180009579  mov     eax, dword ptr [rsp+68h+arg_10]
0x180009580  add     rsp, 60h
0x180009584  pop     rbx
0x180009585  retn
```
