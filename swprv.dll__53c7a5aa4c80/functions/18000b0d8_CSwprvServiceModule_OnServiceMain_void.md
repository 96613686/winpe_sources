# CSwprvServiceModule::OnServiceMain(void)

- ea: `0x18000b0d8`
- end: `0x18000b26a`
- name: `?OnServiceMain@CSwprvServiceModule@@QEAAXXZ`
- size: `402`
- prototype: `void __fastcall(CSwprvServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c750`

## callees

- `0x18000212c`
- `0x18000aa5c`
- `0x18000af80`
- `0x18000b0d8`
- `0x18000b448`
- `0x18000c770`
- `0x180033a8c`
- `0x180033c78`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b16e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b16e`

## string_xrefs

- `0x18000b0f2`: `CSwprvServiceModule::OnServiceMain`
- `0x18000b1c9`: `RegisterServiceCtrlHandlerEx(%s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSwprvServiceModule::OnServiceMain(CSwprvServiceModule *this)
{
  SERVICE_STATUS_HANDLE v1; // rax
  CSwprvServiceModule *v2; // rcx
  CSwprvServiceModule *v3; // rcx
  CSwprvServiceModule *v4; // rcx
  CSwprvServiceModule *v5; // rcx
  CSwprvServiceModule *v6; // rcx
  CSwprvServiceModule *v7; // rcx
  CSwprvServiceModule *v8; // rcx
  CSwprvServiceModule *v9; // rcx
  unsigned int v10; // [rsp+40h] [rbp-158h] BYREF
  const unsigned __int16 *v11; // [rsp+48h] [rbp-150h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp-148h]
  const unsigned __int16 *v13; // [rsp+58h] [rbp-140h]
  int v14; // [rsp+60h] [rbp-138h]
  int v15; // [rsp+64h] [rbp-134h]
  int v16; // [rsp+68h] [rbp-130h]
  _BYTE v17[120]; // [rsp+70h] [rbp-128h] BYREF
  int v18; // [rsp+E8h] [rbp-B0h]
  _com_error *v19; // [rsp+F0h] [rbp-A8h] BYREF
  const std::exception *v20; // [rsp+F8h] [rbp-A0h] BYREF
  LPVOID v21; // [rsp+100h] [rbp-98h] BYREF
  __int64 v22; // [rsp+108h] [rbp-90h]
  unsigned int v23; // [rsp+124h] [rbp-74h]

  v11 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v12 = L"CSwprvServiceModule::OnServiceMain";
  v13 = L"SPRSWPRC";
  v14 = 299;
  v15 = 2;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v21, (__int64)&v11, 0);
  ServiceStatus.dwCurrentState = 2;
  v1 = RegisterServiceCtrlHandlerExW(L"swprv", (LPHANDLER_FUNCTION_EX)CSwprvServiceModule::_Handler, 0);
  try
  {
    hServiceStatus = v1;
    if ( !v1 )
    {
      v11 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
      v12 = L"CSwprvServiceModule::OnServiceMain";
      v13 = L"SPRSWPRC";
      v14 = 309;
      v15 = 2;
      v16 = 255;
      v18 = 0x1000000;
      memset_0(v17, 0, sizeof(v17));
      CVssFunctionTracer::TranslateWin32Error(&v21, &v11, L"RegisterServiceCtrlHandlerEx(%s)", L"swprv");
    }
    CSwprvServiceModule::SetServiceStatus(v2, 2u, 1u);
    CSwprvServiceModule::OnInitializing(v3);
    CSwprvServiceModule::OnRunning(v4);
    CSwprvServiceModule::SetServiceStatus(v5, 3u, 1u);
    CSwprvServiceModule::OnStopping(v6);
    CSwprvServiceModule::SetServiceStatus(v7, 1u, 1u);
  }
  catch ( long v10 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v21,
      v10,
      L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
      L"SPRSWPRC",
      L"CSwprvServiceModule::OnServiceMain",
      0x14Au,
      v23);
  }
  catch ( _com_error *v19 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v21,
      v19,
      L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
      L"SPRSWPRC",
      L"CSwprvServiceModule::OnServiceMain",
      0x14Au,
      v23);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v21,
      L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
      L"SPRSWPRC",
      L"CSwprvServiceModule::OnServiceMain",
      0x14Au,
      v23);
  }
  catch ( const std::exception *v20 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v21,
      v20,
      L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
      L"SPRSWPRC",
      L"CSwprvServiceModule::OnServiceMain",
      0x14Au,
      v23);
  }
  if ( (int)v22 < 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v22;
    CSwprvServiceModule::OnStopping(v8);
    CSwprvServiceModule::SetServiceStatus(v9, 1u, 0);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v21);
}

```

## disassembly

```asm
0x18000b0d8  push    rbx
0x18000b0da  push    rsi
0x18000b0db  push    r14
0x18000b0dd  push    r15
0x18000b0df  sub     rsp, 178h
0x18000b0e6  lea     rsi, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000b0ed  mov     [rsp+198h+var_150], rsi
0x18000b0f2  lea     r14, aCswprvservicem_8; "CSwprvServiceModule::OnServiceMain"
0x18000b0f9  mov     [rsp+198h+var_148], r14
0x18000b0fe  lea     r15, aSprswprc; "SPRSWPRC"
0x18000b105  mov     [rsp+198h+var_140], r15
0x18000b10a  mov     [rsp+198h+var_138], 12Bh
0x18000b112  mov     [rsp+198h+var_134], 2
0x18000b11a  mov     [rsp+198h+var_130], 0FFh
0x18000b122  mov     [rsp+198h+var_B0], 1000000h
0x18000b12d  xor     edx, edx; Val
0x18000b12f  lea     r8d, [rdx+78h]; Size
0x18000b133  lea     rcx, [rsp+198h+var_128]; void *
0x18000b138  call    memset_0
0x18000b13d  xor     r8d, r8d
0x18000b140  lea     rdx, [rsp+198h+var_150]
0x18000b145  lea     rcx, [rsp+198h+var_98]
0x18000b14d  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000b152  nop
0x18000b153  mov     cs:ServiceStatus.dwCurrentState, 2
0x18000b15d  xor     r8d, r8d; lpContext
0x18000b160  lea     rdx, ?_Handler@CSwprvServiceModule@@KAKKKPEAX0@Z; lpHandlerProc
0x18000b167  lea     rcx, ServiceName; "swprv"
0x18000b16e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000b174  mov     cs:hServiceStatus, rax
0x18000b17b  test    rax, rax
0x18000b17e  jnz     short loc_18000B1E2
0x18000b180  mov     [rsp+198h+var_150], rsi
0x18000b185  mov     [rsp+198h+var_148], r14
0x18000b18a  mov     [rsp+198h+var_140], r15
0x18000b18f  mov     [rsp+198h+var_138], 135h
0x18000b197  mov     [rsp+198h+var_134], 2
0x18000b19f  mov     [rsp+198h+var_130], 0FFh
0x18000b1a7  mov     [rsp+198h+var_B0], 1000000h
0x18000b1b2  xor     edx, edx; Val
0x18000b1b4  lea     r8d, [rax+78h]; Size
0x18000b1b8  lea     rcx, [rsp+198h+var_128]; void *
0x18000b1bd  call    memset_0
0x18000b1c2  lea     r9, ServiceName; "swprv"
0x18000b1c9  lea     r8, aRegisterservic_0; "RegisterServiceCtrlHandlerEx(%s)"
0x18000b1d0  lea     rdx, [rsp+198h+var_150]
0x18000b1d5  lea     rcx, [rsp+198h+var_98]
0x18000b1dd  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18000b1e2  mov     r8b, 1; bool
0x18000b1e5  mov     edx, 2; unsigned int
0x18000b1ea  call    ?SetServiceStatus@CSwprvServiceModule@@IEAAXK_N@Z; CSwprvServiceModule::SetServiceStatus(ulong,bool)
0x18000b1ef  call    ?OnInitializing@CSwprvServiceModule@@IEAAXXZ; CSwprvServiceModule::OnInitializing(void)
0x18000b1f4  call    ?OnRunning@CSwprvServiceModule@@IEAAXXZ; CSwprvServiceModule::OnRunning(void)
0x18000b1f9  mov     r8b, 1; bool
0x18000b1fc  mov     edx, 3; unsigned int
0x18000b201  call    ?SetServiceStatus@CSwprvServiceModule@@IEAAXK_N@Z; CSwprvServiceModule::SetServiceStatus(ulong,bool)
0x18000b206  call    ?OnStopping@CSwprvServiceModule@@IEAAXXZ; CSwprvServiceModule::OnStopping(void)
0x18000b20b  mov     r8b, 1; bool
0x18000b20e  mov     edx, 1; unsigned int
0x18000b213  call    ?SetServiceStatus@CSwprvServiceModule@@IEAAXK_N@Z; CSwprvServiceModule::SetServiceStatus(ulong,bool)
0x18000b218  nop
0x18000b219  jmp     short loc_18000B221
0x18000b21b  jmp     short loc_18000B221
0x18000b21d  jmp     short loc_18000B221
0x18000b21f  jmp     short $+2
0x18000b221  mov     rax, [rsp+198h+var_90]
0x18000b229  test    eax, eax
0x18000b22b  jns     short loc_18000B24F
0x18000b22d  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000b237  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x18000b23d  call    ?OnStopping@CSwprvServiceModule@@IEAAXXZ; CSwprvServiceModule::OnStopping(void)
0x18000b242  xor     r8d, r8d; bool
0x18000b245  lea     edx, [r8+1]; unsigned int
0x18000b249  call    ?SetServiceStatus@CSwprvServiceModule@@IEAAXK_N@Z; CSwprvServiceModule::SetServiceStatus(ulong,bool)
0x18000b24e  nop
0x18000b24f  lea     rcx, [rsp+198h+var_98]; this
0x18000b257  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000b25c  add     rsp, 178h
0x18000b263  pop     r15
0x18000b265  pop     r14
0x18000b267  pop     rsi
0x18000b268  pop     rbx
0x18000b269  retn
```
