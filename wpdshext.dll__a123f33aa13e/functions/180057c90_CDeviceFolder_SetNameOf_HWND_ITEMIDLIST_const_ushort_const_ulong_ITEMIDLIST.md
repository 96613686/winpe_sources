# CDeviceFolder::SetNameOf(HWND__ *,_ITEMIDLIST const *,ushort const *,ulong,_ITEMIDLIST * *)

- ea: `0x180057c90`
- end: `0x1800581f0`
- name: `?SetNameOf@CDeviceFolder@@UEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEBGKPEAPEFAU3@@Z`
- size: `1376`
- prototype: `int(CDeviceFolder *__hidden this, HWND, const struct _ITEMIDLIST *, const unsigned __int16 *, unsigned int, struct _ITEMIDLIST **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004110`
- `0x180007860`
- `0x18000ce68`
- `0x180013170`
- `0x180016260`
- `0x180024928`
- `0x1800285c8`
- `0x18002e670`
- `0x18002ff5c`
- `0x180035590`
- `0x180039654`
- `0x180039e80`
- `0x180057c90`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180057ec9`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180057ec9`
- `SHLWAPI!StrCmpIW` at `0x180057d8e`
- `SHLWAPI!StrCmpIW` at `0x180057d8e`
- `SHLWAPI!PathRemoveBlanksW` at `0x180057d7d`
- `SHLWAPI!PathRemoveBlanksW` at `0x180057d7d`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800580df`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800580df`
- `ole32!CoTaskMemFree` at `0x180058134`
- `ole32!CoTaskMemFree` at `0x180058157`
- `ole32!CoTaskMemFree` at `0x180058134`
- `ole32!CoTaskMemFree` at `0x180058157`
- `ole32!CoCreateInstance` at `0x180057fae`
- `ole32!CoCreateInstance` at `0x180057fae`
- `SHELL32!__imp_ILFree` at `0x1800580b2`
- `SHELL32!__imp_ILFree` at `0x1800580b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDeviceFolder::SetNameOf(
        struct _ITEMIDLIST **this,
        HWND a2,
        const struct _ITEMIDLIST *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct _ITEMIDLIST **a6)
{
  const struct DEVICEITEM *v10; // rdi
  int v11; // ebx
  int PortableDeviceProperties; // eax
  PVOID *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  CDeviceFolder *v16; // rcx
  size_t v17; // rbx
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *Control; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  struct IPortableDeviceProperties *v26; // [rsp+68h] [rbp-98h] BYREF
  struct IPortableDevice *v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v30[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v31[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v24 = 0;
  pidl = 0;
  pv = 0;
  Control = 0;
  v19 = 0;
  v27 = 0;
  v26 = 0;
  ppv = 0;
  v28 = 0;
  v22 = 0;
  if ( a6 )
    *a6 = 0;
  v10 = CDeviceFolder::_IsValid((CDeviceFolder *)this, a3);
  if ( !v10 )
    goto LABEL_4;
  PortableDeviceProperties = StringCchCopyW(pszPath, 0x104u, a4);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties >= 0 )
  {
    PathRemoveBlanksW(pszPath);
    if ( !StrCmpIW(pszPath, &String) )
    {
LABEL_4:
      v11 = -2147024809;
LABEL_54:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_55;
    }
    PortableDeviceProperties = (*(__int64 (__fastcall **)(char *, GUID *, __int64 *))&(*(this - 2))->mkid.cb)(
                                 (char *)this - 16,
                                 &GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4,
                                 &v22);
    v11 = PortableDeviceProperties;
    if ( PortableDeviceProperties >= 0 )
    {
      PortableDeviceProperties = (*(__int64 (__fastcall **)(__int64, LPVOID *, wchar_t **))(*(_QWORD *)v22 + 24LL))(
                                   v22,
                                   &pv,
                                   &Control);
      v11 = PortableDeviceProperties;
      if ( PortableDeviceProperties >= 0 )
      {
        CDeviceFolder::_Name(v16, v10, v31, 0x104u);
        v19 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned int *))(*(_QWORD *)v22 + 32LL))(
                v22,
                v31,
                &v19);
        if ( v11 >= 0 )
        {
          if ( !v19 )
            v19 = 128;
          v17 = -1;
          do
            ++v17;
          while ( pszPath[v17] );
          if ( wcscspn(pszPath, Control) < v17 || v17 > v19 )
          {
            ShellMessageBoxW(g_hInst, a2, (LPCWSTR)0xC3, (LPCWSTR)0xC4, 0x10010u);
            v11 = -2147467259;
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50,
                (unsigned int)WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
                (unsigned int)pszPath,
                5);
              goto LABEL_54;
            }
          }
          else
          {
            StringCchCopyW(
              v30,
              0x104u,
              (const unsigned __int16 *)v10
            + *(unsigned int *)((char *)v10 + 26)
            + *(unsigned int *)((char *)v10 + 30)
            + 19);
            PortableDeviceProperties = CBaseFolder::_BindToPortableDevice((CBaseFolder *)(this - 2), v30, &v27);
            v11 = PortableDeviceProperties;
            if ( PortableDeviceProperties >= 0 )
            {
              PortableDeviceProperties = GetPortableDeviceProperties(v27, &v26);
              v11 = PortableDeviceProperties;
              if ( PortableDeviceProperties >= 0 )
              {
                PortableDeviceProperties = CoCreateInstance(
                                             &CLSID_PortableDeviceValues,
                                             0,
                                             1u,
                                             &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                                             &ppv);
                v11 = PortableDeviceProperties;
                if ( PortableDeviceProperties >= 0 )
                {
                  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *, wchar_t *))(*(_QWORD *)ppv + 56LL))(
                    ppv,
                    &WPD_DEVICE_FRIENDLY_NAME,
                    pszPath);
                  ((void (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, LPVOID, __int64 *))v26->lpVtbl->SetValues)(
                    v26,
                    L"DEVICE",
                    ppv,
                    &v28);
                  PortableDeviceProperties = CDeviceFolder::_CreateIDList(
                                               (struct IPortableDeviceProperties *)this - 2,
                                               v30,
                                               &pidl,
                                               &v24);
                  v11 = PortableDeviceProperties;
                  if ( PortableDeviceProperties >= 0 )
                  {
                    CBaseFolder::_ChangeNotifyItem((CBaseFolder *)(this - 2), 1, a3, pidl);
                    CDeviceCache::s_AddToCache(v30, this[6], pidl);
                    if ( a6 )
                    {
                      *a6 = pidl;
                    }
                    else if ( pidl )
                    {
                      ILFree(pidl);
                      pidl = 0;
                    }
                    goto LABEL_54;
                  }
                  v13 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v14 = 54;
                    goto LABEL_9;
                  }
                }
                else
                {
                  v13 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v14 = 53;
                    goto LABEL_9;
                  }
                }
              }
              else
              {
                v13 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v14 = 52;
                  goto LABEL_9;
                }
              }
            }
            else
            {
              v13 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v14 = 51;
                goto LABEL_9;
              }
            }
          }
        }
        else
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v14 = 49;
            v15 = (unsigned int)v11;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v14 = 48;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v14 = 47;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v14 = 46;
LABEL_9:
      v15 = (unsigned int)PortableDeviceProperties;
LABEL_10:
      WPP_SF_d(v13[2], v14, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v15);
      goto LABEL_54;
    }
  }
LABEL_55:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Control )
  {
    CoTaskMemFree(Control);
    Control = 0;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 < 0 && v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
    WPP_SF_d(v13[2], 55, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180057c90  push    rbp
0x180057c92  push    rbx
0x180057c93  push    rsi
0x180057c94  push    rdi
0x180057c95  push    r12
0x180057c97  push    r13
0x180057c99  push    r14
0x180057c9b  push    r15
0x180057c9d  lea     rbp, [rsp-5C8h]
0x180057ca5  sub     rsp, 6C8h
0x180057cac  mov     rax, cs:__security_cookie
0x180057cb3  xor     rax, rsp
0x180057cb6  mov     [rbp+600h+var_50], rax
0x180057cbd  mov     rbx, r9
0x180057cc0  mov     r15, r8
0x180057cc3  mov     r12, rdx
0x180057cc6  mov     r13, rcx
0x180057cc9  mov     rsi, [rbp+600h+arg_28]
0x180057cd0  xor     eax, eax
0x180057cd2  mov     [rsp+700h+var_6A8], eax
0x180057cd6  mov     [rsp+700h+pidl], rax
0x180057cdb  mov     [rsp+700h+pv], rax
0x180057ce0  mov     [rsp+700h+Control], rax
0x180057ce5  mov     [rsp+700h+var_6D0], eax
0x180057ce9  mov     [rsp+700h+var_690], rax
0x180057cee  mov     [rsp+700h+var_698], rax
0x180057cf3  mov     [rsp+700h+var_6B0], rax
0x180057cf8  mov     [rsp+700h+var_688], rax
0x180057cfd  mov     [rsp+700h+var_6B8], rax
0x180057d02  test    rsi, rsi
0x180057d05  jz      short loc_180057D0A
0x180057d07  mov     [rsi], rax
0x180057d0a  mov     rdx, r15; struct _ITEMIDLIST *
0x180057d0d  call    ?_IsValid@CDeviceFolder@@AEAAPEFBUDEVICEITEM@@PEFBU_ITEMIDLIST@@@Z; CDeviceFolder::_IsValid(_ITEMIDLIST const *)
0x180057d12  mov     rdi, rax
0x180057d15  lea     r14, WPP_GLOBAL_Control
0x180057d1c  test    rax, rax
0x180057d1f  jnz     short loc_180057D2B
0x180057d21  mov     ebx, 80070057h
0x180057d26  jmp     loc_180058120
0x180057d2b  mov     r8, rbx; unsigned __int16 *
0x180057d2e  mov     edx, 104h; unsigned __int64
0x180057d33  lea     rcx, [rbp+600h+pszPath]; unsigned __int16 *
0x180057d37  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057d3c  mov     ebx, eax
0x180057d3e  test    eax, eax
0x180057d40  jns     short loc_180057D79
0x180057d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d49  cmp     rcx, r14
0x180057d4c  jz      loc_180058127
0x180057d52  test    byte ptr [rcx+1Ch], 2
0x180057d56  jz      loc_180058127
0x180057d5c  mov     edx, 2Eh ; '.'
0x180057d61  mov     r9d, eax
0x180057d64  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180057d6b  mov     rcx, [rcx+10h]
0x180057d6f  call    WPP_SF_d
0x180057d74  jmp     loc_180058120
0x180057d79  lea     rcx, [rbp+600h+pszPath]; pszPath
0x180057d7d  call    cs:__imp_PathRemoveBlanksW
0x180057d83  lea     rdx, String; psz2
0x180057d8a  lea     rcx, [rbp+600h+pszPath]; psz1
0x180057d8e  call    cs:__imp_StrCmpIW
0x180057d94  test    eax, eax
0x180057d96  jz      short loc_180057D21
0x180057d98  lea     r14, [r13-10h]
0x180057d9c  mov     rax, [r14]
0x180057d9f  lea     r8, [rsp+700h+var_6B8]
0x180057da4  lea     rdx, _GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4
0x180057dab  mov     rcx, r14
0x180057dae  mov     rax, [rax]
0x180057db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057db6  mov     ebx, eax
0x180057db8  test    eax, eax
0x180057dba  jns     short loc_180057DE7
0x180057dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180057dc3  lea     r14, WPP_GLOBAL_Control
0x180057dca  cmp     rcx, r14
0x180057dcd  jz      loc_180058127
0x180057dd3  test    byte ptr [rcx+1Ch], 2
0x180057dd7  jz      loc_180058127
0x180057ddd  mov     edx, 2Fh ; '/'
0x180057de2  jmp     loc_180057D61
0x180057de7  mov     rcx, [rsp+700h+var_6B8]
0x180057dec  mov     rax, [rcx]
0x180057def  lea     r8, [rsp+700h+Control]
0x180057df4  lea     rdx, [rsp+700h+pv]
0x180057df9  mov     rax, [rax+18h]
0x180057dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e02  mov     ebx, eax
0x180057e04  test    eax, eax
0x180057e06  jns     short loc_180057E33
0x180057e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e0f  lea     r14, WPP_GLOBAL_Control
0x180057e16  cmp     rcx, r14
0x180057e19  jz      loc_180058127
0x180057e1f  test    byte ptr [rcx+1Ch], 2
0x180057e23  jz      loc_180058127
0x180057e29  mov     edx, 30h ; '0'
0x180057e2e  jmp     loc_180057D61
0x180057e33  mov     r9d, 104h; unsigned int
0x180057e39  lea     r8, [rbp+600h+var_260]; unsigned __int16 *
0x180057e40  mov     rdx, rdi; struct DEVICEITEM *
0x180057e43  call    ?_Name@CDeviceFolder@@AEAAPEBGPEFBUDEVICEITEM@@PEAGI@Z; CDeviceFolder::_Name(DEVICEITEM const *,ushort *,uint)
0x180057e48  mov     [rsp+700h+var_6D0], 0
0x180057e50  mov     rcx, [rsp+700h+var_6B8]
0x180057e55  mov     rax, [rcx]
0x180057e58  lea     r8, [rsp+700h+var_6D0]
0x180057e5d  lea     rdx, [rbp+600h+var_260]
0x180057e64  mov     rax, [rax+20h]
0x180057e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e6d  mov     ebx, eax
0x180057e6f  xor     eax, eax
0x180057e71  test    ebx, ebx
0x180057e73  jns     short loc_180057EA1
0x180057e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e7c  lea     r14, WPP_GLOBAL_Control
0x180057e83  cmp     rcx, r14
0x180057e86  jz      loc_180058127
0x180057e8c  test    byte ptr [rcx+1Ch], 2
0x180057e90  jz      loc_180058127
0x180057e96  lea     edx, [rax+31h]
0x180057e99  mov     r9d, ebx
0x180057e9c  jmp     loc_180057D64
0x180057ea1  cmp     [rsp+700h+var_6D0], eax
0x180057ea5  jnz     short loc_180057EAF
0x180057ea7  mov     [rsp+700h+var_6D0], 80h
0x180057eaf  lea     rcx, [rbp+600h+pszPath]
0x180057eb3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180057eb7  inc     rbx
0x180057eba  cmp     [rcx+rbx*2], ax
0x180057ebe  jnz     short loc_180057EB7
0x180057ec0  mov     rdx, [rsp+700h+Control]; Control
0x180057ec5  lea     rcx, [rbp+600h+pszPath]; String
0x180057ec9  call    cs:__imp_wcscspn
0x180057ecf  cmp     rax, rbx
0x180057ed2  jb      loc_1800580C3
0x180057ed8  mov     eax, [rsp+700h+var_6D0]
0x180057edc  cmp     rbx, rax
0x180057edf  ja      loc_1800580C3
0x180057ee5  mov     ecx, [rdi+1Eh]
0x180057ee8  mov     eax, [rdi+1Ah]
0x180057eeb  add     rax, 13h
0x180057eef  add     rcx, rax
0x180057ef2  lea     r8, [rdi+rcx*2]; unsigned __int16 *
0x180057ef6  mov     edx, 104h; unsigned __int64
0x180057efb  lea     rcx, [rbp+600h+var_470]; unsigned __int16 *
0x180057f02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057f07  lea     r8, [rsp+700h+var_690]; struct IPortableDevice **
0x180057f0c  lea     rdx, [rbp+600h+var_470]; unsigned __int16 *
0x180057f13  mov     rcx, r14; this
0x180057f16  call    ?_BindToPortableDevice@CBaseFolder@@MEAAJPEBGPEAPEAUIPortableDevice@@@Z; CBaseFolder::_BindToPortableDevice(ushort const *,IPortableDevice * *)
0x180057f1b  mov     ebx, eax
0x180057f1d  test    eax, eax
0x180057f1f  jns     short loc_180057F4C
0x180057f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f28  lea     r14, WPP_GLOBAL_Control
0x180057f2f  cmp     rcx, r14
0x180057f32  jz      loc_180058127
0x180057f38  test    byte ptr [rcx+1Ch], 2
0x180057f3c  jz      loc_180058127
0x180057f42  mov     edx, 33h ; '3'
0x180057f47  jmp     loc_180057D61
0x180057f4c  lea     rdx, [rsp+700h+var_698]; struct IPortableDeviceProperties **
0x180057f51  mov     rcx, [rsp+700h+var_690]; struct IPortableDevice *
0x180057f56  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180057f5b  mov     ebx, eax
0x180057f5d  test    eax, eax
0x180057f5f  jns     short loc_180057F8C
0x180057f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f68  lea     r14, WPP_GLOBAL_Control
0x180057f6f  cmp     rcx, r14
0x180057f72  jz      loc_180058127
0x180057f78  test    byte ptr [rcx+1Ch], 2
0x180057f7c  jz      loc_180058127
0x180057f82  mov     edx, 34h ; '4'
0x180057f87  jmp     loc_180057D61
0x180057f8c  lea     rax, [rsp+700h+var_6B0]
0x180057f91  mov     [rsp+700h+ppv], rax; ppv
0x180057f96  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180057f9d  mov     edi, 1
0x180057fa2  mov     r8d, edi; dwClsContext
0x180057fa5  xor     edx, edx; pUnkOuter
0x180057fa7  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180057fae  call    cs:__imp_CoCreateInstance
0x180057fb4  mov     ebx, eax
0x180057fb6  test    eax, eax
0x180057fb8  jns     short loc_180057FE3
0x180057fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180057fc1  lea     r14, WPP_GLOBAL_Control
0x180057fc8  cmp     rcx, r14
0x180057fcb  jz      loc_180058127
0x180057fd1  test    byte ptr [rcx+1Ch], 2
0x180057fd5  jz      loc_180058127
0x180057fdb  lea     edx, [rdi+34h]
0x180057fde  jmp     loc_180057D61
0x180057fe3  mov     rcx, [rsp+700h+var_6B0]
0x180057fe8  mov     rax, [rcx]
0x180057feb  lea     r8, [rbp+600h+pszPath]
0x180057fef  lea     rdx, WPD_DEVICE_FRIENDLY_NAME
0x180057ff6  mov     rax, [rax+38h]
0x180057ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fff  mov     rcx, [rsp+700h+var_698]
0x180058004  mov     rax, [rcx]
0x180058007  lea     r9, [rsp+700h+var_688]
0x18005800c  mov     r8, [rsp+700h+var_6B0]
0x180058011  lea     rdx, aDevice_0; "DEVICE"
0x180058018  mov     rax, [rax+30h]
0x18005801c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058021  lea     r9, [rsp+700h+var_6A8]; int *
0x180058026  lea     r8, [rsp+700h+pidl]; struct _ITEMIDLIST **
0x18005802b  lea     rdx, [rbp+600h+var_470]; unsigned __int16 *
0x180058032  mov     rcx, r14; this
0x180058035  call    ?_CreateIDList@CDeviceFolder@@AEAAJPEBGPEAPEFAU_ITEMIDLIST@@PEAH@Z; CDeviceFolder::_CreateIDList(ushort const *,_ITEMIDLIST * *,int *)
0x18005803a  mov     ebx, eax
0x18005803c  test    eax, eax
0x18005803e  jns     short loc_18005806B
0x180058040  mov     rcx, cs:WPP_GLOBAL_Control
0x180058047  lea     r14, WPP_GLOBAL_Control
0x18005804e  cmp     rcx, r14
0x180058051  jz      loc_180058127
0x180058057  test    byte ptr [rcx+1Ch], 2
0x18005805b  jz      loc_180058127
0x180058061  mov     edx, 36h ; '6'
0x180058066  jmp     loc_180057D61
0x18005806b  mov     r9, [rsp+700h+pidl]; struct _ITEMIDLIST *
0x180058070  mov     r8, r15; struct _ITEMIDLIST *
0x180058073  mov     edx, edi; int
0x180058075  mov     rcx, r14; this
0x180058078  call    ?_ChangeNotifyItem@CBaseFolder@@IEAAJJPEFBU_ITEMIDLIST@@0@Z; CBaseFolder::_ChangeNotifyItem(long,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18005807d  mov     r8, [rsp+700h+pidl]; struct _ITEMIDLIST *
0x180058082  mov     rdx, [r13+30h]; struct _ITEMIDLIST *
0x180058086  lea     rcx, [rbp+600h+var_470]; unsigned __int16 *
0x18005808d  call    ?s_AddToCache@CDeviceCache@@CAJPEBGPEFAU_ITEMIDLIST@@1@Z; CDeviceCache::s_AddToCache(ushort const *,_ITEMIDLIST *,_ITEMIDLIST *)
0x180058092  test    rsi, rsi
0x180058095  jz      short loc_1800580A8
0x180058097  mov     rax, [rsp+700h+pidl]
0x18005809c  mov     [rsi], rax
0x18005809f  lea     r14, WPP_GLOBAL_Control
0x1800580a6  jmp     short loc_180058120
0x1800580a8  mov     rcx, [rsp+700h+pidl]; pidl
0x1800580ad  test    rcx, rcx
0x1800580b0  jz      short loc_18005809F
0x1800580b2  call    cs:__imp_ILFree
0x1800580b8  mov     [rsp+700h+pidl], 0
0x1800580c1  jmp     short loc_18005809F
0x1800580c3  mov     dword ptr [rsp+700h+ppv], 10010h; fuStyle
0x1800580cb  mov     r9d, 0C4h; lpcTitle
0x1800580d1  lea     r8d, [r9-1]; lpcText
0x1800580d5  mov     rdx, r12; hWnd
0x1800580d8  mov     rcx, cs:g_hInst; hAppInst
0x1800580df  call    cs:__imp_ShellMessageBoxW
0x1800580e5  mov     ebx, 80004005h
0x1800580ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580f1  lea     r14, WPP_GLOBAL_Control
0x1800580f8  cmp     rcx, r14
0x1800580fb  jz      short loc_180058127
0x1800580fd  test    byte ptr [rcx+1Ch], 2
0x180058101  jz      short loc_180058127
0x180058103  mov     edx, 32h ; '2'
0x180058108  mov     dword ptr [rsp+700h+ppv], ebx
0x18005810c  lea     r9, [rbp+600h+pszPath]
0x180058110  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180058117  mov     rcx, [rcx+10h]
0x18005811b  call    WPP_SF_Sd
0x180058120  mov     rcx, cs:WPP_GLOBAL_Control
0x180058127  mov     rax, [rsp+700h+pv]
0x18005812c  test    rax, rax
0x18005812f  jz      short loc_18005814A
0x180058131  mov     rcx, rax; pv
0x180058134  call    cs:__imp_CoTaskMemFree
0x18005813a  mov     [rsp+700h+pv], 0
0x180058143  mov     rcx, cs:WPP_GLOBAL_Control
0x18005814a  mov     rax, [rsp+700h+Control]
0x18005814f  test    rax, rax
0x180058152  jz      short loc_18005816D
0x180058154  mov     rcx, rax; pv
0x180058157  call    cs:__imp_CoTaskMemFree
0x18005815d  mov     [rsp+700h+Control], 0
0x180058166  mov     rcx, cs:WPP_GLOBAL_Control
0x18005816d  test    ebx, ebx
0x18005816f  jns     short loc_180058195
0x180058171  cmp     rcx, r14
0x180058174  jz      short loc_180058195
0x180058176  test    byte ptr [rcx+1Ch], 2
0x18005817a  jz      short loc_180058195
0x18005817c  mov     edx, 37h ; '7'
0x180058181  mov     r9d, ebx
0x180058184  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x18005818b  mov     rcx, [rcx+10h]
0x18005818f  call    WPP_SF_d
0x180058194  nop
0x180058195  lea     rcx, [rsp+700h+var_6B8]
0x18005819a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005819f  nop
0x1800581a0  lea     rcx, [rsp+700h+var_688]
0x1800581a5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800581aa  nop
0x1800581ab  lea     rcx, [rsp+700h+var_6B0]
0x1800581b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
  ... truncated ...
```
