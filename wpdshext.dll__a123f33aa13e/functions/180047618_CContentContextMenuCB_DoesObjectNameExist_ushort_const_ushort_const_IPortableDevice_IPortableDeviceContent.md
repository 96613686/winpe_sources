# CContentContextMenuCB::_DoesObjectNameExist(ushort const *,ushort const *,IPortableDevice *,IPortableDeviceContent *)

- ea: `0x180047618`
- end: `0x180047a2e`
- name: `?_DoesObjectNameExist@CContentContextMenuCB@@AEAAJPEBG0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@@Z`
- size: `1046`
- prototype: `int(CContentContextMenuCB *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IPortableDevice *, struct IPortableDeviceContent *)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800311d8`
- `0x18004673c`

## callees

- `0x180016260`
- `0x1800177dc`
- `0x1800285c8`
- `0x18002e870`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039d74`
- `0x180047618`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x1800478df`
- `SHLWAPI!StrCmpIW` at `0x180047909`
- `SHLWAPI!StrCmpIW` at `0x1800478df`
- `SHLWAPI!StrCmpIW` at `0x180047909`
- `ole32!CoTaskMemFree` at `0x180047947`
- `ole32!CoTaskMemFree` at `0x180047958`
- `ole32!CoTaskMemFree` at `0x180047987`
- `ole32!CoTaskMemFree` at `0x180047947`
- `ole32!CoTaskMemFree` at `0x180047958`
- `ole32!CoTaskMemFree` at `0x180047987`
- `ole32!CoCreateInstance` at `0x1800476f9`
- `ole32!CoCreateInstance` at `0x1800476f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContentContextMenuCB::_DoesObjectNameExist(
        CBaseFolder **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IPortableDevice *a4,
        struct IPortableDeviceContent *a5)
{
  WCHAR *v8; // r12
  HRESULT PortableDeviceProperties; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // r13
  int v14; // r15d
  struct IPortableDeviceProperties *v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // r14
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 i; // r14
  void *v22; // rcx
  unsigned int v24; // [rsp+30h] [rbp-A1h] BYREF
  struct IUnknown *v25; // [rsp+38h] [rbp-99h] BYREF
  PCWSTR psz1; // [rsp+40h] [rbp-91h]
  LPVOID ppv; // [rsp+48h] [rbp-89h] BYREF
  PCWSTR psz2; // [rsp+50h] [rbp-81h] BYREF
  struct IPortableDeviceProperties *v29; // [rsp+58h] [rbp-79h] BYREF
  __int64 v30; // [rsp+60h] [rbp-71h] BYREF
  struct _GUID v31; // [rsp+68h] [rbp-69h] BYREF
  LPVOID pv[10]; // [rsp+80h] [rbp-51h] BYREF

  psz1 = a2;
  v8 = 0;
  psz2 = 0;
  memset_0(pv, 0, sizeof(pv));
  v24 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  ppv = 0;
  v25 = 0;
  CBaseFolder::_GetParentFolderClassID(this[4], &v31);
  PortableDeviceProperties = GetPortableDeviceProperties(a4, &v29);
  v10 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_56;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v12 = 347;
    goto LABEL_13;
  }
  PortableDeviceProperties = CoCreateInstance(
                               &CLSID_PortableDeviceKeyCollection,
                               0,
                               1u,
                               &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
                               &ppv);
  v10 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_56;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v12 = 348;
    goto LABEL_13;
  }
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_NAME);
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ORIGINAL_FILE_NAME);
  PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, _QWORD, const unsigned __int16 *, _QWORD, __int64 *))a5->lpVtbl->EnumObjects)(
                               a5,
                               0,
                               a3,
                               0,
                               &v30);
  v10 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_56;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v12 = 349;
LABEL_13:
    WPP_SF_d(v11[2], v12, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
    v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_14:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_d(v11[2], 354, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v10);
    goto LABEL_56;
  }
  v13 = 0;
  v14 = 0;
  v15 = v29;
  do
  {
    if ( (*(int (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v30 + 24LL))(v30, 10, pv, &v24) < 0 )
      goto LABEL_53;
    v16 = v24;
    if ( !v24 )
      break;
    v17 = 0;
    do
    {
      v18 = (unsigned int)v17;
      if ( pv[v17] )
      {
        if ( v25 )
        {
          ATL::AtlComPtrAssign(&v25, 0);
          v18 = (unsigned int)v17;
        }
        if ( ((int (__fastcall *)(struct IPortableDeviceProperties *, LPVOID, LPVOID, struct IUnknown **))v15->lpVtbl->GetValues)(
               v15,
               pv[v18],
               ppv,
               &v25) < 0 )
          goto LABEL_43;
        if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v25->lpVtbl[2].Release)(
               v25,
               &WPD_OBJECT_NAME,
               &psz2) >= 0 )
          v13 = (WCHAR *)psz2;
        if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v25->lpVtbl[2].Release)(
               v25,
               &WPD_OBJECT_ORIGINAL_FILE_NAME,
               &psz2) >= 0 )
          v8 = (WCHAR *)psz2;
        if ( v8 )
        {
          if ( StrCmpIW(psz1, v8) )
            goto LABEL_39;
          v14 = 1;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_39;
          v20 = 350;
        }
        else
        {
          if ( StrCmpIW(psz1, v13) )
            goto LABEL_39;
          v14 = 1;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_39;
          v20 = 351;
        }
        WPP_SF_S(v19[2], v20, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, psz1);
LABEL_39:
        if ( v13 )
        {
          CoTaskMemFree(v13);
          v13 = 0;
        }
        if ( v8 )
        {
          CoTaskMemFree(v8);
          v8 = 0;
        }
LABEL_43:
        v16 = v24;
      }
      if ( v14 )
        break;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < v16 );
    for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
    {
      v22 = pv[i];
      if ( v22 )
      {
        CoTaskMemFree(v22);
        pv[i] = 0;
        v16 = v24;
      }
    }
  }
  while ( !v14 );
  if ( v14 == 1 )
  {
    v10 = 0;
    goto LABEL_56;
  }
LABEL_53:
  v10 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 353, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, psz1);
LABEL_56:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  return v10;
}

```

## disassembly

```asm
0x180047618  push    rbp
0x18004761a  push    rbx
0x18004761b  push    rsi
0x18004761c  push    rdi
0x18004761d  push    r12
0x18004761f  push    r13
0x180047621  push    r14
0x180047623  push    r15
0x180047625  lea     rbp, [rsp-17h]
0x18004762a  sub     rsp, 0E8h
0x180047631  mov     rax, cs:__security_cookie
0x180047638  xor     rax, rsp
0x18004763b  mov     [rbp+4Fh+var_50], rax
0x18004763f  mov     rdi, r9
0x180047642  mov     r15, r8
0x180047645  mov     [rsp+120h+psz1], rdx
0x18004764a  mov     rbx, rcx
0x18004764d  mov     r14, [rbp+4Fh+arg_20]
0x180047651  xor     r12d, r12d
0x180047654  mov     [rsp+120h+psz2], r12
0x180047659  xor     edx, edx; Val
0x18004765b  lea     r8d, [r12+50h]; Size
0x180047660  lea     rcx, [rbp+4Fh+pv]; void *
0x180047664  call    memset_0
0x180047669  mov     [rsp+120h+var_F0], r12d
0x18004766e  xorps   xmm0, xmm0
0x180047671  movups  xmmword ptr [rbp+4Fh+var_B8.Data1], xmm0
0x180047675  mov     [rbp+4Fh+var_C0], r12
0x180047679  mov     [rbp+4Fh+var_C8], r12
0x18004767d  mov     [rsp+120h+var_D8], r12
0x180047682  mov     [rsp+120h+var_E8], r12
0x180047687  lea     rdx, [rbp+4Fh+var_B8]; struct _GUID *
0x18004768b  mov     rcx, [rbx+20h]; this
0x18004768f  call    ?_GetParentFolderClassID@CBaseFolder@@IEAAJPEAU_GUID@@@Z; CBaseFolder::_GetParentFolderClassID(_GUID *)
0x180047694  lea     rdx, [rbp+4Fh+var_C8]; struct IPortableDeviceProperties **
0x180047698  mov     rcx, rdi; struct IPortableDevice *
0x18004769b  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x1800476a0  mov     ebx, eax
0x1800476a2  mov     r13b, 2
0x1800476a5  lea     rsi, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800476ac  test    eax, eax
0x1800476ae  jns     short loc_1800476DB
0x1800476b0  lea     rdi, WPP_GLOBAL_Control
0x1800476b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800476be  cmp     rcx, rdi
0x1800476c1  jz      loc_1800479E3
0x1800476c7  test    [rcx+1Ch], r13b
0x1800476cb  jz      loc_1800477BB
0x1800476d1  mov     edx, 15Bh
0x1800476d6  jmp     loc_1800477A5
0x1800476db  lea     rax, [rsp+120h+var_D8]
0x1800476e0  mov     [rsp+120h+ppv], rax; ppv
0x1800476e5  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x1800476ec  xor     edx, edx; pUnkOuter
0x1800476ee  lea     r8d, [rdx+1]; dwClsContext
0x1800476f2  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x1800476f9  call    cs:__imp_CoCreateInstance
0x1800476ff  mov     ebx, eax
0x180047701  test    eax, eax
0x180047703  jns     short loc_18004772D
0x180047705  lea     rdi, WPP_GLOBAL_Control
0x18004770c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047713  cmp     rcx, rdi
0x180047716  jz      loc_1800479E3
0x18004771c  test    [rcx+1Ch], r13b
0x180047720  jz      loc_1800477BB
0x180047726  mov     edx, 15Ch
0x18004772b  jmp     short loc_1800477A5
0x18004772d  mov     rcx, [rsp+120h+var_D8]
0x180047732  mov     rax, [rcx]
0x180047735  lea     rdx, WPD_OBJECT_NAME
0x18004773c  mov     rax, [rax+28h]
0x180047740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047745  mov     rcx, [rsp+120h+var_D8]
0x18004774a  mov     rax, [rcx]
0x18004774d  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180047754  mov     rax, [rax+28h]
0x180047758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004775d  mov     rax, [r14]
0x180047760  lea     rcx, [rbp+4Fh+var_C0]
0x180047764  mov     [rsp+120h+ppv], rcx
0x180047769  xor     r9d, r9d
0x18004776c  mov     r8, r15
0x18004776f  xor     edx, edx
0x180047771  mov     rcx, r14
0x180047774  mov     rax, [rax+18h]
0x180047778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004777d  mov     ebx, eax
0x18004777f  test    eax, eax
0x180047781  jns     short loc_1800477E7
0x180047783  lea     rdi, WPP_GLOBAL_Control
0x18004778a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047791  cmp     rcx, rdi
0x180047794  jz      loc_1800479E3
0x18004779a  test    [rcx+1Ch], r13b
0x18004779e  jz      short loc_1800477BB
0x1800477a0  mov     edx, 15Dh
0x1800477a5  mov     r9d, eax
0x1800477a8  mov     r8, rsi
0x1800477ab  mov     rcx, [rcx+10h]
0x1800477af  call    WPP_SF_d
0x1800477b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800477bb  cmp     rcx, rdi
0x1800477be  jz      loc_1800479E3
0x1800477c4  test    [rcx+1Ch], r13b
0x1800477c8  jz      loc_1800479E3
0x1800477ce  mov     edx, 162h
0x1800477d3  mov     r9d, ebx
0x1800477d6  mov     r8, rsi
0x1800477d9  mov     rcx, [rcx+10h]
0x1800477dd  call    WPP_SF_d
0x1800477e2  jmp     loc_1800479E3
0x1800477e7  mov     r13, r12
0x1800477ea  xor     r15d, r15d
0x1800477ed  lea     rdi, WPP_GLOBAL_Control
0x1800477f4  lea     rsi, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800477fb  mov     rbx, [rbp+4Fh+var_C8]
0x1800477ff  mov     rcx, [rbp+4Fh+var_C0]
0x180047803  mov     rax, [rcx]
0x180047806  lea     r9, [rsp+120h+var_F0]
0x18004780b  lea     r8, [rbp+4Fh+pv]
0x18004780f  mov     edx, 0Ah
0x180047814  mov     rax, [rax+18h]
0x180047818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004781d  test    eax, eax
0x18004781f  js      loc_1800479B5
0x180047825  mov     eax, [rsp+120h+var_F0]
0x180047829  test    eax, eax
0x18004782b  jz      loc_1800479AB
0x180047831  xor     r14d, r14d
0x180047834  test    eax, eax
0x180047836  jz      loc_180047976
0x18004783c  mov     ecx, r14d
0x18004783f  cmp     [rbp+r14*8+4Fh+pv], 0
0x180047845  jz      loc_180047965
0x18004784b  cmp     [rsp+120h+var_E8], 0
0x180047851  jz      short loc_180047862
0x180047853  xor     edx, edx; struct IUnknown *
0x180047855  lea     rcx, [rsp+120h+var_E8]; struct IUnknown **
0x18004785a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004785f  mov     ecx, r14d
0x180047862  mov     rax, [rbx]
0x180047865  lea     r9, [rsp+120h+var_E8]
0x18004786a  mov     r8, [rsp+120h+var_D8]
0x18004786f  mov     rdx, [rbp+rcx*8+4Fh+pv]
0x180047874  mov     rcx, rbx
0x180047877  mov     rax, [rax+28h]
0x18004787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047880  test    eax, eax
0x180047882  js      loc_180047961
0x180047888  mov     rcx, [rsp+120h+var_E8]
0x18004788d  mov     rax, [rcx]
0x180047890  lea     r8, [rsp+120h+psz2]
0x180047895  lea     rdx, WPD_OBJECT_NAME
0x18004789c  mov     rax, [rax+40h]
0x1800478a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478a5  test    eax, eax
0x1800478a7  cmovns  r13, [rsp+120h+psz2]
0x1800478ad  mov     rcx, [rsp+120h+var_E8]
0x1800478b2  mov     rax, [rcx]
0x1800478b5  lea     r8, [rsp+120h+psz2]
0x1800478ba  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x1800478c1  mov     rax, [rax+40h]
0x1800478c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478ca  test    eax, eax
0x1800478cc  cmovns  r12, [rsp+120h+psz2]
0x1800478d2  mov     rcx, [rsp+120h+psz1]; psz1
0x1800478d7  test    r12, r12
0x1800478da  jz      short loc_180047906
0x1800478dc  mov     rdx, r12; psz2
0x1800478df  call    cs:__imp_StrCmpIW
0x1800478e5  test    eax, eax
0x1800478e7  jnz     short loc_18004793F
0x1800478e9  lea     r15d, [rax+1]
0x1800478ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478f4  cmp     rcx, rdi
0x1800478f7  jz      short loc_18004793F
0x1800478f9  test    byte ptr [rcx+1Ch], 40h
0x1800478fd  jz      short loc_18004793F
0x1800478ff  mov     edx, 15Eh
0x180047904  jmp     short loc_18004792E
0x180047906  mov     rdx, r13; psz2
0x180047909  call    cs:__imp_StrCmpIW
0x18004790f  test    eax, eax
0x180047911  jnz     short loc_18004793F
0x180047913  lea     r15d, [rax+1]
0x180047917  mov     rcx, cs:WPP_GLOBAL_Control
0x18004791e  cmp     rcx, rdi
0x180047921  jz      short loc_18004793F
0x180047923  test    byte ptr [rcx+1Ch], 40h
0x180047927  jz      short loc_18004793F
0x180047929  mov     edx, 15Fh
0x18004792e  mov     r9, [rsp+120h+psz1]
0x180047933  mov     r8, rsi
0x180047936  mov     rcx, [rcx+10h]
0x18004793a  call    WPP_SF_S
0x18004793f  test    r13, r13
0x180047942  jz      short loc_180047950
0x180047944  mov     rcx, r13; pv
0x180047947  call    cs:__imp_CoTaskMemFree
0x18004794d  xor     r13d, r13d
0x180047950  test    r12, r12
0x180047953  jz      short loc_180047961
0x180047955  mov     rcx, r12; pv
0x180047958  call    cs:__imp_CoTaskMemFree
0x18004795e  xor     r12d, r12d
0x180047961  mov     eax, [rsp+120h+var_F0]
0x180047965  test    r15d, r15d
0x180047968  jnz     short loc_180047976
0x18004796a  inc     r14d
0x18004796d  cmp     r14d, eax
0x180047970  jb      loc_18004783C
0x180047976  xor     r14d, r14d
0x180047979  test    eax, eax
0x18004797b  jz      short loc_1800479A2
0x18004797d  mov     rcx, [rbp+r14*8+4Fh+pv]; pv
0x180047982  test    rcx, rcx
0x180047985  jz      short loc_18004799A
0x180047987  call    cs:__imp_CoTaskMemFree
0x18004798d  mov     [rbp+r14*8+4Fh+pv], 0
0x180047996  mov     eax, [rsp+120h+var_F0]
0x18004799a  inc     r14d
0x18004799d  cmp     r14d, eax
0x1800479a0  jb      short loc_18004797D
0x1800479a2  test    r15d, r15d
0x1800479a5  jz      loc_1800477FF
0x1800479ab  cmp     r15d, 1
0x1800479af  jnz     short loc_1800479B5
0x1800479b1  xor     ebx, ebx
0x1800479b3  jmp     short loc_1800479E3
0x1800479b5  mov     ebx, 1
0x1800479ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800479c1  cmp     rcx, rdi
0x1800479c4  jz      short loc_1800479E3
0x1800479c6  test    byte ptr [rcx+1Ch], 40h
0x1800479ca  jz      short loc_1800479E3
0x1800479cc  mov     edx, 161h
0x1800479d1  mov     r9, [rsp+120h+psz1]
0x1800479d6  mov     r8, rsi
0x1800479d9  mov     rcx, [rcx+10h]
0x1800479dd  call    WPP_SF_S
0x1800479e2  nop
0x1800479e3  lea     rcx, [rsp+120h+var_E8]
0x1800479e8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800479ed  nop
0x1800479ee  lea     rcx, [rsp+120h+var_D8]
0x1800479f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800479f8  nop
0x1800479f9  lea     rcx, [rbp+4Fh+var_C8]
0x1800479fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a02  nop
0x180047a03  lea     rcx, [rbp+4Fh+var_C0]
0x180047a07  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047a0c  mov     eax, ebx
0x180047a0e  mov     rcx, [rbp+4Fh+var_50]
0x180047a12  xor     rcx, rsp; StackCookie
0x180047a15  call    __security_check_cookie
0x180047a1a  add     rsp, 0E8h
0x180047a21  pop     r15
0x180047a23  pop     r14
0x180047a25  pop     r13
0x180047a27  pop     r12
0x180047a29  pop     rdi
0x180047a2a  pop     rsi
0x180047a2b  pop     rbx
0x180047a2c  pop     rbp
0x180047a2d  retn
```
