# ?ProcessValue@?QITaskXmlHandler@@BuilderXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z

- ea: `0x18001a1c0`
- end: `0x18001c270`
- name: `?ProcessValue@?QITaskXmlHandler@@BuilderXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z`
- size: `8368`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180008d30`
- `0x18001a1c0`
- `0x18001c280`
- `0x18001c440`
- `0x18001c4b0`
- `0x18001c800`
- `0x18001c8b0`
- `0x18001c954`
- `0x180039524`
- `0x180041510`
- `0x180041770`
- `0x18004305c`
- `0x1800430c8`
- `0x180043154`
- `0x1800431d8`
- `0x18004325c`
- `0x1800432dc`
- `0x18004ca50`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x18001a391`
- `msvcrt!free` at `0x18001a590`
- `msvcrt!free` at `0x18001a391`
- `msvcrt!free` at `0x18001a590`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a75f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a8fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a75f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a8fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a378`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a57a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a74d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a378`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a57a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a74d`
- `OLEAUT32!__imp_VariantClear` at `0x18001a8e7`
- `OLEAUT32!__imp_VariantClear` at `0x18001a950`
- `OLEAUT32!__imp_VariantClear` at `0x18001a8e7`
- `OLEAUT32!__imp_VariantClear` at `0x18001a950`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall _ProcessValue__QITaskXmlHandler__BuilderXmlHandler__MEAAJAEBUSchema__W4TaskXmlNodeId__AEBUData_1__N_Z(
        __int64 a1,
        int *a2,
        int a3,
        __int64 a4,
        char a5)
{
  __int64 result; // rax
  __int64 v9; // rdx
  int v10; // edi
  WCHAR *v11; // rdx
  int v12; // eax
  __int64 *v13; // rbx
  __int64 v14; // rdi
  __int64 *v15; // rax
  __int64 v16; // rdx
  BSTR *v17; // rbx
  BSTR v18; // rcx
  int v19; // eax
  __int64 *v20; // rbx
  __int64 v21; // rdi
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 *v26; // rbx
  __int64 v27; // rdi
  __int64 *v28; // rax
  __int64 v29; // rdx
  void *v30; // rbx
  __int64 v31; // rdi
  _QWORD *v32; // rax
  __int64 v33; // rdx
  void *v34; // rbx
  __int64 v35; // rdi
  _QWORD *v36; // rax
  __int64 v37; // rdx
  const OLECHAR *NullTerminated; // rbx
  __int64 v39; // rsi
  OLECHAR *v40; // rcx
  BSTR v41; // rax
  _bstr_t::Data_t *v42; // rbx
  __int64 v43; // rdi
  __int64 *v44; // rax
  __int64 v45; // rdx
  _bstr_t::Data_t *v46; // rbx
  __int64 v47; // rdi
  __int64 *v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rdi
  __int64 v51; // rsi
  const OLECHAR **v52; // rax
  const OLECHAR *v53; // rbx
  PrincipalImpl *v54; // rbx
  __int64 v55; // rcx
  __int64 *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 *v60; // rbx
  __int64 v61; // rdi
  __int64 *v62; // rax
  __int64 v63; // rdx
  RegistrationInfoImpl *v64; // rbx
  __int64 v65; // rcx
  unsigned __int16 **v66; // rax
  unsigned __int16 *v67; // rdx
  __int64 v68; // rdi
  __int64 *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rdi
  __int64 *v72; // rax
  __int64 v73; // rdx
  __int64 *v74; // rax
  __int64 *v75; // rbx
  __int64 v76; // rdi
  __int64 *v77; // rax
  __int64 v78; // rdx
  __int64 (__fastcall ***v79)(_QWORD, GUID *, void **); // rcx
  __int64 *v80; // rbx
  __int64 v81; // rdi
  __int64 *v82; // rax
  __int64 v83; // rdx
  RegistrationInfoImpl *v84; // rbx
  __int64 v85; // rcx
  unsigned __int16 **v86; // rax
  unsigned __int16 *v87; // rdx
  __int64 *v88; // rax
  void *v89; // rbx
  __int64 v90; // rdi
  __int64 *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rdi
  __int64 *v94; // rax
  __int64 v95; // rdx
  _bstr_t::Data_t *v96; // rbx
  __int64 v97; // rdi
  __int64 *v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rdx
  void *v101; // rbx
  __int64 v102; // rdi
  __int64 *v103; // rax
  __int64 v104; // rdx
  _bstr_t::Data_t *v105; // rbx
  __int64 v106; // rdi
  __int64 *v107; // rax
  __int64 v108; // rdx
  __int64 *v109; // rbx
  __int64 v110; // rdi
  __int64 *v111; // rax
  __int64 v112; // rdx
  void *v113; // rbx
  __int64 v114; // rdi
  __int64 *v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rdx
  __int64 v119; // rdx
  __int64 v120; // rdx
  __int64 v121; // rdx
  unsigned __int16 ***Copy; // rax
  unsigned __int16 *v123; // rdx
  __int64 v124; // rdi
  __int64 *v125; // rax
  __int64 v126; // rdx
  void *v127; // rbx
  __int64 v128; // rdi
  __int64 *v129; // rax
  __int64 v130; // rdx
  void *v131; // rbx
  __int64 v132; // rdi
  __int64 *v133; // rax
  __int64 v134; // rdx
  void *v135; // rbx
  __int64 v136; // rdi
  __int64 *v137; // rax
  __int64 v138; // rdx
  unsigned __int16 ***v139; // rax
  unsigned __int16 *v140; // rdx
  __int64 *v141; // rax
  _bstr_t::Data_t *v142; // rbx
  __int64 v143; // rdi
  __int64 *v144; // rax
  __int64 v145; // rdx
  __int64 **v146; // rax
  _bstr_t::Data_t *v147; // rbx
  __int64 v148; // rdi
  __int64 *v149; // rax
  __int64 v150; // rdx
  _bstr_t::Data_t *v151; // rbx
  __int64 v152; // rdi
  __int64 *v153; // rax
  __int64 v154; // rdx
  _bstr_t::Data_t *v155; // rbx
  __int64 v156; // rdi
  __int64 *v157; // rax
  __int64 v158; // rdx
  _bstr_t::Data_t *v159; // rbx
  __int64 v160; // rdi
  __int64 *v161; // rax
  __int64 v162; // rdx
  _bstr_t::Data_t *v163; // rbx
  __int64 v164; // rdi
  __int64 *v165; // rax
  __int64 v166; // rdx
  _bstr_t::Data_t *v167; // rbx
  __int64 v168; // rdi
  __int64 *v169; // rax
  __int64 v170; // rdx
  __int64 **v171; // rax
  _bstr_t::Data_t *v172; // rbx
  __int64 v173; // rdi
  __int64 *v174; // rax
  __int64 v175; // rdx
  __int64 *v176; // rax
  __int64 *v177; // rax
  __int64 **v178; // rax
  _bstr_t::Data_t *v179; // rbx
  __int64 v180; // rdi
  __int64 *v181; // rax
  __int64 v182; // rdx
  __int64 **v183; // rax
  _bstr_t::Data_t *v184; // rbx
  __int64 v185; // rdi
  __int64 *v186; // rax
  __int64 v187; // rdx
  PrincipalImpl *v188; // rbx
  unsigned __int16 **v189; // rax
  unsigned __int16 *v190; // rdx
  __int64 *v191; // rbx
  __int64 v192; // rdi
  __int64 *v193; // rax
  __int64 v194; // rdx
  RegistrationInfoImpl *v195; // rbx
  __int64 v196; // rcx
  __int64 v197; // rcx
  __int64 v198; // rdx
  __int64 v199; // rcx
  __int64 v200; // rcx
  __int64 v201; // rax
  __int64 v202; // rcx
  __int64 v203; // rcx
  __int64 v204; // rdx
  void *Block; // [rsp+38h] [rbp-80h] BYREF
  _bstr_t::Data_t *v206; // [rsp+40h] [rbp-78h] BYREF
  char v207[8]; // [rsp+48h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-68h] BYREF
  VARIANTARG v209; // [rsp+70h] [rbp-48h] BYREF

  result = ValidationXmlHandler::ProcessValue(a1, a2, a3, a4);
  v10 = result;
  if ( (int)result >= 0 )
  {
    switch ( a3 )
    {
      case 74:
        LOWORD(v9) = -(*(_BYTE *)(a4 + 32) != 0);
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 144LL))(
                *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                v9);
        break;
      case 2:
        v12 = *(_DWORD *)(a4 + 32);
        if ( v12 == 65538 )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                  *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                  2);
        }
        else
        {
          switch ( v12 )
          {
            case 65536:
              v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                      *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                      0);
              break;
            case 65537:
              v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                      *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                      1);
              break;
            case 65539:
              v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                      *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                      3);
              break;
            case 65540:
              v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                      *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                      4);
              break;
            case 65541:
              v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                      *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                      5);
              break;
            case 65542:
              v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 288LL))(
                      *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                      6);
              break;
            default:
              return (unsigned int)v10;
          }
        }
        break;
      case 75:
        LOWORD(v9) = -(*(_BYTE *)(a4 + 32) != 0);
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 128LL))(
                *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                v9);
        break;
      default:
        v11 = &_ImageBase;
        switch ( a3 )
        {
          case 4:
            v26 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v27 = *v26;
            v28 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v28 )
              v29 = *v28;
            else
              v29 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v27 + 160))(v26, v29);
            v17 = (BSTR *)Block;
            if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v17 )
            {
              if ( *v17 )
              {
                SysFreeString(*v17);
                *v17 = 0;
              }
              v18 = v17[1];
              if ( !v18 )
                goto LABEL_21;
              goto LABEL_48;
            }
            return (unsigned int)v10;
          case 5:
            v50 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v51 = *v50;
            v52 = *(const OLECHAR ***)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v52 )
              v53 = *v52;
            else
              v53 = 0;
            pvarg.vt = 0;
            VariantClear(&pvarg);
            pvarg.vt = 8;
            pvarg.llVal = (LONGLONG)SysAllocString(v53);
            if ( !pvarg.llVal && v53 )
            {
              pvarg.vt = 10;
              pvarg.lVal = -2147024882;
              ATL::PrivateAtlThrow(-2147024882);
            }
            v209 = pvarg;
            v10 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v51 + 176))(v50, &v209);
            VariantClear(&pvarg);
            goto LABEL_85;
          case 6:
            v84 = *(RegistrationInfoImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v85 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              v86 = *(unsigned __int16 ***)XmlParserTempString::GetCopy(v85, &Block);
              if ( v86 )
                v87 = *v86;
              else
                v87 = 0;
              RegistrationInfoImpl::put_LocSource(v84, v87);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            else
            {
              v93 = *(_QWORD *)v84;
              v94 = *(__int64 **)XmlParserTempString::GetCopy(v85, &Block);
              if ( v94 )
                v95 = *v94;
              else
                v95 = 0;
              v10 = (*(__int64 (__fastcall **)(RegistrationInfoImpl *, __int64))(v93 + 192))(v84, v95);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            return (unsigned int)v10;
          case 7:
            v80 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v81 = *v80;
            v82 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v82 )
              v83 = *v82;
            else
              v83 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v81 + 112))(v80, v83);
            _bstr_t::_Free((_bstr_t *)&Block);
            return (unsigned int)v10;
          case 8:
            v54 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v55 = *(_QWORD *)(a4 + 48);
            if ( !*(_DWORD *)(a1 + 572) )
            {
              v71 = *(_QWORD *)v54;
              v72 = *(__int64 **)XmlParserTempString::GetCopy(v55, &Block);
              if ( v72 )
                v73 = *v72;
              else
                v73 = 0;
              goto LABEL_304;
            }
            v56 = *(__int64 **)XmlParserTempString::GetCopy(v55, &Block);
            if ( v56 )
              v57 = *v56;
            else
              v57 = 0;
            ComHandlerActionImpl<IComHandlerAction,5>::put_ClassId(v54, v57);
LABEL_85:
            if ( Block )
              _bstr_t::Data_t::Release((_bstr_t::Data_t *)Block);
            return (unsigned int)v10;
          case 9:
            v60 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v61 = *v60;
            v62 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v62 )
              v63 = *v62;
            else
              v63 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v61 + 96))(v60, v63);
            goto LABEL_85;
          case 10:
            v64 = *(RegistrationInfoImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v65 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              v66 = *(unsigned __int16 ***)XmlParserTempString::GetCopy(v65, &Block);
              if ( v66 )
                v67 = *v66;
              else
                v67 = 0;
              RegistrationInfoImpl::put_LocDescription(v64, v67);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            else
            {
              v68 = *(_QWORD *)v64;
              v74 = *(__int64 **)XmlParserTempString::GetCopy(v65, &Block);
              if ( v74 )
                v70 = *v74;
              else
                v70 = 0;
LABEL_300:
              v10 = (*(__int64 (__fastcall **)(RegistrationInfoImpl *, __int64))(v68 + 64))(v64, v70);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            return (unsigned int)v10;
          case 11:
            v195 = *(RegistrationInfoImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v196 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              Copy = (unsigned __int16 ***)XmlParserTempString::GetCopy(v196, &Block);
              if ( *Copy )
                v123 = **Copy;
              else
                v123 = 0;
              RegistrationInfoImpl::put_LocDocumentation(v195, v123);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            else
            {
              v124 = *(_QWORD *)v195;
              v125 = *(__int64 **)XmlParserTempString::GetCopy(v196, &Block);
              if ( v125 )
                v126 = *v125;
              else
                v126 = 0;
              v10 = (*(__int64 (__fastcall **)(RegistrationInfoImpl *, __int64))(v124 + 128))(v195, v126);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            return (unsigned int)v10;
          case 19:
            if ( *(_DWORD *)(a1 + 568) )
            {
              LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
              return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512)
                                                                                            + 80LL)
                                                                              + 240LL))(
                                     *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                     v11);
            }
            return (unsigned int)v10;
          case 20:
            if ( *(_DWORD *)(a1 + 568) )
            {
              v75 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 80LL);
              v76 = *v75;
              v77 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
              if ( v77 )
                v78 = *v77;
              else
                v78 = 0;
              v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v76 + 224))(v75, v78);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            return (unsigned int)v10;
          case 72:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 64LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 73:
            v19 = *(_DWORD *)(a4 + 32);
            switch ( v19 )
            {
              case 0x1000:
                v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 112LL))(
                        *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                        1);
                break;
              case 0x400:
                v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 112LL))(
                        *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                        0);
                break;
              case 0x800:
                v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 112LL))(
                        *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                        3);
                break;
              case 0x2000:
                v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 112LL))(
                        *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                        2);
                break;
            }
            return (unsigned int)v10;
          case 76:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 160LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 77:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 176LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 78:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 208LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 79:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 352LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 81:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 304LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 82:
            v109 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 80LL);
            v110 = *v109;
            v111 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v111 )
              v112 = *v111;
            else
              v112 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v110 + 256))(v109, v112);
            _bstr_t::_Free((_bstr_t *)&Block);
            return (unsigned int)v10;
          case 83:
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                           + 272LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   *(unsigned __int16 *)(a4 + 32));
          case 84:
            LOWORD(v11) = -(*(_BYTE *)(a4 + 32) != 0);
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                            + 336LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                   v11);
          case 86:
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &Block);
            if ( v10 >= 0 )
            {
              v34 = Block;
              v35 = *(_QWORD *)Block;
              v36 = *(_QWORD **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              v37 = v36 ? *v36 : 0LL;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v35 + 64))(v34, v37);
              if ( v206 )
                _bstr_t::Data_t::Release(v206);
            }
            v25 = Block;
            goto LABEL_37;
          case 87:
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &Block);
            if ( v10 >= 0 )
            {
              v30 = Block;
              v31 = *(_QWORD *)Block;
              v32 = *(_QWORD **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              v33 = v32 ? *v32 : 0LL;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v31 + 80))(v30, v33);
              if ( v206 )
                _bstr_t::Data_t::Release(v206);
            }
            v25 = Block;
            goto LABEL_37;
          case 88:
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &Block);
            if ( v10 >= 0 )
            {
              LOWORD(v24) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 96LL))(Block, v24);
            }
            v25 = Block;
            goto LABEL_37;
          case 89:
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &Block);
            if ( v10 >= 0 )
            {
              LOWORD(v59) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 112LL))(Block, v59);
            }
            v25 = Block;
            goto LABEL_37;
          case 91:
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 360LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &Block);
            if ( v10 >= 0 )
            {
              v127 = Block;
              v128 = *(_QWORD *)Block;
              v129 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v129 )
                v130 = *v129;
              else
                v130 = 0;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v128 + 64))(v127, v130);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            goto LABEL_372;
          case 92:
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL) + 360LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &Block);
            if ( v10 >= 0 )
            {
              v131 = Block;
              v132 = *(_QWORD *)Block;
              v133 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v133 )
                v134 = *v133;
              else
                v134 = 0;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v132 + 80))(v131, v134);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            goto LABEL_372;
          case 94:
            if ( !*(_DWORD *)(a1 + 568) )
              return (unsigned int)v10;
            v54 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 80LL);
            v71 = *(_QWORD *)v54;
            v88 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v88 )
              v73 = *v88;
            else
              v73 = 0;
            goto LABEL_304;
          case 95:
            if ( *(_DWORD *)(a1 + 568) )
              return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                             + 96LL))(
                                     *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                                     *(unsigned __int16 *)(a4 + 32));
            return (unsigned int)v10;
          case 96:
            if ( *(_DWORD *)(a1 + 520) != 107 )
            {
              NullTerminated = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
              v39 = *(_QWORD *)(a1 + 512);
              v40 = *(OLECHAR **)(v39 + 120);
              if ( NullTerminated != v40 )
              {
                SysFreeString(v40);
                if ( NullTerminated )
                {
                  v41 = SysAllocString(NullTerminated);
                  *(_QWORD *)(v39 + 120) = v41;
                  if ( !v41 )
                    ATL::PrivateAtlThrow(-2147024882);
                }
                else
                {
                  *(_QWORD *)(v39 + 120) = 0;
                }
              }
              return (unsigned int)v10;
            }
            Block = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_6d2fd252_75c5_4f66_90ba_2a7d8cc3039f,
                    &Block);
            if ( v10 >= 0 )
            {
              v101 = Block;
              v102 = *(_QWORD *)Block;
              v103 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v103 )
                v104 = *v103;
              else
                v104 = 0;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v102 + 104))(v101, v104);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            v25 = Block;
            goto LABEL_37;
          case 99:
            v20 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 104LL);
            v21 = *v20;
            v22 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v22 )
              v23 = *v22;
            else
              v23 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v21 + 64))(v20, v23);
            v17 = (BSTR *)Block;
            if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 )
              goto LABEL_17;
            return (unsigned int)v10;
          case 104:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v42 = v206;
            v43 = *(_QWORD *)v206;
            v44 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v44 )
              v45 = *v44;
            else
              v45 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v43 + 88))(v42, v45);
            if ( Block )
              _bstr_t::Data_t::Release((_bstr_t::Data_t *)Block);
            goto LABEL_74;
          case 105:
            if ( *(_DWORD *)(a1 + 520) != 103 )
              return (unsigned int)v10;
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
                    &v206);
            if ( v10 < 0 )
            {
              v25 = v206;
            }
            else
            {
              v46 = v206;
              v47 = *(_QWORD *)v206;
              v48 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
              if ( v48 )
                v49 = *v48;
              else
                v49 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v47 + 104))(v46, v49);
              _bstr_t::_Free((_bstr_t *)&Block);
              v25 = v206;
            }
            goto LABEL_37;
          case 106:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
                    &v206);
            if ( v10 >= 0 )
            {
              v105 = v206;
              v106 = *(_QWORD *)v206;
              v107 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
              if ( v107 )
                v108 = *v107;
              else
                v108 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v106 + 120))(v105, v108);
              _bstr_t::_Free((_bstr_t *)&Block);
              v25 = v206;
            }
            else
            {
              v25 = v206;
            }
            goto LABEL_37;
          case 108:
            if ( *(_DWORD *)(a1 + 520) != 107
              || (v79 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 + 528)) == 0 )
            {
              return (unsigned int)-2147024809;
            }
            Block = 0;
            v10 = (**v79)(v79, &GUID_6d2fd252_75c5_4f66_90ba_2a7d8cc3039f, &Block);
            if ( v10 >= 0 )
            {
              v89 = Block;
              v90 = *(_QWORD *)Block;
              v91 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v91 )
                v92 = *v91;
              else
                v92 = 0;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v90 + 88))(v89, v92);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            v25 = Block;
            goto LABEL_37;
          case 109:
            if ( *(_DWORD *)(a1 + 520) != 103
              && *(_DWORD *)(a1 + 520) != 107
              && *(_DWORD *)(a1 + 520) != 113
              && *(_DWORD *)(a1 + 520) != 128 )
            {
              return (unsigned int)v10;
            }
            v64 = *(RegistrationInfoImpl **)(a1 + 528);
            v68 = *(_QWORD *)v64;
            v69 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v69 )
              v70 = *v69;
            else
              v70 = 0;
            goto LABEL_300;
          case 110:
            v13 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 96LL);
            v14 = *v13;
            v15 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v15 )
              v16 = *v15;
            else
              v16 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v14 + 128))(v13, v16);
            v17 = (BSTR *)Block;
            if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 )
            {
LABEL_17:
              if ( v17 )
              {
                if ( *v17 )
                {
                  SysFreeString(*v17);
                  *v17 = 0;
                }
                v18 = v17[1];
                if ( v18 )
                {
LABEL_48:
                  free(v18);
                  v17[1] = 0;
                }
LABEL_21:
                free(v17);
              }
            }
            return (unsigned int)v10;
          case 112:
            v54 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 104LL);
            v197 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              v139 = (unsigned __int16 ***)XmlParserTempString::GetCopy(v197, &Block);
              if ( *v139 )
                v140 = **v139;
              else
                v140 = 0;
              PrincipalImpl::put_LocDisplayName(v54, v140);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            else
            {
              v71 = *(_QWORD *)v54;
              v141 = *(__int64 **)XmlParserTempString::GetCopy(v197, &Block);
              if ( v141 )
                v73 = *v141;
              else
                v73 = 0;
LABEL_304:
              v10 = (*(__int64 (__fastcall **)(PrincipalImpl *, __int64))(v71 + 80))(v54, v73);
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            return (unsigned int)v10;
          case 114:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v142 = v206;
            v143 = *(_QWORD *)v206;
            v144 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v144 )
              v145 = *v144;
            else
              v145 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v143 + 88))(v142, v145);
            _bstr_t::_Free((_bstr_t *)&Block);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 115:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 >= 0 )
            {
              v199 = *(_QWORD *)(a4 + 48);
              if ( *(_DWORD *)(a1 + 572) )
              {
                v146 = (__int64 **)XmlParserTempString::GetCopy(v199, &Block);
                if ( *v146 )
                  v118 = **v146;
                else
                  v118 = 0;
                EmailActionImpl<IEmailAction,6>::put_LocSubject(v206, v118);
              }
              else
              {
                v147 = v206;
                v148 = *(_QWORD *)v206;
                v149 = *(__int64 **)XmlParserTempString::GetCopy(v199, &Block);
                if ( v149 )
                  v150 = *v149;
                else
                  v150 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v148 + 104))(v147, v150);
              }
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            goto LABEL_369;
          case 116:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v151 = v206;
            v152 = *(_QWORD *)v206;
            v153 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v153 )
              v154 = *v153;
            else
              v154 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v152 + 120))(v151, v154);
            _bstr_t::_Free((_bstr_t *)&Block);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 117:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v155 = v206;
            v156 = *(_QWORD *)v206;
            v157 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v157 )
              v158 = *v157;
            else
              v158 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v156 + 136))(v155, v158);
            _bstr_t::_Free((_bstr_t *)&Block);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 118:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v159 = v206;
            v160 = *(_QWORD *)v206;
            v161 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v161 )
              v162 = *v161;
            else
              v162 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v160 + 152))(v159, v162);
            _bstr_t::_Free((_bstr_t *)&Block);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 119:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v163 = v206;
            v164 = *(_QWORD *)v206;
            v165 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v165 )
              v166 = *v165;
            else
              v166 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v164 + 168))(v163, v166);
            _bstr_t::_Free((_bstr_t *)&Block);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 120:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_356;
            v167 = v206;
            v168 = *(_QWORD *)v206;
            v169 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v169 )
              v170 = *v169;
            else
              v170 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v168 + 184))(v167, v170);
            _bstr_t::_Free((_bstr_t *)&Block);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 121:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 >= 0 )
            {
              v200 = *(_QWORD *)(a4 + 48);
              if ( *(_DWORD *)(a1 + 572) )
              {
                v171 = (__int64 **)XmlParserTempString::GetCopy(v200, &Block);
                if ( *v171 )
                  v119 = **v171;
                else
                  v119 = 0;
                EmailActionImpl<IEmailAction,6>::put_LocBody(v206, v119);
              }
              else
              {
                v172 = v206;
                v173 = *(_QWORD *)v206;
                v174 = *(__int64 **)XmlParserTempString::GetCopy(v200, &Block);
                if ( v174 )
                  v175 = *v174;
                else
                  v175 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v173 + 216))(v172, v175);
              }
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            goto LABEL_369;
          case 123:
            v201 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            std::list<_bstr_t>::push_back(a1 + 552, v201);
            _bstr_t::_Free((_bstr_t *)&Block);
            return (unsigned int)v10;
          case 126:
            v64 = *(RegistrationInfoImpl **)(a1 + 544);
            v68 = *(_QWORD *)v64;
            v176 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v176 )
              v70 = *v176;
            else
              v70 = 0;
            goto LABEL_300;
          case 127:
            v54 = *(PrincipalImpl **)(a1 + 544);
            v71 = *(_QWORD *)v54;
            v177 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &Block);
            if ( v177 )
              v73 = *v177;
            else
              v73 = 0;
            goto LABEL_304;
          case 129:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_505e9e68_af89_46b8_a30f_56162a83d537,
                    &v206);
            if ( v10 >= 0 )
            {
              v202 = *(_QWORD *)(a4 + 48);
              if ( *(_DWORD *)(a1 + 572) )
              {
                v178 = (__int64 **)XmlParserTempString::GetCopy(v202, &Block);
                if ( *v178 )
                  v120 = **v178;
                else
                  v120 = 0;
                ShowMessageActionImpl<IShowMessageAction,7>::put_LocTitle(v206, v120);
              }
              else
              {
                v179 = v206;
                v180 = *(_QWORD *)v206;
                v181 = *(__int64 **)XmlParserTempString::GetCopy(v202, &Block);
                if ( v181 )
                  v182 = *v181;
                else
                  v182 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v180 + 88))(v179, v182);
              }
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            goto LABEL_369;
          case 130:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_505e9e68_af89_46b8_a30f_56162a83d537,
                    &v206);
            if ( v10 >= 0 )
            {
              v203 = *(_QWORD *)(a4 + 48);
              if ( *(_DWORD *)(a1 + 572) )
              {
                v183 = (__int64 **)XmlParserTempString::GetCopy(v203, &Block);
                if ( *v183 )
                  v121 = **v183;
                else
                  v121 = 0;
                EmailActionImpl<IEmailAction,6>::put_To(v206, v121);
              }
              else
              {
                v184 = v206;
                v185 = *(_QWORD *)v206;
                v186 = *(__int64 **)XmlParserTempString::GetCopy(v203, &Block);
                if ( v186 )
                  v187 = *v186;
                else
                  v187 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v185 + 104))(v184, v187);
              }
              _bstr_t::_Free((_bstr_t *)&Block);
            }
            goto LABEL_369;
          case 131:
            Block = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_2c05c3f0_6eed_4c05_a15f_ed7d7a98a369,
                    &Block);
            if ( v10 >= 0 )
            {
              LOWORD(v58) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 80LL))(Block, v58);
            }
            v25 = Block;
            goto LABEL_37;
          case 132:
            Block = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_2c05c3f0_6eed_4c05_a15f_ed7d7a98a369,
                    &Block);
            if ( v10 >= 0 )
            {
              LOWORD(v100) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 64LL))(Block, v100);
            }
            v25 = Block;
            goto LABEL_37;
          case 135:
            Block = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(*(_QWORD *)(a1 + 512) + 104LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 104LL),
                    &GUID_248919ae_e345_4a6d_8aeb_e0d3165c904e,
                    &Block);
            if ( v10 >= 0 )
            {
              v135 = Block;
              v136 = *(_QWORD *)Block;
              v137 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v137 )
                v138 = *v137;
              else
                v138 = 0;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v136 + 88))(v135, v138);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            goto LABEL_372;
          case 137:
            Block = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &Block);
            if ( v10 < 0 )
              goto LABEL_172;
            v206 = 0;
            v10 = (*(__int64 (__fastcall **)(void *, _bstr_t::Data_t **))(*(_QWORD *)Block + 408LL))(Block, &v206);
            if ( v10 < 0 )
            {
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Block);
              return (unsigned int)v10;
            }
            v96 = v206;
            v97 = *(_QWORD *)v206;
            v98 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v207);
            if ( v98 )
              v99 = *v98;
            else
              v99 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v97 + 56))(v96, v99);
            _bstr_t::_Free((_bstr_t *)v207);
            if ( v206 )
              (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v206 + 16LL))(v206);
LABEL_172:
            v25 = Block;
            goto LABEL_37;
          case 138:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_174;
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, void **))(*(_QWORD *)v206 + 408LL))(v206, &Block);
            if ( v10 >= 0 )
            {
              v113 = Block;
              v114 = *(_QWORD *)Block;
              v115 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v207);
              if ( v115 )
                v116 = *v115;
              else
                v116 = 0;
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(v114 + 72))(v113, v116);
              _bstr_t::_Free((_bstr_t *)v207);
              if ( Block )
                (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
LABEL_174:
              v25 = v206;
            }
            else
            {
              if ( Block )
                (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
              v25 = v206;
            }
            goto LABEL_37;
          case 139:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_369;
            Block = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, void **))(*(_QWORD *)v206 + 408LL))(v206, &Block);
            if ( v10 >= 0 )
            {
              LOWORD(v117) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 88LL))(Block, v117);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Block);
LABEL_369:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            }
            else
            {
              if ( Block )
                (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
LABEL_74:
              v25 = v206;
LABEL_37:
              if ( v25 )
                (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
            }
            break;
          case 140:
            Block = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &Block);
            if ( v10 >= 0 )
            {
              LOWORD(v204) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)Block + 440LL))(Block, v204);
            }
LABEL_372:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Block);
            return (unsigned int)v10;
          case 145:
            v188 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 104LL);
            v189 = *(unsigned __int16 ***)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v207);
            if ( v189 )
              v190 = *v189;
            else
              v190 = 0;
            v10 = PrincipalImpl::put_PackageId(v188, v190);
            _bstr_t::_Free((_bstr_t *)v207);
            return (unsigned int)v10;
          case 147:
            v191 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 104LL);
            v192 = *v191;
            v193 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v207);
            if ( v193 )
              v194 = *v193;
            else
              v194 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v192 + 152))(v191, v194);
            _bstr_t::_Free((_bstr_t *)v207);
            return (unsigned int)v10;
          case 148:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_f2a82542_bda5_4e6b_9143_e2bf4f8987b6,
                    &v206);
            if ( v10 >= 0 )
            {
              LOWORD(v198) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v206 + 136LL))(v206, v198);
            }
LABEL_356:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          default:
            return (unsigned int)v10;
        }
        break;
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x18001a1c0  push    rbx
0x18001a1c2  push    rsi
0x18001a1c3  push    rdi
0x18001a1c4  push    r14
0x18001a1c6  push    r15
0x18001a1c8  sub     rsp, 90h
0x18001a1cf  mov     r14, r9
0x18001a1d2  mov     ebx, r8d
0x18001a1d5  mov     rsi, rcx
0x18001a1d8  xor     r15d, r15d
0x18001a1db  mov     [rsp+0B8h+var_88], r15d
0x18001a1e0  movzx   eax, [rsp+0B8h+arg_20]
0x18001a1e8  mov     [rsp+0B8h+var_98], al
0x18001a1ec  call    ?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x18001a1f1  mov     edi, eax
0x18001a1f3  mov     [rsp+0B8h+var_88], eax
0x18001a1f7  test    eax, eax
0x18001a1f9  js      loc_18001BB3B
0x18001a1ff  cmp     ebx, 4Ah ; 'J'
0x18001a202  jz      short loc_18001A270
0x18001a204  cmp     ebx, 2
0x18001a207  jz      loc_18001A2AB
0x18001a20d  cmp     ebx, 4Bh ; 'K'
0x18001a210  jz      loc_18001A2DD
0x18001a216  add     ebx, 0FFFFFFFCh; switch 145 cases
0x18001a219  cmp     ebx, 90h
0x18001a21f  ja      short def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a221  movsxd  rax, ebx
0x18001a224  lea     rdx, __ImageBase
0x18001a22b  movzx   eax, ds:(byte_18001C1C0 - 180000000h)[rdx+rax]
0x18001a233  mov     ecx, ds:(jpt_18001A23D - 180000000h)[rdx+rax*4]
0x18001a23a  add     rcx, rdx
0x18001a23d  jmp     rcx; switch jump
0x18001a23f  cmp     dword ptr [rsi+238h], 0; jumptable 000000018001A23D case 19
0x18001a246  jz      short def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a248  mov     rax, [rsi+200h]
0x18001a24f  mov     rcx, [rax+50h]
0x18001a253  mov     r8, [rcx]
0x18001a256  movzx   eax, byte ptr [r14+20h]
0x18001a25b  neg     al
0x18001a25d  sbb     dx, dx
0x18001a260  mov     rax, [r8+0F0h]
0x18001a267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a26c  mov     edi, eax
0x18001a26e  jmp     short loc_18001A296
0x18001a270  mov     rax, [rsi+200h]
0x18001a277  mov     rcx, [rax+50h]
0x18001a27b  mov     r8, [rcx]
0x18001a27e  movzx   eax, byte ptr [r14+20h]
0x18001a283  neg     al
0x18001a285  sbb     dx, dx
0x18001a288  mov     rax, [r8+90h]
0x18001a28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a294  mov     edi, eax
0x18001a296  mov     [rsp+0B8h+var_88], eax
0x18001a29a  mov     eax, edi; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a29c  add     rsp, 90h
0x18001a2a3  pop     r15
0x18001a2a5  pop     r14
0x18001a2a7  pop     rdi
0x18001a2a8  pop     rsi
0x18001a2a9  pop     rbx
0x18001a2aa  retn
0x18001a2ab  mov     eax, [r14+20h]
0x18001a2af  cmp     eax, 10002h
0x18001a2b4  jnz     loc_18001A3EF
0x18001a2ba  mov     rax, [rsi+200h]
0x18001a2c1  mov     rcx, [rax+50h]
0x18001a2c5  mov     rax, [rcx]
0x18001a2c8  mov     edx, 2
0x18001a2cd  mov     rax, [rax+120h]
0x18001a2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2d9  mov     edi, eax
0x18001a2db  jmp     short loc_18001A296
0x18001a2dd  mov     rax, [rsi+200h]
0x18001a2e4  mov     rcx, [rax+50h]
0x18001a2e8  mov     r8, [rcx]
0x18001a2eb  movzx   eax, byte ptr [r14+20h]
0x18001a2f0  neg     al
0x18001a2f2  sbb     dx, dx
0x18001a2f5  mov     rax, [r8+80h]
0x18001a2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a301  mov     edi, eax
0x18001a303  jmp     short loc_18001A296
0x18001a305  mov     rax, [rsi+200h]; jumptable 000000018001A23D case 110
0x18001a30c  mov     rbx, [rax+60h]
0x18001a310  mov     rdi, [rbx]
0x18001a313  lea     rdx, [rsp+0B8h+Block]
0x18001a318  mov     rcx, [r14+30h]
0x18001a31c  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001a321  nop
0x18001a322  mov     rax, [rax]
0x18001a325  test    rax, rax
0x18001a328  jz      loc_18001AAD4
0x18001a32e  mov     rdx, [rax]
0x18001a331  mov     rcx, rbx
0x18001a334  mov     rax, [rdi+80h]
0x18001a33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a340  mov     edi, eax
0x18001a342  mov     [rsp+0B8h+var_88], eax
0x18001a346  mov     rbx, [rsp+0B8h+Block]
0x18001a34b  test    rbx, rbx
0x18001a34e  jz      def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a354  mov     eax, 0FFFFFFFFh
0x18001a359  lock xadd [rbx+10h], eax
0x18001a35e  cmp     eax, 1
0x18001a361  jnz     def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a367  test    rbx, rbx
0x18001a36a  jz      def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a370  mov     rcx, [rbx]; bstrString
0x18001a373  test    rcx, rcx
0x18001a376  jz      short loc_18001A381
0x18001a378  call    cs:__imp_SysFreeString
0x18001a37e  mov     [rbx], r15
0x18001a381  mov     rcx, [rbx+8]
0x18001a385  test    rcx, rcx
0x18001a388  jnz     loc_18001A590
0x18001a38e  mov     rcx, rbx; Block
0x18001a391  call    cs:__imp_free
0x18001a397  jmp     def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a39c  mov     eax, [r14+20h]; jumptable 000000018001A23D case 73
0x18001a3a0  cmp     eax, 1000h
0x18001a3a5  jz      loc_18001A9B0
0x18001a3ab  cmp     eax, 400h
0x18001a3b0  jz      loc_18001ABCC
0x18001a3b6  cmp     eax, 800h
0x18001a3bb  jz      loc_18001B2E7
0x18001a3c1  cmp     eax, 2000h
0x18001a3c6  jnz     def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a3cc  mov     rax, [rsi+200h]
0x18001a3d3  mov     rcx, [rax+50h]
0x18001a3d7  mov     rax, [rcx]
0x18001a3da  mov     edx, 2
0x18001a3df  mov     rax, [rax+70h]
0x18001a3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3e8  mov     edi, eax
0x18001a3ea  jmp     loc_18001A296
0x18001a3ef  add     eax, 0FFFF0000h; switch 7 cases
0x18001a3f4  cmp     eax, 6
0x18001a3f7  ja      def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a3fd  cdqe
0x18001a3ff  lea     rdx, __ImageBase
0x18001a406  mov     eax, ds:(jpt_18001A410 - 180000000h)[rdx+rax*4]
0x18001a40d  add     rax, rdx
0x18001a410  jmp     rax; switch jump
0x18001a412  mov     rax, [rsi+200h]; jumptable 000000018001A410 case 65542
0x18001a419  mov     rcx, [rax+50h]
0x18001a41d  mov     rax, [rcx]
0x18001a420  mov     edx, 6
0x18001a425  mov     rax, [rax+120h]
0x18001a42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a431  mov     edi, eax
0x18001a433  jmp     loc_18001A296
0x18001a438  mov     rax, [rsi+200h]; jumptable 000000018001A23D case 99
0x18001a43f  mov     rbx, [rax+68h]
0x18001a443  mov     rdi, [rbx]
0x18001a446  lea     rdx, [rsp+0B8h+Block]
0x18001a44b  mov     rcx, [r14+30h]
0x18001a44f  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001a454  nop
0x18001a455  mov     rax, [rax]
0x18001a458  test    rax, rax
0x18001a45b  jz      loc_18001AB55
0x18001a461  mov     rdx, [rax]
0x18001a464  mov     rcx, rbx
0x18001a467  mov     rax, [rdi+40h]
0x18001a46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a470  mov     edi, eax
0x18001a472  mov     [rsp+0B8h+var_88], eax
0x18001a476  mov     rbx, [rsp+0B8h+Block]
0x18001a47b  test    rbx, rbx
0x18001a47e  jz      def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a484  mov     eax, 0FFFFFFFFh
0x18001a489  lock xadd [rbx+10h], eax
0x18001a48e  cmp     eax, 1
0x18001a491  jnz     def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a497  jmp     loc_18001A367
0x18001a49c  mov     [rsp+0B8h+Block], r15; jumptable 000000018001A23D case 88
0x18001a4a1  mov     rax, [rsi+200h]
0x18001a4a8  mov     rcx, [rax+50h]
0x18001a4ac  mov     rax, [rcx]
0x18001a4af  lea     rdx, [rsp+0B8h+Block]
0x18001a4b4  mov     rax, [rax+138h]
0x18001a4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4c0  mov     edi, eax
0x18001a4c2  mov     [rsp+0B8h+var_88], eax
0x18001a4c6  test    eax, eax
0x18001a4c8  js      short loc_18001A4EB
0x18001a4ca  mov     rcx, [rsp+0B8h+Block]
0x18001a4cf  mov     r8, [rcx]
0x18001a4d2  movzx   eax, byte ptr [r14+20h]
0x18001a4d7  neg     al
0x18001a4d9  sbb     dx, dx
0x18001a4dc  mov     rax, [r8+60h]
0x18001a4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4e5  mov     edi, eax
0x18001a4e7  mov     [rsp+0B8h+var_88], eax
0x18001a4eb  mov     rcx, [rsp+0B8h+Block]
0x18001a4f0  test    rcx, rcx
0x18001a4f3  jz      short loc_18001A502
0x18001a4f5  mov     rax, [rcx]
0x18001a4f8  mov     rax, [rax+10h]
0x18001a4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a501  nop
0x18001a502  jmp     def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a507  mov     rax, [rsi+200h]; jumptable 000000018001A23D case 4
0x18001a50e  mov     rbx, [rax+48h]
0x18001a512  mov     rdi, [rbx]
0x18001a515  lea     rdx, [rsp+0B8h+Block]
0x18001a51a  mov     rcx, [r14+30h]
0x18001a51e  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001a523  nop
0x18001a524  mov     rax, [rax]
0x18001a527  test    rax, rax
0x18001a52a  jz      loc_18001ABC4
0x18001a530  mov     rdx, [rax]
0x18001a533  mov     rcx, rbx
0x18001a536  mov     rax, [rdi+0A0h]
0x18001a53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a542  mov     edi, eax
0x18001a544  mov     [rsp+0B8h+var_88], eax
0x18001a548  mov     rbx, [rsp+0B8h+Block]
0x18001a54d  test    rbx, rbx
0x18001a550  jz      def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a556  mov     eax, 0FFFFFFFFh
0x18001a55b  lock xadd [rbx+10h], eax
0x18001a560  cmp     eax, 1
0x18001a563  jnz     def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a569  test    rbx, rbx
0x18001a56c  jz      def_18001A23D; jumptable 000000018001A23D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001a572  mov     rcx, [rbx]; bstrString
0x18001a575  test    rcx, rcx
0x18001a578  jz      short loc_18001A583
0x18001a57a  call    cs:__imp_SysFreeString
0x18001a580  mov     [rbx], r15
0x18001a583  mov     rcx, [rbx+8]; Block
0x18001a587  test    rcx, rcx
0x18001a58a  jz      loc_18001A38E
0x18001a590  call    cs:__imp_free
0x18001a596  mov     [rbx+8], r15
0x18001a59a  jmp     loc_18001A38E
0x18001a59f  mov     rax, [rsi+200h]; jumptable 000000018001A23D case 77
0x18001a5a6  mov     rcx, [rax+50h]
0x18001a5aa  mov     r8, [rcx]
0x18001a5ad  movzx   eax, byte ptr [r14+20h]
0x18001a5b2  neg     al
0x18001a5b4  sbb     dx, dx
0x18001a5b7  mov     rax, [r8+0B0h]
0x18001a5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5c3  mov     edi, eax
0x18001a5c5  jmp     loc_18001A296
0x18001a5ca  mov     rax, [rsi+200h]; jumptable 000000018001A23D case 79
0x18001a5d1  mov     rcx, [rax+50h]
0x18001a5d5  mov     r8, [rcx]
0x18001a5d8  movzx   eax, byte ptr [r14+20h]
0x18001a5dd  neg     al
0x18001a5df  sbb     dx, dx
0x18001a5e2  mov     rax, [r8+160h]
0x18001a5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ee  mov     edi, eax
0x18001a5f0  jmp     loc_18001A296
0x18001a5f5  mov     [rsp+0B8h+Block], r15; jumptable 000000018001A23D case 87
0x18001a5fa  mov     rax, [rsi+200h]
0x18001a601  mov     rcx, [rax+50h]
0x18001a605  mov     rax, [rcx]
0x18001a608  lea     rdx, [rsp+0B8h+Block]
0x18001a60d  mov     rax, [rax+138h]
0x18001a614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a619  mov     edi, eax
0x18001a61b  mov     [rsp+0B8h+var_88], eax
0x18001a61f  test    eax, eax
0x18001a621  js      short loc_18001A66B
0x18001a623  mov     rbx, [rsp+0B8h+Block]
0x18001a628  mov     rdi, [rbx]
0x18001a62b  lea     rdx, [rsp+0B8h+var_78]
0x18001a630  mov     rcx, [r14+30h]
0x18001a634  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001a639  nop
0x18001a63a  mov     rax, [rax]
0x18001a63d  test    rax, rax
0x18001a640  jz      loc_18001AE69
0x18001a646  mov     rdx, [rax]
0x18001a649  mov     rcx, rbx
0x18001a64c  mov     rax, [rdi+50h]
0x18001a650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a655  mov     edi, eax
0x18001a657  mov     [rsp+0B8h+var_88], eax
0x18001a65b  mov     rcx, [rsp+0B8h+var_78]; this
0x18001a660  test    rcx, rcx
0x18001a663  jz      short loc_18001A66B
0x18001a665  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18001a66a  nop
0x18001a66b  mov     rcx, [rsp+0B8h+Block]
0x18001a670  jmp     loc_18001A4F0
0x18001a675  mov     rax, [rsi+200h]; jumptable 000000018001A23D case 76
0x18001a67c  mov     rcx, [rax+50h]
0x18001a680  mov     r8, [rcx]
0x18001a683  movzx   eax, byte ptr [r14+20h]
0x18001a688  neg     al
0x18001a68a  sbb     dx, dx
  ... truncated ...
```
