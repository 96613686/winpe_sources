# CVsServiceModule::_WinMain(HINSTANCE__ *,ushort *)

- ea: `0x140033780`
- end: `0x140033e16`
- name: `?_WinMain@CVsServiceModule@@QEAAHPEAUHINSTANCE__@@PEAG@Z`
- size: `1686`
- prototype: `__int64 __fastcall(CVsServiceModule *this, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003374c`

## callees

- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140033780`
- `0x140033e1c`
- `0x140091560`
- `0x1400921dc`
- `0x140095a18`
- `0x140096544`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140033d61`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140033d61`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003393b`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14003393b`
- `ntdll!EtwUnregisterTraceGuids` at `0x140033acd`
- `ntdll!EtwUnregisterTraceGuids` at `0x140033acd`
- `ntdll!EtwRegisterTraceGuidsW` at `0x1400339c8`
- `ntdll!EtwRegisterTraceGuidsW` at `0x1400339c8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400339d6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400339d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140033860`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140033b45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140033860`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140033b45`
- `VssTrace!__imp_VssTraceMessage` at `0x140033cc1`
- `VssTrace!__imp_VssTraceMessage` at `0x140033cc1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140033c10`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140033c54`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140033c10`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140033c54`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400338b4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400338b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033c3c`

## string_xrefs

- `0x1400337b8`: `CVsServiceModule::_WinMain`
- `0x140033a42`: `Trace: VSS command-line: '%s'`
- `0x140033d28`: `Current token = '%s'`
- `0x140033dda`: `Run-time registration of service no longer supported.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVsServiceModule::_WinMain(CVsServiceModule *this, __int64 a2, unsigned __int16 *a3)
{
  __int64 v4; // rax
  unsigned int v5; // r15d
  unsigned int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  __int64 *v9; // rbx
  __int64 *v10; // rsi
  __int64 v11; // r8
  const WCHAR *CommandLineW; // rbx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v13; // rdx
  ATL::CComModule *v14; // rcx
  HINSTANCE v15; // r8
  const struct _GUID *v16; // r9
  const unsigned __int16 *j; // rax
  CVsServiceModule *v18; // rcx
  const WCHAR *v19; // rbx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v20; // rbx
  unsigned int v21; // r14d
  DWORD v22; // esi
  PCNZWCH lpString2; // [rsp+20h] [rbp-1B8h]
  int cchCount2[2]; // [rsp+28h] [rbp-1B0h]
  __int64 v26; // [rsp+30h] [rbp-1A8h]
  __int64 v27; // [rsp+38h] [rbp-1A0h]
  __int64 v28; // [rsp+40h] [rbp-198h]
  _DWORD v29[2]; // [rsp+50h] [rbp-188h] BYREF
  int v30; // [rsp+58h] [rbp-180h]
  const unsigned __int16 *v31; // [rsp+60h] [rbp-178h]
  const unsigned __int16 *v32; // [rsp+68h] [rbp-170h]
  unsigned int v33; // [rsp+70h] [rbp-168h]
  unsigned int v34; // [rsp+74h] [rbp-164h]
  const unsigned __int16 *v35; // [rsp+78h] [rbp-160h]
  unsigned int v36; // [rsp+80h] [rbp-158h]
  DWORD TickCount; // [rsp+84h] [rbp-154h]
  unsigned int v38; // [rsp+88h] [rbp-150h]
  LPVOID pv[2]; // [rsp+90h] [rbp-148h]
  LPVOID v40[2]; // [rsp+A0h] [rbp-138h]
  __int64 v41; // [rsp+B0h] [rbp-128h]
  _QWORD v42[2]; // [rsp+C0h] [rbp-118h] BYREF
  const unsigned __int16 *v43; // [rsp+D0h] [rbp-108h] BYREF
  const unsigned __int16 *v44; // [rsp+D8h] [rbp-100h]
  const unsigned __int16 *v45; // [rsp+E0h] [rbp-F8h]
  int v46; // [rsp+E8h] [rbp-F0h]
  int v47; // [rsp+ECh] [rbp-ECh]
  int v48; // [rsp+F0h] [rbp-E8h]
  LPVOID v49[2]; // [rsp+F8h] [rbp-E0h] BYREF
  __int128 v50; // [rsp+108h] [rbp-D0h]
  __int128 v51; // [rsp+118h] [rbp-C0h]
  __int128 v52; // [rsp+128h] [rbp-B0h]
  __int128 v53; // [rsp+138h] [rbp-A0h]
  __int128 v54; // [rsp+148h] [rbp-90h]
  __int128 v55; // [rsp+158h] [rbp-80h]
  __int64 v56; // [rsp+168h] [rbp-70h]
  int v57; // [rsp+170h] [rbp-68h]
  int v58; // [rsp+178h] [rbp-60h] BYREF
  _com_error *v59; // [rsp+180h] [rbp-58h] BYREF
  const std::exception *v60; // [rsp+188h] [rbp-50h] BYREF
  WCHAR v61[4]; // [rsp+190h] [rbp-48h] BYREF

  v43 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v44 = L"CVsServiceModule::_WinMain";
  v45 = L"CORSVCC";
  v46 = 1029;
  v47 = 1;
  v48 = 255;
  v57 = 0x1000000;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v30 = 0;
  v35 = L"CVsServiceModule::_WinMain";
  v31 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v32 = L"CORSVCC";
  v33 = 1029;
  v34 = 1;
  TickCount = GetTickCount();
  v29[1] = -1;
  v38 = 255;
  v29[0] = 0;
  v41 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v40 = 0;
  *(_QWORD *)v61 = 0;
  if ( (int)VssGetTracingContextPerThread(v61) < 0 || (int)VssSetTracingContextPerThread(v29) < 0 )
  {
    v4 = v41;
  }
  else
  {
    v4 = *(_QWORD *)v61;
    v41 = *(_QWORD *)v61;
  }
  if ( v4 )
    v36 = *(_DWORD *)(v4 + 48) + 1;
  else
    v36 = 0;
  v5 = 160;
  v6 = 160;
  if ( v38 != 255 )
    v6 = v38;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v29, v34) )
    VssTraceMessage(v31, v32, v33, v36, v34, v35, L"ENTER", v6, 0);
  for ( i = 0; i != 15; ++i )
  {
    v8 = v49[i];
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v49[i] = 0;
    }
  }
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  qword_14014F7F0 = 0;
  WPP_MAIN_CB = 0;
  qword_14014F7F8 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ControlGuid;
  v9 = &WPP_MAIN_CB;
  WPP_GLOBAL_Control = (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_MAIN_CB;
  v10 = &WPP_REGISTRATION_GUIDS;
  do
  {
    v11 = *v10++;
    v42[0] = v11;
    v42[1] = 0;
    v9[4] = v11;
    EtwRegisterTraceGuidsW(WppControlCallback, v9, v11, 1, v42, 0, 0, v9 + 1);
    v9 = (__int64 *)*v9;
  }
  while ( v9 );
  CommandLineW = GetCommandLineW();
  v43 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v44 = L"CVsServiceModule::_WinMain";
  v45 = L"CORSVCC";
  v46 = 1039;
  v47 = 1;
  v48 = 255;
  v57 = 0x1000000;
  memset_0(v49, 0, 0x78u);
  CVssFunctionTracer::Trace(v29, &v43, L"Trace: VSS command-line: '%s'", CommandLineW);
  ATL::CComModule::Init(v14, v13, v15, v16);
  qword_14014F9D8 = a2;
  wcscpy(v61, L"-/");
  for ( j = ATL::CAtlModule::FindOneOf(CommandLineW, v61); ; j = ATL::CAtlModule::FindOneOf(v19, v61) )
  {
    v19 = j;
    if ( !j )
      break;
    v43 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
    v44 = L"CVsServiceModule::_WinMain";
    v45 = L"CORSVCC";
    v46 = 1052;
    v47 = 1;
    v48 = 255;
    v57 = 0x1000000;
    memset_0(v49, 0, 0x78u);
    CVssFunctionTracer::Trace(v29, &v43, L"Current token = '%s'", v19);
    if ( CompareStringW(0x7Fu, 1u, v19, -1, L"Register", -1) == 2 )
    {
      v43 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
      v44 = L"CVsServiceModule::_WinMain";
      v45 = L"CORSVCC";
      v46 = 1057;
      v47 = 1;
      v48 = 255;
      v57 = 0x1000000;
      memset_0(v49, 0, 0x78u);
      CVssFunctionTracer::Trace(v29, &v43, L"Run-time registration of service no longer supported.");
      HIDWORD(xmmword_14014F990) = 50;
      goto LABEL_18;
    }
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    CVsServiceModule::StartDispatcher(v18);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v58) )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)v29,
        v58,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::_WinMain",
        0x42Eu,
        v34);
      v5 = 160;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_140033E02);
      goto LABEL_18;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v59) )
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)v29,
        v59,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::_WinMain",
        0x42Eu,
        v34);
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)v29,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::_WinMain",
        0x42Eu,
        v34);
      v5 = 160;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140033E06);
      goto LABEL_18;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v60) )
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)v29,
        v60,
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::_WinMain",
        0x42Eu,
        v34);
  }
LABEL_18:
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control )
  {
    if ( WPP_GLOBAL_Control )
    {
      do
      {
        if ( *(_QWORD *)&v20->Mbr.Signature )
        {
          EtwUnregisterTraceGuids();
          *(_QWORD *)&v20->Mbr.Signature = 0;
        }
        v20 = *(struct _DRIVE_LAYOUT_INFORMATION_EX **)&v20->PartitionStyle;
      }
      while ( v20 );
    }
    WPP_GLOBAL_Control = (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control;
  }
  v21 = HIDWORD(xmmword_14014F990);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v40[0]);
  v40[0] = 0;
  CoTaskMemFree(v40[1]);
  v40[1] = 0;
  v22 = GetTickCount() - TickCount;
  if ( v38 != 255 )
    v5 = v38;
  LODWORD(v28) = v22;
  LODWORD(v27) = v22 % 0x3E8;
  LODWORD(v26) = v22 / 0x3E8 % 0x3C;
  cchCount2[0] = v22 / 0xEA60 % 0x3C;
  LODWORD(lpString2) = v22 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v29,
    L"EXIT",
    v5,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    lpString2,
    *(_QWORD *)cchCount2,
    v26,
    v27,
    v28,
    v30);
  VssSetTracingContextPerThread(v41);
  return v21;
}

```

## disassembly

```asm
0x140033780  mov     r11, rsp
0x140033783  push    rbx
0x140033784  push    rsi
0x140033785  push    rdi
0x140033786  push    r12
0x140033788  push    r13
0x14003378a  push    r14
0x14003378c  push    r15
0x14003378e  sub     rsp, 1A0h
0x140033795  mov     rax, cs:__security_cookie
0x14003379c  xor     rax, rsp
0x14003379f  mov     [rsp+1D8h+var_40], rax
0x1400337a7  mov     r14, rdx
0x1400337aa  lea     r12, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400337b1  mov     [r11-108h], r12
0x1400337b8  lea     r13, aCvsservicemodu_2; "CVsServiceModule::_WinMain"
0x1400337bf  mov     [r11-100h], r13
0x1400337c6  lea     rcx, aCorsvcc; "CORSVCC"
0x1400337cd  mov     [r11-0F8h], rcx
0x1400337d4  mov     [rsp+1D8h+var_F0], 405h
0x1400337df  mov     [rsp+1D8h+var_EC], 1
0x1400337ea  mov     [rsp+1D8h+var_E8], 0FFh
0x1400337f5  xor     edi, edi
0x1400337f7  mov     dword ptr [r11-68h], 1000000h
0x1400337ff  xorps   xmm0, xmm0
0x140033802  xor     eax, eax
0x140033804  movups  xmmword ptr [rsp+1D8h+var_E0], xmm0
0x14003380c  movups  [rsp+1D8h+var_D0], xmm0
0x140033814  movups  [rsp+1D8h+var_C0], xmm0
0x14003381c  movups  [rsp+1D8h+var_B0], xmm0
0x140033824  movups  [rsp+1D8h+var_A0], xmm0
0x14003382c  movups  [rsp+1D8h+var_90], xmm0
0x140033834  movups  xmmword ptr [r11-80h], xmm0
0x140033839  mov     [r11-70h], rax
0x14003383d  mov     [rsp+1D8h+var_180], edi
0x140033841  mov     [rsp+1D8h+var_160], r13
0x140033846  mov     [rsp+1D8h+var_178], r12
0x14003384b  mov     [rsp+1D8h+var_170], rcx
0x140033850  mov     [rsp+1D8h+var_168], 405h
0x140033858  mov     [rsp+1D8h+var_164], 1
0x140033860  call    cs:__imp_GetTickCount
0x140033866  mov     [rsp+1D8h+var_154], eax
0x14003386d  mov     [rsp+1D8h+var_184], 0FFFFFFFFh
0x140033875  mov     [rsp+1D8h+var_150], 0FFh
0x140033880  mov     [rsp+1D8h+var_188], edi
0x140033884  mov     [rsp+1D8h+var_128], rdi
0x14003388c  xorps   xmm0, xmm0
0x14003388f  movdqa  xmmword ptr [rsp+1D8h+pv], xmm0
0x140033898  xorps   xmm1, xmm1
0x14003389b  movdqa  xmmword ptr [rsp+1D8h+var_138], xmm1
0x1400338a4  mov     qword ptr [rsp+1D8h+var_48], rdi
0x1400338ac  lea     rcx, [rsp+1D8h+var_48]
0x1400338b4  call    cs:__imp_VssGetTracingContextPerThread
0x1400338ba  test    eax, eax
0x1400338bc  jns     loc_140033C4F
0x1400338c2  mov     rax, [rsp+1D8h+var_128]
0x1400338ca  test    rax, rax
0x1400338cd  jz      loc_140033C77
0x1400338d3  mov     eax, [rax+30h]
0x1400338d6  inc     eax
0x1400338d8  mov     [rsp+1D8h+var_158], eax
0x1400338df  mov     r15d, 0A0h
0x1400338e5  mov     ebx, r15d
0x1400338e8  cmp     [rsp+1D8h+var_150], 0FFh
0x1400338f3  cmovnz  ebx, [rsp+1D8h+var_150]
0x1400338fb  mov     edx, [rsp+1D8h+var_164]; unsigned int
0x1400338ff  lea     rcx, [rsp+1D8h+var_188]; this
0x140033904  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140033909  test    eax, eax
0x14003390b  jnz     loc_140033C83
0x140033911  mov     rbx, rdi
0x140033914  mov     rcx, [rsp+rbx*8+1D8h+var_E0]; pv
0x14003391c  test    rcx, rcx
0x14003391f  jnz     loc_140033C3C
0x140033925  inc     rbx
0x140033928  cmp     rbx, 0Fh
0x14003392c  jnz     short loc_140033914
0x14003392e  xor     r9d, r9d; HeapInformationLength
0x140033931  xor     r8d, r8d; HeapInformation
0x140033934  mov     edx, 1; HeapInformationClass
0x140033939  xor     ecx, ecx; HeapHandle
0x14003393b  call    cs:__imp_HeapSetInformation
0x140033941  mov     cs:qword_14014F7F0, rdi
0x140033948  mov     cs:WPP_MAIN_CB, rdi
0x14003394f  mov     cs:qword_14014F7F8, 1
0x14003395a  lea     rax, WPP_ThisDir_CTLGUID_ControlGuid
0x140033961  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140033968  lea     rbx, WPP_MAIN_CB
0x14003396f  mov     cs:WPP_GLOBAL_Control, rbx
0x140033976  lea     rsi, WPP_REGISTRATION_GUIDS
0x14003397d  mov     r8, [rsi]
0x140033980  lea     rsi, [rsi+8]
0x140033984  mov     [rsp+1D8h+var_118], r8
0x14003398c  mov     [rsp+1D8h+var_110], rdi
0x140033994  mov     [rbx+20h], r8
0x140033998  lea     rax, [rbx+8]
0x14003399c  mov     [rsp+1D8h+var_1A0], rax
0x1400339a1  mov     [rsp+1D8h+var_1A8], rdi
0x1400339a6  mov     qword ptr [rsp+1D8h+cchCount2], rdi
0x1400339ab  lea     rax, [rsp+1D8h+var_118]
0x1400339b3  mov     [rsp+1D8h+lpString2], rax
0x1400339b8  mov     r9d, 1
0x1400339be  mov     rdx, rbx
0x1400339c1  lea     rcx, WppControlCallback
0x1400339c8  call    cs:__imp_EtwRegisterTraceGuidsW
0x1400339ce  mov     rbx, [rbx]
0x1400339d1  test    rbx, rbx
0x1400339d4  jnz     short loc_14003397D
0x1400339d6  call    cs:__imp_GetCommandLineW
0x1400339dc  mov     rbx, rax
0x1400339df  mov     [rsp+1D8h+var_108], r12
0x1400339e7  mov     [rsp+1D8h+var_100], r13
0x1400339ef  lea     rsi, aCorsvcc; "CORSVCC"
0x1400339f6  mov     [rsp+1D8h+var_F8], rsi
0x1400339fe  mov     [rsp+1D8h+var_F0], 40Fh
0x140033a09  mov     [rsp+1D8h+var_EC], 1
0x140033a14  mov     [rsp+1D8h+var_E8], 0FFh
0x140033a1f  mov     [rsp+1D8h+var_68], 1000000h
0x140033a2a  xor     edx, edx; Val
0x140033a2c  mov     r8d, 78h ; 'x'; Size
0x140033a32  lea     rcx, [rsp+1D8h+var_E0]; void *
0x140033a3a  call    memset_0
0x140033a3f  mov     r9, rbx
0x140033a42  lea     r8, aTraceVssComman; "Trace: VSS command-line: '%s'"
0x140033a49  lea     rdx, [rsp+1D8h+var_108]
0x140033a51  lea     rcx, [rsp+1D8h+var_188]
0x140033a56  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140033a5b  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x140033a60  mov     cs:qword_14014F9D8, r14
0x140033a67  mov     eax, dword ptr cs:asc_1401079EC; "-/"
0x140033a6d  mov     dword ptr [rsp+1D8h+var_48], eax
0x140033a74  movzx   eax, word ptr cs:asc_1401079EC+4; ""
0x140033a7b  mov     [rsp+1D8h+var_48+4], ax
0x140033a83  lea     rdx, [rsp+1D8h+var_48]; LPCWSTR
0x140033a8b  mov     rcx, rbx; lpsz
0x140033a8e  call    ?FindOneOf@CAtlModule@ATL@@SAPEBGPEBG0@Z; ATL::CAtlModule::FindOneOf(ushort const *,ushort const *)
0x140033a93  lea     r14, String2; "Register"
0x140033a9a  mov     rbx, rax
0x140033a9d  test    rax, rax
0x140033aa0  jnz     loc_140033CCC
0x140033aa6  call    ?StartDispatcher@CVsServiceModule@@IEAAXXZ; CVsServiceModule::StartDispatcher(void)
0x140033aab  nop
0x140033aac  lea     rsi, WPP_GLOBAL_Control
0x140033ab3  mov     rbx, cs:WPP_GLOBAL_Control
0x140033aba  cmp     rbx, rsi
0x140033abd  jz      short loc_140033AE6
0x140033abf  test    rbx, rbx
0x140033ac2  jz      short loc_140033ADF
0x140033ac4  mov     rcx, [rbx+8]
0x140033ac8  test    rcx, rcx
0x140033acb  jz      short loc_140033AD7
0x140033acd  call    cs:__imp_EtwUnregisterTraceGuids
0x140033ad3  mov     [rbx+8], rdi
0x140033ad7  mov     rbx, [rbx]
0x140033ada  test    rbx, rbx
0x140033add  jnz     short loc_140033AC4
0x140033adf  mov     cs:WPP_GLOBAL_Control, rsi
0x140033ae6  mov     r14d, dword ptr cs:xmmword_14014F990+0Ch
0x140033aed  mov     rcx, [rsp+1D8h+pv]; pv
0x140033af5  call    cs:__imp_CoTaskMemFree
0x140033afb  mov     [rsp+1D8h+pv], rdi
0x140033b03  mov     rcx, [rsp+1D8h+pv+8]; pv
0x140033b0b  call    cs:__imp_CoTaskMemFree
0x140033b11  mov     [rsp+1D8h+pv+8], rdi
0x140033b19  mov     rcx, [rsp+1D8h+var_138]; pv
0x140033b21  call    cs:__imp_CoTaskMemFree
0x140033b27  mov     [rsp+1D8h+var_138], rdi
0x140033b2f  mov     rcx, [rsp+1D8h+var_138+8]; pv
0x140033b37  call    cs:__imp_CoTaskMemFree
0x140033b3d  mov     [rsp+1D8h+var_138+8], rdi
0x140033b45  call    cs:__imp_GetTickCount
0x140033b4b  mov     esi, eax
0x140033b4d  sub     esi, [rsp+1D8h+var_154]
0x140033b54  mov     eax, 10624DD3h
0x140033b59  mul     esi
0x140033b5b  mov     edi, edx
0x140033b5d  shr     edi, 6
0x140033b60  mov     eax, 88888889h
0x140033b65  mul     edi
0x140033b67  shr     edx, 5
0x140033b6a  imul    ecx, edx, 3Ch ; '<'
0x140033b6d  mov     ebx, edi
0x140033b6f  sub     ebx, ecx
0x140033b71  mov     eax, 45E7B273h
0x140033b76  mul     esi
0x140033b78  mov     r11d, edx
0x140033b7b  shr     r11d, 0Eh
0x140033b7f  mov     eax, 88888889h
0x140033b84  mul     r11d
0x140033b87  shr     edx, 5
0x140033b8a  imul    ecx, edx, 3Ch ; '<'
0x140033b8d  sub     r11d, ecx
0x140033b90  mov     eax, 95217CB1h
0x140033b95  mul     esi
0x140033b97  mov     r10d, edx
0x140033b9a  shr     r10d, 15h
0x140033b9e  mov     eax, 88888889h
0x140033ba3  mul     r10d
0x140033ba6  shr     edx, 5
0x140033ba9  imul    eax, edx, 3Ch ; '<'
0x140033bac  sub     r10d, eax
0x140033baf  mov     r9d, [rsp+1D8h+var_180]
0x140033bb4  cmp     [rsp+1D8h+var_150], 0FFh
0x140033bbf  cmovnz  r15d, [rsp+1D8h+var_150]
0x140033bc8  imul    ecx, edi, 3E8h
0x140033bce  mov     edx, esi
0x140033bd0  sub     edx, ecx
0x140033bd2  mov     [rsp+1D8h+var_190], r9d
0x140033bd7  mov     dword ptr [rsp+1D8h+var_198], esi
0x140033bdb  mov     dword ptr [rsp+1D8h+var_1A0], edx
0x140033bdf  mov     dword ptr [rsp+1D8h+var_1A8], ebx
0x140033be3  mov     [rsp+1D8h+cchCount2], r11d
0x140033be8  mov     dword ptr [rsp+1D8h+lpString2], r10d
0x140033bed  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140033bf4  mov     r8d, r15d; unsigned int
0x140033bf7  lea     rdx, aExit; "EXIT"
0x140033bfe  lea     rcx, [rsp+1D8h+var_188]; this
0x140033c03  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140033c08  mov     rcx, [rsp+1D8h+var_128]
0x140033c10  call    cs:__imp_VssSetTracingContextPerThread
0x140033c16  mov     eax, r14d
0x140033c19  mov     rcx, [rsp+1D8h+var_40]
0x140033c21  xor     rcx, rsp; StackCookie
0x140033c24  call    __security_check_cookie
0x140033c29  add     rsp, 1A0h
0x140033c30  pop     r15
0x140033c32  pop     r14
0x140033c34  pop     r13
0x140033c36  pop     r12
0x140033c38  pop     rdi
0x140033c39  pop     rsi
0x140033c3a  pop     rbx
0x140033c3b  retn
0x140033c3c  call    cs:__imp_CoTaskMemFree
0x140033c42  mov     [rsp+rbx*8+1D8h+var_E0], rdi
0x140033c4a  jmp     loc_140033925
0x140033c4f  lea     rcx, [rsp+1D8h+var_188]
0x140033c54  call    cs:__imp_VssSetTracingContextPerThread
0x140033c5a  test    eax, eax
0x140033c5c  js      loc_1400338C2
0x140033c62  mov     rax, qword ptr [rsp+1D8h+var_48]
0x140033c6a  mov     [rsp+1D8h+var_128], rax
0x140033c72  jmp     loc_1400338CA
0x140033c77  mov     [rsp+1D8h+var_158], edi
0x140033c7e  jmp     loc_1400338DF
0x140033c83  mov     [rsp+1D8h+var_198], rdi
0x140033c88  mov     dword ptr [rsp+1D8h+var_1A0], ebx
0x140033c8c  lea     rax, aEnter; "ENTER"
0x140033c93  mov     [rsp+1D8h+var_1A8], rax
0x140033c98  mov     rax, [rsp+1D8h+var_160]
0x140033c9d  mov     qword ptr [rsp+1D8h+cchCount2], rax
0x140033ca2  mov     eax, [rsp+1D8h+var_164]
0x140033ca6  mov     dword ptr [rsp+1D8h+lpString2], eax
0x140033caa  mov     r9d, [rsp+1D8h+var_158]
0x140033cb2  mov     r8d, [rsp+1D8h+var_168]
0x140033cb7  mov     rdx, [rsp+1D8h+var_170]
0x140033cbc  mov     rcx, [rsp+1D8h+var_178]
0x140033cc1  call    cs:__imp_VssTraceMessage
0x140033cc7  jmp     loc_140033911
0x140033ccc  mov     [rsp+1D8h+var_108], r12
0x140033cd4  mov     [rsp+1D8h+var_100], r13
0x140033cdc  mov     [rsp+1D8h+var_F8], rsi
0x140033ce4  mov     [rsp+1D8h+var_F0], 41Ch
0x140033cef  mov     [rsp+1D8h+var_EC], 1
0x140033cfa  mov     [rsp+1D8h+var_E8], 0FFh
0x140033d05  mov     [rsp+1D8h+var_68], 1000000h
0x140033d10  xor     edx, edx; Val
0x140033d12  mov     r8d, 78h ; 'x'; Size
0x140033d18  lea     rcx, [rsp+1D8h+var_E0]; void *
0x140033d20  call    memset_0
0x140033d25  mov     r9, rbx
0x140033d28  lea     r8, aCurrentTokenS; "Current token = '%s'"
0x140033d2f  lea     rdx, [rsp+1D8h+var_108]
0x140033d37  lea     rcx, [rsp+1D8h+var_188]
0x140033d3c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140033d41  mov     [rsp+1D8h+cchCount2], 0FFFFFFFFh; cchCount2
0x140033d49  mov     [rsp+1D8h+lpString2], r14; lpString2
0x140033d4e  mov     r9d, 0FFFFFFFFh; cchCount1
0x140033d54  mov     r8, rbx; lpString1
0x140033d57  mov     edx, 1; dwCmpFlags
0x140033d5c  mov     ecx, 7Fh; Locale
0x140033d61  call    cs:__imp_CompareStringW
0x140033d67  cmp     eax, 2
0x140033d6a  jz      short loc_140033D81
0x140033d6c  lea     rdx, [rsp+1D8h+var_48]; LPCWSTR
0x140033d74  mov     rcx, rbx; lpsz
0x140033d77  call    ?FindOneOf@CAtlModule@ATL@@SAPEBGPEBG0@Z; ATL::CAtlModule::FindOneOf(ushort const *,ushort const *)
0x140033d7c  jmp     loc_140033A9A
0x140033d81  mov     [rsp+1D8h+var_108], r12
0x140033d89  mov     [rsp+1D8h+var_100], r13
0x140033d91  mov     [rsp+1D8h+var_F8], rsi
0x140033d99  mov     [rsp+1D8h+var_F0], 421h
0x140033da4  mov     [rsp+1D8h+var_EC], 1
0x140033daf  mov     [rsp+1D8h+var_E8], 0FFh
0x140033dba  mov     [rsp+1D8h+var_68], 1000000h
0x140033dc5  xor     edx, edx; Val
0x140033dc7  mov     r8d, 78h ; 'x'; Size
0x140033dcd  lea     rcx, [rsp+1D8h+var_E0]; void *
0x140033dd5  call    memset_0
0x140033dda  lea     r8, aRunTimeRegistr; "Run-time registration of service no lon"...
  ... truncated ...
```
