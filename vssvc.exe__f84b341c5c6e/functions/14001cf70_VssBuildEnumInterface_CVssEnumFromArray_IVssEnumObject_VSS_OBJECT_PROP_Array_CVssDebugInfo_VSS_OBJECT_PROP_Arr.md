# VssBuildEnumInterface<CVssEnumFromArray,IVssEnumObject,VSS_OBJECT_PROP_Array>(CVssDebugInfo,VSS_OBJECT_PROP_Array *,IVssEnumObject * *)

- ea: `0x14001cf70`
- end: `0x14001d415`
- name: `??$VssBuildEnumInterface@VCVssEnumFromArray@@UIVssEnumObject@@VVSS_OBJECT_PROP_Array@@@@YAJUCVssDebugInfo@@PEAVVSS_OBJECT_PROP_Array@@PEAPEAUIVssEnumObject@@@Z`
- size: `1189`
- prototype: `_BOOL8 __fastcall(struct CVssDebugInfo *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x14009d7e0`

## callees

- `0x1400088fc`
- `0x1400138e0`
- `0x140013cb0`
- `0x140015e38`
- `0x140019e30`
- `0x14001ca34`
- `0x14001cf70`
- `0x140049ec4`
- `0x14006c8c4`
- `0x14006c8f4`
- `0x1400921dc`
- `0x1400cdfa4`
- `0x1400da314`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d01a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d162`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d01a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d162`
- `VssTrace!__imp_VssTraceMessage` at `0x14001d367`
- `VssTrace!__imp_VssTraceMessage` at `0x14001d367`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d21b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d30c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d21b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d30c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001d051`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001d051`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d270`

## string_xrefs

- `0x14001d383`: `Cannot create enumerator instance. [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_BOOL8 __fastcall VssBuildEnumInterface<CVssEnumFromArray,IVssEnumObject,VSS_OBJECT_PROP_Array>(
        struct CVssDebugInfo *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rcx
  unsigned int v7; // r12d
  unsigned int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  int v13; // ebx
  BOOL v14; // r15d
  __int64 j; // rbx
  DWORD v16; // esi
  __int64 k; // rbx
  void *v18; // rcx
  int v20; // eax
  CVssDebugInfo *v21; // rax
  int v22; // r9d
  CVssDebugInfo *v23; // rax
  int v24; // r9d
  __int64 v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+28h] [rbp-D8h]
  __int64 v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h]
  _DWORD v30[2]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+88h] [rbp-78h]
  const wchar_t *v32; // [rsp+90h] [rbp-70h]
  const wchar_t *v33; // [rsp+98h] [rbp-68h]
  unsigned int v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A4h] [rbp-5Ch]
  const wchar_t *v36; // [rsp+A8h] [rbp-58h]
  unsigned int v37; // [rsp+B0h] [rbp-50h]
  DWORD TickCount; // [rsp+B4h] [rbp-4Ch]
  unsigned int v39; // [rsp+B8h] [rbp-48h]
  LPVOID pv[2]; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64); // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v44; // [rsp+F8h] [rbp-8h] BYREF
  const wchar_t *v45; // [rsp+100h] [rbp+0h]
  const wchar_t *v46; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+110h] [rbp+10h]
  int v48; // [rsp+114h] [rbp+14h]
  int v49; // [rsp+118h] [rbp+18h]
  LPVOID v50[15]; // [rsp+120h] [rbp+20h] BYREF
  int v51; // [rsp+198h] [rbp+98h]
  __int64 v52; // [rsp+1F8h] [rbp+F8h] BYREF

  v44 = L"base\\stor\\vss\\inc\\enum.hxx";
  v45 = L"VssBuildEnumInterface";
  v46 = L"INCENUMH";
  v47 = 210;
  v48 = 11;
  v49 = 255;
  v51 = 0x1000000;
  memset_0(v50, 0, sizeof(v50));
  v31 = 0;
  v36 = L"VssBuildEnumInterface";
  v32 = L"base\\stor\\vss\\inc\\enum.hxx";
  v33 = L"INCENUMH";
  v34 = 210;
  v35 = 11;
  TickCount = GetTickCount();
  v30[1] = -1;
  v39 = 255;
  v30[0] = 0;
  v42 = 0;
  *(_OWORD *)pv = 0;
  v41 = 0;
  v52 = 0;
  if ( (int)VssGetTracingContextPerThread(&v52) >= 0 )
  {
    v20 = VssSetTracingContextPerThread(v30);
    v6 = v42;
    if ( v20 >= 0 )
      v6 = v52;
    v42 = v6;
  }
  else
  {
    v6 = v42;
  }
  if ( v6 )
    v37 = *(_DWORD *)(v6 + 48) + 1;
  else
    v37 = 0;
  v7 = 160;
  v8 = 160;
  if ( v39 != 255 )
    v8 = v39;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v30) )
    VssTraceMessage(v32, v33, v34, v37, v35, v36, L"ENTER", v8, 0);
  if ( HIBYTE(v51) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v10 = v50[i];
      if ( v10 )
      {
        CoTaskMemFree(v10);
        v50[i] = 0;
      }
    }
  }
  v52 = 0;
  v11 = ATL::CComObject<ATL::CComEnumOnSTL<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array,ATL::CComMultiThreadModel>>::CreateInstance(&v52);
  v31 = v11;
  if ( v11 < 0 )
  {
    v21 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)&v44, a1);
    LODWORD(v25) = v22;
    CVssFunctionTracer::Throw(v30, v21, 2147942414LL, L"Cannot create enumerator instance. [0x%08lx]", v25);
  }
  ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v43, v52, v12, (unsigned int)v11);
  v13 = ATL::IEnumOnSTLImpl<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array>::Init(
          v52,
          a2,
          a2);
  v31 = v13;
  if ( v13 < 0 )
  {
    v44 = *(const wchar_t **)a1;
    v46 = (const wchar_t *)*((_QWORD *)a1 + 2);
    v45 = (const wchar_t *)*((_QWORD *)a1 + 1);
    v47 = *((_DWORD *)a1 + 6);
    v48 = *((_DWORD *)a1 + 7);
    LOWORD(v51) = *((_WORD *)a1 + 80);
    BYTE2(v51) = *((_BYTE *)a1 + 162);
    v49 = *((_DWORD *)a1 + 8);
    HIBYTE(v51) = *((_BYTE *)a1 + 163);
    *((_BYTE *)a1 + 163) = 0;
    memcpy_0(v50, (char *)a1 + 40, sizeof(v50));
    LODWORD(v25) = v13;
    CVssFunctionTracer::TranslateGenericError(
      v30,
      &v44,
      (unsigned int)v13,
      L"Cannot initialize enumerator instance. [0x%08lx]",
      v25);
  }
  v31 = (**v43)(v43, &GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3, a3);
  if ( v31 < 0 )
  {
    v23 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)&v44, a1);
    LODWORD(v29) = 0;
    LODWORD(v28) = 57;
    LODWORD(v27) = 138;
    LODWORD(v26) = 4563;
    LODWORD(v25) = 12128;
    CVssFunctionTracer::TranslateComError(
      v30,
      v23,
      L"Error querying the <IEnumInterface> interface with GUID {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}. hr = 0x%08lx",
      2921099536LL,
      v25,
      v26,
      v27,
      v28,
      v29,
      192,
      79,
      114,
      216,
      227,
      v24);
  }
  v14 = *(_DWORD *)(a2 + 16) == 0;
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(&v43);
  for ( j = 0; j != 4; ++j )
  {
    CoTaskMemFree(pv[j]);
    pv[j] = 0;
  }
  v16 = GetTickCount() - TickCount;
  if ( v39 != 255 )
    v7 = v39;
  LODWORD(v29) = v16;
  LODWORD(v28) = v16 % 0x3E8;
  LODWORD(v27) = v16 / 0x3E8 % 0x3C;
  LODWORD(v26) = v16 / 0xEA60 % 0x3C;
  LODWORD(v25) = v16 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v30,
    L"EXIT",
    v7,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v25,
    v26,
    v27,
    v28,
    v29,
    v31);
  VssSetTracingContextPerThread(v42);
  if ( *((_BYTE *)a1 + 163) )
  {
    for ( k = 0; k != 15; ++k )
    {
      v18 = (void *)*((_QWORD *)a1 + k + 5);
      if ( v18 )
      {
        CoTaskMemFree(v18);
        *((_QWORD *)a1 + k + 5) = 0;
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x14001cf70  mov     [rsp-8+arg_8], rbx
0x14001cf75  mov     [rsp-8+arg_0], rcx
0x14001cf7a  push    rbp
0x14001cf7b  push    rsi
0x14001cf7c  push    rdi
0x14001cf7d  push    r12
0x14001cf7f  push    r13
0x14001cf81  push    r14
0x14001cf83  push    r15
0x14001cf85  lea     rbp, [rsp-0A0h]
0x14001cf8d  sub     rsp, 1A0h
0x14001cf94  mov     rsi, r8
0x14001cf97  mov     rdi, rdx
0x14001cf9a  mov     r14, rcx
0x14001cf9d  lea     rax, aBaseStorVssInc_6; "base\\stor\\vss\\inc\\enum.hxx"
0x14001cfa4  mov     [rbp+0D0h+var_D8], rax
0x14001cfa8  lea     rax, aVssbuildenumin; "VssBuildEnumInterface"
0x14001cfaf  mov     [rbp+0D0h+var_D0], rax
0x14001cfb3  lea     rax, aIncenumh; "INCENUMH"
0x14001cfba  mov     [rbp+0D0h+var_C8], rax
0x14001cfbe  mov     [rbp+0D0h+var_C0], 0D2h
0x14001cfc5  mov     [rbp+0D0h+var_BC], 0Bh
0x14001cfcc  mov     r15d, 0FFh
0x14001cfd2  mov     [rbp+0D0h+var_B8], r15d
0x14001cfd6  xor     r13d, r13d
0x14001cfd9  mov     [rbp+0D0h+var_38], 1000000h
0x14001cfe3  xor     edx, edx; Val
0x14001cfe5  lea     r8d, [r13+78h]; Size
0x14001cfe9  lea     rcx, [rbp+0D0h+var_B0]; void *
0x14001cfed  call    memset_0
0x14001cff2  mov     [rbp+0D0h+var_148], r13d
0x14001cff6  mov     rax, [rbp+0D0h+var_D0]
0x14001cffa  mov     [rbp+0D0h+var_128], rax
0x14001cffe  mov     rax, [rbp+0D0h+var_D8]
0x14001d002  mov     [rbp+0D0h+var_140], rax
0x14001d006  mov     rax, [rbp+0D0h+var_C8]
0x14001d00a  mov     [rbp+0D0h+var_138], rax
0x14001d00e  mov     eax, [rbp+0D0h+var_C0]
0x14001d011  mov     [rbp+0D0h+var_130], eax
0x14001d014  mov     eax, [rbp+0D0h+var_BC]
0x14001d017  mov     [rbp+0D0h+var_12C], eax
0x14001d01a  call    cs:__imp_GetTickCount
0x14001d020  mov     [rbp+0D0h+var_11C], eax
0x14001d023  mov     [rbp+0D0h+var_14C], 0FFFFFFFFh
0x14001d02a  mov     eax, [rbp+0D0h+var_B8]
0x14001d02d  mov     [rbp+0D0h+var_118], eax
0x14001d030  mov     [rbp+0D0h+var_150], r13d
0x14001d034  mov     [rbp+0D0h+var_F0], r13
0x14001d038  xorps   xmm0, xmm0
0x14001d03b  movups  xmmword ptr [rbp+0D0h+pv], xmm0
0x14001d03f  movups  [rbp+0D0h+var_100], xmm0
0x14001d043  mov     [rbp+0D0h+arg_18], r13
0x14001d04a  lea     rcx, [rbp+0D0h+arg_18]
0x14001d051  call    cs:__imp_VssGetTracingContextPerThread
0x14001d057  test    eax, eax
0x14001d059  jns     loc_14001D308
0x14001d05f  mov     rcx, [rbp+0D0h+var_F0]
0x14001d063  test    rcx, rcx
0x14001d066  jz      loc_14001D329
0x14001d06c  mov     eax, [rcx+30h]
0x14001d06f  inc     eax
0x14001d071  mov     [rbp+0D0h+var_120], eax
0x14001d074  mov     r12d, 0A0h
0x14001d07a  mov     ebx, r12d
0x14001d07d  cmp     [rbp+0D0h+var_118], r15d
0x14001d081  cmovnz  ebx, [rbp+0D0h+var_118]
0x14001d085  lea     rcx, [rbp+0D0h+var_150]; this
0x14001d089  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14001d08e  test    eax, eax
0x14001d090  jnz     loc_14001D332
0x14001d096  cmp     byte ptr [rbp+0D0h+var_38+3], r13b
0x14001d09d  jz      short loc_14001D0B9
0x14001d09f  mov     rbx, r13
0x14001d0a2  mov     rcx, [rbp+rbx*8+0D0h+var_B0]; pv
0x14001d0a7  test    rcx, rcx
0x14001d0aa  jnz     loc_14001D25F
0x14001d0b0  inc     rbx
0x14001d0b3  cmp     rbx, 0Fh
0x14001d0b7  jnz     short loc_14001D0A2
0x14001d0b9  mov     [rbp+0D0h+arg_18], r13
0x14001d0c0  lea     rcx, [rbp+0D0h+arg_18]
0x14001d0c7  call    ?CreateInstance@?$CComObject@V?$CComEnumOnSTL@UIVssEnumObject@@$1?_GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3@@3U__s_GUID@@BU_VSS_OBJECT_PROP@@VVSS_OBJECT_PROP_Copy@@VVSS_OBJECT_PROP_Array@@VCComMultiThreadModel@ATL@@@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CComEnumOnSTL<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array,ATL::CComMultiThreadModel>>::CreateInstance(ATL::CComObject<ATL::CComEnumOnSTL<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array,ATL::CComMultiThreadModel>> * *)
0x14001d0cc  mov     r9d, eax
0x14001d0cf  mov     [rbp+0D0h+var_148], eax
0x14001d0d2  test    eax, eax
0x14001d0d4  js      loc_14001D372
0x14001d0da  mov     rdx, [rbp+0D0h+arg_18]
0x14001d0e1  lea     rcx, [rbp+0D0h+var_E0]
0x14001d0e5  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x14001d0ea  nop
0x14001d0eb  mov     r8, rdi
0x14001d0ee  mov     rdx, rdi
0x14001d0f1  mov     rcx, [rbp+0D0h+arg_18]
0x14001d0f8  call    ?Init@?$IEnumOnSTLImpl@UIVssEnumObject@@$1?_GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3@@3U__s_GUID@@BU_VSS_OBJECT_PROP@@VVSS_OBJECT_PROP_Copy@@VVSS_OBJECT_PROP_Array@@@ATL@@QEAAJPEAUIUnknown@@AEAVVSS_OBJECT_PROP_Array@@@Z; ATL::IEnumOnSTLImpl<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array>::Init(IUnknown *,VSS_OBJECT_PROP_Array &)
0x14001d0fd  mov     ebx, eax
0x14001d0ff  mov     [rbp+0D0h+var_148], eax
0x14001d102  test    eax, eax
0x14001d104  js      loc_14001D27D
0x14001d10a  mov     rcx, [rbp+0D0h+var_E0]
0x14001d10e  mov     rax, [rcx]
0x14001d111  mov     r8, rsi
0x14001d114  lea     rdx, _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3
0x14001d11b  mov     rax, [rax]
0x14001d11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d123  mov     r9d, eax
0x14001d126  mov     [rbp+0D0h+var_148], eax
0x14001d129  test    eax, eax
0x14001d12b  js      loc_14001D39D
0x14001d131  mov     r15d, r13d
0x14001d134  cmp     [rdi+10h], r13d
0x14001d138  setz    r15b
0x14001d13c  lea     rcx, [rbp+0D0h+var_E0]
0x14001d140  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001d145  nop
0x14001d146  mov     rbx, r13
0x14001d149  mov     rcx, [rbp+rbx*8+0D0h+pv]; pv
0x14001d14e  call    cs:__imp_CoTaskMemFree
0x14001d154  mov     [rbp+rbx*8+0D0h+pv], r13
0x14001d159  inc     rbx
0x14001d15c  cmp     rbx, 4
0x14001d160  jnz     short loc_14001D149
0x14001d162  call    cs:__imp_GetTickCount
0x14001d168  mov     esi, eax
0x14001d16a  sub     esi, [rbp+0D0h+var_11C]
0x14001d16d  mov     eax, 10624DD3h
0x14001d172  mul     esi
0x14001d174  mov     edi, edx
0x14001d176  shr     edi, 6
0x14001d179  mov     r8d, 88888889h
0x14001d17f  mov     eax, r8d
0x14001d182  mul     edi
0x14001d184  shr     edx, 5
0x14001d187  imul    ecx, edx, 3Ch ; '<'
0x14001d18a  mov     ebx, edi
0x14001d18c  sub     ebx, ecx
0x14001d18e  mov     eax, 45E7B273h
0x14001d193  mul     esi
0x14001d195  mov     r11d, edx
0x14001d198  shr     r11d, 0Eh
0x14001d19c  mov     eax, r8d
0x14001d19f  mul     r11d
0x14001d1a2  shr     edx, 5
0x14001d1a5  imul    ecx, edx, 3Ch ; '<'
0x14001d1a8  sub     r11d, ecx
0x14001d1ab  mov     eax, 95217CB1h
0x14001d1b0  mul     esi
0x14001d1b2  mov     r10d, edx
0x14001d1b5  shr     r10d, 15h
0x14001d1b9  mov     eax, r8d
0x14001d1bc  mul     r10d
0x14001d1bf  shr     edx, 5
0x14001d1c2  imul    eax, edx, 3Ch ; '<'
0x14001d1c5  sub     r10d, eax
0x14001d1c8  mov     r9d, [rbp+0D0h+var_148]
0x14001d1cc  cmp     [rbp+0D0h+var_118], 0FFh
0x14001d1d3  cmovnz  r12d, [rbp+0D0h+var_118]
0x14001d1d8  imul    eax, edi, 3E8h
0x14001d1de  mov     ecx, esi
0x14001d1e0  sub     ecx, eax
0x14001d1e2  mov     [rsp+1D0h+var_188], r9d
0x14001d1e7  mov     dword ptr [rsp+1D0h+var_190], esi
0x14001d1eb  mov     dword ptr [rsp+1D0h+var_198], ecx
0x14001d1ef  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x14001d1f3  mov     dword ptr [rsp+1D0h+var_1A8], r11d
0x14001d1f8  mov     dword ptr [rsp+1D0h+var_1B0], r10d
0x14001d1fd  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14001d204  mov     r8d, r12d; unsigned int
0x14001d207  lea     rdx, aExit; "EXIT"
0x14001d20e  lea     rcx, [rbp+0D0h+var_150]; this
0x14001d212  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14001d217  mov     rcx, [rbp+0D0h+var_F0]
0x14001d21b  call    cs:__imp_VssSetTracingContextPerThread
0x14001d221  nop
0x14001d222  cmp     [r14+0A3h], r13b
0x14001d229  jz      short loc_14001D241
0x14001d22b  mov     rbx, r13
0x14001d22e  mov     rcx, [r14+rbx*8+28h]; pv
0x14001d233  test    rcx, rcx
0x14001d236  jnz     short loc_14001D270
0x14001d238  inc     rbx
0x14001d23b  cmp     rbx, 0Fh
0x14001d23f  jnz     short loc_14001D22E
0x14001d241  mov     eax, r15d
0x14001d244  mov     rbx, [rsp+1D0h+arg_8]
0x14001d24c  add     rsp, 1A0h
0x14001d253  pop     r15
0x14001d255  pop     r14
0x14001d257  pop     r13
0x14001d259  pop     r12
0x14001d25b  pop     rdi
0x14001d25c  pop     rsi
0x14001d25d  pop     rbp
0x14001d25e  retn
0x14001d25f  call    cs:__imp_CoTaskMemFree
0x14001d265  nop
0x14001d266  mov     [rbp+rbx*8+0D0h+var_B0], r13
0x14001d26b  jmp     loc_14001D0B0
0x14001d270  call    cs:__imp_CoTaskMemFree
0x14001d276  mov     [r14+rbx*8+28h], r13
0x14001d27b  jmp     short loc_14001D238
0x14001d27d  mov     rcx, [r14]
0x14001d280  mov     [rbp+0D0h+var_D8], rcx
0x14001d284  mov     rcx, [r14+10h]
0x14001d288  mov     [rbp+0D0h+var_C8], rcx
0x14001d28c  mov     rcx, [r14+8]
0x14001d290  mov     [rbp+0D0h+var_D0], rcx
0x14001d294  mov     ecx, [r14+18h]
0x14001d298  mov     [rbp+0D0h+var_C0], ecx
0x14001d29b  mov     eax, [r14+1Ch]
0x14001d29f  mov     [rbp+0D0h+var_BC], eax
0x14001d2a2  movzx   eax, word ptr [r14+0A0h]
0x14001d2aa  mov     word ptr [rbp+0D0h+var_38], ax
0x14001d2b1  mov     al, [r14+0A2h]
0x14001d2b8  mov     byte ptr [rbp+0D0h+var_38+2], al
0x14001d2be  mov     eax, [r14+20h]
0x14001d2c2  mov     [rbp+0D0h+var_B8], eax
0x14001d2c5  mov     al, [r14+0A3h]
0x14001d2cc  mov     byte ptr [rbp+0D0h+var_38+3], al
0x14001d2d2  mov     [r14+0A3h], r13b
0x14001d2d9  lea     rdx, [r14+28h]; Src
0x14001d2dd  mov     r8d, 78h ; 'x'; Size
0x14001d2e3  lea     rcx, [rbp+0D0h+var_B0]; void *
0x14001d2e7  call    memcpy_0
0x14001d2ec  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x14001d2f0  lea     r9, aCannotInitiali_0; "Cannot initialize enumerator instance. "...
0x14001d2f7  mov     r8d, ebx
0x14001d2fa  lea     rdx, [rbp+0D0h+var_D8]
0x14001d2fe  lea     rcx, [rbp+0D0h+var_150]
0x14001d302  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001d308  lea     rcx, [rbp+0D0h+var_150]
0x14001d30c  call    cs:__imp_VssSetTracingContextPerThread
0x14001d312  mov     rcx, [rbp+0D0h+var_F0]
0x14001d316  test    eax, eax
0x14001d318  cmovns  rcx, [rbp+0D0h+arg_18]
0x14001d320  mov     [rbp+0D0h+var_F0], rcx
0x14001d324  jmp     loc_14001D063
0x14001d329  mov     [rbp+0D0h+var_120], r13d
0x14001d32d  jmp     loc_14001D074
0x14001d332  mov     [rsp+1D0h+var_190], r13
0x14001d337  mov     dword ptr [rsp+1D0h+var_198], ebx
0x14001d33b  lea     rax, aEnter; "ENTER"
0x14001d342  mov     [rsp+1D0h+var_1A0], rax
0x14001d347  mov     rax, [rbp+0D0h+var_128]
0x14001d34b  mov     [rsp+1D0h+var_1A8], rax
0x14001d350  mov     eax, [rbp+0D0h+var_12C]
0x14001d353  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14001d357  mov     r9d, [rbp+0D0h+var_120]
0x14001d35b  mov     r8d, [rbp+0D0h+var_130]
0x14001d35f  mov     rdx, [rbp+0D0h+var_138]
0x14001d363  mov     rcx, [rbp+0D0h+var_140]
0x14001d367  call    cs:__imp_VssTraceMessage
0x14001d36d  jmp     loc_14001D096
0x14001d372  mov     rdx, r14; struct CVssDebugInfo *
0x14001d375  lea     rcx, [rbp+0D0h+var_D8]; this
0x14001d379  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14001d37e  mov     dword ptr [rsp+1D0h+var_1B0], r9d
0x14001d383  lea     r9, aCannotCreateEn; "Cannot create enumerator instance. [0x%"...
0x14001d38a  mov     r8d, 8007000Eh
0x14001d390  mov     rdx, rax
0x14001d393  lea     rcx, [rbp+0D0h+var_150]
0x14001d397  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14001d39d  mov     rdx, r14; struct CVssDebugInfo *
0x14001d3a0  lea     rcx, [rbp+0D0h+var_D8]; this
0x14001d3a4  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14001d3a9  mov     [rsp+1D0h+var_160], r9d
0x14001d3ae  mov     [rsp+1D0h+var_168], 0E3h
0x14001d3b6  mov     [rsp+1D0h+var_170], 0D8h
0x14001d3be  mov     [rsp+1D0h+var_178], 72h ; 'r'
0x14001d3c6  mov     [rsp+1D0h+var_180], 4Fh ; 'O'
0x14001d3ce  mov     [rsp+1D0h+var_188], 0C0h
0x14001d3d6  mov     dword ptr [rsp+1D0h+var_190], r13d
0x14001d3db  mov     dword ptr [rsp+1D0h+var_198], 39h ; '9'
0x14001d3e3  mov     dword ptr [rsp+1D0h+var_1A0], 8Ah
0x14001d3eb  mov     dword ptr [rsp+1D0h+var_1A8], 11D3h
0x14001d3f3  mov     dword ptr [rsp+1D0h+var_1B0], 2F60h
0x14001d3fb  mov     r9d, 0AE1C7110h
0x14001d401  lea     r8, aErrorQueryingT; "Error querying the <IEnumInterface> int"...
0x14001d408  mov     rdx, rax
0x14001d40b  lea     rcx, [rbp+0D0h+var_150]
0x14001d40f  call    ?TranslateComError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateComError(CVssDebugInfo,ushort const *,...)
```
