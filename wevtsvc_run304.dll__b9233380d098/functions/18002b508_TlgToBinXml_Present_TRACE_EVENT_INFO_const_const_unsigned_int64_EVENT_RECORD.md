# TlgToBinXml::Present(_TRACE_EVENT_INFO const * const,unsigned __int64,_EVENT_RECORD *)

- ea: `0x18002b508`
- end: `0x18002c53a`
- name: `?Present@TlgToBinXml@@QEAAKQEBU_TRACE_EVENT_INFO@@_KPEAU_EVENT_RECORD@@@Z`
- size: `4146`
- prototype: `unsigned int(TlgToBinXml *__hidden this, const struct _TRACE_EVENT_INFO *const, unsigned __int64, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001a5bc`

## callees

- `0x180014bd0`
- `0x180017b60`
- `0x18001c320`
- `0x180028c4c`
- `0x180029964`
- `0x180029e2c`
- `0x180029fb4`
- `0x18002ad30`
- `0x18002afa8`
- `0x18002b508`
- `0x18002c640`
- `0x18002d6dc`
- `0x18006a830`
- `0x18006a88c`
- `0x18006b27c`
- `0x18006d9e0`
- `0x18006df78`
- `0x18006fd30`
- `0x1800703cc`
- `0x180071b68`
- `0x180092008`
- `0x18009aee0`
- `0x1800ae3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18002b783`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18002b783`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002b731`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002b746`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002b75e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002b731`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002b746`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18002b75e`

## string_xrefs

- `0x18002b852`: `</Task><Channel>`
- `0x18002b818`: `</Opcode><Task>`
- `0x18002be57`: `<ComplexData Name="`
- `0x18002c115`: `</ComplexData>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TlgToBinXml::Present(
        TlgToBinXml *this,
        const struct _TRACE_EVENT_INFO *const a2,
        __int64 a3,
        struct _EVENT_RECORD *a4)
{
  char *v6; // r14
  __int64 v7; // rcx
  char *v8; // r15
  __int64 v9; // rax
  _WORD *v10; // rcx
  char *v11; // rsi
  _WORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // edi
  ULONG PropertyCount; // r12d
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r9
  ULONG *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  void *v25; // r15
  __int64 v26; // r8
  int v27; // r13d
  char v28; // r12
  TlgToBinXml *v29; // r15
  __int64 ItemInfo; // rax
  __int128 v31; // xmm6
  __int64 v32; // rcx
  __int64 RawItemInfo; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned int v37; // r15d
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  _QWORD *v43; // rcx
  __int64 v44; // rdx
  _QWORD *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  __int128 v48; // xmm6
  int v49; // r12d
  __int64 v50; // rax
  void *v51; // r12
  __int64 v52; // r8
  __int64 v53; // rax
  _QWORD *v54; // rcx
  __int64 v55; // rdx
  unsigned int v56; // esi
  unsigned int v57; // r12d
  char v58; // al
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rax
  bool v62[8]; // [rsp+28h] [rbp-E0h] BYREF
  TlgToBinXml *v63; // [rsp+30h] [rbp-D8h]
  struct _EVENT_RECORD *v64[2]; // [rsp+38h] [rbp-D0h] BYREF
  struct _EVENT_RECORD *v65; // [rsp+48h] [rbp-C0h] BYREF
  signed __int64 v66; // [rsp+50h] [rbp-B8h]
  void *v67; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v68[16]; // [rsp+68h] [rbp-A0h] BYREF
  void *v69[2]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v70[16]; // [rsp+88h] [rbp-80h] BYREF
  void *v71; // [rsp+98h] [rbp-70h]
  __int128 v72; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-58h]
  __int128 v74; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v75; // [rsp+C8h] [rbp-40h]
  __int64 v76; // [rsp+D8h] [rbp-30h]
  _QWORD v77[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v78[2]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v79[2]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v80[3]; // [rsp+130h] [rbp+28h] BYREF
  _WORD v81[12]; // [rsp+160h] [rbp+58h] BYREF
  _WORD v82[12]; // [rsp+178h] [rbp+70h] BYREF
  _WORD v83[12]; // [rsp+190h] [rbp+88h] BYREF

  v64[0] = a4;
  v63 = this;
  v62[4] = (a4->EventHeader.Flags & 0x20) != 0;
  v6 = (char *)this + 8;
  EtwEnumerator::PreviewEvent((char *)this + 8, a4);
  v7 = *((_QWORD *)this + 54);
  if ( v7 != *((_QWORD *)this + 55) )
    *((_QWORD *)this + 55) = v7;
  v8 = (char *)this + 456;
  v9 = *((_QWORD *)this + 57);
  if ( v9 != *((_QWORD *)this + 58) )
    *((_QWORD *)this + 58) = v9;
  v71 = (char *)this + 400;
  v10 = (_WORD *)*((_QWORD *)this + 50);
  *((_QWORD *)this + 51) = v10;
  *v10 = 0;
  v11 = (char *)this + 368;
  v12 = (_WORD *)*((_QWORD *)this + 46);
  *((_QWORD *)this + 47) = v12;
  *v12 = 0;
  v14 = 14;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                           (char *)this + 368,
                           512) )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v14;
    }
    v46 = 10;
LABEL_122:
    WPP_SF_d(v45[2], v46, &WPP_5cb89b9b5b123b924a78b049cb6271fe_Traceguids, v14);
    return v14;
  }
  PropertyCount = a2->PropertyCount;
  *(_DWORD *)v62 = PropertyCount;
  v16 = PropertyCount;
  v17 = 0;
  if ( PropertyCount )
  {
    while ( (a2->EventPropertyInfoArray[(unsigned int)v17].Flags & 1) == 0 )
    {
      if ( (unsigned __int8)IsCountedType(
                              a2->EventPropertyInfoArray[(unsigned int)v17].nonStructType.InType,
                              v13,
                              v17,
                              v16,
                              *(_QWORD *)v62) )
      {
        ++PropertyCount;
LABEL_10:
        *(_DWORD *)v62 = PropertyCount;
      }
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= (unsigned int)v16 )
        goto LABEL_12;
    }
    --PropertyCount;
    goto LABEL_10;
  }
LABEL_12:
  std::vector<unsigned long>::reserve((char *)v63 + 432, PropertyCount, v17, v16);
  std::vector<unsigned long>::reserve(v8, PropertyCount + 1LL, v18, v19);
  v20 = (ULONG *)*((_QWORD *)this + 58);
  if ( v20 == *((ULONG **)this + 59) )
  {
    std::vector<unsigned long>::_Emplace_reallocate<unsigned long>(v8, v20, v62);
  }
  else
  {
    *v20 = PropertyCount;
    *((_QWORD *)this + 58) += 4LL;
  }
  if ( !EtwEnumerator::StartEventWithTraceEventInfo((EtwEnumerator *)v6, v64[0], a2) )
  {
    v14 = *((_DWORD *)v6 + 16);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v14;
    }
    v46 = 11;
    goto LABEL_122;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v69);
  *(_OWORD *)v64 = 0;
  if ( !EtwEnumerator::FormatCurrentEventName((EtwEnumerator *)v6, (struct EtwStringViewZ *)v64) )
  {
    v14 = *((_DWORD *)v63 + 18);
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_225;
    }
    v55 = 12;
    goto LABEL_137;
  }
  v65 = v64[0];
  v66 = LODWORD(v64[1]);
  if ( !(unsigned __int8)AppendEscapedXml(v69, &v65, 0) )
  {
    v14 = 14;
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_225;
    }
    v55 = 13;
LABEL_137:
    WPP_SF_d(v54[2], v55, &WPP_5cb89b9b5b123b924a78b049cb6271fe_Traceguids, v14);
LABEL_225:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v69);
    return v14;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v67);
  *(_OWORD *)v64 = 0;
  if ( !EtwEnumerator::FormatCurrentProviderName((EtwEnumerator *)v6, (struct EtwStringViewZ *)v64) )
  {
    v56 = *((_DWORD *)v63 + 18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_5cb89b9b5b123b924a78b049cb6271fe_Traceguids, v56);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v67);
    v14 = v56;
    goto LABEL_225;
  }
  v65 = v64[0];
  v66 = LODWORD(v64[1]);
  if ( !(unsigned __int8)AppendEscapedXml(&v67, &v65, 0) )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = 15;
      goto LABEL_223;
    }
    goto LABEL_224;
  }
  _o__ultow_s(a2->EventDescriptor.Level, v81, 11);
  _o__ultow_s(a2->EventDescriptor.Opcode, v82, 11);
  _o__ultow_s(a2->EventDescriptor.Channel, v83, 11);
  memset(v80, 0, 42);
  _o__ui64tow_s(a2->EventDescriptor.Keyword, v80, 21, 10);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  v21 = -1;
  do
    ++v21;
  while ( v81[v21] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  v22 = -1;
  do
    ++v22;
  while ( v82[v22] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  v23 = -1;
  do
    ++v23;
  while ( v83[v23] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
    goto LABEL_85;
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)v80 + v24) );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
  {
LABEL_85:
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = 16;
LABEL_229:
      WPP_SF_d(v43[2], v44, &WPP_5cb89b9b5b123b924a78b049cb6271fe_Traceguids, 14);
    }
    goto LABEL_86;
  }
  v25 = v71;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v71)
    || (v65 = (struct _EVENT_RECORD *)v69[0],
        v66 = ((char *)v69[1] - (char *)v69[0]) >> 1,
        LOBYTE(v26) = 1,
        !(unsigned __int8)AppendEscapedXml(v25, &v65, v26))
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v25) )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = 17;
LABEL_223:
      WPP_SF_d(v40[2], v41, &WPP_5cb89b9b5b123b924a78b049cb6271fe_Traceguids, 14);
    }
LABEL_224:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v67);
    goto LABEL_225;
  }
  *(_DWORD *)v62 = 0;
  v27 = 0;
LABEL_46:
  v28 = 1;
LABEL_47:
  v29 = v63;
  while ( EtwEnumerator::MoveNext((EtwEnumerator *)v6) )
  {
    switch ( *((_BYTE *)v29 + 66) )
    {
      case 4:
        ItemInfo = EtwEnumerator::GetItemInfo(v6, v79);
        v31 = *(_OWORD *)ItemInfo;
        v74 = *(_OWORD *)ItemInfo;
        v75 = *(_OWORD *)(ItemInfo + 16);
        v76 = *(_QWORD *)(ItemInfo + 32);
        RawItemInfo = EtwEnumerator::GetRawItemInfo(v32, v79);
        v72 = *(_OWORD *)RawItemInfo;
        v73 = *(_QWORD *)(RawItemInfo + 16);
        if ( v28 )
        {
          v28 = 0;
        }
        else
        {
          v28 = 0;
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   v11,
                                   44) )
          {
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v41 = 18;
              goto LABEL_223;
            }
            goto LABEL_224;
          }
          if ( !v27
            && (!(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
             || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                    v11,
                                    4LL * *(unsigned int *)v62)) )
          {
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v41 = 19;
              goto LABEL_223;
            }
            goto LABEL_224;
          }
        }
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)(v31 + 2 * v34) );
        v77[0] = v31;
        v77[1] = v34;
        if ( !(unsigned __int8)AppendEscapedXml(v11, v77, 0)
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v44 = 20;
            goto LABEL_229;
          }
          goto LABEL_86;
        }
        if ( v6[58] != 4 )
          __int2c();
        *((_DWORD *)v6 + 58) = 0;
        EtwEnumerator::AddCurrentValue(v6, v6 + 224);
        if ( *((_DWORD *)v6 + 16) )
        {
          v79[0] = 0;
          v35 = 0;
          LODWORD(v36) = 0;
        }
        else
        {
          v35 = *((_QWORD *)v6 + 28);
          v36 = *((unsigned int *)v6 + 58);
          if ( (unsigned int)v36 < *((_DWORD *)v6 + 59) )
            *(_WORD *)(v35 + 2 * v36) = -3;
          HIDWORD(v79[0]) = 0;
        }
        v78[0] = v35;
        v78[1] = (unsigned int)v36;
        if ( !(unsigned __int8)AppendEscapedXml(v11, v78, 0) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 21;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        v29 = v63;
        if ( !v27 )
        {
          v37 = TlgToBinXml::BuildSinglePropertyEntry(
                  v63,
                  (struct EtwItemInfo *)&v74,
                  (struct EtwRawItemInfo *)&v72,
                  v62[4]);
          if ( !v37 )
            goto LABEL_47;
          v38 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v39 = 22;
            goto LABEL_209;
          }
LABEL_210:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v67);
          v14 = v37;
          goto LABEL_225;
        }
        break;
      case 5:
        v59 = EtwEnumerator::GetItemInfo(v6, v79);
        v74 = *(_OWORD *)v59;
        v75 = *(_OWORD *)(v59 + 16);
        v76 = *(_QWORD *)(v59 + 32);
        v61 = EtwEnumerator::GetRawItemInfo(v60, v79);
        v72 = *(_OWORD *)v61;
        v73 = *(_QWORD *)(v61 + 16);
        if ( !v28 )
        {
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   v11,
                                   44) )
          {
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v41 = 23;
              goto LABEL_223;
            }
            goto LABEL_224;
          }
          if ( !v27
            && (!(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
             || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                    v11,
                                    4LL * *(unsigned int *)v62)) )
          {
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v41 = 24;
              goto LABEL_223;
            }
            goto LABEL_224;
          }
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 v11,
                                 91) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 25;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        v37 = TlgToBinXml::BuildSinglePropertyEntry(
                v29,
                (struct EtwItemInfo *)&v74,
                (struct EtwRawItemInfo *)&v72,
                v62[4]);
        if ( !v37 )
        {
          ++v27;
          goto LABEL_46;
        }
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_210;
        }
        v39 = 26;
LABEL_209:
        WPP_SF_d(v38[2], v39, &WPP_5cb89b9b5b123b924a78b049cb6271fe_Traceguids, v37);
        goto LABEL_210;
      case 6:
        v47 = EtwEnumerator::GetItemInfo(v6, v79);
        v48 = *(_OWORD *)v47;
        v75 = *(_OWORD *)(v47 + 16);
        v76 = *(_QWORD *)(v47 + 32);
        if ( v28 )
          goto LABEL_107;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 v11,
                                 44) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 28;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        if ( v27 )
        {
LABEL_107:
          v49 = *(_DWORD *)v62;
        }
        else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
               || (v49 = *(_DWORD *)v62,
                   !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                       v11,
                                       4LL * *(unsigned int *)v62)) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 29;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        v50 = -1;
        do
          ++v50;
        while ( *(_WORD *)(v48 + 2 * v50) );
        v65 = (struct _EVENT_RECORD *)v48;
        v66 = v50;
        if ( !(unsigned __int8)AppendEscapedXml(v11, &v65, 0) )
          goto LABEL_118;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
          goto LABEL_118;
        *(_DWORD *)v62 = v49 + 1;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 v11,
                                 4LL * (unsigned int)(v49 + 1)) )
          goto LABEL_118;
        v51 = v71;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v71) )
          goto LABEL_118;
        v53 = -1;
        do
          ++v53;
        while ( *(_WORD *)(v48 + 2 * v53) );
        v64[0] = (struct _EVENT_RECORD *)v48;
        v64[1] = (struct _EVENT_RECORD *)v53;
        LOBYTE(v52) = 1;
        if ( !(unsigned __int8)AppendEscapedXml(v51, v64, v52)
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v51) )
        {
LABEL_118:
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 30;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        goto LABEL_46;
      case 7:
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 v11,
                                 93) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 27;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        --v27;
        v28 = 0;
        break;
      case 8:
        v57 = --*(_DWORD *)v62;
        if ( v27 )
        {
          v28 = 0;
        }
        else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11)
               || (v58 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v11,
                           4LL * v57),
                   v28 = 0,
                   !v58) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 31;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 v11,
                                 125)
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append((char *)v29 + 400) )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = 32;
            goto LABEL_223;
          }
          goto LABEL_224;
        }
        break;
    }
  }
  v37 = *((_DWORD *)v29 + 18);
  if ( v37 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_210;
    }
    v39 = 33;
    goto LABEL_209;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v71)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v11) )
  {
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = 34;
      goto LABEL_229;
    }
LABEL_86:
    if ( v67 != v68 )
      operator delete(v67);
    if ( v69[0] != v70 )
      operator delete(v69[0]);
    return v14;
  }
  *(_QWORD *)v6 = 0;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *((_WORD *)v6 + 29) = 0;
  *((_DWORD *)v6 + 16) = 0;
  if ( v67 != v68 )
    operator delete(v67);
  if ( v69[0] != v70 )
    operator delete(v69[0]);
  return 0;
}

```

## disassembly

```asm
0x18002b508  mov     rax, rsp
0x18002b50b  mov     [rax+18h], rbx
0x18002b50f  push    rbp
0x18002b510  push    rsi
0x18002b511  push    rdi
0x18002b512  push    r12
0x18002b514  push    r13
0x18002b516  push    r14
0x18002b518  push    r15
0x18002b51a  lea     rbp, [rax-0F8h]
0x18002b521  sub     rsp, 1C0h
0x18002b528  movaps  xmmword ptr [rax-48h], xmm6
0x18002b52c  mov     rax, cs:__security_cookie
0x18002b533  xor     rax, rsp
0x18002b536  mov     [rbp+0F0h+var_50], rax
0x18002b53d  mov     [rsp+1F0h+var_1C8+8], r9
0x18002b542  mov     r13, rdx
0x18002b545  mov     rbx, rcx
0x18002b548  mov     [rsp+1F0h+var_1C8], rcx
0x18002b54d  mov     cl, [r9+4]
0x18002b551  shr     cl, 5
0x18002b554  and     cl, 1
0x18002b557  mov     [rsp+1F0h+var_1D0+4], cl
0x18002b55b  lea     r14, [rbx+8]
0x18002b55f  mov     rdx, r9
0x18002b562  mov     rcx, r14
0x18002b565  call    ?PreviewEvent@EtwEnumerator@@QEAA?AW4EtwEventCategory@@PEBU_EVENT_RECORD@@@Z; EtwEnumerator::PreviewEvent(_EVENT_RECORD const *)
0x18002b56a  lea     rax, [rbx+1B0h]
0x18002b571  mov     rcx, [rax]
0x18002b574  cmp     rcx, [rax+8]
0x18002b578  jnz     loc_18002BEEA
0x18002b57e  lea     r15, [rbx+1C8h]
0x18002b585  mov     rax, [r15]
0x18002b588  cmp     rax, [r15+8]
0x18002b58c  jnz     loc_18002BEF3
0x18002b592  lea     rax, [rbx+190h]
0x18002b599  mov     [rbp+0F0h+var_160], rax
0x18002b59d  mov     rcx, [rax]
0x18002b5a0  mov     [rax+8], rcx
0x18002b5a4  xor     eax, eax
0x18002b5a6  mov     [rcx], ax
0x18002b5a9  lea     rsi, [rbx+170h]
0x18002b5b0  mov     rcx, [rsi]
0x18002b5b3  mov     [rsi+8], rcx
0x18002b5b7  xor     ebx, ebx
0x18002b5b9  mov     [rcx], bx
0x18002b5bc  mov     edx, 200h
0x18002b5c1  mov     rcx, rsi
0x18002b5c4  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18002b5c9  lea     edi, [rbx+0Eh]
0x18002b5cc  test    al, al
0x18002b5ce  jz      loc_18002BD36
0x18002b5d4  mov     r12d, [r13+64h]
0x18002b5d8  mov     dword ptr [rsp+1F0h+var_1D0], r12d
0x18002b5dd  mov     r9d, r12d
0x18002b5e0  mov     r8d, ebx
0x18002b5e3  test    r12d, r12d
0x18002b5e6  jz      short loc_18002B61A
0x18002b5e8  mov     eax, r8d
0x18002b5eb  lea     rcx, [rax+rax*2]
0x18002b5ef  test    byte ptr [r13+rcx*8+70h], 1
0x18002b5f5  jnz     loc_18002BF19
0x18002b5fb  movzx   ecx, word ptr [r13+rcx*8+78h]
0x18002b601  call    IsCountedType
0x18002b606  test    al, al
0x18002b608  jz      short loc_18002B612
0x18002b60a  inc     r12d
0x18002b60d  mov     dword ptr [rsp+1F0h+var_1D0], r12d
0x18002b612  inc     r8d
0x18002b615  cmp     r8d, r9d
0x18002b618  jb      short loc_18002B5E8
0x18002b61a  mov     ebx, r12d
0x18002b61d  mov     edx, r12d
0x18002b620  mov     rcx, [rsp+1F0h+var_1C8]
0x18002b625  add     rcx, 1B0h
0x18002b62c  call    ?reserve@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::reserve(unsigned __int64)
0x18002b631  lea     rdx, [rbx+1]
0x18002b635  mov     rcx, r15
0x18002b638  call    ?reserve@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::reserve(unsigned __int64)
0x18002b63d  mov     rdx, [r15+8]
0x18002b641  cmp     rdx, [r15+10h]
0x18002b645  jz      loc_18002BF21
0x18002b64b  mov     [rdx], r12d
0x18002b64e  add     qword ptr [r15+8], 4
0x18002b653  mov     r8, r13; struct _TRACE_EVENT_INFO *
0x18002b656  mov     rdx, [rsp+1F0h+var_1C8+8]; struct _EVENT_RECORD *
0x18002b65b  mov     rcx, r14; this
0x18002b65e  call    ?StartEventWithTraceEventInfo@EtwEnumerator@@QEAA_NPEBU_EVENT_RECORD@@PEBU_TRACE_EVENT_INFO@@@Z; EtwEnumerator::StartEventWithTraceEventInfo(_EVENT_RECORD const *,_TRACE_EVENT_INFO const *)
0x18002b663  xor     r12d, r12d
0x18002b666  test    al, al
0x18002b668  jz      loc_18002BF33
0x18002b66e  lea     rcx, [rsp+1F0h+var_180]; void *
0x18002b673  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002b678  nop
0x18002b679  xorps   xmm0, xmm0
0x18002b67c  movups  xmmword ptr [rsp+1F0h+var_1C8+8], xmm0
0x18002b681  lea     rdx, [rsp+1F0h+var_1C8+8]; struct EtwStringViewZ *
0x18002b686  mov     rcx, r14; this
0x18002b689  call    ?FormatCurrentEventName@EtwEnumerator@@QEAA_NPEAUEtwStringViewZ@@@Z; EtwEnumerator::FormatCurrentEventName(EtwStringViewZ *)
0x18002b68e  test    al, al
0x18002b690  jz      loc_18002BF68
0x18002b696  mov     rax, [rsp+1F0h+var_1C8+8]
0x18002b69b  mov     [rsp+1F0h+var_1B0], rax
0x18002b6a0  mov     eax, dword ptr [rsp+1F0h+var_1B8]
0x18002b6a4  mov     [rsp+1F0h+var_1A8], rax
0x18002b6a9  xor     r8d, r8d
0x18002b6ac  lea     rdx, [rsp+1F0h+var_1B0]
0x18002b6b1  lea     rcx, [rsp+1F0h+var_180]
0x18002b6b6  call    AppendEscapedXml
0x18002b6bb  test    al, al
0x18002b6bd  jz      loc_18002BFA4
0x18002b6c3  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x18002b6c8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002b6cd  nop
0x18002b6ce  xorps   xmm0, xmm0
0x18002b6d1  movups  xmmword ptr [rsp+1F0h+var_1C8+8], xmm0
0x18002b6d6  lea     rdx, [rsp+1F0h+var_1C8+8]; struct EtwStringViewZ *
0x18002b6db  mov     rcx, r14; this
0x18002b6de  call    ?FormatCurrentProviderName@EtwEnumerator@@QEAA_NPEAUEtwStringViewZ@@@Z; EtwEnumerator::FormatCurrentProviderName(EtwStringViewZ *)
0x18002b6e3  test    al, al
0x18002b6e5  jz      loc_18002BFF1
0x18002b6eb  mov     rax, [rsp+1F0h+var_1C8+8]
0x18002b6f0  mov     [rsp+1F0h+var_1B0], rax
0x18002b6f5  mov     eax, dword ptr [rsp+1F0h+var_1B8]
0x18002b6f9  mov     [rsp+1F0h+var_1A8], rax
0x18002b6fe  xor     r8d, r8d
0x18002b701  lea     rdx, [rsp+1F0h+var_1B0]
0x18002b706  lea     rcx, [rsp+1F0h+var_1A0]
0x18002b70b  call    AppendEscapedXml
0x18002b710  test    al, al
0x18002b712  jz      loc_18002C043
0x18002b718  movzx   ecx, byte ptr [r13+24h]
0x18002b71d  lea     ebx, [r12+0Ah]
0x18002b722  mov     r9d, ebx
0x18002b725  lea     r15d, [r12+0Bh]
0x18002b72a  mov     r8d, r15d
0x18002b72d  lea     rdx, [rbp+0F0h+var_98]
0x18002b731  call    cs:__imp__o__ultow_s
0x18002b737  movzx   ecx, byte ptr [r13+25h]
0x18002b73c  mov     r9d, ebx
0x18002b73f  mov     r8d, r15d
0x18002b742  lea     rdx, [rbp+0F0h+var_80]
0x18002b746  call    cs:__imp__o__ultow_s
0x18002b74c  movzx   ecx, byte ptr [r13+23h]
0x18002b751  mov     r9d, ebx
0x18002b754  mov     r8d, r15d
0x18002b757  lea     rdx, [rbp+0F0h+var_68]
0x18002b75e  call    cs:__imp__o__ultow_s
0x18002b764  xorps   xmm0, xmm0
0x18002b767  movups  [rbp+0F0h+var_C8], xmm0
0x18002b76b  movups  xmmword ptr [rbp+0F0h+var_B8], xmm0
0x18002b76f  movups  xmmword ptr [rbp+0F0h+var_B8+0Ah], xmm0
0x18002b773  mov     r9d, ebx
0x18002b776  lea     r8d, [r12+15h]
0x18002b77b  lea     rdx, [rbp+0F0h+var_C8]
0x18002b77f  mov     rcx, [r13+28h]
0x18002b783  call    cs:__imp__o__ui64tow_s
0x18002b789  lea     r8d, [r12+24h]
0x18002b78e  lea     rdx, aRenderinginfoC; "<RenderingInfo Culture=\"zxx\"><Level>"
0x18002b795  mov     rcx, rsi
0x18002b798  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b79d  lea     r15d, [r12+10h]
0x18002b7a2  test    al, al
0x18002b7a4  jz      loc_18002BC84
0x18002b7aa  lea     rax, [rbp+0F0h+var_98]
0x18002b7ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b7b2  mov     r8, rbx
0x18002b7b5  inc     r8
0x18002b7b8  cmp     [rax+r8*2], r12w
0x18002b7bd  jnz     short loc_18002B7B5
0x18002b7bf  lea     rdx, [rbp+0F0h+var_98]
0x18002b7c3  mov     rcx, rsi
0x18002b7c6  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b7cb  test    al, al
0x18002b7cd  jz      loc_18002BC84
0x18002b7d3  mov     r8, r15
0x18002b7d6  lea     rdx, aLevelOpcode; "</Level><Opcode>"
0x18002b7dd  mov     rcx, rsi
0x18002b7e0  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b7e5  test    al, al
0x18002b7e7  jz      loc_18002BC84
0x18002b7ed  lea     rax, [rbp+0F0h+var_80]
0x18002b7f1  mov     r8, rbx
0x18002b7f4  inc     r8
0x18002b7f7  cmp     [rax+r8*2], r12w
0x18002b7fc  jnz     short loc_18002B7F4
0x18002b7fe  lea     rdx, [rbp+0F0h+var_80]
0x18002b802  mov     rcx, rsi
0x18002b805  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b80a  test    al, al
0x18002b80c  jz      loc_18002BC84
0x18002b812  mov     r8d, 0Fh
0x18002b818  lea     rdx, aOpcodeTask; "</Opcode><Task>"
0x18002b81f  mov     rcx, rsi
0x18002b822  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b827  test    al, al
0x18002b829  jz      loc_18002BC84
0x18002b82f  mov     r8, [rsp+1F0h+var_178]
0x18002b834  mov     rdx, [rsp+1F0h+var_180]
0x18002b839  sub     r8, rdx
0x18002b83c  sar     r8, 1
0x18002b83f  mov     rcx, rsi
0x18002b842  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b847  test    al, al
0x18002b849  jz      loc_18002BC84
0x18002b84f  mov     r8, r15
0x18002b852  lea     rdx, aTaskChannel; "</Task><Channel>"
0x18002b859  mov     rcx, rsi
0x18002b85c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b861  test    al, al
0x18002b863  jz      loc_18002BC84
0x18002b869  lea     rax, [rbp+0F0h+var_68]
0x18002b870  mov     r8, rbx
0x18002b873  inc     r8
0x18002b876  cmp     [rax+r8*2], r12w
0x18002b87b  jnz     short loc_18002B873
0x18002b87d  lea     rdx, [rbp+0F0h+var_68]
0x18002b884  mov     rcx, rsi
0x18002b887  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b88c  test    al, al
0x18002b88e  jz      loc_18002BC84
0x18002b894  mov     r8d, 14h
0x18002b89a  lea     rdx, aChannelProvide; "</Channel><Provider>"
0x18002b8a1  mov     rcx, rsi
0x18002b8a4  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b8a9  test    al, al
0x18002b8ab  jz      loc_18002BC84
0x18002b8b1  mov     r8, qword ptr [rsp+1F0h+var_198]
0x18002b8b6  mov     rdx, [rsp+1F0h+var_1A0]
0x18002b8bb  sub     r8, rdx
0x18002b8be  sar     r8, 1
0x18002b8c1  mov     rcx, rsi
0x18002b8c4  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b8c9  test    al, al
0x18002b8cb  jz      loc_18002BC84
0x18002b8d1  mov     r13d, 1Eh
0x18002b8d7  mov     r8d, r13d
0x18002b8da  lea     rdx, aProviderKeywor; "</Provider><Keywords><Keyword>"
0x18002b8e1  mov     rcx, rsi
0x18002b8e4  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b8e9  test    al, al
0x18002b8eb  jz      loc_18002BC84
0x18002b8f1  lea     rax, [rbp+0F0h+var_C8]
0x18002b8f5  mov     r8, rbx
0x18002b8f8  inc     r8
0x18002b8fb  cmp     [rax+r8*2], r12w
0x18002b900  jnz     short loc_18002B8F8
0x18002b902  lea     rdx, [rbp+0F0h+var_C8]
0x18002b906  mov     rcx, rsi
0x18002b909  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b90e  test    al, al
0x18002b910  jz      loc_18002BC84
0x18002b916  mov     r8, r13
0x18002b919  lea     rdx, aKeywordKeyword; "</Keyword></Keywords><Message>"
0x18002b920  mov     rcx, rsi
0x18002b923  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b928  test    al, al
0x18002b92a  jz      loc_18002BC84
0x18002b930  mov     r8, [rsp+1F0h+var_178]
0x18002b935  mov     rdx, [rsp+1F0h+var_180]
0x18002b93a  sub     r8, rdx
0x18002b93d  sar     r8, 1
0x18002b940  mov     rcx, rsi
0x18002b943  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b948  test    al, al
0x18002b94a  jz      loc_18002BC84
0x18002b950  mov     r8d, 4
0x18002b956  lea     rdx, asc_1800EADE0; "\r\n\r\n"
0x18002b95d  mov     rcx, rsi
0x18002b960  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b965  test    al, al
0x18002b967  jz      loc_18002BC84
0x18002b96d  mov     r13d, 11h
0x18002b973  mov     r8d, r13d
0x18002b976  lea     rdx, aEventdataName; "<EventData Name=\""
0x18002b97d  mov     r15, [rbp+0F0h+var_160]
0x18002b981  mov     rcx, r15
0x18002b984  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b989  lea     ebx, [r13-0Fh]
0x18002b98d  test    al, al
0x18002b98f  jz      loc_18002C4B7
0x18002b995  mov     rax, [rsp+1F0h+var_180]
0x18002b99a  mov     [rsp+1F0h+var_1B0], rax
0x18002b99f  mov     rcx, [rsp+1F0h+var_178]
0x18002b9a4  sub     rcx, rax
0x18002b9a7  sar     rcx, 1
0x18002b9aa  mov     [rsp+1F0h+var_1A8], rcx
0x18002b9af  mov     r8b, 1
0x18002b9b2  lea     rdx, [rsp+1F0h+var_1B0]
0x18002b9b7  mov     rcx, r15
0x18002b9ba  call    AppendEscapedXml
0x18002b9bf  test    al, al
0x18002b9c1  jz      loc_18002C4B7
0x18002b9c7  mov     r8d, ebx
0x18002b9ca  lea     rdx, asc_1800EADB0; "\">"
0x18002b9d1  mov     rcx, r15
0x18002b9d4  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002b9d9  test    al, al
0x18002b9db  jz      loc_18002C4B7
0x18002b9e1  xor     eax, eax
  ... truncated ...
```
