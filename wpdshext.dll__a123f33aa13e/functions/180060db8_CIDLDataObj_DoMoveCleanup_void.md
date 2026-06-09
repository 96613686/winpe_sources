# CIDLDataObj::_DoMoveCleanup(void)

- ea: `0x180060db8`
- end: `0x180061065`
- name: `?_DoMoveCleanup@CIDLDataObj@@AEAAXXZ`
- size: `685`
- prototype: `void __fastcall(CIDLDataObj *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800223b0`

## callees

- `0x180014dd0`
- `0x180024aa4`
- `0x1800285c8`
- `0x180029bac`
- `0x18002ff5c`
- `0x180060db8`
- `0x1800628cc`
- `0x180062e70`
- `0x18006b954`
- `0x18006bc1c`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180060e10`
- `ole32!CoCreateInstance` at `0x180060e10`
- `SHELL32!__imp_ILRemoveLastID` at `0x180060ff4`
- `SHELL32!__imp_ILRemoveLastID` at `0x180060ff4`
- `SHELL32!__imp_ILFree` at `0x18006100f`
- `SHELL32!__imp_ILFree` at `0x18006100f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CIDLDataObj::_DoMoveCleanup(CIDLDataObj *this)
{
  HRESULT Instance; // eax
  __int64 HIDA; // rax
  struct _IDA *v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  ITEMIDLIST *v8; // rbx
  BOOL v9; // edi
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+A8h] [rbp+38h] BYREF
  struct IPortableDevicePropVariantCollection *ppv; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+48h] BYREF

  v17 = 0;
  v18 = 0;
  v13 = 0;
  v21 = 0;
  v16 = 0;
  v15 = 0;
  ppv = 0;
  v14 = 0;
  Instance = CoCreateInstance(
               &CLSID_PortableDevicePropVariantCollection,
               0,
               1u,
               &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    HIDA = DataObj_GetHIDA(this, &v17);
    v4 = (struct _IDA *)HIDA;
    if ( !HIDA )
      goto LABEL_28;
    v5 = IDA_ILClone(HIDA, 0);
    v8 = (ITEMIDLIST *)v5;
    if ( !v5 )
    {
LABEL_27:
      ReleaseStgMediumHGLOBAL(v7, &v17);
      goto LABEL_28;
    }
    if ( (int)SHBindToIDList(v5, v6, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v13) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v21) >= 0 )
    {
      v9 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 48LL))(v13, &v15) >= 0
        && (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v15 + 32LL))(
             v15,
             &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS,
             &v16) >= 0 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v16 + 192LL))(
               v16,
               &WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED,
               &v19) >= 0 )
          v9 = v19 != 0;
      }
      v10 = CollectPersistentUniqueIDs(v4, ppv, !v9);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, struct IPortableDevicePropVariantCollection *, __int64 *))(*(_QWORD *)v21 + 72LL))(
                v21,
                ppv,
                &v14);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, BOOL, __int64, _QWORD))(*(_QWORD *)v21 + 64LL))(v21, v9, v14, 0);
          if ( v10 >= 0 )
            goto LABEL_26;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_26;
          v12 = 57;
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_26;
          v12 = 56;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_26;
        v12 = 55;
      }
      WPP_SF_d(v11[2], v12, &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids, (unsigned int)v10);
    }
LABEL_26:
    ChangeNotifyFreeSpace(v8);
    ILRemoveLastID(v8);
    ChangeNotify(4096, 0, v8, 0);
    ILFree(v8);
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)Instance);
LABEL_28:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
}

```

## disassembly

```asm
0x180060db8  push    rbp
0x180060dba  push    rbx
0x180060dbb  push    rsi
0x180060dbc  push    rdi
0x180060dbd  push    r15
0x180060dbf  mov     rbp, rsp
0x180060dc2  sub     rsp, 70h
0x180060dc6  mov     rbx, rcx
0x180060dc9  xorps   xmm0, xmm0
0x180060dcc  xor     eax, eax
0x180060dce  movups  [rbp+var_20], xmm0
0x180060dd2  mov     [rbp+var_10], rax
0x180060dd6  mov     [rbp+var_40], rax
0x180060dda  mov     [rbp+arg_18], rax
0x180060dde  mov     [rbp+var_28], rax
0x180060de2  mov     [rbp+var_30], rax
0x180060de6  mov     [rbp+arg_10], rax
0x180060dea  mov     [rbp+var_38], rax
0x180060dee  lea     rax, [rbp+arg_10]
0x180060df2  mov     [rsp+70h+ppv], rax; ppv
0x180060df7  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x180060dfe  mov     r15d, 1
0x180060e04  mov     r8d, r15d; dwClsContext
0x180060e07  xor     edx, edx; pUnkOuter
0x180060e09  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x180060e10  call    cs:__imp_CoCreateInstance
0x180060e16  test    eax, eax
0x180060e18  jns     short loc_180060E57
0x180060e1a  lea     rdx, WPP_GLOBAL_Control
0x180060e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e28  cmp     rcx, rdx
0x180060e2b  jz      loc_18006101F
0x180060e31  test    byte ptr [rcx+1Ch], 2
0x180060e35  jz      loc_18006101F
0x180060e3b  lea     edx, [r15+35h]
0x180060e3f  mov     r9d, eax
0x180060e42  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x180060e49  mov     rcx, [rcx+10h]
0x180060e4d  call    WPP_SF_d
0x180060e52  jmp     loc_18006101F
0x180060e57  lea     rdx, [rbp+var_20]
0x180060e5b  mov     rcx, rbx
0x180060e5e  call    DataObj_GetHIDA
0x180060e63  mov     rsi, rax
0x180060e66  test    rax, rax
0x180060e69  jz      loc_18006101F
0x180060e6f  xor     edx, edx
0x180060e71  mov     rcx, rax
0x180060e74  call    IDA_ILClone
0x180060e79  mov     rbx, rax
0x180060e7c  test    rax, rax
0x180060e7f  jz      loc_180061015
0x180060e85  lea     r9, [rbp+var_40]
0x180060e89  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x180060e90  mov     rcx, rax
0x180060e93  call    SHBindToIDList
0x180060e98  test    eax, eax
0x180060e9a  js      loc_180060FE9
0x180060ea0  mov     rcx, [rbp+var_40]
0x180060ea4  mov     rdx, [rcx]
0x180060ea7  mov     rax, [rdx+28h]
0x180060eab  lea     rdx, [rbp+arg_18]
0x180060eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060eb4  test    eax, eax
0x180060eb6  js      loc_180060FE9
0x180060ebc  xor     edi, edi
0x180060ebe  mov     rcx, [rbp+var_40]
0x180060ec2  mov     rax, [rcx]
0x180060ec5  lea     rdx, [rbp+var_30]
0x180060ec9  mov     rax, [rax+30h]
0x180060ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ed2  test    eax, eax
0x180060ed4  js      short loc_180060F21
0x180060ed6  mov     rcx, [rbp+var_30]
0x180060eda  mov     rax, [rcx]
0x180060edd  lea     r8, [rbp+var_28]
0x180060ee1  lea     rdx, WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS
0x180060ee8  mov     rax, [rax+20h]
0x180060eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ef1  test    eax, eax
0x180060ef3  js      short loc_180060F21
0x180060ef5  mov     [rbp+arg_8], edi
0x180060ef8  mov     rcx, [rbp+var_28]
0x180060efc  mov     rax, [rcx]
0x180060eff  lea     r8, [rbp+arg_8]
0x180060f03  lea     rdx, WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED
0x180060f0a  mov     rax, [rax+0C0h]
0x180060f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f16  test    eax, eax
0x180060f18  js      short loc_180060F21
0x180060f1a  cmp     [rbp+arg_8], edi
0x180060f1d  cmovnz  edi, r15d
0x180060f21  mov     r8d, edi
0x180060f24  xor     r8d, r15d; int
0x180060f27  mov     rdx, [rbp+arg_10]; struct IPortableDevicePropVariantCollection *
0x180060f2b  mov     rcx, rsi; struct _IDA *
0x180060f2e  call    ?CollectPersistentUniqueIDs@@YAJPEAU_IDA@@PEAUIPortableDevicePropVariantCollection@@H@Z; CollectPersistentUniqueIDs(_IDA *,IPortableDevicePropVariantCollection *,int)
0x180060f33  test    eax, eax
0x180060f35  jns     short loc_180060F5F
0x180060f37  lea     rdx, WPP_GLOBAL_Control
0x180060f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060f45  cmp     rcx, rdx
0x180060f48  jz      loc_180060FE9
0x180060f4e  test    byte ptr [rcx+1Ch], 2
0x180060f52  jz      loc_180060FE9
0x180060f58  mov     edx, 37h ; '7'
0x180060f5d  jmp     short loc_180060FD6
0x180060f5f  mov     rcx, [rbp+arg_18]
0x180060f63  mov     rax, [rcx]
0x180060f66  lea     r8, [rbp+var_38]
0x180060f6a  mov     rdx, [rbp+arg_10]
0x180060f6e  mov     rax, [rax+48h]
0x180060f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f77  test    eax, eax
0x180060f79  jns     short loc_180060F9B
0x180060f7b  lea     rdx, WPP_GLOBAL_Control
0x180060f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180060f89  cmp     rcx, rdx
0x180060f8c  jz      short loc_180060FE9
0x180060f8e  test    byte ptr [rcx+1Ch], 2
0x180060f92  jz      short loc_180060FE9
0x180060f94  mov     edx, 38h ; '8'
0x180060f99  jmp     short loc_180060FD6
0x180060f9b  mov     rcx, [rbp+arg_18]
0x180060f9f  mov     rax, [rcx]
0x180060fa2  xor     r9d, r9d
0x180060fa5  mov     r8, [rbp+var_38]
0x180060fa9  mov     edx, edi
0x180060fab  mov     rax, [rax+40h]
0x180060faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fb4  test    eax, eax
0x180060fb6  jns     short loc_180060FE9
0x180060fb8  lea     rdx, WPP_GLOBAL_Control
0x180060fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180060fc6  cmp     rcx, rdx
0x180060fc9  jz      short loc_180060FE9
0x180060fcb  test    byte ptr [rcx+1Ch], 2
0x180060fcf  jz      short loc_180060FE9
0x180060fd1  mov     edx, 39h ; '9'
0x180060fd6  mov     r9d, eax
0x180060fd9  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x180060fe0  mov     rcx, [rcx+10h]
0x180060fe4  call    WPP_SF_d
0x180060fe9  mov     rcx, rbx; struct _ITEMIDLIST *
0x180060fec  call    ?ChangeNotifyFreeSpace@@YAXPEFAU_ITEMIDLIST@@@Z; ChangeNotifyFreeSpace(_ITEMIDLIST *)
0x180060ff1  mov     rcx, rbx; pidl
0x180060ff4  call    cs:__imp_ILRemoveLastID
0x180060ffa  xor     r9d, r9d; dwItem2
0x180060ffd  mov     r8, rbx; dwItem1
0x180061000  xor     edx, edx; uFlags
0x180061002  mov     ecx, 1000h; wEventId
0x180061007  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18006100c  mov     rcx, rbx; pidl
0x18006100f  call    cs:__imp_ILFree
0x180061015  lea     rdx, [rbp+var_20]
0x180061019  call    ReleaseStgMediumHGLOBAL
0x18006101e  nop
0x18006101f  lea     rcx, [rbp+var_38]
0x180061023  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061028  nop
0x180061029  lea     rcx, [rbp+arg_10]
0x18006102d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061032  nop
0x180061033  lea     rcx, [rbp+var_30]
0x180061037  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006103c  nop
0x18006103d  lea     rcx, [rbp+var_28]
0x180061041  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061046  nop
0x180061047  lea     rcx, [rbp+arg_18]
0x18006104b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061050  nop
0x180061051  lea     rcx, [rbp+var_40]
0x180061055  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006105a  add     rsp, 70h
0x18006105e  pop     r15
0x180061060  pop     rdi
0x180061061  pop     rsi
0x180061062  pop     rbx
0x180061063  pop     rbp
0x180061064  retn
```
