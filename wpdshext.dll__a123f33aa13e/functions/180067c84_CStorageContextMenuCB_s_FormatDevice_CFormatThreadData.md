# CStorageContextMenuCB::s_FormatDevice(CFormatThreadData *)

- ea: `0x180067c84`
- end: `0x180068078`
- name: `?s_FormatDevice@CStorageContextMenuCB@@CAKPEAVCFormatThreadData@@@Z`
- size: `1012`
- prototype: `unsigned int __fastcall(struct CFormatThreadData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800684e0`

## callees

- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x180067748`
- `0x180067c84`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `USER32!SendMessageW` at `0x180067ce8`
- `USER32!SendMessageW` at `0x180067fc2`
- `USER32!SendMessageW` at `0x180067ce8`
- `USER32!SendMessageW` at `0x180067fc2`
- `USER32!GetDlgItem` at `0x180067cd0`
- `USER32!GetDlgItem` at `0x180067cd0`
- `USER32!PostMessageW` at `0x180068025`
- `USER32!PostMessageW` at `0x180068025`
- `ole32!CoCreateInstance` at `0x180067da2`
- `ole32!CoCreateInstance` at `0x180067da2`
- `SHELL32!__imp_ILCombine` at `0x180067fd4`
- `SHELL32!__imp_ILCombine` at `0x180067fd4`
- `SHELL32!__imp_ILFree` at `0x180068010`
- `SHELL32!__imp_ILFree` at `0x180068010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageContextMenuCB::s_FormatDevice(struct CFormatThreadData *a1)
{
  HWND DlgItem; // rdi
  HRESULT StorageObjectID; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  LPITEMIDLIST v6; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v12[264]; // [rsp+50h] [rbp-B0h] BYREF

  v11 = 0;
  ppv = 0;
  v10 = 0;
  DlgItem = GetDlgItem(*((HWND *)a1 + 3), 301);
  SendMessageW(DlgItem, 0x40Au, 1u, 0);
  StorageObjectID = CStorageFolder::_GetStorageObjectID(
                      *((CStorageFolder **)a1 + 1),
                      *((const struct STORAGEITEM **)a1 + 2),
                      v12,
                      0x104u);
  if ( StorageObjectID >= 0 )
  {
    StorageObjectID = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)a1 + 1) + 136LL))(
                        *((_QWORD *)a1 + 1),
                        *(_QWORD *)(*((_QWORD *)a1 + 1) + 64LL),
                        &v11);
    if ( StorageObjectID >= 0 )
    {
      StorageObjectID = CoCreateInstance(
                          &CLSID_PortableDeviceValues,
                          0,
                          1u,
                          &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                          &ppv);
      if ( StorageObjectID >= 0 )
      {
        StorageObjectID = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const PROPERTYKEY *))(*(_QWORD *)ppv + 216LL))(
                            ppv,
                            &WPD_PROPERTY_COMMON_COMMAND_CATEGORY,
                            &WPD_COMMAND_STORAGE_FORMAT);
        if ( StorageObjectID >= 0 )
        {
          StorageObjectID = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)ppv + 72LL))(
                              ppv,
                              &WPD_PROPERTY_COMMON_COMMAND_ID,
                              2);
          if ( StorageObjectID >= 0 )
          {
            StorageObjectID = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(
                                ppv,
                                &WPD_PROPERTY_STORAGE_OBJECT_ID,
                                v12);
            if ( StorageObjectID >= 0 )
            {
              StorageObjectID = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID, __int64 *))(*(_QWORD *)v11 + 32LL))(
                                  v11,
                                  0,
                                  ppv,
                                  &v10);
              if ( StorageObjectID >= 0 )
              {
                v9 = 0;
                StorageObjectID = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v10 + 160LL))(
                                    v10,
                                    &WPD_PROPERTY_COMMON_HRESULT,
                                    &v9);
                if ( StorageObjectID >= 0 )
                {
                  StorageObjectID = v9;
                  if ( v9 < 0 )
                  {
                    v4 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v5 = 196;
                      goto LABEL_37;
                    }
                  }
                }
                else
                {
                  v4 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v5 = 195;
                    goto LABEL_37;
                  }
                }
              }
              else
              {
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v5 = 194;
                  goto LABEL_37;
                }
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                193,
                (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
                (unsigned int)v12,
                StorageObjectID);
            }
          }
          else
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v5 = 192;
              goto LABEL_37;
            }
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v5 = 191;
            goto LABEL_37;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v5 = 190;
          goto LABEL_37;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 189;
        goto LABEL_37;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 188;
LABEL_37:
      WPP_SF_d(v4[2], v5, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)StorageObjectID);
    }
  }
  SendMessageW(DlgItem, 0x40Au, 0, 0);
  v6 = ILCombine(*(LPCITEMIDLIST *)(*((_QWORD *)a1 + 1) + 64LL), *((LPCITEMIDLIST *)a1 + 2));
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD, LPITEMIDLIST))(**((_QWORD **)a1 + 1) + 160LL))(*((_QWORD *)a1 + 1), v6);
    ChangeNotify(4096, 0, v6, 0);
    ILFree(v6);
  }
  PostMessageW(*((HWND *)a1 + 3), 0x464u, 0, StorageObjectID);
  (*(void (__fastcall **)(struct CFormatThreadData *))(*(_QWORD *)a1 + 16LL))(a1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  return (unsigned int)StorageObjectID;
}

```

## disassembly

```asm
0x180067c84  push    rbp
0x180067c86  push    rbx
0x180067c87  push    rsi
0x180067c88  push    rdi
0x180067c89  lea     rbp, [rsp-178h]
0x180067c91  sub     rsp, 278h
0x180067c98  mov     rax, cs:__security_cookie
0x180067c9f  xor     rax, rsp
0x180067ca2  mov     [rbp+190h+var_30], rax
0x180067ca9  mov     rsi, rcx
0x180067cac  mov     [rsp+290h+var_248], 0
0x180067cb5  mov     [rsp+290h+var_260], 0
0x180067cbe  mov     [rsp+290h+var_250], 0
0x180067cc7  mov     edx, 12Dh; nIDDlgItem
0x180067ccc  mov     rcx, [rcx+18h]; hDlg
0x180067cd0  call    cs:__imp_GetDlgItem
0x180067cd6  mov     rdi, rax
0x180067cd9  xor     r9d, r9d; lParam
0x180067cdc  mov     edx, 40Ah; Msg
0x180067ce1  lea     r8d, [r9+1]; wParam
0x180067ce5  mov     rcx, rax; hWnd
0x180067ce8  call    cs:__imp_SendMessageW
0x180067cee  mov     r9d, 104h; unsigned int
0x180067cf4  lea     r8, [rsp+290h+var_240]; unsigned __int16 *
0x180067cf9  mov     rdx, [rsi+10h]; struct STORAGEITEM *
0x180067cfd  mov     rcx, [rsi+8]; this
0x180067d01  call    ?_GetStorageObjectID@CStorageFolder@@AEAAJPEFBUSTORAGEITEM@@PEAGI@Z; CStorageFolder::_GetStorageObjectID(STORAGEITEM const *,ushort *,uint)
0x180067d06  mov     ebx, eax
0x180067d08  test    eax, eax
0x180067d0a  jns     short loc_180067D37
0x180067d0c  lea     rax, WPP_GLOBAL_Control
0x180067d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180067d1a  cmp     rcx, rax
0x180067d1d  jz      loc_180067FB4
0x180067d23  test    byte ptr [rcx+1Ch], 2
0x180067d27  jz      loc_180067FB4
0x180067d2d  mov     edx, 0BCh
0x180067d32  jmp     loc_180067FA1
0x180067d37  mov     rcx, [rsi+8]
0x180067d3b  mov     rax, [rcx]
0x180067d3e  lea     r8, [rsp+290h+var_248]
0x180067d43  mov     rdx, [rcx+40h]
0x180067d47  mov     rax, [rax+88h]
0x180067d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d53  mov     ebx, eax
0x180067d55  test    eax, eax
0x180067d57  jns     short loc_180067D84
0x180067d59  lea     rax, WPP_GLOBAL_Control
0x180067d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180067d67  cmp     rcx, rax
0x180067d6a  jz      loc_180067FB4
0x180067d70  test    byte ptr [rcx+1Ch], 2
0x180067d74  jz      loc_180067FB4
0x180067d7a  mov     edx, 0BDh
0x180067d7f  jmp     loc_180067FA1
0x180067d84  lea     rax, [rsp+290h+var_260]
0x180067d89  mov     [rsp+290h+ppv], rax; ppv
0x180067d8e  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180067d95  xor     edx, edx; pUnkOuter
0x180067d97  lea     r8d, [rdx+1]; dwClsContext
0x180067d9b  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180067da2  call    cs:__imp_CoCreateInstance
0x180067da8  mov     ebx, eax
0x180067daa  test    eax, eax
0x180067dac  jns     short loc_180067DD9
0x180067dae  lea     rax, WPP_GLOBAL_Control
0x180067db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180067dbc  cmp     rcx, rax
0x180067dbf  jz      loc_180067FB4
0x180067dc5  test    byte ptr [rcx+1Ch], 2
0x180067dc9  jz      loc_180067FB4
0x180067dcf  mov     edx, 0BEh
0x180067dd4  jmp     loc_180067FA1
0x180067dd9  mov     rcx, [rsp+290h+var_260]
0x180067dde  mov     rax, [rcx]
0x180067de1  lea     r8, WPD_COMMAND_STORAGE_FORMAT
0x180067de8  lea     rdx, WPD_PROPERTY_COMMON_COMMAND_CATEGORY
0x180067def  mov     rax, [rax+0D8h]
0x180067df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dfb  mov     ebx, eax
0x180067dfd  test    eax, eax
0x180067dff  jns     short loc_180067E2C
0x180067e01  lea     rax, WPP_GLOBAL_Control
0x180067e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e0f  cmp     rcx, rax
0x180067e12  jz      loc_180067FB4
0x180067e18  test    byte ptr [rcx+1Ch], 2
0x180067e1c  jz      loc_180067FB4
0x180067e22  mov     edx, 0BFh
0x180067e27  jmp     loc_180067FA1
0x180067e2c  mov     rcx, [rsp+290h+var_260]
0x180067e31  mov     rax, [rcx]
0x180067e34  mov     r8d, 2
0x180067e3a  lea     rdx, WPD_PROPERTY_COMMON_COMMAND_ID
0x180067e41  mov     rax, [rax+48h]
0x180067e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e4a  mov     ebx, eax
0x180067e4c  test    eax, eax
0x180067e4e  jns     short loc_180067E7B
0x180067e50  lea     rax, WPP_GLOBAL_Control
0x180067e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e5e  cmp     rcx, rax
0x180067e61  jz      loc_180067FB4
0x180067e67  test    byte ptr [rcx+1Ch], 2
0x180067e6b  jz      loc_180067FB4
0x180067e71  mov     edx, 0C0h
0x180067e76  jmp     loc_180067FA1
0x180067e7b  mov     rcx, [rsp+290h+var_260]
0x180067e80  mov     rax, [rcx]
0x180067e83  lea     r8, [rsp+290h+var_240]
0x180067e88  lea     rdx, WPD_PROPERTY_STORAGE_OBJECT_ID
0x180067e8f  mov     rax, [rax+38h]
0x180067e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e98  mov     ebx, eax
0x180067e9a  test    eax, eax
0x180067e9c  jns     short loc_180067EE2
0x180067e9e  lea     rax, WPP_GLOBAL_Control
0x180067ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180067eac  cmp     rcx, rax
0x180067eaf  jz      loc_180067FB4
0x180067eb5  test    byte ptr [rcx+1Ch], 2
0x180067eb9  jz      loc_180067FB4
0x180067ebf  mov     edx, 0C1h
0x180067ec4  mov     dword ptr [rsp+290h+ppv], ebx
0x180067ec8  lea     r9, [rsp+290h+var_240]
0x180067ecd  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180067ed4  mov     rcx, [rcx+10h]
0x180067ed8  call    WPP_SF_Sd
0x180067edd  jmp     loc_180067FB4
0x180067ee2  mov     rcx, [rsp+290h+var_248]
0x180067ee7  mov     rax, [rcx]
0x180067eea  lea     r9, [rsp+290h+var_250]
0x180067eef  mov     r8, [rsp+290h+var_260]
0x180067ef4  xor     edx, edx
0x180067ef6  mov     rax, [rax+20h]
0x180067efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067eff  mov     ebx, eax
0x180067f01  test    eax, eax
0x180067f03  jns     short loc_180067F2D
0x180067f05  lea     rax, WPP_GLOBAL_Control
0x180067f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f13  cmp     rcx, rax
0x180067f16  jz      loc_180067FB4
0x180067f1c  test    byte ptr [rcx+1Ch], 2
0x180067f20  jz      loc_180067FB4
0x180067f26  mov     edx, 0C2h
0x180067f2b  jmp     short loc_180067FA1
0x180067f2d  mov     [rsp+290h+var_258], 0
0x180067f35  mov     rcx, [rsp+290h+var_250]
0x180067f3a  mov     rax, [rcx]
0x180067f3d  lea     r8, [rsp+290h+var_258]
0x180067f42  lea     rdx, WPD_PROPERTY_COMMON_HRESULT
0x180067f49  mov     rax, [rax+0A0h]
0x180067f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f55  mov     ebx, eax
0x180067f57  test    eax, eax
0x180067f59  jns     short loc_180067F7B
0x180067f5b  lea     rax, WPP_GLOBAL_Control
0x180067f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f69  cmp     rcx, rax
0x180067f6c  jz      short loc_180067FB4
0x180067f6e  test    byte ptr [rcx+1Ch], 2
0x180067f72  jz      short loc_180067FB4
0x180067f74  mov     edx, 0C3h
0x180067f79  jmp     short loc_180067FA1
0x180067f7b  mov     ebx, [rsp+290h+var_258]
0x180067f7f  test    ebx, ebx
0x180067f81  jns     short loc_180067FB4
0x180067f83  lea     rax, WPP_GLOBAL_Control
0x180067f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f91  cmp     rcx, rax
0x180067f94  jz      short loc_180067FB4
0x180067f96  test    byte ptr [rcx+1Ch], 2
0x180067f9a  jz      short loc_180067FB4
0x180067f9c  mov     edx, 0C4h
0x180067fa1  mov     r9d, ebx
0x180067fa4  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180067fab  mov     rcx, [rcx+10h]
0x180067faf  call    WPP_SF_d
0x180067fb4  xor     r9d, r9d; lParam
0x180067fb7  xor     r8d, r8d; wParam
0x180067fba  mov     edx, 40Ah; Msg
0x180067fbf  mov     rcx, rdi; hWnd
0x180067fc2  call    cs:__imp_SendMessageW
0x180067fc8  mov     rcx, [rsi+8]
0x180067fcc  mov     rdx, [rsi+10h]; pidl2
0x180067fd0  mov     rcx, [rcx+40h]; pidl1
0x180067fd4  call    cs:__imp_ILCombine
0x180067fda  mov     rdi, rax
0x180067fdd  test    rax, rax
0x180067fe0  jz      short loc_180068016
0x180067fe2  mov     r8, [rsi+8]
0x180067fe6  mov     rcx, [r8]
0x180067fe9  mov     rax, [rcx+0A0h]
0x180067ff0  mov     rdx, rdi
0x180067ff3  mov     rcx, r8
0x180067ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ffb  xor     r9d, r9d; dwItem2
0x180067ffe  mov     r8, rdi; dwItem1
0x180068001  xor     edx, edx; uFlags
0x180068003  mov     ecx, 1000h; wEventId
0x180068008  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18006800d  mov     rcx, rdi; pidl
0x180068010  call    cs:__imp_ILFree
0x180068016  movsxd  r9, ebx; lParam
0x180068019  xor     r8d, r8d; wParam
0x18006801c  mov     edx, 464h; Msg
0x180068021  mov     rcx, [rsi+18h]; hWnd
0x180068025  call    cs:__imp_PostMessageW
0x18006802b  mov     rax, [rsi]
0x18006802e  mov     rcx, rsi
0x180068031  mov     rax, [rax+10h]
0x180068035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006803a  nop
0x18006803b  lea     rcx, [rsp+290h+var_250]
0x180068040  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068045  nop
0x180068046  lea     rcx, [rsp+290h+var_260]
0x18006804b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068050  nop
0x180068051  lea     rcx, [rsp+290h+var_248]
0x180068056  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006805b  mov     eax, ebx
0x18006805d  mov     rcx, [rbp+190h+var_30]
0x180068064  xor     rcx, rsp; StackCookie
0x180068067  call    __security_check_cookie
0x18006806c  add     rsp, 278h
0x180068073  pop     rdi
0x180068074  pop     rsi
0x180068075  pop     rbx
0x180068076  pop     rbp
0x180068077  retn
```
