# CMSCContextMenu::_MapDriveToPnPDevicePath(ushort const *,ushort *,uint)

- ea: `0x18006ac50`
- end: `0x18006b28d`
- name: `?_MapDriveToPnPDevicePath@CMSCContextMenu@@AEAAJPEBGPEAGI@Z`
- size: `1597`
- prototype: `int(CMSCContextMenu *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006a710`

## callees

- `0x180004110`
- `0x18000d610`
- `0x180014748`
- `0x180015700`
- `0x1800177dc`
- `0x180022028`
- `0x1800285c8`
- `0x18002950c`
- `0x18002feb4`
- `0x18002ff5c`
- `0x18006ac50`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b011`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006b011`
- `ole32!CoTaskMemFree` at `0x18006b1cf`
- `ole32!CoTaskMemFree` at `0x18006b1cf`
- `ole32!PropVariantClear` at `0x18006b076`
- `ole32!PropVariantClear` at `0x18006b076`
- `ole32!CoCreateInstance` at `0x18006acb0`
- `ole32!CoCreateInstance` at `0x18006ae0e`
- `ole32!CoCreateInstance` at `0x18006acb0`
- `ole32!CoCreateInstance` at `0x18006ae0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMSCContextMenu::_MapDriveToPnPDevicePath(
        CMSCContextMenu *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  const unsigned __int16 *v5; // rbx
  HRESULT v6; // eax
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int128 v10; // rax
  _QWORD *v11; // r14
  int v12; // r15d
  HRESULT ClientInfo; // eax
  int v14; // esi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r15d
  struct IPortableDeviceValues *v18; // rdi
  int v19; // eax
  __int64 v20; // r8
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rbx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  unsigned int i; // edi
  struct IUnknown *v27; // [rsp+48h] [rbp-39h] BYREF
  __int64 v28; // [rsp+50h] [rbp-31h] BYREF
  __int64 v29; // [rsp+58h] [rbp-29h] BYREF
  int v30; // [rsp+60h] [rbp-21h] BYREF
  LPVOID v31; // [rsp+68h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-11h] BYREF
  int v33; // [rsp+78h] [rbp-9h] BYREF
  int v34; // [rsp+7Ch] [rbp-5h] BYREF
  struct IPortableDeviceValues *v35; // [rsp+80h] [rbp-1h] BYREF
  PROPVARIANT pvar; // [rsp+88h] [rbp+7h] BYREF
  unsigned int v37; // [rsp+E8h] [rbp+67h] BYREF
  int v38; // [rsp+ECh] [rbp+6Bh]
  const unsigned __int16 *v39; // [rsp+F0h] [rbp+6Fh]
  int v40; // [rsp+100h] [rbp+7Fh]

  v40 = a4;
  v39 = a2;
  v38 = HIDWORD(this);
  v5 = a2;
  v37 = 0;
  v31 = 0;
  v35 = 0;
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_PortableDeviceManager, 0, 1u, &GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40, &ppv);
  if ( v6 < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 15;
LABEL_5:
      v9 = (unsigned int)v6;
LABEL_84:
      WPP_SF_d(v7[2], v8, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids, v9);
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned int *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v37);
  if ( v6 < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 16;
      goto LABEL_5;
    }
LABEL_86:
    v14 = -2147467263;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
      WPP_SF_d(v7[2], 28, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids, 2147500033LL);
    goto LABEL_89;
  }
  if ( !v37 )
  {
LABEL_85:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_86;
  }
  v10 = v37 * (unsigned __int128)8uLL;
  if ( !is_mul_ok(v37, 8u) )
    *(_QWORD *)&v10 = -1;
  v11 = operator new(v10, *((const struct std::nothrow_t **)&v10 + 1));
  if ( !v11 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 18;
      v9 = 2147942414LL;
      goto LABEL_84;
    }
    goto LABEL_86;
  }
  v12 = 0;
  v40 = 0;
  ClientInfo = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, unsigned int *))(*(_QWORD *)ppv + 24LL))(ppv, v11, &v37);
  v14 = ClientInfo;
  if ( ClientInfo >= 0 )
  {
    ClientInfo = GetClientInfo(1, &v35);
    v14 = ClientInfo;
    if ( ClientInfo >= 0 )
    {
      ClientInfo = CoCreateInstance(&CLSID_PortableDevice, 0, 1u, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v31);
      v14 = ClientInfo;
      if ( ClientInfo >= 0 )
      {
        v17 = 0;
        v18 = v35;
        while ( v17 < v37 )
        {
          v30 = 0;
          v34 = 4;
          v33 = 4;
          if ( (*(int (__fastcall **)(LPVOID, _QWORD, const wchar_t *, int *, int *, int *))(*(_QWORD *)ppv + 64LL))(
                 ppv,
                 v11[v17],
                 L"PortableDeviceIsMassStorage",
                 &v30,
                 &v34,
                 &v33) >= 0 )
          {
            v19 = v30;
          }
          else
          {
            v19 = 0;
            v30 = 0;
          }
          if ( v19 == 1 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v29);
            v28 = 0;
            v27 = 0;
            memset(&pvar, 0, sizeof(pvar));
            v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPortableDeviceValues *))(*(_QWORD *)v31 + 24LL))(
                    v31,
                    v11[v17],
                    v18);
            if ( v14 == -2147024891 )
            {
              v14 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))v18->lpVtbl->SetUnsignedIntegerValue)(
                      v18,
                      &WPD_CLIENT_DESIRED_ACCESS,
                      0x80000000LL);
              if ( v14 < 0 )
              {
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v24 = 21;
                  goto LABEL_73;
                }
                goto LABEL_74;
              }
              v14 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))v18->lpVtbl->SetUnsignedIntegerValue)(
                      v18,
                      &WPD_CLIENT_SHARE_MODE,
                      1);
              if ( v14 < 0 )
              {
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v24 = 22;
                  goto LABEL_73;
                }
                goto LABEL_74;
              }
              v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPortableDeviceValues *))(*(_QWORD *)v31 + 24LL))(
                      v31,
                      v11[v17],
                      v18);
            }
            if ( v14 < 0 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_74;
              v24 = 23;
LABEL_73:
              WPP_SF_d(v23[2], v24, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids, (unsigned int)v14);
              goto LABEL_74;
            }
            v14 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown **))(*(_QWORD *)v31 + 48LL))(v31, &v27);
            if ( v14 < 0 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_74;
              v24 = 24;
              goto LABEL_73;
            }
            v14 = ((__int64 (__fastcall *)(struct IUnknown *, const GUID *, __int64 *))v27->lpVtbl[2].QueryInterface)(
                    v27,
                    &WPD_FUNCTIONAL_CATEGORY_STORAGE,
                    &v28);
            if ( v14 < 0 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_74;
              v24 = 25;
              goto LABEL_73;
            }
            v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v28 + 32LL))(v28, 0, &pvar);
            if ( v14 < 0 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v24 = 26;
                goto LABEL_73;
              }
LABEL_74:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
              ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
              break;
            }
            if ( v27 )
              ATL::AtlComPtrAssign(&v27, 0);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 64LL))(v31);
            if ( pvar.hVal.QuadPart )
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)(pvar.hVal.QuadPart + 2 * v20) );
            }
            else
            {
              v20 = 0;
            }
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ATL::CSimpleStringT<unsigned short,0>::SetString)(
              &v29,
              (LARGE_INTEGER)pvar.hVal.QuadPart,
              v20);
            v21 = v5;
            v22 = v29;
            if ( !(unsigned int)_o__wcsicmp(v29, v21) )
            {
              v40 = 1;
              v14 = StringCchCopyW(a3, 0x104u, (const unsigned __int16 *)v11[v17]);
              if ( v14 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  27,
                  WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids,
                  (unsigned int)v14);
              }
            }
            PropVariantClear(&pvar);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
            ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
            if ( v40 == 1 )
              break;
            v5 = v39;
          }
          ++v17;
        }
        v12 = v40;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v16 = 20;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 19;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v16 = 17;
LABEL_18:
      WPP_SF_d(v15[2], v16, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids, (unsigned int)ClientInfo);
    }
  }
  for ( i = 0; i < v37; ++i )
  {
    CoTaskMemFree((LPVOID)v11[i]);
    v11[i] = 0;
  }
  operator delete(v11);
  if ( !v12 || v14 < 0 )
    goto LABEL_85;
LABEL_89:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18006ac50  mov     rax, rsp
0x18006ac53  mov     [rax+18h], rbx
0x18006ac57  mov     [rax+20h], r9d
0x18006ac5b  mov     [rax+10h], rdx
0x18006ac5f  mov     [rax+8], rcx
0x18006ac63  push    rbp
0x18006ac64  push    rsi
0x18006ac65  push    rdi
0x18006ac66  push    r12
0x18006ac68  push    r13
0x18006ac6a  push    r14
0x18006ac6c  push    r15
0x18006ac6e  lea     rbp, [rax-5Fh]
0x18006ac72  sub     rsp, 0A0h
0x18006ac79  mov     r13, r8
0x18006ac7c  mov     rbx, rdx
0x18006ac7f  xor     r12d, r12d
0x18006ac82  mov     [rbp+57h+arg_0], r12d
0x18006ac86  mov     [rbp+57h+var_70], r12
0x18006ac8a  mov     [rbp+57h+var_58], r12
0x18006ac8e  mov     [rbp+57h+var_68], r12
0x18006ac92  lea     rax, [rbp+57h+var_68]
0x18006ac96  mov     [rsp+0D0h+ppv], rax; ppv
0x18006ac9b  lea     r9, _GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40; riid
0x18006aca2  xor     edx, edx; pUnkOuter
0x18006aca4  lea     r8d, [r12+1]; dwClsContext
0x18006aca9  lea     rcx, CLSID_PortableDeviceManager; rclsid
0x18006acb0  call    cs:__imp_CoCreateInstance
0x18006acb6  mov     sil, 2
0x18006acb9  lea     r15, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids
0x18006acc0  lea     rdi, WPP_GLOBAL_Control
0x18006acc7  test    eax, eax
0x18006acc9  jns     short loc_18006ACF2
0x18006accb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006acd2  cmp     rcx, rdi
0x18006acd5  jz      loc_18006B223
0x18006acdb  test    [rcx+1Ch], sil
0x18006acdf  jz      loc_18006B223
0x18006ace5  lea     edx, [r12+0Fh]
0x18006acea  mov     r9d, eax
0x18006aced  jmp     loc_18006B210
0x18006acf2  mov     rcx, [rbp+57h+var_68]
0x18006acf6  mov     rax, [rcx]
0x18006acf9  lea     r8, [rbp+57h+arg_0]
0x18006acfd  xor     edx, edx
0x18006acff  mov     rax, [rax+18h]
0x18006ad03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad08  test    eax, eax
0x18006ad0a  jns     short loc_18006AD2D
0x18006ad0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad13  cmp     rcx, rdi
0x18006ad16  jz      loc_18006B223
0x18006ad1c  test    [rcx+1Ch], sil
0x18006ad20  jz      loc_18006B223
0x18006ad26  mov     edx, 10h
0x18006ad2b  jmp     short loc_18006ACEA
0x18006ad2d  mov     eax, [rbp+57h+arg_0]
0x18006ad30  test    eax, eax
0x18006ad32  jz      loc_18006B21C
0x18006ad38  mov     ecx, eax
0x18006ad3a  mov     eax, 8
0x18006ad3f  mul     rcx
0x18006ad42  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006ad49  cmovb   rax, rcx
0x18006ad4d  mov     rcx, rax; unsigned __int64
0x18006ad50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006ad55  mov     r14, rax
0x18006ad58  test    rax, rax
0x18006ad5b  jz      loc_18006B1F3
0x18006ad61  mov     r15d, r12d
0x18006ad64  mov     [rbp+57h+arg_18], r12d
0x18006ad68  mov     rcx, [rbp+57h+var_68]
0x18006ad6c  mov     rdx, [rcx]
0x18006ad6f  mov     rax, [rdx+18h]
0x18006ad73  lea     r8, [rbp+57h+arg_0]
0x18006ad77  mov     rdx, r14
0x18006ad7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad7f  mov     esi, eax
0x18006ad81  test    eax, eax
0x18006ad83  jns     short loc_18006ADBC
0x18006ad85  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad8c  cmp     rcx, rdi
0x18006ad8f  jz      loc_18006B1C0
0x18006ad95  test    byte ptr [rcx+1Ch], 2
0x18006ad99  jz      loc_18006B1C0
0x18006ad9f  mov     edx, 11h
0x18006ada4  mov     r9d, eax
0x18006ada7  lea     r8, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids
0x18006adae  mov     rcx, [rcx+10h]
0x18006adb2  call    WPP_SF_d
0x18006adb7  jmp     loc_18006B1C0
0x18006adbc  lea     rdx, [rbp+57h+var_58]; struct IPortableDeviceValues **
0x18006adc0  mov     ecx, 1; int
0x18006adc5  call    ?GetClientInfo@@YAJHPEAPEAUIPortableDeviceValues@@@Z; GetClientInfo(int,IPortableDeviceValues * *)
0x18006adca  mov     esi, eax
0x18006adcc  test    eax, eax
0x18006adce  jns     short loc_18006ADF1
0x18006add0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006add7  cmp     rcx, rdi
0x18006adda  jz      loc_18006B1C0
0x18006ade0  test    byte ptr [rcx+1Ch], 2
0x18006ade4  jz      loc_18006B1C0
0x18006adea  mov     edx, 13h
0x18006adef  jmp     short loc_18006ADA4
0x18006adf1  lea     rax, [rbp+57h+var_70]
0x18006adf5  mov     [rsp+0D0h+ppv], rax; ppv
0x18006adfa  lea     r9, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c; riid
0x18006ae01  xor     edx, edx; pUnkOuter
0x18006ae03  lea     r8d, [rdx+1]; dwClsContext
0x18006ae07  lea     rcx, CLSID_PortableDevice; rclsid
0x18006ae0e  call    cs:__imp_CoCreateInstance
0x18006ae14  mov     esi, eax
0x18006ae16  test    eax, eax
0x18006ae18  jns     short loc_18006AE3E
0x18006ae1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ae21  cmp     rcx, rdi
0x18006ae24  jz      loc_18006B1C0
0x18006ae2a  test    byte ptr [rcx+1Ch], 2
0x18006ae2e  jz      loc_18006B1C0
0x18006ae34  mov     edx, 14h
0x18006ae39  jmp     loc_18006ADA4
0x18006ae3e  mov     r15d, r12d
0x18006ae41  mov     rdi, [rbp+57h+var_58]
0x18006ae45  cmp     r15d, [rbp+57h+arg_0]
0x18006ae49  jnb     loc_18006B1BC
0x18006ae4f  mov     [rbp+57h+var_78], r12d
0x18006ae53  mov     [rbp+57h+var_5C], 4
0x18006ae5a  mov     [rbp+57h+var_60], 4
0x18006ae61  mov     rcx, [rbp+57h+var_68]
0x18006ae65  mov     r12d, r15d
0x18006ae68  mov     rax, [rcx]
0x18006ae6b  lea     rdx, [rbp+57h+var_60]
0x18006ae6f  mov     [rsp+28h], rdx
0x18006ae74  lea     rdx, [rbp+57h+var_5C]
0x18006ae78  mov     [rsp+0D0h+ppv], rdx
0x18006ae7d  lea     r9, [rbp+57h+var_78]
0x18006ae81  lea     r8, aPortabledevice_2; "PortableDeviceIsMassStorage"
0x18006ae88  mov     rdx, [r14+r12*8]
0x18006ae8c  mov     rax, [rax+40h]
0x18006ae90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae95  xor     ecx, ecx
0x18006ae97  test    eax, eax
0x18006ae99  jns     short loc_18006AEA2
0x18006ae9b  mov     eax, ecx
0x18006ae9d  mov     [rbp+57h+var_78], ecx
0x18006aea0  jmp     short loc_18006AEA5
0x18006aea2  mov     eax, [rbp+57h+var_78]
0x18006aea5  cmp     eax, 1
0x18006aea8  jnz     loc_18006B0A8
0x18006aeae  lea     rcx, [rbp+57h+var_80]
0x18006aeb2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18006aeb7  nop
0x18006aeb8  xor     eax, eax
0x18006aeba  mov     [rbp+57h+var_88], rax
0x18006aebe  mov     [rbp+57h+var_90], rax
0x18006aec2  xorps   xmm0, xmm0
0x18006aec5  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18006aec9  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18006aecd  mov     rcx, [rbp+57h+var_70]
0x18006aed1  mov     rax, [rcx]
0x18006aed4  mov     r8, rdi
0x18006aed7  mov     rdx, [r14+r12*8]
0x18006aedb  mov     rax, [rax+18h]
0x18006aedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aee4  mov     esi, eax
0x18006aee6  cmp     eax, 80070005h
0x18006aeeb  jnz     short loc_18006AF52
0x18006aeed  mov     rax, [rdi]
0x18006aef0  mov     r8d, 80000000h
0x18006aef6  lea     rdx, WPD_CLIENT_DESIRED_ACCESS
0x18006aefd  mov     rcx, rdi
0x18006af00  mov     rax, [rax+48h]
0x18006af04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af09  mov     esi, eax
0x18006af0b  test    eax, eax
0x18006af0d  js      loc_18006B0DE
0x18006af13  mov     rax, [rdi]
0x18006af16  mov     r8d, 1
0x18006af1c  lea     rdx, WPD_CLIENT_SHARE_MODE
0x18006af23  mov     rcx, rdi
0x18006af26  mov     rax, [rax+48h]
0x18006af2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af2f  mov     esi, eax
0x18006af31  test    eax, eax
0x18006af33  js      loc_18006B0B3
0x18006af39  mov     rcx, [rbp+57h+var_70]
0x18006af3d  mov     rax, [rcx]
0x18006af40  mov     r8, rdi
0x18006af43  mov     rdx, [r14+r12*8]
0x18006af47  mov     rax, [rax+18h]
0x18006af4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af50  mov     esi, eax
0x18006af52  test    esi, esi
0x18006af54  js      loc_18006B166
0x18006af5a  mov     rcx, [rbp+57h+var_70]
0x18006af5e  mov     rax, [rcx]
0x18006af61  lea     rdx, [rbp+57h+var_90]
0x18006af65  mov     rax, [rax+30h]
0x18006af69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af6e  mov     esi, eax
0x18006af70  test    eax, eax
0x18006af72  js      loc_18006B146
0x18006af78  mov     rcx, [rbp+57h+var_90]
0x18006af7c  mov     rax, [rcx]
0x18006af7f  lea     r8, [rbp+57h+var_88]
0x18006af83  lea     rdx, WPD_FUNCTIONAL_CATEGORY_STORAGE
0x18006af8a  mov     rax, [rax+30h]
0x18006af8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af93  mov     esi, eax
0x18006af95  test    eax, eax
0x18006af97  js      loc_18006B126
0x18006af9d  mov     rcx, [rbp+57h+var_88]
0x18006afa1  mov     rax, [rcx]
0x18006afa4  lea     r8, [rbp+57h+pvar]
0x18006afa8  xor     edx, edx
0x18006afaa  mov     rax, [rax+20h]
0x18006afae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afb3  mov     esi, eax
0x18006afb5  xor     eax, eax
0x18006afb7  test    esi, esi
0x18006afb9  js      loc_18006B106
0x18006afbf  cmp     [rbp+57h+var_90], rax
0x18006afc3  jz      short loc_18006AFD0
0x18006afc5  xor     edx, edx; struct IUnknown *
0x18006afc7  lea     rcx, [rbp+57h+var_90]; struct IUnknown **
0x18006afcb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18006afd0  mov     rcx, [rbp+57h+var_70]
0x18006afd4  mov     rax, [rcx]
0x18006afd7  mov     rax, [rax+40h]
0x18006afdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afe0  mov     rdx, qword ptr [rbp+57h+pvar+8]
0x18006afe4  xor     eax, eax
0x18006afe6  test    rdx, rdx
0x18006afe9  jnz     short loc_18006AFF0
0x18006afeb  mov     r8d, eax
0x18006afee  jmp     short loc_18006AFFE
0x18006aff0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006aff4  inc     r8
0x18006aff7  cmp     [rdx+r8*2], ax
0x18006affc  jnz     short loc_18006AFF4
0x18006affe  lea     rcx, [rbp+57h+var_80]
0x18006b002  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18006b007  mov     rdx, rbx
0x18006b00a  mov     rbx, [rbp+57h+var_80]
0x18006b00e  mov     rcx, rbx
0x18006b011  call    cs:__imp__o__wcsicmp
0x18006b017  test    eax, eax
0x18006b019  jnz     short loc_18006B06F
0x18006b01b  mov     [rbp+57h+arg_18], 1
0x18006b022  mov     r8, [r14+r12*8]; unsigned __int16 *
0x18006b026  mov     edx, 104h; unsigned __int64
0x18006b02b  mov     rcx, r13; unsigned __int16 *
0x18006b02e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006b033  mov     esi, eax
0x18006b035  xor     r12d, r12d
0x18006b038  test    eax, eax
0x18006b03a  jns     short loc_18006B072
0x18006b03c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b043  lea     rax, WPP_GLOBAL_Control
0x18006b04a  cmp     rcx, rax
0x18006b04d  jz      short loc_18006B072
0x18006b04f  test    byte ptr [rcx+1Ch], 40h
0x18006b053  jz      short loc_18006B072
0x18006b055  lea     edx, [r12+1Bh]
0x18006b05a  mov     r9d, esi
0x18006b05d  lea     r8, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids
0x18006b064  mov     rcx, [rcx+10h]
0x18006b068  call    WPP_SF_d
0x18006b06d  jmp     short loc_18006B072
0x18006b06f  xor     r12d, r12d
0x18006b072  lea     rcx, [rbp+57h+pvar]; pvar
0x18006b076  call    cs:__imp_PropVariantClear
0x18006b07c  nop
0x18006b07d  lea     rcx, [rbp+57h+var_90]
0x18006b081  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b086  nop
0x18006b087  lea     rcx, [rbp+57h+var_88]
0x18006b08b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b090  nop
0x18006b091  lea     rcx, [rbx-18h]; this
0x18006b095  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006b09a  cmp     [rbp+57h+arg_18], 1
0x18006b09e  jz      loc_18006B1BC
0x18006b0a4  mov     rbx, [rbp+57h+arg_8]
0x18006b0a8  inc     r15d
0x18006b0ab  xor     r12d, r12d
0x18006b0ae  jmp     loc_18006AE45
0x18006b0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b0ba  lea     rax, WPP_GLOBAL_Control
0x18006b0c1  cmp     rcx, rax
0x18006b0c4  jz      loc_18006B198
0x18006b0ca  test    byte ptr [rcx+1Ch], 2
0x18006b0ce  jz      loc_18006B198
0x18006b0d4  mov     edx, 16h
0x18006b0d9  jmp     loc_18006B184
0x18006b0de  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b0e5  lea     rax, WPP_GLOBAL_Control
0x18006b0ec  cmp     rcx, rax
0x18006b0ef  jz      loc_18006B198
0x18006b0f5  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
