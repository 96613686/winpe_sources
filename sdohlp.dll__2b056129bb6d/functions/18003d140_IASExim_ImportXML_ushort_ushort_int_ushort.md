# IASExim::ImportXML(ushort *,ushort *,int,ushort * *)

- ea: `0x18003d140`
- end: `0x18003d7a5`
- name: `?ImportXML@IASExim@@AEAAJPEAG0HPEAPEAG@Z`
- size: `1637`
- prototype: `__int64 __usercall@<rax>(IASExim *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003bb3c`

## callees

- `0x180024cac`
- `0x18002cca4`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002efa0`
- `0x180038ff4`
- `0x180039628`
- `0x180039830`
- `0x180039924`
- `0x18003a164`
- `0x18003b8ac`
- `0x18003bc7c`
- `0x18003c96c`
- `0x18003d140`
- `0x18003d9b0`
- `0x18003f638`
- `0x180042a80`
- `0x180047298`
- `0x180047628`
- `0x1800477a4`
- `0x180047a60`
- `0x180054770`
- `0x1800548c0`
- `0x180054c80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003d3aa`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d3aa`
- `OLEAUT32!__imp_VariantInit` at `0x18003d17b`
- `OLEAUT32!__imp_VariantInit` at `0x18003d17b`
- `OLEAUT32!__imp_VariantClear` at `0x18003d768`
- `OLEAUT32!__imp_VariantClear` at `0x18003d768`

## string_xrefs

- `0x18003d33a`: `IDR_IAS_XML_RES.XML`
- `0x18003d32e`: `IDR_IASMIG_XML_RES_XML`
- `0x18003d278`: `ias_converted.xml`
- `0x18003d1e2`: `Cannot find IAS system directory`
- `0x18003d2e8`: `Failed to get unsupported parameters from XML file. Import failed.`
- `0x18003d37e`: `Failed to convert XML to current version. Import failed.`
- `0x18003d411`: `Open the updated ias.xml returned 0x%x. Import failed.`
- `0x18003d4d9`: `ImportRegistry failed with 0x%x`
- `0x18003d70f`: `m_pXmlHelper->Import failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IASExim::ImportXML(
        IASExim *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5)
{
  CUtils *v9; // rcx
  unsigned int v10; // ebx
  int UnsupportedPropertiesInXML; // edi
  __int64 v12; // rdx
  __int64 v13; // rdi
  unsigned __int16 **v14; // r14
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // r8
  const OLECHAR **v18; // rbx
  const unsigned __int16 *v19; // rdx
  const OLECHAR *v20; // rcx
  int v21; // edx
  unsigned __int16 *v22; // rdx
  unsigned __int16 *v23; // r8
  int v24; // eax
  char v25; // di
  unsigned __int16 *v26; // rdx
  unsigned __int16 *v27; // r8
  int v28; // eax
  char v29; // di
  const unsigned __int16 *v30; // rdx
  const unsigned __int16 *v31; // rcx
  const OLECHAR *v32; // r8
  const unsigned __int16 *v34; // [rsp+20h] [rbp-C1h]
  struct IXMLDOMNode *v35; // [rsp+30h] [rbp-B1h] BYREF
  const unsigned __int16 **v36; // [rsp+38h] [rbp-A9h] BYREF
  struct IXMLDOMElement *v37; // [rsp+40h] [rbp-A1h] BYREF
  struct IXMLDOMNode *v38; // [rsp+48h] [rbp-99h] BYREF
  __int64 v39; // [rsp+50h] [rbp-91h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-89h] BYREF
  struct tagVARIANT v41; // [rsp+70h] [rbp-71h] BYREF
  _BYTE v42[160]; // [rsp+90h] [rbp-51h] BYREF
  __int64 *v43; // [rsp+150h] [rbp+6Fh] BYREF

  v39 = 0;
  v38 = 0;
  v37 = 0;
  VariantInit(&pvarg);
  DataStoreClient::DataStoreClient((DataStoreClient *)v42);
  if ( a3 )
  {
    v36 = 0;
    v43 = 0;
    if ( (unsigned int)CUtils::GetIAS2Directory(v9, (struct _bstr_t *)&v43) )
    {
      UnsupportedPropertiesInXML = 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_96;
      }
      WppDbgPrint("Cannot find IAS system directory");
      v12 = 27;
    }
    else
    {
      _bstr_t::operator=(&v36, &v43);
      if ( v43 )
        v13 = *v43;
      else
        v13 = 0;
      v10 = 1;
      if ( *(_WORD *)(v13 + 2LL * (_bstr_t::length((_bstr_t *)&v43) - 1)) != 92 )
      {
        _bstr_t::_bstr_t((_bstr_t *)&v35, L"\\");
        _bstr_t::operator+=((struct _bstr_t *)&v36, (struct _bstr_t *)&v35);
        _bstr_t::_Free((_bstr_t *)&v35);
      }
      _bstr_t::_bstr_t((_bstr_t *)&v35, L"ias_converted.xml");
      _bstr_t::operator+=((struct _bstr_t *)&v36, (struct _bstr_t *)&v35);
      _bstr_t::_Free((_bstr_t *)&v35);
      v14 = a5;
      UnsupportedPropertiesInXML = CIASXMLConverter::FindUnsupportedPropertiesInXML(a3, v15, v16, a5);
      if ( UnsupportedPropertiesInXML >= 0 )
      {
        if ( *v14 )
        {
          _bstr_t::_Free((_bstr_t *)&v43);
          _bstr_t::_Free((_bstr_t *)&v36);
          goto LABEL_97;
        }
        v18 = v36;
        if ( v36 )
          v19 = *v36;
        else
          v19 = 0;
        UnsupportedPropertiesInXML = CIASXMLConverter::ConvertIasXMLToCurrentVersion(
                                       a3,
                                       v19,
                                       v17,
                                       L"IDR_IAS_XML_RES.XML",
                                       v34,
                                       L"IDR_IASMIG_XML_RES_XML");
        if ( UnsupportedPropertiesInXML >= 0 )
        {
          pvarg.vt = 8;
          if ( v18 )
            v20 = *v18;
          else
            v20 = 0;
          pvarg.llVal = (LONGLONG)SysAllocString(v20);
          v41 = pvarg;
          UnsupportedPropertiesInXML = GetDocumentRootElement(*((struct IXMLDOMDocument2 **)this + 1), &v41, &v37);
          if ( UnsupportedPropertiesInXML >= 0 )
          {
            if ( v18 )
              v22 = (unsigned __int16 *)*v18;
            else
              v22 = 0;
            UnsupportedPropertiesInXML = IASExim::CheckProductLimitsForXmlImport(this, v22);
            if ( UnsupportedPropertiesInXML >= 0 )
            {
              v35 = 0;
              if ( v18 )
                v23 = (unsigned __int16 *)*v18;
              else
                v23 = 0;
              v24 = IASExim::ImportRegistry((struct IXMLDOMDocument2 **)this, a2, v23, &v35);
              v25 = v24;
              if ( v24 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WppDbgPrint("ImportRegistry failed with 0x%x");
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
                  (unsigned int)"NPSSDO",
                  v25);
              }
              if ( !v35 && !a4 )
              {
                UnsupportedPropertiesInXML = -2147024809;
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
                goto LABEL_96;
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              UnsupportedPropertiesInXML = DataStoreClient::Initialize((DataStoreClient *)v42, a2);
              if ( UnsupportedPropertiesInXML >= 0 )
              {
                UnsupportedPropertiesInXML = DataStoreClient::GetSystemInfo(
                                               (DataStoreClient *)v42,
                                               (unsigned __int16 *)this + 8);
                if ( UnsupportedPropertiesInXML >= 0 )
                {
                  DataStoreClient::Shutdown((DataStoreClient *)v42);
                  if ( v18 )
                    v27 = (unsigned __int16 *)*v18;
                  else
                    v27 = 0;
                  v28 = IASExim::ImportSystemInfo(this, v26, v27, &v38);
                  v29 = v28;
                  if ( v28 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                    {
                      WppDbgPrint("ImportSystemInfo failed with 0x%x, ignored");
                      WPP_SF_sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        35,
                        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
                        (unsigned int)"NPSSDO",
                        v29);
                    }
                    TraceXMLFailure(*((struct IXMLDOMDocument2 **)this + 1));
                  }
                  if ( *((_DWORD *)this + 5)
                    && (!v18 ? (v30 = 0) : (v30 = *v18),
                        !v18 ? (v31 = 0) : (v31 = *v18),
                        UnsupportedPropertiesInXML = CIASXMLConverter::ConvertEAPBlobs(v31, v30),
                        UnsupportedPropertiesInXML < 0) )
                  {
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                    {
                      goto LABEL_96;
                    }
                    WppDbgPrint("ConvertEAPBlobs failed with 0x%x");
                    v21 = 36;
                  }
                  else
                  {
                    if ( v18 )
                      v32 = *v18;
                    else
                      v32 = 0;
                    UnsupportedPropertiesInXML = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, const OLECHAR *))(**(_QWORD **)this + 32LL))(
                                                   *(_QWORD *)this,
                                                   a2,
                                                   v32);
                    if ( UnsupportedPropertiesInXML >= 0
                      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                    {
                      goto LABEL_96;
                    }
                    WppDbgPrint("m_pXmlHelper->Import failed with 0x%x");
                    v21 = 37;
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                  {
                    goto LABEL_96;
                  }
                  WppDbgPrint("dataStore.GetSystemInfo() failed with %!hresult!");
                  v21 = 34;
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                {
                  goto LABEL_96;
                }
                WppDbgPrint("dataStore.Initialize() failed with %!hresult!");
                v21 = 33;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
              {
                goto LABEL_96;
              }
              WppDbgPrint("Check for license limitations returned 0x%x. Import failed.");
              v21 = 31;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_96;
            }
            WppDbgPrint("Open the updated ias.xml returned 0x%x. Import failed.");
            v21 = 30;
          }
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            UnsupportedPropertiesInXML);
          goto LABEL_96;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_96;
        }
        WppDbgPrint("Failed to convert XML to current version. Import failed.");
        v12 = 29;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_96;
        }
        WppDbgPrint("Failed to get unsupported parameters from XML file. Import failed.");
        v12 = 28;
      }
    }
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
LABEL_96:
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v36);
    v10 = UnsupportedPropertiesInXML;
    goto LABEL_97;
  }
  v10 = -2147467261;
LABEL_97:
  DataStoreClient::~DataStoreClient((DataStoreClient *)v42);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  return v10;
}

```

## disassembly

```asm
0x18003d140  push    rbp
0x18003d142  push    rbx
0x18003d143  push    rsi
0x18003d144  push    rdi
0x18003d145  push    r12
0x18003d147  push    r13
0x18003d149  push    r14
0x18003d14b  push    r15
0x18003d14d  lea     rbp, [rsp-17h]
0x18003d152  sub     rsp, 0F8h
0x18003d159  mov     r12d, r9d
0x18003d15c  mov     rsi, r8
0x18003d15f  mov     r13, rdx
0x18003d162  mov     r15, rcx
0x18003d165  xor     ebx, ebx
0x18003d167  mov     [rsp+130h+var_E0], rbx
0x18003d16c  mov     [rsp+130h+var_E8], rbx
0x18003d171  mov     [rsp+130h+var_F0], rbx
0x18003d176  lea     rcx, [rsp+130h+pvarg]; pvarg
0x18003d17b  call    cs:__imp_VariantInit
0x18003d181  nop
0x18003d182  lea     rcx, [rbp+4Fh+var_A0]; this
0x18003d186  call    ??0DataStoreClient@@QEAA@XZ; DataStoreClient::DataStoreClient(void)
0x18003d18b  nop
0x18003d18c  test    rsi, rsi
0x18003d18f  jnz     short loc_18003D19B
0x18003d191  mov     ebx, 80004003h
0x18003d196  jmp     loc_18003D759
0x18003d19b  mov     [rsp+130h+var_F8], rbx
0x18003d1a0  mov     [rbp+4Fh+arg_10], rbx
0x18003d1a4  lea     rdx, [rbp+4Fh+arg_10]; struct _bstr_t *
0x18003d1a8  call    ?GetIAS2Directory@CUtils@@QEBAJAEAV_bstr_t@@@Z; CUtils::GetIAS2Directory(_bstr_t &)
0x18003d1ad  test    eax, eax
0x18003d1af  jz      short loc_18003D216
0x18003d1b1  mov     edi, ebx
0x18003d1b3  lea     r14, WPP_GLOBAL_Control
0x18003d1ba  mov     rax, cs:WPP_GLOBAL_Control
0x18003d1c1  cmp     rax, r14
0x18003d1c4  jz      loc_18003D743
0x18003d1ca  cmp     byte ptr [rax+19h], 2
0x18003d1ce  jb      loc_18003D743
0x18003d1d4  mov     esi, 400h
0x18003d1d9  test    [rax+1Ch], esi
0x18003d1dc  jz      loc_18003D743
0x18003d1e2  lea     rcx, aCannotFindIasS; "Cannot find IAS system directory"
0x18003d1e9  call    WppDbgPrint
0x18003d1ee  mov     edx, 1Bh
0x18003d1f3  lea     r9, aNpssdo; "NPSSDO"
0x18003d1fa  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003d201  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d208  mov     rcx, [rcx+10h]
0x18003d20c  call    WPP_SF_s
0x18003d211  jmp     loc_18003D743
0x18003d216  lea     rdx, [rbp+4Fh+arg_10]
0x18003d21a  lea     rcx, [rsp+130h+var_F8]
0x18003d21f  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18003d224  mov     rax, [rbp+4Fh+arg_10]
0x18003d228  test    rax, rax
0x18003d22b  jz      short loc_18003D232
0x18003d22d  mov     rdi, [rax]
0x18003d230  jmp     short loc_18003D235
0x18003d232  mov     rdi, rbx
0x18003d235  lea     rcx, [rbp+4Fh+arg_10]; this
0x18003d239  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003d23e  mov     ebx, 1
0x18003d243  sub     eax, ebx
0x18003d245  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x18003d24a  jz      short loc_18003D278
0x18003d24c  lea     rdx, asc_180064534; "\\"
0x18003d253  lea     rcx, [rsp+130h+var_100]; this
0x18003d258  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003d25d  nop
0x18003d25e  lea     rdx, [rsp+130h+var_100]; struct _bstr_t *
0x18003d263  lea     rcx, [rsp+130h+var_F8]; struct _bstr_t *
0x18003d268  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18003d26d  nop
0x18003d26e  lea     rcx, [rsp+130h+var_100]; this
0x18003d273  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d278  lea     rdx, aIasConvertedXm; "ias_converted.xml"
0x18003d27f  lea     rcx, [rsp+130h+var_100]; this
0x18003d284  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003d289  nop
0x18003d28a  lea     rdx, [rsp+130h+var_100]; struct _bstr_t *
0x18003d28f  lea     rcx, [rsp+130h+var_F8]; struct _bstr_t *
0x18003d294  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18003d299  nop
0x18003d29a  lea     rcx, [rsp+130h+var_100]; this
0x18003d29f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d2a4  mov     r14, [rbp+4Fh+arg_20]
0x18003d2a8  mov     r9, r14; unsigned __int16 **
0x18003d2ab  mov     rcx, rsi; unsigned __int16 *
0x18003d2ae  call    ?FindUnsupportedPropertiesInXML@CIASXMLConverter@@SAJPEBG00PEAPEAG@Z; CIASXMLConverter::FindUnsupportedPropertiesInXML(ushort const *,ushort const *,ushort const *,ushort * *)
0x18003d2b3  mov     edi, eax
0x18003d2b5  test    eax, eax
0x18003d2b7  jns     short loc_18003D2FE
0x18003d2b9  lea     r14, WPP_GLOBAL_Control
0x18003d2c0  mov     rax, cs:WPP_GLOBAL_Control
0x18003d2c7  cmp     rax, r14
0x18003d2ca  jz      loc_18003D743
0x18003d2d0  cmp     byte ptr [rax+19h], 2
0x18003d2d4  jb      loc_18003D743
0x18003d2da  mov     esi, 400h
0x18003d2df  test    [rax+1Ch], esi
0x18003d2e2  jz      loc_18003D743
0x18003d2e8  lea     rcx, aFailedToGetUns; "Failed to get unsupported parameters fr"...
0x18003d2ef  call    WppDbgPrint
0x18003d2f4  mov     edx, 1Ch
0x18003d2f9  jmp     loc_18003D1F3
0x18003d2fe  cmp     qword ptr [r14], 0
0x18003d302  jz      short loc_18003D31D
0x18003d304  lea     rcx, [rbp+4Fh+arg_10]; this
0x18003d308  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d30d  nop
0x18003d30e  lea     rcx, [rsp+130h+var_F8]; this
0x18003d313  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d318  jmp     loc_18003D759
0x18003d31d  mov     rbx, [rsp+130h+var_F8]
0x18003d322  test    rbx, rbx
0x18003d325  jz      short loc_18003D32C
0x18003d327  mov     rdx, [rbx]
0x18003d32a  jmp     short loc_18003D32E
0x18003d32c  xor     edx, edx; unsigned __int16 *
0x18003d32e  lea     rax, aIdrIasmigXmlRe; "IDR_IASMIG_XML_RES_XML"
0x18003d335  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18003d33a  lea     r9, aIdrIasXmlResXm; "IDR_IAS_XML_RES.XML"
0x18003d341  mov     rcx, rsi; unsigned __int16 *
0x18003d344  call    ?ConvertIasXMLToCurrentVersion@CIASXMLConverter@@SAJPEBG00000@Z; CIASXMLConverter::ConvertIasXMLToCurrentVersion(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003d349  mov     edi, eax
0x18003d34b  test    eax, eax
0x18003d34d  jns     short loc_18003D394
0x18003d34f  lea     r14, WPP_GLOBAL_Control
0x18003d356  mov     rax, cs:WPP_GLOBAL_Control
0x18003d35d  cmp     rax, r14
0x18003d360  jz      loc_18003D743
0x18003d366  cmp     byte ptr [rax+19h], 2
0x18003d36a  jb      loc_18003D743
0x18003d370  mov     esi, 400h
0x18003d375  test    [rax+1Ch], esi
0x18003d378  jz      loc_18003D743
0x18003d37e  lea     rcx, aFailedToConver; "Failed to convert XML to current versio"...
0x18003d385  call    WppDbgPrint
0x18003d38a  mov     edx, 1Dh
0x18003d38f  jmp     loc_18003D1F3
0x18003d394  mov     eax, 8
0x18003d399  mov     word ptr [rsp+130h+pvarg], ax
0x18003d39e  test    rbx, rbx
0x18003d3a1  jz      short loc_18003D3A8
0x18003d3a3  mov     rcx, [rbx]
0x18003d3a6  jmp     short loc_18003D3AA
0x18003d3a8  xor     ecx, ecx; psz
0x18003d3aa  call    cs:__imp_SysAllocString
0x18003d3b0  mov     qword ptr [rsp+130h+pvarg+8], rax
0x18003d3b5  movups  xmm0, xmmword ptr [rsp+130h+pvarg]
0x18003d3ba  movaps  xmmword ptr [rbp+4Fh+var_C0], xmm0
0x18003d3be  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18003d3c3  movsd   qword ptr [rbp+4Fh+var_C0+10h], xmm1
0x18003d3c8  lea     r8, [rsp+130h+var_F0]; struct IXMLDOMElement **
0x18003d3cd  lea     rdx, [rbp+4Fh+var_C0]; struct tagVARIANT
0x18003d3d1  mov     rcx, [r15+8]; struct IXMLDOMDocument2 *
0x18003d3d5  call    ?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)
0x18003d3da  mov     edi, eax
0x18003d3dc  test    eax, eax
0x18003d3de  jns     short loc_18003D427
0x18003d3e0  lea     r14, WPP_GLOBAL_Control
0x18003d3e7  mov     rax, cs:WPP_GLOBAL_Control
0x18003d3ee  cmp     rax, r14
0x18003d3f1  jz      loc_18003D743
0x18003d3f7  cmp     byte ptr [rax+19h], 2
0x18003d3fb  jb      loc_18003D743
0x18003d401  mov     esi, 400h
0x18003d406  test    [rax+1Ch], esi
0x18003d409  jz      loc_18003D743
0x18003d40f  mov     edx, edi
0x18003d411  lea     rcx, aOpenTheUpdated; "Open the updated ias.xml returned 0x%x."...
0x18003d418  call    WppDbgPrint
0x18003d41d  mov     edx, 1Eh
0x18003d422  jmp     loc_18003D720
0x18003d427  test    rbx, rbx
0x18003d42a  jz      short loc_18003D431
0x18003d42c  mov     rdx, [rbx]
0x18003d42f  jmp     short loc_18003D433
0x18003d431  xor     edx, edx; unsigned __int16 *
0x18003d433  mov     rcx, r15; this
0x18003d436  call    ?CheckProductLimitsForXmlImport@IASExim@@AEAAJPEAG@Z; IASExim::CheckProductLimitsForXmlImport(ushort *)
0x18003d43b  mov     edi, eax
0x18003d43d  test    eax, eax
0x18003d43f  jns     short loc_18003D488
0x18003d441  lea     r14, WPP_GLOBAL_Control
0x18003d448  mov     rax, cs:WPP_GLOBAL_Control
0x18003d44f  cmp     rax, r14
0x18003d452  jz      loc_18003D743
0x18003d458  cmp     byte ptr [rax+19h], 2
0x18003d45c  jb      loc_18003D743
0x18003d462  mov     esi, 400h
0x18003d467  test    [rax+1Ch], esi
0x18003d46a  jz      loc_18003D743
0x18003d470  mov     edx, edi
0x18003d472  lea     rcx, aCheckForLicens; "Check for license limitations returned "...
0x18003d479  call    WppDbgPrint
0x18003d47e  mov     edx, 1Fh
0x18003d483  jmp     loc_18003D720
0x18003d488  mov     [rsp+130h+var_100], 0
0x18003d491  test    rbx, rbx
0x18003d494  jz      short loc_18003D49B
0x18003d496  mov     r8, [rbx]
0x18003d499  jmp     short loc_18003D49E
0x18003d49b  xor     r8d, r8d; unsigned __int16 *
0x18003d49e  lea     r9, [rsp+130h+var_100]; struct IXMLDOMNode **
0x18003d4a3  mov     rdx, r13; unsigned __int16 *
0x18003d4a6  mov     rcx, r15; this
0x18003d4a9  call    ?ImportRegistry@IASExim@@AEAAJPEAG0PEAPEAUIXMLDOMNode@@@Z; IASExim::ImportRegistry(ushort *,ushort *,IXMLDOMNode * *)
0x18003d4ae  mov     edi, eax
0x18003d4b0  mov     esi, 400h
0x18003d4b5  lea     r14, WPP_GLOBAL_Control
0x18003d4bc  test    eax, eax
0x18003d4be  jns     short loc_18003D50C
0x18003d4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4c7  cmp     rcx, r14
0x18003d4ca  jz      short loc_18003D50C
0x18003d4cc  cmp     byte ptr [rcx+19h], 2
0x18003d4d0  jb      short loc_18003D50C
0x18003d4d2  test    [rcx+1Ch], esi
0x18003d4d5  jz      short loc_18003D50C
0x18003d4d7  mov     edx, eax
0x18003d4d9  lea     rcx, aImportregistry; "ImportRegistry failed with 0x%x"
0x18003d4e0  call    WppDbgPrint
0x18003d4e5  mov     edx, 20h ; ' '
0x18003d4ea  mov     dword ptr [rsp+130h+var_110], edi
0x18003d4ee  lea     r9, aNpssdo; "NPSSDO"
0x18003d4f5  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003d4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d503  mov     rcx, [rcx+10h]
0x18003d507  call    WPP_SF_sd
0x18003d50c  cmp     [rsp+130h+var_100], 0
0x18003d512  jnz     short loc_18003D52D
0x18003d514  test    r12d, r12d
0x18003d517  jnz     short loc_18003D52D
0x18003d519  mov     edi, 80070057h
0x18003d51e  lea     rcx, [rsp+130h+var_100]
0x18003d523  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d528  jmp     loc_18003D743
0x18003d52d  lea     rcx, [rsp+130h+var_100]
0x18003d532  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d537  mov     rdx, r13; unsigned __int16 *
0x18003d53a  lea     rcx, [rbp+4Fh+var_A0]; this
0x18003d53e  call    ?Initialize@DataStoreClient@@UEAAJPEBG@Z; DataStoreClient::Initialize(ushort const *)
0x18003d543  mov     edi, eax
0x18003d545  test    eax, eax
0x18003d547  jns     short loc_18003D5A6
0x18003d549  mov     rax, cs:WPP_GLOBAL_Control
0x18003d550  cmp     rax, r14
0x18003d553  jz      loc_18003D743
0x18003d559  cmp     byte ptr [rax+19h], 2
0x18003d55d  jb      loc_18003D743
0x18003d563  test    [rax+1Ch], esi
0x18003d566  jz      loc_18003D743
0x18003d56c  mov     edx, edi
0x18003d56e  lea     rcx, aDatastoreIniti_0; "dataStore.Initialize() failed with %!hr"...
0x18003d575  call    WppDbgPrint
0x18003d57a  mov     edx, 21h ; '!'
0x18003d57f  mov     dword ptr [rsp+130h+var_110], edi
0x18003d583  lea     r9, aNpssdo; "NPSSDO"
0x18003d58a  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003d591  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d598  mov     rcx, [rcx+10h]
0x18003d59c  call    WPP_SF_sd
0x18003d5a1  jmp     loc_18003D743
0x18003d5a6  lea     rdx, [r15+10h]; unsigned __int16 *
0x18003d5aa  lea     rcx, [rbp+4Fh+var_A0]; this
0x18003d5ae  call    ?GetSystemInfo@DataStoreClient@@UEBAJPEAG@Z; DataStoreClient::GetSystemInfo(ushort *)
0x18003d5b3  mov     edi, eax
0x18003d5b5  test    eax, eax
0x18003d5b7  jns     short loc_18003D5F1
0x18003d5b9  mov     rax, cs:WPP_GLOBAL_Control
0x18003d5c0  cmp     rax, r14
0x18003d5c3  jz      loc_18003D743
0x18003d5c9  cmp     byte ptr [rax+19h], 2
0x18003d5cd  jb      loc_18003D743
0x18003d5d3  test    [rax+1Ch], esi
0x18003d5d6  jz      loc_18003D743
0x18003d5dc  mov     edx, edi
0x18003d5de  lea     rcx, aDatastoreGetsy_0; "dataStore.GetSystemInfo() failed with %"...
0x18003d5e5  call    WppDbgPrint
0x18003d5ea  mov     edx, 22h ; '"'
0x18003d5ef  jmp     short loc_18003D57F
0x18003d5f1  lea     rcx, [rbp+4Fh+var_A0]; this
0x18003d5f5  call    ?Shutdown@DataStoreClient@@UEAAXXZ; DataStoreClient::Shutdown(void)
0x18003d5fa  test    rbx, rbx
0x18003d5fd  jz      short loc_18003D604
0x18003d5ff  mov     r8, [rbx]
0x18003d602  jmp     short loc_18003D607
0x18003d604  xor     r8d, r8d; unsigned __int16 *
0x18003d607  lea     r9, [rsp+130h+var_E8]; struct IXMLDOMNode **
0x18003d60c  mov     rcx, r15; this
0x18003d60f  call    ?ImportSystemInfo@IASExim@@AEAAJPEAG0PEAPEAUIXMLDOMNode@@@Z; IASExim::ImportSystemInfo(ushort *,ushort *,IXMLDOMNode * *)
0x18003d614  mov     edi, eax
0x18003d616  test    eax, eax
0x18003d618  jns     short loc_18003D66F
0x18003d61a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d621  cmp     rcx, r14
  ... truncated ...
```
