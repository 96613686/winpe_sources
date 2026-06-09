# CSwprvServiceModule::SetServiceStatus(ulong,bool)

- ea: `0x18000c770`
- end: `0x18000c997`
- name: `?SetServiceStatus@CSwprvServiceModule@@IEAAXK_N@Z`
- size: `551`
- prototype: `void __fastcall(CSwprvServiceModule *__hidden this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a378`
- `0x18000aa5c`
- `0x18000b0d8`

## callees

- `0x18000212c`
- `0x18000c770`
- `0x180033a8c`
- `0x180033c78`
- `0x180036614`
- `0x1800367b8`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c86d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c86d`

## string_xrefs

- `0x18000c79a`: `CSwprvServiceModule::SetServiceStatus`
- `0x18000c8e5`: `CSwprvServiceModule::SetServiceStatus`
- `0x18000c83f`: `Attempt to change the service status to %lu`
- `0x18000c8bc`: `SetServiceStatus(%ld)`
- `0x18000c94f`: `Error on calling SetServiceStatus. 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSwprvServiceModule::SetServiceStatus(CSwprvServiceModule *this, DWORD a2, unsigned __int8 a3)
{
  unsigned int v4; // r15d
  __int64 v5; // [rsp+28h] [rbp-160h]
  const unsigned __int16 *v6; // [rsp+40h] [rbp-148h] BYREF
  const unsigned __int16 *v7; // [rsp+48h] [rbp-140h]
  const unsigned __int16 *v8; // [rsp+50h] [rbp-138h]
  int v9; // [rsp+58h] [rbp-130h]
  int v10; // [rsp+5Ch] [rbp-12Ch]
  int v11; // [rsp+60h] [rbp-128h]
  _BYTE v12[120]; // [rsp+68h] [rbp-120h] BYREF
  int v13; // [rsp+E0h] [rbp-A8h]
  unsigned int v14; // [rsp+E8h] [rbp-A0h] BYREF
  LPVOID v15; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v16; // [rsp+F8h] [rbp-90h]
  unsigned int v17; // [rsp+114h] [rbp-74h]
  const std::exception *v18; // [rsp+160h] [rbp-28h] BYREF
  _com_error *v19; // [rsp+168h] [rbp-20h] BYREF

  v6 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v7 = L"CSwprvServiceModule::SetServiceStatus";
  v8 = L"SPRSWPRC";
  v9 = 442;
  v10 = 2;
  v11 = 255;
  v13 = 0x1000000;
  memset_0(v12, 0, sizeof(v12));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v15, (__int64)&v6, 0);
  v6 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v7 = L"CSwprvServiceModule::SetServiceStatus";
  v8 = L"SPRSWPRC";
  v9 = 446;
  v10 = 2;
  v11 = 255;
  v13 = 0x1000000;
  memset_0(v12, 0, sizeof(v12));
  CVssFunctionTracer::Trace(&v15, &v6, L"Attempt to change the service status to %lu", a2);
  ServiceStatus.dwCurrentState = a2;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    v6 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
    v7 = L"CSwprvServiceModule::SetServiceStatus";
    v8 = L"SPRSWPRC";
    v9 = 453;
    v10 = 2;
    v11 = 255;
    v13 = 0x1000000;
    memset_0(v12, 0, sizeof(v12));
    try
    {
      CVssFunctionTracer::TranslateWin32Error(&v15, &v6, L"SetServiceStatus(%ld)", a2);
    }
    catch ( long v14 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v15,
        v14,
        L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
        L"SPRSWPRC",
        L"CSwprvServiceModule::SetServiceStatus",
        0x1C7u,
        v17);
    }
    catch ( _com_error *v19 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v15,
        v19,
        L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
        L"SPRSWPRC",
        L"CSwprvServiceModule::SetServiceStatus",
        0x1C7u,
        v17);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v15,
        L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
        L"SPRSWPRC",
        L"CSwprvServiceModule::SetServiceStatus",
        0x1C7u,
        v17);
    }
    catch ( const std::exception *v18 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v15,
        v18,
        L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
        L"SPRSWPRC",
        L"CSwprvServiceModule::SetServiceStatus",
        0x1C7u,
        v17);
    }
  }
  v4 = v16;
  if ( (int)v16 < 0 )
  {
    v6 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
    v7 = L"CSwprvServiceModule::SetServiceStatus";
    v8 = L"SPRSWPRC";
    v9 = 458;
    v10 = 2;
    v11 = 255;
    v13 = 0x1000000;
    memset_0(v12, 0, sizeof(v12));
    LODWORD(v5) = v4;
    CVssFunctionTracer::ThrowIf(&v15, a3, &v6, v4, L"Error on calling SetServiceStatus. 0x%08lx", v5);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v15);
}

```

## disassembly

```asm
0x18000c770  mov     rax, rsp
0x18000c773  mov     [rax+10h], rbx
0x18000c777  mov     [rax+20h], rsi
0x18000c77b  mov     [rax+18h], r8b
0x18000c77f  push    rdi
0x18000c780  push    r14
0x18000c782  push    r15
0x18000c784  sub     rsp, 170h
0x18000c78b  mov     r15d, edx
0x18000c78e  lea     rdi, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000c795  mov     [rsp+188h+var_148], rdi
0x18000c79a  lea     rsi, aCswprvservicem_7; "CSwprvServiceModule::SetServiceStatus"
0x18000c7a1  mov     [rsp+188h+var_140], rsi
0x18000c7a6  lea     r14, aSprswprc; "SPRSWPRC"
0x18000c7ad  mov     [rsp+188h+var_138], r14
0x18000c7b2  mov     [rsp+188h+var_130], 1BAh
0x18000c7ba  mov     [rsp+188h+var_12C], 2
0x18000c7c2  mov     [rsp+188h+var_128], 0FFh
0x18000c7ca  mov     dword ptr [rax-0A8h], 1000000h
0x18000c7d4  xor     edx, edx; Val
0x18000c7d6  lea     r8d, [rdx+78h]; Size
0x18000c7da  lea     rcx, [rsp+188h+var_120]; void *
0x18000c7df  call    memset_0
0x18000c7e4  xor     r8d, r8d
0x18000c7e7  lea     rdx, [rsp+188h+var_148]
0x18000c7ec  lea     rcx, [rsp+188h+var_98]
0x18000c7f4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000c7f9  nop
0x18000c7fa  mov     [rsp+188h+var_148], rdi
0x18000c7ff  mov     [rsp+188h+var_140], rsi
0x18000c804  mov     [rsp+188h+var_138], r14
0x18000c809  mov     [rsp+188h+var_130], 1BEh
0x18000c811  mov     [rsp+188h+var_12C], 2
0x18000c819  mov     [rsp+188h+var_128], 0FFh
0x18000c821  mov     [rsp+188h+var_A8], 1000000h
0x18000c82c  xor     edx, edx; Val
0x18000c82e  lea     r8d, [rdx+78h]; Size
0x18000c832  lea     rcx, [rsp+188h+var_120]; void *
0x18000c837  call    memset_0
0x18000c83c  mov     r9d, r15d
0x18000c83f  lea     r8, aAttemptToChang; "Attempt to change the service status to"...
0x18000c846  lea     rdx, [rsp+188h+var_148]
0x18000c84b  lea     rcx, [rsp+188h+var_98]
0x18000c853  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000c858  mov     cs:ServiceStatus.dwCurrentState, r15d
0x18000c85f  lea     rdx, ServiceStatus; lpServiceStatus
0x18000c866  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000c86d  call    cs:__imp_SetServiceStatus
0x18000c873  test    eax, eax
0x18000c875  jnz     short loc_18000C8D6
0x18000c877  mov     [rsp+188h+var_148], rdi
0x18000c87c  mov     [rsp+188h+var_140], rsi
0x18000c881  mov     [rsp+188h+var_138], r14
0x18000c886  mov     [rsp+188h+var_130], 1C5h
0x18000c88e  mov     [rsp+188h+var_12C], 2
0x18000c896  mov     [rsp+188h+var_128], 0FFh
0x18000c89e  mov     [rsp+188h+var_A8], 1000000h
0x18000c8a9  xor     edx, edx; Val
0x18000c8ab  lea     r8d, [rax+78h]; Size
0x18000c8af  lea     rcx, [rsp+188h+var_120]; void *
0x18000c8b4  call    memset_0
0x18000c8b9  mov     r9d, r15d
0x18000c8bc  lea     r8, aSetservicestat_0; "SetServiceStatus(%ld)"
0x18000c8c3  lea     rdx, [rsp+188h+var_148]
0x18000c8c8  lea     rcx, [rsp+188h+var_98]
0x18000c8d0  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18000c8d6  jmp     short loc_18000C8F3
0x18000c8d8  jmp     short loc_18000C8DE
0x18000c8da  jmp     short loc_18000C8DE
0x18000c8dc  jmp     short $+2
0x18000c8de  lea     r14, aSprswprc; "SPRSWPRC"
0x18000c8e5  lea     rsi, aCswprvservicem_7; "CSwprvServiceModule::SetServiceStatus"
0x18000c8ec  lea     rdi, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000c8f3  mov     r15, [rsp+188h+var_90]
0x18000c8fb  test    r15d, r15d
0x18000c8fe  jns     short loc_18000C971
0x18000c900  mov     [rsp+188h+var_148], rdi
0x18000c905  mov     [rsp+188h+var_140], rsi
0x18000c90a  mov     [rsp+188h+var_138], r14
0x18000c90f  mov     [rsp+188h+var_130], 1CAh
0x18000c917  mov     [rsp+188h+var_12C], 2
0x18000c91f  mov     [rsp+188h+var_128], 0FFh
0x18000c927  mov     [rsp+188h+var_A8], 1000000h
0x18000c932  xor     edx, edx; Val
0x18000c934  lea     r8d, [rdx+78h]; Size
0x18000c938  lea     rcx, [rsp+188h+var_120]; void *
0x18000c93d  call    memset_0
0x18000c942  movzx   edx, [rsp+188h+arg_10]
0x18000c94a  mov     dword ptr [rsp+188h+var_160], r15d
0x18000c94f  lea     rax, aErrorOnCalling; "Error on calling SetServiceStatus. 0x%0"...
0x18000c956  mov     [rsp+188h+var_168], rax
0x18000c95b  mov     r9d, r15d
0x18000c95e  lea     r8, [rsp+188h+var_148]
0x18000c963  lea     rcx, [rsp+188h+var_98]
0x18000c96b  call    ?ThrowIf@CVssFunctionTracer@@QEAAXHUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::ThrowIf(int,CVssDebugInfo,long,ushort * const,...)
0x18000c970  nop
0x18000c971  lea     rcx, [rsp+188h+var_98]; this
0x18000c979  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000c97e  lea     r11, [rsp+188h+var_18]
0x18000c986  mov     rbx, [r11+28h]
0x18000c98a  mov     rsi, [r11+38h]
0x18000c98e  mov     rsp, r11
0x18000c991  pop     r15
0x18000c993  pop     r14
0x18000c995  pop     rdi
0x18000c996  retn
```
