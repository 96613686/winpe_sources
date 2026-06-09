# CSimpleAppList::WndProc(uint,unsigned __int64,__int64)

- ea: `0x18025ee58`
- end: `0x18025f2c2`
- name: `?WndProc@CSimpleAppList@@QEAA_NI_K_J@Z`
- size: `1130`
- prototype: `bool __fastcall(CSimpleAppList *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18025ff10`

## callees

- `0x18000b7e8`
- `0x180011884`
- `0x1800150c0`
- `0x1800a1adc`
- `0x18013d330`
- `0x18025c2c0`
- `0x18025e6fc`
- `0x18025ee58`
- `0x18025f2c8`
- `0x18025f6fc`
- `0x18025f904`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18025f16b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18025f16b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025ef29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025f096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025ef29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025f096`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18025ef76`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18025ef76`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x18025f26f`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x18025f26f`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18025eef8`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18025f25b`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18025eef8`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18025f25b`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18025ef13`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18025f27f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18025ef13`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18025f27f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18025ef97`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18025ef97`
- `DUI70!StrToID` at `0x18025ef8b`
- `DUI70!StrToID` at `0x18025ef8b`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18025f183`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18025f183`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18025ef04`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18025ef04`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18025ef3c`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18025f0d9`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18025ef3c`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18025f0d9`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18025f1c1`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18025f288`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18025f1c1`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18025f288`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18025f07a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18025f206`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18025f07a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18025f206`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Unlock` at `0x18025f03d`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Unlock` at `0x18025f03d`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Lock` at `0x18025f01a`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Lock` at `0x18025f01a`

## string_xrefs

- `0x18025ef84`: `LockScreenRemoveApp`

## pseudocode

```c
char __fastcall CSimpleAppList::WndProc(CSimpleAppList *this, int a2, void *a3, ITEMIDLIST *a4)
{
  char v7; // bl
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  unsigned int v12; // edx
  int v13; // eax
  LPITEMIDLIST *v14; // r15
  DirectUI::Element *v15; // rcx
  _DWORD *v16; // rax
  bool v17; // dl
  __int64 v18; // r8
  struct DirectUI::Element **v19; // rcx
  struct DirectUI::Element *Descendent; // rcx
  DirectUI::Element *Parent; // rdi
  unsigned __int16 v22; // ax
  HANDLE v23; // rbx
  const struct _ITEMIDLIST_ABSOLUTE *v24; // r9
  void **ppvItem; // rax
  LPITEMIDLIST *v26; // rdi
  void (__fastcall *v27)(LPITEMIDLIST *, const PROPERTYKEY *, LONG *); // rbx
  _DWORD *Children; // rax
  _DWORD *v29; // r15
  unsigned int v30; // edi
  unsigned int v31; // r12d
  _QWORD *v32; // r13
  struct DirectUI::Element *v33; // r13
  __int64 v34; // rax
  const WCHAR *v35; // rax
  bool v36; // dl
  __int64 v37; // rcx
  __int64 v38; // rcx
  int ScaleFactorForPart; // eax
  LPITEMIDLIST *pppidl; // [rsp+30h] [rbp-30h] BYREF
  LONG plEvent[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v43; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v44[2]; // [rsp+48h] [rbp-18h] BYREF

  v7 = 0;
  v8 = a2 - 1034;
  if ( !v8 )
  {
    pppidl = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pppidl);
    if ( SHCreateItemWithParent(
           *(LPCITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL),
           0,
           a4,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           (void **)&pppidl) >= 0 )
    {
      v38 = *((_QWORD *)this + 29);
      *(_QWORD *)plEvent = 0;
      if ( (*(int (__fastcall **)(__int64, LPITEMIDLIST *, __int64, LONG *))(*(_QWORD *)v38 + 48LL))(
             v38,
             pppidl,
             2,
             plEvent) >= 0 )
      {
        ScaleFactorForPart = CLauncherSettings::GetScaleFactorForPart();
        DirectUI::Element::SetWidth(
          *(DirectUI::Element **)plEvent,
          (int)(float)((float)(344 * ScaleFactorForPart) / 100.0));
        if ( (int)DirectUI::Element::Add(
                    this,
                    *(struct DirectUI::Element **)plEvent,
                    (int (*)(const void *, const void *))CSimpleAppList::_s_SortItemsProc) < 0 )
          DirectUI::Element::Destroy(*(DirectUI::Element **)plEvent, 0);
      }
    }
    ILFree(a4);
    v7 = 1;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pppidl);
    return v7;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    *(_QWORD *)plEvent = 0;
    pppidl = 0;
    ppvItem = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&pppidl);
    if ( SHCreateItemWithParent(
           *(LPCITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL),
           0,
           a4,
           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
           ppvItem) >= 0 )
    {
      v26 = pppidl;
      v27 = *(void (__fastcall **)(LPITEMIDLIST *, const PROPERTYKEY *, LONG *))((char *)&(*pppidl)[45].mkid.cb + 1);
      CoTaskMemFree(*(LPVOID *)plEvent);
      v27(v26, &PKEY_AppUserModel_ID, plEvent);
    }
    v7 = 1;
    if ( *(_QWORD *)plEvent && **(_WORD **)plEvent )
    {
      v44[0] = 0;
      Children = (_DWORD *)DirectUI::Element::GetChildren(this, v44);
      v29 = Children;
      if ( Children )
      {
        v30 = 0;
        v31 = *Children & 0xFFFFFFF;
        while ( v30 < v31 )
        {
          v32 = v29 + 2;
          if ( (*v29 & 0x10000000) != 0 )
            v32 = (_QWORD *)*v32;
          v33 = (struct DirectUI::Element *)v32[v30];
          if ( v33 )
          {
            v34 = *(_QWORD *)v33;
            v43 = 0;
            if ( (*(int (__fastcall **)(struct DirectUI::Element *, GUID *, __int64 *))(v34 + 200))(
                   v33,
                   &GUID_5b485fb6_49e4_4d60_9ac4_19ea5e074d57,
                   &v43) >= 0 )
            {
              v35 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
              if ( CompareStringOrdinal(*(LPCWCH *)plEvent, -1, v35, -1, 1) != 2 )
              {
                if ( (int)DirectUI::Element::Remove(this, v33) >= 0 && v31 == 1 )
                {
                  CSimpleAppList::_SetEmptyListMessage(this, v36);
                  v37 = *((_QWORD *)this + 26);
                  if ( v37 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 168LL))(v37);
                }
                break;
              }
            }
          }
          ++v30;
        }
      }
      CValuePtr::Release((CValuePtr *)v44);
    }
    ILFree(a4);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pppidl);
    v15 = *(DirectUI::Element **)plEvent;
    goto LABEL_12;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    pppidl = 0;
    plEvent[0] = 0;
    v23 = SHChangeNotification_Lock(a3, (DWORD)a4, &pppidl, plEvent);
    if ( v23 )
    {
      CSimpleAppList::_OnChange(this, plEvent[0], (const struct _ITEMIDLIST_ABSOLUTE *)*pppidl, v24);
      SHChangeNotification_Unlock(v23);
    }
    return 1;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    pppidl = 0;
    v16 = (_DWORD *)DirectUI::Element::GetChildren(this, &pppidl);
    v7 = 1;
    if ( !v16 || (*v16 & 0xFFFFFFF) == 0 )
      goto LABEL_22;
    v19 = (struct DirectUI::Element **)(v16 + 2);
    if ( (*v16 & 0x10000000) != 0 )
      v19 = (struct DirectUI::Element **)*v19;
    Descendent = *v19;
    if ( Descendent )
    {
      if ( (*((_BYTE *)this + 244) & 1) != 0 )
      {
        Parent = DirectUI::Element::GetParent(this);
        if ( !Parent )
          goto LABEL_25;
        v22 = StrToID(L"LockScreenRemoveApp");
        Descendent = DirectUI::Element::FindDescendent(Parent, v22);
        if ( !Descendent )
          goto LABEL_25;
      }
    }
    else
    {
LABEL_22:
      if ( !*((_QWORD *)this + 26) )
      {
LABEL_25:
        if ( (Microsoft_Windows_Immersive_ShellEnableBits & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &MICROSOFT_TWINUI_PUBLISHER_Context,
            LockscreenApplications_LoadPopup_Stop,
            v18,
            1,
            v44);
        CValuePtr::Release((CValuePtr *)&pppidl);
        return v7;
      }
      CSimpleAppList::_SetEmptyListMessage(this, v17);
      Descendent = (struct DirectUI::Element *)*((_QWORD *)this + 26);
    }
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 168LL))(Descendent);
    goto LABEL_25;
  }
  if ( v11 == 1 )
  {
    pppidl = 0;
    if ( (int)CSimpleAppList::_CreatePackageElement(
                this,
                (const unsigned __int16 *)a3,
                (struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *)a4,
                (struct DirectUI::Element **)&pppidl) >= 0 )
    {
      v13 = CLauncherSettings::GetScaleFactorForPart();
      v14 = pppidl;
      DirectUI::Element::SetWidth((DirectUI::Element *)pppidl, (int)(float)((float)(344 * v13) / 100.0));
      if ( (int)DirectUI::Element::Add(this, (struct DirectUI::Element *)v14) < 0 )
        DirectUI::Element::Destroy((DirectUI::Element *)v14, 0);
    }
    if ( a4 )
      CSimpleUserDefaultLocaleCaseInsensitiveStringArray::`scalar deleting destructor'(
        (CSimpleUserDefaultLocaleCaseInsensitiveStringArray *)a4,
        v12);
    v15 = (DirectUI::Element *)a3;
LABEL_12:
    CoTaskMemFree(v15);
  }
  return v7;
}

```

## disassembly

```asm
0x18025ee58  mov     [rsp-38h+arg_8], rbx
0x18025ee5d  push    rbp
0x18025ee5e  push    rsi
0x18025ee5f  push    rdi
0x18025ee60  push    r12
0x18025ee62  push    r13
0x18025ee64  push    r14
0x18025ee66  push    r15
0x18025ee68  mov     rbp, rsp
0x18025ee6b  sub     rsp, 60h
0x18025ee6f  mov     rax, cs:__security_cookie
0x18025ee76  xor     rax, rsp
0x18025ee79  mov     [rbp+var_8], rax
0x18025ee7d  xor     r13d, r13d
0x18025ee80  mov     r14, r9
0x18025ee83  mov     rdi, r8
0x18025ee86  mov     rsi, rcx
0x18025ee89  mov     bl, r13b
0x18025ee8c  sub     edx, 40Ah
0x18025ee92  jz      loc_18025F1D9
0x18025ee98  sub     edx, 1
0x18025ee9b  jz      loc_18025F04D
0x18025eea1  sub     edx, 1
0x18025eea4  jz      loc_18025F004
0x18025eeaa  sub     edx, 1
0x18025eead  jz      loc_18025EF34
0x18025eeb3  cmp     edx, 1
0x18025eeb6  jnz     loc_18025F29C
0x18025eebc  lea     r9, [rbp+pppidl]; struct DirectUI::Element **
0x18025eec0  mov     [rbp+pppidl], r13
0x18025eec4  mov     r8, r14; struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *
0x18025eec7  mov     rdx, rdi; unsigned __int16 *
0x18025eeca  call    ?_CreatePackageElement@CSimpleAppList@@AEAAJPEBGPEAVCSimpleUserDefaultLocaleCaseInsensitiveStringArray@@PEAPEAVElement@DirectUI@@@Z; CSimpleAppList::_CreatePackageElement(ushort const *,CSimpleUserDefaultLocaleCaseInsensitiveStringArray *,DirectUI::Element * *)
0x18025eecf  test    eax, eax
0x18025eed1  js      short loc_18025EF19
0x18025eed3  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x18025eed8  mov     r15, [rbp+pppidl]
0x18025eedc  imul    edx, eax, 158h
0x18025eee2  mov     rcx, r15
0x18025eee5  movd    xmm0, edx
0x18025eee9  cvtdq2ps xmm0, xmm0
0x18025eeec  divss   xmm0, cs:__real@42c80000
0x18025eef4  cvttss2si edx, xmm0
0x18025eef8  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18025eefe  mov     rdx, r15
0x18025ef01  mov     rcx, rsi
0x18025ef04  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18025ef0a  test    eax, eax
0x18025ef0c  jns     short loc_18025EF19
0x18025ef0e  xor     edx, edx
0x18025ef10  mov     rcx, r15
0x18025ef13  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18025ef19  test    r14, r14
0x18025ef1c  jz      short loc_18025EF26
0x18025ef1e  mov     rcx, r14; this
0x18025ef21  call    ??_GCSimpleUserDefaultLocaleCaseInsensitiveStringArray@@QEAAPEAXI@Z; CSimpleUserDefaultLocaleCaseInsensitiveStringArray::`scalar deleting destructor'(uint)
0x18025ef26  mov     rcx, rdi; pv
0x18025ef29  call    cs:__imp_CoTaskMemFree
0x18025ef2f  jmp     loc_18025F29C
0x18025ef34  lea     rdx, [rbp+pppidl]
0x18025ef38  mov     [rbp+pppidl], r13
0x18025ef3c  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18025ef42  mov     ebx, 1
0x18025ef47  test    rax, rax
0x18025ef4a  jz      short loc_18025EFA7
0x18025ef4c  test    dword ptr [rax], 0FFFFFFFh
0x18025ef52  jbe     short loc_18025EFA7
0x18025ef54  test    dword ptr [rax], 10000000h
0x18025ef5a  lea     rcx, [rax+8]
0x18025ef5e  jz      short loc_18025EF63
0x18025ef60  mov     rcx, [rcx]
0x18025ef63  mov     rcx, [rcx]
0x18025ef66  test    rcx, rcx
0x18025ef69  jz      short loc_18025EFA7
0x18025ef6b  test    [rsi+0F4h], bl
0x18025ef71  jz      short loc_18025EFBF
0x18025ef73  mov     rcx, rsi
0x18025ef76  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18025ef7c  mov     rdi, rax
0x18025ef7f  test    rax, rax
0x18025ef82  jz      short loc_18025EFCE
0x18025ef84  lea     rcx, aLockscreenremo; "LockScreenRemoveApp"
0x18025ef8b  call    cs:__imp_StrToID
0x18025ef91  movzx   edx, ax
0x18025ef94  mov     rcx, rdi
0x18025ef97  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18025ef9d  mov     rcx, rax
0x18025efa0  test    rax, rax
0x18025efa3  jz      short loc_18025EFCE
0x18025efa5  jmp     short loc_18025EFBF
0x18025efa7  cmp     [rsi+0D0h], r13
0x18025efae  jz      short loc_18025EFCE
0x18025efb0  mov     rcx, rsi; this
0x18025efb3  call    ?_SetEmptyListMessage@CSimpleAppList@@AEAAX_N@Z; CSimpleAppList::_SetEmptyListMessage(bool)
0x18025efb8  mov     rcx, [rsi+0D0h]
0x18025efbf  mov     rax, [rcx]
0x18025efc2  mov     rax, [rax+0A8h]
0x18025efc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025efce  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 4
0x18025efd5  jz      short loc_18025EFF6
0x18025efd7  lea     rax, [rbp+var_18]
0x18025efdb  mov     r9d, ebx
0x18025efde  lea     rdx, LockscreenApplications_LoadPopup_Stop
0x18025efe5  mov     [rsp+60h+ppvItem], rax
0x18025efea  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18025eff1  call    McGenEventWrite_EventWriteTransfer
0x18025eff6  lea     rcx, [rbp+pppidl]; this
0x18025effa  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18025efff  jmp     loc_18025F29C
0x18025f004  mov     edx, r14d; dwProcId
0x18025f007  mov     [rbp+pppidl], r13
0x18025f00b  lea     r9, [rbp+plEvent]; plEvent
0x18025f00f  mov     [rbp+plEvent], r13d
0x18025f013  lea     r8, [rbp+pppidl]; pppidl
0x18025f017  mov     rcx, rdi; hChange
0x18025f01a  call    cs:__imp_SHChangeNotification_Lock
0x18025f020  mov     rbx, rax
0x18025f023  test    rax, rax
0x18025f026  jz      short loc_18025F043
0x18025f028  mov     r8, [rbp+pppidl]
0x18025f02c  mov     rcx, rsi; this
0x18025f02f  mov     edx, [rbp+plEvent]; int
0x18025f032  mov     r8, [r8]; struct _ITEMIDLIST_ABSOLUTE *
0x18025f035  call    ?_OnChange@CSimpleAppList@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z; CSimpleAppList::_OnChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x18025f03a  mov     rcx, rbx; hLock
0x18025f03d  call    cs:__imp_SHChangeNotification_Unlock
0x18025f043  mov     ebx, 1
0x18025f048  jmp     loc_18025F29C
0x18025f04d  lea     rcx, [rbp+pppidl]
0x18025f051  mov     qword ptr [rbp+plEvent], r13
0x18025f055  mov     [rbp+pppidl], r13
0x18025f059  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18025f05e  mov     rcx, [rsi+0C8h]
0x18025f065  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18025f06c  mov     r8, r14; pidl
0x18025f06f  mov     [rsp+60h+ppvItem], rax; ppvItem
0x18025f074  xor     edx, edx; psfParent
0x18025f076  mov     rcx, [rcx+18h]; pidlParent
0x18025f07a  call    cs:__imp_SHCreateItemWithParent
0x18025f080  test    eax, eax
0x18025f082  js      short loc_18025F0B2
0x18025f084  mov     rdi, [rbp+pppidl]
0x18025f088  mov     rcx, qword ptr [rbp+plEvent]; pv
0x18025f08c  mov     rax, [rdi]
0x18025f08f  mov     rbx, [rax+88h]
0x18025f096  call    cs:__imp_CoTaskMemFree
0x18025f09c  lea     r8, [rbp+plEvent]
0x18025f0a0  mov     rcx, rdi
0x18025f0a3  lea     rdx, PKEY_AppUserModel_ID
0x18025f0aa  mov     rax, rbx
0x18025f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f0b2  mov     rax, qword ptr [rbp+plEvent]
0x18025f0b6  mov     ebx, 1
0x18025f0bb  test    rax, rax
0x18025f0be  jz      loc_18025F1BE
0x18025f0c4  cmp     [rax], r13w
0x18025f0c8  jz      loc_18025F1BE
0x18025f0ce  lea     rdx, [rbp+var_18]
0x18025f0d2  mov     [rbp+var_18], r13
0x18025f0d6  mov     rcx, rsi
0x18025f0d9  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18025f0df  mov     r15, rax
0x18025f0e2  test    rax, rax
0x18025f0e5  jz      loc_18025F1B5
0x18025f0eb  mov     r12d, [rax]
0x18025f0ee  mov     edi, r13d
0x18025f0f1  and     r12d, 0FFFFFFFh
0x18025f0f8  cmp     edi, r12d
0x18025f0fb  jnb     loc_18025F1B5
0x18025f101  test    dword ptr [r15], 10000000h
0x18025f108  lea     r13, [r15+8]
0x18025f10c  jz      short loc_18025F112
0x18025f10e  mov     r13, [r13+0]
0x18025f112  mov     eax, edi
0x18025f114  mov     r13, [r13+rax*8+0]
0x18025f119  test    r13, r13
0x18025f11c  jz      short loc_18025F176
0x18025f11e  mov     rax, [r13+0]
0x18025f122  lea     r8, [rbp+var_20]
0x18025f126  lea     rdx, _GUID_5b485fb6_49e4_4d60_9ac4_19ea5e074d57
0x18025f12d  mov     [rbp+var_20], 0
0x18025f135  mov     rcx, r13
0x18025f138  mov     rax, [rax+0C8h]
0x18025f13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f144  test    eax, eax
0x18025f146  js      short loc_18025F176
0x18025f148  mov     rcx, [rbp+var_20]
0x18025f14c  mov     rax, [rcx]
0x18025f14f  mov     rax, [rax+8]
0x18025f153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f158  or      ecx, 0FFFFFFFFh
0x18025f15b  mov     dword ptr [rsp+60h+ppvItem], ebx; bIgnoreCase
0x18025f15f  mov     r9d, ecx; cchCount2
0x18025f162  mov     edx, ecx; cchCount1
0x18025f164  mov     rcx, qword ptr [rbp+plEvent]; lpString1
0x18025f168  mov     r8, rax; lpString2
0x18025f16b  call    cs:__imp_CompareStringOrdinal
0x18025f171  cmp     eax, 2
0x18025f174  jnz     short loc_18025F17D
0x18025f176  add     edi, ebx
0x18025f178  jmp     loc_18025F0F8
0x18025f17d  mov     rdx, r13
0x18025f180  mov     rcx, rsi
0x18025f183  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x18025f189  test    eax, eax
0x18025f18b  js      short loc_18025F1B5
0x18025f18d  cmp     r12d, ebx
0x18025f190  jnz     short loc_18025F1B5
0x18025f192  mov     rcx, rsi; this
0x18025f195  call    ?_SetEmptyListMessage@CSimpleAppList@@AEAAX_N@Z; CSimpleAppList::_SetEmptyListMessage(bool)
0x18025f19a  mov     rcx, [rsi+0D0h]
0x18025f1a1  test    rcx, rcx
0x18025f1a4  jz      short loc_18025F1B5
0x18025f1a6  mov     rax, [rcx]
0x18025f1a9  mov     rax, [rax+0A8h]
0x18025f1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f1b5  lea     rcx, [rbp+var_18]; this
0x18025f1b9  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18025f1be  mov     rcx, r14; pidl
0x18025f1c1  call    cs:__imp_ILFree
0x18025f1c7  lea     rcx, [rbp+pppidl]
0x18025f1cb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18025f1d0  mov     rcx, qword ptr [rbp+plEvent]
0x18025f1d4  jmp     loc_18025EF29
0x18025f1d9  lea     rcx, [rbp+pppidl]
0x18025f1dd  mov     [rbp+pppidl], r13
0x18025f1e1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18025f1e6  mov     rcx, [rsi+0C8h]
0x18025f1ed  lea     rax, [rbp+pppidl]
0x18025f1f1  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18025f1f8  mov     [rsp+60h+ppvItem], rax; ppvItem
0x18025f1fd  mov     r8, r14; pidl
0x18025f200  xor     edx, edx; psfParent
0x18025f202  mov     rcx, [rcx+18h]; pidlParent
0x18025f206  call    cs:__imp_SHCreateItemWithParent
0x18025f20c  test    eax, eax
0x18025f20e  js      short loc_18025F285
0x18025f210  mov     rcx, [rsi+0E8h]
0x18025f217  lea     r9, [rbp+plEvent]
0x18025f21b  mov     rdx, [rbp+pppidl]
0x18025f21f  mov     r8d, 2
0x18025f225  mov     qword ptr [rbp+plEvent], r13
0x18025f229  mov     rax, [rcx]
0x18025f22c  mov     rax, [rax+30h]
0x18025f230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f235  test    eax, eax
0x18025f237  js      short loc_18025F285
0x18025f239  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x18025f23e  imul    ecx, eax, 158h
0x18025f244  movd    xmm0, ecx
0x18025f248  mov     rcx, qword ptr [rbp+plEvent]
0x18025f24c  cvtdq2ps xmm0, xmm0
0x18025f24f  divss   xmm0, cs:__real@42c80000
0x18025f257  cvttss2si edx, xmm0
0x18025f25b  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18025f261  mov     rdx, qword ptr [rbp+plEvent]
0x18025f265  lea     r8, ?_s_SortItemsProc@CSimpleAppList@@CAHPEBX0@Z; CSimpleAppList::_s_SortItemsProc(void const *,void const *)
0x18025f26c  mov     rcx, rsi
0x18025f26f  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z; DirectUI::Element::Add(DirectUI::Element *,int (*)(void const *,void const *))
0x18025f275  test    eax, eax
0x18025f277  jns     short loc_18025F285
0x18025f279  mov     rcx, qword ptr [rbp+plEvent]
0x18025f27d  xor     edx, edx
0x18025f27f  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18025f285  mov     rcx, r14; pidl
0x18025f288  call    cs:__imp_ILFree
0x18025f28e  lea     rcx, [rbp+pppidl]
0x18025f292  mov     ebx, 1
0x18025f297  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18025f29c  mov     al, bl
0x18025f29e  mov     rcx, [rbp+var_8]
0x18025f2a2  xor     rcx, rsp; StackCookie
0x18025f2a5  call    __security_check_cookie
0x18025f2aa  mov     rbx, [rsp+60h+arg_8]
0x18025f2b2  add     rsp, 60h
0x18025f2b6  pop     r15
0x18025f2b8  pop     r14
0x18025f2ba  pop     r13
0x18025f2bc  pop     r12
0x18025f2be  pop     rdi
0x18025f2bf  pop     rsi
0x18025f2c0  pop     rbp
0x18025f2c1  retn
```
