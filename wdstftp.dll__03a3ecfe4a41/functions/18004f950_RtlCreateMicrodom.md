# RtlCreateMicrodom

- ea: `0x18004f950`
- end: `0x18005019e`
- name: `RtlCreateMicrodom`
- size: `2126`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044a88`
- `0x1800491c8`

## callees

- `0x1800370f4`
- `0x180037adc`
- `0x180037b80`
- `0x180037bb8`
- `0x18004f950`
- `0x180050e28`
- `0x1800575e8`
- `0x18005cb78`
- `0x18005cc64`
- `0x1800607b0`
- `0x180060e42`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180050118`
- `ntdll!RtlRaiseStatus` at `0x180050118`
- `ntdll!NtYieldExecution` at `0x18004fa59`
- `ntdll!NtYieldExecution` at `0x18004fa59`

## string_xrefs

- `0x18004f9ae`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004fa86`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004fac7`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004faff`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004fb33`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004fbd1`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004fe72`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004feb7`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004ff14`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004ff96`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005006e`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004f9c4`: `RtlCreateMicrodom`
- `0x18004fa9c`: `RtlCreateMicrodom`
- `0x18004fadd`: `RtlCreateMicrodom`
- `0x18004fb15`: `RtlCreateMicrodom`
- `0x18004fb49`: `RtlCreateMicrodom`
- `0x18004fbe7`: `RtlCreateMicrodom`
- `0x18004fe88`: `RtlCreateMicrodom`
- `0x18004fed6`: `RtlCreateMicrodom`
- `0x18004ff33`: `RtlCreateMicrodom`
- `0x18004ffb5`: `RtlCreateMicrodom`
- `0x18005008d`: `RtlCreateMicrodom`
- `0x18004faa7`: `(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Xml)`
- `0x18004fae8`: `(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Blob)`
- `0x18004fe93`: `RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)`
- `0x18004fee4`: `RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodom(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  signed __int32 v5; // eax
  int v6; // ebx
  int LBlob; // edi
  size_t v8; // rdx
  __int128 *v9; // rax
  __int64 v10; // xmm1_8
  __int64 *v11; // r14
  SIZE_T v12; // rbx
  __int64 v13; // rcx
  void (__fastcall ***v14)(_QWORD); // rbx
  void (__fastcall ***v15)(_QWORD); // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  __int64 v23; // rdx
  signed __int32 v25[8]; // [rsp+0h] [rbp-100h] BYREF
  _QWORD v26[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+40h] [rbp-C0h]
  _QWORD v28[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  char v36; // [rsp+98h] [rbp-68h]
  _QWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v38; // [rsp+B0h] [rbp-50h]
  const char *v39; // [rsp+B8h] [rbp-48h]
  _QWORD v40[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+D0h] [rbp-30h]
  const char *v42; // [rsp+D8h] [rbp-28h]
  _QWORD v43[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v44; // [rsp+F0h] [rbp-10h]
  const char *v45; // [rsp+F8h] [rbp-8h]
  _QWORD v46[2]; // [rsp+100h] [rbp+0h] BYREF
  int v47; // [rsp+110h] [rbp+10h]
  const char *v48; // [rsp+118h] [rbp+18h]
  _QWORD v49[2]; // [rsp+120h] [rbp+20h] BYREF
  int v50; // [rsp+130h] [rbp+30h]
  const char *v51; // [rsp+138h] [rbp+38h]
  _QWORD v52[2]; // [rsp+140h] [rbp+40h] BYREF
  int v53; // [rsp+150h] [rbp+50h]
  __int64 v54; // [rsp+158h] [rbp+58h]
  _QWORD v55[2]; // [rsp+160h] [rbp+60h] BYREF
  int v56; // [rsp+170h] [rbp+70h]
  const char *v57; // [rsp+178h] [rbp+78h]
  _QWORD v58[2]; // [rsp+180h] [rbp+80h] BYREF
  int v59; // [rsp+190h] [rbp+90h]
  const char *v60; // [rsp+198h] [rbp+98h]
  _QWORD v61[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v62; // [rsp+1B0h] [rbp+B0h]
  const char *v63; // [rsp+1B8h] [rbp+B8h]
  _QWORD v64[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v65; // [rsp+1D0h] [rbp+D0h]
  __int64 v66; // [rsp+1D8h] [rbp+D8h]
  _QWORD v67[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v68; // [rsp+1F0h] [rbp+F0h]
  __int64 v69; // [rsp+1F8h] [rbp+F8h]
  int v70; // [rsp+200h] [rbp+100h] BYREF
  __int64 v71; // [rsp+208h] [rbp+108h]
  __int64 v72; // [rsp+210h] [rbp+110h]
  _BYTE v73[40]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v74[48]; // [rsp+240h] [rbp+140h] BYREF
  unsigned int v75; // [rsp+270h] [rbp+170h]
  size_t Size; // [rsp+3A0h] [rbp+2A0h] BYREF
  void (__fastcall ***v77)(_QWORD); // [rsp+3A8h] [rbp+2A8h] BYREF
  unsigned int v78; // [rsp+3B0h] [rbp+2B0h]
  _QWORD v79[2]; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int64 v80; // [rsp+3C8h] [rbp+2C8h]
  __int128 v81; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v82; // [rsp+3E0h] [rbp+2E0h]
  _QWORD v83[2]; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v84; // [rsp+3F8h] [rbp+2F8h]

  v78 = 0;
  v81 = 0u;
  v82 = 0;
  if ( !a1 )
  {
    v38 = 4096;
    v37[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = v37;
    v37[1] = "RtlCreateMicrodom";
    v39 = "Not-null check failed: Params";
LABEL_26:
    RtlReportErrorOrigination(v4, a2, 3221225485LL);
    LBlob = -1073741811;
LABEL_96:
    if ( v82 )
      RtlFreeLBlob(&v81);
    return (unsigned int)LBlob;
  }
  if ( dword_180077958 != 2 )
  {
    _InterlockedOr(v25, 0);
    v5 = _InterlockedCompareExchange(&dword_180077958, 1, 0);
    if ( v5 )
    {
      if ( v5 == 1 )
      {
        while ( dword_180077958 != 2 )
          NtYieldExecution();
      }
    }
    else
    {
      qword_180077970 = (__int64)&MicrodomImplementation::g_OneShotMicrodomInit;
      qword_180077978 = (__int64)Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Teardown;
      if ( MicrodomImplementation::g_OneShotMicrodomInit )
        __debugbreak();
      dword_180077948 = 0;
      MicrodomImplementation::g_OneShotMicrodomInit = (__int64)&dword_180077948;
      dword_18007794C = 0;
      _InterlockedExchange(&dword_180077958, 2);
    }
    _InterlockedOr(v25, 0);
  }
  if ( dword_180077958 != 2 )
    __debugbreak();
  if ( *(_DWORD *)a1 >= 2u )
  {
    v41 = 4102;
    v40[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = v40;
    v40[1] = "RtlCreateMicrodom";
    v42 = "(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::"
          "Microdom::Rtl::CreateMicrodomSource::Xml)";
    goto LABEL_26;
  }
  v6 = *(_DWORD *)(a1 + 4);
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      if ( v6 != 1 )
      {
        v44 = 4107;
        v43[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v4 = v43;
        v43[1] = "RtlCreateMicrodom";
        v45 = "(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Win"
              "dows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rtl:"
              ":CreateMicrodomSource::Blob)";
        goto LABEL_26;
      }
      if ( !*(_QWORD *)(a1 + 8) )
      {
        v47 = 4113;
        v46[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v4 = v46;
        v46[1] = "RtlCreateMicrodom";
        v48 = "Not-null check failed: Params->Source.pBlob";
        goto LABEL_26;
      }
    }
  }
  else if ( !*(_QWORD *)(a1 + 8) )
  {
    v50 = 4110;
    v49[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = v49;
    v49[1] = "RtlCreateMicrodom";
    v51 = "Not-null check failed: Params->Source.pIStream";
    goto LABEL_26;
  }
  memset_0(&v31, 0, 0x38u);
  v36 = *(_BYTE *)(a1 + 48);
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
      goto LABEL_93;
    v11 = *(__int64 **)(a1 + 8);
    v79[0] = 0;
    v79[1] = 0;
    v80 = 0;
    v83[0] = 0;
    v83[1] = 0;
    v84 = 0;
    if ( !v6 )
    {
      Size = 0;
      v26[0] = 0;
      v12 = 0;
      v26[1] = 0;
      Src = 0;
      LBlob = RtlAllocateLBlob(0x400u);
      if ( LBlob >= 0 )
      {
        do
        {
          LBlob = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, size_t *))(**(_QWORD **)(a1 + 8) + 16LL))(
                    *(_QWORD *)(a1 + 8),
                    8,
                    Src,
                    &Size);
          if ( LBlob < 0 )
            goto LABEL_44;
          v12 += Size;
        }
        while ( Size == 8 );
        LBlob = RtlAllocateLBlob(v12);
        if ( LBlob < 0 )
          goto LABEL_44;
        v13 = *(_QWORD *)(a1 + 8);
        v77 = 0;
        v14 = 0;
        LBlob = (*(__int64 (__fastcall **)(__int64, GUID *, void (__fastcall ****)(_QWORD)))(*(_QWORD *)v13 + 8LL))(
                  v13,
                  &GUID_55eab610_3945_4595_b7f9_75bebf9486f4,
                  &v77);
        if ( LBlob < 0 )
        {
          v15 = v77;
        }
        else
        {
          if ( !v77 )
          {
            LBlob = -1073741127;
LABEL_42:
            if ( v14 )
              (**v14)(v14);
            goto LABEL_44;
          }
          v15 = 0;
          v14 = v77;
          v77 = 0;
        }
        if ( v15 )
        {
          v77 = 0;
          (**v15)(v15);
        }
        if ( LBlob >= 0 )
        {
          v16 = v79[0];
          while ( 1 )
          {
            LBlob = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, size_t *))(**(_QWORD **)(a1 + 8) + 16LL))(
                      *(_QWORD *)(a1 + 8),
                      8,
                      Src,
                      &Size);
            if ( LBlob < 0 )
              break;
            v8 = Size;
            if ( Size )
            {
              memcpy_0((void *)(v16 + v80), Src, Size);
              v8 = Size;
              v16 += Size;
              v79[0] = v16;
            }
            if ( v8 != 8 )
            {
              v11 = v79;
              if ( v14 )
                (**v14)(v14);
              if ( Src )
                RtlFreeLBlob(v26);
              goto LABEL_60;
            }
          }
        }
        goto LABEL_42;
      }
LABEL_44:
      if ( Src )
        RtlFreeLBlob(v26);
LABEL_85:
      if ( v84 )
        RtlFreeLBlob(v83);
      if ( v80 )
        RtlFreeLBlob(v79);
      goto LABEL_96;
    }
LABEL_60:
    if ( *(_BYTE *)(a1 + 49) || *(_BYTE *)(a1 + 50) )
    {
      v71 = v11[2];
      v17 = *v11;
      v70 = 64;
      v72 = v17;
      memset_0(v73, 0, sizeof(v73));
      memset_0(v74, 0, 0x160u);
      LBlob = RtlXmlInitializeTokenization(v74, &v70);
      if ( LBlob < 0 )
      {
        v56 = 4193;
        v55[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v19 = v55;
        v55[1] = "RtlCreateMicrodom";
        v57 = "RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)";
LABEL_66:
        RtlReportErrorOrigination(v19, v18, (unsigned int)LBlob);
        goto LABEL_85;
      }
      LBlob = RtlXmlDetermineStreamEncoding(v74, &v30);
      if ( LBlob < 0 )
      {
        v59 = 4194;
        v58[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v19 = v58;
        v58[1] = "RtlCreateMicrodom";
        v60 = "RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)";
        goto LABEL_66;
      }
      v8 = v75;
      if ( v75 != 5 )
      {
        if ( *(_BYTE *)(a1 + 49) )
        {
          v62 = 4198;
          v61[0] = "onecore\\base\\xml\\udom_microdom.cpp";
          v20 = v61;
          v61[1] = "RtlCreateMicrodom";
          v63 = "Params->fRequireUtf8";
LABEL_75:
          RtlReportErrorOrigination(v20, v8, 3221225485LL);
          LBlob = -1073741811;
          goto LABEL_85;
        }
        v21 = *v11;
        v29 = v11[2];
        v29 += v30;
        v28[0] = v21 - v30;
        v28[1] = v21 - v30;
        LODWORD(v8) = v75 - 1;
        if ( v75 == 1 )
        {
          v22 = 1019;
        }
        else
        {
          LODWORD(v8) = v75 - 2;
          if ( v75 == 2 )
          {
            v22 = 1018;
          }
          else
          {
            v8 = v75 - 3;
            if ( v75 == 3 )
            {
              v22 = 1014;
            }
            else
            {
              if ( v75 != 4 )
              {
                v65 = 4221;
                v64[0] = "onecore\\base\\xml\\udom_microdom.cpp";
                v20 = v64;
                v66 = 0;
                v64[1] = "RtlCreateMicrodom";
                goto LABEL_75;
              }
              v22 = 1013;
            }
          }
        }
        LBlob = RtlTranscodeLBlobs(5, v8, v22, (unsigned int)v28, 106, (__int64)v83);
        if ( LBlob < 0 )
          goto LABEL_85;
        v11 = v83;
      }
    }
    LBlob = MicrodomImplementation::CreateBinaryMicrodomFromXml(*(_QWORD *)(a1 + 40), v8, v11, &v81);
    if ( LBlob >= 0 )
    {
      v32 = v82;
      v31 = v81;
      if ( (_QWORD)v81 )
      {
        if ( v84 )
          RtlFreeLBlob(v83);
        if ( v80 )
          RtlFreeLBlob(v79);
        goto LABEL_93;
      }
      v68 = 4251;
      v67[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v69 = 0;
      v67[1] = "RtlCreateMicrodom";
      RtlReportErrorOrigination(v67, v23, 3221266563LL);
      LBlob = -1073700733;
    }
    goto LABEL_85;
  }
  if ( v6 == 1 )
  {
    v9 = *(__int128 **)(a1 + 8);
    v10 = *((_QWORD *)v9 + 2);
    v31 = *v9;
    v32 = v10;
  }
  else
  {
    if ( v6 != 2 )
    {
      v53 = 4133;
      v52[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v54 = 0;
      v52[1] = "RtlCreateMicrodom";
      RtlReportErrorOrigination(v52, v8, 3221225474LL);
      LBlob = -1073741822;
      goto LABEL_96;
    }
    v33 = *(_QWORD *)(a1 + 8);
    v34 = *(_QWORD *)(a1 + 16);
    v35 = *(_QWORD *)(a1 + 24);
  }
LABEL_93:
  if ( dword_180077958 != 2 )
    RtlRaiseStatus(-1073741595);
  LBlob = Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CMicrodom>::CreateInstance<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff,MicrodomImplementation::MdCreateParams,Windows::Microdom::Rtl::IRtlMicrodom>(
            MicrodomImplementation::g_OneShotMicrodomInit,
            &v31,
            a2);
  if ( LBlob < 0 )
    goto LABEL_96;
  if ( v82 )
    RtlFreeLBlob(&v81);
  return v78;
}

```

## disassembly

```asm
0x18004f950  mov     [rsp-8+arg_10], rbx
0x18004f955  mov     [rsp-8+arg_18], rsi
0x18004f95a  push    rbp
0x18004f95b  push    rdi
0x18004f95c  push    r12
0x18004f95e  push    r13
0x18004f960  push    r14
0x18004f962  lea     rbp, [rsp-310h]
0x18004f96a  sub     rsp, 410h
0x18004f971  mov     rax, cs:__security_cookie
0x18004f978  xor     rax, rsp
0x18004f97b  mov     [rbp+330h+var_30], rax
0x18004f982  xor     eax, eax
0x18004f984  xor     r13d, r13d
0x18004f987  mov     [rbp+330h+var_80], r13d
0x18004f98e  mov     r12, rdx
0x18004f991  mov     qword ptr [rbp+330h+var_60], rax
0x18004f998  mov     rsi, rcx
0x18004f99b  mov     qword ptr [rbp+330h+var_60+8], rax
0x18004f9a2  mov     [rbp+330h+var_50], rax
0x18004f9a9  test    rcx, rcx
0x18004f9ac  jnz     short loc_18004F9DF
0x18004f9ae  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004f9b5  mov     [rbp+330h+var_380], 1000h
0x18004f9bc  mov     [rbp+330h+var_390], rax
0x18004f9c0  lea     rcx, [rbp+330h+var_390]
0x18004f9c4  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x18004f9cb  mov     [rbp+330h+var_388], rax
0x18004f9cf  lea     rax, aNotNullCheckFa_3; "Not-null check failed: Params"
0x18004f9d6  mov     [rbp+330h+var_378], rax
0x18004f9da  jmp     loc_18004FB5F
0x18004f9df  mov     eax, cs:dword_180077958
0x18004f9e5  mov     edi, 1
0x18004f9ea  cmp     eax, 2
0x18004f9ed  jz      loc_18004FA75
0x18004f9f3  lock or [rsp+430h+var_430], r13d
0x18004f9f8  xor     eax, eax
0x18004f9fa  lock cmpxchg cs:dword_180077958, edi
0x18004fa02  jnz     short loc_18004FA53
0x18004fa04  cmp     cs:?g_OneShotMicrodomInit@MicrodomImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@A, r13; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom> MicrodomImplementation::g_OneShotMicrodomInit
0x18004fa0b  lea     rax, ?g_OneShotMicrodomInit@MicrodomImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom> MicrodomImplementation::g_OneShotMicrodomInit
0x18004fa12  mov     cs:qword_180077970, rax
0x18004fa19  lea     rax, ?Teardown@?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@CAXPEAX@Z; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Teardown(void *)
0x18004fa20  mov     cs:qword_180077978, rax
0x18004fa27  jz      short loc_18004FA2A
0x18004fa29  int     3; Trap to Debugger
0x18004fa2a  lea     rax, dword_180077948
0x18004fa31  mov     cs:dword_180077948, r13d
0x18004fa38  mov     cs:?g_OneShotMicrodomInit@MicrodomImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@A, rax; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom> MicrodomImplementation::g_OneShotMicrodomInit
0x18004fa3f  mov     eax, 2
0x18004fa44  mov     cs:dword_18007794C, r13d
0x18004fa4b  xchg    eax, cs:dword_180077958
0x18004fa51  jmp     short loc_18004FA70
0x18004fa53  cmp     eax, edi
0x18004fa55  jnz     short loc_18004FA70
0x18004fa57  jmp     short loc_18004FA65
0x18004fa59  call    cs:__imp_NtYieldExecution
0x18004fa60  nop     dword ptr [rax+rax+00h]
0x18004fa65  mov     eax, cs:dword_180077958
0x18004fa6b  cmp     eax, 2
0x18004fa6e  jnz     short loc_18004FA59
0x18004fa70  lock or [rsp+430h+var_430], r13d
0x18004fa75  mov     eax, cs:dword_180077958
0x18004fa7b  cmp     eax, 2
0x18004fa7e  jz      short loc_18004FA81
0x18004fa80  int     3; Trap to Debugger
0x18004fa81  cmp     dword ptr [rsi], 2
0x18004fa84  jb      short loc_18004FAB7
0x18004fa86  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004fa8d  mov     [rbp+330h+var_360], 1006h
0x18004fa94  mov     [rbp+330h+var_370], rax
0x18004fa98  lea     rcx, [rbp+330h+var_370]
0x18004fa9c  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x18004faa3  mov     [rbp+330h+var_368], rax
0x18004faa7  lea     rax, aParamsInputtyp; "(Params->InputType == Windows::Microdom"...
0x18004faae  mov     [rbp+330h+var_358], rax
0x18004fab2  jmp     loc_18004FB5F
0x18004fab7  mov     ebx, [rsi+4]
0x18004faba  test    ebx, ebx
0x18004fabc  jz      short loc_18004FB2D
0x18004fabe  cmp     ebx, 2
0x18004fac1  jz      short loc_18004FAF5
0x18004fac3  cmp     ebx, edi
0x18004fac5  jz      short loc_18004FAF9
0x18004fac7  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004face  mov     [rbp+330h+var_340], 100Bh
0x18004fad5  mov     [rbp+330h+var_350], rax
0x18004fad9  lea     rcx, [rbp+330h+var_350]
0x18004fadd  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x18004fae4  mov     [rbp+330h+var_348], rax
0x18004fae8  lea     rax, aParamsSourcety; "(Params->SourceType == Windows::Microdo"...
0x18004faef  mov     [rbp+330h+var_338], rax
0x18004faf3  jmp     short loc_18004FB5F
0x18004faf5  cmp     ebx, edi
0x18004faf7  jnz     short loc_18004FB74
0x18004faf9  cmp     [rsi+8], r13
0x18004fafd  jnz     short loc_18004FB74
0x18004faff  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004fb06  mov     [rbp+330h+var_320], 1011h
0x18004fb0d  mov     [rbp+330h+var_330], rax
0x18004fb11  lea     rcx, [rbp+330h+var_330]
0x18004fb15  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x18004fb1c  mov     [rbp+330h+var_328], rax
0x18004fb20  lea     rax, aNotNullCheckFa_0; "Not-null check failed: Params->Source.p"...
0x18004fb27  mov     [rbp+330h+var_318], rax
0x18004fb2b  jmp     short loc_18004FB5F
0x18004fb2d  cmp     [rsi+8], r13
0x18004fb31  jnz     short loc_18004FB74
0x18004fb33  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004fb3a  mov     [rbp+330h+var_300], 100Eh
0x18004fb41  mov     [rbp+330h+var_310], rax
0x18004fb45  lea     rcx, [rbp+330h+var_310]
0x18004fb49  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x18004fb50  mov     [rbp+330h+var_308], rax
0x18004fb54  lea     rax, aNotNullCheckFa_29; "Not-null check failed: Params->Source.p"...
0x18004fb5b  mov     [rbp+330h+var_2F8], rax
0x18004fb5f  mov     r8d, 0C000000Dh
0x18004fb65  call    RtlReportErrorOrigination
0x18004fb6a  mov     edi, 0C000000Dh
0x18004fb6f  jmp     loc_18005013F
0x18004fb74  xor     edx, edx; Val
0x18004fb76  lea     rcx, [rsp+430h+var_3C8]; void *
0x18004fb7b  lea     r8d, [rdx+38h]; Size
0x18004fb7f  call    memset_0
0x18004fb84  mov     al, [rsi+30h]
0x18004fb87  mov     [rbp+330h+var_398], al
0x18004fb8a  cmp     [rsi], r13d
0x18004fb8d  jnz     short loc_18004FC0B
0x18004fb8f  cmp     ebx, edi
0x18004fb91  jnz     short loc_18004FBAF
0x18004fb93  mov     rax, [rsi+8]
0x18004fb97  movups  xmm0, xmmword ptr [rax]
0x18004fb9a  movsd   xmm1, qword ptr [rax+10h]
0x18004fb9f  movups  [rsp+430h+var_3C8], xmm0
0x18004fba4  movsd   [rsp+430h+var_3B8], xmm1
0x18004fbaa  jmp     loc_180050108
0x18004fbaf  cmp     ebx, 2
0x18004fbb2  jnz     short loc_18004FBD1
0x18004fbb4  mov     rax, [rsi+8]
0x18004fbb8  mov     [rbp+330h+var_3B0], rax
0x18004fbbc  mov     rax, [rsi+10h]
0x18004fbc0  mov     [rbp+330h+var_3A8], rax
0x18004fbc4  mov     rax, [rsi+18h]
0x18004fbc8  mov     [rbp+330h+var_3A0], rax
0x18004fbcc  jmp     loc_180050108
0x18004fbd1  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004fbd8  mov     [rbp+330h+var_2E0], 1025h
0x18004fbdf  mov     [rbp+330h+var_2F0], rax
0x18004fbe3  lea     rcx, [rbp+330h+var_2F0]
0x18004fbe7  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x18004fbee  mov     [rbp+330h+var_2D8], r13
0x18004fbf2  mov     r8d, 0C0000002h
0x18004fbf8  mov     [rbp+330h+var_2E8], rax
0x18004fbfc  call    RtlReportErrorOrigination
0x18004fc01  mov     edi, 0C0000002h
0x18004fc06  jmp     loc_18005013F
0x18004fc0b  cmp     [rsi], edi
0x18004fc0d  jnz     loc_180050108
0x18004fc13  mov     r14, [rsi+8]
0x18004fc17  xor     eax, eax
0x18004fc19  mov     [rbp+330h+var_78], rax
0x18004fc20  mov     [rbp+330h+var_70], rax
0x18004fc27  mov     [rbp+330h+var_68], rax
0x18004fc2e  mov     [rbp+330h+var_48], rax
0x18004fc35  mov     [rbp+330h+var_40], rax
0x18004fc3c  mov     [rbp+330h+var_38], rax
0x18004fc43  test    ebx, ebx
0x18004fc45  jnz     loc_18004FE04
0x18004fc4b  lea     rdx, [rsp+430h+var_400]
0x18004fc50  mov     [rbp+330h+Size], r13
0x18004fc57  mov     ecx, 400h; Size
0x18004fc5c  mov     [rsp+430h+var_400], rax
0x18004fc61  mov     rbx, r13
0x18004fc64  mov     [rsp+430h+var_3F8], rax
0x18004fc69  mov     [rsp+430h+Src], rax
0x18004fc6e  call    RtlAllocateLBlob
0x18004fc73  mov     edi, eax
0x18004fc75  test    eax, eax
0x18004fc77  js      loc_18004FD1F
0x18004fc7d  mov     rcx, [rsi+8]
0x18004fc81  lea     r9, [rbp+330h+Size]
0x18004fc88  mov     r8, [rsp+430h+Src]
0x18004fc8d  mov     edx, 8
0x18004fc92  mov     rax, [rcx]
0x18004fc95  mov     rax, [rax+10h]
0x18004fc99  call    cs:__guard_dispatch_icall_fptr
0x18004fc9f  mov     edi, eax
0x18004fca1  test    eax, eax
0x18004fca3  js      short loc_18004FD1F
0x18004fca5  add     rbx, [rbp+330h+Size]
0x18004fcac  cmp     [rbp+330h+Size], 8
0x18004fcb4  jz      short loc_18004FC7D
0x18004fcb6  lea     rdx, [rbp+330h+var_78]
0x18004fcbd  mov     rcx, rbx; Size
0x18004fcc0  call    RtlAllocateLBlob
0x18004fcc5  mov     edi, eax
0x18004fcc7  test    eax, eax
0x18004fcc9  js      short loc_18004FD1F
0x18004fccb  mov     rcx, [rsi+8]
0x18004fccf  lea     r8, [rbp+330h+var_88]
0x18004fcd6  lea     rdx, _GUID_55eab610_3945_4595_b7f9_75bebf9486f4
0x18004fcdd  mov     [rbp+330h+var_88], r13
0x18004fce4  mov     rbx, r13
0x18004fce7  mov     rax, [rcx]
0x18004fcea  mov     rax, [rax+8]
0x18004fcee  call    cs:__guard_dispatch_icall_fptr
0x18004fcf4  mov     edi, eax
0x18004fcf6  test    eax, eax
0x18004fcf8  js      short loc_18004FD48
0x18004fcfa  mov     rax, [rbp+330h+var_88]
0x18004fd01  test    rax, rax
0x18004fd04  jnz     short loc_18004FD39
0x18004fd06  mov     edi, 0C00002B9h
0x18004fd0b  test    rbx, rbx
0x18004fd0e  jz      short loc_18004FD1F
0x18004fd10  mov     rax, [rbx]
0x18004fd13  mov     rcx, rbx
0x18004fd16  mov     rax, [rax]
0x18004fd19  call    cs:__guard_dispatch_icall_fptr
0x18004fd1f  cmp     [rsp+430h+Src], r13
0x18004fd24  jz      loc_1800500B2
0x18004fd2a  lea     rcx, [rsp+430h+var_400]
0x18004fd2f  call    RtlFreeLBlob
0x18004fd34  jmp     loc_1800500B2
0x18004fd39  mov     rcx, r13
0x18004fd3c  mov     rbx, rax
0x18004fd3f  mov     [rbp+330h+var_88], rcx
0x18004fd46  jmp     short loc_18004FD4F
0x18004fd48  mov     rcx, [rbp+330h+var_88]
0x18004fd4f  test    rcx, rcx
0x18004fd52  jz      short loc_18004FD67
0x18004fd54  mov     [rbp+330h+var_88], r13
0x18004fd5b  mov     rax, [rcx]
0x18004fd5e  mov     rax, [rax]
0x18004fd61  call    cs:__guard_dispatch_icall_fptr
0x18004fd67  test    edi, edi
0x18004fd69  js      short loc_18004FD0B
0x18004fd6b  mov     r14, [rbp+330h+var_78]
0x18004fd72  mov     rcx, [rsi+8]
0x18004fd76  lea     r9, [rbp+330h+Size]
0x18004fd7d  mov     r8, [rsp+430h+Src]
0x18004fd82  mov     edx, 8
0x18004fd87  mov     rax, [rcx]
0x18004fd8a  mov     rax, [rax+10h]
0x18004fd8e  call    cs:__guard_dispatch_icall_fptr
0x18004fd94  mov     edi, eax
0x18004fd96  test    eax, eax
0x18004fd98  js      loc_18004FD0B
0x18004fd9e  mov     rdx, [rbp+330h+Size]
0x18004fda5  test    rdx, rdx
0x18004fda8  jz      short loc_18004FDD2
0x18004fdaa  mov     rcx, [rbp+330h+var_68]
0x18004fdb1  mov     r8, rdx; Size
0x18004fdb4  mov     rdx, [rsp+430h+Src]; Src
0x18004fdb9  add     rcx, r14; void *
0x18004fdbc  call    memcpy_0
0x18004fdc1  mov     rdx, [rbp+330h+Size]
0x18004fdc8  add     r14, rdx
0x18004fdcb  mov     [rbp+330h+var_78], r14
0x18004fdd2  cmp     rdx, 8
0x18004fdd6  jz      short loc_18004FD72
0x18004fdd8  lea     r14, [rbp+330h+var_78]
0x18004fddf  test    rbx, rbx
0x18004fde2  jz      short loc_18004FDF3
0x18004fde4  mov     rax, [rbx]
0x18004fde7  mov     rcx, rbx
0x18004fdea  mov     rax, [rax]
0x18004fded  call    cs:__guard_dispatch_icall_fptr
0x18004fdf3  cmp     [rsp+430h+Src], r13
0x18004fdf8  jz      short loc_18004FE04
0x18004fdfa  lea     rcx, [rsp+430h+var_400]
0x18004fdff  call    RtlFreeLBlob
0x18004fe04  cmp     [rsi+31h], r13b
0x18004fe08  jnz     short loc_18004FE14
0x18004fe0a  cmp     [rsi+32h], r13b
0x18004fe0e  jz      loc_180050031
0x18004fe14  mov     rax, [r14+10h]
0x18004fe18  lea     rcx, [rbp+330h+var_218]; void *
0x18004fe1f  xor     edx, edx; Val
0x18004fe21  mov     [rbp+330h+var_228], rax
0x18004fe28  mov     rax, [r14]
0x18004fe2b  mov     [rbp+330h+var_230], 40h ; '@'
0x18004fe35  mov     [rbp+330h+var_220], rax
0x18004fe3c  lea     r8d, [rdx+28h]; Size
0x18004fe40  call    memset_0
0x18004fe45  xor     edx, edx; Val
0x18004fe47  lea     rcx, [rbp+330h+var_1F0]; void *
0x18004fe4e  mov     r8d, 160h; Size
0x18004fe54  call    memset_0
0x18004fe59  lea     rdx, [rbp+330h+var_230]
0x18004fe60  lea     rcx, [rbp+330h+var_1F0]
0x18004fe67  call    RtlXmlInitializeTokenization
0x18004fe6c  mov     edi, eax
0x18004fe6e  test    eax, eax
0x18004fe70  jns     short loc_18004FEA0
0x18004fe72  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004fe79  mov     [rbp+330h+var_2C0], 1061h
0x18004fe80  mov     [rbp+330h+var_2D0], rax
0x18004fe84  lea     rcx, [rbp+330h+var_2D0]
0x18004fe88  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
  ... truncated ...
```
