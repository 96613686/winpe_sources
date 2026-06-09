# ActivationProperties::SetupForUnserializing(Serializer *)

- ea: `0x180020730`
- end: `0x1800210f1`
- name: `?SetupForUnserializing@ActivationProperties@@QEAAJPEAVSerializer@@@Z`
- size: `2497`
- prototype: `__int64 __fastcall(ActivationProperties *__hidden this, struct Serializer *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021120`

## callees

- `0x180020730`
- `0x1800210f8`
- `0x180058b70`
- `0x180114010`

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180020eb1`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180020f3d`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180020fe1`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180020eb1`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180020f3d`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x180020fe1`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180020899`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180020ce3`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180020d7a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180020899`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180020ce3`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180020d7a`
- `RPCRT4!NdrMesTypeDecode2` at `0x180020778`
- `RPCRT4!NdrMesTypeDecode2` at `0x180020778`
- `RPCRT4!MesHandleFree` at `0x180020868`
- `RPCRT4!MesHandleFree` at `0x180020d47`
- `RPCRT4!MesHandleFree` at `0x180020868`
- `RPCRT4!MesHandleFree` at `0x180020d47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020c08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020c08`

## string_xrefs

- `0x1800207d2`: `onecore\com\combase\actprops\actprops.cxx`
- `0x1800207ff`: `onecore\com\combase\actprops\actprops.cxx`
- `0x180020b94`: `onecore\com\combase\actprops\actprops.cxx`
- `0x180020e7e`: `onecore\com\combase\actprops\actprops.cxx`
- `0x180020ef4`: `onecore\com\combase\actprops\actprops.cxx`
- `0x180020f7b`: `onecore\com\combase\actprops\actprops.cxx`
- `0x180020fa0`: `onecore\com\combase\actprops\actprops.cxx`
- `0x180021061`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002107f`: `onecore\com\combase\actprops\actprops.cxx`
- `0x1800210d1`: `onecore\com\combase\actprops\actprops.cxx`

## pseudocode

```c
__int64 __fastcall ActivationProperties::SetupForUnserializing(ActivationProperties *this, struct Serializer *a2)
{
  void *v3; // rcx
  unsigned int v6; // edi
  unsigned int *v7; // r15
  unsigned int v8; // ebx
  unsigned int v9; // edx
  RPC_STATUS v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // ecx
  unsigned int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // r11d
  unsigned int i; // r9d
  __int64 v17; // rcx
  __int64 v18; // r10
  _QWORD *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  signed int v39; // ebx
  _QWORD *v40; // rax
  _QWORD *v41; // rdi
  int v42; // ecx
  int v43; // r8d
  int v44; // edx
  __int64 v45; // rcx
  int v46; // ebp
  unsigned int v47; // edx
  char *v48; // rcx
  RPC_STATUS v49; // eax
  bool v50; // sf
  __int64 v51; // rbp
  unsigned int v52; // edx
  RPC_STATUS v53; // eax
  unsigned int v54; // edi
  __int64 v55; // rax
  int v56; // ebx
  bool v57; // sf
  bool v58; // sf
  wil::details::in1diag3 *v59; // rcx
  __int64 v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rax
  int pObject; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int *v68; // [rsp+70h] [rbp+8h]
  __int64 v69; // [rsp+78h] [rbp+10h] BYREF

  v3 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 22) = 0;
  NdrMesTypeDecode2(v3, &pPicklingInfo, &pStubDesc, &pFormatString, (char *)this + 120);
  *((_DWORD *)this + 17) = *((_DWORD *)this + 33);
  *((_DWORD *)this + 16) = *((_DWORD *)this + 32);
  *((_QWORD *)this + 14) = *((_QWORD *)this + 22);
  *((_DWORD *)this + 11) = 1;
  if ( !*((_QWORD *)this + 21) || !*((_QWORD *)this + 20) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
      (const char *)0x80070057LL,
      pObject);
    return 2147942487LL;
  }
  if ( (unsigned int)(*((_DWORD *)this + 34) - 1) > 0xA )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
      (const char *)0x80070057LL,
      pObject);
    return 2147942487LL;
  }
  v6 = *((_DWORD *)a2 + 16) + *((_DWORD *)this + 31);
  v7 = (unsigned int *)((char *)a2 + 40);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 2) + 56LL))(
         *((_QWORD *)a2 + 2),
         *((unsigned int *)a2 + 9),
         v6);
  v68 = (unsigned int *)((char *)a2 + 40);
  if ( v8 )
    goto LABEL_124;
  MesHandleFree(*((handle_t *)a2 + 6));
  v9 = *v7;
  *((_QWORD *)a2 + 6) = 0;
  if ( v9 < v6 )
  {
    v8 = -2147024809;
    goto LABEL_139;
  }
  if ( *((_DWORD *)a2 + 15) == 1 )
  {
    v10 = MesDecodeBufferHandleCreate((char *)(*((_QWORD *)a2 + 3) + v6), v9 - v6, (handle_t *)a2 + 6);
  }
  else
  {
    *((_DWORD *)a2 + 8) = 0;
    if ( v9 == v6 )
      goto LABEL_13;
    v10 = MesEncodeFixedBufferHandleCreate(
            (char *)(*((_QWORD *)a2 + 3) + v6),
            v9 - v6,
            (unsigned int *)a2 + 8,
            (handle_t *)a2 + 6);
  }
  v8 = v10;
  if ( v10 )
  {
    if ( (v10 & 0x1FFF0000) != 0x10000 )
    {
      v57 = v10 < 0;
      if ( v10 <= 0 )
        goto LABEL_125;
      v8 = (unsigned __int16)v10 | 0x80070000;
    }
LABEL_124:
    v57 = (v8 & 0x80000000) != 0;
LABEL_125:
    if ( !v57 )
    {
      v68 = (unsigned int *)((char *)a2 + 40);
      goto LABEL_14;
    }
LABEL_139:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
      (const char *)v8,
      pObject);
    return v8;
  }
  if ( !*((_QWORD *)a2 + 6) )
  {
    v8 = -2147024882;
    goto LABEL_139;
  }
  v68 = (unsigned int *)((char *)a2 + 40);
LABEL_13:
  *((_DWORD *)a2 + 16) = v6;
LABEL_14:
  v11 = *v7;
  if ( *v7 > *((_DWORD *)a2 + 9) || (v12 = *((_DWORD *)a2 + 16), v12 > v11) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25E,
      (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
      (const char *)0x80070057LL,
      pObject);
    return 2147942487LL;
  }
  v13 = v11 - v12;
  v14 = v13;
  if ( (v13 & 7) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
      (const char *)0x80070057LL,
      pObject);
    return 2147942487LL;
  }
  v15 = *((_DWORD *)this + 34);
  for ( i = 0; i < v15; ++i )
  {
    v17 = *(unsigned int *)(*((_QWORD *)this + 21) + 4LL * i);
    if ( (v17 & 7) != 0 )
    {
      v59 = retaddr;
      v56 = -2147024809;
      v61 = 614;
      v60 = 2147942487LL;
      goto LABEL_137;
    }
    v18 = (unsigned int)v17;
    if ( v17 > v14 )
    {
      v59 = retaddr;
      v56 = -2147024809;
      v61 = 615;
      v60 = 2147942487LL;
      goto LABEL_137;
    }
    v19 = (_QWORD *)(16LL * i + *((_QWORD *)this + 20));
    v20 = *v19 - *(_QWORD *)&IID_IActivationSecurityInfo.Data1;
    if ( *v19 == *(_QWORD *)&IID_IActivationSecurityInfo.Data1 )
      v20 = v19[1] - *(_QWORD *)IID_IActivationSecurityInfo.Data4;
    if ( v20 )
    {
      v21 = *v19 - *(_QWORD *)&IID_ILegacyInfo.Data1;
      if ( *v19 == *(_QWORD *)&IID_ILegacyInfo.Data1 )
        v21 = v19[1] - *(_QWORD *)IID_ILegacyInfo.Data4;
      if ( v21 )
      {
        v22 = *v19 - *(_QWORD *)&IID_IServerLocationInfo.Data1;
        if ( *v19 == *(_QWORD *)&IID_IServerLocationInfo.Data1 )
          v22 = v19[1] - *(_QWORD *)IID_IServerLocationInfo.Data4;
        if ( v22 )
        {
          v23 = *v19 - *(_QWORD *)&IID_IInstantiationInfo.Data1;
          if ( *v19 == *(_QWORD *)&IID_IInstantiationInfo.Data1 )
            v23 = v19[1] - *(_QWORD *)IID_IInstantiationInfo.Data4;
          if ( v23 )
          {
            v24 = *v19 - *(_QWORD *)&IID_IActivationContextInfo.Data1;
            if ( *v19 == *(_QWORD *)&IID_IActivationContextInfo.Data1 )
              v24 = v19[1] - *(_QWORD *)IID_IActivationContextInfo.Data4;
            if ( v24 )
            {
              v25 = *v19 - *(_QWORD *)&IID_IPrivActivationContextInfo.Data1;
              if ( *v19 == *(_QWORD *)&IID_IPrivActivationContextInfo.Data1 )
                v25 = v19[1] - *(_QWORD *)IID_IPrivActivationContextInfo.Data4;
              if ( v25 )
              {
                v26 = *v19 - *(_QWORD *)&IID_IInstanceInfo.Data1;
                if ( *v19 == *(_QWORD *)&IID_IInstanceInfo.Data1 )
                  v26 = v19[1] - *(_QWORD *)IID_IInstanceInfo.Data4;
                if ( v26 )
                {
                  v27 = *v19 - *(_QWORD *)&IID_IScmRequestInfo.Data1;
                  if ( *v19 == *(_QWORD *)&IID_IScmRequestInfo.Data1 )
                    v27 = v19[1] - *(_QWORD *)IID_IScmRequestInfo.Data4;
                  if ( v27 )
                  {
                    v28 = *v19 - *(_QWORD *)&IID_ISpecialSystemProperties.Data1;
                    if ( *v19 == *(_QWORD *)&IID_ISpecialSystemProperties.Data1 )
                      v28 = v19[1] - *(_QWORD *)IID_ISpecialSystemProperties.Data4;
                    if ( v28 )
                    {
                      v29 = *v19 - *(_QWORD *)&IID_IOpaqueDataInfo.Data1;
                      if ( *v19 == *(_QWORD *)&IID_IOpaqueDataInfo.Data1 )
                        v29 = v19[1] - *(_QWORD *)IID_IOpaqueDataInfo.Data4;
                      if ( v29 )
                      {
                        v30 = *v19 - *(_QWORD *)&CLSID_ActivationPropertiesOut.Data1;
                        if ( *v19 == *(_QWORD *)&CLSID_ActivationPropertiesOut.Data1 )
                          v30 = v19[1] - *(_QWORD *)CLSID_ActivationPropertiesOut.Data4;
                        if ( v30 )
                        {
                          v31 = *v19 - *(_QWORD *)&IID_IScmReplyInfo.Data1;
                          if ( *v19 == *(_QWORD *)&IID_IScmReplyInfo.Data1 )
                            v31 = v19[1] - *(_QWORD *)IID_IScmReplyInfo.Data4;
                          if ( v31 )
                          {
                            v32 = *v19 - *(_QWORD *)&IID_IPrivActivationContextInfo.Data1;
                            if ( *v19 == *(_QWORD *)&IID_IPrivActivationContextInfo.Data1 )
                              v32 = v19[1] - *(_QWORD *)IID_IPrivActivationContextInfo.Data4;
                            if ( v32 )
                            {
                              v33 = *v19 - *(_QWORD *)&IID_IActivationProperties.Data1;
                              if ( *v19 == *(_QWORD *)&IID_IActivationProperties.Data1 )
                                v33 = v19[1] - *(_QWORD *)IID_IActivationProperties.Data4;
                              if ( v33 )
                              {
                                v34 = *v19 - *(_QWORD *)&IID_IPrivActivationPropertiesOut.Data1;
                                if ( *v19 == *(_QWORD *)&IID_IPrivActivationPropertiesOut.Data1 )
                                  v34 = v19[1] - *(_QWORD *)IID_IPrivActivationPropertiesOut.Data4;
                                if ( v34 )
                                {
                                  v35 = *v19 - *(_QWORD *)&IID_IPrivActivationPropertiesIn.Data1;
                                  if ( *v19 == *(_QWORD *)&IID_IPrivActivationPropertiesIn.Data1 )
                                    v35 = v19[1] - *(_QWORD *)IID_IPrivActivationPropertiesIn.Data4;
                                  if ( v35 )
                                  {
                                    v36 = *v19 - *(_QWORD *)&GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1;
                                    if ( *v19 == *(_QWORD *)&GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1 )
                                      v36 = v19[1] - *(_QWORD *)GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4;
                                    if ( v36 )
                                    {
                                      v37 = *v19 - *(_QWORD *)&IID_IUserContextProperties.Data1;
                                      if ( *v19 == *(_QWORD *)&IID_IUserContextProperties.Data1 )
                                        v37 = v19[1] - *(_QWORD *)IID_IUserContextProperties.Data4;
                                      if ( v37 )
                                      {
                                        v38 = *v19 - *(_QWORD *)&IID_IExtensionActivationContextProperties.Data1;
                                        if ( *v19 == *(_QWORD *)&IID_IExtensionActivationContextProperties.Data1 )
                                          v38 = v19[1] - *(_QWORD *)IID_IExtensionActivationContextProperties.Data4;
                                        if ( v38 )
                                        {
                                          wil::details::in1diag3::Return_Hr(
                                            retaddr,
                                            (void *)0x268,
                                            (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
                                            (const char *)0x80004002LL,
                                            pObject);
                                          return 2147500034LL;
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v14 -= v18;
  }
  *((_DWORD *)this + 76) = v15;
  v39 = -2147467259;
  v69 = 0;
  if ( *(_QWORD *)a2 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 2) + 56LL))(
      *((_QWORD *)a2 + 2),
      *((unsigned int *)a2 + 9),
      0);
    if ( *((_QWORD *)a2 + 1) )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a2 + 2) + 72LL))(*((_QWORD *)a2 + 2), 8);
      v39 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)a2 + 104LL))(*(_QWORD *)a2, &v69);
      if ( v39 )
        goto LABEL_109;
    }
    else
    {
      v69 = *(_QWORD *)a2;
    }
    v40 = HeapAlloc(g_hHeap, 0, 0x58u);
    v41 = v40;
    if ( !v40 )
    {
      v54 = -2147024882;
      goto LABEL_118;
    }
    v42 = *((_DWORD *)a2 + 18);
    v43 = *((_DWORD *)a2 + 20);
    v44 = *((_DWORD *)a2 + 19);
    *(_QWORD *)((char *)v40 + 36) = 0;
    v40[3] = 0;
    *((_DWORD *)v40 + 8) = 0;
    v40[8] = 0;
    *v40 = 0;
    v40[1] = 0;
    v40[2] = 0;
    v40[6] = 0;
    *((_DWORD *)v40 + 14) = 1;
    *((_DWORD *)v40 + 18) = v42;
    *((_DWORD *)v40 + 19) = v44;
    *((_DWORD *)v40 + 20) = v43;
    v45 = v69;
    v46 = *((_DWORD *)a2 + 15);
    *((_DWORD *)v40 + 10) = *v68;
    *((_DWORD *)v40 + 15) = v46;
    *v40 = v45;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
    if ( (**(unsigned int (__fastcall ***)(_QWORD, GUID *, __int64))*v41)(
           *v41,
           &IID_IBufferInternal,
           (__int64)(v41 + 2)) )
    {
      v39 = -2147467259;
      goto LABEL_104;
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD *))(*(_QWORD *)v41[2] + 32LL))(
           v41[2],
           (__int64)v41 + 36,
           v41 + 3) )
    {
      v39 = -2147467259;
      goto LABEL_104;
    }
    v47 = *((_DWORD *)v41 + 9);
    if ( v47 < *((_DWORD *)v41 + 10) )
    {
      v39 = -2147467259;
      goto LABEL_104;
    }
    v48 = (char *)v41[3];
    v41[6] = 0;
    if ( v46 == 1 )
      v49 = MesDecodeBufferHandleCreate(v48, v47, (handle_t *)v41 + 6);
    else
      v49 = MesEncodeFixedBufferHandleCreate(v48, v47, (unsigned int *)v41 + 8, (handle_t *)v41 + 6);
    v39 = v49;
    if ( !v49 )
    {
      if ( !v41[6] )
      {
        v39 = -2147024882;
LABEL_104:
        if ( v69 != *(_QWORD *)a2 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        if ( v39 < 0 )
        {
          Serializer::Release((Serializer *)v41);
          *((_QWORD *)this + 69) = 0;
        }
        v7 = v68;
        goto LABEL_109;
      }
      goto LABEL_95;
    }
    if ( (v49 & 0x1FFF0000) != 0x10000 )
    {
      v50 = v49 < 0;
      if ( v49 <= 0 )
      {
LABEL_94:
        if ( v50 )
          goto LABEL_104;
LABEL_95:
        v51 = *((unsigned int *)a2 + 16);
        v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)v41[2] + 56LL))(
                v41[2],
                *((unsigned int *)v41 + 9),
                v51);
        if ( !v39 )
        {
          MesHandleFree((handle_t)v41[6]);
          v52 = *((_DWORD *)v41 + 10);
          v41[6] = 0;
          if ( v52 < (unsigned int)v51 )
          {
            v39 = -2147024809;
            goto LABEL_104;
          }
          if ( *((_DWORD *)v41 + 15) == 1 )
          {
            v53 = MesDecodeBufferHandleCreate((char *)(v41[3] + (unsigned int)v51), v52 - v51, (handle_t *)v41 + 6);
          }
          else
          {
            *((_DWORD *)v41 + 8) = 0;
            if ( v52 == (_DWORD)v51 )
            {
LABEL_101:
              *((_DWORD *)v41 + 16) = v51;
              goto LABEL_102;
            }
            v53 = MesEncodeFixedBufferHandleCreate(
                    (char *)(v41[3] + v51),
                    v52 - v51,
                    (unsigned int *)v41 + 8,
                    (handle_t *)v41 + 6);
          }
          v39 = v53;
          if ( !v53 )
          {
            if ( !v41[6] )
            {
              v39 = -2147024882;
              goto LABEL_104;
            }
            goto LABEL_101;
          }
          if ( (v53 & 0x1FFF0000) != 0x10000 )
          {
            v58 = v53 < 0;
            if ( v53 <= 0 )
              goto LABEL_134;
            v39 = (unsigned __int16)v53 | 0x80070000;
          }
        }
        v58 = v39 < 0;
LABEL_134:
        if ( v58 )
          goto LABEL_104;
LABEL_102:
        v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 2) + 56LL))(
                *((_QWORD *)a2 + 2),
                *((unsigned int *)a2 + 9),
                *((unsigned int *)a2 + 16));
        if ( v39 >= 0 )
          *((_QWORD *)this + 69) = v41;
        goto LABEL_104;
      }
      v39 = (unsigned __int16)v49 | 0x80070000;
    }
    v50 = v39 < 0;
    goto LABEL_94;
  }
LABEL_109:
  v54 = v39;
  if ( v39 < 0 )
  {
LABEL_118:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26C,
      (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
      (const char *)v54,
      pObject);
    return v54;
  }
  v55 = *((_QWORD *)a2 + 1);
  if ( v55 && v55 != *(_QWORD *)a2 )
  {
    do
    {
      v62 = *((_QWORD *)a2 + 1);
      v63 = *v7;
      v64 = *((_QWORD *)a2 + 3);
      *((_DWORD *)a2 + 8) = 0;
      v56 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v62 + 32LL))(
              v62,
              v64,
              v63,
              (char *)a2 + 32);
      if ( v56 )
        break;
      v65 = *((unsigned int *)a2 + 8);
      *v7 -= v65;
      *((_QWORD *)a2 + 3) += v65;
    }
    while ( *v7 );
  }
  else
  {
    v56 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a2 + 2) + 56LL))(
            *((_QWORD *)a2 + 2),
            *((unsigned int *)a2 + 9),
            *v7);
  }
  if ( v56 >= 0 )
    return 0;
  v59 = retaddr;
  v60 = (unsigned int)v56;
  v61 = 621;
LABEL_137:
  wil::details::in1diag3::Return_Hr(
    v59,
    (void *)v61,
    (unsigned int)"onecore\\com\\combase\\actprops\\actprops.cxx",
    (const char *)v60,
    pObject);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x180020730  push    rbx
0x180020732  push    rbp
0x180020733  push    rsi
0x180020734  push    r13
0x180020736  push    r14
0x180020738  sub     rsp, 40h
0x18002073c  mov     r13, rcx
0x18002073f  lea     r9, pFormatString; pFormatString
0x180020746  mov     rcx, [rdx+30h]; Handle
0x18002074a  lea     r8, pStubDesc; pStubDesc
0x180020751  xor     ebp, ebp
0x180020753  mov     rsi, rdx
0x180020756  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002075d  lea     rax, [r13+78h]
0x180020761  mov     [r13+0A8h], rbp
0x180020768  mov     [rax+28h], rbp
0x18002076c  mov     qword ptr [rsp+68h+pObject], rax; int
0x180020771  mov     [r13+0B0h], rbp
0x180020778  call    cs:__imp_NdrMesTypeDecode2
0x18002077f  nop     dword ptr [rax+rax+00h]
0x180020784  mov     eax, [r13+84h]
0x18002078b  mov     [r13+44h], eax
0x18002078f  mov     eax, [r13+80h]
0x180020796  mov     [r13+40h], eax
0x18002079a  mov     rax, [r13+0B0h]
0x1800207a1  mov     [r13+70h], rax
0x1800207a5  mov     dword ptr [r13+2Ch], 1
0x1800207ad  cmp     [r13+0A8h], rbp
0x1800207b4  jz      short loc_1800207FA
0x1800207b6  cmp     [r13+0A0h], rbp
0x1800207bd  jz      short loc_1800207FA
0x1800207bf  mov     eax, [r13+88h]
0x1800207c6  dec     eax
0x1800207c8  cmp     eax, 0Ah
0x1800207cb  jbe     short loc_180020827
0x1800207cd  mov     rcx, [rsp+68h]; this
0x1800207d2  lea     r8, aOnecoreComComb_104; "onecore\\com\\combase\\actprops\\actpro"...
0x1800207d9  mov     ebx, 80070057h
0x1800207de  mov     edx, 25Bh; void *
0x1800207e3  mov     r9d, ebx; char *
0x1800207e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800207eb  mov     eax, ebx
0x1800207ed  add     rsp, 40h
0x1800207f1  pop     r14
0x1800207f3  pop     r13
0x1800207f5  pop     rsi
0x1800207f6  pop     rbp
0x1800207f7  pop     rbx
0x1800207f8  retn
0x1800207fa  mov     rcx, [rsp+68h]; this
0x1800207ff  lea     r8, aOnecoreComComb_104; "onecore\\com\\combase\\actprops\\actpro"...
0x180020806  mov     ebx, 80070057h
0x18002080b  mov     edx, 25Ah; void *
0x180020810  mov     r9d, ebx; char *
0x180020813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020818  mov     eax, ebx
0x18002081a  add     rsp, 40h
0x18002081e  pop     r14
0x180020820  pop     r13
0x180020822  pop     rsi
0x180020823  pop     rbp
0x180020824  pop     rbx
0x180020825  retn
0x180020827  mov     rcx, [rsi+10h]
0x18002082b  mov     edx, [rsi+24h]
0x18002082e  mov     [rsp+68h+arg_10], rdi
0x180020836  mov     edi, [r13+7Ch]
0x18002083a  mov     rax, [rcx]
0x18002083d  add     edi, [rsi+40h]
0x180020840  mov     r8d, edi
0x180020843  mov     [rsp+68h+var_38], r15
0x180020848  mov     rax, [rax+38h]
0x18002084c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020851  lea     r15, [rsi+28h]
0x180020855  mov     ebx, eax
0x180020857  mov     [rsp+68h+arg_0], r15
0x18002085c  test    eax, eax
0x18002085e  jnz     loc_180020EDD
0x180020864  mov     rcx, [rsi+30h]; Handle
0x180020868  call    cs:__imp_MesHandleFree
0x18002086f  nop     dword ptr [rax+rax+00h]
0x180020874  mov     edx, [r15]
0x180020877  mov     [rsi+30h], rbp
0x18002087b  cmp     edx, edi
0x18002087d  jb      loc_180020F96
0x180020883  cmp     dword ptr [rsi+3Ch], 1
0x180020887  jnz     loc_180020E96
0x18002088d  mov     ecx, edi
0x18002088f  lea     r8, [rsi+30h]; pHandle
0x180020893  add     rcx, [rsi+18h]; Buffer
0x180020897  sub     edx, edi; BufferSize
0x180020899  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800208a0  nop     dword ptr [rax+rax+00h]
0x1800208a5  mov     ebx, eax
0x1800208a7  test    eax, eax
0x1800208a9  jnz     loc_180020EC2
0x1800208af  cmp     [rsi+30h], rbp
0x1800208b3  jz      loc_180020FD2
0x1800208b9  mov     [rsp+68h+arg_0], r15
0x1800208be  mov     [rsi+40h], edi
0x1800208c1  mov     eax, [r15]
0x1800208c4  cmp     eax, [rsi+24h]
0x1800208c7  ja      loc_1800210CC
0x1800208cd  mov     ecx, [rsi+40h]
0x1800208d0  cmp     ecx, eax
0x1800208d2  ja      loc_1800210CC
0x1800208d8  sub     eax, ecx
0x1800208da  mov     r8d, eax
0x1800208dd  test    al, 7
0x1800208df  jnz     loc_180020EEF
0x1800208e5  mov     r11d, [r13+88h]
0x1800208ec  mov     r9d, ebp
0x1800208ef  mov     rbp, qword ptr cs:IID_ILegacyInfo.Data1
0x1800208f6  mov     rbx, qword ptr cs:IID_IActivationSecurityInfo.Data4
0x1800208fd  mov     rdi, qword ptr cs:IID_ILegacyInfo.Data4
0x180020904  mov     r14, qword ptr cs:IID_IServerLocationInfo.Data4
0x18002090b  mov     [rsp+68h+var_30], r12
0x180020910  mov     r12, qword ptr cs:IID_IServerLocationInfo.Data1
0x180020917  cmp     r9d, r11d
0x18002091a  jnb     loc_180020BB5
0x180020920  mov     rax, [r13+0A8h]
0x180020927  mov     edx, r9d
0x18002092a  mov     ecx, [rax+rdx*4]
0x18002092d  test    cl, 7
0x180020930  jnz     loc_18002107A
0x180020936  mov     r10d, ecx
0x180020939  cmp     rcx, r8
0x18002093c  jg      loc_18002105C
0x180020942  mov     rcx, [r13+0A0h]
0x180020949  shl     rdx, 4
0x18002094d  add     rcx, rdx
0x180020950  mov     rax, [rcx]
0x180020953  sub     rax, qword ptr cs:IID_IActivationSecurityInfo.Data1
0x18002095a  jnz     short loc_180020963
0x18002095c  mov     rax, [rcx+8]
0x180020960  sub     rax, rbx
0x180020963  test    rax, rax
0x180020966  jnz     short loc_180020970
0x180020968  sub     r8, r10
0x18002096b  inc     r9d
0x18002096e  jmp     short loc_180020917
0x180020970  mov     rax, [rcx]
0x180020973  sub     rax, rbp
0x180020976  jnz     short loc_18002097F
0x180020978  mov     rax, [rcx+8]
0x18002097c  sub     rax, rdi
0x18002097f  test    rax, rax
0x180020982  jz      short loc_180020968
0x180020984  mov     rax, [rcx]
0x180020987  sub     rax, r12
0x18002098a  jnz     short loc_180020993
0x18002098c  mov     rax, [rcx+8]
0x180020990  sub     rax, r14
0x180020993  test    rax, rax
0x180020996  jz      short loc_180020968
0x180020998  mov     rax, [rcx]
0x18002099b  sub     rax, qword ptr cs:IID_IInstantiationInfo.Data1
0x1800209a2  jnz     short loc_1800209AF
0x1800209a4  mov     rax, [rcx+8]
0x1800209a8  sub     rax, qword ptr cs:IID_IInstantiationInfo.Data4
0x1800209af  test    rax, rax
0x1800209b2  jz      short loc_180020968
0x1800209b4  mov     rax, [rcx]
0x1800209b7  sub     rax, qword ptr cs:IID_IActivationContextInfo.Data1
0x1800209be  jnz     short loc_1800209CB
0x1800209c0  mov     rax, [rcx+8]
0x1800209c4  sub     rax, qword ptr cs:IID_IActivationContextInfo.Data4
0x1800209cb  test    rax, rax
0x1800209ce  jz      short loc_180020968
0x1800209d0  mov     rax, [rcx]
0x1800209d3  mov     rdx, qword ptr cs:IID_IPrivActivationContextInfo.Data1
0x1800209da  sub     rax, rdx
0x1800209dd  jnz     short loc_1800209EA
0x1800209df  mov     rax, [rcx+8]
0x1800209e3  sub     rax, qword ptr cs:IID_IPrivActivationContextInfo.Data4
0x1800209ea  test    rax, rax
0x1800209ed  jz      loc_180020968
0x1800209f3  mov     rax, [rcx]
0x1800209f6  sub     rax, qword ptr cs:IID_IInstanceInfo.Data1
0x1800209fd  jnz     short loc_180020A0A
0x1800209ff  mov     rax, [rcx+8]
0x180020a03  sub     rax, qword ptr cs:IID_IInstanceInfo.Data4
0x180020a0a  test    rax, rax
0x180020a0d  jz      loc_180020968
0x180020a13  mov     rax, [rcx]
0x180020a16  sub     rax, qword ptr cs:IID_IScmRequestInfo.Data1
0x180020a1d  jnz     short loc_180020A2A
0x180020a1f  mov     rax, [rcx+8]
0x180020a23  sub     rax, qword ptr cs:IID_IScmRequestInfo.Data4
0x180020a2a  test    rax, rax
0x180020a2d  jz      loc_180020968
0x180020a33  mov     rax, [rcx]
0x180020a36  sub     rax, qword ptr cs:IID_ISpecialSystemProperties.Data1
0x180020a3d  jnz     short loc_180020A4A
0x180020a3f  mov     rax, [rcx+8]
0x180020a43  sub     rax, qword ptr cs:IID_ISpecialSystemProperties.Data4
0x180020a4a  test    rax, rax
0x180020a4d  jz      loc_180020968
0x180020a53  mov     rax, [rcx]
0x180020a56  sub     rax, qword ptr cs:IID_IOpaqueDataInfo.Data1
0x180020a5d  jnz     short loc_180020A6A
0x180020a5f  mov     rax, [rcx+8]
0x180020a63  sub     rax, qword ptr cs:IID_IOpaqueDataInfo.Data4
0x180020a6a  test    rax, rax
0x180020a6d  jz      loc_180020968
0x180020a73  mov     rax, [rcx]
0x180020a76  sub     rax, qword ptr cs:CLSID_ActivationPropertiesOut.Data1
0x180020a7d  jnz     short loc_180020A8A
0x180020a7f  mov     rax, [rcx+8]
0x180020a83  sub     rax, qword ptr cs:CLSID_ActivationPropertiesOut.Data4
0x180020a8a  test    rax, rax
0x180020a8d  jz      loc_180020968
0x180020a93  mov     rax, [rcx]
0x180020a96  sub     rax, qword ptr cs:IID_IScmReplyInfo.Data1
0x180020a9d  jnz     short loc_180020AAA
0x180020a9f  mov     rax, [rcx+8]
0x180020aa3  sub     rax, qword ptr cs:IID_IScmReplyInfo.Data4
0x180020aaa  test    rax, rax
0x180020aad  jz      loc_180020968
0x180020ab3  mov     rax, [rcx]
0x180020ab6  sub     rax, rdx
0x180020ab9  jnz     short loc_180020AC6
0x180020abb  mov     rax, [rcx+8]
0x180020abf  sub     rax, qword ptr cs:IID_IPrivActivationContextInfo.Data4
0x180020ac6  test    rax, rax
0x180020ac9  jz      loc_180020968
0x180020acf  mov     rax, [rcx]
0x180020ad2  sub     rax, qword ptr cs:IID_IActivationProperties.Data1
0x180020ad9  jnz     short loc_180020AE6
0x180020adb  mov     rax, [rcx+8]
0x180020adf  sub     rax, qword ptr cs:IID_IActivationProperties.Data4
0x180020ae6  test    rax, rax
0x180020ae9  jz      loc_180020968
0x180020aef  mov     rax, [rcx]
0x180020af2  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesOut.Data1
0x180020af9  jnz     short loc_180020B06
0x180020afb  mov     rax, [rcx+8]
0x180020aff  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesOut.Data4
0x180020b06  test    rax, rax
0x180020b09  jz      loc_180020968
0x180020b0f  mov     rax, [rcx]
0x180020b12  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesIn.Data1
0x180020b19  jnz     short loc_180020B26
0x180020b1b  mov     rax, [rcx+8]
0x180020b1f  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesIn.Data4
0x180020b26  test    rax, rax
0x180020b29  jz      loc_180020968
0x180020b2f  mov     rax, [rcx]
0x180020b32  sub     rax, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1
0x180020b39  jnz     short loc_180020B46
0x180020b3b  mov     rax, [rcx+8]
0x180020b3f  sub     rax, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4
0x180020b46  test    rax, rax
0x180020b49  jz      loc_180020968
0x180020b4f  mov     rax, [rcx]
0x180020b52  sub     rax, qword ptr cs:IID_IUserContextProperties.Data1
0x180020b59  jnz     short loc_180020B66
0x180020b5b  mov     rax, [rcx+8]
0x180020b5f  sub     rax, qword ptr cs:IID_IUserContextProperties.Data4
0x180020b66  test    rax, rax
0x180020b69  jz      loc_180020968
0x180020b6f  mov     rax, [rcx]
0x180020b72  sub     rax, qword ptr cs:IID_IExtensionActivationContextProperties.Data1
0x180020b79  jnz     short loc_180020B86
0x180020b7b  mov     rax, [rcx+8]
0x180020b7f  sub     rax, qword ptr cs:IID_IExtensionActivationContextProperties.Data4
0x180020b86  test    rax, rax
0x180020b89  jz      loc_180020968
0x180020b8f  mov     rcx, [rsp+68h]; this
0x180020b94  lea     r8, aOnecoreComComb_104; "onecore\\com\\combase\\actprops\\actpro"...
0x180020b9b  mov     r9d, 80004002h; char *
0x180020ba1  mov     edx, 268h; void *
0x180020ba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bab  mov     eax, 80004002h
0x180020bb0  jmp     loc_180020E25
0x180020bb5  xor     ebp, ebp
0x180020bb7  mov     [r13+130h], r11d
0x180020bbe  mov     ebx, 80004005h
0x180020bc3  mov     [rsp+68h+arg_8], rbp
0x180020bc8  cmp     [rsi], rbp
0x180020bcb  jz      loc_180020DE7
0x180020bd1  mov     rcx, [rsi+10h]
0x180020bd5  xor     r8d, r8d
0x180020bd8  mov     edx, [rsi+24h]
0x180020bdb  mov     rax, [rcx]
0x180020bde  mov     rax, [rax+38h]
0x180020be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be7  cmp     [rsi+8], rbp
0x180020beb  jnz     loc_180020E3C
0x180020bf1  mov     rax, [rsi]
0x180020bf4  mov     [rsp+68h+arg_8], rax
0x180020bf9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180020c00  xor     edx, edx; dwFlags
0x180020c02  mov     r8d, 58h ; 'X'; dwBytes
0x180020c08  call    cs:__imp_HeapAlloc
0x180020c0f  nop     dword ptr [rax+rax+00h]
0x180020c14  mov     rdi, rax
0x180020c17  test    rax, rax
0x180020c1a  jz      loc_180020E74
0x180020c20  mov     ecx, [rsi+48h]
  ... truncated ...
```
