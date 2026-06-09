# User::FromSidToDomainAccount(_bstr_t &,void *)

- ea: `0x1800421e8`
- end: `0x18004240f`
- name: `?FromSidToDomainAccount@User@@CAJAEAV_bstr_t@@PEAX@Z`
- size: `551`
- prototype: `__int64 __fastcall(struct _bstr_t *this, PSID Sid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180031ef0`

## callees

- `0x18000dc30`
- `0x18002a320`
- `0x1800322a0`
- `0x1800421e8`
- `0x180043190`
- `0x18004af28`
- `0x1800504b4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800422d8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800422f7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800422d8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800422f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800422c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800422cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180042332`
- `OLEAUT32!__imp_SysFreeString` at `0x18004233c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042395`
- `OLEAUT32!__imp_SysFreeString` at `0x18004239e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800422c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800422cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180042332`
- `OLEAUT32!__imp_SysFreeString` at `0x18004233c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042395`
- `OLEAUT32!__imp_SysFreeString` at `0x18004239e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004225b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004225b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423a8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180042255`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800422b2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180042255`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800422b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall User::FromSidToDomainAccount(struct _bstr_t *this, PSID Sid)
{
  BOOL v4; // esi
  UINT v5; // edx
  WCHAR *v6; // rbx
  UINT v7; // edx
  WCHAR *v8; // rdi
  bool v9; // r8
  _bstr_t *v10; // rax
  bool v11; // r8
  _bstr_t *v12; // rax
  signed int LastError; // eax
  unsigned int v14; // ebx
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-40h] BYREF
  __int64 v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-28h] BYREF
  WCHAR *v20; // [rsp+50h] [rbp-20h] BYREF
  WCHAR *v21; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v22; // [rsp+60h] [rbp-10h] BYREF
  DWORD ui; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+A8h] [rbp+38h] BYREF

  v18 = 0;
  v17 = 0;
  cchName = 0;
  ui = 0;
  peUse = SidTypeUnknown;
  v22 = 0;
  v19 = 0;
  LookupAccountSidLocalW(Sid, 0, &cchName, 0, &ui, &peUse);
  if ( GetLastError() == 122 )
  {
    v5 = cchName++;
    if ( v5 )
    {
      v6 = SysAllocStringLen(0, v5);
      v20 = v6;
      if ( !v6 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    else
    {
      v6 = 0;
      v20 = 0;
    }
    v7 = ui++;
    if ( v7 )
    {
      v8 = SysAllocStringLen(0, v7);
      v21 = v8;
      if ( !v8 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    else
    {
      v8 = 0;
      v21 = 0;
    }
    v4 = LookupAccountSidLocalW(Sid, v6, &cchName, v8, &ui, &peUse);
    if ( v4 )
    {
      ATL::CComBSTR::operator=(&v22, &v20);
      ATL::CComBSTR::operator=(&v19, &v21);
      SysFreeString(v8);
      SysFreeString(v6);
      v10 = _bstr_t::_bstr_t((_bstr_t *)&v21, v19, v9);
      _bstr_t::operator=(&v17, v10);
      _bstr_t::~_bstr_t((_bstr_t *)&v21);
      v19 = 0;
      v12 = _bstr_t::_bstr_t((_bstr_t *)&v21, v22, v11);
      _bstr_t::operator=(&v18, v12);
      _bstr_t::~_bstr_t((_bstr_t *)&v21);
      v4 = 1;
    }
    else
    {
      SysFreeString(v8);
      SysFreeString(v6);
    }
  }
  else
  {
    v4 = 0;
  }
  SysFreeString(0);
  SysFreeString(0);
  if ( v4 )
  {
    User::AssembleFullUserName(this, (struct _bstr_t *)&v17, (struct _bstr_t *)&v18);
    _bstr_t::~_bstr_t((_bstr_t *)&v17);
    _bstr_t::~_bstr_t((_bstr_t *)&v18);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    _bstr_t::~_bstr_t((_bstr_t *)&v17);
    _bstr_t::~_bstr_t((_bstr_t *)&v18);
    return v14;
  }
}

```

## disassembly

```asm
0x1800421e8  mov     r11, rsp
0x1800421eb  mov     [r11+8], rbx
0x1800421ef  mov     [r11+10h], rsi
0x1800421f3  push    rbp
0x1800421f4  push    rdi
0x1800421f5  push    r14
0x1800421f7  mov     rbp, rsp
0x1800421fa  sub     rsp, 70h
0x1800421fe  mov     rsi, rdx
0x180042201  mov     r14, rcx
0x180042204  mov     [rbp+var_30], 0
0x18004220c  mov     [rbp+var_38], 0
0x180042214  mov     [rbp+cchName], 0
0x18004221b  mov     [rbp+ui], 0
0x180042222  mov     [rbp+var_40], 8
0x180042229  mov     [rbp+var_10], 0
0x180042231  mov     [rbp+var_28], 0
0x180042239  lea     rax, [rbp+var_40]
0x18004223d  mov     [r11-60h], rax
0x180042241  lea     rax, [rbp+ui]
0x180042245  mov     [r11-68h], rax
0x180042249  xor     r9d, r9d; ReferencedDomainName
0x18004224c  lea     r8, [rbp+cchName]; cchName
0x180042250  xor     edx, edx; Name
0x180042252  mov     rcx, rsi; Sid
0x180042255  call    cs:__imp_LookupAccountSidLocalW
0x18004225b  call    cs:__imp_GetLastError
0x180042261  cmp     eax, 7Ah ; 'z'
0x180042264  jz      short loc_18004226D
0x180042266  xor     esi, esi
0x180042268  jmp     loc_180042393
0x18004226d  mov     edx, [rbp+cchName]; ui
0x180042270  lea     eax, [rdx+1]
0x180042273  mov     [rbp+cchName], eax
0x180042276  test    edx, edx
0x180042278  jnz     short loc_1800422D6
0x18004227a  xor     ebx, ebx
0x18004227c  mov     [rbp+var_20], rbx
0x180042280  mov     edx, [rbp+ui]; ui
0x180042283  lea     eax, [rdx+1]
0x180042286  mov     [rbp+ui], eax
0x180042289  test    edx, edx
0x18004228b  jnz     short loc_1800422F5
0x18004228d  xor     edi, edi
0x18004228f  mov     [rbp+var_18], rdi
0x180042293  lea     rax, [rbp+var_40]
0x180042297  mov     [rsp+70h+peUse], rax; peUse
0x18004229c  lea     rax, [rbp+ui]
0x1800422a0  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800422a5  mov     r9, rdi; ReferencedDomainName
0x1800422a8  lea     r8, [rbp+cchName]; cchName
0x1800422ac  mov     rdx, rbx; Name
0x1800422af  mov     rcx, rsi; Sid
0x1800422b2  call    cs:__imp_LookupAccountSidLocalW
0x1800422b8  mov     esi, eax
0x1800422ba  test    eax, eax
0x1800422bc  jnz     short loc_180042314
0x1800422be  mov     rcx, rdi; bstrString
0x1800422c1  call    cs:__imp_SysFreeString
0x1800422c7  nop
0x1800422c8  mov     rcx, rbx; bstrString
0x1800422cb  call    cs:__imp_SysFreeString
0x1800422d1  jmp     loc_180042393
0x1800422d6  xor     ecx, ecx; strIn
0x1800422d8  call    cs:__imp_SysAllocStringLen
0x1800422de  mov     rbx, rax
0x1800422e1  mov     [rbp+var_20], rax
0x1800422e5  test    rax, rax
0x1800422e8  jnz     short loc_180042280
0x1800422ea  mov     ecx, 8007000Eh; unsigned int
0x1800422ef  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800422f5  xor     ecx, ecx; strIn
0x1800422f7  call    cs:__imp_SysAllocStringLen
0x1800422fd  mov     rdi, rax
0x180042300  mov     [rbp+var_18], rax
0x180042304  test    rax, rax
0x180042307  jnz     short loc_180042293
0x180042309  mov     ecx, 8007000Eh; unsigned int
0x18004230e  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180042314  lea     rdx, [rbp+var_20]
0x180042318  lea     rcx, [rbp+var_10]
0x18004231c  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x180042321  lea     rdx, [rbp+var_18]
0x180042325  lea     rcx, [rbp+var_28]
0x180042329  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18004232e  nop
0x18004232f  mov     rcx, rdi; bstrString
0x180042332  call    cs:__imp_SysFreeString
0x180042338  nop
0x180042339  mov     rcx, rbx; bstrString
0x18004233c  call    cs:__imp_SysFreeString
0x180042342  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180042346  lea     rcx, [rbp+var_18]; this
0x18004234a  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18004234f  mov     rdx, rax
0x180042352  lea     rcx, [rbp+var_38]
0x180042356  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004235b  lea     rcx, [rbp+var_18]; this
0x18004235f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180042364  mov     [rbp+var_28], 0
0x18004236c  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180042370  lea     rcx, [rbp+var_18]; this
0x180042374  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180042379  mov     rdx, rax
0x18004237c  lea     rcx, [rbp+var_30]
0x180042380  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180042385  lea     rcx, [rbp+var_18]; this
0x180042389  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18004238e  mov     esi, 1
0x180042393  xor     ecx, ecx; bstrString
0x180042395  call    cs:__imp_SysFreeString
0x18004239b  nop
0x18004239c  xor     ecx, ecx; bstrString
0x18004239e  call    cs:__imp_SysFreeString
0x1800423a4  test    esi, esi
0x1800423a6  jnz     short loc_1800423D4
0x1800423a8  call    cs:__imp_GetLastError
0x1800423ae  mov     ebx, eax
0x1800423b0  test    eax, eax
0x1800423b2  jle     short loc_1800423BD
0x1800423b4  movzx   ebx, ax
0x1800423b7  or      ebx, 80070000h
0x1800423bd  lea     rcx, [rbp+var_38]; this
0x1800423c1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800423c6  nop
0x1800423c7  lea     rcx, [rbp+var_30]; this
0x1800423cb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800423d0  mov     eax, ebx
0x1800423d2  jmp     short loc_1800423FA
0x1800423d4  lea     r8, [rbp+var_30]; struct _bstr_t *
0x1800423d8  lea     rdx, [rbp+var_38]; struct _bstr_t *
0x1800423dc  mov     rcx, r14; this
0x1800423df  call    ?AssembleFullUserName@User@@CAJAEAV_bstr_t@@00@Z; User::AssembleFullUserName(_bstr_t &,_bstr_t &,_bstr_t &)
0x1800423e4  nop
0x1800423e5  lea     rcx, [rbp+var_38]; this
0x1800423e9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800423ee  nop
0x1800423ef  lea     rcx, [rbp+var_30]; this
0x1800423f3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800423f8  xor     eax, eax
0x1800423fa  lea     r11, [rsp+70h+var_s0]
0x1800423ff  mov     rbx, [r11+20h]
0x180042403  mov     rsi, [r11+28h]
0x180042407  mov     rsp, r11
0x18004240a  pop     r14
0x18004240c  pop     rdi
0x18004240d  pop     rbp
0x18004240e  retn
```
