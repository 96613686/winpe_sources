# Vml::VmGuid::Assign(ushort const * const)

- ea: `0x1800078bc`
- end: `0x180008859`
- name: `?Assign@VmGuid@Vml@@QEAAXQEBG@Z`
- size: `3997`
- prototype: `void __fastcall(Vml::VmGuid *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002460`

## callees

- `0x180006158`
- `0x1800078bc`
- `0x18000d108`

## string_xrefs

- `0x180008335`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008358`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000837b`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000839e`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800083c1`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800083e4`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008407`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000842a`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000844d`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008470`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008493`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800084b6`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800084d9`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800084fc`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000851f`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008542`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008565`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008588`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800085ab`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800085ce`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800085f1`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008614`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008637`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000865a`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000867d`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800086a0`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800086c3`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800086e6`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008709`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000872c`: `onecore\vm\common\vml\VmGuid.h`
- `0x18000874f`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008772`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008795`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800087b8`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800087db`: `onecore\vm\common\vml\VmGuid.h`
- `0x1800087fe`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008821`: `onecore\vm\common\vml\VmGuid.h`
- `0x180008844`: `onecore\vm\common\vml\VmGuid.h`

## pseudocode

```c
void __fastcall Vml::VmGuid::Assign(Vml::VmGuid *this, const unsigned __int16 *const a2)
{
  unsigned __int16 v4; // r14
  unsigned __int16 v5; // dx
  const unsigned __int16 *v6; // rcx
  int v7; // r9d
  int v8; // edx
  int v9; // esi
  unsigned __int16 v10; // dx
  unsigned __int8 v11; // di
  unsigned __int16 v12; // dx
  unsigned __int8 v13; // bl
  unsigned __int16 v14; // dx
  unsigned __int8 v15; // r11
  unsigned __int16 v16; // dx
  unsigned __int8 v17; // r10
  unsigned __int16 v18; // dx
  unsigned __int8 v19; // r8
  unsigned __int16 v20; // dx
  unsigned __int8 v21; // dl
  unsigned __int16 v22; // dx
  unsigned __int16 v23; // r8
  __int16 v24; // r9
  unsigned __int16 v25; // r10
  unsigned __int8 v26; // r8
  unsigned __int16 v27; // r10
  unsigned __int8 v28; // al
  unsigned __int16 v29; // dx
  unsigned __int16 v30; // r8
  __int16 v31; // r9
  unsigned __int16 v32; // r10
  unsigned __int8 v33; // r8
  unsigned __int16 v34; // r10
  unsigned __int8 v35; // al
  unsigned __int16 v36; // dx
  unsigned __int16 v37; // r8
  char v38; // r8
  unsigned __int16 v39; // dx
  unsigned __int16 v40; // r8
  char v41; // r8
  unsigned __int16 v42; // dx
  unsigned __int16 v43; // r8
  char v44; // r8
  unsigned __int16 v45; // dx
  unsigned __int16 v46; // r8
  char v47; // r8
  unsigned __int16 v48; // dx
  unsigned __int16 v49; // r8
  char v50; // r8
  unsigned __int16 v51; // dx
  unsigned __int16 v52; // r8
  char v53; // r8
  unsigned __int16 v54; // dx
  unsigned __int16 v55; // r8
  char v56; // r8
  unsigned __int16 v57; // dx
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
    v5 = *a2;
  v6 = a2 + 1;
  if ( v4 != 123 )
    v6 = a2;
  if ( !v5 )
    goto LABEL_263;
  if ( (unsigned __int16)(v5 - 48) <= 9u )
  {
    v7 = v5;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(v5 - 97) <= 5u )
  {
    v7 = v5 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(v5 - 65) > 5u )
  {
LABEL_263:
    v98 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v98,
      v99);
  }
  v7 = v5 - 55;
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
    v97 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v10 )
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
    v96 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v12 )
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
    v95 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v14 )
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
    v94 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v16 )
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
    v93 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v18 )
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
    v92 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v20 )
    goto LABEL_256;
  if ( (unsigned __int16)(v20 - 48) > 9u )
  {
    if ( (unsigned __int16)(v20 - 97) <= 5u )
    {
      v21 = v20 - 87;
      goto LABEL_64;
    }
    if ( (unsigned __int16)(v20 - 65) <= 5u )
    {
      v21 = v20 - 55;
      goto LABEL_64;
    }
LABEL_256:
    v91 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v91,
      v99);
  }
  v21 = v20 - 48;
LABEL_64:
  LODWORD(v100) = v21
                | (16 * (v19 | (16 * (v17 | (16 * (v15 | (16 * (v13 | (16 * (v11 | (16 * (v9 | (16 * v7)))))))))))));
  if ( v6[8] != 45 )
  {
    v61 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44B,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v61,
      v100);
  }
  v22 = v6[9];
  if ( !v22 )
    goto LABEL_255;
  if ( (unsigned __int16)(v22 - 48) <= 9u )
    goto LABEL_71;
  if ( (unsigned __int16)(v22 - 97) <= 5u )
  {
    v22 -= 87;
    goto LABEL_71;
  }
  if ( (unsigned __int16)(v22 - 65) > 5u )
  {
LABEL_255:
    v90 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v90,
      v100);
  }
  v22 -= 55;
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
    v89 = wil::verify_hresult<long>(2147942487LL);
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
    v88 = wil::verify_hresult<long>(2147942487LL);
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
    v87 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v87,
      v100);
  }
LABEL_89:
  WORD2(v100) = v28 | (unsigned __int16)(16 * (v26 | (unsigned __int16)(16 * (v24 | (16 * v22)))));
  if ( v6[13] != 45 )
  {
    v62 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v62,
      v100);
  }
  v29 = v6[14];
  if ( !v29 )
    goto LABEL_251;
  if ( (unsigned __int16)(v29 - 48) <= 9u )
    goto LABEL_96;
  if ( (unsigned __int16)(v29 - 97) <= 5u )
  {
    v29 -= 87;
    goto LABEL_96;
  }
  if ( (unsigned __int16)(v29 - 65) > 5u )
  {
LABEL_251:
    v86 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v86,
      v100);
  }
  v29 -= 55;
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
    v85 = wil::verify_hresult<long>(2147942487LL);
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
    v84 = wil::verify_hresult<long>(2147942487LL);
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
    v83 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v83,
      v100);
  }
LABEL_114:
  WORD3(v100) = v35 | (unsigned __int16)(16 * (v33 | (unsigned __int16)(16 * (v31 | (16 * v29)))));
  if ( v6[18] != 45 )
  {
    v63 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v63,
      v100);
  }
  v36 = v6[19];
  if ( !v36 )
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
    v82 = wil::verify_hresult<long>(2147942487LL);
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
    v81 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v39 )
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
    v80 = wil::verify_hresult<long>(2147942487LL);
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
    v79 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v79,
      v100);
  }
  v41 = v40 - 48;
LABEL_141:
  BYTE9(v100) = v41 | (16 * v39);
  if ( v6[23] != 45 )
  {
    v64 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v64,
      v100);
  }
  v42 = v6[24];
  if ( !v42 )
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
    v78 = wil::verify_hresult<long>(2147942487LL);
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
    v77 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v45 )
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
    v76 = wil::verify_hresult<long>(2147942487LL);
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
    v75 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v48 )
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
    v74 = wil::verify_hresult<long>(2147942487LL);
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
    v73 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v51 )
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
    v72 = wil::verify_hresult<long>(2147942487LL);
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
    v71 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v54 )
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
    v70 = wil::verify_hresult<long>(2147942487LL);
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
    v69 = wil::verify_hresult<long>(2147942487LL);
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
  if ( !v57 )
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
    v68 = wil::verify_hresult<long>(2147942487LL);
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
    v67 = wil::verify_hresult<long>(2147942487LL);
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
  if ( v4 == 123 )
  {
    if ( *v60 != 125 )
    {
      v65 = wil::verify_hresult<long>(2147942487LL);
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
    v66 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v66,
      v100);
  }
  HIBYTE(v100) = v59 | (16 * v57);
  *(_OWORD *)this = v100;
}

```

## disassembly

```asm
0x1800078bc  push    rbp
0x1800078be  push    rbx
0x1800078bf  push    rsi
0x1800078c0  push    rdi
0x1800078c1  push    r12
0x1800078c3  push    r13
0x1800078c5  push    r14
0x1800078c7  push    r15
0x1800078c9  mov     rbp, rsp
0x1800078cc  sub     rsp, 38h
0x1800078d0  mov     rax, rdx
0x1800078d3  mov     r15, rcx
0x1800078d6  test    rdx, rdx
0x1800078d9  jz      loc_18000830F
0x1800078df  movzx   r14d, word ptr [rdx]
0x1800078e3  test    r14w, r14w
0x1800078e7  jz      loc_18000830F
0x1800078ed  cmp     r14w, 7Bh ; '{'
0x1800078f2  jnz     short loc_1800078FA
0x1800078f4  movzx   edx, word ptr [rdx+2]
0x1800078f8  jmp     short loc_1800078FE
0x1800078fa  movzx   edx, r14w
0x1800078fe  lea     rcx, [rax+2]
0x180007902  cmovnz  rcx, rax
0x180007906  test    dx, dx
0x180007909  jz      loc_180008836
0x18000790f  mov     r13d, 30h ; '0'
0x180007915  movzx   eax, dx
0x180007918  sub     ax, r13w
0x18000791c  mov     bx, 9
0x180007920  mov     r11w, 61h ; 'a'
0x180007925  mov     r12w, 5
0x18000792a  mov     r10w, 41h ; 'A'
0x18000792f  lea     edi, [r13+27h]
0x180007933  cmp     ax, bx
0x180007936  ja      short loc_18000793E
0x180007938  movzx   r9d, dx
0x18000793c  jmp     short loc_18000796D
0x18000793e  movzx   eax, dx
0x180007941  sub     ax, r11w
0x180007945  cmp     ax, r12w
0x180007949  ja      short loc_180007954
0x18000794b  movzx   r9d, dx
0x18000794f  sub     r9d, edi
0x180007952  jmp     short loc_18000796D
0x180007954  movzx   eax, dx
0x180007957  sub     ax, r10w
0x18000795b  cmp     ax, r12w
0x18000795f  ja      loc_180008836
0x180007965  movzx   r9d, dx
0x180007969  sub     r9d, 37h ; '7'
0x18000796d  movzx   edx, word ptr [rcx+2]
0x180007971  test    dx, dx
0x180007974  jz      loc_180008813
0x18000797a  movzx   eax, dx
0x18000797d  sub     ax, r13w
0x180007981  cmp     ax, bx
0x180007984  ja      short loc_18000798D
0x180007986  mov     esi, edx
0x180007988  sub     esi, r13d
0x18000798b  jmp     short loc_1800079B4
0x18000798d  movzx   eax, dx
0x180007990  sub     ax, r11w
0x180007994  cmp     ax, r12w
0x180007998  ja      short loc_1800079A0
0x18000799a  mov     esi, edx
0x18000799c  sub     esi, edi
0x18000799e  jmp     short loc_1800079B4
0x1800079a0  movzx   eax, dx
0x1800079a3  sub     ax, r10w
0x1800079a7  cmp     ax, r12w
0x1800079ab  ja      loc_180008813
0x1800079b1  lea     esi, [rdx-37h]
0x1800079b4  movzx   edx, word ptr [rcx+4]
0x1800079b8  test    dx, dx
0x1800079bb  jz      loc_1800087F0
0x1800079c1  movzx   eax, dx
0x1800079c4  sub     ax, r13w
0x1800079c8  cmp     ax, bx
0x1800079cb  ja      short loc_1800079D4
0x1800079cd  mov     edi, edx
0x1800079cf  sub     edi, r13d
0x1800079d2  jmp     short loc_1800079FA
0x1800079d4  movzx   eax, dx
0x1800079d7  sub     ax, r11w
0x1800079db  cmp     ax, r12w
0x1800079df  ja      short loc_1800079E6
0x1800079e1  lea     edi, [rdx-57h]
0x1800079e4  jmp     short loc_1800079FA
0x1800079e6  movzx   eax, dx
0x1800079e9  sub     ax, r10w
0x1800079ed  cmp     ax, r12w
0x1800079f1  ja      loc_1800087F0
0x1800079f7  lea     edi, [rdx-37h]
0x1800079fa  movzx   edx, word ptr [rcx+6]
0x1800079fe  test    dx, dx
0x180007a01  jz      loc_1800087CD
0x180007a07  movzx   eax, dx
0x180007a0a  sub     ax, r13w
0x180007a0e  cmp     ax, bx
0x180007a11  ja      short loc_180007A1A
0x180007a13  mov     ebx, edx
0x180007a15  sub     ebx, r13d
0x180007a18  jmp     short loc_180007A40
0x180007a1a  movzx   eax, dx
0x180007a1d  sub     ax, r11w
0x180007a21  cmp     ax, r12w
0x180007a25  ja      short loc_180007A2C
0x180007a27  lea     ebx, [rdx-57h]
0x180007a2a  jmp     short loc_180007A40
0x180007a2c  movzx   eax, dx
0x180007a2f  sub     ax, r10w
0x180007a33  cmp     ax, r12w
0x180007a37  ja      loc_1800087CD
0x180007a3d  lea     ebx, [rdx-37h]
0x180007a40  movzx   edx, word ptr [rcx+8]
0x180007a44  test    dx, dx
0x180007a47  jz      loc_1800087AA
0x180007a4d  movzx   eax, dx
0x180007a50  sub     ax, r13w
0x180007a54  cmp     ax, 9
0x180007a58  ja      short loc_180007A62
0x180007a5a  mov     r11d, edx
0x180007a5d  sub     r11d, r13d
0x180007a60  jmp     short loc_180007A8A
0x180007a62  movzx   eax, dx
0x180007a65  sub     ax, r11w
0x180007a69  cmp     ax, r12w
0x180007a6d  ja      short loc_180007A75
0x180007a6f  lea     r11d, [rdx-57h]
0x180007a73  jmp     short loc_180007A8A
0x180007a75  movzx   eax, dx
0x180007a78  sub     ax, r10w
0x180007a7c  cmp     ax, r12w
0x180007a80  ja      loc_1800087AA
0x180007a86  lea     r11d, [rdx-37h]
0x180007a8a  movzx   edx, word ptr [rcx+0Ah]
0x180007a8e  test    dx, dx
0x180007a91  jz      loc_180008787
0x180007a97  movzx   eax, dx
0x180007a9a  sub     ax, r13w
0x180007a9e  cmp     ax, 9
0x180007aa2  ja      short loc_180007AAC
0x180007aa4  mov     r10d, edx
0x180007aa7  sub     r10d, r13d
0x180007aaa  jmp     short loc_180007AD0
0x180007aac  lea     eax, [rdx-61h]
0x180007aaf  cmp     ax, r12w
0x180007ab3  ja      short loc_180007ABB
0x180007ab5  lea     r10d, [rdx-57h]
0x180007ab9  jmp     short loc_180007AD0
0x180007abb  movzx   eax, dx
0x180007abe  sub     ax, r10w
0x180007ac2  cmp     ax, r12w
0x180007ac6  ja      loc_180008787
0x180007acc  lea     r10d, [rdx-37h]
0x180007ad0  movzx   edx, word ptr [rcx+0Ch]
0x180007ad4  test    dx, dx
0x180007ad7  jz      loc_180008764
0x180007add  movzx   eax, dx
0x180007ae0  sub     ax, r13w
0x180007ae4  cmp     ax, 9
0x180007ae8  ja      short loc_180007AF2
0x180007aea  mov     r8d, edx
0x180007aed  sub     r8d, r13d
0x180007af0  jmp     short loc_180007B12
0x180007af2  lea     eax, [rdx-61h]
0x180007af5  cmp     ax, r12w
0x180007af9  ja      short loc_180007B01
0x180007afb  lea     r8d, [rdx-57h]
0x180007aff  jmp     short loc_180007B12
0x180007b01  lea     eax, [rdx-41h]
0x180007b04  cmp     ax, r12w
0x180007b08  ja      loc_180008764
0x180007b0e  lea     r8d, [rdx-37h]
0x180007b12  movzx   edx, word ptr [rcx+0Eh]
0x180007b16  test    dx, dx
0x180007b19  jz      loc_180008741
0x180007b1f  movzx   eax, dx
0x180007b22  sub     ax, r13w
0x180007b26  cmp     ax, 9
0x180007b2a  ja      short loc_180007B31
0x180007b2c  sub     edx, r13d
0x180007b2f  jmp     short loc_180007B4F
0x180007b31  lea     eax, [rdx-61h]
0x180007b34  cmp     ax, r12w
0x180007b38  ja      short loc_180007B3F
0x180007b3a  sub     edx, 57h ; 'W'
0x180007b3d  jmp     short loc_180007B4F
0x180007b3f  lea     eax, [rdx-41h]
0x180007b42  cmp     ax, r12w
0x180007b46  ja      loc_180008741
0x180007b4c  sub     edx, 37h ; '7'
0x180007b4f  shl     r9d, 4
0x180007b53  or      r9d, esi
0x180007b56  movzx   eax, dil
0x180007b5a  shl     r9d, 4
0x180007b5e  or      r9d, eax
0x180007b61  movzx   eax, bl
0x180007b64  shl     r9d, 4
0x180007b68  or      r9d, eax
0x180007b6b  movzx   eax, r11b
0x180007b6f  shl     r9d, 4
0x180007b73  or      r9d, eax
0x180007b76  movzx   eax, r10b
0x180007b7a  shl     r9d, 4
0x180007b7e  or      r9d, eax
0x180007b81  movzx   eax, r8b
0x180007b85  shl     r9d, 4
0x180007b89  or      r9d, eax
0x180007b8c  movzx   eax, dl
0x180007b8f  shl     r9d, 4
0x180007b93  or      r9d, eax
0x180007b96  cmp     word ptr [rcx+10h], 2Dh ; '-'
0x180007b9b  mov     dword ptr [rbp+var_18], r9d
0x180007b9f  jnz     loc_180008327
0x180007ba5  movzx   edx, word ptr [rcx+12h]
0x180007ba9  xor     r11d, r11d
0x180007bac  test    dx, dx
0x180007baf  jz      loc_18000871E
0x180007bb5  movzx   eax, dx
0x180007bb8  mov     si, 9
0x180007bbc  sub     ax, r13w
0x180007bc0  mov     di, 61h ; 'a'
0x180007bc4  mov     bx, 41h ; 'A'
0x180007bc8  cmp     ax, si
0x180007bcb  jbe     short loc_180007BF7
0x180007bcd  movzx   eax, dx
0x180007bd0  sub     ax, di
0x180007bd3  cmp     ax, r12w
0x180007bd7  ja      short loc_180007BE3
0x180007bd9  lea     r10d, [r11+57h]
0x180007bdd  sub     dx, r10w
0x180007be1  jmp     short loc_180007BFD
0x180007be3  movzx   eax, dx
0x180007be6  sub     ax, bx
0x180007be9  cmp     ax, r12w
0x180007bed  ja      loc_18000871E
0x180007bf3  sub     dx, 37h ; '7'
0x180007bf7  mov     r10d, 57h ; 'W'
0x180007bfd  movzx   r8d, word ptr [rcx+14h]
0x180007c02  test    r8w, r8w
0x180007c06  jz      loc_1800086FB
0x180007c0c  movzx   r9d, r8w
0x180007c10  sub     r9w, r13w
0x180007c14  cmp     r9w, si
0x180007c18  jbe     short loc_180007C46
0x180007c1a  movzx   eax, r8w
0x180007c1e  sub     ax, di
0x180007c21  cmp     ax, r12w
0x180007c25  ja      short loc_180007C31
0x180007c27  movzx   r9d, r8w
0x180007c2b  sub     r9w, r10w
0x180007c2f  jmp     short loc_180007C46
0x180007c31  movzx   eax, r8w
0x180007c35  sub     ax, bx
0x180007c38  cmp     ax, r12w
0x180007c3c  ja      loc_1800086FB
0x180007c42  lea     r9d, [r8-37h]
0x180007c46  movzx   r10d, word ptr [rcx+16h]
0x180007c4b  test    r10w, r10w
0x180007c4f  jz      loc_1800086D8
0x180007c55  movzx   r8d, r10w
0x180007c59  sub     r8w, r13w
0x180007c5d  cmp     r8w, si
0x180007c61  jbe     short loc_180007C8B
0x180007c63  movzx   eax, r10w
0x180007c67  sub     ax, di
0x180007c6a  cmp     ax, r12w
0x180007c6e  ja      short loc_180007C76
0x180007c70  lea     r8d, [r10-57h]
0x180007c74  jmp     short loc_180007C8B
0x180007c76  movzx   eax, r10w
0x180007c7a  sub     ax, bx
0x180007c7d  cmp     ax, r12w
0x180007c81  ja      loc_1800086D8
0x180007c87  lea     r8d, [r10-37h]
0x180007c8b  movzx   r10d, word ptr [rcx+18h]
0x180007c90  test    r10w, r10w
0x180007c94  jz      loc_1800086B5
0x180007c9a  movzx   eax, r10w
0x180007c9e  sub     ax, r13w
0x180007ca2  cmp     ax, si
0x180007ca5  jbe     short loc_180007CD5
0x180007ca7  movzx   eax, r10w
0x180007cab  sub     ax, di
0x180007cae  cmp     ax, r12w
0x180007cb2  movzx   eax, r10w
0x180007cb6  ja      short loc_180007CC4
0x180007cb8  mov     r10d, 57h ; 'W'
0x180007cbe  sub     ax, r10w
0x180007cc2  jmp     short loc_180007CDB
0x180007cc4  sub     ax, bx
0x180007cc7  cmp     ax, r12w
0x180007ccb  ja      loc_1800086B5
0x180007cd1  lea     eax, [r10-37h]
0x180007cd5  mov     r10d, 57h ; 'W'
0x180007cdb  shl     dx, 4
0x180007cdf  or      dx, r9w
0x180007ce3  mov     r9d, 0FFh
  ... truncated ...
```
