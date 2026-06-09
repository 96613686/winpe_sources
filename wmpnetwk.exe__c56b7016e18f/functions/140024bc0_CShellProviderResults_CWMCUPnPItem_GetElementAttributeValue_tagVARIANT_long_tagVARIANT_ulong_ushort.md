# CShellProviderResults::CWMCUPnPItem::GetElementAttributeValue(tagVARIANT,long,tagVARIANT,ulong,ushort *)

- ea: `0x140024bc0`
- end: `0x140025126`
- name: `?GetElementAttributeValue@CWMCUPnPItem@CShellProviderResults@@UEAAJUtagVARIANT@@J0KPEAG@Z`
- size: `1382`
- prototype: `__int64 __usercall@<rax>(CShellProviderResults::CWMCUPnPItem *__hidden this@<rcx>, struct tagVARIANT *__struct_ptr@<rdx>, int@<r8d>, struct tagVARIANT *__struct_ptr@<r9>, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000c920`
- `0x140024bc0`
- `0x140025ab0`
- `0x140027f4c`
- `0x1400282b0`
- `0x140045f20`
- `0x140054490`
- `0x140063398`
- `0x1400777cc`
- `0x14007a548`
- `0x14007fcd0`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x140024d0d`
- `ole32!PropVariantClear` at `0x140024d1f`
- `ole32!PropVariantClear` at `0x140024dc6`
- `ole32!PropVariantClear` at `0x140024d0d`
- `ole32!PropVariantClear` at `0x140024d1f`
- `ole32!PropVariantClear` at `0x140024dc6`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1400250bf`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1400250bf`
- `PROPSYS!PropVariantToString` at `0x140024dba`
- `PROPSYS!PropVariantToString` at `0x1400250d6`
- `PROPSYS!PropVariantToString` at `0x140024dba`
- `PROPSYS!PropVariantToString` at `0x1400250d6`

## pseudocode

```c
__int64 __fastcall CShellProviderResults::CWMCUPnPItem::GetElementAttributeValue(
        __int64 **this,
        struct tagVARIANT *a2,
        unsigned int a3,
        struct tagVARIANT *a4,
        UINT cch,
        unsigned __int16 *psz)
{
  char v6; // bl
  unsigned __int16 *v11; // rbx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int Lo; // r10d
  unsigned int v15; // r11d
  __int64 *v16; // rsi
  HRESULT ArtistAuthorElementData; // edi
  __int64 v18; // rax
  int AtomForElementAttribute; // eax
  __int64 v20; // rdx
  __int64 (__fastcall *v21)(__int64 *, _QWORD, _QWORD, __int64 *, PROPVARIANT *); // rax
  __int64 v23; // rax
  const WCHAR *v24; // rcx
  unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // rcx
  __int64 v27; // rsi
  __int64 v28; // rax
  const WCHAR *v29; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 *v31; // rax
  IRecordInfo *v32; // xmm1_8
  __int64 v33; // rbx
  const unsigned __int16 *v34; // rax
  unsigned __int16 *v35[2]; // [rsp+40h] [rbp-59h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-49h] BYREF
  IRecordInfo *v37; // [rsp+60h] [rbp-39h]
  PROPVARIANT ppropvar[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v39; // [rsp+80h] [rbp-19h]
  IID clsid; // [rsp+88h] [rbp-11h] BYREF

  v6 = 0;
  LODWORD(v35[0]) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    pRecInfo = a4->pRecInfo;
    *(_OWORD *)pvar = *(_OWORD *)&a4->vt;
    v37 = pRecInfo;
    v31 = (__int64 *)PrintVariant(&clsid, pvar);
    v32 = a2->pRecInfo;
    v33 = *v31;
    *(_OWORD *)pvar = *(_OWORD *)&a2->vt;
    v37 = v32;
    PrintVariant(v35, pvar);
    WPP_SF_SdSDq(*((_QWORD *)WPP_GLOBAL_Control + 2), a3, v33, cch, (char)psz);
    v6 = 3;
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v35);
  }
  if ( (v6 & 1) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&clsid);
  v11 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  *psz = 0;
  v35[0] = v11;
  if ( a2->vt != 19 || a4->vt != 19 )
  {
    ArtistAuthorElementData = -2147024809;
    goto LABEL_29;
  }
  Lo = a2->cyVal.Lo;
  v15 = a4->cyVal.Lo;
  if ( Lo != 3 )
  {
    if ( Lo == 10 || Lo == 11 )
    {
      ArtistAuthorElementData = CShellProviderResults::CWMCUPnPObject::GetArtistAuthorElementData(
                                  (int)this + 8,
                                  Lo,
                                  v15,
                                  a3,
                                  (__int64)v35);
      if ( ArtistAuthorElementData >= 0 )
        goto LABEL_57;
    }
    else
    {
      if ( Lo != 31 )
        goto LABEL_24;
      ArtistAuthorElementData = CShellProviderResults::CWMCUPnPItem::GetDescElementData((CShellProviderResults::CWMCUPnPItem *)this);
      if ( ArtistAuthorElementData >= 0 )
      {
LABEL_57:
        v11 = v35[0];
        ArtistAuthorElementData = StringCchCopyW(psz, cch, v35[0]);
        goto LABEL_29;
      }
    }
    v11 = v35[0];
    goto LABEL_29;
  }
  if ( v15 - 27 <= 1 )
  {
    v16 = this[14];
    v39 = 0;
    *(_OWORD *)ppropvar = 0;
    if ( v15 == 27 )
    {
      if ( !a3 )
      {
        ArtistAuthorElementData = (*(__int64 (__fastcall **)(__int64 *, const PROPERTYKEY *, PROPVARIANT *))(*v16 + 40))(
                                    v16,
                                    &PKEY_Audio_Format,
                                    ppropvar);
        if ( LOWORD(ppropvar[0]) >= 2u )
          goto LABEL_18;
      }
    }
    else if ( !a3 )
    {
      ArtistAuthorElementData = (*(__int64 (__fastcall **)(__int64 *, const PROPERTYKEY *, PROPVARIANT *))(*v16 + 40))(
                                  v16,
                                  &PKEY_Video_Compression,
                                  ppropvar);
      if ( ArtistAuthorElementData < 0 || LOWORD(ppropvar[0]) <= 1u )
      {
        v37 = 0;
        v18 = *v16;
        *(_OWORD *)pvar = 0;
        if ( (*(int (__fastcall **)(__int64 *, const PROPERTYKEY *, PROPVARIANT *))(v18 + 40))(
               v16,
               &PKEY_Video_FourCC,
               pvar) >= 0
          && LOWORD(pvar[0]) == 19 )
        {
          *(_DWORD *)&clsid.Data4[4] = *(_DWORD *)&MFVideoFormat_Base.Data4[4];
          clsid.Data1 = (unsigned int)pvar[1];
          *(_QWORD *)&clsid.Data2 = *(_QWORD *)&MFVideoFormat_Base.Data2;
          ArtistAuthorElementData = InitPropVariantFromCLSID(&clsid, ppropvar);
        }
        else
        {
          ArtistAuthorElementData = -2147023728;
        }
        PropVariantClear(pvar);
      }
      goto LABEL_18;
    }
    ArtistAuthorElementData = -2147023728;
LABEL_18:
    if ( ArtistAuthorElementData >= 0 )
      ArtistAuthorElementData = PropVariantToString(ppropvar, psz, cch);
    PropVariantClear(ppropvar);
    goto LABEL_29;
  }
LABEL_24:
  if ( v15 != 5 )
  {
    v37 = 0;
    *(_OWORD *)pvar = 0;
    AtomForElementAttribute = CdsValues::GetAtomForElementAttribute(Lo, v15, v12, v13);
    v20 = 10LL * AtomForElementAttribute;
    v21 = (__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, __int64 *, PROPVARIANT *))*((_QWORD *)&CShellPropertyThunk::s_arrCdsPropertyMap
                                                                                       + 10 * AtomForElementAttribute
                                                                                       + 9);
    if ( v21 )
    {
      ArtistAuthorElementData = v21(
                                  this[14],
                                  *((_QWORD *)&CShellPropertyThunk::s_arrCdsPropertyMap + v20 + 8),
                                  a3,
                                  this[16],
                                  pvar);
      if ( ArtistAuthorElementData >= 0 )
        ArtistAuthorElementData = PropVariantToString(pvar, psz, cch);
    }
    else
    {
      ArtistAuthorElementData = -2147023728;
    }
    PropVariantClear(pvar);
    goto LABEL_29;
  }
  v27 = cch;
  v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))(*this[16] + 56))(this[16]);
  if ( !IsRestrictedContainer(v34) )
  {
    if ( cch )
    {
      if ( cch <= 0x7FFFFFFFuLL )
      {
        v28 = 2147483646;
        v29 = L"0";
        v25 = psz;
        do
        {
          if ( !v28 )
            break;
          if ( !*v29 )
            break;
          *v25++ = *v29++;
          --v28;
          --v27;
        }
        while ( v27 );
        goto LABEL_41;
      }
      ArtistAuthorElementData = -2147024809;
LABEL_65:
      *psz = 0;
      goto LABEL_29;
    }
LABEL_63:
    ArtistAuthorElementData = -2147024809;
    goto LABEL_29;
  }
  if ( !cch )
    goto LABEL_63;
  if ( cch > 0x7FFFFFFFuLL )
  {
    ArtistAuthorElementData = -2147024809;
    goto LABEL_65;
  }
  v23 = 2147483646;
  v24 = L"1";
  v25 = psz;
  do
  {
    if ( !v23 )
      break;
    if ( !*v24 )
      break;
    *v25++ = *v24++;
    --v23;
    --v27;
  }
  while ( v27 );
LABEL_41:
  v26 = v25 - 1;
  ArtistAuthorElementData = -2147024774;
  if ( v27 )
  {
    v26 = v25;
    ArtistAuthorElementData = 0;
  }
  *v26 = 0;
LABEL_29:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ArtistAuthorElementData >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
      ArtistAuthorElementData,
      (__int64)psz);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  return (unsigned int)ArtistAuthorElementData;
}

```

## disassembly

```asm
0x140024bc0  push    rbp
0x140024bc2  push    rbx
0x140024bc3  push    rsi
0x140024bc4  push    rdi
0x140024bc5  push    r12
0x140024bc7  push    r13
0x140024bc9  push    r14
0x140024bcb  push    r15
0x140024bcd  lea     rbp, [rsp-0Fh]
0x140024bd2  sub     rsp, 0A8h
0x140024bd9  mov     rax, cs:__security_cookie
0x140024be0  xor     rax, rsp
0x140024be3  mov     [rbp+47h+var_48], rax
0x140024be7  mov     r14, [rbp+47h+psz]
0x140024beb  xor     ebx, ebx
0x140024bed  mov     dword ptr [rbp+47h+var_A0], ebx
0x140024bf0  mov     rdi, r9
0x140024bf3  mov     r12d, r8d
0x140024bf6  mov     rsi, rdx
0x140024bf9  mov     r15, rcx
0x140024bfc  mov     rax, cs:WPP_GLOBAL_Control
0x140024c03  lea     rcx, WPP_GLOBAL_Control
0x140024c0a  mov     r13d, [rbp+47h+cch]
0x140024c0e  cmp     rax, rcx
0x140024c11  jz      short loc_140024C1D
0x140024c13  test    byte ptr [rax+1Ch], 1
0x140024c17  jnz     loc_140024F1C
0x140024c1d  test    bl, 2
0x140024c20  jnz     loc_140024F9D
0x140024c26  test    bl, 1
0x140024c29  jnz     loc_140024FAE
0x140024c2f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140024c36  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140024c3d  mov     rax, [rax+18h]
0x140024c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c46  lea     rbx, [rax+18h]
0x140024c4a  xor     eax, eax
0x140024c4c  mov     [r14], ax
0x140024c50  mov     eax, 13h
0x140024c55  mov     [rbp+47h+var_A0], rbx
0x140024c59  cmp     ax, [rsi]
0x140024c5c  jnz     loc_1400250E3
0x140024c62  cmp     ax, [rdi]
0x140024c65  jnz     loc_1400250E3
0x140024c6b  mov     r10d, [rsi+8]
0x140024c6f  mov     r11d, [rdi+8]
0x140024c73  cmp     r10d, 3
0x140024c77  jnz     loc_140024D2A
0x140024c7d  lea     eax, [r11-1Bh]
0x140024c81  cmp     eax, 1
0x140024c84  ja      loc_140024D48
0x140024c8a  mov     rsi, [r15+70h]
0x140024c8e  xor     eax, eax
0x140024c90  mov     [rbp+47h+var_60], rax
0x140024c94  xorps   xmm0, xmm0
0x140024c97  movups  xmmword ptr [rbp+47h+ppropvar], xmm0
0x140024c9b  cmp     r11d, 1Bh
0x140024c9f  jz      loc_140024E2D
0x140024ca5  test    r12d, r12d
0x140024ca8  jnz     loc_140024E59
0x140024cae  mov     rax, [rsi]
0x140024cb1  lea     r8, [rbp+47h+ppropvar]
0x140024cb5  lea     rdx, PKEY_Video_Compression
0x140024cbc  mov     rcx, rsi
0x140024cbf  mov     rax, [rax+28h]
0x140024cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024cc8  mov     edi, eax
0x140024cca  test    eax, eax
0x140024ccc  js      short loc_140024CD5
0x140024cce  cmp     word ptr [rbp+47h+ppropvar], 1
0x140024cd3  ja      short loc_140024D13
0x140024cd5  xor     eax, eax
0x140024cd7  lea     r8, [rbp+47h+pvar]
0x140024cdb  mov     [rbp+47h+var_80], rax
0x140024cdf  lea     rdx, PKEY_Video_FourCC
0x140024ce6  mov     rax, [rsi]
0x140024ce9  xorps   xmm0, xmm0
0x140024cec  mov     rcx, rsi
0x140024cef  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x140024cf3  mov     rax, [rax+28h]
0x140024cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024cfc  test    eax, eax
0x140024cfe  jns     loc_14002508C
0x140024d04  mov     edi, 80070490h
0x140024d09  lea     rcx, [rbp+47h+pvar]; pvar
0x140024d0d  call    cs:__imp_PropVariantClear
0x140024d13  test    edi, edi
0x140024d15  jns     loc_1400250CC
0x140024d1b  lea     rcx, [rbp+47h+ppropvar]; pvar
0x140024d1f  call    cs:__imp_PropVariantClear
0x140024d25  jmp     loc_140024DCC
0x140024d2a  mov     edx, r10d
0x140024d2d  sub     edx, 0Ah
0x140024d30  jz      loc_140024FED
0x140024d36  sub     edx, 1
0x140024d39  jz      loc_140024FED
0x140024d3f  cmp     edx, 14h
0x140024d42  jz      loc_140024FBC
0x140024d48  cmp     r11d, 5
0x140024d4c  jz      loc_140025030
0x140024d52  xorps   xmm0, xmm0
0x140024d55  xor     eax, eax
0x140024d57  mov     edx, r11d
0x140024d5a  mov     [rbp+47h+var_80], rax
0x140024d5e  mov     ecx, r10d
0x140024d61  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x140024d65  call    ?GetAtomForElementAttribute@CdsValues@@SA?AW4Value@CdsValue@@W4CDS_ELEMENT_VALUE@@W4CDS_ATTRIBUTE_VALUE@@@Z; CdsValues::GetAtomForElementAttribute(CDS_ELEMENT_VALUE,CDS_ATTRIBUTE_VALUE)
0x140024d6a  movsxd  rcx, eax
0x140024d6d  lea     r10, ?s_arrCdsPropertyMap@CShellPropertyThunk@@0QBUCdsValueMap@1@B; CShellPropertyThunk::CdsValueMap const near * const CShellPropertyThunk::s_arrCdsPropertyMap
0x140024d74  lea     rdx, [rcx+rcx*4]
0x140024d78  add     rdx, rdx
0x140024d7b  mov     rax, [r10+rdx*8+48h]
0x140024d80  test    rax, rax
0x140024d83  jz      loc_140025082
0x140024d89  mov     r9, [r15+80h]
0x140024d90  lea     rcx, [rbp+47h+pvar]
0x140024d94  mov     rdx, [r10+rdx*8+40h]
0x140024d99  mov     r8d, r12d
0x140024d9c  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x140024da1  mov     rcx, [r15+70h]
0x140024da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024daa  mov     edi, eax
0x140024dac  test    eax, eax
0x140024dae  js      short loc_140024DC2
0x140024db0  mov     r8d, r13d; cch
0x140024db3  lea     rcx, [rbp+47h+pvar]; propvar
0x140024db7  mov     rdx, r14; psz
0x140024dba  call    cs:__imp_PropVariantToString
0x140024dc0  mov     edi, eax
0x140024dc2  lea     rcx, [rbp+47h+pvar]; pvar
0x140024dc6  call    cs:__imp_PropVariantClear
0x140024dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140024dd3  lea     rax, WPP_GLOBAL_Control
0x140024dda  cmp     rcx, rax
0x140024ddd  jz      short loc_140024DE9
0x140024ddf  test    byte ptr [rcx+1Ch], 1
0x140024de3  jnz     loc_1400250ED
0x140024de9  lea     rdx, [rbx-18h]
0x140024ded  mov     eax, 0FFFFFFFFh
0x140024df2  lock xadd [rdx+10h], eax
0x140024df7  sub     eax, 1
0x140024dfa  jg      short loc_140024E0B
0x140024dfc  mov     rcx, [rdx]
0x140024dff  mov     rax, [rcx]
0x140024e02  mov     rax, [rax+8]
0x140024e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e0b  mov     eax, edi
0x140024e0d  mov     rcx, [rbp+47h+var_48]
0x140024e11  xor     rcx, rsp; StackCookie
0x140024e14  call    __security_check_cookie
0x140024e19  add     rsp, 0A8h
0x140024e20  pop     r15
0x140024e22  pop     r14
0x140024e24  pop     r13
0x140024e26  pop     r12
0x140024e28  pop     rdi
0x140024e29  pop     rsi
0x140024e2a  pop     rbx
0x140024e2b  pop     rbp
0x140024e2c  retn
0x140024e2d  test    r12d, r12d
0x140024e30  jnz     short loc_140024E59
0x140024e32  mov     rax, [rsi]
0x140024e35  lea     r8, [rbp+47h+ppropvar]
0x140024e39  lea     rdx, PKEY_Audio_Format
0x140024e40  mov     rcx, rsi
0x140024e43  mov     rax, [rax+28h]
0x140024e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e4c  cmp     word ptr [rbp+47h+ppropvar], 2
0x140024e51  mov     edi, eax
0x140024e53  jnb     loc_140024D13
0x140024e59  mov     edi, 80070490h
0x140024e5e  jmp     loc_140024D13
0x140024e63  test    r13d, r13d
0x140024e66  jz      loc_140025062
0x140024e6c  cmp     r13, 7FFFFFFFh
0x140024e73  ja      loc_14002505B
0x140024e79  mov     eax, 7FFFFFFEh
0x140024e7e  lea     rcx, a1_0; "1"
0x140024e85  mov     rdx, r14
0x140024e88  test    rax, rax
0x140024e8b  jnz     short loc_140024EAD
0x140024e8d  test    rsi, rsi
0x140024e90  lea     rcx, [rdx-2]
0x140024e94  mov     edi, 8007007Ah
0x140024e99  cmovnz  rcx, rdx
0x140024e9d  xor     eax, eax
0x140024e9f  test    rsi, rsi
0x140024ea2  cmovnz  edi, eax
0x140024ea5  mov     [rcx], ax
0x140024ea8  jmp     loc_140024DCC
0x140024ead  movzx   r8d, word ptr [rcx]
0x140024eb1  test    r8w, r8w
0x140024eb5  jz      short loc_140024E8D
0x140024eb7  mov     [rdx], r8w
0x140024ebb  add     rcx, 2
0x140024ebf  add     rdx, 2
0x140024ec3  dec     rax
0x140024ec6  sub     rsi, 1
0x140024eca  jnz     short loc_140024E88
0x140024ecc  jmp     short loc_140024E8D
0x140024ece  test    r13d, r13d
0x140024ed1  jz      loc_140025062
0x140024ed7  cmp     r13, 7FFFFFFFh
0x140024ede  ja      loc_140025072
0x140024ee4  mov     eax, 7FFFFFFEh
0x140024ee9  lea     rcx, a0; "0"
0x140024ef0  mov     rdx, r14
0x140024ef3  test    rax, rax
0x140024ef6  jz      short loc_140024E8D
0x140024ef8  movzx   r8d, word ptr [rcx]
0x140024efc  test    r8w, r8w
0x140024f00  jz      short loc_140024E8D
0x140024f02  mov     [rdx], r8w
0x140024f06  add     rcx, 2
0x140024f0a  add     rdx, 2
0x140024f0e  dec     rax
0x140024f11  sub     rsi, 1
0x140024f15  jnz     short loc_140024EF3
0x140024f17  jmp     loc_140024E8D
0x140024f1c  cmp     byte ptr [rax+19h], 5
0x140024f20  jb      loc_140024C1D
0x140024f26  movups  xmm0, xmmword ptr [r9]
0x140024f2a  lea     rdx, [rbp+47h+pvar]
0x140024f2e  movsd   xmm1, qword ptr [r9+10h]
0x140024f34  lea     rcx, [rbp+47h+clsid]
0x140024f38  movaps  xmmword ptr [rbp+47h+pvar], xmm0
0x140024f3c  movsd   [rbp+47h+var_80], xmm1
0x140024f41  call    ?PrintVariant@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@UtagVARIANT@@@Z; PrintVariant(tagVARIANT)
0x140024f46  movups  xmm0, xmmword ptr [rsi]
0x140024f49  lea     rdx, [rbp+47h+pvar]
0x140024f4d  movsd   xmm1, qword ptr [rsi+10h]
0x140024f52  lea     rcx, [rbp+47h+var_A0]
0x140024f56  mov     rbx, [rax]
0x140024f59  movaps  xmmword ptr [rbp+47h+pvar], xmm0
0x140024f5d  movsd   [rbp+47h+var_80], xmm1
0x140024f62  call    ?PrintVariant@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@UtagVARIANT@@@Z; PrintVariant(tagVARIANT)
0x140024f67  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f6e  mov     edx, 2Ah ; '*'
0x140024f73  mov     qword ptr [rsp+0E0h+var_A8], r14; char
0x140024f78  mov     dword ptr [rsp+0E0h+var_B0], r13d; char
0x140024f7d  mov     r9, [rax]
0x140024f80  mov     rcx, [rcx+10h]; LoggerHandle
0x140024f84  mov     [rsp+0E0h+var_B8], rbx; __int64
0x140024f89  mov     dword ptr [rsp+0E0h+var_C0], r12d; char
0x140024f8e  call    WPP_SF_SdSDq
0x140024f93  mov     ebx, 3
0x140024f98  jmp     loc_140024C1D
0x140024f9d  and     ebx, 0FFFFFFFDh
0x140024fa0  lea     rcx, [rbp+47h+var_A0]
0x140024fa4  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140024fa9  jmp     loc_140024C26
0x140024fae  lea     rcx, [rbp+47h+clsid]
0x140024fb2  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140024fb7  jmp     loc_140024C2F
0x140024fbc  lea     r9, [rbp+47h+var_A0]
0x140024fc0  mov     r8d, r12d
0x140024fc3  mov     edx, r11d
0x140024fc6  mov     rcx, r15; this
0x140024fc9  call    ?GetDescElementData@CWMCUPnPItem@CShellProviderResults@@AEAAJW4CDS_ATTRIBUTE_VALUE@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CShellProviderResults::CWMCUPnPItem::GetDescElementData(CDS_ATTRIBUTE_VALUE,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140024fce  mov     edi, eax
0x140024fd0  test    eax, eax
0x140024fd2  js      short loc_140025027
0x140024fd4  mov     rbx, [rbp+47h+var_A0]
0x140024fd8  mov     rdx, r13; unsigned __int64
0x140024fdb  mov     r8, rbx; unsigned __int16 *
0x140024fde  mov     rcx, r14; unsigned __int16 *
0x140024fe1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140024fe6  mov     edi, eax
0x140024fe8  jmp     loc_140024DCC
0x140024fed  lea     rax, [rbp+47h+var_A0]
0x140024ff1  mov     r9d, r12d
0x140024ff4  lea     rcx, [r15+8]
0x140024ff8  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140024ffd  mov     r8d, r11d
0x140025000  mov     edx, r10d
0x140025003  call    ?GetArtistAuthorElementData@CWMCUPnPObject@CShellProviderResults@@IEAAJW4CDS_ELEMENT_VALUE@@W4CDS_ATTRIBUTE_VALUE@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CShellProviderResults::CWMCUPnPObject::GetArtistAuthorElementData(CDS_ELEMENT_VALUE,CDS_ATTRIBUTE_VALUE,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140025008  mov     edi, eax
0x14002500a  test    eax, eax
0x14002500c  js      short loc_140025027
0x14002500e  mov     rbx, [rbp+47h+var_A0]
0x140025012  mov     rdx, r13; unsigned __int64
0x140025015  mov     r8, rbx; unsigned __int16 *
0x140025018  mov     rcx, r14; unsigned __int16 *
0x14002501b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140025020  mov     edi, eax
0x140025022  jmp     loc_140024DCC
0x140025027  mov     rbx, [rbp+47h+var_A0]
0x14002502b  jmp     loc_140024DCC
0x140025030  mov     rcx, [r15+80h]
0x140025037  mov     rsi, r13
0x14002503a  mov     rax, [rcx]
0x14002503d  mov     rax, [rax+38h]
0x140025041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025046  mov     rcx, rax; unsigned __int16 *
0x140025049  call    ?IsRestrictedContainer@@YA_NPEBG@Z; IsRestrictedContainer(ushort const *)
0x14002504e  test    al, al
0x140025050  jz      loc_140024ECE
0x140025056  jmp     loc_140024E63
0x14002505b  mov     edi, 80070057h
  ... truncated ...
```
