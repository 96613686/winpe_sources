# PAL_System_CritSecInit

- ea: `0x180005e38`
- end: `0x180005fa9`
- name: `PAL_System_CritSecInit`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004970`

## callees

- `0x180001008`
- `0x180005e38`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180005f0b`
- `KERNEL32!InitializeCriticalSection` at `0x180005f0b`
- `KERNEL32!LocalAlloc` at `0x180005e58`
- `KERNEL32!LocalAlloc` at `0x180005e58`

## string_xrefs

- `0x180005e89`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x180005f3b`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`

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
    if ( (unsigned int)dword_180013020 > 2 )
    {
      v10 = "PAL_System_CritSecInit";
      v8 = 698;
      v11 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v9 = -2147467259;
      v7 = "Failed to allocate CRITICAL_SECTION";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)byte_180010F19,
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
0x180005e38  push    rbx
0x180005e3a  sub     rsp, 60h
0x180005e3e  mov     rbx, rcx
0x180005e41  test    rcx, rcx
0x180005e44  jnz     short loc_180005E50
0x180005e46  mov     eax, 80070057h
0x180005e4b  jmp     loc_180005FA3
0x180005e50  mov     edx, 28h ; '('; uBytes
0x180005e55  lea     ecx, [rdx+18h]; uFlags
0x180005e58  call    cs:__imp_LocalAlloc
0x180005e5e  test    rax, rax
0x180005e61  jnz     loc_180005EFA
0x180005e67  mov     eax, cs:dword_180013020
0x180005e6d  cmp     eax, 2
0x180005e70  jbe     short loc_180005EF0
0x180005e72  lea     rax, aPalSystemCrits; "PAL_System_CritSecInit"
0x180005e79  mov     [rsp+68h+arg_10], rax
0x180005e81  mov     [rsp+68h+arg_0], 2BAh
0x180005e89  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180005e90  mov     [rsp+68h+arg_18], rax
0x180005e98  mov     [rsp+68h+arg_8], 80004005h
0x180005ea0  lea     rax, aFailedToAlloca; "Failed to allocate CRITICAL_SECTION"
0x180005ea7  mov     [rsp+68h+var_18], rax
0x180005eac  lea     rax, [rsp+68h+arg_10]
0x180005eb4  mov     [rsp+68h+var_28], rax
0x180005eb9  lea     rax, [rsp+68h+arg_0]
0x180005ebe  mov     [rsp+68h+var_30], rax
0x180005ec3  lea     rax, [rsp+68h+arg_18]
0x180005ecb  mov     [rsp+68h+var_38], rax
0x180005ed0  lea     rax, [rsp+68h+arg_8]
0x180005ed5  mov     [rsp+68h+var_40], rax
0x180005eda  lea     rax, [rsp+68h+var_18]
0x180005edf  mov     [rsp+68h+var_48], rax
0x180005ee4  lea     rdx, byte_180010F19
0x180005eeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180005ef0  mov     eax, 8007000Eh
0x180005ef5  jmp     loc_180005FA3
0x180005efa  mov     dword ptr [rsp+68h+arg_10], 80004005h
0x180005f05  mov     [rbx], rax
0x180005f08  mov     rcx, rax; lpCriticalSection
0x180005f0b  call    cs:__imp_InitializeCriticalSection
0x180005f11  nop
0x180005f12  xor     eax, eax
0x180005f14  jmp     loc_180005FA3
0x180005f19  mov     eax, cs:dword_180013020
0x180005f1f  cmp     eax, 2
0x180005f22  jbe     short loc_180005F9C
0x180005f24  lea     rax, aPalSystemCrits; "PAL_System_CritSecInit"
0x180005f2b  mov     [rsp+68h+arg_18], rax
0x180005f33  mov     [rsp+68h+arg_0], 2C5h
0x180005f3b  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180005f42  mov     [rsp+68h+var_18], rax
0x180005f47  mov     [rsp+68h+arg_8], 80004005h
0x180005f4f  lea     rax, aFailToInitialz; "Fail to initialzie critical section"
0x180005f56  mov     [rsp+68h+var_10], rax
0x180005f5b  lea     rax, [rsp+68h+arg_18]
0x180005f63  mov     [rsp+68h+var_28], rax
0x180005f68  lea     rax, [rsp+68h+arg_0]
0x180005f6d  mov     [rsp+68h+var_30], rax
0x180005f72  lea     rax, [rsp+68h+var_18]
0x180005f77  mov     [rsp+68h+var_38], rax
0x180005f7c  lea     rax, [rsp+68h+arg_8]
0x180005f81  mov     [rsp+68h+var_40], rax
0x180005f86  lea     rax, [rsp+68h+var_10]
0x180005f8b  mov     [rsp+68h+var_48], rax
0x180005f90  lea     rdx, word_180010F5E
0x180005f97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180005f9c  mov     eax, dword ptr [rsp+68h+arg_10]
0x180005fa3  add     rsp, 60h
0x180005fa7  pop     rbx
0x180005fa8  retn
```
