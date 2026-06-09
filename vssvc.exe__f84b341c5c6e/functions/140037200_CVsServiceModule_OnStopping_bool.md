# CVsServiceModule::OnStopping(bool &)

- ea: `0x140037200`
- end: `0x1400376d7`
- name: `?OnStopping@CVsServiceModule@@MEAAXAEA_N@Z`
- size: `1239`
- prototype: `void __fastcall(CVsServiceModule *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140037200`
- `0x1400376e0`
- `0x140037d20`
- `0x140037df4`
- `0x140037edc`
- `0x140037fa0`
- `0x140038228`
- `0x14003836c`
- `0x140038798`
- `0x140042070`
- `0x140052624`
- `0x140058f44`
- `0x140091584`
- `0x1400921dc`
- `0x1400c55a0`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400375db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400375db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400375d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400375d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400372ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400372ca`
- `VssTrace!__imp_VssTraceMessage` at `0x1400373e3`
- `VssTrace!__imp_VssTraceMessage` at `0x1400373e3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003732b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003732b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003731c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003731c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003740d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400375c1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003740d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400375c1`

## string_xrefs

- `0x140037231`: `CVsServiceModule::OnStopping`
- `0x1400375ae`: `CVsServiceModule::OnStopping`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVsServiceModule::OnStopping(CVsServiceModule *this, bool *a2)
{
  bool *v2; // rbx
  CVsServiceModule *v3; // rsi
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  DWORD LastError; // ebx
  void **v8; // rbx
  void *v9; // rbx
  unsigned __int64 v10; // [rsp+50h] [rbp-178h] BYREF
  int v11; // [rsp+58h] [rbp-170h]
  const unsigned __int16 *v12; // [rsp+60h] [rbp-168h]
  const unsigned __int16 *v13; // [rsp+68h] [rbp-160h]
  unsigned int v14; // [rsp+70h] [rbp-158h]
  unsigned int v15; // [rsp+74h] [rbp-154h]
  const unsigned __int16 *v16; // [rsp+78h] [rbp-150h]
  unsigned int v17; // [rsp+80h] [rbp-148h]
  DWORD TickCount; // [rsp+84h] [rbp-144h]
  int v19; // [rsp+88h] [rbp-140h]
  __int128 v20; // [rsp+90h] [rbp-138h]
  __int128 v21; // [rsp+A0h] [rbp-128h]
  __int64 v22; // [rsp+B0h] [rbp-118h]
  const unsigned __int16 *v23; // [rsp+C0h] [rbp-108h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp-100h]
  const unsigned __int16 *v25; // [rsp+D0h] [rbp-F8h]
  int v26; // [rsp+D8h] [rbp-F0h]
  int v27; // [rsp+DCh] [rbp-ECh]
  int v28; // [rsp+E0h] [rbp-E8h]
  _BYTE v29[120]; // [rsp+E8h] [rbp-E0h] BYREF
  int v30; // [rsp+160h] [rbp-68h]
  int v31; // [rsp+168h] [rbp-60h] BYREF
  int v32; // [rsp+16Ch] [rbp-5Ch] BYREF
  _com_error *v33; // [rsp+170h] [rbp-58h] BYREF
  const std::exception *v34; // [rsp+178h] [rbp-50h] BYREF
  _com_error *v35; // [rsp+180h] [rbp-48h] BYREF
  const std::exception *v36; // [rsp+188h] [rbp-40h] BYREF
  int v39; // [rsp+1E0h] [rbp+18h]
  int v40; // [rsp+1E0h] [rbp+18h]
  __int64 v41; // [rsp+1E8h] [rbp+20h] BYREF

  v2 = a2;
  v3 = this;
  v23 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v24 = L"CVsServiceModule::OnStopping";
  v25 = L"CORSVCC";
  v26 = 800;
  v27 = 1;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  v11 = 0;
  v16 = L"CVsServiceModule::OnStopping";
  v12 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v13 = L"CORSVCC";
  v14 = 800;
  v15 = 1;
  TickCount = GetTickCount();
  v19 = 255;
  v10 = 0xFFFFFFFF00000000uLL;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 )
  {
    v5 = v22;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(&v10);
    v5 = v22;
    if ( v4 >= 0 )
      v5 = v41;
    v22 = v5;
  }
  if ( v5 )
    v17 = *(_DWORD *)(v5 + 48) + 1;
  else
    v17 = 0;
  v6 = 160;
  if ( v19 != 255 )
    v6 = v19;
  v39 = v6;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v10) )
    VssTraceMessage(v12, v13, v14, v17, v15, v16, L"ENTER", v39, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v23);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v3 + 46, 1, 0) )
  {
    if ( *v2 )
    {
      CoUninitialize();
      *v2 = 0;
    }
  }
  else
  {
    try
    {
      CRegistryWriter::DestroyWriter();
      CComRegDBWriterWrapper::DestroyWriter();
      CVssAsrWriterBackup::DestroyWriter();
      CVssDeletingWriter::DestroyWriter();
      if ( *((_QWORD *)v3 + 24) )
      {
        v23 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
        v24 = L"CVsServiceModule::OnStopping";
        v25 = L"CORSVCC";
        v26 = 825;
        v27 = 1;
        v28 = 255;
        v30 = 0x1000000;
        memset_0(v29, 0, sizeof(v29));
        CVssFunctionTracer::Trace(&v10, &v23, L"about to enter context callback for disconnect");
        v40 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(**((_QWORD **)v3 + 24) + 24LL))(
                *((_QWORD *)v3 + 24),
                DisconnectCallback,
                0,
                &IID_IContextCallback,
                5,
                0);
        v11 = v40;
        if ( v40 < 0 )
        {
          v23 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
          v24 = L"CVsServiceModule::OnStopping";
          v25 = L"CORSVCC";
          v26 = 828;
          v27 = 1;
          v28 = 255;
          v30 = 0x1000000;
          memset_0(v29, 0, sizeof(v29));
          CVssFunctionTracer::Trace(
            &v10,
            &v23,
            L"IContextCallback::ContextCallback(DisconnectCallback) failed wiht 0x%08lx",
            (unsigned int)v40);
        }
        CVssSafeComPtr<IContextCallback>::Reset((char *)v3 + 208);
        ATL::CComPtr<IVssHardwareSnapshotProviderEx>::operator=((struct IUnknown **)v3 + 24);
      }
      CVssProviderManager::UnloadInternalProvidersArray();
      CVssProviderManager::UnloadGlobalProviderItfCache();
      try
      {
        CVssProviderManager::DeactivateAll();
      }
      catch ( long v31 )
      {
        CVssFunctionTracer::HandleHresultException(
          (CVssFunctionTracer *)&v10,
          v31,
          L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
          L"CORSVCC",
          L"CVsServiceModule::OnStopping",
          0x34Fu,
          v15);
        v2 = a2;
        v3 = this;
      }
      catch ( _com_error *v33 )
      {
        CVssFunctionTracer::HandleComException(
          (CVssFunctionTracer *)&v10,
          v33,
          L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
          L"CORSVCC",
          L"CVsServiceModule::OnStopping",
          0x34Fu,
          v15);
      }
      catch ( std::bad_alloc )
      {
        CVssFunctionTracer::HandleStdBadAllocException(
          (CVssFunctionTracer *)&v10,
          L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
          L"CORSVCC",
          L"CVsServiceModule::OnStopping",
          0x34Fu,
          v15);
        v2 = a2;
        v3 = this;
      }
      catch ( const std::exception *v34 )
      {
        CVssFunctionTracer::HandleStdGenericException(
          (CVssFunctionTracer *)&v10,
          v34,
          L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
          L"CORSVCC",
          L"CVsServiceModule::OnStopping",
          0x34Fu,
          v15);
      }
      if ( *v2 )
      {
        CoUninitialize();
        *v2 = 0;
      }
      if ( !CloseHandle(*((HANDLE *)v3 + 19)) )
      {
        LastError = GetLastError();
        v23 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
        v24 = L"CVsServiceModule::OnStopping";
        v25 = L"CORSVCC";
        v26 = 859;
        v27 = 1;
        v28 = 255;
        v30 = 0x1000000;
        memset_0(v29, 0, sizeof(v29));
        CVssFunctionTracer::Trace(&v10, &v23, L"Error closing the sub sync event 0x%08lx", LastError);
      }
      if ( (unsigned int)CVssSKU::IsServer() && *((_BYTE *)v3 + 161) )
      {
        v8 = (void **)*((_QWORD *)v3 + 22);
        CVssDeviceNotifier::UnregisterDeviceInterfaceNotification((CVssDeviceNotifier *)v8, v8 + 3);
        CVssDeviceNotifier::UnregisterDeviceInterfaceNotification((CVssDeviceNotifier *)v8, v8 + 2);
        CVssDeviceNotifier::UnregisterDeviceInterfaceNotification((CVssDeviceNotifier *)v8, v8 + 1);
      }
      v9 = (void *)*((_QWORD *)v3 + 22);
      if ( v9 )
      {
        CVssDeviceNotifier::~CVssDeviceNotifier(*((CVssDeviceNotifier **)v3 + 22));
        operator delete(v9);
      }
    }
    catch ( long v32 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v10,
        v32,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::OnStopping",
        0x361u,
        v15);
    }
    catch ( _com_error *v35 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v10,
        v35,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::OnStopping",
        0x361u,
        v15);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v10,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::OnStopping",
        0x361u,
        v15);
    }
    catch ( const std::exception *v36 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v10,
        v36,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::OnStopping",
        0x361u,
        v15);
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v10);
}

```

## disassembly

```asm
0x140037200  mov     rax, rsp
0x140037203  mov     [rax+10h], rdx
0x140037207  mov     [rax+8], rcx
0x14003720b  push    rbx
0x14003720c  push    rsi
0x14003720d  push    rdi
0x14003720e  push    r12
0x140037210  push    r13
0x140037212  push    r14
0x140037214  push    r15
0x140037216  sub     rsp, 190h
0x14003721d  mov     rbx, rdx
0x140037220  mov     rsi, rcx
0x140037223  lea     r15, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14003722a  mov     [rax-108h], r15
0x140037231  lea     r12, aCvsservicemodu_3; "CVsServiceModule::OnStopping"
0x140037238  mov     [rax-100h], r12
0x14003723f  lea     r13, aCorsvcc; "CORSVCC"
0x140037246  mov     [rax-0F8h], r13
0x14003724d  mov     dword ptr [rax-0F0h], 320h
0x140037257  mov     r14d, 1
0x14003725d  mov     [rax-0ECh], r14d
0x140037264  mov     dword ptr [rax-0E8h], 0FFh
0x14003726e  xor     edi, edi
0x140037270  mov     dword ptr [rax-68h], 1000000h
0x140037277  xor     edx, edx; Val
0x140037279  lea     r8d, [r14+77h]; Size
0x14003727d  lea     rcx, [rax-0E0h]; void *
0x140037284  call    memset_0
0x140037289  mov     [rsp+1C8h+var_170], edi
0x14003728d  mov     rax, [rsp+1C8h+var_100]
0x140037295  mov     [rsp+1C8h+var_150], rax
0x14003729a  mov     rax, [rsp+1C8h+var_108]
0x1400372a2  mov     [rsp+1C8h+var_168], rax
0x1400372a7  mov     rax, [rsp+1C8h+var_F8]
0x1400372af  mov     [rsp+1C8h+var_160], rax
0x1400372b4  mov     eax, [rsp+1C8h+var_F0]
0x1400372bb  mov     [rsp+1C8h+var_158], eax
0x1400372bf  mov     eax, [rsp+1C8h+var_EC]
0x1400372c6  mov     [rsp+1C8h+var_154], eax
0x1400372ca  call    cs:__imp_GetTickCount
0x1400372d0  mov     [rsp+1C8h+var_144], eax
0x1400372d7  mov     [rsp+1C8h+var_174], 0FFFFFFFFh
0x1400372df  mov     eax, [rsp+1C8h+var_E8]
0x1400372e6  mov     [rsp+1C8h+var_140], eax
0x1400372ed  mov     [rsp+1C8h+var_178], edi
0x1400372f1  mov     [rsp+1C8h+var_118], rdi
0x1400372f9  xorps   xmm0, xmm0
0x1400372fc  movups  [rsp+1C8h+var_138], xmm0
0x140037304  movups  [rsp+1C8h+var_128], xmm0
0x14003730c  mov     [rsp+1C8h+arg_18], rdi
0x140037314  lea     rcx, [rsp+1C8h+arg_18]
0x14003731c  call    cs:__imp_VssGetTracingContextPerThread
0x140037322  test    eax, eax
0x140037324  js      short loc_14003734E
0x140037326  lea     rcx, [rsp+1C8h+var_178]
0x14003732b  call    cs:__imp_VssSetTracingContextPerThread
0x140037331  mov     rcx, [rsp+1C8h+var_118]
0x140037339  test    eax, eax
0x14003733b  cmovns  rcx, [rsp+1C8h+arg_18]
0x140037344  mov     [rsp+1C8h+var_118], rcx
0x14003734c  jmp     short loc_140037356
0x14003734e  mov     rcx, [rsp+1C8h+var_118]
0x140037356  test    rcx, rcx
0x140037359  jz      short loc_14003736A
0x14003735b  mov     eax, [rcx+30h]
0x14003735e  add     eax, r14d
0x140037361  mov     [rsp+1C8h+var_148], eax
0x140037368  jmp     short loc_140037371
0x14003736a  mov     [rsp+1C8h+var_148], edi
0x140037371  mov     eax, 0A0h
0x140037376  cmp     [rsp+1C8h+var_140], 0FFh
0x140037381  cmovnz  eax, [rsp+1C8h+var_140]
0x140037389  mov     [rsp+1C8h+arg_10], eax
0x140037390  lea     rcx, [rsp+1C8h+var_178]; this
0x140037395  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003739a  test    eax, eax
0x14003739c  jz      short loc_1400373E9
0x14003739e  mov     [rsp+1C8h+var_188], rdi
0x1400373a3  mov     eax, [rsp+1C8h+arg_10]
0x1400373aa  mov     [rsp+1C8h+var_190], eax
0x1400373ae  lea     rax, aEnter; "ENTER"
0x1400373b5  mov     [rsp+1C8h+var_198], rax
0x1400373ba  mov     rax, [rsp+1C8h+var_150]
0x1400373bf  mov     [rsp+1C8h+var_1A0], rax
0x1400373c4  mov     eax, [rsp+1C8h+var_154]
0x1400373c8  mov     [rsp+1C8h+var_1A8], eax
0x1400373cc  mov     r9d, [rsp+1C8h+var_148]
0x1400373d4  mov     r8d, [rsp+1C8h+var_158]
0x1400373d9  mov     rdx, [rsp+1C8h+var_160]
0x1400373de  mov     rcx, [rsp+1C8h+var_168]
0x1400373e3  call    cs:__imp_VssTraceMessage
0x1400373e9  lea     rcx, [rsp+1C8h+var_108]; this
0x1400373f1  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x1400373f6  nop
0x1400373f7  xor     eax, eax
0x1400373f9  lock cmpxchg [rsi+0B8h], r14d
0x140037402  jz      short loc_14003741B
0x140037404  cmp     [rbx], dil
0x140037407  jz      loc_1400376BA
0x14003740d  call    cs:__imp_CoUninitialize
0x140037413  mov     [rbx], dil
0x140037416  jmp     loc_1400376BA
0x14003741b  call    ?DestroyWriter@CRegistryWriter@@SAXXZ; CRegistryWriter::DestroyWriter(void)
0x140037420  call    ?DestroyWriter@CComRegDBWriterWrapper@@SAXXZ; CComRegDBWriterWrapper::DestroyWriter(void)
0x140037425  call    ?DestroyWriter@CVssAsrWriterBackup@@SAXXZ; CVssAsrWriterBackup::DestroyWriter(void)
0x14003742a  call    ?DestroyWriter@CVssDeletingWriter@@SAXXZ; CVssDeletingWriter::DestroyWriter(void)
0x14003742f  cmp     [rsi+0C0h], rdi
0x140037436  jz      loc_140037576
0x14003743c  mov     [rsp+1C8h+var_108], r15
0x140037444  mov     [rsp+1C8h+var_100], r12
0x14003744c  mov     [rsp+1C8h+var_F8], r13
0x140037454  mov     [rsp+1C8h+var_F0], 339h
0x14003745f  mov     [rsp+1C8h+var_EC], r14d
0x140037467  mov     [rsp+1C8h+var_E8], 0FFh
0x140037472  mov     [rsp+1C8h+var_68], 1000000h
0x14003747d  xor     edx, edx; Val
0x14003747f  lea     r8d, [rdx+78h]; Size
0x140037483  lea     rcx, [rsp+1C8h+var_E0]; void *
0x14003748b  call    memset_0
0x140037490  lea     r8, aAboutToEnterCo; "about to enter context callback for dis"...
0x140037497  lea     rdx, [rsp+1C8h+var_108]
0x14003749f  lea     rcx, [rsp+1C8h+var_178]
0x1400374a4  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400374a9  mov     rcx, [rsi+0C0h]
0x1400374b0  mov     rax, [rcx]
0x1400374b3  mov     [rsp+1C8h+var_1A0], rdi
0x1400374b8  mov     [rsp+1C8h+var_1A8], 5
0x1400374c0  lea     r9, IID_IContextCallback
0x1400374c7  xor     r8d, r8d
0x1400374ca  lea     rdx, ?DisconnectCallback@@YAJPEAUtagComCallData@@@Z; DisconnectCallback(tagComCallData *)
0x1400374d1  mov     rax, [rax+18h]
0x1400374d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400374da  mov     [rsp+1C8h+arg_10], eax
0x1400374e1  mov     [rsp+1C8h+var_170], eax
0x1400374e5  test    eax, eax
0x1400374e7  jns     short loc_14003755E
0x1400374e9  mov     [rsp+1C8h+var_108], r15
0x1400374f1  mov     [rsp+1C8h+var_100], r12
0x1400374f9  mov     [rsp+1C8h+var_F8], r13
0x140037501  mov     [rsp+1C8h+var_F0], 33Ch
0x14003750c  mov     [rsp+1C8h+var_EC], r14d
0x140037514  mov     [rsp+1C8h+var_E8], 0FFh
0x14003751f  mov     [rsp+1C8h+var_68], 1000000h
0x14003752a  xor     edx, edx; Val
0x14003752c  lea     r8d, [rdx+78h]; Size
0x140037530  lea     rcx, [rsp+1C8h+var_E0]; void *
0x140037538  call    memset_0
0x14003753d  mov     r9d, [rsp+1C8h+arg_10]
0x140037545  lea     r8, aIcontextcallba; "IContextCallback::ContextCallback(Disco"...
0x14003754c  lea     rdx, [rsp+1C8h+var_108]
0x140037554  lea     rcx, [rsp+1C8h+var_178]
0x140037559  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003755e  lea     rcx, [rsi+0D0h]
0x140037565  call    ?Reset@?$CVssSafeComPtr@UIContextCallback@@@@QEAAXXZ; CVssSafeComPtr<IContextCallback>::Reset(void)
0x14003756a  lea     rcx, [rsi+0C0h]
0x140037571  call    ??4?$CComPtr@UIVssHardwareSnapshotProviderEx@@@ATL@@QEAAPEAUIVssHardwareSnapshotProviderEx@@PEAU2@@Z; ATL::CComPtr<IVssHardwareSnapshotProviderEx>::operator=(IVssHardwareSnapshotProviderEx *)
0x140037576  call    ?UnloadInternalProvidersArray@CVssProviderManager@@SAXXZ; CVssProviderManager::UnloadInternalProvidersArray(void)
0x14003757b  call    ?UnloadGlobalProviderItfCache@CVssProviderManager@@SAXXZ; CVssProviderManager::UnloadGlobalProviderItfCache(void)
0x140037580  nop
0x140037581  call    ?DeactivateAll@CVssProviderManager@@SAXXZ; CVssProviderManager::DeactivateAll(void)
0x140037586  nop
0x140037587  jmp     short loc_1400375BC
0x140037589  jmp     short loc_14003758F
0x14003758b  jmp     short loc_14003758F
0x14003758d  jmp     short $+2
0x14003758f  mov     rbx, [rsp+1C8h+arg_8]
0x140037597  mov     rsi, [rsp+1C8h+arg_0]
0x14003759f  mov     r14d, 1
0x1400375a5  xor     edi, edi
0x1400375a7  lea     r13, aCorsvcc; "CORSVCC"
0x1400375ae  lea     r12, aCvsservicemodu_3; "CVsServiceModule::OnStopping"
0x1400375b5  lea     r15, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400375bc  cmp     [rbx], dil
0x1400375bf  jz      short loc_1400375CA
0x1400375c1  call    cs:__imp_CoUninitialize
0x1400375c7  mov     [rbx], dil
0x1400375ca  mov     rcx, [rsi+98h]; hObject
0x1400375d1  call    cs:__imp_CloseHandle
0x1400375d7  test    eax, eax
0x1400375d9  jnz     short loc_140037653
0x1400375db  call    cs:__imp_GetLastError
0x1400375e1  mov     ebx, eax
0x1400375e3  mov     [rsp+1C8h+var_108], r15
0x1400375eb  mov     [rsp+1C8h+var_100], r12
0x1400375f3  mov     [rsp+1C8h+var_F8], r13
0x1400375fb  mov     [rsp+1C8h+var_F0], 35Bh
0x140037606  mov     [rsp+1C8h+var_EC], r14d
0x14003760e  mov     [rsp+1C8h+var_E8], 0FFh
0x140037619  mov     [rsp+1C8h+var_68], 1000000h
0x140037624  xor     edx, edx; Val
0x140037626  lea     r8d, [rdx+78h]; Size
0x14003762a  lea     rcx, [rsp+1C8h+var_E0]; void *
0x140037632  call    memset_0
0x140037637  mov     r9d, ebx
0x14003763a  lea     r8, aErrorClosingTh_1; "Error closing the sub sync event 0x%08l"...
0x140037641  lea     rdx, [rsp+1C8h+var_108]
0x140037649  lea     rcx, [rsp+1C8h+var_178]
0x14003764e  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140037653  call    ?IsServer@CVssSKU@@SAHXZ; CVssSKU::IsServer(void)
0x140037658  test    eax, eax
0x14003765a  jz      short loc_140037690
0x14003765c  cmp     [rsi+0A1h], dil
0x140037663  jz      short loc_140037690
0x140037665  mov     rbx, [rsi+0B0h]
0x14003766c  lea     rdx, [rbx+18h]; void **
0x140037670  mov     rcx, rbx; this
0x140037673  call    ?UnregisterDeviceInterfaceNotification@CVssDeviceNotifier@@AEAAXAEAPEAX@Z; CVssDeviceNotifier::UnregisterDeviceInterfaceNotification(void * &)
0x140037678  lea     rdx, [rbx+10h]; void **
0x14003767c  mov     rcx, rbx; this
0x14003767f  call    ?UnregisterDeviceInterfaceNotification@CVssDeviceNotifier@@AEAAXAEAPEAX@Z; CVssDeviceNotifier::UnregisterDeviceInterfaceNotification(void * &)
0x140037684  lea     rdx, [rbx+8]; void **
0x140037688  mov     rcx, rbx; this
0x14003768b  call    ?UnregisterDeviceInterfaceNotification@CVssDeviceNotifier@@AEAAXAEAPEAX@Z; CVssDeviceNotifier::UnregisterDeviceInterfaceNotification(void * &)
0x140037690  mov     rbx, [rsi+0B0h]
0x140037697  test    rbx, rbx
0x14003769a  jz      short loc_1400376B2
0x14003769c  mov     rcx, rbx; this
0x14003769f  call    ??1CVssDeviceNotifier@@QEAA@XZ; CVssDeviceNotifier::~CVssDeviceNotifier(void)
0x1400376a4  mov     edx, 60h ; '`'
0x1400376a9  mov     rcx, rbx; Block
0x1400376ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400376b1  nop
0x1400376b2  jmp     short loc_1400376BA
0x1400376b4  jmp     short loc_1400376BA
0x1400376b6  jmp     short loc_1400376BA
0x1400376b8  jmp     short $+2
0x1400376ba  lea     rcx, [rsp+1C8h+var_178]; this
0x1400376bf  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400376c4  add     rsp, 190h
0x1400376cb  pop     r15
0x1400376cd  pop     r14
0x1400376cf  pop     r13
0x1400376d1  pop     r12
0x1400376d3  pop     rdi
0x1400376d4  pop     rsi
0x1400376d5  pop     rbx
0x1400376d6  retn
```
