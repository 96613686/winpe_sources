# CContentDropTarget::_DeleteExistingObject(IPortableDevice *,ushort const *,int,CProgressUI *)

- ea: `0x18003b8e4`
- end: `0x18003bbff`
- name: `?_DeleteExistingObject@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEBGHPEAVCProgressUI@@@Z`
- size: `795`
- prototype: `int(CContentDropTarget *__hidden this, struct IPortableDevice *, const unsigned __int16 *, int, struct CProgressUI *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ab88`
- `0x18003bc08`
- `0x18003c878`

## callees

- `0x180016260`
- `0x1800285c8`
- `0x18002ff5c`
- `0x18003b8e4`
- `0x180047160`
- `0x180054524`
- `0x1800545c8`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003baae`
- `KERNEL32!Sleep` at `0x18003baae`
- `ole32!CoCreateInstance` at `0x18003b9c0`
- `ole32!CoCreateInstance` at `0x18003b9c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CContentDropTarget::_DeleteExistingObject(
        CContentDropTarget *this,
        struct IPortableDevice *a2,
        const unsigned __int16 *a3,
        int a4,
        struct CProgressUI *a5)
{
  HRESULT PortableDeviceProperties; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  struct CProgressUI *v11; // rdi
  int v12; // r14d
  int v13; // esi
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int v17; // ebx
  CContentFolder *v18; // rcx
  int v19; // eax
  struct IPortableDeviceProperties *v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h] BYREF
  __int64 v24; // [rsp+48h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  int v26; // [rsp+98h] [rbp+48h] BYREF

  ppv = this;
  v23 = 0;
  v24 = 0;
  if ( !a4 )
  {
    v21 = 0;
    ppv = 0;
    v22 = 0;
    PortableDeviceProperties = GetPortableDeviceProperties(a2, &v21);
    v8 = PortableDeviceProperties;
    if ( PortableDeviceProperties < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_7;
      v10 = 177;
LABEL_6:
      WPP_SF_d(v9[2], v10, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)PortableDeviceProperties);
LABEL_7:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
LABEL_41:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_42;
    }
    PortableDeviceProperties = CoCreateInstance(
                                 &CLSID_PortableDeviceValues,
                                 0,
                                 1u,
                                 &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                                 &ppv);
    v8 = PortableDeviceProperties;
    if ( PortableDeviceProperties < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_7;
      v10 = 178;
      goto LABEL_6;
    }
    if ( (*(int (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)ppv + 184LL))(
           ppv,
           &WPD_OBJECT_CAN_DELETE,
           1) >= 0 )
      ((void (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, LPVOID, __int64 *))v21->lpVtbl->SetValues)(
        v21,
        a3,
        ppv,
        &v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  }
  v11 = a5;
  if ( a5 )
  {
    v12 = 0;
    v13 = 0;
    while ( !*((_DWORD *)v11 + 26) )
    {
      v8 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a2->lpVtbl->Capabilities)(a2, &v23);
      if ( v8 != -2147024726 )
        goto LABEL_25;
      if ( !v12 )
      {
        v12 = 1;
        v13 = 1;
        CProgressUI::_StartMarquee(v11);
      }
      if ( *((_DWORD *)v11 + 26) )
        break;
      Sleep(0x5DCu);
    }
    v8 = -2147023673;
LABEL_25:
    if ( v13 )
      CProgressUI::_StopMarquee(v11);
    if ( *((_DWORD *)v11 + 26) )
    {
      v8 = -2147023673;
LABEL_30:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_45;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_42;
      v15 = 179;
      v16 = v8;
LABEL_40:
      WPP_SF_d(v14[2], v15, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v16);
      goto LABEL_41;
    }
  }
  else
  {
    v8 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a2->lpVtbl->Capabilities)(a2, &v23);
  }
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_30;
  v17 = 0;
  if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v23 + 32LL))(
         v23,
         &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS,
         &v24) >= 0 )
  {
    v26 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v24 + 192LL))(
           v24,
           &WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED,
           &v26) >= 0 )
      v17 = v26 != 0;
  }
  v19 = CContentFolder::_DeleteObject(v18, a2, a3, v17, v11);
  v8 = v19;
  if ( v19 < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_42:
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
          WPP_SF_d(v14[2], 181, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v8);
        goto LABEL_45;
      }
      v15 = 180;
      v16 = (unsigned int)v19;
      goto LABEL_40;
    }
  }
LABEL_45:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  return v8;
}

```

## disassembly

```asm
0x18003b8e4  mov     [rsp-28h+arg_8], rbx
0x18003b8e9  mov     [rsp-28h+arg_10], rsi
0x18003b8ee  mov     [rsp-28h+arg_0], rcx
0x18003b8f3  push    rbp
0x18003b8f4  push    rdi
0x18003b8f5  push    r12
0x18003b8f7  push    r14
0x18003b8f9  push    r15
0x18003b8fb  mov     rbp, rsp
0x18003b8fe  sub     rsp, 50h
0x18003b902  mov     r12, r8
0x18003b905  mov     r15, rdx
0x18003b908  mov     [rbp+var_10], 0
0x18003b910  mov     [rbp+var_8], 0
0x18003b918  mov     esi, 1
0x18003b91d  test    r9d, r9d
0x18003b920  jnz     loc_18003BA46
0x18003b926  mov     [rbp+var_20], 0
0x18003b92e  mov     [rbp+arg_0], 0
0x18003b936  mov     [rbp+var_18], 0
0x18003b93e  lea     rdx, [rbp+var_20]; struct IPortableDeviceProperties **
0x18003b942  mov     rcx, r15; struct IPortableDevice *
0x18003b945  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x18003b94a  mov     ebx, eax
0x18003b94c  test    eax, eax
0x18003b94e  jns     short loc_18003B9A4
0x18003b950  lea     rdi, WPP_GLOBAL_Control
0x18003b957  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b95e  cmp     rcx, rdi
0x18003b961  jz      short loc_18003B982
0x18003b963  test    byte ptr [rcx+1Ch], 2
0x18003b967  jz      short loc_18003B982
0x18003b969  mov     edx, 0B1h
0x18003b96e  mov     r9d, eax
0x18003b971  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003b978  mov     rcx, [rcx+10h]
0x18003b97c  call    WPP_SF_d
0x18003b981  nop
0x18003b982  lea     rcx, [rbp+var_18]
0x18003b986  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b98b  nop
0x18003b98c  lea     rcx, [rbp+arg_0]
0x18003b990  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b995  nop
0x18003b996  lea     rcx, [rbp+var_20]
0x18003b99a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b99f  jmp     loc_18003BBA6
0x18003b9a4  lea     rax, [rbp+arg_0]
0x18003b9a8  mov     [rsp+50h+ppv], rax; ppv
0x18003b9ad  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x18003b9b4  mov     r8d, esi; dwClsContext
0x18003b9b7  xor     edx, edx; pUnkOuter
0x18003b9b9  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x18003b9c0  call    cs:__imp_CoCreateInstance
0x18003b9c6  mov     ebx, eax
0x18003b9c8  test    eax, eax
0x18003b9ca  jns     short loc_18003B9EC
0x18003b9cc  lea     rdi, WPP_GLOBAL_Control
0x18003b9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9da  cmp     rcx, rdi
0x18003b9dd  jz      short loc_18003B982
0x18003b9df  test    byte ptr [rcx+1Ch], 2
0x18003b9e3  jz      short loc_18003B982
0x18003b9e5  mov     edx, 0B2h
0x18003b9ea  jmp     short loc_18003B96E
0x18003b9ec  mov     rcx, [rbp+arg_0]
0x18003b9f0  mov     rax, [rcx]
0x18003b9f3  mov     r8d, esi
0x18003b9f6  lea     rdx, WPD_OBJECT_CAN_DELETE
0x18003b9fd  mov     rax, [rax+0B8h]
0x18003ba04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba09  test    eax, eax
0x18003ba0b  js      short loc_18003BA29
0x18003ba0d  mov     rcx, [rbp+var_20]
0x18003ba11  mov     rax, [rcx]
0x18003ba14  lea     r9, [rbp+var_18]
0x18003ba18  mov     r8, [rbp+arg_0]
0x18003ba1c  mov     rdx, r12
0x18003ba1f  mov     rax, [rax+30h]
0x18003ba23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba28  nop
0x18003ba29  lea     rcx, [rbp+var_18]
0x18003ba2d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ba32  nop
0x18003ba33  lea     rcx, [rbp+arg_0]
0x18003ba37  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ba3c  nop
0x18003ba3d  lea     rcx, [rbp+var_20]
0x18003ba41  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ba46  mov     rdi, [rbp+arg_20]
0x18003ba4a  test    rdi, rdi
0x18003ba4d  jnz     short loc_18003BA66
0x18003ba4f  mov     rax, [r15]
0x18003ba52  lea     rdx, [rbp+var_10]
0x18003ba56  mov     rcx, r15
0x18003ba59  mov     rax, [rax+30h]
0x18003ba5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba62  mov     ebx, eax
0x18003ba64  jmp     short loc_18003BADE
0x18003ba66  xor     r14d, r14d
0x18003ba69  xor     esi, esi
0x18003ba6b  cmp     dword ptr [rdi+68h], 0
0x18003ba6f  jnz     short loc_18003BABB
0x18003ba71  mov     rax, [r15]
0x18003ba74  lea     rdx, [rbp+var_10]
0x18003ba78  mov     rcx, r15
0x18003ba7b  mov     rax, [rax+30h]
0x18003ba7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba84  mov     ebx, eax
0x18003ba86  cmp     eax, 800700AAh
0x18003ba8b  jnz     short loc_18003BAC0
0x18003ba8d  test    r14d, r14d
0x18003ba90  jnz     short loc_18003BAA3
0x18003ba92  lea     eax, [r14+1]
0x18003ba96  mov     r14d, eax
0x18003ba99  mov     esi, eax
0x18003ba9b  mov     rcx, rdi; this
0x18003ba9e  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003baa3  cmp     dword ptr [rdi+68h], 0
0x18003baa7  jnz     short loc_18003BABB
0x18003baa9  mov     ecx, 5DCh; dwMilliseconds
0x18003baae  call    cs:__imp_Sleep
0x18003bab4  test    r14d, r14d
0x18003bab7  jz      short loc_18003BAC0
0x18003bab9  jmp     short loc_18003BA6B
0x18003babb  mov     ebx, 800704C7h
0x18003bac0  test    esi, esi
0x18003bac2  jz      short loc_18003BACC
0x18003bac4  mov     rcx, rdi; this
0x18003bac7  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003bacc  cmp     dword ptr [rdi+68h], 0
0x18003bad0  jz      short loc_18003BAD9
0x18003bad2  mov     ebx, 800704C7h
0x18003bad7  jmp     short loc_18003BAE2
0x18003bad9  mov     esi, 1
0x18003bade  test    ebx, ebx
0x18003bae0  jns     short loc_18003BB10
0x18003bae2  lea     rdi, WPP_GLOBAL_Control
0x18003bae9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003baf0  cmp     rcx, rdi
0x18003baf3  jz      loc_18003BBD1
0x18003baf9  test    byte ptr [rcx+1Ch], 2
0x18003bafd  jz      loc_18003BBAD
0x18003bb03  mov     edx, 0B3h
0x18003bb08  mov     r9d, ebx
0x18003bb0b  jmp     loc_18003BB96
0x18003bb10  xor     ebx, ebx
0x18003bb12  mov     rcx, [rbp+var_10]
0x18003bb16  mov     rax, [rcx]
0x18003bb19  lea     r8, [rbp+var_8]
0x18003bb1d  lea     rdx, WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS
0x18003bb24  mov     rax, [rax+20h]
0x18003bb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb2d  test    eax, eax
0x18003bb2f  js      short loc_18003BB5C
0x18003bb31  mov     [rbp+arg_18], ebx
0x18003bb34  mov     rcx, [rbp+var_8]
0x18003bb38  mov     rax, [rcx]
0x18003bb3b  lea     r8, [rbp+arg_18]
0x18003bb3f  lea     rdx, WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED
0x18003bb46  mov     rax, [rax+0C0h]
0x18003bb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb52  test    eax, eax
0x18003bb54  js      short loc_18003BB5C
0x18003bb56  cmp     [rbp+arg_18], ebx
0x18003bb59  cmovnz  ebx, esi
0x18003bb5c  mov     [rsp+50h+ppv], rdi; struct CProgressUI *
0x18003bb61  mov     r9d, ebx; unsigned int
0x18003bb64  mov     r8, r12; unsigned __int16 *
0x18003bb67  mov     rdx, r15; struct IPortableDevice *
0x18003bb6a  call    ?_DeleteObject@CContentFolder@@AEAAJPEAUIPortableDevice@@PEBGKPEAVCProgressUI@@@Z; CContentFolder::_DeleteObject(IPortableDevice *,ushort const *,ulong,CProgressUI *)
0x18003bb6f  mov     ebx, eax
0x18003bb71  test    eax, eax
0x18003bb73  jns     short loc_18003BBD1
0x18003bb75  lea     rdi, WPP_GLOBAL_Control
0x18003bb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb83  cmp     rcx, rdi
0x18003bb86  jz      short loc_18003BBD1
0x18003bb88  test    byte ptr [rcx+1Ch], 2
0x18003bb8c  jz      short loc_18003BBAD
0x18003bb8e  mov     edx, 0B4h
0x18003bb93  mov     r9d, eax
0x18003bb96  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003bb9d  mov     rcx, [rcx+10h]
0x18003bba1  call    WPP_SF_d
0x18003bba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bbad  cmp     rcx, rdi
0x18003bbb0  jz      short loc_18003BBD1
0x18003bbb2  test    byte ptr [rcx+1Ch], 2
0x18003bbb6  jz      short loc_18003BBD1
0x18003bbb8  mov     edx, 0B5h
0x18003bbbd  mov     r9d, ebx
0x18003bbc0  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003bbc7  mov     rcx, [rcx+10h]
0x18003bbcb  call    WPP_SF_d
0x18003bbd0  nop
0x18003bbd1  lea     rcx, [rbp+var_8]
0x18003bbd5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bbda  nop
0x18003bbdb  lea     rcx, [rbp+var_10]
0x18003bbdf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bbe4  mov     eax, ebx
0x18003bbe6  lea     r11, [rsp+50h+var_s0]
0x18003bbeb  mov     rbx, [r11+38h]
0x18003bbef  mov     rsi, [r11+40h]
0x18003bbf3  mov     rsp, r11
0x18003bbf6  pop     r15
0x18003bbf8  pop     r14
0x18003bbfa  pop     r12
0x18003bbfc  pop     rdi
0x18003bbfd  pop     rbp
0x18003bbfe  retn
```
