# LogAdapter::Logger::LogPartial<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)

- ea: `0x1800118a4`
- end: `0x1800119e2`
- name: `??$LogPartial@PEB_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBQEB_W@Z`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, struct Windows::Rtl::IRtlFormattedOutputStream *, __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011e10`
- `0x1800130b8`
- `0x180013b2c`
- `0x180014054`
- `0x180014470`
- `0x1800147b0`

## callees

- `0x180007568`
- `0x1800118a4`
- `0x18001696c`
- `0x18001a5e4`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180011928`
- `ntdll!RtlLeaveCriticalSection` at `0x18001195b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800119ba`
- `ntdll!RtlLeaveCriticalSection` at `0x180011928`
- `ntdll!RtlLeaveCriticalSection` at `0x18001195b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800119ba`
- `ntdll!RtlRaiseStatus` at `0x180011938`
- `ntdll!RtlRaiseStatus` at `0x180011967`
- `ntdll!RtlRaiseStatus` at `0x1800119c6`
- `ntdll!RtlRaiseStatus` at `0x180011938`
- `ntdll!RtlRaiseStatus` at `0x180011967`
- `ntdll!RtlRaiseStatus` at `0x1800119c6`
- `ntdll!RtlEnterCriticalSection` at `0x1800118cb`
- `ntdll!RtlEnterCriticalSection` at `0x1800118cb`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogPartial<wchar_t const *>(
        __int64 a1,
        __int64 a2,
        struct Windows::Rtl::IRtlFormattedOutputStream *a3,
        __int64 a4)
{
  struct LogAdapter::Logger *v4; // r14
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  int v8; // eax
  bool v9; // di
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  Windows::WCP::Rtl *v15; // rcx
  int v16; // eax
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v18; // [rsp+20h] [rbp-48h] BYREF
  const char *v19; // [rsp+28h] [rbp-40h]
  __int64 v20; // [rsp+30h] [rbp-38h]
  const char *v21; // [rsp+38h] [rbp-30h]

  v4 = LogAdapter::g_Logger;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)LogAdapter::g_Logger + 4160);
  v8 = RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogAdapter::g_Logger + 104);
  v9 = v8 >= 0;
  if ( v8 >= 0 )
  {
    v10 = (**(__int64 (__fastcall ***)(struct LogAdapter::Logger *))v4)(v4);
    if ( v10 >= 0 )
    {
      v15 = (Windows::WCP::Rtl *)*((_QWORD *)v4 + 1);
      v19 = (const char *)`Windows::Tracing::RtlFormatIntoStream<unsigned short,wchar_t const *>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
      v20 = a4;
      Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(v15, a3, (const char *const)1, (unsigned __int64)&v18, 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 496LL))(*((_QWORD *)v4 + 1));
      if ( v9 )
      {
        v16 = RtlLeaveCriticalSection(v7);
        if ( v16 < 0 )
          RtlRaiseStatus(v16);
      }
      return 0;
    }
    else if ( v9 )
    {
      v14 = RtlLeaveCriticalSection(v7);
      if ( v14 < 0 )
        RtlRaiseStatus(v14);
    }
  }
  else
  {
    v20 = 195;
    v18 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)"OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v19 = "LogAdapter::Logger::LogNumObjects";
    v21 = "QueueLock.Acquire()";
    v10 = ConvertNtStatusToHResult(v8);
    RtlReportErrorOrigination(v12, v11, (unsigned int)v10);
    if ( v9 )
    {
      v13 = RtlLeaveCriticalSection(v7);
      if ( v13 < 0 )
        RtlRaiseStatus(v13);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800118a4  mov     [rsp+arg_0], rbx
0x1800118a9  push    rbp
0x1800118aa  push    rsi
0x1800118ab  push    rdi
0x1800118ac  push    r14
0x1800118ae  push    r15
0x1800118b0  sub     rsp, 40h
0x1800118b4  mov     r14, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800118bb  mov     r15, r9
0x1800118be  mov     rbp, r8
0x1800118c1  lea     rsi, [r14+1040h]
0x1800118c8  mov     rcx, rsi; CriticalSection
0x1800118cb  call    cs:__imp_RtlEnterCriticalSection
0x1800118d1  mov     edi, eax
0x1800118d3  shr     edi, 1Fh
0x1800118d6  xor     dil, 1
0x1800118da  test    eax, eax
0x1800118dc  jns     short loc_18001193F
0x1800118de  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x1800118e5  mov     [rsp+68h+var_38], 0C3h
0x1800118ee  mov     [rsp+68h+var_48], rcx
0x1800118f3  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x1800118fa  mov     [rsp+68h+var_40], rcx
0x1800118ff  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x180011906  mov     [rsp+68h+var_30], rcx
0x18001190b  mov     ecx, eax; Status
0x18001190d  call    ConvertNtStatusToHResult
0x180011912  mov     r8d, eax
0x180011915  mov     ebx, eax
0x180011917  call    RtlReportErrorOrigination
0x18001191c  test    dil, dil
0x18001191f  jz      loc_1800119CF
0x180011925  mov     rcx, rsi; CriticalSection
0x180011928  call    cs:__imp_RtlLeaveCriticalSection
0x18001192e  test    eax, eax
0x180011930  jns     loc_1800119CF
0x180011936  mov     ecx, eax; Status
0x180011938  call    cs:__imp_RtlRaiseStatus
0x18001193e  int     3; Trap to Debugger
0x18001193f  mov     rax, [r14]
0x180011942  mov     rcx, r14
0x180011945  mov     rax, [rax]
0x180011948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194d  mov     ebx, eax
0x18001194f  test    eax, eax
0x180011951  jns     short loc_18001196E
0x180011953  test    dil, dil
0x180011956  jz      short loc_1800119CF
0x180011958  mov     rcx, rsi; CriticalSection
0x18001195b  call    cs:__imp_RtlLeaveCriticalSection
0x180011961  test    eax, eax
0x180011963  jns     short loc_1800119CF
0x180011965  mov     ecx, eax; Status
0x180011967  call    cs:__imp_RtlRaiseStatus
0x18001196d  int     3; Trap to Debugger
0x18001196e  mov     rcx, [r14+8]; this
0x180011972  lea     rax, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlFormatIntoStream@GPEB_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEBGAEBQEB_W@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<ushort,wchar_t const *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,ushort const &,wchar_t const * const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180011979  lea     r9, [rsp+68h+var_48]; unsigned __int64
0x18001197e  mov     [rsp+68h+var_40], rax
0x180011983  mov     r8d, 1; char *
0x180011989  mov     [rsp+68h+var_48], 0; struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *
0x180011992  mov     rdx, rbp; struct Windows::Rtl::IRtlFormattedOutputStream *
0x180011995  mov     [rsp+68h+var_38], r15
0x18001199a  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x18001199f  mov     rcx, [r14+8]
0x1800119a3  mov     rax, [rcx]
0x1800119a6  mov     rax, [rax+1F0h]
0x1800119ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b2  test    dil, dil
0x1800119b5  jz      short loc_1800119CD
0x1800119b7  mov     rcx, rsi; CriticalSection
0x1800119ba  call    cs:__imp_RtlLeaveCriticalSection
0x1800119c0  test    eax, eax
0x1800119c2  jns     short loc_1800119CD
0x1800119c4  mov     ecx, eax; Status
0x1800119c6  call    cs:__imp_RtlRaiseStatus
0x1800119cc  int     3; Trap to Debugger
0x1800119cd  xor     ebx, ebx
0x1800119cf  mov     eax, ebx
0x1800119d1  mov     rbx, [rsp+68h+arg_0]
0x1800119d6  add     rsp, 40h
0x1800119da  pop     r15
0x1800119dc  pop     r14
0x1800119de  pop     rdi
0x1800119df  pop     rsi
0x1800119e0  pop     rbp
0x1800119e1  retn
```
