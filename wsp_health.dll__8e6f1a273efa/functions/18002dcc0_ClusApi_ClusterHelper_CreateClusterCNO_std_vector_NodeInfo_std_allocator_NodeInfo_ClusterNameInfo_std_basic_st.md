# ClusApi::ClusterHelper::CreateClusterCNO(std::vector<_NodeInfo,std::allocator<_NodeInfo>> &,_ClusterNameInfo &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18002dcc0`
- end: `0x18002dfdb`
- name: `?CreateClusterCNO@ClusterHelper@ClusApi@@UEAAJAEAV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEAU_ClusterNameInfo@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@2222@Z`
- size: `795`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x180002b50`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000d390`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f89c`
- `0x180011800`
- `0x18002be18`
- `0x18002be54`
- `0x18002cecc`
- `0x18002d090`
- `0x18002dcc0`
- `0x18002ed6c`
- `0x180043be8`
- `0x1800442a0`

## import_xrefs

- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x18002de21`
- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x18002de21`

## string_xrefs

- `0x18002dd53`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x18002de55`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x18002dedc`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x18002de7b`: `{0} Failed to create cluster name in AD {1}`

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
  signed int v24; // eax
  struct cxl::TextWriter *v25; // rbx
  __int64 v26; // rax
  struct ClusterNameADClusterState *v28; // [rsp+30h] [rbp-89h] BYREF
  struct ClusterNameADClusterState *v29; // [rsp+38h] [rbp-81h] BYREF
  __int64 v30; // [rsp+40h] [rbp-79h]
  __int64 v31; // [rsp+48h] [rbp-71h]
  char v32[8]; // [rsp+50h] [rbp-69h] BYREF
  wchar_t *v33; // [rsp+58h] [rbp-61h]
  char v34[8]; // [rsp+60h] [rbp-59h] BYREF
  struct ClusterNameADClusterState *v35; // [rsp+68h] [rbp-51h]
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
    string = cxl::load_string(v38, qword_1801599A0, 2006);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(string);
    v19 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*a2);
    v21 = CCHlpCreateClusterNameInAD(v19, v14, v16, v20, 0, &v28);
    v22 = v21;
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
    std::wstring::_Tidy_deallocate(v38);
    if ( v22 >= 0 )
    {
      v29 = v28;
      v36 = 0;
      v24 = ProtectedPwd::Get((struct ClusterNameADClusterState *)((char *)v28 + 128), &v36);
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
        std::wstring::assign(a4, v36);
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
        std::wstring::wstring(v38, &v36);
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
      std::wstring::wstring(v38, &v36);
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
    std::wstring::wstring(&v36, v38);
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
0x18002dcc0  mov     [rsp-8+arg_0], rbx
0x18002dcc5  push    rbp
0x18002dcc6  push    rsi
0x18002dcc7  push    rdi
0x18002dcc8  push    r12
0x18002dcca  push    r13
0x18002dccc  push    r14
0x18002dcce  push    r15
0x18002dcd0  lea     rbp, [rsp-7]
0x18002dcd5  sub     rsp, 0C0h
0x18002dcdc  mov     rax, cs:__security_cookie
0x18002dce3  xor     rax, rsp
0x18002dce6  mov     [rbp+37h+var_40], rax
0x18002dcea  mov     r15, r9
0x18002dced  mov     rsi, r8
0x18002dcf0  mov     r14, rdx
0x18002dcf3  mov     r12, [rbp+37h+arg_20]
0x18002dcf7  mov     r13, [rbp+37h+arg_28]
0x18002dcfb  mov     rax, [rbp+37h+arg_30]
0x18002dcff  mov     [rbp+37h+var_B0], rax
0x18002dd03  mov     rax, [rbp+37h+arg_38]
0x18002dd07  mov     [rbp+37h+var_A8], rax
0x18002dd0b  xor     ebx, ebx
0x18002dd0d  mov     [rsp+0F0h+var_B8], rbx
0x18002dd12  mov     [rbp+37h+var_80], rbx
0x18002dd16  mov     [rbp+37h+var_88], rbx
0x18002dd1a  mov     [rbp+37h+var_98], rbx
0x18002dd1e  mov     rcx, r8
0x18002dd21  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002dd26  lea     r8, [rbp+37h+var_80]
0x18002dd2a  lea     rdx, [rsp+0F0h+var_B8]
0x18002dd2f  mov     rcx, rax
0x18002dd32  call    ClRtlParseDistinguishedName
0x18002dd37  mov     edi, eax
0x18002dd39  test    eax, eax
0x18002dd3b  jle     short loc_18002DD46
0x18002dd3d  movzx   edi, ax
0x18002dd40  or      edi, 80070000h
0x18002dd46  test    edi, edi
0x18002dd48  jns     short loc_18002DDA1
0x18002dd4a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002dd4f  lea     rbx, [rax+28h]
0x18002dd53  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x18002dd5a  lea     rcx, [rbp+37h+var_60]
0x18002dd5e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002dd63  nop
0x18002dd64  lea     rdx, [rbp+37h+var_60]
0x18002dd68  lea     rcx, [rbp+37h+var_80]
0x18002dd6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002dd71  nop
0x18002dd72  mov     r9, rsi
0x18002dd75  lea     r8, [rbp+37h+var_80]
0x18002dd79  lea     rdx, a0UnableToParse; "{0} Unable to parse cluster name {1}"
0x18002dd80  mov     rcx, rbx; struct cxl::TextWriter *
0x18002dd83  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x18002dd88  nop
0x18002dd89  lea     rcx, [rbp+37h+var_80]
0x18002dd8d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd92  nop
0x18002dd93  lea     rcx, [rbp+37h+var_60]
0x18002dd97  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd9c  jmp     loc_18002DF9E
0x18002dda1  mov     rsi, rbx
0x18002dda4  mov     rbx, [rsp+0F0h+var_B8]
0x18002dda9  test    rbx, rbx
0x18002ddac  jz      short loc_18002DDBE
0x18002ddae  lea     rcx, [rbp+37h+var_90]
0x18002ddb2  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002ddb7  mov     [rbp+37h+var_88], rbx
0x18002ddbb  mov     rsi, rbx
0x18002ddbe  xor     edi, edi
0x18002ddc0  mov     rbx, [rbp+37h+var_80]
0x18002ddc4  test    rbx, rbx
0x18002ddc7  jz      short loc_18002DDD9
0x18002ddc9  lea     rcx, [rbp+37h+var_A0]
0x18002ddcd  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002ddd2  mov     [rbp+37h+var_98], rbx
0x18002ddd6  mov     rdi, rbx
0x18002ddd9  xor     ebx, ebx
0x18002dddb  mov     [rsp+0F0h+var_C0], rbx
0x18002dde0  mov     r8d, 7D6h
0x18002dde6  mov     rdx, cs:qword_1801599A0
0x18002dded  lea     rcx, [rbp+37h+var_60]
0x18002ddf1  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18002ddf6  nop
0x18002ddf7  mov     rcx, rax
0x18002ddfa  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ddff  mov     r9, rax
0x18002de02  mov     rcx, [r14]
0x18002de05  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002de0a  lea     rcx, [rsp+0F0h+var_C0]
0x18002de0f  mov     [rsp+0F0h+var_C8], rcx
0x18002de14  mov     [rsp+0F0h+var_D0], ebx
0x18002de18  mov     r8, rdi
0x18002de1b  mov     rdx, rsi
0x18002de1e  mov     rcx, rax
0x18002de21  call    cs:__imp_?CCHlpCreateClusterNameInAD@@YAKPEB_W000HPEAPEAVClusterNameADClusterState@@@Z; CCHlpCreateClusterNameInAD(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,ClusterNameADClusterState * *)
0x18002de28  nop     dword ptr [rax+rax+00h]
0x18002de2d  mov     esi, eax
0x18002de2f  test    eax, eax
0x18002de31  jle     short loc_18002DE3C
0x18002de33  movzx   esi, ax
0x18002de36  or      esi, 80070000h
0x18002de3c  lea     rcx, [rbp+37h+var_60]
0x18002de40  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002de45  test    esi, esi
0x18002de47  jns     short loc_18002DEA5
0x18002de49  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002de4e  lea     rdi, [rax+28h]
0x18002de52  mov     rbx, [r14]
0x18002de55  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x18002de5c  lea     rcx, [rbp+37h+var_80]
0x18002de60  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002de65  nop
0x18002de66  lea     rdx, [rbp+37h+var_80]
0x18002de6a  lea     rcx, [rbp+37h+var_60]
0x18002de6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002de73  nop
0x18002de74  mov     r9, rbx
0x18002de77  lea     r8, [rbp+37h+var_60]
0x18002de7b  lea     rdx, a0FailedToCreat; "{0} Failed to create cluster name in AD"...
0x18002de82  mov     rcx, rdi; struct cxl::TextWriter *
0x18002de85  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x18002de8a  nop
0x18002de8b  lea     rcx, [rbp+37h+var_60]
0x18002de8f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002de94  nop
0x18002de95  lea     rcx, [rbp+37h+var_80]
0x18002de99  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002de9e  mov     edi, esi
0x18002dea0  jmp     loc_18002DF9E
0x18002dea5  mov     rcx, [rsp+0F0h+var_C0]
0x18002deaa  mov     [rsp+0F0h+var_B8], rcx
0x18002deaf  mov     [rbp+37h+var_80], rbx
0x18002deb3  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x18002deb7  lea     rdx, [rbp+37h+var_80]; wchar_t **
0x18002debb  call    ?Get@ProtectedPwd@@QEAAKPEAPEA_W@Z; ProtectedPwd::Get(wchar_t * *)
0x18002dec0  mov     edi, eax
0x18002dec2  test    eax, eax
0x18002dec4  jle     short loc_18002DECF
0x18002dec6  movzx   edi, ax
0x18002dec9  or      edi, 80070000h
0x18002decf  test    edi, edi
0x18002ded1  jns     short loc_18002DF24
0x18002ded3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002ded8  lea     rbx, [rax+28h]
0x18002dedc  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x18002dee3  lea     rcx, [rbp+37h+var_80]
0x18002dee7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002deec  nop
0x18002deed  lea     rdx, [rbp+37h+var_80]
0x18002def1  lea     rcx, [rbp+37h+var_60]
0x18002def5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002defa  nop
0x18002defb  lea     r8, [rbp+37h+var_60]
0x18002deff  lea     rdx, a0FailedToGetNe; "{0} Failed to get netname password"
0x18002df06  mov     rcx, rbx; struct cxl::TextWriter *
0x18002df09  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x18002df0e  nop
0x18002df0f  lea     rcx, [rbp+37h+var_60]
0x18002df13  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002df18  nop
0x18002df19  lea     rcx, [rbp+37h+var_80]
0x18002df1d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002df22  jmp     short loc_18002DF93
0x18002df24  mov     rdx, [rbp+37h+var_80]
0x18002df28  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002df2c  inc     rax
0x18002df2f  cmp     [rdx+rax*2], bx
0x18002df33  jnz     short loc_18002DF2C
0x18002df35  mov     [rbp+37h+var_80], rdx
0x18002df39  lea     eax, ds:2[rax*2]
0x18002df40  mov     [rbp+37h+var_78], eax
0x18002df43  mov     rcx, r15
0x18002df46  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18002df4b  mov     rbx, [rsp+0F0h+var_C0]
0x18002df50  lea     rdx, [rbx+40h]
0x18002df54  mov     rcx, [rbp+37h+var_B0]
0x18002df58  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002df5d  lea     rdx, [rbx+60h]
0x18002df61  mov     rcx, [rbp+37h+var_A8]
0x18002df65  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002df6a  mov     rdx, [rsp+0F0h+var_C0]
0x18002df6f  mov     rcx, r12
0x18002df72  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002df77  mov     rdx, [rsp+0F0h+var_C0]
0x18002df7c  add     rdx, 20h ; ' '
0x18002df80  mov     rcx, r13
0x18002df83  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002df88  nop
0x18002df89  lea     rcx, [rbp+37h+var_80]
0x18002df8d  call    ??1?$SecureAutoLdapType@_W@@QEAA@XZ; SecureAutoLdapType<wchar_t>::~SecureAutoLdapType<wchar_t>(void)
0x18002df92  nop
0x18002df93  lea     rcx, [rsp+0F0h+var_B8]
0x18002df98  call    ??1?$unique_ptr@VClusterNameADClusterState@@U?$default_delete@VClusterNameADClusterState@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusterNameADClusterState>::~unique_ptr<ClusterNameADClusterState>(void)
0x18002df9d  nop
0x18002df9e  lea     rcx, [rbp+37h+var_A0]
0x18002dfa2  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002dfa7  nop
0x18002dfa8  lea     rcx, [rbp+37h+var_90]
0x18002dfac  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002dfb1  mov     eax, edi
0x18002dfb3  mov     rcx, [rbp+37h+var_40]
0x18002dfb7  xor     rcx, rsp; StackCookie
0x18002dfba  call    __security_check_cookie
0x18002dfbf  mov     rbx, [rsp+0F0h+arg_0]
0x18002dfc7  add     rsp, 0C0h
0x18002dfce  pop     r15
0x18002dfd0  pop     r14
0x18002dfd2  pop     r13
0x18002dfd4  pop     r12
0x18002dfd6  pop     rdi
0x18002dfd7  pop     rsi
0x18002dfd8  pop     rbp
0x18002dfd9  retn
```
