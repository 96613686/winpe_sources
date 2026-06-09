# User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)

- ea: `0x18002933c`
- end: `0x180029501`
- name: `?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct _bstr_t *, struct _bstr_t *, enum _SID_NAME_USE *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800291e8`
- `0x1800679e0`

## callees

- `0x18000dc30`
- `0x18002933c`
- `0x18002a320`
- `0x1800322a0`
- `0x18004af28`
- `0x1800504b4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180029420`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002943f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180029420`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002943f`
- `OLEAUT32!__imp_SysFreeString` at `0x180029409`
- `OLEAUT32!__imp_SysFreeString` at `0x180029413`
- `OLEAUT32!__imp_SysFreeString` at `0x18002947a`
- `OLEAUT32!__imp_SysFreeString` at `0x180029484`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294ea`
- `OLEAUT32!__imp_SysFreeString` at `0x180029409`
- `OLEAUT32!__imp_SysFreeString` at `0x180029413`
- `OLEAUT32!__imp_SysFreeString` at `0x18002947a`
- `OLEAUT32!__imp_SysFreeString` at `0x180029484`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293a3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002939d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800293fa`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002939d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800293fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x18002933c  push    rbp
0x18002933e  push    rbx
0x18002933f  push    rsi
0x180029340  push    rdi
0x180029341  push    r12
0x180029343  push    r14
0x180029345  push    r15
0x180029347  mov     rbp, rsp
0x18002934a  sub     rsp, 60h
0x18002934e  mov     rsi, r9
0x180029351  mov     r14, r8
0x180029354  mov     r15, rdx
0x180029357  mov     r12, rcx
0x18002935a  mov     [rbp+cchName], 0
0x180029361  mov     [rbp+ui], 0
0x180029368  mov     [rbp+var_28], 8
0x18002936f  mov     [rbp+var_8], 0
0x180029377  mov     [rbp+var_20], 0
0x18002937f  lea     rax, [rbp+var_28]
0x180029383  mov     [rsp+60h+peUse], rax; peUse
0x180029388  lea     rax, [rbp+ui]
0x18002938c  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180029391  xor     r9d, r9d; ReferencedDomainName
0x180029394  lea     r8, [rbp+cchName]; cchName
0x180029398  xor     edx, edx; Name
0x18002939a  mov     rcx, rsi; Sid
0x18002939d  call    cs:__imp_LookupAccountSidLocalW
0x1800293a3  call    cs:__imp_GetLastError
0x1800293a9  cmp     eax, 7Ah ; 'z'
0x1800293ac  jz      short loc_1800293B5
0x1800293ae  xor     esi, esi
0x1800293b0  jmp     loc_1800294DF
0x1800293b5  mov     edx, [rbp+cchName]; ui
0x1800293b8  lea     eax, [rdx+1]
0x1800293bb  mov     [rbp+cchName], eax
0x1800293be  test    edx, edx
0x1800293c0  jnz     short loc_18002941E
0x1800293c2  xor     ebx, ebx
0x1800293c4  mov     [rbp+var_18], rbx
0x1800293c8  mov     edx, [rbp+ui]; ui
0x1800293cb  lea     eax, [rdx+1]
0x1800293ce  mov     [rbp+ui], eax
0x1800293d1  test    edx, edx
0x1800293d3  jnz     short loc_18002943D
0x1800293d5  xor     edi, edi
0x1800293d7  mov     [rbp+var_10], rdi
0x1800293db  lea     rax, [rbp+var_28]
0x1800293df  mov     [rsp+60h+peUse], rax; peUse
0x1800293e4  lea     rax, [rbp+ui]
0x1800293e8  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800293ed  mov     r9, rdi; ReferencedDomainName
0x1800293f0  lea     r8, [rbp+cchName]; cchName
0x1800293f4  mov     rdx, rbx; Name
0x1800293f7  mov     rcx, rsi; Sid
0x1800293fa  call    cs:__imp_LookupAccountSidLocalW
0x180029400  mov     esi, eax
0x180029402  test    eax, eax
0x180029404  jnz     short loc_18002945C
0x180029406  mov     rcx, rdi; bstrString
0x180029409  call    cs:__imp_SysFreeString
0x18002940f  nop
0x180029410  mov     rcx, rbx; bstrString
0x180029413  call    cs:__imp_SysFreeString
0x180029419  jmp     loc_1800294DF
0x18002941e  xor     ecx, ecx; strIn
0x180029420  call    cs:__imp_SysAllocStringLen
0x180029426  mov     rbx, rax
0x180029429  mov     [rbp+var_18], rax
0x18002942d  test    rax, rax
0x180029430  jnz     short loc_1800293C8
0x180029432  mov     ecx, 8007000Eh; unsigned int
0x180029437  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002943d  xor     ecx, ecx; strIn
0x18002943f  call    cs:__imp_SysAllocStringLen
0x180029445  mov     rdi, rax
0x180029448  mov     [rbp+var_10], rax
0x18002944c  test    rax, rax
0x18002944f  jnz     short loc_1800293DB
0x180029451  mov     ecx, 8007000Eh; unsigned int
0x180029456  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002945c  lea     rdx, [rbp+var_18]
0x180029460  lea     rcx, [rbp+var_8]
0x180029464  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x180029469  lea     rdx, [rbp+var_10]
0x18002946d  lea     rcx, [rbp+var_20]
0x180029471  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x180029476  nop
0x180029477  mov     rcx, rdi; bstrString
0x18002947a  call    cs:__imp_SysFreeString
0x180029480  nop
0x180029481  mov     rcx, rbx; bstrString
0x180029484  call    cs:__imp_SysFreeString
0x18002948a  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18002948e  lea     rcx, [rbp+var_10]; this
0x180029492  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180029497  mov     rdx, rax
0x18002949a  mov     rcx, r12
0x18002949d  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800294a2  lea     rcx, [rbp+var_10]; this
0x1800294a6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800294ab  mov     [rbp+var_20], 0
0x1800294b3  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x1800294b7  lea     rcx, [rbp+var_10]; this
0x1800294bb  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x1800294c0  mov     rdx, rax
0x1800294c3  mov     rcx, r15
0x1800294c6  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800294cb  lea     rcx, [rbp+var_10]; this
0x1800294cf  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800294d4  mov     eax, [rbp+var_28]
0x1800294d7  mov     [r14], eax
0x1800294da  mov     esi, 1
0x1800294df  xor     ecx, ecx; bstrString
0x1800294e1  call    cs:__imp_SysFreeString
0x1800294e7  nop
0x1800294e8  xor     ecx, ecx; bstrString
0x1800294ea  call    cs:__imp_SysFreeString
0x1800294f0  mov     eax, esi
0x1800294f2  add     rsp, 60h
0x1800294f6  pop     r15
0x1800294f8  pop     r14
0x1800294fa  pop     r12
0x1800294fc  pop     rdi
0x1800294fd  pop     rsi
0x1800294fe  pop     rbx
0x1800294ff  pop     rbp
0x180029500  retn
```
