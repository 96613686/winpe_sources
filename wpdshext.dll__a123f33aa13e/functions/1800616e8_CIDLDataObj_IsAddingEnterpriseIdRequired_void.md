# CIDLDataObj::_IsAddingEnterpriseIdRequired(void)

- ea: `0x1800616e8`
- end: `0x180061942`
- name: `?_IsAddingEnterpriseIdRequired@CIDLDataObj@@AEAAHXZ`
- size: `602`
- prototype: `__int64 __fastcall(CIDLDataObj *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001f0a0`
- `0x180061478`

## callees

- `0x180014dd0`
- `0x180016260`
- `0x180024aa4`
- `0x1800285c8`
- `0x180028f0c`
- `0x180035590`
- `0x1800616e8`
- `0x1800628cc`
- `0x180062e70`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006176f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006176f`
- `ole32!CoTaskMemFree` at `0x1800618c2`
- `ole32!CoTaskMemFree` at `0x1800618c2`
- `ole32!CoCreateInstance` at `0x180061841`
- `ole32!CoCreateInstance` at `0x180061841`
- `SHELL32!__imp_ILFree` at `0x1800618d4`
- `SHELL32!__imp_ILFree` at `0x1800618d4`

## string_xrefs

- `0x180061750`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CIDLDataObj::_IsAddingEnterpriseIdRequired(CIDLDataObj *this)
{
  __int64 v2; // rdi
  ITEMIDLIST *v3; // rbx
  unsigned __int8 v4; // al
  unsigned int v5; // esi
  __int64 HIDA; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  void *v9; // rcx
  _BYTE v11[8]; // [rsp+30h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-49h] BYREF
  struct IPortableDeviceProperties *v14; // [rsp+48h] [rbp-41h] BYREF
  __int64 v15; // [rsp+50h] [rbp-39h] BYREF
  struct IPortableDevice *v16; // [rsp+58h] [rbp-31h] BYREF
  __int64 v17; // [rsp+60h] [rbp-29h] BYREF
  int (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-21h] BYREF
  __int128 v19; // [rsp+70h] [rbp-19h] BYREF
  __int64 v20; // [rsp+80h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+17h]

  v11[0] = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v2 = 0;
  v3 = 0;
  pv = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  ppv = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.EnterpriseData.ProtectionPolicyManager",
    0x38u,
    0x37u);
  if ( (int)RoGetActivationFactory(v22, &GUID_20b794db_ccbd_490f_8c83_49ccb77aea6c, &v18) < 0
    || (**v18)(v18, &GUID_b68f9a8c_39e0_4649_b2e4_070ab8a579b3, &v17) < 0
    || (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 112LL))(v17, v11) >= 0 )
  {
    v4 = v11[0];
  }
  else
  {
    v4 = 0;
    v11[0] = 0;
  }
  v5 = v4;
  if ( v4
    && (HIDA = DataObj_GetHIDA(this, &v19), (v2 = HIDA) != 0)
    && (v7 = IDA_ILClone(HIDA, 0), (v3 = (ITEMIDLIST *)v7) != 0)
    && (int)SHBindToIDList(v7, v8, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v16) >= 0
    && (int)GetPortableDeviceProperties(v16, &v14) >= 0
    && CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &ppv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_DEVICE_EDP_IDENTITY);
    if ( ((int (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, LPVOID, __int64 *))v14->lpVtbl->GetValues)(
           v14,
           L"DEVICE",
           ppv,
           &v15) < 0
      || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v15 + 64LL))(
           v15,
           &WPD_DEVICE_EDP_IDENTITY,
           &pv) < 0 )
    {
      v9 = pv;
    }
    else
    {
      v9 = pv;
      if ( *(_WORD *)pv )
        goto LABEL_19;
    }
    v5 = 0;
  }
  else
  {
    v9 = pv;
  }
LABEL_19:
  if ( v9 )
  {
    CoTaskMemFree(v9);
    pv = 0;
  }
  if ( v3 )
    ILFree(v3);
  if ( v2 )
    ReleaseStgMediumHGLOBAL(v9, &v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  return v5;
}

```

## disassembly

```asm
0x1800616e8  push    rbp
0x1800616ea  push    rbx
0x1800616eb  push    rsi
0x1800616ec  push    rdi
0x1800616ed  push    r14
0x1800616ef  push    r15
0x1800616f1  lea     rbp, [rsp-2Fh]
0x1800616f6  sub     rsp, 0B8h
0x1800616fd  mov     rax, cs:__security_cookie
0x180061704  xor     rax, rsp
0x180061707  mov     [rbp+57h+var_38], rax
0x18006170b  mov     r14, rcx
0x18006170e  xor     r15d, r15d
0x180061711  mov     [rbp+57h+var_B0], r15b
0x180061715  mov     [rbp+57h+var_78], r15
0x180061719  mov     [rbp+57h+var_80], r15
0x18006171d  xorps   xmm0, xmm0
0x180061720  xor     eax, eax
0x180061722  movups  [rbp+57h+var_70], xmm0
0x180061726  mov     [rbp+57h+var_60], rax
0x18006172a  mov     edi, r15d
0x18006172d  mov     ebx, r15d
0x180061730  mov     [rbp+57h+pv], r15
0x180061734  mov     [rbp+57h+var_88], r15
0x180061738  mov     [rbp+57h+var_90], r15
0x18006173c  mov     [rbp+57h+var_98], r15
0x180061740  mov     [rbp+57h+var_A0], r15
0x180061744  mov     [rbp+57h+var_40], r15
0x180061748  lea     r9d, [r15+37h]; unsigned int
0x18006174c  lea     r8d, [r15+38h]; unsigned int
0x180061750  lea     rdx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x180061757  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006175b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180061760  lea     r8, [rbp+57h+var_78]
0x180061764  lea     rdx, _GUID_20b794db_ccbd_490f_8c83_49ccb77aea6c
0x18006176b  mov     rcx, [rbp+57h+var_40]
0x18006176f  call    cs:__imp_RoGetActivationFactory
0x180061775  test    eax, eax
0x180061777  js      short loc_1800617B8
0x180061779  mov     rcx, [rbp+57h+var_78]
0x18006177d  mov     rax, [rcx]
0x180061780  lea     r8, [rbp+57h+var_80]
0x180061784  lea     rdx, _GUID_b68f9a8c_39e0_4649_b2e4_070ab8a579b3
0x18006178b  mov     rax, [rax]
0x18006178e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061793  nop
0x180061794  test    eax, eax
0x180061796  js      short loc_1800617B8
0x180061798  mov     rcx, [rbp+57h+var_80]
0x18006179c  mov     rax, [rcx]
0x18006179f  lea     rdx, [rbp+57h+var_B0]
0x1800617a3  mov     rax, [rax+70h]
0x1800617a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617ac  test    eax, eax
0x1800617ae  jns     short loc_1800617B8
0x1800617b0  mov     al, r15b
0x1800617b3  mov     [rbp+57h+var_B0], al
0x1800617b6  jmp     short loc_1800617BB
0x1800617b8  mov     al, [rbp+57h+var_B0]
0x1800617bb  movzx   esi, al
0x1800617be  test    al, al
0x1800617c0  jz      loc_1800618B9
0x1800617c6  lea     rdx, [rbp+57h+var_70]
0x1800617ca  mov     rcx, r14
0x1800617cd  call    DataObj_GetHIDA
0x1800617d2  mov     rdi, rax
0x1800617d5  test    rax, rax
0x1800617d8  jz      loc_1800618B9
0x1800617de  xor     edx, edx
0x1800617e0  mov     rcx, rax
0x1800617e3  call    IDA_ILClone
0x1800617e8  mov     rbx, rax
0x1800617eb  test    rax, rax
0x1800617ee  jz      loc_1800618B9
0x1800617f4  lea     r9, [rbp+57h+var_88]
0x1800617f8  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x1800617ff  mov     rcx, rax
0x180061802  call    SHBindToIDList
0x180061807  test    eax, eax
0x180061809  js      loc_1800618B9
0x18006180f  lea     rdx, [rbp+57h+var_98]; struct IPortableDeviceProperties **
0x180061813  mov     rcx, [rbp+57h+var_88]; struct IPortableDevice *
0x180061817  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x18006181c  test    eax, eax
0x18006181e  js      loc_1800618B9
0x180061824  lea     rax, [rbp+57h+var_A0]
0x180061828  mov     [rsp+0E0h+ppv], rax; ppv
0x18006182d  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180061834  xor     edx, edx; pUnkOuter
0x180061836  lea     r8d, [rdx+1]; dwClsContext
0x18006183a  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180061841  call    cs:__imp_CoCreateInstance
0x180061847  test    eax, eax
0x180061849  js      short loc_1800618B9
0x18006184b  mov     rcx, [rbp+57h+var_A0]
0x18006184f  mov     rax, [rcx]
0x180061852  lea     rdx, WPD_DEVICE_EDP_IDENTITY
0x180061859  mov     rax, [rax+28h]
0x18006185d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061862  mov     rcx, [rbp+57h+var_98]
0x180061866  mov     rax, [rcx]
0x180061869  lea     r9, [rbp+57h+var_90]
0x18006186d  mov     r8, [rbp+57h+var_A0]
0x180061871  lea     rdx, aDevice_0; "DEVICE"
0x180061878  mov     rax, [rax+28h]
0x18006187c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061881  test    eax, eax
0x180061883  js      short loc_1800618B0
0x180061885  mov     rcx, [rbp+57h+var_90]
0x180061889  mov     rax, [rcx]
0x18006188c  lea     r8, [rbp+57h+pv]
0x180061890  lea     rdx, WPD_DEVICE_EDP_IDENTITY
0x180061897  mov     rax, [rax+40h]
0x18006189b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618a0  test    eax, eax
0x1800618a2  js      short loc_1800618B0
0x1800618a4  mov     rcx, [rbp+57h+pv]
0x1800618a8  cmp     [rcx], r15w
0x1800618ac  jnz     short loc_1800618BD
0x1800618ae  jmp     short loc_1800618B4
0x1800618b0  mov     rcx, [rbp+57h+pv]
0x1800618b4  mov     esi, r15d
0x1800618b7  jmp     short loc_1800618BD
0x1800618b9  mov     rcx, [rbp+57h+pv]; pv
0x1800618bd  test    rcx, rcx
0x1800618c0  jz      short loc_1800618CC
0x1800618c2  call    cs:__imp_CoTaskMemFree
0x1800618c8  mov     [rbp+57h+pv], r15
0x1800618cc  test    rbx, rbx
0x1800618cf  jz      short loc_1800618DA
0x1800618d1  mov     rcx, rbx; pidl
0x1800618d4  call    cs:__imp_ILFree
0x1800618da  test    rdi, rdi
0x1800618dd  jz      short loc_1800618E9
0x1800618df  lea     rdx, [rbp+57h+var_70]
0x1800618e3  call    ReleaseStgMediumHGLOBAL
0x1800618e8  nop
0x1800618e9  lea     rcx, [rbp+57h+var_A0]
0x1800618ed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800618f2  nop
0x1800618f3  lea     rcx, [rbp+57h+var_98]
0x1800618f7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800618fc  nop
0x1800618fd  lea     rcx, [rbp+57h+var_90]
0x180061901  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061906  nop
0x180061907  lea     rcx, [rbp+57h+var_88]
0x18006190b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061910  nop
0x180061911  lea     rcx, [rbp+57h+var_80]
0x180061915  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006191a  nop
0x18006191b  lea     rcx, [rbp+57h+var_78]
0x18006191f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061924  mov     eax, esi
0x180061926  mov     rcx, [rbp+57h+var_38]
0x18006192a  xor     rcx, rsp; StackCookie
0x18006192d  call    __security_check_cookie
0x180061932  add     rsp, 0B8h
0x180061939  pop     r15
0x18006193b  pop     r14
0x18006193d  pop     rdi
0x18006193e  pop     rsi
0x18006193f  pop     rbx
0x180061940  pop     rbp
0x180061941  retn
```
