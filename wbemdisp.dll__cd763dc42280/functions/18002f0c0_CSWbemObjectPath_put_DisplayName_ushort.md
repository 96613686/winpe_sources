# CSWbemObjectPath::put_DisplayName(ushort *)

- ea: `0x18002f0c0`
- end: `0x18002f314`
- name: `?put_DisplayName@CSWbemObjectPath@@UEAAJPEAG@Z`
- size: `596`
- prototype: `int(CSWbemObjectPath *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18000f7d0`
- `0x18000fd64`
- `0x180010188`
- `0x18001051c`
- `0x180017ce0`
- `0x18001ca1c`
- `0x18002f0c0`
- `0x180032c08`
- `0x180034090`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002f114`
- `msvcrt!_wcsnicmp` at `0x18002f1e3`
- `msvcrt!_wcsnicmp` at `0x18002f114`
- `msvcrt!_wcsnicmp` at `0x18002f1e3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f285`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f2a1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f285`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f2a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f27a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f296`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f2b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f2bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f2cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f27a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f296`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f2b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f2bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f2cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemObjectPath::put_DisplayName(CSWbemObjectPath *this, unsigned __int16 *a2)
{
  int v4; // r14d
  int v5; // ebx
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  bool v9; // [rsp+40h] [rbp-C0h] BYREF
  bool v10; // [rsp+41h] [rbp-BFh] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  enum WbemAuthenticationLevelEnum v12; // [rsp+50h] [rbp-B0h] BYREF
  enum WbemImpersonationLevelEnum v13; // [rsp+54h] [rbp-ACh] BYREF
  BSTR v14; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *psz; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[144]; // [rsp+70h] [rbp-90h] BYREF

  v4 = -2147217407;
  ResetLastErrors();
  if ( !a2 )
    goto LABEL_14;
  v5 = 9;
  if ( _wcsnicmp(a2, L"WINMGMTS:", 9u) )
    goto LABEL_14;
  v9 = 0;
  v10 = 0;
  v12 = wbemAuthenticationLevelDefault;
  v13 = wbemImpersonationLevelAnonymous;
  CSWbemPrivilegeSet::CSWbemPrivilegeSet((CSWbemPrivilegeSet *)v16);
  psz = 0;
  v14 = 0;
  LODWORD(bstrString) = 0;
  if ( CWbemParseDN::ParseSecurity(
         a2 + 9,
         (unsigned int *)&bstrString,
         &v9,
         &v12,
         &v10,
         &v13,
         (struct CSWbemPrivilegeSet *)v16,
         &psz) )
  {
    v5 = (_DWORD)bstrString + 9;
  }
  LODWORD(bstrString) = 0;
  if ( CWbemParseDN::ParseLocale(&a2[v5], (unsigned int *)&bstrString, &v14) )
    v5 += (int)bstrString;
  v6 = &a2[v5];
  if ( *v6 )
    _wcsnicmp(v6, L"!", 1u);
  bstrString = 0;
  ATL::CComBSTR::operator=(&bstrString);
  v7 = *((_QWORD *)this + 14);
  if ( v7
    && *(_QWORD *)(v7 + 120)
    && (unsigned __int8)CWbemPathCracker::operator=(
                          *((CWbemPathCracker **)this + 18),
                          (struct ATL::CComBSTR *)&bstrString) )
  {
    *(_BYTE *)(*((_QWORD *)this + 14) + 108LL) = v9;
    *(_BYTE *)(*((_QWORD *)this + 14) + 109LL) = v10;
    *(_DWORD *)(*((_QWORD *)this + 14) + 112LL) = v12;
    *(_DWORD *)(*((_QWORD *)this + 14) + 116LL) = v13;
    CSWbemPrivilegeSet::Reset(
      *(CSWbemPrivilegeSet **)(*((_QWORD *)this + 14) + 120LL),
      (struct CSWbemPrivilegeSet *)v16);
    SysFreeString(*((BSTR *)this + 16));
    *((_QWORD *)this + 16) = SysAllocString(psz);
    SysFreeString(*((BSTR *)this + 15));
    *((_QWORD *)this + 15) = SysAllocString(v14);
    v4 = 0;
  }
  SysFreeString(bstrString);
  SysFreeString(v14);
  SysFreeString(psz);
  CSWbemPrivilegeSet::~CSWbemPrivilegeSet((CSWbemPrivilegeSet *)v16);
  if ( v4 < 0 )
LABEL_14:
    CDispatchHelp::RaiseException((CSWbemObjectPath *)((char *)this + 32), v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f0c0  mov     [rsp-8+arg_10], rbx
0x18002f0c5  mov     [rsp-8+arg_18], rsi
0x18002f0ca  push    rbp
0x18002f0cb  push    rdi
0x18002f0cc  push    r14
0x18002f0ce  lea     rbp, [rsp-10h]
0x18002f0d3  sub     rsp, 110h
0x18002f0da  mov     rax, cs:__security_cookie
0x18002f0e1  xor     rax, rsp
0x18002f0e4  mov     [rbp+20h+var_20], rax
0x18002f0e8  mov     rdi, rdx
0x18002f0eb  mov     rsi, rcx
0x18002f0ee  mov     r14d, 80041001h
0x18002f0f4  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002f0f9  test    rdi, rdi
0x18002f0fc  jz      loc_18002F2E1
0x18002f102  mov     ebx, 9
0x18002f107  mov     r8d, ebx; MaxCount
0x18002f10a  lea     rdx, aWinmgmts_0; "WINMGMTS:"
0x18002f111  mov     rcx, rdi; String1
0x18002f114  call    cs:__imp__wcsnicmp
0x18002f11a  test    eax, eax
0x18002f11c  jnz     loc_18002F2E1
0x18002f122  mov     [rsp+120h+var_E0], al
0x18002f126  mov     [rsp+120h+var_DF], al
0x18002f12a  mov     [rsp+120h+var_D0], eax
0x18002f12e  mov     [rsp+120h+var_CC], 1
0x18002f136  lea     rcx, [rsp+120h+var_B0]; this
0x18002f13b  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x18002f140  nop
0x18002f141  mov     [rsp+120h+psz], 0
0x18002f14a  mov     [rsp+120h+var_C8], 0
0x18002f153  mov     dword ptr [rsp+120h+bstrString], 0
0x18002f15b  lea     rcx, [rdi+12h]; unsigned __int16 *
0x18002f15f  lea     rax, [rsp+120h+psz]
0x18002f164  mov     [rsp+120h+var_E8], rax; unsigned __int16 **
0x18002f169  lea     rax, [rsp+120h+var_B0]
0x18002f16e  mov     [rsp+120h+var_F0], rax; struct CSWbemPrivilegeSet *
0x18002f173  lea     rax, [rsp+120h+var_CC]
0x18002f178  mov     [rsp+120h+var_F8], rax; enum WbemImpersonationLevelEnum *
0x18002f17d  lea     rax, [rsp+120h+var_DF]
0x18002f182  mov     [rsp+120h+var_100], rax; bool *
0x18002f187  lea     r9, [rsp+120h+var_D0]; enum WbemAuthenticationLevelEnum *
0x18002f18c  lea     r8, [rsp+120h+var_E0]; bool *
0x18002f191  lea     rdx, [rsp+120h+bstrString]; unsigned int *
0x18002f196  call    ?ParseSecurity@CWbemParseDN@@SA_NPEAGPEAKAEA_NPEAW4WbemAuthenticationLevelEnum@@2PEAW4WbemImpersonationLevelEnum@@AEAVCSWbemPrivilegeSet@@AEAPEAG@Z; CWbemParseDN::ParseSecurity(ushort *,ulong *,bool &,WbemAuthenticationLevelEnum *,bool &,WbemImpersonationLevelEnum *,CSWbemPrivilegeSet &,ushort * &)
0x18002f19b  test    al, al
0x18002f19d  jz      short loc_18002F1A6
0x18002f19f  mov     ebx, dword ptr [rsp+120h+bstrString]
0x18002f1a3  add     ebx, 9
0x18002f1a6  mov     dword ptr [rsp+120h+bstrString], 0
0x18002f1ae  mov     eax, ebx
0x18002f1b0  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x18002f1b4  lea     r8, [rsp+120h+var_C8]; unsigned __int16 **
0x18002f1b9  lea     rdx, [rsp+120h+bstrString]; unsigned int *
0x18002f1be  call    ?ParseLocale@CWbemParseDN@@SA_NPEAGPEAKAEAPEAG@Z; CWbemParseDN::ParseLocale(ushort *,ulong *,ushort * &)
0x18002f1c3  test    al, al
0x18002f1c5  jz      short loc_18002F1CB
0x18002f1c7  add     ebx, dword ptr [rsp+120h+bstrString]
0x18002f1cb  mov     eax, ebx
0x18002f1cd  lea     rcx, [rdi+rax*2]; String1
0x18002f1d1  xor     eax, eax
0x18002f1d3  cmp     ax, [rcx]
0x18002f1d6  jz      short loc_18002F1EF
0x18002f1d8  lea     r8d, [rax+1]; MaxCount
0x18002f1dc  lea     rdx, asc_18003AEE8; "!"
0x18002f1e3  call    cs:__imp__wcsnicmp
0x18002f1e9  test    eax, eax
0x18002f1eb  jnz     short loc_18002F1EF
0x18002f1ed  inc     ebx
0x18002f1ef  mov     [rsp+120h+bstrString], 0
0x18002f1f8  mov     eax, ebx
0x18002f1fa  lea     rdx, [rdi+rax*2]
0x18002f1fe  lea     rcx, [rsp+120h+bstrString]
0x18002f203  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002f208  mov     rax, [rsi+70h]
0x18002f20c  test    rax, rax
0x18002f20f  jz      loc_18002F2AE
0x18002f215  cmp     qword ptr [rax+78h], 0
0x18002f21a  jz      loc_18002F2AE
0x18002f220  lea     rdx, [rsp+120h+bstrString]; struct ATL::CComBSTR *
0x18002f225  mov     rcx, [rsi+90h]; this
0x18002f22c  call    ??4CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@@Z; CWbemPathCracker::operator=(ATL::CComBSTR const &)
0x18002f231  test    al, al
0x18002f233  jz      short loc_18002F2AE
0x18002f235  mov     rcx, [rsi+70h]
0x18002f239  mov     al, [rsp+120h+var_E0]
0x18002f23d  mov     [rcx+6Ch], al
0x18002f240  mov     rcx, [rsi+70h]
0x18002f244  mov     al, [rsp+120h+var_DF]
0x18002f248  mov     [rcx+6Dh], al
0x18002f24b  mov     rcx, [rsi+70h]
0x18002f24f  mov     eax, [rsp+120h+var_D0]
0x18002f253  mov     [rcx+70h], eax
0x18002f256  mov     rcx, [rsi+70h]
0x18002f25a  mov     eax, [rsp+120h+var_CC]
0x18002f25e  mov     [rcx+74h], eax
0x18002f261  mov     rcx, [rsi+70h]
0x18002f265  lea     rdx, [rsp+120h+var_B0]; struct CSWbemPrivilegeSet *
0x18002f26a  mov     rcx, [rcx+78h]; this
0x18002f26e  call    ?Reset@CSWbemPrivilegeSet@@QEAAXAEAV1@@Z; CSWbemPrivilegeSet::Reset(CSWbemPrivilegeSet &)
0x18002f273  mov     rcx, [rsi+80h]; bstrString
0x18002f27a  call    cs:__imp_SysFreeString
0x18002f280  mov     rcx, [rsp+120h+psz]; psz
0x18002f285  call    cs:__imp_SysAllocString
0x18002f28b  mov     [rsi+80h], rax
0x18002f292  mov     rcx, [rsi+78h]; bstrString
0x18002f296  call    cs:__imp_SysFreeString
0x18002f29c  mov     rcx, [rsp+120h+var_C8]; psz
0x18002f2a1  call    cs:__imp_SysAllocString
0x18002f2a7  mov     [rsi+78h], rax
0x18002f2ab  xor     r14d, r14d
0x18002f2ae  mov     rcx, [rsp+120h+bstrString]; bstrString
0x18002f2b3  call    cs:__imp_SysFreeString
0x18002f2b9  nop
0x18002f2ba  mov     rcx, [rsp+120h+var_C8]; bstrString
0x18002f2bf  call    cs:__imp_SysFreeString
0x18002f2c5  nop
0x18002f2c6  mov     rcx, [rsp+120h+psz]; bstrString
0x18002f2cb  call    cs:__imp_SysFreeString
0x18002f2d1  nop
0x18002f2d2  lea     rcx, [rsp+120h+var_B0]; this
0x18002f2d7  call    ??1CSWbemPrivilegeSet@@UEAA@XZ; CSWbemPrivilegeSet::~CSWbemPrivilegeSet(void)
0x18002f2dc  test    r14d, r14d
0x18002f2df  jns     short loc_18002F2ED
0x18002f2e1  lea     rcx, [rsi+20h]; this
0x18002f2e5  mov     edx, r14d; int
0x18002f2e8  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18002f2ed  mov     eax, r14d
0x18002f2f0  mov     rcx, [rbp+20h+var_20]
0x18002f2f4  xor     rcx, rsp; StackCookie
0x18002f2f7  call    __security_check_cookie
0x18002f2fc  lea     r11, [rsp+120h+var_10]
0x18002f304  mov     rbx, [r11+30h]
0x18002f308  mov     rsi, [r11+38h]
0x18002f30c  mov     rsp, r11
0x18002f30f  pop     r14
0x18002f311  pop     rdi
0x18002f312  pop     rbp
0x18002f313  retn
```
