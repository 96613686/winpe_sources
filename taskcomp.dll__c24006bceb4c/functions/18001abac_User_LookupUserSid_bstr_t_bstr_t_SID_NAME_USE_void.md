# User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)

- ea: `0x18001abac`
- end: `0x18001ad35`
- name: `?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z`
- size: `393`
- prototype: `static int(struct _bstr_t *, struct _bstr_t *, enum _SID_NAME_USE *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001953c`
- `0x18001af08`

## callees

- `0x180003dac`
- `0x180004e50`
- `0x180004eec`
- `0x180004f28`
- `0x1800187a4`
- `0x18001abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac11`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac7a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001acaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001acba`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad17`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad20`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac7a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001acaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001acba`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad17`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad20`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ac0b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ac6a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ac0b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001ac6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall User::LookupUserSid(struct _bstr_t *a1, struct _bstr_t *a2, enum _SID_NAME_USE *a3, void *a4)
{
  unsigned int v8; // esi
  UINT v9; // edx
  UINT v10; // edx
  _bstr_t *v11; // rax
  _bstr_t *v12; // rax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-2Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v19; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-8h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  v20 = 0;
  v19 = 0;
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
      ATL::CComBSTR::operator=(&v20, (LPCSTR *)&Name);
      ATL::CComBSTR::operator=(&v19, (LPCSTR *)&ReferencedDomainName);
      SysFreeString(ReferencedDomainName);
      SysFreeString(Name);
      v11 = _bstr_t::_bstr_t((_bstr_t *)&Name, v19);
      _bstr_t::operator=(a1, (__int64)v11);
      _bstr_t::~_bstr_t((_bstr_t *)&Name);
      v19 = 0;
      v12 = _bstr_t::_bstr_t((_bstr_t *)&Name, v20);
      _bstr_t::operator=(a2, (__int64)v12);
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
0x18001abac  push    rbp
0x18001abae  push    rsi
0x18001abaf  push    r12
0x18001abb1  push    r14
0x18001abb3  push    r15
0x18001abb5  mov     rbp, rsp
0x18001abb8  sub     rsp, 60h
0x18001abbc  mov     rsi, r9
0x18001abbf  mov     r14, r8
0x18001abc2  mov     r15, rdx
0x18001abc5  mov     r12, rcx
0x18001abc8  mov     [rbp+cchName], 0
0x18001abcf  mov     [rbp+var_30], 0
0x18001abd6  mov     [rbp+var_28], 8
0x18001abdd  mov     [rbp+var_8], 0
0x18001abe5  mov     [rbp+var_10], 0
0x18001abed  lea     rax, [rbp+var_28]
0x18001abf1  mov     [rsp+60h+peUse], rax; peUse
0x18001abf6  lea     rax, [rbp+var_30]
0x18001abfa  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001abff  xor     r9d, r9d; ReferencedDomainName
0x18001ac02  lea     r8, [rbp+cchName]; cchName
0x18001ac06  xor     edx, edx; Name
0x18001ac08  mov     rcx, rsi; Sid
0x18001ac0b  call    cs:__imp_LookupAccountSidLocalW
0x18001ac11  call    cs:__imp_GetLastError
0x18001ac17  cmp     eax, 7Ah ; 'z'
0x18001ac1a  jz      short loc_18001AC23
0x18001ac1c  xor     esi, esi
0x18001ac1e  jmp     loc_18001AD15
0x18001ac23  mov     edx, [rbp+cchName]; int
0x18001ac26  lea     eax, [rdx+1]
0x18001ac29  mov     [rbp+cchName], eax
0x18001ac2c  lea     rcx, [rbp+Name]; this
0x18001ac30  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001ac35  nop
0x18001ac36  mov     edx, [rbp+var_30]; int
0x18001ac39  lea     eax, [rdx+1]
0x18001ac3c  mov     [rbp+var_30], eax
0x18001ac3f  lea     rcx, [rbp+ReferencedDomainName]; this
0x18001ac43  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18001ac48  nop
0x18001ac49  lea     rax, [rbp+var_28]
0x18001ac4d  mov     [rsp+60h+peUse], rax; peUse
0x18001ac52  lea     rax, [rbp+var_30]
0x18001ac56  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001ac5b  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x18001ac5f  lea     r8, [rbp+cchName]; cchName
0x18001ac63  mov     rdx, [rbp+Name]; Name
0x18001ac67  mov     rcx, rsi; Sid
0x18001ac6a  call    cs:__imp_LookupAccountSidLocalW
0x18001ac70  mov     esi, eax
0x18001ac72  test    eax, eax
0x18001ac74  jnz     short loc_18001AC90
0x18001ac76  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x18001ac7a  call    cs:__imp_SysFreeString
0x18001ac80  nop
0x18001ac81  mov     rcx, [rbp+Name]; bstrString
0x18001ac85  call    cs:__imp_SysFreeString
0x18001ac8b  jmp     loc_18001AD15
0x18001ac90  lea     rdx, [rbp+Name]
0x18001ac94  lea     rcx, [rbp+var_8]
0x18001ac98  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18001ac9d  lea     rdx, [rbp+ReferencedDomainName]
0x18001aca1  lea     rcx, [rbp+var_10]
0x18001aca5  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18001acaa  nop
0x18001acab  mov     rcx, [rbp+ReferencedDomainName]; bstrString
0x18001acaf  call    cs:__imp_SysFreeString
0x18001acb5  nop
0x18001acb6  mov     rcx, [rbp+Name]; bstrString
0x18001acba  call    cs:__imp_SysFreeString
0x18001acc0  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18001acc4  lea     rcx, [rbp+Name]; this
0x18001acc8  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001accd  mov     rdx, rax
0x18001acd0  mov     rcx, r12
0x18001acd3  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001acd8  lea     rcx, [rbp+Name]; this
0x18001acdc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ace1  mov     [rbp+var_10], 0
0x18001ace9  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x18001aced  lea     rcx, [rbp+Name]; this
0x18001acf1  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001acf6  mov     rdx, rax
0x18001acf9  mov     rcx, r15
0x18001acfc  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001ad01  lea     rcx, [rbp+Name]; this
0x18001ad05  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ad0a  mov     eax, [rbp+var_28]
0x18001ad0d  mov     [r14], eax
0x18001ad10  mov     esi, 1
0x18001ad15  xor     ecx, ecx; bstrString
0x18001ad17  call    cs:__imp_SysFreeString
0x18001ad1d  nop
0x18001ad1e  xor     ecx, ecx; bstrString
0x18001ad20  call    cs:__imp_SysFreeString
0x18001ad26  mov     eax, esi
0x18001ad28  add     rsp, 60h
0x18001ad2c  pop     r15
0x18001ad2e  pop     r14
0x18001ad30  pop     r12
0x18001ad32  pop     rsi
0x18001ad33  pop     rbp
0x18001ad34  retn
```
