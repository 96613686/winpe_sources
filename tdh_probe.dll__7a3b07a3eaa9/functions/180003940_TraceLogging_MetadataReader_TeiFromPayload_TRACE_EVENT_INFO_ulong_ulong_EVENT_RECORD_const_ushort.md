# TraceLogging::MetadataReader::TeiFromPayload(_TRACE_EVENT_INFO *,ulong,ulong *,_EVENT_RECORD const *,ushort *)

- ea: `0x180003940`
- end: `0x180004c8c`
- name: `?TeiFromPayload@MetadataReader@TraceLogging@@SAKPEAU_TRACE_EVENT_INFO@@KPEAKPEBU_EVENT_RECORD@@PEAG@Z`
- size: `4940`
- prototype: `__int64 __fastcall(struct _TRACE_EVENT_INFO *, unsigned int, unsigned int *, const struct _EVENT_RECORD *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800010c0`
- `0x180001730`
- `0x180003270`

## callees

- `0x180003940`
- `0x180005a70`
- `0x180007750`
- `0x18000d5b0`
- `0x1800120d8`
- `0x180012d38`
- `0x1800207c0`
- `0x180021490`
- `0x180023b05`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800039ff`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800039ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TraceLogging::MetadataReader::TeiFromPayload(
        struct _TRACE_EVENT_INFO *a1,
        unsigned int a2,
        unsigned int *a3,
        const struct _EVENT_RECORD *a4,
        unsigned __int16 *a5)
{
  struct _TRACE_EVENT_INFO *v5; // r15
  struct _EVENT_HEADER_EXTENDED_DATA_ITEM *v6; // r12
  const struct _EVENT_RECORD *v7; // r14
  USHORT ExtendedDataCount; // cx
  _WORD *UserData; // rbx
  __int64 UserDataLength; // rdi
  struct FieldVtbl *v12; // rdi
  unsigned __int16 v13; // ax
  _WORD *v14; // rbx
  __int64 v15; // rsi
  unsigned __int16 v16; // ax
  unsigned __int16 v17; // si
  char *v18; // rdx
  __int64 DataSize; // rax
  ULONG v20; // edi
  unsigned int v21; // r12d
  char v22; // r13
  unsigned int v23; // edi
  unsigned __int8 *v24; // r11
  unsigned int v25; // r9d
  unsigned __int8 *v26; // rcx
  unsigned __int8 v27; // al
  unsigned int v28; // edx
  __int16 v29; // r8
  unsigned int v30; // edx
  struct FieldVtbl *lpVtbl; // r8
  ULONG v32; // r12d
  unsigned __int8 *v33; // r11
  unsigned int v34; // r10d
  unsigned __int8 *v35; // rcx
  unsigned __int8 QueryInterface; // al
  unsigned int v37; // edx
  __int16 v38; // r9
  unsigned int v39; // edx
  unsigned int v40; // r12d
  struct FieldVtbl *v41; // rbx
  __int64 v42; // rdx
  int v43; // r10d
  char v44; // r8
  __int64 v45; // rcx
  unsigned int v46; // edi
  __int64 v47; // rsi
  struct FieldVtbl *v48; // rcx
  char v49; // r11
  __int64 v50; // rax
  struct _EVENT_PROPERTY_INFO *v51; // r13
  unsigned int v52; // edi
  struct FieldVtbl *v53; // rdx
  unsigned int v54; // r8d
  unsigned __int8 *v55; // r14
  unsigned __int8 *v56; // r9
  unsigned __int8 v57; // al
  __int16 v58; // cx
  unsigned int v59; // r8d
  unsigned int v60; // r9d
  unsigned __int8 *v61; // r14
  char v62; // r15
  int v63; // ecx
  bool v64; // r12
  __int16 v65; // r14
  int v66; // ecx
  int v67; // ecx
  __int16 v68; // dx
  char *v69; // rcx
  char *v70; // rdx
  int v71; // eax
  unsigned __int64 v72; // rdi
  USHORT v73; // ax
  PROPERTY_FLAGS v74; // eax
  ULONG lpVtbl_high; // eax
  PROPERTY_FLAGS Flags; // eax
  bool v77; // zf
  ULONG v78; // ecx
  unsigned __int16 v79; // ax
  ULONG TopLevelPropertyCount; // r8d
  __int64 v81; // rdx
  USHORT OutType; // r11
  int v84; // eax
  char v85; // r10
  __int64 *v86; // r9
  __int64 v87; // rcx
  char *v88; // r11
  int v89; // ecx
  char *v90; // rax
  unsigned int v91; // esi
  unsigned int v92; // edx
  __int64 v93; // rcx
  unsigned __int8 *v94; // r14
  int v95; // eax
  int v96; // edx
  const wchar_t *v97; // rcx
  USHORT CustomSchemaOffset_low; // cx
  ULONG v99; // edx
  unsigned int v100; // eax
  EVENT_DESCRIPTOR EventDescriptor; // xmm0
  __int16 v102; // cx
  __int16 v103; // ax
  char v104; // al
  unsigned int v105; // r8d
  char v106; // r9
  unsigned __int16 v107; // cx
  USHORT i; // r8
  struct _EVENT_HEADER_EXTENDED_DATA_ITEM *v109; // r10
  PEVENT_HEADER_EXTENDED_DATA_ITEM ExtendedData; // r11
  char v111; // r10
  unsigned int v112; // r10d
  char v113; // r11
  unsigned int v114; // r10d
  char v115; // di
  unsigned int v116; // r10d
  char v117; // r11
  unsigned int v118; // r11d
  char v119; // bl
  unsigned int v120; // r11d
  char v121; // di
  unsigned int v122; // r11d
  char v123; // r10
  unsigned int v124; // r10d
  char v125; // r11
  unsigned int v126; // r10d
  char v127; // bl
  unsigned int v128; // r10d
  unsigned int lpVtbl_low; // edx
  int v130; // esi
  unsigned __int8 *v131; // rax
  __int64 v132; // rbx
  _WORD *v133; // rdi
  __int64 v134; // rax
  __int16 v135; // ax
  unsigned __int8 v136; // r10
  unsigned __int8 v137; // dl
  unsigned __int8 v138; // r8
  __int64 v139; // rax
  __int64 NameOffset; // r9
  char *v141; // r8
  bool v142; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v143; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int8 v144[2]; // [rsp+42h] [rbp-BEh] BYREF
  unsigned int v145; // [rsp+44h] [rbp-BCh]
  unsigned __int8 v146; // [rsp+48h] [rbp-B8h] BYREF
  char v147; // [rsp+49h] [rbp-B7h]
  unsigned int v148; // [rsp+4Ch] [rbp-B4h] BYREF
  char v149; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v150; // [rsp+51h] [rbp-AFh]
  unsigned __int8 *v151; // [rsp+58h] [rbp-A8h]
  unsigned int v152; // [rsp+60h] [rbp-A0h]
  int v153; // [rsp+64h] [rbp-9Ch]
  Field v154[4]; // [rsp+68h] [rbp-98h] BYREF
  struct FieldVtbl *DataPtr; // [rsp+88h] [rbp-78h] BYREF
  struct FieldVtbl *v156; // [rsp+90h] [rbp-70h]
  unsigned __int64 v157; // [rsp+98h] [rbp-68h]
  const struct _EVENT_RECORD *v158; // [rsp+A0h] [rbp-60h]
  struct FieldVtbl *v159; // [rsp+A8h] [rbp-58h]
  struct _TRACE_EVENT_INFO *v160; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v161; // [rsp+B8h] [rbp-48h] BYREF
  struct _EVENT_HEADER_EXTENDED_DATA_ITEM *v162; // [rsp+C0h] [rbp-40h]
  struct FieldVtbl *v163; // [rsp+C8h] [rbp-38h]
  struct _EVENT_PROPERTY_INFO *v164; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v165; // [rsp+D8h] [rbp-28h]
  unsigned int *v166; // [rsp+E0h] [rbp-20h]
  _BYTE v167[2]; // [rsp+F0h] [rbp-10h] BYREF
  USHORT InType; // [rsp+F2h] [rbp-Eh]
  _WORD v169[382]; // [rsp+F4h] [rbp-Ch]
  __int64 v170; // [rsp+3F0h] [rbp+2F0h] BYREF

  v5 = a1;
  v160 = a1;
  *a3 = 0;
  v6 = 0;
  v165 = a5;
  v7 = a4;
  v158 = a4;
  *a5 = 0;
  ExtendedDataCount = a4->ExtendedDataCount;
  v166 = a3;
  v145 = a2;
  v162 = 0;
  if ( !ExtendedDataCount )
    goto LABEL_2;
  ExtendedData = a4->ExtendedData;
  v109 = 0;
  for ( i = 0; i < ExtendedDataCount; ++i )
  {
    if ( ExtendedData[i].ExtType == 11 )
    {
      v6 = &ExtendedData[i];
    }
    else if ( ExtendedData[i].ExtType == 12 )
    {
      v109 = &ExtendedData[i];
    }
  }
  v162 = v6;
  if ( !v109 )
  {
    if ( !v6 )
    {
LABEL_2:
      UserData = a4->UserData;
      UserDataLength = a4->UserDataLength;
      goto LABEL_3;
    }
    return 1392;
  }
  if ( !v6 )
    return 1392;
  UserData = (_WORD *)v109->DataPtr;
  UserDataLength = v109->DataSize;
LABEL_3:
  v12 = (struct FieldVtbl *)((char *)UserData + UserDataLength);
  v156 = v12;
  if ( (unsigned __int64)((char *)v12 - (char *)UserData) < 2 )
    return 1392;
  v13 = *UserData;
  v14 = UserData + 1;
  if ( v13 < 3u )
    return 1392;
  v15 = (unsigned __int16)(v13 - 2);
  if ( (struct FieldVtbl *)((char *)v14 + v15) > v12 )
    return 1392;
  v16 = strnlen((const char *)v14, (unsigned __int16)(v13 - 2));
  if ( v16 >= (unsigned __int16)v15 )
    return 1392;
  v17 = v15 - v16 - 1;
  v18 = (char *)v14 + v16 + 1;
  if ( (char *)v12 - v18 < v17 )
    return 1392;
  DataPtr = (struct FieldVtbl *)&v18[v17];
  if ( v6 )
  {
    DataSize = v6->DataSize;
    DataPtr = (struct FieldVtbl *)v6->DataPtr;
    v156 = (struct FieldVtbl *)((char *)DataPtr + DataSize);
  }
  v148 = 0;
  v144[0] = 0;
  v143 = 0;
  memset(v154, 0, sizeof(v154));
  if ( (unsigned int)Z::ReadFields<`TraceLogging::MetadataReader::TeiFromPayload'::`2'::PropertyCounter,unsigned long near * const volatile,_TRACE_EVENT_INFO *,unsigned long,unsigned long *,_EVENT_RECORD const *,unsigned short *>(
                       (unsigned int)&DataPtr,
                       (unsigned int)&v148,
                       (unsigned int)v154,
                       (unsigned int)v167,
                       (__int64)v144,
                       (__int64)&v143) )
    return 1392;
  v144[0] = v143;
  v20 = v143;
  v21 = 24 * v143 + 112;
  if ( v21 <= a2 )
  {
    v22 = 1;
    v142 = 1;
    memset_0(v5, 0, v21);
    v100 = 16 * v148;
    v5->ProviderGuid = v7->EventHeader.ProviderId;
    EventDescriptor = v7->EventHeader.EventDescriptor;
    v5->PropertyCount = v20;
    v5->Flags = v100;
    v5->EventDescriptor = EventDescriptor;
    v5->DecodingSource = DecodingSourceTlg;
  }
  else
  {
    v22 = 0;
    v142 = 0;
  }
  v23 = v145;
  v24 = (unsigned __int8 *)v5 + v21;
  v25 = 0;
  v151 = v24;
  v26 = v24;
  if ( v145 >= v21 )
    v25 = v145 - v21;
  v27 = *(_BYTE *)v14;
  v28 = 0;
  if ( *(_BYTE *)v14 )
  {
    do
    {
      v29 = v27;
      v14 = (_WORD *)((char *)v14 + 1);
      if ( v27 > 0xBFu )
      {
        v111 = *(_BYTE *)v14;
        if ( (*(_BYTE *)v14 & 0xC0) == 0x80 )
        {
          if ( v27 > 0xDFu )
          {
            v113 = *((_BYTE *)v14 + 1);
            if ( (v113 & 0xC0) == 0x80 )
            {
              if ( v27 > 0xEFu )
              {
                v115 = *((_BYTE *)v14 + 2);
                if ( (v115 & 0xC0) == 0x80 && v27 <= 0xF4u )
                {
                  v116 = (((v27 & 7) << 18) | v115 & 0x3F | ((v113 & 0x3F | ((v111 & 0x3F) << 6)) << 6)) - 0x10000;
                  if ( v116 <= 0xFFFFF )
                  {
                    v28 += 2;
                    if ( v28 <= v25 )
                    {
                      *(_WORD *)v26 = (v116 >> 10) | 0xD800;
                      v26 += 2;
                    }
                    v29 = v116 & 0x3FF | 0xDC00;
                    v14 = (_WORD *)((char *)v14 + 3);
                  }
                }
              }
              else
              {
                v114 = ((v27 & 0xF) << 12) | v113 & 0x3F | ((v111 & 0x3F) << 6);
                if ( v114 >= 0x800 )
                {
                  v29 = v114;
                  ++v14;
                }
              }
            }
          }
          else
          {
            v112 = ((v27 & 0x1F) << 6) | v111 & 0x3F;
            if ( v112 >= 0x80 )
            {
              v29 = v112;
              v14 = (_WORD *)((char *)v14 + 1);
            }
          }
        }
      }
      v28 += 2;
      if ( v28 <= v25 )
      {
        *(_WORD *)v26 = v29;
        v26 += 2;
      }
      v27 = *(_BYTE *)v14;
    }
    while ( *(_BYTE *)v14 );
    v23 = v145;
    v24 = v151;
  }
  v30 = v28 + 2;
  if ( v30 <= v25 )
    *(_WORD *)v26 = 0;
  if ( v22 && v30 + v21 <= v23 )
    v5->ProviderNameOffset = v21;
  lpVtbl = v154[0].lpVtbl;
  v32 = v30 + v21;
  v33 = &v24[v30];
  v34 = v23 - v32;
  v151 = v33;
  v35 = v33;
  if ( v23 < v32 )
    v34 = 0;
  QueryInterface = (unsigned __int8)v154[0].lpVtbl->QueryInterface;
  v37 = 0;
  if ( LOBYTE(v154[0].lpVtbl->QueryInterface) )
  {
    do
    {
      v38 = QueryInterface;
      lpVtbl = (struct FieldVtbl *)((char *)lpVtbl + 1);
      if ( QueryInterface > 0xBFu )
      {
        v117 = (char)lpVtbl->QueryInterface;
        if ( ((__int64)lpVtbl->QueryInterface & 0xC0) == 0x80 )
        {
          if ( QueryInterface > 0xDFu )
          {
            v119 = BYTE1(lpVtbl->QueryInterface);
            if ( (v119 & 0xC0) == 0x80 )
            {
              if ( QueryInterface > 0xEFu )
              {
                v121 = BYTE2(lpVtbl->QueryInterface);
                if ( (v121 & 0xC0) == 0x80 && QueryInterface <= 0xF4u )
                {
                  v122 = (((QueryInterface & 7) << 18) | v121 & 0x3F | ((v119 & 0x3F | ((v117 & 0x3F) << 6)) << 6))
                       - 0x10000;
                  if ( v122 <= 0xFFFFF )
                  {
                    v37 += 2;
                    if ( v37 <= v34 )
                    {
                      *(_WORD *)v35 = (v122 >> 10) | 0xD800;
                      v35 += 2;
                    }
                    v38 = v122 & 0x3FF | 0xDC00;
                    lpVtbl = (struct FieldVtbl *)((char *)lpVtbl + 3);
                  }
                }
              }
              else
              {
                v120 = ((QueryInterface & 0xF) << 12) | v119 & 0x3F | ((v117 & 0x3F) << 6);
                if ( v120 >= 0x800 )
                {
                  v38 = v120;
                  lpVtbl = (struct FieldVtbl *)((char *)lpVtbl + 2);
                }
              }
            }
          }
          else
          {
            v118 = ((QueryInterface & 0x1F) << 6) | v117 & 0x3F;
            if ( v118 >= 0x80 )
            {
              v38 = v118;
              lpVtbl = (struct FieldVtbl *)((char *)lpVtbl + 1);
            }
          }
        }
      }
      v37 += 2;
      if ( v37 <= v34 )
      {
        *(_WORD *)v35 = v38;
        v35 += 2;
      }
      QueryInterface = (unsigned __int8)lpVtbl->QueryInterface;
    }
    while ( LOBYTE(lpVtbl->QueryInterface) );
    v23 = v145;
    v33 = v151;
  }
  v39 = v37 + 2;
  if ( v39 <= v34 )
    *(_WORD *)v35 = 0;
  if ( v22 && v39 + v32 <= v23 )
  {
    v5->EventNameOffset = v32;
    v40 = v39 + v32;
    v151 = &v33[v39];
    goto LABEL_36;
  }
  v40 = v39 + v32;
  v151 = &v33[v39];
  if ( v22 )
LABEL_36:
    v5->TaskNameOffset = v5->EventNameOffset;
  v41 = v156;
  if ( (BYTE1(v154[1].lpVtbl) & 0x7F) == 0 )
  {
    if ( v22 )
      v5->TopLevelPropertyCount = 0;
    goto LABEL_125;
  }
  LOBYTE(v42) = 1;
  LOBYTE(v43) = v144[0];
  v163 = DataPtr;
  v147 = 0;
  v159 = v156;
LABEL_39:
  while ( 2 )
  {
    v42 = *((unsigned __int8 *)&InType + 6 * (unsigned __int8)v42 + 1);
    v44 = *((_BYTE *)&InType + 6 * (unsigned __int8)v167[6 * (unsigned __int8)v167[6 * v42] + 1] + 1);
    do
    {
      v45 = 3LL * (unsigned __int8)v42;
      LOBYTE(v42) = v167[6 * (unsigned __int8)v42 + 1];
      if ( (_BYTE)v42 )
        goto LABEL_39;
      LOBYTE(v42) = *((_BYTE *)&InType + 2 * v45 + 1);
    }
    while ( (_BYTE)v42 != v44 );
LABEL_42:
    v150 = v43;
    v149 = v42;
    do
    {
      v46 = v145;
      v47 = (unsigned __int8)v42;
      memset(&v154[1], 0, 24);
      v157 = 6LL * (unsigned __int8)v42;
      v48 = (struct FieldVtbl *)((char *)v163 + (unsigned __int16)v169[v157 / 2]);
      v154[0].lpVtbl = v48;
      while ( LOBYTE(v48->QueryInterface) )
      {
        v48 = (struct FieldVtbl *)((char *)v48 + 1);
        if ( v48 == v41 )
          goto LABEL_46;
      }
      v69 = (char *)&v48->QueryInterface + 1;
      if ( v41 == (struct FieldVtbl *)v69 )
        goto LABEL_46;
      v49 = *v69;
      v70 = v69 + 1;
      v143 = v49;
      LOBYTE(v154[1].lpVtbl) = v49;
      DataPtr = (struct FieldVtbl *)(v69 + 1);
      HIDWORD(v154[1].lpVtbl) = 0;
      if ( v49 < 0 )
      {
        if ( v41 == (struct FieldVtbl *)v70 )
          goto LABEL_48;
        v104 = *v70;
        v70 = v69 + 2;
        BYTE1(v154[1].lpVtbl) = v104;
        DataPtr = (struct FieldVtbl *)(v69 + 2);
        if ( v104 < 0 )
        {
          HIDWORD(v154[1].lpVtbl) = 0;
          v105 = 0;
          while ( v41 != (struct FieldVtbl *)v70 )
          {
            v106 = *v70++;
            DataPtr = (struct FieldVtbl *)v70;
            if ( v105 <= 0x15 )
            {
              HIDWORD(v154[1].lpVtbl) |= (v106 & 0x7F) << (21 - v105);
              v105 += 7;
            }
            if ( v106 >= 0 )
              goto LABEL_81;
          }
          goto LABEL_48;
        }
      }
      else
      {
        BYTE1(v154[1].lpVtbl) = 0;
      }
LABEL_81:
      WORD1(v154[1].lpVtbl) = 0;
      v71 = v49 & 0x60;
      if ( v71 == 32 )
      {
        if ( (unsigned __int64)((char *)v41 - v70) >= 2 )
        {
          v107 = *(_WORD *)v70;
          WORD1(v154[1].lpVtbl) = *(_WORD *)v70;
          if ( (v49 & 0x7F) == 0x20 && v107 <= 0x7Fu )
          {
            BYTE1(v154[1].lpVtbl) = v107;
            v49 = 24;
            WORD1(v154[1].lpVtbl) = 0;
            LOBYTE(v154[1].lpVtbl) = 24;
            goto LABEL_47;
          }
        }
      }
      else if ( v71 == 96 )
      {
        if ( !(unsigned int)TraceLogging::MetadataReader::ReadValue<unsigned short>(&DataPtr, &v154[3])
          && LOWORD(v154[3].lpVtbl) )
        {
          v154[2].lpVtbl = DataPtr;
          TraceLogging::MetadataReader::Skip<unsigned short>(&DataPtr);
        }
        v41 = v156;
        v159 = v156;
LABEL_46:
        v49 = (char)v154[1].lpVtbl;
LABEL_47:
        v143 = v49;
      }
LABEL_48:
      v50 = (unsigned __int8)(v43 - 1);
      v146 = v50;
      v43 = (unsigned __int8)v50;
      v153 = (unsigned __int8)v50;
      if ( v22 )
        v51 = (EVENT_PROPERTY_INFO *)((char *)v5->EventPropertyInfoArray + 16 * v50 + 8 * v50);
      else
        v51 = 0;
      v164 = v51;
      if ( v46 < v40 )
        v52 = 0;
      else
        v52 = v46 - v40;
      v53 = v154[0].lpVtbl;
      v54 = 0;
      v55 = v151;
      v56 = v151;
      v57 = (unsigned __int8)v154[0].lpVtbl->QueryInterface;
      if ( LOBYTE(v154[0].lpVtbl->QueryInterface) )
      {
        do
        {
          v58 = v57;
          v53 = (struct FieldVtbl *)((char *)v53 + 1);
          if ( v57 > 0xBFu )
          {
            v123 = (char)v53->QueryInterface;
            if ( ((__int64)v53->QueryInterface & 0xC0) == 0x80 )
            {
              if ( v57 > 0xDFu )
              {
                v125 = BYTE1(v53->QueryInterface);
                if ( (v125 & 0xC0) == 0x80 )
                {
                  if ( v57 > 0xEFu )
                  {
                    v127 = BYTE2(v53->QueryInterface);
                    if ( (v127 & 0xC0) == 0x80 && v57 <= 0xF4u )
                    {
                      v128 = (((v57 & 7) << 18) | v127 & 0x3F | ((v125 & 0x3F | ((v123 & 0x3F) << 6)) << 6)) - 0x10000;
                      if ( v128 <= 0xFFFFF )
                      {
                        v54 += 2;
                        if ( v54 <= v52 )
                        {
                          *(_WORD *)v56 = (v128 >> 10) | 0xD800;
                          v56 += 2;
                        }
                        v58 = v128 & 0x3FF | 0xDC00;
                        v53 = (struct FieldVtbl *)((char *)v53 + 3);
                      }
                    }
                  }
                  else
                  {
                    v126 = ((v57 & 0xF) << 12) | v125 & 0x3F | ((v123 & 0x3F) << 6);
                    if ( v126 >= 0x800 )
                    {
                      v58 = v126;
                      v53 = (struct FieldVtbl *)((char *)v53 + 2);
                    }
                  }
                }
              }
              else
              {
                v124 = ((v57 & 0x1F) << 6) | v123 & 0x3F;
                if ( v124 >= 0x80 )
                {
                  v58 = v124;
                  v53 = (struct FieldVtbl *)((char *)v53 + 1);
                }
              }
            }
          }
          v54 += 2;
          if ( v54 <= v52 )
          {
            *(_WORD *)v56 = v58;
            v56 += 2;
          }
          v57 = (unsigned __int8)v53->QueryInterface;
        }
        while ( LOBYTE(v53->QueryInterface) );
        v41 = v159;
        v49 = v143;
        v43 = v153;
        v55 = v151;
      }
      v59 = v54 + 2;
      if ( v59 <= v52 )
        *(_WORD *)v56 = 0;
      v60 = v145;
      if ( v142 && v59 + v40 <= v145 )
        v51->NameOffset = v40;
      v40 += v59;
      v61 = &v55[v59];
      v152 = v40;
      v148 = v40;
      v151 = v61;
      v161 = v61;
      if ( v51 )
      {
        lpVtbl_high = HIDWORD(v154[1].lpVtbl);
        if ( HIDWORD(v154[1].lpVtbl) )
        {
          v51->Flags |= 0x40u;
          v51->Reserved = lpVtbl_high;
        }
      }
      v62 = v49 & 0x60;
      if ( (v49 & 0x60) == 0x20 && !WORD1(v154[1].lpVtbl) )
      {
        v72 = v157;
        if ( !v51 )
          goto LABEL_91;
        *(_DWORD *)&v51->nonStructType.InType = 0;
        goto LABEL_119;
      }
      v63 = v49 & 0x1F;
      if ( v63 == 24 )
      {
        if ( v62 != 96 )
        {
          v72 = v157;
          if ( v51 )
          {
            if ( v167[v157 + 1] )
            {
              CustomSchemaOffset_low = (unsigned __int8)LOWORD(v160->EventPropertyInfoArray[v47].customSchemaType.CustomSchemaOffset);
              v99 = v160->EventPropertyInfoArray[v47].nonStructType.MapNameOffset >> 8;
              v160->EventPropertyInfoArray[v47].nonStructType.MapNameOffset = 0;
            }
            else
            {
              LOWORD(v99) = 0;
              CustomSchemaOffset_low = 0;
            }
            v51->nonStructType.InType = CustomSchemaOffset_low;
            v43 = v153;
            v51->nonStructType.OutType = v99;
            v51->length = 0;
          }
          if ( (v49 & 0x40) != 0 || (v49 & 0x1F) == 0xE )
          {
            if ( v51 )
            {
              v51->Flags |= 5u;
              v51->count = (unsigned __int8)v43 - 1;
              v90 = (char *)&v51[-1];
              *((_WORD *)v90 + 4) = 6;
              --v51;
              *((_DWORD *)v90 + 4) = 131073;
            }
            v91 = v145;
            LOBYTE(v43) = v43 - 1;
            v153 = v43;
            v148 = 0;
            if ( v145 < v40 )
              v92 = 0;
            else
              v92 = v145 - v40;
            TraceLogging::MetadataReader::Utf16FromUtf8((wchar_t *)v61, v92, &v148, (char *)v154[0].lpVtbl);
            v93 = v148;
            if ( v142 && v148 + v40 <= v91 )
              v51->NameOffset = v40;
            v94 = &v61[v93 - 2];
            v95 = v40 + v93 - 2;
            v151 = v94;
            v96 = v95;
            v97 = L".Count";
            do
            {
              v96 += 2;
              if ( v95 + 2 <= v91 )
              {
                *(_WORD *)v94 = *v97;
                v94 += 2;
              }
              ++v97;
              v95 = v96;
            }
            while ( *v97 );
            v40 = v96 + 2;
            v151 = v94;
            if ( v96 + 2 <= v91 )
            {
              *(_WORD *)v94 = 0;
              v151 = v94 + 2;
            }
            LOBYTE(v43) = v153;
            goto LABEL_91;
          }
          if ( !v51 )
          {
LABEL_91:
            v22 = v142;
            goto LABEL_92;
          }
          Flags = v51->Flags;
          if ( v62 == 32 )
          {
            v51->Flags = Flags | 0x21;
            v51->count = WORD1(v154[1].lpVtbl);
            goto LABEL_91;
          }
          v51->Flags = Flags | 1;
LABEL_119:
          v51->count = 1;
          goto LABEL_91;
        }
LABEL_263:
        lpVtbl_low = LOWORD(v154[3].lpVtbl);
        v64 = 1;
        v65 = 14;
        v130 = LOWORD(v154[3].lpVtbl) + 4;
        if ( v51 && v130 + v152 <= v60 )
        {
          v131 = v151;
          v132 = LOWORD(v154[3].lpVtbl);
          v51->Flags |= 0x80u;
          v133 = v131 + 2;
          v147 = 1;
          *(_WORD *)v131 = v63;
          *((_WORD *)v131 + 1) = lpVtbl_low;
          memcpy_0(v131 + 4, v154[2].lpVtbl, lpVtbl_low);
          v49 = v143;
          v134 = v132 + 2;
          v41 = v159;
          LOBYTE(v43) = v153;
          v151 = (unsigned __int8 *)v133 + v134;
          v161 = (unsigned __int8 *)v133 + v134;
        }
        v152 += v130;
        v148 = v152;
        goto LABEL_70;
      }
      if ( v62 == 96 )
        goto LABEL_263;
      v64 = 0;
      v65 = v49 & 0x1F;
      if ( (v49 & 0x1F) != 0 )
      {
        v66 = v63 - 14;
        if ( v66 )
        {
          v67 = v66 - 8;
          if ( v67 )
          {
            if ( v67 == 1 )
              v65 = 301;
          }
          else
          {
            v65 = 300;
          }
        }
        else
        {
          if ( v62 )
            return 1392;
          v64 = 1;
        }
      }
      else if ( v62 )
      {
        return 1392;
      }
LABEL_70:
      if ( (BYTE1(v154[1].lpVtbl) & 0x7Fu) < 0x20 )
      {
        switch ( BYTE1(v154[1].lpVtbl) & 0x7F )
        {
          case 1:
            v68 = 301;
            break;
          case 2:
            v68 = 1;
            break;
          case 3:
            v68 = 13;
            break;
          case 4:
            switch ( v65 )
            {
              case 4:
                v68 = 16;
                break;
              case 6:
                v68 = 17;
                break;
              case 8:
                v68 = 18;
                break;
              case 10:
                v68 = 19;
                break;
              default:
                v68 = 15;
                break;
            }
            break;
          case 5:
            v68 = 20;
            break;
          case 6:
            v68 = 21;
            break;
          case 7:
            v68 = 22;
            break;
          case 8:
            v68 = 23;
            break;
          case 9:
            v68 = 24;
            break;
          case 0xA:
            v68 = 25;
            break;
          case 0xB:
            v68 = 28;
            break;
          case 0xC:
            v68 = 34;
            break;
          case 0xD:
            v68 = 30;
            break;
          case 0xE:
            v68 = 31;
            break;
          case 0xF:
            v68 = 32;
            break;
          default:
            v68 = 0;
            break;
        }
      }
      else
      {
        v68 = BYTE1(v154[1].lpVtbl) & 0x7F;
      }
      if ( v51 && !v64 )
      {
        switch ( v65 )
        {
          case 21:
LABEL_87:
            v51->length = 8;
            break;
          case 20:
LABEL_109:
            v51->length = 4;
            break;
          case 14:
LABEL_77:
            v51->length = 1;
            break;
          default:
            switch ( v65 )
            {
              case 3:
              case 4:
                goto LABEL_77;
              case 5:
              case 6:
                v51->length = 2;
                break;
              case 7:
              case 8:
              case 11:
              case 13:
                goto LABEL_109;
              case 9:
              case 10:
              case 12:
              case 17:
                goto LABEL_87;
              case 15:
              case 18:
                v51->length = 16;
                break;
              case 16:
                if ( (v158->EventHeader.Flags & 0x20) != 0 )
                  v135 = 4;
                else
                  v135 = 8;
                v51->length = v135;
                break;
              default:
                goto LABEL_88;
            }
            break;
        }
      }
LABEL_88:
      if ( (v49 & 0x40) == 0 && (v49 & 0x1F) != 0xE )
      {
        v40 = v152;
        v72 = v157;
        if ( !v51 )
          goto LABEL_91;
        v51->nonStructType.InType = v65;
        v51->nonStructType.OutType = v68;
        if ( v62 )
        {
          v73 = WORD1(v154[1].lpVtbl);
          v51->Flags |= 0x20u;
          v51->count = v73;
          goto LABEL_91;
        }
        goto LABEL_119;
      }
      if ( v51 )
      {
        v51->nonStructType.InType = v65;
        v51->nonStructType.OutType = v68;
        v74 = v51->Flags;
        if ( v64 )
        {
          v51->Flags = v74 | 2;
          v51->count = 1;
          v51->length = (unsigned __int8)v43 - 1;
        }
        else
        {
          v51->Flags = v74 | 4;
          v51->count = (unsigned __int8)v43 - 1;
        }
      }
      v22 = v142;
      TraceLogging::MetadataReader::AddImpliedProperty(v154, &v164, &v161, &v146, &v148, v145, v142, v64);
      v40 = v148;
      LOBYTE(v43) = v146;
      v72 = v157;
      v151 = v161;
LABEL_92:
      v42 = *((unsigned __int8 *)&InType + v72 + 1);
      v5 = v160;
    }
    while ( (_BYTE)v42 != v149 );
    if ( v22 )
      v160->EventPropertyInfoArray[(unsigned __int8)v167[6 * v42]].nonStructType.MapNameOffset = (unsigned __int8)v43
                                                                                               | ((v150
                                                                                                 - (unsigned __int8)v43) << 8);
    v42 = (unsigned __int8)v167[6 * v42];
    if ( (_BYTE)v42 )
    {
      if ( (_BYTE)v42 != v167[6 * (unsigned __int8)v167[6 * v42] + 1] )
        continue;
      LOBYTE(v42) = *((_BYTE *)&InType + 6 * v42 + 1);
      goto LABEL_42;
    }
    break;
  }
  v23 = v145;
  if ( v22 )
  {
    v77 = v147 == 0;
    v78 = (unsigned __int16)(v5->EventPropertyInfoArray[0].nonStructType.MapNameOffset >> 8);
    v5->EventPropertyInfoArray[0].nonStructType.MapNameOffset = 0;
    v5->TopLevelPropertyCount = v78;
    if ( !v77 && v40 <= v23 )
    {
      v136 = v144[0];
      if ( v144[0] )
      {
        v137 = 0;
        v138 = 0;
        do
        {
          if ( SLOBYTE(v5->EventPropertyInfoArray[v137].Flags) < 0 )
          {
            v139 = -1;
            NameOffset = v5->EventPropertyInfoArray[v138].NameOffset;
            v141 = (char *)v5 + 24 * v138;
            do
              ++v139;
            while ( *(_WORD *)((char *)&v5->ProviderGuid.Data1 + 2 * v139 + NameOffset) );
            *((_DWORD *)v141 + 31) = NameOffset + 2 * (v139 + 1);
          }
          v138 = ++v137;
        }
        while ( v137 != v136 );
      }
    }
  }
  v7 = v158;
LABEL_125:
  if ( v162 )
    v79 = 0;
  else
    v79 = (_WORD)v41 - LOWORD(v7->UserData);
  *v165 = v79;
  *v166 = v40;
  if ( v40 > v23 )
    return 122;
  TopLevelPropertyCount = v5->TopLevelPropertyCount;
  if ( !TopLevelPropertyCount )
    return 0;
  v81 = 0;
  while ( 2 )
  {
    if ( (v5->EventPropertyInfoArray[v81].Flags & 1) == 0 )
    {
LABEL_131:
      v81 = (unsigned int)(v81 + 1);
      if ( (_DWORD)v81 == TopLevelPropertyCount )
        return 0;
      continue;
    }
    break;
  }
  OutType = v5->EventPropertyInfoArray[v81].nonStructType.OutType;
  v84 = v5->EventPropertyInfoArray[v81].Flags & 0x24;
  v85 = v84 != 0;
  if ( !OutType )
  {
    if ( v84 )
      return 13;
    goto LABEL_131;
  }
  v86 = (__int64 *)v167;
  InType = v5->EventPropertyInfoArray[v81].nonStructType.InType;
  v169[0] = OutType + InType;
  v167[0] = v84 != 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v87 = *((unsigned __int16 *)v86 + 1);
      *((_WORD *)v86 + 1) = v87 + 1;
      v88 = (char *)v5 + 24 * v87;
      v89 = *((_DWORD *)v88 + 28);
      if ( (v89 & 1) != 0 )
        break;
      if ( v85 && (!*((_WORD *)v88 + 60) || !*((_WORD *)v88 + 64) && (v89 & 4) == 0) )
        return 13;
LABEL_150:
      while ( *((_WORD *)v86 + 1) == *((_WORD *)v86 + 2) )
      {
        if ( v86 == (__int64 *)v167 )
          goto LABEL_131;
        v86 = (__int64 *)((char *)v86 - 6);
      }
      v85 = *(_BYTE *)v86;
    }
    v85 = v85 || (v89 & 0x24) != 0;
    v102 = *((_WORD *)v88 + 61);
    if ( !v102 )
      break;
    v86 = (__int64 *)((char *)v86 + 6);
    if ( v86 >= &v170 )
      return 13;
    v103 = *((_WORD *)v88 + 60);
    *((_WORD *)v86 + 1) = v103;
    *((_WORD *)v86 + 2) = v102 + v103;
    *(_BYTE *)v86 = v85;
  }
  if ( !v85 )
    goto LABEL_150;
  return 13;
}

```

## disassembly

```asm
0x180003940  mov     [rsp-8+arg_8], rbx
0x180003945  push    rbp
0x180003946  push    rsi
0x180003947  push    rdi
0x180003948  push    r12
0x18000394a  push    r13
0x18000394c  push    r14
0x18000394e  push    r15
0x180003950  lea     rbp, [rsp-300h]
0x180003958  sub     rsp, 400h
0x18000395f  mov     rax, cs:__security_cookie
0x180003966  xor     rax, rsp
0x180003969  mov     [rbp+330h+var_40], rax
0x180003970  mov     r15, rcx
0x180003973  mov     [rbp+330h+var_380], rcx
0x180003977  mov     rcx, [rbp+330h+arg_20]
0x18000397e  xor     eax, eax
0x180003980  mov     dword ptr [r8], 0
0x180003987  xor     r12d, r12d
0x18000398a  mov     [rbp+330h+var_358], rcx
0x18000398e  mov     r14, r9
0x180003991  mov     [rbp+330h+var_390], r9
0x180003995  mov     r13d, edx
0x180003998  mov     [rcx], ax
0x18000399b  movzx   ecx, word ptr [r9+54h]
0x1800039a0  mov     [rbp+330h+var_350], r8
0x1800039a4  mov     [rsp+430h+var_3EC], edx
0x1800039a8  mov     [rbp+330h+var_370], r12
0x1800039ac  cmp     ax, cx
0x1800039af  jb      loc_1800046AC
0x1800039b5  mov     rbx, [r14+60h]
0x1800039b9  movzx   edi, word ptr [r14+56h]
0x1800039be  add     rdi, rbx
0x1800039c1  mov     rax, rdi
0x1800039c4  mov     [rbp+330h+var_3A0], rdi
0x1800039c8  sub     rax, rbx
0x1800039cb  cmp     rax, 2
0x1800039cf  jb      loc_180004157
0x1800039d5  movzx   eax, word ptr [rbx]
0x1800039d8  add     rbx, 2
0x1800039dc  cmp     ax, 3
0x1800039e0  jb      loc_180004157
0x1800039e6  sub     ax, 2
0x1800039ea  movzx   esi, ax
0x1800039ed  lea     rax, [rsi+rbx]
0x1800039f1  cmp     rax, rdi
0x1800039f4  ja      loc_180004157
0x1800039fa  mov     edx, esi; MaxCount
0x1800039fc  mov     rcx, rbx; String
0x1800039ff  call    cs:__imp_strnlen
0x180003a05  cmp     ax, si
0x180003a08  jnb     loc_180004157
0x180003a0e  sub     si, ax
0x180003a11  movzx   edx, ax
0x180003a14  inc     rdx
0x180003a17  dec     si
0x180003a1a  add     rdx, rbx
0x180003a1d  movzx   eax, si
0x180003a20  sub     rdi, rdx
0x180003a23  cmp     rdi, rax
0x180003a26  jl      loc_180004157
0x180003a2c  add     rax, rdx
0x180003a2f  mov     [rbp+330h+var_3A8], rax
0x180003a33  test    r12, r12
0x180003a36  jz      short loc_180003A4E
0x180003a38  mov     rcx, [r12+8]
0x180003a3d  movzx   eax, word ptr [r12+6]
0x180003a43  add     rax, rcx
0x180003a46  mov     [rbp+330h+var_3A8], rcx
0x180003a4a  mov     [rbp+330h+var_3A0], rax
0x180003a4e  xorps   xmm0, xmm0
0x180003a51  mov     [rsp+430h+var_3E4], 0
0x180003a59  lea     rax, [rsp+430h+var_3EF]
0x180003a5e  mov     [rsp+430h+var_3EE], 0
0x180003a63  mov     qword ptr [rsp+430h+var_408], rax
0x180003a68  lea     r9, [rbp+330h+var_340]
0x180003a6c  lea     rax, [rsp+430h+var_3EE]
0x180003a71  mov     [rsp+430h+var_3EF], 0
0x180003a76  lea     r8, [rsp+430h+var_3C8]
0x180003a7b  mov     [rsp+430h+var_410], rax
0x180003a80  lea     rdx, [rsp+430h+var_3E4]
0x180003a85  lea     rcx, [rbp+330h+var_3A8]
0x180003a89  movups  xmmword ptr [rsp+430h+var_3C8.lpVtbl], xmm0
0x180003a8e  movups  xmmword ptr [rsp+430h+Src], xmm0
0x180003a93  call    ??$ReadFields@UPropertyCounter@?1??TeiFromPayload@MetadataReader@TraceLogging@@SAKPEAU_TRACE_EVENT_INFO@@KPEAKPEBU_EVENT_RECORD@@PEAG@Z@@MetadataReader@TraceLogging@@AEAAKAEAIAEAUField@01@QEAUFieldNode@01@AEAEAEAUPropertyCounter@?1??TeiFromPayload@01@SAKPEAU_TRACE_EVENT_INFO@@KPEAKPEBU_EVENT_RECORD@@PEAG@Z@@Z; TraceLogging::MetadataReader::ReadFields<`TraceLogging::MetadataReader::TeiFromPayload(_TRACE_EVENT_INFO *,ulong,ulong *,_EVENT_RECORD const *,ushort *)'::`2'::PropertyCounter>(uint &,TraceLogging::MetadataReader::Field &,TraceLogging::MetadataReader::FieldNode * const,uchar &,`TraceLogging::MetadataReader::TeiFromPayload(_TRACE_EVENT_INFO *,ulong,ulong *,_EVENT_RECORD const *,ushort *)'::`2'::PropertyCounter &)
0x180003a98  test    eax, eax
0x180003a9a  jnz     loc_180004157
0x180003aa0  movzx   eax, [rsp+430h+var_3EF]
0x180003aa5  mov     [rsp+430h+var_3EE], al
0x180003aa9  mov     edi, eax
0x180003aab  lea     eax, [rax+rax*2]
0x180003aae  lea     r12d, ds:70h[rax*8]
0x180003ab6  mov     esi, r12d
0x180003ab9  cmp     r12d, r13d
0x180003abc  jbe     loc_180004414
0x180003ac2  xor     r13b, r13b
0x180003ac5  mov     [rsp+430h+var_3F0], r13b
0x180003aca  mov     edi, [rsp+430h+var_3EC]
0x180003ace  lea     r11, [r15+rsi]
0x180003ad2  xor     r9d, r9d
0x180003ad5  mov     [rsp+430h+var_3D8], r11
0x180003ada  mov     eax, edi
0x180003adc  mov     esi, 0D800h
0x180003ae1  sub     eax, r12d
0x180003ae4  mov     rcx, r11
0x180003ae7  cmp     edi, r12d
0x180003aea  cmovnb  r9d, eax
0x180003aee  movzx   eax, byte ptr [rbx]
0x180003af1  xor     edx, edx
0x180003af3  test    al, al
0x180003af5  jz      short loc_180003B34
0x180003af7  nop     word ptr [rax+rax+00000000h]
0x180003b00  movzx   r8d, al
0x180003b04  inc     rbx
0x180003b07  cmp     r8d, 0BFh
0x180003b0e  ja      loc_1800046C6
0x180003b14  add     edx, 2
0x180003b17  cmp     edx, r9d
0x180003b1a  ja      short loc_180003B24
0x180003b1c  mov     [rcx], r8w
0x180003b20  add     rcx, 2
0x180003b24  movzx   eax, byte ptr [rbx]
0x180003b27  test    al, al
0x180003b29  jnz     short loc_180003B00
0x180003b2b  mov     edi, [rsp+430h+var_3EC]
0x180003b2f  mov     r11, [rsp+430h+var_3D8]
0x180003b34  add     edx, 2
0x180003b37  cmp     edx, r9d
0x180003b3a  ja      short loc_180003B41
0x180003b3c  xor     eax, eax
0x180003b3e  mov     [rcx], ax
0x180003b41  test    r13b, r13b
0x180003b44  jnz     loc_180004192
0x180003b4a  mov     r8, [rsp+430h+var_3C8.lpVtbl]
0x180003b4f  add     r12d, edx
0x180003b52  mov     eax, edx
0x180003b54  mov     r10d, edi
0x180003b57  add     r11, rax
0x180003b5a  sub     r10d, r12d
0x180003b5d  xor     eax, eax
0x180003b5f  mov     [rsp+430h+var_3D8], r11
0x180003b64  cmp     edi, r12d
0x180003b67  mov     rcx, r11
0x180003b6a  cmovb   r10d, eax
0x180003b6e  movzx   eax, byte ptr [r8]
0x180003b72  xor     edx, edx
0x180003b74  test    al, al
0x180003b76  jz      short loc_180003BB5
0x180003b78  nop     dword ptr [rax+rax+00000000h]
0x180003b80  movzx   r9d, al
0x180003b84  inc     r8
0x180003b87  cmp     r9d, 0BFh
0x180003b8e  ja      loc_1800047E3
0x180003b94  add     edx, 2
0x180003b97  cmp     edx, r10d
0x180003b9a  ja      short loc_180003BA4
0x180003b9c  mov     [rcx], r9w
0x180003ba0  add     rcx, 2
0x180003ba4  movzx   eax, byte ptr [r8]
0x180003ba8  test    al, al
0x180003baa  jnz     short loc_180003B80
0x180003bac  mov     edi, [rsp+430h+var_3EC]
0x180003bb0  mov     r11, [rsp+430h+var_3D8]
0x180003bb5  add     edx, 2
0x180003bb8  cmp     edx, r10d
0x180003bbb  ja      short loc_180003BC2
0x180003bbd  xor     eax, eax
0x180003bbf  mov     [rcx], ax
0x180003bc2  test    r13b, r13b
0x180003bc5  jnz     loc_1800041A7
0x180003bcb  mov     eax, edx
0x180003bcd  add     r12d, edx
0x180003bd0  add     r11, rax
0x180003bd3  mov     [rsp+430h+var_3D8], r11
0x180003bd8  test    r13b, r13b
0x180003bdb  jz      short loc_180003BE5
0x180003bdd  mov     eax, [r15+5Ch]
0x180003be1  mov     [r15+44h], eax
0x180003be5  test    byte ptr [rsp+430h+var_3C8.lpVtbl+9], 7Fh
0x180003bea  mov     esi, 0Dh
0x180003bef  mov     rbx, [rbp+330h+var_3A0]
0x180003bf3  jz      loc_1800041E8
0x180003bf9  mov     rax, [rbp+330h+var_3A8]
0x180003bfd  mov     dl, 1
0x180003bff  movzx   r10d, [rsp+430h+var_3EE]
0x180003c05  mov     r14d, 15h
0x180003c0b  mov     [rbp+330h+var_368], rax
0x180003c0f  mov     [rsp+430h+var_3E7], 0
0x180003c14  mov     [rbp+330h+var_388], rbx
0x180003c18  nop     dword ptr [rax+rax+00000000h]
0x180003c20  movzx   eax, dl
0x180003c23  lea     rcx, [rax+rax*2]
0x180003c27  movzx   edx, [rbp+rcx*2+330h+var_33D]
0x180003c2c  lea     rcx, [rdx+rdx*2]
0x180003c30  movzx   eax, [rbp+rcx*2+330h+var_340]
0x180003c35  lea     rcx, [rax+rax*2]
0x180003c39  movzx   eax, [rbp+rcx*2+330h+var_33F]
0x180003c3e  lea     rcx, [rax+rax*2]
0x180003c42  movzx   r8d, [rbp+rcx*2+330h+var_33D]
0x180003c48  movzx   eax, dl
0x180003c4b  lea     rcx, [rax+rax*2]
0x180003c4f  movzx   edx, [rbp+rcx*2+330h+var_33F]
0x180003c54  test    dl, dl
0x180003c56  jnz     short loc_180003C20
0x180003c58  movzx   edx, [rbp+rcx*2+330h+var_33D]
0x180003c5d  cmp     dl, r8b
0x180003c60  jnz     short loc_180003C48
0x180003c62  mov     [rsp+430h+var_3DF], r10b
0x180003c67  mov     [rsp+430h+var_3E0], dl
0x180003c6b  nop     dword ptr [rax+rax+00h]
0x180003c70  mov     edi, [rsp+430h+var_3EC]
0x180003c74  xorps   xmm0, xmm0
0x180003c77  movzx   esi, dl
0x180003c7a  movdqu  xmmword ptr [rsp+430h+var_3C8.lpVtbl+8], xmm0
0x180003c80  mov     [rbp+330h+Src+8], 0
0x180003c88  lea     rax, [rsi+rsi*2]
0x180003c8c  add     rax, rax
0x180003c8f  mov     [rbp+330h+var_398], rax
0x180003c93  movzx   ecx, [rbp+rax+330h+var_33C]
0x180003c98  add     rcx, [rbp+330h+var_368]
0x180003c9c  mov     [rsp+430h+var_3C8.lpVtbl], rcx
0x180003ca1  cmp     byte ptr [rcx], 0
0x180003ca4  jz      loc_180003E3C
0x180003caa  inc     rcx
0x180003cad  cmp     rcx, rbx
0x180003cb0  jnz     short loc_180003CA1
0x180003cb2  movzx   r11d, byte ptr [rsp+430h+var_3C8.lpVtbl+8]
0x180003cb8  mov     [rsp+430h+var_3EF], r11b
0x180003cbd  dec     r10b
0x180003cc0  movzx   eax, r10b
0x180003cc4  mov     [rsp+430h+var_3E8], al
0x180003cc8  movzx   r10d, al
0x180003ccc  mov     [rsp+430h+var_3CC], r10d
0x180003cd1  test    r13b, r13b
0x180003cd4  jz      loc_180003FFA
0x180003cda  lea     r13, [rax+7]
0x180003cde  lea     r13, [rax+r13*2]
0x180003ce2  lea     r13, [r15+r13*8]
0x180003ce6  mov     [rbp+330h+var_360], r13
0x180003cea  cmp     edi, r12d
0x180003ced  jb      loc_180004018
0x180003cf3  sub     edi, r12d
0x180003cf6  mov     rdx, [rsp+430h+var_3C8.lpVtbl]
0x180003cfb  xor     r8d, r8d
0x180003cfe  mov     r14, [rsp+430h+var_3D8]
0x180003d03  mov     r9, r14
0x180003d06  movzx   eax, byte ptr [rdx]
0x180003d09  test    al, al
0x180003d0b  jz      short loc_180003D4E
0x180003d0d  nop     dword ptr [rax]
0x180003d10  movzx   ecx, al
0x180003d13  inc     rdx
0x180003d16  cmp     ecx, 0BFh
0x180003d1c  ja      loc_1800048FE
0x180003d22  add     r8d, 2
0x180003d26  cmp     r8d, edi
0x180003d29  ja      short loc_180003D33
0x180003d2b  mov     [r9], cx
0x180003d2f  add     r9, 2
0x180003d33  movzx   eax, byte ptr [rdx]
0x180003d36  test    al, al
0x180003d38  jnz     short loc_180003D10
0x180003d3a  mov     rbx, [rbp+330h+var_388]
0x180003d3e  movzx   r11d, [rsp+430h+var_3EF]
0x180003d44  mov     r10d, [rsp+430h+var_3CC]
0x180003d49  mov     r14, [rsp+430h+var_3D8]
0x180003d4e  add     r8d, 2
0x180003d52  cmp     r8d, edi
0x180003d55  ja      short loc_180003D5D
0x180003d57  xor     eax, eax
0x180003d59  mov     [r9], ax
0x180003d5d  cmp     [rsp+430h+var_3F0], 0
0x180003d62  mov     r9d, [rsp+430h+var_3EC]
0x180003d67  jnz     loc_180004002
0x180003d6d  add     r12d, r8d
0x180003d70  mov     eax, r8d
0x180003d73  add     r14, rax
0x180003d76  mov     [rsp+430h+var_3D0], r12d
0x180003d7b  mov     [rsp+430h+var_3E4], r12d
0x180003d80  mov     [rsp+430h+var_3D8], r14
0x180003d85  mov     [rbp+330h+var_378], r14
0x180003d89  test    r13, r13
0x180003d8c  jnz     loc_18000402B
0x180003d92  movzx   r15d, r11b
0x180003d96  and     r15b, 60h
0x180003d9a  cmp     r15b, 20h ; ' '
0x180003d9e  jz      loc_1800045A8
0x180003da4  movzx   ecx, r11b
0x180003da8  and     ecx, 1Fh
0x180003dab  cmp     ecx, 18h
0x180003dae  jz      loc_180004045
0x180003db4  cmp     r15b, 60h ; '`'
0x180003db8  jz      loc_180004A2B
0x180003dbe  xor     r12b, r12b
0x180003dc1  mov     r14d, ecx
0x180003dc4  test    ecx, ecx
0x180003dc6  jz      loc_18000414E
0x180003dcc  sub     ecx, 0Eh
0x180003dcf  jz      loc_1800045CC
0x180003dd5  sub     ecx, 8
  ... truncated ...
```
