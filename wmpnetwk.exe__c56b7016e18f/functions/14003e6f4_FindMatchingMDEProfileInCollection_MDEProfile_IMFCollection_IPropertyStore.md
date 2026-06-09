# FindMatchingMDEProfileInCollection(MDEProfile *,IMFCollection *,IPropertyStore * *)

- ea: `0x14003e6f4`
- end: `0x14003f147`
- name: `?FindMatchingMDEProfileInCollection@@YAJPEAUMDEProfile@@PEAUIMFCollection@@PEAPEAUIPropertyStore@@@Z`
- size: `2643`
- prototype: `__int64 __fastcall(struct MDEProfile *, struct IMFCollection *, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140041c80`

## callees

- `0x14003ca4c`
- `0x14003de0c`
- `0x14003e6f4`
- `0x14003f17c`
- `0x14003f1bc`
- `0x14004a834`
- `0x140054534`
- `0x1400547b0`
- `0x14005480c`
- `0x140057bc4`
- `0x1400909a4`
- `0x140095d54`
- `0x14009a8e4`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14003ee42`
- `KERNEL32!CompareStringOrdinal` at `0x14003ee42`
- `ole32!PropVariantClear` at `0x14003e8e0`
- `ole32!PropVariantClear` at `0x14003ea28`
- `ole32!PropVariantClear` at `0x14003ead0`
- `ole32!PropVariantClear` at `0x14003eb9c`
- `ole32!PropVariantClear` at `0x14003ed3a`
- `ole32!PropVariantClear` at `0x14003ee5c`
- `ole32!PropVariantClear` at `0x14003eef5`
- `ole32!PropVariantClear` at `0x14003f0dc`
- `ole32!PropVariantClear` at `0x14003e8e0`
- `ole32!PropVariantClear` at `0x14003ea28`
- `ole32!PropVariantClear` at `0x14003ead0`
- `ole32!PropVariantClear` at `0x14003eb9c`
- `ole32!PropVariantClear` at `0x14003ed3a`
- `ole32!PropVariantClear` at `0x14003ee5c`
- `ole32!PropVariantClear` at `0x14003eef5`
- `ole32!PropVariantClear` at `0x14003f0dc`

## pseudocode

```c
__int64 __fastcall FindMatchingMDEProfileInCollection(
        struct MDEProfile *a1,
        struct IMFCollection *a2,
        struct IPropertyStore **a3)
{
  struct IMFCollection *v4; // rdi
  struct IMFCollectionVtbl *lpVtbl; // rax
  int v7; // eax
  int v8; // ebx
  PVOID *v9; // rcx
  unsigned int i; // esi
  struct IMFCollectionVtbl *v11; // rax
  HRESULT (__stdcall *GetElement)(IMFCollection *, DWORD, IUnknown **); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, struct IPropertyStore **); // rdi
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  PVOID *v20; // rcx
  int v21; // r15d
  int v22; // r14d
  BOOL v23; // esi
  int v24; // ebx
  int v25; // ebx
  _QWORD *v26; // rdi
  __int64 v27; // rax
  int v28; // eax
  _QWORD *v29; // r8
  PVOID *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const WCHAR *v33; // r8
  PVOID *v34; // rcx
  int v35; // edi
  int v36; // esi
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  struct IPropertyStore *v40; // r9
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  int v44; // [rsp+28h] [rbp-48h]
  int v45; // [rsp+30h] [rbp-40h]
  int v46; // [rsp+38h] [rbp-38h]
  struct IPropertyStore *v47; // [rsp+40h] [rbp-30h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, struct IPropertyStore **); // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v50; // [rsp+60h] [rbp-10h]
  unsigned int v52; // [rsp+C0h] [rbp+50h]
  unsigned int v53; // [rsp+C8h] [rbp+58h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, a1, a2, a3);
  }
  v50 = 0;
  lpVtbl = v4->lpVtbl;
  v53 = 0;
  *(_OWORD *)pvar = 0;
  v7 = ((__int64 (__fastcall *)(struct IMFCollection *, unsigned int *))lpVtbl->GetElementCount)(v4, &v53);
  v8 = v7;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v7 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      &WPP_12d29b41b149367017654092f21a41cc_Traceguids,
      (unsigned int)v7);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v52 = i;
      if ( i >= v53 )
        goto LABEL_134;
      v11 = v4->lpVtbl;
      v48 = 0;
      GetElement = v11->GetElement;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      v13 = ((__int64 (__fastcall *)(struct IMFCollection *, _QWORD, _QWORD))GetElement)(v4, i, &v48);
      v8 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v13 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_ddq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_12d29b41b149367017654092f21a41cc_Traceguids,
          (unsigned int)v13,
          i,
          v48);
      }
      if ( v8 >= 0 )
        break;
LABEL_33:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v48;
    v47 = 0;
    v15 = **v48;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v16 = v15(v14, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v47);
    v8 = v16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v16 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        &WPP_12d29b41b149367017654092f21a41cc_Traceguids,
        (unsigned int)v16,
        v47);
    }
    if ( v8 < 0 )
      goto LABEL_32;
    PropVariantClear(pvar);
    v17 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
            v47,
            PKEY_MDEPROFILE_TRANSCODING_PROFILE,
            pvar);
    v8 = v17;
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v18 = ((v17 >> 31) & 0xFFFFFFFD) + 5;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v18 )
      {
        v46 = LOWORD(pvar[0]);
        v45 = 11;
        v44 = 1;
        WPP_SF_d_guid_Ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
          v17,
          (__int64)PKEY_MDEPROFILE_TRANSCODING_PROFILE);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v8 < 0 )
    {
LABEL_32:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
      v4 = a2;
      goto LABEL_33;
    }
    if ( LOWORD(pvar[0]) != 11 )
    {
      v8 = -2147418113;
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x20) != 0 && *((_BYTE *)v20 + 25) >= 4u )
        WPP_SF__guid_Ddd(v20[2], 70, v19, PKEY_MDEPROFILE_TRANSCODING_PROFILE, 1, 11, LOWORD(pvar[0]), v46);
      goto LABEL_32;
    }
    v21 = 0;
    v22 = 0;
    v23 = LOWORD(pvar[1]) != 0;
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x20) != 0 && *((_BYTE *)v20 + 25) >= 4u )
      WPP_SF_ll(v20[2], v18, v19, LOWORD(pvar[1]) != 0, *((_DWORD *)a1 + 5), v44, v45);
    PropVariantClear(pvar);
    v24 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
            v47,
            PKEY_MDEPROFILE_HTTP_ENABLED,
            pvar);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v24 >> 31) & 0xFFFFFFFD) + 5 )
    {
      v46 = LOWORD(pvar[0]);
      v45 = 11;
      v44 = 8;
      WPP_SF_d_guid_Ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
        v24,
        (__int64)PKEY_MDEPROFILE_HTTP_ENABLED);
    }
    if ( v24 >= 0 && LOWORD(pvar[0]) == 11 )
      LOBYTE(v22) = LOWORD(pvar[1]) != 0;
    PropVariantClear(pvar);
    v25 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
            v47,
            PKEY_MDEPROFILE_RTSP_ENABLED,
            pvar);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v25 >> 31) & 0xFFFFFFFD) + 5 )
    {
      v46 = LOWORD(pvar[0]);
      v45 = 11;
      v44 = 5;
      WPP_SF_d_guid_Ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
        v25,
        (__int64)PKEY_MDEPROFILE_RTSP_ENABLED);
    }
    if ( v25 >= 0 && LOWORD(pvar[0]) == 11 )
      LOBYTE(v21) = LOWORD(pvar[1]) != 0;
    v26 = (_QWORD *)((char *)a1 + 4);
    v27 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)((char *)a1 + 4);
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)((char *)a1 + 4) )
      v27 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)((char *)a1 + 12);
    if ( v27 )
    {
      PropVariantClear(pvar);
      v28 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
              v47,
              PKEY_MDEPROFILE_UNIQUE_PROFILEID,
              pvar);
      v8 = v28;
      v30 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v28 >> 31) & 0xFFFFFFFD) + 5 )
      {
        v46 = LOWORD(pvar[0]);
        v45 = 72;
        v44 = 0;
        WPP_SF_d_guid_Ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
          v28,
          (__int64)PKEY_MDEPROFILE_UNIQUE_PROFILEID);
        v30 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 >= 0 )
      {
        if ( LOWORD(pvar[0]) == 72 && (v29 = pvar[1]) != 0 )
        {
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 0x20) != 0 && *((_BYTE *)v30 + 25) >= 4u )
          {
            WPP_SF__guid__guid_(
              (unsigned int)v30[2],
              76,
              (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
              pvar[1],
              (__int64)a1 + 4);
            v29 = pvar[1];
          }
          v31 = *v29 - *v26;
          if ( *v29 == *v26 )
            v31 = v29[1] - *(_QWORD *)((char *)a1 + 12);
          if ( !v31 )
          {
            v40 = v47;
            *a3 = v47;
            v47 = 0;
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            {
              goto LABEL_129;
            }
            v42 = 77;
            goto LABEL_128;
          }
        }
        else
        {
          v8 = -2147418113;
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 0x20) != 0 && *((_BYTE *)v30 + 25) >= 4u )
            WPP_SF__guid_Ddd(v30[2], 75, v29, PKEY_MDEPROFILE_UNIQUE_PROFILEID, 0, 72, LOWORD(pvar[0]), v46);
        }
      }
      goto LABEL_69;
    }
    v8 = 0;
    if ( *((_DWORD *)a1 + 5) )
    {
      if ( v23 && (v22 && !*((_DWORD *)a1 + 14) || v21 && *((_DWORD *)a1 + 14) == 1) )
      {
        PropVariantClear(pvar);
        v32 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
                v47,
                PKEY_MDEPROFILE_OUTPUTMIMETYPE,
                pvar);
        v8 = v32;
        v34 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v32 >> 31) & 0xFFFFFFFD) + 5 )
        {
          v46 = LOWORD(pvar[0]);
          v45 = 31;
          v44 = 3;
          WPP_SF_d_guid_Ddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
            v32,
            (__int64)PKEY_MDEPROFILE_OUTPUTMIMETYPE);
          v34 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v8 >= 0 )
        {
          if ( LOWORD(pvar[0]) == 31 && (v33 = (const WCHAR *)pvar[1]) != 0 )
          {
            if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 0x20) != 0 && *((_BYTE *)v34 + 25) >= 4u )
            {
              WPP_SF_SS((TRACEHANDLE)v34[2], *((_QWORD *)a1 + 4));
              v33 = (const WCHAR *)pvar[1];
            }
            if ( v33 && CompareStringOrdinal(*((LPCWCH *)a1 + 4), -1, v33, -1, 1) == 2 )
            {
              v35 = -1;
              v36 = -1;
              PropVariantClear(pvar);
              v37 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
                      v47,
                      PKEY_MDEPROFILE_IMAGE_WIDTH,
                      pvar);
              v38 = v37;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v37 >> 31) & 0xFFFFFFFD) + 5 )
              {
                v46 = LOWORD(pvar[0]);
                v45 = 19;
                v44 = 40;
                WPP_SF_d_guid_Ddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  82,
                  (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
                  v37,
                  (__int64)PKEY_MDEPROFILE_IMAGE_WIDTH);
              }
              if ( v38 >= 0 && LOWORD(pvar[0]) == 19 )
                v35 = (int)pvar[1];
              PropVariantClear(pvar);
              v39 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v47->lpVtbl->GetValue)(
                      v47,
                      PKEY_MDEPROFILE_IMAGE_HEIGHT,
                      pvar);
              v8 = v39;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v39 >> 31) & 0xFFFFFFFD) + 5 )
              {
                v46 = LOWORD(pvar[0]);
                v45 = 19;
                v44 = 41;
                WPP_SF_d_guid_Ddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  83,
                  (unsigned int)&WPP_12d29b41b149367017654092f21a41cc_Traceguids,
                  v39,
                  (__int64)PKEY_MDEPROFILE_IMAGE_HEIGHT);
              }
              if ( v8 >= 0 && LOWORD(pvar[0]) == 19 )
                v36 = (int)pvar[1];
              if ( v35 == *((_DWORD *)a1 + 26) && v36 == *((_DWORD *)a1 + 27) )
              {
                v40 = v47;
                v47 = 0;
                *a3 = v40;
                v41 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  v42 = 84;
                  goto LABEL_128;
                }
LABEL_129:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
                v9 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_134;
              }
LABEL_69:
              i = v52;
              goto LABEL_32;
            }
          }
          else
          {
            v8 = -2147418113;
            if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 0x20) != 0 && *((_BYTE *)v34 + 25) >= 4u )
              WPP_SF__guid_Ddd(v34[2], 80, v33, PKEY_MDEPROFILE_OUTPUTMIMETYPE, 3, 31, LOWORD(pvar[0]), v46);
          }
        }
        i = v52;
        goto LABEL_32;
      }
    }
    else if ( !v23 && (v22 && !*((_DWORD *)a1 + 14) || v21 && *((_DWORD *)a1 + 14) == 1) )
    {
      v40 = v47;
      *a3 = v47;
      v47 = 0;
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_129;
      }
      v42 = 78;
LABEL_128:
      WPP_SF_q(v41[2], v42, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, v40);
      goto LABEL_129;
    }
    i = v52;
    goto LABEL_32;
  }
LABEL_134:
  if ( !*a3 )
  {
    v8 = -2147024809;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_d(v9[2], 85, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, 2147942487LL);
  }
  PropVariantClear(pvar);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      &WPP_12d29b41b149367017654092f21a41cc_Traceguids,
      (unsigned int)v8,
      *a3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003e6f4  mov     [rsp-38h+arg_0], rbx
0x14003e6f9  mov     [rsp-38h+arg_8], rdx
0x14003e6fe  push    rbp
0x14003e6ff  push    rsi
0x14003e700  push    rdi
0x14003e701  push    r12
0x14003e703  push    r13
0x14003e705  push    r14
0x14003e707  push    r15
0x14003e709  mov     rbp, rsp
0x14003e70c  sub     rsp, 70h
0x14003e710  mov     r12, r8
0x14003e713  mov     rdi, rdx
0x14003e716  mov     r13, rcx
0x14003e719  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e720  lea     r15, WPP_GLOBAL_Control
0x14003e727  cmp     rcx, r15
0x14003e72a  jz      short loc_14003E75A
0x14003e72c  test    byte ptr [rcx+1Ch], 2
0x14003e730  jz      short loc_14003E75A
0x14003e732  cmp     byte ptr [rcx+19h], 5
0x14003e736  jb      short loc_14003E75A
0x14003e738  mov     rcx, [rcx+10h]
0x14003e73c  mov     edx, 41h ; 'A'
0x14003e741  mov     [rsp+70h+var_48], r8
0x14003e746  mov     r9, r13
0x14003e749  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003e750  mov     qword ptr [rsp+70h+bIgnoreCase], rdi
0x14003e755  call    WPP_SF_qqq
0x14003e75a  xor     eax, eax
0x14003e75c  lea     rdx, [rbp+arg_18]
0x14003e760  mov     [rbp+var_10], rax
0x14003e764  xorps   xmm0, xmm0
0x14003e767  mov     rax, [rdi]
0x14003e76a  xor     r14d, r14d
0x14003e76d  mov     rcx, rdi
0x14003e770  mov     [rbp+arg_18], r14d
0x14003e774  movups  xmmword ptr [rbp+pvar], xmm0
0x14003e778  mov     rax, [rax+18h]
0x14003e77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e781  mov     ebx, eax
0x14003e783  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e78a  cmp     rcx, r15
0x14003e78d  jz      short loc_14003E7CD
0x14003e78f  test    byte ptr [rcx+1Ch], 20h
0x14003e793  jz      short loc_14003E7CD
0x14003e795  mov     edx, eax
0x14003e797  movzx   eax, byte ptr [rcx+19h]
0x14003e79b  sar     edx, 1Fh
0x14003e79e  and     edx, 0FFFFFFFDh
0x14003e7a1  add     edx, 5
0x14003e7a4  cmp     eax, edx
0x14003e7a6  jb      short loc_14003E7CD
0x14003e7a8  mov     eax, [rbp+arg_18]
0x14003e7ab  lea     edx, [r14+42h]
0x14003e7af  mov     rcx, [rcx+10h]
0x14003e7b3  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003e7ba  mov     r9d, ebx
0x14003e7bd  mov     [rsp+70h+bIgnoreCase], eax
0x14003e7c1  call    WPP_SF_Dd
0x14003e7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e7cd  test    ebx, ebx
0x14003e7cf  js      loc_14003F0A2
0x14003e7d5  mov     esi, r14d
0x14003e7d8  mov     [rbp+arg_10], esi
0x14003e7db  cmp     esi, [rbp+arg_18]
0x14003e7de  jnb     loc_14003F0A2
0x14003e7e4  mov     rax, [rdi]
0x14003e7e7  lea     rcx, [rbp+var_28]
0x14003e7eb  mov     [rbp+var_28], r14
0x14003e7ef  mov     rbx, [rax+20h]
0x14003e7f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003e7f8  lea     r8, [rbp+var_28]
0x14003e7fc  mov     edx, esi
0x14003e7fe  mov     rcx, rdi
0x14003e801  mov     rax, rbx
0x14003e804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e809  mov     ebx, eax
0x14003e80b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e812  cmp     rcx, r15
0x14003e815  jz      short loc_14003E855
0x14003e817  test    byte ptr [rcx+1Ch], 20h
0x14003e81b  jz      short loc_14003E855
0x14003e81d  mov     edx, eax
0x14003e81f  movzx   eax, byte ptr [rcx+19h]
0x14003e823  sar     edx, 1Fh
0x14003e826  and     edx, 0FFFFFFFDh
0x14003e829  add     edx, 5
0x14003e82c  cmp     eax, edx
0x14003e82e  jb      short loc_14003E855
0x14003e830  mov     rax, [rbp+var_28]
0x14003e834  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003e83b  mov     rcx, [rcx+10h]
0x14003e83f  mov     edx, 43h ; 'C'
0x14003e844  mov     [rsp+70h+var_48], rax
0x14003e849  mov     r9d, ebx
0x14003e84c  mov     [rsp+70h+bIgnoreCase], esi
0x14003e850  call    WPP_SF_ddq
0x14003e855  test    ebx, ebx
0x14003e857  js      loc_14003E9D1
0x14003e85d  mov     rbx, [rbp+var_28]
0x14003e861  lea     rcx, [rbp+var_30]
0x14003e865  mov     [rbp+var_30], r14
0x14003e869  mov     rax, [rbx]
0x14003e86c  mov     rdi, [rax]
0x14003e86f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003e874  lea     r8, [rbp+var_30]
0x14003e878  mov     rcx, rbx
0x14003e87b  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x14003e882  mov     rax, rdi
0x14003e885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e88a  mov     ebx, eax
0x14003e88c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e893  cmp     rcx, r15
0x14003e896  jz      short loc_14003E8D2
0x14003e898  test    byte ptr [rcx+1Ch], 20h
0x14003e89c  jz      short loc_14003E8D2
0x14003e89e  mov     edx, eax
0x14003e8a0  movzx   eax, byte ptr [rcx+19h]
0x14003e8a4  sar     edx, 1Fh
0x14003e8a7  and     edx, 0FFFFFFFDh
0x14003e8aa  add     edx, 5
0x14003e8ad  cmp     eax, edx
0x14003e8af  jb      short loc_14003E8D2
0x14003e8b1  mov     rax, [rbp+var_30]
0x14003e8b5  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003e8bc  mov     rcx, [rcx+10h]
0x14003e8c0  mov     edx, 44h ; 'D'
0x14003e8c5  mov     r9d, ebx
0x14003e8c8  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x14003e8cd  call    WPP_SF_dq
0x14003e8d2  xor     edi, edi
0x14003e8d4  test    ebx, ebx
0x14003e8d6  js      loc_14003E9C1
0x14003e8dc  lea     rcx, [rbp+pvar]; pvar
0x14003e8e0  call    cs:__imp_PropVariantClear
0x14003e8e6  mov     rcx, [rbp+var_30]
0x14003e8ea  lea     r8, [rbp+pvar]
0x14003e8ee  lea     rdx, PKEY_MDEPROFILE_TRANSCODING_PROFILE
0x14003e8f5  mov     rax, [rcx]
0x14003e8f8  mov     rax, [rax+28h]
0x14003e8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e901  mov     ebx, eax
0x14003e903  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e90a  cmp     rcx, r15
0x14003e90d  jz      short loc_14003E96E
0x14003e90f  test    byte ptr [rcx+1Ch], 20h
0x14003e913  jz      short loc_14003E96E
0x14003e915  mov     edx, eax
0x14003e917  lea     r14d, [rdi+0Bh]
0x14003e91b  movzx   eax, byte ptr [rcx+19h]
0x14003e91f  sar     edx, 1Fh
0x14003e922  and     edx, 0FFFFFFFDh
0x14003e925  add     edx, 5
0x14003e928  cmp     eax, edx
0x14003e92a  jb      short loc_14003E974
0x14003e92c  movzx   eax, word ptr [rbp+pvar]
0x14003e930  lea     edx, [rdi+45h]
0x14003e933  mov     rcx, [rcx+10h]
0x14003e937  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003e93e  mov     [rsp+70h+var_38], eax
0x14003e942  mov     r9d, ebx
0x14003e945  mov     eax, cs:dword_1400A5F20
0x14003e94b  mov     [rsp+70h+var_40], r14d
0x14003e950  mov     dword ptr [rsp+70h+var_48], eax
0x14003e954  lea     rax, PKEY_MDEPROFILE_TRANSCODING_PROFILE
0x14003e95b  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x14003e960  call    WPP_SF_d_guid_Ddd
0x14003e965  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e96c  jmp     short loc_14003E974
0x14003e96e  mov     r14d, 0Bh
0x14003e974  test    ebx, ebx
0x14003e976  js      short loc_14003E9C1
0x14003e978  cmp     r14w, word ptr [rbp+pvar]
0x14003e97d  jz      short loc_14003E9E8
0x14003e97f  mov     ebx, 8000FFFFh
0x14003e984  cmp     rcx, r15
0x14003e987  jz      short loc_14003E9C1
0x14003e989  test    byte ptr [rcx+1Ch], 20h
0x14003e98d  jz      short loc_14003E9C1
0x14003e98f  cmp     byte ptr [rcx+19h], 4
0x14003e993  jb      short loc_14003E9C1
0x14003e995  movzx   eax, word ptr [rbp+pvar]
0x14003e999  lea     r9, PKEY_MDEPROFILE_TRANSCODING_PROFILE
0x14003e9a0  mov     rcx, [rcx+10h]
0x14003e9a4  mov     edx, 46h ; 'F'
0x14003e9a9  mov     [rsp+70h+var_40], eax
0x14003e9ad  mov     eax, cs:dword_1400A5F20
0x14003e9b3  mov     dword ptr [rsp+70h+var_48], r14d
0x14003e9b8  mov     [rsp+70h+bIgnoreCase], eax
0x14003e9bc  call    WPP_SF__guid_Ddd
0x14003e9c1  xor     r14d, r14d
0x14003e9c4  lea     rcx, [rbp+var_30]
0x14003e9c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003e9cd  mov     rdi, [rbp+arg_8]
0x14003e9d1  lea     rcx, [rbp+var_28]
0x14003e9d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003e9da  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e9e1  inc     esi
0x14003e9e3  jmp     loc_14003E7D8
0x14003e9e8  cmp     word ptr [rbp+pvar+8], di
0x14003e9ec  mov     esi, edi
0x14003e9ee  mov     r15d, edi
0x14003e9f1  mov     r14d, edi
0x14003e9f4  setnz   sil
0x14003e9f8  lea     rax, WPP_GLOBAL_Control
0x14003e9ff  cmp     rcx, rax
0x14003ea02  jz      short loc_14003EA24
0x14003ea04  test    byte ptr [rcx+1Ch], 20h
0x14003ea08  jz      short loc_14003EA24
0x14003ea0a  cmp     byte ptr [rcx+19h], 4
0x14003ea0e  jb      short loc_14003EA24
0x14003ea10  mov     eax, [r13+14h]
0x14003ea14  mov     r9d, esi
0x14003ea17  mov     rcx, [rcx+10h]
0x14003ea1b  mov     [rsp+70h+bIgnoreCase], eax
0x14003ea1f  call    WPP_SF_ll
0x14003ea24  lea     rcx, [rbp+pvar]; pvar
0x14003ea28  call    cs:__imp_PropVariantClear
0x14003ea2e  mov     rcx, [rbp+var_30]
0x14003ea32  lea     r8, [rbp+pvar]
0x14003ea36  lea     rdx, PKEY_MDEPROFILE_HTTP_ENABLED
0x14003ea3d  mov     rax, [rcx]
0x14003ea40  mov     rax, [rax+28h]
0x14003ea44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ea49  mov     ebx, eax
0x14003ea4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea52  lea     rax, WPP_GLOBAL_Control
0x14003ea59  cmp     rcx, rax
0x14003ea5c  jz      short loc_14003EAB5
0x14003ea5e  test    byte ptr [rcx+1Ch], 20h
0x14003ea62  jz      short loc_14003EAB5
0x14003ea64  movzx   eax, byte ptr [rcx+19h]
0x14003ea68  mov     edx, ebx
0x14003ea6a  sar     edx, 1Fh
0x14003ea6d  and     edx, 0FFFFFFFDh
0x14003ea70  add     edx, 5
0x14003ea73  cmp     eax, edx
0x14003ea75  jb      short loc_14003EAB5
0x14003ea77  movzx   eax, word ptr [rbp+pvar]
0x14003ea7b  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003ea82  mov     rcx, [rcx+10h]
0x14003ea86  mov     edx, 48h ; 'H'
0x14003ea8b  mov     [rsp+70h+var_38], eax
0x14003ea8f  mov     r9d, ebx
0x14003ea92  mov     eax, cs:dword_1400A5F98
0x14003ea98  mov     [rsp+70h+var_40], 0Bh
0x14003eaa0  mov     dword ptr [rsp+70h+var_48], eax
0x14003eaa4  lea     rax, PKEY_MDEPROFILE_HTTP_ENABLED
0x14003eaab  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x14003eab0  call    WPP_SF_d_guid_Ddd
0x14003eab5  test    ebx, ebx
0x14003eab7  js      short loc_14003EACC
0x14003eab9  mov     eax, 0Bh
0x14003eabe  cmp     ax, word ptr [rbp+pvar]
0x14003eac2  jnz     short loc_14003EACC
0x14003eac4  cmp     word ptr [rbp+pvar+8], di
0x14003eac8  setnz   r14b
0x14003eacc  lea     rcx, [rbp+pvar]; pvar
0x14003ead0  call    cs:__imp_PropVariantClear
0x14003ead6  mov     rcx, [rbp+var_30]
0x14003eada  lea     r8, [rbp+pvar]
0x14003eade  lea     rdx, PKEY_MDEPROFILE_RTSP_ENABLED
0x14003eae5  mov     rax, [rcx]
0x14003eae8  mov     rax, [rax+28h]
0x14003eaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eaf1  mov     ebx, eax
0x14003eaf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eafa  lea     rax, WPP_GLOBAL_Control
0x14003eb01  cmp     rcx, rax
0x14003eb04  jz      short loc_14003EB5D
0x14003eb06  test    byte ptr [rcx+1Ch], 20h
0x14003eb0a  jz      short loc_14003EB5D
0x14003eb0c  movzx   eax, byte ptr [rcx+19h]
0x14003eb10  mov     edx, ebx
0x14003eb12  sar     edx, 1Fh
0x14003eb15  and     edx, 0FFFFFFFDh
0x14003eb18  add     edx, 5
0x14003eb1b  cmp     eax, edx
0x14003eb1d  jb      short loc_14003EB5D
0x14003eb1f  movzx   eax, word ptr [rbp+pvar]
0x14003eb23  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x14003eb2a  mov     rcx, [rcx+10h]
0x14003eb2e  mov     edx, 49h ; 'I'
0x14003eb33  mov     [rsp+70h+var_38], eax
0x14003eb37  mov     r9d, ebx
0x14003eb3a  mov     eax, cs:dword_1400A5F80
0x14003eb40  mov     [rsp+70h+var_40], 0Bh
0x14003eb48  mov     dword ptr [rsp+70h+var_48], eax
0x14003eb4c  lea     rax, PKEY_MDEPROFILE_RTSP_ENABLED
0x14003eb53  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x14003eb58  call    WPP_SF_d_guid_Ddd
0x14003eb5d  test    ebx, ebx
0x14003eb5f  js      short loc_14003EB74
0x14003eb61  mov     eax, 0Bh
0x14003eb66  cmp     ax, word ptr [rbp+pvar]
0x14003eb6a  jnz     short loc_14003EB74
0x14003eb6c  cmp     word ptr [rbp+pvar+8], di
0x14003eb70  setnz   r15b
0x14003eb74  mov     rax, qword ptr cs:GUID_NULL.Data1
  ... truncated ...
```
