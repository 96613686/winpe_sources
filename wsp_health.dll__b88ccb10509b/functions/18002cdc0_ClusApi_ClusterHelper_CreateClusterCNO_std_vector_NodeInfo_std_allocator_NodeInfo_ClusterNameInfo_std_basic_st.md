# ClusApi::ClusterHelper::CreateClusterCNO(std::vector<_NodeInfo,std::allocator<_NodeInfo>> &,_ClusterNameInfo &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18002cdc0`
- end: `0x18002d0d4`
- name: `?CreateClusterCNO@ClusterHelper@ClusApi@@UEAAJAEAV?$vector@U_NodeInfo@@V?$allocator@U_NodeInfo@@@std@@@std@@AEAU_ClusterNameInfo@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@2222@Z`
- size: `788`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x180002ae0`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000cfb4`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000f3e8`
- `0x1800112f0`
- `0x18002b050`
- `0x18002b08c`
- `0x18002c060`
- `0x18002c218`
- `0x18002cdc0`
- `0x18002ddc8`
- `0x1800424d8`
- `0x180042adc`

## import_xrefs

- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x18002cf21`
- `CLUSAPI!CCHlpCreateClusterNameInAD` at `0x18002cf21`

## string_xrefs

- `0x18002ce53`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x18002cf4f`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x18002cfd6`: `ClusApi::ClusterHelper::CreateClusterCNO`
- `0x18002cf75`: `{0} Failed to create cluster name in AD {1}`

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
    string = cxl::load_string(v39, qword_1801578A0, 2006);
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
0x18002cdc0  mov     [rsp-8+arg_0], rbx
0x18002cdc5  push    rbp
0x18002cdc6  push    rsi
0x18002cdc7  push    rdi
0x18002cdc8  push    r12
0x18002cdca  push    r13
0x18002cdcc  push    r14
0x18002cdce  push    r15
0x18002cdd0  lea     rbp, [rsp-7]
0x18002cdd5  sub     rsp, 0C0h
0x18002cddc  mov     rax, cs:__security_cookie
0x18002cde3  xor     rax, rsp
0x18002cde6  mov     [rbp+37h+var_40], rax
0x18002cdea  mov     r15, r9
0x18002cded  mov     rsi, r8
0x18002cdf0  mov     r14, rdx
0x18002cdf3  mov     r12, [rbp+37h+arg_20]
0x18002cdf7  mov     r13, [rbp+37h+arg_28]
0x18002cdfb  mov     rax, [rbp+37h+arg_30]
0x18002cdff  mov     [rbp+37h+var_B0], rax
0x18002ce03  mov     rax, [rbp+37h+arg_38]
0x18002ce07  mov     [rbp+37h+var_A8], rax
0x18002ce0b  xor     ebx, ebx
0x18002ce0d  mov     [rsp+0F0h+var_B8], rbx
0x18002ce12  mov     [rbp+37h+var_80], rbx
0x18002ce16  mov     [rbp+37h+var_88], rbx
0x18002ce1a  mov     [rbp+37h+var_98], rbx
0x18002ce1e  mov     rcx, r8
0x18002ce21  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ce26  lea     r8, [rbp+37h+var_80]
0x18002ce2a  lea     rdx, [rsp+0F0h+var_B8]
0x18002ce2f  mov     rcx, rax
0x18002ce32  call    ClRtlParseDistinguishedName
0x18002ce37  mov     edi, eax
0x18002ce39  test    eax, eax
0x18002ce3b  jle     short loc_18002CE46
0x18002ce3d  movzx   edi, ax
0x18002ce40  or      edi, 80070000h
0x18002ce46  test    edi, edi
0x18002ce48  jns     short loc_18002CEA1
0x18002ce4a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002ce4f  lea     rbx, [rax+28h]
0x18002ce53  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x18002ce5a  lea     rcx, [rbp+37h+var_60]
0x18002ce5e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ce63  nop
0x18002ce64  lea     rdx, [rbp+37h+var_60]
0x18002ce68  lea     rcx, [rbp+37h+var_80]
0x18002ce6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ce71  nop
0x18002ce72  mov     r9, rsi
0x18002ce75  lea     r8, [rbp+37h+var_80]
0x18002ce79  lea     rdx, a0UnableToParse; "{0} Unable to parse cluster name {1}"
0x18002ce80  mov     rcx, rbx; struct cxl::TextWriter *
0x18002ce83  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x18002ce88  nop
0x18002ce89  lea     rcx, [rbp+37h+var_80]
0x18002ce8d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce92  nop
0x18002ce93  lea     rcx, [rbp+37h+var_60]
0x18002ce97  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce9c  jmp     loc_18002D098
0x18002cea1  mov     rsi, rbx
0x18002cea4  mov     rbx, [rsp+0F0h+var_B8]
0x18002cea9  test    rbx, rbx
0x18002ceac  jz      short loc_18002CEBE
0x18002ceae  lea     rcx, [rbp+37h+var_90]
0x18002ceb2  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002ceb7  mov     [rbp+37h+var_88], rbx
0x18002cebb  mov     rsi, rbx
0x18002cebe  xor     edi, edi
0x18002cec0  mov     rbx, [rbp+37h+var_80]
0x18002cec4  test    rbx, rbx
0x18002cec7  jz      short loc_18002CED9
0x18002cec9  lea     rcx, [rbp+37h+var_A0]
0x18002cecd  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002ced2  mov     [rbp+37h+var_98], rbx
0x18002ced6  mov     rdi, rbx
0x18002ced9  xor     ebx, ebx
0x18002cedb  mov     [rsp+0F0h+var_C0], rbx
0x18002cee0  mov     r8d, 7D6h
0x18002cee6  mov     rdx, cs:qword_1801578A0
0x18002ceed  lea     rcx, [rbp+37h+var_60]
0x18002cef1  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18002cef6  nop
0x18002cef7  mov     rcx, rax
0x18002cefa  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ceff  mov     r9, rax
0x18002cf02  mov     rcx, [r14]
0x18002cf05  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cf0a  lea     rcx, [rsp+0F0h+var_C0]
0x18002cf0f  mov     [rsp+0F0h+var_C8], rcx
0x18002cf14  mov     [rsp+0F0h+var_D0], ebx
0x18002cf18  mov     r8, rdi
0x18002cf1b  mov     rdx, rsi
0x18002cf1e  mov     rcx, rax
0x18002cf21  call    cs:__imp_?CCHlpCreateClusterNameInAD@@YAKPEB_W000HPEAPEAVClusterNameADClusterState@@@Z; CCHlpCreateClusterNameInAD(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,ClusterNameADClusterState * *)
0x18002cf27  mov     esi, eax
0x18002cf29  test    eax, eax
0x18002cf2b  jle     short loc_18002CF36
0x18002cf2d  movzx   esi, ax
0x18002cf30  or      esi, 80070000h
0x18002cf36  lea     rcx, [rbp+37h+var_60]
0x18002cf3a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cf3f  test    esi, esi
0x18002cf41  jns     short loc_18002CF9F
0x18002cf43  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002cf48  lea     rdi, [rax+28h]
0x18002cf4c  mov     rbx, [r14]
0x18002cf4f  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x18002cf56  lea     rcx, [rbp+37h+var_80]
0x18002cf5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002cf5f  nop
0x18002cf60  lea     rdx, [rbp+37h+var_80]
0x18002cf64  lea     rcx, [rbp+37h+var_60]
0x18002cf68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cf6d  nop
0x18002cf6e  mov     r9, rbx
0x18002cf71  lea     r8, [rbp+37h+var_60]
0x18002cf75  lea     rdx, a0FailedToCreat; "{0} Failed to create cluster name in AD"...
0x18002cf7c  mov     rcx, rdi; struct cxl::TextWriter *
0x18002cf7f  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring>(char const *,TraceFunction const &,std::wstring const &)
0x18002cf84  nop
0x18002cf85  lea     rcx, [rbp+37h+var_60]
0x18002cf89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cf8e  nop
0x18002cf8f  lea     rcx, [rbp+37h+var_80]
0x18002cf93  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cf98  mov     edi, esi
0x18002cf9a  jmp     loc_18002D098
0x18002cf9f  mov     rcx, [rsp+0F0h+var_C0]
0x18002cfa4  mov     [rsp+0F0h+var_B8], rcx
0x18002cfa9  mov     [rbp+37h+var_80], rbx
0x18002cfad  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x18002cfb1  lea     rdx, [rbp+37h+var_80]; wchar_t **
0x18002cfb5  call    ?Get@ProtectedPwd@@QEAAKPEAPEA_W@Z; ProtectedPwd::Get(wchar_t * *)
0x18002cfba  mov     edi, eax
0x18002cfbc  test    eax, eax
0x18002cfbe  jle     short loc_18002CFC9
0x18002cfc0  movzx   edi, ax
0x18002cfc3  or      edi, 80070000h
0x18002cfc9  test    edi, edi
0x18002cfcb  jns     short loc_18002D01E
0x18002cfcd  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18002cfd2  lea     rbx, [rax+28h]
0x18002cfd6  lea     rdx, aClusapiCluster; "ClusApi::ClusterHelper::CreateClusterCN"...
0x18002cfdd  lea     rcx, [rbp+37h+var_80]
0x18002cfe1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002cfe6  nop
0x18002cfe7  lea     rdx, [rbp+37h+var_80]
0x18002cfeb  lea     rcx, [rbp+37h+var_60]
0x18002cfef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cff4  nop
0x18002cff5  lea     r8, [rbp+37h+var_60]
0x18002cff9  lea     rdx, a0FailedToGetNe; "{0} Failed to get netname password"
0x18002d000  mov     rcx, rbx; struct cxl::TextWriter *
0x18002d003  call    ??$WriteLine@DUTraceFunction@@$$V@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@@Z; cxl::TextWriter::WriteLine<char,TraceFunction,>(char const *,TraceFunction const &)
0x18002d008  nop
0x18002d009  lea     rcx, [rbp+37h+var_60]
0x18002d00d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d012  nop
0x18002d013  lea     rcx, [rbp+37h+var_80]
0x18002d017  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d01c  jmp     short loc_18002D08D
0x18002d01e  mov     rdx, [rbp+37h+var_80]
0x18002d022  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d026  inc     rax
0x18002d029  cmp     [rdx+rax*2], bx
0x18002d02d  jnz     short loc_18002D026
0x18002d02f  mov     [rbp+37h+var_80], rdx
0x18002d033  lea     eax, ds:2[rax*2]
0x18002d03a  mov     [rbp+37h+var_78], eax
0x18002d03d  mov     rcx, r15
0x18002d040  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18002d045  mov     rbx, [rsp+0F0h+var_C0]
0x18002d04a  lea     rdx, [rbx+40h]
0x18002d04e  mov     rcx, [rbp+37h+var_B0]
0x18002d052  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d057  lea     rdx, [rbx+60h]
0x18002d05b  mov     rcx, [rbp+37h+var_A8]
0x18002d05f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d064  mov     rdx, [rsp+0F0h+var_C0]
0x18002d069  mov     rcx, r12
0x18002d06c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d071  mov     rdx, [rsp+0F0h+var_C0]
0x18002d076  add     rdx, 20h ; ' '
0x18002d07a  mov     rcx, r13
0x18002d07d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d082  nop
0x18002d083  lea     rcx, [rbp+37h+var_80]
0x18002d087  call    ??1?$SecureAutoLdapType@_W@@QEAA@XZ; SecureAutoLdapType<wchar_t>::~SecureAutoLdapType<wchar_t>(void)
0x18002d08c  nop
0x18002d08d  lea     rcx, [rsp+0F0h+var_B8]
0x18002d092  call    ??1?$unique_ptr@VClusterNameADClusterState@@U?$default_delete@VClusterNameADClusterState@@@std@@@std@@QEAA@XZ; std::unique_ptr<ClusterNameADClusterState>::~unique_ptr<ClusterNameADClusterState>(void)
0x18002d097  nop
0x18002d098  lea     rcx, [rbp+37h+var_A0]
0x18002d09c  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002d0a1  nop
0x18002d0a2  lea     rcx, [rbp+37h+var_90]
0x18002d0a6  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18002d0ab  mov     eax, edi
0x18002d0ad  mov     rcx, [rbp+37h+var_40]
0x18002d0b1  xor     rcx, rsp; StackCookie
0x18002d0b4  call    __security_check_cookie
0x18002d0b9  mov     rbx, [rsp+0F0h+arg_0]
0x18002d0c1  add     rsp, 0C0h
0x18002d0c8  pop     r15
0x18002d0ca  pop     r14
0x18002d0cc  pop     r13
0x18002d0ce  pop     r12
0x18002d0d0  pop     rdi
0x18002d0d1  pop     rsi
0x18002d0d2  pop     rbp
0x18002d0d3  retn
```
