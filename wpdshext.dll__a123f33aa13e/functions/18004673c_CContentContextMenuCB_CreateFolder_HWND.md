# CContentContextMenuCB::_CreateFolder(HWND__ *)

- ea: `0x18004673c`
- end: `0x180046d35`
- name: `?_CreateFolder@CContentContextMenuCB@@AEAAJPEAUHWND__@@@Z`
- size: `1529`
- prototype: `__int64 __fastcall(CContentContextMenuCB *__hidden this, HWND hWnd)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180042340`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x1800082e0`
- `0x18000ef50`
- `0x180012408`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x18004673c`
- `0x180047618`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180046bca`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180046bca`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180046cad`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180046cad`
- `USER32!LoadStringW` at `0x180046949`
- `USER32!LoadStringW` at `0x18004699d`
- `USER32!LoadStringW` at `0x180046949`
- `USER32!LoadStringW` at `0x18004699d`
- `USER32!SendMessageW` at `0x180046be2`
- `USER32!SendMessageW` at `0x180046be2`
- `ole32!CoTaskMemFree` at `0x180046c7e`
- `ole32!CoTaskMemFree` at `0x180046c7e`
- `ole32!CoCreateInstance` at `0x1800469dd`
- `ole32!CoCreateInstance` at `0x1800469dd`
- `SHELL32!__imp_ILFindLastID` at `0x180046834`
- `SHELL32!__imp_ILFindLastID` at `0x180046834`
- `SHELL32!__imp_ILFree` at `0x180046c2d`
- `SHELL32!__imp_ILFree` at `0x180046c3b`
- `SHELL32!__imp_ILFree` at `0x180046c2d`
- `SHELL32!__imp_ILFree` at `0x180046c3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContentContextMenuCB::_CreateFolder(CContentContextMenuCB *this, HWND hWnd)
{
  ITEMIDLIST *v4; // rsi
  ITEMIDLIST *v5; // r15
  int DoesObjectNameExist; // eax
  int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v11; // rcx
  const struct CONTENTITEM *v12; // rax
  int ObjectID; // eax
  int v14; // r12d
  int v15; // eax
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  unsigned __int64 v19; // rax
  struct IPortableDevice *v21; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-C8h] BYREF
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPCVOID dwItem1; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  struct IPortableDeviceValues *ppv; // [rsp+58h] [rbp-A8h] BYREF
  struct IPortableDeviceContent *v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+68h] [rbp-98h] BYREF
  WCHAR v29[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v31[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v32[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v4 = 0;
  pidl = 0;
  v5 = 0;
  dwItem1 = 0;
  pv = 0;
  ppvOut = 0;
  v21 = 0;
  v27 = 0;
  ppv = 0;
  DoesObjectNameExist = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IPortableDevice **))(**((_QWORD **)this + 4)
                                                                                             + 136LL))(
                          *((_QWORD *)this + 4),
                          *((_QWORD *)this + 5),
                          &v21);
  v7 = DoesObjectNameExist;
  if ( DoesObjectNameExist < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_62;
    v9 = 355;
LABEL_60:
    v16 = (unsigned int)DoesObjectNameExist;
LABEL_61:
    WPP_SF_d(v8[2], v9, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v16);
    goto LABEL_62;
  }
  DoesObjectNameExist = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v21->lpVtbl->Content)(
                          v21,
                          &v27);
  v7 = DoesObjectNameExist;
  if ( DoesObjectNameExist < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_62;
    v9 = 356;
    goto LABEL_60;
  }
  ID = ILFindLastID(*((LPCITEMIDLIST *)this + 5));
  v12 = CContentFolder::_IsValid(v11, ID);
  if ( v12 )
  {
    StringCchCopyW(
      v32,
      0x104u,
      (const unsigned __int16 *)v12 + *(unsigned int *)((char *)v12 + 62) + *(unsigned int *)((char *)v12 + 66) + 37);
    ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)this + 4), v32, v31, 0x104u);
    v7 = ObjectID;
    if ( ObjectID < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          357,
          (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v32,
          ObjectID);
      goto LABEL_62;
    }
  }
  else
  {
    DoesObjectNameExist = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 4)
                                                                                                 + 88LL))(
                            *((_QWORD *)this + 4),
                            *((_QWORD *)this + 5),
                            v31,
                            260);
    v7 = DoesObjectNameExist;
    if ( DoesObjectNameExist < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_62;
      v9 = 358;
      goto LABEL_60;
    }
  }
  v14 = 1;
  v29[0] = 0;
  LoadStringW(g_hInst, 0x2403u, Buffer, 260);
  while ( 1 )
  {
    DoesObjectNameExist = CContentContextMenuCB::_DoesObjectNameExist((CBaseFolder **)this, Buffer, v31, v21, v27);
    v7 = DoesObjectNameExist;
    if ( DoesObjectNameExist < 0 )
      break;
    if ( DoesObjectNameExist )
    {
      DoesObjectNameExist = CoCreateInstance(
                              &CLSID_PortableDeviceValues,
                              0,
                              1u,
                              &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                              (LPVOID *)&ppv);
      v7 = DoesObjectNameExist;
      if ( DoesObjectNameExist < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v9 = 360;
          goto LABEL_60;
        }
        goto LABEL_62;
      }
      DoesObjectNameExist = GetFolderProperties(ppv, 0, v31, Buffer, 0);
      v7 = DoesObjectNameExist;
      if ( DoesObjectNameExist < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v9 = 361;
          goto LABEL_60;
        }
        goto LABEL_62;
      }
      v15 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, struct IPortableDeviceValues *, LPVOID *))v27->lpVtbl->CreateObjectWithPropertiesOnly)(
              v27,
              ppv,
              &pv);
      v7 = 0;
      if ( v15 != -2147023893 )
        v7 = v15;
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v9 = 362;
          v16 = (unsigned int)v7;
          goto LABEL_61;
        }
        goto LABEL_62;
      }
      if ( pv )
      {
        v17 = CContentFolder::_CreateIDList(*((CContentFolder **)this + 4), v21, (unsigned __int16 *)pv, 0, &pidl, &v28);
        v7 = v17;
        if ( v17 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              363,
              WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
              (unsigned int)v17);
          v4 = pidl;
LABEL_55:
          if ( v4 )
            ILFree(v4);
          goto LABEL_62;
        }
        v4 = pidl;
        v18 = SHILCombine(*((_QWORD *)this + 5), pidl, &dwItem1);
        v7 = v18;
        if ( v18 >= 0 )
        {
          ChangeNotify(0, 0x1000u, 0, 0);
          v5 = (ITEMIDLIST *)dwItem1;
          ChangeNotify(8, 0x1000u, dwItem1, 0);
          if ( IUnknown_QueryService(
                 *((IUnknown **)this + 1),
                 (const GUID *const)&SID_DefView,
                 &GUID_000214e3_0000_0000_c000_000000000046,
                 &ppvOut) >= 0
            || (v19 = SendMessageW(hWnd, 0x407u, 0, 0), v19 >= 0x10000)
            && (*(int (__fastcall **)(unsigned __int64, void **))(*(_QWORD *)v19 + 120LL))(v19, &ppvOut) >= 0 )
          {
            (*(void (__fastcall **)(void *, ITEMIDLIST *, __int64))(*(_QWORD *)ppvOut + 112LL))(ppvOut, v4, 3);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              364,
              WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
              (unsigned int)v18);
          v5 = (ITEMIDLIST *)dwItem1;
        }
      }
      if ( v5 )
        ILFree(v5);
      goto LABEL_55;
    }
    if ( !v29[0] )
      LoadStringW(g_hInst, 0x2404u, v29, 260);
    StringCchPrintfW(Buffer, 0x104u, v29, (unsigned int)++v14);
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 359;
    goto LABEL_60;
  }
LABEL_62:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v7 < 0 )
  {
    ShellMessageBoxW(g_hInst, hWnd, (LPCWSTR)0x116, (LPCWSTR)0x115, 0x10010u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        365,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v7);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004673c  mov     [rsp-8+arg_10], rbx
0x180046741  push    rbp
0x180046742  push    rsi
0x180046743  push    rdi
0x180046744  push    r12
0x180046746  push    r13
0x180046748  push    r14
0x18004674a  push    r15
0x18004674c  lea     rbp, [rsp-7C0h]
0x180046754  sub     rsp, 8C0h
0x18004675b  mov     rax, cs:__security_cookie
0x180046762  xor     rax, rsp
0x180046765  mov     [rbp+7F0h+var_40], rax
0x18004676c  mov     r13, rdx
0x18004676f  mov     r14, rcx
0x180046772  xor     edi, edi
0x180046774  mov     esi, edi
0x180046776  mov     [rsp+8F0h+pidl], rdi
0x18004677b  mov     r15d, edi
0x18004677e  mov     [rsp+8F0h+dwItem1], rdi
0x180046783  mov     [rsp+8F0h+pv], rdi
0x180046788  mov     [rsp+8F0h+ppvOut], rdi
0x18004678d  mov     [rsp+8F0h+var_8C0], rdi
0x180046792  mov     [rsp+8F0h+var_890], rdi
0x180046797  mov     [rsp+8F0h+var_898], rdi
0x18004679c  mov     rcx, [rcx+20h]
0x1800467a0  mov     rax, [rcx]
0x1800467a3  lea     r8, [rsp+8F0h+var_8C0]
0x1800467a8  mov     rdx, [r14+28h]
0x1800467ac  mov     rax, [rax+88h]
0x1800467b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467b8  mov     ebx, eax
0x1800467ba  test    eax, eax
0x1800467bc  jns     short loc_1800467E9
0x1800467be  lea     rdi, WPP_GLOBAL_Control
0x1800467c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800467cc  cmp     rcx, rdi
0x1800467cf  jz      loc_180046C74
0x1800467d5  test    byte ptr [rcx+1Ch], 2
0x1800467d9  jz      loc_180046C74
0x1800467df  mov     edx, 163h
0x1800467e4  jmp     loc_180046C61
0x1800467e9  mov     rcx, [rsp+8F0h+var_8C0]
0x1800467ee  mov     rax, [rcx]
0x1800467f1  lea     rdx, [rsp+8F0h+var_890]
0x1800467f6  mov     rax, [rax+28h]
0x1800467fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467ff  mov     ebx, eax
0x180046801  test    eax, eax
0x180046803  jns     short loc_180046830
0x180046805  lea     rdi, WPP_GLOBAL_Control
0x18004680c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046813  cmp     rcx, rdi
0x180046816  jz      loc_180046C74
0x18004681c  test    byte ptr [rcx+1Ch], 2
0x180046820  jz      loc_180046C74
0x180046826  mov     edx, 164h
0x18004682b  jmp     loc_180046C61
0x180046830  mov     rcx, [r14+28h]; pidl
0x180046834  call    cs:__imp_ILFindLastID
0x18004683a  mov     rdx, rax; struct _ITEMIDLIST *
0x18004683d  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180046842  mov     edi, 104h
0x180046847  test    rax, rax
0x18004684a  jz      loc_1800468D9
0x180046850  mov     edx, [rax+42h]
0x180046853  mov     ecx, [rax+3Eh]
0x180046856  add     rcx, 25h ; '%'
0x18004685a  add     rdx, rcx
0x18004685d  lea     r8, [rax+rdx*2]; unsigned __int16 *
0x180046861  mov     edx, edi; unsigned __int64
0x180046863  lea     rcx, [rbp+7F0h+var_250]; unsigned __int16 *
0x18004686a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004686f  mov     r9d, edi; unsigned int
0x180046872  lea     r8, [rbp+7F0h+var_460]; unsigned __int16 *
0x180046879  lea     rdx, [rbp+7F0h+var_250]; unsigned __int16 *
0x180046880  mov     rcx, [r14+20h]; this
0x180046884  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x180046889  mov     ebx, eax
0x18004688b  test    eax, eax
0x18004688d  jns     loc_180046928
0x180046893  lea     rdi, WPP_GLOBAL_Control
0x18004689a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468a1  cmp     rcx, rdi
0x1800468a4  jz      loc_180046C74
0x1800468aa  test    byte ptr [rcx+1Ch], 2
0x1800468ae  jz      loc_180046C74
0x1800468b4  mov     edx, 165h
0x1800468b9  mov     dword ptr [rsp+8F0h+ppv], eax
0x1800468bd  lea     r9, [rbp+7F0h+var_250]
0x1800468c4  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800468cb  mov     rcx, [rcx+10h]
0x1800468cf  call    WPP_SF_Sd
0x1800468d4  jmp     loc_180046C74
0x1800468d9  mov     rcx, [r14+20h]
0x1800468dd  mov     rax, [rcx]
0x1800468e0  mov     r9d, edi
0x1800468e3  lea     r8, [rbp+7F0h+var_460]
0x1800468ea  mov     rdx, [r14+28h]
0x1800468ee  mov     rax, [rax+58h]
0x1800468f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468f7  mov     ebx, eax
0x1800468f9  test    eax, eax
0x1800468fb  jns     short loc_180046928
0x1800468fd  lea     rdi, WPP_GLOBAL_Control
0x180046904  mov     rcx, cs:WPP_GLOBAL_Control
0x18004690b  cmp     rcx, rdi
0x18004690e  jz      loc_180046C74
0x180046914  test    byte ptr [rcx+1Ch], 2
0x180046918  jz      loc_180046C74
0x18004691e  mov     edx, 166h
0x180046923  jmp     loc_180046C61
0x180046928  xor     eax, eax
0x18004692a  lea     r12d, [rax+1]
0x18004692e  mov     [rsp+8F0h+var_880], ax
0x180046933  mov     r9d, edi; cchBufferMax
0x180046936  lea     r8, [rbp+7F0h+Buffer]; lpBuffer
0x18004693d  mov     edx, 2403h; uID
0x180046942  mov     rcx, cs:g_hInst; hInstance
0x180046949  call    cs:__imp_LoadStringW
0x18004694f  mov     rax, [rsp+8F0h+var_890]
0x180046954  mov     [rsp+8F0h+ppv], rax; struct IPortableDeviceContent *
0x180046959  mov     r9, [rsp+8F0h+var_8C0]; struct IPortableDevice *
0x18004695e  lea     r8, [rbp+7F0h+var_460]; unsigned __int16 *
0x180046965  lea     rdx, [rbp+7F0h+Buffer]; unsigned __int16 *
0x18004696c  mov     rcx, r14; this
0x18004696f  call    ?_DoesObjectNameExist@CContentContextMenuCB@@AEAAJPEBG0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@@Z; CContentContextMenuCB::_DoesObjectNameExist(ushort const *,ushort const *,IPortableDevice *,IPortableDeviceContent *)
0x180046974  mov     ebx, eax
0x180046976  test    eax, eax
0x180046978  js      loc_180046C43
0x18004697e  jnz     short loc_1800469BF
0x180046980  xor     eax, eax
0x180046982  cmp     ax, [rsp+8F0h+var_880]
0x180046987  jnz     short loc_1800469A3
0x180046989  mov     r9d, edi; cchBufferMax
0x18004698c  lea     r8, [rsp+8F0h+var_880]; lpBuffer
0x180046991  mov     edx, 2404h; uID
0x180046996  mov     rcx, cs:g_hInst; hInstance
0x18004699d  call    cs:__imp_LoadStringW
0x1800469a3  inc     r12d
0x1800469a6  mov     r9d, r12d
0x1800469a9  lea     r8, [rsp+8F0h+var_880]; unsigned __int16 *
0x1800469ae  mov     rdx, rdi; unsigned __int64
0x1800469b1  lea     rcx, [rbp+7F0h+Buffer]; unsigned __int16 *
0x1800469b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800469bd  jmp     short loc_18004694F
0x1800469bf  lea     rax, [rsp+8F0h+var_898]
0x1800469c4  mov     [rsp+8F0h+ppv], rax; ppv
0x1800469c9  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x1800469d0  xor     edx, edx; pUnkOuter
0x1800469d2  lea     r8d, [rdx+1]; dwClsContext
0x1800469d6  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x1800469dd  call    cs:__imp_CoCreateInstance
0x1800469e3  mov     ebx, eax
0x1800469e5  test    eax, eax
0x1800469e7  jns     short loc_180046A14
0x1800469e9  lea     rdi, WPP_GLOBAL_Control
0x1800469f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469f7  cmp     rcx, rdi
0x1800469fa  jz      loc_180046C74
0x180046a00  test    byte ptr [rcx+1Ch], 2
0x180046a04  jz      loc_180046C74
0x180046a0a  mov     edx, 168h
0x180046a0f  jmp     loc_180046C61
0x180046a14  mov     [rsp+8F0h+ppv], 0; unsigned __int16 *
0x180046a1d  lea     r9, [rbp+7F0h+Buffer]; unsigned __int16 *
0x180046a24  lea     r8, [rbp+7F0h+var_460]; unsigned __int16 *
0x180046a2b  xor     edx, edx; struct _ITEMIDLIST *
0x180046a2d  mov     rcx, [rsp+8F0h+var_898]; struct IPortableDeviceValues *
0x180046a32  call    ?GetFolderProperties@@YAJPEAUIPortableDeviceValues@@PEFBU_ITEMIDLIST@@PEBG22@Z; GetFolderProperties(IPortableDeviceValues *,_ITEMIDLIST const *,ushort const *,ushort const *,ushort const *)
0x180046a37  mov     ebx, eax
0x180046a39  test    eax, eax
0x180046a3b  jns     short loc_180046A68
0x180046a3d  lea     rdi, WPP_GLOBAL_Control
0x180046a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a4b  cmp     rcx, rdi
0x180046a4e  jz      loc_180046C74
0x180046a54  test    byte ptr [rcx+1Ch], 2
0x180046a58  jz      loc_180046C74
0x180046a5e  mov     edx, 169h
0x180046a63  jmp     loc_180046C61
0x180046a68  mov     rcx, [rsp+8F0h+var_890]
0x180046a6d  mov     rax, [rcx]
0x180046a70  lea     r8, [rsp+8F0h+pv]
0x180046a75  mov     rdx, [rsp+8F0h+var_898]
0x180046a7a  mov     rax, [rax+30h]
0x180046a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a83  xor     ebx, ebx
0x180046a85  cmp     eax, 800703EBh
0x180046a8a  cmovnz  ebx, eax
0x180046a8d  test    ebx, ebx
0x180046a8f  jns     short loc_180046ABF
0x180046a91  lea     rdi, WPP_GLOBAL_Control
0x180046a98  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a9f  cmp     rcx, rdi
0x180046aa2  jz      loc_180046C74
0x180046aa8  test    byte ptr [rcx+1Ch], 2
0x180046aac  jz      loc_180046C74
0x180046ab2  mov     edx, 16Ah
0x180046ab7  mov     r9d, ebx
0x180046aba  jmp     loc_180046C64
0x180046abf  lea     rdi, WPP_GLOBAL_Control
0x180046ac6  mov     rcx, [rsp+8F0h+pv]
0x180046acb  test    rcx, rcx
0x180046ace  jz      loc_180046C25
0x180046ad4  lea     rax, [rsp+8F0h+var_888]
0x180046ad9  mov     [rsp+8F0h+var_8C8], rax; int *
0x180046ade  lea     rax, [rsp+8F0h+pidl]
0x180046ae3  mov     [rsp+8F0h+ppv], rax; struct _ITEMIDLIST **
0x180046ae8  xor     r9d, r9d; int
0x180046aeb  mov     r8, rcx; unsigned __int16 *
0x180046aee  mov     rdx, [rsp+8F0h+var_8C0]; struct IPortableDevice *
0x180046af3  mov     rcx, [r14+20h]; this
0x180046af7  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x180046afc  mov     ebx, eax
0x180046afe  test    eax, eax
0x180046b00  jns     short loc_180046B36
0x180046b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b09  cmp     rcx, rdi
0x180046b0c  jz      short loc_180046B2C
0x180046b0e  test    byte ptr [rcx+1Ch], 2
0x180046b12  jz      short loc_180046B2C
0x180046b14  mov     edx, 16Bh
0x180046b19  mov     r9d, eax
0x180046b1c  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180046b23  mov     rcx, [rcx+10h]
0x180046b27  call    WPP_SF_d
0x180046b2c  mov     rsi, [rsp+8F0h+pidl]
0x180046b31  jmp     loc_180046C33
0x180046b36  lea     r8, [rsp+8F0h+dwItem1]
0x180046b3b  mov     rsi, [rsp+8F0h+pidl]
0x180046b40  mov     rdx, rsi
0x180046b43  mov     rcx, [r14+28h]
0x180046b47  call    SHILCombine
0x180046b4c  mov     ebx, eax
0x180046b4e  test    eax, eax
0x180046b50  jns     short loc_180046B86
0x180046b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b59  cmp     rcx, rdi
0x180046b5c  jz      short loc_180046B7C
0x180046b5e  test    byte ptr [rcx+1Ch], 2
0x180046b62  jz      short loc_180046B7C
0x180046b64  mov     edx, 16Ch
0x180046b69  mov     r9d, eax
0x180046b6c  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180046b73  mov     rcx, [rcx+10h]
0x180046b77  call    WPP_SF_d
0x180046b7c  mov     r15, [rsp+8F0h+dwItem1]
0x180046b81  jmp     loc_180046C25
0x180046b86  xor     r9d, r9d; dwItem2
0x180046b89  xor     r8d, r8d; dwItem1
0x180046b8c  mov     r12d, 1000h
0x180046b92  mov     edx, r12d; uFlags
0x180046b95  xor     ecx, ecx; wEventId
0x180046b97  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x180046b9c  xor     r9d, r9d; dwItem2
0x180046b9f  mov     r15, [rsp+8F0h+dwItem1]
0x180046ba4  mov     r8, r15; dwItem1
0x180046ba7  mov     edx, r12d; uFlags
0x180046baa  lea     ecx, [r9+8]; wEventId
0x180046bae  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x180046bb3  lea     r9, [rsp+8F0h+ppvOut]; ppvOut
0x180046bb8  lea     r8, _GUID_000214e3_0000_0000_c000_000000000046; riid
0x180046bbf  lea     rdx, SID_DefView; guidService
0x180046bc6  mov     rcx, [r14+8]; punk
0x180046bca  call    cs:__imp_IUnknown_QueryService
0x180046bd0  test    eax, eax
0x180046bd2  jns     short loc_180046C0B
0x180046bd4  xor     r9d, r9d; lParam
0x180046bd7  xor     r8d, r8d; wParam
0x180046bda  mov     edx, 407h; Msg
0x180046bdf  mov     rcx, r13; hWnd
0x180046be2  call    cs:__imp_SendMessageW
0x180046be8  mov     r8, rax
0x180046beb  cmp     rax, 10000h
0x180046bf1  jb      short loc_180046C25
0x180046bf3  mov     rcx, [rax]
0x180046bf6  mov     rax, [rcx+78h]
0x180046bfa  lea     rdx, [rsp+8F0h+ppvOut]
0x180046bff  mov     rcx, r8
0x180046c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c07  test    eax, eax
0x180046c09  js      short loc_180046C25
0x180046c0b  mov     rcx, [rsp+8F0h+ppvOut]
0x180046c10  mov     rax, [rcx]
0x180046c13  mov     r8d, 3
0x180046c19  mov     rdx, rsi
0x180046c1c  mov     rax, [rax+70h]
0x180046c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c25  test    r15, r15
0x180046c28  jz      short loc_180046C33
0x180046c2a  mov     rcx, r15; pidl
0x180046c2d  call    cs:__imp_ILFree
0x180046c33  test    rsi, rsi
0x180046c36  jz      short loc_180046C74
0x180046c38  mov     rcx, rsi; pidl
0x180046c3b  call    cs:__imp_ILFree
0x180046c41  jmp     short loc_180046C74
0x180046c43  lea     rdi, WPP_GLOBAL_Control
0x180046c4a  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
