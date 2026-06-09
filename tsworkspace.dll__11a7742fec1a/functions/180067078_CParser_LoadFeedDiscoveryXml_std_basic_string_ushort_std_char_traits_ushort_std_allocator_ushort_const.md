# CParser::LoadFeedDiscoveryXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180067078`
- end: `0x1800676d2`
- name: `?LoadFeedDiscoveryXml@CParser@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1626`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18004cfc0`

## callees

- `0x1800054c4`
- `0x18000b1d8`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000ff00`
- `0x180027e9c`
- `0x1800289a8`
- `0x1800461b0`
- `0x180067078`
- `0x18006c158`
- `0x18009a520`
- `0x18009a5e0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18006711a`
- `ole32!CoCreateInstance` at `0x18006711a`
- `OLEAUT32!__imp_SysFreeString` at `0x180067667`
- `OLEAUT32!__imp_SysFreeString` at `0x180067667`
- `OLEAUT32!__imp_VariantInit` at `0x1800670e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800670e2`
- `OLEAUT32!__imp_VariantClear` at `0x180067695`
- `OLEAUT32!__imp_VariantClear` at `0x180067695`

## string_xrefs

- `0x1800671d8`: `IXmlDOMDocument::put_async failed`
- `0x180067230`: `IXmlDOMDocument::put_validateOnParse failed`
- `0x18006743c`: `MaxXMLSize`
- `0x18006748a`: `IXmlDOMDocument::setProperty  MaxXMLSize failed`
- `0x1800674f4`: `TSWFileURLFromPath failed`
- `0x18006715a`: `CoCreateInstance DomDocument60 failed`
- `0x18006728b`: `IXmlDOMDocument::put_resolveExternals failed`
- `0x18006734d`: `IXmlDOMDocument::setProperty  UseInlineSchema failed`
- `0x180067409`: `IXmlDOMDocument::setProperty NormalizeAttributeValues failed`
- `0x1800675a1`: `IXmlDOMDocument::LoadXML failed`

## pseudocode

```c
__int64 __fastcall CParser::LoadFeedDiscoveryXml(__int64 a1, const unsigned __int16 *a2)
{
  _QWORD *v4; // rsi
  int Instance; // ebx
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, __int64, VARIANTARG *); // r14
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64, VARIANTARG *); // r14
  __int128 v17; // xmm6
  IRecordInfo *v18; // xmm7_8
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, VARIANTARG *, __int16 *); // rbx
  const struct _bstr_t *v24; // rax
  BSTR v25; // rbx
  char v26; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v28; // r8d
  __int16 v30; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  IRecordInfo *v36; // [rsp+60h] [rbp-A0h]
  VARIANTARG v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v42[2088]; // [rsp+C0h] [rbp-40h] BYREF

  v41 = -2;
  v30 = 0;
  VariantInit(&pvarg);
  v39 = 0;
  v38 = 0;
  v32 = 0;
  *(_BYTE *)(a1 + 80) = 0;
  v4 = (_QWORD *)(a1 + 168);
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               3u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               (LPVOID *)(a1 + 168));
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 504LL))(*v4, 0);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 544LL))(*v4, 0);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 560LL))(*v4, 0);
        if ( Instance >= 0 )
        {
          v9 = *v4;
          v10 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)*v4 + 640LL);
          LOWORD(v35) = 11;
          WORD4(v35) = 0;
          v11 = v35;
          v12 = v36;
          v13 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, L"UseInlineSchema");
          if ( *(_QWORD *)v13 )
            v14 = **(_QWORD **)v13;
          else
            v14 = 0;
          *(_OWORD *)&v37.vt = v11;
          v37.pRecInfo = v12;
          Instance = v10(v9, v14, &v37);
          _bstr_t::_Free((_bstr_t *)&bstrString);
          _variant_t::~_variant_t((_variant_t *)&v35);
          if ( Instance >= 0 )
          {
            v15 = *v4;
            v16 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)*v4 + 640LL);
            LOWORD(v35) = 11;
            WORD4(v35) = 0;
            v17 = v35;
            v18 = v36;
            v19 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, L"NormalizeAttributeValues");
            if ( *(_QWORD *)v19 )
              v20 = **(_QWORD **)v19;
            else
              v20 = 0;
            *(_OWORD *)&v37.vt = v17;
            v37.pRecInfo = v18;
            Instance = v16(v15, v20, &v37);
            _bstr_t::_Free((_bstr_t *)&bstrString);
            _variant_t::~_variant_t((_variant_t *)&v35);
            if ( Instance >= 0 )
            {
              ATL::CComVariant::operator=(&pvarg);
              v21 = *v4;
              v37 = pvarg;
              Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v21 + 640LL))(
                           v21,
                           L"MaxXMLSize",
                           &v37);
              if ( Instance >= 0 )
              {
                v32 = 2084;
                if ( *((_QWORD *)a2 + 3) >= 8u )
                  a2 = *(const unsigned __int16 **)a2;
                Instance = TSWFileURLFromPath(a2, v42, &v32);
                if ( Instance >= 0 )
                {
                  v22 = *v4;
                  v23 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int16 *))(*(_QWORD *)*v4 + 464LL);
                  v24 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, v42);
                  v37 = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v35, v24);
                  Instance = v23(v22, &v37, &v30);
                  _variant_t::~_variant_t((_variant_t *)&v35);
                  _bstr_t::_Free((_bstr_t *)&bstrString);
                  if ( Instance >= 0 )
                  {
                    if ( v30 )
                    {
                      Instance = 0;
                    }
                    else
                    {
                      v34 = 0;
                      v33 = 0;
                      bstrString = 0;
                      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 480LL))(*v4, &v34) >= 0 )
                      {
                        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 88LL))(v34, &v33);
                        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v34 + 72LL))(v34, &bstrString);
                      }
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v25 = bstrString;
                        v26 = v33;
                        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                        WPP_SF_DdS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          122,
                          v28,
                          CurrentThreadActivityIdPrefix,
                          v26,
                          (__int64)v25);
                      }
                      Instance = -2147220988;
                      SysFreeString(bstrString);
                      ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v34);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v7 = 121;
                    v8 = "IXmlDOMDocument::LoadXML failed";
                    goto LABEL_6;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v7 = 120;
                  v8 = "TSWFileURLFromPath failed";
                  goto LABEL_6;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                v7 = 119;
                v8 = "IXmlDOMDocument::setProperty  MaxXMLSize failed";
                goto LABEL_6;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v6 = RdpWppGetCurrentThreadActivityIdPrefix();
              v7 = 118;
              v8 = "IXmlDOMDocument::setProperty NormalizeAttributeValues failed";
              goto LABEL_6;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 117;
            v8 = "IXmlDOMDocument::setProperty  UseInlineSchema failed";
            goto LABEL_6;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 116;
          v8 = "IXmlDOMDocument::put_resolveExternals failed";
          goto LABEL_6;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 115;
        v8 = "IXmlDOMDocument::put_validateOnParse failed";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 114;
      v8 = "IXmlDOMDocument::put_async failed";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 113;
    v8 = "CoCreateInstance DomDocument60 failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v6,
      (__int64)v8,
      Instance);
  }
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v38);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v39);
  VariantClear(&pvarg);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180067078  push    rbp
0x18006707a  push    rdi
0x18006707b  push    r12
0x18006707d  push    r14
0x18006707f  push    r15
0x180067081  lea     rbp, [rsp-1040h]
0x180067089  mov     eax, 1140h
0x18006708e  call    _alloca_probe
0x180067093  sub     rsp, rax
0x180067096  mov     [rbp+1060h+var_10A8], 0FFFFFFFFFFFFFFFEh
0x18006709e  mov     [rsp+1160h+arg_10], rbx
0x1800670a6  mov     [rsp+1160h+arg_18], rsi
0x1800670ae  movaps  [rsp+1160h+var_30], xmm6
0x1800670b6  movaps  [rsp+1160h+var_40], xmm7
0x1800670be  mov     rax, cs:__security_cookie
0x1800670c5  xor     rax, rsp
0x1800670c8  mov     [rbp+1060h+var_50], rax
0x1800670cf  mov     rdi, rdx
0x1800670d2  mov     rbx, rcx
0x1800670d5  xor     r15d, r15d
0x1800670d8  mov     [rsp+1160h+var_1130], r15w
0x1800670de  lea     rcx, [rbp+1060h+pvarg]; pvarg
0x1800670e2  call    cs:__imp_VariantInit
0x1800670e8  nop
0x1800670e9  mov     [rbp+1060h+var_10C8], r15
0x1800670ed  mov     [rbp+1060h+var_10D0], r15
0x1800670f1  mov     [rsp+1160h+var_1120], r15d
0x1800670f6  mov     [rbx+50h], r15b
0x1800670fa  lea     rsi, [rbx+0A8h]
0x180067101  mov     [rsp+1160h+ppv], rsi; ppv
0x180067106  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18006710d  xor     edx, edx; pUnkOuter
0x18006710f  lea     r8d, [r15+3]; dwClsContext
0x180067113  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18006711a  call    cs:__imp_CoCreateInstance
0x180067120  mov     ebx, eax
0x180067122  test    eax, eax
0x180067124  jns     short loc_180067189
0x180067126  lea     rcx, WPP_GLOBAL_Control
0x18006712d  mov     rax, cs:WPP_GLOBAL_Control
0x180067134  cmp     rax, rcx
0x180067137  jz      loc_18006767D
0x18006713d  test    byte ptr [rax+1Ch], 8
0x180067141  jz      loc_18006767D
0x180067147  cmp     byte ptr [rax+19h], 2
0x18006714b  jb      loc_18006767D
0x180067151  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067156  lea     edx, [r15+71h]
0x18006715a  lea     rcx, aCocreateinstan_7; "CoCreateInstance DomDocument60 failed"
0x180067161  mov     dword ptr [rsp+1160h+var_1138], ebx
0x180067165  mov     [rsp+1160h+ppv], rcx
0x18006716a  mov     r9d, eax
0x18006716d  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180067174  mov     rcx, cs:WPP_GLOBAL_Control
0x18006717b  mov     rcx, [rcx+10h]
0x18006717f  call    WPP_SF_DsD
0x180067184  jmp     loc_18006767D
0x180067189  mov     rcx, [rsi]
0x18006718c  mov     rax, [rcx]
0x18006718f  xor     edx, edx
0x180067191  mov     rax, [rax+1F8h]
0x180067198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006719d  mov     ebx, eax
0x18006719f  test    eax, eax
0x1800671a1  jns     short loc_1800671E1
0x1800671a3  lea     rcx, WPP_GLOBAL_Control
0x1800671aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800671b1  cmp     rax, rcx
0x1800671b4  jz      loc_18006767D
0x1800671ba  test    byte ptr [rax+1Ch], 8
0x1800671be  jz      loc_18006767D
0x1800671c4  cmp     byte ptr [rax+19h], 2
0x1800671c8  jb      loc_18006767D
0x1800671ce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800671d3  mov     edx, 72h ; 'r'
0x1800671d8  lea     rcx, aIxmldomdocumen_4; "IXmlDOMDocument::put_async failed"
0x1800671df  jmp     short loc_180067161
0x1800671e1  mov     rcx, [rsi]
0x1800671e4  mov     rax, [rcx]
0x1800671e7  xor     edx, edx
0x1800671e9  mov     rax, [rax+220h]
0x1800671f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671f5  mov     ebx, eax
0x1800671f7  test    eax, eax
0x1800671f9  jns     short loc_18006723C
0x1800671fb  lea     rcx, WPP_GLOBAL_Control
0x180067202  mov     rax, cs:WPP_GLOBAL_Control
0x180067209  cmp     rax, rcx
0x18006720c  jz      loc_18006767D
0x180067212  test    byte ptr [rax+1Ch], 8
0x180067216  jz      loc_18006767D
0x18006721c  cmp     byte ptr [rax+19h], 2
0x180067220  jb      loc_18006767D
0x180067226  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006722b  mov     edx, 73h ; 's'
0x180067230  lea     rcx, aIxmldomdocumen_6; "IXmlDOMDocument::put_validateOnParse fa"...
0x180067237  jmp     loc_180067161
0x18006723c  mov     rcx, [rsi]
0x18006723f  mov     rax, [rcx]
0x180067242  xor     edx, edx
0x180067244  mov     rax, [rax+230h]
0x18006724b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067250  mov     ebx, eax
0x180067252  test    eax, eax
0x180067254  jns     short loc_180067297
0x180067256  lea     rcx, WPP_GLOBAL_Control
0x18006725d  mov     rax, cs:WPP_GLOBAL_Control
0x180067264  cmp     rax, rcx
0x180067267  jz      loc_18006767D
0x18006726d  test    byte ptr [rax+1Ch], 8
0x180067271  jz      loc_18006767D
0x180067277  cmp     byte ptr [rax+19h], 2
0x18006727b  jb      loc_18006767D
0x180067281  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067286  mov     edx, 74h ; 't'
0x18006728b  lea     rcx, aIxmldomdocumen_3; "IXmlDOMDocument::put_resolveExternals f"...
0x180067292  jmp     loc_180067161
0x180067297  mov     rbx, [rsi]
0x18006729a  mov     rax, [rbx]
0x18006729d  mov     r14, [rax+280h]
0x1800672a4  mov     r12d, 0Bh
0x1800672aa  mov     word ptr [rsp+1160h+var_1110], r12w
0x1800672b0  mov     word ptr [rsp+1160h+var_1110+8], r15w
0x1800672b6  movups  xmm6, [rsp+1160h+var_1110]
0x1800672bb  movsd   xmm7, [rsp+1160h+var_1100]
0x1800672c1  lea     rdx, aUseinlineschem; "UseInlineSchema"
0x1800672c8  lea     rcx, [rsp+1160h+bstrString]; this
0x1800672cd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800672d2  nop
0x1800672d3  mov     rdx, [rax]
0x1800672d6  test    rdx, rdx
0x1800672d9  jz      short loc_1800672E0
0x1800672db  mov     rdx, [rdx]
0x1800672de  jmp     short loc_1800672E3
0x1800672e0  mov     rdx, r15
0x1800672e3  movaps  [rsp+1160h+var_10F0], xmm6
0x1800672e8  movsd   [rbp+1060h+var_10E0], xmm7
0x1800672ed  lea     r8, [rsp+1160h+var_10F0]
0x1800672f2  mov     rcx, rbx
0x1800672f5  mov     rax, r14
0x1800672f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672fd  mov     ebx, eax
0x1800672ff  lea     rcx, [rsp+1160h+bstrString]; this
0x180067304  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180067309  nop
0x18006730a  lea     rcx, [rsp+1160h+var_1110]; this
0x18006730f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067314  test    ebx, ebx
0x180067316  jns     short loc_180067359
0x180067318  lea     rcx, WPP_GLOBAL_Control
0x18006731f  mov     rax, cs:WPP_GLOBAL_Control
0x180067326  cmp     rax, rcx
0x180067329  jz      loc_18006767D
0x18006732f  test    byte ptr [rax+1Ch], 8
0x180067333  jz      loc_18006767D
0x180067339  cmp     byte ptr [rax+19h], 2
0x18006733d  jb      loc_18006767D
0x180067343  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067348  mov     edx, 75h ; 'u'
0x18006734d  lea     rcx, aIxmldomdocumen_5; "IXmlDOMDocument::setProperty  UseInline"...
0x180067354  jmp     loc_180067161
0x180067359  mov     rbx, [rsi]
0x18006735c  mov     rax, [rbx]
0x18006735f  mov     r14, [rax+280h]
0x180067366  mov     word ptr [rsp+1160h+var_1110], r12w
0x18006736c  mov     word ptr [rsp+1160h+var_1110+8], r15w
0x180067372  movups  xmm6, [rsp+1160h+var_1110]
0x180067377  movsd   xmm7, [rsp+1160h+var_1100]
0x18006737d  lea     rdx, aNormalizeattri; "NormalizeAttributeValues"
0x180067384  lea     rcx, [rsp+1160h+bstrString]; this
0x180067389  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006738e  nop
0x18006738f  mov     rdx, [rax]
0x180067392  test    rdx, rdx
0x180067395  jz      short loc_18006739C
0x180067397  mov     rdx, [rdx]
0x18006739a  jmp     short loc_18006739F
0x18006739c  mov     rdx, r15
0x18006739f  movaps  [rsp+1160h+var_10F0], xmm6
0x1800673a4  movsd   [rbp+1060h+var_10E0], xmm7
0x1800673a9  lea     r8, [rsp+1160h+var_10F0]
0x1800673ae  mov     rcx, rbx
0x1800673b1  mov     rax, r14
0x1800673b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673b9  mov     ebx, eax
0x1800673bb  lea     rcx, [rsp+1160h+bstrString]; this
0x1800673c0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800673c5  nop
0x1800673c6  lea     rcx, [rsp+1160h+var_1110]; this
0x1800673cb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800673d0  test    ebx, ebx
0x1800673d2  jns     short loc_180067415
0x1800673d4  lea     rcx, WPP_GLOBAL_Control
0x1800673db  mov     rax, cs:WPP_GLOBAL_Control
0x1800673e2  cmp     rax, rcx
0x1800673e5  jz      loc_18006767D
0x1800673eb  test    byte ptr [rax+1Ch], 8
0x1800673ef  jz      loc_18006767D
0x1800673f5  cmp     byte ptr [rax+19h], 2
0x1800673f9  jb      loc_18006767D
0x1800673ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067404  mov     edx, 76h ; 'v'
0x180067409  lea     rcx, aIxmldomdocumen_0; "IXmlDOMDocument::setProperty NormalizeA"...
0x180067410  jmp     loc_180067161
0x180067415  lea     rcx, [rbp+1060h+pvarg]
0x180067419  call    ??4CComVariant@ATL@@QEAAAEAV01@H@Z; ATL::CComVariant::operator=(int)
0x18006741e  mov     rcx, [rsi]
0x180067421  movups  xmm0, xmmword ptr [rbp+1060h+pvarg]
0x180067425  movaps  [rsp+1160h+var_10F0], xmm0
0x18006742a  movsd   xmm1, qword ptr [rbp+1060h+pvarg+10h]
0x18006742f  movsd   [rbp+1060h+var_10E0], xmm1
0x180067434  mov     rax, [rcx]
0x180067437  lea     r8, [rsp+1160h+var_10F0]
0x18006743c  lea     rdx, aMaxxmlsize; "MaxXMLSize"
0x180067443  mov     rax, [rax+280h]
0x18006744a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006744f  mov     ebx, eax
0x180067451  test    eax, eax
0x180067453  jns     short loc_180067496
0x180067455  lea     rcx, WPP_GLOBAL_Control
0x18006745c  mov     rax, cs:WPP_GLOBAL_Control
0x180067463  cmp     rax, rcx
0x180067466  jz      loc_18006767D
0x18006746c  test    byte ptr [rax+1Ch], 8
0x180067470  jz      loc_18006767D
0x180067476  cmp     byte ptr [rax+19h], 2
0x18006747a  jb      loc_18006767D
0x180067480  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067485  mov     edx, 77h ; 'w'
0x18006748a  lea     rcx, aIxmldomdocumen_1; "IXmlDOMDocument::setProperty  MaxXMLSiz"...
0x180067491  jmp     loc_180067161
0x180067496  mov     [rsp+1160h+var_1120], 824h
0x18006749e  cmp     qword ptr [rdi+18h], 8
0x1800674a3  jb      short loc_1800674A8
0x1800674a5  mov     rdi, [rdi]
0x1800674a8  lea     r8, [rsp+1160h+var_1120]; unsigned int *
0x1800674ad  lea     rdx, [rbp+1060h+var_10A0]; unsigned __int16 *
0x1800674b1  mov     rcx, rdi; unsigned __int16 *
0x1800674b4  call    ?TSWFileURLFromPath@@YAJPEBGPEAGPEAK@Z; TSWFileURLFromPath(ushort const *,ushort *,ulong *)
0x1800674b9  mov     ebx, eax
0x1800674bb  test    eax, eax
0x1800674bd  jns     short loc_180067500
0x1800674bf  lea     rcx, WPP_GLOBAL_Control
0x1800674c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800674cd  cmp     rax, rcx
0x1800674d0  jz      loc_18006767D
0x1800674d6  test    byte ptr [rax+1Ch], 8
0x1800674da  jz      loc_18006767D
0x1800674e0  cmp     byte ptr [rax+19h], 2
0x1800674e4  jb      loc_18006767D
0x1800674ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800674ef  mov     edx, 78h ; 'x'
0x1800674f4  lea     rcx, aTswfileurlfrom; "TSWFileURLFromPath failed"
0x1800674fb  jmp     loc_180067161
0x180067500  mov     rdi, [rsi]
0x180067503  mov     rax, [rdi]
0x180067506  mov     rbx, [rax+1D0h]
0x18006750d  lea     rdx, [rbp+1060h+var_10A0]; unsigned __int16 *
0x180067511  lea     rcx, [rsp+1160h+bstrString]; this
0x180067516  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006751b  nop
0x18006751c  mov     rdx, rax; struct _bstr_t *
0x18006751f  lea     rcx, [rsp+1160h+var_1110]; this
0x180067524  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x180067529  nop
0x18006752a  movups  xmm0, xmmword ptr [rax]
0x18006752d  movaps  [rsp+1160h+var_10F0], xmm0
0x180067532  movsd   xmm1, qword ptr [rax+10h]
0x180067537  movsd   [rbp+1060h+var_10E0], xmm1
0x18006753c  lea     r8, [rsp+1160h+var_1130]
0x180067541  lea     rdx, [rsp+1160h+var_10F0]
0x180067546  mov     rcx, rdi
0x180067549  mov     rax, rbx
0x18006754c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067551  mov     ebx, eax
0x180067553  lea     rcx, [rsp+1160h+var_1110]; this
0x180067558  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006755d  nop
0x18006755e  lea     rcx, [rsp+1160h+bstrString]; this
0x180067563  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180067568  test    ebx, ebx
0x18006756a  jns     short loc_1800675AD
0x18006756c  lea     rcx, WPP_GLOBAL_Control
0x180067573  mov     rax, cs:WPP_GLOBAL_Control
0x18006757a  cmp     rax, rcx
0x18006757d  jz      loc_18006767D
0x180067583  test    byte ptr [rax+1Ch], 8
0x180067587  jz      loc_18006767D
0x18006758d  cmp     byte ptr [rax+19h], 2
0x180067591  jb      loc_18006767D
0x180067597  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006759c  mov     edx, 79h ; 'y'
0x1800675a1  lea     rcx, aIxmldomdocumen_8; "IXmlDOMDocument::LoadXML failed"
0x1800675a8  jmp     loc_180067161
0x1800675ad  cmp     [rsp+1160h+var_1130], r15w
0x1800675b3  jnz     loc_18006767A
0x1800675b9  mov     [rsp+1160h+var_1118], r15
0x1800675be  mov     [rsp+1160h+var_111C], r15d
0x1800675c3  mov     [rsp+1160h+bstrString], r15
0x1800675c8  mov     rcx, [rsi]
  ... truncated ...
```
