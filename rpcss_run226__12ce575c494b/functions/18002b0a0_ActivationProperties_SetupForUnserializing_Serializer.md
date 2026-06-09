# ActivationProperties::SetupForUnserializing(Serializer *)

- ea: `0x18002b0a0`
- end: `0x18002ba21`
- name: `?SetupForUnserializing@ActivationProperties@@QEAAJPEAVSerializer@@@Z`
- size: `2433`
- prototype: `__int64 __fastcall(ActivationProperties *__hidden this, struct Serializer *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ba50`

## callees

- `0x18002b0a0`
- `0x18002ba28`
- `0x180052f20`
- `0x18010b010`

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002b7f5`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002b87b`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002b919`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002b7f5`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002b87b`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002b919`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002b1fb`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002b639`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002b6c4`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002b1fb`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002b639`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002b6c4`
- `RPCRT4!NdrMesTypeDecode2` at `0x18002b0e8`
- `RPCRT4!NdrMesTypeDecode2` at `0x18002b0e8`
- `RPCRT4!MesHandleFree` at `0x18002b1d0`
- `RPCRT4!MesHandleFree` at `0x18002b697`
- `RPCRT4!MesHandleFree` at `0x18002b1d0`
- `RPCRT4!MesHandleFree` at `0x18002b697`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b564`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b564`

## string_xrefs

- `0x18002b13c`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b168`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b4f0`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b7c2`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b832`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b8b3`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b8d8`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b991`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002b9af`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18002ba01`: `onecore\com\combase\actprops\actprops.cxx`

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
0x18002b0a0  push    rbx
0x18002b0a2  push    rbp
0x18002b0a3  push    rsi
0x18002b0a4  push    r13
0x18002b0a6  push    r14
0x18002b0a8  sub     rsp, 40h
0x18002b0ac  mov     r13, rcx
0x18002b0af  lea     r9, pFormatString; pFormatString
0x18002b0b6  mov     rcx, [rdx+30h]; Handle
0x18002b0ba  lea     r8, pStubDesc; pStubDesc
0x18002b0c1  xor     ebp, ebp
0x18002b0c3  mov     rsi, rdx
0x18002b0c6  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002b0cd  lea     rax, [r13+78h]
0x18002b0d1  mov     [r13+0A8h], rbp
0x18002b0d8  mov     [rax+28h], rbp
0x18002b0dc  mov     qword ptr [rsp+68h+pObject], rax; int
0x18002b0e1  mov     [r13+0B0h], rbp
0x18002b0e8  call    cs:__imp_NdrMesTypeDecode2
0x18002b0ee  mov     eax, [r13+84h]
0x18002b0f5  mov     [r13+44h], eax
0x18002b0f9  mov     eax, [r13+80h]
0x18002b100  mov     [r13+40h], eax
0x18002b104  mov     rax, [r13+0B0h]
0x18002b10b  mov     [r13+70h], rax
0x18002b10f  mov     dword ptr [r13+2Ch], 1
0x18002b117  cmp     [r13+0A8h], rbp
0x18002b11e  jz      short loc_18002B163
0x18002b120  cmp     [r13+0A0h], rbp
0x18002b127  jz      short loc_18002B163
0x18002b129  mov     eax, [r13+88h]
0x18002b130  dec     eax
0x18002b132  cmp     eax, 0Ah
0x18002b135  jbe     short loc_18002B18F
0x18002b137  mov     rcx, [rsp+68h]; this
0x18002b13c  lea     r8, aOnecoreComComb_104; "onecore\\com\\combase\\actprops\\actpro"...
0x18002b143  mov     ebx, 80070057h
0x18002b148  mov     edx, 25Bh; void *
0x18002b14d  mov     r9d, ebx; char *
0x18002b150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b155  mov     eax, ebx
0x18002b157  add     rsp, 40h
0x18002b15b  pop     r14
0x18002b15d  pop     r13
0x18002b15f  pop     rsi
0x18002b160  pop     rbp
0x18002b161  pop     rbx
0x18002b162  retn
0x18002b163  mov     rcx, [rsp+68h]; this
0x18002b168  lea     r8, aOnecoreComComb_104; "onecore\\com\\combase\\actprops\\actpro"...
0x18002b16f  mov     ebx, 80070057h
0x18002b174  mov     edx, 25Ah; void *
0x18002b179  mov     r9d, ebx; char *
0x18002b17c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b181  mov     eax, ebx
0x18002b183  add     rsp, 40h
0x18002b187  pop     r14
0x18002b189  pop     r13
0x18002b18b  pop     rsi
0x18002b18c  pop     rbp
0x18002b18d  pop     rbx
0x18002b18e  retn
0x18002b18f  mov     rcx, [rsi+10h]
0x18002b193  mov     edx, [rsi+24h]
0x18002b196  mov     [rsp+68h+arg_10], rdi
0x18002b19e  mov     edi, [r13+7Ch]
0x18002b1a2  mov     rax, [rcx]
0x18002b1a5  add     edi, [rsi+40h]
0x18002b1a8  mov     r8d, edi
0x18002b1ab  mov     [rsp+68h+var_38], r15
0x18002b1b0  mov     rax, [rax+38h]
0x18002b1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1b9  lea     r15, [rsi+28h]
0x18002b1bd  mov     ebx, eax
0x18002b1bf  mov     [rsp+68h+arg_0], r15
0x18002b1c4  test    eax, eax
0x18002b1c6  jnz     loc_18002B81B
0x18002b1cc  mov     rcx, [rsi+30h]; Handle
0x18002b1d0  call    cs:__imp_MesHandleFree
0x18002b1d6  mov     edx, [r15]
0x18002b1d9  mov     [rsi+30h], rbp
0x18002b1dd  cmp     edx, edi
0x18002b1df  jb      loc_18002B8CE
0x18002b1e5  cmp     dword ptr [rsi+3Ch], 1
0x18002b1e9  jnz     loc_18002B7DA
0x18002b1ef  mov     ecx, edi
0x18002b1f1  lea     r8, [rsi+30h]; pHandle
0x18002b1f5  add     rcx, [rsi+18h]; Buffer
0x18002b1f9  sub     edx, edi; BufferSize
0x18002b1fb  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002b201  mov     ebx, eax
0x18002b203  test    eax, eax
0x18002b205  jnz     loc_18002B800
0x18002b20b  cmp     [rsi+30h], rbp
0x18002b20f  jz      loc_18002B90A
0x18002b215  mov     [rsp+68h+arg_0], r15
0x18002b21a  mov     [rsi+40h], edi
0x18002b21d  mov     eax, [r15]
0x18002b220  cmp     eax, [rsi+24h]
0x18002b223  ja      loc_18002B9FC
0x18002b229  mov     ecx, [rsi+40h]
0x18002b22c  cmp     ecx, eax
0x18002b22e  ja      loc_18002B9FC
0x18002b234  sub     eax, ecx
0x18002b236  mov     r8d, eax
0x18002b239  test    al, 7
0x18002b23b  jnz     loc_18002B82D
0x18002b241  mov     r11d, [r13+88h]
0x18002b248  mov     r9d, ebp
0x18002b24b  mov     rbp, qword ptr cs:IID_ILegacyInfo.Data1
0x18002b252  mov     rbx, qword ptr cs:IID_IActivationSecurityInfo.Data4
0x18002b259  mov     rdi, qword ptr cs:IID_ILegacyInfo.Data4
0x18002b260  mov     r14, qword ptr cs:IID_IServerLocationInfo.Data4
0x18002b267  mov     [rsp+68h+var_30], r12
0x18002b26c  mov     r12, qword ptr cs:IID_IServerLocationInfo.Data1
0x18002b273  cmp     r9d, r11d
0x18002b276  jnb     loc_18002B511
0x18002b27c  mov     rax, [r13+0A8h]
0x18002b283  mov     edx, r9d
0x18002b286  mov     ecx, [rax+rdx*4]
0x18002b289  test    cl, 7
0x18002b28c  jnz     loc_18002B9AA
0x18002b292  mov     r10d, ecx
0x18002b295  cmp     rcx, r8
0x18002b298  jg      loc_18002B98C
0x18002b29e  mov     rcx, [r13+0A0h]
0x18002b2a5  shl     rdx, 4
0x18002b2a9  add     rcx, rdx
0x18002b2ac  mov     rax, [rcx]
0x18002b2af  sub     rax, qword ptr cs:IID_IActivationSecurityInfo.Data1
0x18002b2b6  jnz     short loc_18002B2BF
0x18002b2b8  mov     rax, [rcx+8]
0x18002b2bc  sub     rax, rbx
0x18002b2bf  test    rax, rax
0x18002b2c2  jnz     short loc_18002B2CC
0x18002b2c4  sub     r8, r10
0x18002b2c7  inc     r9d
0x18002b2ca  jmp     short loc_18002B273
0x18002b2cc  mov     rax, [rcx]
0x18002b2cf  sub     rax, rbp
0x18002b2d2  jnz     short loc_18002B2DB
0x18002b2d4  mov     rax, [rcx+8]
0x18002b2d8  sub     rax, rdi
0x18002b2db  test    rax, rax
0x18002b2de  jz      short loc_18002B2C4
0x18002b2e0  mov     rax, [rcx]
0x18002b2e3  sub     rax, r12
0x18002b2e6  jnz     short loc_18002B2EF
0x18002b2e8  mov     rax, [rcx+8]
0x18002b2ec  sub     rax, r14
0x18002b2ef  test    rax, rax
0x18002b2f2  jz      short loc_18002B2C4
0x18002b2f4  mov     rax, [rcx]
0x18002b2f7  sub     rax, qword ptr cs:IID_IInstantiationInfo.Data1
0x18002b2fe  jnz     short loc_18002B30B
0x18002b300  mov     rax, [rcx+8]
0x18002b304  sub     rax, qword ptr cs:IID_IInstantiationInfo.Data4
0x18002b30b  test    rax, rax
0x18002b30e  jz      short loc_18002B2C4
0x18002b310  mov     rax, [rcx]
0x18002b313  sub     rax, qword ptr cs:IID_IActivationContextInfo.Data1
0x18002b31a  jnz     short loc_18002B327
0x18002b31c  mov     rax, [rcx+8]
0x18002b320  sub     rax, qword ptr cs:IID_IActivationContextInfo.Data4
0x18002b327  test    rax, rax
0x18002b32a  jz      short loc_18002B2C4
0x18002b32c  mov     rax, [rcx]
0x18002b32f  mov     rdx, qword ptr cs:IID_IPrivActivationContextInfo.Data1
0x18002b336  sub     rax, rdx
0x18002b339  jnz     short loc_18002B346
0x18002b33b  mov     rax, [rcx+8]
0x18002b33f  sub     rax, qword ptr cs:IID_IPrivActivationContextInfo.Data4
0x18002b346  test    rax, rax
0x18002b349  jz      loc_18002B2C4
0x18002b34f  mov     rax, [rcx]
0x18002b352  sub     rax, qword ptr cs:IID_IInstanceInfo.Data1
0x18002b359  jnz     short loc_18002B366
0x18002b35b  mov     rax, [rcx+8]
0x18002b35f  sub     rax, qword ptr cs:IID_IInstanceInfo.Data4
0x18002b366  test    rax, rax
0x18002b369  jz      loc_18002B2C4
0x18002b36f  mov     rax, [rcx]
0x18002b372  sub     rax, qword ptr cs:IID_IScmRequestInfo.Data1
0x18002b379  jnz     short loc_18002B386
0x18002b37b  mov     rax, [rcx+8]
0x18002b37f  sub     rax, qword ptr cs:IID_IScmRequestInfo.Data4
0x18002b386  test    rax, rax
0x18002b389  jz      loc_18002B2C4
0x18002b38f  mov     rax, [rcx]
0x18002b392  sub     rax, qword ptr cs:IID_ISpecialSystemProperties.Data1
0x18002b399  jnz     short loc_18002B3A6
0x18002b39b  mov     rax, [rcx+8]
0x18002b39f  sub     rax, qword ptr cs:IID_ISpecialSystemProperties.Data4
0x18002b3a6  test    rax, rax
0x18002b3a9  jz      loc_18002B2C4
0x18002b3af  mov     rax, [rcx]
0x18002b3b2  sub     rax, qword ptr cs:IID_IOpaqueDataInfo.Data1
0x18002b3b9  jnz     short loc_18002B3C6
0x18002b3bb  mov     rax, [rcx+8]
0x18002b3bf  sub     rax, qword ptr cs:IID_IOpaqueDataInfo.Data4
0x18002b3c6  test    rax, rax
0x18002b3c9  jz      loc_18002B2C4
0x18002b3cf  mov     rax, [rcx]
0x18002b3d2  sub     rax, qword ptr cs:CLSID_ActivationPropertiesOut.Data1
0x18002b3d9  jnz     short loc_18002B3E6
0x18002b3db  mov     rax, [rcx+8]
0x18002b3df  sub     rax, qword ptr cs:CLSID_ActivationPropertiesOut.Data4
0x18002b3e6  test    rax, rax
0x18002b3e9  jz      loc_18002B2C4
0x18002b3ef  mov     rax, [rcx]
0x18002b3f2  sub     rax, qword ptr cs:IID_IScmReplyInfo.Data1
0x18002b3f9  jnz     short loc_18002B406
0x18002b3fb  mov     rax, [rcx+8]
0x18002b3ff  sub     rax, qword ptr cs:IID_IScmReplyInfo.Data4
0x18002b406  test    rax, rax
0x18002b409  jz      loc_18002B2C4
0x18002b40f  mov     rax, [rcx]
0x18002b412  sub     rax, rdx
0x18002b415  jnz     short loc_18002B422
0x18002b417  mov     rax, [rcx+8]
0x18002b41b  sub     rax, qword ptr cs:IID_IPrivActivationContextInfo.Data4
0x18002b422  test    rax, rax
0x18002b425  jz      loc_18002B2C4
0x18002b42b  mov     rax, [rcx]
0x18002b42e  sub     rax, qword ptr cs:IID_IActivationProperties.Data1
0x18002b435  jnz     short loc_18002B442
0x18002b437  mov     rax, [rcx+8]
0x18002b43b  sub     rax, qword ptr cs:IID_IActivationProperties.Data4
0x18002b442  test    rax, rax
0x18002b445  jz      loc_18002B2C4
0x18002b44b  mov     rax, [rcx]
0x18002b44e  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesOut.Data1
0x18002b455  jnz     short loc_18002B462
0x18002b457  mov     rax, [rcx+8]
0x18002b45b  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesOut.Data4
0x18002b462  test    rax, rax
0x18002b465  jz      loc_18002B2C4
0x18002b46b  mov     rax, [rcx]
0x18002b46e  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesIn.Data1
0x18002b475  jnz     short loc_18002B482
0x18002b477  mov     rax, [rcx+8]
0x18002b47b  sub     rax, qword ptr cs:IID_IPrivActivationPropertiesIn.Data4
0x18002b482  test    rax, rax
0x18002b485  jz      loc_18002B2C4
0x18002b48b  mov     rax, [rcx]
0x18002b48e  sub     rax, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1
0x18002b495  jnz     short loc_18002B4A2
0x18002b497  mov     rax, [rcx+8]
0x18002b49b  sub     rax, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4
0x18002b4a2  test    rax, rax
0x18002b4a5  jz      loc_18002B2C4
0x18002b4ab  mov     rax, [rcx]
0x18002b4ae  sub     rax, qword ptr cs:IID_IUserContextProperties.Data1
0x18002b4b5  jnz     short loc_18002B4C2
0x18002b4b7  mov     rax, [rcx+8]
0x18002b4bb  sub     rax, qword ptr cs:IID_IUserContextProperties.Data4
0x18002b4c2  test    rax, rax
0x18002b4c5  jz      loc_18002B2C4
0x18002b4cb  mov     rax, [rcx]
0x18002b4ce  sub     rax, qword ptr cs:IID_IExtensionActivationContextProperties.Data1
0x18002b4d5  jnz     short loc_18002B4E2
0x18002b4d7  mov     rax, [rcx+8]
0x18002b4db  sub     rax, qword ptr cs:IID_IExtensionActivationContextProperties.Data4
0x18002b4e2  test    rax, rax
0x18002b4e5  jz      loc_18002B2C4
0x18002b4eb  mov     rcx, [rsp+68h]; this
0x18002b4f0  lea     r8, aOnecoreComComb_104; "onecore\\com\\combase\\actprops\\actpro"...
0x18002b4f7  mov     r9d, 80004002h; char *
0x18002b4fd  mov     edx, 268h; void *
0x18002b502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b507  mov     eax, 80004002h
0x18002b50c  jmp     loc_18002B769
0x18002b511  xor     ebp, ebp
0x18002b513  mov     [r13+130h], r11d
0x18002b51a  mov     ebx, 80004005h
0x18002b51f  mov     [rsp+68h+arg_8], rbp
0x18002b524  cmp     [rsi], rbp
0x18002b527  jz      loc_18002B72B
0x18002b52d  mov     rcx, [rsi+10h]
0x18002b531  xor     r8d, r8d
0x18002b534  mov     edx, [rsi+24h]
0x18002b537  mov     rax, [rcx]
0x18002b53a  mov     rax, [rax+38h]
0x18002b53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b543  cmp     [rsi+8], rbp
0x18002b547  jnz     loc_18002B780
0x18002b54d  mov     rax, [rsi]
0x18002b550  mov     [rsp+68h+arg_8], rax
0x18002b555  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002b55c  xor     edx, edx; dwFlags
0x18002b55e  mov     r8d, 58h ; 'X'; dwBytes
0x18002b564  call    cs:__imp_HeapAlloc
0x18002b56a  mov     rdi, rax
0x18002b56d  test    rax, rax
0x18002b570  jz      loc_18002B7B8
0x18002b576  mov     ecx, [rsi+48h]
0x18002b579  mov     r8d, [rsi+50h]
0x18002b57d  mov     edx, [rsi+4Ch]
0x18002b580  mov     [rax+24h], rbp
0x18002b584  mov     [rax+18h], rbp
  ... truncated ...
```
