# CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity(_GUID,unsigned __int64 *)

- ea: `0x14003f700`
- end: `0x14003fba7`
- name: `?GetIpsecSecurity@CVdsIscsiInitiatorPortalInternal@@UEAAJU_GUID@@PEA_K@Z`
- size: `1191`
- prototype: `__int64 __fastcall(CVdsIscsiInitiatorPortalInternal *__hidden this, struct _GUID *__struct_ptr, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000dd3c`
- `0x140012c48`
- `0x14002e123`
- `0x14003f700`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f94d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f94d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003f93b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003fb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003fb5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003f93b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003fb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003fb5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f803`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003f803`
- `vdsutil!VdsTrace` at `0x14003f87d`
- `vdsutil!VdsTrace` at `0x14003f87d`
- `vdsutil!VdsIscsiIpsecIdToIpAddress` at `0x14003f9d3`
- `vdsutil!VdsIscsiIpsecIdToIpAddress` at `0x14003f9d3`
- `vdsutil!VdsIscsiCheckEqualIpAddress` at `0x14003fad3`
- `vdsutil!VdsIscsiCheckEqualIpAddress` at `0x14003fad3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003f794`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003f794`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003fb68`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003fb68`
- `vdsutil!VdsTraceW` at `0x14003f7de`
- `vdsutil!VdsTraceW` at `0x14003f83e`
- `vdsutil!VdsTraceW` at `0x14003f964`
- `vdsutil!VdsTraceW` at `0x14003f980`
- `vdsutil!VdsTraceW` at `0x14003fb09`
- `vdsutil!VdsTraceW` at `0x14003fb2c`
- `vdsutil!VdsTraceW` at `0x14003f7de`
- `vdsutil!VdsTraceW` at `0x14003f83e`
- `vdsutil!VdsTraceW` at `0x14003f964`
- `vdsutil!VdsTraceW` at `0x14003f980`
- `vdsutil!VdsTraceW` at `0x14003fb09`
- `vdsutil!VdsTraceW` at `0x14003fb2c`

## string_xrefs

- `0x14003f785`: `CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity()`
- `0x14003f7d5`: `CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity: NULL input arguments`
- `0x14003fb23`: `CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity: Could not access necessary function in iSCSI library.`
- `0x14003f832`: `CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity: m_pParentAdapter->GetProperties: %X`
- `0x14003fb1a`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: Could not retrieve target portal object from provider: %X`
- `0x14003fafd`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortalUnk->QueryInterface IID_IVdsIscsiPortal: %X`
- `0x14003f8e9`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortal->GetProperties: %X`
- `0x14003faf1`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: VdsIscsiIpsecIdToIpAddress: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity(
        CVdsIscsiInitiatorPortalInternal *this,
        struct _GUID *a2,
        unsigned __int64 *a3)
{
  unsigned int *v6; // rdi
  FARPROC ProcAddress; // rsi
  int v8; // eax
  int ObjectFromProviders; // ebx
  const wchar_t *v10; // rdx
  int v11; // eax
  int v12; // eax
  __int64 i; // rsi
  __int64 v14; // rcx
  _OWORD *v15; // rcx
  char *v16; // rax
  __int64 v17; // rdx
  _OWORD *v18; // rcx
  _OWORD *v19; // rax
  __int64 v20; // rdx
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[560]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[560]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v29; // [rsp+4D0h] [rbp+3D0h] BYREF
  LPVOID pv; // [rsp+4E0h] [rbp+3E0h]
  _BYTE v31[560]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v32[16]; // [rsp+720h] [rbp+620h] BYREF
  char v33; // [rsp+730h] [rbp+630h] BYREF

  v29 = 0;
  pv = 0;
  v24[0] = 0;
  v23 = 0;
  memset_0(v32, 0, 0x23Cu);
  v22 = 0;
  v6 = 0;
  memset_0(v31, 0, 0x228u);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v26, 0x5Eu, "CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity()");
  v29 = 0;
  pv = 0;
  memset_0(v32, 0, 0x23Cu);
  memset_0(v31, 0, 0x228u);
  if ( !a3 )
    VdsTraceW(0, L"CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity: NULL input arguments");
  *a3 = 0;
  if ( !CVdsService::m_hIscsidscModule
    || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "GetIScsiIKEInfoW")) == 0 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity: Could not access necessary function in iSCSI library.");
    ObjectFromProviders = -2147212288;
    goto LABEL_42;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8), &v29);
  ObjectFromProviders = v8;
  if ( v8 < 0 )
  {
    v10 = L"CVdsIscsiInitiatorPortalInternal::GetIpsecSecurity: m_pParentAdapter->GetProperties: %X";
LABEL_7:
    VdsTraceW(0, v10, (unsigned int)v8);
    goto LABEL_42;
  }
  v25 = *a2;
  ObjectFromProviders = CVdsService::GetObjectFromProviders(&v25, VDS_OT_PORTAL, v24);
  if ( ObjectFromProviders == -2147212283 )
  {
    VdsTrace(0, "IVdsIscsiInitiatorAdapter::GetProperties, 1, hr: %x", -2147212283);
    goto LABEL_42;
  }
  if ( ObjectFromProviders < 0 || !v24[0] )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: Could not retrieve target portal object from provider: %X",
      (unsigned int)ObjectFromProviders);
LABEL_38:
    if ( ObjectFromProviders >= 0 )
      ObjectFromProviders = -2147467259;
    goto LABEL_42;
  }
  ObjectFromProviders = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v24[0]->lpVtbl->QueryInterface)(
                          v24[0],
                          &IID_IVdsIscsiPortal,
                          &v23);
  if ( ObjectFromProviders < 0 || !v23 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortalUnk->QueryInterface IID_IVdsIscsiPortal: %X",
      (unsigned int)ObjectFromProviders);
    goto LABEL_38;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v23 + 24LL))(v23, v32);
  ObjectFromProviders = v11;
  if ( v11 >= 0 )
  {
    while ( 1 )
    {
      v12 = ((__int64 (__fastcall *)(LPVOID, _QWORD, unsigned int *, unsigned int *))ProcAddress)(
              pv,
              *((unsigned int *)this + 160),
              &v22,
              v6);
      if ( !v12 || (v12 & 0xFFF0000) != 0 && (v12 & 0xC0000000) != 0xC0000000 )
        break;
      if ( v12 != 122 )
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: GetIScsiIKEInfoW failed: %X",
          (unsigned int)ObjectFromProviders);
        ObjectFromProviders = -2147211003;
        goto LABEL_42;
      }
      if ( v6 )
        CoTaskMemFree(v6);
      v6 = (unsigned int *)CoTaskMemAlloc(48LL * v22);
      if ( !v6 )
      {
        VdsTraceW(0, L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: pIkeAuthInfo Alloc: Out of memory.");
        ObjectFromProviders = -2147024882;
        goto LABEL_42;
      }
    }
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v22 )
        goto LABEL_35;
      memset_0(v31, 0, 0x228u);
      LOBYTE(v14) = v6[12 * i + 4];
      v8 = VdsIscsiIpsecIdToIpAddress(v14, v6[12 * i + 5], *(_QWORD *)&v6[12 * i + 6], v31);
      ObjectFromProviders = v8;
      if ( v8 < 0 )
        break;
      v15 = v27;
      v16 = &v33;
      v17 = 4;
      do
      {
        *v15 = *(_OWORD *)v16;
        v15[1] = *((_OWORD *)v16 + 1);
        v15[2] = *((_OWORD *)v16 + 2);
        v15[3] = *((_OWORD *)v16 + 3);
        v15[4] = *((_OWORD *)v16 + 4);
        v15[5] = *((_OWORD *)v16 + 5);
        v15[6] = *((_OWORD *)v16 + 6);
        v15[7] = *((_OWORD *)v16 + 7);
        v15 += 8;
        v16 += 128;
        --v17;
      }
      while ( v17 );
      *v15 = *(_OWORD *)v16;
      v15[1] = *((_OWORD *)v16 + 1);
      *((_QWORD *)v15 + 4) = *((_QWORD *)v16 + 4);
      v18 = v28;
      v19 = v31;
      v20 = 4;
      do
      {
        *v18 = *v19;
        v18[1] = v19[1];
        v18[2] = v19[2];
        v18[3] = v19[3];
        v18[4] = v19[4];
        v18[5] = v19[5];
        v18[6] = v19[6];
        v18[7] = v19[7];
        v18 += 8;
        v19 += 8;
        --v20;
      }
      while ( v20 );
      *v18 = *v19;
      v18[1] = v19[1];
      *((_QWORD *)v18 + 4) = *((_QWORD *)v19 + 4);
      if ( (unsigned int)VdsIscsiCheckEqualIpAddress(v28, v27) )
      {
        *a3 = *(_QWORD *)&v6[12 * i + 2];
LABEL_35:
        ObjectFromProviders = 0;
        goto LABEL_42;
      }
    }
    v10 = L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: VdsIscsiIpsecIdToIpAddress: %X";
    goto LABEL_7;
  }
  VdsTraceW(0, L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortal->GetProperties: %X", (unsigned int)v11);
LABEL_42:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v6 )
    CoTaskMemFree(v6);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v24);
  return (unsigned int)ObjectFromProviders;
}

```

## disassembly

```asm
0x14003f700  push    rbp
0x14003f702  push    rbx
0x14003f703  push    rsi
0x14003f704  push    rdi
0x14003f705  push    r12
0x14003f707  push    r14
0x14003f709  push    r15
0x14003f70b  lea     rbp, [rsp-870h]
0x14003f713  sub     rsp, 970h
0x14003f71a  mov     rax, cs:__security_cookie
0x14003f721  xor     rax, rsp
0x14003f724  mov     [rbp+8A0h+var_40], rax
0x14003f72b  mov     r12, r8
0x14003f72e  mov     r14, rdx
0x14003f731  mov     r15, rcx
0x14003f734  xorps   xmm0, xmm0
0x14003f737  xor     eax, eax
0x14003f739  movups  [rbp+8A0h+var_4D0], xmm0
0x14003f740  mov     [rbp+8A0h+pv], rax
0x14003f747  mov     [rsp+9A0h+var_960], rax
0x14003f74c  mov     [rsp+9A0h+var_968], rax
0x14003f751  mov     ebx, 23Ch
0x14003f756  mov     r8d, ebx; Size
0x14003f759  xor     edx, edx; Val
0x14003f75b  lea     rcx, [rbp+8A0h+var_280]; void *
0x14003f762  call    memset_0
0x14003f767  mov     [rsp+9A0h+var_970], 0
0x14003f76f  xor     edi, edi
0x14003f771  lea     esi, [rbx-14h]
0x14003f774  mov     r8d, esi; Size
0x14003f777  xor     edx, edx; Val
0x14003f779  lea     rcx, [rbp+8A0h+var_4B0]; void *
0x14003f780  call    memset_0
0x14003f785  lea     r8, aCvdsiscsiiniti_57; "CVdsIscsiInitiatorPortalInternal::GetIp"...
0x14003f78c  lea     edx, [rdi+5Eh]
0x14003f78f  lea     rcx, [rsp+9A0h+var_940]
0x14003f794  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003f79a  nop
0x14003f79b  xorps   xmm0, xmm0
0x14003f79e  xor     eax, eax
0x14003f7a0  movups  [rbp+8A0h+var_4D0], xmm0
0x14003f7a7  mov     [rbp+8A0h+pv], rax
0x14003f7ae  mov     r8d, ebx; Size
0x14003f7b1  xor     edx, edx; Val
0x14003f7b3  lea     rcx, [rbp+8A0h+var_280]; void *
0x14003f7ba  call    memset_0
0x14003f7bf  mov     r8d, esi; Size
0x14003f7c2  xor     edx, edx; Val
0x14003f7c4  lea     rcx, [rbp+8A0h+var_4B0]; void *
0x14003f7cb  call    memset_0
0x14003f7d0  test    r12, r12
0x14003f7d3  jnz     short loc_14003F7E4
0x14003f7d5  lea     rdx, aCvdsiscsiiniti_78; "CVdsIscsiInitiatorPortalInternal::GetIp"...
0x14003f7dc  xor     ecx, ecx
0x14003f7de  call    cs:__imp_VdsTraceW
0x14003f7e4  mov     qword ptr [r12], 0
0x14003f7ec  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14003f7f3  test    rcx, rcx
0x14003f7f6  jz      loc_14003FB23
0x14003f7fc  lea     rdx, aGetiscsiikeinf; "GetIScsiIKEInfoW"
0x14003f803  call    cs:__imp_GetProcAddress
0x14003f809  mov     rsi, rax
0x14003f80c  test    rax, rax
0x14003f80f  jz      loc_14003FB23
0x14003f815  mov     rcx, [r15+40h]
0x14003f819  mov     rdx, [rcx]
0x14003f81c  mov     rax, [rdx+18h]
0x14003f820  lea     rdx, [rbp+8A0h+var_4D0]
0x14003f827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f82c  mov     ebx, eax
0x14003f82e  test    eax, eax
0x14003f830  jns     short loc_14003F849
0x14003f832  lea     rdx, aCvdsiscsiiniti_15; "CVdsIscsiInitiatorPortalInternal::GetIp"...
0x14003f839  mov     r8d, eax
0x14003f83c  xor     ecx, ecx
0x14003f83e  call    cs:__imp_VdsTraceW
0x14003f844  jmp     loc_14003FB37
0x14003f849  movups  xmm0, xmmword ptr [r14]
0x14003f84d  movdqu  xmmword ptr [rsp+9A0h+var_950.Data1], xmm0
0x14003f853  lea     r8, [rsp+9A0h+var_960]; struct IUnknown **
0x14003f858  mov     edx, 24h ; '$'; enum _VDS_OBJECT_TYPE
0x14003f85d  lea     rcx, [rsp+9A0h+var_950]; struct _GUID
0x14003f862  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x14003f867  mov     ebx, eax
0x14003f869  mov     r8d, 80042405h
0x14003f86f  cmp     eax, r8d
0x14003f872  jnz     short loc_14003F888
0x14003f874  lea     rdx, aIvdsiscsiiniti; "IVdsIscsiInitiatorAdapter::GetPropertie"...
0x14003f87b  xor     ecx, ecx
0x14003f87d  call    cs:__imp_VdsTrace
0x14003f883  jmp     loc_14003FB37
0x14003f888  test    ebx, ebx
0x14003f88a  js      loc_14003FB1A
0x14003f890  mov     rcx, [rsp+9A0h+var_960]
0x14003f895  test    rcx, rcx
0x14003f898  jz      loc_14003FB1A
0x14003f89e  mov     rax, [rcx]
0x14003f8a1  lea     r8, [rsp+9A0h+var_968]
0x14003f8a6  lea     rdx, IID_IVdsIscsiPortal
0x14003f8ad  mov     rax, [rax]
0x14003f8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f8b5  mov     ebx, eax
0x14003f8b7  test    eax, eax
0x14003f8b9  js      loc_14003FAFD
0x14003f8bf  mov     rcx, [rsp+9A0h+var_968]
0x14003f8c4  test    rcx, rcx
0x14003f8c7  jz      loc_14003FAFD
0x14003f8cd  mov     rax, [rcx]
0x14003f8d0  lea     rdx, [rbp+8A0h+var_280]
0x14003f8d7  mov     rax, [rax+18h]
0x14003f8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f8e0  mov     ebx, eax
0x14003f8e2  test    eax, eax
0x14003f8e4  jns     short loc_14003F8F5
0x14003f8e6  mov     r8d, eax
0x14003f8e9  lea     rdx, aCvdsiscsiiniti_139; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003f8f0  jmp     loc_14003F83C
0x14003f8f5  mov     r14d, 0C0000000h
0x14003f8fb  mov     r9, rdi
0x14003f8fe  lea     r8, [rsp+9A0h+var_970]
0x14003f903  mov     edx, [r15+280h]
0x14003f90a  mov     rcx, [rbp+8A0h+pv]
0x14003f911  mov     rax, rsi
0x14003f914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f919  test    eax, eax
0x14003f91b  jz      short loc_14003F990
0x14003f91d  test    eax, 0FFF0000h
0x14003f922  jz      short loc_14003F92E
0x14003f924  mov     edx, eax
0x14003f926  and     edx, r14d
0x14003f929  cmp     edx, r14d
0x14003f92c  jnz     short loc_14003F990
0x14003f92e  cmp     eax, 7Ah ; 'z'
0x14003f931  jnz     short loc_14003F974
0x14003f933  test    rdi, rdi
0x14003f936  jz      short loc_14003F941
0x14003f938  mov     rcx, rdi; pv
0x14003f93b  call    cs:__imp_CoTaskMemFree
0x14003f941  mov     eax, [rsp+9A0h+var_970]
0x14003f945  lea     rcx, [rax+rax*2]
0x14003f949  shl     rcx, 4; cb
0x14003f94d  call    cs:__imp_CoTaskMemAlloc
0x14003f953  mov     rdi, rax
0x14003f956  test    rax, rax
0x14003f959  jnz     short loc_14003F8FB
0x14003f95b  lea     rdx, aCvdsiscsiiniti_138; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003f962  xor     ecx, ecx
0x14003f964  call    cs:__imp_VdsTraceW
0x14003f96a  mov     ebx, 8007000Eh
0x14003f96f  jmp     loc_14003FB37
0x14003f974  mov     r8d, ebx
0x14003f977  lea     rdx, aCvdsiscsiiniti_90; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003f97e  xor     ecx, ecx
0x14003f980  call    cs:__imp_VdsTraceW
0x14003f986  mov     ebx, 80042905h
0x14003f98b  jmp     loc_14003FB37
0x14003f990  xor     esi, esi
0x14003f992  mov     r15d, 80h
0x14003f998  cmp     esi, [rsp+9A0h+var_970]
0x14003f99c  jnb     loc_14003FAED
0x14003f9a2  xor     edx, edx; Val
0x14003f9a4  mov     r8d, 228h; Size
0x14003f9aa  lea     rcx, [rbp+8A0h+var_4B0]; void *
0x14003f9b1  call    memset_0
0x14003f9b6  lea     r14, [rsi+rsi*2]
0x14003f9ba  add     r14, r14
0x14003f9bd  lea     r9, [rbp+8A0h+var_4B0]
0x14003f9c4  mov     r8, [rdi+r14*8+18h]
0x14003f9c9  mov     edx, [rdi+r14*8+14h]
0x14003f9ce  mov     cl, [rdi+r14*8+10h]
0x14003f9d3  call    cs:__imp_VdsIscsiIpsecIdToIpAddress
0x14003f9d9  mov     ebx, eax
0x14003f9db  test    eax, eax
0x14003f9dd  js      loc_14003FAF1
0x14003f9e3  lea     rcx, [rsp+9A0h+var_930]
0x14003f9e8  lea     rax, [rbp+8A0h+var_270]
0x14003f9ef  mov     edx, 4
0x14003f9f4  movups  xmm0, xmmword ptr [rax]
0x14003f9f7  movups  xmmword ptr [rcx], xmm0
0x14003f9fa  movups  xmm1, xmmword ptr [rax+10h]
0x14003f9fe  movups  xmmword ptr [rcx+10h], xmm1
0x14003fa02  movups  xmm0, xmmword ptr [rax+20h]
0x14003fa06  movups  xmmword ptr [rcx+20h], xmm0
0x14003fa0a  movups  xmm1, xmmword ptr [rax+30h]
0x14003fa0e  movups  xmmword ptr [rcx+30h], xmm1
0x14003fa12  movups  xmm0, xmmword ptr [rax+40h]
0x14003fa16  movups  xmmword ptr [rcx+40h], xmm0
0x14003fa1a  movups  xmm1, xmmword ptr [rax+50h]
0x14003fa1e  movups  xmmword ptr [rcx+50h], xmm1
0x14003fa22  movups  xmm0, xmmword ptr [rax+60h]
0x14003fa26  movups  xmmword ptr [rcx+60h], xmm0
0x14003fa2a  movups  xmm1, xmmword ptr [rax+70h]
0x14003fa2e  movups  xmmword ptr [rcx+70h], xmm1
0x14003fa32  add     rcx, r15
0x14003fa35  add     rax, r15
0x14003fa38  sub     rdx, 1
0x14003fa3c  jnz     short loc_14003F9F4
0x14003fa3e  movups  xmm0, xmmword ptr [rax]
0x14003fa41  movups  xmmword ptr [rcx], xmm0
0x14003fa44  movups  xmm1, xmmword ptr [rax+10h]
0x14003fa48  movups  xmmword ptr [rcx+10h], xmm1
0x14003fa4c  mov     rax, [rax+20h]
0x14003fa50  mov     [rcx+20h], rax
0x14003fa54  lea     rcx, [rbp+8A0h+var_700]
0x14003fa5b  lea     rax, [rbp+8A0h+var_4B0]
0x14003fa62  mov     edx, 4
0x14003fa67  movups  xmm0, xmmword ptr [rax]
0x14003fa6a  movups  xmmword ptr [rcx], xmm0
0x14003fa6d  movups  xmm1, xmmword ptr [rax+10h]
0x14003fa71  movups  xmmword ptr [rcx+10h], xmm1
0x14003fa75  movups  xmm0, xmmword ptr [rax+20h]
0x14003fa79  movups  xmmword ptr [rcx+20h], xmm0
0x14003fa7d  movups  xmm1, xmmword ptr [rax+30h]
0x14003fa81  movups  xmmword ptr [rcx+30h], xmm1
0x14003fa85  movups  xmm0, xmmword ptr [rax+40h]
0x14003fa89  movups  xmmword ptr [rcx+40h], xmm0
0x14003fa8d  movups  xmm1, xmmword ptr [rax+50h]
0x14003fa91  movups  xmmword ptr [rcx+50h], xmm1
0x14003fa95  movups  xmm0, xmmword ptr [rax+60h]
0x14003fa99  movups  xmmword ptr [rcx+60h], xmm0
0x14003fa9d  movups  xmm1, xmmword ptr [rax+70h]
0x14003faa1  movups  xmmword ptr [rcx+70h], xmm1
0x14003faa5  add     rcx, r15
0x14003faa8  add     rax, r15
0x14003faab  sub     rdx, 1
0x14003faaf  jnz     short loc_14003FA67
0x14003fab1  movups  xmm0, xmmword ptr [rax]
0x14003fab4  movups  xmmword ptr [rcx], xmm0
0x14003fab7  movups  xmm1, xmmword ptr [rax+10h]
0x14003fabb  movups  xmmword ptr [rcx+10h], xmm1
0x14003fabf  mov     rax, [rax+20h]
0x14003fac3  mov     [rcx+20h], rax
0x14003fac7  lea     rdx, [rsp+9A0h+var_930]
0x14003facc  lea     rcx, [rbp+8A0h+var_700]
0x14003fad3  call    cs:__imp_VdsIscsiCheckEqualIpAddress
0x14003fad9  test    eax, eax
0x14003fadb  jnz     short loc_14003FAE4
0x14003fadd  inc     esi
0x14003fadf  jmp     loc_14003F998
0x14003fae4  mov     rax, [rdi+r14*8+8]
0x14003fae9  mov     [r12], rax
0x14003faed  xor     ebx, ebx
0x14003faef  jmp     short loc_14003FB37
0x14003faf1  lea     rdx, aCvdsiscsiiniti_82; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003faf8  jmp     loc_14003F839
0x14003fafd  lea     rdx, aCvdsiscsiiniti_46; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003fb04  mov     r8d, ebx
0x14003fb07  xor     ecx, ecx
0x14003fb09  call    cs:__imp_VdsTraceW
0x14003fb0f  test    ebx, ebx
0x14003fb11  js      short loc_14003FB37
0x14003fb13  mov     ebx, 80004005h
0x14003fb18  jmp     short loc_14003FB37
0x14003fb1a  lea     rdx, aCvdsiscsiiniti_7; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003fb21  jmp     short loc_14003FB04
0x14003fb23  lea     rdx, aCvdsiscsiiniti_61; "CVdsIscsiInitiatorPortalInternal::GetIp"...
0x14003fb2a  xor     ecx, ecx
0x14003fb2c  call    cs:__imp_VdsTraceW
0x14003fb32  mov     ebx, 80042400h
0x14003fb37  mov     rcx, [rbp+8A0h+pv]; pv
0x14003fb3e  test    rcx, rcx
0x14003fb41  jz      short loc_14003FB54
0x14003fb43  call    cs:__imp_CoTaskMemFree
0x14003fb49  mov     [rbp+8A0h+pv], 0
0x14003fb54  test    rdi, rdi
0x14003fb57  jz      short loc_14003FB63
0x14003fb59  mov     rcx, rdi; pv
0x14003fb5c  call    cs:__imp_CoTaskMemFree
0x14003fb62  nop
0x14003fb63  lea     rcx, [rsp+9A0h+var_940]
0x14003fb68  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003fb6e  nop
0x14003fb6f  lea     rcx, [rsp+9A0h+var_968]
0x14003fb74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003fb79  nop
0x14003fb7a  lea     rcx, [rsp+9A0h+var_960]
0x14003fb7f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003fb84  mov     eax, ebx
0x14003fb86  mov     rcx, [rbp+8A0h+var_40]
0x14003fb8d  xor     rcx, rsp; StackCookie
0x14003fb90  call    __security_check_cookie
0x14003fb95  add     rsp, 970h
0x14003fb9c  pop     r15
0x14003fb9e  pop     r14
0x14003fba0  pop     r12
0x14003fba2  pop     rdi
0x14003fba3  pop     rsi
0x14003fba4  pop     rbx
0x14003fba5  pop     rbp
0x14003fba6  retn
```
