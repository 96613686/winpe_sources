# CVsServiceModule::StartDispatcher(void)

- ea: `0x140033e1c`
- end: `0x140034313`
- name: `?StartDispatcher@CVsServiceModule@@IEAAXXZ`
- size: `1271`
- prototype: `void __fastcall(CVsServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140033780`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140015e38`
- `0x140032fcc`
- `0x1400330fc`
- `0x140033e1c`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140034213`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140034213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400340e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400340eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400340e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400340eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14003418f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14003418f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003428d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003428d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140033ee8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140033ee8`
- `VssTrace!__imp_VssTraceMessage` at `0x140033ff0`
- `VssTrace!__imp_VssTraceMessage` at `0x140033ff0`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140033f49`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140033f49`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140033f3a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140033f3a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400342a4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400342a4`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14003403a`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14003403a`

## string_xrefs

- `0x140033e49`: `CVsServiceModule::StartDispatcher`
- `0x14003415c`: `StartServiceCtrlDispatcherW failed. 0x%08lx`
- `0x1400341f2`: `CVsServiceModule::StartDispatcher: Waiting for ServiceMain thread to finish...`
- `0x140034271`: `CVsServiceModule::StartDispatcher: Wait timed out, ending anyway`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVsServiceModule::StartDispatcher(CVsServiceModule *this)
{
  int v1; // eax
  CVsServiceModule *v2; // rcx
  int v3; // ebx
  BOOL started; // eax
  int LastError; // eax
  CVssDebugInfo *v6; // rax
  DWORD v7; // edi
  signed int v8; // eax
  unsigned int v9; // ebx
  HANDLE v10; // rbx
  __int64 v11; // [rsp+20h] [rbp-258h]
  unsigned __int64 v12; // [rsp+50h] [rbp-228h] BYREF
  HRESULT v13; // [rsp+58h] [rbp-220h]
  const unsigned __int16 *v14; // [rsp+60h] [rbp-218h]
  const unsigned __int16 *v15; // [rsp+68h] [rbp-210h]
  unsigned int v16; // [rsp+70h] [rbp-208h]
  unsigned int v17; // [rsp+74h] [rbp-204h]
  const unsigned __int16 *v18; // [rsp+78h] [rbp-200h]
  unsigned int v19; // [rsp+80h] [rbp-1F8h]
  DWORD TickCount; // [rsp+84h] [rbp-1F4h]
  int v21; // [rsp+88h] [rbp-1F0h]
  __int128 v22; // [rsp+90h] [rbp-1E8h]
  __int128 v23; // [rsp+A0h] [rbp-1D8h]
  CVsServiceModule *v24; // [rsp+B0h] [rbp-1C8h]
  const unsigned __int16 *v25; // [rsp+C0h] [rbp-1B8h] BYREF
  const unsigned __int16 *v26; // [rsp+C8h] [rbp-1B0h]
  const unsigned __int16 *v27; // [rsp+D0h] [rbp-1A8h]
  int v28; // [rsp+D8h] [rbp-1A0h]
  int v29; // [rsp+DCh] [rbp-19Ch]
  int v30; // [rsp+E0h] [rbp-198h]
  _BYTE v31[120]; // [rsp+E8h] [rbp-190h] BYREF
  int v32; // [rsp+160h] [rbp-118h]
  int v33; // [rsp+168h] [rbp-110h] BYREF
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+170h] [rbp-108h] BYREF
  __int64 v35; // [rsp+180h] [rbp-F8h]
  __int64 v36; // [rsp+188h] [rbp-F0h]
  const std::exception *v37; // [rsp+190h] [rbp-E8h] BYREF
  _com_error *v38; // [rsp+198h] [rbp-E0h] BYREF
  char v39[176]; // [rsp+1A0h] [rbp-D8h] BYREF
  CVsServiceModule *v40; // [rsp+280h] [rbp+8h] BYREF

  v40 = this;
  v25 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v26 = L"CVsServiceModule::StartDispatcher";
  v27 = L"CORSVCC";
  v28 = 243;
  v29 = 1;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  v13 = 0;
  v18 = L"CVsServiceModule::StartDispatcher";
  v14 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v15 = L"CORSVCC";
  v16 = 243;
  v17 = 1;
  TickCount = GetTickCount();
  v21 = 255;
  v12 = 0xFFFFFFFF00000000uLL;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v40 = 0;
  if ( (int)VssGetTracingContextPerThread(&v40) < 0 )
  {
    v2 = v24;
  }
  else
  {
    v1 = VssSetTracingContextPerThread(&v12);
    v2 = v24;
    if ( v1 >= 0 )
      v2 = v40;
    v24 = v2;
  }
  if ( v2 )
    v19 = *((_DWORD *)v2 + 12) + 1;
  else
    v19 = 0;
  v3 = 160;
  if ( v21 != 255 )
    v3 = v21;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v12) )
    VssTraceMessage(v14, v15, v16, v19, v17, v18, L"ENTER", v3, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v25);
  ServiceStartTable.lpServiceName = (LPWSTR)L"VSS";
  ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)CVsServiceModule::_ServiceMain;
  v35 = 0;
  v36 = 0;
  started = StartServiceCtrlDispatcherW(&ServiceStartTable);
  try
  {
    if ( !started )
    {
      v25 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
      v26 = L"CVsServiceModule::StartDispatcher";
      v27 = L"CORSVCC";
      v28 = 256;
      v29 = 1;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v25, (CVssDebugInfo *)v39, LastError);
      CVssFunctionTracer::LogError((__int64)&v12, 1u, (__int64)v6, 1u);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v25);
      v7 = GetLastError();
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v25 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
      v26 = L"CVsServiceModule::StartDispatcher";
      v27 = L"CORSVCC";
      v28 = 257;
      v29 = 1;
      v30 = 255;
      v32 = 0x1000000;
      memset_0(v31, 0, sizeof(v31));
      LODWORD(v11) = v7;
      CVssFunctionTracer::Throw(&v12, &v25, v9, L"StartServiceCtrlDispatcherW failed. 0x%08lx", v11);
    }
    if ( dwThreadId )
    {
      v10 = OpenThread(0x100000u, 0, dwThreadId);
      if ( v10 )
      {
        v25 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
        v26 = L"CVsServiceModule::StartDispatcher";
        v27 = L"CORSVCC";
        v28 = 269;
        v29 = 1;
        v30 = 255;
        v32 = 0x1000000;
        memset_0(v31, 0, sizeof(v31));
        CVssFunctionTracer::Trace(
          &v12,
          &v25,
          L"CVsServiceModule::StartDispatcher: Waiting for ServiceMain thread to finish...");
        if ( WaitForSingleObject(v10, 0x2710u) == 258 )
        {
          v25 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
          v26 = L"CVsServiceModule::StartDispatcher";
          v27 = L"CORSVCC";
          v28 = 273;
          v29 = 1;
          v30 = 255;
          v32 = 0x1000000;
          memset_0(v31, 0, sizeof(v31));
          CVssFunctionTracer::Trace(&v12, &v25, L"CVsServiceModule::StartDispatcher: Wait timed out, ending anyway");
        }
        CloseHandle(v10);
      }
    }
    if ( !_InterlockedCompareExchange(&dword_14014F9E8, 1, 0) )
    {
      v13 = CoInitializeEx(0, 0);
      if ( v13 >= 0 )
      {
        LOBYTE(v40) = 1;
        (*(void (__fastcall **)(void *, CVsServiceModule **))(_Module + 96LL))(&_Module, &v40);
      }
    }
  }
  catch ( long v33 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v12,
      v33,
      L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
      L"CORSVCC",
      L"CVsServiceModule::StartDispatcher",
      0x122u,
      v17);
  }
  catch ( _com_error *v38 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v12,
      v38,
      L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
      L"CORSVCC",
      L"CVsServiceModule::StartDispatcher",
      0x122u,
      v17);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v12,
      L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
      L"CORSVCC",
      L"CVsServiceModule::StartDispatcher",
      0x122u,
      v17);
  }
  catch ( const std::exception *v37 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v12,
      v37,
      L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
      L"CORSVCC",
      L"CVsServiceModule::StartDispatcher",
      0x122u,
      v17);
  }
  HIDWORD(xmmword_14014F990) = v13;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v12);
}

```

## disassembly

```asm
0x140033e1c  mov     rax, rsp
0x140033e1f  mov     [rax+10h], rbx
0x140033e23  mov     [rax+18h], rsi
0x140033e27  mov     [rax+8], rcx
0x140033e2b  push    rdi
0x140033e2c  push    r12
0x140033e2e  push    r13
0x140033e30  push    r14
0x140033e32  push    r15
0x140033e34  sub     rsp, 250h
0x140033e3b  lea     r12, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140033e42  mov     [rax-1B8h], r12
0x140033e49  lea     r13, aCvsservicemodu_6; "CVsServiceModule::StartDispatcher"
0x140033e50  mov     [rax-1B0h], r13
0x140033e57  lea     rdi, aCorsvcc; "CORSVCC"
0x140033e5e  mov     [rax-1A8h], rdi
0x140033e65  mov     dword ptr [rax-1A0h], 0F3h
0x140033e6f  mov     r14d, 1
0x140033e75  mov     [rax-19Ch], r14d
0x140033e7c  mov     r15d, 0FFh
0x140033e82  mov     [rax-198h], r15d
0x140033e89  xor     esi, esi
0x140033e8b  mov     dword ptr [rax-118h], 1000000h
0x140033e95  xor     edx, edx; Val
0x140033e97  lea     r8d, [r14+77h]; Size
0x140033e9b  lea     rcx, [rax-190h]; void *
0x140033ea2  call    memset_0
0x140033ea7  mov     [rsp+278h+var_220], esi
0x140033eab  mov     rax, [rsp+278h+var_1B0]
0x140033eb3  mov     [rsp+278h+var_200], rax
0x140033eb8  mov     rax, [rsp+278h+var_1B8]
0x140033ec0  mov     [rsp+278h+var_218], rax
0x140033ec5  mov     rax, [rsp+278h+var_1A8]
0x140033ecd  mov     [rsp+278h+var_210], rax
0x140033ed2  mov     eax, [rsp+278h+var_1A0]
0x140033ed9  mov     [rsp+278h+var_208], eax
0x140033edd  mov     eax, [rsp+278h+var_19C]
0x140033ee4  mov     [rsp+278h+var_204], eax
0x140033ee8  call    cs:__imp_GetTickCount
0x140033eee  mov     [rsp+278h+var_1F4], eax
0x140033ef5  mov     [rsp+278h+var_224], 0FFFFFFFFh
0x140033efd  mov     eax, [rsp+278h+var_198]
0x140033f04  mov     [rsp+278h+var_1F0], eax
0x140033f0b  mov     [rsp+278h+var_228], esi
0x140033f0f  mov     [rsp+278h+var_1C8], rsi
0x140033f17  xorps   xmm0, xmm0
0x140033f1a  movups  [rsp+278h+var_1E8], xmm0
0x140033f22  movups  [rsp+278h+var_1D8], xmm0
0x140033f2a  mov     [rsp+278h+arg_0], rsi
0x140033f32  lea     rcx, [rsp+278h+arg_0]
0x140033f3a  call    cs:__imp_VssGetTracingContextPerThread
0x140033f40  test    eax, eax
0x140033f42  js      short loc_140033F6C
0x140033f44  lea     rcx, [rsp+278h+var_228]
0x140033f49  call    cs:__imp_VssSetTracingContextPerThread
0x140033f4f  mov     rcx, [rsp+278h+var_1C8]
0x140033f57  test    eax, eax
0x140033f59  cmovns  rcx, [rsp+278h+arg_0]
0x140033f62  mov     [rsp+278h+var_1C8], rcx
0x140033f6a  jmp     short loc_140033F74
0x140033f6c  mov     rcx, [rsp+278h+var_1C8]
0x140033f74  test    rcx, rcx
0x140033f77  jz      short loc_140033F88
0x140033f79  mov     eax, [rcx+30h]
0x140033f7c  add     eax, r14d
0x140033f7f  mov     [rsp+278h+var_1F8], eax
0x140033f86  jmp     short loc_140033F8F
0x140033f88  mov     [rsp+278h+var_1F8], esi
0x140033f8f  mov     ebx, 0A0h
0x140033f94  cmp     [rsp+278h+var_1F0], r15d
0x140033f9c  cmovnz  ebx, [rsp+278h+var_1F0]
0x140033fa4  lea     rcx, [rsp+278h+var_228]; this
0x140033fa9  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140033fae  test    eax, eax
0x140033fb0  jz      short loc_140033FF6
0x140033fb2  mov     [rsp+278h+var_238], rsi
0x140033fb7  mov     [rsp+278h+var_240], ebx
0x140033fbb  lea     rax, aEnter; "ENTER"
0x140033fc2  mov     [rsp+278h+var_248], rax
0x140033fc7  mov     rax, [rsp+278h+var_200]
0x140033fcc  mov     [rsp+278h+var_250], rax
0x140033fd1  mov     eax, [rsp+278h+var_204]
0x140033fd5  mov     dword ptr [rsp+278h+var_258], eax
0x140033fd9  mov     r9d, [rsp+278h+var_1F8]
0x140033fe1  mov     r8d, [rsp+278h+var_208]
0x140033fe6  mov     rdx, [rsp+278h+var_210]
0x140033feb  mov     rcx, [rsp+278h+var_218]
0x140033ff0  call    cs:__imp_VssTraceMessage
0x140033ff6  lea     rcx, [rsp+278h+var_1B8]; this
0x140033ffe  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140034003  nop
0x140034004  lea     rax, ServiceName; "VSS"
0x14003400b  mov     [rsp+278h+ServiceStartTable.lpServiceName], rax
0x140034013  lea     rax, ?_ServiceMain@CVsServiceModule@@KAXKPEAPEAG@Z; CVsServiceModule::_ServiceMain(ulong,ushort * *)
0x14003401a  mov     [rsp+278h+ServiceStartTable.lpServiceProc], rax
0x140034022  mov     [rsp+278h+var_F8], rsi
0x14003402a  mov     [rsp+278h+var_F0], rsi
0x140034032  lea     rcx, [rsp+278h+ServiceStartTable]; lpServiceStartTable
0x14003403a  call    cs:__imp_StartServiceCtrlDispatcherW
0x140034040  test    eax, eax
0x140034042  jnz     loc_140034178
0x140034048  mov     [rsp+278h+var_1B8], r12
0x140034050  mov     [rsp+278h+var_1B0], r13
0x140034058  mov     [rsp+278h+var_1A8], rdi
0x140034060  mov     [rsp+278h+var_1A0], 100h
0x14003406b  mov     [rsp+278h+var_19C], r14d
0x140034073  mov     [rsp+278h+var_198], r15d
0x14003407b  mov     [rsp+278h+var_118], 1000000h
0x140034086  xor     edx, edx; Val
0x140034088  lea     r8d, [rax+78h]; Size
0x14003408c  lea     rcx, [rsp+278h+var_190]; void *
0x140034094  call    memset_0
0x140034099  call    cs:__imp_GetLastError
0x14003409f  test    eax, eax
0x1400340a1  jle     short loc_1400340AB
0x1400340a3  movzx   eax, ax
0x1400340a6  or      eax, 80070000h
0x1400340ab  mov     r8d, eax; dwMessageId
0x1400340ae  lea     rdx, [rsp+278h+var_D8]; this
0x1400340b6  lea     rcx, [rsp+278h+var_1B8]; struct CVssDebugInfo *
0x1400340be  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x1400340c3  mov     r9d, r14d
0x1400340c6  mov     r8, rax
0x1400340c9  mov     edx, r14d
0x1400340cc  lea     rcx, [rsp+278h+var_228]
0x1400340d1  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x1400340d6  lea     rcx, [rsp+278h+var_1B8]; this
0x1400340de  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x1400340e3  call    cs:__imp_GetLastError
0x1400340e9  mov     edi, eax
0x1400340eb  call    cs:__imp_GetLastError
0x1400340f1  mov     ebx, eax
0x1400340f3  test    eax, eax
0x1400340f5  jle     short loc_140034100
0x1400340f7  movzx   ebx, ax
0x1400340fa  or      ebx, 80070000h
0x140034100  mov     [rsp+278h+var_1B8], r12
0x140034108  mov     [rsp+278h+var_1B0], r13
0x140034110  lea     rax, aCorsvcc; "CORSVCC"
0x140034117  mov     [rsp+278h+var_1A8], rax
0x14003411f  mov     [rsp+278h+var_1A0], 101h
0x14003412a  mov     [rsp+278h+var_19C], r14d
0x140034132  mov     [rsp+278h+var_198], r15d
0x14003413a  mov     [rsp+278h+var_118], 1000000h
0x140034145  xor     edx, edx; Val
0x140034147  lea     r8d, [rdx+78h]; Size
0x14003414b  lea     rcx, [rsp+278h+var_190]; void *
0x140034153  call    memset_0
0x140034158  mov     dword ptr [rsp+278h+var_258], edi
0x14003415c  lea     r9, aStartservicect_0; "StartServiceCtrlDispatcherW failed. 0x%"...
0x140034163  mov     r8d, ebx
0x140034166  lea     rdx, [rsp+278h+var_1B8]
0x14003416e  lea     rcx, [rsp+278h+var_228]
0x140034173  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140034178  mov     r8d, cs:dwThreadId; dwThreadId
0x14003417f  test    r8d, r8d
0x140034182  jz      loc_140034293
0x140034188  xor     edx, edx; bInheritHandle
0x14003418a  mov     ecx, 100000h; dwDesiredAccess
0x14003418f  call    cs:__imp_OpenThread
0x140034195  mov     rbx, rax
0x140034198  test    rax, rax
0x14003419b  jz      loc_140034293
0x1400341a1  mov     [rsp+278h+var_1B8], r12
0x1400341a9  mov     [rsp+278h+var_1B0], r13
0x1400341b1  mov     [rsp+278h+var_1A8], rdi
0x1400341b9  mov     [rsp+278h+var_1A0], 10Dh
0x1400341c4  mov     [rsp+278h+var_19C], r14d
0x1400341cc  mov     [rsp+278h+var_198], r15d
0x1400341d4  mov     [rsp+278h+var_118], 1000000h
0x1400341df  xor     edx, edx; Val
0x1400341e1  lea     r8d, [rdx+78h]; Size
0x1400341e5  lea     rcx, [rsp+278h+var_190]; void *
0x1400341ed  call    memset_0
0x1400341f2  lea     r8, aCvsservicemodu_7; "CVsServiceModule::StartDispatcher: Wait"...
0x1400341f9  lea     rdx, [rsp+278h+var_1B8]
0x140034201  lea     rcx, [rsp+278h+var_228]
0x140034206  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003420b  mov     edx, 2710h; dwMilliseconds
0x140034210  mov     rcx, rbx; hHandle
0x140034213  call    cs:__imp_WaitForSingleObject
0x140034219  cmp     eax, 102h
0x14003421e  jnz     short loc_14003428A
0x140034220  mov     [rsp+278h+var_1B8], r12
0x140034228  mov     [rsp+278h+var_1B0], r13
0x140034230  mov     [rsp+278h+var_1A8], rdi
0x140034238  mov     [rsp+278h+var_1A0], 111h
0x140034243  mov     [rsp+278h+var_19C], r14d
0x14003424b  mov     [rsp+278h+var_198], r15d
0x140034253  mov     [rsp+278h+var_118], 1000000h
0x14003425e  xor     edx, edx; Val
0x140034260  lea     r8d, [rdx+78h]; Size
0x140034264  lea     rcx, [rsp+278h+var_190]; void *
0x14003426c  call    memset_0
0x140034271  lea     r8, aCvsservicemodu_12; "CVsServiceModule::StartDispatcher: Wait"...
0x140034278  lea     rdx, [rsp+278h+var_1B8]
0x140034280  lea     rcx, [rsp+278h+var_228]
0x140034285  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003428a  mov     rcx, rbx; hObject
0x14003428d  call    cs:__imp_CloseHandle
0x140034293  xor     eax, eax
0x140034295  lock cmpxchg cs:dword_14014F9E8, r14d
0x14003429e  jnz     short loc_1400342DA
0x1400342a0  xor     edx, edx; dwCoInit
0x1400342a2  xor     ecx, ecx; pvReserved
0x1400342a4  call    cs:__imp_CoInitializeEx
0x1400342aa  mov     [rsp+278h+var_220], eax
0x1400342ae  test    eax, eax
0x1400342b0  js      short loc_1400342DA
0x1400342b2  mov     byte ptr [rsp+278h+arg_0], r14b
0x1400342ba  mov     rax, cs:?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x1400342c1  lea     rdx, [rsp+278h+arg_0]
0x1400342c9  lea     rcx, ?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x1400342d0  mov     rax, [rax+60h]
0x1400342d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400342d9  nop
0x1400342da  jmp     short loc_1400342E2
0x1400342dc  jmp     short loc_1400342E2
0x1400342de  jmp     short loc_1400342E2
0x1400342e0  jmp     short $+2
0x1400342e2  mov     eax, [rsp+278h+var_220]
0x1400342e6  mov     dword ptr cs:xmmword_14014F990+0Ch, eax
0x1400342ec  lea     rcx, [rsp+278h+var_228]; this
0x1400342f1  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400342f6  lea     r11, [rsp+278h+var_28]
0x1400342fe  mov     rbx, [r11+38h]
0x140034302  mov     rsi, [r11+40h]
0x140034306  mov     rsp, r11
0x140034309  pop     r15
0x14003430b  pop     r14
0x14003430d  pop     r13
0x14003430f  pop     r12
0x140034311  pop     rdi
0x140034312  retn
```
