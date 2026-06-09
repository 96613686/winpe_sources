# PolicyAllowList<tagEnterprisePolicy>::Populate(std::map<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>> &)

- ea: `0x1800258e0`
- end: `0x180025c48`
- name: `?Populate@?$PolicyAllowList@W4tagEnterprisePolicy@@@@QEAAJAEAV?$map@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@@std@@@Z`
- size: `872`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180012340`

## callees

- `0x18000aac0`
- `0x18000e7e4`
- `0x18000e8cc`
- `0x18000f8a8`
- `0x180010260`
- `0x18001faac`
- `0x1800258e0`
- `0x180025c50`
- `0x1800261ec`
- `0x18003002c`
- `0x180030734`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025a46`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ab9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025acc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ba4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025a46`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ab9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025acc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025b97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ba4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 PolicyAllowList<enum tagEnterprisePolicy>::Populate()
{
  void **v0; // rax
  void **v1; // rdi
  __int64 v2; // rcx
  int SlapiMdmAllowedPoliciesString; // eax
  unsigned int v4; // ebx
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // r13
  __int64 v8; // r12
  __int64 v9; // rbx
  const wchar_t *v10; // rdx
  __int64 v11; // rax
  size_t v12; // r8
  const wchar_t *v13; // rcx
  __int64 *v14; // rbx
  const wchar_t *v15; // rcx
  unsigned __int64 v16; // rsi
  size_t v17; // r8
  const WCHAR *v18; // rcx
  __int64 i; // rsi
  const wchar_t *v20; // rdx
  size_t v21; // r14
  const wchar_t *v22; // rcx
  size_t v23; // r15
  size_t v24; // r8
  const WCHAR *v25; // rsi
  __int64 **v26; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  __int128 v30; // [rsp+20h] [rbp-60h] BYREF
  __int64 v31; // [rsp+30h] [rbp-50h]
  int v32; // [rsp+38h] [rbp-48h] BYREF
  wchar_t *S2[2]; // [rsp+40h] [rbp-40h] BYREF
  size_t N; // [rsp+50h] [rbp-30h]
  unsigned __int64 v35; // [rsp+58h] [rbp-28h]
  char v36; // [rsp+60h] [rbp-20h]
  void **v37; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v0 = (void **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v1 = v0;
  if ( v0 )
  {
    *(_OWORD *)v0 = 0;
    v0[2] = 0;
    v0[3] = (void *)7;
    *(_WORD *)v0 = 0;
  }
  else
  {
    v1 = 0;
  }
  v37 = v1;
  v30 = 0;
  v31 = 0;
  if ( !(_BYTE)word_18004EF30 )
  {
    std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::merge<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>(&qword_18004EF38);
    SlapiMdmAllowedPoliciesString = PolicyAllowList<enum tagEnterprisePolicy>::GetSlapiMdmAllowedPoliciesString(v2, v1);
    v4 = SlapiMdmAllowedPoliciesString;
    if ( SlapiMdmAllowedPoliciesString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyAllowList.cpp",
        (const char *)(unsigned int)SlapiMdmAllowedPoliciesString,
        v30);
      goto LABEL_60;
    }
    v5 = PolicyHelpers::Tokenize(&v32, v1);
    v6 = 0;
    if ( &v30 == (__int128 *)v5 )
    {
      v8 = *((_QWORD *)&v30 + 1);
      v7 = v30;
    }
    else
    {
      std::vector<std::wstring>::_Tidy(&v30);
      v7 = *(_QWORD *)v5;
      *(_QWORD *)&v30 = *(_QWORD *)v5;
      v6 = *(_QWORD *)(v5 + 8);
      v8 = v6;
      *((_QWORD *)&v30 + 1) = v6;
      v31 = *(_QWORD *)(v5 + 16);
      *(_QWORD *)v5 = 0;
      *(_QWORD *)(v5 + 8) = 0;
      *(_QWORD *)(v5 + 16) = 0;
    }
    std::vector<std::wstring>::_Tidy(&v32);
    v9 = v7;
    if ( v7 != v6 )
    {
      v10 = EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName;
      do
      {
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
        v12 = *(_QWORD *)(v9 + 16);
        v13 = (const wchar_t *)v9;
        if ( *(_QWORD *)(v9 + 24) > 7u )
          v13 = *(const wchar_t **)v9;
        if ( v12 == v11 )
        {
          if ( !v12 || !wmemcmp(v13, v10, v12) )
            break;
          v10 = EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName;
        }
        v9 += 32;
      }
      while ( v9 != v6 );
    }
    if ( v9 == v8 )
    {
      v14 = *(__int64 **)qword_18004EF38;
      if ( !*(_BYTE *)(*(_QWORD *)qword_18004EF38 + 25LL) )
      {
        do
        {
          v15 = (const wchar_t *)(v14 + 5);
          v16 = v14[7];
          if ( (unsigned __int64)v14[8] > 7 )
            v15 = *(const wchar_t **)v15;
          v17 = v14[7];
          if ( v16 > 4 )
            v17 = 4;
          if ( !wmemcmp(v15, L"None", v17) && v16 == 4 )
          {
            v25 = (const WCHAR *)(v14 + 5);
            *((_BYTE *)v14 + 72) = 1;
            OutputDebugStringW(L"Allowing aggregated policy by default: ");
            if ( (unsigned __int64)v14[8] > 7 )
              v25 = *(const WCHAR **)v25;
            OutputDebugStringW(v25);
            OutputDebugStringW(L"\n");
          }
          else
          {
            OutputDebugStringW(L"Search result for policy in SLAPI allow list: ");
            v18 = (const WCHAR *)(v14 + 5);
            if ( (unsigned __int64)v14[8] > 7 )
              v18 = (const WCHAR *)v14[5];
            OutputDebugStringW(v18);
            v32 = *((_DWORD *)v14 + 8);
            std::wstring::wstring((__int64)S2, (__int64)(v14 + 5));
            v36 = *((_BYTE *)v14 + 72);
            for ( i = v7; i != v8; i += 32 )
            {
              v20 = (const wchar_t *)S2;
              if ( v35 > 7 )
                v20 = S2[0];
              v21 = *(_QWORD *)(i + 16);
              v22 = (const wchar_t *)i;
              if ( *(_QWORD *)(i + 24) > 7u )
                v22 = *(const wchar_t **)i;
              v23 = N;
              v24 = *(_QWORD *)(i + 16);
              if ( N < v21 )
                v24 = N;
              if ( !wmemcmp(v22, v20, v24) && v21 >= v23 && v21 <= v23 )
                break;
            }
            std::wstring::~wstring(S2);
            if ( i == v8 )
            {
              OutputDebugStringW(L",--NOT FOUND\n");
              *((_BYTE *)v14 + 72) = 0;
            }
            else
            {
              OutputDebugStringW(L"++FOUND\n");
              *((_BYTE *)v14 + 72) = 1;
            }
          }
          v26 = (__int64 **)v14[2];
          if ( *((_BYTE *)v26 + 25) )
          {
            for ( j = (__int64 *)v14[1]; !*((_BYTE *)j + 25) && v14 == (__int64 *)j[2]; j = (__int64 *)j[1] )
              v14 = j;
            v14 = j;
          }
          else
          {
            v14 = (__int64 *)v14[2];
            for ( k = *v26; !*((_BYTE *)k + 25); k = (__int64 *)*k )
              v14 = k;
          }
        }
        while ( !*((_BYTE *)v14 + 25) );
      }
      LOBYTE(word_18004EF30) = 1;
    }
    else
    {
      OutputDebugStringW(L"All policies are allowed\n");
      word_18004EF30 = 257;
    }
  }
  v4 = 0;
LABEL_60:
  std::vector<std::wstring>::_Tidy(&v30);
  if ( v1 )
  {
    std::wstring::~wstring(v1);
    operator delete(v1);
  }
  return v4;
}

```

## disassembly

```asm
0x1800258e0  mov     [rsp-28h+arg_0], rbx
0x1800258e5  mov     [rsp-28h+arg_8], rsi
0x1800258ea  mov     [rsp-28h+arg_10], rdi
0x1800258ef  push    rbp
0x1800258f0  push    r12
0x1800258f2  push    r13
0x1800258f4  push    r14
0x1800258f6  push    r15
0x1800258f8  mov     rbp, rsp
0x1800258fb  sub     rsp, 80h
0x180025902  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025909  mov     ecx, 20h ; ' '; unsigned __int64
0x18002590e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025913  mov     rdi, rax
0x180025916  xor     r15d, r15d
0x180025919  test    rax, rax
0x18002591c  jz      short loc_180025936
0x18002591e  xorps   xmm0, xmm0
0x180025921  movups  xmmword ptr [rax], xmm0
0x180025924  mov     [rax+10h], r15
0x180025928  mov     qword ptr [rax+18h], 7
0x180025930  mov     [rax], r15w
0x180025934  jmp     short loc_180025939
0x180025936  mov     rdi, r15
0x180025939  mov     [rbp+var_18], rdi
0x18002593d  xorps   xmm1, xmm1
0x180025940  movdqu  [rbp+var_60], xmm1
0x180025945  mov     [rbp+var_50], r15
0x180025949  cmp     byte ptr cs:word_18004EF30, r15b
0x180025950  jnz     loc_180025BFE
0x180025956  lea     rcx, qword_18004EF38
0x18002595d  call    ??$merge@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAAXAEAV01@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::merge<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>(std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>> &)
0x180025962  mov     rdx, rdi
0x180025965  call    ?GetSlapiMdmAllowedPoliciesString@?$PolicyAllowList@W4tagEnterprisePolicy@@@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; PolicyAllowList<tagEnterprisePolicy>::GetSlapiMdmAllowedPoliciesString(std::wstring &)
0x18002596a  mov     ebx, eax
0x18002596c  test    eax, eax
0x18002596e  jns     short loc_18002598D
0x180025970  mov     rcx, [rbp+28h]; this
0x180025974  mov     r9d, eax; char *
0x180025977  lea     r8, aCW1SSrcClientP_6; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18002597e  mov     edx, 3Dh ; '='; void *
0x180025983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025988  jmp     loc_180025C01
0x18002598d  mov     rdx, rdi
0x180025990  lea     rcx, [rbp+var_48]
0x180025994  call    ?Tokenize@PolicyHelpers@@SA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@_W@Z; PolicyHelpers::Tokenize(std::wstring const &,wchar_t)
0x180025999  mov     rbx, rax
0x18002599c  mov     rsi, r15
0x18002599f  lea     rax, [rbp+var_60]
0x1800259a3  cmp     rax, rbx
0x1800259a6  jz      short loc_1800259D8
0x1800259a8  lea     rcx, [rbp+var_60]
0x1800259ac  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800259b1  mov     r13, [rbx]
0x1800259b4  mov     qword ptr [rbp+var_60], r13
0x1800259b8  mov     rsi, [rbx+8]
0x1800259bc  mov     r12, rsi
0x1800259bf  mov     qword ptr [rbp+var_60+8], rsi
0x1800259c3  mov     rax, [rbx+10h]
0x1800259c7  mov     [rbp+var_50], rax
0x1800259cb  mov     [rbx], r15
0x1800259ce  mov     [rbx+8], r15
0x1800259d2  mov     [rbx+10h], r15
0x1800259d6  jmp     short loc_1800259E0
0x1800259d8  mov     r12, qword ptr [rbp+var_60+8]
0x1800259dc  mov     r13, qword ptr [rbp+var_60]
0x1800259e0  lea     rcx, [rbp+var_48]
0x1800259e4  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800259e9  mov     rbx, r13
0x1800259ec  cmp     r13, rsi
0x1800259ef  jz      short loc_180025A3A
0x1800259f1  mov     rdx, cs:?c_szPolicy_CspUpdateAreaName@EnterprisePolicyReader@@2QEB_WEB; S2
0x1800259f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800259fc  inc     rax
0x1800259ff  cmp     [rdx+rax*2], r15w
0x180025a04  jnz     short loc_1800259FC
0x180025a06  mov     r8, [rbx+10h]; N
0x180025a0a  mov     rcx, rbx
0x180025a0d  cmp     qword ptr [rbx+18h], 7
0x180025a12  jbe     short loc_180025A17
0x180025a14  mov     rcx, [rbx]; S1
0x180025a17  cmp     r8, rax
0x180025a1a  jnz     short loc_180025A31
0x180025a1c  test    r8, r8
0x180025a1f  jz      short loc_180025A3A
0x180025a21  call    wmemcmp
0x180025a26  test    eax, eax
0x180025a28  jz      short loc_180025A3A
0x180025a2a  mov     rdx, cs:?c_szPolicy_CspUpdateAreaName@EnterprisePolicyReader@@2QEB_WEB; wchar_t const * const EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName
0x180025a31  add     rbx, 20h ; ' '
0x180025a35  cmp     rbx, rsi
0x180025a38  jnz     short loc_1800259F8
0x180025a3a  cmp     rbx, r12
0x180025a3d  jz      short loc_180025A5A
0x180025a3f  lea     rcx, aAllPoliciesAre; "All policies are allowed\n"
0x180025a46  call    cs:__imp_OutputDebugStringW
0x180025a4c  mov     cs:word_18004EF30, 101h
0x180025a55  jmp     loc_180025BFE
0x180025a5a  mov     rbx, cs:qword_18004EF38
0x180025a61  mov     rbx, [rbx]
0x180025a64  cmp     [rbx+19h], r15b
0x180025a68  jnz     loc_180025BF7
0x180025a6e  mov     r14d, 4
0x180025a74  lea     rcx, [rbx+28h]
0x180025a78  mov     rsi, [rbx+38h]
0x180025a7c  cmp     qword ptr [rcx+18h], 7
0x180025a81  jbe     short loc_180025A86
0x180025a83  mov     rcx, [rcx]; S1
0x180025a86  mov     r8, rsi
0x180025a89  cmp     rsi, r14
0x180025a8c  cmova   r8, r14; N
0x180025a90  lea     rdx, aNone; "None"
0x180025a97  call    wmemcmp
0x180025a9c  test    eax, eax
0x180025a9e  jnz     short loc_180025AAB
0x180025aa0  cmp     rsi, r14
0x180025aa3  jb      short loc_180025AAB
0x180025aa5  jbe     loc_180025B75
0x180025aab  lea     rsi, [rbx+28h]
0x180025aaf  mov     r14, rsi
0x180025ab2  lea     rcx, aSearchResultFo; "Search result for policy in SLAPI allow"...
0x180025ab9  call    cs:__imp_OutputDebugStringW
0x180025abf  mov     rcx, rsi
0x180025ac2  cmp     qword ptr [rsi+18h], 7
0x180025ac7  jbe     short loc_180025ACC
0x180025ac9  mov     rcx, [rsi]; lpOutputString
0x180025acc  call    cs:__imp_OutputDebugStringW
0x180025ad2  mov     eax, [rbx+20h]
0x180025ad5  mov     [rbp+var_48], eax
0x180025ad8  mov     rdx, rsi
0x180025adb  lea     rcx, [rbp+S2]
0x180025adf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025ae4  mov     al, [rbx+48h]
0x180025ae7  mov     [rbp+var_20], al
0x180025aea  mov     rsi, r13
0x180025aed  cmp     r13, r12
0x180025af0  jz      short loc_180025B3B
0x180025af2  lea     rdx, [rbp+S2]
0x180025af6  cmp     [rbp+var_28], 7
0x180025afb  cmova   rdx, [rbp+S2]; S2
0x180025b00  mov     r14, [rsi+10h]
0x180025b04  mov     rcx, rsi
0x180025b07  cmp     qword ptr [rsi+18h], 7
0x180025b0c  jbe     short loc_180025B11
0x180025b0e  mov     rcx, [rsi]; S1
0x180025b11  mov     r15, [rbp+N]
0x180025b15  mov     r8, r14
0x180025b18  cmp     r15, r14
0x180025b1b  cmovb   r8, r15; N
0x180025b1f  call    wmemcmp
0x180025b24  test    eax, eax
0x180025b26  jnz     short loc_180025B2F
0x180025b28  cmp     r14, r15
0x180025b2b  jb      short loc_180025B2F
0x180025b2d  jbe     short loc_180025B38
0x180025b2f  add     rsi, 20h ; ' '
0x180025b33  cmp     rsi, r12
0x180025b36  jnz     short loc_180025AF2
0x180025b38  xor     r15d, r15d
0x180025b3b  lea     rcx, [rbp+S2]; void *
0x180025b3f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025b44  cmp     rsi, r12
0x180025b47  jnz     short loc_180025B62
0x180025b49  lea     rcx, aNotFound; ",--NOT FOUND\n"
0x180025b50  call    cs:__imp_OutputDebugStringW
0x180025b56  mov     [rbx+48h], r15b
0x180025b5a  mov     r14d, 4
0x180025b60  jmp     short loc_180025BAA
0x180025b62  lea     rcx, aFound; "++FOUND\n"
0x180025b69  call    cs:__imp_OutputDebugStringW
0x180025b6f  mov     byte ptr [rbx+48h], 1
0x180025b73  jmp     short loc_180025B5A
0x180025b75  lea     rsi, [rbx+28h]
0x180025b79  mov     byte ptr [rsi+20h], 1
0x180025b7d  lea     rcx, aAllowingAggreg; "Allowing aggregated policy by default: "
0x180025b84  call    cs:__imp_OutputDebugStringW
0x180025b8a  cmp     qword ptr [rbx+40h], 7
0x180025b8f  jbe     short loc_180025B94
0x180025b91  mov     rsi, [rsi]
0x180025b94  mov     rcx, rsi; lpOutputString
0x180025b97  call    cs:__imp_OutputDebugStringW
0x180025b9d  lea     rcx, asc_18003C448; "\n"
0x180025ba4  call    cs:__imp_OutputDebugStringW
0x180025baa  mov     rcx, [rbx+10h]
0x180025bae  cmp     [rcx+19h], r15b
0x180025bb2  jz      short loc_180025BD2
0x180025bb4  mov     rax, [rbx+8]
0x180025bb8  jmp     short loc_180025BC7
0x180025bba  cmp     rbx, [rax+10h]
0x180025bbe  jnz     short loc_180025BCD
0x180025bc0  mov     rbx, rax
0x180025bc3  mov     rax, [rax+8]
0x180025bc7  cmp     [rax+19h], r15b
0x180025bcb  jz      short loc_180025BBA
0x180025bcd  mov     rbx, rax
0x180025bd0  jmp     short loc_180025BED
0x180025bd2  mov     rbx, rcx
0x180025bd5  mov     rcx, [rcx]
0x180025bd8  cmp     [rcx+19h], r15b
0x180025bdc  jnz     short loc_180025BED
0x180025bde  mov     rbx, rcx
0x180025be1  mov     rax, [rcx]
0x180025be4  mov     rcx, rax
0x180025be7  cmp     [rax+19h], r15b
0x180025beb  jz      short loc_180025BDE
0x180025bed  cmp     [rbx+19h], r15b
0x180025bf1  jz      loc_180025A74
0x180025bf7  mov     byte ptr cs:word_18004EF30, 1
0x180025bfe  mov     ebx, r15d
0x180025c01  lea     rcx, [rbp+var_60]
0x180025c05  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180025c0a  nop
0x180025c0b  test    rdi, rdi
0x180025c0e  jz      short loc_180025C25
0x180025c10  mov     rcx, rdi; void *
0x180025c13  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025c18  mov     edx, 20h ; ' '
0x180025c1d  mov     rcx, rdi; Block
0x180025c20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025c25  mov     eax, ebx
0x180025c27  lea     r11, [rsp+80h+var_s0]
0x180025c2f  mov     rbx, [r11+30h]
0x180025c33  mov     rsi, [r11+38h]
0x180025c37  mov     rdi, [r11+40h]
0x180025c3b  mov     rsp, r11
0x180025c3e  pop     r15
0x180025c40  pop     r14
0x180025c42  pop     r13
0x180025c44  pop     r12
0x180025c46  pop     rbp
0x180025c47  retn
```
