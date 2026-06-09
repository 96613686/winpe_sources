# CWallpaperCore::_InitializePathComboBox(void)

- ea: `0x180040f88`
- end: `0x1800414af`
- name: `?_InitializePathComboBox@CWallpaperCore@@AEAAJXZ`
- size: `1319`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x18003bacc`

## callees

- `0x180002280`
- `0x180002650`
- `0x18000268c`
- `0x18003b0fc`
- `0x180040788`
- `0x180040f88`
- `0x18004277c`
- `0x18004eae4`
- `0x18004eb24`
- `0x180054ebc`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x1800410e0`
- `SHELL32!__imp_ILClone` at `0x1800410e0`
- `SHELL32!__imp_ILFree` at `0x180041129`
- `SHELL32!__imp_ILFree` at `0x180041129`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x180041116`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x180041241`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x1800412c1`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x180041116`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x180041241`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x1800412c1`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x180040fe2`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x180040fe2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041459`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004125e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004125e`
- `USER32!SendMessageW` at `0x18004139a`
- `USER32!SendMessageW` at `0x18004139a`
- `USER32!SetWindowLongPtrW` at `0x18004100b`
- `USER32!SetWindowLongPtrW` at `0x18004100b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180041338`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180041338`
- `DUI70!StrToID` at `0x180041326`
- `DUI70!StrToID` at `0x180041326`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180041350`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180041350`

## string_xrefs

- `0x18004131f`: `ComboBox_PictureFolder`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_InitializePathComboBox(CWallpaperCore *this)
{
  struct _DPA *v2; // rcx
  HWND v3; // rax
  LPITEMIDLIST *v4; // r14
  unsigned int v5; // r8d
  int Instance; // esi
  __int64 v7; // rcx
  __int64 v8; // rcx
  LPITEMIDLIST *v9; // rax
  LPCITEMIDLIST *v10; // r15
  LPITEMIDLIST *v11; // rbx
  LPITEMIDLIST v12; // rcx
  LPITEMIDLIST v13; // rax
  volatile signed __int32 *v14; // rcx
  struct IShellItemArray *v15; // rcx
  unsigned __int16 **v16; // rax
  unsigned __int16 **v17; // rbx
  LPITEMIDLIST v18; // rcx
  int v19; // eax
  volatile signed __int32 *v20; // rcx
  LPITEMIDLIST v21; // rcx
  signed int LastError; // eax
  DirectUI::Element *v23; // rbx
  unsigned __int16 v24; // ax
  struct DirectUI::Element *Descendent; // r14
  __int64 ClassInfoPtr; // rbx
  HWND v27; // rax
  unsigned int i; // ebx
  struct _DPA *v29; // rcx
  int v30; // eax
  _DWORD *Ptr; // r15
  __int64 v32; // rcx
  int v33; // eax
  unsigned int j; // ebx
  struct _DPA *v35; // rcx
  int v36; // eax
  char *v37; // rax
  __int64 v38; // rcx
  char *v39; // r15
  int v40; // eax
  __int64 v41; // rcx
  int v42; // eax
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  CFileSource *v45; // [rsp+48h] [rbp-B8h] BYREF
  struct IShellItemArray *v46; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = (struct _DPA *)*((_QWORD *)this + 10);
  if ( v2 )
    DPA_DeleteAllPtrs(v2);
  v3 = (HWND)SHCreateWorkerWindowW(CWallpaperCore::s_WndProcListener, 0, 0, 0, 0, this);
  *((_QWORD *)this + 7) = v3;
  if ( v3 )
  {
    SetWindowLongPtrW(v3, -21, (LONG_PTR)this);
    v4 = (LPITEMIDLIST *)((char *)this + 432);
    Instance = CDefTaskLock::CreateInstance(
                 (struct IUnknown *)this + 2,
                 *((HWND *)this + 7),
                 v5,
                 (struct CDefTaskLock **)this + 54);
    if ( Instance < 0 )
      goto LABEL_32;
    v7 = *((_QWORD *)this + 52);
    v44 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 136LL))(v7, &v44) >= 0 && (v44 & 2) != 0 )
    {
      v8 = *((_QWORD *)this + 52);
      v46 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, struct IShellItemArray **))(*(_QWORD *)v8 + 104LL))(v8, &v46) )
      {
        v45 = 0;
        if ( (int)CFileSource::s_CreateFromShellItemArray(v46, &v45) >= 0 )
        {
          v9 = (LPITEMIDLIST *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          v10 = (LPCITEMIDLIST *)v45;
          v11 = v9;
          if ( v9 )
          {
            v12 = *v4;
            v9[1] = *v4;
            _InterlockedAdd((volatile signed __int32 *)v12[34].mkid.abID, 1u);
            v13 = ILClone(v10[1]);
            *v11 = v13;
            if ( !v13
              || !(unsigned int)SHQueueUserWorkItem(
                                  CWallpaperCore::_LoadCurrentPathFromSlideshowThread,
                                  v11,
                                  0,
                                  0,
                                  0,
                                  0,
                                  16) )
            {
              ILFree(*v11);
              v14 = (volatile signed __int32 *)v11[1];
              if ( v14 && _InterlockedExchangeAdd(v14 + 26, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v14 + 16LL))(v14, 1);
              operator delete(v11, (const struct std::nothrow_t *)0x10);
            }
          }
          CFileSource::Release((CFileSource *)v10);
        }
      }
      v15 = v46;
      v46 = 0;
      if ( v15 )
        ((void (__fastcall *)(struct IShellItemArray *))v15->lpVtbl->Release)(v15);
      goto LABEL_32;
    }
    v16 = (unsigned __int16 **)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( !v16 )
    {
LABEL_32:
      _InterlockedAdd((volatile signed __int32 *)(*v4)[34].mkid.abID, 1u);
      if ( !(unsigned int)SHQueueUserWorkItem(CWallpaperCore::_LoadMRUPathsThread, *v4, 0, 0, 0, 0, 16) )
      {
        v21 = *v4;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*v4)[34].mkid.abID, 0xFFFFFFFF) == 1 )
        {
          if ( v21 )
            (*(void (__fastcall **)(LPITEMIDLIST, __int64))(*(_QWORD *)&v21->mkid.cb + 16LL))(v21, 1);
        }
      }
      goto LABEL_41;
    }
    *(_OWORD *)v16 = 0;
    v18 = *v4;
    v16[1] = (unsigned __int16 *)*v4;
    _InterlockedAdd((volatile signed __int32 *)v18[34].mkid.abID, 1u);
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 **))(**((_QWORD **)this + 52) + 32LL))(
            *((_QWORD *)this + 52),
            0,
            v16);
    Instance = v19;
    if ( v19 == 1 )
    {
      *((_BYTE *)this + 185) = 1;
      CoTaskMemFree(*v17);
      Instance = CWallpaperCore::_PathOfFirstMonitorWithWallpaper(this, v17);
      if ( Instance < 0 )
        goto LABEL_28;
      if ( !**v17 )
        *((_BYTE *)this + 185) = 0;
    }
    else if ( v19 < 0 )
    {
      goto LABEL_28;
    }
    if ( (unsigned int)SHQueueUserWorkItem(CWallpaperCore::_LoadCurrentPathThread, v17, 0, 0, 0, 0, 16) )
    {
      Instance = 0;
      goto LABEL_32;
    }
    Instance = -2147467259;
LABEL_28:
    CoTaskMemFree(*v17);
    v20 = (volatile signed __int32 *)v17[1];
    if ( v20 && _InterlockedExchangeAdd(v20 + 26, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v20 + 16LL))(v20, 1);
    operator delete(v17, (const struct std::nothrow_t *)0x10);
    goto LABEL_32;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
  Instance = LastError;
LABEL_41:
  v23 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v24 = StrToID(L"ComboBox_PictureFolder");
  Descendent = DirectUI::Element::FindDescendent(v23, v24);
  if ( Descendent )
  {
    ClassInfoPtr = DirectUI::Combobox::GetClassInfoPtr();
    if ( (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 280LL))(Descendent) == ClassInfoPtr )
    {
      v27 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
      SendMessageW(v27, 0x14Bu, 0, 0);
      for ( i = 0; ; ++i )
      {
        v29 = (struct _DPA *)*((_QWORD *)this + 12);
        v30 = v29 ? *(_DWORD *)v29 : 0;
        if ( (int)i >= v30 )
          break;
        Ptr = DPA_GetPtr(v29, (int)i);
        v33 = CWallpaperCore::_FillComboItem(v32, Descendent, Ptr + 135, i, 2);
        if ( v33 != -1 )
          Ptr[270] = v33;
      }
      for ( j = 0; ; ++j )
      {
        v35 = (struct _DPA *)*((_QWORD *)this + 11);
        v36 = v35 ? *(_DWORD *)v35 : 0;
        if ( (int)j >= v36 )
          break;
        v37 = (char *)DPA_GetPtr(v35, (int)j);
        v39 = v37;
        if ( v37 )
        {
          v40 = CWallpaperCore::_FillComboItem(v38, Descendent, v37 + 8, j, 3);
          if ( v40 != -1 )
            *((_DWORD *)v39 + 132) = v40;
        }
      }
      if ( LoadStringW(g_hinst, 0x48u, Buffer, 260) )
      {
        v42 = CWallpaperCore::_FillComboItem(v41, Descendent, Buffer, 0, 1);
        if ( v42 != -1 )
          *((_DWORD *)this + 54) = v42;
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180040f88  push    rbp
0x180040f8a  push    rbx
0x180040f8b  push    rsi
0x180040f8c  push    rdi
0x180040f8d  push    r12
0x180040f8f  push    r13
0x180040f91  push    r14
0x180040f93  push    r15
0x180040f95  lea     rbp, [rsp-188h]
0x180040f9d  sub     rsp, 288h
0x180040fa4  mov     rax, cs:__security_cookie
0x180040fab  xor     rax, rsp
0x180040fae  mov     [rbp+1C0h+var_50], rax
0x180040fb5  mov     rdi, rcx
0x180040fb8  xor     r12d, r12d
0x180040fbb  mov     rcx, [rcx+50h]; hdpa
0x180040fbf  test    rcx, rcx
0x180040fc2  jz      short loc_180040FC9
0x180040fc4  call    DPA_DeleteAllPtrs
0x180040fc9  mov     [rsp+2C0h+var_298], rdi
0x180040fce  lea     rcx, ?s_WndProcListener@CWallpaperCore@@CA_JPEAUHWND__@@I_K_J@Z; CWallpaperCore::s_WndProcListener(HWND__ *,uint,unsigned __int64,__int64)
0x180040fd5  xor     r9d, r9d
0x180040fd8  mov     [rsp+2C0h+var_2A0], r12
0x180040fdd  xor     r8d, r8d
0x180040fe0  xor     edx, edx
0x180040fe2  call    cs:__imp_SHCreateWorkerWindowW
0x180040fe9  nop     dword ptr [rax+rax+00h]
0x180040fee  mov     [rdi+38h], rax
0x180040ff2  mov     r13d, 1
0x180040ff8  test    rax, rax
0x180040ffb  jz      loc_1800412F7
0x180041001  mov     r8, rdi; dwNewLong
0x180041004  lea     edx, [r13-16h]; nIndex
0x180041008  mov     rcx, rax; hWnd
0x18004100b  call    cs:__imp_SetWindowLongPtrW
0x180041012  nop     dword ptr [rax+rax+00h]
0x180041017  mov     rdx, [rdi+38h]; HWND
0x18004101b  lea     r14, [rdi+1B0h]
0x180041022  mov     r9, r14; struct CDefTaskLock **
0x180041025  lea     rcx, [rdi+10h]; struct IUnknown *
0x180041029  call    ?CreateInstance@CDefTaskLock@@SAJPEAUIUnknown@@PEAUHWND__@@IPEAPEAV1@@Z; CDefTaskLock::CreateInstance(IUnknown *,HWND__ *,uint,CDefTaskLock * *)
0x18004102e  lea     r15d, [r13+0Fh]
0x180041032  mov     esi, eax
0x180041034  test    eax, eax
0x180041036  js      loc_18004129A
0x18004103c  mov     rcx, [rdi+1A0h]
0x180041043  mov     [rsp+2C0h+var_280], r12d
0x180041048  mov     rdx, [rcx]
0x18004104b  mov     rax, [rdx+88h]
0x180041052  lea     rdx, [rsp+2C0h+var_280]
0x180041057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004105c  test    eax, eax
0x18004105e  js      loc_180041199
0x180041064  test    byte ptr [rsp+2C0h+var_280], 2
0x180041069  jz      loc_180041199
0x18004106f  mov     rcx, [rdi+1A0h]
0x180041076  lea     rdx, [rsp+2C0h+var_270]
0x18004107b  mov     [rsp+2C0h+var_270], r12
0x180041080  mov     rax, [rcx]
0x180041083  mov     rax, [rax+68h]
0x180041087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004108c  test    eax, eax
0x18004108e  jnz     loc_180041175
0x180041094  mov     rcx, [rsp+2C0h+var_270]; struct IShellItemArray *
0x180041099  lea     rdx, [rsp+2C0h+var_278]; struct CFileSource **
0x18004109e  mov     [rsp+2C0h+var_278], r12
0x1800410a3  call    ?s_CreateFromShellItemArray@CFileSource@@SAJPEAUIShellItemArray@@PEAPEAV1@@Z; CFileSource::s_CreateFromShellItemArray(IShellItemArray *,CFileSource * *)
0x1800410a8  test    eax, eax
0x1800410aa  js      loc_180041175
0x1800410b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800410b7  mov     ecx, r15d; unsigned __int64
0x1800410ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800410bf  mov     r15, [rsp+2C0h+var_278]
0x1800410c4  mov     rbx, rax
0x1800410c7  test    rax, rax
0x1800410ca  jz      loc_180041167
0x1800410d0  mov     rcx, [r14]
0x1800410d3  mov     [rax+8], rcx
0x1800410d7  lock add [rcx+68h], r13d
0x1800410dc  mov     rcx, [r15+8]; pidl
0x1800410e0  call    cs:__imp_ILClone
0x1800410e7  nop     dword ptr [rax+rax+00h]
0x1800410ec  mov     [rbx], rax
0x1800410ef  test    rax, rax
0x1800410f2  jz      short loc_180041126
0x1800410f4  mov     [rsp+2C0h+var_290], 10h
0x1800410fc  lea     rcx, ?_LoadCurrentPathFromSlideshowThread@CWallpaperCore@@CAKPEAX@Z; CWallpaperCore::_LoadCurrentPathFromSlideshowThread(void *)
0x180041103  mov     [rsp+2C0h+var_298], r12
0x180041108  xor     r9d, r9d
0x18004110b  xor     r8d, r8d
0x18004110e  mov     [rsp+2C0h+var_2A0], r12
0x180041113  mov     rdx, rbx
0x180041116  call    cs:__imp_SHQueueUserWorkItem
0x18004111d  nop     dword ptr [rax+rax+00h]
0x180041122  test    eax, eax
0x180041124  jnz     short loc_180041167
0x180041126  mov     rcx, [rbx]; pidl
0x180041129  call    cs:__imp_ILFree
0x180041130  nop     dword ptr [rax+rax+00h]
0x180041135  mov     rcx, [rbx+8]
0x180041139  test    rcx, rcx
0x18004113c  jz      short loc_18004115A
0x18004113e  or      eax, 0FFFFFFFFh
0x180041141  lock xadd [rcx+68h], eax
0x180041146  cmp     eax, r13d
0x180041149  jnz     short loc_18004115A
0x18004114b  mov     rax, [rcx]
0x18004114e  mov     edx, r13d
0x180041151  mov     rax, [rax+10h]
0x180041155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004115a  mov     edx, 10h; struct std::nothrow_t *
0x18004115f  mov     rcx, rbx; void *
0x180041162  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180041167  mov     rcx, r15; this
0x18004116a  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x18004116f  mov     r15d, 10h
0x180041175  mov     rcx, [rsp+2C0h+var_270]
0x18004117a  mov     [rsp+2C0h+var_270], r12
0x18004117f  test    rcx, rcx
0x180041182  jz      loc_18004129A
0x180041188  mov     rax, [rcx]
0x18004118b  mov     rax, [rax+10h]
0x18004118f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041194  jmp     loc_18004129A
0x180041199  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800411a0  mov     rcx, r15; unsigned __int64
0x1800411a3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800411a8  mov     rbx, rax
0x1800411ab  test    rax, rax
0x1800411ae  jz      loc_18004129A
0x1800411b4  xorps   xmm0, xmm0
0x1800411b7  movups  xmmword ptr [rax], xmm0
0x1800411ba  mov     rcx, [r14]
0x1800411bd  mov     [rax+8], rcx
0x1800411c1  lock add [rcx+68h], r13d
0x1800411c6  mov     rcx, [rdi+1A0h]
0x1800411cd  mov     r8, rbx
0x1800411d0  mov     rdx, [rcx]
0x1800411d3  mov     rax, [rdx+20h]
0x1800411d7  xor     edx, edx
0x1800411d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411de  mov     esi, eax
0x1800411e0  cmp     eax, r13d
0x1800411e3  jnz     short loc_18004121E
0x1800411e5  mov     [rdi+0B9h], r13b
0x1800411ec  mov     rcx, [rbx]; pv
0x1800411ef  call    cs:__imp_CoTaskMemFree
0x1800411f6  nop     dword ptr [rax+rax+00h]
0x1800411fb  mov     rdx, rbx; unsigned __int16 **
0x1800411fe  mov     rcx, rdi; this
0x180041201  call    ?_PathOfFirstMonitorWithWallpaper@CWallpaperCore@@AEAAJPEAPEAG@Z; CWallpaperCore::_PathOfFirstMonitorWithWallpaper(ushort * *)
0x180041206  mov     esi, eax
0x180041208  test    eax, eax
0x18004120a  js      short loc_18004125B
0x18004120c  mov     rax, [rbx]
0x18004120f  cmp     [rax], r12w
0x180041213  jnz     short loc_180041222
0x180041215  mov     [rdi+0B9h], r12b
0x18004121c  jmp     short loc_180041222
0x18004121e  test    eax, eax
0x180041220  js      short loc_18004125B
0x180041222  mov     [rsp+2C0h+var_290], r15d
0x180041227  lea     rcx, ?_LoadCurrentPathThread@CWallpaperCore@@CAKPEAX@Z; CWallpaperCore::_LoadCurrentPathThread(void *)
0x18004122e  mov     [rsp+2C0h+var_298], r12
0x180041233  xor     r9d, r9d
0x180041236  xor     r8d, r8d
0x180041239  mov     [rsp+2C0h+var_2A0], r12
0x18004123e  mov     rdx, rbx
0x180041241  call    cs:__imp_SHQueueUserWorkItem
0x180041248  nop     dword ptr [rax+rax+00h]
0x18004124d  test    eax, eax
0x18004124f  jz      short loc_180041256
0x180041251  mov     esi, r12d
0x180041254  jmp     short loc_18004129A
0x180041256  mov     esi, 80004005h
0x18004125b  mov     rcx, [rbx]; pv
0x18004125e  call    cs:__imp_CoTaskMemFree
0x180041265  nop     dword ptr [rax+rax+00h]
0x18004126a  mov     rcx, [rbx+8]
0x18004126e  test    rcx, rcx
0x180041271  jz      short loc_18004128F
0x180041273  or      eax, 0FFFFFFFFh
0x180041276  lock xadd [rcx+68h], eax
0x18004127b  cmp     eax, r13d
0x18004127e  jnz     short loc_18004128F
0x180041280  mov     rax, [rcx]
0x180041283  mov     edx, r13d
0x180041286  mov     rax, [rax+10h]
0x18004128a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004128f  mov     rdx, r15; struct std::nothrow_t *
0x180041292  mov     rcx, rbx; void *
0x180041295  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004129a  mov     rax, [r14]
0x18004129d  lock add [rax+68h], r13d
0x1800412a2  mov     rdx, [r14]
0x1800412a5  lea     rcx, ?_LoadMRUPathsThread@CWallpaperCore@@CAKPEAX@Z; CWallpaperCore::_LoadMRUPathsThread(void *)
0x1800412ac  mov     [rsp+2C0h+var_290], r15d
0x1800412b1  xor     r9d, r9d
0x1800412b4  mov     [rsp+2C0h+var_298], r12
0x1800412b9  xor     r8d, r8d
0x1800412bc  mov     [rsp+2C0h+var_2A0], r12
0x1800412c1  call    cs:__imp_SHQueueUserWorkItem
0x1800412c8  nop     dword ptr [rax+rax+00h]
0x1800412cd  test    eax, eax
0x1800412cf  jnz     short loc_18004131B
0x1800412d1  mov     rcx, [r14]
0x1800412d4  or      eax, 0FFFFFFFFh
0x1800412d7  lock xadd [rcx+68h], eax
0x1800412dc  cmp     eax, r13d
0x1800412df  jnz     short loc_18004131B
0x1800412e1  test    rcx, rcx
0x1800412e4  jz      short loc_18004131B
0x1800412e6  mov     rax, [rcx]
0x1800412e9  mov     edx, r13d
0x1800412ec  mov     rax, [rax+10h]
0x1800412f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412f5  jmp     short loc_18004131B
0x1800412f7  call    cs:__imp_GetLastError
0x1800412fe  nop     dword ptr [rax+rax+00h]
0x180041303  test    eax, eax
0x180041305  jle     short loc_18004130F
0x180041307  movzx   eax, ax
0x18004130a  or      eax, 80070000h
0x18004130f  mov     esi, 80004005h
0x180041314  test    eax, eax
0x180041316  cmovns  eax, esi
0x180041319  mov     esi, eax
0x18004131b  mov     rbx, [rdi+20h]
0x18004131f  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x180041326  call    cs:__imp_StrToID
0x18004132d  nop     dword ptr [rax+rax+00h]
0x180041332  movzx   edx, ax
0x180041335  mov     rcx, rbx
0x180041338  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18004133f  nop     dword ptr [rax+rax+00h]
0x180041344  mov     r14, rax
0x180041347  test    rax, rax
0x18004134a  jz      loc_180041489
0x180041350  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x180041357  nop     dword ptr [rax+rax+00h]
0x18004135c  mov     rcx, [r14]
0x18004135f  mov     rbx, rax
0x180041362  mov     rax, [rcx+118h]
0x180041369  mov     rcx, r14
0x18004136c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041371  cmp     rax, rbx
0x180041374  jnz     loc_180041489
0x18004137a  mov     rax, [r14]
0x18004137d  mov     rcx, r14
0x180041380  mov     rax, [rax+168h]
0x180041387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004138c  xor     r9d, r9d; lParam
0x18004138f  xor     r8d, r8d; wParam
0x180041392  mov     edx, 14Bh; Msg
0x180041397  mov     rcx, rax; hWnd
0x18004139a  call    cs:__imp_SendMessageW
0x1800413a1  nop     dword ptr [rax+rax+00h]
0x1800413a6  mov     ebx, r12d
0x1800413a9  mov     rcx, [rdi+60h]; hdpa
0x1800413ad  test    rcx, rcx
0x1800413b0  jz      short loc_1800413B6
0x1800413b2  mov     eax, [rcx]
0x1800413b4  jmp     short loc_1800413B9
0x1800413b6  mov     eax, r12d
0x1800413b9  cmp     ebx, eax
0x1800413bb  jge     short loc_1800413F3
0x1800413bd  movsxd  rdx, ebx; i
0x1800413c0  call    DPA_GetPtr
0x1800413c5  mov     r9d, ebx
0x1800413c8  mov     dword ptr [rsp+2C0h+var_2A0], 2
0x1800413d0  mov     rdx, r14
0x1800413d3  mov     r15, rax
0x1800413d6  lea     r8, [rax+21Ch]
0x1800413dd  call    ?_FillComboItem@CWallpaperCore@@AEAAHPEAVCombobox@DirectUI@@PEBGHW4PATHTYPE@1@@Z; CWallpaperCore::_FillComboItem(DirectUI::Combobox *,ushort const *,int,CWallpaperCore::PATHTYPE)
0x1800413e2  cmp     eax, 0FFFFFFFFh
0x1800413e5  jz      short loc_1800413EE
0x1800413e7  mov     [r15+438h], eax
0x1800413ee  add     ebx, r13d
0x1800413f1  jmp     short loc_1800413A9
0x1800413f3  mov     ebx, r12d
0x1800413f6  mov     rcx, [rdi+58h]; hdpa
0x1800413fa  test    rcx, rcx
0x1800413fd  jz      short loc_180041403
0x1800413ff  mov     eax, [rcx]
0x180041401  jmp     short loc_180041406
0x180041403  mov     eax, r12d
0x180041406  cmp     ebx, eax
0x180041408  jge     short loc_180041442
0x18004140a  movsxd  rdx, ebx; i
0x18004140d  call    DPA_GetPtr
0x180041412  mov     r15, rax
0x180041415  test    rax, rax
0x180041418  jz      short loc_18004143D
0x18004141a  lea     r8, [rax+8]
0x18004141e  mov     dword ptr [rsp+2C0h+var_2A0], 3
0x180041426  mov     r9d, ebx
0x180041429  mov     rdx, r14
0x18004142c  call    ?_FillComboItem@CWallpaperCore@@AEAAHPEAVCombobox@DirectUI@@PEBGHW4PATHTYPE@1@@Z; CWallpaperCore::_FillComboItem(DirectUI::Combobox *,ushort const *,int,CWallpaperCore::PATHTYPE)
0x180041431  cmp     eax, 0FFFFFFFFh
0x180041434  jz      short loc_18004143D
  ... truncated ...
```
