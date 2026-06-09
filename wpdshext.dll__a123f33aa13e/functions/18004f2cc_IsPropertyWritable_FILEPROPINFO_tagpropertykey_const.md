# _IsPropertyWritable(FILEPROPINFO *,_tagpropertykey const &)

- ea: `0x18004f2cc`
- end: `0x18004fa4b`
- name: `?_IsPropertyWritable@@YAHPEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z`
- size: `1919`
- prototype: `__int64 __fastcall(struct FILEPROPINFO *, const struct _tagpropertykey *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d8e4`
- `0x18004ee88`

## callees

- `0x180014dd0`
- `0x1800285c8`
- `0x180029bac`
- `0x18002ff5c`
- `0x180035590`
- `0x18004f2cc`
- `0x1800628cc`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18004f851`
- `ole32!PropVariantClear` at `0x18004f9d3`
- `ole32!PropVariantClear` at `0x18004f851`
- `ole32!PropVariantClear` at `0x18004f9d3`
- `ole32!CoCreateInstance` at `0x18004f373`
- `ole32!CoCreateInstance` at `0x18004f3d6`
- `ole32!CoCreateInstance` at `0x18004f373`
- `ole32!CoCreateInstance` at `0x18004f3d6`
- `SHELL32!__imp_ILFree` at `0x18004f9c9`
- `SHELL32!__imp_ILFree` at `0x18004f9c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall _IsPropertyWritable(struct FILEPROPINFO *a1, const struct _tagpropertykey *a2)
{
  HRESULT Instance; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rdx
  ITEMIDLIST *v9; // r14
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int i; // edi
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  unsigned int j; // ebx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // ebx
  int v24; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-75h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-71h] BYREF
  __int64 v27; // [rsp+40h] [rbp-69h] BYREF
  __int64 v28; // [rsp+48h] [rbp-61h] BYREF
  __int64 v29; // [rsp+50h] [rbp-59h] BYREF
  __int64 v30; // [rsp+58h] [rbp-51h] BYREF
  __int64 v31; // [rsp+60h] [rbp-49h] BYREF
  __int64 v32; // [rsp+68h] [rbp-41h] BYREF
  struct IPortableDevicePropVariantCollection *ppv; // [rsp+70h] [rbp-39h] BYREF
  LPVOID v34; // [rsp+78h] [rbp-31h] BYREF
  __int64 v35; // [rsp+80h] [rbp-29h] BYREF
  __int64 v36; // [rsp+88h] [rbp-21h] BYREF
  __int64 v37; // [rsp+90h] [rbp-19h] BYREF
  PROPVARIANT pvar; // [rsp+98h] [rbp-11h] BYREF
  GUID fmtid; // [rsp+B0h] [rbp+7h] BYREF
  int v40; // [rsp+C0h] [rbp+17h]
  __int128 v41; // [rsp+C8h] [rbp+1Fh] BYREF

  v36 = 0;
  v35 = 0;
  v31 = 0;
  v37 = 0;
  v34 = 0;
  ppv = 0;
  v32 = 0;
  fmtid = WPD_PROPERTY_NULL.fmtid;
  v40 = 0;
  v41 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( !a1 )
    goto LABEL_100;
  Instance = CoCreateInstance(
               &CLSID_PortableDevicePropVariantCollection,
               0,
               1u,
               &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
               (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 58;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)Instance);
      goto LABEL_100;
    }
    goto LABEL_100;
  }
  Instance = CoCreateInstance(
               &CLSID_PortableDeviceKeyCollection,
               0,
               1u,
               &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
               &v34);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)v34 + 40LL))(v34, &WPD_OBJECT_FORMAT);
    if ( Instance < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 60;
        goto LABEL_6;
      }
      goto LABEL_100;
    }
    v7 = IDA_ILClone(*((_QWORD *)a1 + 7), 0);
    v9 = (ITEMIDLIST *)v7;
    if ( !v7 )
      goto LABEL_100;
    v10 = SHBindToIDList(v7, v8, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v36);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 48LL))(v36, &v37);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 40LL))(v36, &v35);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 32LL))(v35, &v31);
          if ( v10 >= 0 )
          {
            v10 = CollectPersistentUniqueIDs(*((struct _IDA **)a1 + 7), ppv, 0);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, struct IPortableDevicePropVariantCollection *, __int64 *))(*(_QWORD *)v35 + 72LL))(
                      v35,
                      ppv,
                      &v32);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 24LL))(v32, &v26);
                if ( v10 >= 0 )
                {
                  for ( i = 0; i < v26; ++i )
                  {
                    v30 = 0;
                    v29 = 0;
                    v28 = 0;
                    memset(&pvar, 0, sizeof(pvar));
                    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v32 + 32LL))(
                            v32,
                            i,
                            &pvar);
                    if ( v14 < 0 )
                    {
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_87;
                      v16 = 68;
LABEL_97:
                      WPP_SF_d(v15[2], v16, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v14);
                      goto LABEL_87;
                    }
                    v14 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, LPVOID, __int64 *))(*(_QWORD *)v31 + 40LL))(
                            v31,
                            pvar.hVal,
                            v34,
                            &v29);
                    if ( v14 < 0 )
                    {
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_87;
                      v16 = 69;
                      goto LABEL_97;
                    }
                    v14 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v29 + 224LL))(
                            v29,
                            &WPD_OBJECT_FORMAT,
                            &v41);
                    if ( v14 < 0 )
                    {
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_87;
                      v16 = 70;
                      goto LABEL_97;
                    }
                    if ( (*(int (__fastcall **)(__int64, __int128 *, const struct _tagpropertykey *, __int64 *))(*(_QWORD *)v37 + 80LL))(
                           v37,
                           &v41,
                           a2,
                           &v28) < 0 )
                      goto LABEL_54;
                    v14 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v28 + 192LL))(
                            v28,
                            &WPD_PROPERTY_ATTRIBUTE_CAN_WRITE,
                            &v24);
                    if ( v14 < 0 )
                    {
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_87;
                      v16 = 71;
                      goto LABEL_97;
                    }
                    if ( !v24 )
                      goto LABEL_87;
                    if ( v24 != 1 )
                    {
LABEL_54:
                      if ( (*(int (__fastcall **)(__int64, LARGE_INTEGER, const struct _tagpropertykey *, __int64 *))(*(_QWORD *)v31 + 32LL))(
                             v31,
                             pvar.hVal,
                             a2,
                             &v30) < 0 )
                      {
                        v27 = 0;
                        v17 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, __int64 *))(*(_QWORD *)v31 + 24LL))(
                                v31,
                                pvar.hVal,
                                &v27);
                        if ( v17 < 0 )
                        {
                          v20 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                          {
                            goto LABEL_86;
                          }
                          v21 = 73;
                        }
                        else
                        {
                          v25 = 0;
                          v17 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 24LL))(v27, &v25);
                          if ( v17 >= 0 )
                          {
                            v24 = 0;
                            for ( j = 0; ; ++j )
                            {
                              if ( j >= v25 )
                                goto LABEL_70;
                              fmtid = WPD_PROPERTY_NULL.fmtid;
                              v40 = 0;
                              v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *))(*(_QWORD *)v27 + 32LL))(
                                      v27,
                                      j,
                                      &fmtid);
                              if ( v17 < 0 )
                                break;
                              if ( a2->pid == v40 )
                              {
                                v19 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&fmtid.Data1;
                                if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&fmtid.Data1 )
                                  v19 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)fmtid.Data4;
                                if ( !v19 )
                                {
                                  v24 = 1;
LABEL_70:
                                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
                                  goto LABEL_71;
                                }
                              }
                            }
                            v20 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                            {
                              v21 = 75;
                              goto LABEL_85;
                            }
LABEL_86:
                            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
                            goto LABEL_87;
                          }
                          v20 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                          {
                            goto LABEL_86;
                          }
                          v21 = 74;
                        }
LABEL_85:
                        WPP_SF_d(v20[2], v21, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v17);
                        goto LABEL_86;
                      }
                      v14 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v30 + 192LL))(
                              v30,
                              &WPD_PROPERTY_ATTRIBUTE_CAN_WRITE,
                              &v24);
                      if ( v14 < 0 )
                      {
                        v15 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v16 = 72;
                          goto LABEL_97;
                        }
LABEL_87:
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                        goto LABEL_99;
                      }
LABEL_71:
                      PropVariantClear(&pvar);
                      if ( !v24 )
                        goto LABEL_87;
                    }
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                  }
                  v24 = 1;
                  goto LABEL_99;
                }
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                {
LABEL_99:
                  ILFree(v9);
                  goto LABEL_100;
                }
                v12 = 67;
              }
              else
              {
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_99;
                v12 = 66;
              }
            }
            else
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_99;
              v12 = 65;
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_99;
            v12 = 64;
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_99;
          v12 = 63;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_99;
        v12 = 62;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_99;
      v12 = 61;
    }
    WPP_SF_d(v11[2], v12, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v10);
    goto LABEL_99;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v6 = 59;
    goto LABEL_6;
  }
LABEL_100:
  PropVariantClear(&pvar);
  v22 = v24;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  return v22;
}

```

## disassembly

```asm
0x18004f2cc  mov     [rsp-8+arg_10], rbx
0x18004f2d1  mov     [rsp-8+arg_18], rsi
0x18004f2d6  push    rbp
0x18004f2d7  push    rdi
0x18004f2d8  push    r12
0x18004f2da  push    r14
0x18004f2dc  push    r15
0x18004f2de  lea     rbp, [rsp-37h]
0x18004f2e3  sub     rsp, 0E0h
0x18004f2ea  mov     rax, cs:__security_cookie
0x18004f2f1  xor     rax, rsp
0x18004f2f4  mov     [rbp+57h+var_28], rax
0x18004f2f8  mov     rsi, rdx
0x18004f2fb  mov     rbx, rcx
0x18004f2fe  xor     r15d, r15d
0x18004f301  mov     [rbp+57h+var_78], r15
0x18004f305  mov     [rbp+57h+var_80], r15
0x18004f309  mov     [rbp+57h+var_A0], r15
0x18004f30d  mov     [rbp+57h+var_70], r15
0x18004f311  mov     [rbp+57h+var_88], r15
0x18004f315  mov     [rbp+57h+var_90], r15
0x18004f319  mov     [rbp+57h+var_98], r15
0x18004f31d  movups  xmm0, xmmword ptr cs:WPD_PROPERTY_NULL.fmtid.Data1
0x18004f324  movdqu  [rbp+57h+var_50], xmm0
0x18004f329  mov     [rbp+57h+var_40], r15d
0x18004f32d  xorps   xmm0, xmm0
0x18004f330  movups  [rbp+57h+var_38], xmm0
0x18004f334  mov     [rbp+57h+var_C8], r15d
0x18004f338  mov     [rbp+57h+var_CC], r15d
0x18004f33c  mov     [rbp+57h+var_D0], r15d
0x18004f340  xor     eax, eax
0x18004f342  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18004f346  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18004f34a  test    rcx, rcx
0x18004f34d  jz      loc_18004F9CF
0x18004f353  lea     rax, [rbp+57h+var_90]
0x18004f357  mov     [rsp+100h+ppv], rax; ppv
0x18004f35c  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x18004f363  lea     r12d, [r15+1]
0x18004f367  mov     r8d, r12d; dwClsContext
0x18004f36a  xor     edx, edx; pUnkOuter
0x18004f36c  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x18004f373  call    cs:__imp_CoCreateInstance
0x18004f379  test    eax, eax
0x18004f37b  jns     short loc_18004F3BA
0x18004f37d  lea     rdx, WPP_GLOBAL_Control
0x18004f384  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f38b  cmp     rcx, rdx
0x18004f38e  jz      loc_18004F9CF
0x18004f394  test    byte ptr [rcx+1Ch], 2
0x18004f398  jz      loc_18004F9CF
0x18004f39e  lea     edx, [r15+3Ah]
0x18004f3a2  mov     r9d, eax
0x18004f3a5  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004f3ac  mov     rcx, [rcx+10h]
0x18004f3b0  call    WPP_SF_d
0x18004f3b5  jmp     loc_18004F9CF
0x18004f3ba  lea     rax, [rbp+57h+var_88]
0x18004f3be  mov     [rsp+100h+ppv], rax; ppv
0x18004f3c3  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x18004f3ca  mov     r8d, r12d; dwClsContext
0x18004f3cd  xor     edx, edx; pUnkOuter
0x18004f3cf  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x18004f3d6  call    cs:__imp_CoCreateInstance
0x18004f3dc  test    eax, eax
0x18004f3de  jns     short loc_18004F408
0x18004f3e0  lea     rdx, WPP_GLOBAL_Control
0x18004f3e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f3ee  cmp     rcx, rdx
0x18004f3f1  jz      loc_18004F9CF
0x18004f3f7  test    byte ptr [rcx+1Ch], 2
0x18004f3fb  jz      loc_18004F9CF
0x18004f401  mov     edx, 3Bh ; ';'
0x18004f406  jmp     short loc_18004F3A2
0x18004f408  mov     rcx, [rbp+57h+var_88]
0x18004f40c  mov     rax, [rcx]
0x18004f40f  lea     rdx, WPD_OBJECT_FORMAT
0x18004f416  mov     rax, [rax+28h]
0x18004f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f41f  test    eax, eax
0x18004f421  jns     short loc_18004F44E
0x18004f423  lea     rdx, WPP_GLOBAL_Control
0x18004f42a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f431  cmp     rcx, rdx
0x18004f434  jz      loc_18004F9CF
0x18004f43a  test    byte ptr [rcx+1Ch], 2
0x18004f43e  jz      loc_18004F9CF
0x18004f444  mov     edx, 3Ch ; '<'
0x18004f449  jmp     loc_18004F3A2
0x18004f44e  xor     edx, edx
0x18004f450  mov     rcx, [rbx+38h]
0x18004f454  call    IDA_ILClone
0x18004f459  mov     r14, rax
0x18004f45c  test    rax, rax
0x18004f45f  jz      loc_18004F9CF
0x18004f465  lea     r9, [rbp+57h+var_78]
0x18004f469  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x18004f470  mov     rcx, rax
0x18004f473  call    SHBindToIDList
0x18004f478  test    eax, eax
0x18004f47a  jns     short loc_18004F4BA
0x18004f47c  lea     rdx, WPP_GLOBAL_Control
0x18004f483  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f48a  cmp     rcx, rdx
0x18004f48d  jz      loc_18004F9C6
0x18004f493  test    byte ptr [rcx+1Ch], 2
0x18004f497  jz      loc_18004F9C6
0x18004f49d  mov     edx, 3Dh ; '='
0x18004f4a2  mov     r9d, eax
0x18004f4a5  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004f4ac  mov     rcx, [rcx+10h]
0x18004f4b0  call    WPP_SF_d
0x18004f4b5  jmp     loc_18004F9C6
0x18004f4ba  mov     rcx, [rbp+57h+var_78]
0x18004f4be  mov     rax, [rcx]
0x18004f4c1  lea     rdx, [rbp+57h+var_70]
0x18004f4c5  mov     rax, [rax+30h]
0x18004f4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4ce  test    eax, eax
0x18004f4d0  jns     short loc_18004F4FA
0x18004f4d2  lea     rdx, WPP_GLOBAL_Control
0x18004f4d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f4e0  cmp     rcx, rdx
0x18004f4e3  jz      loc_18004F9C6
0x18004f4e9  test    byte ptr [rcx+1Ch], 2
0x18004f4ed  jz      loc_18004F9C6
0x18004f4f3  mov     edx, 3Eh ; '>'
0x18004f4f8  jmp     short loc_18004F4A2
0x18004f4fa  mov     rcx, [rbp+57h+var_78]
0x18004f4fe  mov     rax, [rcx]
0x18004f501  lea     rdx, [rbp+57h+var_80]
0x18004f505  mov     rax, [rax+28h]
0x18004f509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f50e  test    eax, eax
0x18004f510  jns     short loc_18004F53D
0x18004f512  lea     rdx, WPP_GLOBAL_Control
0x18004f519  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f520  cmp     rcx, rdx
0x18004f523  jz      loc_18004F9C6
0x18004f529  test    byte ptr [rcx+1Ch], 2
0x18004f52d  jz      loc_18004F9C6
0x18004f533  mov     edx, 3Fh ; '?'
0x18004f538  jmp     loc_18004F4A2
0x18004f53d  mov     rcx, [rbp+57h+var_80]
0x18004f541  mov     rax, [rcx]
0x18004f544  lea     rdx, [rbp+57h+var_A0]
0x18004f548  mov     rax, [rax+20h]
0x18004f54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f551  test    eax, eax
0x18004f553  jns     short loc_18004F580
0x18004f555  lea     rdx, WPP_GLOBAL_Control
0x18004f55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f563  cmp     rcx, rdx
0x18004f566  jz      loc_18004F9C6
0x18004f56c  test    byte ptr [rcx+1Ch], 2
0x18004f570  jz      loc_18004F9C6
0x18004f576  mov     edx, 40h ; '@'
0x18004f57b  jmp     loc_18004F4A2
0x18004f580  xor     r8d, r8d; int
0x18004f583  mov     rdx, [rbp+57h+var_90]; struct IPortableDevicePropVariantCollection *
0x18004f587  mov     rcx, [rbx+38h]; struct _IDA *
0x18004f58b  call    ?CollectPersistentUniqueIDs@@YAJPEAU_IDA@@PEAUIPortableDevicePropVariantCollection@@H@Z; CollectPersistentUniqueIDs(_IDA *,IPortableDevicePropVariantCollection *,int)
0x18004f590  test    eax, eax
0x18004f592  jns     short loc_18004F5BF
0x18004f594  lea     rdx, WPP_GLOBAL_Control
0x18004f59b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f5a2  cmp     rcx, rdx
0x18004f5a5  jz      loc_18004F9C6
0x18004f5ab  test    byte ptr [rcx+1Ch], 2
0x18004f5af  jz      loc_18004F9C6
0x18004f5b5  mov     edx, 41h ; 'A'
0x18004f5ba  jmp     loc_18004F4A2
0x18004f5bf  mov     rcx, [rbp+57h+var_80]
0x18004f5c3  mov     rax, [rcx]
0x18004f5c6  lea     r8, [rbp+57h+var_98]
0x18004f5ca  mov     rdx, [rbp+57h+var_90]
0x18004f5ce  mov     rax, [rax+48h]
0x18004f5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5d7  test    eax, eax
0x18004f5d9  jns     short loc_18004F606
0x18004f5db  lea     rdx, WPP_GLOBAL_Control
0x18004f5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f5e9  cmp     rcx, rdx
0x18004f5ec  jz      loc_18004F9C6
0x18004f5f2  test    byte ptr [rcx+1Ch], 2
0x18004f5f6  jz      loc_18004F9C6
0x18004f5fc  mov     edx, 42h ; 'B'
0x18004f601  jmp     loc_18004F4A2
0x18004f606  mov     rcx, [rbp+57h+var_98]
0x18004f60a  mov     rax, [rcx]
0x18004f60d  lea     rdx, [rbp+57h+var_C8]
0x18004f611  mov     rax, [rax+18h]
0x18004f615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f61a  test    eax, eax
0x18004f61c  jns     short loc_18004F649
0x18004f61e  lea     rdx, WPP_GLOBAL_Control
0x18004f625  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f62c  cmp     rcx, rdx
0x18004f62f  jz      loc_18004F9C6
0x18004f635  test    byte ptr [rcx+1Ch], 2
0x18004f639  jz      loc_18004F9C6
0x18004f63f  mov     edx, 43h ; 'C'
0x18004f644  jmp     loc_18004F4A2
0x18004f649  mov     edi, r15d
0x18004f64c  cmp     edi, [rbp+57h+var_C8]
0x18004f64f  jnb     loc_18004F9C2
0x18004f655  mov     [rbp+57h+var_A8], r15
0x18004f659  mov     [rbp+57h+var_B0], r15
0x18004f65d  mov     [rbp+57h+var_B8], r15
0x18004f661  xorps   xmm0, xmm0
0x18004f664  xor     eax, eax
0x18004f666  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18004f66a  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18004f66e  mov     rcx, [rbp+57h+var_98]
0x18004f672  mov     rax, [rcx]
0x18004f675  lea     r8, [rbp+57h+pvar]
0x18004f679  mov     edx, edi
0x18004f67b  mov     rax, [rax+20h]
0x18004f67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f684  test    eax, eax
0x18004f686  js      loc_18004F98C
0x18004f68c  mov     rcx, [rbp+57h+var_A0]
0x18004f690  mov     rax, [rcx]
0x18004f693  lea     r9, [rbp+57h+var_B0]
0x18004f697  mov     r8, [rbp+57h+var_88]
0x18004f69b  mov     rdx, qword ptr [rbp+57h+pvar+8]
0x18004f69f  mov     rax, [rax+28h]
0x18004f6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6a8  test    eax, eax
0x18004f6aa  js      loc_18004F96C
0x18004f6b0  mov     rcx, [rbp+57h+var_B0]
0x18004f6b4  mov     rax, [rcx]
0x18004f6b7  lea     r8, [rbp+57h+var_38]
0x18004f6bb  lea     rdx, WPD_OBJECT_FORMAT
0x18004f6c2  mov     rax, [rax+0E0h]
0x18004f6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6ce  test    eax, eax
0x18004f6d0  js      loc_18004F94C
0x18004f6d6  mov     rcx, [rbp+57h+var_70]
0x18004f6da  mov     rax, [rcx]
0x18004f6dd  lea     r9, [rbp+57h+var_B8]
0x18004f6e1  mov     r8, rsi
0x18004f6e4  lea     rdx, [rbp+57h+var_38]
0x18004f6e8  mov     rax, [rax+50h]
0x18004f6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6f1  test    eax, eax
0x18004f6f3  js      short loc_18004F72F
0x18004f6f5  mov     rcx, [rbp+57h+var_B8]
0x18004f6f9  mov     rax, [rcx]
0x18004f6fc  lea     r8, [rbp+57h+var_D0]
0x18004f700  lea     rdx, WPD_PROPERTY_ATTRIBUTE_CAN_WRITE
0x18004f707  mov     rax, [rax+0C0h]
0x18004f70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f713  test    eax, eax
0x18004f715  js      loc_18004F886
0x18004f71b  mov     eax, [rbp+57h+var_D0]
0x18004f71e  test    eax, eax
0x18004f720  jz      loc_18004F92D
0x18004f726  cmp     eax, r12d
0x18004f729  jz      loc_18004F861
0x18004f72f  mov     rcx, [rbp+57h+var_A0]
0x18004f733  mov     rax, [rcx]
0x18004f736  lea     r9, [rbp+57h+var_A8]
0x18004f73a  mov     r8, rsi
0x18004f73d  mov     rdx, qword ptr [rbp+57h+pvar+8]
0x18004f741  mov     rax, [rax+20h]
0x18004f745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f74a  test    eax, eax
0x18004f74c  js      short loc_18004F79F
0x18004f74e  mov     rcx, [rbp+57h+var_A8]
0x18004f752  mov     rax, [rcx]
0x18004f755  lea     r8, [rbp+57h+var_D0]
0x18004f759  lea     rdx, WPD_PROPERTY_ATTRIBUTE_CAN_WRITE
0x18004f760  mov     rax, [rax+0C0h]
0x18004f767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f76c  test    eax, eax
0x18004f76e  jns     loc_18004F84D
0x18004f774  lea     rdx, WPP_GLOBAL_Control
0x18004f77b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f782  cmp     rcx, rdx
0x18004f785  jz      loc_18004F92D
0x18004f78b  test    byte ptr [rcx+1Ch], 2
0x18004f78f  jz      loc_18004F92D
0x18004f795  mov     edx, 48h ; 'H'
0x18004f79a  jmp     loc_18004F9AA
0x18004f79f  mov     [rbp+57h+var_C0], r15
0x18004f7a3  mov     rcx, [rbp+57h+var_A0]
0x18004f7a7  mov     rax, [rcx]
0x18004f7aa  lea     r8, [rbp+57h+var_C0]
0x18004f7ae  mov     rdx, qword ptr [rbp+57h+pvar+8]
0x18004f7b2  mov     rax, [rax+18h]
0x18004f7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7bb  test    eax, eax
0x18004f7bd  js      loc_18004F8F1
0x18004f7c3  mov     [rbp+57h+var_CC], r15d
0x18004f7c7  mov     rcx, [rbp+57h+var_C0]
0x18004f7cb  mov     rax, [rcx]
0x18004f7ce  lea     rdx, [rbp+57h+var_CC]
0x18004f7d2  mov     rax, [rax+18h]
0x18004f7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
