# CContentFolder::_CreateIDListForFileSysSimpleItem(ushort const *,IFileSystemBindData *,_ITEMIDLIST * *)

- ea: `0x180046d3c`
- end: `0x180046fb9`
- name: `?_CreateIDListForFileSysSimpleItem@CContentFolder@@AEAAJPEBGPEAUIFileSystemBindData@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, const unsigned __int16 *, struct IFileSystemBindData *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004200`

## callees

- `0x18000ff40`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180046d3c`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180046f92`
- `ole32!CoTaskMemFree` at `0x180046f92`
- `ole32!CoCreateInstance` at `0x180046da8`
- `ole32!CoCreateInstance` at `0x180046da8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentFolder::_CreateIDListForFileSysSimpleItem(
        CContentFolder *this,
        const unsigned __int16 *a2,
        struct IFileSystemBindData *a3,
        struct _ITEMIDLIST **a4)
{
  int Instance; // eax
  unsigned int v9; // edi
  PVOID *v10; // rcx
  __int64 v11; // rdx
  struct _ITEMIDLIST *v12; // rax
  struct IPortableDeviceValues *ppv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[592]; // [rsp+50h] [rbp-B0h] BYREF

  pv = 0;
  ppv = 0;
  *a4 = 0;
  Instance = CoCreateInstance(
               &CLSID_PortableDeviceValues,
               0,
               1u,
               &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
               (LPVOID *)&ppv);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v11 = 198;
    goto LABEL_22;
  }
  Instance = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const unsigned __int16 *))ppv->lpVtbl->SetStringValue)(
               ppv,
               &WPD_OBJECT_ORIGINAL_FILE_NAME,
               a2);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v11 = 199;
    goto LABEL_22;
  }
  memset_0(v16, 0, sizeof(v16));
  Instance = ((__int64 (__fastcall *)(struct IFileSystemBindData *, _BYTE *))a3->lpVtbl->GetFindData)(a3, v16);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v11 = 200;
    goto LABEL_22;
  }
  if ( (v16[0] & 0x10) != 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const GUID *))ppv->lpVtbl->SetGuidValue)(
                 ppv,
                 &WPD_OBJECT_CONTENT_TYPE,
                 &WPD_CONTENT_TYPE_FOLDER);
    v9 = Instance;
    if ( Instance < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_27;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v11 = 201;
      goto LABEL_22;
    }
  }
  Instance = CContentFolder::_CreateContentItem(this, 1, ppv, 0, 0, 0, 0, (struct CONTENTITEM **)&pv);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    v12 = (struct _ITEMIDLIST *)pv;
    pv = 0;
    *a4 = v12;
    goto LABEL_27;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_23:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
        WPP_SF_d(v10[2], 203, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v9);
      goto LABEL_27;
    }
    v11 = 202;
LABEL_22:
    WPP_SF_d(v10[2], v11, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_23;
  }
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  CoTaskMemFree(pv);
  return v9;
}

```

## disassembly

```asm
0x180046d3c  push    rbp
0x180046d3e  push    rbx
0x180046d3f  push    rsi
0x180046d40  push    rdi
0x180046d41  push    r14
0x180046d43  push    r15
0x180046d45  lea     rbp, [rsp-1B8h]
0x180046d4d  sub     rsp, 2B8h
0x180046d54  mov     rax, cs:__security_cookie
0x180046d5b  xor     rax, rsp
0x180046d5e  mov     [rbp+1E0h+var_40], rax
0x180046d65  mov     rbx, r9
0x180046d68  mov     rsi, r8
0x180046d6b  mov     r14, rdx
0x180046d6e  mov     r15, rcx
0x180046d71  mov     [rsp+2E0h+pv], 0
0x180046d7a  mov     [rsp+2E0h+var_2A0], 0
0x180046d83  mov     qword ptr [r9], 0
0x180046d8a  lea     rax, [rsp+2E0h+var_2A0]
0x180046d8f  mov     [rsp+2E0h+ppv], rax; ppv
0x180046d94  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180046d9b  xor     edx, edx; pUnkOuter
0x180046d9d  lea     r8d, [rdx+1]; dwClsContext
0x180046da1  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180046da8  call    cs:__imp_CoCreateInstance
0x180046dae  mov     edi, eax
0x180046db0  test    eax, eax
0x180046db2  jns     short loc_180046DDF
0x180046db4  lea     rbx, WPP_GLOBAL_Control
0x180046dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180046dc2  cmp     rcx, rbx
0x180046dc5  jz      loc_180046F82
0x180046dcb  test    byte ptr [rcx+1Ch], 2
0x180046dcf  jz      loc_180046F4C
0x180046dd5  mov     edx, 0C6h
0x180046dda  jmp     loc_180046F32
0x180046ddf  mov     rcx, [rsp+2E0h+var_2A0]
0x180046de4  mov     rax, [rcx]
0x180046de7  mov     r8, r14
0x180046dea  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180046df1  mov     rax, [rax+38h]
0x180046df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dfa  mov     edi, eax
0x180046dfc  test    eax, eax
0x180046dfe  jns     short loc_180046E2B
0x180046e00  lea     rbx, WPP_GLOBAL_Control
0x180046e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e0e  cmp     rcx, rbx
0x180046e11  jz      loc_180046F82
0x180046e17  test    byte ptr [rcx+1Ch], 2
0x180046e1b  jz      loc_180046F4C
0x180046e21  mov     edx, 0C7h
0x180046e26  jmp     loc_180046F32
0x180046e2b  xor     edx, edx; Val
0x180046e2d  mov     r8d, 250h; Size
0x180046e33  lea     rcx, [rsp+2E0h+var_290]; void *
0x180046e38  call    memset_0
0x180046e3d  mov     rax, [rsi]
0x180046e40  lea     rdx, [rsp+2E0h+var_290]
0x180046e45  mov     rcx, rsi
0x180046e48  mov     rax, [rax+20h]
0x180046e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e51  mov     edi, eax
0x180046e53  test    eax, eax
0x180046e55  jns     short loc_180046E82
0x180046e57  lea     rbx, WPP_GLOBAL_Control
0x180046e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e65  cmp     rcx, rbx
0x180046e68  jz      loc_180046F82
0x180046e6e  test    byte ptr [rcx+1Ch], 2
0x180046e72  jz      loc_180046F4C
0x180046e78  mov     edx, 0C8h
0x180046e7d  jmp     loc_180046F32
0x180046e82  test    [rsp+2E0h+var_290], 10h
0x180046e87  jz      short loc_180046ED5
0x180046e89  mov     rcx, [rsp+2E0h+var_2A0]
0x180046e8e  mov     rax, [rcx]
0x180046e91  lea     r8, WPD_CONTENT_TYPE_FOLDER
0x180046e98  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x180046e9f  mov     rax, [rax+0D8h]
0x180046ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046eab  mov     edi, eax
0x180046ead  test    eax, eax
0x180046eaf  jns     short loc_180046ED5
0x180046eb1  lea     rbx, WPP_GLOBAL_Control
0x180046eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ebf  cmp     rcx, rbx
0x180046ec2  jz      loc_180046F82
0x180046ec8  test    byte ptr [rcx+1Ch], 2
0x180046ecc  jz      short loc_180046F4C
0x180046ece  mov     edx, 0C9h
0x180046ed3  jmp     short loc_180046F32
0x180046ed5  lea     rax, [rsp+2E0h+pv]
0x180046eda  mov     [rsp+2E0h+var_2A8], rax; struct CONTENTITEM **
0x180046edf  mov     [rsp+2E0h+var_2B0], 0; struct IPortableDeviceValues *
0x180046ee8  mov     [rsp+2E0h+var_2B8], 0; struct IPortableDeviceKeyCollection *
0x180046ef1  mov     [rsp+2E0h+ppv], 0; struct IPortableDevice *
0x180046efa  xor     r9d, r9d; unsigned __int16 *
0x180046efd  mov     r8, [rsp+2E0h+var_2A0]; struct IPortableDeviceValues *
0x180046f02  lea     edx, [r9+1]; int
0x180046f06  mov     rcx, r15; this
0x180046f09  call    ?_CreateContentItem@CContentFolder@@AEAAJHPEAUIPortableDeviceValues@@PEBGPEAUIPortableDevice@@PEAUIPortableDeviceKeyCollection@@0PEAPEFAUCONTENTITEM@@@Z; CContentFolder::_CreateContentItem(int,IPortableDeviceValues *,ushort const *,IPortableDevice *,IPortableDeviceKeyCollection *,IPortableDeviceValues *,CONTENTITEM * *)
0x180046f0e  mov     edi, eax
0x180046f10  test    eax, eax
0x180046f12  jns     short loc_180046F71
0x180046f14  lea     rbx, WPP_GLOBAL_Control
0x180046f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f22  cmp     rcx, rbx
0x180046f25  jz      short loc_180046F82
0x180046f27  test    byte ptr [rcx+1Ch], 2
0x180046f2b  jz      short loc_180046F4C
0x180046f2d  mov     edx, 0CAh
0x180046f32  mov     r9d, eax
0x180046f35  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180046f3c  mov     rcx, [rcx+10h]
0x180046f40  call    WPP_SF_d
0x180046f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f4c  cmp     rcx, rbx
0x180046f4f  jz      short loc_180046F82
0x180046f51  test    byte ptr [rcx+1Ch], 2
0x180046f55  jz      short loc_180046F82
0x180046f57  mov     edx, 0CBh
0x180046f5c  mov     r9d, edi
0x180046f5f  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180046f66  mov     rcx, [rcx+10h]
0x180046f6a  call    WPP_SF_d
0x180046f6f  jmp     short loc_180046F82
0x180046f71  mov     rax, [rsp+2E0h+pv]
0x180046f76  mov     [rsp+2E0h+pv], 0
0x180046f7f  mov     [rbx], rax
0x180046f82  lea     rcx, [rsp+2E0h+var_2A0]
0x180046f87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180046f8c  nop
0x180046f8d  mov     rcx, [rsp+2E0h+pv]; pv
0x180046f92  call    cs:__imp_CoTaskMemFree
0x180046f98  mov     eax, edi
0x180046f9a  mov     rcx, [rbp+1E0h+var_40]
0x180046fa1  xor     rcx, rsp; StackCookie
0x180046fa4  call    __security_check_cookie
0x180046fa9  add     rsp, 2B8h
0x180046fb0  pop     r15
0x180046fb2  pop     r14
0x180046fb4  pop     rdi
0x180046fb5  pop     rsi
0x180046fb6  pop     rbx
0x180046fb7  pop     rbp
0x180046fb8  retn
```
