# ClusApi::ClusterHelper::CreateClusterCNO(std::vector<_NodeInfo,std::allocator<_NodeInfo>> &,_ClusterNameInfo &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180030ad0`
- end: `0x180030de4`
- name: `?CreateClusterCNO@ClusterHelper@ClusApi@@UEAAJAEAV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEAU_ClusterNameInfo@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@2222@Z`
- size: `788`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x180002a70`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000d250`
- `0x18000d794`
- `0x18000dd74`
- `0x18000e6f4`
- `0x18001072c`
- `0x180012660`
- `0x18002ed90`
- `0x18002edcc`
- `0x18002fd5c`
- `0x18002ff20`
- `0x180030ad0`
- `0x180031b18`
- `0x180077948`
- `0x18007f514`

## import_xrefs

- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x180030c31`
- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x180030c31`

## string_xrefs

- `0x180030b63`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x180030c5f`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x180030ce6`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x180030c85`: `{0} Failed to create cluster name in AD {1}`

## pseudocode

```c
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
  const void **v15; // rbx
  const wchar_t *v16; // rdi
  wchar_t *v17; // rbx
  __int64 string; // rax
  const wchar_t *v19; // rax
  const wchar_t *v20; // r9
  int ClusterNameInAD; // eax
  signed int v22; // esi
  struct cxl::TextWriter *v23; // rdi
  signed int v24; // eax
  struct cxl::TextWriter *v25; // rbx
  __int64 v26; // rax
  const void **v28; // [rsp+30h] [rbp-89h] BYREF
  const void **v29; // [rsp+38h] [rbp-81h] BYREF
  __int64 v30; // [rsp+40h] [rbp-79h]
  __int64 v31; // [rsp+48h] [rbp-71h]
  char v32[8]; // [rsp+50h] [rbp-69h] BYREF
  wchar_t *v33; // [rsp+58h] [rbp-61h]
  char v34[8]; // [rsp+60h] [rbp-59h] BYREF
  const void **v35; // [rsp+68h] [rbp-51h]
  wchar_t *v36; // [rsp+70h] [rbp-49h] BYREF
  int v37; // [rsp+78h] [rbp-41h]
  _BYTE v38[32]; // [rsp+90h] [rbp-29h] BYREF

  v30 = a7;
  v31 = a8;
  v29 = 0;
  v36 = 0;
  v35 = 0;
  v33 = 0;
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v11 = ClRtlParseDistinguishedName(v10, &v29, &v36);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 >= 0 )
  {
    v14 = 0;
    v15 = v29;
    if ( v29 )
    {
      cxl::LocalHeapPtr<unsigned char>::Clear(v34);
      v35 = v15;
      v14 = (const wchar_t *)v15;
    }
    v16 = 0;
    v17 = v36;
    if ( v36 )
    {
      cxl::LocalHeapPtr<unsigned char>::Clear(v32);
      v33 = v17;
      v16 = v17;
    }
    v28 = 0;
    string = cxl::load_string(v38, qword_180187E10, 2006);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(string);
    v19 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*a2);
    ClusterNameInAD = CCHlpCreateClusterNameInAD(v19, v14, v16, v20, 0, (struct ClusterNameADClusterState **)&v28);
    v22 = ClusterNameInAD;
    if ( ClusterNameInAD > 0 )
      v22 = (unsigned __int16)ClusterNameInAD | 0x80070000;
    std::wstring::_Tidy_deallocate(v38);
    if ( v22 >= 0 )
    {
      v29 = v28;
      v36 = 0;
      v24 = ProtectedPwd::Get(v28 + 16, &v36);
      v12 = v24;
      if ( v24 > 0 )
        v12 = (unsigned __int16)v24 | 0x80070000;
      if ( v12 >= 0 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v36[v26] );
        v37 = 2 * v26 + 2;
        std::wstring::assign(a4);
        std::wstring::operator=(v30);
        std::wstring::operator=(v31);
        std::wstring::operator=(a5);
        std::wstring::operator=(a6);
        SecureAutoLdapType<wchar_t>::~SecureAutoLdapType<wchar_t>(&v36);
      }
      else
      {
        v25 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
        std::wstring::wstring(&v36, L"ClusApi::ClusterHelper::CreateClusterCNO");
        std::wstring::wstring(v38);
        cxl::TextWriter::WriteLine<char,TraceFunction,>(v25, "{0} Failed to get netname password");
        std::wstring::_Tidy_deallocate(v38);
        std::wstring::_Tidy_deallocate(&v36);
      }
      std::unique_ptr<ClusterNameADClusterState>::~unique_ptr<ClusterNameADClusterState>(&v29);
    }
    else
    {
      v23 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      std::wstring::wstring(&v36, L"ClusApi::ClusterHelper::CreateClusterCNO");
      std::wstring::wstring(v38);
      cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(v23, "{0} Failed to create cluster name in AD {1}");
      std::wstring::_Tidy_deallocate(v38);
      std::wstring::_Tidy_deallocate(&v36);
      v12 = v22;
    }
  }
  else
  {
    v13 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
    std::wstring::wstring(v38, L"ClusApi::ClusterHelper::CreateClusterCNO");
    std::wstring::wstring(&v36);
    cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(v13, "{0} Unable to parse cluster name {1}");
    std::wstring::_Tidy_deallocate(&v36);
    std::wstring::_Tidy_deallocate(v38);
  }
  cxl::LocalHeapPtr<unsigned char>::Clear(v32);
  cxl::LocalHeapPtr<unsigned char>::Clear(v34);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180030ad0  mov     [rsp-8+arg_0], rbx
0x180030ad5  push    rbp
0x180030ad6  push    rsi
0x180030ad7  push    rdi
0x180030ad8  push    r12
0x180030ada  push    r13
0x180030adc  push    r14
0x180030ade  push    r15
0x180030ae0  lea     rbp, [rsp-7]
0x180030ae5  sub     rsp, 0C0h
0x180030aec  mov     rax, cs:__security_cookie
0x180030af3  xor     rax, rsp
0x180030af6  mov     [rbp+37h+var_40], rax
0x180030afa  mov     r15, r9
0x180030afd  mov     rsi, r8
0x180030b00  mov     r14, rdx
0x180030b03  mov     r12, [rbp+37h+arg_20]
0x180030b07  mov     r13, [rbp+37h+arg_28]
0x180030b0b  mov     rax, [rbp+37h+arg_30]
0x180030b0f  mov     [rbp+37h+var_B0], rax
0x180030b13  mov     rax, [rbp+37h+arg_38]
0x180030b17  mov     [rbp+37h+var_A8], rax
0x180030b1b  xor     ebx, ebx
0x180030b1d  mov     [rsp+0F0h+var_B8], rbx
0x180030b22  mov     [rbp+37h+var_80], rbx
0x180030b26  mov     [rbp+37h+var_88], rbx
0x180030b2a  mov     [rbp+37h+var_98], rbx
0x180030b2e  mov     rcx, r8
0x180030b31  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180030b36  lea     r8, [rbp+37h+var_80]
0x180030b3a  lea     rdx, [rsp+0F0h+var_B8]
0x180030b3f  mov     rcx, rax
0x180030b42  call    ClRtlParseDistinguishedName
0x180030b47  mov     edi, eax
0x180030b49  test    eax, eax
0x180030b4b  jle     short loc_180030B56
0x180030b4d  movzx   edi, ax
0x180030b50  or      edi, 80070000h
0x180030b56  test    edi, edi
0x180030b58  jns     short loc_180030BB1
0x180030b5a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180030b5f  lea     rbx, [rax+28h]
0x180030b63  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x180030b6a  lea     rcx, [rbp+37h+var_60]
0x180030b6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180030b73  nop
0x180030b74  lea     rdx, [rbp+37h+var_60]
0x180030b78  lea     rcx, [rbp+37h+var_80]
0x180030b7c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030b81  nop
0x180030b82  mov     r9, rsi
0x180030b85  lea     r8, [rbp+37h+var_80]
0x180030b89  lea     rdx, a0UnableToParse; "{0} Unable to parse cluster name {1}"
0x180030b90  mov     rcx, rbx; struct cxl::TextWriter *
0x180030b93  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x180030b98  nop
0x180030b99  lea     rcx, [rbp+37h+var_80]
0x180030b9d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030ba2  nop
0x180030ba3  lea     rcx, [rbp+37h+var_60]
0x180030ba7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030bac  jmp     loc_180030DA8
0x180030bb1  mov     rsi, rbx
0x180030bb4  mov     rbx, [rsp+0F0h+var_B8]
0x180030bb9  test    rbx, rbx
0x180030bbc  jz      short loc_180030BCE
0x180030bbe  lea     rcx, [rbp+37h+var_90]
0x180030bc2  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180030bc7  mov     [rbp+37h+var_88], rbx
0x180030bcb  mov     rsi, rbx
0x180030bce  xor     edi, edi
0x180030bd0  mov     rbx, [rbp+37h+var_80]
0x180030bd4  test    rbx, rbx
0x180030bd7  jz      short loc_180030BE9
0x180030bd9  lea     rcx, [rbp+37h+var_A0]
0x180030bdd  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180030be2  mov     [rbp+37h+var_98], rbx
0x180030be6  mov     rdi, rbx
0x180030be9  xor     ebx, ebx
0x180030beb  mov     [rsp+0F0h+var_C0], rbx
0x180030bf0  mov     r8d, 7D6h
0x180030bf6  mov     rdx, cs:qword_180187E10
0x180030bfd  lea     rcx, [rbp+37h+var_60]
0x180030c01  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x180030c06  nop
0x180030c07  mov     rcx, rax
0x180030c0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180030c0f  mov     r9, rax
0x180030c12  mov     rcx, [r14]
0x180030c15  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180030c1a  lea     rcx, [rsp+0F0h+var_C0]
0x180030c1f  mov     [rsp+0F0h+var_C8], rcx
0x180030c24  mov     [rsp+0F0h+var_D0], ebx
0x180030c28  mov     r8, rdi
0x180030c2b  mov     rdx, rsi
0x180030c2e  mov     rcx, rax
0x180030c31  call    cs:__imp_?CCHlpCreateClusterNameInAD@@YAKPEB_W000HPEAPEAVClusterNameADClusterState@@@Z; CCHlpCreateClusterNameInAD(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,ClusterNameADClusterState * *)
0x180030c37  mov     esi, eax
0x180030c39  test    eax, eax
0x180030c3b  jle     short loc_180030C46
0x180030c3d  movzx   esi, ax
0x180030c40  or      esi, 80070000h
0x180030c46  lea     rcx, [rbp+37h+var_60]
0x180030c4a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030c4f  test    esi, esi
0x180030c51  jns     short loc_180030CAF
0x180030c53  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180030c58  lea     rdi, [rax+28h]
0x180030c5c  mov     rbx, [r14]
0x180030c5f  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x180030c66  lea     rcx, [rbp+37h+var_80]
0x180030c6a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180030c6f  nop
0x180030c70  lea     rdx, [rbp+37h+var_80]
0x180030c74  lea     rcx, [rbp+37h+var_60]
0x180030c78  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030c7d  nop
0x180030c7e  mov     r9, rbx
0x180030c81  lea     r8, [rbp+37h+var_60]
0x180030c85  lea     rdx, a0FailedToCreat; "{0} Failed to create cluster name in AD"...
0x180030c8c  mov     rcx, rdi; struct cxl::TextWriter *
0x180030c8f  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x180030c94  nop
0x180030c95  lea     rcx, [rbp+37h+var_60]
0x180030c99  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030c9e  nop
0x180030c9f  lea     rcx, [rbp+37h+var_80]
0x180030ca3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030ca8  mov     edi, esi
0x180030caa  jmp     loc_180030DA8
0x180030caf  mov     rcx, [rsp+0F0h+var_C0]
0x180030cb4  mov     [rsp+0F0h+var_B8], rcx
0x180030cb9  mov     [rbp+37h+var_80], rbx
0x180030cbd  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x180030cc1  lea     rdx, [rbp+37h+var_80]; wchar_t **
0x180030cc5  call    ?Get@ProtectedPwd@@QEAAKPEAPEA_W@Z; ProtectedPwd::Get(wchar_t * *)
0x180030cca  mov     edi, eax
0x180030ccc  test    eax, eax
0x180030cce  jle     short loc_180030CD9
0x180030cd0  movzx   edi, ax
0x180030cd3  or      edi, 80070000h
0x180030cd9  test    edi, edi
0x180030cdb  jns     short loc_180030D2E
0x180030cdd  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180030ce2  lea     rbx, [rax+28h]
0x180030ce6  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x180030ced  lea     rcx, [rbp+37h+var_80]
0x180030cf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180030cf6  nop
0x180030cf7  lea     rdx, [rbp+37h+var_80]
0x180030cfb  lea     rcx, [rbp+37h+var_60]
0x180030cff  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180030d04  nop
0x180030d05  lea     r8, [rbp+37h+var_60]
0x180030d09  lea     rdx, a0FailedToGetNe; "{0} Failed to get netname password"
0x180030d10  mov     rcx, rbx; struct cxl::TextWriter *
0x180030d13  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x180030d18  nop
0x180030d19  lea     rcx, [rbp+37h+var_60]
0x180030d1d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030d22  nop
0x180030d23  lea     rcx, [rbp+37h+var_80]
0x180030d27  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030d2c  jmp     short loc_180030D9D
0x180030d2e  mov     rdx, [rbp+37h+var_80]
0x180030d32  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030d36  inc     rax
0x180030d39  cmp     [rdx+rax*2], bx
0x180030d3d  jnz     short loc_180030D36
0x180030d3f  mov     [rbp+37h+var_80], rdx
0x180030d43  lea     eax, ds:2[rax*2]
0x180030d4a  mov     [rbp+37h+var_78], eax
0x180030d4d  mov     rcx, r15
0x180030d50  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180030d55  mov     rbx, [rsp+0F0h+var_C0]
0x180030d5a  lea     rdx, [rbx+40h]
0x180030d5e  mov     rcx, [rbp+37h+var_B0]
0x180030d62  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180030d67  lea     rdx, [rbx+60h]
0x180030d6b  mov     rcx, [rbp+37h+var_A8]
0x180030d6f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180030d74  mov     rdx, [rsp+0F0h+var_C0]
0x180030d79  mov     rcx, r12
0x180030d7c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180030d81  mov     rdx, [rsp+0F0h+var_C0]
0x180030d86  add     rdx, 20h ; ' '
0x180030d8a  mov     rcx, r13
0x180030d8d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180030d92  nop
0x180030d93  lea     rcx, [rbp+37h+var_80]
0x180030d97  call    ??1?$SecureAutoLdapType@_W@@QEAA@XZ; SecureAutoLdapType<wchar_t>::~SecureAutoLdapType<wchar_t>(void)
0x180030d9c  nop
0x180030d9d  lea     rcx, [rsp+0F0h+var_B8]
0x180030da2  call    ??1?$unique_ptr@VClusterNameADClusterState@@U?$default_delete@VClusterNameADClusterState@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusterNameADClusterState>::~unique_ptr<ClusterNameADClusterState>(void)
0x180030da7  nop
0x180030da8  lea     rcx, [rbp+37h+var_A0]
0x180030dac  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180030db1  nop
0x180030db2  lea     rcx, [rbp+37h+var_90]
0x180030db6  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180030dbb  mov     eax, edi
0x180030dbd  mov     rcx, [rbp+37h+var_40]
0x180030dc1  xor     rcx, rsp; StackCookie
0x180030dc4  call    __security_check_cookie
0x180030dc9  mov     rbx, [rsp+0F0h+arg_0]
0x180030dd1  add     rsp, 0C0h
0x180030dd8  pop     r15
0x180030dda  pop     r14
0x180030ddc  pop     r13
0x180030dde  pop     r12
0x180030de0  pop     rdi
0x180030de1  pop     rsi
0x180030de2  pop     rbp
0x180030de3  retn
```
