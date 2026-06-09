# Vml::VmGuid::Assign(ushort const * const)

- ea: `0x1400864a8`
- end: `0x140087444`
- name: `?Assign@VmGuid@Vml@@QEAAXQEBG@Z`
- size: `3996`
- prototype: `void __fastcall(Vml::VmGuid *__hidden this, const unsigned __int16 *const)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14008744c`
- `0x140087d00`
- `0x14009a630`
- `0x14009b370`

## callees

- `0x1400083bc`
- `0x14000ea60`
- `0x1400864a8`

## string_xrefs

- `0x140086f20`: `onecore\vm\common\vml\VmGuid.h`
- `0x140086f43`: `onecore\vm\common\vml\VmGuid.h`
- `0x140086f66`: `onecore\vm\common\vml\VmGuid.h`
- `0x140086f89`: `onecore\vm\common\vml\VmGuid.h`
- `0x140086fac`: `onecore\vm\common\vml\VmGuid.h`
- `0x140086fcf`: `onecore\vm\common\vml\VmGuid.h`
- `0x140086ff2`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087015`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087038`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008705b`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008707e`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400870a1`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400870c4`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400870e7`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008710a`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008712d`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087150`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087173`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087196`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400871b9`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400871dc`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400871ff`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087222`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087245`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087268`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008728b`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400872ae`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400872d1`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400872f4`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087317`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008733a`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008735d`: `onecore\vm\common\vml\VmGuid.h`
- `0x140087380`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400873a3`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400873c6`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400873e9`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008740c`: `onecore\vm\common\vml\VmGuid.h`
- `0x14008742f`: `onecore\vm\common\vml\VmGuid.h`

## pseudocode

```c
void __fastcall Vml::VmGuid::Assign(Vml::VmGuid *this, const unsigned __int16 *a2)
{
  unsigned __int16 v4; // r14
  __int64 v5; // rdx
  const unsigned __int16 *v6; // rcx
  int v7; // r9d
  __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // rdx
  unsigned __int8 v11; // di
  __int64 v12; // rdx
  unsigned __int8 v13; // bl
  __int64 v14; // rdx
  unsigned __int8 v15; // r11
  __int64 v16; // rdx
  unsigned __int8 v17; // r10
  __int64 v18; // rdx
  unsigned __int8 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned __int16 v23; // r8
  __int16 v24; // r9
  unsigned __int16 v25; // r10
  unsigned __int8 v26; // r8
  unsigned __int16 v27; // r10
  unsigned __int8 v28; // al
  __int64 v29; // rdx
  unsigned __int16 v30; // r8
  __int16 v31; // r9
  unsigned __int16 v32; // r10
  unsigned __int8 v33; // r8
  unsigned __int16 v34; // r10
  unsigned __int8 v35; // al
  __int64 v36; // rdx
  unsigned __int16 v37; // r8
  char v38; // r8
  __int64 v39; // rdx
  unsigned __int16 v40; // r8
  char v41; // r8
  __int64 v42; // rdx
  unsigned __int16 v43; // r8
  char v44; // r8
  __int64 v45; // rdx
  unsigned __int16 v46; // r8
  char v47; // r8
  __int64 v48; // rdx
  unsigned __int16 v49; // r8
  char v50; // r8
  __int64 v51; // rdx
  unsigned __int16 v52; // r8
  char v53; // r8
  __int64 v54; // rdx
  unsigned __int16 v55; // r8
  char v56; // r8
  __int64 v57; // rdx
  unsigned __int16 v58; // r8
  char v59; // r8
  _WORD *v60; // rcx
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // eax
  unsigned int v78; // eax
  unsigned int v79; // eax
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned int v82; // eax
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v85; // eax
  unsigned int v86; // eax
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // eax
  unsigned int v90; // eax
  unsigned int v91; // eax
  unsigned int v92; // eax
  unsigned int v93; // eax
  unsigned int v94; // eax
  unsigned int v95; // eax
  unsigned int v96; // eax
  unsigned int v97; // eax
  unsigned int v98; // eax
  int v99; // [rsp+20h] [rbp-18h]
  __int128 v100; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]

  if ( !a2 || (v4 = *a2) == 0 )
  {
    *(_OWORD *)this = 0;
    return;
  }
  if ( v4 == 123 )
    v5 = a2[1];
  else
    v5 = v4;
  v6 = a2 + 1;
  if ( v4 != 123 )
    v6 = a2;
  if ( !(_WORD)v5 )
    goto LABEL_263;
  if ( (unsigned __int16)(v5 - 48) <= 9u )
  {
    v7 = (unsigned __int16)v5;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(v5 - 97) <= 5u )
  {
    v7 = (unsigned __int16)v5 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(v5 - 65) > 5u )
  {
LABEL_263:
    v98 = wil::verify_hresult<long>(2147942487LL, v5);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v98,
      v99);
  }
  v7 = (unsigned __int16)v5 - 55;
LABEL_15:
  v8 = v6[1];
  if ( !(_WORD)v8 )
    goto LABEL_262;
  if ( (unsigned __int16)(v8 - 48) > 9u )
  {
    if ( (unsigned __int16)(v8 - 97) <= 5u )
    {
      v9 = v8 - 87;
      goto LABEL_22;
    }
    if ( (unsigned __int16)(v8 - 65) <= 5u )
    {
      v9 = v8 - 55;
      goto LABEL_22;
    }
LABEL_262:
    v97 = wil::verify_hresult<long>(2147942487LL, v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v97,
      v99);
  }
  v9 = v8 - 48;
LABEL_22:
  v10 = v6[2];
  if ( !(_WORD)v10 )
    goto LABEL_261;
  if ( (unsigned __int16)(v10 - 48) <= 9u )
  {
    v11 = v10 - 48;
    goto LABEL_29;
  }
  if ( (unsigned __int16)(v10 - 97) <= 5u )
  {
    v11 = v10 - 87;
    goto LABEL_29;
  }
  if ( (unsigned __int16)(v10 - 65) > 5u )
  {
LABEL_261:
    v96 = wil::verify_hresult<long>(2147942487LL, v10);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v96,
      v99);
  }
  v11 = v10 - 55;
LABEL_29:
  v12 = v6[3];
  if ( !(_WORD)v12 )
    goto LABEL_260;
  if ( (unsigned __int16)(v12 - 48) > 9u )
  {
    if ( (unsigned __int16)(v12 - 97) <= 5u )
    {
      v13 = v12 - 87;
      goto LABEL_36;
    }
    if ( (unsigned __int16)(v12 - 65) <= 5u )
    {
      v13 = v12 - 55;
      goto LABEL_36;
    }
LABEL_260:
    v95 = wil::verify_hresult<long>(2147942487LL, v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v95,
      v99);
  }
  v13 = v12 - 48;
LABEL_36:
  v14 = v6[4];
  if ( !(_WORD)v14 )
    goto LABEL_259;
  if ( (unsigned __int16)(v14 - 48) <= 9u )
  {
    v15 = v14 - 48;
    goto LABEL_43;
  }
  if ( (unsigned __int16)(v14 - 97) <= 5u )
  {
    v15 = v14 - 87;
    goto LABEL_43;
  }
  if ( (unsigned __int16)(v14 - 65) > 5u )
  {
LABEL_259:
    v94 = wil::verify_hresult<long>(2147942487LL, v14);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v94,
      v99);
  }
  v15 = v14 - 55;
LABEL_43:
  v16 = v6[5];
  if ( !(_WORD)v16 )
    goto LABEL_258;
  if ( (unsigned __int16)(v16 - 48) > 9u )
  {
    if ( (unsigned __int16)(v16 - 97) <= 5u )
    {
      v17 = v16 - 87;
      goto LABEL_50;
    }
    if ( (unsigned __int16)(v16 - 65) <= 5u )
    {
      v17 = v16 - 55;
      goto LABEL_50;
    }
LABEL_258:
    v93 = wil::verify_hresult<long>(2147942487LL, v16);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v93,
      v99);
  }
  v17 = v16 - 48;
LABEL_50:
  v18 = v6[6];
  if ( !(_WORD)v18 )
    goto LABEL_257;
  if ( (unsigned __int16)(v18 - 48) <= 9u )
  {
    v19 = v18 - 48;
    goto LABEL_57;
  }
  if ( (unsigned __int16)(v18 - 97) <= 5u )
  {
    v19 = v18 - 87;
    goto LABEL_57;
  }
  if ( (unsigned __int16)(v18 - 65) > 5u )
  {
LABEL_257:
    v92 = wil::verify_hresult<long>(2147942487LL, v18);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v92,
      v99);
  }
  v19 = v18 - 55;
LABEL_57:
  v20 = v6[7];
  if ( !(_WORD)v20 )
    goto LABEL_256;
  if ( (unsigned __int16)(v20 - 48) > 9u )
  {
    if ( (unsigned __int16)(v20 - 97) <= 5u )
    {
      v21 = (unsigned int)(v20 - 87);
      goto LABEL_64;
    }
    if ( (unsigned __int16)(v20 - 65) <= 5u )
    {
      v21 = (unsigned int)(v20 - 55);
      goto LABEL_64;
    }
LABEL_256:
    v91 = wil::verify_hresult<long>(2147942487LL, v20);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v91,
      v99);
  }
  v21 = (unsigned int)(v20 - 48);
LABEL_64:
  LODWORD(v100) = (unsigned __int8)v21
                | (16 * (v19 | (16 * (v17 | (16 * (v15 | (16 * (v13 | (16 * (v11 | (16 * (v9 | (16 * v7)))))))))))));
  if ( v6[8] != 45 )
  {
    v61 = wil::verify_hresult<long>(2147942487LL, v21);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44B,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v61,
      v100);
  }
  v22 = v6[9];
  if ( !(_WORD)v22 )
    goto LABEL_255;
  if ( (unsigned __int16)(v22 - 48) <= 9u )
    goto LABEL_71;
  if ( (unsigned __int16)(v22 - 97) <= 5u )
  {
    LOWORD(v22) = v22 - 87;
    goto LABEL_71;
  }
  if ( (unsigned __int16)(v22 - 65) > 5u )
  {
LABEL_255:
    v90 = wil::verify_hresult<long>(2147942487LL, v22);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v90,
      v100);
  }
  LOWORD(v22) = v22 - 55;
LABEL_71:
  v23 = v6[10];
  if ( !v23 )
    goto LABEL_254;
  v24 = v23 - 48;
  if ( (unsigned __int16)(v23 - 48) > 9u )
  {
    if ( (unsigned __int16)(v23 - 97) <= 5u )
    {
      v24 = v23 - 87;
      goto LABEL_77;
    }
    if ( (unsigned __int16)(v23 - 65) <= 5u )
    {
      v24 = v23 - 55;
      goto LABEL_77;
    }
LABEL_254:
    v89 = wil::verify_hresult<long>(2147942487LL, v22);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v89,
      v100);
  }
LABEL_77:
  v25 = v6[11];
  if ( !v25 )
    goto LABEL_253;
  v26 = v25 - 48;
  if ( (unsigned __int16)(v25 - 48) <= 9u )
    goto LABEL_83;
  if ( (unsigned __int16)(v25 - 97) <= 5u )
  {
    v26 = v25 - 87;
    goto LABEL_83;
  }
  if ( (unsigned __int16)(v25 - 65) > 5u )
  {
LABEL_253:
    v88 = wil::verify_hresult<long>(2147942487LL, v22);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v88,
      v100);
  }
  v26 = v25 - 55;
LABEL_83:
  v27 = v6[12];
  if ( !v27 )
    goto LABEL_252;
  v28 = v27 - 48;
  if ( (unsigned __int16)(v27 - 48) > 9u )
  {
    if ( (unsigned __int16)(v27 - 97) <= 5u )
    {
      v28 = v27 - 87;
      goto LABEL_89;
    }
    if ( (unsigned __int16)(v27 - 65) <= 5u )
    {
      v28 = v27 - 55;
      goto LABEL_89;
    }
LABEL_252:
    v87 = wil::verify_hresult<long>(2147942487LL, v22);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v87,
      v100);
  }
LABEL_89:
  LOWORD(v22) = v28 | (unsigned __int16)(16 * (v26 | (unsigned __int16)(16 * (v24 | (16 * v22)))));
  WORD2(v100) = v22;
  if ( v6[13] != 45 )
  {
    v62 = wil::verify_hresult<long>(2147942487LL, v22);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v62,
      v100);
  }
  v29 = v6[14];
  if ( !(_WORD)v29 )
    goto LABEL_251;
  if ( (unsigned __int16)(v29 - 48) <= 9u )
    goto LABEL_96;
  if ( (unsigned __int16)(v29 - 97) <= 5u )
  {
    LOWORD(v29) = v29 - 87;
    goto LABEL_96;
  }
  if ( (unsigned __int16)(v29 - 65) > 5u )
  {
LABEL_251:
    v86 = wil::verify_hresult<long>(2147942487LL, v29);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v86,
      v100);
  }
  LOWORD(v29) = v29 - 55;
LABEL_96:
  v30 = v6[15];
  if ( !v30 )
    goto LABEL_250;
  v31 = v30 - 48;
  if ( (unsigned __int16)(v30 - 48) > 9u )
  {
    if ( (unsigned __int16)(v30 - 97) <= 5u )
    {
      v31 = v30 - 87;
      goto LABEL_102;
    }
    if ( (unsigned __int16)(v30 - 65) <= 5u )
    {
      v31 = v30 - 55;
      goto LABEL_102;
    }
LABEL_250:
    v85 = wil::verify_hresult<long>(2147942487LL, v29);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v85,
      v100);
  }
LABEL_102:
  v32 = v6[16];
  if ( !v32 )
    goto LABEL_249;
  v33 = v32 - 48;
  if ( (unsigned __int16)(v32 - 48) <= 9u )
    goto LABEL_108;
  if ( (unsigned __int16)(v32 - 97) <= 5u )
  {
    v33 = v32 - 87;
    goto LABEL_108;
  }
  if ( (unsigned __int16)(v32 - 65) > 5u )
  {
LABEL_249:
    v84 = wil::verify_hresult<long>(2147942487LL, v29);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v84,
      v100);
  }
  v33 = v32 - 55;
LABEL_108:
  v34 = v6[17];
  if ( !v34 )
    goto LABEL_248;
  v35 = v34 - 48;
  if ( (unsigned __int16)(v34 - 48) > 9u )
  {
    if ( (unsigned __int16)(v34 - 97) <= 5u )
    {
      v35 = v34 - 87;
      goto LABEL_114;
    }
    if ( (unsigned __int16)(v34 - 65) <= 5u )
    {
      v35 = v34 - 55;
      goto LABEL_114;
    }
LABEL_248:
    v83 = wil::verify_hresult<long>(2147942487LL, v29);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v83,
      v100);
  }
LABEL_114:
  LOWORD(v29) = v35 | (unsigned __int16)(16 * (v33 | (unsigned __int16)(16 * (v31 | (16 * v29)))));
  WORD3(v100) = v29;
  if ( v6[18] != 45 )
  {
    v63 = wil::verify_hresult<long>(2147942487LL, v29);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v63,
      v100);
  }
  v36 = v6[19];
  if ( !(_WORD)v36 )
    goto LABEL_247;
  if ( (unsigned __int16)(v36 - 48) <= 9u )
    goto LABEL_121;
  if ( (unsigned __int16)(v36 - 97) <= 5u )
  {
    LOBYTE(v36) = v36 - 87;
    goto LABEL_121;
  }
  if ( (unsigned __int16)(v36 - 65) > 5u )
  {
LABEL_247:
    v82 = wil::verify_hresult<long>(2147942487LL, v36);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v82,
      v100);
  }
  LOBYTE(v36) = v36 - 55;
LABEL_121:
  v37 = v6[20];
  if ( !v37 )
    goto LABEL_246;
  if ( (unsigned __int16)(v37 - 48) > 9u )
  {
    if ( (unsigned __int16)(v37 - 97) <= 5u )
    {
      v38 = v37 - 87;
      goto LABEL_128;
    }
    if ( (unsigned __int16)(v37 - 65) <= 5u )
    {
      v38 = v37 - 55;
      goto LABEL_128;
    }
LABEL_246:
    v81 = wil::verify_hresult<long>(2147942487LL, v36);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v81,
      v100);
  }
  v38 = v37 - 48;
LABEL_128:
  BYTE8(v100) = v38 | (16 * v36);
  v39 = v6[21];
  if ( !(_WORD)v39 )
    goto LABEL_245;
  if ( (unsigned __int16)(v39 - 48) <= 9u )
    goto LABEL_134;
  if ( (unsigned __int16)(v39 - 97) <= 5u )
  {
    LOBYTE(v39) = v39 - 87;
    goto LABEL_134;
  }
  if ( (unsigned __int16)(v39 - 65) > 5u )
  {
LABEL_245:
    v80 = wil::verify_hresult<long>(2147942487LL, v39);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v80,
      v100);
  }
  LOBYTE(v39) = v39 - 55;
LABEL_134:
  v40 = v6[22];
  if ( !v40 )
    goto LABEL_244;
  if ( (unsigned __int16)(v40 - 48) > 9u )
  {
    if ( (unsigned __int16)(v40 - 97) <= 5u )
    {
      v41 = v40 - 87;
      goto LABEL_141;
    }
    if ( (unsigned __int16)(v40 - 65) <= 5u )
    {
      v41 = v40 - 55;
      goto LABEL_141;
    }
LABEL_244:
    v79 = wil::verify_hresult<long>(2147942487LL, v39);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v79,
      v100);
  }
  v41 = v40 - 48;
LABEL_141:
  LOBYTE(v39) = v41 | (16 * v39);
  BYTE9(v100) = v39;
  if ( v6[23] != 45 )
  {
    v64 = wil::verify_hresult<long>(2147942487LL, v39);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v64,
      v100);
  }
  v42 = v6[24];
  if ( !(_WORD)v42 )
    goto LABEL_243;
  if ( (unsigned __int16)(v42 - 48) <= 9u )
    goto LABEL_148;
  if ( (unsigned __int16)(v42 - 97) <= 5u )
  {
    LOBYTE(v42) = v42 - 87;
    goto LABEL_148;
  }
  if ( (unsigned __int16)(v42 - 65) > 5u )
  {
LABEL_243:
    v78 = wil::verify_hresult<long>(2147942487LL, v42);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v78,
      v100);
  }
  LOBYTE(v42) = v42 - 55;
LABEL_148:
  v43 = v6[25];
  if ( !v43 )
    goto LABEL_242;
  if ( (unsigned __int16)(v43 - 48) > 9u )
  {
    if ( (unsigned __int16)(v43 - 97) <= 5u )
    {
      v44 = v43 - 87;
      goto LABEL_155;
    }
    if ( (unsigned __int16)(v43 - 65) <= 5u )
    {
      v44 = v43 - 55;
      goto LABEL_155;
    }
LABEL_242:
    v77 = wil::verify_hresult<long>(2147942487LL, v42);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v77,
      v100);
  }
  v44 = v43 - 48;
LABEL_155:
  BYTE10(v100) = v44 | (16 * v42);
  v45 = v6[26];
  if ( !(_WORD)v45 )
    goto LABEL_241;
  if ( (unsigned __int16)(v45 - 48) <= 9u )
    goto LABEL_161;
  if ( (unsigned __int16)(v45 - 97) <= 5u )
  {
    LOBYTE(v45) = v45 - 87;
    goto LABEL_161;
  }
  if ( (unsigned __int16)(v45 - 65) > 5u )
  {
LABEL_241:
    v76 = wil::verify_hresult<long>(2147942487LL, v45);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v76,
      v100);
  }
  LOBYTE(v45) = v45 - 55;
LABEL_161:
  v46 = v6[27];
  if ( !v46 )
    goto LABEL_240;
  if ( (unsigned __int16)(v46 - 48) > 9u )
  {
    if ( (unsigned __int16)(v46 - 97) <= 5u )
    {
      v47 = v46 - 87;
      goto LABEL_168;
    }
    if ( (unsigned __int16)(v46 - 65) <= 5u )
    {
      v47 = v46 - 55;
      goto LABEL_168;
    }
LABEL_240:
    v75 = wil::verify_hresult<long>(2147942487LL, v45);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v75,
      v100);
  }
  v47 = v46 - 48;
LABEL_168:
  BYTE11(v100) = v47 | (16 * v45);
  v48 = v6[28];
  if ( !(_WORD)v48 )
    goto LABEL_239;
  if ( (unsigned __int16)(v48 - 48) <= 9u )
    goto LABEL_174;
  if ( (unsigned __int16)(v48 - 97) <= 5u )
  {
    LOBYTE(v48) = v48 - 87;
    goto LABEL_174;
  }
  if ( (unsigned __int16)(v48 - 65) > 5u )
  {
LABEL_239:
    v74 = wil::verify_hresult<long>(2147942487LL, v48);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v74,
      v100);
  }
  LOBYTE(v48) = v48 - 55;
LABEL_174:
  v49 = v6[29];
  if ( !v49 )
    goto LABEL_238;
  if ( (unsigned __int16)(v49 - 48) > 9u )
  {
    if ( (unsigned __int16)(v49 - 97) <= 5u )
    {
      v50 = v49 - 87;
      goto LABEL_181;
    }
    if ( (unsigned __int16)(v49 - 65) <= 5u )
    {
      v50 = v49 - 55;
      goto LABEL_181;
    }
LABEL_238:
    v73 = wil::verify_hresult<long>(2147942487LL, v48);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v73,
      v100);
  }
  v50 = v49 - 48;
LABEL_181:
  BYTE12(v100) = v50 | (16 * v48);
  v51 = v6[30];
  if ( !(_WORD)v51 )
    goto LABEL_237;
  if ( (unsigned __int16)(v51 - 48) <= 9u )
    goto LABEL_187;
  if ( (unsigned __int16)(v51 - 97) <= 5u )
  {
    LOBYTE(v51) = v51 - 87;
    goto LABEL_187;
  }
  if ( (unsigned __int16)(v51 - 65) > 5u )
  {
LABEL_237:
    v72 = wil::verify_hresult<long>(2147942487LL, v51);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v72,
      v100);
  }
  LOBYTE(v51) = v51 - 55;
LABEL_187:
  v52 = v6[31];
  if ( !v52 )
    goto LABEL_236;
  if ( (unsigned __int16)(v52 - 48) > 9u )
  {
    if ( (unsigned __int16)(v52 - 97) <= 5u )
    {
      v53 = v52 - 87;
      goto LABEL_194;
    }
    if ( (unsigned __int16)(v52 - 65) <= 5u )
    {
      v53 = v52 - 55;
      goto LABEL_194;
    }
LABEL_236:
    v71 = wil::verify_hresult<long>(2147942487LL, v51);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v71,
      v100);
  }
  v53 = v52 - 48;
LABEL_194:
  BYTE13(v100) = v53 | (16 * v51);
  v54 = v6[32];
  if ( !(_WORD)v54 )
    goto LABEL_235;
  if ( (unsigned __int16)(v54 - 48) <= 9u )
    goto LABEL_200;
  if ( (unsigned __int16)(v54 - 97) <= 5u )
  {
    LOBYTE(v54) = v54 - 87;
    goto LABEL_200;
  }
  if ( (unsigned __int16)(v54 - 65) > 5u )
  {
LABEL_235:
    v70 = wil::verify_hresult<long>(2147942487LL, v54);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v70,
      v100);
  }
  LOBYTE(v54) = v54 - 55;
LABEL_200:
  v55 = v6[33];
  if ( !v55 )
    goto LABEL_234;
  if ( (unsigned __int16)(v55 - 48) > 9u )
  {
    if ( (unsigned __int16)(v55 - 97) <= 5u )
    {
      v56 = v55 - 87;
      goto LABEL_207;
    }
    if ( (unsigned __int16)(v55 - 65) <= 5u )
    {
      v56 = v55 - 55;
      goto LABEL_207;
    }
LABEL_234:
    v69 = wil::verify_hresult<long>(2147942487LL, v54);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v69,
      v100);
  }
  v56 = v55 - 48;
LABEL_207:
  BYTE14(v100) = v56 | (16 * v54);
  v57 = v6[34];
  if ( !(_WORD)v57 )
    goto LABEL_233;
  if ( (unsigned __int16)(v57 - 48) <= 9u )
    goto LABEL_213;
  if ( (unsigned __int16)(v57 - 97) <= 5u )
  {
    LOBYTE(v57) = v57 - 87;
    goto LABEL_213;
  }
  if ( (unsigned __int16)(v57 - 65) > 5u )
  {
LABEL_233:
    v68 = wil::verify_hresult<long>(2147942487LL, v57);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v68,
      v100);
  }
  LOBYTE(v57) = v57 - 55;
LABEL_213:
  v58 = v6[35];
  if ( !v58 )
    goto LABEL_232;
  if ( (unsigned __int16)(v58 - 48) > 9u )
  {
    if ( (unsigned __int16)(v58 - 97) <= 5u )
    {
      v59 = v58 - 87;
      goto LABEL_220;
    }
    if ( (unsigned __int16)(v58 - 65) <= 5u )
    {
      v59 = v58 - 55;
      goto LABEL_220;
    }
LABEL_232:
    v67 = wil::verify_hresult<long>(2147942487LL, v57);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v67,
      v100);
  }
  v59 = v58 - 48;
LABEL_220:
  v60 = v6 + 36;
  LOBYTE(v57) = v59 | (16 * v57);
  HIBYTE(v100) = v57;
  if ( v4 == 123 )
  {
    if ( *v60 != 125 )
    {
      v65 = wil::verify_hresult<long>(2147942487LL, v57);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x497,
        (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
        (const char *)v65,
        v100);
    }
    ++v60;
  }
  if ( *v60 )
  {
    v66 = wil::verify_hresult<long>(2147942487LL, v57);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v66,
      v100);
  }
  *(_OWORD *)this = v100;
}

```

## disassembly

```asm
0x1400864a8  push    rbp
0x1400864aa  push    rbx
0x1400864ab  push    rsi
0x1400864ac  push    rdi
0x1400864ad  push    r12
0x1400864af  push    r13
0x1400864b1  push    r14
0x1400864b3  push    r15
0x1400864b5  mov     rbp, rsp
0x1400864b8  sub     rsp, 38h
0x1400864bc  mov     rax, rdx
0x1400864bf  mov     r15, rcx
0x1400864c2  test    rdx, rdx
0x1400864c5  jz      loc_140086EFB
0x1400864cb  movzx   r14d, word ptr [rdx]
0x1400864cf  test    r14w, r14w
0x1400864d3  jz      loc_140086EFB
0x1400864d9  cmp     r14w, 7Bh ; '{'
0x1400864de  jnz     short loc_1400864E6
0x1400864e0  movzx   edx, word ptr [rdx+2]
0x1400864e4  jmp     short loc_1400864EA
0x1400864e6  movzx   edx, r14w
0x1400864ea  lea     rcx, [rax+2]
0x1400864ee  cmovnz  rcx, rax
0x1400864f2  test    dx, dx
0x1400864f5  jz      loc_140087421
0x1400864fb  mov     r13d, 30h ; '0'
0x140086501  movzx   eax, dx
0x140086504  sub     ax, r13w
0x140086508  mov     bx, 9
0x14008650c  mov     r11w, 61h ; 'a'
0x140086511  mov     r12w, 5
0x140086516  mov     r10w, 41h ; 'A'
0x14008651b  lea     edi, [r13+27h]
0x14008651f  cmp     ax, bx
0x140086522  ja      short loc_14008652A
0x140086524  movzx   r9d, dx
0x140086528  jmp     short loc_140086559
0x14008652a  movzx   eax, dx
0x14008652d  sub     ax, r11w
0x140086531  cmp     ax, r12w
0x140086535  ja      short loc_140086540
0x140086537  movzx   r9d, dx
0x14008653b  sub     r9d, edi
0x14008653e  jmp     short loc_140086559
0x140086540  movzx   eax, dx
0x140086543  sub     ax, r10w
0x140086547  cmp     ax, r12w
0x14008654b  ja      loc_140087421
0x140086551  movzx   r9d, dx
0x140086555  sub     r9d, 37h ; '7'
0x140086559  movzx   edx, word ptr [rcx+2]
0x14008655d  test    dx, dx
0x140086560  jz      loc_1400873FE
0x140086566  movzx   eax, dx
0x140086569  sub     ax, r13w
0x14008656d  cmp     ax, bx
0x140086570  ja      short loc_140086579
0x140086572  mov     esi, edx
0x140086574  sub     esi, r13d
0x140086577  jmp     short loc_1400865A0
0x140086579  movzx   eax, dx
0x14008657c  sub     ax, r11w
0x140086580  cmp     ax, r12w
0x140086584  ja      short loc_14008658C
0x140086586  mov     esi, edx
0x140086588  sub     esi, edi
0x14008658a  jmp     short loc_1400865A0
0x14008658c  movzx   eax, dx
0x14008658f  sub     ax, r10w
0x140086593  cmp     ax, r12w
0x140086597  ja      loc_1400873FE
0x14008659d  lea     esi, [rdx-37h]
0x1400865a0  movzx   edx, word ptr [rcx+4]
0x1400865a4  test    dx, dx
0x1400865a7  jz      loc_1400873DB
0x1400865ad  movzx   eax, dx
0x1400865b0  sub     ax, r13w
0x1400865b4  cmp     ax, bx
0x1400865b7  ja      short loc_1400865C0
0x1400865b9  mov     edi, edx
0x1400865bb  sub     edi, r13d
0x1400865be  jmp     short loc_1400865E6
0x1400865c0  movzx   eax, dx
0x1400865c3  sub     ax, r11w
0x1400865c7  cmp     ax, r12w
0x1400865cb  ja      short loc_1400865D2
0x1400865cd  lea     edi, [rdx-57h]
0x1400865d0  jmp     short loc_1400865E6
0x1400865d2  movzx   eax, dx
0x1400865d5  sub     ax, r10w
0x1400865d9  cmp     ax, r12w
0x1400865dd  ja      loc_1400873DB
0x1400865e3  lea     edi, [rdx-37h]
0x1400865e6  movzx   edx, word ptr [rcx+6]
0x1400865ea  test    dx, dx
0x1400865ed  jz      loc_1400873B8
0x1400865f3  movzx   eax, dx
0x1400865f6  sub     ax, r13w
0x1400865fa  cmp     ax, bx
0x1400865fd  ja      short loc_140086606
0x1400865ff  mov     ebx, edx
0x140086601  sub     ebx, r13d
0x140086604  jmp     short loc_14008662C
0x140086606  movzx   eax, dx
0x140086609  sub     ax, r11w
0x14008660d  cmp     ax, r12w
0x140086611  ja      short loc_140086618
0x140086613  lea     ebx, [rdx-57h]
0x140086616  jmp     short loc_14008662C
0x140086618  movzx   eax, dx
0x14008661b  sub     ax, r10w
0x14008661f  cmp     ax, r12w
0x140086623  ja      loc_1400873B8
0x140086629  lea     ebx, [rdx-37h]
0x14008662c  movzx   edx, word ptr [rcx+8]
0x140086630  test    dx, dx
0x140086633  jz      loc_140087395
0x140086639  movzx   eax, dx
0x14008663c  sub     ax, r13w
0x140086640  cmp     ax, 9
0x140086644  ja      short loc_14008664E
0x140086646  mov     r11d, edx
0x140086649  sub     r11d, r13d
0x14008664c  jmp     short loc_140086676
0x14008664e  movzx   eax, dx
0x140086651  sub     ax, r11w
0x140086655  cmp     ax, r12w
0x140086659  ja      short loc_140086661
0x14008665b  lea     r11d, [rdx-57h]
0x14008665f  jmp     short loc_140086676
0x140086661  movzx   eax, dx
0x140086664  sub     ax, r10w
0x140086668  cmp     ax, r12w
0x14008666c  ja      loc_140087395
0x140086672  lea     r11d, [rdx-37h]
0x140086676  movzx   edx, word ptr [rcx+0Ah]
0x14008667a  test    dx, dx
0x14008667d  jz      loc_140087372
0x140086683  movzx   eax, dx
0x140086686  sub     ax, r13w
0x14008668a  cmp     ax, 9
0x14008668e  ja      short loc_140086698
0x140086690  mov     r10d, edx
0x140086693  sub     r10d, r13d
0x140086696  jmp     short loc_1400866BC
0x140086698  lea     eax, [rdx-61h]
0x14008669b  cmp     ax, r12w
0x14008669f  ja      short loc_1400866A7
0x1400866a1  lea     r10d, [rdx-57h]
0x1400866a5  jmp     short loc_1400866BC
0x1400866a7  movzx   eax, dx
0x1400866aa  sub     ax, r10w
0x1400866ae  cmp     ax, r12w
0x1400866b2  ja      loc_140087372
0x1400866b8  lea     r10d, [rdx-37h]
0x1400866bc  movzx   edx, word ptr [rcx+0Ch]
0x1400866c0  test    dx, dx
0x1400866c3  jz      loc_14008734F
0x1400866c9  movzx   eax, dx
0x1400866cc  sub     ax, r13w
0x1400866d0  cmp     ax, 9
0x1400866d4  ja      short loc_1400866DE
0x1400866d6  mov     r8d, edx
0x1400866d9  sub     r8d, r13d
0x1400866dc  jmp     short loc_1400866FE
0x1400866de  lea     eax, [rdx-61h]
0x1400866e1  cmp     ax, r12w
0x1400866e5  ja      short loc_1400866ED
0x1400866e7  lea     r8d, [rdx-57h]
0x1400866eb  jmp     short loc_1400866FE
0x1400866ed  lea     eax, [rdx-41h]
0x1400866f0  cmp     ax, r12w
0x1400866f4  ja      loc_14008734F
0x1400866fa  lea     r8d, [rdx-37h]
0x1400866fe  movzx   edx, word ptr [rcx+0Eh]
0x140086702  test    dx, dx
0x140086705  jz      loc_14008732C
0x14008670b  movzx   eax, dx
0x14008670e  sub     ax, r13w
0x140086712  cmp     ax, 9
0x140086716  ja      short loc_14008671D
0x140086718  sub     edx, r13d
0x14008671b  jmp     short loc_14008673B
0x14008671d  lea     eax, [rdx-61h]
0x140086720  cmp     ax, r12w
0x140086724  ja      short loc_14008672B
0x140086726  sub     edx, 57h ; 'W'
0x140086729  jmp     short loc_14008673B
0x14008672b  lea     eax, [rdx-41h]
0x14008672e  cmp     ax, r12w
0x140086732  ja      loc_14008732C
0x140086738  sub     edx, 37h ; '7'
0x14008673b  shl     r9d, 4
0x14008673f  or      r9d, esi
0x140086742  movzx   eax, dil
0x140086746  shl     r9d, 4
0x14008674a  or      r9d, eax
0x14008674d  movzx   eax, bl
0x140086750  shl     r9d, 4
0x140086754  or      r9d, eax
0x140086757  movzx   eax, r11b
0x14008675b  shl     r9d, 4
0x14008675f  or      r9d, eax
0x140086762  movzx   eax, r10b
0x140086766  shl     r9d, 4
0x14008676a  or      r9d, eax
0x14008676d  movzx   eax, r8b
0x140086771  shl     r9d, 4
0x140086775  or      r9d, eax
0x140086778  movzx   eax, dl
0x14008677b  shl     r9d, 4
0x14008677f  or      r9d, eax
0x140086782  cmp     word ptr [rcx+10h], 2Dh ; '-'
0x140086787  mov     dword ptr [rbp+var_18], r9d
0x14008678b  jnz     loc_140086F12
0x140086791  movzx   edx, word ptr [rcx+12h]
0x140086795  xor     r11d, r11d
0x140086798  test    dx, dx
0x14008679b  jz      loc_140087309
0x1400867a1  movzx   eax, dx
0x1400867a4  mov     si, 9
0x1400867a8  sub     ax, r13w
0x1400867ac  mov     di, 61h ; 'a'
0x1400867b0  mov     bx, 41h ; 'A'
0x1400867b4  cmp     ax, si
0x1400867b7  jbe     short loc_1400867E3
0x1400867b9  movzx   eax, dx
0x1400867bc  sub     ax, di
0x1400867bf  cmp     ax, r12w
0x1400867c3  ja      short loc_1400867CF
0x1400867c5  lea     r10d, [r11+57h]
0x1400867c9  sub     dx, r10w
0x1400867cd  jmp     short loc_1400867E9
0x1400867cf  movzx   eax, dx
0x1400867d2  sub     ax, bx
0x1400867d5  cmp     ax, r12w
0x1400867d9  ja      loc_140087309
0x1400867df  sub     dx, 37h ; '7'
0x1400867e3  mov     r10d, 57h ; 'W'
0x1400867e9  movzx   r8d, word ptr [rcx+14h]
0x1400867ee  test    r8w, r8w
0x1400867f2  jz      loc_1400872E6
0x1400867f8  movzx   r9d, r8w
0x1400867fc  sub     r9w, r13w
0x140086800  cmp     r9w, si
0x140086804  jbe     short loc_140086832
0x140086806  movzx   eax, r8w
0x14008680a  sub     ax, di
0x14008680d  cmp     ax, r12w
0x140086811  ja      short loc_14008681D
0x140086813  movzx   r9d, r8w
0x140086817  sub     r9w, r10w
0x14008681b  jmp     short loc_140086832
0x14008681d  movzx   eax, r8w
0x140086821  sub     ax, bx
0x140086824  cmp     ax, r12w
0x140086828  ja      loc_1400872E6
0x14008682e  lea     r9d, [r8-37h]
0x140086832  movzx   r10d, word ptr [rcx+16h]
0x140086837  test    r10w, r10w
0x14008683b  jz      loc_1400872C3
0x140086841  movzx   r8d, r10w
0x140086845  sub     r8w, r13w
0x140086849  cmp     r8w, si
0x14008684d  jbe     short loc_140086877
0x14008684f  movzx   eax, r10w
0x140086853  sub     ax, di
0x140086856  cmp     ax, r12w
0x14008685a  ja      short loc_140086862
0x14008685c  lea     r8d, [r10-57h]
0x140086860  jmp     short loc_140086877
0x140086862  movzx   eax, r10w
0x140086866  sub     ax, bx
0x140086869  cmp     ax, r12w
0x14008686d  ja      loc_1400872C3
0x140086873  lea     r8d, [r10-37h]
0x140086877  movzx   r10d, word ptr [rcx+18h]
0x14008687c  test    r10w, r10w
0x140086880  jz      loc_1400872A0
0x140086886  movzx   eax, r10w
0x14008688a  sub     ax, r13w
0x14008688e  cmp     ax, si
0x140086891  jbe     short loc_1400868C1
0x140086893  movzx   eax, r10w
0x140086897  sub     ax, di
0x14008689a  cmp     ax, r12w
0x14008689e  movzx   eax, r10w
0x1400868a2  ja      short loc_1400868B0
0x1400868a4  mov     r10d, 57h ; 'W'
0x1400868aa  sub     ax, r10w
0x1400868ae  jmp     short loc_1400868C7
0x1400868b0  sub     ax, bx
0x1400868b3  cmp     ax, r12w
0x1400868b7  ja      loc_1400872A0
0x1400868bd  lea     eax, [r10-37h]
0x1400868c1  mov     r10d, 57h ; 'W'
0x1400868c7  shl     dx, 4
0x1400868cb  or      dx, r9w
0x1400868cf  mov     r9d, 0FFh
  ... truncated ...
```
