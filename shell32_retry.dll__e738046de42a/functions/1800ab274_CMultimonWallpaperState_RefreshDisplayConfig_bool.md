# CMultimonWallpaperState::RefreshDisplayConfig(bool *)

- ea: `0x1800ab274`
- end: `0x1800ab9e7`
- name: `?RefreshDisplayConfig@CMultimonWallpaperState@@QEAAJPEA_N@Z`
- size: `1907`
- prototype: `__int64 __fastcall(CMultimonWallpaperState *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config`

## callers

- `0x1800aae20`
- `0x1800aae84`

## callees

- `0x180026dc4`
- `0x18003ef10`
- `0x180043380`
- `0x1800ab274`
- `0x1800abc10`
- `0x1800ac89c`
- `0x1800b8f00`
- `0x1800f0c90`
- `0x1800f124c`
- `0x1800f188c`
- `0x18013c244`
- `0x18014bb94`
- `0x180159804`
- `0x180182474`
- `0x180233280`
- `0x180233b54`
- `0x1802342fc`
- `0x18028ad58`
- `0x1804997a4`

## import_xrefs

- `USER32!GetDisplayConfigBufferSizes` at `0x1800ab308`
- `USER32!GetDisplayConfigBufferSizes` at `0x1800ab308`
- `USER32!QueryDisplayConfig` at `0x1800ab3ab`
- `USER32!QueryDisplayConfig` at `0x1800ab3ab`
- `USER32!DisplayConfigGetDeviceInfo` at `0x1800ab4d9`
- `USER32!DisplayConfigGetDeviceInfo` at `0x1800ab6a3`
- `USER32!DisplayConfigGetDeviceInfo` at `0x1800ab4d9`
- `USER32!DisplayConfigGetDeviceInfo` at `0x1800ab6a3`
- `USER32!EnumDisplayMonitors` at `0x1800ab782`
- `USER32!EnumDisplayMonitors` at `0x1800ab782`
- `USER32!CopyRect` at `0x1800ab817`
- `USER32!CopyRect` at `0x1800ab817`
- `USER32!MonitorFromPoint` at `0x1800ab567`
- `USER32!MonitorFromPoint` at `0x1800ab567`
- `USER32!GetSystemMetrics` at `0x1800ab89b`
- `USER32!GetSystemMetrics` at `0x1800ab8aa`
- `USER32!GetSystemMetrics` at `0x1800ab8ba`
- `USER32!GetSystemMetrics` at `0x1800ab89b`
- `USER32!GetSystemMetrics` at `0x1800ab8aa`
- `USER32!GetSystemMetrics` at `0x1800ab8ba`
- `GDI32!DeleteObject` at `0x1800ab821`
- `GDI32!DeleteObject` at `0x1800ab821`
- `GDI32!GetRgnBox` at `0x1800ab800`
- `GDI32!GetRgnBox` at `0x1800ab800`
- `Windows.Storage!GetMonitorRects` at `0x1800ab5c9`
- `Windows.Storage!GetMonitorRects` at `0x1800ab5c9`

## pseudocode

```c
__int64 __fastcall CMultimonWallpaperState::RefreshDisplayConfig(CMultimonWallpaperState *this, bool *a2)
{
  bool *v2; // r14
  _DWORD *v4; // rax
  LONG DisplayConfigBufferSizes; // eax
  signed int v6; // edi
  unsigned __int64 v7; // rax
  DISPLAYCONFIG_PATH_INFO *v8; // r13
  unsigned __int64 v9; // rax
  DISPLAYCONFIG_MODE_INFO *v10; // rax
  DISPLAYCONFIG_MODE_INFO *v11; // r15
  LONG v12; // eax
  int v13; // edx
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdx
  HDSA v18; // rbx
  int i; // r14d
  int v20; // eax
  struct _DSA **ItemPtr; // rax
  int j; // ebx
  struct _DSA *v23; // rcx
  UINT32 *v24; // rax
  UINT32 *v25; // r12
  unsigned int DeviceInfo; // eax
  __int64 v27; // rdx
  unsigned __int64 v28; // r14
  unsigned int v29; // edx
  unsigned int v30; // ecx
  unsigned int v31; // edx
  unsigned int v32; // ecx
  LONG v33; // edx
  LONG v34; // ecx
  HMONITOR v35; // rax
  int k; // r13d
  struct _DPA *v37; // rcx
  int v38; // edx
  HMONITOR v39; // rcx
  unsigned int v40; // eax
  HMONITOR v41; // rdx
  unsigned int v42; // ecx
  unsigned int v43; // eax
  int refreshed; // eax
  __int64 v45; // rax
  unsigned int v46; // edx
  unsigned int v47; // ecx
  unsigned int v48; // r10d
  unsigned int v49; // eax
  unsigned int v50; // r8d
  unsigned int v51; // eax
  unsigned int v52; // ecx
  unsigned int v53; // eax
  HRGN v54; // rcx
  int v55; // ecx
  bool v56; // al
  int v57; // edx
  bool v58; // al
  int SystemMetrics; // ebx
  int v60; // eax
  int v61; // ecx
  int v62; // eax
  unsigned int v63; // ebx
  unsigned int v64; // r9d
  int v65; // eax
  int m; // ebx
  struct _DPA *v67; // rcx
  int v68; // eax
  CTranscodedImage *Ptr; // rax
  unsigned int modeInfoArray; // [rsp+20h] [rbp-E0h]
  int currentTopologyId; // [rsp+28h] [rbp-D8h]
  int v73; // [rsp+50h] [rbp-B0h]
  HDSA hdsa; // [rsp+58h] [rbp-A8h] BYREF
  POINT pt; // [rsp+60h] [rbp-A0h]
  HMONITOR v76; // [rsp+68h] [rbp-98h]
  DISPLAYCONFIG_PATH_INFO *v77; // [rsp+70h] [rbp-90h]
  struct _DSA **v78; // [rsp+78h] [rbp-88h]
  bool *v79; // [rsp+80h] [rbp-80h]
  struct tagRECT v80; // [rsp+90h] [rbp-70h] BYREF
  UINT32 numPathArrayElements; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 numModeInfoArrayElements[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  LPARAM dwData; // [rsp+B0h] [rbp-50h] BYREF
  int v84; // [rsp+B8h] [rbp-48h]
  int v85; // [rsp+BCh] [rbp-44h]
  HRGN hrgn; // [rsp+C0h] [rbp-40h]
  char v87; // [rsp+C8h] [rbp-38h]
  int v88; // [rsp+DCh] [rbp-24h]
  int v89; // [rsp+E0h] [rbp-20h]
  unsigned int v90; // [rsp+E8h] [rbp-18h]
  unsigned int v91[4]; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT rc; // [rsp+100h] [rbp+0h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v94[134]; // [rsp+1B4h] [rbp+B4h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER v95; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned int v96; // [rsp+654h] [rbp+554h]
  unsigned int v97; // [rsp+658h] [rbp+558h]
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  v79 = a2;
  v2 = a2;
  if ( a2 )
    *a2 = 0;
  memset_0(&dwData, 0, 0x40u);
  v4 = *(_DWORD **)this;
  dwData = (LPARAM)this;
  if ( v4 )
    LODWORD(v4) = *v4;
  v84 = (int)v4;
  v85 = (int)v4;
  v87 = 1;
  *((_QWORD *)this + 8) = 0;
  numPathArrayElements = 0;
  numModeInfoArrayElements[0] = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, numModeInfoArrayElements);
  v6 = DisplayConfigBufferSizes;
  if ( DisplayConfigBufferSizes < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC75,
      (unsigned int)"shell\\shell32\\unicpp\\wallpaperrenderer.cpp",
      (const char *)(unsigned int)DisplayConfigBufferSizes,
      modeInfoArray);
    goto LABEL_90;
  }
  v7 = 72LL * numPathArrayElements;
  if ( !is_mul_ok(numPathArrayElements, 0x48u) )
    v7 = -1;
  v8 = (DISPLAYCONFIG_PATH_INFO *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v77 = v8;
  v9 = (unsigned __int64)numModeInfoArrayElements[0] << 6;
  if ( !is_mul_ok(numModeInfoArrayElements[0], 0x40u) )
    v9 = -1;
  v10 = (DISPLAYCONFIG_MODE_INFO *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v8 || !v10 )
  {
    v6 = -2147024882;
    v16 = 3194;
    v15 = 2147942414LL;
    goto LABEL_88;
  }
  v12 = QueryDisplayConfig(2u, &numPathArrayElements, v8, numModeInfoArrayElements, v10, 0);
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0x80070000;
  if ( v6 < 0 )
  {
    if ( EnumDisplayMonitors(0, 0, CMultimonWallpaperState::s_RefreshDisplayMonitorEnumProc, (LPARAM)&dwData) )
      v6 = 0;
    goto LABEL_89;
  }
  hdsa = 0;
  CDSA_Base<_AdapterInfo>::Create(&hdsa);
  v14 = _BuildDisplayIndex(
          (_DWORD)v8,
          v13,
          numPathArrayElements,
          (unsigned int)&hdsa,
          modeInfoArray,
          currentTopologyId,
          1,
          0,
          0);
  v6 = v14;
  if ( v14 >= 0 )
  {
    v6 = -2147467259;
    memset_0(&requestPacket, 0, 0x1A4u);
    v18 = hdsa;
    for ( i = 0; ; ++i )
    {
      v73 = i;
      if ( v18 )
        v20 = *(_DWORD *)v18;
      else
        v20 = 0;
      if ( i >= v20 )
      {
        LOBYTE(v17) = 1;
        ClearAdapterInfo(&hdsa, v17);
        v2 = v79;
        goto LABEL_89;
      }
      ItemPtr = (struct _DSA **)DSA_GetItemPtr(v18, i);
      v78 = ItemPtr;
      if ( !ItemPtr )
        continue;
      for ( j = 0; ; ++j )
      {
        v23 = ItemPtr[2];
        v17 = v23 ? *(unsigned int *)v23 : 0LL;
        if ( j >= (int)v17 )
          break;
        v24 = (UINT32 *)DSA_GetItemPtr(v23, j);
        v25 = v24;
        if ( v24[1] != -1 && *((_BYTE *)v24 + 8) )
        {
          memset_0(&requestPacket.adapterId, 0, 0x19Cu);
          requestPacket.size = 420;
          requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
          requestPacket.adapterId = v8[v25[3]].targetInfo.adapterId;
          requestPacket.id = *v25;
          DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
          if ( DeviceInfo )
          {
            v27 = 3228;
LABEL_58:
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)v27,
              (unsigned int)"shell\\shell32\\unicpp\\wallpaperrenderer.cpp",
              (const char *)DeviceInfo,
              modeInfoArray);
            goto LABEL_55;
          }
          v6 = 0;
          if ( v8[v25[3]].sourceInfo.modeInfoIdx != -1 )
          {
            v28 = (unsigned __int64)v8[v25[3]].sourceInfo.modeInfoIdx << 6;
            v29 = *(UINT32 *)((char *)&v11->sourceMode.width + v28);
            if ( v29 )
            {
              v30 = *(UINT32 *)((char *)&v11->sourceMode.height + v28);
              if ( v30 )
              {
                v31 = v29 >> 1;
                v32 = v30 >> 1;
                if ( ((v8[v25[3]].targetInfo.rotation - 2) & 0xFFFFFFFD) != 0 )
                {
                  v33 = *(UINT32 *)((char *)&v11->targetMode.targetVideoSignalInfo.hSyncFreq.Denominator + v28) + v31;
                  pt.y = *(UINT32 *)((char *)&v11->targetMode.targetVideoSignalInfo.vSyncFreq.Numerator + v28) + v32;
                  pt.x = v33;
                }
                else
                {
                  v34 = *(UINT32 *)((char *)&v11->targetMode.targetVideoSignalInfo.hSyncFreq.Denominator + v28) + v32;
                  pt.y = *(UINT32 *)((char *)&v11->targetMode.targetVideoSignalInfo.vSyncFreq.Numerator + v28) + v31;
                  pt.x = v34;
                }
                v35 = MonitorFromPoint(pt, 0);
                v76 = v35;
                if ( v35 )
                {
                  for ( k = 0; ; ++k )
                  {
                    v37 = *(struct _DPA **)this;
                    v38 = *(_QWORD *)this ? *(_DWORD *)v37 : 0;
                    if ( k >= v38 )
                      break;
                    v39 = (HMONITOR)*((_QWORD *)DPA_GetPtr(v37, k) + 262);
                    v35 = v76;
                    if ( v39 && v39 == v76 )
                      goto LABEL_54;
                  }
                  rc = 0;
                  GetMonitorRects(v35, &rc, 0);
                  v40 = *((_DWORD *)this + 16);
                  v41 = v76;
                  if ( v40 <= rc.right - rc.left )
                    v40 = rc.right - rc.left;
                  v80 = rc;
                  v42 = rc.bottom - rc.top;
                  *((_DWORD *)this + 16) = v40;
                  v43 = *((_DWORD *)this + 17);
                  if ( v43 <= v42 )
                    v43 = v42;
                  *((_DWORD *)this + 17) = v43;
                  refreshed = CMultimonWallpaperState::_RefreshDisplayConfigForMonitor(
                                (struct CMultimonWallpaperState::REFRESH_DISPLAY_CONFIG_DATA *)&dwData,
                                v41,
                                &v80,
                                v94,
                                v25[1] + 1);
                  v6 = refreshed;
                  if ( refreshed < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0xCC2,
                      (unsigned int)"shell\\shell32\\unicpp\\wallpaperrenderer.cpp",
                      (const char *)(unsigned int)refreshed,
                      modeInfoArray);
LABEL_54:
                    v8 = v77;
                    goto LABEL_55;
                  }
                  memset_0(&v95.adapterId, 0, 0x3A8u);
                  v45 = (int)v25[3];
                  v8 = v77;
                  v95.size = 944;
                  v95.type = -7;
                  v95.adapterId = v77[v45].targetInfo.adapterId;
                  v95.id = *v25;
                  DeviceInfo = DisplayConfigGetDeviceInfo(&v95);
                  if ( DeviceInfo )
                  {
                    v27 = 3273;
                    goto LABEL_58;
                  }
                  v46 = v97;
                  v47 = v97;
                  v48 = *(UINT32 *)((char *)&v11->sourceMode.width + v28);
                  v49 = v48;
                  v50 = *(UINT32 *)((char *)&v11->sourceMode.height + v28);
                  if ( v96 > v97 )
                    v47 = v96;
                  if ( v48 <= v50 )
                    v49 = *(UINT32 *)((char *)&v11->sourceMode.height + v28);
                  if ( v47 <= v49 )
                  {
                    v51 = *(UINT32 *)((char *)&v11->sourceMode.height + v28);
                    if ( v48 > v50 )
                      v51 = *(UINT32 *)((char *)&v11->sourceMode.width + v28);
                  }
                  else
                  {
                    v51 = v97;
                    if ( v96 > v97 )
                      v51 = v96;
                  }
                  if ( v90 <= v51 )
                  {
                    v52 = v97;
                    v53 = *(UINT32 *)((char *)&v11->sourceMode.width + v28);
                    if ( v96 > v97 )
                      v52 = v96;
                    if ( v48 <= v50 )
                      v53 = *(UINT32 *)((char *)&v11->sourceMode.height + v28);
                    if ( v52 <= v53 )
                    {
                      if ( v48 > v50 )
                        v50 = *(UINT32 *)((char *)&v11->sourceMode.width + v28);
                      v90 = v50;
                    }
                    else
                    {
                      if ( v96 > v97 )
                        v46 = v96;
                      v90 = v46;
                    }
                  }
                }
              }
            }
          }
        }
LABEL_55:
        ItemPtr = v78;
      }
      v18 = hdsa;
      i = v73;
    }
  }
  v15 = (unsigned int)v14;
  v16 = 3203;
LABEL_88:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"shell\\shell32\\unicpp\\wallpaperrenderer.cpp",
    (const char *)v15,
    modeInfoArray);
LABEL_89:
  CZeroInitNew::operator delete(v8);
  CZeroInitNew::operator delete(v11);
LABEL_90:
  if ( *(_QWORD *)this )
    DPA_Sort(*(HDPA *)this, CMultimonWallpaperState::CMultimonWallpaperEntry::s_MultimonWallpaperEntrySort, 0);
  CMultimonWallpaperState::CMultimonSpanLayout::Reset((CMultimonWallpaperState *)((char *)this + 8));
  v54 = hrgn;
  *((_QWORD *)this + 4) = hrgn;
  rc = 0;
  hrgn = 0;
  if ( GetRgnBox(v54, &rc) != 3 )
  {
    *((_BYTE *)this + 40) = 1;
    CopyRect((LPRECT)this + 1, &rc);
    DeleteObject(*((HGDIOBJ *)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  v55 = v88;
  v56 = v88 > 0 && v89 > 0;
  *((_BYTE *)this + 329) = v56;
  CMultimonWallpaperState::_CalculateImageOrientationThreshold(this, v55 > 0);
  v57 = v88 + v89;
  *((_DWORD *)this + 86) = v88 + v89;
  if ( *((_DWORD *)this + 87) >= v57 )
    *((_DWORD *)this + 87) = -1;
  v58 = v87 && *((_BYTE *)this + 40);
  *((_BYTE *)this + 328) = v58;
  if ( !v57 )
    *((_BYTE *)this + 328) = 0;
  SystemMetrics = GetSystemMetrics(79);
  v60 = GetSystemMetrics(78);
  v61 = 78;
  if ( v60 <= SystemMetrics )
    v61 = 79;
  v62 = GetSystemMetrics(v61);
  v91[0] = 0;
  v63 = v62;
  if ( v2 )
  {
    if ( (int)SHRegGetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"MaxVirtualDesktopDimension", v91) < 0
      || v63 > v91[0] )
    {
      SHRegSetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"MaxVirtualDesktopDimension", v63);
      *v2 = 1;
    }
    if ( (int)SHRegGetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"MaxMonitorDimension", v91) < 0
      || v90 > v91[0] )
    {
      SHRegSetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"MaxMonitorDimension", v90);
      *v2 = 1;
    }
  }
  if ( v6 >= 0 )
  {
    v64 = *(_QWORD *)this ? **(_DWORD **)this : 0;
    v65 = SHRegSetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"TranscodedImageCount", v64);
    if ( v65 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x109A,
        (unsigned int)"shell\\shell32\\unicpp\\wallpaperrenderer.cpp",
        (const char *)(unsigned int)v65,
        modeInfoArray);
  }
  for ( m = 0; ; ++m )
  {
    v67 = *(struct _DPA **)this;
    v68 = *(_QWORD *)this ? *(_DWORD *)v67 : 0;
    if ( m >= v68 )
      break;
    Ptr = (CTranscodedImage *)DPA_GetPtr(v67, m);
    CTranscodedImage::RemoveInvalidSurfaces(Ptr);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ab274  mov     [rsp-8+arg_10], rbx
0x1800ab279  push    rbp
0x1800ab27a  push    rsi
0x1800ab27b  push    rdi
0x1800ab27c  push    r12
0x1800ab27e  push    r13
0x1800ab280  push    r14
0x1800ab282  push    r15
0x1800ab284  lea     rbp, [rsp-580h]
0x1800ab28c  sub     rsp, 680h
0x1800ab293  mov     rax, cs:__security_cookie
0x1800ab29a  xor     rax, rsp
0x1800ab29d  mov     [rbp+5B0h+var_40], rax
0x1800ab2a4  mov     [rbp+5B0h+var_630], rdx
0x1800ab2a8  mov     r14, rdx
0x1800ab2ab  mov     rsi, rcx
0x1800ab2ae  test    rdx, rdx
0x1800ab2b1  jz      short loc_1800AB2B6
0x1800ab2b3  mov     byte ptr [rdx], 0
0x1800ab2b6  mov     ebx, 40h ; '@'
0x1800ab2bb  lea     rcx, [rbp+5B0h+dwData]; void *
0x1800ab2bf  mov     r8d, ebx; Size
0x1800ab2c2  xor     edx, edx; Val
0x1800ab2c4  call    memset_0
0x1800ab2c9  mov     rax, [rsi]
0x1800ab2cc  mov     [rbp+5B0h+dwData], rsi
0x1800ab2d0  test    rax, rax
0x1800ab2d3  jz      short loc_1800AB2D7
0x1800ab2d5  mov     eax, [rax]
0x1800ab2d7  mov     r12d, 2
0x1800ab2dd  mov     [rbp+5B0h+var_5F8], eax
0x1800ab2e0  mov     ecx, r12d; flags
0x1800ab2e3  mov     [rbp+5B0h+var_5F4], eax
0x1800ab2e6  lea     r8, [rbp+5B0h+numModeInfoArrayElements]; numModeInfoArrayElements
0x1800ab2ea  mov     [rbp+5B0h+var_5E8], 1
0x1800ab2ee  lea     rdx, [rbp+5B0h+numPathArrayElements]; numPathArrayElements
0x1800ab2f2  mov     qword ptr [rsi+40h], 0
0x1800ab2fa  mov     [rbp+5B0h+numPathArrayElements], 0
0x1800ab301  mov     [rbp+5B0h+numModeInfoArrayElements], 0
0x1800ab308  call    cs:__imp_GetDisplayConfigBufferSizes
0x1800ab30e  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ab312  mov     edi, eax
0x1800ab314  test    eax, eax
0x1800ab316  jns     short loc_1800AB338
0x1800ab318  mov     rcx, [rbp+5B8h]; this
0x1800ab31f  lea     r8, aShellShell32Un_17; "shell\\shell32\\unicpp\\wallpaperrender"...
0x1800ab326  mov     r9d, eax; char *
0x1800ab329  mov     edx, 0C75h; void *
0x1800ab32e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ab333  jmp     loc_1800AB7C5
0x1800ab338  mov     ecx, [rbp+5B0h+numPathArrayElements]
0x1800ab33b  mov     eax, 48h ; 'H'
0x1800ab340  mul     rcx
0x1800ab343  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ab34a  cmovb   rax, r15
0x1800ab34e  mov     rcx, rax; unsigned __int64
0x1800ab351  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ab356  mov     ecx, [rbp+5B0h+numModeInfoArrayElements]
0x1800ab359  mov     r13, rax
0x1800ab35c  mov     [rsp+6B0h+var_640], rax
0x1800ab361  mov     rax, rbx
0x1800ab364  mul     rcx
0x1800ab367  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ab36e  cmovb   rax, r15
0x1800ab372  mov     rcx, rax; unsigned __int64
0x1800ab375  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ab37a  mov     r15, rax
0x1800ab37d  test    r13, r13
0x1800ab380  jz      loc_1800AB791
0x1800ab386  test    rax, rax
0x1800ab389  jz      loc_1800AB791
0x1800ab38f  mov     [rsp+6B0h+currentTopologyId], 0; currentTopologyId
0x1800ab398  lea     r9, [rbp+5B0h+numModeInfoArrayElements]; numModeInfoArrayElements
0x1800ab39c  mov     r8, r13; pathArray
0x1800ab39f  mov     [rsp+6B0h+modeInfoArray], rax; modeInfoArray
0x1800ab3a4  lea     rdx, [rbp+5B0h+numPathArrayElements]; numPathArrayElements
0x1800ab3a8  mov     ecx, r12d; flags
0x1800ab3ab  call    cs:__imp_QueryDisplayConfig
0x1800ab3b1  mov     edi, eax
0x1800ab3b3  test    eax, eax
0x1800ab3b5  jle     short loc_1800AB3C0
0x1800ab3b7  movzx   edi, ax
0x1800ab3ba  or      edi, 80070000h
0x1800ab3c0  test    edi, edi
0x1800ab3c2  js      loc_1800AB773
0x1800ab3c8  lea     rcx, [rsp+6B0h+hdsa]
0x1800ab3cd  mov     [rsp+6B0h+hdsa], 0
0x1800ab3d6  call    ?Create@?$CDSA_Base@U_AdapterInfo@@@@QEAAHH@Z; CDSA_Base<_AdapterInfo>::Create(int)
0x1800ab3db  mov     r8d, [rbp+5B0h+numPathArrayElements]
0x1800ab3df  lea     r9, [rsp+6B0h+hdsa]
0x1800ab3e4  mov     [rsp+6B0h+var_670], 0
0x1800ab3ed  mov     rcx, r13
0x1800ab3f0  mov     [rsp+6B0h+var_678], 0
0x1800ab3f9  mov     [rsp+6B0h+var_680], 1
0x1800ab3fe  call    ?_BuildDisplayIndex@@YAJPEAUDISPLAYCONFIG_PATH_INFO@@0IPEAV?$CDSA@U_AdapterInfo@@@@HI_NPEAH3@Z; _BuildDisplayIndex(DISPLAYCONFIG_PATH_INFO *,DISPLAYCONFIG_PATH_INFO *,uint,CDSA<_AdapterInfo> *,int,uint,bool,int *,int *)
0x1800ab403  mov     edi, eax
0x1800ab405  test    eax, eax
0x1800ab407  jns     short loc_1800AB416
0x1800ab409  mov     r9d, eax
0x1800ab40c  mov     edx, 0C83h
0x1800ab411  jmp     loc_1800AB79E
0x1800ab416  xor     edx, edx; Val
0x1800ab418  lea     rcx, [rbp+5B0h+requestPacket]; void *
0x1800ab41c  mov     r8d, 1A4h; Size
0x1800ab422  mov     edi, 80004005h
0x1800ab427  call    memset_0
0x1800ab42c  mov     rbx, [rsp+6B0h+hdsa]
0x1800ab431  xor     r14d, r14d
0x1800ab434  mov     [rsp+6B0h+var_660], r14d
0x1800ab439  test    rbx, rbx
0x1800ab43c  jz      short loc_1800AB442
0x1800ab43e  mov     eax, [rbx]
0x1800ab440  jmp     short loc_1800AB444
0x1800ab442  xor     eax, eax
0x1800ab444  cmp     r14d, eax
0x1800ab447  jge     loc_1800AB761
0x1800ab44d  mov     edx, r14d; i
0x1800ab450  mov     rcx, rbx; hdsa
0x1800ab453  call    DSA_GetItemPtr
0x1800ab458  mov     [rsp+6B0h+var_638], rax
0x1800ab45d  test    rax, rax
0x1800ab460  jz      loc_1800AB759
0x1800ab466  xor     ebx, ebx
0x1800ab468  mov     rcx, [rax+10h]; hdsa
0x1800ab46c  test    rcx, rcx
0x1800ab46f  jz      short loc_1800AB475
0x1800ab471  mov     edx, [rcx]
0x1800ab473  jmp     short loc_1800AB477
0x1800ab475  xor     edx, edx
0x1800ab477  cmp     ebx, edx
0x1800ab479  jge     loc_1800AB74F
0x1800ab47f  mov     edx, ebx; i
0x1800ab481  call    DSA_GetItemPtr
0x1800ab486  mov     r12, rax
0x1800ab489  cmp     dword ptr [rax+4], 0FFFFFFFFh
0x1800ab48d  jz      loc_1800AB644
0x1800ab493  cmp     byte ptr [rax+8], 0
0x1800ab497  jz      loc_1800AB644
0x1800ab49d  xor     edx, edx; Val
0x1800ab49f  lea     rcx, [rbp+5B0h+requestPacket.adapterId]; void *
0x1800ab4a3  mov     r8d, 19Ch; Size
0x1800ab4a9  call    memset_0
0x1800ab4ae  mov     [rbp+5B0h+requestPacket.size], 1A4h
0x1800ab4b5  mov     [rbp+5B0h+requestPacket.type], 2
0x1800ab4bc  movsxd  rax, dword ptr [r12+0Ch]
0x1800ab4c1  lea     rcx, [rax+rax*8]
0x1800ab4c5  mov     rax, [r13+rcx*8+14h]
0x1800ab4ca  lea     rcx, [rbp+5B0h+requestPacket]; requestPacket
0x1800ab4ce  mov     qword ptr [rbp+5B0h+requestPacket.adapterId.LowPart], rax
0x1800ab4d2  mov     eax, [r12]
0x1800ab4d6  mov     [rbp+5B0h+requestPacket.id], eax
0x1800ab4d9  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800ab4df  test    eax, eax
0x1800ab4e1  jz      short loc_1800AB4ED
0x1800ab4e3  mov     edx, 0C9Ch
0x1800ab4e8  jmp     loc_1800AB6B2
0x1800ab4ed  movsxd  rax, dword ptr [r12+0Ch]
0x1800ab4f2  xor     edi, edi
0x1800ab4f4  lea     rax, [rax+rax*8]
0x1800ab4f8  cmp     dword ptr [r13+rax*8+0Ch], 0FFFFFFFFh
0x1800ab4fe  jz      loc_1800AB644
0x1800ab504  mov     r14d, [r13+rax*8+0Ch]
0x1800ab509  shl     r14, 6
0x1800ab50d  mov     edx, [r14+r15+10h]
0x1800ab512  test    edx, edx
0x1800ab514  jz      loc_1800AB644
0x1800ab51a  mov     ecx, [r14+r15+14h]
0x1800ab51f  test    ecx, ecx
0x1800ab521  jz      loc_1800AB644
0x1800ab527  mov     eax, [r13+rax*8+28h]
0x1800ab52c  sub     eax, 2
0x1800ab52f  shr     edx, 1
0x1800ab531  shr     ecx, 1
0x1800ab533  test    eax, 0FFFFFFFDh
0x1800ab538  jz      short loc_1800AB54E
0x1800ab53a  add     edx, [r14+r15+1Ch]
0x1800ab53f  add     ecx, [r14+r15+20h]
0x1800ab544  mov     [rsp+6B0h+pt.y], ecx
0x1800ab548  mov     [rsp+6B0h+pt.x], edx
0x1800ab54c  jmp     short loc_1800AB560
0x1800ab54e  add     ecx, [r14+r15+1Ch]
0x1800ab553  add     edx, [r14+r15+20h]
0x1800ab558  mov     [rsp+6B0h+pt.y], edx
0x1800ab55c  mov     [rsp+6B0h+pt.x], ecx
0x1800ab560  mov     rcx, qword ptr [rsp+6B0h+pt.x]; pt
0x1800ab565  xor     edx, edx; dwFlags
0x1800ab567  call    cs:__imp_MonitorFromPoint
0x1800ab56d  mov     [rsp+6B0h+var_648], rax
0x1800ab572  test    rax, rax
0x1800ab575  jz      loc_1800AB644
0x1800ab57b  xor     r13d, r13d
0x1800ab57e  mov     rcx, [rsi]; hdpa
0x1800ab581  test    rcx, rcx
0x1800ab584  jz      short loc_1800AB58A
0x1800ab586  mov     edx, [rcx]
0x1800ab588  jmp     short loc_1800AB58C
0x1800ab58a  xor     edx, edx
0x1800ab58c  cmp     r13d, edx
0x1800ab58f  jge     short loc_1800AB5B8
0x1800ab591  movsxd  rdx, r13d; i
0x1800ab594  call    DPA_GetPtr
0x1800ab599  mov     rcx, [rax+830h]
0x1800ab5a0  mov     rax, [rsp+6B0h+var_648]
0x1800ab5a5  test    rcx, rcx
0x1800ab5a8  jz      short loc_1800AB5B3
0x1800ab5aa  cmp     rcx, rax
0x1800ab5ad  jz      loc_1800AB63F
0x1800ab5b3  inc     r13d
0x1800ab5b6  jmp     short loc_1800AB57E
0x1800ab5b8  xorps   xmm0, xmm0
0x1800ab5bb  lea     rdx, [rbp+5B0h+rc]
0x1800ab5bf  xor     r8d, r8d
0x1800ab5c2  mov     rcx, rax
0x1800ab5c5  movups  xmmword ptr [rbp+5B0h+rc.left], xmm0
0x1800ab5c9  call    cs:__imp_?GetMonitorRects@@YAHPEAUHMONITOR__@@PEAUtagRECT@@H@Z; GetMonitorRects(HMONITOR__ *,tagRECT *,int)
0x1800ab5cf  mov     eax, [rsi+40h]
0x1800ab5d2  lea     r9, [rbp+5B0h+var_4FC]; unsigned __int16 *
0x1800ab5d9  mov     ecx, [rbp+5B0h+rc.right]
0x1800ab5dc  lea     r8, [rbp+5B0h+var_620]; struct tagRECT
0x1800ab5e0  sub     ecx, [rbp+5B0h+rc.left]
0x1800ab5e3  movaps  xmm0, xmmword ptr [rbp+5B0h+rc.left]
0x1800ab5e7  cmp     eax, ecx
0x1800ab5e9  mov     rdx, [rsp+6B0h+var_648]; HMONITOR
0x1800ab5ee  cmovbe  eax, ecx
0x1800ab5f1  movdqa  xmmword ptr [rbp+5B0h+var_620.left], xmm0
0x1800ab5f6  mov     ecx, [rbp+5B0h+rc.bottom]
0x1800ab5f9  sub     ecx, [rbp+5B0h+rc.top]
0x1800ab5fc  mov     [rsi+40h], eax
0x1800ab5ff  mov     eax, [rsi+44h]
0x1800ab602  cmp     eax, ecx
0x1800ab604  cmovbe  eax, ecx
0x1800ab607  lea     rcx, [rbp+5B0h+dwData]; struct CMultimonWallpaperState::REFRESH_DISPLAY_CONFIG_DATA *
0x1800ab60b  mov     [rsi+44h], eax
0x1800ab60e  mov     eax, [r12+4]
0x1800ab613  inc     eax
0x1800ab615  mov     dword ptr [rsp+6B0h+modeInfoArray], eax; unsigned int
0x1800ab619  call    ?_RefreshDisplayConfigForMonitor@CMultimonWallpaperState@@SAJPEAUREFRESH_DISPLAY_CONFIG_DATA@1@PEAUHMONITOR__@@UtagRECT@@PEBGI@Z; CMultimonWallpaperState::_RefreshDisplayConfigForMonitor(CMultimonWallpaperState::REFRESH_DISPLAY_CONFIG_DATA *,HMONITOR__ *,tagRECT,ushort const *,uint)
0x1800ab61e  mov     edi, eax
0x1800ab620  test    eax, eax
0x1800ab622  jns     short loc_1800AB650
0x1800ab624  mov     rcx, [rbp+5B8h]; this
0x1800ab62b  lea     r8, aShellShell32Un_17; "shell\\shell32\\unicpp\\wallpaperrender"...
0x1800ab632  mov     r9d, eax; char *
0x1800ab635  mov     edx, 0CC2h; void *
0x1800ab63a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ab63f  mov     r13, [rsp+6B0h+var_640]
0x1800ab644  mov     rax, [rsp+6B0h+var_638]
0x1800ab649  inc     ebx
0x1800ab64b  jmp     loc_1800AB468
0x1800ab650  xor     edx, edx; Val
0x1800ab652  lea     rcx, [rbp+5B0h+var_3F0.adapterId]; void *
0x1800ab659  mov     r8d, 3A8h; Size
0x1800ab65f  call    memset_0
0x1800ab664  movsxd  rax, dword ptr [r12+0Ch]
0x1800ab669  mov     r13, [rsp+6B0h+var_640]
0x1800ab66e  mov     [rbp+5B0h+var_3F0.size], 3B0h
0x1800ab678  mov     [rbp+5B0h+var_3F0.type], 0FFFFFFF9h
0x1800ab682  lea     rcx, [rax+rax*8]
0x1800ab686  mov     rax, [r13+rcx*8+14h]
0x1800ab68b  lea     rcx, [rbp+5B0h+var_3F0]; requestPacket
0x1800ab692  mov     qword ptr [rbp+5B0h+var_3F0.adapterId.LowPart], rax
0x1800ab699  mov     eax, [r12]
0x1800ab69d  mov     [rbp+5B0h+var_3F0.id], eax
0x1800ab6a3  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800ab6a9  test    eax, eax
0x1800ab6ab  jz      short loc_1800AB6CD
0x1800ab6ad  mov     edx, 0CC9h; void *
0x1800ab6b2  mov     rcx, [rbp+5B8h]; this
0x1800ab6b9  lea     r8, aShellShell32Un_17; "shell\\shell32\\unicpp\\wallpaperrender"...
0x1800ab6c0  mov     r9d, eax; char *
0x1800ab6c3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800ab6c8  jmp     loc_1800AB644
0x1800ab6cd  mov     edx, [rbp+5B0h+var_58]
0x1800ab6d3  mov     ecx, edx
0x1800ab6d5  mov     r9d, [rbp+5B0h+var_5C]
0x1800ab6dc  cmp     r9d, edx
0x1800ab6df  mov     r10d, [r14+r15+10h]
0x1800ab6e4  mov     eax, r10d
0x1800ab6e7  mov     r8d, [r14+r15+14h]
0x1800ab6ec  cmova   ecx, r9d
0x1800ab6f0  cmp     r10d, r8d
0x1800ab6f3  cmovbe  eax, r8d
0x1800ab6f7  cmp     ecx, eax
0x1800ab6f9  jbe     short loc_1800AB706
0x1800ab6fb  cmp     r9d, edx
0x1800ab6fe  mov     eax, edx
0x1800ab700  cmova   eax, r9d
0x1800ab704  jmp     short loc_1800AB710
0x1800ab706  cmp     r10d, r8d
0x1800ab709  mov     eax, r8d
0x1800ab70c  cmova   eax, r10d
0x1800ab710  cmp     [rbp+5B0h+var_5C8], eax
0x1800ab713  ja      loc_1800AB644
0x1800ab719  cmp     r9d, edx
0x1800ab71c  mov     ecx, edx
0x1800ab71e  mov     eax, r10d
0x1800ab721  cmova   ecx, r9d
0x1800ab725  cmp     r10d, r8d
0x1800ab728  cmovbe  eax, r8d
0x1800ab72c  cmp     ecx, eax
  ... truncated ...
```
