# User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)

- ea: `0x18001bf80`
- end: `0x18001c140`
- name: `?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z`
- size: `448`
- prototype: `static int(struct _bstr_t *, struct _bstr_t *, enum _SID_NAME_USE *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a794`
- `0x18001c3ac`

## callees

- `0x180003f7c`
- `0x1800050d0`
- `0x180005184`
- `0x1800051c4`
- `0x180019954`
- `0x18001bf80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c060`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c071`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c115`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c124`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c060`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c071`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c115`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c124`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001bfdf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001c04a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001bfdf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001c04a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall User::LookupUserSid(struct _bstr_t *a1, struct _bstr_t *a2, enum _SID_NAME_USE *a3, void *a4)
{
  unsigned int v8; // esi
  int v9; // edx
  int v10; // edx
  bool v11; // r8
  _bstr_t *v12; // rax
  bool v13; // r8
  _bstr_t *v14; // rax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-2Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-8h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  v22 = 0;
  v21 = 0;
  LookupAccountSidLocalW(a4, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
  if ( GetLastError() == 122 )
  {
    v9 = cchName++;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&Name, v9);
    v10 = cchReferencedDomainName++;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&ReferencedDomainName, v10);
    v8 = LookupAccountSidLocalW(a4, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    if ( v8 )
    {
      ATL::CComBSTR::operator=(&v22, &Name);
      ATL::CComBSTR::operator=(&v21, &ReferencedDomainName);
      SysFreeString(ReferencedDomainName);
      SysFreeString(Name);
      v12 = _bstr_t::_bstr_t((_bstr_t *)&Name, v21, v11);
      _bstr_t::operator=(a1, v12);
      _bstr_t::~_bstr_t((_bstr_t *)&Name);
      v21 = 0;
      v14 = _bstr_t::_bstr_t((_bstr_t *)&Name, v22, v13);
      _bstr_t::operator=(a2, v14);
      _bstr_t::~_bstr_t((_bstr_t *)&Name);
      *a3 = peUse;
      v8 = 1;
    }
    else
    {
      SysFreeString(ReferencedDomainName);
      SysFreeString(Name);
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
0x18001bf80  push    rbp
0x18001bf82  push    rsi
0x18001bf83  push    r12
0x18001bf85  push    r14
0x18001bf87  push    r15
0x18001bf89  mov     rbp, rsp
0x18001bf8c  sub     rsp, 60h
0x18001bf90  mov     rsi, r9
0x18001bf93  mov     r14, r8
0x18001bf96  mov     r15, rdx
0x18001bf99  mov     r12, rcx
0x18001bf9c  mov     [rbp+cchName], 0
0x18001bfa3  mov     [rbp+var_30], 0
0x18001bfaa  mov     [rbp+var_28], 8
0x18001bfb1  mov     [rbp+var_8], 0
0x18001bfb9  mov     [rbp+var_10], 0
0x18001bfc1  lea     rax, [rbp+var_28]
0x18001bfc5  mov     [rsp+60h+peUse], rax; peUse
0x18001bfca  lea     rax, [rbp+var_30]
0x18001bfce  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001bfd3  xor     r9d, r9d; ReferencedDomainName
0x18001bfd6  lea     r8, [rbp+cchName]; cchName
0x18001bfda  xor     edx, edx; Name
0x18001bfdc  mov     rcx, rsi; Sid
0x18001bfdf  call    cs:__imp_LookupAccountSidLocalW
0x18001bfe6  nop     dword ptr [rax+rax+00h]
0x18001bfeb  call    cs:__imp_GetLastError
0x18001bff2  nop     dword ptr [rax+rax+00h]
0x18001bff7  cmp     eax, 7Ah ; 'z'
0x18001bffa  jz      short loc_18001C003
0x18001bffc  xor     esi, esi
0x18001bffe  jmp     loc_18001C113
0x18001c003  mov     edx, [rbp+cchName]; int
0x18001c006  lea     eax, [rdx+1]
0x18001c009  mov     [rbp+cchName], eax
0x18001c00c  lea     rcx, [rbp+Name]; this
0x18001c010  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001c015  nop
0x18001c016  mov     edx, [rbp+var_30]; int
0x18001c019  lea     eax, [rdx+1]
0x18001c01c  mov     [rbp+var_30], eax
0x18001c01f  lea     rcx, [rbp+ReferencedDomainName]; this
0x18001c023  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001c028  nop
0x18001c029  lea     rax, [rbp+var_28]
0x18001c02d  mov     [rsp+60h+peUse], rax; peUse
0x18001c032  lea     rax, [rbp+var_30]
0x18001c036  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001c03b  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x18001c03f  lea     r8, [rbp+cchName]; cchName
0x18001c043  mov     rdx, [rbp+Name]; Name
0x18001c047  mov     rcx, rsi; Sid
0x18001c04a  call    cs:__imp_LookupAccountSidLocalW
0x18001c051  nop     dword ptr [rax+rax+00h]
0x18001c056  mov     esi, eax
0x18001c058  test    eax, eax
0x18001c05a  jnz     short loc_18001C082
0x18001c05c  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x18001c060  call    cs:__imp_SysFreeString
0x18001c067  nop     dword ptr [rax+rax+00h]
0x18001c06c  nop
0x18001c06d  mov     rcx, [rbp+Name]; bstrString
0x18001c071  call    cs:__imp_SysFreeString
0x18001c078  nop     dword ptr [rax+rax+00h]
0x18001c07d  jmp     loc_18001C113
0x18001c082  lea     rdx, [rbp+Name]
0x18001c086  lea     rcx, [rbp+var_8]
0x18001c08a  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18001c08f  lea     rdx, [rbp+ReferencedDomainName]
0x18001c093  lea     rcx, [rbp+var_10]
0x18001c097  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18001c09c  nop
0x18001c09d  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x18001c0a1  call    cs:__imp_SysFreeString
0x18001c0a8  nop     dword ptr [rax+rax+00h]
0x18001c0ad  nop
0x18001c0ae  mov     rcx, [rbp+Name]; bstrString
0x18001c0b2  call    cs:__imp_SysFreeString
0x18001c0b9  nop     dword ptr [rax+rax+00h]
0x18001c0be  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18001c0c2  lea     rcx, [rbp+Name]; this
0x18001c0c6  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001c0cb  mov     rdx, rax
0x18001c0ce  mov     rcx, r12
0x18001c0d1  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001c0d6  lea     rcx, [rbp+Name]; this
0x18001c0da  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c0df  mov     [rbp+var_10], 0
0x18001c0e7  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x18001c0eb  lea     rcx, [rbp+Name]; this
0x18001c0ef  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001c0f4  mov     rdx, rax
0x18001c0f7  mov     rcx, r15
0x18001c0fa  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001c0ff  lea     rcx, [rbp+Name]; this
0x18001c103  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001c108  mov     eax, [rbp+var_28]
0x18001c10b  mov     [r14], eax
0x18001c10e  mov     esi, 1
0x18001c113  xor     ecx, ecx; bstrString
0x18001c115  call    cs:__imp_SysFreeString
0x18001c11c  nop     dword ptr [rax+rax+00h]
0x18001c121  nop
0x18001c122  xor     ecx, ecx; bstrString
0x18001c124  call    cs:__imp_SysFreeString
0x18001c12b  nop     dword ptr [rax+rax+00h]
0x18001c130  mov     eax, esi
0x18001c132  add     rsp, 60h
0x18001c136  pop     r15
0x18001c138  pop     r14
0x18001c13a  pop     r12
0x18001c13c  pop     rsi
0x18001c13d  pop     rbp
0x18001c13e  retn
```
