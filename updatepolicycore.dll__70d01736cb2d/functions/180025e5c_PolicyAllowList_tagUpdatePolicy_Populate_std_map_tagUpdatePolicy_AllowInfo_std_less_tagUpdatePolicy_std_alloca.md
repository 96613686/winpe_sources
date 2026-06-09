# PolicyAllowList<tagUpdatePolicy>::Populate(std::map<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>> &)

- ea: `0x180025e5c`
- end: `0x1800261c4`
- name: `?Populate@?$PolicyAllowList@W4tagUpdatePolicy@@@@QEAAJAEAV?$map@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@@std@@@Z`
- size: `872`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18001a5ac`

## callees

- `0x18000aac0`
- `0x18000e7e4`
- `0x18000e8cc`
- `0x18000f8a8`
- `0x180010260`
- `0x18001faac`
- `0x180025c50`
- `0x180025e5c`
- `0x180026328`
- `0x18003002c`
- `0x180030734`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025fc2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026035`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800260cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800260e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026100`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026113`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026120`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025fc2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026035`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800260cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800260e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026100`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026113`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026120`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 PolicyAllowList<enum tagUpdatePolicy>::Populate()
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
  if ( !(_BYTE)word_18004EF80 )
  {
    std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::merge<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>(&qword_18004EF88);
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
      v14 = *(__int64 **)qword_18004EF88;
      if ( !*(_BYTE *)(*(_QWORD *)qword_18004EF88 + 25LL) )
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
      LOBYTE(word_18004EF80) = 1;
    }
    else
    {
      OutputDebugStringW(L"All policies are allowed\n");
      word_18004EF80 = 257;
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
0x180025e5c  mov     [rsp-28h+arg_0], rbx
0x180025e61  mov     [rsp-28h+arg_8], rsi
0x180025e66  mov     [rsp-28h+arg_10], rdi
0x180025e6b  push    rbp
0x180025e6c  push    r12
0x180025e6e  push    r13
0x180025e70  push    r14
0x180025e72  push    r15
0x180025e74  mov     rbp, rsp
0x180025e77  sub     rsp, 80h
0x180025e7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025e85  mov     ecx, 20h ; ' '; unsigned __int64
0x180025e8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025e8f  mov     rdi, rax
0x180025e92  xor     r15d, r15d
0x180025e95  test    rax, rax
0x180025e98  jz      short loc_180025EB2
0x180025e9a  xorps   xmm0, xmm0
0x180025e9d  movups  xmmword ptr [rax], xmm0
0x180025ea0  mov     [rax+10h], r15
0x180025ea4  mov     qword ptr [rax+18h], 7
0x180025eac  mov     [rax], r15w
0x180025eb0  jmp     short loc_180025EB5
0x180025eb2  mov     rdi, r15
0x180025eb5  mov     [rbp+var_18], rdi
0x180025eb9  xorps   xmm1, xmm1
0x180025ebc  movdqu  [rbp+var_60], xmm1
0x180025ec1  mov     [rbp+var_50], r15
0x180025ec5  cmp     byte ptr cs:word_18004EF80, r15b
0x180025ecc  jnz     loc_18002617A
0x180025ed2  lea     rcx, qword_18004EF88
0x180025ed9  call    ??$merge@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAAXAEAV01@@Z; std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::merge<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>(std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>> &)
0x180025ede  mov     rdx, rdi
0x180025ee1  call    ?GetSlapiMdmAllowedPoliciesString@?$PolicyAllowList@W4tagEnterprisePolicy@@@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; PolicyAllowList<tagEnterprisePolicy>::GetSlapiMdmAllowedPoliciesString(std::wstring &)
0x180025ee6  mov     ebx, eax
0x180025ee8  test    eax, eax
0x180025eea  jns     short loc_180025F09
0x180025eec  mov     rcx, [rbp+28h]; this
0x180025ef0  mov     r9d, eax; char *
0x180025ef3  lea     r8, aCW1SSrcClientP_6; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180025efa  mov     edx, 3Dh ; '='; void *
0x180025eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f04  jmp     loc_18002617D
0x180025f09  mov     rdx, rdi
0x180025f0c  lea     rcx, [rbp+var_48]
0x180025f10  call    ?Tokenize@PolicyHelpers@@SA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@_W@Z; PolicyHelpers::Tokenize(std::wstring const &,wchar_t)
0x180025f15  mov     rbx, rax
0x180025f18  mov     rsi, r15
0x180025f1b  lea     rax, [rbp+var_60]
0x180025f1f  cmp     rax, rbx
0x180025f22  jz      short loc_180025F54
0x180025f24  lea     rcx, [rbp+var_60]
0x180025f28  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180025f2d  mov     r13, [rbx]
0x180025f30  mov     qword ptr [rbp+var_60], r13
0x180025f34  mov     rsi, [rbx+8]
0x180025f38  mov     r12, rsi
0x180025f3b  mov     qword ptr [rbp+var_60+8], rsi
0x180025f3f  mov     rax, [rbx+10h]
0x180025f43  mov     [rbp+var_50], rax
0x180025f47  mov     [rbx], r15
0x180025f4a  mov     [rbx+8], r15
0x180025f4e  mov     [rbx+10h], r15
0x180025f52  jmp     short loc_180025F5C
0x180025f54  mov     r12, qword ptr [rbp+var_60+8]
0x180025f58  mov     r13, qword ptr [rbp+var_60]
0x180025f5c  lea     rcx, [rbp+var_48]
0x180025f60  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180025f65  mov     rbx, r13
0x180025f68  cmp     r13, rsi
0x180025f6b  jz      short loc_180025FB6
0x180025f6d  mov     rdx, cs:?c_szPolicy_CspUpdateAreaName@EnterprisePolicyReader@@2QEB_WEB; S2
0x180025f74  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025f78  inc     rax
0x180025f7b  cmp     [rdx+rax*2], r15w
0x180025f80  jnz     short loc_180025F78
0x180025f82  mov     r8, [rbx+10h]; N
0x180025f86  mov     rcx, rbx
0x180025f89  cmp     qword ptr [rbx+18h], 7
0x180025f8e  jbe     short loc_180025F93
0x180025f90  mov     rcx, [rbx]; S1
0x180025f93  cmp     r8, rax
0x180025f96  jnz     short loc_180025FAD
0x180025f98  test    r8, r8
0x180025f9b  jz      short loc_180025FB6
0x180025f9d  call    wmemcmp
0x180025fa2  test    eax, eax
0x180025fa4  jz      short loc_180025FB6
0x180025fa6  mov     rdx, cs:?c_szPolicy_CspUpdateAreaName@EnterprisePolicyReader@@2QEB_WEB; wchar_t const * const EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName
0x180025fad  add     rbx, 20h ; ' '
0x180025fb1  cmp     rbx, rsi
0x180025fb4  jnz     short loc_180025F74
0x180025fb6  cmp     rbx, r12
0x180025fb9  jz      short loc_180025FD6
0x180025fbb  lea     rcx, aAllPoliciesAre; "All policies are allowed\n"
0x180025fc2  call    cs:__imp_OutputDebugStringW
0x180025fc8  mov     cs:word_18004EF80, 101h
0x180025fd1  jmp     loc_18002617A
0x180025fd6  mov     rbx, cs:qword_18004EF88
0x180025fdd  mov     rbx, [rbx]
0x180025fe0  cmp     [rbx+19h], r15b
0x180025fe4  jnz     loc_180026173
0x180025fea  mov     r14d, 4
0x180025ff0  lea     rcx, [rbx+28h]
0x180025ff4  mov     rsi, [rbx+38h]
0x180025ff8  cmp     qword ptr [rcx+18h], 7
0x180025ffd  jbe     short loc_180026002
0x180025fff  mov     rcx, [rcx]; S1
0x180026002  mov     r8, rsi
0x180026005  cmp     rsi, r14
0x180026008  cmova   r8, r14; N
0x18002600c  lea     rdx, aNone; "None"
0x180026013  call    wmemcmp
0x180026018  test    eax, eax
0x18002601a  jnz     short loc_180026027
0x18002601c  cmp     rsi, r14
0x18002601f  jb      short loc_180026027
0x180026021  jbe     loc_1800260F1
0x180026027  lea     rsi, [rbx+28h]
0x18002602b  mov     r14, rsi
0x18002602e  lea     rcx, aSearchResultFo; "Search result for policy in SLAPI allow"...
0x180026035  call    cs:__imp_OutputDebugStringW
0x18002603b  mov     rcx, rsi
0x18002603e  cmp     qword ptr [rsi+18h], 7
0x180026043  jbe     short loc_180026048
0x180026045  mov     rcx, [rsi]; lpOutputString
0x180026048  call    cs:__imp_OutputDebugStringW
0x18002604e  mov     eax, [rbx+20h]
0x180026051  mov     [rbp+var_48], eax
0x180026054  mov     rdx, rsi
0x180026057  lea     rcx, [rbp+S2]
0x18002605b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026060  mov     al, [rbx+48h]
0x180026063  mov     [rbp+var_20], al
0x180026066  mov     rsi, r13
0x180026069  cmp     r13, r12
0x18002606c  jz      short loc_1800260B7
0x18002606e  lea     rdx, [rbp+S2]
0x180026072  cmp     [rbp+var_28], 7
0x180026077  cmova   rdx, [rbp+S2]; S2
0x18002607c  mov     r14, [rsi+10h]
0x180026080  mov     rcx, rsi
0x180026083  cmp     qword ptr [rsi+18h], 7
0x180026088  jbe     short loc_18002608D
0x18002608a  mov     rcx, [rsi]; S1
0x18002608d  mov     r15, [rbp+N]
0x180026091  mov     r8, r14
0x180026094  cmp     r15, r14
0x180026097  cmovb   r8, r15; N
0x18002609b  call    wmemcmp
0x1800260a0  test    eax, eax
0x1800260a2  jnz     short loc_1800260AB
0x1800260a4  cmp     r14, r15
0x1800260a7  jb      short loc_1800260AB
0x1800260a9  jbe     short loc_1800260B4
0x1800260ab  add     rsi, 20h ; ' '
0x1800260af  cmp     rsi, r12
0x1800260b2  jnz     short loc_18002606E
0x1800260b4  xor     r15d, r15d
0x1800260b7  lea     rcx, [rbp+S2]; void *
0x1800260bb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800260c0  cmp     rsi, r12
0x1800260c3  jnz     short loc_1800260DE
0x1800260c5  lea     rcx, aNotFound; ",--NOT FOUND\n"
0x1800260cc  call    cs:__imp_OutputDebugStringW
0x1800260d2  mov     [rbx+48h], r15b
0x1800260d6  mov     r14d, 4
0x1800260dc  jmp     short loc_180026126
0x1800260de  lea     rcx, aFound; "++FOUND\n"
0x1800260e5  call    cs:__imp_OutputDebugStringW
0x1800260eb  mov     byte ptr [rbx+48h], 1
0x1800260ef  jmp     short loc_1800260D6
0x1800260f1  lea     rsi, [rbx+28h]
0x1800260f5  mov     byte ptr [rsi+20h], 1
0x1800260f9  lea     rcx, aAllowingAggreg; "Allowing aggregated policy by default: "
0x180026100  call    cs:__imp_OutputDebugStringW
0x180026106  cmp     qword ptr [rbx+40h], 7
0x18002610b  jbe     short loc_180026110
0x18002610d  mov     rsi, [rsi]
0x180026110  mov     rcx, rsi; lpOutputString
0x180026113  call    cs:__imp_OutputDebugStringW
0x180026119  lea     rcx, asc_18003C448; "\n"
0x180026120  call    cs:__imp_OutputDebugStringW
0x180026126  mov     rcx, [rbx+10h]
0x18002612a  cmp     [rcx+19h], r15b
0x18002612e  jz      short loc_18002614E
0x180026130  mov     rax, [rbx+8]
0x180026134  jmp     short loc_180026143
0x180026136  cmp     rbx, [rax+10h]
0x18002613a  jnz     short loc_180026149
0x18002613c  mov     rbx, rax
0x18002613f  mov     rax, [rax+8]
0x180026143  cmp     [rax+19h], r15b
0x180026147  jz      short loc_180026136
0x180026149  mov     rbx, rax
0x18002614c  jmp     short loc_180026169
0x18002614e  mov     rbx, rcx
0x180026151  mov     rcx, [rcx]
0x180026154  cmp     [rcx+19h], r15b
0x180026158  jnz     short loc_180026169
0x18002615a  mov     rbx, rcx
0x18002615d  mov     rax, [rcx]
0x180026160  mov     rcx, rax
0x180026163  cmp     [rax+19h], r15b
0x180026167  jz      short loc_18002615A
0x180026169  cmp     [rbx+19h], r15b
0x18002616d  jz      loc_180025FF0
0x180026173  mov     byte ptr cs:word_18004EF80, 1
0x18002617a  mov     ebx, r15d
0x18002617d  lea     rcx, [rbp+var_60]
0x180026181  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180026186  nop
0x180026187  test    rdi, rdi
0x18002618a  jz      short loc_1800261A1
0x18002618c  mov     rcx, rdi; void *
0x18002618f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026194  mov     edx, 20h ; ' '
0x180026199  mov     rcx, rdi; Block
0x18002619c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800261a1  mov     eax, ebx
0x1800261a3  lea     r11, [rsp+80h+var_s0]
0x1800261ab  mov     rbx, [r11+30h]
0x1800261af  mov     rsi, [r11+38h]
0x1800261b3  mov     rdi, [r11+40h]
0x1800261b7  mov     rsp, r11
0x1800261ba  pop     r15
0x1800261bc  pop     r14
0x1800261be  pop     r13
0x1800261c0  pop     r12
0x1800261c2  pop     rbp
0x1800261c3  retn
```
