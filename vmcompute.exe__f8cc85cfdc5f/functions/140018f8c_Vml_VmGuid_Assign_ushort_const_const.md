# Vml::VmGuid::Assign(ushort const * const)

- ea: `0x140018f8c`
- end: `0x14001a00e`
- name: `?Assign@VmGuid@Vml@@QEAAXQEBG@Z`
- size: `4226`
- prototype: `void __fastcall(Vml::VmGuid *__hidden this, const unsigned __int16 *const)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400185ac`
- `0x140070d60`
- `0x140089c30`
- `0x140092d38`
- `0x1400d995c`
- `0x1400e4348`
- `0x1400f8ab8`
- `0x1401197f4`
- `0x1401198b4`
- `0x14022624c`

## callees

- `0x140018f8c`
- `0x1400c40e0`

## string_xrefs

- `0x140019bdb`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019bf7`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019c13`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019c2f`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019c51`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019c76`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019c92`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019cae`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019cca`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019ce6`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019d02`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019d1e`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019d3a`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019d56`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019d72`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019d8e`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019daa`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019dc6`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019de2`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019dfe`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019e1a`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019e36`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019e52`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019e6e`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019e8a`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019ea6`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019ec2`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019ede`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019efa`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019f16`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019f32`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019f4e`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019f6a`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019f86`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019fa2`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019fbe`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019fda`: `onecore\vm\common\vml\VmGuid.h`
- `0x140019ff6`: `onecore\vm\common\vml\VmGuid.h`

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
  int v61; // [rsp+20h] [rbp-18h]
  __int128 v62; // [rsp+20h] [rbp-18h]
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
    goto LABEL_10;
  }
  if ( (unsigned __int16)(v5 - 97) > 5u )
  {
    if ( (unsigned __int16)(v5 - 65) <= 5u )
    {
      v7 = v5 - 55;
      goto LABEL_10;
    }
LABEL_263:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v7 = v5 - 87;
LABEL_10:
  v8 = v6[1];
  if ( !(_WORD)v8 )
    goto LABEL_262;
  if ( (unsigned __int16)(v8 - 48) <= 9u )
  {
    v9 = v8 - 48;
    goto LABEL_13;
  }
  if ( (unsigned __int16)(v8 - 97) > 5u )
  {
    if ( (unsigned __int16)(v8 - 65) <= 5u )
    {
      v9 = v8 - 55;
      goto LABEL_13;
    }
LABEL_262:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v9 = v8 - 87;
LABEL_13:
  v10 = v6[2];
  if ( !v10 )
    goto LABEL_261;
  if ( (unsigned __int16)(v10 - 48) <= 9u )
  {
    v11 = v10 - 48;
    goto LABEL_16;
  }
  if ( (unsigned __int16)(v10 - 97) > 5u )
  {
    if ( (unsigned __int16)(v10 - 65) <= 5u )
    {
      v11 = v10 - 55;
      goto LABEL_16;
    }
LABEL_261:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v11 = v10 - 87;
LABEL_16:
  v12 = v6[3];
  if ( !v12 )
    goto LABEL_260;
  if ( (unsigned __int16)(v12 - 48) <= 9u )
  {
    v13 = v12 - 48;
    goto LABEL_19;
  }
  if ( (unsigned __int16)(v12 - 97) > 5u )
  {
    if ( (unsigned __int16)(v12 - 65) <= 5u )
    {
      v13 = v12 - 55;
      goto LABEL_19;
    }
LABEL_260:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v13 = v12 - 87;
LABEL_19:
  v14 = v6[4];
  if ( !v14 )
    goto LABEL_259;
  if ( (unsigned __int16)(v14 - 48) <= 9u )
  {
    v15 = v14 - 48;
    goto LABEL_22;
  }
  if ( (unsigned __int16)(v14 - 97) > 5u )
  {
    if ( (unsigned __int16)(v14 - 65) <= 5u )
    {
      v15 = v14 - 55;
      goto LABEL_22;
    }
LABEL_259:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v15 = v14 - 87;
LABEL_22:
  v16 = v6[5];
  if ( !v16 )
    goto LABEL_258;
  if ( (unsigned __int16)(v16 - 48) <= 9u )
  {
    v17 = v16 - 48;
    goto LABEL_25;
  }
  if ( (unsigned __int16)(v16 - 97) > 5u )
  {
    if ( (unsigned __int16)(v16 - 65) <= 5u )
    {
      v17 = v16 - 55;
      goto LABEL_25;
    }
LABEL_258:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v17 = v16 - 87;
LABEL_25:
  v18 = v6[6];
  if ( !v18 )
    goto LABEL_257;
  if ( (unsigned __int16)(v18 - 48) <= 9u )
  {
    v19 = v18 - 48;
    goto LABEL_28;
  }
  if ( (unsigned __int16)(v18 - 97) > 5u )
  {
    if ( (unsigned __int16)(v18 - 65) <= 5u )
    {
      v19 = v18 - 55;
      goto LABEL_28;
    }
LABEL_257:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v19 = v18 - 87;
LABEL_28:
  v20 = v6[7];
  if ( !v20 )
    goto LABEL_256;
  if ( (unsigned __int16)(v20 - 48) <= 9u )
  {
    v21 = v20 - 48;
    goto LABEL_31;
  }
  if ( (unsigned __int16)(v20 - 97) > 5u )
  {
    if ( (unsigned __int16)(v20 - 65) <= 5u )
    {
      v21 = v20 - 55;
      goto LABEL_31;
    }
LABEL_256:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v61);
  }
  v21 = v20 - 87;
LABEL_31:
  LODWORD(v62) = v21
               | (16 * (v19 | (16 * (v17 | (16 * (v15 | (16 * (v13 | (16 * (v11 | (16 * (v9 | (16 * v7)))))))))))));
  if ( v6[8] != 45 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44B,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  v22 = v6[9];
  if ( !v22 )
    goto LABEL_255;
  if ( (unsigned __int16)(v22 - 48) <= 9u )
    goto LABEL_34;
  if ( (unsigned __int16)(v22 - 97) > 5u )
  {
    if ( (unsigned __int16)(v22 - 65) <= 5u )
    {
      v22 -= 55;
      goto LABEL_34;
    }
LABEL_255:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v22 -= 87;
LABEL_34:
  v23 = v6[10];
  if ( !v23 )
    goto LABEL_254;
  v24 = v23 - 48;
  if ( (unsigned __int16)(v23 - 48) <= 9u )
    goto LABEL_36;
  if ( (unsigned __int16)(v23 - 97) > 5u )
  {
    if ( (unsigned __int16)(v23 - 65) <= 5u )
    {
      v24 = v23 - 55;
      goto LABEL_36;
    }
LABEL_254:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v24 = v23 - 87;
LABEL_36:
  v25 = v6[11];
  if ( !v25 )
    goto LABEL_253;
  v26 = v25 - 48;
  if ( (unsigned __int16)(v25 - 48) <= 9u )
    goto LABEL_38;
  if ( (unsigned __int16)(v25 - 97) > 5u )
  {
    if ( (unsigned __int16)(v25 - 65) <= 5u )
    {
      v26 = v25 - 55;
      goto LABEL_38;
    }
LABEL_253:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v26 = v25 - 87;
LABEL_38:
  v27 = v6[12];
  if ( !v27 )
    goto LABEL_252;
  v28 = v27 - 48;
  if ( (unsigned __int16)(v27 - 48) <= 9u )
    goto LABEL_40;
  if ( (unsigned __int16)(v27 - 97) > 5u )
  {
    if ( (unsigned __int16)(v27 - 65) <= 5u )
    {
      v28 = v27 - 55;
      goto LABEL_40;
    }
LABEL_252:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v28 = v27 - 87;
LABEL_40:
  WORD2(v62) = v28 | (unsigned __int16)(16 * (v26 | (unsigned __int16)(16 * (v24 | (16 * v22)))));
  if ( v6[13] != 45 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  v29 = v6[14];
  if ( !v29 )
    goto LABEL_251;
  if ( (unsigned __int16)(v29 - 48) <= 9u )
    goto LABEL_43;
  if ( (unsigned __int16)(v29 - 97) > 5u )
  {
    if ( (unsigned __int16)(v29 - 65) <= 5u )
    {
      v29 -= 55;
      goto LABEL_43;
    }
LABEL_251:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v29 -= 87;
LABEL_43:
  v30 = v6[15];
  if ( !v30 )
    goto LABEL_250;
  v31 = v30 - 48;
  if ( (unsigned __int16)(v30 - 48) <= 9u )
    goto LABEL_45;
  if ( (unsigned __int16)(v30 - 97) > 5u )
  {
    if ( (unsigned __int16)(v30 - 65) <= 5u )
    {
      v31 = v30 - 55;
      goto LABEL_45;
    }
LABEL_250:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v31 = v30 - 87;
LABEL_45:
  v32 = v6[16];
  if ( !v32 )
    goto LABEL_249;
  v33 = v32 - 48;
  if ( (unsigned __int16)(v32 - 48) <= 9u )
    goto LABEL_47;
  if ( (unsigned __int16)(v32 - 97) > 5u )
  {
    if ( (unsigned __int16)(v32 - 65) <= 5u )
    {
      v33 = v32 - 55;
      goto LABEL_47;
    }
LABEL_249:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v33 = v32 - 87;
LABEL_47:
  v34 = v6[17];
  if ( !v34 )
    goto LABEL_248;
  v35 = v34 - 48;
  if ( (unsigned __int16)(v34 - 48) <= 9u )
    goto LABEL_49;
  if ( (unsigned __int16)(v34 - 97) > 5u )
  {
    if ( (unsigned __int16)(v34 - 65) <= 5u )
    {
      v35 = v34 - 55;
      goto LABEL_49;
    }
LABEL_248:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v35 = v34 - 87;
LABEL_49:
  WORD3(v62) = v35 | (unsigned __int16)(16 * (v33 | (unsigned __int16)(16 * (v31 | (16 * v29)))));
  if ( v6[18] != 45 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  v36 = v6[19];
  if ( !v36 )
    goto LABEL_247;
  if ( (unsigned __int16)(v36 - 48) <= 9u )
    goto LABEL_52;
  if ( (unsigned __int16)(v36 - 97) > 5u )
  {
    if ( (unsigned __int16)(v36 - 65) <= 5u )
    {
      LOBYTE(v36) = v36 - 55;
      goto LABEL_52;
    }
LABEL_247:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v36) = v36 - 87;
LABEL_52:
  v37 = v6[20];
  if ( !v37 )
    goto LABEL_246;
  if ( (unsigned __int16)(v37 - 48) <= 9u )
  {
    v38 = v37 - 48;
    goto LABEL_55;
  }
  if ( (unsigned __int16)(v37 - 97) > 5u )
  {
    if ( (unsigned __int16)(v37 - 65) <= 5u )
    {
      v38 = v37 - 55;
      goto LABEL_55;
    }
LABEL_246:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v38 = v37 - 87;
LABEL_55:
  BYTE8(v62) = v38 | (16 * v36);
  v39 = v6[21];
  if ( !v39 )
    goto LABEL_245;
  if ( (unsigned __int16)(v39 - 48) <= 9u )
    goto LABEL_57;
  if ( (unsigned __int16)(v39 - 97) > 5u )
  {
    if ( (unsigned __int16)(v39 - 65) <= 5u )
    {
      LOBYTE(v39) = v39 - 55;
      goto LABEL_57;
    }
LABEL_245:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v39) = v39 - 87;
LABEL_57:
  v40 = v6[22];
  if ( !v40 )
    goto LABEL_244;
  if ( (unsigned __int16)(v40 - 48) <= 9u )
  {
    v41 = v40 - 48;
    goto LABEL_60;
  }
  if ( (unsigned __int16)(v40 - 97) > 5u )
  {
    if ( (unsigned __int16)(v40 - 65) <= 5u )
    {
      v41 = v40 - 55;
      goto LABEL_60;
    }
LABEL_244:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v41 = v40 - 87;
LABEL_60:
  BYTE9(v62) = v41 | (16 * v39);
  if ( v6[23] != 45 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  v42 = v6[24];
  if ( !v42 )
    goto LABEL_243;
  if ( (unsigned __int16)(v42 - 48) <= 9u )
    goto LABEL_63;
  if ( (unsigned __int16)(v42 - 97) > 5u )
  {
    if ( (unsigned __int16)(v42 - 65) <= 5u )
    {
      LOBYTE(v42) = v42 - 55;
      goto LABEL_63;
    }
LABEL_243:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v42) = v42 - 87;
LABEL_63:
  v43 = v6[25];
  if ( !v43 )
    goto LABEL_242;
  if ( (unsigned __int16)(v43 - 48) <= 9u )
  {
    v44 = v43 - 48;
    goto LABEL_66;
  }
  if ( (unsigned __int16)(v43 - 97) > 5u )
  {
    if ( (unsigned __int16)(v43 - 65) <= 5u )
    {
      v44 = v43 - 55;
      goto LABEL_66;
    }
LABEL_242:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v44 = v43 - 87;
LABEL_66:
  BYTE10(v62) = v44 | (16 * v42);
  v45 = v6[26];
  if ( !v45 )
    goto LABEL_241;
  if ( (unsigned __int16)(v45 - 48) <= 9u )
    goto LABEL_68;
  if ( (unsigned __int16)(v45 - 97) > 5u )
  {
    if ( (unsigned __int16)(v45 - 65) <= 5u )
    {
      LOBYTE(v45) = v45 - 55;
      goto LABEL_68;
    }
LABEL_241:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v45) = v45 - 87;
LABEL_68:
  v46 = v6[27];
  if ( !v46 )
    goto LABEL_240;
  if ( (unsigned __int16)(v46 - 48) <= 9u )
  {
    v47 = v46 - 48;
    goto LABEL_71;
  }
  if ( (unsigned __int16)(v46 - 97) > 5u )
  {
    if ( (unsigned __int16)(v46 - 65) <= 5u )
    {
      v47 = v46 - 55;
      goto LABEL_71;
    }
LABEL_240:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v47 = v46 - 87;
LABEL_71:
  BYTE11(v62) = v47 | (16 * v45);
  v48 = v6[28];
  if ( !v48 )
    goto LABEL_239;
  if ( (unsigned __int16)(v48 - 48) <= 9u )
    goto LABEL_73;
  if ( (unsigned __int16)(v48 - 97) > 5u )
  {
    if ( (unsigned __int16)(v48 - 65) <= 5u )
    {
      LOBYTE(v48) = v48 - 55;
      goto LABEL_73;
    }
LABEL_239:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v48) = v48 - 87;
LABEL_73:
  v49 = v6[29];
  if ( !v49 )
    goto LABEL_238;
  if ( (unsigned __int16)(v49 - 48) <= 9u )
  {
    v50 = v49 - 48;
    goto LABEL_76;
  }
  if ( (unsigned __int16)(v49 - 97) > 5u )
  {
    if ( (unsigned __int16)(v49 - 65) <= 5u )
    {
      v50 = v49 - 55;
      goto LABEL_76;
    }
LABEL_238:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v50 = v49 - 87;
LABEL_76:
  BYTE12(v62) = v50 | (16 * v48);
  v51 = v6[30];
  if ( !v51 )
    goto LABEL_237;
  if ( (unsigned __int16)(v51 - 48) <= 9u )
    goto LABEL_78;
  if ( (unsigned __int16)(v51 - 97) > 5u )
  {
    if ( (unsigned __int16)(v51 - 65) <= 5u )
    {
      LOBYTE(v51) = v51 - 55;
      goto LABEL_78;
    }
LABEL_237:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v51) = v51 - 87;
LABEL_78:
  v52 = v6[31];
  if ( !v52 )
    goto LABEL_236;
  if ( (unsigned __int16)(v52 - 48) <= 9u )
  {
    v53 = v52 - 48;
    goto LABEL_81;
  }
  if ( (unsigned __int16)(v52 - 97) > 5u )
  {
    if ( (unsigned __int16)(v52 - 65) <= 5u )
    {
      v53 = v52 - 55;
      goto LABEL_81;
    }
LABEL_236:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v53 = v52 - 87;
LABEL_81:
  BYTE13(v62) = v53 | (16 * v51);
  v54 = v6[32];
  if ( !v54 )
    goto LABEL_235;
  if ( (unsigned __int16)(v54 - 48) <= 9u )
    goto LABEL_83;
  if ( (unsigned __int16)(v54 - 97) > 5u )
  {
    if ( (unsigned __int16)(v54 - 65) <= 5u )
    {
      LOBYTE(v54) = v54 - 55;
      goto LABEL_83;
    }
LABEL_235:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v54) = v54 - 87;
LABEL_83:
  v55 = v6[33];
  if ( !v55 )
    goto LABEL_234;
  if ( (unsigned __int16)(v55 - 48) <= 9u )
  {
    v56 = v55 - 48;
    goto LABEL_86;
  }
  if ( (unsigned __int16)(v55 - 97) > 5u )
  {
    if ( (unsigned __int16)(v55 - 65) <= 5u )
    {
      v56 = v55 - 55;
      goto LABEL_86;
    }
LABEL_234:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v56 = v55 - 87;
LABEL_86:
  BYTE14(v62) = v56 | (16 * v54);
  v57 = v6[34];
  if ( !v57 )
    goto LABEL_233;
  if ( (unsigned __int16)(v57 - 48) <= 9u )
    goto LABEL_88;
  if ( (unsigned __int16)(v57 - 97) > 5u )
  {
    if ( (unsigned __int16)(v57 - 65) <= 5u )
    {
      LOBYTE(v57) = v57 - 55;
      goto LABEL_88;
    }
LABEL_233:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  LOBYTE(v57) = v57 - 87;
LABEL_88:
  v58 = v6[35];
  if ( !v58 )
    goto LABEL_232;
  if ( (unsigned __int16)(v58 - 48) > 9u )
  {
    if ( (unsigned __int16)(v58 - 97) <= 5u )
    {
      v59 = v58 - 87;
      goto LABEL_91;
    }
    if ( (unsigned __int16)(v58 - 65) <= 5u )
    {
      v59 = v58 - 55;
      goto LABEL_91;
    }
LABEL_232:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  }
  v59 = v58 - 48;
LABEL_91:
  v60 = v6 + 36;
  if ( v4 == 123 )
  {
    if ( *v60 != 125 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x497,
        (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
        (const char *)0x80070057LL,
        v62);
    ++v60;
  }
  if ( *v60 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)0x80070057LL,
      v62);
  HIBYTE(v62) = v59 | (16 * v57);
  *(_OWORD *)this = v62;
}

```

## disassembly

```asm
0x140018f8c  push    rbp
0x140018f8e  push    rbx
0x140018f8f  push    rsi
0x140018f90  push    rdi
0x140018f91  push    r12
0x140018f93  push    r13
0x140018f95  push    r14
0x140018f97  push    r15
0x140018f99  mov     rbp, rsp
0x140018f9c  sub     rsp, 38h
0x140018fa0  mov     rax, rdx
0x140018fa3  mov     r15, rcx
0x140018fa6  test    rdx, rdx
0x140018fa9  jz      loc_140019A99
0x140018faf  movzx   r14d, word ptr [rdx]
0x140018fb3  test    r14w, r14w
0x140018fb7  jz      loc_140019A99
0x140018fbd  cmp     r14w, 7Bh ; '{'
0x140018fc2  jz      loc_140019BCE
0x140018fc8  movzx   edx, r14w
0x140018fcc  lea     rcx, [rax+2]
0x140018fd0  cmovnz  rcx, rax
0x140018fd4  test    dx, dx
0x140018fd7  jz      loc_140019FF2
0x140018fdd  mov     r13d, 30h ; '0'
0x140018fe3  movzx   eax, dx
0x140018fe6  sub     ax, r13w
0x140018fea  mov     bx, 9
0x140018fee  mov     r11w, 61h ; 'a'
0x140018ff3  mov     r12w, 5
0x140018ff8  mov     r10w, 41h ; 'A'
0x140018ffd  lea     edi, [r13+27h]
0x140019001  cmp     ax, bx
0x140019004  ja      loc_14001956B
0x14001900a  movzx   r9d, dx
0x14001900e  movzx   edx, word ptr [rcx+2]
0x140019012  test    dx, dx
0x140019015  jz      loc_140019FD6
0x14001901b  movzx   eax, dx
0x14001901e  sub     ax, r13w
0x140019022  cmp     ax, bx
0x140019025  ja      loc_14001959A
0x14001902b  mov     esi, edx
0x14001902d  sub     esi, r13d
0x140019030  movzx   edx, word ptr [rcx+4]
0x140019034  test    dx, dx
0x140019037  jz      loc_140019FBA
0x14001903d  movzx   eax, dx
0x140019040  sub     ax, r13w
0x140019044  cmp     ax, bx
0x140019047  ja      loc_1400195C4
0x14001904d  mov     edi, edx
0x14001904f  sub     edi, r13d
0x140019052  movzx   edx, word ptr [rcx+6]
0x140019056  test    dx, dx
0x140019059  jz      loc_140019F9E
0x14001905f  movzx   eax, dx
0x140019062  sub     ax, r13w
0x140019066  cmp     ax, bx
0x140019069  ja      loc_1400195EE
0x14001906f  mov     ebx, edx
0x140019071  sub     ebx, r13d
0x140019074  movzx   edx, word ptr [rcx+8]
0x140019078  test    dx, dx
0x14001907b  jz      loc_140019F82
0x140019081  movzx   eax, dx
0x140019084  sub     ax, r13w
0x140019088  cmp     ax, 9
0x14001908c  ja      loc_140019618
0x140019092  mov     r11d, edx
0x140019095  sub     r11d, r13d
0x140019098  movzx   edx, word ptr [rcx+0Ah]
0x14001909c  test    dx, dx
0x14001909f  jz      loc_140019F66
0x1400190a5  movzx   eax, dx
0x1400190a8  sub     ax, r13w
0x1400190ac  cmp     ax, 9
0x1400190b0  ja      loc_140019643
0x1400190b6  mov     r10d, edx
0x1400190b9  sub     r10d, r13d
0x1400190bc  movzx   edx, word ptr [rcx+0Ch]
0x1400190c0  test    dx, dx
0x1400190c3  jz      loc_140019F4A
0x1400190c9  movzx   eax, dx
0x1400190cc  sub     ax, r13w
0x1400190d0  cmp     ax, 9
0x1400190d4  ja      loc_14001966A
0x1400190da  mov     r8d, edx
0x1400190dd  sub     r8d, r13d
0x1400190e0  movzx   edx, word ptr [rcx+0Eh]
0x1400190e4  test    dx, dx
0x1400190e7  jz      loc_140019F2E
0x1400190ed  movzx   eax, dx
0x1400190f0  sub     ax, r13w
0x1400190f4  cmp     ax, 9
0x1400190f8  ja      loc_14001968D
0x1400190fe  sub     edx, r13d
0x140019101  shl     r9d, 4
0x140019105  or      r9d, esi
0x140019108  movzx   eax, dil
0x14001910c  shl     r9d, 4
0x140019110  or      r9d, eax
0x140019113  movzx   eax, bl
0x140019116  shl     r9d, 4
0x14001911a  or      r9d, eax
0x14001911d  movzx   eax, r11b
0x140019121  shl     r9d, 4
0x140019125  or      r9d, eax
0x140019128  movzx   eax, r10b
0x14001912c  shl     r9d, 4
0x140019130  or      r9d, eax
0x140019133  movzx   eax, r8b
0x140019137  shl     r9d, 4
0x14001913b  or      r9d, eax
0x14001913e  movzx   eax, dl
0x140019141  shl     r9d, 4
0x140019145  or      r9d, eax
0x140019148  cmp     word ptr [rcx+10h], 2Dh ; '-'
0x14001914d  mov     dword ptr [rbp+var_18], r9d
0x140019151  jnz     loc_140019BD7
0x140019157  movzx   edx, word ptr [rcx+12h]
0x14001915b  xor     r11d, r11d
0x14001915e  test    dx, dx
0x140019161  jz      loc_140019F12
0x140019167  movzx   eax, dx
0x14001916a  mov     si, 9
0x14001916e  sub     ax, r13w
0x140019172  mov     di, 61h ; 'a'
0x140019176  mov     bx, 41h ; 'A'
0x14001917a  cmp     ax, si
0x14001917d  ja      loc_1400196AF
0x140019183  mov     r10d, 57h ; 'W'
0x140019189  movzx   r8d, word ptr [rcx+14h]
0x14001918e  test    r8w, r8w
0x140019192  jz      loc_140019EF6
0x140019198  movzx   r9d, r8w
0x14001919c  sub     r9w, r13w
0x1400191a0  cmp     r9w, si
0x1400191a4  ja      loc_1400196D8
0x1400191aa  movzx   r10d, word ptr [rcx+16h]
0x1400191af  test    r10w, r10w
0x1400191b3  jz      loc_140019EDA
0x1400191b9  movzx   r8d, r10w
0x1400191bd  sub     r8w, r13w
0x1400191c1  cmp     r8w, si
0x1400191c5  ja      loc_140019703
0x1400191cb  movzx   r10d, word ptr [rcx+18h]
0x1400191d0  test    r10w, r10w
0x1400191d4  jz      loc_140019EBE
0x1400191da  movzx   eax, r10w
0x1400191de  sub     ax, r13w
0x1400191e2  cmp     ax, si
0x1400191e5  ja      loc_14001972E
0x1400191eb  mov     r10d, 57h ; 'W'
0x1400191f1  shl     dx, 4
0x1400191f5  or      dx, r9w
0x1400191f9  mov     r9d, 0FFh
0x1400191ff  shl     dx, 4
0x140019203  and     r8w, r9w
0x140019207  or      dx, r8w
0x14001920b  and     ax, r9w
0x14001920f  shl     dx, 4
0x140019213  or      dx, ax
0x140019216  cmp     word ptr [rcx+1Ah], 2Dh ; '-'
0x14001921b  mov     word ptr [rbp+var_18+4], dx
0x14001921f  jnz     loc_140019BF3
0x140019225  movzx   edx, word ptr [rcx+1Ch]
0x140019229  test    dx, dx
0x14001922c  jz      loc_140019EA2
0x140019232  movzx   eax, dx
0x140019235  sub     ax, r13w
0x140019239  cmp     ax, si
0x14001923c  ja      loc_140019759
0x140019242  movzx   r8d, word ptr [rcx+1Eh]
0x140019247  test    r8w, r8w
0x14001924b  jz      loc_140019E86
0x140019251  movzx   r9d, r8w
0x140019255  sub     r9w, r13w
0x140019259  cmp     r9w, si
0x14001925d  ja      loc_140019782
0x140019263  movzx   r10d, word ptr [rcx+20h]
0x140019268  test    r10w, r10w
0x14001926c  jz      loc_140019E6A
0x140019272  movzx   r8d, r10w
0x140019276  sub     r8w, r13w
0x14001927a  cmp     r8w, si
0x14001927e  ja      loc_1400197AD
0x140019284  movzx   r10d, word ptr [rcx+22h]
0x140019289  test    r10w, r10w
0x14001928d  jz      loc_140019E4E
0x140019293  movzx   eax, r10w
0x140019297  sub     ax, r13w
0x14001929b  cmp     ax, si
0x14001929e  ja      loc_1400197D8
0x1400192a4  mov     r10d, 57h ; 'W'
0x1400192aa  shl     dx, 4
0x1400192ae  or      dx, r9w
0x1400192b2  mov     r9d, 0FFh
0x1400192b8  shl     dx, 4
0x1400192bc  and     r8w, r9w
0x1400192c0  or      dx, r8w
0x1400192c4  and     ax, r9w
0x1400192c8  shl     dx, 4
0x1400192cc  or      dx, ax
0x1400192cf  cmp     word ptr [rcx+24h], 2Dh ; '-'
0x1400192d4  mov     word ptr [rbp+var_18+6], dx
0x1400192d8  jnz     loc_140019C0F
0x1400192de  movzx   edx, word ptr [rcx+26h]
0x1400192e2  test    dx, dx
0x1400192e5  jz      loc_140019E32
0x1400192eb  movzx   eax, dx
0x1400192ee  sub     ax, r13w
0x1400192f2  cmp     ax, si
0x1400192f5  ja      loc_140019803
0x1400192fb  mov     r9d, 37h ; '7'
0x140019301  movzx   r8d, word ptr [rcx+28h]
0x140019306  test    r8w, r8w
0x14001930a  jz      loc_140019E16
0x140019310  movzx   eax, r8w
0x140019314  sub     ax, r13w
0x140019318  cmp     ax, si
0x14001931b  ja      loc_140019831
0x140019321  sub     r8b, r13b
0x140019324  shl     dl, 4
0x140019327  or      dl, r8b
0x14001932a  mov     byte ptr [rbp+var_18+8], dl
0x14001932d  movzx   edx, word ptr [rcx+2Ah]
0x140019331  test    dx, dx
0x140019334  jz      loc_140019DFA
0x14001933a  movzx   eax, dx
0x14001933d  sub     ax, r13w
0x140019341  cmp     ax, si
0x140019344  ja      loc_14001985B
0x14001934a  movzx   r8d, word ptr [rcx+2Ch]
0x14001934f  test    r8w, r8w
0x140019353  jz      loc_140019DDE
0x140019359  movzx   eax, r8w
0x14001935d  sub     ax, r13w
0x140019361  cmp     ax, si
0x140019364  ja      loc_140019883
0x14001936a  sub     r8b, r13b
0x14001936d  shl     dl, 4
0x140019370  or      dl, r8b
0x140019373  cmp     word ptr [rcx+2Eh], 2Dh ; '-'
0x140019378  mov     byte ptr [rbp+var_18+9], dl
0x14001937b  jnz     loc_140019C2B
0x140019381  movzx   edx, word ptr [rcx+30h]
0x140019385  test    dx, dx
0x140019388  jz      loc_140019DC2
0x14001938e  movzx   eax, dx
0x140019391  sub     ax, r13w
0x140019395  cmp     ax, si
0x140019398  ja      loc_1400198AD
0x14001939e  movzx   r8d, word ptr [rcx+32h]
0x1400193a3  test    r8w, r8w
0x1400193a7  jz      loc_140019DA6
0x1400193ad  movzx   eax, r8w
0x1400193b1  sub     ax, r13w
0x1400193b5  cmp     ax, si
0x1400193b8  ja      loc_1400198D5
0x1400193be  sub     r8b, r13b
0x1400193c1  shl     dl, 4
0x1400193c4  or      dl, r8b
0x1400193c7  mov     byte ptr [rbp+var_18+0Ah], dl
0x1400193ca  movzx   edx, word ptr [rcx+34h]
0x1400193ce  test    dx, dx
0x1400193d1  jz      loc_140019D8A
0x1400193d7  movzx   eax, dx
0x1400193da  sub     ax, r13w
0x1400193de  cmp     ax, si
0x1400193e1  ja      loc_1400198FF
0x1400193e7  movzx   r8d, word ptr [rcx+36h]
0x1400193ec  test    r8w, r8w
0x1400193f0  jz      loc_140019D6E
0x1400193f6  movzx   eax, r8w
0x1400193fa  sub     ax, r13w
0x1400193fe  cmp     ax, si
0x140019401  ja      loc_140019927
0x140019407  sub     r8b, r13b
0x14001940a  shl     dl, 4
0x14001940d  or      dl, r8b
0x140019410  mov     byte ptr [rbp+var_18+0Bh], dl
0x140019413  movzx   edx, word ptr [rcx+38h]
0x140019417  test    dx, dx
0x14001941a  jz      loc_140019D52
0x140019420  movzx   eax, dx
0x140019423  sub     ax, r13w
0x140019427  cmp     ax, si
0x14001942a  ja      loc_140019951
0x140019430  movzx   r8d, word ptr [rcx+3Ah]
0x140019435  test    r8w, r8w
0x140019439  jz      loc_140019D36
0x14001943f  movzx   eax, r8w
0x140019443  sub     ax, r13w
0x140019447  cmp     ax, si
0x14001944a  ja      loc_140019979
0x140019450  sub     r8b, r13b
0x140019453  shl     dl, 4
0x140019456  or      dl, r8b
0x140019459  mov     byte ptr [rbp+var_18+0Ch], dl
  ... truncated ...
```
