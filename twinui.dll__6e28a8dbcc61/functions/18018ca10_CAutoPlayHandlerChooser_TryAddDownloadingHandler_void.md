# CAutoPlayHandlerChooser::TryAddDownloadingHandler(void)

- ea: `0x18018ca10`
- end: `0x18018d150`
- name: `?TryAddDownloadingHandler@CAutoPlayHandlerChooser@@MEAAJXZ`
- size: `1856`
- prototype: `__int64 __fastcall(CAutoPlayHandlerChooser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bdd30`

## callees

- `0x18000b7e8`
- `0x180054170`
- `0x18011ee30`
- `0x18013f43c`
- `0x18013f4a4`
- `0x18018b470`
- `0x18018b5c8`
- `0x18018ca10`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cf9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cfa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cfb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cfbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cf9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cfa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cfb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018cfbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018cee1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018cee1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18018ca3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18018ca3d`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18018cf8d`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18018cf8d`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18018cfc9`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18018cfc9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18018cab2`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18018cab2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18018ce98`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18018ce98`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18018cd65`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18018cd88`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18018cd65`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18018cd88`
- `DUI70!StrToID` at `0x18018cd59`
- `DUI70!StrToID` at `0x18018cd7c`
- `DUI70!StrToID` at `0x18018cd59`
- `DUI70!StrToID` at `0x18018cd7c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18018ce41`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18018ce55`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18018ce41`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18018ce55`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18018ce26`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18018ce26`
- `DUI70!ColorFromEnumI` at `0x18018cdbb`
- `DUI70!ColorFromEnumI` at `0x18018cdbb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18018cd08`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18018cd08`

## pseudocode

```c
__int64 __fastcall CAutoPlayHandlerChooser::TryAddDownloadingHandler(HWND *this)
{
  HRESULT ObjectQuery; // edi
  int ObjectProperties; // eax
  WCHAR *v4; // r15
  WCHAR *v5; // r12
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r10
  __int64 v9; // r11
  __int64 v10; // r15
  __int64 v11; // r12
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r13
  __int64 v17; // rdx
  int *v18; // rdx
  __int64 v19; // r8
  void *p_psz1; // r9
  unsigned int *v21; // rdx
  int v22; // eax
  CAutoPlayHandlerChooser *v23; // rsi
  DirectUI::Element *v24; // rbx
  unsigned __int16 v25; // ax
  DirectUI::Element *Descendent; // r13
  DirectUI::Element *v27; // rbx
  unsigned __int16 v28; // ax
  struct DirectUI::Element *v29; // rax
  struct DirectUI::Element *v30; // r14
  unsigned int v31; // edx
  unsigned __int16 *v32; // rcx
  const unsigned __int16 *v33; // rax
  CAutoPlayHandlerChooser *v34; // rbx
  unsigned int v36; // [rsp+50h] [rbp-29h]
  HRESULT v37; // [rsp+54h] [rbp-25h]
  LPVOID pv; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v39; // [rsp+60h] [rbp-19h] BYREF
  __int64 v40; // [rsp+68h] [rbp-11h] BYREF
  PCWSTR psz2; // [rsp+70h] [rbp-9h] BYREF
  PCWSTR psz1; // [rsp+78h] [rbp-1h] BYREF
  __int64 v43; // [rsp+80h] [rbp+7h]
  CAutoPlayHandlerChooser *ppv; // [rsp+E0h] [rbp+67h] BYREF
  char v45; // [rsp+E8h] [rbp+6Fh]
  unsigned int v46; // [rsp+F0h] [rbp+77h] BYREF
  int v47; // [rsp+F8h] [rbp+7Fh]

  ppv = (CAutoPlayHandlerChooser *)this;
  ObjectQuery = 0;
  if ( !IsWindow(this[28]) )
    return (unsigned int)ObjectQuery;
  v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1804B6DE4 > *(_DWORD *)(v43 + 4) )
  {
    Init_thread_header(&dword_1804B6DE4);
    if ( dword_1804B6DE4 == -1 )
    {
      dword_1804B4D50 = 12;
      xmmword_1804B4D40 = DEVPKEY_DeviceSetup_DCA_State;
      dword_1804B4D70 = 100;
      xmmword_1804B4D60 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
      dword_1804B4D90 = 116;
      xmmword_1804B4D80 = DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName;
      dword_1804B4DB0 = 105;
      xmmword_1804B4DA0 = DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath;
      dword_1804B4DD0 = 106;
      xmmword_1804B4DC0 = DEVPKEY_DeviceContainer_DCA_Tile_Background;
      dword_1804B4D54 = 1;
      qword_1804B4D58 = 0;
      xmmword_1804B4DE0 = DEVPKEY_DeviceContainer_DCA_ItemNameDisplay;
      dword_1804B4D74 = 0;
      qword_1804B4D78 = 0;
      dword_1804B4D94 = 0;
      qword_1804B4D98 = 0;
      dword_1804B4DB4 = 1;
      qword_1804B4DB8 = 0;
      dword_1804B4DD4 = 1;
      qword_1804B4DD8 = 0;
      dword_1804B4DF0 = 107;
      dword_1804B4DF4 = 1;
      qword_1804B4DF8 = 0;
      Init_thread_footer(&dword_1804B6DE4);
    }
  }
  v46 = 0;
  v40 = 0;
  ObjectProperties = DevGetObjectProperties(2, this + 4, 4, 6, &xmmword_1804B4D40, &v46, &v40);
  ObjectQuery = ObjectProperties;
  if ( ObjectProperties < 0 )
    return (unsigned int)ObjectQuery;
  v4 = 0;
  psz1 = 0;
  v5 = 0;
  psz2 = 0;
  pv = 0;
  v39 = 0;
  if ( v46 != 6 )
  {
    ObjectQuery = -2147418113;
    goto LABEL_74;
  }
  v6 = *((_QWORD *)&DEVPKEY_DeviceSetup_DCA_State + 1);
  v7 = 0;
  v8 = DEVPKEY_DeviceSetup_DCA_State;
  v9 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
  v10 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
  v11 = *((_QWORD *)&DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName + 1);
  v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath + 1);
  v13 = DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath;
  v14 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_Background + 1);
  v37 = ObjectProperties;
  v15 = 0;
  v36 = 0;
  v45 = 0;
  v16 = DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName;
  v47 = 0;
  do
  {
    v17 = *(unsigned int *)(v40 + 48 * v15 + 16);
    switch ( (_DWORD)v17 )
    {
      case 0xC:
        if ( *(_QWORD *)(v40 + 48 * v15) == v8 && *(_QWORD *)(v40 + 48 * v15 + 8) == v6 )
        {
          v18 = *(int **)(v40 + 48 * v15 + 40);
          if ( v18 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 7 )
              v7 = *v18;
          }
        }
        break;
      case 0x64:
        if ( *(_QWORD *)(v40 + 48 * v15) == v10 && *(_QWORD *)(v40 + 48 * v15 + 8) == v9 )
        {
          v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
          if ( v19 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 8210 )
            {
              p_psz1 = &psz1;
LABEL_36:
              _AllocString<CTCoAllocPolicy>(6 * v15, v17, v19, p_psz1);
              v6 = *((_QWORD *)&DEVPKEY_DeviceSetup_DCA_State + 1);
              v8 = DEVPKEY_DeviceSetup_DCA_State;
              v9 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
              v10 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
              v11 = *((_QWORD *)&DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName + 1);
              v16 = DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName;
              v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath + 1);
              v13 = DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath;
              v14 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_Background + 1);
            }
          }
        }
        break;
      case 0x74:
        if ( *(_QWORD *)(v40 + 48 * v15) == v16 && *(_QWORD *)(v40 + 48 * v15 + 8) == v11 )
        {
          v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
          if ( v19 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 18 )
            {
              p_psz1 = &psz2;
              goto LABEL_36;
            }
          }
        }
        break;
      case 0x6B:
        if ( *(_QWORD *)(v40 + 48 * v15) == (_QWORD)DEVPKEY_DeviceContainer_DCA_ItemNameDisplay )
        {
          v17 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_ItemNameDisplay + 1);
          if ( *(_QWORD *)(v40 + 48 * v15 + 8) == *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_ItemNameDisplay + 1) )
          {
            v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
            if ( v19 )
            {
              if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 18 )
              {
                p_psz1 = &pv;
                goto LABEL_36;
              }
            }
          }
        }
        break;
      case 0x69:
        if ( *(_QWORD *)(v40 + 48 * v15) == v13 && *(_QWORD *)(v40 + 48 * v15 + 8) == v12 )
        {
          v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
          if ( v19 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 18 )
            {
              p_psz1 = &v39;
              goto LABEL_36;
            }
          }
        }
        break;
      default:
        if ( (_DWORD)v17 == 106
          && *(_QWORD *)(v40 + 48 * v15) == (_QWORD)DEVPKEY_DeviceContainer_DCA_Tile_Background
          && *(_QWORD *)(v40 + 48 * v15 + 8) == v14 )
        {
          v21 = *(unsigned int **)(v40 + 48 * v15 + 40);
          if ( v21 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 7 )
            {
              v36 = *v21;
              v45 = 1;
            }
          }
        }
        break;
    }
    v15 = (unsigned int)(v47 + 1);
    v47 = v15;
  }
  while ( (unsigned int)v15 < v46 );
  v5 = (WCHAR *)psz2;
  v4 = (WCHAR *)psz1;
  v22 = StrCmpIW(psz1, psz2);
  ObjectQuery = v37;
  v23 = ppv;
  if ( !v22 )
  {
    switch ( v7 )
    {
      case 0:
      case 6:
        if ( dword_1804B6DE8 > *(_DWORD *)(v43 + 4) )
        {
          Init_thread_header(&dword_1804B6DE8);
          if ( dword_1804B6DE8 == -1 )
          {
            dword_1804B4E10 = 12;
            xmmword_1804B4E00 = DEVPKEY_DeviceSetup_DCA_State;
            dword_1804B4E14 = 1;
            qword_1804B4E18 = 0;
            Init_thread_footer(&dword_1804B6DE8);
          }
        }
        ObjectQuery = DevCreateObjectQuery(
                        2,
                        1,
                        1,
                        &xmmword_1804B4E00,
                        0,
                        0,
                        CAutoPlayHandlerChooser::DownloadStateChange,
                        v23,
                        (char *)v23 + 288);
        break;
      case 1:
        if ( !*((_DWORD *)ppv + 37) )
        {
          v24 = (DirectUI::Element *)*((_QWORD *)ppv + 29);
          v25 = StrToID(L"eRecommendedGroupTitle");
          Descendent = DirectUI::Element::FindDescendent(v24, v25);
          v27 = (DirectUI::Element *)*((_QWORD *)v23 + 29);
          v28 = StrToID(L"eRecommendedGroupItems");
          v29 = DirectUI::Element::FindDescendent(v27, v28);
          v30 = v29;
          if ( Descendent )
          {
            if ( v29 )
            {
              ppv = 0;
              if ( v45 )
                v31 = v36;
              else
                v31 = ColorFromEnumI(20011);
              v32 = v39;
              if ( !v39 )
                v32 = (unsigned __int16 *)*((_QWORD *)v23 + 38);
              v33 = (const unsigned __int16 *)pv;
              if ( !pv )
                v33 = (const unsigned __int16 *)*((_QWORD *)v23 + 31);
              ObjectQuery = AutoPlayTile::CreateAndInitInProgress(
                              (const struct CDUIResourceManager *)v32,
                              v23,
                              v30,
                              *((const unsigned __int16 **)v23 + 2),
                              *((const unsigned __int16 **)v23 + 3),
                              v33,
                              v32,
                              v31,
                              &ppv);
              if ( ObjectQuery >= 0 )
              {
                v34 = ppv;
                ObjectQuery = DirectUI::Element::Add(v30, ppv);
                if ( ObjectQuery < 0
                  || (*((_QWORD *)v23 + 35) = v34,
                      ObjectQuery = DirectUI::Element::SetLayoutPos(Descendent, 1),
                      ObjectQuery < 0)
                  || (ObjectQuery = DirectUI::Element::SetLayoutPos(v30, 1), ObjectQuery < 0) )
                {
                  if ( v34 )
                  {
                    DirectUI::Element::Destroy(v34, 1);
                    *((_QWORD *)v23 + 35) = 0;
                  }
                }
                else
                {
                  *((_DWORD *)v23 + 37) = 1;
                  CAutoPlayHandlerChooser::TryUpdateManufacturerHeader(v23);
                  (*(void (__fastcall **)(CAutoPlayHandlerChooser *))(*(_QWORD *)v23 + 160LL))(v23);
                }
              }
            }
          }
        }
        break;
      case 4:
        ppv = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        ObjectQuery = CoCreateInstance(
                        &CLSID_AutoplayHandler,
                        0,
                        3u,
                        &GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f,
                        (LPVOID *)&ppv);
        if ( ObjectQuery >= 0 )
        {
          ObjectQuery = (*(__int64 (__fastcall **)(CAutoPlayHandlerChooser *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          *((_QWORD *)v23 + 3));
          if ( ObjectQuery >= 0 )
          {
            ObjectQuery = (*(__int64 (__fastcall **)(CAutoPlayHandlerChooser *, _QWORD))(*(_QWORD *)ppv + 128LL))(
                            ppv,
                            *((_QWORD *)v23 + 2));
            if ( ObjectQuery >= 0 )
              ObjectQuery = CAutoPlayHandlerChooser::AddRecommendedHandler(v23, ppv);
          }
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        break;
    }
  }
LABEL_74:
  CoTaskMemFree(v4);
  CoTaskMemFree(v5);
  CoTaskMemFree(pv);
  CoTaskMemFree(v39);
  DevFreeObjectProperties(v46, v40);
  return (unsigned int)ObjectQuery;
}

```

## disassembly

```asm
0x18018ca10  mov     [rsp-8+arg_0], rcx
0x18018ca15  push    rbp
0x18018ca16  push    rbx
0x18018ca17  push    rsi
0x18018ca18  push    rdi
0x18018ca19  push    r12
0x18018ca1b  push    r13
0x18018ca1d  push    r14
0x18018ca1f  push    r15
0x18018ca21  lea     rbp, [rsp-1Fh]
0x18018ca26  sub     rsp, 98h
0x18018ca2d  mov     rsi, rcx
0x18018ca30  xor     r13d, r13d
0x18018ca33  mov     rcx, [rcx+0E0h]; hWnd
0x18018ca3a  mov     edi, r13d
0x18018ca3d  call    cs:__imp_IsWindow
0x18018ca43  test    eax, eax
0x18018ca45  jz      loc_18018CFCF
0x18018ca4b  mov     rax, gs:58h
0x18018ca54  lea     ebx, [r13+1]
0x18018ca58  mov     edx, cs:_tls_index
0x18018ca5e  mov     ecx, 4
0x18018ca63  mov     r14, [rax+rdx*8]
0x18018ca67  mov     [rbp+57h+var_50], r14
0x18018ca6b  mov     eax, [r14+rcx]
0x18018ca6f  cmp     cs:dword_1804B6DE4, eax
0x18018ca75  jg      loc_18018D03A
0x18018ca7b  mov     ecx, 2
0x18018ca80  mov     [rbp+57h+arg_10], r13d
0x18018ca84  lea     rax, [rbp+57h+var_68]
0x18018ca88  mov     [rbp+57h+var_68], r13
0x18018ca8c  mov     [rsp+0D0h+var_A0], rax
0x18018ca91  lea     rdx, [rsi+20h]
0x18018ca95  lea     rax, [rbp+57h+arg_10]
0x18018ca99  mov     [rsp+0D0h+var_A8], rax
0x18018ca9e  lea     r9d, [rcx+4]
0x18018caa2  lea     rax, xmmword_1804B4D40
0x18018caa9  lea     r8d, [rcx+2]
0x18018caad  mov     [rsp+0D0h+ppv], rax
0x18018cab2  call    cs:__imp_DevGetObjectProperties
0x18018cab8  mov     edi, eax
0x18018caba  test    eax, eax
0x18018cabc  js      loc_18018CFCF
0x18018cac2  cmp     [rbp+57h+arg_10], 6
0x18018cac6  mov     r15, r13
0x18018cac9  mov     [rbp+57h+psz1], r13
0x18018cacd  mov     r12, r13
0x18018cad0  mov     [rbp+57h+psz2], r13
0x18018cad4  mov     [rbp+57h+pv], r13
0x18018cad8  mov     [rbp+57h+var_70], r13
0x18018cadc  jnz     loc_18018CF97
0x18018cae2  mov     r9, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State+8
0x18018cae9  mov     ebx, r13d
0x18018caec  mov     r10, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State
0x18018caf3  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x18018cafa  mov     r15, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x18018cb01  mov     r12, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName+8
0x18018cb08  mov     r14, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath+8
0x18018cb0f  mov     rsi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath
0x18018cb16  mov     rdi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_Background+8
0x18018cb1d  mov     [rbp+57h+var_7C], eax
0x18018cb20  mov     eax, r13d
0x18018cb23  mov     [rbp+57h+var_80], r13d
0x18018cb27  mov     [rbp+57h+arg_8], r13b
0x18018cb2b  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName
0x18018cb32  mov     [rbp+57h+arg_18], eax
0x18018cb35  lea     rcx, [rax+rax*2]
0x18018cb39  mov     rax, [rbp+57h+var_68]
0x18018cb3d  add     rcx, rcx
0x18018cb40  mov     edx, [rax+rcx*8+10h]
0x18018cb44  cmp     edx, 0Ch
0x18018cb47  jnz     short loc_18018CB7E
0x18018cb49  cmp     [rax+rcx*8], r10
0x18018cb4d  jnz     loc_18018CCE9
0x18018cb53  cmp     [rax+rcx*8+8], r9
0x18018cb58  jnz     loc_18018CCE9
0x18018cb5e  mov     rdx, [rax+rcx*8+28h]
0x18018cb63  test    rdx, rdx
0x18018cb66  jz      loc_18018CCE9
0x18018cb6c  cmp     dword ptr [rax+rcx*8+20h], 7
0x18018cb71  jnz     loc_18018CCE9
0x18018cb77  mov     ebx, [rdx]
0x18018cb79  jmp     loc_18018CCE9
0x18018cb7e  cmp     edx, 64h ; 'd'
0x18018cb81  jnz     short loc_18018CBBD
0x18018cb83  cmp     [rax+rcx*8], r15
0x18018cb87  jnz     loc_18018CCE9
0x18018cb8d  cmp     [rax+rcx*8+8], r11
0x18018cb92  jnz     loc_18018CCE9
0x18018cb98  mov     r8, [rax+rcx*8+28h]
0x18018cb9d  test    r8, r8
0x18018cba0  jz      loc_18018CCE9
0x18018cba6  cmp     dword ptr [rax+rcx*8+20h], 2012h
0x18018cbae  jnz     loc_18018CCE9
0x18018cbb4  lea     r9, [rbp+57h+psz1]
0x18018cbb8  jmp     loc_18018CC70
0x18018cbbd  cmp     edx, 74h ; 't'
0x18018cbc0  jnz     short loc_18018CBF6
0x18018cbc2  cmp     [rax+rcx*8], r13
0x18018cbc6  jnz     loc_18018CCE9
0x18018cbcc  cmp     [rax+rcx*8+8], r12
0x18018cbd1  jnz     loc_18018CCE9
0x18018cbd7  mov     r8, [rax+rcx*8+28h]
0x18018cbdc  test    r8, r8
0x18018cbdf  jz      loc_18018CCE9
0x18018cbe5  cmp     dword ptr [rax+rcx*8+20h], 12h
0x18018cbea  jnz     loc_18018CCE9
0x18018cbf0  lea     r9, [rbp+57h+psz2]
0x18018cbf4  jmp     short loc_18018CC70
0x18018cbf6  cmp     edx, 6Bh ; 'k'
0x18018cbf9  jnz     short loc_18018CC3D
0x18018cbfb  mov     rdx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_ItemNameDisplay
0x18018cc02  cmp     [rax+rcx*8], rdx
0x18018cc06  jnz     loc_18018CCE9
0x18018cc0c  mov     rdx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_ItemNameDisplay+8
0x18018cc13  cmp     [rax+rcx*8+8], rdx
0x18018cc18  jnz     loc_18018CCE9
0x18018cc1e  mov     r8, [rax+rcx*8+28h]
0x18018cc23  test    r8, r8
0x18018cc26  jz      loc_18018CCE9
0x18018cc2c  cmp     dword ptr [rax+rcx*8+20h], 12h
0x18018cc31  jnz     loc_18018CCE9
0x18018cc37  lea     r9, [rbp+57h+pv]
0x18018cc3b  jmp     short loc_18018CC70
0x18018cc3d  cmp     edx, 69h ; 'i'
0x18018cc40  jnz     short loc_18018CCB6
0x18018cc42  cmp     [rax+rcx*8], rsi
0x18018cc46  jnz     loc_18018CCE9
0x18018cc4c  cmp     [rax+rcx*8+8], r14
0x18018cc51  jnz     loc_18018CCE9
0x18018cc57  mov     r8, [rax+rcx*8+28h]
0x18018cc5c  test    r8, r8
0x18018cc5f  jz      loc_18018CCE9
0x18018cc65  cmp     dword ptr [rax+rcx*8+20h], 12h
0x18018cc6a  jnz     short loc_18018CCE9
0x18018cc6c  lea     r9, [rbp+57h+var_70]
0x18018cc70  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18018cc75  mov     r9, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State+8
0x18018cc7c  mov     r10, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State
0x18018cc83  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x18018cc8a  mov     r15, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x18018cc91  mov     r12, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName+8
0x18018cc98  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName
0x18018cc9f  mov     r14, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath+8
0x18018cca6  mov     rsi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath
0x18018ccad  mov     rdi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_Background+8
0x18018ccb4  jmp     short loc_18018CCE9
0x18018ccb6  cmp     edx, 6Ah ; 'j'
0x18018ccb9  jnz     short loc_18018CCE9
0x18018ccbb  mov     rdx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_Background
0x18018ccc2  cmp     [rax+rcx*8], rdx
0x18018ccc6  jnz     short loc_18018CCE9
0x18018ccc8  cmp     [rax+rcx*8+8], rdi
0x18018cccd  jnz     short loc_18018CCE9
0x18018cccf  mov     rdx, [rax+rcx*8+28h]
0x18018ccd4  test    rdx, rdx
0x18018ccd7  jz      short loc_18018CCE9
0x18018ccd9  cmp     dword ptr [rax+rcx*8+20h], 7
0x18018ccde  jnz     short loc_18018CCE9
0x18018cce0  mov     eax, [rdx]
0x18018cce2  mov     [rbp+57h+var_80], eax
0x18018cce5  mov     [rbp+57h+arg_8], 1
0x18018cce9  mov     eax, [rbp+57h+arg_18]
0x18018ccec  inc     eax
0x18018ccee  mov     [rbp+57h+arg_18], eax
0x18018ccf1  cmp     eax, [rbp+57h+arg_10]
0x18018ccf4  jb      loc_18018CB35
0x18018ccfa  mov     r12, [rbp+57h+psz2]
0x18018ccfe  mov     r15, [rbp+57h+psz1]
0x18018cd02  mov     rdx, r12; psz2
0x18018cd05  mov     rcx, r15; psz1
0x18018cd08  call    cs:__imp_StrCmpIW
0x18018cd0e  mov     edi, [rbp+57h+var_7C]
0x18018cd11  xor     r13d, r13d
0x18018cd14  mov     rsi, [rbp+57h+arg_0]
0x18018cd18  mov     r14, [rbp+57h+var_50]
0x18018cd1c  test    eax, eax
0x18018cd1e  jnz     loc_18018CF9C
0x18018cd24  test    ebx, ebx
0x18018cd26  jz      loc_18018CF3D
0x18018cd2c  cmp     ebx, 6
0x18018cd2f  jz      loc_18018CF3D
0x18018cd35  cmp     ebx, 1
0x18018cd38  jnz     loc_18018CEAE
0x18018cd3e  cmp     [rsi+94h], r13d
0x18018cd45  jnz     loc_18018CF9C
0x18018cd4b  mov     rcx, cs:off_1803E1440; "eRecommendedGroupTitle"
0x18018cd52  mov     rbx, [rsi+0E8h]
0x18018cd59  call    cs:__imp_StrToID
0x18018cd5f  movzx   edx, ax
0x18018cd62  mov     rcx, rbx
0x18018cd65  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18018cd6b  mov     rcx, cs:off_1803AC5C0; "eRecommendedGroupItems"
0x18018cd72  mov     r13, rax
0x18018cd75  mov     rbx, [rsi+0E8h]
0x18018cd7c  call    cs:__imp_StrToID
0x18018cd82  movzx   edx, ax
0x18018cd85  mov     rcx, rbx
0x18018cd88  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18018cd8e  mov     r14, rax
0x18018cd91  test    r13, r13
0x18018cd94  jz      loc_18018CF9C
0x18018cd9a  test    rax, rax
0x18018cd9d  jz      loc_18018CF9C
0x18018cda3  cmp     [rbp+57h+arg_8], 0
0x18018cda7  mov     [rbp+57h+arg_0], 0
0x18018cdaf  jz      short loc_18018CDB6
0x18018cdb1  mov     edx, [rbp+57h+var_80]
0x18018cdb4  jmp     short loc_18018CDC3
0x18018cdb6  mov     ecx, 4E2Bh
0x18018cdbb  call    cs:__imp_ColorFromEnumI
0x18018cdc1  mov     edx, eax
0x18018cdc3  mov     rcx, [rbp+57h+var_70]
0x18018cdc7  test    rcx, rcx
0x18018cdca  jnz     short loc_18018CDD3
0x18018cdcc  mov     rcx, [rsi+130h]; struct CDUIResourceManager *
0x18018cdd3  mov     rax, [rbp+57h+pv]
0x18018cdd7  test    rax, rax
0x18018cdda  jnz     short loc_18018CDE3
0x18018cddc  mov     rax, [rsi+0F8h]
0x18018cde3  mov     r9, [rsi+10h]; unsigned __int16 *
0x18018cde7  lea     r8, [rbp+57h+arg_0]
0x18018cdeb  mov     [rsp+0D0h+var_90], r8; struct DirectUI::Element **
0x18018cdf0  mov     r8, r14; struct DirectUI::Element *
0x18018cdf3  mov     [rsp+0D0h+var_98], edx; unsigned int
0x18018cdf7  mov     rdx, rsi; struct CAutoPlayHandlerChooser *
0x18018cdfa  mov     [rsp+0D0h+var_A0], rcx; unsigned __int16 *
0x18018cdff  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 *
0x18018ce04  mov     rax, [rsi+18h]
0x18018ce08  mov     [rsp+0D0h+ppv], rax; unsigned __int16 *
0x18018ce0d  call    ?CreateAndInitInProgress@AutoPlayTile@@SAJAEBVCDUIResourceManager@@PEAVCAutoPlayHandlerChooser@@PEAVElement@DirectUI@@PEBG333KPEAPEAV45@@Z; AutoPlayTile::CreateAndInitInProgress(CDUIResourceManager const &,CAutoPlayHandlerChooser *,DirectUI::Element *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,DirectUI::Element * *)
0x18018ce12  mov     edi, eax
0x18018ce14  test    eax, eax
0x18018ce16  js      loc_18018CF9C
0x18018ce1c  mov     rbx, [rbp+57h+arg_0]
0x18018ce20  mov     rcx, r14
0x18018ce23  mov     rdx, rbx
0x18018ce26  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18018ce2c  mov     edi, eax
0x18018ce2e  test    eax, eax
0x18018ce30  js      short loc_18018CE8A
0x18018ce32  mov     edx, 1
0x18018ce37  mov     [rsi+118h], rbx
0x18018ce3e  mov     rcx, r13
0x18018ce41  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18018ce47  mov     edi, eax
0x18018ce49  test    eax, eax
0x18018ce4b  js      short loc_18018CE8A
0x18018ce4d  mov     edx, 1
0x18018ce52  mov     rcx, r14
0x18018ce55  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18018ce5b  mov     edi, eax
0x18018ce5d  test    eax, eax
0x18018ce5f  js      short loc_18018CE8A
0x18018ce61  mov     rcx, rsi; this
0x18018ce64  mov     dword ptr [rsi+94h], 1
0x18018ce6e  call    ?TryUpdateManufacturerHeader@CAutoPlayHandlerChooser@@IEAAXXZ; CAutoPlayHandlerChooser::TryUpdateManufacturerHeader(void)
0x18018ce73  mov     rax, [rsi]
0x18018ce76  mov     rcx, rsi
0x18018ce79  mov     rax, [rax+0A0h]
0x18018ce80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ce85  jmp     loc_18018CF9C
0x18018ce8a  test    rbx, rbx
0x18018ce8d  jz      loc_18018CF9C
0x18018ce93  mov     dl, 1
0x18018ce95  mov     rcx, rbx
0x18018ce98  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18018ce9e  mov     qword ptr [rsi+118h], 0
0x18018cea9  jmp     loc_18018CF9C
0x18018ceae  cmp     ebx, 4
0x18018ceb1  jnz     loc_18018CF9C
0x18018ceb7  lea     rcx, [rbp+57h+arg_0]
0x18018cebb  mov     [rbp+57h+arg_0], r13
0x18018cebf  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18018cec4  lea     rax, [rbp+57h+arg_0]
0x18018cec8  xor     edx, edx; pUnkOuter
0x18018ceca  lea     r9, _GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f; riid
0x18018ced1  mov     [rsp+0D0h+ppv], rax; ppv
0x18018ced6  lea     r8d, [rbx-1]; dwClsContext
0x18018ceda  lea     rcx, CLSID_AutoplayHandler; rclsid
0x18018cee1  call    cs:__imp_CoCreateInstance
0x18018cee7  mov     edi, eax
0x18018cee9  test    eax, eax
0x18018ceeb  js      short loc_18018CF32
0x18018ceed  mov     rcx, [rbp+57h+arg_0]
0x18018cef1  mov     rdx, [rsi+18h]
0x18018cef5  mov     rax, [rcx]
0x18018cef8  mov     rax, [rax+18h]
0x18018cefc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018cf01  mov     edi, eax
0x18018cf03  test    eax, eax
0x18018cf05  js      short loc_18018CF32
0x18018cf07  mov     rcx, [rbp+57h+arg_0]
0x18018cf0b  mov     rdx, [rsi+10h]
0x18018cf0f  mov     rax, [rcx]
0x18018cf12  mov     rax, [rax+80h]
0x18018cf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018cf1e  mov     edi, eax
0x18018cf20  test    eax, eax
0x18018cf22  js      short loc_18018CF32
  ... truncated ...
```
