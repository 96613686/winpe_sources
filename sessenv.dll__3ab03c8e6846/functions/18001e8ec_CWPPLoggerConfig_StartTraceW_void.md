# CWPPLoggerConfig::StartTraceW(void)

- ea: `0x18001e8ec`
- end: `0x18001eba1`
- name: `?StartTraceW@CWPPLoggerConfig@@AEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001e23c`
- `0x18001e6f8`

## callees

- `0x1800014b8`
- `0x1800017d0`
- `0x180004e00`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x18001e468`
- `0x18001e8ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e94d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e94d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001e9bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001e9bf`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001ea7e`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001eab1`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001ea7e`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001eab1`

## pseudocode

```c
__int64 __fastcall CWPPLoggerConfig::StartTraceW(CWPPLoggerConfig *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // r15
  signed int started; // eax
  int v7; // r8d
  int v8; // r9d
  ULONG v9; // esi
  int v10; // ecx
  __int64 v11; // rax
  const char *v12; // rcx
  int wYear; // [rsp+28h] [rbp-D8h]
  int wMonth; // [rsp+30h] [rbp-D0h]
  int wDay; // [rsp+38h] [rbp-C8h]
  int wHour; // [rsp+40h] [rbp-C0h]
  int wMinute; // [rsp+48h] [rbp-B8h]
  int wSecond; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  const char *v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v24; // [rsp+80h] [rbp-80h] BYREF
  const char *v25; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, 0x208u);
  SystemTime = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    GetSystemDirectoryW(Buffer, 0x104u);
    **((_DWORD **)this + 4) = *((_DWORD *)this + 10);
    *(_DWORD *)(*((_QWORD *)this + 4) + 44LL) = 0x20000;
    *(_DWORD *)(*((_QWORD *)this + 4) + 40LL) = 2;
    if ( *((_DWORD *)this + 2) )
      *(_OWORD *)(*((_QWORD *)this + 4) + 24LL) = *(_OWORD *)*((_QWORD *)this + 2);
    *(_DWORD *)(*((_QWORD *)this + 4) + 72LL) = 0xFFFF;
    *(_DWORD *)(*((_QWORD *)this + 4) + 116LL) = 120;
    *(_DWORD *)(*((_QWORD *)this + 4) + 112LL) = *(_DWORD *)(*((_QWORD *)this + 4) + 116LL) + 520;
    v3 = *((_QWORD *)this + 4);
    v4 = (unsigned __int16 *)(v3 + *(unsigned int *)(v3 + 116));
    v5 = (unsigned __int16 *)(v3 + *(unsigned int *)(v3 + 112));
    GetSystemTime(&SystemTime);
    StringCchCopyW(v4, 0x104u, *(const unsigned __int16 **)this);
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    wYear = SystemTime.wYear;
    StringCchPrintfW(
      v5,
      0x104u,
      L"%s\\LogFiles\\WMI\\%s-%04d%02d%02d-%02d%02d%02d.etl",
      Buffer,
      *(_QWORD *)this,
      wYear,
      wMonth,
      wDay,
      wHour,
      wMinute,
      wSecond);
    *(_DWORD *)(*((_QWORD *)this + 4) + 48LL) = 20;
    *(_DWORD *)(*((_QWORD *)this + 4) + 60LL) = *((_DWORD *)this + 13);
    *(_DWORD *)(*((_QWORD *)this + 4) + 52LL) = 10;
    *(_DWORD *)(*((_QWORD *)this + 4) + 68LL) = 60;
    *(_DWORD *)(*((_QWORD *)this + 4) + 64LL) = 2;
    if ( CWPPLoggerConfig::IsTraceToDebugger(this) )
      *(_DWORD *)(*((_QWORD *)this + 4) + 64LL) |= 0x80000u;
    started = StartTraceW((PTRACEHANDLE)this + 3, *(LPCWSTR *)this, *((PEVENT_TRACE_PROPERTIES *)this + 4));
    v9 = started;
    if ( started > 0 )
      v2 = (unsigned __int16)started | 0x80070000;
    else
      v2 = started;
    if ( started == 112 )
    {
      *(_DWORD *)(*((_QWORD *)this + 4) + 60LL) = 1;
      v9 = StartTraceW((PTRACEHANDLE)this + 3, *(LPCWSTR *)this, *((PEVENT_TRACE_PROPERTIES *)this + 4));
      if ( (unsigned int)dword_180084170 > 2 )
      {
        v20 = *((unsigned int *)this + 13);
        v21 = "Specified buffer size is too large, using something smaller. Buffer size set to 1MB (which ends up being 2"
              "01MB according to the API)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned int)byte_180078CBD,
          v7,
          v8,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    if ( v9 && (unsigned int)dword_180084170 > 2 )
    {
      v11 = *((_QWORD *)this + 4);
      v23 = v5;
      v12 = (const char *)*(unsigned int *)(v11 + 60);
      v22 = *((_QWORD *)this + 3);
      v24 = *(_DWORD **)this;
      v25 = "StartTraceW failed with these values";
      v21 = v12;
      LODWORD(v20) = v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v12,
        (unsigned int)word_180078ACA,
        v7,
        v8,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001e8ec  push    rbp
0x18001e8ee  push    rbx
0x18001e8ef  push    rsi
0x18001e8f0  push    rdi
0x18001e8f1  push    r14
0x18001e8f3  push    r15
0x18001e8f5  lea     rbp, [rsp-1C8h]
0x18001e8fd  sub     rsp, 2C8h
0x18001e904  mov     rax, cs:__security_cookie
0x18001e90b  xor     rax, rsp
0x18001e90e  mov     [rbp+1F0h+var_40], rax
0x18001e915  mov     rdi, rcx
0x18001e918  mov     r15d, 208h
0x18001e91e  mov     r8d, r15d; Size
0x18001e921  lea     rcx, [rbp+1F0h+Buffer]; void *
0x18001e925  xor     edx, edx; Val
0x18001e927  xor     ebx, ebx
0x18001e929  call    memset_0
0x18001e92e  lea     r14, [rdi+18h]
0x18001e932  xorps   xmm0, xmm0
0x18001e935  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18001e939  cmp     [r14], rbx
0x18001e93c  jnz     loc_18001EB80
0x18001e942  mov     esi, 104h
0x18001e947  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x18001e94b  mov     edx, esi; uSize
0x18001e94d  call    cs:__imp_GetSystemDirectoryW
0x18001e953  mov     eax, [rdi+28h]
0x18001e956  mov     rcx, [rdi+20h]
0x18001e95a  mov     [rcx], eax
0x18001e95c  mov     rax, [rdi+20h]
0x18001e960  mov     dword ptr [rax+2Ch], 20000h
0x18001e967  mov     rax, [rdi+20h]
0x18001e96b  mov     dword ptr [rax+28h], 2
0x18001e972  cmp     [rdi+8], ebx
0x18001e975  jbe     short loc_18001E987
0x18001e977  mov     rax, [rdi+10h]
0x18001e97b  movups  xmm0, xmmword ptr [rax]
0x18001e97e  mov     rax, [rdi+20h]
0x18001e982  movdqu  xmmword ptr [rax+18h], xmm0
0x18001e987  mov     rax, [rdi+20h]
0x18001e98b  mov     dword ptr [rax+48h], 0FFFFh
0x18001e992  mov     rax, [rdi+20h]
0x18001e996  mov     dword ptr [rax+74h], 78h ; 'x'
0x18001e99d  mov     rcx, [rdi+20h]
0x18001e9a1  mov     eax, [rcx+74h]
0x18001e9a4  add     eax, r15d
0x18001e9a7  mov     [rcx+70h], eax
0x18001e9aa  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18001e9ae  mov     rdx, [rdi+20h]
0x18001e9b2  mov     ebx, [rdx+74h]
0x18001e9b5  mov     r15d, [rdx+70h]
0x18001e9b9  add     rbx, rdx
0x18001e9bc  add     r15, rdx
0x18001e9bf  call    cs:__imp_GetSystemTime
0x18001e9c5  mov     r8, [rdi]; unsigned __int16 *
0x18001e9c8  mov     rdx, rsi; unsigned __int64
0x18001e9cb  mov     rcx, rbx; unsigned __int16 *
0x18001e9ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e9d3  movzx   eax, [rbp+1F0h+SystemTime.wMinute]
0x18001e9d7  mov     rdx, rsi; unsigned __int64
0x18001e9da  movzx   ecx, [rbp+1F0h+SystemTime.wHour]
0x18001e9de  movzx   r8d, [rbp+1F0h+SystemTime.wDay]
0x18001e9e3  movzx   r9d, [rbp+1F0h+SystemTime.wMonth]
0x18001e9e8  movzx   r10d, [rbp+1F0h+SystemTime.wSecond]
0x18001e9ed  movzx   r11d, [rbp+1F0h+SystemTime.wYear]
0x18001e9f2  mov     [rsp+2F0h+var_2A0], r10d
0x18001e9f7  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x18001e9fb  mov     rax, [rdi]
0x18001e9fe  mov     dword ptr [rsp+2F0h+var_2B0], ecx
0x18001ea02  mov     rcx, r15; unsigned __int16 *
0x18001ea05  mov     dword ptr [rsp+2F0h+var_2B8], r8d
0x18001ea0a  lea     r8, aSLogfilesWmiS0; "%s\\LogFiles\\WMI\\%s-%04d%02d%02d-%02d"...
0x18001ea11  mov     dword ptr [rsp+2F0h+var_2C0], r9d
0x18001ea16  lea     r9, [rbp+1F0h+Buffer]
0x18001ea1a  mov     dword ptr [rsp+2F0h+var_2C8], r11d
0x18001ea1f  mov     [rsp+2F0h+var_2D0], rax
0x18001ea24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ea29  mov     rax, [rdi+20h]
0x18001ea2d  mov     dword ptr [rax+30h], 14h
0x18001ea34  mov     rcx, [rdi+20h]
0x18001ea38  mov     eax, [rdi+34h]
0x18001ea3b  mov     [rcx+3Ch], eax
0x18001ea3e  mov     rcx, rdi; this
0x18001ea41  mov     rax, [rdi+20h]
0x18001ea45  mov     dword ptr [rax+34h], 0Ah
0x18001ea4c  mov     rax, [rdi+20h]
0x18001ea50  mov     dword ptr [rax+44h], 3Ch ; '<'
0x18001ea57  mov     rax, [rdi+20h]
0x18001ea5b  mov     dword ptr [rax+40h], 2
0x18001ea62  call    ?IsTraceToDebugger@CWPPLoggerConfig@@QEBAEXZ; CWPPLoggerConfig::IsTraceToDebugger(void)
0x18001ea67  test    al, al
0x18001ea69  jz      short loc_18001EA74
0x18001ea6b  mov     rax, [rdi+20h]
0x18001ea6f  bts     dword ptr [rax+40h], 13h
0x18001ea74  mov     r8, [rdi+20h]; Properties
0x18001ea78  mov     rcx, r14; TraceHandle
0x18001ea7b  mov     rdx, [rdi]; InstanceName
0x18001ea7e  call    cs:__imp_StartTraceW
0x18001ea84  mov     esi, eax
0x18001ea86  test    eax, eax
0x18001ea88  jg      short loc_18001EA8E
0x18001ea8a  mov     ebx, eax
0x18001ea8c  jmp     short loc_18001EA97
0x18001ea8e  movzx   ebx, ax
0x18001ea91  or      ebx, 80070000h
0x18001ea97  cmp     eax, 70h ; 'p'
0x18001ea9a  jnz     short loc_18001EAF8
0x18001ea9c  mov     rax, [rdi+20h]
0x18001eaa0  mov     rcx, r14; TraceHandle
0x18001eaa3  mov     dword ptr [rax+3Ch], 1
0x18001eaaa  mov     r8, [rdi+20h]; Properties
0x18001eaae  mov     rdx, [rdi]; InstanceName
0x18001eab1  call    cs:__imp_StartTraceW
0x18001eab7  mov     esi, eax
0x18001eab9  mov     eax, cs:dword_180084170
0x18001eabf  cmp     eax, 2
0x18001eac2  jbe     short loc_18001EAF8
0x18001eac4  mov     eax, [rdi+34h]
0x18001eac7  lea     rdx, byte_180078CBD
0x18001eace  mov     [rsp+2F0h+var_290], rax
0x18001ead3  lea     rax, aSpecifiedBuffe; "Specified buffer size is too large, usi"...
0x18001eada  mov     [rsp+2F0h+var_288], rax
0x18001eadf  lea     rax, [rsp+2F0h+var_290]
0x18001eae4  mov     [rsp+2F0h+var_2C8], rax
0x18001eae9  lea     rax, [rsp+2F0h+var_288]
0x18001eaee  mov     [rsp+2F0h+var_2D0], rax
0x18001eaf3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001eaf8  test    esi, esi
0x18001eafa  jz      loc_18001EB80
0x18001eb00  mov     eax, cs:dword_180084170
0x18001eb06  cmp     eax, 2
0x18001eb09  jbe     short loc_18001EB80
0x18001eb0b  mov     rax, [rdi+20h]
0x18001eb0f  lea     rdx, word_180078ACA
0x18001eb16  mov     [rsp+2F0h+var_278], r15
0x18001eb1b  mov     ecx, [rax+3Ch]
0x18001eb1e  mov     rax, [r14]
0x18001eb21  mov     [rsp+2F0h+var_280], rax
0x18001eb26  mov     rax, [rdi]
0x18001eb29  mov     [rbp+1F0h+var_270], rax
0x18001eb2d  lea     rax, aStarttracewFai; "StartTraceW failed with these values"
0x18001eb34  mov     [rbp+1F0h+var_268], rax
0x18001eb38  lea     rax, [rsp+2F0h+var_288]
0x18001eb3d  mov     [rsp+2F0h+var_2A8], rax
0x18001eb42  lea     rax, [rsp+2F0h+var_280]
0x18001eb47  mov     [rsp+2F0h+var_2B0], rax
0x18001eb4c  lea     rax, [rsp+2F0h+var_278]
0x18001eb51  mov     [rsp+2F0h+var_2B8], rax
0x18001eb56  lea     rax, [rsp+2F0h+var_290]
0x18001eb5b  mov     [rsp+2F0h+var_2C0], rax
0x18001eb60  lea     rax, [rbp+1F0h+var_270]
0x18001eb64  mov     [rsp+2F0h+var_2C8], rax
0x18001eb69  lea     rax, [rbp+1F0h+var_268]
0x18001eb6d  mov     [rsp+2F0h+var_2D0], rax
0x18001eb72  mov     [rsp+2F0h+var_288], rcx
0x18001eb77  mov     dword ptr [rsp+2F0h+var_290], ebx
0x18001eb7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18001eb80  mov     eax, ebx
0x18001eb82  mov     rcx, [rbp+1F0h+var_40]
0x18001eb89  xor     rcx, rsp; StackCookie
0x18001eb8c  call    __security_check_cookie
0x18001eb91  add     rsp, 2C8h
0x18001eb98  pop     r15
0x18001eb9a  pop     r14
0x18001eb9c  pop     rdi
0x18001eb9d  pop     rsi
0x18001eb9e  pop     rbx
0x18001eb9f  pop     rbp
0x18001eba0  retn
```
