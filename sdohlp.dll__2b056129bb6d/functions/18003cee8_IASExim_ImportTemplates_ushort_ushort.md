# IASExim::ImportTemplates(ushort *,ushort *)

- ea: `0x18003cee8`
- end: `0x18003d138`
- name: `?ImportTemplates@IASExim@@QEAAJPEAG0@Z`
- size: `592`
- prototype: `int(IASExim *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002e770`

## callees

- `0x18002cca4`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002efa0`
- `0x180039830`
- `0x180039924`
- `0x18003cee8`
- `0x18003f638`
- `0x180042a80`
- `0x180047298`
- `0x1800477a4`
- `0x180058010`

## string_xrefs

- `0x18003d033`: `IDR_IASTEMPLATES_XML_RES.XML`
- `0x18003d027`: `IDR_IASTEMPLATESMIG_XML_RES_XML`
- `0x18003cfef`: `iasTemplates_converted.xml`
- `0x18003cf66`: `Cannot find IAS system directory`
- `0x18003d076`: `Failed to convert XML to current version. Import failed.`
- `0x18003d0d5`: `m_pXmlHelper->Import failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IASExim::ImportTemplates(IASExim *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rbx
  const unsigned __int16 *v9; // r8
  const unsigned __int16 **v10; // rbx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v14; // [rsp+20h] [rbp-20h]
  _BYTE v15[16]; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+20h] BYREF
  const unsigned __int16 **v17; // [rsp+78h] [rbp+38h] BYREF

  if ( *(_QWORD *)this && a3 )
  {
    v17 = 0;
    v16 = 0;
    if ( (unsigned int)CUtils::GetIAS2Directory(this, (struct _bstr_t *)&v16) )
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_30;
      }
      WppDbgPrint("Cannot find IAS system directory");
      v7 = 41;
    }
    else
    {
      _bstr_t::operator=(&v17, &v16);
      if ( v16 )
        v8 = *v16;
      else
        v8 = 0;
      if ( *(_WORD *)(v8 + 2LL * (_bstr_t::length((_bstr_t *)&v16) - 1)) != 92 )
      {
        _bstr_t::_bstr_t((_bstr_t *)v15, L"\\");
        _bstr_t::operator+=((struct _bstr_t *)&v17, (struct _bstr_t *)v15);
        _bstr_t::_Free((_bstr_t *)v15);
      }
      _bstr_t::_bstr_t((_bstr_t *)v15, L"iasTemplates_converted.xml");
      _bstr_t::operator+=((struct _bstr_t *)&v17, (struct _bstr_t *)v15);
      _bstr_t::_Free((_bstr_t *)v15);
      v10 = v17;
      if ( v17 )
        v11 = *v17;
      else
        v11 = 0;
      v6 = CIASXMLConverter::ConvertIasXMLToCurrentVersion(
             a3,
             v11,
             v9,
             L"IDR_IASTEMPLATES_XML_RES.XML",
             v14,
             L"IDR_IASTEMPLATESMIG_XML_RES_XML");
      if ( v6 >= 0 )
      {
        if ( v10 )
          v12 = *v10;
        else
          v12 = 0;
        v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, const unsigned __int16 *))(**(_QWORD **)this + 40LL))(
               *(_QWORD *)this,
               a2,
               v12);
        if ( v6 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("m_pXmlHelper->Import failed with 0x%x");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            v6);
        }
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
LABEL_30:
        _bstr_t::_Free((_bstr_t *)&v16);
        _bstr_t::_Free((_bstr_t *)&v17);
        return (unsigned int)v6;
      }
      WppDbgPrint("Failed to convert XML to current version. Import failed.");
      v7 = 42;
    }
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
    goto LABEL_30;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18003cee8  mov     [rsp-18h+arg_8], rbx
0x18003ceed  mov     [rsp-18h+arg_10], rsi
0x18003cef2  push    rbp
0x18003cef3  push    rdi
0x18003cef4  push    r14
0x18003cef6  mov     rbp, rsp
0x18003cef9  sub     rsp, 40h
0x18003cefd  mov     rdi, r8
0x18003cf00  mov     r14, rdx
0x18003cf03  mov     rsi, rcx
0x18003cf06  cmp     qword ptr [rcx], 0
0x18003cf0a  jz      loc_18003D120
0x18003cf10  test    r8, r8
0x18003cf13  jz      loc_18003D120
0x18003cf19  mov     [rbp+arg_18], 0
0x18003cf21  mov     [rbp+arg_0], 0
0x18003cf29  lea     rdx, [rbp+arg_0]; struct _bstr_t *
0x18003cf2d  call    ?GetIAS2Directory@CUtils@@QEBAJAEAV_bstr_t@@@Z; CUtils::GetIAS2Directory(_bstr_t &)
0x18003cf32  test    eax, eax
0x18003cf34  jz      short loc_18003CF98
0x18003cf36  xor     edi, edi
0x18003cf38  lea     rax, WPP_GLOBAL_Control
0x18003cf3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf46  cmp     rcx, rax
0x18003cf49  jz      loc_18003D109
0x18003cf4f  cmp     byte ptr [rcx+19h], 2
0x18003cf53  jb      loc_18003D109
0x18003cf59  test    dword ptr [rcx+1Ch], 400h
0x18003cf60  jz      loc_18003D109
0x18003cf66  lea     rcx, aCannotFindIasS; "Cannot find IAS system directory"
0x18003cf6d  call    WppDbgPrint
0x18003cf72  lea     edx, [rdi+29h]
0x18003cf75  lea     r9, aNpssdo; "NPSSDO"
0x18003cf7c  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003cf83  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf8a  mov     rcx, [rcx+10h]
0x18003cf8e  call    WPP_SF_s
0x18003cf93  jmp     loc_18003D109
0x18003cf98  lea     rdx, [rbp+arg_0]
0x18003cf9c  lea     rcx, [rbp+arg_18]
0x18003cfa0  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18003cfa5  mov     rax, [rbp+arg_0]
0x18003cfa9  test    rax, rax
0x18003cfac  jz      short loc_18003CFB3
0x18003cfae  mov     rbx, [rax]
0x18003cfb1  jmp     short loc_18003CFB5
0x18003cfb3  xor     ebx, ebx
0x18003cfb5  lea     rcx, [rbp+arg_0]; this
0x18003cfb9  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003cfbe  dec     eax
0x18003cfc0  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18003cfc5  jz      short loc_18003CFEF
0x18003cfc7  lea     rdx, asc_180064534; "\\"
0x18003cfce  lea     rcx, [rbp+var_10]; this
0x18003cfd2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003cfd7  nop
0x18003cfd8  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x18003cfdc  lea     rcx, [rbp+arg_18]; struct _bstr_t *
0x18003cfe0  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18003cfe5  nop
0x18003cfe6  lea     rcx, [rbp+var_10]; this
0x18003cfea  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003cfef  lea     rdx, aIastemplatesCo; "iasTemplates_converted.xml"
0x18003cff6  lea     rcx, [rbp+var_10]; this
0x18003cffa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003cfff  nop
0x18003d000  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x18003d004  lea     rcx, [rbp+arg_18]; struct _bstr_t *
0x18003d008  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18003d00d  nop
0x18003d00e  lea     rcx, [rbp+var_10]; this
0x18003d012  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d017  mov     rbx, [rbp+arg_18]
0x18003d01b  test    rbx, rbx
0x18003d01e  jz      short loc_18003D025
0x18003d020  mov     rdx, [rbx]
0x18003d023  jmp     short loc_18003D027
0x18003d025  xor     edx, edx; unsigned __int16 *
0x18003d027  lea     rax, aIdrIastemplate; "IDR_IASTEMPLATESMIG_XML_RES_XML"
0x18003d02e  mov     [rsp+40h+var_18], rax; unsigned __int16 *
0x18003d033  lea     r9, aIdrIastemplate_0; "IDR_IASTEMPLATES_XML_RES.XML"
0x18003d03a  mov     rcx, rdi; unsigned __int16 *
0x18003d03d  call    ?ConvertIasXMLToCurrentVersion@CIASXMLConverter@@SAJPEBG00000@Z; CIASXMLConverter::ConvertIasXMLToCurrentVersion(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003d042  mov     edi, eax
0x18003d044  test    eax, eax
0x18003d046  jns     short loc_18003D08C
0x18003d048  lea     rax, WPP_GLOBAL_Control
0x18003d04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d056  cmp     rcx, rax
0x18003d059  jz      loc_18003D109
0x18003d05f  cmp     byte ptr [rcx+19h], 2
0x18003d063  jb      loc_18003D109
0x18003d069  test    dword ptr [rcx+1Ch], 400h
0x18003d070  jz      loc_18003D109
0x18003d076  lea     rcx, aFailedToConver; "Failed to convert XML to current versio"...
0x18003d07d  call    WppDbgPrint
0x18003d082  mov     edx, 2Ah ; '*'
0x18003d087  jmp     loc_18003CF75
0x18003d08c  mov     rcx, [rsi]
0x18003d08f  mov     rax, [rcx]
0x18003d092  test    rbx, rbx
0x18003d095  jz      short loc_18003D09C
0x18003d097  mov     r8, [rbx]
0x18003d09a  jmp     short loc_18003D09F
0x18003d09c  xor     r8d, r8d
0x18003d09f  mov     rdx, r14
0x18003d0a2  mov     rax, [rax+28h]
0x18003d0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0ab  mov     edi, eax
0x18003d0ad  test    eax, eax
0x18003d0af  jns     short loc_18003D109
0x18003d0b1  lea     rax, WPP_GLOBAL_Control
0x18003d0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0bf  cmp     rcx, rax
0x18003d0c2  jz      short loc_18003D109
0x18003d0c4  cmp     byte ptr [rcx+19h], 2
0x18003d0c8  jb      short loc_18003D109
0x18003d0ca  test    dword ptr [rcx+1Ch], 400h
0x18003d0d1  jz      short loc_18003D109
0x18003d0d3  mov     edx, edi
0x18003d0d5  lea     rcx, aMPxmlhelperImp; "m_pXmlHelper->Import failed with 0x%x"
0x18003d0dc  call    WppDbgPrint
0x18003d0e1  mov     edx, 2Bh ; '+'
0x18003d0e6  mov     dword ptr [rsp+40h+var_20], edi
0x18003d0ea  lea     r9, aNpssdo; "NPSSDO"
0x18003d0f1  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003d0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0ff  mov     rcx, [rcx+10h]
0x18003d103  call    WPP_SF_sd
0x18003d108  nop
0x18003d109  lea     rcx, [rbp+arg_0]; this
0x18003d10d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d112  nop
0x18003d113  lea     rcx, [rbp+arg_18]; this
0x18003d117  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d11c  mov     eax, edi
0x18003d11e  jmp     short loc_18003D125
0x18003d120  mov     eax, 80004003h
0x18003d125  mov     rbx, [rsp+40h+arg_8]
0x18003d12a  mov     rsi, [rsp+40h+arg_10]
0x18003d12f  add     rsp, 40h
0x18003d133  pop     r14
0x18003d135  pop     rdi
0x18003d136  pop     rbp
0x18003d137  retn
```
