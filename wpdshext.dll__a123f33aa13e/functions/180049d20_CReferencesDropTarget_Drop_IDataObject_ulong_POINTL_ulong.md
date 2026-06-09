# CReferencesDropTarget::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x180049d20`
- end: `0x18004a541`
- name: `?Drop@CReferencesDropTarget@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `2081`
- prototype: `int(CReferencesDropTarget *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004190`
- `0x1800082e0`
- `0x18000c180`
- `0x18000d610`
- `0x18000ef50`
- `0x180017724`
- `0x1800285c8`
- `0x180029730`
- `0x18002ff5c`
- `0x180032298`
- `0x180035590`
- `0x1800361ba`
- `0x1800496e0`
- `0x180049d20`
- `0x1800535f8`
- `0x180053794`
- `0x180053fd8`
- `0x180054524`
- `0x18005fb88`
- `0x18006c108`
- `0x180078010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18004a4b7`
- `KERNEL32!GlobalFree` at `0x18004a4b7`
- `KERNEL32!GetCurrentThreadId` at `0x180049f8d`
- `KERNEL32!GetCurrentThreadId` at `0x180049f8d`
- `SHLWAPI!PathRemoveExtensionW` at `0x18004a3f2`
- `SHLWAPI!PathRemoveExtensionW` at `0x18004a3f2`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18004a164`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18004a164`
- `USER32!LoadStringW` at `0x18004a07e`
- `USER32!LoadStringW` at `0x18004a1ab`
- `USER32!LoadStringW` at `0x18004a07e`
- `USER32!LoadStringW` at `0x18004a1ab`
- `USER32!SendMessageW` at `0x18004a441`
- `USER32!SendMessageW` at `0x18004a478`
- `USER32!SendMessageW` at `0x18004a441`
- `USER32!SendMessageW` at `0x18004a478`
- `USER32!GetDlgItem` at `0x180049db4`
- `USER32!GetDlgItem` at `0x180049db4`
- `ole32!PropVariantClear` at `0x18004a494`
- `ole32!PropVariantClear` at `0x18004a494`
- `ole32!CoCreateInstance` at `0x180049e89`
- `ole32!CoCreateInstance` at `0x180049e89`
- `SHELL32!SHGetFileInfoW` at `0x18004a3e4`
- `SHELL32!SHGetFileInfoW` at `0x18004a3e4`
- `SHELL32!__imp_ILFree` at `0x18004a486`
- `SHELL32!__imp_ILFree` at `0x18004a486`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CReferencesDropTarget::Drop(
        CReferencesDropTarget *this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  char *v7; // r15
  HWND DlgItem; // rax
  int v9; // ebx
  HRESULT Instance; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const struct std::nothrow_t *v13; // rdx
  CProgressUI *v14; // rax
  CProgressUI *v15; // rax
  CProgressUI *v16; // r14
  int started; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD CurrentThreadId; // eax
  unsigned int i; // edi
  CContentFolder *v22; // rcx
  ITEMIDLIST *v23; // r13
  CContentFolder *v24; // rcx
  unsigned int v25; // r9d
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-818h] BYREF
  int v28; // [rsp+38h] [rbp-810h] BYREF
  unsigned int v29; // [rsp+3Ch] [rbp-80Ch] BYREF
  HGLOBAL hMem; // [rsp+40h] [rbp-808h] BYREF
  struct IPortableDevicePropVariantCollection *ppv; // [rsp+48h] [rbp-800h] BYREF
  struct IPortableDevice *v32; // [rsp+50h] [rbp-7F8h] BYREF
  struct CONTENTITEM *v33; // [rsp+58h] [rbp-7F0h] BYREF
  HWND hWnd; // [rsp+60h] [rbp-7E8h]
  __int64 v35; // [rsp+68h] [rbp-7E0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-7D8h] BYREF
  CProgressUI *v37; // [rsp+78h] [rbp-7D0h]
  HWND v38; // [rsp+80h] [rbp-7C8h]
  char *v39; // [rsp+88h] [rbp-7C0h]
  int v40; // [rsp+90h] [rbp-7B8h] BYREF
  PROPVARIANT pvar; // [rsp+98h] [rbp-7B0h] BYREF
  _DWORD lParam[6]; // [rsp+B0h] [rbp-798h] BYREF
  WCHAR *v43; // [rsp+C8h] [rbp-780h]
  int v44; // [rsp+D0h] [rbp-778h]
  int iIcon; // [rsp+D4h] [rbp-774h]
  SHFILEINFOW psfi; // [rsp+110h] [rbp-738h] BYREF
  struct _GUID v47; // [rsp+3D0h] [rbp-478h] BYREF
  GUID v48; // [rsp+3E0h] [rbp-468h]
  WCHAR Buffer[264]; // [rsp+3F0h] [rbp-458h] BYREF
  WCHAR pszPath[264]; // [rsp+600h] [rbp-248h] BYREF

  hMem = 0;
  memset_0(Buffer, 0, 0x208u);
  v29 = 0;
  v28 = 0;
  v47 = WPD_CONTENT_TYPE_AUDIO;
  v48 = WPD_CONTENT_TYPE_VIDEO;
  v32 = 0;
  v36 = 0;
  v35 = 0;
  ppv = 0;
  v7 = (char *)this + 16;
  DlgItem = GetDlgItem(*(HWND *)(*(_QWORD *)v7 + 48LL), 803);
  hWnd = DlgItem;
  if ( !a2 || !a5 || (v39 = v7, !*(_QWORD *)v7) || (v38 = DlgItem) == 0 )
  {
    v9 = -2147024809;
LABEL_81:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids,
        (unsigned int)v9);
    goto LABEL_84;
  }
  Instance = DataObj_CopyHIDA(a2, (struct _IDA **)&hMem);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 15;
LABEL_10:
      WPP_SF_d(v11[2], v12, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)Instance);
      goto LABEL_78;
    }
    goto LABEL_78;
  }
  if ( !hMem )
  {
    v9 = -2147467259;
    goto LABEL_81;
  }
  if ( !*(_DWORD *)hMem )
  {
    v9 = 0;
    goto LABEL_78;
  }
  Instance = CoCreateInstance(
               &CLSID_PortableDevicePropVariantCollection,
               0,
               1u,
               &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
               (LPVOID *)&ppv);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    v14 = (CProgressUI *)operator new(0xB08u, v13);
    v37 = v14;
    if ( !v14 || (v15 = CProgressUI::CProgressUI(v14), (v16 = v15) == 0) )
    {
      v9 = -2147024882;
      goto LABEL_78;
    }
    v37 = v15;
    started = CProgressUI::_Initialize(v15, &String);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 17;
      goto LABEL_25;
    }
    started = CProgressUI::_BeginProgressUI(v16, SPACTION_COPYING, 0x71u);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 18;
      goto LABEL_25;
    }
    CurrentThreadId = GetCurrentThreadId();
    started = CDeviceCache::s_BindToPortableDevice(
                (const unsigned __int16 *)(*(_QWORD *)v7 + 680LL),
                CurrentThreadId,
                0,
                0,
                1,
                &v32);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 19;
      goto LABEL_25;
    }
    started = CProgressUI::_AssociateDevice(v16, v32);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 20;
      goto LABEL_25;
    }
    started = CProgressUI::_StartMarquee(v16);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 21;
      goto LABEL_25;
    }
    LoadStringW(g_hInst, 0x7Eu, Buffer, 260);
    CProgressUI::_ShowFileName(v16, Buffer, &String);
    started = CollectPersistentUniqueIDsUsingContentTypeFilter(v16, (struct _IDA *)hMem, ppv, &v47, 2u, 1);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 22;
      goto LABEL_25;
    }
    if ( started == 1 )
      goto LABEL_53;
    started = ((__int64 (__fastcall *)(struct IPortableDevicePropVariantCollection *, int *))ppv->lpVtbl->GetCount)(
                ppv,
                &v28);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 23;
      goto LABEL_25;
    }
    if ( !v28 )
    {
      CProgressUI::_EndProgressUI(v16);
      ShellMessageBoxW(g_hInst, *(HWND *)(*(_QWORD *)v7 + 48LL), (LPCWSTR)0x10F, (LPCWSTR)0x10E, 0x40u);
      goto LABEL_53;
    }
    LoadStringW(g_hInst, 0x82u, Buffer, 260);
    CProgressUI::_ShowFileName(v16, Buffer, &String);
    started = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v32->lpVtbl->Content)(v32, &v36);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 24;
      goto LABEL_25;
    }
    started = (*(__int64 (__fastcall **)(__int64, struct IPortableDevicePropVariantCollection *, __int64 *))(*(_QWORD *)v36 + 72LL))(
                v36,
                ppv,
                &v35);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 25;
      goto LABEL_25;
    }
    started = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 24LL))(v35, &v29);
    v9 = started;
    if ( started < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v19 = 26;
LABEL_25:
      WPP_SF_d(v18[2], v19, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)started);
LABEL_53:
      CProgressUI::_EndProgressUI(v16);
      (**(void (__fastcall ***)(CProgressUI *, __int64))v16)(v16, 1);
      goto LABEL_78;
    }
    for ( i = 0; ; ++i )
    {
      LODWORD(pidl) = i;
      if ( i >= v29 )
        goto LABEL_53;
      memset(&pvar, 0, sizeof(pvar));
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v35 + 32LL))(v35, i, &pvar);
      if ( v9 >= 0 )
      {
        try
        {
          ((void (__fastcall *)(_QWORD, _QWORD))ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add)(
            *(_QWORD *)v7 + 632LL,
            (LARGE_INTEGER)pvar.hVal.QuadPart);
        }
        catch ( ATL::CAtlException v40 )
        {
          LODWORD(v33) = v40;
          v9 = (int)v33;
          v16 = v37;
          i = (unsigned int)pidl;
          v7 = v39;
          hWnd = v38;
          if ( (int)v33 < 0 )
            goto LABEL_76;
        }
        pidl = 0;
        v9 = CContentFolder::_CreateIDList(
               *(CContentFolder **)(*(_QWORD *)v7 + 16LL),
               v32,
               pvar.bstrVal,
               0,
               &pidl,
               (int *)&v33);
        v23 = pidl;
        if ( v9 >= 0 )
        {
          v33 = CContentFolder::_IsValid(v22, pidl);
          if ( v33 )
          {
            memset_0(&psfi, 0, sizeof(psfi));
            memset_0(pszPath, 0, 0x208u);
            CContentFolder::_Name(v24, v33, pszPath, v25);
            SHGetFileInfoW(pszPath, 0, &psfi, 0x2B8u, 0x4011u);
            PathRemoveExtensionW(pszPath);
            memset_0(lParam, 0, 0x58u);
            lParam[0] = 3;
            v43 = pszPath;
            v44 = 260;
            lParam[1] = SendMessageW(hWnd, 0x1004u, 0, 0);
            iIcon = psfi.iIcon;
            lParam[2] = 0;
            SendMessageW(hWnd, 0x104Du, 0, (LPARAM)lParam);
          }
        }
        if ( v23 )
          ILFree(v23);
      }
LABEL_76:
      PropVariantClear(&pvar);
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 16;
    goto LABEL_10;
  }
LABEL_78:
  if ( hMem )
    GlobalFree(hMem);
  if ( v9 < 0 )
    goto LABEL_81;
LABEL_84:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180049d20  mov     [rsp+arg_10], rbx
0x180049d25  push    rsi
0x180049d26  push    rdi
0x180049d27  push    r13
0x180049d29  push    r14
0x180049d2b  push    r15
0x180049d2d  sub     rsp, 820h
0x180049d34  mov     rax, cs:__security_cookie
0x180049d3b  xor     rax, rsp
0x180049d3e  mov     [rsp+848h+var_38], rax
0x180049d46  mov     rdi, rdx
0x180049d49  mov     r15, rcx
0x180049d4c  xor     esi, esi
0x180049d4e  mov     [rsp+848h+hMem], rsi
0x180049d53  xor     edx, edx; Val
0x180049d55  mov     r8d, 208h; Size
0x180049d5b  lea     rcx, [rsp+848h+Buffer]; void *
0x180049d63  call    memset_0
0x180049d68  mov     [rsp+848h+var_80C], esi
0x180049d6c  mov     [rsp+848h+var_810], esi
0x180049d70  movups  xmm0, xmmword ptr cs:WPD_CONTENT_TYPE_AUDIO.Data1
0x180049d77  movdqu  xmmword ptr [rsp+848h+var_478.Data1], xmm0
0x180049d80  movups  xmm1, xmmword ptr cs:WPD_CONTENT_TYPE_VIDEO.Data1
0x180049d87  movdqu  [rsp+848h+var_468], xmm1
0x180049d90  mov     [rsp+848h+var_7F8], rsi
0x180049d95  mov     [rsp+848h+var_7D8], rsi
0x180049d9a  mov     [rsp+848h+var_7E0], rsi
0x180049d9f  mov     [rsp+848h+var_800], rsi
0x180049da4  add     r15, 10h
0x180049da8  mov     rcx, [r15]
0x180049dab  mov     edx, 323h; nIDDlgItem
0x180049db0  mov     rcx, [rcx+30h]; hDlg
0x180049db4  call    cs:__imp_GetDlgItem
0x180049dba  mov     [rsp+848h+hWnd], rax
0x180049dbf  test    rdi, rdi
0x180049dc2  jnz     short loc_180049DD5
0x180049dc4  mov     ebx, 80070057h
0x180049dc9  lea     rdi, WPP_GLOBAL_Control
0x180049dd0  jmp     loc_18004A4C1
0x180049dd5  cmp     [rsp+848h+arg_20], rsi
0x180049ddd  jz      short loc_180049DC4
0x180049ddf  mov     [rsp+848h+var_7C0], r15
0x180049de7  cmp     [r15], rsi
0x180049dea  jz      short loc_180049DC4
0x180049dec  mov     [rsp+848h+var_7C8], rax
0x180049df4  test    rax, rax
0x180049df7  jz      short loc_180049DC4
0x180049df9  lea     rdx, [rsp+848h+hMem]; struct _IDA **
0x180049dfe  mov     rcx, rdi; struct IDataObject *
0x180049e01  call    ?DataObj_CopyHIDA@@YAJPEAUIDataObject@@PEAPEAU_IDA@@@Z; DataObj_CopyHIDA(IDataObject *,_IDA * *)
0x180049e06  mov     ebx, eax
0x180049e08  test    eax, eax
0x180049e0a  jns     short loc_180049E4A
0x180049e0c  lea     rdi, WPP_GLOBAL_Control
0x180049e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e1a  cmp     rcx, rdi
0x180049e1d  jz      loc_18004A4AD
0x180049e23  test    byte ptr [rcx+1Ch], 2
0x180049e27  jz      loc_18004A4AD
0x180049e2d  mov     edx, 0Fh
0x180049e32  mov     r9d, eax
0x180049e35  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x180049e3c  mov     rcx, [rcx+10h]
0x180049e40  call    WPP_SF_d
0x180049e45  jmp     loc_18004A4AD
0x180049e4a  cmp     [rsp+848h+hMem], rsi
0x180049e4f  jnz     short loc_180049E5B
0x180049e51  mov     ebx, 80004005h
0x180049e56  jmp     loc_180049DC9
0x180049e5b  mov     rax, [rsp+848h+hMem]
0x180049e60  cmp     [rax], esi
0x180049e62  jnz     short loc_180049E6B
0x180049e64  mov     ebx, esi
0x180049e66  jmp     loc_18004A4A6
0x180049e6b  lea     rax, [rsp+848h+var_800]
0x180049e70  mov     [rsp+848h+ppv], rax; ppv
0x180049e75  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x180049e7c  xor     edx, edx; pUnkOuter
0x180049e7e  lea     r8d, [rdx+1]; dwClsContext
0x180049e82  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x180049e89  call    cs:__imp_CoCreateInstance
0x180049e8f  mov     ebx, eax
0x180049e91  test    eax, eax
0x180049e93  jns     short loc_180049EC0
0x180049e95  lea     rdi, WPP_GLOBAL_Control
0x180049e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ea3  cmp     rcx, rdi
0x180049ea6  jz      loc_18004A4AD
0x180049eac  test    byte ptr [rcx+1Ch], 2
0x180049eb0  jz      loc_18004A4AD
0x180049eb6  mov     edx, 10h
0x180049ebb  jmp     loc_180049E32
0x180049ec0  mov     ecx, 0B08h; unsigned __int64
0x180049ec5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180049eca  mov     [rsp+848h+var_7D0], rax
0x180049ecf  test    rax, rax
0x180049ed2  jz      loc_18004A4A1
0x180049ed8  mov     rcx, rax; this
0x180049edb  call    ??0CProgressUI@@QEAA@XZ; CProgressUI::CProgressUI(void)
0x180049ee0  mov     r14, rax
0x180049ee3  test    rax, rax
0x180049ee6  jz      loc_18004A4A1
0x180049eec  mov     [rsp+848h+var_7D0], rax
0x180049ef1  xor     r9d, r9d; int
0x180049ef4  lea     r8d, [r9+1]; int
0x180049ef8  lea     rdi, String
0x180049eff  mov     rdx, rdi; unsigned __int16 *
0x180049f02  mov     rcx, rax; this
0x180049f05  call    ?_Initialize@CProgressUI@@QEAAJPEBGHH@Z; CProgressUI::_Initialize(ushort const *,int,int)
0x180049f0a  mov     ebx, eax
0x180049f0c  test    eax, eax
0x180049f0e  jns     short loc_180049F4E
0x180049f10  lea     rdi, WPP_GLOBAL_Control
0x180049f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f1e  cmp     rcx, rdi
0x180049f21  jz      loc_18004A171
0x180049f27  test    byte ptr [rcx+1Ch], 2
0x180049f2b  jz      loc_18004A171
0x180049f31  mov     edx, 11h
0x180049f36  mov     r9d, eax
0x180049f39  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x180049f40  mov     rcx, [rcx+10h]
0x180049f44  call    WPP_SF_d
0x180049f49  jmp     loc_18004A171
0x180049f4e  mov     edx, 2; enum _SPACTION
0x180049f53  lea     r8d, [rdx+6Fh]; unsigned int
0x180049f57  mov     rcx, r14; this
0x180049f5a  call    ?_BeginProgressUI@CProgressUI@@QEAAJW4_SPACTION@@I@Z; CProgressUI::_BeginProgressUI(_SPACTION,uint)
0x180049f5f  mov     ebx, eax
0x180049f61  test    eax, eax
0x180049f63  jns     short loc_180049F8D
0x180049f65  lea     rdi, WPP_GLOBAL_Control
0x180049f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f73  cmp     rcx, rdi
0x180049f76  jz      loc_18004A171
0x180049f7c  test    byte ptr [rcx+1Ch], 2
0x180049f80  jz      loc_18004A171
0x180049f86  mov     edx, 12h
0x180049f8b  jmp     short loc_180049F36
0x180049f8d  call    cs:__imp_GetCurrentThreadId
0x180049f93  mov     rcx, [r15]
0x180049f96  add     rcx, 2A8h; unsigned __int16 *
0x180049f9d  lea     rdx, [rsp+848h+var_7F8]
0x180049fa2  mov     [rsp+848h+var_820], rdx; struct IPortableDevice **
0x180049fa7  mov     dword ptr [rsp+848h+ppv], 1; int
0x180049faf  xor     r9d, r9d; struct _ITEMIDLIST *
0x180049fb2  xor     r8d, r8d; struct _ITEMIDLIST *
0x180049fb5  mov     edx, eax; unsigned int
0x180049fb7  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x180049fbc  mov     ebx, eax
0x180049fbe  test    eax, eax
0x180049fc0  jns     short loc_180049FED
0x180049fc2  lea     rdi, WPP_GLOBAL_Control
0x180049fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fd0  cmp     rcx, rdi
0x180049fd3  jz      loc_18004A171
0x180049fd9  test    byte ptr [rcx+1Ch], 2
0x180049fdd  jz      loc_18004A171
0x180049fe3  mov     edx, 13h
0x180049fe8  jmp     loc_180049F36
0x180049fed  mov     rdx, [rsp+848h+var_7F8]; struct IPortableDevice *
0x180049ff2  mov     rcx, r14; this
0x180049ff5  call    ?_AssociateDevice@CProgressUI@@QEAAJPEAUIPortableDevice@@@Z; CProgressUI::_AssociateDevice(IPortableDevice *)
0x180049ffa  mov     ebx, eax
0x180049ffc  test    eax, eax
0x180049ffe  jns     short loc_18004A02B
0x18004a000  lea     rdi, WPP_GLOBAL_Control
0x18004a007  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a00e  cmp     rcx, rdi
0x18004a011  jz      loc_18004A171
0x18004a017  test    byte ptr [rcx+1Ch], 2
0x18004a01b  jz      loc_18004A171
0x18004a021  mov     edx, 14h
0x18004a026  jmp     loc_180049F36
0x18004a02b  mov     rcx, r14; this
0x18004a02e  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18004a033  mov     ebx, eax
0x18004a035  test    eax, eax
0x18004a037  jns     short loc_18004A064
0x18004a039  lea     rdi, WPP_GLOBAL_Control
0x18004a040  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a047  cmp     rcx, rdi
0x18004a04a  jz      loc_18004A171
0x18004a050  test    byte ptr [rcx+1Ch], 2
0x18004a054  jz      loc_18004A171
0x18004a05a  mov     edx, 15h
0x18004a05f  jmp     loc_180049F36
0x18004a064  mov     r9d, 104h; cchBufferMax
0x18004a06a  lea     r8, [rsp+848h+Buffer]; lpBuffer
0x18004a072  mov     edx, 7Eh ; '~'; uID
0x18004a077  mov     rcx, cs:g_hInst; hInstance
0x18004a07e  call    cs:__imp_LoadStringW
0x18004a084  mov     r8, rdi; unsigned __int16 *
0x18004a087  lea     rdx, [rsp+848h+Buffer]; unsigned __int16 *
0x18004a08f  mov     rcx, r14; this
0x18004a092  call    ?_ShowFileName@CProgressUI@@QEAAJPEBG0@Z; CProgressUI::_ShowFileName(ushort const *,ushort const *)
0x18004a097  mov     dword ptr [rsp+848h+var_820], 1; int
0x18004a09f  mov     dword ptr [rsp+848h+ppv], 2; unsigned int
0x18004a0a7  lea     r9, [rsp+848h+var_478]; struct _GUID *
0x18004a0af  mov     r8, [rsp+848h+var_800]; struct IPortableDevicePropVariantCollection *
0x18004a0b4  mov     rdx, [rsp+848h+hMem]; struct _IDA *
0x18004a0b9  mov     rcx, r14; struct CProgressUI *
0x18004a0bc  call    ?CollectPersistentUniqueIDsUsingContentTypeFilter@@YAJPEAVCProgressUI@@PEAU_IDA@@PEAUIPortableDevicePropVariantCollection@@PEAU_GUID@@KH@Z; CollectPersistentUniqueIDsUsingContentTypeFilter(CProgressUI *,_IDA *,IPortableDevicePropVariantCollection *,_GUID *,ulong,int)
0x18004a0c1  mov     ebx, eax
0x18004a0c3  test    eax, eax
0x18004a0c5  jns     short loc_18004A0F2
0x18004a0c7  lea     rdi, WPP_GLOBAL_Control
0x18004a0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0d5  cmp     rcx, rdi
0x18004a0d8  jz      loc_18004A171
0x18004a0de  test    byte ptr [rcx+1Ch], 2
0x18004a0e2  jz      loc_18004A171
0x18004a0e8  mov     edx, 16h
0x18004a0ed  jmp     loc_180049F36
0x18004a0f2  cmp     eax, 1
0x18004a0f5  jz      short loc_18004A16A
0x18004a0f7  mov     rcx, [rsp+848h+var_800]
0x18004a0fc  mov     rax, [rcx]
0x18004a0ff  lea     rdx, [rsp+848h+var_810]
0x18004a104  mov     rax, [rax+18h]
0x18004a108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a10d  mov     ebx, eax
0x18004a10f  test    eax, eax
0x18004a111  jns     short loc_18004A136
0x18004a113  lea     rdi, WPP_GLOBAL_Control
0x18004a11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a121  cmp     rcx, rdi
0x18004a124  jz      short loc_18004A171
0x18004a126  test    byte ptr [rcx+1Ch], 2
0x18004a12a  jz      short loc_18004A171
0x18004a12c  mov     edx, 17h
0x18004a131  jmp     loc_180049F36
0x18004a136  cmp     [rsp+848h+var_810], esi
0x18004a13a  jnz     short loc_18004A191
0x18004a13c  mov     rcx, r14; this
0x18004a13f  call    ?_EndProgressUI@CProgressUI@@QEAAJXZ; CProgressUI::_EndProgressUI(void)
0x18004a144  mov     rdx, [r15]
0x18004a147  mov     dword ptr [rsp+848h+ppv], 40h ; '@'; fuStyle
0x18004a14f  mov     r9d, 10Eh; lpcTitle
0x18004a155  lea     r8d, [r9+1]; lpcText
0x18004a159  mov     rdx, [rdx+30h]; hWnd
0x18004a15d  mov     rcx, cs:g_hInst; hAppInst
0x18004a164  call    cs:__imp_ShellMessageBoxW
0x18004a16a  lea     rdi, WPP_GLOBAL_Control
0x18004a171  mov     rcx, r14; this
0x18004a174  call    ?_EndProgressUI@CProgressUI@@QEAAJXZ; CProgressUI::_EndProgressUI(void)
0x18004a179  mov     rax, [r14]
0x18004a17c  mov     edx, 1
0x18004a181  mov     rcx, r14
0x18004a184  mov     rax, [rax]
0x18004a187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a18c  jmp     loc_18004A4AD
0x18004a191  mov     r9d, 104h; cchBufferMax
0x18004a197  lea     r8, [rsp+848h+Buffer]; lpBuffer
0x18004a19f  mov     edx, 82h; uID
0x18004a1a4  mov     rcx, cs:g_hInst; hInstance
0x18004a1ab  call    cs:__imp_LoadStringW
0x18004a1b1  mov     r8, rdi; unsigned __int16 *
0x18004a1b4  lea     rdx, [rsp+848h+Buffer]; unsigned __int16 *
0x18004a1bc  mov     rcx, r14; this
0x18004a1bf  call    ?_ShowFileName@CProgressUI@@QEAAJPEBG0@Z; CProgressUI::_ShowFileName(ushort const *,ushort const *)
0x18004a1c4  mov     rcx, [rsp+848h+var_7F8]
0x18004a1c9  mov     rax, [rcx]
0x18004a1cc  lea     rdx, [rsp+848h+var_7D8]
0x18004a1d1  mov     rax, [rax+28h]
0x18004a1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1da  mov     ebx, eax
0x18004a1dc  test    eax, eax
0x18004a1de  jns     short loc_18004A20B
0x18004a1e0  lea     rdi, WPP_GLOBAL_Control
0x18004a1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1ee  cmp     rcx, rdi
0x18004a1f1  jz      loc_18004A171
0x18004a1f7  test    byte ptr [rcx+1Ch], 2
0x18004a1fb  jz      loc_18004A171
0x18004a201  mov     edx, 18h
0x18004a206  jmp     loc_180049F36
0x18004a20b  mov     rcx, [rsp+848h+var_7D8]
0x18004a210  mov     rax, [rcx]
0x18004a213  lea     r8, [rsp+848h+var_7E0]
0x18004a218  mov     rdx, [rsp+848h+var_800]
0x18004a21d  mov     rax, [rax+48h]
0x18004a221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a226  mov     ebx, eax
0x18004a228  test    eax, eax
0x18004a22a  jns     short loc_18004A257
0x18004a22c  lea     rdi, WPP_GLOBAL_Control
0x18004a233  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a23a  cmp     rcx, rdi
0x18004a23d  jz      loc_18004A171
0x18004a243  test    byte ptr [rcx+1Ch], 2
0x18004a247  jz      loc_18004A171
0x18004a24d  mov     edx, 19h
0x18004a252  jmp     loc_180049F36
0x18004a257  mov     rcx, [rsp+848h+var_7E0]
0x18004a25c  mov     rax, [rcx]
0x18004a25f  lea     rdx, [rsp+848h+var_80C]
0x18004a264  mov     rax, [rax+18h]
0x18004a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a26d  mov     ebx, eax
  ... truncated ...
```
