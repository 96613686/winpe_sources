# ?ProcessValue@?QITaskXmlHandler@@BuilderXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z

- ea: `0x18001b390`
- end: `0x18001d3e0`
- name: `?ProcessValue@?QITaskXmlHandler@@BuilderXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z`
- size: `8272`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180009150`
- `0x18000a728`
- `0x18001b390`
- `0x18001d3f0`
- `0x18001d5d0`
- `0x18001d650`
- `0x18001d700`
- `0x18001d7c0`
- `0x18001d880`
- `0x18003c664`
- `0x180044c40`
- `0x180044ed0`
- `0x180046830`
- `0x18004689c`
- `0x180046930`
- `0x1800469b8`
- `0x180046a40`
- `0x180046ac8`
- `0x180050690`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001b8a9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba50`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b8a9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba50`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b891`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b891`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba37`
- `OLEAUT32!__imp_VariantClear` at `0x18001baac`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba37`
- `OLEAUT32!__imp_VariantClear` at `0x18001baac`

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
  unsigned int v17; // edx
  _bstr_t::Data_t *v18; // rcx
  int v19; // eax
  __int64 *v20; // rbx
  __int64 v21; // rdi
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  _bstr_t::Data_t *v25; // rcx
  __int64 *v26; // rbx
  __int64 v27; // rdi
  __int64 *v28; // rax
  __int64 v29; // rdx
  _bstr_t::Data_t *v30; // rbx
  __int64 v31; // rdi
  _QWORD *v32; // rax
  __int64 v33; // rdx
  _bstr_t::Data_t *v34; // rbx
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
  __int64 (__fastcall ***v79)(_QWORD, GUID *, _bstr_t::Data_t **); // rcx
  __int64 *v80; // rbx
  __int64 v81; // rdi
  __int64 *v82; // rax
  __int64 v83; // rdx
  RegistrationInfoImpl *v84; // rbx
  __int64 v85; // rcx
  unsigned __int16 **v86; // rax
  unsigned __int16 *v87; // rdx
  __int64 *v88; // rax
  _bstr_t::Data_t *v89; // rbx
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
  _bstr_t::Data_t *v101; // rbx
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
  _bstr_t::Data_t *v113; // rbx
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
  _bstr_t::Data_t *v127; // rbx
  __int64 v128; // rdi
  __int64 *v129; // rax
  __int64 v130; // rdx
  _bstr_t::Data_t *v131; // rbx
  __int64 v132; // rdi
  __int64 *v133; // rax
  __int64 v134; // rdx
  _bstr_t::Data_t *v135; // rbx
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
  _bstr_t::Data_t *v205; // [rsp+38h] [rbp-80h] BYREF
  _bstr_t::Data_t *v206; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v207[8]; // [rsp+48h] [rbp-70h] BYREF
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
            v28 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v28 )
              v29 = *v28;
            else
              v29 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v27 + 160))(v26, v29);
            goto LABEL_16;
          case 5:
            v50 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v51 = *v50;
            v52 = *(const OLECHAR ***)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
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
            goto LABEL_75;
          case 6:
            v84 = *(RegistrationInfoImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v85 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              v86 = *(unsigned __int16 ***)XmlParserTempString::GetCopy(v85, &v205);
              if ( v86 )
                v87 = *v86;
              else
                v87 = 0;
              RegistrationInfoImpl::put_LocSource(v84, v87);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            else
            {
              v93 = *(_QWORD *)v84;
              v94 = *(__int64 **)XmlParserTempString::GetCopy(v85, &v205);
              if ( v94 )
                v95 = *v94;
              else
                v95 = 0;
              v10 = (*(__int64 (__fastcall **)(RegistrationInfoImpl *, __int64))(v93 + 192))(v84, v95);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            return (unsigned int)v10;
          case 7:
            v80 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v81 = *v80;
            v82 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v82 )
              v83 = *v82;
            else
              v83 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v81 + 112))(v80, v83);
            _bstr_t::_Free((_bstr_t *)&v205);
            return (unsigned int)v10;
          case 8:
            v54 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v55 = *(_QWORD *)(a4 + 48);
            if ( !*(_DWORD *)(a1 + 572) )
            {
              v71 = *(_QWORD *)v54;
              v72 = *(__int64 **)XmlParserTempString::GetCopy(v55, &v205);
              if ( v72 )
                v73 = *v72;
              else
                v73 = 0;
              goto LABEL_294;
            }
            v56 = *(__int64 **)XmlParserTempString::GetCopy(v55, &v205);
            if ( v56 )
              v57 = *v56;
            else
              v57 = 0;
            ComHandlerActionImpl<IComHandlerAction,5>::put_ClassId(v54, v57);
            _bstr_t::_Free((_bstr_t *)&v205);
            return (unsigned int)v10;
          case 9:
            v60 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 72LL);
            v61 = *v60;
            v62 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v62 )
              v63 = *v62;
            else
              v63 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v61 + 96))(v60, v63);
LABEL_75:
            if ( v205 )
              _bstr_t::Data_t::Release(v205);
            return (unsigned int)v10;
          case 10:
            v64 = *(RegistrationInfoImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v65 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              v66 = *(unsigned __int16 ***)XmlParserTempString::GetCopy(v65, &v205);
              if ( v66 )
                v67 = *v66;
              else
                v67 = 0;
              RegistrationInfoImpl::put_LocDescription(v64, v67);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            else
            {
              v68 = *(_QWORD *)v64;
              v74 = *(__int64 **)XmlParserTempString::GetCopy(v65, &v205);
              if ( v74 )
                v70 = *v74;
              else
                v70 = 0;
LABEL_290:
              v10 = (*(__int64 (__fastcall **)(RegistrationInfoImpl *, __int64))(v68 + 64))(v64, v70);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            return (unsigned int)v10;
          case 11:
            v195 = *(RegistrationInfoImpl **)(*(_QWORD *)(a1 + 512) + 72LL);
            v196 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              Copy = (unsigned __int16 ***)XmlParserTempString::GetCopy(v196, &v205);
              if ( *Copy )
                v123 = **Copy;
              else
                v123 = 0;
              RegistrationInfoImpl::put_LocDocumentation(v195, v123);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            else
            {
              v124 = *(_QWORD *)v195;
              v125 = *(__int64 **)XmlParserTempString::GetCopy(v196, &v205);
              if ( v125 )
                v126 = *v125;
              else
                v126 = 0;
              v10 = (*(__int64 (__fastcall **)(RegistrationInfoImpl *, __int64))(v124 + 128))(v195, v126);
              _bstr_t::_Free((_bstr_t *)&v205);
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
              v77 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
              if ( v77 )
                v78 = *v77;
              else
                v78 = 0;
              v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v76 + 224))(v75, v78);
              _bstr_t::_Free((_bstr_t *)&v205);
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
            v111 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v111 )
              v112 = *v111;
            else
              v112 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v110 + 256))(v109, v112);
            _bstr_t::_Free((_bstr_t *)&v205);
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
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, _bstr_t::Data_t **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                        + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &v205);
            if ( v10 >= 0 )
            {
              v34 = v205;
              v35 = *(_QWORD *)v205;
              v36 = *(_QWORD **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              v37 = v36 ? *v36 : 0LL;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v35 + 64))(v34, v37);
              if ( v206 )
                _bstr_t::Data_t::Release(v206);
            }
            v25 = v205;
            goto LABEL_33;
          case 87:
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, _bstr_t::Data_t **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                        + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &v205);
            if ( v10 >= 0 )
            {
              v30 = v205;
              v31 = *(_QWORD *)v205;
              v32 = *(_QWORD **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              v33 = v32 ? *v32 : 0LL;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v31 + 80))(v30, v33);
              if ( v206 )
                _bstr_t::Data_t::Release(v206);
            }
            v25 = v205;
            goto LABEL_33;
          case 88:
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, _bstr_t::Data_t **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                        + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &v205);
            if ( v10 >= 0 )
            {
              LOWORD(v24) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v205 + 96LL))(v205, v24);
            }
            v25 = v205;
            goto LABEL_33;
          case 89:
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, _bstr_t::Data_t **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                        + 312LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &v205);
            if ( v10 >= 0 )
            {
              LOWORD(v59) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v205 + 112LL))(v205, v59);
            }
            v25 = v205;
            goto LABEL_33;
          case 91:
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, _bstr_t::Data_t **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                        + 360LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &v205);
            if ( v10 >= 0 )
            {
              v127 = v205;
              v128 = *(_QWORD *)v205;
              v129 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v129 )
                v130 = *v129;
              else
                v130 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v128 + 64))(v127, v130);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            goto LABEL_362;
          case 92:
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, _bstr_t::Data_t **))(**(_QWORD **)(*(_QWORD *)(a1 + 512) + 80LL)
                                                                        + 360LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &v205);
            if ( v10 >= 0 )
            {
              v131 = v205;
              v132 = *(_QWORD *)v205;
              v133 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v133 )
                v134 = *v133;
              else
                v134 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v132 + 80))(v131, v134);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            goto LABEL_362;
          case 94:
            if ( !*(_DWORD *)(a1 + 568) )
              return (unsigned int)v10;
            v54 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 80LL);
            v71 = *(_QWORD *)v54;
            v88 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v88 )
              v73 = *v88;
            else
              v73 = 0;
            goto LABEL_294;
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
            v205 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_6d2fd252_75c5_4f66_90ba_2a7d8cc3039f,
                    &v205);
            if ( v10 >= 0 )
            {
              v101 = v205;
              v102 = *(_QWORD *)v205;
              v103 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v103 )
                v104 = *v103;
              else
                v104 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v102 + 104))(v101, v104);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            v25 = v205;
            goto LABEL_33;
          case 99:
            v20 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 104LL);
            v21 = *v20;
            v22 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v22 )
              v23 = *v22;
            else
              v23 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v21 + 64))(v20, v23);
            goto LABEL_16;
          case 104:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v42 = v206;
            v43 = *(_QWORD *)v206;
            v44 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v44 )
              v45 = *v44;
            else
              v45 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v43 + 88))(v42, v45);
            if ( v205 )
              _bstr_t::Data_t::Release(v205);
            goto LABEL_64;
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
              v48 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
              if ( v48 )
                v49 = *v48;
              else
                v49 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v47 + 104))(v46, v49);
              _bstr_t::_Free((_bstr_t *)&v205);
              v25 = v206;
            }
            goto LABEL_33;
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
              v107 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
              if ( v107 )
                v108 = *v107;
              else
                v108 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v106 + 120))(v105, v108);
              _bstr_t::_Free((_bstr_t *)&v205);
              v25 = v206;
            }
            else
            {
              v25 = v206;
            }
            goto LABEL_33;
          case 108:
            if ( *(_DWORD *)(a1 + 520) != 107
              || (v79 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528)) == 0 )
            {
              return (unsigned int)-2147024809;
            }
            v205 = 0;
            v10 = (**v79)(v79, &GUID_6d2fd252_75c5_4f66_90ba_2a7d8cc3039f, &v205);
            if ( v10 >= 0 )
            {
              v89 = v205;
              v90 = *(_QWORD *)v205;
              v91 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v91 )
                v92 = *v91;
              else
                v92 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v90 + 88))(v89, v92);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            v25 = v205;
            goto LABEL_33;
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
            v69 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v69 )
              v70 = *v69;
            else
              v70 = 0;
            goto LABEL_290;
          case 110:
            v13 = *(__int64 **)(*(_QWORD *)(a1 + 512) + 96LL);
            v14 = *v13;
            v15 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v15 )
              v16 = *v15;
            else
              v16 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v14 + 128))(v13, v16);
LABEL_16:
            v18 = v205;
            if ( v205 && _InterlockedExchangeAdd((volatile signed __int32 *)v205 + 4, 0xFFFFFFFF) == 1 )
            {
              if ( v18 )
                _bstr_t::Data_t::`scalar deleting destructor'(v18, v17);
            }
            return (unsigned int)v10;
          case 112:
            v54 = *(PrincipalImpl **)(*(_QWORD *)(a1 + 512) + 104LL);
            v197 = *(_QWORD *)(a4 + 48);
            if ( *(_DWORD *)(a1 + 572) )
            {
              v139 = (unsigned __int16 ***)XmlParserTempString::GetCopy(v197, &v205);
              if ( *v139 )
                v140 = **v139;
              else
                v140 = 0;
              PrincipalImpl::put_LocDisplayName(v54, v140);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            else
            {
              v71 = *(_QWORD *)v54;
              v141 = *(__int64 **)XmlParserTempString::GetCopy(v197, &v205);
              if ( v141 )
                v73 = *v141;
              else
                v73 = 0;
LABEL_294:
              v10 = (*(__int64 (__fastcall **)(PrincipalImpl *, __int64))(v71 + 80))(v54, v73);
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            return (unsigned int)v10;
          case 114:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v142 = v206;
            v143 = *(_QWORD *)v206;
            v144 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v144 )
              v145 = *v144;
            else
              v145 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v143 + 88))(v142, v145);
            _bstr_t::_Free((_bstr_t *)&v205);
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
                v146 = (__int64 **)XmlParserTempString::GetCopy(v199, &v205);
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
                v149 = *(__int64 **)XmlParserTempString::GetCopy(v199, &v205);
                if ( v149 )
                  v150 = *v149;
                else
                  v150 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v148 + 104))(v147, v150);
              }
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            goto LABEL_359;
          case 116:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v151 = v206;
            v152 = *(_QWORD *)v206;
            v153 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v153 )
              v154 = *v153;
            else
              v154 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v152 + 120))(v151, v154);
            _bstr_t::_Free((_bstr_t *)&v205);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 117:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v155 = v206;
            v156 = *(_QWORD *)v206;
            v157 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v157 )
              v158 = *v157;
            else
              v158 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v156 + 136))(v155, v158);
            _bstr_t::_Free((_bstr_t *)&v205);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 118:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v159 = v206;
            v160 = *(_QWORD *)v206;
            v161 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v161 )
              v162 = *v161;
            else
              v162 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v160 + 152))(v159, v162);
            _bstr_t::_Free((_bstr_t *)&v205);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 119:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v163 = v206;
            v164 = *(_QWORD *)v206;
            v165 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v165 )
              v166 = *v165;
            else
              v166 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v164 + 168))(v163, v166);
            _bstr_t::_Free((_bstr_t *)&v205);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            return (unsigned int)v10;
          case 120:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(a1 + 528))(
                    *(_QWORD *)(a1 + 528),
                    &GUID_10f62c64_7e16_4314_a0c2_0c3683f99d40,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_346;
            v167 = v206;
            v168 = *(_QWORD *)v206;
            v169 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v169 )
              v170 = *v169;
            else
              v170 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v168 + 184))(v167, v170);
            _bstr_t::_Free((_bstr_t *)&v205);
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
                v171 = (__int64 **)XmlParserTempString::GetCopy(v200, &v205);
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
                v174 = *(__int64 **)XmlParserTempString::GetCopy(v200, &v205);
                if ( v174 )
                  v175 = *v174;
                else
                  v175 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v173 + 216))(v172, v175);
              }
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            goto LABEL_359;
          case 123:
            v201 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            std::list<_bstr_t>::push_back(a1 + 552, v201);
            _bstr_t::_Free((_bstr_t *)&v205);
            return (unsigned int)v10;
          case 126:
            v64 = *(RegistrationInfoImpl **)(a1 + 544);
            v68 = *(_QWORD *)v64;
            v176 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v176 )
              v70 = *v176;
            else
              v70 = 0;
            goto LABEL_290;
          case 127:
            v54 = *(PrincipalImpl **)(a1 + 544);
            v71 = *(_QWORD *)v54;
            v177 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v205);
            if ( v177 )
              v73 = *v177;
            else
              v73 = 0;
            goto LABEL_294;
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
                v178 = (__int64 **)XmlParserTempString::GetCopy(v202, &v205);
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
                v181 = *(__int64 **)XmlParserTempString::GetCopy(v202, &v205);
                if ( v181 )
                  v182 = *v181;
                else
                  v182 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v180 + 88))(v179, v182);
              }
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            goto LABEL_359;
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
                v183 = (__int64 **)XmlParserTempString::GetCopy(v203, &v205);
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
                v186 = *(__int64 **)XmlParserTempString::GetCopy(v203, &v205);
                if ( v186 )
                  v187 = *v186;
                else
                  v187 = 0;
                v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v185 + 104))(v184, v187);
              }
              _bstr_t::_Free((_bstr_t *)&v205);
            }
            goto LABEL_359;
          case 131:
            v205 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_2c05c3f0_6eed_4c05_a15f_ed7d7a98a369,
                    &v205);
            if ( v10 >= 0 )
            {
              LOWORD(v58) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v205 + 80LL))(v205, v58);
            }
            v25 = v205;
            goto LABEL_33;
          case 132:
            v205 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_2c05c3f0_6eed_4c05_a15f_ed7d7a98a369,
                    &v205);
            if ( v10 >= 0 )
            {
              LOWORD(v100) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v205 + 64LL))(v205, v100);
            }
            v25 = v205;
            goto LABEL_33;
          case 135:
            v205 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 104LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 104LL),
                    &GUID_248919ae_e345_4a6d_8aeb_e0d3165c904e,
                    &v205);
            if ( v10 >= 0 )
            {
              v135 = v205;
              v136 = *(_QWORD *)v205;
              v137 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), &v206);
              if ( v137 )
                v138 = *v137;
              else
                v138 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v136 + 88))(v135, v138);
              _bstr_t::_Free((_bstr_t *)&v206);
            }
            goto LABEL_362;
          case 137:
            v205 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &v205);
            if ( v10 < 0 )
              goto LABEL_162;
            v206 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, _bstr_t::Data_t **))(*(_QWORD *)v205 + 408LL))(
                    v205,
                    &v206);
            if ( v10 < 0 )
            {
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v205);
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
LABEL_162:
            v25 = v205;
            goto LABEL_33;
          case 138:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_164;
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, _bstr_t::Data_t **))(*(_QWORD *)v206 + 408LL))(
                    v206,
                    &v205);
            if ( v10 >= 0 )
            {
              v113 = v205;
              v114 = *(_QWORD *)v205;
              v115 = *(__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v207);
              if ( v115 )
                v116 = *v115;
              else
                v116 = 0;
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(v114 + 72))(v113, v116);
              _bstr_t::_Free((_bstr_t *)v207);
              if ( v205 )
                (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v205 + 16LL))(v205);
LABEL_164:
              v25 = v206;
            }
            else
            {
              if ( v205 )
                (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v205 + 16LL))(v205);
              v25 = v206;
            }
            goto LABEL_33;
          case 139:
            v206 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &v206);
            if ( v10 < 0 )
              goto LABEL_359;
            v205 = 0;
            v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, _bstr_t::Data_t **))(*(_QWORD *)v206 + 408LL))(
                    v206,
                    &v205);
            if ( v10 >= 0 )
            {
              LOWORD(v117) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v205 + 88LL))(v205, v117);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v205);
LABEL_359:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v206);
            }
            else
            {
              if ( v205 )
                (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v205 + 16LL))(v205);
LABEL_64:
              v25 = v206;
LABEL_33:
              if ( v25 )
                (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v25 + 16LL))(v25);
            }
            break;
          case 140:
            v205 = 0;
            v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _bstr_t::Data_t **))(*(_QWORD *)(a1 + 512) + 80LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 512) + 80LL),
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    &v205);
            if ( v10 >= 0 )
            {
              LOWORD(v204) = -(*(_BYTE *)(a4 + 32) != 0);
              v10 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, __int64))(*(_QWORD *)v205 + 440LL))(v205, v204);
            }
LABEL_362:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v205);
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
LABEL_346:
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
0x18001b390  push    rbx
0x18001b392  push    rsi
0x18001b393  push    rdi
0x18001b394  push    r14
0x18001b396  push    r15
0x18001b398  sub     rsp, 90h
0x18001b39f  mov     r14, r9
0x18001b3a2  mov     ebx, r8d
0x18001b3a5  mov     rsi, rcx
0x18001b3a8  xor     r15d, r15d
0x18001b3ab  mov     [rsp+0B8h+var_88], r15d
0x18001b3b0  movzx   eax, [rsp+0B8h+arg_20]
0x18001b3b8  mov     [rsp+0B8h+var_98], al
0x18001b3bc  call    ?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x18001b3c1  mov     edi, eax
0x18001b3c3  mov     [rsp+0B8h+var_88], eax
0x18001b3c7  test    eax, eax
0x18001b3c9  js      loc_18001CCAA
0x18001b3cf  cmp     ebx, 4Ah ; 'J'
0x18001b3d2  jz      short loc_18001B444
0x18001b3d4  cmp     ebx, 2
0x18001b3d7  jz      loc_18001B480
0x18001b3dd  cmp     ebx, 4Bh ; 'K'
0x18001b3e0  jz      loc_18001B4B2
0x18001b3e6  add     ebx, 0FFFFFFFCh; switch 145 cases
0x18001b3e9  cmp     ebx, 90h
0x18001b3ef  ja      short def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b3f1  movsxd  rax, ebx
0x18001b3f4  lea     rdx, __ImageBase
0x18001b3fb  movzx   eax, ds:(byte_18001D330 - 180000000h)[rdx+rax]
0x18001b403  mov     ecx, ds:(jpt_18001B40D - 180000000h)[rdx+rax*4]
0x18001b40a  add     rcx, rdx
0x18001b40d  jmp     rcx; switch jump
0x18001b413  cmp     dword ptr [rsi+238h], 0; jumptable 000000018001B40D case 19
0x18001b41a  jz      short def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b41c  mov     rax, [rsi+200h]
0x18001b423  mov     rcx, [rax+50h]
0x18001b427  mov     r8, [rcx]
0x18001b42a  movzx   eax, byte ptr [r14+20h]
0x18001b42f  neg     al
0x18001b431  sbb     dx, dx
0x18001b434  mov     rax, [r8+0F0h]
0x18001b43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b440  mov     edi, eax
0x18001b442  jmp     short loc_18001B46A
0x18001b444  mov     rax, [rsi+200h]
0x18001b44b  mov     rcx, [rax+50h]
0x18001b44f  mov     r8, [rcx]
0x18001b452  movzx   eax, byte ptr [r14+20h]
0x18001b457  neg     al
0x18001b459  sbb     dx, dx
0x18001b45c  mov     rax, [r8+90h]
0x18001b463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b468  mov     edi, eax
0x18001b46a  mov     [rsp+0B8h+var_88], eax
0x18001b46e  mov     eax, edi; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b470  add     rsp, 90h
0x18001b477  pop     r15
0x18001b479  pop     r14
0x18001b47b  pop     rdi
0x18001b47c  pop     rsi
0x18001b47d  pop     rbx
0x18001b47e  retn
0x18001b480  mov     eax, [r14+20h]
0x18001b484  cmp     eax, 10002h
0x18001b489  jnz     loc_18001B5A2
0x18001b48f  mov     rax, [rsi+200h]
0x18001b496  mov     rcx, [rax+50h]
0x18001b49a  mov     rax, [rcx]
0x18001b49d  mov     edx, 2
0x18001b4a2  mov     rax, [rax+120h]
0x18001b4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ae  mov     edi, eax
0x18001b4b0  jmp     short loc_18001B46A
0x18001b4b2  mov     rax, [rsi+200h]
0x18001b4b9  mov     rcx, [rax+50h]
0x18001b4bd  mov     r8, [rcx]
0x18001b4c0  movzx   eax, byte ptr [r14+20h]
0x18001b4c5  neg     al
0x18001b4c7  sbb     dx, dx
0x18001b4ca  mov     rax, [r8+80h]
0x18001b4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4d6  mov     edi, eax
0x18001b4d8  jmp     short loc_18001B46A
0x18001b4da  mov     rax, [rsi+200h]; jumptable 000000018001B40D case 110
0x18001b4e1  mov     rbx, [rax+60h]
0x18001b4e5  mov     rdi, [rbx]
0x18001b4e8  lea     rdx, [rsp+0B8h+var_80]
0x18001b4ed  mov     rcx, [r14+30h]
0x18001b4f1  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001b4f6  nop
0x18001b4f7  mov     rax, [rax]
0x18001b4fa  test    rax, rax
0x18001b4fd  jz      loc_18001BC43
0x18001b503  mov     rdx, [rax]
0x18001b506  mov     rcx, rbx
0x18001b509  mov     rax, [rdi+80h]
0x18001b510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b515  mov     edi, eax
0x18001b517  mov     [rsp+0B8h+var_88], eax
0x18001b51b  mov     rcx, [rsp+0B8h+var_80]; this
0x18001b520  test    rcx, rcx
0x18001b523  jz      def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b529  mov     eax, 0FFFFFFFFh
0x18001b52e  lock xadd [rcx+10h], eax
0x18001b533  cmp     eax, 1
0x18001b536  jnz     def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b53c  test    rcx, rcx
0x18001b53f  jz      def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b545  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x18001b54a  jmp     def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b54f  mov     eax, [r14+20h]; jumptable 000000018001B40D case 73
0x18001b553  cmp     eax, 1000h
0x18001b558  jz      loc_18001BB1F
0x18001b55e  cmp     eax, 400h
0x18001b563  jz      loc_18001BD3B
0x18001b569  cmp     eax, 800h
0x18001b56e  jz      loc_18001C456
0x18001b574  cmp     eax, 2000h
0x18001b579  jnz     def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b57f  mov     rax, [rsi+200h]
0x18001b586  mov     rcx, [rax+50h]
0x18001b58a  mov     rax, [rcx]
0x18001b58d  mov     edx, 2
0x18001b592  mov     rax, [rax+70h]
0x18001b596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b59b  mov     edi, eax
0x18001b59d  jmp     loc_18001B46A
0x18001b5a2  add     eax, 0FFFF0000h; switch 7 cases
0x18001b5a7  cmp     eax, 6
0x18001b5aa  ja      def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b5b0  cdqe
0x18001b5b2  lea     rdx, __ImageBase
0x18001b5b9  mov     eax, ds:(jpt_18001B5C3 - 180000000h)[rdx+rax*4]
0x18001b5c0  add     rax, rdx
0x18001b5c3  jmp     rax; switch jump
0x18001b5c9  mov     rax, [rsi+200h]; jumptable 000000018001B5C3 case 65542
0x18001b5d0  mov     rcx, [rax+50h]
0x18001b5d4  mov     rax, [rcx]
0x18001b5d7  mov     edx, 6
0x18001b5dc  mov     rax, [rax+120h]
0x18001b5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5e8  mov     edi, eax
0x18001b5ea  jmp     loc_18001B46A
0x18001b5ef  mov     rax, [rsi+200h]; jumptable 000000018001B40D case 99
0x18001b5f6  mov     rbx, [rax+68h]
0x18001b5fa  mov     rdi, [rbx]
0x18001b5fd  lea     rdx, [rsp+0B8h+var_80]
0x18001b602  mov     rcx, [r14+30h]
0x18001b606  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001b60b  nop
0x18001b60c  mov     rax, [rax]
0x18001b60f  test    rax, rax
0x18001b612  jz      loc_18001BCC4
0x18001b618  mov     rdx, [rax]
0x18001b61b  mov     rcx, rbx
0x18001b61e  mov     rax, [rdi+40h]
0x18001b622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b627  mov     edi, eax
0x18001b629  mov     [rsp+0B8h+var_88], eax
0x18001b62d  jmp     loc_18001B51B
0x18001b632  mov     [rsp+0B8h+var_80], r15; jumptable 000000018001B40D case 88
0x18001b637  mov     rax, [rsi+200h]
0x18001b63e  mov     rcx, [rax+50h]
0x18001b642  mov     rax, [rcx]
0x18001b645  lea     rdx, [rsp+0B8h+var_80]
0x18001b64a  mov     rax, [rax+138h]
0x18001b651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b656  mov     edi, eax
0x18001b658  mov     [rsp+0B8h+var_88], eax
0x18001b65c  test    eax, eax
0x18001b65e  js      short loc_18001B681
0x18001b660  mov     rcx, [rsp+0B8h+var_80]
0x18001b665  mov     r8, [rcx]
0x18001b668  movzx   eax, byte ptr [r14+20h]
0x18001b66d  neg     al
0x18001b66f  sbb     dx, dx
0x18001b672  mov     rax, [r8+60h]
0x18001b676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b67b  mov     edi, eax
0x18001b67d  mov     [rsp+0B8h+var_88], eax
0x18001b681  mov     rcx, [rsp+0B8h+var_80]
0x18001b686  test    rcx, rcx
0x18001b689  jz      short loc_18001B698
0x18001b68b  mov     rax, [rcx]
0x18001b68e  mov     rax, [rax+10h]
0x18001b692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b697  nop
0x18001b698  jmp     def_18001B40D; jumptable 000000018001B40D default case, cases 12-18,21-71,74,75,80,85,90,93,97,98,100-103,107,111,113,122,124,125,128,133,134,136,141-144,146
0x18001b69d  mov     rax, [rsi+200h]; jumptable 000000018001B40D case 4
0x18001b6a4  mov     rbx, [rax+48h]
0x18001b6a8  mov     rdi, [rbx]
0x18001b6ab  lea     rdx, [rsp+0B8h+var_80]
0x18001b6b0  mov     rcx, [r14+30h]
0x18001b6b4  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001b6b9  nop
0x18001b6ba  mov     rax, [rax]
0x18001b6bd  test    rax, rax
0x18001b6c0  jz      loc_18001BD33
0x18001b6c6  mov     rdx, [rax]
0x18001b6c9  mov     rcx, rbx
0x18001b6cc  mov     rax, [rdi+0A0h]
0x18001b6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6d8  mov     edi, eax
0x18001b6da  mov     [rsp+0B8h+var_88], eax
0x18001b6de  jmp     loc_18001B51B
0x18001b6e3  mov     rax, [rsi+200h]; jumptable 000000018001B40D case 77
0x18001b6ea  mov     rcx, [rax+50h]
0x18001b6ee  mov     r8, [rcx]
0x18001b6f1  movzx   eax, byte ptr [r14+20h]
0x18001b6f6  neg     al
0x18001b6f8  sbb     dx, dx
0x18001b6fb  mov     rax, [r8+0B0h]
0x18001b702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b707  mov     edi, eax
0x18001b709  jmp     loc_18001B46A
0x18001b70e  mov     rax, [rsi+200h]; jumptable 000000018001B40D case 79
0x18001b715  mov     rcx, [rax+50h]
0x18001b719  mov     r8, [rcx]
0x18001b71c  movzx   eax, byte ptr [r14+20h]
0x18001b721  neg     al
0x18001b723  sbb     dx, dx
0x18001b726  mov     rax, [r8+160h]
0x18001b72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b732  mov     edi, eax
0x18001b734  jmp     loc_18001B46A
0x18001b739  mov     [rsp+0B8h+var_80], r15; jumptable 000000018001B40D case 87
0x18001b73e  mov     rax, [rsi+200h]
0x18001b745  mov     rcx, [rax+50h]
0x18001b749  mov     rax, [rcx]
0x18001b74c  lea     rdx, [rsp+0B8h+var_80]
0x18001b751  mov     rax, [rax+138h]
0x18001b758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b75d  mov     edi, eax
0x18001b75f  mov     [rsp+0B8h+var_88], eax
0x18001b763  test    eax, eax
0x18001b765  js      short loc_18001B7AF
0x18001b767  mov     rbx, [rsp+0B8h+var_80]
0x18001b76c  mov     rdi, [rbx]
0x18001b76f  lea     rdx, [rsp+0B8h+var_78]
0x18001b774  mov     rcx, [r14+30h]
0x18001b778  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001b77d  nop
0x18001b77e  mov     rax, [rax]
0x18001b781  test    rax, rax
0x18001b784  jz      loc_18001BFD8
0x18001b78a  mov     rdx, [rax]
0x18001b78d  mov     rcx, rbx
0x18001b790  mov     rax, [rdi+50h]
0x18001b794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b799  mov     edi, eax
0x18001b79b  mov     [rsp+0B8h+var_88], eax
0x18001b79f  mov     rcx, [rsp+0B8h+var_78]; this
0x18001b7a4  test    rcx, rcx
0x18001b7a7  jz      short loc_18001B7AF
0x18001b7a9  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18001b7ae  nop
0x18001b7af  mov     rcx, [rsp+0B8h+var_80]
0x18001b7b4  jmp     loc_18001B686
0x18001b7b9  mov     rax, [rsi+200h]; jumptable 000000018001B40D case 76
0x18001b7c0  mov     rcx, [rax+50h]
0x18001b7c4  mov     r8, [rcx]
0x18001b7c7  movzx   eax, byte ptr [r14+20h]
0x18001b7cc  neg     al
0x18001b7ce  sbb     dx, dx
0x18001b7d1  mov     rax, [r8+0A0h]
0x18001b7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7dd  mov     edi, eax
0x18001b7df  jmp     loc_18001B46A
0x18001b7e4  mov     [rsp+0B8h+var_80], r15; jumptable 000000018001B40D case 86
0x18001b7e9  mov     rax, [rsi+200h]
0x18001b7f0  mov     rcx, [rax+50h]
0x18001b7f4  mov     rax, [rcx]
0x18001b7f7  lea     rdx, [rsp+0B8h+var_80]
0x18001b7fc  mov     rax, [rax+138h]
0x18001b803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b808  mov     edi, eax
0x18001b80a  mov     [rsp+0B8h+var_88], eax
0x18001b80e  test    eax, eax
0x18001b810  js      short loc_18001B85A
0x18001b812  mov     rbx, [rsp+0B8h+var_80]
0x18001b817  mov     rdi, [rbx]
0x18001b81a  lea     rdx, [rsp+0B8h+var_78]
0x18001b81f  mov     rcx, [r14+30h]
0x18001b823  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18001b828  nop
0x18001b829  mov     rax, [rax]
0x18001b82c  test    rax, rax
0x18001b82f  jz      loc_18001BFB6
0x18001b835  mov     rdx, [rax]
0x18001b838  mov     rcx, rbx
0x18001b83b  mov     rax, [rdi+40h]
0x18001b83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b844  mov     edi, eax
0x18001b846  mov     [rsp+0B8h+var_88], eax
0x18001b84a  mov     rcx, [rsp+0B8h+var_78]; this
0x18001b84f  test    rcx, rcx
0x18001b852  jz      short loc_18001B85A
0x18001b854  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18001b859  nop
  ... truncated ...
```
