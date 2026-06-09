# CPropertyStore::_ConvertToPKEY(_tagpropertykey const &,tagPROPVARIANT const *,_tagpropertykey *,tagPROPVARIANT *)

- ea: `0x18001b0b0`
- end: `0x18001ba3b`
- name: `?_ConvertToPKEY@CPropertyStore@@AEAAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@PEAU2@PEAU3@@Z`
- size: `2443`
- prototype: `int(CPropertyStore *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a630`

## callees

- `0x18001b0b0`
- `0x18001ba50`
- `0x18002ff5c`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantCopy` at `0x18001b37a`
- `ole32!PropVariantCopy` at `0x18001b739`
- `ole32!PropVariantCopy` at `0x18001b877`
- `ole32!PropVariantCopy` at `0x18001b8bf`
- `ole32!PropVariantCopy` at `0x18001b8f9`
- `ole32!PropVariantCopy` at `0x18001b933`
- `ole32!PropVariantCopy` at `0x18001b37a`
- `ole32!PropVariantCopy` at `0x18001b739`
- `ole32!PropVariantCopy` at `0x18001b877`
- `ole32!PropVariantCopy` at `0x18001b8bf`
- `ole32!PropVariantCopy` at `0x18001b8f9`
- `ole32!PropVariantCopy` at `0x18001b933`

## pseudocode

```c
__int64 __fastcall CPropertyStore::_ConvertToPKEY(
        CPropertyStore *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3,
        struct _tagpropertykey *a4,
        struct tagPROPVARIANT *pvarDest)
{
  __int64 v5; // rax
  HRESULT v9; // esi
  unsigned __int64 v10; // rdx
  __int64 (__fastcall *v11)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *); // rax
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  PVOID *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  DWORD pid; // eax
  __int64 v26; // rax
  DWORD *p_pid; // r12
  __int64 i; // rcx
  unsigned __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 (__fastcall *v31)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *); // rax
  HRESULT v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 j; // rcx
  unsigned __int64 v37; // rdx
  __int64 v38; // rax
  struct _tagpropertykey *v39; // r15
  __int64 k; // rcx
  unsigned __int64 v41; // rdx
  __int64 m; // rcx
  unsigned __int64 v43; // rdx
  unsigned __int64 vt; // rcx
  unsigned __int64 v45; // rdx
  struct _tagpropertykey *v46; // r15
  __int64 v47; // rax
  __int64 (__fastcall *v48)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *); // rax
  HRESULT v49; // eax
  bool v50; // zf
  __int64 v51; // rax
  __int64 (__fastcall *v52)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *); // rax
  HRESULT v53; // eax
  bool v54; // zf
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 (__fastcall *v58)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *); // rax
  __int64 v59; // rax
  __int64 (__fastcall *v60)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *); // rax
  HRESULT v61; // eax
  bool v62; // zf
  _QWORD *v63; // rcx
  __int64 v64; // rdx
  HRESULT v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rcx
  struct _tagpropertykey *v68; // [rsp+A8h] [rbp+20h]

  v68 = a4;
  v5 = 0;
  *(_OWORD *)&pvarDest->vt = 0;
  pvarDest->bstrblobVal.pData = 0;
  if ( !a3->vt || a3->vt == 10 )
  {
    v9 = -2147418113;
LABEL_25:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v9 = 1;
  while ( 1 )
  {
    if ( (unsigned int)v5 >= 5 )
      goto LABEL_10;
    v10 = 48 * v5;
    if ( a2->pid == *(_DWORD *)&byte_1800921A0[48 * v5] )
    {
      v20 = *(_QWORD *)&a2->fmtid.Data1 - qword_180092190[v10 / 8];
      if ( *(_QWORD *)&a2->fmtid.Data1 == qword_180092190[v10 / 8] )
        v20 = *(_QWORD *)a2->fmtid.Data4 - qword_180092190[v10 / 8 + 1];
      if ( !v20 )
        break;
    }
    v5 = (unsigned int)(v5 + 1);
  }
  *a4 = *(struct _tagpropertykey *)&dword_1800921A4[v10 / 4];
  v11 = (__int64 (__fastcall *)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *))qword_1800921A8[v10 / 8 + 2];
  if ( !v11 )
  {
    v9 = PropVariantCopy(pvarDest, a3);
    if ( v9 >= 0 )
      goto LABEL_9;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v30 = 48;
LABEL_58:
      WPP_SF_d(v19[2], v30, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v9);
      goto LABEL_25;
    }
LABEL_26:
    v12 = v9;
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
    {
      v17 = 49;
      v18 = (unsigned int)v9;
LABEL_23:
      WPP_SF_d(v19[2], v17, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v18);
    }
    return v12;
  }
  v9 = v11(&dword_1800921A4[v10 / 4], a3, pvarDest);
  if ( v9 < 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v30 = 47;
      goto LABEL_58;
    }
    goto LABEL_26;
  }
LABEL_9:
  a4 = v68;
LABEL_10:
  v12 = v9;
  v13 = *(_QWORD *)&WPD_CONTENT_TYPE_VIDEO.Data1 - *((_QWORD *)this + 6);
  if ( *(_QWORD *)&WPD_CONTENT_TYPE_VIDEO.Data1 == *((_QWORD *)this + 6) )
    v13 = *(_QWORD *)WPD_CONTENT_TYPE_VIDEO.Data4 - *((_QWORD *)this + 7);
  if ( v13 )
  {
    v14 = *(_QWORD *)&WPD_CONTENT_TYPE_IMAGE.Data1 - *((_QWORD *)this + 6);
    if ( *(_QWORD *)&WPD_CONTENT_TYPE_IMAGE.Data1 == *((_QWORD *)this + 6) )
      v14 = *(_QWORD *)WPD_CONTENT_TYPE_IMAGE.Data4 - *((_QWORD *)this + 7);
    if ( v14 )
    {
      v15 = *(_QWORD *)&WPD_CONTENT_TYPE_AUDIO.Data1 - *((_QWORD *)this + 6);
      if ( *(_QWORD *)&WPD_CONTENT_TYPE_AUDIO.Data1 == *((_QWORD *)this + 6) )
        v15 = *(_QWORD *)WPD_CONTENT_TYPE_AUDIO.Data4 - *((_QWORD *)this + 7);
      if ( v15 )
        return v12;
    }
  }
  v21 = *(_QWORD *)&WPD_MEDIA_PROPERTIES_V1.Data1 - *(_QWORD *)&a2->fmtid.Data1;
  if ( *(_QWORD *)&WPD_MEDIA_PROPERTIES_V1.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
    v21 = *(_QWORD *)WPD_MEDIA_PROPERTIES_V1.Data4 - *(_QWORD *)a2->fmtid.Data4;
  if ( v21 )
  {
    v22 = *(_QWORD *)&WPD_MUSIC_OBJECT_PROPERTIES_V1.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&WPD_MUSIC_OBJECT_PROPERTIES_V1.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      v22 = *(_QWORD *)WPD_MUSIC_OBJECT_PROPERTIES_V1.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( v22 )
    {
      v23 = *(_QWORD *)&WPD_VIDEO_OBJECT_PROPERTIES_V1.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&WPD_VIDEO_OBJECT_PROPERTIES_V1.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        v23 = *(_QWORD *)WPD_VIDEO_OBJECT_PROPERTIES_V1.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( v23 )
      {
        v24 = *(_QWORD *)&WPD_IMAGE_OBJECT_PROPERTIES_V1.Data1 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)&WPD_IMAGE_OBJECT_PROPERTIES_V1.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
          v24 = *(_QWORD *)WPD_IMAGE_OBJECT_PROPERTIES_V1.Data4 - *(_QWORD *)a2->fmtid.Data4;
        if ( v24 )
        {
          pid = a2->pid;
          if ( pid != 20 )
            goto LABEL_44;
          v67 = *(_QWORD *)&WPD_OBJECT_DATE_AUTHORED.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
          if ( *(_QWORD *)&WPD_OBJECT_DATE_AUTHORED.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
            v67 = *(_QWORD *)WPD_OBJECT_DATE_AUTHORED.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
          if ( v67 )
          {
LABEL_44:
            if ( pid != 18 )
              return v12;
            v26 = *(_QWORD *)&WPD_OBJECT_DATE_CREATED.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
            if ( *(_QWORD *)&WPD_OBJECT_DATE_CREATED.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
              v26 = *(_QWORD *)WPD_OBJECT_DATE_CREATED.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
            if ( v26 )
              return v12;
          }
        }
      }
    }
  }
  *(_OWORD *)&pvarDest->vt = 0;
  pvarDest->bstrblobVal.pData = 0;
  if ( !a3->vt || a3->vt == 10 )
  {
    p_pid = &a2->pid;
    v12 = -2147418113;
    goto LABEL_62;
  }
  v12 = 1;
  p_pid = &a2->pid;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0xF )
      goto LABEL_61;
    v29 = 48 * i;
    if ( *p_pid == *(_DWORD *)&byte_180092290[48 * i] )
    {
      v38 = *(_QWORD *)&a2->fmtid.Data1 - qword_180092280[v29 / 8];
      if ( *(_QWORD *)&a2->fmtid.Data1 == qword_180092280[v29 / 8] )
        v38 = *(_QWORD *)a2->fmtid.Data4 - qword_180092280[v29 / 8 + 1];
      if ( !v38 )
        break;
    }
  }
  *a4 = *(struct _tagpropertykey *)&dword_180092294[v29 / 4];
  v31 = (__int64 (__fastcall *)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *))qword_180092298[v29 / 8 + 2];
  if ( v31 )
  {
    v32 = v31(&dword_180092294[v29 / 4], a3, pvarDest);
    v12 = v32;
    if ( v32 >= 0 )
      goto LABEL_61;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_62;
    v56 = 47;
LABEL_124:
    WPP_SF_d(v55[2], v56, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v32);
    goto LABEL_62;
  }
  v32 = PropVariantCopy(pvarDest, a3);
  v12 = v32;
  if ( v32 < 0 )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_62;
    v56 = 48;
    goto LABEL_124;
  }
LABEL_61:
  if ( !v12 )
    return v12;
LABEL_62:
  v33 = *(_QWORD *)&WPD_CONTENT_TYPE_AUDIO.Data1 - *((_QWORD *)this + 6);
  if ( *(_QWORD *)&WPD_CONTENT_TYPE_AUDIO.Data1 == *((_QWORD *)this + 6) )
    v33 = *(_QWORD *)WPD_CONTENT_TYPE_AUDIO.Data4 - *((_QWORD *)this + 7);
  if ( !v33 )
  {
    *(_OWORD *)&pvarDest->vt = 0;
    pvarDest->bstrblobVal.pData = 0;
    vt = a3->vt;
    if ( !(_WORD)vt || (_WORD)vt == 10 )
    {
LABEL_102:
      v46 = v68;
    }
    else
    {
      for ( vt = 0; ; vt = (unsigned int)(vt + 1) )
      {
        if ( (unsigned int)vt >= 5 )
          goto LABEL_102;
        v45 = 12 * vt;
        if ( *p_pid == *(_DWORD *)&byte_180092560[48 * vt] )
        {
          v59 = *(_QWORD *)&a2->fmtid.Data1 - qword_180092550[v45 / 2];
          if ( *(_QWORD *)&a2->fmtid.Data1 == qword_180092550[v45 / 2] )
            v59 = *(_QWORD *)a2->fmtid.Data4 - qword_180092550[v45 / 2 + 1];
          if ( !v59 )
            break;
        }
      }
      v46 = v68;
      v68->fmtid = *(GUID *)&dword_180092564[v45];
      v68->pid = dword_180092564[v45 + 4];
      v60 = *(__int64 (__fastcall **)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *))((char *)&off_180092578 + v45 * 4);
      if ( v60 )
      {
        v61 = v60(&dword_180092564[v45], a3, pvarDest);
        v62 = v61 == 0;
        if ( v61 >= 0 )
        {
LABEL_137:
          if ( !v62 )
            return (unsigned int)CPropertyStore::_WpdKeyToPKEY(
                                   (CPropertyStore *)vt,
                                   a2,
                                   a3,
                                   v46,
                                   pvarDest,
                                   (const struct METADATA_MAPPING *)qword_180092640,
                                   7u);
          return 0;
        }
        vt = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v66 = 47;
          goto LABEL_157;
        }
      }
      else
      {
        v61 = PropVariantCopy(pvarDest, a3);
        v62 = v61 == 0;
        if ( v61 >= 0 )
          goto LABEL_137;
        vt = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v66 = 48;
LABEL_157:
          WPP_SF_d(*(_QWORD *)(vt + 16), v66, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v61);
        }
      }
    }
    return (unsigned int)CPropertyStore::_WpdKeyToPKEY(
                           (CPropertyStore *)vt,
                           a2,
                           a3,
                           v46,
                           pvarDest,
                           (const struct METADATA_MAPPING *)qword_180092640,
                           7u);
  }
  v34 = *(_QWORD *)&WPD_CONTENT_TYPE_IMAGE.Data1 - *((_QWORD *)this + 6);
  if ( *(_QWORD *)&WPD_CONTENT_TYPE_IMAGE.Data1 == *((_QWORD *)this + 6) )
    v34 = *(_QWORD *)WPD_CONTENT_TYPE_IMAGE.Data4 - *((_QWORD *)this + 7);
  if ( v34 )
  {
    v35 = *(_QWORD *)&WPD_CONTENT_TYPE_VIDEO.Data1 - *((_QWORD *)this + 6);
    if ( *(_QWORD *)&WPD_CONTENT_TYPE_VIDEO.Data1 == *((_QWORD *)this + 6) )
      v35 = *(_QWORD *)WPD_CONTENT_TYPE_VIDEO.Data4 - *((_QWORD *)this + 7);
    if ( v35 )
      return v12;
    *(_OWORD *)&pvarDest->vt = 0;
    pvarDest->bstrblobVal.pData = 0;
    if ( !a3->vt || a3->vt == 10 )
    {
LABEL_82:
      v39 = v68;
    }
    else
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= 5 )
          goto LABEL_82;
        v37 = 12 * j;
        if ( *p_pid == *(_DWORD *)&byte_180092560[48 * j] )
        {
          v47 = *(_QWORD *)&a2->fmtid.Data1 - qword_180092550[v37 / 2];
          if ( *(_QWORD *)&a2->fmtid.Data1 == qword_180092550[v37 / 2] )
            v47 = *(_QWORD *)a2->fmtid.Data4 - qword_180092550[v37 / 2 + 1];
          if ( !v47 )
            break;
        }
      }
      v39 = v68;
      v68->fmtid = *(GUID *)&dword_180092564[v37];
      v68->pid = dword_180092564[v37 + 4];
      v48 = *(__int64 (__fastcall **)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *))((char *)&off_180092578 + v37 * 4);
      if ( v48 )
      {
        v49 = v48(&dword_180092564[v37], a3, pvarDest);
        v50 = v49 == 0;
        if ( v49 >= 0 )
        {
LABEL_109:
          if ( !v50 )
            goto LABEL_83;
          return 0;
        }
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v64 = 47;
          goto LABEL_143;
        }
      }
      else
      {
        v49 = PropVariantCopy(pvarDest, a3);
        v50 = v49 == 0;
        if ( v49 >= 0 )
          goto LABEL_109;
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v64 = 48;
LABEL_143:
          WPP_SF_d(v63[2], v64, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v49);
        }
      }
    }
LABEL_83:
    *(_OWORD *)&pvarDest->vt = 0;
    pvarDest->bstrblobVal.pData = 0;
    if ( a3->vt && a3->vt != 10 )
    {
      v12 = 1;
      for ( k = 0; (unsigned int)k < 0xD; k = (unsigned int)(k + 1) )
      {
        v41 = 12 * k;
        if ( *p_pid == *(_DWORD *)&byte_180092A70[48 * k] )
        {
          v51 = *(_QWORD *)&a2->fmtid.Data1 - qword_180092A60[v41 / 2];
          if ( *(_QWORD *)&a2->fmtid.Data1 == qword_180092A60[v41 / 2] )
            v51 = *(_QWORD *)a2->fmtid.Data4 - qword_180092A60[v41 / 2 + 1];
          if ( !v51 )
          {
            v39->fmtid = *(GUID *)&dword_180092A74[v41];
            v39->pid = dword_180092A74[v41 + 4];
            v52 = *(__int64 (__fastcall **)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *))((char *)&off_180092A88 + v41 * 4);
            if ( v52 )
            {
              v53 = v52(&dword_180092A74[v41], a3, pvarDest);
              v12 = v53;
              if ( v53 >= 0 )
                return v12;
              v19 = (PVOID *)WPP_GLOBAL_Control;
              v54 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
              goto LABEL_117;
            }
            v53 = PropVariantCopy(pvarDest, a3);
            v12 = v53;
            if ( v53 < 0 )
            {
              v19 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v17 = 48;
                goto LABEL_148;
              }
            }
            return v12;
          }
        }
      }
      return v12;
    }
    return (unsigned int)-2147418113;
  }
  *(_OWORD *)&pvarDest->vt = 0;
  pvarDest->bstrblobVal.pData = 0;
  if ( !a3->vt || a3->vt == 10 )
    return (unsigned int)-2147418113;
  v12 = 1;
  for ( m = 0; (unsigned int)m < 0xF; m = (unsigned int)(m + 1) )
  {
    v43 = 48 * m;
    if ( *p_pid == *(_DWORD *)&byte_1800927A0[48 * m] )
    {
      v57 = *(_QWORD *)&a2->fmtid.Data1 - qword_180092790[v43 / 8];
      if ( *(_QWORD *)&a2->fmtid.Data1 == qword_180092790[v43 / 8] )
        v57 = *(_QWORD *)a2->fmtid.Data4 - qword_180092790[v43 / 8 + 1];
      if ( !v57 )
      {
        v68->fmtid = *(GUID *)&dword_1800927A4[v43 / 4];
        v68->pid = dword_1800927A4[v43 / 4 + 4];
        v58 = (__int64 (__fastcall *)(int *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *))qword_1800927A8[v43 / 8 + 2];
        if ( v58 )
        {
          v53 = v58(&dword_1800927A4[v43 / 4], a3, pvarDest);
          v12 = v53;
          if ( v53 < 0 )
          {
            v19 = (PVOID *)WPP_GLOBAL_Control;
            v54 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
LABEL_117:
            if ( !v54 && (*((_BYTE *)v19 + 28) & 2) != 0 )
            {
              v17 = 47;
LABEL_148:
              v18 = (unsigned int)v53;
              goto LABEL_23;
            }
          }
        }
        else
        {
          v65 = PropVariantCopy(pvarDest, a3);
          v12 = v65;
          if ( v65 < 0 )
          {
            v19 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v17 = 48;
              v18 = (unsigned int)v65;
              goto LABEL_23;
            }
          }
        }
        return v12;
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18001b0b0  mov     [rsp+arg_18], r9
0x18001b0b5  push    rbx
0x18001b0b6  push    rbp
0x18001b0b7  push    rsi
0x18001b0b8  push    rdi
0x18001b0b9  push    r12
0x18001b0bb  push    r13
0x18001b0bd  push    r14
0x18001b0bf  push    r15
0x18001b0c1  sub     rsp, 48h
0x18001b0c5  mov     rbp, [rsp+88h+pvarDest]
0x18001b0cd  xor     eax, eax
0x18001b0cf  xorps   xmm0, xmm0
0x18001b0d2  mov     rbx, rdx
0x18001b0d5  mov     r13, r8
0x18001b0d8  mov     r15, rcx
0x18001b0db  movups  xmmword ptr [rbp+0], xmm0
0x18001b0df  mov     [rbp+10h], rax
0x18001b0e3  movzx   edx, word ptr [r8]
0x18001b0e7  cmp     ax, dx
0x18001b0ea  jz      loc_18001B234
0x18001b0f0  mov     r10d, 0Ah
0x18001b0f6  cmp     r10w, dx
0x18001b0fa  jz      loc_18001B234
0x18001b100  mov     esi, 1
0x18001b105  lea     r8, __ImageBase
0x18001b10c  nop     dword ptr [rax+00h]
0x18001b110  cmp     eax, 5
0x18001b113  jnb     short loc_18001B185
0x18001b115  lea     rdx, [rax+rax*2]
0x18001b119  shl     rdx, 4
0x18001b11d  mov     ecx, [rdx+r8+921A0h]
0x18001b125  cmp     [rbx+10h], ecx
0x18001b128  jz      loc_18001B24B
0x18001b12e  inc     eax
0x18001b130  jmp     short loc_18001B110
0x18001b132  lea     rcx, rva dword_1800921A4[r8]
0x18001b139  add     rcx, rdx
0x18001b13c  movups  xmm0, xmmword ptr [rcx]
0x18001b13f  movups  xmmword ptr [r9], xmm0
0x18001b143  mov     eax, [rcx+10h]
0x18001b146  mov     [r9+10h], eax
0x18001b14a  mov     rax, [rdx+r8+921B8h]
0x18001b152  mov     rdx, r13; pvarSrc
0x18001b155  test    rax, rax
0x18001b158  jz      loc_18001B377
0x18001b15e  mov     r8, rbp
0x18001b161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b166  mov     esi, eax
0x18001b168  test    eax, eax
0x18001b16a  js      loc_18001B99D
0x18001b170  mov     r9, [rsp+88h+arg_18]
0x18001b178  lea     r8, __ImageBase
0x18001b17f  mov     r10d, 0Ah
0x18001b185  mov     edi, esi
0x18001b187  test    esi, esi
0x18001b189  js      short loc_18001B201
0x18001b18b  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_VIDEO.Data1
0x18001b192  sub     rax, [r15+30h]
0x18001b196  jnz     short loc_18001B1A3
0x18001b198  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_VIDEO.Data4
0x18001b19f  sub     rax, [r15+38h]
0x18001b1a3  test    rax, rax
0x18001b1a6  jz      loc_18001B272
0x18001b1ac  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_IMAGE.Data1
0x18001b1b3  sub     rax, [r15+30h]
0x18001b1b7  jnz     short loc_18001B1C4
0x18001b1b9  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_IMAGE.Data4
0x18001b1c0  sub     rax, [r15+38h]
0x18001b1c4  test    rax, rax
0x18001b1c7  jz      loc_18001B272
0x18001b1cd  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_AUDIO.Data1
0x18001b1d4  sub     rax, [r15+30h]
0x18001b1d8  jnz     short loc_18001B1E5
0x18001b1da  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_AUDIO.Data4
0x18001b1e1  sub     rax, [r15+38h]
0x18001b1e5  test    rax, rax
0x18001b1e8  jz      loc_18001B272
0x18001b1ee  mov     eax, edi
0x18001b1f0  add     rsp, 48h
0x18001b1f4  pop     r15
0x18001b1f6  pop     r14
0x18001b1f8  pop     r13
0x18001b1fa  pop     r12
0x18001b1fc  pop     rdi
0x18001b1fd  pop     rsi
0x18001b1fe  pop     rbp
0x18001b1ff  pop     rbx
0x18001b200  retn
0x18001b201  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b208  lea     r14, WPP_GLOBAL_Control
0x18001b20f  cmp     rcx, r14
0x18001b212  jz      short loc_18001B1EE
0x18001b214  test    byte ptr [rcx+1Ch], 2
0x18001b218  jz      short loc_18001B1EE
0x18001b21a  mov     edx, 31h ; '1'
0x18001b21f  mov     r9d, esi
0x18001b222  mov     rcx, [rcx+10h]
0x18001b226  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001b22d  call    WPP_SF_d
0x18001b232  jmp     short loc_18001B1EE
0x18001b234  mov     esi, 8000FFFFh
0x18001b239  lea     r14, WPP_GLOBAL_Control
0x18001b240  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b247  mov     edi, esi
0x18001b249  jmp     short loc_18001B20F
0x18001b24b  mov     rcx, [rbx]
0x18001b24e  sub     rcx, [rdx+r8+92190h]
0x18001b256  jnz     short loc_18001B264
0x18001b258  mov     rcx, [rbx+8]
0x18001b25c  sub     rcx, [rdx+r8+92198h]
0x18001b264  test    rcx, rcx
0x18001b267  jnz     loc_18001B12E
0x18001b26d  jmp     loc_18001B132
0x18001b272  mov     rax, qword ptr cs:WPD_MEDIA_PROPERTIES_V1.Data1
0x18001b279  sub     rax, [rbx]
0x18001b27c  jnz     short loc_18001B289
0x18001b27e  mov     rax, qword ptr cs:WPD_MEDIA_PROPERTIES_V1.Data4
0x18001b285  sub     rax, [rbx+8]
0x18001b289  test    rax, rax
0x18001b28c  jz      loc_18001B31B
0x18001b292  mov     rax, qword ptr cs:WPD_MUSIC_OBJECT_PROPERTIES_V1.Data1
0x18001b299  sub     rax, [rbx]
0x18001b29c  jnz     short loc_18001B2A9
0x18001b29e  mov     rax, qword ptr cs:WPD_MUSIC_OBJECT_PROPERTIES_V1.Data4
0x18001b2a5  sub     rax, [rbx+8]
0x18001b2a9  test    rax, rax
0x18001b2ac  jz      short loc_18001B31B
0x18001b2ae  mov     rax, qword ptr cs:WPD_VIDEO_OBJECT_PROPERTIES_V1.Data1
0x18001b2b5  sub     rax, [rbx]
0x18001b2b8  jnz     short loc_18001B2C5
0x18001b2ba  mov     rax, qword ptr cs:WPD_VIDEO_OBJECT_PROPERTIES_V1.Data4
0x18001b2c1  sub     rax, [rbx+8]
0x18001b2c5  test    rax, rax
0x18001b2c8  jz      short loc_18001B31B
0x18001b2ca  mov     rax, qword ptr cs:WPD_IMAGE_OBJECT_PROPERTIES_V1.Data1
0x18001b2d1  sub     rax, [rbx]
0x18001b2d4  jnz     short loc_18001B2E1
0x18001b2d6  mov     rax, qword ptr cs:WPD_IMAGE_OBJECT_PROPERTIES_V1.Data4
0x18001b2dd  sub     rax, [rbx+8]
0x18001b2e1  test    rax, rax
0x18001b2e4  jz      short loc_18001B31B
0x18001b2e6  mov     eax, [rbx+10h]
0x18001b2e9  cmp     eax, 14h
0x18001b2ec  jz      loc_18001B978
0x18001b2f2  cmp     eax, 12h
0x18001b2f5  jnz     loc_18001B1EE
0x18001b2fb  mov     rax, qword ptr cs:WPD_OBJECT_DATE_CREATED.fmtid.Data1
0x18001b302  sub     rax, [rbx]
0x18001b305  jnz     short loc_18001B312
0x18001b307  mov     rax, qword ptr cs:WPD_OBJECT_DATE_CREATED.fmtid.Data4
0x18001b30e  sub     rax, [rbx+8]
0x18001b312  test    rax, rax
0x18001b315  jnz     loc_18001B1EE
0x18001b31b  xor     eax, eax
0x18001b31d  xorps   xmm0, xmm0
0x18001b320  movups  xmmword ptr [rbp+0], xmm0
0x18001b324  mov     [rbp+10h], rax
0x18001b328  movzx   ecx, word ptr [r13+0]
0x18001b32d  cmp     ax, cx
0x18001b330  jz      loc_18001B4CA
0x18001b336  cmp     r10w, cx
0x18001b33a  jz      loc_18001B4CA
0x18001b340  mov     edi, 1
0x18001b345  lea     r12, [rbx+10h]
0x18001b349  xor     ecx, ecx
0x18001b34b  nop     dword ptr [rax+rax+00h]
0x18001b350  cmp     ecx, 0Fh
0x18001b353  jnb     loc_18001B40C
0x18001b359  lea     rdx, [rcx+rcx*2]
0x18001b35d  shl     rdx, 4
0x18001b361  mov     eax, [rdx+r8+92290h]
0x18001b369  cmp     [r12], eax
0x18001b36d  jz      loc_18001B4DA
0x18001b373  inc     ecx
0x18001b375  jmp     short loc_18001B350
0x18001b377  mov     rcx, rbp; pvarDest
0x18001b37a  call    cs:__imp_PropVariantCopy
0x18001b380  mov     esi, eax
0x18001b382  test    eax, eax
0x18001b384  jns     loc_18001B170
0x18001b38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b391  lea     r14, WPP_GLOBAL_Control
0x18001b398  cmp     rcx, r14
0x18001b39b  jz      loc_18001B247
0x18001b3a1  test    byte ptr [rcx+1Ch], 2
0x18001b3a5  jz      loc_18001B247
0x18001b3ab  mov     edx, 30h ; '0'
0x18001b3b0  mov     rcx, [rcx+10h]
0x18001b3b4  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001b3bb  mov     r9d, esi
0x18001b3be  call    WPP_SF_d
0x18001b3c3  jmp     loc_18001B240
0x18001b3c8  lea     rcx, rva dword_180092294[r8]
0x18001b3cf  add     rcx, rdx
0x18001b3d2  movups  xmm0, xmmword ptr [rcx]
0x18001b3d5  movups  xmmword ptr [r9], xmm0
0x18001b3d9  mov     eax, [rcx+10h]
0x18001b3dc  mov     [r9+10h], eax
0x18001b3e0  mov     rax, [rdx+r8+922A8h]
0x18001b3e8  mov     rdx, r13; pvarSrc
0x18001b3eb  test    rax, rax
0x18001b3ee  jz      loc_18001B736
0x18001b3f4  mov     r8, rbp
0x18001b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3fc  mov     edi, eax
0x18001b3fe  test    eax, eax
0x18001b400  js      loc_18001B9C8
0x18001b406  mov     r10d, 0Ah
0x18001b40c  test    edi, edi
0x18001b40e  jz      loc_18001B1EE
0x18001b414  mov     esi, 8000FFFFh
0x18001b419  lea     r14, WPP_GLOBAL_Control
0x18001b420  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_AUDIO.Data1
0x18001b427  sub     rax, [r15+30h]
0x18001b42b  jnz     short loc_18001B438
0x18001b42d  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_AUDIO.Data4
0x18001b434  sub     rax, [r15+38h]
0x18001b438  test    rax, rax
0x18001b43b  jz      loc_18001B5C0
0x18001b441  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_IMAGE.Data1
0x18001b448  sub     rax, [r15+30h]
0x18001b44c  jnz     short loc_18001B459
0x18001b44e  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_IMAGE.Data4
0x18001b455  sub     rax, [r15+38h]
0x18001b459  test    rax, rax
0x18001b45c  jz      loc_18001B567
0x18001b462  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_VIDEO.Data1
0x18001b469  sub     rax, [r15+30h]
0x18001b46d  jnz     short loc_18001B47A
0x18001b46f  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_VIDEO.Data4
0x18001b476  sub     rax, [r15+38h]
0x18001b47a  test    rax, rax
0x18001b47d  jnz     loc_18001B1EE
0x18001b483  xorps   xmm0, xmm0
0x18001b486  movups  xmmword ptr [rbp+0], xmm0
0x18001b48a  mov     [rbp+10h], rax
0x18001b48e  movzx   ecx, word ptr [r13+0]
0x18001b493  cmp     ax, cx
0x18001b496  jz      short loc_18001B501
0x18001b498  cmp     r10w, cx
0x18001b49c  jz      short loc_18001B501
0x18001b49e  xor     ecx, ecx
0x18001b4a0  lea     r8, __ImageBase
0x18001b4a7  cmp     ecx, 5
0x18001b4aa  jnb     short loc_18001B501
0x18001b4ac  lea     rdx, [rcx+rcx*2]
0x18001b4b0  shl     rdx, 4
0x18001b4b4  mov     eax, [rdx+r8+92560h]
0x18001b4bc  cmp     [r12], eax
0x18001b4c0  jz      loc_18001B63F
0x18001b4c6  inc     ecx
0x18001b4c8  jmp     short loc_18001B4A7
0x18001b4ca  mov     esi, 8000FFFFh
0x18001b4cf  lea     r12, [rbx+10h]
0x18001b4d3  mov     edi, esi
0x18001b4d5  jmp     loc_18001B419
0x18001b4da  mov     rax, [rbx]
0x18001b4dd  sub     rax, [rdx+r8+92280h]
0x18001b4e5  jnz     short loc_18001B4F3
0x18001b4e7  mov     rax, [rbx+8]
0x18001b4eb  sub     rax, [rdx+r8+92288h]
0x18001b4f3  test    rax, rax
0x18001b4f6  jnz     loc_18001B373
0x18001b4fc  jmp     loc_18001B3C8
0x18001b501  mov     r15, [rsp+88h+arg_18]
0x18001b509  xor     eax, eax
0x18001b50b  xorps   xmm0, xmm0
0x18001b50e  movups  xmmword ptr [rbp+0], xmm0
0x18001b512  mov     [rbp+10h], rax
0x18001b516  movzx   ecx, word ptr [r13+0]
0x18001b51b  cmp     ax, cx
0x18001b51e  jz      loc_18001B5B9
0x18001b524  mov     eax, 0Ah
0x18001b529  cmp     ax, cx
0x18001b52c  jz      loc_18001B5B9
0x18001b532  mov     edi, 1
0x18001b537  lea     r8, __ImageBase
0x18001b53e  xor     ecx, ecx
0x18001b540  cmp     ecx, 0Dh
0x18001b543  jnb     loc_18001B1EE
0x18001b549  lea     rdx, [rcx+rcx*2]
0x18001b54d  shl     rdx, 4
0x18001b551  mov     eax, [rdx+r8+92A70h]
0x18001b559  cmp     [r12], eax
0x18001b55d  jz      loc_18001B6B2
0x18001b563  inc     ecx
0x18001b565  jmp     short loc_18001B540
0x18001b567  xor     eax, eax
0x18001b569  xorps   xmm0, xmm0
0x18001b56c  movups  xmmword ptr [rbp+0], xmm0
0x18001b570  mov     [rbp+10h], rax
0x18001b574  movzx   ecx, word ptr [r13+0]
0x18001b579  cmp     ax, cx
0x18001b57c  jz      short loc_18001B5B9
0x18001b57e  cmp     r10w, cx
0x18001b582  jz      short loc_18001B5B9
0x18001b584  mov     edi, 1
0x18001b589  lea     r8, __ImageBase
0x18001b590  xor     ecx, ecx
  ... truncated ...
```
