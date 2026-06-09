# _InitResources(FILEPROPINFO *)

- ea: `0x18004e598`
- end: `0x18004ee81`
- name: `?_InitResources@@YAXPEAUFILEPROPINFO@@@Z`
- size: `2281`
- prototype: `void __fastcall(struct FILEPROPINFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b2a0`

## callees

- `0x180004110`
- `0x18000d610`
- `0x180022374`
- `0x1800285c8`
- `0x18002ea3c`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18004e598`
- `0x18005072c`
- `0x180051170`
- `0x18005125c`
- `0x1800513f4`
- `0x18005b5e4`
- `0x1800628cc`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18004e878`
- `KERNEL32!GetProcAddress` at `0x18004e878`
- `KERNEL32!FreeLibrary` at `0x18004ee31`
- `KERNEL32!FreeLibrary` at `0x18004ee31`
- `GDI32!GetDeviceCaps` at `0x18004e833`
- `GDI32!GetDeviceCaps` at `0x18004e833`
- `GDI32!DeleteDC` at `0x18004e850`
- `GDI32!DeleteDC` at `0x18004e850`
- `GDI32!CreateCompatibleDC` at `0x18004e81d`
- `GDI32!CreateCompatibleDC` at `0x18004e81d`
- `USER32!LoadStringW` at `0x18004e9d2`
- `USER32!LoadStringW` at `0x18004eb49`
- `USER32!LoadStringW` at `0x18004ecc0`
- `USER32!LoadStringW` at `0x18004edcd`
- `USER32!LoadStringW` at `0x18004e9d2`
- `USER32!LoadStringW` at `0x18004eb49`
- `USER32!LoadStringW` at `0x18004ecc0`
- `USER32!LoadStringW` at `0x18004edcd`
- `USER32!SendMessageW` at `0x18004e680`
- `USER32!SendMessageW` at `0x18004e697`
- `USER32!SendMessageW` at `0x18004e6e4`
- `USER32!SendMessageW` at `0x18004e8c0`
- `USER32!SendMessageW` at `0x18004ea0b`
- `USER32!SendMessageW` at `0x18004ea2d`
- `USER32!SendMessageW` at `0x18004eb82`
- `USER32!SendMessageW` at `0x18004eba4`
- `USER32!SendMessageW` at `0x18004ecf9`
- `USER32!SendMessageW` at `0x18004ed1b`
- `USER32!SendMessageW` at `0x18004ee06`
- `USER32!SendMessageW` at `0x18004ee28`
- `USER32!SendMessageW` at `0x18004e680`
- `USER32!SendMessageW` at `0x18004e697`
- `USER32!SendMessageW` at `0x18004e6e4`
- `USER32!SendMessageW` at `0x18004e8c0`
- `USER32!SendMessageW` at `0x18004ea0b`
- `USER32!SendMessageW` at `0x18004ea2d`
- `USER32!SendMessageW` at `0x18004eb82`
- `USER32!SendMessageW` at `0x18004eba4`
- `USER32!SendMessageW` at `0x18004ecf9`
- `USER32!SendMessageW` at `0x18004ed1b`
- `USER32!SendMessageW` at `0x18004ee06`
- `USER32!SendMessageW` at `0x18004ee28`
- `USER32!GetDlgItem` at `0x18004e65f`
- `USER32!GetDlgItem` at `0x18004e65f`
- `USER32!GetClientRect` at `0x18004e6ac`
- `USER32!GetClientRect` at `0x18004e6ac`
- `USER32!GetSystemMetrics` at `0x18004e6b6`
- `USER32!GetSystemMetrics` at `0x18004e6b6`
- `ole32!PropVariantClear` at `0x18004e8cb`
- `ole32!PropVariantClear` at `0x18004ea42`
- `ole32!PropVariantClear` at `0x18004ebb9`
- `ole32!PropVariantClear` at `0x18004ed30`
- `ole32!PropVariantClear` at `0x18004ee45`
- `ole32!PropVariantClear` at `0x18004e8cb`
- `ole32!PropVariantClear` at `0x18004ea42`
- `ole32!PropVariantClear` at `0x18004ebb9`
- `ole32!PropVariantClear` at `0x18004ed30`
- `ole32!PropVariantClear` at `0x18004ee45`
- `SHELL32!__imp_SHDefExtractIconW` at `0x18004ed97`
- `SHELL32!__imp_SHDefExtractIconW` at `0x18004ed97`
- `SHELL32!__imp_ILFindLastID` at `0x18004e70f`
- `SHELL32!__imp_ILFindLastID` at `0x18004e70f`
- `SHELL32!__imp_ILFree` at `0x18004ee3a`
- `SHELL32!__imp_ILFree` at `0x18004ee3a`

## string_xrefs

- `0x18004ed90`: `wpdshext.dll`
- `0x18004e86e`: `ImageList_Create`
- `0x18004e856`: `comctl32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _InitResources(HWND *a1)
{
  HWND DlgItem; // rax
  HWND v3; // rsi
  const ITEMIDLIST *v4; // rax
  ITEMIDLIST *v5; // r13
  HWND v6; // rdi
  __int64 (__fastcall *v7)(HWND, LPITEMIDLIST, __int64 *, _QWORD); // rbx
  LPITEMIDLIST ID; // rax
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  HDC CompatibleDC; // rax
  HDC v14; // rdi
  HMODULE LibraryW; // rax
  HMODULE v16; // r12
  FARPROC ProcAddress; // rax
  LPARAM v18; // rax
  LPARAM v19; // r15
  const struct std::nothrow_t *v20; // rdx
  CExtractImage *v21; // rax
  CExtractImage *v22; // rax
  CExtractImage *v23; // rdi
  int v24; // edi
  const struct std::nothrow_t *v25; // rdx
  CExtractImage *v26; // rax
  CExtractImage *v27; // rax
  CExtractImage *v28; // rdi
  int v29; // edi
  const struct std::nothrow_t *v30; // rdx
  CExtractImage *v31; // rax
  CExtractImage *v32; // rax
  CExtractImage *v33; // rdi
  int v34; // ebx
  __int64 v35; // rdx
  int v36; // ebx
  CExtractImage *v37; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pvar; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v43; // [rsp+74h] [rbp-8Ch]
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  HICON phiconLarge; // [rsp+80h] [rbp-80h] BYREF
  int v46; // [rsp+90h] [rbp-70h] BYREF
  int v47; // [rsp+94h] [rbp-6Ch]
  int v48; // [rsp+98h] [rbp-68h]
  WCHAR *v49; // [rsp+A8h] [rbp-58h]
  int v50; // [rsp+B0h] [rbp-50h]
  int v51; // [rsp+B4h] [rbp-4Ch]
  LPARAM lParam[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v53; // [rsp+100h] [rbp+0h]
  __int64 v54; // [rsp+110h] [rbp+10h]
  struct tagRECT Rect; // [rsp+118h] [rbp+18h] BYREF
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v57[264]; // [rsp+340h] [rbp+240h] BYREF

  v40 = 0;
  *(_OWORD *)lParam = 0;
  v53 = 0;
  v54 = 0;
  v44 = 0;
  phiconLarge = 0;
  memset_0(v57, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v39 = 0x10000000;
  v38 = 256;
  Rect = 0;
  v42 = 48;
  v43 = 48;
  memset(&pvar, 0, sizeof(pvar));
  if ( a1[1] )
  {
    if ( a1[2] )
    {
      DlgItem = GetDlgItem(a1[5], 801);
      v3 = DlgItem;
      if ( DlgItem )
      {
        SendMessageW(DlgItem, 0x108Eu, 4u, 0);
        SendMessageW(v3, 0x1036u, 0, 0x4000);
        _SetExplorerTheme(v3);
        GetClientRect(v3, &Rect);
        lParam[0] = 0x100000028LL;
        LODWORD(lParam[1]) = 1;
        HIDWORD(lParam[1]) = Rect.right - GetSystemMetrics(2);
        SendMessageW(v3, 0x10A2u, 0, (LPARAM)lParam);
        v4 = (const ITEMIDLIST *)IDA_ILClone(a1[7], 0);
        v5 = (ITEMIDLIST *)v4;
        if ( v4 )
        {
          v6 = a1[1];
          v7 = *(__int64 (__fastcall **)(HWND, LPITEMIDLIST, __int64 *, _QWORD))(*(_QWORD *)v6 + 32LL);
          ID = ILFindLastID(v4);
          v9 = v7(v6, ID, &v40, 0);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
                   v40,
                   &WPD_OBJECT_PERSISTENT_UNIQUE_ID,
                   &pvar);
            if ( v9 >= 0 )
            {
              if ( pvar.vt == 10 || !pvar.vt )
                goto LABEL_62;
              v9 = StringCchCopyW(v57, 0x104u, pvar.bstrVal);
              if ( v9 >= 0 )
              {
                v12 = 16711680;
                CompatibleDC = CreateCompatibleDC(0);
                v14 = CompatibleDC;
                if ( CompatibleDC )
                {
                  if ( GetDeviceCaps(CompatibleDC, 12) >= 32 && (int)StartGdiPlus() >= 0 )
                    v12 = 0xFFFFFF;
                  DeleteDC(v14);
                }
                LibraryW = (HMODULE)IsolationAwareLoadLibraryW(L"comctl32.dll");
                v16 = LibraryW;
                if ( LibraryW )
                {
                  ProcAddress = GetProcAddress(LibraryW, "ImageList_Create");
                  if ( ProcAddress )
                  {
                    v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(v42, v43, 33);
                    v19 = v18;
                    if ( v18 )
                    {
                      SendMessageW(v3, 0x1003u, 0, v18);
                      PropVariantClear(&pvar);
                      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
                             v40,
                             &WPDNSE_OBJECT_HAS_CONTACT_PHOTO,
                             &pvar) >= 0
                        && pvar.vt == 11
                        && pvar.iVal == -1 )
                      {
                        v21 = (CExtractImage *)operator new(0x250u, v20);
                        v37 = v21;
                        if ( v21 )
                        {
                          v22 = CExtractImage::CExtractImage(v21, v5, v57, &WPD_RESOURCE_CONTACT_PHOTO);
                          v23 = v22;
                          v37 = v22;
                          if ( v22 )
                          {
                            (*(void (__fastcall **)(CExtractImage *, WCHAR *, __int64, int *, unsigned int *, int, int *))(*(_QWORD *)v22 + 24LL))(
                              v22,
                              Buffer,
                              260,
                              &v39,
                              &v42,
                              32,
                              &v38);
                            if ( (*(int (__fastcall **)(CExtractImage *, __int64 *))(*(_QWORD *)v23 + 32LL))(v23, &v44) >= 0 )
                            {
                              v24 = IsolationAwareImageList_AddMasked(v19, v44, v12);
                              if ( v24 >= 0 )
                              {
                                LoadStringW(g_hInst, 0x39Du, Buffer, 260);
                                memset_0(&v46, 0, 0x58u);
                                v46 = 3;
                                v49 = Buffer;
                                v50 = 260;
                                v47 = SendMessageW(v3, 0x1004u, 0, 0);
                                v51 = v24;
                                v48 = 0;
                                SendMessageW(v3, 0x104Du, 0, (LPARAM)&v46);
                              }
                            }
                            IUnknown_SafeReleaseAndNullPtr<IPortableDevice>(&v37);
                          }
                        }
                      }
                      PropVariantClear(&pvar);
                      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
                             v40,
                             &WPDNSE_OBJECT_HAS_THUMBNAIL,
                             &pvar) >= 0
                        && pvar.vt == 11
                        && pvar.iVal == -1 )
                      {
                        v26 = (CExtractImage *)operator new(0x250u, v25);
                        v37 = v26;
                        if ( v26 )
                        {
                          v27 = CExtractImage::CExtractImage(v26, v5, v57, &WPD_RESOURCE_THUMBNAIL);
                          v28 = v27;
                          v37 = v27;
                          if ( v27 )
                          {
                            (*(void (__fastcall **)(CExtractImage *, WCHAR *, __int64, int *, unsigned int *, int, int *))(*(_QWORD *)v27 + 24LL))(
                              v27,
                              Buffer,
                              260,
                              &v39,
                              &v42,
                              32,
                              &v38);
                            if ( (*(int (__fastcall **)(CExtractImage *, __int64 *))(*(_QWORD *)v28 + 32LL))(v28, &v44) >= 0 )
                            {
                              v29 = IsolationAwareImageList_AddMasked(v19, v44, v12);
                              if ( v29 >= 0 )
                              {
                                LoadStringW(g_hInst, 0x39Eu, Buffer, 260);
                                memset_0(&v46, 0, 0x58u);
                                v46 = 3;
                                v49 = Buffer;
                                v50 = 260;
                                v47 = SendMessageW(v3, 0x1004u, 0, 0);
                                v51 = v29;
                                v48 = 0;
                                SendMessageW(v3, 0x104Du, 0, (LPARAM)&v46);
                              }
                            }
                            IUnknown_SafeReleaseAndNullPtr<IPortableDevice>(&v37);
                          }
                        }
                      }
                      PropVariantClear(&pvar);
                      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
                             v40,
                             &WPDNSE_OBJECT_HAS_ALBUM_ART,
                             &pvar) >= 0
                        && pvar.vt == 11
                        && pvar.iVal == -1 )
                      {
                        v31 = (CExtractImage *)operator new(0x250u, v30);
                        v37 = v31;
                        if ( v31 )
                        {
                          v32 = CExtractImage::CExtractImage(v31, v5, v57, &WPD_RESOURCE_ALBUM_ART);
                          v33 = v32;
                          v37 = v32;
                          if ( v32 )
                          {
                            (*(void (__fastcall **)(CExtractImage *, WCHAR *, __int64, int *, unsigned int *, int, int *))(*(_QWORD *)v32 + 24LL))(
                              v32,
                              Buffer,
                              260,
                              &v39,
                              &v42,
                              32,
                              &v38);
                            if ( (*(int (__fastcall **)(CExtractImage *, __int64 *))(*(_QWORD *)v33 + 32LL))(v33, &v44) >= 0 )
                            {
                              v34 = IsolationAwareImageList_AddMasked(v19, v44, v12);
                              if ( v34 >= 0 )
                              {
                                LoadStringW(g_hInst, 0x39Fu, Buffer, 260);
                                memset_0(&v46, 0, 0x58u);
                                v46 = 3;
                                v49 = Buffer;
                                v50 = 260;
                                v47 = SendMessageW(v3, 0x1004u, 0, 0);
                                v51 = v34;
                                v48 = 0;
                                SendMessageW(v3, 0x104Du, 0, (LPARAM)&v46);
                              }
                            }
                            IUnknown_SafeReleaseAndNullPtr<IPortableDevice>(&v37);
                          }
                        }
                      }
                      PropVariantClear(&pvar);
                      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
                             v40,
                             &WPDNSE_OBJECT_HAS_AUDIO_CLIP,
                             &pvar) >= 0
                        && pvar.vt == 11
                        && pvar.iVal == -1
                        && SHDefExtractIconW(L"wpdshext.dll", -681, 0, &phiconLarge, 0, 0x30u) >= 0 )
                      {
                        v36 = IsolationAwareImageList_ReplaceIcon(v19, v35, phiconLarge);
                        if ( v36 >= 0 )
                        {
                          LoadStringW(g_hInst, 0x3A0u, Buffer, 260);
                          memset_0(&v46, 0, 0x58u);
                          v46 = 3;
                          v49 = Buffer;
                          v50 = 260;
                          v47 = SendMessageW(v3, 0x1004u, 0, 0);
                          v51 = v36;
                          v48 = 0;
                          SendMessageW(v3, 0x104Du, 0, (LPARAM)&v46);
                        }
                      }
                    }
                  }
                  FreeLibrary(v16);
                }
                goto LABEL_62;
              }
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
LABEL_62:
                ILFree(v5);
                goto LABEL_63;
              }
              v11 = 34;
            }
            else
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_62;
              v11 = 33;
            }
          }
          else
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_62;
            v11 = 32;
          }
          WPP_SF_d(v10[2], v11, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v9);
          goto LABEL_62;
        }
      }
    }
  }
LABEL_63:
  PropVariantClear(&pvar);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
}

```

## disassembly

```asm
0x18004e598  mov     [rsp-8+arg_8], rbx
0x18004e59d  mov     [rsp-8+arg_10], rsi
0x18004e5a2  push    rbp
0x18004e5a3  push    rdi
0x18004e5a4  push    r12
0x18004e5a6  push    r13
0x18004e5a8  push    r15
0x18004e5aa  lea     rbp, [rsp-460h]
0x18004e5b2  sub     rsp, 560h
0x18004e5b9  mov     rax, cs:__security_cookie
0x18004e5c0  xor     rax, rsp
0x18004e5c3  mov     [rbp+480h+var_30], rax
0x18004e5ca  mov     rdi, rcx
0x18004e5cd  xor     r15d, r15d
0x18004e5d0  mov     [rsp+580h+var_530], r15
0x18004e5d5  xorps   xmm0, xmm0
0x18004e5d8  xor     eax, eax
0x18004e5da  movups  xmmword ptr [rbp+480h+lParam], xmm0
0x18004e5de  movups  [rbp+480h+var_480], xmm0
0x18004e5e2  mov     [rbp+480h+var_470], rax
0x18004e5e6  mov     [rsp+580h+var_508], r15
0x18004e5eb  mov     [rbp+480h+phiconLarge], r15
0x18004e5ef  mov     ebx, 208h
0x18004e5f4  mov     r8d, ebx; Size
0x18004e5f7  xor     edx, edx; Val
0x18004e5f9  lea     rcx, [rbp+480h+var_240]; void *
0x18004e600  call    memset_0
0x18004e605  mov     r8d, ebx; Size
0x18004e608  xor     edx, edx; Val
0x18004e60a  lea     rcx, [rbp+480h+Buffer]; void *
0x18004e60e  call    memset_0
0x18004e613  mov     [rsp+580h+var_534], 10000000h
0x18004e61b  mov     [rsp+580h+var_538], 100h
0x18004e623  xorps   xmm0, xmm0
0x18004e626  movups  xmmword ptr [rbp+480h+Rect.left], xmm0
0x18004e62a  lea     eax, [r15+30h]
0x18004e62e  mov     [rsp+580h+var_510], eax
0x18004e632  mov     [rsp+580h+var_50C], eax
0x18004e636  xor     eax, eax
0x18004e638  movups  xmmword ptr [rsp+580h+pvar], xmm0
0x18004e63d  mov     qword ptr [rsp+580h+pvar+10h], rax
0x18004e642  cmp     [rdi+8], r15
0x18004e646  jz      loc_18004EE40
0x18004e64c  cmp     [rdi+10h], r15
0x18004e650  jz      loc_18004EE40
0x18004e656  mov     edx, 321h; nIDDlgItem
0x18004e65b  mov     rcx, [rdi+28h]; hDlg
0x18004e65f  call    cs:__imp_GetDlgItem
0x18004e665  mov     rsi, rax
0x18004e668  test    rax, rax
0x18004e66b  jz      loc_18004EE40
0x18004e671  xor     r9d, r9d; lParam
0x18004e674  mov     edx, 108Eh; Msg
0x18004e679  lea     r8d, [r15+4]; wParam
0x18004e67d  mov     rcx, rax; hWnd
0x18004e680  call    cs:__imp_SendMessageW
0x18004e686  mov     r9d, 4000h; lParam
0x18004e68c  xor     r8d, r8d; wParam
0x18004e68f  mov     edx, 1036h; Msg
0x18004e694  mov     rcx, rsi; hWnd
0x18004e697  call    cs:__imp_SendMessageW
0x18004e69d  mov     rcx, rsi; HWND
0x18004e6a0  call    ?_SetExplorerTheme@@YAJPEAUHWND__@@@Z; _SetExplorerTheme(HWND__ *)
0x18004e6a5  lea     rdx, [rbp+480h+Rect]; lpRect
0x18004e6a9  mov     rcx, rsi; hWnd
0x18004e6ac  call    cs:__imp_GetClientRect
0x18004e6b2  lea     ecx, [r15+2]; nIndex
0x18004e6b6  call    cs:__imp_GetSystemMetrics
0x18004e6bc  mov     ecx, [rbp+480h+Rect.right]
0x18004e6bf  sub     ecx, eax
0x18004e6c1  mov     dword ptr [rbp+480h+lParam], 28h ; '('
0x18004e6c8  lea     eax, [r15+1]
0x18004e6cc  mov     dword ptr [rbp+480h+lParam+8], eax
0x18004e6cf  mov     dword ptr [rbp+480h+lParam+4], eax
0x18004e6d2  mov     dword ptr [rbp+480h+lParam+0Ch], ecx
0x18004e6d5  lea     r9, [rbp+480h+lParam]; lParam
0x18004e6d9  xor     r8d, r8d; wParam
0x18004e6dc  mov     edx, 10A2h; Msg
0x18004e6e1  mov     rcx, rsi; hWnd
0x18004e6e4  call    cs:__imp_SendMessageW
0x18004e6ea  xor     edx, edx
0x18004e6ec  mov     rcx, [rdi+38h]
0x18004e6f0  call    IDA_ILClone
0x18004e6f5  mov     r13, rax
0x18004e6f8  test    rax, rax
0x18004e6fb  jz      loc_18004EE40
0x18004e701  mov     rdi, [rdi+8]
0x18004e705  mov     rdx, [rdi]
0x18004e708  mov     rbx, [rdx+20h]
0x18004e70c  mov     rcx, rax; pidl
0x18004e70f  call    cs:__imp_ILFindLastID
0x18004e715  xor     r9d, r9d
0x18004e718  lea     r8, [rsp+580h+var_530]
0x18004e71d  mov     rdx, rax
0x18004e720  mov     rcx, rdi
0x18004e723  mov     rax, rbx
0x18004e726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e72b  test    eax, eax
0x18004e72d  jns     short loc_18004E76C
0x18004e72f  lea     rdx, WPP_GLOBAL_Control
0x18004e736  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e73d  cmp     rcx, rdx
0x18004e740  jz      loc_18004EE37
0x18004e746  test    byte ptr [rcx+1Ch], 2
0x18004e74a  jz      loc_18004EE37
0x18004e750  lea     edx, [r15+20h]
0x18004e754  mov     r9d, eax
0x18004e757  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004e75e  mov     rcx, [rcx+10h]
0x18004e762  call    WPP_SF_d
0x18004e767  jmp     loc_18004EE37
0x18004e76c  mov     rcx, [rsp+580h+var_530]
0x18004e771  mov     rax, [rcx]
0x18004e774  lea     r8, [rsp+580h+pvar]
0x18004e779  lea     rdx, WPD_OBJECT_PERSISTENT_UNIQUE_ID
0x18004e780  mov     rax, [rax+28h]
0x18004e784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e789  test    eax, eax
0x18004e78b  jns     short loc_18004E7B5
0x18004e78d  lea     rdx, WPP_GLOBAL_Control
0x18004e794  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e79b  cmp     rcx, rdx
0x18004e79e  jz      loc_18004EE37
0x18004e7a4  test    byte ptr [rcx+1Ch], 2
0x18004e7a8  jz      loc_18004EE37
0x18004e7ae  mov     edx, 21h ; '!'
0x18004e7b3  jmp     short loc_18004E754
0x18004e7b5  mov     eax, 0Ah
0x18004e7ba  cmp     ax, word ptr [rsp+580h+pvar]
0x18004e7bf  jz      loc_18004EE37
0x18004e7c5  cmp     r15w, word ptr [rsp+580h+pvar]
0x18004e7cb  jz      loc_18004EE37
0x18004e7d1  mov     r8, qword ptr [rsp+580h+pvar+8]; unsigned __int16 *
0x18004e7d6  mov     edx, 104h; unsigned __int64
0x18004e7db  lea     rcx, [rbp+480h+var_240]; unsigned __int16 *
0x18004e7e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004e7e7  test    eax, eax
0x18004e7e9  jns     short loc_18004E816
0x18004e7eb  lea     rdx, WPP_GLOBAL_Control
0x18004e7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e7f9  cmp     rcx, rdx
0x18004e7fc  jz      loc_18004EE37
0x18004e802  test    byte ptr [rcx+1Ch], 2
0x18004e806  jz      loc_18004EE37
0x18004e80c  mov     edx, 22h ; '"'
0x18004e811  jmp     loc_18004E754
0x18004e816  mov     ebx, 0FF0000h
0x18004e81b  xor     ecx, ecx; hdc
0x18004e81d  call    cs:__imp_CreateCompatibleDC
0x18004e823  mov     rdi, rax
0x18004e826  test    rax, rax
0x18004e829  jz      short loc_18004E856
0x18004e82b  mov     edx, 0Ch; index
0x18004e830  mov     rcx, rax; hdc
0x18004e833  call    cs:__imp_GetDeviceCaps
0x18004e839  cmp     eax, 20h ; ' '
0x18004e83c  jl      short loc_18004E84D
0x18004e83e  call    ?StartGdiPlus@@YAJXZ; StartGdiPlus(void)
0x18004e843  mov     ecx, 0FFFFFFh
0x18004e848  test    eax, eax
0x18004e84a  cmovns  ebx, ecx
0x18004e84d  mov     rcx, rdi; hdc
0x18004e850  call    cs:__imp_DeleteDC
0x18004e856  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18004e85d  call    IsolationAwareLoadLibraryW
0x18004e862  mov     r12, rax
0x18004e865  test    rax, rax
0x18004e868  jz      loc_18004EE37
0x18004e86e  lea     rdx, aImagelistCreat; "ImageList_Create"
0x18004e875  mov     rcx, rax; hModule
0x18004e878  call    cs:__imp_GetProcAddress
0x18004e87e  test    rax, rax
0x18004e881  jz      loc_18004EE2E
0x18004e887  mov     dword ptr [rsp+580h+phiconSmall], 4
0x18004e88f  mov     r9d, 4
0x18004e895  lea     r8d, [r9+1Dh]
0x18004e899  mov     edx, [rsp+580h+var_50C]
0x18004e89d  mov     ecx, [rsp+580h+var_510]
0x18004e8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8a6  mov     r15, rax
0x18004e8a9  test    rax, rax
0x18004e8ac  jz      loc_18004EE2E
0x18004e8b2  mov     r9, rax; lParam
0x18004e8b5  xor     r8d, r8d; wParam
0x18004e8b8  mov     edx, 1003h; Msg
0x18004e8bd  mov     rcx, rsi; hWnd
0x18004e8c0  call    cs:__imp_SendMessageW
0x18004e8c6  lea     rcx, [rsp+580h+pvar]; pvar
0x18004e8cb  call    cs:__imp_PropVariantClear
0x18004e8d1  mov     rcx, [rsp+580h+var_530]
0x18004e8d6  mov     rdx, [rcx]
0x18004e8d9  mov     rax, [rdx+28h]
0x18004e8dd  lea     r8, [rsp+580h+pvar]
0x18004e8e2  lea     rdx, WPDNSE_OBJECT_HAS_CONTACT_PHOTO
0x18004e8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8ee  test    eax, eax
0x18004e8f0  js      loc_18004EA3D
0x18004e8f6  cmp     word ptr [rsp+580h+pvar], 0Bh
0x18004e8fc  jnz     loc_18004EA3D
0x18004e902  cmp     word ptr [rsp+580h+pvar+8], 0FFFFh
0x18004e908  jnz     loc_18004EA3D
0x18004e90e  mov     ecx, 250h; unsigned __int64
0x18004e913  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004e918  mov     [rsp+580h+var_540], rax
0x18004e91d  test    rax, rax
0x18004e920  jz      loc_18004EA3D
0x18004e926  lea     r9, WPD_RESOURCE_CONTACT_PHOTO; struct _tagpropertykey *
0x18004e92d  lea     r8, [rbp+480h+var_240]; unsigned __int16 *
0x18004e934  mov     rdx, r13; struct _ITEMIDLIST *
0x18004e937  mov     rcx, rax; this
0x18004e93a  call    ??0CExtractImage@@QEAA@PEFAU_ITEMIDLIST@@PEBGAEBU_tagpropertykey@@@Z; CExtractImage::CExtractImage(_ITEMIDLIST *,ushort const *,_tagpropertykey const &)
0x18004e93f  mov     rdi, rax
0x18004e942  mov     [rsp+580h+var_540], rax
0x18004e947  test    rax, rax
0x18004e94a  jz      loc_18004EA3D
0x18004e950  mov     rcx, [rax]
0x18004e953  mov     rax, [rcx+18h]
0x18004e957  lea     rcx, [rsp+580h+var_538]
0x18004e95c  mov     [rsp+580h+var_550], rcx
0x18004e961  mov     [rsp+580h+nIconSize], 20h ; ' '
0x18004e969  lea     rcx, [rsp+580h+var_510]
0x18004e96e  mov     [rsp+580h+phiconSmall], rcx
0x18004e973  lea     r9, [rsp+580h+var_534]
0x18004e978  mov     r8d, 104h
0x18004e97e  lea     rdx, [rbp+480h+Buffer]
0x18004e982  mov     rcx, rdi
0x18004e985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e98a  mov     rax, [rdi]
0x18004e98d  lea     rdx, [rsp+580h+var_508]
0x18004e992  mov     rcx, rdi
0x18004e995  mov     rax, [rax+20h]
0x18004e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e99e  test    eax, eax
0x18004e9a0  js      loc_18004EA33
0x18004e9a6  mov     r8d, ebx
0x18004e9a9  mov     rdx, [rsp+580h+var_508]
0x18004e9ae  mov     rcx, r15
0x18004e9b1  call    IsolationAwareImageList_AddMasked
0x18004e9b6  mov     edi, eax
0x18004e9b8  test    eax, eax
0x18004e9ba  js      short loc_18004EA33
0x18004e9bc  mov     r9d, 104h; cchBufferMax
0x18004e9c2  lea     r8, [rbp+480h+Buffer]; lpBuffer
0x18004e9c6  mov     edx, 39Dh; uID
0x18004e9cb  mov     rcx, cs:g_hInst; hInstance
0x18004e9d2  call    cs:__imp_LoadStringW
0x18004e9d8  xor     edx, edx; Val
0x18004e9da  lea     r8d, [rdx+58h]; Size
0x18004e9de  lea     rcx, [rbp+480h+var_4F0]; void *
0x18004e9e2  call    memset_0
0x18004e9e7  mov     dword ptr [rbp+480h+var_4F0], 3
0x18004e9ee  lea     rax, [rbp+480h+Buffer]
0x18004e9f2  mov     [rbp+480h+var_4D8], rax
0x18004e9f6  mov     [rbp+480h+var_4D0], 104h
0x18004e9fd  xor     r9d, r9d; lParam
0x18004ea00  xor     r8d, r8d; wParam
0x18004ea03  mov     edx, 1004h; Msg
0x18004ea08  mov     rcx, rsi; hWnd
0x18004ea0b  call    cs:__imp_SendMessageW
0x18004ea11  mov     dword ptr [rbp+480h+var_4F0+4], eax
0x18004ea14  mov     [rbp+480h+var_4CC], edi
0x18004ea17  mov     [rbp+480h+var_4E8], 0
0x18004ea1e  lea     r9, [rbp+480h+var_4F0]; lParam
0x18004ea22  xor     r8d, r8d; wParam
0x18004ea25  mov     edx, 104Dh; Msg
0x18004ea2a  mov     rcx, rsi; hWnd
0x18004ea2d  call    cs:__imp_SendMessageW
0x18004ea33  lea     rcx, [rsp+580h+var_540]
0x18004ea38  call    ??$IUnknown_SafeReleaseAndNullPtr@UIPortableDevice@@@@YAXAEAPEAUIPortableDevice@@@Z; IUnknown_SafeReleaseAndNullPtr<IPortableDevice>(IPortableDevice * &)
0x18004ea3d  lea     rcx, [rsp+580h+pvar]; pvar
0x18004ea42  call    cs:__imp_PropVariantClear
0x18004ea48  mov     rcx, [rsp+580h+var_530]
0x18004ea4d  mov     rax, [rcx]
0x18004ea50  lea     r8, [rsp+580h+pvar]
0x18004ea55  lea     rdx, WPDNSE_OBJECT_HAS_THUMBNAIL
0x18004ea5c  mov     rax, [rax+28h]
0x18004ea60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea65  test    eax, eax
0x18004ea67  js      loc_18004EBB4
0x18004ea6d  cmp     word ptr [rsp+580h+pvar], 0Bh
0x18004ea73  jnz     loc_18004EBB4
0x18004ea79  cmp     word ptr [rsp+580h+pvar+8], 0FFFFh
0x18004ea7f  jnz     loc_18004EBB4
0x18004ea85  mov     ecx, 250h; unsigned __int64
0x18004ea8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004ea8f  mov     [rsp+580h+var_540], rax
0x18004ea94  test    rax, rax
0x18004ea97  jz      loc_18004EBB4
0x18004ea9d  lea     r9, WPD_RESOURCE_THUMBNAIL; struct _tagpropertykey *
0x18004eaa4  lea     r8, [rbp+480h+var_240]; unsigned __int16 *
0x18004eaab  mov     rdx, r13; struct _ITEMIDLIST *
0x18004eaae  mov     rcx, rax; this
0x18004eab1  call    ??0CExtractImage@@QEAA@PEFAU_ITEMIDLIST@@PEBGAEBU_tagpropertykey@@@Z; CExtractImage::CExtractImage(_ITEMIDLIST *,ushort const *,_tagpropertykey const &)
0x18004eab6  mov     rdi, rax
0x18004eab9  mov     [rsp+580h+var_540], rax
0x18004eabe  test    rax, rax
0x18004eac1  jz      loc_18004EBB4
0x18004eac7  mov     rcx, [rax]
0x18004eaca  mov     rax, [rcx+18h]
0x18004eace  lea     rcx, [rsp+580h+var_538]
  ... truncated ...
```
