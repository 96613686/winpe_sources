# _VssCreatorClass<CVssCoordinator,&__s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140034940`
- end: `0x140034efc`
- name: `?CreateInstance@?$_VssCreatorClass@VCVssCoordinator@@$1?_GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623@@3U__s_GUID@@B@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `1468`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140034940`
- `0x1400443e4`
- `0x1400921dc`
- `0x1400955e0`
- `0x1400965c0`
- `0x140096640`
- `0x1400ce824`
- `0x1400da308`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400349ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140034c4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400349ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140034c4e`
- `VssTrace!__imp_VssTraceMessage` at `0x140034e41`
- `VssTrace!__imp_VssTraceMessage` at `0x140034e41`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140034d09`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140034d3d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140034d09`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140034d3d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140034a2b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140034a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034d28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034d28`

## string_xrefs

- `0x140034970`: `_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance`
- `0x140034aa2`: `_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance`
- `0x140034d83`: `_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance`
- `0x140034e89`: `_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance`
- `0x140034bf9`: `Warning: Somebody tried to create a remote coordinator object and Remote Snapshots are not allowed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _VssCreatorClass<CVssCoordinator,&__s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v6; // rax
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  __int64 v11; // rcx
  DWORD v12; // esi
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int Instance; // eax
  CVsServiceModule *v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+78h] [rbp-88h]
  const wchar_t *v32; // [rsp+80h] [rbp-80h]
  const wchar_t *v33; // [rsp+88h] [rbp-78h]
  unsigned int v34; // [rsp+90h] [rbp-70h]
  unsigned int v35; // [rsp+94h] [rbp-6Ch]
  const wchar_t *v36; // [rsp+98h] [rbp-68h]
  unsigned int v37; // [rsp+A0h] [rbp-60h]
  DWORD TickCount; // [rsp+A4h] [rbp-5Ch]
  unsigned int v39; // [rsp+A8h] [rbp-58h]
  LPVOID pv[2]; // [rsp+B0h] [rbp-50h]
  LPVOID v41[2]; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  const wchar_t *v43; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v44; // [rsp+E8h] [rbp-18h]
  const wchar_t *v45; // [rsp+F0h] [rbp-10h]
  int v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+FCh] [rbp-4h]
  int v48; // [rsp+100h] [rbp+0h]
  LPVOID v49[2]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v50; // [rsp+118h] [rbp+18h]
  __int128 v51; // [rsp+128h] [rbp+28h]
  __int128 v52; // [rsp+138h] [rbp+38h]
  __int128 v53; // [rsp+148h] [rbp+48h]
  __int128 v54; // [rsp+158h] [rbp+58h]
  __int128 v55; // [rsp+168h] [rbp+68h]
  __int64 v56; // [rsp+178h] [rbp+78h]
  int v57; // [rsp+180h] [rbp+80h]
  __int64 v58; // [rsp+1F8h] [rbp+F8h] BYREF

  v43 = L"base\\stor\\vss\\modules\\coord\\inc\\svc.hxx";
  v44 = L"_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance";
  v45 = L"CORSVCH";
  v46 = 225;
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
  v31 = 0;
  v36 = L"_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance";
  v32 = L"base\\stor\\vss\\modules\\coord\\inc\\svc.hxx";
  v33 = L"CORSVCH";
  v34 = 225;
  v35 = 1;
  TickCount = GetTickCount();
  v39 = 255;
  v30 = 0xFFFFFFFF00000000uLL;
  v42 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v41 = 0;
  v58 = 0;
  if ( (int)VssGetTracingContextPerThread(&v58) < 0 || (int)VssSetTracingContextPerThread(&v30) < 0 )
  {
    v6 = v42;
  }
  else
  {
    v6 = v58;
    v42 = v58;
  }
  if ( v6 )
    v37 = *(_DWORD *)(v6 + 48) + 1;
  else
    v37 = 0;
  v7 = 160;
  v8 = 160;
  if ( v39 != 255 )
    v8 = v39;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v30, v35) )
    VssTraceMessage(v32, v33, v34, v37, v35, v36, L"ENTER", v8, 0);
  for ( i = 0; i != 15; ++i )
  {
    v10 = v49[i];
    if ( v10 )
    {
      CoTaskMemFree(v10);
      v49[i] = 0;
    }
  }
  v43 = L"base\\stor\\vss\\modules\\coord\\inc\\svc.hxx";
  v44 = L"_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance";
  v45 = L"CORSVCH";
  v46 = 227;
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
  LODWORD(v27) = 222;
  LODWORD(v25) = 217;
  LODWORD(v23) = 190;
  LODWORD(v21) = 17588;
  LODWORD(v19) = 7364;
  CVssFunctionTracer::Trace(
    &v30,
    &v43,
    L"Creating an instance with class ID {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
    3849956191LL,
    v19,
    v21,
    v23,
    v25,
    v27,
    9,
    145,
    255,
    6,
    35);
  if ( !CVssSKU::ms_bInitialized )
    CVssSKU::Initialize();
  if ( (CVssSKU::ms_eSKU == 1 || !IsApresEnabled())
    && !memcmp_0(&GUID_95243a62_2f9b_4fdf_b437_40d965f6d17f, &GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623, 0x10u) )
  {
    v43 = L"base\\stor\\vss\\modules\\coord\\inc\\svc.hxx";
    v44 = L"_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance";
    v45 = L"CORSVCH";
    v46 = 234;
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
    CVssFunctionTracer::Trace(
      &v30,
      &v43,
      L"Warning: Somebody tried to create a remote coordinator object and Remote Snapshots are not allowed");
    v31 = -2147467262;
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v41[0]);
    v41[0] = 0;
    CoTaskMemFree(v41[1]);
    v41[1] = 0;
    v12 = GetTickCount() - TickCount;
    if ( v39 != 255 )
      v7 = v39;
    LODWORD(v29) = v31;
    LODWORD(v28) = v12;
    LODWORD(v26) = v12 % 0x3E8;
    LODWORD(v24) = v12 / 0x3E8 % 0x3C;
    LODWORD(v22) = v12 / 0xEA60 % 0x3C;
    LODWORD(v20) = v12 / 0x36EE80 % 0x3C;
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v30,
      L"EXIT",
      v7,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      v20,
      v22,
      v24,
      v26,
      v28,
      v29);
    VssSetTracingContextPerThread(v42);
    return 2147500034LL;
  }
  else
  {
    if ( a1 )
      Instance = ATL::CComCreator<ATL::CComAggObject<CVssCoordinator>>::CreateInstance(a1, a2, a3);
    else
      Instance = ATL::CComCreator<ATL::CComObject<CVssCoordinator>>::CreateInstance(v11, a2, a3);
    v14 = Instance;
    v31 = Instance;
    if ( Instance < 0 )
    {
      v43 = L"base\\stor\\vss\\modules\\coord\\inc\\svc.hxx";
      v44 = L"_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance";
      v45 = L"CORSVCH";
      v46 = 245;
      v47 = 1;
      v48 = 255;
      v57 = 0x1000000;
      memset_0(v49, 0, 0x78u);
      CVssFunctionTracer::Trace(&v30, &v43, L"Error while creating the coordinator object [0x%08lx]", v14);
    }
    else if ( CVsServiceModule::IsDuringShutdown(v17) )
    {
      v43 = L"base\\stor\\vss\\modules\\coord\\inc\\svc.hxx";
      v44 = L"_VssCreatorClass<class CVssCoordinator,&struct __s_GUID const _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623>::CreateInstance";
      v45 = L"CORSVCH";
      v46 = 252;
      v47 = 1;
      v48 = 255;
      v57 = 0x1000000;
      memset_0(v49, 0, 0x78u);
      CVssFunctionTracer::Trace(&v30, &v43, L"Warning: Shutdown started while while creating the coordinator object.");
      v15 = *a3;
      *a3 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v31 = -2146959352;
      CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v30);
      return 2148007944LL;
    }
    v18 = v31;
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v30);
    return v18;
  }
}

```

## disassembly

```asm
0x140034940  push    rbp
0x140034942  push    rbx
0x140034943  push    rsi
0x140034944  push    rdi
0x140034945  push    r12
0x140034947  push    r13
0x140034949  push    r14
0x14003494b  push    r15
0x14003494d  lea     rbp, [rsp-98h]
0x140034955  sub     rsp, 198h
0x14003495c  mov     rdi, r8
0x14003495f  mov     r15, rdx
0x140034962  mov     rsi, rcx
0x140034965  lea     rcx, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\coord\\inc\\s"...
0x14003496c  mov     [rbp+0D0h+var_F0], rcx
0x140034970  lea     rdx, aVsscreatorclas_0; "_VssCreatorClass<class CVssCoordinator,"...
0x140034977  mov     [rbp+0D0h+var_E8], rdx
0x14003497b  lea     r8, aCorsvch; "CORSVCH"
0x140034982  mov     [rbp+0D0h+var_E0], r8
0x140034986  mov     [rbp+0D0h+var_D8], 0E1h
0x14003498d  mov     [rbp+0D0h+var_D4], 1
0x140034994  mov     [rbp+0D0h+var_D0], 0FFh
0x14003499b  xor     r12d, r12d
0x14003499e  mov     [rbp+0D0h+var_50], 1000000h
0x1400349a8  xorps   xmm0, xmm0
0x1400349ab  xor     eax, eax
0x1400349ad  movups  xmmword ptr [rbp+0D0h+var_C8], xmm0
0x1400349b1  movups  [rbp+0D0h+var_B8], xmm0
0x1400349b5  movups  [rbp+0D0h+var_A8], xmm0
0x1400349b9  movups  [rbp+0D0h+var_98], xmm0
0x1400349bd  movups  [rbp+0D0h+var_88], xmm0
0x1400349c1  movups  [rbp+0D0h+var_78], xmm0
0x1400349c5  movups  [rbp+0D0h+var_68], xmm0
0x1400349c9  mov     [rbp+0D0h+var_58], rax
0x1400349cd  mov     [rsp+1D0h+var_158], r12d
0x1400349d2  mov     [rbp+0D0h+var_138], rdx
0x1400349d6  mov     [rbp+0D0h+var_150], rcx
0x1400349da  mov     [rbp+0D0h+var_148], r8
0x1400349de  mov     [rbp+0D0h+var_140], 0E1h
0x1400349e5  mov     [rbp+0D0h+var_13C], 1
0x1400349ec  call    cs:__imp_GetTickCount
0x1400349f2  mov     [rbp+0D0h+var_12C], eax
0x1400349f5  mov     [rsp+1D0h+var_15C], 0FFFFFFFFh
0x1400349fd  mov     [rbp+0D0h+var_128], 0FFh
0x140034a04  mov     [rsp+1D0h+var_160], r12d
0x140034a09  mov     [rbp+0D0h+var_100], r12
0x140034a0d  xorps   xmm0, xmm0
0x140034a10  movdqa  xmmword ptr [rbp+0D0h+pv], xmm0
0x140034a15  xorps   xmm1, xmm1
0x140034a18  movdqa  xmmword ptr [rbp+0D0h+var_110], xmm1
0x140034a1d  mov     [rbp+0D0h+arg_18], r12
0x140034a24  lea     rcx, [rbp+0D0h+arg_18]
0x140034a2b  call    cs:__imp_VssGetTracingContextPerThread
0x140034a31  test    eax, eax
0x140034a33  jns     loc_140034D38
0x140034a39  mov     rax, [rbp+0D0h+var_100]
0x140034a3d  test    rax, rax
0x140034a40  jz      loc_140034D5B
0x140034a46  mov     eax, [rax+30h]
0x140034a49  inc     eax
0x140034a4b  mov     [rbp+0D0h+var_130], eax
0x140034a4e  mov     r14d, 0A0h
0x140034a54  mov     ebx, r14d
0x140034a57  cmp     [rbp+0D0h+var_128], 0FFh
0x140034a5e  cmovnz  ebx, [rbp+0D0h+var_128]
0x140034a62  mov     edx, [rbp+0D0h+var_13C]; unsigned int
0x140034a65  lea     rcx, [rsp+1D0h+var_160]; this
0x140034a6a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140034a6f  test    eax, eax
0x140034a71  jnz     loc_140034E0C
0x140034a77  mov     rbx, r12
0x140034a7a  nop     word ptr [rax+rax+00h]
0x140034a80  mov     rcx, [rbp+rbx*8+0D0h+var_C8]; pv
0x140034a85  test    rcx, rcx
0x140034a88  jnz     loc_140034D28
0x140034a8e  inc     rbx
0x140034a91  cmp     rbx, 0Fh
0x140034a95  jnz     short loc_140034A80
0x140034a97  lea     r13, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\coord\\inc\\s"...
0x140034a9e  mov     [rbp+0D0h+var_F0], r13
0x140034aa2  lea     rbx, aVsscreatorclas_0; "_VssCreatorClass<class CVssCoordinator,"...
0x140034aa9  mov     [rbp+0D0h+var_E8], rbx
0x140034aad  lea     rax, aCorsvch; "CORSVCH"
0x140034ab4  mov     [rbp+0D0h+var_E0], rax
0x140034ab8  mov     [rbp+0D0h+var_D8], 0E3h
0x140034abf  mov     [rbp+0D0h+var_D4], 1
0x140034ac6  mov     [rbp+0D0h+var_D0], 0FFh
0x140034acd  mov     [rbp+0D0h+var_50], 1000000h
0x140034ad7  xorps   xmm0, xmm0
0x140034ada  xor     eax, eax
0x140034adc  movups  xmmword ptr [rbp+0D0h+var_C8], xmm0
0x140034ae0  movups  [rbp+0D0h+var_B8], xmm0
0x140034ae4  movups  [rbp+0D0h+var_A8], xmm0
0x140034ae8  movups  [rbp+0D0h+var_98], xmm0
0x140034aec  movups  [rbp+0D0h+var_88], xmm0
0x140034af0  movups  [rbp+0D0h+var_78], xmm0
0x140034af4  movups  [rbp+0D0h+var_68], xmm0
0x140034af8  mov     [rbp+0D0h+var_58], rax
0x140034afc  mov     [rsp+1D0h+var_168], 23h ; '#'
0x140034b04  mov     [rsp+1D0h+var_170], 6
0x140034b0c  mov     [rsp+1D0h+var_178], 0FFh
0x140034b14  mov     [rsp+1D0h+var_180], 91h
0x140034b1c  mov     dword ptr [rsp+1D0h+var_188], 9
0x140034b24  mov     dword ptr [rsp+1D0h+var_190], 0DEh
0x140034b2c  mov     dword ptr [rsp+1D0h+var_198], 0D9h
0x140034b34  mov     dword ptr [rsp+1D0h+var_1A0], 0BEh
0x140034b3c  mov     dword ptr [rsp+1D0h+var_1A8], 44B4h
0x140034b44  mov     dword ptr [rsp+1D0h+var_1B0], 1CC4h
0x140034b4c  mov     r9d, 0E579AB5Fh
0x140034b52  lea     r8, aCreatingAnInst; "Creating an instance with class ID {%.8"...
0x140034b59  lea     rdx, [rbp+0D0h+var_F0]
0x140034b5d  lea     rcx, [rsp+1D0h+var_160]
0x140034b62  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140034b67  cmp     cs:?ms_bInitialized@CVssSKU@@0HA, 0; int CVssSKU::ms_bInitialized
0x140034b6e  jz      loc_140034E4C
0x140034b74  cmp     cs:?ms_eSKU@CVssSKU@@0W4EVssSKUType@1@A, 1; CVssSKU::EVssSKUType CVssSKU::ms_eSKU
0x140034b7b  jnz     loc_140034E56
0x140034b81  mov     r8d, 10h; Size
0x140034b87  lea     rdx, _GUID_e579ab5f_1cc4_44b4_bed9_de0991ff0623; Buf2
0x140034b8e  lea     rcx, _GUID_95243a62_2f9b_4fdf_b437_40d965f6d17f; Buf1
0x140034b95  call    memcmp_0
0x140034b9a  test    eax, eax
0x140034b9c  jnz     loc_140034E63
0x140034ba2  mov     [rbp+0D0h+var_F0], r13
0x140034ba6  mov     [rbp+0D0h+var_E8], rbx
0x140034baa  lea     rax, aCorsvch; "CORSVCH"
0x140034bb1  mov     [rbp+0D0h+var_E0], rax
0x140034bb5  mov     [rbp+0D0h+var_D8], 0EAh
0x140034bbc  mov     [rbp+0D0h+var_D4], 1
0x140034bc3  mov     [rbp+0D0h+var_D0], 0FFh
0x140034bca  mov     [rbp+0D0h+var_50], 1000000h
0x140034bd4  xorps   xmm0, xmm0
0x140034bd7  xor     eax, eax
0x140034bd9  movups  xmmword ptr [rbp+0D0h+var_C8], xmm0
0x140034bdd  movups  [rbp+0D0h+var_B8], xmm0
0x140034be1  movups  [rbp+0D0h+var_A8], xmm0
0x140034be5  movups  [rbp+0D0h+var_98], xmm0
0x140034be9  movups  [rbp+0D0h+var_88], xmm0
0x140034bed  movups  [rbp+0D0h+var_78], xmm0
0x140034bf1  movups  [rbp+0D0h+var_68], xmm0
0x140034bf5  mov     [rbp+0D0h+var_58], rax
0x140034bf9  lea     r8, aWarningSomebod; "Warning: Somebody tried to create a rem"...
0x140034c00  lea     rdx, [rbp+0D0h+var_F0]
0x140034c04  lea     rcx, [rsp+1D0h+var_160]
0x140034c09  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140034c0e  mov     [rsp+1D0h+var_158], 80004002h
0x140034c16  mov     rcx, [rbp+0D0h+pv]; pv
0x140034c1a  call    cs:__imp_CoTaskMemFree
0x140034c20  mov     [rbp+0D0h+pv], r12
0x140034c24  mov     rcx, [rbp+0D0h+pv+8]; pv
0x140034c28  call    cs:__imp_CoTaskMemFree
0x140034c2e  mov     [rbp+0D0h+pv+8], r12
0x140034c32  mov     rcx, [rbp+0D0h+var_110]; pv
0x140034c36  call    cs:__imp_CoTaskMemFree
0x140034c3c  mov     [rbp+0D0h+var_110], r12
0x140034c40  mov     rcx, [rbp+0D0h+var_110+8]; pv
0x140034c44  call    cs:__imp_CoTaskMemFree
0x140034c4a  mov     [rbp+0D0h+var_110+8], r12
0x140034c4e  call    cs:__imp_GetTickCount
0x140034c54  mov     esi, eax
0x140034c56  sub     esi, [rbp+0D0h+var_12C]
0x140034c59  mov     eax, 10624DD3h
0x140034c5e  mul     esi
0x140034c60  mov     edi, edx
0x140034c62  shr     edi, 6
0x140034c65  mov     eax, 88888889h
0x140034c6a  mul     edi
0x140034c6c  shr     edx, 5
0x140034c6f  imul    ecx, edx, 3Ch ; '<'
0x140034c72  mov     ebx, edi
0x140034c74  sub     ebx, ecx
0x140034c76  mov     eax, 45E7B273h
0x140034c7b  mul     esi
0x140034c7d  mov     r11d, edx
0x140034c80  shr     r11d, 0Eh
0x140034c84  mov     eax, 88888889h
0x140034c89  mul     r11d
0x140034c8c  shr     edx, 5
0x140034c8f  imul    ecx, edx, 3Ch ; '<'
0x140034c92  sub     r11d, ecx
0x140034c95  mov     eax, 95217CB1h
0x140034c9a  mul     esi
0x140034c9c  mov     r10d, edx
0x140034c9f  shr     r10d, 15h
0x140034ca3  mov     eax, 88888889h
0x140034ca8  mul     r10d
0x140034cab  shr     edx, 5
0x140034cae  imul    eax, edx, 3Ch ; '<'
0x140034cb1  sub     r10d, eax
0x140034cb4  mov     r9d, [rsp+1D0h+var_158]
0x140034cb9  cmp     [rbp+0D0h+var_128], 0FFh
0x140034cc0  cmovnz  r14d, [rbp+0D0h+var_128]
0x140034cc5  imul    ecx, edi, 3E8h
0x140034ccb  mov     edx, esi
0x140034ccd  sub     edx, ecx
0x140034ccf  mov     dword ptr [rsp+1D0h+var_188], r9d
0x140034cd4  mov     dword ptr [rsp+1D0h+var_190], esi
0x140034cd8  mov     dword ptr [rsp+1D0h+var_198], edx
0x140034cdc  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x140034ce0  mov     dword ptr [rsp+1D0h+var_1A8], r11d
0x140034ce5  mov     dword ptr [rsp+1D0h+var_1B0], r10d
0x140034cea  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140034cf1  mov     r8d, r14d; unsigned int
0x140034cf4  lea     rdx, aExit; "EXIT"
0x140034cfb  lea     rcx, [rsp+1D0h+var_160]; this
0x140034d00  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140034d05  mov     rcx, [rbp+0D0h+var_100]
0x140034d09  call    cs:__imp_VssSetTracingContextPerThread
0x140034d0f  mov     eax, 80004002h
0x140034d14  add     rsp, 198h
0x140034d1b  pop     r15
0x140034d1d  pop     r14
0x140034d1f  pop     r13
0x140034d21  pop     r12
0x140034d23  pop     rdi
0x140034d24  pop     rsi
0x140034d25  pop     rbx
0x140034d26  pop     rbp
0x140034d27  retn
0x140034d28  call    cs:__imp_CoTaskMemFree
0x140034d2e  mov     [rbp+rbx*8+0D0h+var_C8], r12
0x140034d33  jmp     loc_140034A8E
0x140034d38  lea     rcx, [rsp+1D0h+var_160]
0x140034d3d  call    cs:__imp_VssSetTracingContextPerThread
0x140034d43  test    eax, eax
0x140034d45  js      loc_140034A39
0x140034d4b  mov     rax, [rbp+0D0h+arg_18]
0x140034d52  mov     [rbp+0D0h+var_100], rax
0x140034d56  jmp     loc_140034A3D
0x140034d5b  mov     [rbp+0D0h+var_130], r12d
0x140034d5f  jmp     loc_140034A4E
0x140034d64  mov     ebx, eax
0x140034d66  mov     [rsp+1D0h+var_158], eax
0x140034d6a  test    eax, eax
0x140034d6c  js      loc_140034E85
0x140034d72  call    ?IsDuringShutdown@CVsServiceModule@@QEBA_NXZ; CVsServiceModule::IsDuringShutdown(void)
0x140034d77  test    al, al
0x140034d79  jz      loc_140034EE7
0x140034d7f  mov     [rbp+0D0h+var_F0], r13
0x140034d83  lea     rax, aVsscreatorclas_0; "_VssCreatorClass<class CVssCoordinator,"...
0x140034d8a  mov     [rbp+0D0h+var_E8], rax
0x140034d8e  lea     rax, aCorsvch; "CORSVCH"
0x140034d95  mov     [rbp+0D0h+var_E0], rax
0x140034d99  mov     [rbp+0D0h+var_D8], 0FCh
0x140034da0  mov     [rbp+0D0h+var_D4], 1
0x140034da7  mov     [rbp+0D0h+var_D0], 0FFh
0x140034dae  mov     [rbp+0D0h+var_50], 1000000h
0x140034db8  xor     edx, edx; Val
0x140034dba  mov     r8d, 78h ; 'x'; Size
0x140034dc0  lea     rcx, [rbp+0D0h+var_C8]; void *
0x140034dc4  call    memset_0
0x140034dc9  lea     r8, aWarningShutdow; "Warning: Shutdown started while while c"...
0x140034dd0  lea     rdx, [rbp+0D0h+var_F0]
0x140034dd4  lea     rcx, [rsp+1D0h+var_160]
0x140034dd9  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140034dde  mov     rcx, [rdi]
0x140034de1  mov     [rdi], r12
0x140034de4  mov     rax, [rcx]
0x140034de7  mov     rax, [rax+10h]
0x140034deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034df0  mov     [rsp+1D0h+var_158], 80080008h
0x140034df8  lea     rcx, [rsp+1D0h+var_160]; this
0x140034dfd  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140034e02  mov     eax, 80080008h
0x140034e07  jmp     loc_140034D14
0x140034e0c  mov     [rsp+1D0h+var_190], r12
0x140034e11  mov     dword ptr [rsp+1D0h+var_198], ebx
0x140034e15  lea     rax, aEnter; "ENTER"
0x140034e1c  mov     [rsp+1D0h+var_1A0], rax
0x140034e21  mov     rax, [rbp+0D0h+var_138]
0x140034e25  mov     [rsp+1D0h+var_1A8], rax
0x140034e2a  mov     eax, [rbp+0D0h+var_13C]
0x140034e2d  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140034e31  mov     r9d, [rbp+0D0h+var_130]
0x140034e35  mov     r8d, [rbp+0D0h+var_140]
0x140034e39  mov     rdx, [rbp+0D0h+var_148]
0x140034e3d  mov     rcx, [rbp+0D0h+var_150]
0x140034e41  call    cs:__imp_VssTraceMessage
0x140034e47  jmp     loc_140034A77
0x140034e4c  call    ?Initialize@CVssSKU@@CAXXZ; CVssSKU::Initialize(void)
0x140034e51  jmp     loc_140034B74
0x140034e56  call    ?IsApresEnabled@@YA_NXZ; IsApresEnabled(void)
0x140034e5b  test    al, al
0x140034e5d  jz      loc_140034B81
0x140034e63  mov     r8, rdi
0x140034e66  mov     rdx, r15
0x140034e69  test    rsi, rsi
0x140034e6c  jnz     short loc_140034E78
0x140034e6e  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCVssCoordinator@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CVssCoordinator>>::CreateInstance(void *,_GUID const &,void * *)
0x140034e73  jmp     loc_140034D64
0x140034e78  mov     rcx, rsi
0x140034e7b  call    ?CreateInstance@?$CComCreator@V?$CComAggObject@VCVssCoordinator@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CVssCoordinator>>::CreateInstance(void *,_GUID const &,void * *)
0x140034e80  jmp     loc_140034D64
0x140034e85  mov     [rbp+0D0h+var_F0], r13
0x140034e89  lea     rax, aVsscreatorclas_0; "_VssCreatorClass<class CVssCoordinator,"...
0x140034e90  mov     [rbp+0D0h+var_E8], rax
0x140034e94  lea     rax, aCorsvch; "CORSVCH"
0x140034e9b  mov     [rbp+0D0h+var_E0], rax
0x140034e9f  mov     [rbp+0D0h+var_D8], 0F5h
0x140034ea6  mov     [rbp+0D0h+var_D4], 1
  ... truncated ...
```
