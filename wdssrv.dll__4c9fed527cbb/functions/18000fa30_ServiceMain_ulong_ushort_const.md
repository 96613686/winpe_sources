# ServiceMain(ulong,ushort * * const)

- ea: `0x18000fa30`
- end: `0x18000fb48`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `280`
- prototype: `void __fastcall(__int64, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009da4`
- `0x18000fa30`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000fb30`
- `KERNEL32!SetLastError` at `0x18000fb30`
- `KERNEL32!GetLastError` at `0x18000faa6`
- `KERNEL32!GetLastError` at `0x18000faf5`
- `KERNEL32!GetLastError` at `0x18000faa6`
- `KERNEL32!GetLastError` at `0x18000faf5`
- `WdsServerCommonLib!?WDSCheckForDebugger@@YAXPEBG@Z` at `0x18000fa67`
- `WdsServerCommonLib!?WDSCheckForDebugger@@YAXPEBG@Z` at `0x18000fa67`
- `WdsServerCommonLib!?WDSCheckCommonDebugging@@YAXPEBG@Z` at `0x18000fa7a`
- `WdsServerCommonLib!?WDSCheckCommonDebugging@@YAXPEBG@Z` at `0x18000fa7a`

## string_xrefs

- `0x18000fa52`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x18000fa73`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **const a2)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx

  dword_180028B90 = 1;
  g_ErrLibTraceFunction = ErrLibTrace;
  g_ErrLibTraceFunctionEx = ErrLibTraceEx;
  WDSCheckForDebugger(L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters");
  WDSCheckCommonDebugging(L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters");
  v2 = CWdsService::Initialize((CWdsService *)&qword_180028BD0);
  if ( v2 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\main.cpp",
        165,
        &dword_18001F974,
        v2);
    }
    else
    {
      if ( !g_ErrLibTraceFunction )
        return;
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\main.cpp",
        165,
        &dword_18001F974,
        v2);
    }
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x18000fa30  mov     [rsp+arg_0], rbx
0x18000fa35  push    rdi
0x18000fa36  sub     rsp, 40h
0x18000fa3a  lea     rax, ?ErrLibTrace@@YAXPEBGZZ; ErrLibTrace(ushort const *,...)
0x18000fa41  mov     cs:dword_180028B90, 1
0x18000fa4b  mov     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rax; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000fa52  lea     rcx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000fa59  lea     rax, ?ErrLibTraceEx@@YAXKPEBGZZ; ErrLibTraceEx(ulong,ushort const *,...)
0x18000fa60  mov     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rax; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000fa67  call    cs:__imp_?WDSCheckForDebugger@@YAXPEBG@Z; WDSCheckForDebugger(ushort const *)
0x18000fa6e  nop     dword ptr [rax+rax+00h]
0x18000fa73  lea     rcx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000fa7a  call    cs:__imp_?WDSCheckCommonDebugging@@YAXPEBG@Z; WDSCheckCommonDebugging(ushort const *)
0x18000fa81  nop     dword ptr [rax+rax+00h]
0x18000fa86  lea     rcx, qword_180028BD0; this
0x18000fa8d  call    ?Initialize@CWdsService@@QEAAKXZ; CWdsService::Initialize(void)
0x18000fa92  mov     edi, eax
0x18000fa94  test    eax, eax
0x18000fa96  jz      loc_18000FB3C
0x18000fa9c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000faa4  jz      short loc_18000FAEB
0x18000faa6  call    cs:__imp_GetLastError
0x18000faad  nop     dword ptr [rax+rax+00h]
0x18000fab2  lea     r9, dword_18001F974
0x18000fab9  mov     [rsp+48h+var_20], edi
0x18000fabd  mov     [rsp+48h+var_28], r9
0x18000fac2  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\server\\src\\ma"...
0x18000fac9  mov     ebx, eax
0x18000facb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000fad2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000fad9  mov     r9d, 0A5h
0x18000fadf  mov     ecx, 80000h
0x18000fae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fae9  jmp     short loc_18000FB2E
0x18000faeb  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000faf3  jz      short loc_18000FB3C
0x18000faf5  call    cs:__imp_GetLastError
0x18000fafc  nop     dword ptr [rax+rax+00h]
0x18000fb01  lea     r9, dword_18001F974
0x18000fb08  mov     dword ptr [rsp+48h+var_28], edi
0x18000fb0c  mov     ebx, eax
0x18000fb0e  lea     rdx, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\server\\src\\ma"...
0x18000fb15  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000fb1c  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000fb23  mov     r8d, 0A5h
0x18000fb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb2e  mov     ecx, ebx; dwErrCode
0x18000fb30  call    cs:__imp_SetLastError
0x18000fb37  nop     dword ptr [rax+rax+00h]
0x18000fb3c  mov     rbx, [rsp+48h+arg_0]
0x18000fb41  add     rsp, 40h
0x18000fb45  pop     rdi
0x18000fb46  retn
```
