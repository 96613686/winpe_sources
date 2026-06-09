# EventRendering::MessageRender(PublisherMetadataObject *,Session *,Event const &,ulong,_EVT_VARIANT *,ulong,ulong,wchar_t *,ulong &)

- ea: `0x180007fb8`
- end: `0x180008911`
- name: `?MessageRender@EventRendering@@YAXPEAVPublisherMetadataObject@@PEAVSession@@AEBVEvent@@KPEAU_EVT_VARIANT@@KKPEA_WAEAK@Z`
- size: `2393`
- prototype: `void __fastcall(EventRendering *this, struct PublisherMetadataObject *, struct BinXmlTemplateTable **, const struct Event *, struct _EVT_VARIANT *, struct _EVT_VARIANT *, unsigned int, _WORD *, wchar_t *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180006410`

## callees

- `0x180001568`
- `0x180001840`
- `0x180001f34`
- `0x180003dc0`
- `0x180006aec`
- `0x180007fb8`
- `0x18000a0dc`
- `0x18000a100`
- `0x18000a4b4`
- `0x18000a724`
- `0x18000a978`
- `0x18000b638`
- `0x18000b95c`
- `0x18000c404`
- `0x18000decc`
- `0x18001b3d4`
- `0x18001bda4`
- `0x18001ce98`
- `0x18001fdb4`
- `0x1800231d0`
- `0x180023504`
- `0x180023548`
- `0x180024a50`
- `0x180038fa4`
- `0x180038fbc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800087cc`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800087cc`

## pseudocode

```c
void __fastcall EventRendering::MessageRender(
        EventRendering *this,
        struct PublisherMetadataObject *a2,
        struct BinXmlTemplateTable **a3,
        const struct Event *a4,
        struct _EVT_VARIANT *a5,
        struct _EVT_VARIANT *a6,
        unsigned int a7,
        _WORD *a8,
        wchar_t *a9)
{
  LCID ThreadLocale; // r12d
  unsigned int v12; // r15d
  __int64 v13; // r8
  LastErrInfo *v14; // rcx
  void *v15; // rax
  __int64 v16; // r9
  __int64 v17; // rbx
  LastErrInfo *v18; // rcx
  LastErrInfo *v19; // rcx
  unsigned int v20; // edi
  LastErrInfo *v21; // rcx
  __int64 v22; // r8
  unsigned __int64 v23; // rdi
  __int64 v24; // r9
  unsigned int v25; // r8d
  LastErrInfo *v26; // rcx
  unsigned __int64 v27; // r9
  unsigned int v28; // r10d
  LastErrInfo *v29; // rcx
  char *v30; // rax
  char *v31; // rcx
  unsigned int v32; // esi
  char *v33; // r13
  __int64 v34; // rax
  __int64 v35; // r8
  unsigned int v36; // edi
  __int64 v37; // rax
  unsigned int *v38; // [rsp+20h] [rbp-E0h]
  _DWORD v39[2]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v40; // [rsp+4Ch] [rbp-B4h]
  void *v41[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v42; // [rsp+60h] [rbp-A0h] BYREF
  void *v43[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-80h] BYREF
  struct PublisherMetadataObject *v45; // [rsp+90h] [rbp-70h]
  __int128 pExceptionObject; // [rsp+98h] [rbp-68h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h]
  int v48; // [rsp+B0h] [rbp-50h]
  int v49; // [rsp+B4h] [rbp-4Ch]
  int v50; // [rsp+B8h] [rbp-48h]
  struct Session *v51; // [rsp+C0h] [rbp-40h]
  _BYTE v52[24]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v53[3]; // [rsp+E0h] [rbp-20h] BYREF
  void *v54[2]; // [rsp+F8h] [rbp-8h] BYREF
  char v55; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v56[3]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v57; // [rsp+130h] [rbp+30h]
  _BYTE v58[192]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v59; // [rsp+200h] [rbp+100h] BYREF
  int v60; // [rsp+208h] [rbp+108h]
  __int128 v61; // [rsp+210h] [rbp+110h] BYREF
  struct _EVT_VARIANT *v62[2]; // [rsp+220h] [rbp+120h] BYREF
  wchar_t v63; // [rsp+230h] [rbp+130h]
  void *Src[2]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v65; // [rsp+248h] [rbp+148h] BYREF
  unsigned int v66; // [rsp+250h] [rbp+150h]
  int v67; // [rsp+254h] [rbp+154h]
  int v68; // [rsp+258h] [rbp+158h]

  v40 = (unsigned int)a4;
  v51 = (struct Session *)a3;
  v45 = a2;
  v62[0] = a5;
  v39[0] = (_DWORD)a6;
  v59 = 0;
  v60 = 0;
  if ( this )
    ThreadLocale = *((_DWORD *)this + 16);
  else
    ThreadLocale = GetThreadLocale();
  *(_DWORD *)a9 = 0;
  if ( a8 && a7 )
    *a8 = 0;
  v12 = 2 * a7;
  if ( 2 * (unsigned __int64)a7 <= 0xFFFFFFFF )
  {
    v56[0] = 0;
    v57 = 0;
    v56[1] = a3[7];
    v56[2] = *((unsigned int *)a3 + 17);
    BinXmlReader::BinXmlReader((BinXmlReader *)v58, (struct BinXmlReaderData *)v56, (unsigned int)a3, 0, 0, a3[5]);
    v39[1] = 0;
    v61 = 0;
    GetEventDescriptor((BinXmlReader *)v58);
    if ( v39[0] != 9 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v43);
      if ( !(unsigned __int8)GetEmbededMsg((BinXmlReader *)v58, ThreadLocale, (__int64)v43) )
      {
        if ( v43[0] != v44 )
          operator delete(v43[0]);
        SubstitutionValues::SubstitutionValues((SubstitutionValues *)v52, (const struct Event *)a3, v40, v62[0]);
        v62[0] = (struct _EVT_VARIANT *)(-1431655765 * (unsigned int)((__int64)(v53[1] - v53[0]) >> 3));
        v62[1] = (struct _EVT_VARIANT *)v53[0];
        GetRenderedMessageFromService(
          (unsigned int)Src,
          (_DWORD)this,
          (_DWORD)v45,
          (unsigned int)&v61,
          -1,
          (__int64)v62,
          v39[0],
          (__int64)&v59);
        v15 = Src[1];
        if ( Src[1] )
        {
          v16 = (unsigned int)(LODWORD(Src[1]) + 1);
          *(_DWORD *)a9 = v16;
          if ( (unsigned int)v16 <= a7 )
          {
            v17 = (__int64)v15;
            memcpy_0(a8, Src[0], 2LL * (_QWORD)v15);
            a8[v17] = 0;
            LastErrInfo::Reset(v18);
LABEL_18:
            utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v65);
            utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v53);
            utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(v52);
LABEL_19:
            BinXmlReader::~BinXmlReader((BinXmlReader *)v58);
            return;
          }
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v16, a7);
          }
          LODWORD(v59) = 122;
        }
        LastErrInfo::Set(v14, (struct tag_RpcInfo *)&v59);
        goto LABEL_18;
      }
      v27 = ((char *)v43[1] - (char *)v43[0]) >> 1;
      if ( v27 > 0xFFFFFFFF )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v13, v27);
        }
      }
      else
      {
        v28 = *(_DWORD *)a9;
        if ( (unsigned int)v27 + v28 >= v28 )
        {
          *(_DWORD *)a9 += v27;
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 15033);
          }
          pExceptionObject = 0;
          v47 = 0;
          v48 = 15033;
          v49 = -1;
          v50 = 984;
          throw (EvtException *)&pExceptionObject;
        }
        *(_DWORD *)a9 = -1;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v28, v27);
        }
      }
      LODWORD(v59) = 122;
      LastErrInfo::Set(v29, (struct tag_RpcInfo *)&v59);
      v30 = v44;
      v31 = (char *)v43[0];
LABEL_49:
      if ( v31 != v30 )
        operator delete(v31);
      goto LABEL_19;
    }
    v39[0] = 0;
    v20 = EventRendering::RenderEventToXml((EventRendering *)a3, (const struct Event *)v12, (unsigned int)a8, v39, v38);
    *(_DWORD *)a9 = v39[0] >> 1;
    if ( v20 && v20 != 122 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v20);
      }
      *(_OWORD *)Src = 0;
      v65 = 0;
      v66 = v20;
      v67 = -1;
      v68 = 845;
      throw (EvtException *)Src;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v54);
    if ( (unsigned __int8)GetEmbededMsg((BinXmlReader *)v58, ThreadLocale, (__int64)v54) )
    {
      LODWORD(v59) = v20;
      LastErrInfo::Set(v21, (struct tag_RpcInfo *)&v59);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v54);
      goto LABEL_19;
    }
    if ( v54[0] != &v55 )
      operator delete(v54[0]);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
    if ( !(unsigned __int8)BuildRenderingInfoXml(this, v45, v51, &v61, v41, &v59) )
    {
LABEL_48:
      v30 = &v42;
      v31 = (char *)v41[0];
      goto LABEL_49;
    }
    v23 = ((char *)v41[1] - (char *)v41[0]) >> 1;
    if ( v23 > 0x7FFFFFFF )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v22, (unsigned int)v23);
      }
    }
    else
    {
      v24 = *(unsigned int *)a9;
      v25 = v24 + v23;
      if ( (int)v24 + (int)v23 >= (unsigned int)v24 )
      {
        *(_DWORD *)a9 = v25;
        if ( v25 > a7 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v25, a7);
          }
          LODWORD(v59) = 122;
          goto LABEL_47;
        }
        *(_OWORD *)v62 = *(_OWORD *)L"</Event>";
        v63 = aEvent[8];
        if ( (unsigned int)v24 >= 9 )
        {
          v32 = 2 * v24 - 18;
          if ( v32 > v12 || !a8 || v12 - v32 < 0x12 )
            goto LABEL_86;
          v33 = (char *)a8 + v32;
          *(_OWORD *)Src = *(_OWORD *)v33;
          LOWORD(v65) = *((_WORD *)v33 + 8);
          v34 = -1;
          v35 = -1;
          do
            ++v35;
          while ( *((_WORD *)Src + v35) );
          do
            ++v34;
          while ( *((_WORD *)v62 + v34) );
          if ( v35 != v34
            || (unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(Src, v62) )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 13);
            }
            pExceptionObject = 0;
            v47 = 0;
            v48 = 13;
            v49 = -1;
            v50 = 933;
            throw (EvtException *)&pExceptionObject;
          }
          v36 = 2 * v23;
          if ( v36 > v12 - v32
            || v36 > 0x10000000
            || (memcpy_0((char *)a8 + v32, v41[0], v36), v37 = v32 + v36, v12 - (unsigned int)v37 < 0x12) )
          {
LABEL_86:
            UserBuffer::ThrowUnexpectedEOFException();
          }
          *(_OWORD *)((char *)a8 + v37) = *(_OWORD *)v62;
          *(_WORD *)((char *)a8 + (unsigned int)v37 + 16) = v63;
          LastErrInfo::Reset((LastErrInfo *)(unsigned int)v37);
          goto LABEL_48;
        }
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v24);
        }
      }
      else
      {
        *(_DWORD *)a9 = -1;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v24, v23);
        }
      }
    }
    LODWORD(v59) = 534;
LABEL_47:
    LastErrInfo::Set(v26, (struct tag_RpcInfo *)&v59);
    goto LABEL_48;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, a7);
  }
  LODWORD(v59) = 534;
  LastErrInfo::Set(v19, (struct tag_RpcInfo *)&v59);
}

```

## disassembly

```asm
0x180007fb8  push    rbp
0x180007fba  push    rbx
0x180007fbb  push    rsi
0x180007fbc  push    rdi
0x180007fbd  push    r12
0x180007fbf  push    r13
0x180007fc1  push    r14
0x180007fc3  push    r15
0x180007fc5  lea     rbp, [rsp-178h]
0x180007fcd  sub     rsp, 278h
0x180007fd4  mov     rax, cs:__security_cookie
0x180007fdb  xor     rax, rsp
0x180007fde  mov     [rbp+1B0h+var_50], rax
0x180007fe5  mov     [rsp+2B0h+var_264], r9d
0x180007fea  mov     rdi, r8
0x180007fed  mov     [rbp+1B0h+var_1F0], r8
0x180007ff1  mov     [rbp+1B0h+var_220], rdx
0x180007ff5  mov     r13, rcx
0x180007ff8  mov     rax, [rbp+1B0h+arg_20]
0x180007fff  mov     [rbp+1B0h+var_90], rax
0x180008006  mov     eax, dword ptr [rbp+1B0h+arg_28]
0x18000800c  mov     [rsp+2B0h+var_26C], eax
0x180008010  mov     r14, [rbp+1B0h+arg_38]
0x180008017  mov     rsi, [rbp+1B0h+arg_40]
0x18000801e  xor     eax, eax
0x180008020  mov     [rbp+1B0h+var_B0], rax
0x180008027  mov     [rbp+1B0h+var_A8], eax
0x18000802d  xor     ecx, ecx
0x18000802f  test    r13, r13
0x180008032  jz      loc_1800087CC
0x180008038  mov     r12d, [r13+40h]
0x18000803c  mov     [rsp+2B0h+var_270], cl
0x180008040  mov     [rsi], ecx
0x180008042  mov     ebx, [rbp+1B0h+arg_30]
0x180008048  test    r14, r14
0x18000804b  jnz     loc_180008299
0x180008051  mov     r15, rbx
0x180008054  add     r15, r15
0x180008057  mov     eax, 0FFFFFFFFh
0x18000805c  cmp     r15, rax
0x18000805f  ja      loc_18000826A
0x180008065  mov     [rbp+1B0h+var_198], rcx
0x180008069  xorps   xmm0, xmm0
0x18000806c  movdqu  [rbp+1B0h+var_180], xmm0
0x180008071  mov     rax, [rdi+38h]
0x180008075  mov     [rbp+1B0h+var_190], rax
0x180008079  mov     eax, [rdi+44h]
0x18000807c  mov     [rbp+1B0h+var_188], rax
0x180008080  mov     rax, [rdi+28h]
0x180008084  mov     [rsp+2B0h+var_288], rax; struct BinXmlTemplateTable *
0x180008089  mov     [rsp+2B0h+var_290], rcx; unsigned int *
0x18000808e  xor     r9d, r9d; struct AbstractPublishedEventRecord *
0x180008091  lea     rdx, [rbp+1B0h+var_198]; struct BinXmlReaderData *
0x180008095  lea     rcx, [rbp+1B0h+var_170]; this
0x180008099  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x18000809e  nop
0x18000809f  mov     [rsp+2B0h+var_268], 0
0x1800080a7  xorps   xmm0, xmm0
0x1800080aa  movups  [rbp+1B0h+var_A0], xmm0
0x1800080b1  lea     r8, [rsp+2B0h+var_268]
0x1800080b6  lea     rdx, [rbp+1B0h+var_A0]
0x1800080bd  lea     rcx, [rbp+1B0h+var_170]; this
0x1800080c1  call    GetEventDescriptor
0x1800080c6  mov     r8d, [rsp+2B0h+var_26C]
0x1800080cb  cmp     r8d, 9
0x1800080cf  jz      loc_1800082AC
0x1800080d5  lea     rcx, [rsp+2B0h+var_240]
0x1800080da  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800080df  nop
0x1800080e0  lea     rax, [rsp+2B0h+var_240]
0x1800080e5  mov     [rsp+2B0h+var_290], rax; __int64
0x1800080ea  mov     r9d, r8d
0x1800080ed  lea     r8, [rsp+2B0h+var_270]
0x1800080f2  mov     edx, r12d; Locale
0x1800080f5  lea     rcx, [rbp+1B0h+var_170]; this
0x1800080f9  call    GetEmbededMsg
0x1800080fe  xor     r15d, r15d
0x180008101  test    al, al
0x180008103  jnz     loc_1800083D9
0x180008109  lea     rax, [rbp+1B0h+var_230]
0x18000810d  mov     rcx, [rsp+2B0h+var_240]; void *
0x180008112  cmp     rcx, rax
0x180008115  jz      short loc_18000811C
0x180008117  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000811c  mov     r9, [rbp+1B0h+var_90]; struct _EVT_VARIANT *
0x180008123  mov     r8d, [rsp+2B0h+var_264]; unsigned int
0x180008128  mov     rdx, rdi; struct Event *
0x18000812b  lea     rcx, [rbp+1B0h+var_1E8]; this
0x18000812f  call    ??0SubstitutionValues@@QEAA@PEBVEvent@@KPEAU_EVT_VARIANT@@@Z; SubstitutionValues::SubstitutionValues(Event const *,ulong,_EVT_VARIANT *)
0x180008134  nop
0x180008135  mov     dword ptr [rbp+1B0h+var_90+4], r15d
0x18000813c  mov     rcx, [rbp+1B0h+var_1C8]
0x180008140  mov     rax, [rbp+1B0h+var_1D0]
0x180008144  sub     rcx, rax
0x180008147  sar     rcx, 3
0x18000814b  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180008155  imul    rcx, rdx
0x180008159  mov     dword ptr [rbp+1B0h+var_90], ecx
0x18000815f  mov     [rbp+1B0h+var_90+8], rax
0x180008166  lea     rax, [rbp+1B0h+var_B0]
0x18000816d  mov     [rsp+2B0h+var_278], rax
0x180008172  mov     eax, [rsp+2B0h+var_26C]
0x180008176  mov     [rsp+2B0h+var_280], eax
0x18000817a  lea     rax, [rbp+1B0h+var_90]
0x180008181  mov     [rsp+2B0h+var_288], rax
0x180008186  mov     dword ptr [rsp+2B0h+var_290], 0FFFFFFFFh
0x18000818e  lea     r9, [rbp+1B0h+var_A0]
0x180008195  mov     r8, [rbp+1B0h+var_220]
0x180008199  mov     rdx, r13
0x18000819c  lea     rcx, [rbp+1B0h+Src]
0x1800081a3  call    GetRenderedMessageFromService
0x1800081a8  mov     rax, [rbp+1B0h+Src+8]
0x1800081af  test    rax, rax
0x1800081b2  jz      short loc_180008212
0x1800081b4  lea     r9d, [rax+1]
0x1800081b8  mov     [rsi], r9d
0x1800081bb  cmp     r9d, ebx
0x1800081be  ja      short loc_1800081E2
0x1800081c0  lea     rbx, [rax+rax]
0x1800081c4  mov     r8, rbx; Size
0x1800081c7  mov     rdx, [rbp+1B0h+Src]; Src
0x1800081ce  mov     rcx, r14; void *
0x1800081d1  call    memcpy_0
0x1800081d6  mov     [rbx+r14], r15w
0x1800081db  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800081e0  jmp     short loc_18000821E
0x1800081e2  lea     rax, WPP_GLOBAL_Control
0x1800081e9  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800081f0  cmp     rcx, rax
0x1800081f3  jz      short loc_180008208
0x1800081f5  test    dword ptr [rcx+1Ch], 40000h
0x1800081fc  jz      short loc_180008208
0x1800081fe  cmp     byte ptr [rcx+19h], 4
0x180008202  jnb     loc_1800087AE
0x180008208  mov     dword ptr [rbp+1B0h+var_B0], 7Ah ; 'z'
0x180008212  lea     rdx, [rbp+1B0h+var_B0]; struct tag_RpcInfo *
0x180008219  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x18000821e  lea     rcx, [rbp+1B0h+var_68]
0x180008225  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18000822a  nop
0x18000822b  lea     rcx, [rbp+1B0h+var_1D0]
0x18000822f  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x180008234  lea     rcx, [rbp+1B0h+var_1E8]
0x180008238  call    ?_Uninit@?$vector@VBinXmlVariantHolder@@V?$allocator@VBinXmlVariantHolder@@@utl@@@utl@@AEAAXXZ; utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(void)
0x18000823d  nop
0x18000823e  lea     rcx, [rbp+1B0h+var_170]; this
0x180008242  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x180008247  mov     rcx, [rbp+1B0h+var_50]
0x18000824e  xor     rcx, rsp; StackCookie
0x180008251  call    __security_check_cookie
0x180008256  add     rsp, 278h
0x18000825d  pop     r15
0x18000825f  pop     r14
0x180008261  pop     r13
0x180008263  pop     r12
0x180008265  pop     rdi
0x180008266  pop     rsi
0x180008267  pop     rbx
0x180008268  pop     rbp
0x180008269  retn
0x18000826a  lea     rax, WPP_GLOBAL_Control
0x180008271  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180008278  cmp     rcx, rax
0x18000827b  jnz     loc_180008831
0x180008281  mov     dword ptr [rbp+1B0h+var_B0], 216h
0x18000828b  lea     rdx, [rbp+1B0h+var_B0]; struct tag_RpcInfo *
0x180008292  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x180008297  jmp     short loc_180008247
0x180008299  test    ebx, ebx
0x18000829b  jz      loc_180008051
0x1800082a1  mov     [r14], cx
0x1800082a5  xor     ecx, ecx
0x1800082a7  jmp     loc_180008051
0x1800082ac  mov     [rsp+2B0h+var_26C], 0
0x1800082b4  lea     r9, [rsp+2B0h+var_26C]; void *
0x1800082b9  mov     r8, r14; unsigned int
0x1800082bc  mov     edx, r15d; struct Event *
0x1800082bf  mov     rcx, rdi; this
0x1800082c2  call    ?RenderEventToXml@EventRendering@@YAKAEBVEvent@@KPEAXPEAK@Z; EventRendering::RenderEventToXml(Event const &,ulong,void *,ulong *)
0x1800082c7  mov     edi, eax
0x1800082c9  mov     ecx, [rsp+2B0h+var_26C]
0x1800082cd  shr     ecx, 1
0x1800082cf  mov     [rsi], ecx
0x1800082d1  test    eax, eax
0x1800082d3  jnz     loc_180008865
0x1800082d9  lea     rcx, [rbp+1B0h+var_1B8]
0x1800082dd  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800082e2  nop
0x1800082e3  lea     rax, [rbp+1B0h+var_1B8]
0x1800082e7  mov     [rsp+2B0h+var_290], rax; __int64
0x1800082ec  xor     r9d, r9d
0x1800082ef  lea     r8, [rsp+2B0h+var_270]
0x1800082f4  mov     edx, r12d; Locale
0x1800082f7  lea     rcx, [rbp+1B0h+var_170]; this
0x1800082fb  call    GetEmbededMsg
0x180008300  xor     r12d, r12d
0x180008303  test    al, al
0x180008305  jnz     loc_1800088EF
0x18000830b  lea     rax, [rbp+1B0h+var_1A8]
0x18000830f  mov     rcx, [rbp+1B0h+var_1B8]; void *
0x180008313  cmp     rcx, rax
0x180008316  jz      short loc_18000831D
0x180008318  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000831d  lea     rcx, [rsp+2B0h+var_260]
0x180008322  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180008327  nop
0x180008328  lea     rax, [rbp+1B0h+var_B0]
0x18000832f  mov     [rsp+2B0h+var_288], rax
0x180008334  lea     rax, [rsp+2B0h+var_260]
0x180008339  mov     [rsp+2B0h+var_290], rax
0x18000833e  lea     r9, [rbp+1B0h+var_A0]
0x180008345  mov     r8, [rbp+1B0h+var_1F0]
0x180008349  mov     rdx, [rbp+1B0h+var_220]
0x18000834d  mov     rcx, r13
0x180008350  call    BuildRenderingInfoXml
0x180008355  test    al, al
0x180008357  jz      loc_1800084B6
0x18000835d  mov     rdi, [rsp+2B0h+var_258]
0x180008362  sub     rdi, [rsp+2B0h+var_260]
0x180008367  sar     rdi, 1
0x18000836a  cmp     rdi, 7FFFFFFFh
0x180008371  ja      loc_18000846C
0x180008377  mov     r9d, [rsi]
0x18000837a  lea     r8d, [r9+rdi]
0x18000837e  cmp     r8d, r9d
0x180008381  jnb     loc_180008514
0x180008387  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000838d  lea     rax, WPP_GLOBAL_Control
0x180008394  mov     rcx, cs:WPP_GLOBAL_Control
0x18000839b  cmp     rcx, rax
0x18000839e  jz      loc_18000849F
0x1800083a4  test    dword ptr [rcx+1Ch], 40000h
0x1800083ab  jz      loc_18000849F
0x1800083b1  cmp     byte ptr [rcx+19h], 2
0x1800083b5  jb      loc_18000849F
0x1800083bb  mov     edx, 1Bh
0x1800083c0  mov     dword ptr [rsp+2B0h+var_290], edi
0x1800083c4  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x1800083cb  mov     rcx, [rcx+10h]
0x1800083cf  call    WPP_SF_DD
0x1800083d4  jmp     loc_18000849F
0x1800083d9  mov     r9, [rsp+2B0h+var_238]
0x1800083de  mov     rdx, [rsp+2B0h+var_240]; Src
0x1800083e3  sub     r9, rdx
0x1800083e6  sar     r9, 1
0x1800083e9  mov     r12d, 0FFFFFFFFh
0x1800083ef  cmp     r9, r12
0x1800083f2  ja      loc_1800084D3
0x1800083f8  mov     r10d, [rsi]
0x1800083fb  lea     r8d, [r9+r10]
0x1800083ff  cmp     r8d, r10d
0x180008402  jnb     loc_180008643
0x180008408  mov     [rsi], r12d
0x18000840b  lea     rax, WPP_GLOBAL_Control
0x180008412  mov     rcx, cs:WPP_GLOBAL_Control
0x180008419  cmp     rcx, rax
0x18000841c  jz      short loc_18000844A
0x18000841e  test    dword ptr [rcx+1Ch], 40000h
0x180008425  jz      short loc_18000844A
0x180008427  cmp     byte ptr [rcx+19h], 2
0x18000842b  jb      short loc_18000844A
0x18000842d  mov     edx, 20h ; ' '
0x180008432  mov     dword ptr [rsp+2B0h+var_290], r9d
0x180008437  mov     r9d, r10d
0x18000843a  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x180008441  mov     rcx, [rcx+10h]
0x180008445  call    WPP_SF_DD
0x18000844a  mov     dword ptr [rbp+1B0h+var_B0], 7Ah ; 'z'
0x180008454  lea     rdx, [rbp+1B0h+var_B0]; struct tag_RpcInfo *
0x18000845b  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x180008460  nop
0x180008461  lea     rax, [rbp+1B0h+var_230]
0x180008465  mov     rcx, [rsp+2B0h+var_240]
0x18000846a  jmp     short loc_1800084C0
0x18000846c  lea     rax, WPP_GLOBAL_Control
0x180008473  mov     rcx, cs:WPP_GLOBAL_Control
0x18000847a  cmp     rcx, rax
0x18000847d  jz      short loc_18000849F
0x18000847f  test    dword ptr [rcx+1Ch], 40000h
0x180008486  jz      short loc_18000849F
0x180008488  cmp     byte ptr [rcx+19h], 2
0x18000848c  jb      short loc_18000849F
0x18000848e  mov     r9d, edi
0x180008491  mov     edx, 1Ah
0x180008496  mov     rcx, [rcx+10h]
0x18000849a  call    WPP_SF_I
0x18000849f  mov     dword ptr [rbp+1B0h+var_B0], 216h
0x1800084a9  lea     rdx, [rbp+1B0h+var_B0]; struct tag_RpcInfo *
0x1800084b0  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x1800084b5  nop
0x1800084b6  lea     rax, [rsp+2B0h+var_250]
0x1800084bb  mov     rcx, [rsp+2B0h+var_260]; void *
0x1800084c0  cmp     rcx, rax
0x1800084c3  jz      loc_18000823E
0x1800084c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800084ce  jmp     loc_18000823E
0x1800084d3  lea     rax, WPP_GLOBAL_Control
0x1800084da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084e1  cmp     rcx, rax
0x1800084e4  jz      loc_18000844A
  ... truncated ...
```
