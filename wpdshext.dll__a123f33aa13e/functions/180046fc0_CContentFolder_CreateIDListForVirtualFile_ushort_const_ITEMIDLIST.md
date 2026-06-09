# CContentFolder::_CreateIDListForVirtualFile(ushort const *,_ITEMIDLIST * *)

- ea: `0x180046fc0`
- end: `0x180047158`
- name: `?_CreateIDListForVirtualFile@CContentFolder@@AEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, const unsigned __int16 *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004200`

## callees

- `0x18000ff40`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180046fc0`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180047143`
- `ole32!CoTaskMemFree` at `0x180047143`
- `ole32!CoCreateInstance` at `0x18004700a`
- `ole32!CoCreateInstance` at `0x18004700a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentFolder::_CreateIDListForVirtualFile(
        CContentFolder *this,
        const unsigned __int16 *a2,
        struct _ITEMIDLIST **a3)
{
  int Instance; // eax
  unsigned int v7; // edi
  PVOID *v8; // rcx
  __int64 v9; // rdx
  struct _ITEMIDLIST *v10; // rax
  struct IPortableDeviceValues *v12; // [rsp+70h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v12 = 0;
  *a3 = 0;
  Instance = CoCreateInstance(
               &CLSID_PortableDeviceValues,
               0,
               1u,
               &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
               (LPVOID *)&v12);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v9 = 306;
    goto LABEL_13;
  }
  Instance = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const unsigned __int16 *))v12->lpVtbl->SetStringValue)(
               v12,
               &WPD_OBJECT_ORIGINAL_FILE_NAME,
               a2);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v9 = 307;
    goto LABEL_13;
  }
  Instance = CContentFolder::_CreateContentItem(this, 1, v12, 0, 0, 0, 0, (struct CONTENTITEM **)&pv);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    v10 = (struct _ITEMIDLIST *)pv;
    pv = 0;
    *a3 = v10;
    goto LABEL_18;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_14:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
        WPP_SF_d(v8[2], 309, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v7);
      goto LABEL_18;
    }
    v9 = 308;
LABEL_13:
    WPP_SF_d(v8[2], v9, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
LABEL_18:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  CoTaskMemFree(pv);
  return v7;
}

```

## disassembly

```asm
0x180046fc0  mov     r11, rsp
0x180046fc3  mov     [r11+8], rbx
0x180046fc7  push    rbp
0x180046fc8  push    rsi
0x180046fc9  push    rdi
0x180046fca  sub     rsp, 40h
0x180046fce  mov     rbx, r8
0x180046fd1  mov     rbp, rdx
0x180046fd4  mov     rsi, rcx
0x180046fd7  mov     qword ptr [r11+20h], 0
0x180046fdf  mov     qword ptr [r11+18h], 0
0x180046fe7  mov     qword ptr [r8], 0
0x180046fee  lea     rax, [r11+18h]
0x180046ff2  mov     [r11-38h], rax
0x180046ff6  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180046ffd  xor     edx, edx; pUnkOuter
0x180046fff  lea     r8d, [rdx+1]; dwClsContext
0x180047003  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x18004700a  call    cs:__imp_CoCreateInstance
0x180047010  mov     edi, eax
0x180047012  test    eax, eax
0x180047014  jns     short loc_180047041
0x180047016  lea     rbx, WPP_GLOBAL_Control
0x18004701d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047024  cmp     rcx, rbx
0x180047027  jz      loc_180047133
0x18004702d  test    byte ptr [rcx+1Ch], 2
0x180047031  jz      loc_1800470FD
0x180047037  mov     edx, 132h
0x18004703c  jmp     loc_1800470E3
0x180047041  mov     rcx, [rsp+58h+arg_10]
0x180047046  mov     rax, [rcx]
0x180047049  mov     r8, rbp
0x18004704c  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180047053  mov     rax, [rax+38h]
0x180047057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004705c  mov     edi, eax
0x18004705e  test    eax, eax
0x180047060  jns     short loc_180047086
0x180047062  lea     rbx, WPP_GLOBAL_Control
0x180047069  mov     rcx, cs:WPP_GLOBAL_Control
0x180047070  cmp     rcx, rbx
0x180047073  jz      loc_180047133
0x180047079  test    byte ptr [rcx+1Ch], 2
0x18004707d  jz      short loc_1800470FD
0x18004707f  mov     edx, 133h
0x180047084  jmp     short loc_1800470E3
0x180047086  lea     rax, [rsp+58h+pv]
0x18004708b  mov     [rsp+58h+var_20], rax; struct CONTENTITEM **
0x180047090  mov     [rsp+58h+var_28], 0; struct IPortableDeviceValues *
0x180047099  mov     [rsp+58h+var_30], 0; struct IPortableDeviceKeyCollection *
0x1800470a2  mov     [rsp+58h+var_38], 0; struct IPortableDevice *
0x1800470ab  xor     r9d, r9d; unsigned __int16 *
0x1800470ae  mov     r8, [rsp+58h+arg_10]; struct IPortableDeviceValues *
0x1800470b3  lea     edx, [r9+1]; int
0x1800470b7  mov     rcx, rsi; this
0x1800470ba  call    ?_CreateContentItem@CContentFolder@@AEAAJHPEAUIPortableDeviceValues@@PEBGPEAUIPortableDevice@@PEAUIPortableDeviceKeyCollection@@0PEAPEFAUCONTENTITEM@@@Z; CContentFolder::_CreateContentItem(int,IPortableDeviceValues *,ushort const *,IPortableDevice *,IPortableDeviceKeyCollection *,IPortableDeviceValues *,CONTENTITEM * *)
0x1800470bf  mov     edi, eax
0x1800470c1  test    eax, eax
0x1800470c3  jns     short loc_180047122
0x1800470c5  lea     rbx, WPP_GLOBAL_Control
0x1800470cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470d3  cmp     rcx, rbx
0x1800470d6  jz      short loc_180047133
0x1800470d8  test    byte ptr [rcx+1Ch], 2
0x1800470dc  jz      short loc_1800470FD
0x1800470de  mov     edx, 134h
0x1800470e3  mov     r9d, eax
0x1800470e6  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800470ed  mov     rcx, [rcx+10h]
0x1800470f1  call    WPP_SF_d
0x1800470f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470fd  cmp     rcx, rbx
0x180047100  jz      short loc_180047133
0x180047102  test    byte ptr [rcx+1Ch], 2
0x180047106  jz      short loc_180047133
0x180047108  mov     edx, 135h
0x18004710d  mov     r9d, edi
0x180047110  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180047117  mov     rcx, [rcx+10h]
0x18004711b  call    WPP_SF_d
0x180047120  jmp     short loc_180047133
0x180047122  mov     rax, [rsp+58h+pv]
0x180047127  mov     [rsp+58h+pv], 0
0x180047130  mov     [rbx], rax
0x180047133  lea     rcx, [rsp+58h+arg_10]
0x180047138  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004713d  nop
0x18004713e  mov     rcx, [rsp+58h+pv]; pv
0x180047143  call    cs:__imp_CoTaskMemFree
0x180047149  mov     eax, edi
0x18004714b  mov     rbx, [rsp+58h+arg_0]
0x180047150  add     rsp, 40h
0x180047154  pop     rdi
0x180047155  pop     rsi
0x180047156  pop     rbp
0x180047157  retn
```
