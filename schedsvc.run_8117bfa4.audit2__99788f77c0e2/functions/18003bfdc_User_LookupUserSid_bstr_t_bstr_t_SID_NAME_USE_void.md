# User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)

- ea: `0x18003bfdc`
- end: `0x18003c1f0`
- name: `?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z`
- size: `532`
- prototype: `static int(struct _bstr_t *, struct _bstr_t *, enum _SID_NAME_USE *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003be7c`
- `0x18006acbc`

## callees

- `0x180001d10`
- `0x180011e40`
- `0x18001d130`
- `0x18003bfdc`
- `0x18004d2e4`
- `0x1800529a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003c0e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003c10b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003c0e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003c10b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c0bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c0cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c150`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c160`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c0bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c0cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c150`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c160`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c049`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c03d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c0aa`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c03d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c0aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall User::LookupUserSid(struct _bstr_t *a1, struct _bstr_t *a2, enum _SID_NAME_USE *a3, void *a4)
{
  unsigned int v8; // esi
  UINT v9; // edx
  WCHAR *v10; // rbx
  UINT v11; // edx
  WCHAR *v12; // rdi
  bool v13; // r8
  _bstr_t *v14; // rax
  bool v15; // r8
  _bstr_t *v16; // rax
  DWORD ui; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-2Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v21; // [rsp+40h] [rbp-20h] BYREF
  WCHAR *v22; // [rsp+48h] [rbp-18h] BYREF
  WCHAR *v23; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-8h] BYREF

  cchName = 0;
  ui = 0;
  peUse = SidTypeUnknown;
  v24 = 0;
  v21 = 0;
  LookupAccountSidLocalW(a4, 0, &cchName, 0, &ui, &peUse);
  if ( GetLastError() == 122 )
  {
    v9 = cchName++;
    if ( v9 )
    {
      v10 = SysAllocStringLen(0, v9);
      v22 = v10;
      if ( !v10 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    else
    {
      v10 = 0;
      v22 = 0;
    }
    v11 = ui++;
    if ( v11 )
    {
      v12 = SysAllocStringLen(0, v11);
      v23 = v12;
      if ( !v12 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    else
    {
      v12 = 0;
      v23 = 0;
    }
    v8 = LookupAccountSidLocalW(a4, v10, &cchName, v12, &ui, &peUse);
    if ( v8 )
    {
      ATL::CComBSTR::operator=(&v24, &v22);
      ATL::CComBSTR::operator=(&v21, &v23);
      SysFreeString(v12);
      SysFreeString(v10);
      v14 = _bstr_t::_bstr_t((_bstr_t *)&v23, v21, v13);
      _bstr_t::operator=(a1, v14);
      _bstr_t::~_bstr_t((_bstr_t *)&v23);
      v21 = 0;
      v16 = _bstr_t::_bstr_t((_bstr_t *)&v23, v24, v15);
      _bstr_t::operator=(a2, v16);
      _bstr_t::~_bstr_t((_bstr_t *)&v23);
      *a3 = peUse;
      v8 = 1;
    }
    else
    {
      SysFreeString(v12);
      SysFreeString(v10);
    }
  }
  else
  {
    v8 = 0;
  }
  SysFreeString(0);
  SysFreeString(0);
  return v8;
}

```

## disassembly

```asm
0x18003bfdc  push    rbp
0x18003bfde  push    rbx
0x18003bfdf  push    rsi
0x18003bfe0  push    rdi
0x18003bfe1  push    r12
0x18003bfe3  push    r14
0x18003bfe5  push    r15
0x18003bfe7  mov     rbp, rsp
0x18003bfea  sub     rsp, 60h
0x18003bfee  mov     rsi, r9
0x18003bff1  mov     r14, r8
0x18003bff4  mov     r15, rdx
0x18003bff7  mov     r12, rcx
0x18003bffa  mov     [rbp+cchName], 0
0x18003c001  mov     [rbp+ui], 0
0x18003c008  mov     [rbp+var_28], 8
0x18003c00f  mov     [rbp+var_8], 0
0x18003c017  mov     [rbp+var_20], 0
0x18003c01f  lea     rax, [rbp+var_28]
0x18003c023  mov     [rsp+60h+peUse], rax; peUse
0x18003c028  lea     rax, [rbp+ui]
0x18003c02c  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003c031  xor     r9d, r9d; ReferencedDomainName
0x18003c034  lea     r8, [rbp+cchName]; cchName
0x18003c038  xor     edx, edx; Name
0x18003c03a  mov     rcx, rsi; Sid
0x18003c03d  call    cs:__imp_LookupAccountSidLocalW
0x18003c044  nop     dword ptr [rax+rax+00h]
0x18003c049  call    cs:__imp_GetLastError
0x18003c050  nop     dword ptr [rax+rax+00h]
0x18003c055  cmp     eax, 7Ah ; 'z'
0x18003c058  jz      short loc_18003C061
0x18003c05a  xor     esi, esi
0x18003c05c  jmp     loc_18003C1C1
0x18003c061  mov     edx, [rbp+cchName]; ui
0x18003c064  lea     eax, [rdx+1]
0x18003c067  mov     [rbp+cchName], eax
0x18003c06a  test    edx, edx
0x18003c06c  jnz     short loc_18003C0E0
0x18003c06e  xor     ebx, ebx
0x18003c070  mov     [rbp+var_18], rbx
0x18003c074  mov     edx, [rbp+ui]; ui
0x18003c077  lea     eax, [rdx+1]
0x18003c07a  mov     [rbp+ui], eax
0x18003c07d  test    edx, edx
0x18003c07f  jnz     loc_18003C109
0x18003c085  xor     edi, edi
0x18003c087  mov     [rbp+var_10], rdi
0x18003c08b  lea     rax, [rbp+var_28]
0x18003c08f  mov     [rsp+60h+peUse], rax; peUse
0x18003c094  lea     rax, [rbp+ui]
0x18003c098  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003c09d  mov     r9, rdi; ReferencedDomainName
0x18003c0a0  lea     r8, [rbp+cchName]; cchName
0x18003c0a4  mov     rdx, rbx; Name
0x18003c0a7  mov     rcx, rsi; Sid
0x18003c0aa  call    cs:__imp_LookupAccountSidLocalW
0x18003c0b1  nop     dword ptr [rax+rax+00h]
0x18003c0b6  mov     esi, eax
0x18003c0b8  test    eax, eax
0x18003c0ba  jnz     short loc_18003C132
0x18003c0bc  mov     rcx, rdi; bstrString
0x18003c0bf  call    cs:__imp_SysFreeString
0x18003c0c6  nop     dword ptr [rax+rax+00h]
0x18003c0cb  nop
0x18003c0cc  mov     rcx, rbx; bstrString
0x18003c0cf  call    cs:__imp_SysFreeString
0x18003c0d6  nop     dword ptr [rax+rax+00h]
0x18003c0db  jmp     loc_18003C1C1
0x18003c0e0  xor     ecx, ecx; strIn
0x18003c0e2  call    cs:__imp_SysAllocStringLen
0x18003c0e9  nop     dword ptr [rax+rax+00h]
0x18003c0ee  mov     rbx, rax
0x18003c0f1  mov     [rbp+var_18], rax
0x18003c0f5  test    rax, rax
0x18003c0f8  jnz     loc_18003C074
0x18003c0fe  mov     ecx, 8007000Eh; unsigned int
0x18003c103  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18003c109  xor     ecx, ecx; strIn
0x18003c10b  call    cs:__imp_SysAllocStringLen
0x18003c112  nop     dword ptr [rax+rax+00h]
0x18003c117  mov     rdi, rax
0x18003c11a  mov     [rbp+var_10], rax
0x18003c11e  test    rax, rax
0x18003c121  jnz     loc_18003C08B
0x18003c127  mov     ecx, 8007000Eh; unsigned int
0x18003c12c  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18003c132  lea     rdx, [rbp+var_18]
0x18003c136  lea     rcx, [rbp+var_8]
0x18003c13a  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18003c13f  lea     rdx, [rbp+var_10]
0x18003c143  lea     rcx, [rbp+var_20]
0x18003c147  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18003c14c  nop
0x18003c14d  mov     rcx, rdi; bstrString
0x18003c150  call    cs:__imp_SysFreeString
0x18003c157  nop     dword ptr [rax+rax+00h]
0x18003c15c  nop
0x18003c15d  mov     rcx, rbx; bstrString
0x18003c160  call    cs:__imp_SysFreeString
0x18003c167  nop     dword ptr [rax+rax+00h]
0x18003c16c  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18003c170  lea     rcx, [rbp+var_10]; this
0x18003c174  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18003c179  mov     rdx, rax
0x18003c17c  mov     rcx, r12
0x18003c17f  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18003c184  lea     rcx, [rbp+var_10]; this
0x18003c188  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c18d  mov     [rbp+var_20], 0
0x18003c195  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x18003c199  lea     rcx, [rbp+var_10]; this
0x18003c19d  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18003c1a2  mov     rdx, rax
0x18003c1a5  mov     rcx, r15
0x18003c1a8  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18003c1ad  lea     rcx, [rbp+var_10]; this
0x18003c1b1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c1b6  mov     eax, [rbp+var_28]
0x18003c1b9  mov     [r14], eax
0x18003c1bc  mov     esi, 1
0x18003c1c1  xor     ecx, ecx; bstrString
0x18003c1c3  call    cs:__imp_SysFreeString
0x18003c1ca  nop     dword ptr [rax+rax+00h]
0x18003c1cf  nop
0x18003c1d0  xor     ecx, ecx; bstrString
0x18003c1d2  call    cs:__imp_SysFreeString
0x18003c1d9  nop     dword ptr [rax+rax+00h]
0x18003c1de  mov     eax, esi
0x18003c1e0  add     rsp, 60h
0x18003c1e4  pop     r15
0x18003c1e6  pop     r14
0x18003c1e8  pop     r12
0x18003c1ea  pop     rdi
0x18003c1eb  pop     rsi
0x18003c1ec  pop     rbx
0x18003c1ed  pop     rbp
0x18003c1ee  retn
```
