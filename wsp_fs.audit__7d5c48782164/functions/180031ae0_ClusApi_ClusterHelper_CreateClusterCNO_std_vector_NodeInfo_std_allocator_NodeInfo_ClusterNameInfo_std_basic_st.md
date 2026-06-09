# ClusApi::ClusterHelper::CreateClusterCNO(std::vector<_NodeInfo,std::allocator<_NodeInfo>> &,_ClusterNameInfo &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180031ae0`
- end: `0x180031dfb`
- name: `?CreateClusterCNO@ClusterHelper@ClusApi@@UEAAJAEAV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEAU_ClusterNameInfo@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@2222@Z`
- size: `795`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x180002ad0`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000d5b8`
- `0x18000db2c`
- `0x18000e14c`
- `0x18000eb18`
- `0x180010b90`
- `0x180012b00`
- `0x18002fc58`
- `0x18002fc94`
- `0x180030cd8`
- `0x180030ea8`
- `0x180031ae0`
- `0x180032bcc`
- `0x1800795c8`
- `0x1800814f0`

## import_xrefs

- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x180031c41`
- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x180031c41`

## string_xrefs

- `0x180031b73`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x180031c75`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x180031cfc`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x180031c9b`: `{0} Failed to create cluster name in AD {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ClusApi::ClusterHelper::CreateClusterCNO(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v10; // rax
  int v11; // eax
  signed int v12; // edi
  struct cxl::TextWriter *v13; // rbx
  const wchar_t *v14; // rsi
  struct ClusterNameADClusterState *v15; // rbx
  const wchar_t *v16; // rdi
  wchar_t *v17; // rbx
  __int64 string; // rax
  const wchar_t *v19; // rax
  const wchar_t *v20; // r9
  int v21; // eax
  signed int v22; // esi
  struct cxl::TextWriter *v23; // rdi
  int v24; // eax
  struct cxl::TextWriter *v25; // rbx
  __int64 v26; // rax
  struct ClusterNameADClusterState *v27; // rbx
  struct ClusterNameADClusterState *v29; // [rsp+30h] [rbp-89h] BYREF
  struct ClusterNameADClusterState *v30; // [rsp+38h] [rbp-81h] BYREF
  __int64 v31; // [rsp+40h] [rbp-79h]
  __int64 v32; // [rsp+48h] [rbp-71h]
  char v33[8]; // [rsp+50h] [rbp-69h] BYREF
  wchar_t *v34; // [rsp+58h] [rbp-61h]
  char v35[8]; // [rsp+60h] [rbp-59h] BYREF
  struct ClusterNameADClusterState *v36; // [rsp+68h] [rbp-51h]
  wchar_t *v37; // [rsp+70h] [rbp-49h] BYREF
  int v38; // [rsp+78h] [rbp-41h]
  _BYTE v39[32]; // [rsp+90h] [rbp-29h] BYREF

  v31 = a7;
  v32 = a8;
  v30 = 0;
  v37 = 0;
  v36 = 0;
  v34 = 0;
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v11 = ClRtlParseDistinguishedName(v10, &v30, &v37);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 >= 0 )
  {
    v14 = 0;
    v15 = v30;
    if ( v30 )
    {
      cxl::LocalHeapPtr<unsigned char>::Clear(v35);
      v36 = v15;
      v14 = (const wchar_t *)v15;
    }
    v16 = 0;
    v17 = v37;
    if ( v37 )
    {
      cxl::LocalHeapPtr<unsigned char>::Clear(v33);
      v34 = v17;
      v16 = v17;
    }
    v29 = 0;
    string = cxl::load_string(v39, qword_180189F40, 2006);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(string);
    v19 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*a2);
    v21 = CCHlpCreateClusterNameInAD(v19, v14, v16, v20, 0, &v29);
    v22 = v21;
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
    std::wstring::_Tidy_deallocate(v39);
    if ( v22 >= 0 )
    {
      v30 = v29;
      v37 = 0;
      v24 = ProtectedPwd::Get((struct ClusterNameADClusterState *)((char *)v29 + 128), &v37);
      v12 = v24;
      if ( v24 > 0 )
        v12 = (unsigned __int16)v24 | 0x80070000;
      if ( v12 >= 0 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v37[v26] );
        v38 = 2 * v26 + 2;
        std::wstring::assign(a4, v37);
        v27 = v29;
        std::wstring::operator=(v31, (char *)v29 + 64);
        std::wstring::operator=(v32, (char *)v27 + 96);
        std::wstring::operator=(a5, v29);
        std::wstring::operator=(a6, (char *)v29 + 32);
        SecureAutoLdapType<wchar_t>::~SecureAutoLdapType<wchar_t>(&v37);
      }
      else
      {
        v25 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
        std::wstring::wstring(&v37, L"ClusApi::ClusterHelper::CreateClusterCNO");
        std::wstring::wstring(v39, &v37);
        cxl::TextWriter::WriteLine<char,TraceFunction,>(v25, "{0} Failed to get netname password");
        std::wstring::_Tidy_deallocate(v39);
        std::wstring::_Tidy_deallocate(&v37);
      }
      std::unique_ptr<ClusterNameADClusterState>::~unique_ptr<ClusterNameADClusterState>(&v30);
    }
    else
    {
      v23 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      std::wstring::wstring(&v37, L"ClusApi::ClusterHelper::CreateClusterCNO");
      std::wstring::wstring(v39, &v37);
      cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(v23, "{0} Failed to create cluster name in AD {1}");
      std::wstring::_Tidy_deallocate(v39);
      std::wstring::_Tidy_deallocate(&v37);
      v12 = v22;
    }
  }
  else
  {
    v13 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    std::wstring::wstring(v39, L"ClusApi::ClusterHelper::CreateClusterCNO");
    std::wstring::wstring(&v37, v39);
    cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(v13, "{0} Unable to parse cluster name {1}");
    std::wstring::_Tidy_deallocate(&v37);
    std::wstring::_Tidy_deallocate(v39);
  }
  cxl::LocalHeapPtr<unsigned char>::Clear(v33);
  cxl::LocalHeapPtr<unsigned char>::Clear(v35);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180031ae0  mov     [rsp-8+arg_0], rbx
0x180031ae5  push    rbp
0x180031ae6  push    rsi
0x180031ae7  push    rdi
0x180031ae8  push    r12
0x180031aea  push    r13
0x180031aec  push    r14
0x180031aee  push    r15
0x180031af0  lea     rbp, [rsp-7]
0x180031af5  sub     rsp, 0C0h
0x180031afc  mov     rax, cs:__security_cookie
0x180031b03  xor     rax, rsp
0x180031b06  mov     [rbp+37h+var_40], rax
0x180031b0a  mov     r15, r9
0x180031b0d  mov     rsi, r8
0x180031b10  mov     r14, rdx
0x180031b13  mov     r12, [rbp+37h+arg_20]
0x180031b17  mov     r13, [rbp+37h+arg_28]
0x180031b1b  mov     rax, [rbp+37h+arg_30]
0x180031b1f  mov     [rbp+37h+var_B0], rax
0x180031b23  mov     rax, [rbp+37h+arg_38]
0x180031b27  mov     [rbp+37h+var_A8], rax
0x180031b2b  xor     ebx, ebx
0x180031b2d  mov     [rsp+0F0h+var_B8], rbx
0x180031b32  mov     [rbp+37h+var_80], rbx
0x180031b36  mov     [rbp+37h+var_88], rbx
0x180031b3a  mov     [rbp+37h+var_98], rbx
0x180031b3e  mov     rcx, r8
0x180031b41  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031b46  lea     r8, [rbp+37h+var_80]
0x180031b4a  lea     rdx, [rsp+0F0h+var_B8]
0x180031b4f  mov     rcx, rax
0x180031b52  call    ClRtlParseDistinguishedName
0x180031b57  mov     edi, eax
0x180031b59  test    eax, eax
0x180031b5b  jle     short loc_180031B66
0x180031b5d  movzx   edi, ax
0x180031b60  or      edi, 80070000h
0x180031b66  test    edi, edi
0x180031b68  jns     short loc_180031BC1
0x180031b6a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180031b6f  lea     rbx, [rax+28h]
0x180031b73  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x180031b7a  lea     rcx, [rbp+37h+var_60]
0x180031b7e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180031b83  nop
0x180031b84  lea     rdx, [rbp+37h+var_60]
0x180031b88  lea     rcx, [rbp+37h+var_80]
0x180031b8c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031b91  nop
0x180031b92  mov     r9, rsi
0x180031b95  lea     r8, [rbp+37h+var_80]
0x180031b99  lea     rdx, a0UnableToParse; "{0} Unable to parse cluster name {1}"
0x180031ba0  mov     rcx, rbx; struct cxl::TextWriter *
0x180031ba3  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x180031ba8  nop
0x180031ba9  lea     rcx, [rbp+37h+var_80]
0x180031bad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031bb2  nop
0x180031bb3  lea     rcx, [rbp+37h+var_60]
0x180031bb7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031bbc  jmp     loc_180031DBE
0x180031bc1  mov     rsi, rbx
0x180031bc4  mov     rbx, [rsp+0F0h+var_B8]
0x180031bc9  test    rbx, rbx
0x180031bcc  jz      short loc_180031BDE
0x180031bce  lea     rcx, [rbp+37h+var_90]
0x180031bd2  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180031bd7  mov     [rbp+37h+var_88], rbx
0x180031bdb  mov     rsi, rbx
0x180031bde  xor     edi, edi
0x180031be0  mov     rbx, [rbp+37h+var_80]
0x180031be4  test    rbx, rbx
0x180031be7  jz      short loc_180031BF9
0x180031be9  lea     rcx, [rbp+37h+var_A0]
0x180031bed  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180031bf2  mov     [rbp+37h+var_98], rbx
0x180031bf6  mov     rdi, rbx
0x180031bf9  xor     ebx, ebx
0x180031bfb  mov     [rsp+0F0h+var_C0], rbx
0x180031c00  mov     r8d, 7D6h
0x180031c06  mov     rdx, cs:qword_180189F40
0x180031c0d  lea     rcx, [rbp+37h+var_60]
0x180031c11  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x180031c16  nop
0x180031c17  mov     rcx, rax
0x180031c1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031c1f  mov     r9, rax
0x180031c22  mov     rcx, [r14]
0x180031c25  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031c2a  lea     rcx, [rsp+0F0h+var_C0]
0x180031c2f  mov     [rsp+0F0h+var_C8], rcx
0x180031c34  mov     [rsp+0F0h+var_D0], ebx
0x180031c38  mov     r8, rdi
0x180031c3b  mov     rdx, rsi
0x180031c3e  mov     rcx, rax
0x180031c41  call    cs:__imp_?CCHlpCreateClusterNameInAD@@YAKPEB_W000HPEAPEAVClusterNameADClusterState@@@Z; CCHlpCreateClusterNameInAD(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,ClusterNameADClusterState * *)
0x180031c48  nop     dword ptr [rax+rax+00h]
0x180031c4d  mov     esi, eax
0x180031c4f  test    eax, eax
0x180031c51  jle     short loc_180031C5C
0x180031c53  movzx   esi, ax
0x180031c56  or      esi, 80070000h
0x180031c5c  lea     rcx, [rbp+37h+var_60]
0x180031c60  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031c65  test    esi, esi
0x180031c67  jns     short loc_180031CC5
0x180031c69  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180031c6e  lea     rdi, [rax+28h]
0x180031c72  mov     rbx, [r14]
0x180031c75  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x180031c7c  lea     rcx, [rbp+37h+var_80]
0x180031c80  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180031c85  nop
0x180031c86  lea     rdx, [rbp+37h+var_80]
0x180031c8a  lea     rcx, [rbp+37h+var_60]
0x180031c8e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031c93  nop
0x180031c94  mov     r9, rbx
0x180031c97  lea     r8, [rbp+37h+var_60]
0x180031c9b  lea     rdx, a0FailedToCreat; "{0} Failed to create cluster name in AD"...
0x180031ca2  mov     rcx, rdi; struct cxl::TextWriter *
0x180031ca5  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x180031caa  nop
0x180031cab  lea     rcx, [rbp+37h+var_60]
0x180031caf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031cb4  nop
0x180031cb5  lea     rcx, [rbp+37h+var_80]
0x180031cb9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031cbe  mov     edi, esi
0x180031cc0  jmp     loc_180031DBE
0x180031cc5  mov     rcx, [rsp+0F0h+var_C0]
0x180031cca  mov     [rsp+0F0h+var_B8], rcx
0x180031ccf  mov     [rbp+37h+var_80], rbx
0x180031cd3  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x180031cd7  lea     rdx, [rbp+37h+var_80]; wchar_t **
0x180031cdb  call    ?Get@ProtectedPwd@@QEAAKPEAPEA_W@Z; ProtectedPwd::Get(wchar_t * *)
0x180031ce0  mov     edi, eax
0x180031ce2  test    eax, eax
0x180031ce4  jle     short loc_180031CEF
0x180031ce6  movzx   edi, ax
0x180031ce9  or      edi, 80070000h
0x180031cef  test    edi, edi
0x180031cf1  jns     short loc_180031D44
0x180031cf3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180031cf8  lea     rbx, [rax+28h]
0x180031cfc  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x180031d03  lea     rcx, [rbp+37h+var_80]
0x180031d07  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180031d0c  nop
0x180031d0d  lea     rdx, [rbp+37h+var_80]
0x180031d11  lea     rcx, [rbp+37h+var_60]
0x180031d15  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031d1a  nop
0x180031d1b  lea     r8, [rbp+37h+var_60]
0x180031d1f  lea     rdx, a0FailedToGetNe; "{0} Failed to get netname password"
0x180031d26  mov     rcx, rbx; struct cxl::TextWriter *
0x180031d29  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x180031d2e  nop
0x180031d2f  lea     rcx, [rbp+37h+var_60]
0x180031d33  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031d38  nop
0x180031d39  lea     rcx, [rbp+37h+var_80]
0x180031d3d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031d42  jmp     short loc_180031DB3
0x180031d44  mov     rdx, [rbp+37h+var_80]
0x180031d48  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031d4c  inc     rax
0x180031d4f  cmp     [rdx+rax*2], bx
0x180031d53  jnz     short loc_180031D4C
0x180031d55  mov     [rbp+37h+var_80], rdx
0x180031d59  lea     eax, ds:2[rax*2]
0x180031d60  mov     [rbp+37h+var_78], eax
0x180031d63  mov     rcx, r15
0x180031d66  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180031d6b  mov     rbx, [rsp+0F0h+var_C0]
0x180031d70  lea     rdx, [rbx+40h]
0x180031d74  mov     rcx, [rbp+37h+var_B0]
0x180031d78  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180031d7d  lea     rdx, [rbx+60h]
0x180031d81  mov     rcx, [rbp+37h+var_A8]
0x180031d85  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180031d8a  mov     rdx, [rsp+0F0h+var_C0]
0x180031d8f  mov     rcx, r12
0x180031d92  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180031d97  mov     rdx, [rsp+0F0h+var_C0]
0x180031d9c  add     rdx, 20h ; ' '
0x180031da0  mov     rcx, r13
0x180031da3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180031da8  nop
0x180031da9  lea     rcx, [rbp+37h+var_80]
0x180031dad  call    ??1?$SecureAutoLdapType@_W@@QEAA@XZ; SecureAutoLdapType<wchar_t>::~SecureAutoLdapType<wchar_t>(void)
0x180031db2  nop
0x180031db3  lea     rcx, [rsp+0F0h+var_B8]
0x180031db8  call    ??1?$unique_ptr@VClusterNameADClusterState@@U?$default_delete@VClusterNameADClusterState@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusterNameADClusterState>::~unique_ptr<ClusterNameADClusterState>(void)
0x180031dbd  nop
0x180031dbe  lea     rcx, [rbp+37h+var_A0]
0x180031dc2  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180031dc7  nop
0x180031dc8  lea     rcx, [rbp+37h+var_90]
0x180031dcc  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180031dd1  mov     eax, edi
0x180031dd3  mov     rcx, [rbp+37h+var_40]
0x180031dd7  xor     rcx, rsp; StackCookie
0x180031dda  call    __security_check_cookie
0x180031ddf  mov     rbx, [rsp+0F0h+arg_0]
0x180031de7  add     rsp, 0C0h
0x180031dee  pop     r15
0x180031df0  pop     r14
0x180031df2  pop     r13
0x180031df4  pop     r12
0x180031df6  pop     rdi
0x180031df7  pop     rsi
0x180031df8  pop     rbp
0x180031df9  retn
```
