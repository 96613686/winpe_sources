# PolicyAllowList<tagEnterprisePolicy>::GetSlapiMdmAllowedPoliciesString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180025c50`
- end: `0x180025e55`
- name: `?GetSlapiMdmAllowedPoliciesString@?$PolicyAllowList@W4tagEnterprisePolicy@@@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800258e0`
- `0x180025e5c`

## callees

- `0x18000aac0`
- `0x18000f27c`
- `0x18000fcc4`
- `0x180010260`
- `0x180025c50`
- `0x18002d730`
- `0x18002d99c`
- `0x18002ffd0`
- `0x180036a90`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025db2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025dc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025dd2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025db2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025dc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025dd2`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180025ca9`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180025ca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e27`
- `SLC!SLGetWindowsInformation` at `0x180025cc6`
- `SLC!SLGetWindowsInformation` at `0x180025cc6`

## string_xrefs

- `0x180025ca2`: `ext-ms-win-security-slc-l1-1-0`

## pseudocode

```c
__int64 __fastcall PolicyAllowList<enum tagEnterprisePolicy>::GetSlapiMdmAllowedPoliciesString(__int64 a1, void **a2)
{
  PBYTE v3; // rbx
  WUSystemInterfaceHelper *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  void **v9; // r9
  void *v10; // rdx
  char *v11; // r14
  __int64 v12; // rdi
  int v14; // [rsp+20h] [rbp-40h]
  PBYTE ppbValue; // [rsp+28h] [rbp-38h] BYREF
  SLDATATYPE peDataType; // [rsp+30h] [rbp-30h] BYREF
  UINT pcbValue; // [rsp+34h] [rbp-2Ch] BYREF
  void *Src[2]; // [rsp+38h] [rbp-28h] BYREF
  void *v19; // [rsp+48h] [rbp-18h]
  unsigned __int64 v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v3 = 0;
  v14 = 0;
  peDataType = SL_DATA_NONE;
  ppbValue = 0;
  pcbValue = 0;
  if ( (int)WUSystemInterfaceHelper::IsCapabilitySupported((WUSystemInterfaceHelper *)6) >= 0 )
  {
    v5 = WUSystemInterfaceHelper::SLGetWindowsInformation(
           v4,
           (const wchar_t *)&peDataType,
           &pcbValue,
           (unsigned int *)&ppbValue,
           0);
  }
  else
  {
    if ( !IsApiSetImplemented("ext-ms-win-security-slc-l1-1-0") )
    {
LABEL_10:
      v6 = -2147467261;
      v7 = 143;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyAllowList.cpp",
        (const char *)v6,
        v14);
      goto LABEL_29;
    }
    v5 = SLGetWindowsInformation(
           L"enterprisemgmt_policymanager-License-MDMPolicyAllowList",
           &peDataType,
           &pcbValue,
           &ppbValue);
  }
  v6 = v5;
  if ( v5 < 0 )
  {
LABEL_27:
    v7 = 142;
    goto LABEL_28;
  }
  if ( peDataType != SL_DATA_SZ || !pcbValue || (pcbValue & 1) != 0 )
  {
    v6 = -2147418113;
    if ( ppbValue )
      LocalFree(ppbValue);
    goto LABEL_27;
  }
  v3 = ppbValue;
  v14 = (int)ppbValue;
  if ( !ppbValue )
    goto LABEL_10;
  if ( pcbValue < 2 || (pcbValue & 1) != 0 )
  {
    v6 = -2147418113;
    v7 = 144;
    goto LABEL_28;
  }
  *(_OWORD *)Src = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,wchar_t const *>(Src, ppbValue, (unsigned __int64)pcbValue >> 1);
  if ( a2 != Src )
  {
    v9 = Src;
    if ( v20 > 7 )
      v9 = (void **)Src[0];
    v10 = v19;
    if ( v19 > a2[3] )
    {
      std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(a2, v19, v8, v9);
    }
    else
    {
      v11 = (char *)a2;
      if ( (unsigned __int64)a2[3] > 7 )
        v11 = (char *)*a2;
      a2[2] = v19;
      v12 = 2LL * (_QWORD)v10;
      memmove(v11, v9, 2LL * (_QWORD)v10);
      *(_WORD *)&v11[v12] = 0;
    }
  }
  OutputDebugStringW(L"SKU MDM licensing allow list string from SLAPI:\n");
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (void **)*a2;
  OutputDebugStringW((LPCWSTR)a2);
  OutputDebugStringW(L"\n");
  v6 = 0;
  std::wstring::~wstring(Src);
LABEL_29:
  if ( v3 )
    LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x180025c50  mov     [rsp-18h+arg_0], rbx
0x180025c55  mov     [rsp-18h+arg_10], rsi
0x180025c5a  mov     [rsp-18h+arg_18], rdi
0x180025c5f  push    rbp
0x180025c60  push    r14
0x180025c62  push    r15
0x180025c64  mov     rbp, rsp
0x180025c67  sub     rsp, 60h
0x180025c6b  mov     rax, cs:__security_cookie
0x180025c72  xor     rax, rsp
0x180025c75  mov     [rbp+var_8], rax
0x180025c79  mov     rsi, rdx
0x180025c7c  xor     r15d, r15d
0x180025c7f  mov     ebx, r15d
0x180025c82  mov     [rbp+var_40], rbx
0x180025c86  mov     [rbp+peDataType], r15d
0x180025c8a  mov     [rbp+ppbValue], r15
0x180025c8e  mov     [rbp+pcbValue], r15d
0x180025c92  lea     ecx, [r15+6]; this
0x180025c96  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x180025c9b  shr     eax, 1Fh
0x180025c9e  test    al, al
0x180025ca0  jz      short loc_180025CCE
0x180025ca2  lea     rcx, Contract; "ext-ms-win-security-slc-l1-1-0"
0x180025ca9  call    cs:__imp_IsApiSetImplemented
0x180025caf  test    eax, eax
0x180025cb1  jz      short loc_180025D15
0x180025cb3  lea     r9, [rbp+ppbValue]; ppbValue
0x180025cb7  lea     r8, [rbp+pcbValue]; pcbValue
0x180025cbb  lea     rdx, [rbp+peDataType]; peDataType
0x180025cbf  lea     rcx, aEnterprisemgmt; "enterprisemgmt_policymanager-License-MD"...
0x180025cc6  call    cs:__imp_SLGetWindowsInformation
0x180025ccc  jmp     short loc_180025CDF
0x180025cce  lea     r9, [rbp+ppbValue]; unsigned int *
0x180025cd2  lea     r8, [rbp+pcbValue]; unsigned int *
0x180025cd6  lea     rdx, [rbp+peDataType]; wchar_t *
0x180025cda  call    ?SLGetWindowsInformation@WUSystemInterfaceHelper@@YAJPEB_WPEAKPEAIPEAPEAE@Z; WUSystemInterfaceHelper::SLGetWindowsInformation(wchar_t const *,ulong *,uint *,uchar * *)
0x180025cdf  mov     edi, eax
0x180025ce1  test    eax, eax
0x180025ce3  js      loc_180025E06
0x180025ce9  cmp     [rbp+peDataType], 1
0x180025ced  jnz     loc_180025DF2
0x180025cf3  mov     ecx, [rbp+pcbValue]
0x180025cf6  cmp     ecx, 1
0x180025cf9  jb      loc_180025DF2
0x180025cff  test    cl, 1
0x180025d02  jnz     loc_180025DF2
0x180025d08  mov     rbx, [rbp+ppbValue]
0x180025d0c  mov     [rbp+var_40], rbx
0x180025d10  test    rbx, rbx
0x180025d13  jnz     short loc_180025D24
0x180025d15  mov     edi, 80004003h
0x180025d1a  mov     edx, 8Fh
0x180025d1f  jmp     loc_180025E0B
0x180025d24  cmp     ecx, 2
0x180025d27  jb      loc_180025DE6
0x180025d2d  test    cl, 1
0x180025d30  jnz     loc_180025DE6
0x180025d36  xorps   xmm0, xmm0
0x180025d39  movups  xmmword ptr [rbp+Src], xmm0
0x180025d3d  mov     [rbp+var_18], r15
0x180025d41  mov     [rbp+var_10], r15
0x180025d45  mov     r8, rcx
0x180025d48  shr     r8, 1
0x180025d4b  mov     rdx, rbx
0x180025d4e  lea     rcx, [rbp+Src]
0x180025d52  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180025d57  nop
0x180025d58  lea     rax, [rbp+Src]
0x180025d5c  cmp     rsi, rax
0x180025d5f  jz      short loc_180025DAB
0x180025d61  lea     r9, [rbp+Src]
0x180025d65  cmp     [rbp+var_10], 7
0x180025d6a  cmova   r9, [rbp+Src]
0x180025d6f  mov     rdx, [rbp+var_18]
0x180025d73  cmp     rdx, [rsi+18h]
0x180025d77  ja      short loc_180025DA3
0x180025d79  mov     r14, rsi
0x180025d7c  cmp     qword ptr [rsi+18h], 7
0x180025d81  jbe     short loc_180025D86
0x180025d83  mov     r14, [rsi]
0x180025d86  mov     [rsi+10h], rdx
0x180025d8a  lea     rdi, [rdx+rdx]
0x180025d8e  mov     r8, rdi; Size
0x180025d91  mov     rdx, r9; Src
0x180025d94  mov     rcx, r14; void *
0x180025d97  call    memmove
0x180025d9c  mov     [rdi+r14], r15w
0x180025da1  jmp     short loc_180025DAB
0x180025da3  mov     rcx, rsi
0x180025da6  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x180025dab  lea     rcx, aSkuMdmLicensin; "SKU MDM licensing allow list string fro"...
0x180025db2  call    cs:__imp_OutputDebugStringW
0x180025db8  cmp     qword ptr [rsi+18h], 7
0x180025dbd  jbe     short loc_180025DC2
0x180025dbf  mov     rsi, [rsi]
0x180025dc2  mov     rcx, rsi; lpOutputString
0x180025dc5  call    cs:__imp_OutputDebugStringW
0x180025dcb  lea     rcx, asc_18003C448; "\n"
0x180025dd2  call    cs:__imp_OutputDebugStringW
0x180025dd8  mov     edi, r15d
0x180025ddb  lea     rcx, [rbp+Src]; void *
0x180025ddf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025de4  jmp     short loc_180025E1F
0x180025de6  mov     edi, 8000FFFFh
0x180025deb  mov     edx, 90h
0x180025df0  jmp     short loc_180025E0B
0x180025df2  mov     edi, 8000FFFFh
0x180025df7  mov     rcx, [rbp+ppbValue]; hMem
0x180025dfb  test    rcx, rcx
0x180025dfe  jz      short loc_180025E06
0x180025e00  call    cs:__imp_LocalFree
0x180025e06  mov     edx, 8Eh; void *
0x180025e0b  mov     rcx, [rbp+18h]; this
0x180025e0f  mov     r9d, edi; char *
0x180025e12  lea     r8, aCW1SSrcClientP_6; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180025e19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e1e  nop
0x180025e1f  test    rbx, rbx
0x180025e22  jz      short loc_180025E2D
0x180025e24  mov     rcx, rbx; hMem
0x180025e27  call    cs:__imp_LocalFree
0x180025e2d  mov     eax, edi
0x180025e2f  mov     rcx, [rbp+var_8]
0x180025e33  xor     rcx, rsp; StackCookie
0x180025e36  call    __security_check_cookie
0x180025e3b  lea     r11, [rsp+60h+var_s0]
0x180025e40  mov     rbx, [r11+20h]
0x180025e44  mov     rsi, [r11+30h]
0x180025e48  mov     rdi, [r11+38h]
0x180025e4c  mov     rsp, r11
0x180025e4f  pop     r15
0x180025e51  pop     r14
0x180025e53  pop     rbp
0x180025e54  retn
```
