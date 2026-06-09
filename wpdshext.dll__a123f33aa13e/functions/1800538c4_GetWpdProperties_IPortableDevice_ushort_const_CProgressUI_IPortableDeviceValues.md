# _GetWpdProperties(IPortableDevice *,ushort const *,CProgressUI *,IPortableDeviceValues * *)

- ea: `0x1800538c4`
- end: `0x180053f2e`
- name: `?_GetWpdProperties@@YAJPEAUIPortableDevice@@PEBGPEAVCProgressUI@@PEAPEAUIPortableDeviceValues@@@Z`
- size: `1642`
- prototype: `__int64 __fastcall(struct IPortableDevice *, const unsigned __int16 *, struct CProgressUI *, struct IPortableDeviceValues **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180051ee0`

## callees

- `0x180016260`
- `0x1800177dc`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x18003912c`
- `0x1800538c4`
- `0x180054524`
- `0x1800545c8`
- `0x180054740`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800539e1`
- `KERNEL32!Sleep` at `0x180053b2b`
- `KERNEL32!Sleep` at `0x180053e23`
- `KERNEL32!Sleep` at `0x1800539e1`
- `KERNEL32!Sleep` at `0x180053b2b`
- `KERNEL32!Sleep` at `0x180053e23`
- `ole32!PropVariantClear` at `0x180053b7a`
- `ole32!PropVariantClear` at `0x180053c35`
- `ole32!PropVariantClear` at `0x180053b7a`
- `ole32!PropVariantClear` at `0x180053c35`
- `ole32!CoCreateInstance` at `0x180053a3a`
- `ole32!CoCreateInstance` at `0x180053a3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _GetWpdProperties(
        struct IPortableDevice *a1,
        const unsigned __int16 *a2,
        struct CProgressUI *a3,
        struct IPortableDeviceValues **a4)
{
  LONG PortableDeviceProperties; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // r14d
  int v13; // ebx
  HRESULT v14; // eax
  struct IPortableDeviceProperties *v15; // rbx
  int v16; // r15d
  int v17; // r14d
  unsigned int i; // r14d
  CGuidToString *v20; // rax
  int v21; // edx
  int v22; // r8d
  int v23; // r15d
  int v24; // r14d
  struct IUnknown *v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  struct IPortableDeviceProperties *v28; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-A0h] BYREF
  GUID Buf2; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+88h] [rbp-78h]
  OLECHAR sz[64]; // [rsp+90h] [rbp-70h] BYREF

  v26 = 0;
  Buf2 = 0;
  v31 = 0;
  v28 = 0;
  ppv = 0;
  v25 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( !a1 || !a2 )
  {
    PortableDeviceProperties = -2147024809;
    goto LABEL_55;
  }
  if ( !a4 )
  {
    PortableDeviceProperties = -2147467261;
    goto LABEL_55;
  }
  if ( a3 )
  {
    v12 = 0;
    v13 = 0;
    while ( !*((_DWORD *)a3 + 26) )
    {
      PortableDeviceProperties = GetPortableDeviceProperties(a1, &v28);
      if ( PortableDeviceProperties != -2147024726 )
        goto LABEL_23;
      if ( !v12 )
      {
        v12 = 1;
        v13 = 1;
        CProgressUI::_StartMarquee(a3);
      }
      if ( *((_DWORD *)a3 + 26) )
        break;
      Sleep(0x5DCu);
    }
    PortableDeviceProperties = -2147023673;
LABEL_23:
    if ( v13 )
      CProgressUI::_StopMarquee(a3);
    if ( *((_DWORD *)a3 + 26) )
    {
      PortableDeviceProperties = -2147023673;
      goto LABEL_9;
    }
  }
  else
  {
    PortableDeviceProperties = GetPortableDeviceProperties(a1, &v28);
  }
  if ( PortableDeviceProperties < 0 )
  {
LABEL_9:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 96;
LABEL_12:
      v11 = (unsigned int)PortableDeviceProperties;
LABEL_13:
      WPP_SF_d(v9[2], v10, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v11);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  v14 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &ppv);
  PortableDeviceProperties = v14;
  if ( v14 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_55;
    v10 = 97;
    goto LABEL_31;
  }
  v15 = v28;
  if ( a3 )
  {
    v16 = 0;
    v17 = 0;
    while ( !*((_DWORD *)a3 + 26) )
    {
      PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, _QWORD, struct IUnknown **))v15->lpVtbl->GetValues)(
                                   v15,
                                   a2,
                                   0,
                                   &v25);
      if ( PortableDeviceProperties != -2147024726 )
        goto LABEL_49;
      if ( v25 )
        ATL::AtlComPtrAssign(&v25, 0);
      if ( !v16 )
      {
        v16 = 1;
        v17 = 1;
        CProgressUI::_StartMarquee(a3);
      }
      if ( *((_DWORD *)a3 + 26) )
        break;
      Sleep(0x5DCu);
    }
    PortableDeviceProperties = -2147023673;
LABEL_49:
    if ( v17 )
      CProgressUI::_StopMarquee(a3);
    if ( *((_DWORD *)a3 + 26) )
    {
      PortableDeviceProperties = -2147023673;
      goto LABEL_35;
    }
  }
  else
  {
    PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, _QWORD, struct IUnknown **))v28->lpVtbl->GetValues)(
                                 v28,
                                 a2,
                                 0,
                                 &v25);
  }
  if ( PortableDeviceProperties >= 0 )
  {
    while ( 2 )
    {
      if ( !*a4 )
      {
        PortableDeviceProperties = -2147418113;
        goto LABEL_55;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 48LL))(ppv);
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))v25->lpVtbl[1].QueryInterface)(v25, &v26);
      PortableDeviceProperties = v14;
      if ( v14 >= 0 )
      {
        for ( i = 0; i < v26; ++i )
        {
          PropVariantClear(&pvar);
          v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, PROPVARIANT *))v25->lpVtbl[1].AddRef)(
                  v25,
                  i,
                  &Buf2,
                  &pvar);
          PortableDeviceProperties = v14;
          if ( v14 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v10 = 100;
              goto LABEL_31;
            }
            goto LABEL_55;
          }
          if ( pvar.vt )
          {
            if ( pvar.vt == 10 )
            {
              PortableDeviceProperties = pvar.lVal;
              if ( pvar.lVal == -2147024726 )
              {
                (*(void (__fastcall **)(LPVOID, GUID *))(*(_QWORD *)ppv + 40LL))(ppv, &Buf2);
              }
              else if ( (v31 == 6 && !memcmp_0(&WPD_OBJECT_FORMAT, &Buf2, 0x10u)
                      || v31 == 7 && !memcmp_0(&WPD_OBJECT_CONTENT_TYPE, &Buf2, 0x10u))
                     && PortableDeviceProperties < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v20 = CGuidToString::CGuidToString(sz, &Buf2);
                  WPP_SF_DSdd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v21,
                    v22,
                    PortableDeviceProperties,
                    (__int64)v20,
                    v31,
                    PortableDeviceProperties);
                }
                goto LABEL_55;
              }
            }
            else
            {
              v14 = ((__int64 (__fastcall *)(_QWORD, GUID *, PROPVARIANT *))(*a4)->lpVtbl->SetValue)(*a4, &Buf2, &pvar);
              PortableDeviceProperties = v14;
              if ( v14 < 0 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v10 = 102;
                  goto LABEL_31;
                }
                goto LABEL_55;
              }
            }
          }
        }
        v14 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 24LL))(ppv, &v26);
        PortableDeviceProperties = v14;
        if ( v14 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v10 = 103;
            goto LABEL_31;
          }
        }
        else if ( v26 && a3 )
        {
          if ( v25 )
            ATL::AtlComPtrAssign(&v25, 0);
          v23 = 0;
          v24 = 0;
          while ( !*((_DWORD *)a3 + 26) )
          {
            PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, LPVOID, struct IUnknown **))v15->lpVtbl->GetValues)(
                                         v15,
                                         a2,
                                         ppv,
                                         &v25);
            if ( PortableDeviceProperties != -2147024726 )
              goto LABEL_94;
            if ( v25 )
              ATL::AtlComPtrAssign(&v25, 0);
            if ( !v23 )
            {
              v23 = 1;
              v24 = 1;
              CProgressUI::_StartMarquee(a3);
            }
            if ( *((_DWORD *)a3 + 26) )
              break;
            Sleep(0x5DCu);
          }
          PortableDeviceProperties = -2147023673;
LABEL_94:
          if ( v24 )
            CProgressUI::_StopMarquee(a3);
          if ( *((_DWORD *)a3 + 26) )
          {
            PortableDeviceProperties = -2147023673;
          }
          else if ( PortableDeviceProperties >= 0 )
          {
            continue;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v10 = 104;
            goto LABEL_12;
          }
        }
        goto LABEL_55;
      }
      break;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_55;
    v10 = 99;
LABEL_31:
    v11 = (unsigned int)v14;
    goto LABEL_13;
  }
LABEL_35:
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v10 = 98;
    goto LABEL_12;
  }
LABEL_55:
  PropVariantClear(&pvar);
  if ( PortableDeviceProperties < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      105,
      &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
      (unsigned int)PortableDeviceProperties);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  return (unsigned int)PortableDeviceProperties;
}

```

## disassembly

```asm
0x1800538c4  push    rbp
0x1800538c6  push    rbx
0x1800538c7  push    rsi
0x1800538c8  push    rdi
0x1800538c9  push    r12
0x1800538cb  push    r13
0x1800538cd  push    r14
0x1800538cf  push    r15
0x1800538d1  lea     rbp, [rsp-28h]
0x1800538d6  sub     rsp, 128h
0x1800538dd  mov     rax, cs:__security_cookie
0x1800538e4  xor     rax, rsp
0x1800538e7  mov     [rbp+60h+var_50], rax
0x1800538eb  mov     r12, r9
0x1800538ee  mov     rsi, r8
0x1800538f1  mov     r13, rdx
0x1800538f4  mov     r15, rcx
0x1800538f7  xor     ecx, ecx
0x1800538f9  mov     [rsp+160h+var_118], ecx
0x1800538fd  xorps   xmm0, xmm0
0x180053900  xor     eax, eax
0x180053902  movups  [rsp+160h+Buf2], xmm0
0x180053907  mov     [rbp+60h+var_D8], eax
0x18005390a  mov     [rsp+160h+var_108], rcx
0x18005390f  mov     [rsp+160h+var_110], rcx
0x180053914  mov     [rsp+160h+var_120], rcx
0x180053919  movups  xmmword ptr [rsp+160h+pvar], xmm0
0x18005391e  mov     qword ptr [rsp+160h+pvar+10h], rax
0x180053923  lea     rbx, WPP_GLOBAL_Control
0x18005392a  test    r15, r15
0x18005392d  jnz     short loc_180053939
0x18005392f  mov     edi, 80070057h
0x180053934  jmp     loc_180053B75
0x180053939  test    r13, r13
0x18005393c  jz      short loc_18005392F
0x18005393e  test    r12, r12
0x180053941  jnz     short loc_18005394D
0x180053943  mov     edi, 80004003h
0x180053948  jmp     loc_180053B75
0x18005394d  test    rsi, rsi
0x180053950  jnz     short loc_1800539A0
0x180053952  lea     rdx, [rsp+160h+var_108]; struct IPortableDeviceProperties **
0x180053957  mov     rcx, r15; struct IPortableDevice *
0x18005395a  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x18005395f  mov     edi, eax
0x180053961  test    edi, edi
0x180053963  jns     loc_180053A1C
0x180053969  mov     rcx, cs:WPP_GLOBAL_Control
0x180053970  cmp     rcx, rbx
0x180053973  jz      loc_180053B75
0x180053979  test    byte ptr [rcx+1Ch], 2
0x18005397d  jz      loc_180053B75
0x180053983  mov     edx, 60h ; '`'
0x180053988  mov     r9d, edi
0x18005398b  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180053992  mov     rcx, [rcx+10h]
0x180053996  call    WPP_SF_d
0x18005399b  jmp     loc_180053B75
0x1800539a0  mov     r14d, ecx
0x1800539a3  mov     ebx, ecx
0x1800539a5  cmp     [rsi+68h], ecx
0x1800539a8  jnz     short loc_1800539F0
0x1800539aa  lea     rdx, [rsp+160h+var_108]; struct IPortableDeviceProperties **
0x1800539af  mov     rcx, r15; struct IPortableDevice *
0x1800539b2  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x1800539b7  mov     edi, eax
0x1800539b9  cmp     eax, 800700AAh
0x1800539be  jnz     short loc_1800539F5
0x1800539c0  test    r14d, r14d
0x1800539c3  jnz     short loc_1800539D6
0x1800539c5  lea     eax, [r14+1]
0x1800539c9  mov     r14d, eax
0x1800539cc  mov     ebx, eax
0x1800539ce  mov     rcx, rsi; this
0x1800539d1  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x1800539d6  cmp     dword ptr [rsi+68h], 0
0x1800539da  jnz     short loc_1800539F0
0x1800539dc  mov     ecx, 5DCh; dwMilliseconds
0x1800539e1  call    cs:__imp_Sleep
0x1800539e7  xor     ecx, ecx
0x1800539e9  test    r14d, r14d
0x1800539ec  jz      short loc_1800539F5
0x1800539ee  jmp     short loc_1800539A5
0x1800539f0  mov     edi, 800704C7h
0x1800539f5  test    ebx, ebx
0x1800539f7  jz      short loc_180053A01
0x1800539f9  mov     rcx, rsi; this
0x1800539fc  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180053a01  lea     rbx, WPP_GLOBAL_Control
0x180053a08  cmp     dword ptr [rsi+68h], 0
0x180053a0c  jz      loc_180053961
0x180053a12  mov     edi, 800704C7h
0x180053a17  jmp     loc_180053969
0x180053a1c  lea     rax, [rsp+160h+var_110]
0x180053a21  mov     [rsp+160h+ppv], rax; ppv
0x180053a26  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180053a2d  xor     edx, edx; pUnkOuter
0x180053a2f  lea     r8d, [rdx+1]; dwClsContext
0x180053a33  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180053a3a  call    cs:__imp_CoCreateInstance
0x180053a40  mov     edi, eax
0x180053a42  test    eax, eax
0x180053a44  jns     short loc_180053A6D
0x180053a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a4d  cmp     rcx, rbx
0x180053a50  jz      loc_180053B75
0x180053a56  test    byte ptr [rcx+1Ch], 2
0x180053a5a  jz      loc_180053B75
0x180053a60  mov     edx, 61h ; 'a'
0x180053a65  mov     r9d, eax
0x180053a68  jmp     loc_18005398B
0x180053a6d  mov     rbx, [rsp+160h+var_108]
0x180053a72  test    rsi, rsi
0x180053a75  jnz     short loc_180053AC6
0x180053a77  mov     rax, [rbx]
0x180053a7a  lea     r9, [rsp+160h+var_120]
0x180053a7f  xor     r8d, r8d
0x180053a82  mov     rdx, r13
0x180053a85  mov     rcx, rbx
0x180053a88  mov     rax, [rax+28h]
0x180053a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a91  mov     edi, eax
0x180053a93  test    edi, edi
0x180053a95  jns     loc_180053B5E
0x180053a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053aa2  lea     rbx, WPP_GLOBAL_Control
0x180053aa9  cmp     rcx, rbx
0x180053aac  jz      loc_180053B75
0x180053ab2  test    byte ptr [rcx+1Ch], 2
0x180053ab6  jz      loc_180053B75
0x180053abc  mov     edx, 62h ; 'b'
0x180053ac1  jmp     loc_180053988
0x180053ac6  xor     r15d, r15d
0x180053ac9  xor     r14d, r14d
0x180053acc  cmp     dword ptr [rsi+68h], 0
0x180053ad0  jnz     short loc_180053B38
0x180053ad2  mov     rax, [rbx]
0x180053ad5  lea     r9, [rsp+160h+var_120]
0x180053ada  xor     r8d, r8d
0x180053add  mov     rdx, r13
0x180053ae0  mov     rcx, rbx
0x180053ae3  mov     rax, [rax+28h]
0x180053ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aec  mov     edi, eax
0x180053aee  cmp     eax, 800700AAh
0x180053af3  jnz     short loc_180053B3D
0x180053af5  cmp     [rsp+160h+var_120], 0
0x180053afb  jz      short loc_180053B09
0x180053afd  xor     edx, edx; struct IUnknown *
0x180053aff  lea     rcx, [rsp+160h+var_120]; struct IUnknown **
0x180053b04  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180053b09  test    r15d, r15d
0x180053b0c  jnz     short loc_180053B20
0x180053b0e  lea     eax, [r15+1]
0x180053b12  mov     r15d, eax
0x180053b15  mov     r14d, eax
0x180053b18  mov     rcx, rsi; this
0x180053b1b  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180053b20  cmp     dword ptr [rsi+68h], 0
0x180053b24  jnz     short loc_180053B38
0x180053b26  mov     ecx, 5DCh; dwMilliseconds
0x180053b2b  call    cs:__imp_Sleep
0x180053b31  test    r15d, r15d
0x180053b34  jz      short loc_180053B3D
0x180053b36  jmp     short loc_180053ACC
0x180053b38  mov     edi, 800704C7h
0x180053b3d  test    r14d, r14d
0x180053b40  jz      short loc_180053B4A
0x180053b42  mov     rcx, rsi; this
0x180053b45  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180053b4a  cmp     dword ptr [rsi+68h], 0
0x180053b4e  jz      loc_180053A93
0x180053b54  mov     edi, 800704C7h
0x180053b59  jmp     loc_180053A9B
0x180053b5e  cmp     qword ptr [r12], 0
0x180053b63  jnz     loc_180053BF1
0x180053b69  mov     edi, 8000FFFFh
0x180053b6e  lea     rbx, WPP_GLOBAL_Control
0x180053b75  lea     rcx, [rsp+160h+pvar]; pvar
0x180053b7a  call    cs:__imp_PropVariantClear
0x180053b80  test    edi, edi
0x180053b82  jns     short loc_180053BAF
0x180053b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b8b  cmp     rcx, rbx
0x180053b8e  jz      short loc_180053BAF
0x180053b90  test    byte ptr [rcx+1Ch], 2
0x180053b94  jz      short loc_180053BAF
0x180053b96  mov     edx, 69h ; 'i'
0x180053b9b  mov     r9d, edi
0x180053b9e  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180053ba5  mov     rcx, [rcx+10h]
0x180053ba9  call    WPP_SF_d
0x180053bae  nop
0x180053baf  lea     rcx, [rsp+160h+var_120]
0x180053bb4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053bb9  nop
0x180053bba  lea     rcx, [rsp+160h+var_110]
0x180053bbf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053bc4  nop
0x180053bc5  lea     rcx, [rsp+160h+var_108]
0x180053bca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053bcf  mov     eax, edi
0x180053bd1  mov     rcx, [rbp+60h+var_50]
0x180053bd5  xor     rcx, rsp; StackCookie
0x180053bd8  call    __security_check_cookie
0x180053bdd  add     rsp, 128h
0x180053be4  pop     r15
0x180053be6  pop     r14
0x180053be8  pop     r13
0x180053bea  pop     r12
0x180053bec  pop     rdi
0x180053bed  pop     rsi
0x180053bee  pop     rbx
0x180053bef  pop     rbp
0x180053bf0  retn
0x180053bf1  mov     rcx, [rsp+160h+var_110]
0x180053bf6  mov     rax, [rcx]
0x180053bf9  mov     rax, [rax+30h]
0x180053bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c02  mov     rcx, [rsp+160h+var_120]
0x180053c07  mov     rax, [rcx]
0x180053c0a  lea     rdx, [rsp+160h+var_118]
0x180053c0f  mov     rax, [rax+18h]
0x180053c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c18  mov     edi, eax
0x180053c1a  test    eax, eax
0x180053c1c  js      loc_180053F02
0x180053c22  xor     r14d, r14d
0x180053c25  cmp     r14d, [rsp+160h+var_118]
0x180053c2a  jnb     loc_180053D74
0x180053c30  lea     rcx, [rsp+160h+pvar]; pvar
0x180053c35  call    cs:__imp_PropVariantClear
0x180053c3b  mov     rcx, [rsp+160h+var_120]
0x180053c40  mov     rax, [rcx]
0x180053c43  lea     r9, [rsp+160h+pvar]
0x180053c48  lea     r8, [rsp+160h+Buf2]
0x180053c4d  mov     edx, r14d
0x180053c50  mov     rax, [rax+20h]
0x180053c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c59  mov     edi, eax
0x180053c5b  test    eax, eax
0x180053c5d  js      loc_180053E7C
0x180053c63  xor     eax, eax
0x180053c65  cmp     ax, word ptr [rsp+160h+pvar]
0x180053c6a  jz      loc_180053D6C
0x180053c70  mov     eax, 0Ah
0x180053c75  cmp     ax, word ptr [rsp+160h+pvar]
0x180053c7a  jnz     loc_180053D48
0x180053c80  mov     edi, dword ptr [rsp+160h+pvar+8]
0x180053c84  cmp     edi, 800700AAh
0x180053c8a  jnz     short loc_180053CA7
0x180053c8c  mov     rcx, [rsp+160h+var_110]
0x180053c91  mov     rax, [rcx]
0x180053c94  lea     rdx, [rsp+160h+Buf2]
0x180053c99  mov     rax, [rax+28h]
0x180053c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ca2  jmp     loc_180053D6C
0x180053ca7  cmp     [rbp+60h+var_D8], 6
0x180053cab  jnz     short loc_180053CC8
0x180053cad  mov     r8d, 10h; Size
0x180053cb3  lea     rdx, [rsp+160h+Buf2]; Buf2
0x180053cb8  lea     rcx, WPD_OBJECT_FORMAT; Buf1
0x180053cbf  call    memcmp_0
0x180053cc4  test    eax, eax
0x180053cc6  jz      short loc_180053CED
0x180053cc8  cmp     [rbp+60h+var_D8], 7
0x180053ccc  jnz     loc_180053D6C
0x180053cd2  mov     r8d, 10h; Size
0x180053cd8  lea     rdx, [rsp+160h+Buf2]; Buf2
0x180053cdd  lea     rcx, WPD_OBJECT_CONTENT_TYPE; Buf1
0x180053ce4  call    memcmp_0
0x180053ce9  test    eax, eax
0x180053ceb  jnz     short loc_180053D6C
0x180053ced  test    edi, edi
0x180053cef  jns     short loc_180053D6C
0x180053cf1  mov     rax, cs:WPP_GLOBAL_Control
0x180053cf8  lea     rbx, WPP_GLOBAL_Control
0x180053cff  cmp     rax, rbx
0x180053d02  jz      loc_180053B75
0x180053d08  test    byte ptr [rax+1Ch], 2
0x180053d0c  jz      loc_180053B75
0x180053d12  lea     rdx, [rsp+160h+Buf2]; rguid
0x180053d17  lea     rcx, [rbp+60h+sz]; lpsz
0x180053d1b  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x180053d20  mov     [rsp+160h+var_130], edi
0x180053d24  mov     ecx, [rbp+60h+var_D8]
0x180053d27  mov     [rsp+160h+var_138], ecx
0x180053d2b  mov     [rsp+160h+ppv], rax
0x180053d30  mov     r9d, edi
0x180053d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d3a  mov     rcx, [rcx+10h]
0x180053d3e  call    WPP_SF_DSdd
0x180053d43  jmp     loc_180053B75
0x180053d48  mov     rcx, [r12]
0x180053d4c  mov     rax, [rcx]
0x180053d4f  lea     r8, [rsp+160h+pvar]
0x180053d54  lea     rdx, [rsp+160h+Buf2]
0x180053d59  mov     rax, [rax+28h]
0x180053d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d62  mov     edi, eax
  ... truncated ...
```
