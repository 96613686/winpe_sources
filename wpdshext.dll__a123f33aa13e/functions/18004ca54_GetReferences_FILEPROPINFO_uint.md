# _GetReferences(FILEPROPINFO *,uint)

- ea: `0x18004ca54`
- end: `0x18004cf32`
- name: `?_GetReferences@@YAJPEAUFILEPROPINFO@@I@Z`
- size: `1246`
- prototype: `__int64 __fastcall(struct FILEPROPINFO *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c414`

## callees

- `0x180004110`
- `0x180014dd0`
- `0x180016260`
- `0x1800177dc`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18004ca54`
- `0x1800628cc`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18004ce90`
- `ole32!PropVariantClear` at `0x18004ce90`
- `ole32!CoCreateInstance` at `0x18004cb27`
- `ole32!CoCreateInstance` at `0x18004cb85`
- `ole32!CoCreateInstance` at `0x18004cb27`
- `ole32!CoCreateInstance` at `0x18004cb85`
- `SHELL32!__imp_ILFindLastID` at `0x18004cbd7`
- `SHELL32!__imp_ILFindLastID` at `0x18004cbd7`
- `SHELL32!__imp_ILFree` at `0x18004ce75`
- `SHELL32!__imp_ILFree` at `0x18004ce85`
- `SHELL32!__imp_ILFree` at `0x18004ce75`
- `SHELL32!__imp_ILFree` at `0x18004ce85`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _GetReferences(struct FILEPROPINFO *a1)
{
  _DWORD *v2; // rax
  int v3; // ebx
  HRESULT v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  ITEMIDLIST *v7; // r14
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, LPITEMIDLIST, __int64 *, _QWORD); // rbx
  LPITEMIDLIST ID; // rax
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  ITEMIDLIST *v16; // rdi
  int PortableDeviceProperties; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  LPVOID v21; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  struct IPortableDeviceProperties *v25; // [rsp+50h] [rbp-B0h] BYREF
  struct IPortableDevice *v26; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v29[264]; // [rsp+80h] [rbp-80h] BYREF

  v26 = 0;
  v28 = 0;
  v25 = 0;
  ppv = 0;
  v24 = 0;
  v21 = 0;
  v23 = 0;
  memset_0(v29, 0, 0x208u);
  memset(&pvar, 0, sizeof(pvar));
  v2 = (_DWORD *)*((_QWORD *)a1 + 7);
  if ( !v2 || !*((_QWORD *)a1 + 1) || !*v2 )
    goto LABEL_2;
  v4 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &ppv);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 76;
LABEL_9:
      WPP_SF_d(v5[2], v6, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v4);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  v4 = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &v21);
  v3 = v4;
  if ( v4 >= 0 )
  {
    v7 = (ITEMIDLIST *)IDA_ILClone(*((_QWORD *)a1 + 7), 0);
    if ( v7 )
    {
      v8 = *((_QWORD *)a1 + 1);
      v9 = *(__int64 (__fastcall **)(__int64, LPITEMIDLIST, __int64 *, _QWORD))(*(_QWORD *)v8 + 32LL);
      ID = ILFindLastID(v7);
      v11 = v9(v8, ID, &v24, 0);
      v3 = v11;
      if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v13 = 78;
        goto LABEL_19;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v24 + 40LL))(
              v24,
              &WPD_OBJECT_ID,
              &pvar);
      v3 = v11;
      if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v13 = 79;
        goto LABEL_19;
      }
      if ( pvar.vt != 31 || !pvar.hVal.QuadPart )
      {
        v3 = -2147418113;
        goto LABEL_60;
      }
      v11 = StringCchCopyW(v29, 0x104u, pvar.bstrVal);
      v3 = v11;
      if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v13 = 80;
LABEL_19:
        WPP_SF_d(v12[2], v13, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v11);
LABEL_60:
        ILFree(v7);
        goto LABEL_61;
      }
      v14 = IDA_ILClone(*((_QWORD *)a1 + 7), 0);
      v16 = (ITEMIDLIST *)v14;
      if ( !v14 )
      {
        v3 = -2147024882;
        goto LABEL_60;
      }
      PortableDeviceProperties = SHBindToIDList(v14, v15, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v26);
      v3 = PortableDeviceProperties;
      if ( PortableDeviceProperties >= 0 )
      {
        PortableDeviceProperties = GetPortableDeviceProperties(v26, &v25);
        v3 = PortableDeviceProperties;
        if ( PortableDeviceProperties >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_REFERENCES);
          PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, unsigned __int16 *, LPVOID, LPVOID *))v25->lpVtbl->GetValues)(
                                       v25,
                                       v29,
                                       ppv,
                                       &v21);
          v3 = PortableDeviceProperties;
          if ( PortableDeviceProperties >= 0 )
          {
            PortableDeviceProperties = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v21 + 48LL))(
                                         v21,
                                         &WPD_OBJECT_REFERENCES,
                                         &pvar);
            v3 = PortableDeviceProperties;
            if ( PortableDeviceProperties >= 0 )
            {
              if ( pvar.vt != 13 || !pvar.hVal.QuadPart )
              {
                v3 = -2147418113;
                goto LABEL_58;
              }
              PortableDeviceProperties = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, struct IUnknown **))pvar.hVal.QuadPart)(
                                           pvar.hVal,
                                           &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
                                           &v23);
              v3 = PortableDeviceProperties;
              if ( PortableDeviceProperties >= 0 )
              {
                if ( *((struct IUnknown **)a1 + 78) != v23 )
                  ATL::AtlComPtrAssign((struct IUnknown **)a1 + 78, v23);
                goto LABEL_58;
              }
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
LABEL_58:
                ILFree(v16);
                goto LABEL_60;
              }
              v19 = 85;
            }
            else
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_58;
              v19 = 84;
            }
          }
          else
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_58;
            v19 = 83;
          }
        }
        else
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_58;
          v19 = 82;
        }
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_58;
        v19 = 81;
      }
      WPP_SF_d(v18[2], v19, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)PortableDeviceProperties);
      goto LABEL_58;
    }
LABEL_2:
    v3 = -2147024809;
    goto LABEL_61;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v6 = 77;
    goto LABEL_9;
  }
LABEL_61:
  PropVariantClear(&pvar);
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v3);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004ca54  push    rbp
0x18004ca56  push    rbx
0x18004ca57  push    rsi
0x18004ca58  push    rdi
0x18004ca59  push    r13
0x18004ca5b  push    r14
0x18004ca5d  lea     rbp, [rsp-1A8h]
0x18004ca65  sub     rsp, 2A8h
0x18004ca6c  mov     rax, cs:__security_cookie
0x18004ca73  xor     rax, rsp
0x18004ca76  mov     [rbp+1D0h+var_40], rax
0x18004ca7d  mov     rsi, rcx
0x18004ca80  mov     [rsp+2D0h+var_278], 0
0x18004ca89  mov     [rsp+2D0h+var_258], 0
0x18004ca92  mov     [rsp+2D0h+var_280], 0
0x18004ca9b  mov     [rsp+2D0h+var_298], 0
0x18004caa4  mov     [rsp+2D0h+var_288], 0
0x18004caad  mov     [rsp+2D0h+var_2A0], 0
0x18004cab6  mov     [rsp+2D0h+var_290], 0
0x18004cabf  xor     edx, edx; Val
0x18004cac1  mov     r8d, 208h; Size
0x18004cac7  lea     rcx, [rbp+1D0h+var_250]; void *
0x18004cacb  call    memset_0
0x18004cad0  xorps   xmm0, xmm0
0x18004cad3  xor     eax, eax
0x18004cad5  movups  xmmword ptr [rsp+2D0h+pvar], xmm0
0x18004cada  mov     qword ptr [rsp+2D0h+pvar+10h], rax
0x18004cadf  mov     rax, [rsi+38h]
0x18004cae3  lea     r13, WPP_GLOBAL_Control
0x18004caea  test    rax, rax
0x18004caed  jnz     short loc_18004CAF9
0x18004caef  mov     ebx, 80070057h
0x18004caf4  jmp     loc_18004CE8B
0x18004caf9  cmp     qword ptr [rsi+8], 0
0x18004cafe  jz      short loc_18004CAEF
0x18004cb00  cmp     dword ptr [rax], 0
0x18004cb03  jbe     short loc_18004CAEF
0x18004cb05  lea     rax, [rsp+2D0h+var_298]
0x18004cb0a  mov     [rsp+2D0h+ppv], rax; ppv
0x18004cb0f  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x18004cb16  mov     edi, 1
0x18004cb1b  mov     r8d, edi; dwClsContext
0x18004cb1e  xor     edx, edx; pUnkOuter
0x18004cb20  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x18004cb27  call    cs:__imp_CoCreateInstance
0x18004cb2d  mov     ebx, eax
0x18004cb2f  test    eax, eax
0x18004cb31  jns     short loc_18004CB68
0x18004cb33  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb3a  cmp     rcx, r13
0x18004cb3d  jz      loc_18004CE8B
0x18004cb43  test    byte ptr [rcx+1Ch], 2
0x18004cb47  jz      loc_18004CE8B
0x18004cb4d  lea     edx, [rdi+4Bh]
0x18004cb50  mov     r9d, eax
0x18004cb53  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004cb5a  mov     rcx, [rcx+10h]
0x18004cb5e  call    WPP_SF_d
0x18004cb63  jmp     loc_18004CE8B
0x18004cb68  lea     rax, [rsp+2D0h+var_2A0]
0x18004cb6d  mov     [rsp+2D0h+ppv], rax; ppv
0x18004cb72  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x18004cb79  mov     r8d, edi; dwClsContext
0x18004cb7c  xor     edx, edx; pUnkOuter
0x18004cb7e  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x18004cb85  call    cs:__imp_CoCreateInstance
0x18004cb8b  mov     ebx, eax
0x18004cb8d  test    eax, eax
0x18004cb8f  jns     short loc_18004CBB2
0x18004cb91  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb98  cmp     rcx, r13
0x18004cb9b  jz      loc_18004CE8B
0x18004cba1  test    byte ptr [rcx+1Ch], 2
0x18004cba5  jz      loc_18004CE8B
0x18004cbab  mov     edx, 4Dh ; 'M'
0x18004cbb0  jmp     short loc_18004CB50
0x18004cbb2  xor     edx, edx
0x18004cbb4  mov     rcx, [rsi+38h]
0x18004cbb8  call    IDA_ILClone
0x18004cbbd  mov     r14, rax
0x18004cbc0  test    rax, rax
0x18004cbc3  jz      loc_18004CAEF
0x18004cbc9  mov     rdi, [rsi+8]
0x18004cbcd  mov     rax, [rdi]
0x18004cbd0  mov     rbx, [rax+20h]
0x18004cbd4  mov     rcx, r14; pidl
0x18004cbd7  call    cs:__imp_ILFindLastID
0x18004cbdd  xor     r9d, r9d
0x18004cbe0  lea     r8, [rsp+2D0h+var_288]
0x18004cbe5  mov     rdx, rax
0x18004cbe8  mov     rcx, rdi
0x18004cbeb  mov     rax, rbx
0x18004cbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbf3  mov     ebx, eax
0x18004cbf5  test    eax, eax
0x18004cbf7  jns     short loc_18004CC30
0x18004cbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc00  cmp     rcx, r13
0x18004cc03  jz      loc_18004CE82
0x18004cc09  test    byte ptr [rcx+1Ch], 2
0x18004cc0d  jz      loc_18004CE82
0x18004cc13  mov     edx, 4Eh ; 'N'
0x18004cc18  mov     r9d, eax
0x18004cc1b  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004cc22  mov     rcx, [rcx+10h]
0x18004cc26  call    WPP_SF_d
0x18004cc2b  jmp     loc_18004CE82
0x18004cc30  mov     rcx, [rsp+2D0h+var_288]
0x18004cc35  mov     rax, [rcx]
0x18004cc38  lea     r8, [rsp+2D0h+pvar]
0x18004cc3d  lea     rdx, WPD_OBJECT_ID
0x18004cc44  mov     rax, [rax+28h]
0x18004cc48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc4d  mov     ebx, eax
0x18004cc4f  test    eax, eax
0x18004cc51  jns     short loc_18004CC74
0x18004cc53  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc5a  cmp     rcx, r13
0x18004cc5d  jz      loc_18004CE82
0x18004cc63  test    byte ptr [rcx+1Ch], 2
0x18004cc67  jz      loc_18004CE82
0x18004cc6d  mov     edx, 4Fh ; 'O'
0x18004cc72  jmp     short loc_18004CC18
0x18004cc74  cmp     word ptr [rsp+2D0h+pvar], 1Fh
0x18004cc7a  jnz     loc_18004CE7D
0x18004cc80  mov     r8, qword ptr [rsp+2D0h+pvar+8]; unsigned __int16 *
0x18004cc85  test    r8, r8
0x18004cc88  jz      loc_18004CE7D
0x18004cc8e  mov     edx, 104h; unsigned __int64
0x18004cc93  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18004cc97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004cc9c  mov     ebx, eax
0x18004cc9e  test    eax, eax
0x18004cca0  jns     short loc_18004CCC6
0x18004cca2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cca9  cmp     rcx, r13
0x18004ccac  jz      loc_18004CE82
0x18004ccb2  test    byte ptr [rcx+1Ch], 2
0x18004ccb6  jz      loc_18004CE82
0x18004ccbc  mov     edx, 50h ; 'P'
0x18004ccc1  jmp     loc_18004CC18
0x18004ccc6  xor     edx, edx
0x18004ccc8  mov     rcx, [rsi+38h]
0x18004cccc  call    IDA_ILClone
0x18004ccd1  mov     rdi, rax
0x18004ccd4  test    rax, rax
0x18004ccd7  jnz     short loc_18004CCE3
0x18004ccd9  mov     ebx, 8007000Eh
0x18004ccde  jmp     loc_18004CE82
0x18004cce3  lea     r9, [rsp+2D0h+var_278]
0x18004cce8  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x18004ccef  mov     rcx, rdi
0x18004ccf2  call    SHBindToIDList
0x18004ccf7  mov     ebx, eax
0x18004ccf9  test    eax, eax
0x18004ccfb  jns     short loc_18004CD34
0x18004ccfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd04  cmp     rcx, r13
0x18004cd07  jz      loc_18004CE72
0x18004cd0d  test    byte ptr [rcx+1Ch], 2
0x18004cd11  jz      loc_18004CE72
0x18004cd17  mov     edx, 51h ; 'Q'
0x18004cd1c  mov     r9d, eax
0x18004cd1f  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004cd26  mov     rcx, [rcx+10h]
0x18004cd2a  call    WPP_SF_d
0x18004cd2f  jmp     loc_18004CE72
0x18004cd34  lea     rdx, [rsp+2D0h+var_280]; struct IPortableDeviceProperties **
0x18004cd39  mov     rcx, [rsp+2D0h+var_278]; struct IPortableDevice *
0x18004cd3e  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x18004cd43  mov     ebx, eax
0x18004cd45  test    eax, eax
0x18004cd47  jns     short loc_18004CD6A
0x18004cd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd50  cmp     rcx, r13
0x18004cd53  jz      loc_18004CE72
0x18004cd59  test    byte ptr [rcx+1Ch], 2
0x18004cd5d  jz      loc_18004CE72
0x18004cd63  mov     edx, 52h ; 'R'
0x18004cd68  jmp     short loc_18004CD1C
0x18004cd6a  mov     rcx, [rsp+2D0h+var_298]
0x18004cd6f  mov     rax, [rcx]
0x18004cd72  lea     rdx, WPD_OBJECT_REFERENCES
0x18004cd79  mov     rax, [rax+28h]
0x18004cd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd82  mov     rcx, [rsp+2D0h+var_280]
0x18004cd87  mov     rax, [rcx]
0x18004cd8a  lea     r9, [rsp+2D0h+var_2A0]
0x18004cd8f  mov     r8, [rsp+2D0h+var_298]
0x18004cd94  lea     rdx, [rbp+1D0h+var_250]
0x18004cd98  mov     rax, [rax+28h]
0x18004cd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cda1  mov     ebx, eax
0x18004cda3  test    eax, eax
0x18004cda5  jns     short loc_18004CDCB
0x18004cda7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cdae  cmp     rcx, r13
0x18004cdb1  jz      loc_18004CE72
0x18004cdb7  test    byte ptr [rcx+1Ch], 2
0x18004cdbb  jz      loc_18004CE72
0x18004cdc1  mov     edx, 53h ; 'S'
0x18004cdc6  jmp     loc_18004CD1C
0x18004cdcb  mov     rcx, [rsp+2D0h+var_2A0]
0x18004cdd0  mov     rax, [rcx]
0x18004cdd3  lea     r8, [rsp+2D0h+pvar]
0x18004cdd8  lea     rdx, WPD_OBJECT_REFERENCES
0x18004cddf  mov     rax, [rax+30h]
0x18004cde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cde8  mov     ebx, eax
0x18004cdea  test    eax, eax
0x18004cdec  jns     short loc_18004CE0A
0x18004cdee  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cdf5  cmp     rcx, r13
0x18004cdf8  jz      short loc_18004CE72
0x18004cdfa  test    byte ptr [rcx+1Ch], 2
0x18004cdfe  jz      short loc_18004CE72
0x18004ce00  mov     edx, 54h ; 'T'
0x18004ce05  jmp     loc_18004CD1C
0x18004ce0a  cmp     word ptr [rsp+2D0h+pvar], 0Dh
0x18004ce10  jnz     short loc_18004CE6D
0x18004ce12  mov     rcx, qword ptr [rsp+2D0h+pvar+8]
0x18004ce17  test    rcx, rcx
0x18004ce1a  jz      short loc_18004CE6D
0x18004ce1c  mov     rax, [rcx]
0x18004ce1f  lea     r8, [rsp+2D0h+var_290]
0x18004ce24  lea     rdx, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3
0x18004ce2b  mov     rax, [rax]
0x18004ce2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce33  mov     ebx, eax
0x18004ce35  test    eax, eax
0x18004ce37  jns     short loc_18004CE55
0x18004ce39  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce40  cmp     rcx, r13
0x18004ce43  jz      short loc_18004CE72
0x18004ce45  test    byte ptr [rcx+1Ch], 2
0x18004ce49  jz      short loc_18004CE72
0x18004ce4b  mov     edx, 55h ; 'U'
0x18004ce50  jmp     loc_18004CD1C
0x18004ce55  lea     rcx, [rsi+270h]; struct IUnknown **
0x18004ce5c  mov     rdx, [rsp+2D0h+var_290]; struct IUnknown *
0x18004ce61  cmp     [rcx], rdx
0x18004ce64  jz      short loc_18004CE72
0x18004ce66  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004ce6b  jmp     short loc_18004CE72
0x18004ce6d  mov     ebx, 8000FFFFh
0x18004ce72  mov     rcx, rdi; pidl
0x18004ce75  call    cs:__imp_ILFree
0x18004ce7b  jmp     short loc_18004CE82
0x18004ce7d  mov     ebx, 8000FFFFh
0x18004ce82  mov     rcx, r14; pidl
0x18004ce85  call    cs:__imp_ILFree
0x18004ce8b  lea     rcx, [rsp+2D0h+pvar]; pvar
0x18004ce90  call    cs:__imp_PropVariantClear
0x18004ce96  test    ebx, ebx
0x18004ce98  jns     short loc_18004CEC5
0x18004ce9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cea1  cmp     rcx, r13
0x18004cea4  jz      short loc_18004CEC5
0x18004cea6  test    byte ptr [rcx+1Ch], 2
0x18004ceaa  jz      short loc_18004CEC5
0x18004ceac  mov     edx, 56h ; 'V'
0x18004ceb1  mov     r9d, ebx
0x18004ceb4  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004cebb  mov     rcx, [rcx+10h]
0x18004cebf  call    WPP_SF_d
0x18004cec4  nop
0x18004cec5  lea     rcx, [rsp+2D0h+var_290]
0x18004ceca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004cecf  nop
0x18004ced0  lea     rcx, [rsp+2D0h+var_2A0]
0x18004ced5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ceda  nop
0x18004cedb  lea     rcx, [rsp+2D0h+var_288]
0x18004cee0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004cee5  nop
0x18004cee6  lea     rcx, [rsp+2D0h+var_298]
0x18004ceeb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004cef0  nop
0x18004cef1  lea     rcx, [rsp+2D0h+var_280]
0x18004cef6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004cefb  nop
0x18004cefc  lea     rcx, [rsp+2D0h+var_258]
0x18004cf01  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004cf06  nop
0x18004cf07  lea     rcx, [rsp+2D0h+var_278]
0x18004cf0c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004cf11  mov     eax, ebx
0x18004cf13  mov     rcx, [rbp+1D0h+var_40]
0x18004cf1a  xor     rcx, rsp; StackCookie
0x18004cf1d  call    __security_check_cookie
0x18004cf22  add     rsp, 2A8h
0x18004cf29  pop     r14
0x18004cf2b  pop     r13
0x18004cf2d  pop     rdi
0x18004cf2e  pop     rsi
0x18004cf2f  pop     rbx
0x18004cf30  pop     rbp
0x18004cf31  retn
```
