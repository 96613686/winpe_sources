# ComputeService::Net::ApplyFirewallRules(std::vector<ComputeService::Net::CFW_RULE,std::allocator<ComputeService::Net::CFW_RULE>> const &,_GUID const &,ushort const *,uint)

- ea: `0x1400b1cf8`
- end: `0x1400b20ce`
- name: `?ApplyFirewallRules@Net@ComputeService@@YAXAEBV?$vector@UCFW_RULE@Net@ComputeService@@V?$allocator@UCFW_RULE@Net@ComputeService@@@std@@@std@@AEBU_GUID@@PEBGI@Z`
- size: `982`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400ad678`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400083bc`
- `0x140008760`
- `0x14000ea60`
- `0x1400341ac`
- `0x14004346c`
- `0x14008ae64`
- `0x1400b1cf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b1dce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b1e4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b1dce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400b1e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b1dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b1e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b1dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b1e39`
- `FirewallAPI!FWAddFirewallRule` at `0x1400b1fdd`
- `FirewallAPI!FWAddFirewallRule` at `0x1400b1fdd`
- `FirewallAPI!FWOpenPolicyStore` at `0x1400b1dfb`
- `FirewallAPI!FWOpenPolicyStore` at `0x1400b1e76`
- `FirewallAPI!FWOpenPolicyStore` at `0x1400b1dfb`
- `FirewallAPI!FWOpenPolicyStore` at `0x1400b1e76`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b1dc6`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b1e44`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b2022`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b2032`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b1dc6`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b1e44`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b2022`
- `FirewallAPI!FWClosePolicyStore` at `0x1400b2032`

## string_xrefs

- `0x1400b2076`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b2092`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b20a7`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b20bc`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ComputeService::Net::ApplyFirewallRules(__int64 **a1, _QWORD *a2, __int64 a3, int a4)
{
  int v4; // esi
  __int64 result; // rax
  char v8; // r15
  char v9; // r12
  __int64 v10; // rcx
  __int64 *v11; // rdi
  __int64 *v12; // r13
  _QWORD *v13; // rax
  __int64 v14; // rsi
  DWORD LastError; // ebx
  unsigned int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rsi
  DWORD v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int16 v23; // cx
  __int16 v24; // cx
  __int64 v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  _BYTE v30[32]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  _QWORD Src[4]; // [rsp+70h] [rbp-90h] BYREF
  char v34[8]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v35; // [rsp+98h] [rbp-68h]
  _QWORD *v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  int v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+BCh] [rbp-44h]
  __int16 v41; // [rsp+C0h] [rbp-40h]
  int v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  int v45; // [rsp+E8h] [rbp-18h]
  __int64 v46; // [rsp+F0h] [rbp-10h]
  int v47; // [rsp+188h] [rbp+88h]
  _QWORD *v48; // [rsp+190h] [rbp+90h]
  __int64 v49; // [rsp+1A8h] [rbp+A8h]
  int v50; // [rsp+1B0h] [rbp+B0h]
  __int16 v51; // [rsp+1B4h] [rbp+B4h]
  int v52; // [rsp+1E4h] [rbp+E4h]
  int v53; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = a4;
  result = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v31 = 0;
  v32 = 0;
  v11 = *a1;
  v12 = a1[1];
  if ( *a1 != v12 )
  {
    while ( 1 )
    {
      v13 = (_QWORD *)Vml::GuidToString(v30, a2, 0);
      if ( v13[3] > 7u )
        v13 = (_QWORD *)*v13;
      v28 = (unsigned int)v13;
      Vml::FormatString(Src, (wchar_t *)L"%ls - %ls - %ls");
      std::wstring::~wstring(v30);
      if ( *((_DWORD *)v11 + 4) == 2 )
      {
        if ( !v9 )
        {
          v14 = v32;
          if ( v32 )
          {
            LastError = GetLastError();
            FWClosePolicyStore(v14);
            SetLastError(LastError);
          }
          v32 = 0;
          v28 = 0;
          v16 = FWOpenPolicyStore(545, 0, 2, 2);
          if ( v16 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x195,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
              (const char *)v16,
              0);
          v9 = 1;
          v4 = a4;
        }
        v17 = v32;
        goto LABEL_18;
      }
      if ( *((_DWORD *)v11 + 4) == 4 )
        break;
LABEL_39:
      std::wstring::~wstring(Src);
      v11 += 6;
      if ( v11 == v12 )
      {
        v10 = v31;
        result = v32;
        goto LABEL_41;
      }
    }
    if ( !v8 )
    {
      v18 = v31;
      if ( v31 )
      {
        v19 = GetLastError();
        FWClosePolicyStore(v18);
        SetLastError(v19);
      }
      v31 = 0;
      v28 = 0;
      v20 = FWOpenPolicyStore(545, 0, 4, 2);
      if ( v20 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
          (const char *)v20,
          0);
      v8 = 1;
      v4 = a4;
    }
    v17 = v31;
LABEL_18:
    memset_0(v34, 0, 0x1F8u);
    v35 = 539;
    v22 = Src;
    if ( Src[3] > 7u )
      v22 = (_QWORD *)Src[0];
    v36 = v22;
    v37 = *v11;
    v38 = v37;
    v39 = 0x7FFFFFFF;
    v40 = *((_DWORD *)v11 + 5);
    v41 = *((_WORD *)v11 + 12);
    v53 = v4;
    switch ( v41 )
    {
      case 1:
        goto LABEL_30;
      case 6:
      case 17:
        v23 = *((_WORD *)v11 + 13);
        if ( v23 )
        {
          LODWORD(v43) = 1;
          v44 = (__int64)v11 + 30;
          *((_WORD *)v11 + 16) = v23;
          *((_WORD *)v11 + 15) = v23;
        }
        v24 = *((_WORD *)v11 + 14);
        if ( v24 )
        {
          v45 = 1;
          v46 = (__int64)v11 + 34;
          *((_WORD *)v11 + 18) = v24;
          *((_WORD *)v11 + 17) = v24;
        }
        break;
      case 58:
LABEL_30:
        *((_BYTE *)v11 + 38) = *((_BYTE *)v11 + 26);
        *((_WORD *)v11 + 20) = *((_WORD *)v11 + 14);
        v43 = (__int64)v11 + 38;
        v42 = 1;
        break;
      case 256:
        break;
      default:
        v27 = wil::verify_hresult<long>(2147549183LL, v21);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
          (const char *)v27,
          v28);
    }
    if ( *((_DWORD *)v11 + 4) == 2 && (*a2 != *(_QWORD *)&GUID_NULL.Data1 || a2[1] != *(_QWORD *)GUID_NULL.Data4) )
    {
      v47 = 1;
      v48 = a2;
    }
    v25 = v49;
    if ( *(_WORD *)v11[1] )
      v25 = v11[1];
    v49 = v25;
    v50 = 3;
    v51 = 1;
    v52 = 1;
    v26 = FWAddFirewallRule(v17, v34);
    if ( v26 && v26 != 183 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
        (const char *)v26,
        v28);
    goto LABEL_39;
  }
LABEL_41:
  if ( result )
  {
    result = FWClosePolicyStore(result);
    v10 = v31;
  }
  if ( v10 )
    return FWClosePolicyStore(v10);
  return result;
}

```

## disassembly

```asm
0x1400b1cf8  mov     [rsp-8+arg_18], rbx
0x1400b1cfd  push    rbp
0x1400b1cfe  push    rsi
0x1400b1cff  push    rdi
0x1400b1d00  push    r12
0x1400b1d02  push    r13
0x1400b1d04  push    r14
0x1400b1d06  push    r15
0x1400b1d08  lea     rbp, [rsp-1A0h]
0x1400b1d10  sub     rsp, 2A0h
0x1400b1d17  mov     rax, cs:__security_cookie
0x1400b1d1e  xor     rax, rsp
0x1400b1d21  mov     [rbp+1D0h+var_40], rax
0x1400b1d28  mov     esi, r9d
0x1400b1d2b  mov     [rsp+2D0h+var_2A0], r9d
0x1400b1d30  mov     rbx, r8
0x1400b1d33  mov     [rsp+2D0h+var_298], rbx
0x1400b1d38  mov     r14, rdx
0x1400b1d3b  mov     r10, rcx
0x1400b1d3e  xor     eax, eax
0x1400b1d40  mov     r15b, al
0x1400b1d43  mov     r12b, al
0x1400b1d46  mov     ecx, eax
0x1400b1d48  mov     [rsp+2D0h+var_270], rax
0x1400b1d4d  mov     [rsp+2D0h+var_268], rax
0x1400b1d52  mov     rdi, [r10]
0x1400b1d55  mov     r13, [r10+8]
0x1400b1d59  cmp     rdi, r13
0x1400b1d5c  jz      loc_1400B201A
0x1400b1d62  xor     r8d, r8d
0x1400b1d65  mov     rdx, r14
0x1400b1d68  lea     rcx, [rsp+2D0h+var_290]
0x1400b1d6d  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400b1d72  nop
0x1400b1d73  cmp     qword ptr [rax+18h], 7
0x1400b1d78  jbe     short loc_1400B1D7D
0x1400b1d7a  mov     rax, [rax]
0x1400b1d7d  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x1400b1d82  mov     r9, rbx
0x1400b1d85  mov     r8, [rdi]
0x1400b1d88  lea     rdx, aLsLsLs; "%ls - %ls - %ls"
0x1400b1d8f  lea     rcx, [rsp+2D0h+Src]; Src
0x1400b1d94  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400b1d99  nop
0x1400b1d9a  lea     rcx, [rsp+2D0h+var_290]; void *
0x1400b1d9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b1da4  cmp     dword ptr [rdi+10h], 2
0x1400b1da8  jnz     short loc_1400B1E1E
0x1400b1daa  xor     ebx, ebx
0x1400b1dac  test    r12b, r12b
0x1400b1daf  jnz     short loc_1400B1E17
0x1400b1db1  mov     rsi, [rsp+2D0h+var_268]
0x1400b1db6  test    rsi, rsi
0x1400b1db9  jz      short loc_1400B1DD6
0x1400b1dbb  call    cs:__imp_GetLastError
0x1400b1dc1  mov     ebx, eax
0x1400b1dc3  mov     rcx, rsi
0x1400b1dc6  call    cs:__imp_FWClosePolicyStore
0x1400b1dcc  mov     ecx, ebx; dwErrCode
0x1400b1dce  call    cs:__imp_SetLastError
0x1400b1dd4  xor     ebx, ebx
0x1400b1dd6  mov     [rsp+2D0h+var_268], rbx
0x1400b1ddb  mov     ecx, 221h
0x1400b1de0  lea     rax, [rsp+2D0h+var_268]
0x1400b1de5  mov     [rsp+2D0h+var_2A8], rax
0x1400b1dea  mov     [rsp+2D0h+var_2B0], ebx; unsigned int
0x1400b1dee  mov     eax, 2
0x1400b1df3  mov     r9d, eax
0x1400b1df6  mov     r8d, eax
0x1400b1df9  xor     edx, edx
0x1400b1dfb  call    cs:__imp_FWOpenPolicyStore
0x1400b1e01  mov     rcx, [rbp+1D8h]; this
0x1400b1e08  test    eax, eax
0x1400b1e0a  jnz     loc_1400B20A4
0x1400b1e10  mov     r12b, 1
0x1400b1e13  mov     esi, [rsp+2D0h+var_2A0]
0x1400b1e17  mov     rbx, [rsp+2D0h+var_268]
0x1400b1e1c  jmp     short loc_1400B1E97
0x1400b1e1e  cmp     dword ptr [rdi+10h], 4
0x1400b1e22  jnz     loc_1400B1FF9
0x1400b1e28  xor     ebx, ebx
0x1400b1e2a  test    r15b, r15b
0x1400b1e2d  jnz     short loc_1400B1E92
0x1400b1e2f  mov     rsi, [rsp+2D0h+var_270]
0x1400b1e34  test    rsi, rsi
0x1400b1e37  jz      short loc_1400B1E54
0x1400b1e39  call    cs:__imp_GetLastError
0x1400b1e3f  mov     ebx, eax
0x1400b1e41  mov     rcx, rsi
0x1400b1e44  call    cs:__imp_FWClosePolicyStore
0x1400b1e4a  mov     ecx, ebx; dwErrCode
0x1400b1e4c  call    cs:__imp_SetLastError
0x1400b1e52  xor     ebx, ebx
0x1400b1e54  mov     [rsp+2D0h+var_270], rbx
0x1400b1e59  mov     ecx, 221h
0x1400b1e5e  lea     rax, [rsp+2D0h+var_270]
0x1400b1e63  mov     [rsp+2D0h+var_2A8], rax
0x1400b1e68  mov     [rsp+2D0h+var_2B0], ebx; unsigned int
0x1400b1e6c  xor     edx, edx
0x1400b1e6e  lea     r9d, [rdx+2]
0x1400b1e72  lea     r8d, [rdx+4]
0x1400b1e76  call    cs:__imp_FWOpenPolicyStore
0x1400b1e7c  mov     rcx, [rbp+1D8h]; this
0x1400b1e83  test    eax, eax
0x1400b1e85  jnz     loc_1400B20B9
0x1400b1e8b  mov     r15b, 1
0x1400b1e8e  mov     esi, [rsp+2D0h+var_2A0]
0x1400b1e92  mov     rbx, [rsp+2D0h+var_270]
0x1400b1e97  xor     edx, edx; Val
0x1400b1e99  mov     r8d, 1F8h; Size
0x1400b1e9f  lea     rcx, [rbp+1D0h+var_240]; void *
0x1400b1ea3  call    memset_0
0x1400b1ea8  mov     eax, 21Bh
0x1400b1ead  mov     [rbp+1D0h+var_238], ax
0x1400b1eb1  lea     rax, [rsp+2D0h+Src]
0x1400b1eb6  cmp     [rbp+1D0h+var_248], 7
0x1400b1ebb  cmova   rax, [rsp+2D0h+Src]
0x1400b1ec1  mov     [rbp+1D0h+var_230], rax
0x1400b1ec5  mov     rax, [rdi]
0x1400b1ec8  mov     [rbp+1D0h+var_228], rax
0x1400b1ecc  mov     [rbp+1D0h+var_220], rax
0x1400b1ed0  mov     [rbp+1D0h+var_218], 7FFFFFFFh
0x1400b1ed7  mov     eax, [rdi+14h]
0x1400b1eda  mov     [rbp+1D0h+var_214], eax
0x1400b1edd  movzx   ecx, word ptr [rdi+18h]
0x1400b1ee1  mov     [rbp+1D0h+var_210], cx
0x1400b1ee5  mov     [rbp+1D0h+var_78], esi
0x1400b1eeb  sub     ecx, 1
0x1400b1eee  jz      short loc_1400B1F54
0x1400b1ef0  sub     ecx, 5
0x1400b1ef3  jz      short loc_1400B1F13
0x1400b1ef5  sub     ecx, 0Bh
0x1400b1ef8  jz      short loc_1400B1F13
0x1400b1efa  sub     ecx, 29h ; ')'
0x1400b1efd  jz      short loc_1400B1F54
0x1400b1eff  cmp     ecx, 0C6h
0x1400b1f05  jnz     loc_1400B2062
0x1400b1f0b  mov     r9d, 1
0x1400b1f11  jmp     short loc_1400B1F73
0x1400b1f13  movzx   ecx, word ptr [rdi+1Ah]
0x1400b1f17  xor     r8d, r8d
0x1400b1f1a  lea     r9d, [r8+1]
0x1400b1f1e  test    cx, cx
0x1400b1f21  jz      short loc_1400B1F36
0x1400b1f23  mov     dword ptr [rbp+1D0h+var_200], r9d
0x1400b1f27  lea     rax, [rdi+1Eh]
0x1400b1f2b  mov     [rbp+1D0h+var_1F8], rax
0x1400b1f2f  mov     [rdi+20h], cx
0x1400b1f33  mov     [rax], cx
0x1400b1f36  movzx   ecx, word ptr [rdi+1Ch]
0x1400b1f3a  test    cx, cx
0x1400b1f3d  jz      short loc_1400B1F76
0x1400b1f3f  mov     [rbp+1D0h+var_1E8], r9d
0x1400b1f43  lea     rax, [rdi+22h]
0x1400b1f47  mov     [rbp+1D0h+var_1E0], rax
0x1400b1f4b  mov     [rdi+24h], cx
0x1400b1f4f  mov     [rax], cx
0x1400b1f52  jmp     short loc_1400B1F76
0x1400b1f54  lea     rcx, [rdi+26h]
0x1400b1f58  mov     al, [rdi+1Ah]
0x1400b1f5b  mov     [rcx], al
0x1400b1f5d  movzx   eax, word ptr [rdi+1Ch]
0x1400b1f61  mov     r9d, 1
0x1400b1f67  mov     [rdi+28h], ax
0x1400b1f6b  mov     [rbp+1D0h+var_200], rcx
0x1400b1f6f  mov     [rbp+1D0h+var_208], r9d
0x1400b1f73  xor     r8d, r8d
0x1400b1f76  cmp     dword ptr [rdi+10h], 2
0x1400b1f7a  jnz     short loc_1400B1FA3
0x1400b1f7c  mov     rax, [r14]
0x1400b1f7f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1400b1f86  jnz     short loc_1400B1F95
0x1400b1f88  mov     rax, [r14+8]
0x1400b1f8c  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1400b1f93  jz      short loc_1400B1FA3
0x1400b1f95  mov     [rbp+1D0h+var_148], r9d
0x1400b1f9c  mov     [rbp+1D0h+var_140], r14
0x1400b1fa3  mov     rdx, [rdi+8]
0x1400b1fa7  mov     rax, [rbp+1D0h+var_128]
0x1400b1fae  cmp     [rdx], r8w
0x1400b1fb2  cmovnz  rax, rdx
0x1400b1fb6  mov     [rbp+1D0h+var_128], rax
0x1400b1fbd  mov     [rbp+1D0h+var_120], 3
0x1400b1fc7  mov     [rbp+1D0h+var_11C], r9w
0x1400b1fcf  mov     [rbp+1D0h+var_EC], r9d
0x1400b1fd6  lea     rdx, [rbp+1D0h+var_240]
0x1400b1fda  mov     rcx, rbx
0x1400b1fdd  call    cs:__imp_FWAddFirewallRule
0x1400b1fe3  test    eax, eax
0x1400b1fe5  jz      short loc_1400B1FF2
0x1400b1fe7  cmp     eax, 0B7h
0x1400b1fec  jnz     loc_1400B2088
0x1400b1ff2  mov     rbx, [rsp+2D0h+var_298]
0x1400b1ff7  jmp     short $+2
0x1400b1ff9  lea     rcx, [rsp+2D0h+Src]; void *
0x1400b1ffe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400b2003  add     rdi, 30h ; '0'
0x1400b2007  cmp     rdi, r13
0x1400b200a  jnz     loc_1400B1D62
0x1400b2010  mov     rcx, [rsp+2D0h+var_270]
0x1400b2015  mov     rax, [rsp+2D0h+var_268]
0x1400b201a  test    rax, rax
0x1400b201d  jz      short loc_1400B202D
0x1400b201f  mov     rcx, rax
0x1400b2022  call    cs:__imp_FWClosePolicyStore
0x1400b2028  mov     rcx, [rsp+2D0h+var_270]
0x1400b202d  test    rcx, rcx
0x1400b2030  jz      short loc_1400B2038
0x1400b2032  call    cs:__imp_FWClosePolicyStore
0x1400b2038  mov     rcx, [rbp+1D0h+var_40]
0x1400b203f  xor     rcx, rsp; StackCookie
0x1400b2042  call    __security_check_cookie
0x1400b2047  mov     rbx, [rsp+2D0h+arg_18]
0x1400b204f  add     rsp, 2A0h
0x1400b2056  pop     r15
0x1400b2058  pop     r14
0x1400b205a  pop     r13
0x1400b205c  pop     r12
0x1400b205e  pop     rdi
0x1400b205f  pop     rsi
0x1400b2060  pop     rbp
0x1400b2061  retn
0x1400b2062  mov     ecx, 8000FFFFh
0x1400b2067  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400b206c  mov     r9d, eax; char *
0x1400b206f  mov     rcx, [rbp+1D8h]; this
0x1400b2076  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b207d  mov     edx, 11Dh; void *
0x1400b2082  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b2088  mov     rcx, [rbp+1D8h]; this
0x1400b208f  mov     r9d, eax; char *
0x1400b2092  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b2099  mov     edx, 1C4h; void *
0x1400b209e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b20a4  mov     r9d, eax; char *
0x1400b20a7  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b20ae  mov     edx, 195h; void *
0x1400b20b3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b20b9  mov     r9d, eax; char *
0x1400b20bc  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b20c3  mov     edx, 1A5h; void *
0x1400b20c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
