# CVssSoftwareProviderWrapper::CreateInstance(_GUID,_GUID)

- ea: `0x1400281a0`
- end: `0x14002884f`
- name: `?CreateInstance@CVssSoftwareProviderWrapper@@SAPEAUIVssSnapshotProvider@@U_GUID@@0@Z`
- size: `1711`
- prototype: `struct IVssSnapshotProvider *__fastcall(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001818c`

## callees

- `0x140006020`
- `0x1400088fc`
- `0x140010170`
- `0x1400137c0`
- `0x140013c60`
- `0x140015e38`
- `0x140027cb0`
- `0x1400281a0`
- `0x140028858`
- `0x140028888`
- `0x1400328ac`
- `0x140032fcc`
- `0x1400330fc`
- `0x14003c160`
- `0x140042acc`
- `0x140049ec4`
- `0x14006cc2c`
- `0x140091560`
- `0x14009197c`
- `0x1400921dc`
- `0x1400943b4`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140028259`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140028259`
- `VssTrace!__imp_VssTraceMessage` at `0x1400285ec`
- `VssTrace!__imp_VssTraceMessage` at `0x1400285ec`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002858f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002858f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002829a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002829a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028573`

## string_xrefs

- `0x1400281ea`: `CVssSoftwareProviderWrapper::CreateInstance`
- `0x140028434`: `CVssSoftwareProviderWrapper::CreateInstance`
- `0x1400285fc`: `CVssSoftwareProviderWrapper::CreateInstance`
- `0x140028760`: `CoCreateInstance failed with hr = 0x%08lx`
- `0x1400287c6`: `QI for IVssProviderCreateSnapshotSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct IVssSnapshotProvider *__fastcall CVssSoftwareProviderWrapper::CreateInstance(struct _GUID *a1, struct _GUID *a2)
{
  _QWORD *v4; // rax
  int v5; // ebx
  __int64 i; // rbx
  void *v7; // rcx
  signed int v8; // ebx
  _QWORD *v9; // rbx
  bool v10; // al
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  signed int v13; // eax
  __int64 v14; // rbx
  struct CVssDebugInfo *v16; // rax
  CVssDebugInfo *v17; // rax
  DWORD v18; // ebx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h]
  _QWORD *v25; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v26; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v27; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+94h] [rbp-6Ch]
  int v31; // [rsp+98h] [rbp-68h]
  LPVOID pv[15]; // [rsp+A0h] [rbp-60h] BYREF
  int v33; // [rsp+118h] [rbp+18h]
  GUID v34; // [rsp+120h] [rbp+20h] BYREF
  __int128 v35; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v36; // [rsp+140h] [rbp+40h] BYREF
  DWORD dwMessageId; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v38; // [rsp+150h] [rbp+50h]
  const unsigned __int16 *v39; // [rsp+158h] [rbp+58h]
  unsigned int v40; // [rsp+160h] [rbp+60h]
  unsigned int v41; // [rsp+164h] [rbp+64h]
  const wchar_t *v42; // [rsp+168h] [rbp+68h]
  unsigned int v43; // [rsp+170h] [rbp+70h]
  DWORD TickCount; // [rsp+174h] [rbp+74h]
  int v45; // [rsp+178h] [rbp+78h]
  __int128 v46; // [rsp+180h] [rbp+80h]
  __int128 v47; // [rsp+190h] [rbp+90h]
  _QWORD *v48; // [rsp+1A0h] [rbp+A0h]
  char v49[168]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v50[168]; // [rsp+258h] [rbp+158h] BYREF
  unsigned __int16 v51[80]; // [rsp+300h] [rbp+200h] BYREF

  v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
  v28 = L"CORSOFTC";
  v29 = 62;
  v30 = 1;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  dwMessageId = 0;
  v42 = L"CVssSoftwareProviderWrapper::CreateInstance";
  v38 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v39 = L"CORSOFTC";
  v40 = 62;
  v41 = 1;
  TickCount = GetTickCount();
  v45 = 255;
  v36 = 0xFFFFFFFF00000000uLL;
  v48 = 0;
  v46 = 0;
  v47 = 0;
  v25 = 0;
  if ( (int)VssGetTracingContextPerThread(&v25) < 0 || (int)VssSetTracingContextPerThread(&v36) < 0 )
  {
    v4 = v48;
  }
  else
  {
    v4 = v25;
    v48 = v25;
  }
  if ( v4 )
    v43 = *((_DWORD *)v4 + 12) + 1;
  else
    v43 = 0;
  v5 = 160;
  if ( v45 != 255 )
    v5 = v45;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v36, v41) )
    VssTraceMessage(v38, v39, v40, v43, v41, v42, L"ENTER", v5, 0);
  if ( HIBYTE(v33) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v7 = pv[i];
      if ( v7 )
      {
        CoTaskMemFree(v7);
        pv[i] = 0;
      }
    }
  }
  LODWORD(v24) = a1->Data4[2];
  LODWORD(v23) = a1->Data4[1];
  LODWORD(v22) = a1->Data4[0];
  LODWORD(v21) = a1->Data3;
  LODWORD(v19) = a1->Data2;
  v8 = StringCchPrintfW(
         v51,
         0x50u,
         L"SwProvider_{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
         a1->Data1,
         v19,
         v21,
         v22,
         v23,
         v24,
         a1->Data4[3],
         a1->Data4[4],
         a1->Data4[5],
         a1->Data4[6],
         a1->Data4[7]);
  dwMessageId = v8;
  if ( v8 < 0 )
  {
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
    v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
    v28 = L"CORSOFTC";
    v29 = 68;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateGenericError(&v36, &v26, (unsigned int)v8, L"StringCchPrintfW()");
  }
  v9 = operator new(0x378u, (const struct std::nothrow_t *)&std::nothrow);
  v25 = v9;
  if ( v9 )
  {
    *v9 = &CVssSoftwareProviderWrapper::`vftable';
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v9 + 1);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v9 + 2);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v9 + 3);
    *((_DWORD *)v9 + 8) = 0;
    v9[8] = 0;
    v9[7] = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v9[6] = 0;
    *((_DWORD *)v9 + 11) = 1;
    *((_DWORD *)v9 + 10) = 131103;
    *((_BYTE *)v9 + 72) = 0;
    *((_DWORD *)v9 + 220) = 0;
    CVssDiag::Initialize((CVssDiag *)(v9 + 5), v51);
  }
  else
  {
    v9 = 0;
  }
  ATL::CComPtr<CVssSoftwareProviderWrapper>::CComPtr<CVssSoftwareProviderWrapper>(&v25, (__int64)v9);
  v10 = ATL::CComPtrBase<IVssHardwareSnapshotProvider>::operator==(&v25);
  v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
  v30 = 1;
  v31 = 255;
  v33 = 0x1000000;
  v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
  v28 = L"CORSOFTC";
  if ( v10 )
  {
    v29 = 73;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::Throw(&v36, &v26, 2147942414LL, L"Memory allocation error");
  }
  v11 = v25;
  v12 = v25 + 1;
  v29 = 77;
  memset_0(pv, 0, sizeof(pv));
  v34 = GUID_609e123e_2c5a_44d3_8f01_0b1d9a47d1ff;
  v35 = (__int128)*a2;
  CVssFunctionTracer::CoCreateInstanceWithLog(&v36, &v26, &v35, L"SW_PROV", 4, &v34, v12);
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
    v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
    v28 = L"CORSOFTC";
    v29 = 84;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v35 = (__int128)*a2;
    v16 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v26, (CVssDebugInfo *)v50);
    v17 = CVssDebugInfo::operator<<(v16, (CVssDebugInfo *)v49, dwMessageId);
    CVssFunctionTracer::LogError((__int64)&v36, 0x3004u, (__int64)v17, 1u);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v50);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v26);
    v18 = dwMessageId;
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
    v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
    v28 = L"CORSOFTC";
    v29 = 85;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(v20) = v18;
    CVssFunctionTracer::Throw(&v36, &v26, 2147754767LL, L"CoCreateInstance failed with hr = 0x%08lx", v20);
  }
  dwMessageId = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v12)(
                  *v12,
                  &GUID_5f894e5b_1e39_4778_8e23_9abad9f0e08c,
                  (__int64)(v11 + 2));
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
    v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
    v28 = L"CORSOFTC";
    v29 = 92;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v35 = (__int128)*a1;
    CVssFunctionTracer::TranslateProviderError(&v36, &v26, &v35, L"QI for IVssProviderCreateSnapshotSet");
  }
  v13 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v12)(
          *v12,
          &GUID_e561901f_03a5_4afe_86d0_72baeece7004,
          (__int64)(v11 + 3));
  dwMessageId = v13;
  if ( v13 < 0 && v13 != -2147467262 )
  {
    v26 = L"base\\stor\\vss\\modules\\coord\\src\\softwrp.cxx";
    v27 = L"CVssSoftwareProviderWrapper::CreateInstance";
    v28 = L"CORSOFTC";
    v29 = 103;
    v30 = 1;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v35 = (__int128)*a1;
    CVssFunctionTracer::TranslateProviderError(&v36, &v26, &v35, L"QI for IVssProviderNotifications");
  }
  v14 = ATL::CComPtrBase<IVssSnapshotDescription>::Detach(&v25);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v25);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v36);
  return (struct IVssSnapshotProvider *)v14;
}

```

## disassembly

```asm
0x1400281a0  mov     [rsp-8+arg_10], rbx
0x1400281a5  push    rbp
0x1400281a6  push    rsi
0x1400281a7  push    rdi
0x1400281a8  push    r12
0x1400281aa  push    r13
0x1400281ac  push    r14
0x1400281ae  push    r15
0x1400281b0  lea     rbp, [rsp-2C0h]
0x1400281b8  sub     rsp, 3C0h
0x1400281bf  movaps  [rsp+3F0h+var_40], xmm6
0x1400281c7  mov     rax, cs:__security_cookie
0x1400281ce  xor     rax, rsp
0x1400281d1  mov     [rbp+2F0h+var_50], rax
0x1400281d8  mov     r15, rdx
0x1400281db  mov     r14, rcx
0x1400281de  lea     r13, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400281e5  mov     [rsp+3F0h+var_378], r13
0x1400281ea  lea     rax, aCvsssoftwarepr_6; "CVssSoftwareProviderWrapper::CreateInst"...
0x1400281f1  mov     [rbp+2F0h+var_370], rax
0x1400281f5  lea     rax, aCorsoftc; "CORSOFTC"
0x1400281fc  mov     [rbp+2F0h+var_368], rax
0x140028200  mov     [rbp+2F0h+var_360], 3Eh ; '>'
0x140028207  mov     [rbp+2F0h+var_35C], 1
0x14002820e  mov     [rbp+2F0h+var_358], 0FFh
0x140028215  xor     r12d, r12d
0x140028218  mov     [rbp+2F0h+var_2D8], 1000000h
0x14002821f  xor     edx, edx; Val
0x140028221  mov     r8d, 78h ; 'x'; Size
0x140028227  lea     rcx, [rbp+2F0h+pv]; void *
0x14002822b  call    memset_0
0x140028230  mov     [rbp+2F0h+dwMessageId], r12d
0x140028234  mov     rax, [rbp+2F0h+var_370]
0x140028238  mov     [rbp+2F0h+var_288], rax
0x14002823c  mov     rax, [rsp+3F0h+var_378]
0x140028241  mov     [rbp+2F0h+var_2A0], rax
0x140028245  mov     rax, [rbp+2F0h+var_368]
0x140028249  mov     [rbp+2F0h+var_298], rax
0x14002824d  mov     eax, [rbp+2F0h+var_360]
0x140028250  mov     [rbp+2F0h+var_290], eax
0x140028253  mov     eax, [rbp+2F0h+var_35C]
0x140028256  mov     [rbp+2F0h+var_28C], eax
0x140028259  call    cs:__imp_GetTickCount
0x14002825f  mov     [rbp+2F0h+var_27C], eax
0x140028262  mov     [rbp+2F0h+var_2AC], 0FFFFFFFFh
0x140028269  mov     eax, [rbp+2F0h+var_358]
0x14002826c  mov     [rbp+2F0h+var_278], eax
0x14002826f  mov     [rbp+2F0h+var_2B0], r12d
0x140028273  mov     [rbp+2F0h+var_250], r12
0x14002827a  xorps   xmm0, xmm0
0x14002827d  movdqa  [rbp+2F0h+var_270], xmm0
0x140028285  xorps   xmm1, xmm1
0x140028288  movdqa  [rbp+2F0h+var_260], xmm1
0x140028290  mov     [rsp+3F0h+var_380], r12
0x140028295  lea     rcx, [rsp+3F0h+var_380]
0x14002829a  call    cs:__imp_VssGetTracingContextPerThread
0x1400282a0  test    eax, eax
0x1400282a2  jns     loc_14002858B
0x1400282a8  mov     rax, [rbp+2F0h+var_250]
0x1400282af  test    rax, rax
0x1400282b2  jz      loc_1400285AE
0x1400282b8  mov     eax, [rax+30h]
0x1400282bb  inc     eax
0x1400282bd  mov     [rbp+2F0h+var_280], eax
0x1400282c0  mov     ebx, 0A0h
0x1400282c5  cmp     [rbp+2F0h+var_278], 0FFh
0x1400282cc  cmovnz  ebx, [rbp+2F0h+var_278]
0x1400282d0  mov     edx, [rbp+2F0h+var_28C]; unsigned int
0x1400282d3  lea     rcx, [rbp+2F0h+var_2B0]; this
0x1400282d7  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x1400282dc  test    eax, eax
0x1400282de  jnz     loc_1400285B7
0x1400282e4  cmp     byte ptr [rbp+2F0h+var_2D8+3], r12b
0x1400282e8  jz      short loc_140028307
0x1400282ea  mov     rbx, r12
0x1400282ed  nop     dword ptr [rax]
0x1400282f0  mov     rcx, [rbp+rbx*8+2F0h+pv]; pv
0x1400282f5  test    rcx, rcx
0x1400282f8  jnz     loc_140028573
0x1400282fe  inc     rbx
0x140028301  cmp     rbx, 0Fh
0x140028305  jnz     short loc_1400282F0
0x140028307  movzx   eax, byte ptr [r14+0Fh]
0x14002830c  movzx   ecx, byte ptr [r14+0Eh]
0x140028311  movzx   edx, byte ptr [r14+0Dh]
0x140028316  movzx   r8d, byte ptr [r14+0Ch]
0x14002831b  movzx   r9d, byte ptr [r14+0Bh]
0x140028320  movzx   r10d, byte ptr [r14+0Ah]
0x140028325  movzx   r11d, byte ptr [r14+9]
0x14002832a  movzx   ebx, byte ptr [r14+8]
0x14002832f  movzx   edi, word ptr [r14+6]
0x140028334  movzx   esi, word ptr [r14+4]
0x140028339  mov     [rsp+3F0h+var_388], eax
0x14002833d  mov     [rsp+3F0h+var_390], ecx
0x140028341  mov     [rsp+3F0h+var_398], edx
0x140028345  mov     [rsp+3F0h+var_3A0], r8d
0x14002834a  mov     [rsp+3F0h+var_3A8], r9d
0x14002834f  mov     dword ptr [rsp+3F0h+var_3B0], r10d
0x140028354  mov     dword ptr [rsp+3F0h+var_3B8], r11d
0x140028359  mov     dword ptr [rsp+3F0h+var_3C0], ebx
0x14002835d  mov     dword ptr [rsp+3F0h+var_3C8], edi
0x140028361  mov     dword ptr [rsp+3F0h+var_3D0], esi
0x140028365  mov     r9d, [r14]
0x140028368  lea     r8, aSwprovider8x4x; "SwProvider_{%.8x-%.4x-%.4x-%.2x%.2x-%.2"...
0x14002836f  mov     edx, 50h ; 'P'; unsigned __int64
0x140028374  lea     rcx, [rbp+2F0h+var_F0]; unsigned __int16 *
0x14002837b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140028380  mov     ebx, eax
0x140028382  mov     [rbp+2F0h+dwMessageId], eax
0x140028385  test    eax, eax
0x140028387  js      loc_1400285F7
0x14002838d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140028394  mov     ecx, 378h; unsigned __int64
0x140028399  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002839e  mov     rbx, rax
0x1400283a1  mov     [rsp+3F0h+var_380], rax
0x1400283a6  test    rax, rax
0x1400283a9  jz      loc_140028583
0x1400283af  lea     rax, ??_7CVssSoftwareProviderWrapper@@6B@; const CVssSoftwareProviderWrapper::`vftable'
0x1400283b6  mov     [rbx], rax
0x1400283b9  lea     rcx, [rbx+8]
0x1400283bd  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400283c2  nop
0x1400283c3  lea     rcx, [rbx+10h]
0x1400283c7  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400283cc  nop
0x1400283cd  lea     rcx, [rbx+18h]
0x1400283d1  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400283d6  nop
0x1400283d7  mov     [rbx+20h], r12d
0x1400283db  lea     rcx, [rbx+28h]; this
0x1400283df  mov     [rcx+18h], r12
0x1400283e3  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x1400283ea  mov     [rcx+10h], rax
0x1400283ee  mov     [rcx+8], r12
0x1400283f2  mov     dword ptr [rcx+4], 1
0x1400283f9  mov     dword ptr [rcx], 2001Fh
0x1400283ff  mov     byte ptr [rcx+20h], 0
0x140028403  mov     [rcx+348h], r12d
0x14002840a  lea     rdx, [rbp+2F0h+var_F0]; unsigned __int16 *
0x140028411  call    ?Initialize@CVssDiag@@QEAAXPEBG@Z; CVssDiag::Initialize(ushort const *)
0x140028416  nop
0x140028417  mov     rdx, rbx
0x14002841a  lea     rcx, [rsp+3F0h+var_380]
0x14002841f  call    ??0?$CComPtr@VCVssSoftwareProviderWrapper@@@ATL@@QEAA@PEAVCVssSoftwareProviderWrapper@@@Z; ATL::CComPtr<CVssSoftwareProviderWrapper>::CComPtr<CVssSoftwareProviderWrapper>(CVssSoftwareProviderWrapper *)
0x140028424  nop
0x140028425  lea     rcx, [rsp+3F0h+var_380]
0x14002842a  call    ??8?$CComPtrBase@UIVssHardwareSnapshotProvider@@@ATL@@QEBA_NPEAUIVssHardwareSnapshotProvider@@@Z; ATL::CComPtrBase<IVssHardwareSnapshotProvider>::operator==(IVssHardwareSnapshotProvider *)
0x14002842f  mov     [rsp+3F0h+var_378], r13
0x140028434  lea     rsi, aCvsssoftwarepr_6; "CVssSoftwareProviderWrapper::CreateInst"...
0x14002843b  mov     [rbp+2F0h+var_35C], 1
0x140028442  mov     [rbp+2F0h+var_358], 0FFh
0x140028449  mov     [rbp+2F0h+var_2D8], 1000000h
0x140028450  xor     edx, edx; Val
0x140028452  mov     r8d, 78h ; 'x'; Size
0x140028458  lea     rcx, [rbp+2F0h+pv]; void *
0x14002845c  mov     [rbp+2F0h+var_370], rsi
0x140028460  test    al, al
0x140028462  lea     rax, aCorsoftc; "CORSOFTC"
0x140028469  mov     [rbp+2F0h+var_368], rax
0x14002846d  jnz     loc_140028658
0x140028473  mov     rbx, [rsp+3F0h+var_380]
0x140028478  lea     rdi, [rbx+8]
0x14002847c  movups  xmm6, xmmword ptr cs:_GUID_609e123e_2c5a_44d3_8f01_0b1d9a47d1ff.Data1
0x140028483  mov     [rbp+2F0h+var_360], 4Dh ; 'M'
0x14002848a  call    memset_0
0x14002848f  movaps  [rbp+2F0h+var_2D0], xmm6
0x140028493  movaps  xmm0, xmmword ptr [r15]
0x140028497  movdqa  [rbp+2F0h+var_2C0], xmm0
0x14002849c  mov     [rsp+3F0h+var_3C0], rdi
0x1400284a1  lea     rax, [rbp+2F0h+var_2D0]
0x1400284a5  mov     [rsp+3F0h+var_3C8], rax
0x1400284aa  mov     dword ptr [rsp+3F0h+var_3D0], 4
0x1400284b2  lea     r9, aSwProv; "SW_PROV"
0x1400284b9  lea     r8, [rbp+2F0h+var_2C0]
0x1400284bd  lea     rdx, [rsp+3F0h+var_378]
0x1400284c2  lea     rcx, [rbp+2F0h+var_2B0]
0x1400284c6  call    ?CoCreateInstanceWithLog@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@U_GUID@@PEBGK1PEAPEAUIUnknown@@@Z; CVssFunctionTracer::CoCreateInstanceWithLog(CVssDebugInfo,_GUID,ushort const *,ulong,_GUID,IUnknown * *)
0x1400284cb  cmp     [rbp+2F0h+dwMessageId], 0
0x1400284cf  jl      loc_140028680
0x1400284d5  mov     rcx, [rdi]
0x1400284d8  mov     rax, [rcx]
0x1400284db  lea     r8, [rbx+10h]
0x1400284df  lea     rdx, _GUID_5f894e5b_1e39_4778_8e23_9abad9f0e08c
0x1400284e6  mov     rax, [rax]
0x1400284e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400284ee  mov     [rbp+2F0h+dwMessageId], eax
0x1400284f1  test    eax, eax
0x1400284f3  js      loc_14002877C
0x1400284f9  mov     rcx, [rdi]
0x1400284fc  mov     rax, [rcx]
0x1400284ff  lea     r8, [rbx+18h]
0x140028503  lea     rdx, _GUID_e561901f_03a5_4afe_86d0_72baeece7004
0x14002850a  mov     rax, [rax]
0x14002850d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028512  mov     [rbp+2F0h+dwMessageId], eax
0x140028515  test    eax, eax
0x140028517  js      loc_1400287E0
0x14002851d  lea     rcx, [rsp+3F0h+var_380]
0x140028522  call    ?Detach@?$CComPtrBase@VIVssSnapshotDescription@@@ATL@@QEAAPEAVIVssSnapshotDescription@@XZ; ATL::CComPtrBase<IVssSnapshotDescription>::Detach(void)
0x140028527  mov     rbx, rax
0x14002852a  lea     rcx, [rsp+3F0h+var_380]
0x14002852f  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x140028534  nop
0x140028535  lea     rcx, [rbp+2F0h+var_2B0]; this
0x140028539  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002853e  mov     rax, rbx
0x140028541  mov     rcx, [rbp+2F0h+var_50]
0x140028548  xor     rcx, rsp; StackCookie
0x14002854b  call    __security_check_cookie
0x140028550  mov     rbx, [rsp+3F0h+arg_10]
0x140028558  movaps  xmm6, [rsp+3F0h+var_40]
0x140028560  add     rsp, 3C0h
0x140028567  pop     r15
0x140028569  pop     r14
0x14002856b  pop     r13
0x14002856d  pop     r12
0x14002856f  pop     rdi
0x140028570  pop     rsi
0x140028571  pop     rbp
0x140028572  retn
0x140028573  call    cs:__imp_CoTaskMemFree
0x140028579  mov     [rbp+rbx*8+2F0h+pv], r12
0x14002857e  jmp     loc_1400282FE
0x140028583  mov     rbx, r12
0x140028586  jmp     loc_140028417
0x14002858b  lea     rcx, [rbp+2F0h+var_2B0]
0x14002858f  call    cs:__imp_VssSetTracingContextPerThread
0x140028595  test    eax, eax
0x140028597  js      loc_1400282A8
0x14002859d  mov     rax, [rsp+3F0h+var_380]
0x1400285a2  mov     [rbp+2F0h+var_250], rax
0x1400285a9  jmp     loc_1400282AF
0x1400285ae  mov     [rbp+2F0h+var_280], r12d
0x1400285b2  jmp     loc_1400282C0
0x1400285b7  mov     [rsp+3F0h+var_3B0], r12
0x1400285bc  mov     dword ptr [rsp+3F0h+var_3B8], ebx
0x1400285c0  lea     rax, aEnter; "ENTER"
0x1400285c7  mov     [rsp+3F0h+var_3C0], rax
0x1400285cc  mov     rax, [rbp+2F0h+var_288]
0x1400285d0  mov     [rsp+3F0h+var_3C8], rax
0x1400285d5  mov     eax, [rbp+2F0h+var_28C]
0x1400285d8  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x1400285dc  mov     r9d, [rbp+2F0h+var_280]
0x1400285e0  mov     r8d, [rbp+2F0h+var_290]
0x1400285e4  mov     rdx, [rbp+2F0h+var_298]
0x1400285e8  mov     rcx, [rbp+2F0h+var_2A0]
0x1400285ec  call    cs:__imp_VssTraceMessage
0x1400285f2  jmp     loc_1400282E4
0x1400285f7  mov     [rsp+3F0h+var_378], r13
0x1400285fc  lea     rsi, aCvsssoftwarepr_6; "CVssSoftwareProviderWrapper::CreateInst"...
0x140028603  mov     [rbp+2F0h+var_370], rsi
0x140028607  lea     rax, aCorsoftc; "CORSOFTC"
0x14002860e  mov     [rbp+2F0h+var_368], rax
0x140028612  mov     [rbp+2F0h+var_360], 44h ; 'D'
0x140028619  mov     [rbp+2F0h+var_35C], 1
0x140028620  mov     [rbp+2F0h+var_358], 0FFh
0x140028627  mov     [rbp+2F0h+var_2D8], 1000000h
0x14002862e  xor     edx, edx; Val
0x140028630  mov     r8d, 78h ; 'x'; Size
0x140028636  lea     rcx, [rbp+2F0h+pv]; void *
0x14002863a  call    memset_0
0x14002863f  lea     r9, aStringcchprint_14; "StringCchPrintfW()"
0x140028646  mov     r8d, ebx
0x140028649  lea     rdx, [rsp+3F0h+var_378]
0x14002864e  lea     rcx, [rbp+2F0h+var_2B0]
0x140028652  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140028658  mov     [rbp+2F0h+var_360], 49h ; 'I'
0x14002865f  call    memset_0
0x140028664  lea     r9, aMemoryAllocati; "Memory allocation error"
0x14002866b  mov     r8d, 8007000Eh
0x140028671  lea     rdx, [rsp+3F0h+var_378]
0x140028676  lea     rcx, [rbp+2F0h+var_2B0]
0x14002867a  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140028680  mov     [rsp+3F0h+var_378], r13
0x140028685  mov     [rbp+2F0h+var_370], rsi
0x140028689  lea     rdi, aCorsoftc; "CORSOFTC"
0x140028690  mov     [rbp+2F0h+var_368], rdi
0x140028694  mov     [rbp+2F0h+var_360], 54h ; 'T'
0x14002869b  mov     [rbp+2F0h+var_35C], 1
0x1400286a2  mov     [rbp+2F0h+var_358], 0FFh
0x1400286a9  mov     [rbp+2F0h+var_2D8], 1000000h
0x1400286b0  xor     edx, edx; Val
0x1400286b2  mov     r8d, 78h ; 'x'; Size
0x1400286b8  lea     rcx, [rbp+2F0h+pv]; void *
0x1400286bc  call    memset_0
0x1400286c1  movaps  xmm0, xmmword ptr [r15]
0x1400286c5  movdqa  [rbp+2F0h+var_2C0], xmm0
0x1400286ca  lea     r8, [rbp+2F0h+var_2C0]
0x1400286ce  lea     rdx, [rbp+2F0h+var_198]; this
0x1400286d5  lea     rcx, [rsp+3F0h+var_378]; struct CVssDebugInfo *
0x1400286da  call    ??6CVssDebugInfo@@QEAA?AU0@U_GUID@@@Z; CVssDebugInfo::operator<<(_GUID)
0x1400286df  mov     r8d, [rbp+2F0h+dwMessageId]; dwMessageId
0x1400286e3  lea     rdx, [rbp+2F0h+var_240]; this
0x1400286ea  mov     rcx, rax; struct CVssDebugInfo *
0x1400286ed  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x1400286f2  mov     r9d, 1
0x1400286f8  mov     r8, rax
0x1400286fb  mov     edx, 3004h
0x140028700  lea     rcx, [rbp+2F0h+var_2B0]
  ... truncated ...
```
