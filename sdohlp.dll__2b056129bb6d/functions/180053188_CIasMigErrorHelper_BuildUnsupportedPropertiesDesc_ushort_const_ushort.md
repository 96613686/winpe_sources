# CIasMigErrorHelper::BuildUnsupportedPropertiesDesc(ushort const *,ushort * *)

- ea: `0x180053188`
- end: `0x1800534a7`
- name: `?BuildUnsupportedPropertiesDesc@CIasMigErrorHelper@@SAJPEBGPEAPEAG@Z`
- size: `799`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18004cdf4`

## callees

- `0x18002cca4`
- `0x18002cd74`
- `0x18002d08c`
- `0x18002efa0`
- `0x180039924`
- `0x18003f638`
- `0x180042a80`
- `0x180053188`
- `0x180053c30`
- `0x180054220`
- `0x180054320`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180053441`
- `OLEAUT32!__imp_SysAllocString` at `0x180053441`

## string_xrefs

- `0x1800531ac`: `iasmigplugin.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CIasMigErrorHelper::BuildUnsupportedPropertiesDesc(
        const unsigned __int16 *a1,
        unsigned __int16 **a2)
{
  int StringFromResource; // ebx
  __int64 *v4; // rbx
  __int64 v5; // rax
  const OLECHAR *v6; // rcx
  unsigned __int16 *v7; // rax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  __int64 v10; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v11[16]; // [rsp+40h] [rbp-10h] BYREF
  const unsigned __int16 *v12; // [rsp+70h] [rbp+20h] BYREF
  __int64 v13; // [rsp+80h] [rbp+30h] BYREF
  __int64 v14; // [rsp+88h] [rbp+38h] BYREF

  v12 = a1;
  v10 = 0;
  CPolicyectionErrorInfo::printSectionErrors(
    (CPolicyectionErrorInfo *)CIasMigErrorHelper::m_crpErrors,
    L"iasmigplugin.dll",
    (struct _bstr_t *)&v10);
  v9 = 0;
  CPolicyectionErrorInfo::printSectionErrors(
    (CPolicyectionErrorInfo *)CIasMigErrorHelper::m_npErrors,
    L"iasmigplugin.dll",
    (struct _bstr_t *)&v9);
  v14 = 0;
  CClientsSectionErrorInfo::printSectionErrors(
    (CClientsSectionErrorInfo *)&CIasMigErrorHelper::m_clientsErrors,
    L"iasmigplugin.dll",
    (struct _bstr_t *)&v14);
  if ( !_bstr_t::length((_bstr_t *)&v10) && !_bstr_t::length((_bstr_t *)&v9) && !_bstr_t::length((_bstr_t *)&v14) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("errorDescription is empty");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids, "NPSDS");
    }
    *a2 = 0;
    goto LABEL_33;
  }
  v12 = 0;
  StringFromResource = CIasMigErrorHelper::ReadStringFromResource(L"iasmigplugin.dll", 0x1C2u, (struct _bstr_t *)&v12);
  if ( StringFromResource < 0 )
    goto LABEL_10;
  v13 = 0;
  StringFromResource = CIasMigErrorHelper::ReadStringFromResource(L"iasmigplugin.dll", 0x198u, (struct _bstr_t *)&v13);
  if ( StringFromResource < 0 )
    goto LABEL_12;
  _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)&v13);
  if ( _bstr_t::length((_bstr_t *)&v10) )
  {
    _bstr_t::_bstr_t((_bstr_t *)v11, L"\n");
    _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)v11);
    _bstr_t::_Free((_bstr_t *)v11);
    _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)&v10);
  }
  if ( _bstr_t::length((_bstr_t *)&v9) )
  {
    _bstr_t::_bstr_t((_bstr_t *)v11, L"\n");
    _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)v11);
    _bstr_t::_Free((_bstr_t *)v11);
    _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)&v9);
  }
  if ( _bstr_t::length((_bstr_t *)&v14) )
  {
    _bstr_t::_bstr_t((_bstr_t *)v11, L"\n");
    _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)v11);
    _bstr_t::_Free((_bstr_t *)v11);
    _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)&v14);
  }
  StringFromResource = CIasMigErrorHelper::ReadStringFromResource(L"iasmigplugin.dll", 0x1C3u, (struct _bstr_t *)&v13);
  if ( StringFromResource < 0 )
  {
LABEL_12:
    _bstr_t::_Free((_bstr_t *)&v13);
LABEL_10:
    _bstr_t::_Free((_bstr_t *)&v12);
    goto LABEL_34;
  }
  _bstr_t::operator+=((struct _bstr_t *)&v12, (struct _bstr_t *)&v13);
  v4 = (__int64 *)v12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("errorDescription was built: %S");
    if ( v4 )
      v5 = *v4;
    else
      v5 = 0;
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids,
      (unsigned int)"NPSDS",
      v5);
  }
  if ( v4 )
    v6 = (const OLECHAR *)*v4;
  else
    v6 = 0;
  v7 = SysAllocString(v6);
  *a2 = v7;
  if ( v7 )
  {
    _bstr_t::_Free((_bstr_t *)&v13);
    _bstr_t::_Free((_bstr_t *)&v12);
LABEL_33:
    StringFromResource = 0;
    goto LABEL_34;
  }
  _bstr_t::_Free((_bstr_t *)&v13);
  _bstr_t::_Free((_bstr_t *)&v12);
  StringFromResource = 14;
LABEL_34:
  _bstr_t::_Free((_bstr_t *)&v14);
  _bstr_t::_Free((_bstr_t *)&v9);
  _bstr_t::_Free((_bstr_t *)&v10);
  return (unsigned int)StringFromResource;
}

```

## disassembly

```asm
0x180053188  mov     [rsp-18h+arg_8], rbx
0x18005318d  mov     [rsp-18h+arg_0], rcx
0x180053192  push    rbp
0x180053193  push    rdi
0x180053194  push    r14
0x180053196  mov     rbp, rsp
0x180053199  sub     rsp, 50h
0x18005319d  mov     rdi, rdx
0x1800531a0  mov     [rbp+var_18], 0
0x1800531a8  lea     r8, [rbp+var_18]; struct _bstr_t *
0x1800531ac  lea     r14, aIasmigpluginDl; "iasmigplugin.dll"
0x1800531b3  mov     rdx, r14; unsigned __int16 *
0x1800531b6  lea     rcx, ?m_crpErrors@CIasMigErrorHelper@@0VCPolicyectionErrorInfo@@A; this
0x1800531bd  call    ?printSectionErrors@CPolicyectionErrorInfo@@UEAAJPEBGAEAV_bstr_t@@@Z; CPolicyectionErrorInfo::printSectionErrors(ushort const *,_bstr_t &)
0x1800531c2  mov     [rbp+var_20], 0
0x1800531ca  lea     r8, [rbp+var_20]; struct _bstr_t *
0x1800531ce  mov     rdx, r14; unsigned __int16 *
0x1800531d1  lea     rcx, ?m_npErrors@CIasMigErrorHelper@@0VCPolicyectionErrorInfo@@A; this
0x1800531d8  call    ?printSectionErrors@CPolicyectionErrorInfo@@UEAAJPEBGAEAV_bstr_t@@@Z; CPolicyectionErrorInfo::printSectionErrors(ushort const *,_bstr_t &)
0x1800531dd  mov     [rbp+arg_18], 0
0x1800531e5  lea     r8, [rbp+arg_18]; struct _bstr_t *
0x1800531e9  mov     rdx, r14; unsigned __int16 *
0x1800531ec  lea     rcx, ?m_clientsErrors@CIasMigErrorHelper@@0VCClientsSectionErrorInfo@@A; this
0x1800531f3  call    ?printSectionErrors@CClientsSectionErrorInfo@@UEAAJPEBGAEAV_bstr_t@@@Z; CClientsSectionErrorInfo::printSectionErrors(ushort const *,_bstr_t &)
0x1800531f8  lea     rcx, [rbp+var_18]; this
0x1800531fc  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180053201  test    eax, eax
0x180053203  jnz     short loc_180053279
0x180053205  lea     rcx, [rbp+var_20]; this
0x180053209  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18005320e  test    eax, eax
0x180053210  jnz     short loc_180053279
0x180053212  lea     rcx, [rbp+arg_18]; this
0x180053216  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18005321b  test    eax, eax
0x18005321d  jnz     short loc_180053279
0x18005321f  lea     rcx, WPP_GLOBAL_Control
0x180053226  mov     rax, cs:WPP_GLOBAL_Control
0x18005322d  cmp     rax, rcx
0x180053230  jz      short loc_18005326D
0x180053232  cmp     byte ptr [rax+19h], 4
0x180053236  jb      short loc_18005326D
0x180053238  test    byte ptr [rax+1Ch], 10h
0x18005323c  jz      short loc_18005326D
0x18005323e  lea     rcx, aErrordescripti_0; "errorDescription is empty"
0x180053245  call    WppDbgPrint
0x18005324a  mov     edx, 0Bh
0x18005324f  lea     r9, aNpsds; "NPSDS"
0x180053256  lea     r8, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids
0x18005325d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053264  mov     rcx, [rcx+10h]
0x180053268  call    WPP_SF_s
0x18005326d  mov     qword ptr [rdi], 0
0x180053274  jmp     loc_180053478
0x180053279  mov     [rbp+arg_0], 0
0x180053281  lea     r8, [rbp+arg_0]; struct _bstr_t *
0x180053285  mov     edx, 1C2h; uID
0x18005328a  mov     rcx, r14; lpLibFileName
0x18005328d  call    ?ReadStringFromResource@CIasMigErrorHelper@@SAJPEBGIAEAV_bstr_t@@@Z; CIasMigErrorHelper::ReadStringFromResource(ushort const *,uint,_bstr_t &)
0x180053292  mov     ebx, eax
0x180053294  test    eax, eax
0x180053296  jns     short loc_1800532A6
0x180053298  lea     rcx, [rbp+arg_0]; this
0x18005329c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800532a1  jmp     loc_18005347A
0x1800532a6  mov     [rbp+arg_10], 0
0x1800532ae  lea     r8, [rbp+arg_10]; struct _bstr_t *
0x1800532b2  mov     edx, 198h; uID
0x1800532b7  mov     rcx, r14; lpLibFileName
0x1800532ba  call    ?ReadStringFromResource@CIasMigErrorHelper@@SAJPEBGIAEAV_bstr_t@@@Z; CIasMigErrorHelper::ReadStringFromResource(ushort const *,uint,_bstr_t &)
0x1800532bf  mov     ebx, eax
0x1800532c1  test    eax, eax
0x1800532c3  jns     short loc_1800532D0
0x1800532c5  lea     rcx, [rbp+arg_10]; this
0x1800532c9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800532ce  jmp     short loc_180053298
0x1800532d0  lea     rdx, [rbp+arg_10]; struct _bstr_t *
0x1800532d4  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x1800532d8  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800532dd  lea     rcx, [rbp+var_18]; this
0x1800532e1  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800532e6  lea     rbx, asc_180064360; "\n"
0x1800532ed  test    eax, eax
0x1800532ef  jz      short loc_180053322
0x1800532f1  mov     rdx, rbx; unsigned __int16 *
0x1800532f4  lea     rcx, [rbp+var_10]; this
0x1800532f8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800532fd  nop
0x1800532fe  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x180053302  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x180053306  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18005330b  nop
0x18005330c  lea     rcx, [rbp+var_10]; this
0x180053310  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053315  lea     rdx, [rbp+var_18]; struct _bstr_t *
0x180053319  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x18005331d  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180053322  lea     rcx, [rbp+var_20]; this
0x180053326  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18005332b  test    eax, eax
0x18005332d  jz      short loc_180053360
0x18005332f  mov     rdx, rbx; unsigned __int16 *
0x180053332  lea     rcx, [rbp+var_10]; this
0x180053336  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18005333b  nop
0x18005333c  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x180053340  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x180053344  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180053349  nop
0x18005334a  lea     rcx, [rbp+var_10]; this
0x18005334e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053353  lea     rdx, [rbp+var_20]; struct _bstr_t *
0x180053357  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x18005335b  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180053360  lea     rcx, [rbp+arg_18]; this
0x180053364  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180053369  test    eax, eax
0x18005336b  jz      short loc_18005339E
0x18005336d  mov     rdx, rbx; unsigned __int16 *
0x180053370  lea     rcx, [rbp+var_10]; this
0x180053374  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053379  nop
0x18005337a  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x18005337e  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x180053382  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180053387  nop
0x180053388  lea     rcx, [rbp+var_10]; this
0x18005338c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053391  lea     rdx, [rbp+arg_18]; struct _bstr_t *
0x180053395  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x180053399  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18005339e  lea     r8, [rbp+arg_10]; struct _bstr_t *
0x1800533a2  mov     edx, 1C3h; uID
0x1800533a7  mov     rcx, r14; lpLibFileName
0x1800533aa  call    ?ReadStringFromResource@CIasMigErrorHelper@@SAJPEBGIAEAV_bstr_t@@@Z; CIasMigErrorHelper::ReadStringFromResource(ushort const *,uint,_bstr_t &)
0x1800533af  mov     ebx, eax
0x1800533b1  test    eax, eax
0x1800533b3  js      loc_1800532C5
0x1800533b9  lea     rdx, [rbp+arg_10]; struct _bstr_t *
0x1800533bd  lea     rcx, [rbp+arg_0]; struct _bstr_t *
0x1800533c1  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800533c6  lea     rcx, WPP_GLOBAL_Control
0x1800533cd  mov     rbx, [rbp+arg_0]
0x1800533d1  mov     rax, cs:WPP_GLOBAL_Control
0x1800533d8  cmp     rax, rcx
0x1800533db  jz      short loc_180053435
0x1800533dd  cmp     byte ptr [rax+19h], 4
0x1800533e1  jb      short loc_180053435
0x1800533e3  test    byte ptr [rax+1Ch], 10h
0x1800533e7  jz      short loc_180053435
0x1800533e9  test    rbx, rbx
0x1800533ec  jz      short loc_1800533F3
0x1800533ee  mov     rdx, [rbx]
0x1800533f1  jmp     short loc_1800533F5
0x1800533f3  xor     edx, edx
0x1800533f5  lea     rcx, aErrordescripti; "errorDescription was built: %S"
0x1800533fc  call    WppDbgPrint
0x180053401  test    rbx, rbx
0x180053404  jz      short loc_18005340B
0x180053406  mov     rax, [rbx]
0x180053409  jmp     short loc_18005340D
0x18005340b  xor     eax, eax
0x18005340d  mov     edx, 0Ch
0x180053412  mov     [rsp+50h+var_30], rax
0x180053417  lea     r9, aNpsds; "NPSDS"
0x18005341e  lea     r8, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids
0x180053425  mov     rcx, cs:WPP_GLOBAL_Control
0x18005342c  mov     rcx, [rcx+10h]
0x180053430  call    WPP_SF_sS
0x180053435  test    rbx, rbx
0x180053438  jz      short loc_18005343F
0x18005343a  mov     rcx, [rbx]
0x18005343d  jmp     short loc_180053441
0x18005343f  xor     ecx, ecx; psz
0x180053441  call    cs:__imp_SysAllocString
0x180053447  mov     [rdi], rax
0x18005344a  lea     rcx, [rbp+arg_10]; this
0x18005344e  test    rax, rax
0x180053451  jnz     short loc_180053469
0x180053453  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053458  nop
0x180053459  lea     rcx, [rbp+arg_0]; this
0x18005345d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053462  mov     ebx, 0Eh
0x180053467  jmp     short loc_18005347A
0x180053469  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18005346e  nop
0x18005346f  lea     rcx, [rbp+arg_0]; this
0x180053473  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053478  xor     ebx, ebx
0x18005347a  lea     rcx, [rbp+arg_18]; this
0x18005347e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053483  nop
0x180053484  lea     rcx, [rbp+var_20]; this
0x180053488  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18005348d  nop
0x18005348e  lea     rcx, [rbp+var_18]; this
0x180053492  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053497  mov     eax, ebx
0x180053499  mov     rbx, [rsp+50h+arg_8]
0x18005349e  add     rsp, 50h
0x1800534a2  pop     r14
0x1800534a4  pop     rdi
0x1800534a5  pop     rbp
0x1800534a6  retn
```
