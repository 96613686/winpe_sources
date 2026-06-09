# CMicrodomBuilder::WriteXmlDom(_LBLOB *)

- ea: `0x1800566f0`
- end: `0x180057081`
- name: `?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z`
- size: `2449`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800551a4`

## callees

- `0x180037054`
- `0x1800370f4`
- `0x1800505b0`
- `0x180053ec0`
- `0x180053fb4`
- `0x18005414c`
- `0x1800566f0`
- `0x180057da8`
- `0x18005818c`
- `0x1800607b0`
- `0x180060e70`

## string_xrefs

- `0x180056884`: `onecore\base\xml\udom_builder.cpp`
- `0x1800568c6`: `onecore\base\xml\udom_builder.cpp`
- `0x180056b05`: `onecore\base\xml\udom_builder.cpp`
- `0x180056e20`: `onecore\base\xml\udom_builder.cpp`
- `0x180056fa2`: `onecore\base\xml\udom_builder.cpp`
- `0x180056fec`: `onecore\base\xml\udom_builder.cpp`
- `0x180057002`: `CMicrodomBuilder::WriteXmlDom`
- `0x1800568cd`: `CMicrodomBuilder::CFourStringIdTable<struct _MICRODOM_XML_ATTDEF const *>::Initialize`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::WriteXmlDom(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  __int64 *v2; // r14
  __int64 v3; // r12
  _DWORD *v5; // rsi
  CMicrodomBuilder *v6; // r15
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rax
  unsigned __int64 v13; // rdx
  int StringId; // edi
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 (__fastcall *v17)(); // r10
  __int64 v18; // rcx
  unsigned __int64 v19; // rbx
  int v20; // eax
  __int64 **v21; // rcx
  __int64 *i; // rax
  __int64 *v23; // rsi
  unsigned int v24; // r14d
  unsigned int v25; // ecx
  unsigned __int64 v26; // rbx
  int v27; // eax
  int v28; // edi
  int v29; // r11d
  char v30; // al
  int v31; // r9d
  int v32; // r10d
  unsigned __int64 v33; // r8
  __int64 **v34; // rdx
  __int64 *k; // rax
  __int64 *v36; // rax
  unsigned __int64 v37; // rbx
  unsigned __int64 v38; // r15
  unsigned __int64 v39; // r14
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rdi
  bool v42; // cf
  _DWORD *v43; // r14
  int v44; // r9d
  int v45; // eax
  int v46; // r10d
  unsigned __int64 v47; // r8
  __int64 **v48; // rdx
  __int64 *j; // rax
  __int16 *v50; // rax
  __int16 v51; // ax
  int v52; // edi
  __int64 (__fastcall *v53)(); // rax
  CMicrodomBuilder *v54; // rcx
  int v55; // eax
  unsigned __int64 v56; // rbx
  int v57; // ecx
  int v58; // eax
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned __int64 v63; // rcx
  unsigned __int64 v64; // rbx
  int v65; // eax
  int v66; // eax
  unsigned __int64 v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int16 v73; // [rsp+30h] [rbp-D0h]
  char v74; // [rsp+32h] [rbp-CEh]
  char v75; // [rsp+33h] [rbp-CDh] BYREF
  char v76[2]; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v77; // [rsp+36h] [rbp-CAh] BYREF
  int v78; // [rsp+38h] [rbp-C8h]
  int v79; // [rsp+3Ch] [rbp-C4h]
  unsigned __int64 v80; // [rsp+40h] [rbp-C0h]
  int v81; // [rsp+48h] [rbp-B8h]
  unsigned int v82; // [rsp+4Ch] [rbp-B4h] BYREF
  int v83; // [rsp+50h] [rbp-B0h] BYREF
  int v84; // [rsp+54h] [rbp-ACh]
  __int64 (__fastcall *v85)(); // [rsp+58h] [rbp-A8h]
  int v86; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v87; // [rsp+64h] [rbp-9Ch] BYREF
  _DWORD v88[2]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v89[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v90[4]; // [rsp+80h] [rbp-80h] BYREF
  CMicrodomBuilder *v91; // [rsp+90h] [rbp-70h]
  _QWORD v92[2]; // [rsp+98h] [rbp-68h] BYREF
  int v93; // [rsp+A8h] [rbp-58h]
  const char *v94; // [rsp+B0h] [rbp-50h]
  _QWORD v95[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v96; // [rsp+C8h] [rbp-38h]
  const char *v97; // [rsp+D0h] [rbp-30h]
  _QWORD v98[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v99; // [rsp+E8h] [rbp-18h]
  const char *v100; // [rsp+F0h] [rbp-10h]
  _QWORD v101[2]; // [rsp+F8h] [rbp-8h] BYREF
  int v102; // [rsp+108h] [rbp+8h]
  const char *v103; // [rsp+110h] [rbp+10h]
  _QWORD v104[2]; // [rsp+118h] [rbp+18h] BYREF
  int v105; // [rsp+128h] [rbp+28h]
  const char *v106; // [rsp+130h] [rbp+30h]
  __int64 v107; // [rsp+138h] [rbp+38h] BYREF
  __int64 v108; // [rsp+140h] [rbp+40h] BYREF
  __int16 v109; // [rsp+148h] [rbp+48h] BYREF
  int v110; // [rsp+15Ch] [rbp+5Ch]
  int v111; // [rsp+160h] [rbp+60h]
  int v112; // [rsp+164h] [rbp+64h]
  char v113[8]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE *v114; // [rsp+178h] [rbp+78h]
  __int64 v115; // [rsp+180h] [rbp+80h]
  unsigned __int64 v116; // [rsp+188h] [rbp+88h]
  __m128i v117; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v118[240]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v119[8]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE *v120; // [rsp+298h] [rbp+198h]
  __int64 v121; // [rsp+2A0h] [rbp+1A0h]
  unsigned __int64 v122; // [rsp+2A8h] [rbp+1A8h]
  __m128i si128; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v124[240]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v125[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE *v126; // [rsp+3B8h] [rbp+2B8h]
  __m128i v127; // [rsp+3C0h] [rbp+2C0h]
  __m128i v128; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v129[240]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v2 = (__int64 *)((char *)this + 1264);
  v3 = *((_QWORD *)a2 + 2) + *((_QWORD *)a2 + 1);
  v5 = (_DWORD *)(*((_QWORD *)a2 + 2) + *(_QWORD *)a2);
  v6 = this;
  v81 = -1;
  v83 = -1;
  v84 = -1;
  v78 = -1;
  v79 = -1;
  v120 = v124;
  v7 = v124;
  v91 = this;
  v8 = 7;
  v110 = 0;
  v73 = 0;
  v121 = 0;
  v122 = 7;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v7[3] = 0;
    *v7 = v7;
    v7[1] = v7;
    v7[2] = v7;
    v7 += 4;
    --v8;
  }
  while ( v8 );
  v9 = 7;
  v126 = v129;
  v10 = v129;
  v127 = _mm_load_si128((const __m128i *)&_xmm);
  v128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v10[3] = 0;
    *v10 = v10;
    v10[1] = v10;
    v10[2] = v10;
    v10 += 4;
    --v9;
  }
  while ( v9 );
  v114 = v118;
  v11 = 7;
  v12 = v118;
  v115 = 0;
  v116 = 7;
  v117 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v12[3] = 0;
    *v12 = v12;
    v12[1] = v12;
    v12[2] = v12;
    v12 += 4;
    --v11;
  }
  while ( v11 );
  StringId = CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize(v119, 1);
  if ( StringId < 0 )
    goto LABEL_149;
  StringId = CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize(v125, v13);
  if ( StringId < 0 )
    goto LABEL_149;
  if ( v114 == v118 )
  {
    BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v86, v116, 5, &v117.m128i_u64[1]);
    StringId = 0;
    if ( v86 < 0 )
      StringId = v86;
    if ( StringId >= 0 )
    {
      StringId = 0;
      goto LABEL_16;
    }
  }
  else
  {
    __debugbreak();
    StringId = -1073741595;
  }
  v92[0] = "onecore\\base\\xml\\udom_builder.cpp";
  v92[1] = "CMicrodomBuilder::CFourStringIdTable<struct _MICRODOM_XML_ATTDEF const *>::Initialize";
  v93 = 178;
  v94 = "m_StoredTable.Initialize()";
  RtlReportErrorOrigination(v92, v13, (unsigned int)StringId);
LABEL_16:
  if ( StringId < 0 )
    goto LABEL_149;
  StringId = CMicrodomBuilder::FindStringId(v6, (const struct _LUTF8_STRING *)qword_180063AA0, &v82);
  if ( StringId < 0 )
    goto LABEL_149;
  StringId = CMicrodomBuilder::FindStringId(v6, (const struct _LUTF8_STRING *)qword_180063A68, &v87);
  if ( StringId < 0 )
    goto LABEL_149;
  v13 = v3 - (_QWORD)v5;
  v80 = v3 - (_QWORD)v5;
  if ( (unsigned __int64)(v3 - (_QWORD)v5) < 0x14 )
    __debugbreak();
  *v5 = 1816421453;
  v5[2] = *((_DWORD *)v6 + 324);
  v16 = *((_DWORD *)v6 + 324);
  if ( v16 > 0xFF )
  {
    if ( v16 > 0xFFFF )
    {
      v5[1] = 3;
      v17 = CMicrodomBuilder::WriteDomElementIndicies<unsigned long>;
    }
    else
    {
      v5[1] = 2;
      v17 = CMicrodomBuilder::WriteDomElementIndicies<unsigned short>;
    }
  }
  else
  {
    v5[1] = 1;
    v17 = CMicrodomBuilder::WriteDomElementIndicies<unsigned char>;
  }
  v18 = *v2;
  v19 = ((unsigned __int64)v5 + 23) & 0xFFFFFFFFFFFFFFFCuLL;
  v85 = v17;
  v15 = 0;
  if ( (__int64 *)v18 == v2 )
    v18 = 0;
  if ( !v18 )
    __debugbreak();
  if ( *(_WORD *)(v18 + 114) != 14 )
    __debugbreak();
  v20 = *(_DWORD *)(v18 + 72);
  v21 = (__int64 **)(v18 + 88);
  v5[4] = v20;
  for ( i = *v21; ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)v21 )
    {
      __debugbreak();
      goto LABEL_37;
    }
    if ( !*((_WORD *)i + 33) )
      break;
  }
  v5[3] = *((_DWORD *)i + 6);
LABEL_37:
  v23 = (__int64 *)*v2;
  v24 = v82;
  v74 = v75;
  while ( v23 && v23 != (__int64 *)((char *)v6 + 1264) )
  {
    v25 = *((unsigned __int16 *)v23 + 57);
    if ( v25 <= 8 )
    {
      if ( v25 == 8 )
      {
        v57 = *((_DWORD *)v23 + 30);
        v90[0] = *((_DWORD *)v23 + 29);
        v90[2] = -1;
        v90[3] = -1;
        v109 = v73;
        v90[1] = v57;
        v58 = BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::FindOrInsertIfNotPresent<CMicrodomBuilder::FourStringIdPair,unsigned short>(
                (unsigned int)v119,
                (unsigned int)v90,
                (unsigned int)&v109,
                1,
                (__int64)&v75);
        v15 = 0;
        StringId = v58;
        if ( v58 >= 0 )
        {
          StringId = 0;
        }
        else
        {
          v99 = 297;
          v98[0] = "onecore\\base\\xml\\udom_builder.cpp";
          v98[1] = "CMicrodomBuilder::CElementNameToAttributeListTable::MaybeInsert";
          v100 = "m_StoredTable.FindOrInsertIfNotPresent(Pair, Value, 0, pfExisted)";
          RtlReportErrorOrigination(v98, v13, (unsigned int)v58);
          v15 = 0;
        }
        if ( StringId < 0 )
          goto LABEL_149;
        if ( v75 )
          goto LABEL_87;
        goto LABEL_119;
      }
      if ( !*((_WORD *)v23 + 57) )
      {
        v38 = *((unsigned int *)v23 + 19);
        v39 = v23[13] - v38;
        if ( v13 < 0x14 )
          __debugbreak();
        v40 = *((unsigned int *)v23 + 19);
        v41 = v23[13] - v38;
        if ( v38 >= v39 )
        {
          v40 = v23[13] - v38;
          v41 = *((unsigned int *)v23 + 19);
        }
        if ( v40 )
          v41 |= v40 << 22;
        else
          v74 = 0;
        CMicrodomBuilder::CNamespaceNameExistenceCheck::Clear((CMicrodomBuilder::CNamespaceNameExistenceCheck *)v125);
        v42 = v38 < v39;
        v112 = 0;
        v43 = (_DWORD *)((v19 + 27) & 0xFFFFFFFFFFFFFFFCuLL);
        *(_BYTE *)v19 = (16 * (v74 & 7)) | (v42 ? 0x80 : 0) | 1;
        v44 = *((_DWORD *)v23 + 29);
        *(_DWORD *)(v19 + 12) = v44;
        v45 = *((_DWORD *)v23 + 30);
        *(_DWORD *)(v19 + 16) = v45;
        v46 = *((_DWORD *)v23 + 31);
        v81 = v45;
        *(_DWORD *)(v19 + 20) = v46;
        v78 = v44;
        v79 = v46;
        v47 = (unsigned int)(8261505 * v46 + 780587199 * v44 - 65600);
        v48 = (__int64 **)&v120[32 * (v47 % v122)];
        for ( j = *v48; j && j != (__int64 *)v48; j = (__int64 *)*j )
        {
          if ( __PAIR64__(v44, v47) == j[4]
            && v46 == *((_DWORD *)j + 10)
            && *((_DWORD *)j + 11) == -1
            && *((_DWORD *)j + 12) == -1 )
          {
            v50 = (__int16 *)j + 26;
            if ( v50 )
            {
              v51 = *v50;
              goto LABEL_107;
            }
            break;
          }
        }
        v51 = -1;
LABEL_107:
        *(_WORD *)(v19 + 8) = v51;
        if ( v41 >= 0x400000 )
        {
          if ( (unsigned __int64)(v3 - (_QWORD)v43) < 4 )
            __debugbreak();
          *v43 = v41 & 0x3FFFFF;
          *(_BYTE *)(v19 + 1) |= 1u;
          v43 = (_DWORD *)(((unsigned __int64)v43 + 7) & 0xFFFFFFFFFFFFFFFCuLL);
          v52 = (*(_DWORD *)(v19 + 4) ^ (v41 >> 22)) & 0x3FFFFF;
        }
        else
        {
          *(_BYTE *)(v19 + 1) &= ~1u;
          v52 = (*(_DWORD *)(v19 + 4) ^ v41) & 0x3FFFFF;
        }
        v6 = v91;
        v53 = v85;
        v54 = v91;
        *(_DWORD *)(v19 + 4) ^= v52;
        v55 = ((__int64 (__fastcall *)(CMicrodomBuilder *, _DWORD *, __int64 *, __int64 *))v53)(v54, v43, &v107, v23);
        v15 = 0;
        StringId = v55;
        if ( v55 < 0 )
          goto LABEL_149;
        v56 = (unsigned __int64)v43 + v107 + 3;
        v24 = v82;
        v19 = v56 & 0xFFFFFFFFFFFFFFFCuLL;
        goto LABEL_87;
      }
      if ( v25 == 1 )
      {
        if ( v3 - v19 < 0x14 )
          __debugbreak();
        v89[0] = *((_DWORD *)v23 + 30);
        v89[1] = *((_DWORD *)v23 + 31);
        v89[2] = -1;
        v89[3] = -1;
        v77 = 0;
        v27 = BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::FindOrInsertIfNotPresent<CMicrodomBuilder::FourStringIdPair,unsigned short>(
                (unsigned int)v125,
                (unsigned int)v89,
                (unsigned int)&v77,
                1,
                (__int64)v76);
        StringId = v27;
        if ( v27 >= 0 )
        {
          if ( v76[0] )
          {
            v102 = 211;
            v101[0] = "onecore\\base\\xml\\udom_builder.cpp";
            v101[1] = "CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence";
            v103 = "!fExisted";
            RtlReportErrorOrigination(v101, v13, 3221266563LL);
            StringId = -1073700733;
            goto LABEL_149;
          }
          StringId = 0;
        }
        else
        {
          v96 = 209;
          v95[0] = "onecore\\base\\xml\\udom_builder.cpp";
          v95[1] = "CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence";
          v97 = "m_StoredTable.FindOrInsertIfNotPresent(p, (USHORT)0, 0, &fExisted)";
          RtlReportErrorOrigination(v95, v13, (unsigned int)v27);
        }
        if ( StringId < 0 )
          goto LABEL_149;
        v28 = v79;
        v29 = v78;
        *(_BYTE *)v19 = 2;
        *(_DWORD *)(v19 + 12) = *((_DWORD *)v23 + 31);
        *(_DWORD *)(v19 + 8) = *((_DWORD *)v23 + 30);
        *(_DWORD *)(v19 + 4) = *((_DWORD *)v23 + 29);
        *(_DWORD *)(v19 + 16) = *((_DWORD *)v23 + 32);
        v30 = *(_BYTE *)v19;
        if ( !*((_BYTE *)v23 + 132) )
          v30 = 34;
        v111 = 0;
        *(_BYTE *)v19 = v30;
        v31 = *((_DWORD *)v23 + 29);
        v32 = *((_DWORD *)v23 + 31);
        v33 = (unsigned int)(65599 * v31 + v32 + 8261505 * v28 + 780587199 * v29);
        v34 = (__int64 **)&v114[32 * (v33 % v116)];
        for ( k = *v34; ; k = (__int64 *)*k )
        {
          if ( !k || k == (__int64 *)v34 )
          {
            v15 = 0;
            goto LABEL_80;
          }
          if ( __PAIR64__(v29, v33) == k[4]
            && v28 == *((_DWORD *)k + 10)
            && v31 == *((_DWORD *)k + 11)
            && v32 == *((_DWORD *)k + 12) )
          {
            break;
          }
        }
        v15 = 0;
        v36 = k + 7;
        if ( v36 && *(_DWORD *)(*v36 + 12) == 1 )
          *(_BYTE *)v19 |= 0x10u;
LABEL_80:
        if ( (*(_DWORD *)(v19 + 8) == v24 || *(_DWORD *)(v19 + 8) == -1 && v81 == v24) && *(_DWORD *)(v19 + 12) == v87 )
          *(_BYTE *)v19 |= 0x10u;
        v37 = v19 + 23;
        goto LABEL_86;
      }
      if ( v25 <= 3 )
      {
        v78 = -1;
        v79 = -1;
        goto LABEL_88;
      }
      switch ( v25 )
      {
        case 4u:
          if ( v3 - v19 < 8 )
            __debugbreak();
          *(_BYTE *)v19 = 3;
          goto LABEL_53;
        case 5u:
          if ( v3 - v19 < 8 )
            __debugbreak();
          *(_BYTE *)v19 = 19;
LABEL_53:
          *(_DWORD *)(v19 + 4) = *((_DWORD *)v23 + 29);
          v26 = v19 + 11;
LABEL_54:
          v19 = v26 & 0xFFFFFFFFFFFFFFFCuLL;
          goto LABEL_88;
        case 7u:
          ++v73;
          goto LABEL_88;
      }
      goto LABEL_125;
    }
    v59 = v25 - 9;
    if ( v59 )
    {
      v60 = v59 - 1;
      if ( !v60 )
      {
        v88[0] = *((_DWORD *)v23 + 29);
        v88[1] = *((_DWORD *)v23 + 30);
        v66 = CMicrodomBuilder::CNamespaceNamePrefixToAttDef::Insert(
                (CMicrodomBuilder::CNamespaceNamePrefixToAttDef *)v113,
                (const struct CMicrodomBuilder::TwoStringIdPair *)&v83,
                (const struct CMicrodomBuilder::TwoStringIdPair *)v88,
                (const struct _MICRODOM_XML_ATTDEF *)(v23 + 14));
        v15 = 0;
        StringId = v66;
        if ( v66 < 0 )
          goto LABEL_149;
LABEL_119:
        ++v73;
        goto LABEL_87;
      }
      v61 = v60 - 2;
      if ( v61 )
      {
        v62 = v61 - 1;
        if ( !v62 )
        {
          if ( v3 - v19 < 8 )
            __debugbreak();
          *(_BYTE *)v19 = 6;
          goto LABEL_53;
        }
        if ( v62 == 1 )
        {
          if ( v3 - v19 < 4 )
            __debugbreak();
          v63 = v23[13];
          if ( v63 > 0xFFFF )
          {
            StringId = -1073741675;
            goto LABEL_145;
          }
          *(_WORD *)(v19 + 2) = v63;
          if ( v63 != (unsigned __int16)v63 )
          {
            StringId = -1073741595;
LABEL_145:
            v105 = 2661;
            v104[0] = "onecore\\base\\xml\\udom_builder.cpp";
            v104[1] = "CMicrodomBuilder::WriteXmlDom";
            v106 = "BUCL::Rtl::ConvertInteger(pObject->m_cChildren, pDocument->usChildNodes)";
            RtlReportErrorOrigination(v104, v13, (unsigned int)StringId);
            goto LABEL_149;
          }
          *(_BYTE *)v19 = 7;
          v64 = (v19 + 7) & 0xFFFFFFFFFFFFFFFCuLL;
          v65 = ((__int64 (__fastcall *)(CMicrodomBuilder *, unsigned __int64, __int64 *, __int64 *))v17)(
                  v6,
                  v64,
                  &v108,
                  v23);
          v15 = 0;
          StringId = v65;
          if ( v65 < 0 )
            goto LABEL_149;
          v37 = v108 + 3 + v64;
LABEL_86:
          v19 = v37 & 0xFFFFFFFFFFFFFFFCuLL;
LABEL_87:
          v13 = v80;
          goto LABEL_88;
        }
LABEL_125:
        __debugbreak();
        goto LABEL_88;
      }
      if ( v23[8] )
      {
        if ( v3 - v19 < 0xC )
          __debugbreak();
        *(_BYTE *)v19 = 5;
        *(_DWORD *)(v19 + 4) = *((_DWORD *)v23 + 29);
        *(_DWORD *)(v19 + 8) = *((_DWORD *)v23 + 30);
        v26 = v19 + 15;
        goto LABEL_54;
      }
    }
    else
    {
      v83 = -1;
      v84 = -1;
    }
LABEL_88:
    v23 = (__int64 *)*v23;
    v17 = v85;
  }
  v67 = v19 - *((_QWORD *)a2 + 2);
  *(_QWORD *)a2 = v67;
  if ( v67 > *((_QWORD *)a2 + 1) )
    __debugbreak();
  StringId = v110;
LABEL_149:
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
    v113,
    v13,
    v15);
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
    v125,
    v68,
    v69);
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
    v119,
    v70,
    v71);
  return (unsigned int)StringId;
}

```

## disassembly

```asm
0x1800566f0  mov     [rsp-8+arg_10], rbx
0x1800566f5  push    rbp
0x1800566f6  push    rsi
0x1800566f7  push    rdi
0x1800566f8  push    r12
0x1800566fa  push    r13
0x1800566fc  push    r14
0x1800566fe  push    r15
0x180056700  lea     rbp, [rsp-3E0h]
0x180056708  sub     rsp, 4E0h
0x18005670f  mov     rax, cs:__security_cookie
0x180056716  xor     rax, rsp
0x180056719  mov     [rbp+410h+var_40], rax
0x180056720  mov     r12, [rdx+8]
0x180056724  lea     r14, [rcx+4F0h]
0x18005672b  mov     rsi, [rdx]
0x18005672e  xor     ebx, ebx
0x180056730  add     r12, [rdx+10h]
0x180056734  mov     r13, rdx
0x180056737  add     rsi, [rdx+10h]
0x18005673b  mov     r15, rcx
0x18005673e  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x180056746  or      eax, 0FFFFFFFFh
0x180056749  mov     [rsp+510h+var_4C8], eax
0x18005674d  lea     r8d, [rbx+7]
0x180056751  mov     [rsp+510h+var_4C0], eax
0x180056755  lea     edx, [rbx+1]
0x180056758  mov     [rsp+510h+var_4BC], eax
0x18005675c  mov     [rsp+510h+var_4D8], eax
0x180056760  mov     [rsp+510h+var_4D4], eax
0x180056764  lea     rax, [rbp+410h+var_250]
0x18005676b  mov     [rbp+410h+var_278], rax
0x180056772  lea     rax, [rbp+410h+var_250]
0x180056779  mov     [rbp+410h+var_480], rcx
0x18005677d  mov     ecx, r8d
0x180056780  mov     [rbp+410h+var_3B4], ebx
0x180056783  mov     [rsp+510h+var_4E0], bx
0x180056788  mov     [rbp+410h+var_270], rbx
0x18005678f  mov     [rbp+410h+var_268], r8
0x180056796  movdqa  [rbp+410h+var_260], xmm0
0x18005679e  mov     [rax+18h], rbx
0x1800567a2  mov     [rax], rax
0x1800567a5  mov     [rax+8], rax
0x1800567a9  mov     [rax+10h], rax
0x1800567ad  add     rax, 20h ; ' '
0x1800567b1  sub     rcx, rdx
0x1800567b4  jnz     short loc_18005679E
0x1800567b6  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800567be  lea     rax, [rbp+410h+var_130]
0x1800567c5  movdqa  xmm1, cs:__xmm@00000000000000230000000000000000
0x1800567cd  mov     rcx, r8
0x1800567d0  mov     [rbp+410h+var_158], rax
0x1800567d7  lea     rax, [rbp+410h+var_130]
0x1800567de  movdqa  [rbp+410h+var_150], xmm0
0x1800567e6  movdqa  [rbp+410h+var_140], xmm1
0x1800567ee  mov     [rax+18h], rbx
0x1800567f2  mov     [rax], rax
0x1800567f5  mov     [rax+8], rax
0x1800567f9  mov     [rax+10h], rax
0x1800567fd  add     rax, 20h ; ' '
0x180056801  sub     rcx, rdx
0x180056804  jnz     short loc_1800567EE
0x180056806  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x18005680e  lea     rax, [rbp+410h+var_370]
0x180056815  mov     [rbp+410h+var_398], rax
0x180056819  mov     rcx, r8
0x18005681c  lea     rax, [rbp+410h+var_370]
0x180056823  mov     [rbp+410h+var_390], rbx
0x18005682a  mov     [rbp+410h+var_388], r8
0x180056831  movdqa  [rbp+410h+var_380], xmm0
0x180056839  mov     [rax+18h], rbx
0x18005683d  mov     [rax], rax
0x180056840  mov     [rax+8], rax
0x180056844  mov     [rax+10h], rax
0x180056848  add     rax, 20h ; ' '
0x18005684c  sub     rcx, rdx
0x18005684f  jnz     short loc_180056839
0x180056851  lea     rcx, [rbp+410h+var_280]
0x180056858  call    ?Initialize@?$CFourStringIdTable@G@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<ushort>::Initialize(void)
0x18005685d  mov     edi, eax
0x18005685f  test    eax, eax
0x180056861  js      loc_180057034
0x180056867  lea     rcx, [rbp+410h+var_160]
0x18005686e  call    ?Initialize@?$CFourStringIdTable@G@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<ushort>::Initialize(void)
0x180056873  mov     edi, eax
0x180056875  test    eax, eax
0x180056877  js      loc_180057034
0x18005687d  lea     rax, [rbp+410h+var_370]
0x180056884  lea     rcx, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x18005688b  cmp     [rbp+410h+var_398], rax
0x18005688f  jz      short loc_180056899
0x180056891  int     3; Trap to Debugger
0x180056892  mov     edi, 0C00000E5h
0x180056897  jmp     short loc_1800568CD
0x180056899  mov     rdx, [rbp+410h+var_388]
0x1800568a0  lea     r9, [rbp+410h+var_380+8]
0x1800568a7  mov     r8d, 5
0x1800568ad  lea     rcx, [rsp+510h+var_4B0]
0x1800568b2  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?AVCCallDisposition@Rtl@1@_K0AEA_K@Z; BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x1800568b7  mov     eax, [rsp+510h+var_4B0]
0x1800568bb  mov     edi, ebx
0x1800568bd  test    eax, eax
0x1800568bf  cmovs   edi, eax
0x1800568c2  test    edi, edi
0x1800568c4  jns     short loc_1800568FC
0x1800568c6  lea     rcx, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1800568cd  lea     rax, aCmicrodombuild_7; "CMicrodomBuilder::CFourStringIdTable<st"...
0x1800568d4  mov     [rbp+410h+var_478], rcx
0x1800568d8  mov     [rbp+410h+var_470], rax
0x1800568dc  lea     rcx, [rbp+410h+var_478]
0x1800568e0  lea     rax, aMStoredtableIn; "m_StoredTable.Initialize()"
0x1800568e7  mov     [rbp+410h+var_468], 0B2h
0x1800568ee  mov     r8d, edi
0x1800568f1  mov     [rbp+410h+var_460], rax
0x1800568f5  call    RtlReportErrorOrigination
0x1800568fa  jmp     short loc_1800568FE
0x1800568fc  mov     edi, ebx
0x1800568fe  test    edi, edi
0x180056900  js      loc_180057034
0x180056906  lea     r8, [rsp+510h+var_4C4]; unsigned int *
0x18005690b  mov     rcx, r15; this
0x18005690e  lea     rdx, qword_180063AA0; struct _LUTF8_STRING *
0x180056915  call    ?FindStringId@CMicrodomBuilder@@AEAAJAEBU_LUTF8_STRING@@PEAK@Z; CMicrodomBuilder::FindStringId(_LUTF8_STRING const &,ulong *)
0x18005691a  mov     edi, eax
0x18005691c  test    eax, eax
0x18005691e  js      loc_180057034
0x180056924  lea     r8, [rsp+510h+var_4AC]; unsigned int *
0x180056929  mov     rcx, r15; this
0x18005692c  lea     rdx, qword_180063A68; struct _LUTF8_STRING *
0x180056933  call    ?FindStringId@CMicrodomBuilder@@AEAAJAEBU_LUTF8_STRING@@PEAK@Z; CMicrodomBuilder::FindStringId(_LUTF8_STRING const &,ulong *)
0x180056938  mov     edi, eax
0x18005693a  test    eax, eax
0x18005693c  js      loc_180057034
0x180056942  mov     rdx, r12
0x180056945  sub     rdx, rsi
0x180056948  mov     [rsp+510h+var_4D0], rdx
0x18005694d  cmp     rdx, 14h
0x180056951  jnb     short loc_180056954
0x180056953  int     3; Trap to Debugger
0x180056954  mov     dword ptr [rsi], 6C44644Dh
0x18005695a  mov     r9d, 1
0x180056960  mov     eax, [r15+510h]
0x180056967  mov     [rsi+8], eax
0x18005696a  mov     eax, [r15+510h]
0x180056971  cmp     eax, 0FFh
0x180056976  ja      short loc_180056985
0x180056978  mov     [rsi+4], r9d
0x18005697c  lea     r10, ??$WriteDomElementIndicies@E@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<uchar>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x180056983  jmp     short loc_1800569AA
0x180056985  cmp     eax, 0FFFFh
0x18005698a  ja      short loc_18005699C
0x18005698c  mov     dword ptr [rsi+4], 2
0x180056993  lea     r10, ??$WriteDomElementIndicies@G@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<ushort>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x18005699a  jmp     short loc_1800569AA
0x18005699c  mov     dword ptr [rsi+4], 3
0x1800569a3  lea     r10, ??$WriteDomElementIndicies@K@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<ulong>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x1800569aa  mov     rcx, [r14]
0x1800569ad  lea     rbx, [rsi+17h]
0x1800569b1  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800569b5  mov     [rsp+510h+var_4B8], r10
0x1800569ba  cmp     rcx, r14
0x1800569bd  mov     r8d, 0
0x1800569c3  cmovz   rcx, r8
0x1800569c7  test    rcx, rcx
0x1800569ca  jnz     short loc_1800569CD
0x1800569cc  int     3; Trap to Debugger
0x1800569cd  cmp     word ptr [rcx+72h], 0Eh
0x1800569d2  jz      short loc_1800569D5
0x1800569d4  int     3; Trap to Debugger
0x1800569d5  mov     eax, [rcx+48h]
0x1800569d8  add     rcx, 58h ; 'X'
0x1800569dc  mov     [rsi+10h], eax
0x1800569df  mov     rax, [rcx]
0x1800569e2  jmp     short loc_1800569EE
0x1800569e4  cmp     [rax+42h], r8w
0x1800569e9  jz      short loc_180056A66
0x1800569eb  mov     rax, [rax]
0x1800569ee  cmp     rax, rcx
0x1800569f1  jnz     short loc_1800569E4
0x1800569f3  int     3; Trap to Debugger
0x1800569f4  mov     al, [rsp+510h+var_4DD]
0x1800569f8  mov     rsi, [r14]
0x1800569fb  mov     r14d, [rsp+510h+var_4C4]
0x180056a00  mov     [rsp+510h+var_4DE], al
0x180056a04  test    rsi, rsi
0x180056a07  jz      loc_180057022
0x180056a0d  lea     rax, [r15+4F0h]
0x180056a14  cmp     rsi, rax
0x180056a17  jz      loc_180057022
0x180056a1d  movzx   ecx, word ptr [rsi+72h]
0x180056a21  cmp     ecx, 8
0x180056a24  ja      loc_180056E80
0x180056a2a  jz      loc_180056DDB
0x180056a30  test    ecx, ecx
0x180056a32  jz      loc_180056C4F
0x180056a38  cmp     ecx, r9d
0x180056a3b  jz      short loc_180056AB3
0x180056a3d  jbe     loc_180056EA5
0x180056a43  cmp     ecx, 3
0x180056a46  jbe     short loc_180056AA3
0x180056a48  cmp     ecx, 4
0x180056a4b  jz      short loc_180056A91
0x180056a4d  cmp     ecx, 5
0x180056a50  jz      short loc_180056A6E
0x180056a52  cmp     ecx, 7
0x180056a55  jnz     loc_180056EA5
0x180056a5b  add     [rsp+510h+var_4E0], r9w
0x180056a61  jmp     loc_180056C42
0x180056a66  mov     eax, [rax+18h]
0x180056a69  mov     [rsi+0Ch], eax
0x180056a6c  jmp     short loc_1800569F4
0x180056a6e  mov     rax, r12
0x180056a71  sub     rax, rbx
0x180056a74  cmp     rax, 8
0x180056a78  jnb     short loc_180056A7B
0x180056a7a  int     3; Trap to Debugger
0x180056a7b  mov     byte ptr [rbx], 13h
0x180056a7e  mov     eax, [rsi+74h]
0x180056a81  mov     [rbx+4], eax
0x180056a84  add     rbx, 0Bh
0x180056a88  and     rbx, 0FFFFFFFFFFFFFFFCh
0x180056a8c  jmp     loc_180056C42
0x180056a91  mov     rax, r12
0x180056a94  sub     rax, rbx
0x180056a97  cmp     rax, 8
0x180056a9b  jnb     short loc_180056A9E
0x180056a9d  int     3; Trap to Debugger
0x180056a9e  mov     byte ptr [rbx], 3
0x180056aa1  jmp     short loc_180056A7E
0x180056aa3  or      eax, 0FFFFFFFFh
0x180056aa6  mov     [rsp+510h+var_4D8], eax
0x180056aaa  mov     [rsp+510h+var_4D4], eax
0x180056aae  jmp     loc_180056C42
0x180056ab3  mov     rax, r12
0x180056ab6  sub     rax, rbx
0x180056ab9  cmp     rax, 14h
0x180056abd  jnb     short loc_180056AC0
0x180056abf  int     3; Trap to Debugger
0x180056ac0  mov     eax, [rsi+78h]
0x180056ac3  lea     rdx, [rsp+510h+var_4A0]
0x180056ac8  mov     [rsp+510h+var_4A0], eax
0x180056acc  lea     rcx, [rbp+410h+var_160]
0x180056ad3  mov     eax, [rsi+7Ch]
0x180056ad6  mov     [rsp+510h+var_49C], eax
0x180056ada  or      eax, 0FFFFFFFFh
0x180056add  mov     [rsp+510h+var_498], eax
0x180056ae1  mov     [rsp+510h+var_494], eax
0x180056ae5  lea     rax, [rsp+510h+var_4DC]
0x180056aea  mov     [rsp+510h+var_4DA], r8w
0x180056af0  lea     r8, [rsp+510h+var_4DA]
0x180056af5  mov     [rsp+510h+var_4F0], rax
0x180056afa  call    ??$FindOrInsertIfNotPresent@UFourStringIdPair@CMicrodomBuilder@@G@?$CTable@VCTableTraits@?$CFourStringIdTable@G@CMicrodomBuilder@@@HashTable@BUCL@@QEAAJAEBUFourStringIdPair@CMicrodomBuilder@@AEBGPEAPEAGPEA_N@Z; BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>::FindOrInsertIfNotPresent<CMicrodomBuilder::FourStringIdPair,ushort>(CMicrodomBuilder::FourStringIdPair const &,ushort const &,ushort * *,bool *)
0x180056aff  mov     edi, eax
0x180056b01  test    eax, eax
0x180056b03  jns     short loc_180056B3B
0x180056b05  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x180056b0c  mov     [rbp+410h+var_448], 0D1h
0x180056b13  mov     [rbp+410h+var_458], rax
0x180056b17  lea     rcx, [rbp+410h+var_458]
0x180056b1b  lea     rax, aCmicrodombuild_18; "CMicrodomBuilder::CNamespaceNameExisten"...
0x180056b22  mov     r8d, edi
0x180056b25  mov     [rbp+410h+var_450], rax
0x180056b29  lea     rax, aMStoredtableFi_0; "m_StoredTable.FindOrInsertIfNotPresent("...
0x180056b30  mov     [rbp+410h+var_440], rax
0x180056b34  call    RtlReportErrorOrigination
0x180056b39  jmp     short loc_180056B48
0x180056b3b  cmp     [rsp+510h+var_4DC], 0
0x180056b40  jnz     loc_180056FA2
0x180056b46  xor     edi, edi
0x180056b48  test    edi, edi
0x180056b4a  js      loc_180057034
0x180056b50  mov     edi, [rsp+510h+var_4D4]
0x180056b54  mov     ecx, 22h ; '"'
0x180056b59  mov     r11d, [rsp+510h+var_4D8]
0x180056b5e  mov     byte ptr [rbx], 2
0x180056b61  mov     eax, [rsi+7Ch]
0x180056b64  mov     [rbx+0Ch], eax
0x180056b67  mov     eax, [rsi+78h]
0x180056b6a  mov     [rbx+8], eax
0x180056b6d  mov     eax, [rsi+74h]
0x180056b70  mov     [rbx+4], eax
0x180056b73  mov     eax, [rsi+80h]
0x180056b79  mov     [rbx+10h], eax
0x180056b7c  cmp     byte ptr [rsi+84h], 0
0x180056b83  movzx   eax, byte ptr [rbx]
0x180056b86  cmovz   eax, ecx
0x180056b89  and     [rbp+410h+var_3B0], 0
0x180056b8d  mov     [rbx], al
0x180056b8f  xor     edx, edx
0x180056b91  mov     r9d, [rsi+74h]
0x180056b95  mov     r10d, [rsi+7Ch]
0x180056b99  imul    eax, r9d, 1003Fh
0x180056ba0  imul    ecx, edi, 7E0F81h
0x180056ba6  imul    r8d, r11d, 2E86D0BFh
0x180056bad  add     ecx, r10d
0x180056bb0  add     ecx, eax
0x180056bb2  add     r8d, ecx
0x180056bb5  mov     eax, r8d
0x180056bb8  div     [rbp+410h+var_388]
0x180056bbf  shl     rdx, 5
  ... truncated ...
```
