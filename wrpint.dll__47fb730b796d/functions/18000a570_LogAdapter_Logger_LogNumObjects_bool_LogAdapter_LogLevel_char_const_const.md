# LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)

- ea: `0x18000a570`
- end: `0x18000a76d`
- name: `??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z`
- size: `509`
- prototype: `__int64 __fastcall(__int64, char, int, struct Windows::Rtl::IRtlFormattedOutputStream *)`
- caller_count: `22`
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
- `0x180011bc0`
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
- `0x18000a570`
- `0x18001696c`
- `0x18001a5e4`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000a5f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a62b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a6fb`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a73f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a5f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a62b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a6fb`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a73f`
- `ntdll!RtlRaiseStatus` at `0x18000a601`
- `ntdll!RtlRaiseStatus` at `0x18000a637`
- `ntdll!RtlRaiseStatus` at `0x18000a70b`
- `ntdll!RtlRaiseStatus` at `0x18000a74b`
- `ntdll!RtlRaiseStatus` at `0x18000a601`
- `ntdll!RtlRaiseStatus` at `0x18000a637`
- `ntdll!RtlRaiseStatus` at `0x18000a70b`
- `ntdll!RtlRaiseStatus` at `0x18000a74b`
- `ntdll!RtlEnterCriticalSection` at `0x18000a59c`
- `ntdll!RtlEnterCriticalSection` at `0x18000a59c`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<>(
        __int64 a1,
        char a2,
        int a3,
        struct Windows::Rtl::IRtlFormattedOutputStream *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  int v9; // eax
  bool v10; // si
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  const struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v20; // [rsp+20h] [rbp-48h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 4160);
  v9 = RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 4160));
  v10 = v9 >= 0;
  if ( v9 < 0 )
  {
    v11 = ConvertNtStatusToHResult(v9);
    RtlReportErrorOrigination(v13, v12, v11);
    if ( v10 )
    {
      v14 = RtlLeaveCriticalSection(v4);
      if ( v14 < 0 )
        RtlRaiseStatus(v14);
    }
    return v11;
  }
  v11 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( v10 )
    {
      v16 = RtlLeaveCriticalSection(v4);
      if ( v16 < 0 )
        RtlRaiseStatus(v16);
    }
    return v11;
  }
  if ( a2 )
  {
    *(_DWORD *)(a1 + 4152) = a3;
    if ( *(_QWORD *)(a1 + 32) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 224LL))(*(_QWORD *)(a1 + 16), a1 + 40);
      *(_BYTE *)(a1 + 40) = 0;
      *(_QWORD *)(a1 + 32) = 0;
    }
    Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(*(Windows::WCP::Rtl **)(a1 + 16), a4, 0, 0, v20);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
    v11 = *(_DWORD *)(a1 + 4156);
    if ( (v11 & 0x80000000) != 0 )
    {
      RtlReportErrorOrigination("LogAdapter::Logger::LogNumObjects", v17, v11);
      if ( v10 )
      {
        v18 = RtlLeaveCriticalSection(v4);
        if ( v18 < 0 )
          RtlRaiseStatus(v18);
      }
      return v11;
    }
  }
  else
  {
    Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(*(Windows::WCP::Rtl **)(a1 + 8), a4, 0, 0, v20);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
  }
  if ( v10 )
  {
    v19 = RtlLeaveCriticalSection(v4);
    if ( v19 < 0 )
      RtlRaiseStatus(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a570  mov     [rsp+arg_8], rbx
0x18000a575  mov     [rsp+arg_10], rbp
0x18000a57a  push    rsi
0x18000a57b  push    rdi
0x18000a57c  push    r12
0x18000a57e  push    r14
0x18000a580  push    r15
0x18000a582  sub     rsp, 40h
0x18000a586  lea     rbp, [rcx+1040h]
0x18000a58d  mov     rdi, rcx
0x18000a590  mov     rcx, rbp; CriticalSection
0x18000a593  mov     r12, r9
0x18000a596  mov     r15d, r8d
0x18000a599  mov     r14b, dl
0x18000a59c  call    cs:__imp_RtlEnterCriticalSection
0x18000a5a2  mov     esi, eax
0x18000a5a4  shr     esi, 1Fh
0x18000a5a7  xor     sil, 1
0x18000a5ab  test    eax, eax
0x18000a5ad  jns     short loc_18000A60F
0x18000a5af  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x18000a5b6  mov     [rsp+68h+var_38], 0C3h
0x18000a5bf  mov     [rsp+68h+var_48], rcx
0x18000a5c4  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x18000a5cb  mov     [rsp+68h+var_40], rcx
0x18000a5d0  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x18000a5d7  mov     [rsp+68h+var_30], rcx
0x18000a5dc  mov     ecx, eax; Status
0x18000a5de  call    ConvertNtStatusToHResult
0x18000a5e3  mov     r8d, eax
0x18000a5e6  mov     ebx, eax
0x18000a5e8  call    RtlReportErrorOrigination
0x18000a5ed  test    sil, sil
0x18000a5f0  jz      short loc_18000A608
0x18000a5f2  mov     rcx, rbp; CriticalSection
0x18000a5f5  call    cs:__imp_RtlLeaveCriticalSection
0x18000a5fb  test    eax, eax
0x18000a5fd  jns     short loc_18000A608
0x18000a5ff  mov     ecx, eax; Status
0x18000a601  call    cs:__imp_RtlRaiseStatus
0x18000a607  int     3; Trap to Debugger
0x18000a608  mov     eax, ebx
0x18000a60a  jmp     loc_18000A754
0x18000a60f  mov     rax, [rdi]
0x18000a612  mov     rcx, rdi
0x18000a615  mov     rax, [rax]
0x18000a618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a61d  mov     ebx, eax
0x18000a61f  test    eax, eax
0x18000a621  jns     short loc_18000A63E
0x18000a623  test    sil, sil
0x18000a626  jz      short loc_18000A608
0x18000a628  mov     rcx, rbp; CriticalSection
0x18000a62b  call    cs:__imp_RtlLeaveCriticalSection
0x18000a631  test    eax, eax
0x18000a633  jns     short loc_18000A608
0x18000a635  mov     ecx, eax; Status
0x18000a637  call    cs:__imp_RtlRaiseStatus
0x18000a63d  int     3; Trap to Debugger
0x18000a63e  test    r14b, r14b
0x18000a641  jz      loc_18000A712
0x18000a647  mov     [rdi+1038h], r15d
0x18000a64e  cmp     qword ptr [rdi+20h], 0
0x18000a653  jbe     short loc_18000A68B
0x18000a655  mov     rcx, [rdi+8]
0x18000a659  mov     rax, [rcx]
0x18000a65c  mov     rax, [rax+1F0h]
0x18000a663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a668  mov     rcx, [rdi+10h]
0x18000a66c  lea     rdx, [rdi+28h]
0x18000a670  mov     rax, [rcx]
0x18000a673  mov     rax, [rax+0E0h]
0x18000a67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a67f  mov     byte ptr [rdi+28h], 0
0x18000a683  mov     qword ptr [rdi+20h], 0
0x18000a68b  mov     rcx, [rdi+10h]; this
0x18000a68f  xor     r9d, r9d; unsigned __int64
0x18000a692  xor     r8d, r8d; char *
0x18000a695  mov     rdx, r12; struct Windows::Rtl::IRtlFormattedOutputStream *
0x18000a698  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x18000a69d  mov     rcx, [rdi+10h]
0x18000a6a1  mov     rax, [rcx]
0x18000a6a4  mov     rax, [rax+1F0h]
0x18000a6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b0  mov     ebx, [rdi+103Ch]
0x18000a6b6  test    ebx, ebx
0x18000a6b8  jns     short loc_18000A737
0x18000a6ba  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x18000a6c1  mov     [rsp+68h+var_38], 0D7h
0x18000a6ca  mov     [rsp+68h+var_48], rcx
0x18000a6cf  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x18000a6d6  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x18000a6dd  mov     [rsp+68h+var_30], rax
0x18000a6e2  mov     r8d, ebx
0x18000a6e5  mov     [rsp+68h+var_40], rcx
0x18000a6ea  call    RtlReportErrorOrigination
0x18000a6ef  test    sil, sil
0x18000a6f2  jz      loc_18000A608
0x18000a6f8  mov     rcx, rbp; CriticalSection
0x18000a6fb  call    cs:__imp_RtlLeaveCriticalSection
0x18000a701  test    eax, eax
0x18000a703  jns     loc_18000A608
0x18000a709  mov     ecx, eax; Status
0x18000a70b  call    cs:__imp_RtlRaiseStatus
0x18000a711  int     3; Trap to Debugger
0x18000a712  mov     rcx, [rdi+8]; this
0x18000a716  xor     r9d, r9d; unsigned __int64
0x18000a719  xor     r8d, r8d; char *
0x18000a71c  mov     rdx, r12; struct Windows::Rtl::IRtlFormattedOutputStream *
0x18000a71f  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x18000a724  mov     rcx, [rdi+8]
0x18000a728  mov     rax, [rcx]
0x18000a72b  mov     rax, [rax+1F0h]
0x18000a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a737  test    sil, sil
0x18000a73a  jz      short loc_18000A752
0x18000a73c  mov     rcx, rbp; CriticalSection
0x18000a73f  call    cs:__imp_RtlLeaveCriticalSection
0x18000a745  test    eax, eax
0x18000a747  jns     short loc_18000A752
0x18000a749  mov     ecx, eax; Status
0x18000a74b  call    cs:__imp_RtlRaiseStatus
0x18000a751  int     3; Trap to Debugger
0x18000a752  xor     eax, eax
0x18000a754  lea     r11, [rsp+68h+var_28]
0x18000a759  mov     rbx, [r11+38h]
0x18000a75d  mov     rbp, [r11+40h]
0x18000a761  mov     rsp, r11
0x18000a764  pop     r15
0x18000a766  pop     r14
0x18000a768  pop     r12
0x18000a76a  pop     rdi
0x18000a76b  pop     rsi
0x18000a76c  retn
```
