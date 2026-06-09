# LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)

- ea: `0x18000a384`
- end: `0x18000a568`
- name: `??$Log@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(__int64, int, struct Windows::Rtl::IRtlFormattedOutputStream *, __int64)`
- caller_count: `21`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001029c`
- `0x180010448`
- `0x180010750`
- `0x1800109a0`
- `0x180010af0`
- `0x180010de4`
- `0x180010fe0`
- `0x180011248`
- `0x180011364`
- `0x180011654`
- `0x180011b54`
- `0x180011e10`
- `0x180012e78`
- `0x1800130b8`
- `0x1800138a0`
- `0x180013b2c`
- `0x180014054`
- `0x180014470`
- `0x1800147b0`
- `0x180014ce0`
- `0x180014f38`

## callees

- `0x180007568`
- `0x18000a384`
- `0x18001696c`
- `0x18001a5e4`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000a40e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a445`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a51d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a538`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a40e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a445`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a51d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a538`
- `ntdll!RtlRaiseStatus` at `0x18000a41e`
- `ntdll!RtlRaiseStatus` at `0x18000a455`
- `ntdll!RtlRaiseStatus` at `0x18000a529`
- `ntdll!RtlRaiseStatus` at `0x18000a544`
- `ntdll!RtlRaiseStatus` at `0x18000a41e`
- `ntdll!RtlRaiseStatus` at `0x18000a455`
- `ntdll!RtlRaiseStatus` at `0x18000a529`
- `ntdll!RtlRaiseStatus` at `0x18000a544`
- `ntdll!RtlEnterCriticalSection` at `0x18000a3b5`
- `ntdll!RtlEnterCriticalSection` at `0x18000a3b5`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        __int64 a1,
        int a2,
        struct Windows::Rtl::IRtlFormattedOutputStream *a3,
        __int64 a4)
{
  struct LogAdapter::Logger *v4; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // r14
  int v9; // eax
  bool v10; // si
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  Windows::WCP::Rtl *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  unsigned __int64 v21; // [rsp+20h] [rbp-20h] BYREF
  const char *v22; // [rsp+28h] [rbp-18h]
  __int64 v23; // [rsp+30h] [rbp-10h]
  const char *v24; // [rsp+38h] [rbp-8h]

  v4 = LogAdapter::g_Logger;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)LogAdapter::g_Logger + 4160);
  v9 = RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogAdapter::g_Logger + 104);
  v10 = v9 >= 0;
  if ( v9 >= 0 )
  {
    LODWORD(v11) = (**(__int64 (__fastcall ***)(struct LogAdapter::Logger *))v4)(v4);
    if ( (int)v11 >= 0 )
    {
      *((_DWORD *)v4 + 1038) = a2;
      if ( *((_QWORD *)v4 + 4) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 496LL))(*((_QWORD *)v4 + 1));
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 2) + 224LL))(*((_QWORD *)v4 + 2), (__int64)v4 + 40);
        *((_BYTE *)v4 + 40) = 0;
        *((_QWORD *)v4 + 4) = 0;
      }
      v16 = (Windows::WCP::Rtl *)*((_QWORD *)v4 + 2);
      v22 = (const char *)`Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
      v23 = a4;
      Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(v16, a3, (const char *const)1, (unsigned __int64)&v21, 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 2) + 496LL))(*((_QWORD *)v4 + 2));
      LODWORD(v11) = *((_DWORD *)v4 + 1039);
      if ( (int)v11 >= 0 )
      {
        if ( v10 )
        {
          v19 = RtlLeaveCriticalSection(v8);
          if ( v19 < 0 )
            RtlRaiseStatus(v19);
        }
        LODWORD(v11) = 0;
      }
      else
      {
        v23 = 215;
        v21 = (unsigned __int64)"OneCore\\Private\\Base\\inc\\LogAdapter.h";
        v24 = "m_FlushSink.Hr()";
        v22 = "LogAdapter::Logger::LogNumObjects";
        RtlReportErrorOrigination("LogAdapter::Logger::LogNumObjects", v17, (unsigned int)v11);
        if ( v10 )
        {
          v18 = RtlLeaveCriticalSection(v8);
          if ( v18 < 0 )
            RtlRaiseStatus(v18);
        }
      }
    }
    else if ( v10 )
    {
      v15 = RtlLeaveCriticalSection(v8);
      if ( v15 < 0 )
        RtlRaiseStatus(v15);
    }
  }
  else
  {
    v23 = 195;
    v21 = (unsigned __int64)"OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v22 = "LogAdapter::Logger::LogNumObjects";
    v24 = "QueueLock.Acquire()";
    v11 = (unsigned int)ConvertNtStatusToHResult(v9);
    RtlReportErrorOrigination(v13, v12, v11);
    if ( v10 )
    {
      v14 = RtlLeaveCriticalSection(v8);
      if ( v14 < 0 )
        RtlRaiseStatus(v14);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a384  mov     [rsp-38h+arg_0], rbx
0x18000a389  push    rbp
0x18000a38a  push    rsi
0x18000a38b  push    rdi
0x18000a38c  push    r12
0x18000a38e  push    r13
0x18000a390  push    r14
0x18000a392  push    r15
0x18000a394  mov     rbp, rsp
0x18000a397  sub     rsp, 40h
0x18000a39b  mov     rdi, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000a3a2  mov     r13, r9
0x18000a3a5  mov     r12, r8
0x18000a3a8  mov     r15d, edx
0x18000a3ab  lea     r14, [rdi+1040h]
0x18000a3b2  mov     rcx, r14; CriticalSection
0x18000a3b5  call    cs:__imp_RtlEnterCriticalSection
0x18000a3bb  mov     esi, eax
0x18000a3bd  shr     esi, 1Fh
0x18000a3c0  xor     sil, 1
0x18000a3c4  test    eax, eax
0x18000a3c6  jns     short loc_18000A425
0x18000a3c8  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x18000a3cf  mov     [rbp+var_10], 0C3h
0x18000a3d7  mov     [rbp+var_20], rcx
0x18000a3db  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x18000a3e2  mov     [rbp+var_18], rcx
0x18000a3e6  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x18000a3ed  mov     [rbp+var_8], rcx
0x18000a3f1  mov     ecx, eax; Status
0x18000a3f3  call    ConvertNtStatusToHResult
0x18000a3f8  mov     r8d, eax
0x18000a3fb  mov     ebx, eax
0x18000a3fd  call    RtlReportErrorOrigination
0x18000a402  test    sil, sil
0x18000a405  jz      loc_18000A54E
0x18000a40b  mov     rcx, r14; CriticalSection
0x18000a40e  call    cs:__imp_RtlLeaveCriticalSection
0x18000a414  test    eax, eax
0x18000a416  jns     loc_18000A54E
0x18000a41c  mov     ecx, eax; Status
0x18000a41e  call    cs:__imp_RtlRaiseStatus
0x18000a424  int     3; Trap to Debugger
0x18000a425  mov     rax, [rdi]
0x18000a428  mov     rcx, rdi
0x18000a42b  mov     rax, [rax]
0x18000a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a433  mov     ebx, eax
0x18000a435  test    eax, eax
0x18000a437  jns     short loc_18000A45C
0x18000a439  test    sil, sil
0x18000a43c  jz      loc_18000A54E
0x18000a442  mov     rcx, r14; CriticalSection
0x18000a445  call    cs:__imp_RtlLeaveCriticalSection
0x18000a44b  test    eax, eax
0x18000a44d  jns     loc_18000A54E
0x18000a453  mov     ecx, eax; Status
0x18000a455  call    cs:__imp_RtlRaiseStatus
0x18000a45b  int     3; Trap to Debugger
0x18000a45c  mov     [rdi+1038h], r15d
0x18000a463  xor     r15d, r15d
0x18000a466  cmp     [rdi+20h], r15
0x18000a46a  jbe     short loc_18000A49E
0x18000a46c  mov     rcx, [rdi+8]
0x18000a470  mov     rax, [rcx]
0x18000a473  mov     rax, [rax+1F0h]
0x18000a47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a47f  mov     rcx, [rdi+10h]
0x18000a483  lea     rdx, [rdi+28h]
0x18000a487  mov     rax, [rcx]
0x18000a48a  mov     rax, [rax+0E0h]
0x18000a491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a496  mov     [rdi+28h], r15b
0x18000a49a  mov     [rdi+20h], r15
0x18000a49e  mov     rcx, [rdi+10h]; this
0x18000a4a2  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEBU?$FormatHResultWrapper@J@5WCP@3@@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18000a4a9  lea     r9, [rbp+var_20]; unsigned __int64
0x18000a4ad  mov     [rbp+var_18], rax
0x18000a4b1  mov     r8d, 1; char *
0x18000a4b7  mov     [rbp+var_20], r15
0x18000a4bb  mov     rdx, r12; struct Windows::Rtl::IRtlFormattedOutputStream *
0x18000a4be  mov     [rbp+var_10], r13
0x18000a4c2  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x18000a4c7  mov     rcx, [rdi+10h]
0x18000a4cb  mov     rax, [rcx]
0x18000a4ce  mov     rax, [rax+1F0h]
0x18000a4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4da  mov     ebx, [rdi+103Ch]
0x18000a4e0  test    ebx, ebx
0x18000a4e2  jns     short loc_18000A530
0x18000a4e4  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x18000a4eb  mov     [rbp+var_10], 0D7h
0x18000a4f3  mov     [rbp+var_20], rcx
0x18000a4f7  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x18000a4fe  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x18000a505  mov     [rbp+var_8], rax
0x18000a509  mov     r8d, ebx
0x18000a50c  mov     [rbp+var_18], rcx
0x18000a510  call    RtlReportErrorOrigination
0x18000a515  test    sil, sil
0x18000a518  jz      short loc_18000A54E
0x18000a51a  mov     rcx, r14; CriticalSection
0x18000a51d  call    cs:__imp_RtlLeaveCriticalSection
0x18000a523  test    eax, eax
0x18000a525  jns     short loc_18000A54E
0x18000a527  mov     ecx, eax; Status
0x18000a529  call    cs:__imp_RtlRaiseStatus
0x18000a52f  int     3; Trap to Debugger
0x18000a530  test    sil, sil
0x18000a533  jz      short loc_18000A54B
0x18000a535  mov     rcx, r14; CriticalSection
0x18000a538  call    cs:__imp_RtlLeaveCriticalSection
0x18000a53e  test    eax, eax
0x18000a540  jns     short loc_18000A54B
0x18000a542  mov     ecx, eax; Status
0x18000a544  call    cs:__imp_RtlRaiseStatus
0x18000a54a  int     3; Trap to Debugger
0x18000a54b  mov     ebx, r15d
0x18000a54e  mov     eax, ebx
0x18000a550  mov     rbx, [rsp+40h+arg_0]
0x18000a558  add     rsp, 40h
0x18000a55c  pop     r15
0x18000a55e  pop     r14
0x18000a560  pop     r13
0x18000a562  pop     r12
0x18000a564  pop     rdi
0x18000a565  pop     rsi
0x18000a566  pop     rbp
0x18000a567  retn
```
