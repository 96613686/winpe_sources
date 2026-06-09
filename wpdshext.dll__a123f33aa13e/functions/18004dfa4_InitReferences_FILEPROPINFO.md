# _InitReferences(FILEPROPINFO *)

- ea: `0x18004dfa4`
- end: `0x18004e431`
- name: `?_InitReferences@@YAXPEAUFILEPROPINFO@@@Z`
- size: `1165`
- prototype: `void __fastcall(struct FILEPROPINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004af50`

## callees

- `0x180004190`
- `0x1800082e0`
- `0x18000ef50`
- `0x180014dd0`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x1800496e0`
- `0x18004dfa4`
- `0x18005072c`
- `0x1800628cc`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathRemoveExtensionW` at `0x18004e376`
- `SHLWAPI!PathRemoveExtensionW` at `0x18004e376`
- `USER32!LoadStringW` at `0x18004e10d`
- `USER32!LoadStringW` at `0x18004e10d`
- `USER32!SendMessageW` at `0x18004e09e`
- `USER32!SendMessageW` at `0x18004e0ca`
- `USER32!SendMessageW` at `0x18004e15d`
- `USER32!SendMessageW` at `0x18004e3c3`
- `USER32!SendMessageW` at `0x18004e3fc`
- `USER32!SendMessageW` at `0x18004e09e`
- `USER32!SendMessageW` at `0x18004e0ca`
- `USER32!SendMessageW` at `0x18004e15d`
- `USER32!SendMessageW` at `0x18004e3c3`
- `USER32!SendMessageW` at `0x18004e3fc`
- `USER32!GetDlgItem` at `0x18004e076`
- `USER32!GetDlgItem` at `0x18004e076`
- `USER32!GetClientRect` at `0x18004e0db`
- `USER32!GetClientRect` at `0x18004e0db`
- `USER32!GetSystemMetrics` at `0x18004e0e4`
- `USER32!GetSystemMetrics` at `0x18004e0e4`
- `ole32!PropVariantClear` at `0x18004e1de`
- `ole32!PropVariantClear` at `0x18004e423`
- `ole32!PropVariantClear` at `0x18004e1de`
- `ole32!PropVariantClear` at `0x18004e423`
- `SHELL32!SHGetFileInfoW` at `0x18004e368`
- `SHELL32!SHGetFileInfoW` at `0x18004e368`
- `SHELL32!__imp_Shell_GetImageLists` at `0x18004e0b3`
- `SHELL32!__imp_Shell_GetImageLists` at `0x18004e0b3`
- `SHELL32!__imp_ILFree` at `0x18004e1c5`
- `SHELL32!__imp_ILFree` at `0x18004e1d3`
- `SHELL32!__imp_ILFree` at `0x18004e40a`
- `SHELL32!__imp_ILFree` at `0x18004e1c5`
- `SHELL32!__imp_ILFree` at `0x18004e1d3`
- `SHELL32!__imp_ILFree` at `0x18004e40a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _InitReferences(struct FILEPROPINFO *a1)
{
  struct FILEPROPINFO *v1; // r14
  ITEMIDLIST *v2; // rsi
  HWND DlgItem; // rax
  HWND v4; // r15
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rdx
  ITEMIDLIST *v9; // r12
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int i; // ebx
  int v14; // eax
  CContentFolder *v15; // rcx
  const struct CONTENTITEM *v16; // rax
  CContentFolder *v17; // rcx
  unsigned int v18; // r9d
  unsigned int v19; // [rsp+34h] [rbp-634h] BYREF
  int v20; // [rsp+38h] [rbp-630h] BYREF
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-628h] BYREF
  struct IPortableDevice *v22; // [rsp+48h] [rbp-620h] BYREF
  HIMAGELIST phimlSmall; // [rsp+50h] [rbp-618h] BYREF
  ITEMIDLIST *v24; // [rsp+58h] [rbp-610h]
  HWND v25; // [rsp+60h] [rbp-608h]
  struct FILEPROPINFO *v26; // [rsp+68h] [rbp-600h]
  PROPVARIANT pvar; // [rsp+70h] [rbp-5F8h] BYREF
  int v28; // [rsp+88h] [rbp-5E0h] BYREF
  _QWORD *v29; // [rsp+90h] [rbp-5D8h]
  CContentFolder **v30; // [rsp+98h] [rbp-5D0h]
  LPARAM lParam[2]; // [rsp+A0h] [rbp-5C8h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-5B8h]
  __int128 v33; // [rsp+C0h] [rbp-5A8h]
  __int64 v34; // [rsp+D0h] [rbp-598h]
  _DWORD v35[6]; // [rsp+E0h] [rbp-588h] BYREF
  WCHAR *v36; // [rsp+F8h] [rbp-570h]
  int v37; // [rsp+100h] [rbp-568h]
  int iIcon; // [rsp+104h] [rbp-564h]
  struct tagRECT Rect; // [rsp+140h] [rbp-528h] BYREF
  SHFILEINFOW psfi; // [rsp+150h] [rbp-518h] BYREF
  WCHAR Buffer[264]; // [rsp+410h] [rbp-258h] BYREF

  v1 = a1;
  v26 = a1;
  v22 = 0;
  v2 = 0;
  pidl = 0;
  memset_0(&psfi, 0, sizeof(psfi));
  phimlSmall = 0;
  *(_OWORD *)lParam = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  memset_0(Buffer, 0, 0x208u);
  v19 = 0;
  Rect = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( *((_QWORD *)v1 + 1) )
  {
    if ( *((_QWORD *)v1 + 2) )
    {
      DlgItem = GetDlgItem(*((HWND *)v1 + 6), 803);
      v4 = DlgItem;
      v25 = DlgItem;
      if ( DlgItem )
      {
        SendMessageW(DlgItem, 0x1036u, 0, 16416);
        _SetExplorerTheme(v4);
        Shell_GetImageLists(0, &phimlSmall);
        SendMessageW(v4, 0x1003u, 1u, (LPARAM)phimlSmall);
        GetClientRect(v4, &Rect);
        v5 = Rect.right - GetSystemMetrics(2);
        LoadStringW(g_hInst, 0x356u, Buffer, 260);
        LODWORD(lParam[0]) = 6;
        *(_QWORD *)&v32 = Buffer;
        DWORD2(v32) = 260;
        v6 = 10;
        if ( v5 > 10 )
          v6 = v5;
        LODWORD(lParam[1]) = v6;
        SendMessageW(v4, 0x1061u, 0, (LPARAM)lParam);
        v7 = IDA_ILClone(*((_QWORD *)v1 + 7), 0);
        v9 = (ITEMIDLIST *)v7;
        v24 = (ITEMIDLIST *)v7;
        if ( v7 )
        {
          v10 = SHBindToIDList(v7, v8, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v22);
          if ( v10 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 30;
LABEL_11:
              WPP_SF_d(v11[2], v12, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v10);
              goto LABEL_12;
            }
            goto LABEL_12;
          }
          v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v1 + 78) + 24LL))(
                  *((_QWORD *)v1 + 78),
                  &v19);
          if ( v10 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 31;
              goto LABEL_11;
            }
LABEL_12:
            ILFree(v9);
            if ( v2 )
              ILFree(v2);
            goto LABEL_14;
          }
          v30 = (CContentFolder **)((char *)v1 + 16);
          v29 = (_QWORD *)((char *)v1 + 624);
          for ( i = 0; ; ++i )
          {
            if ( i >= v19 )
              goto LABEL_12;
            if ( (*(int (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)*v29 + 32LL))(*v29, i, &pvar) >= 0
              && pvar.vt != 10 )
            {
              try
              {
                ((void (__fastcall *)(_QWORD, _QWORD))ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add)(
                  (char *)v1 + 632,
                  (LARGE_INTEGER)pvar.hVal.QuadPart);
              }
              catch ( ATL::CAtlException v28 )
              {
                v20 = v28;
                v9 = v24;
                v4 = v25;
                v1 = v26;
                if ( v20 < 0 )
                {
                  v2 = pidl;
                  goto LABEL_31;
                }
              }
              v14 = CContentFolder::_CreateIDList(*v30, v22, pvar.bstrVal, 0, &pidl, &v20);
              v2 = pidl;
              if ( v14 >= 0 )
              {
                v16 = CContentFolder::_IsValid(v15, pidl);
                if ( v16 )
                {
                  CContentFolder::_Name(v17, v16, Buffer, v18);
                  SHGetFileInfoW(Buffer, 0, &psfi, 0x2B8u, 0x4011u);
                  PathRemoveExtensionW(Buffer);
                  memset_0(v35, 0, 0x58u);
                  v35[0] = 3;
                  v36 = Buffer;
                  v37 = 260;
                  v35[1] = SendMessageW(v4, 0x1004u, 0, 0);
                  iIcon = psfi.iIcon;
                  v35[2] = 0;
                  SendMessageW(v4, 0x104Du, 0, (LPARAM)v35);
                }
                if ( v2 )
                {
                  ILFree(v2);
                  v2 = 0;
                  pidl = 0;
                }
              }
            }
LABEL_31:
            PropVariantClear(&pvar);
          }
        }
      }
    }
  }
LABEL_14:
  PropVariantClear(&pvar);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
}

```

## disassembly

```asm
0x18004dfa4  push    rbx
0x18004dfa6  push    rsi
0x18004dfa7  push    r12
0x18004dfa9  push    r13
0x18004dfab  push    r14
0x18004dfad  push    r15
0x18004dfaf  sub     rsp, 638h
0x18004dfb6  mov     rax, cs:__security_cookie
0x18004dfbd  xor     rax, rsp
0x18004dfc0  mov     [rsp+668h+var_48], rax
0x18004dfc8  mov     r14, rcx
0x18004dfcb  mov     [rsp+668h+var_600], rcx
0x18004dfd0  mov     [rsp+668h+var_620], 0
0x18004dfd9  xor     esi, esi
0x18004dfdb  mov     [rsp+668h+pidl], rsi
0x18004dfe0  xor     edx, edx; Val
0x18004dfe2  mov     r8d, 2B8h; Size
0x18004dfe8  lea     rcx, [rsp+668h+psfi]; void *
0x18004dff0  call    memset_0
0x18004dff5  mov     [rsp+668h+phimlSmall], rsi
0x18004dffa  xorps   xmm0, xmm0
0x18004dffd  xor     eax, eax
0x18004dfff  movups  xmmword ptr [rsp+668h+lParam], xmm0
0x18004e007  movups  [rsp+668h+var_5B8], xmm0
0x18004e00f  movups  [rsp+668h+var_5A8], xmm0
0x18004e017  mov     [rsp+668h+var_598], rax
0x18004e01f  xor     edx, edx; Val
0x18004e021  mov     r8d, 208h; Size
0x18004e027  lea     rcx, [rsp+668h+Buffer]; void *
0x18004e02f  call    memset_0
0x18004e034  mov     [rsp+668h+var_634], esi
0x18004e038  xorps   xmm0, xmm0
0x18004e03b  movups  xmmword ptr [rsp+668h+Rect.left], xmm0
0x18004e043  xorps   xmm1, xmm1
0x18004e046  xor     eax, eax
0x18004e048  movups  xmmword ptr [rsp+668h+pvar], xmm1
0x18004e04d  mov     qword ptr [rsp+668h+pvar+10h], rax
0x18004e055  cmp     [r14+8], rax
0x18004e059  jz      loc_18004E1D9
0x18004e05f  lea     r13, [r14+10h]
0x18004e063  cmp     [r13+0], rax
0x18004e067  jz      loc_18004E1D9
0x18004e06d  mov     edx, 323h; nIDDlgItem
0x18004e072  mov     rcx, [r14+30h]; hDlg
0x18004e076  call    cs:__imp_GetDlgItem
0x18004e07c  mov     r15, rax
0x18004e07f  mov     [rsp+668h+var_608], rax
0x18004e084  test    rax, rax
0x18004e087  jz      loc_18004E1D9
0x18004e08d  mov     r9d, 4020h; lParam
0x18004e093  xor     r8d, r8d; wParam
0x18004e096  mov     edx, 1036h; Msg
0x18004e09b  mov     rcx, rax; hWnd
0x18004e09e  call    cs:__imp_SendMessageW
0x18004e0a4  mov     rcx, r15; HWND
0x18004e0a7  call    ?_SetExplorerTheme@@YAJPEAUHWND__@@@Z; _SetExplorerTheme(HWND__ *)
0x18004e0ac  lea     rdx, [rsp+668h+phimlSmall]; phimlSmall
0x18004e0b1  xor     ecx, ecx; phiml
0x18004e0b3  call    cs:__imp_Shell_GetImageLists
0x18004e0b9  mov     r9, [rsp+668h+phimlSmall]; lParam
0x18004e0be  mov     edx, 1003h; Msg
0x18004e0c3  lea     r8d, [rsi+1]; wParam
0x18004e0c7  mov     rcx, r15; hWnd
0x18004e0ca  call    cs:__imp_SendMessageW
0x18004e0d0  lea     rdx, [rsp+668h+Rect]; lpRect
0x18004e0d8  mov     rcx, r15; hWnd
0x18004e0db  call    cs:__imp_GetClientRect
0x18004e0e1  lea     ecx, [rsi+2]; nIndex
0x18004e0e4  call    cs:__imp_GetSystemMetrics
0x18004e0ea  mov     ebx, [rsp+668h+Rect.right]
0x18004e0f1  sub     ebx, eax
0x18004e0f3  mov     r9d, 104h; cchBufferMax
0x18004e0f9  lea     r8, [rsp+668h+Buffer]; lpBuffer
0x18004e101  mov     edx, 356h; uID
0x18004e106  mov     rcx, cs:g_hInst; hInstance
0x18004e10d  call    cs:__imp_LoadStringW
0x18004e113  mov     dword ptr [rsp+668h+lParam], 6
0x18004e11e  lea     rax, [rsp+668h+Buffer]
0x18004e126  mov     qword ptr [rsp+668h+var_5B8], rax
0x18004e12e  mov     dword ptr [rsp+668h+var_5B8+8], 104h
0x18004e139  lea     ecx, [rsi+0Ah]
0x18004e13c  mov     eax, ecx
0x18004e13e  cmp     ebx, ecx
0x18004e140  cmovg   eax, ebx
0x18004e143  mov     dword ptr [rsp+668h+lParam+8], eax
0x18004e14a  lea     r9, [rsp+668h+lParam]; lParam
0x18004e152  xor     r8d, r8d; wParam
0x18004e155  mov     edx, 1061h; Msg
0x18004e15a  mov     rcx, r15; hWnd
0x18004e15d  call    cs:__imp_SendMessageW
0x18004e163  xor     edx, edx
0x18004e165  mov     rcx, [r14+38h]
0x18004e169  call    IDA_ILClone
0x18004e16e  mov     r12, rax
0x18004e171  mov     [rsp+668h+var_610], rax
0x18004e176  test    rax, rax
0x18004e179  jz      short loc_18004E1D9
0x18004e17b  lea     r9, [rsp+668h+var_620]
0x18004e180  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x18004e187  mov     rcx, rax
0x18004e18a  call    SHBindToIDList
0x18004e18f  test    eax, eax
0x18004e191  jns     short loc_18004E211
0x18004e193  lea     rdx, WPP_GLOBAL_Control
0x18004e19a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e1a1  cmp     rcx, rdx
0x18004e1a4  jz      short loc_18004E1C2
0x18004e1a6  test    byte ptr [rcx+1Ch], 2
0x18004e1aa  jz      short loc_18004E1C2
0x18004e1ac  lea     edx, [rsi+1Eh]
0x18004e1af  mov     r9d, eax
0x18004e1b2  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004e1b9  mov     rcx, [rcx+10h]
0x18004e1bd  call    WPP_SF_d
0x18004e1c2  mov     rcx, r12; pidl
0x18004e1c5  call    cs:__imp_ILFree
0x18004e1cb  test    rsi, rsi
0x18004e1ce  jz      short loc_18004E1D9
0x18004e1d0  mov     rcx, rsi; pidl
0x18004e1d3  call    cs:__imp_ILFree
0x18004e1d9  lea     rcx, [rsp+668h+pvar]; pvar
0x18004e1de  call    cs:__imp_PropVariantClear
0x18004e1e4  nop
0x18004e1e5  lea     rcx, [rsp+668h+var_620]
0x18004e1ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004e1ef  mov     rcx, [rsp+668h+var_48]
0x18004e1f7  xor     rcx, rsp; StackCookie
0x18004e1fa  call    __security_check_cookie
0x18004e1ff  add     rsp, 638h
0x18004e206  pop     r15
0x18004e208  pop     r14
0x18004e20a  pop     r13
0x18004e20c  pop     r12
0x18004e20e  pop     rsi
0x18004e20f  pop     rbx
0x18004e210  retn
0x18004e211  lea     rbx, [r14+270h]
0x18004e218  mov     rcx, [rbx]
0x18004e21b  mov     rax, [rcx]
0x18004e21e  lea     rdx, [rsp+668h+var_634]
0x18004e223  mov     rax, [rax+18h]
0x18004e227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e22c  test    eax, eax
0x18004e22e  jns     short loc_18004E25B
0x18004e230  lea     rdx, WPP_GLOBAL_Control
0x18004e237  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e23e  cmp     rcx, rdx
0x18004e241  jz      loc_18004E1C2
0x18004e247  test    byte ptr [rcx+1Ch], 2
0x18004e24b  jz      loc_18004E1C2
0x18004e251  mov     edx, 1Fh
0x18004e256  jmp     loc_18004E1AF
0x18004e25b  mov     [rsp+668h+var_5D0], r13
0x18004e263  mov     [rsp+668h+var_5D8], rbx
0x18004e26b  xor     ebx, ebx
0x18004e26d  lea     r13d, [rbx+0Ah]
0x18004e271  mov     [rsp+668h+var_638], ebx
0x18004e275  cmp     ebx, [rsp+668h+var_634]
0x18004e279  jnb     loc_18004E1C2
0x18004e27f  mov     rax, [rsp+668h+var_5D8]
0x18004e287  mov     rcx, [rax]
0x18004e28a  mov     rax, [rcx]
0x18004e28d  lea     r8, [rsp+668h+pvar]
0x18004e292  mov     edx, ebx
0x18004e294  mov     rax, [rax+20h]
0x18004e298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e29d  test    eax, eax
0x18004e29f  js      loc_18004E41E
0x18004e2a5  cmp     word ptr [rsp+668h+pvar], r13w
0x18004e2ab  jz      loc_18004E41E
0x18004e2b1  lea     rcx, [r14+278h]
0x18004e2b8  mov     rdx, qword ptr [rsp+668h+pvar+8]
0x18004e2bd  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x18004e2c2  nop
0x18004e2c3  jmp     short loc_18004E2E9
0x18004e2c5  mov     r13d, 0Ah
0x18004e2cb  mov     r12, [rsp+668h+var_610]
0x18004e2d0  mov     r15, [rsp+668h+var_608]
0x18004e2d5  mov     ebx, [rsp+668h+var_638]
0x18004e2d9  mov     r14, [rsp+668h+var_600]
0x18004e2de  cmp     [rsp+668h+var_630], 0
0x18004e2e3  jl      loc_18004E419
0x18004e2e9  lea     rax, [rsp+668h+var_630]
0x18004e2ee  mov     [rsp+668h+var_640], rax; int *
0x18004e2f3  lea     rax, [rsp+668h+pidl]
0x18004e2f8  mov     qword ptr [rsp+668h+uFlags], rax; struct _ITEMIDLIST **
0x18004e2fd  xor     r9d, r9d; int
0x18004e300  mov     r8, qword ptr [rsp+668h+pvar+8]; unsigned __int16 *
0x18004e305  mov     rdx, [rsp+668h+var_620]; struct IPortableDevice *
0x18004e30a  mov     rcx, [rsp+668h+var_5D0]
0x18004e312  mov     rcx, [rcx]; this
0x18004e315  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x18004e31a  mov     rsi, [rsp+668h+pidl]
0x18004e31f  test    eax, eax
0x18004e321  js      loc_18004E41E
0x18004e327  mov     rdx, rsi; struct _ITEMIDLIST *
0x18004e32a  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18004e32f  test    rax, rax
0x18004e332  jz      loc_18004E402
0x18004e338  lea     r8, [rsp+668h+Buffer]; unsigned __int16 *
0x18004e340  mov     rdx, rax; struct CONTENTITEM *
0x18004e343  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x18004e348  mov     [rsp+668h+uFlags], 4011h; uFlags
0x18004e350  mov     r9d, 2B8h; cbFileInfo
0x18004e356  lea     r8, [rsp+668h+psfi]; psfi
0x18004e35e  xor     edx, edx; dwFileAttributes
0x18004e360  lea     rcx, [rsp+668h+Buffer]; pszPath
0x18004e368  call    cs:__imp_SHGetFileInfoW
0x18004e36e  lea     rcx, [rsp+668h+Buffer]; pszPath
0x18004e376  call    cs:__imp_PathRemoveExtensionW
0x18004e37c  xor     edx, edx; Val
0x18004e37e  lea     r8d, [rdx+58h]; Size
0x18004e382  lea     rcx, [rsp+668h+var_588]; void *
0x18004e38a  call    memset_0
0x18004e38f  mov     dword ptr [rsp+668h+var_588], 3
0x18004e39a  lea     rax, [rsp+668h+Buffer]
0x18004e3a2  mov     [rsp+668h+var_570], rax
0x18004e3aa  mov     [rsp+668h+var_568], 104h
0x18004e3b5  xor     r9d, r9d; lParam
0x18004e3b8  xor     r8d, r8d; wParam
0x18004e3bb  mov     edx, 1004h; Msg
0x18004e3c0  mov     rcx, r15; hWnd
0x18004e3c3  call    cs:__imp_SendMessageW
0x18004e3c9  mov     dword ptr [rsp+668h+var_588+4], eax
0x18004e3d0  mov     eax, [rsp+668h+psfi.iIcon]
0x18004e3d7  mov     [rsp+668h+var_564], eax
0x18004e3de  mov     [rsp+668h+var_580], 0
0x18004e3e9  lea     r9, [rsp+668h+var_588]; lParam
0x18004e3f1  xor     r8d, r8d; wParam
0x18004e3f4  mov     edx, 104Dh; Msg
0x18004e3f9  mov     rcx, r15; hWnd
0x18004e3fc  call    cs:__imp_SendMessageW
0x18004e402  test    rsi, rsi
0x18004e405  jz      short loc_18004E41E
0x18004e407  mov     rcx, rsi; pidl
0x18004e40a  call    cs:__imp_ILFree
0x18004e410  xor     esi, esi
0x18004e412  mov     [rsp+668h+pidl], rsi
0x18004e417  jmp     short loc_18004E41E
0x18004e419  mov     rsi, [rsp+668h+pidl]
0x18004e41e  lea     rcx, [rsp+668h+pvar]; pvar
0x18004e423  call    cs:__imp_PropVariantClear
0x18004e429  inc     ebx
0x18004e42b  jmp     loc_18004E271
```
