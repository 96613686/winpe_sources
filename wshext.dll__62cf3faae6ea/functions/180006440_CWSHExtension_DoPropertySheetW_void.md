# CWSHExtension::DoPropertySheetW(void)

- ea: `0x180006440`
- end: `0x18000670f`
- name: `?DoPropertySheetW@CWSHExtension@@EEAAJXZ`
- size: `719`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006440`
- `0x180007264`
- `0x18000ac84`
- `0x18000adfc`
- `0x18000d17e`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `USER32!LoadStringW` at `0x1800064be`
- `USER32!LoadStringW` at `0x1800064be`
- `USER32!BringWindowToTop` at `0x1800064f9`
- `USER32!BringWindowToTop` at `0x1800064f9`
- `USER32!FindWindowW` at `0x1800064d2`
- `USER32!FindWindowW` at `0x1800064d2`
- `USER32!GetDesktopWindow` at `0x1800066a8`
- `USER32!GetDesktopWindow` at `0x1800066a8`
- `USER32!GetWindowLongPtrA` at `0x1800064e8`
- `USER32!GetWindowLongPtrA` at `0x1800064e8`
- `USER32!SetForegroundWindow` at `0x180006521`
- `USER32!SetForegroundWindow` at `0x180006521`
- `KERNEL32!GetLastError` at `0x180006503`
- `KERNEL32!GetLastError` at `0x180006503`
- `COMCTL32!PropertySheetW` at `0x1800066d4`
- `COMCTL32!PropertySheetW` at `0x1800066d4`

## pseudocode

```c
signed int __fastcall CWSHExtension::DoPropertySheetW(CWSHExtension *this)
{
  void *v1; // rsp
  void *v2; // rsp
  HWND WindowW; // rax
  HKEY v4; // rdx
  HWND v5; // rbx
  signed int result; // eax
  __int64 v7; // rdx
  char *v8; // rcx
  __int64 v9; // r8
  _OWORD *v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  int v20; // eax
  char *v21; // rcx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  int v32; // eax
  HWND DesktopWindow; // rax
  INT_PTR v34; // rax
  int v35; // ecx
  WCHAR Buffer[2048]; // [rsp+0h] [rbp-1000h] BYREF
  PROPSHEETHEADERW_V2 v37; // [rsp+1000h] [rbp+0h] BYREF
  _DWORD v38[2]; // [rsp+1060h] [rbp+60h] BYREF
  HMODULE v39; // [rsp+1068h] [rbp+68h]
  __int64 v40; // [rsp+1070h] [rbp+70h]
  __int64 (__fastcall *v41)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+1088h] [rbp+88h]
  _BYTE *v42; // [rsp+1090h] [rbp+90h]
  _BYTE v43[560]; // [rsp+10D0h] [rbp+D0h] BYREF
  _BYTE v44[32]; // [rsp+1300h] [rbp+300h] BYREF
  __int64 v45; // [rsp+1320h] [rbp+320h]
  char v46; // [rsp+1331h] [rbp+331h]
  char v47; // [rsp+1332h] [rbp+332h]
  __int16 v48; // [rsp+1334h] [rbp+334h]
  __int16 v49; // [rsp+153Ch] [rbp+53Ch]
  char v50; // [rsp+1744h] [rbp+744h] BYREF
  char v51; // [rsp+1968h] [rbp+968h] BYREF

  CSettings::CSettings((CSettings *)v43);
  memset_0(&v37, 0, sizeof(v37));
  CPspGeneral::CPspGeneral((CPspGeneral *)v44);
  v1 = alloca(4096);
  v2 = alloca(4096);
  Buffer[LoadStringW(Global::g_hResource, Global::g_lResourceBase + 1, Buffer, 2048)] = 0;
  WindowW = FindWindowW(0, Buffer);
  v5 = WindowW;
  if ( WindowW && GetWindowLongPtrA(WindowW, -21) == 429392146 )
  {
    if ( BringWindowToTop(v5) && SetForegroundWindow(v5) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    result = CSettings::LoadFromRegistry((CSettings *)v43, v4);
    if ( result >= 0 )
    {
      v7 = 4;
      v46 = 0;
      v8 = &v50;
      v9 = 4;
      v10 = v43;
      do
      {
        v11 = v10[1];
        *(_OWORD *)v8 = *v10;
        v12 = v10[2];
        *((_OWORD *)v8 + 1) = v11;
        v13 = v10[3];
        *((_OWORD *)v8 + 2) = v12;
        v14 = v10[4];
        *((_OWORD *)v8 + 3) = v13;
        v15 = v10[5];
        *((_OWORD *)v8 + 4) = v14;
        v16 = v10[6];
        *((_OWORD *)v8 + 5) = v15;
        v17 = v10[7];
        v10 += 8;
        *((_OWORD *)v8 + 6) = v16;
        *((_OWORD *)v8 + 7) = v17;
        v8 += 128;
        --v9;
      }
      while ( v9 );
      v18 = *v10;
      v19 = v10[1];
      v20 = *((_DWORD *)v10 + 8);
      *(_OWORD *)v8 = v18;
      *((_OWORD *)v8 + 1) = v19;
      *((_DWORD *)v8 + 8) = v20;
      v21 = &v51;
      v22 = v43;
      do
      {
        v23 = v22[1];
        *(_OWORD *)v21 = *v22;
        v24 = v22[2];
        *((_OWORD *)v21 + 1) = v23;
        v25 = v22[3];
        *((_OWORD *)v21 + 2) = v24;
        v26 = v22[4];
        *((_OWORD *)v21 + 3) = v25;
        v27 = v22[5];
        *((_OWORD *)v21 + 4) = v26;
        v28 = v22[6];
        *((_OWORD *)v21 + 5) = v27;
        v29 = v22[7];
        v22 += 8;
        *((_OWORD *)v21 + 6) = v28;
        *((_OWORD *)v21 + 7) = v29;
        v21 += 128;
        --v7;
      }
      while ( v7 );
      v30 = *v22;
      v38[0] = 104;
      v31 = v22[1];
      v32 = *((_DWORD *)v22 + 8);
      *(_OWORD *)v21 = v30;
      v37.dwSize = 96;
      *((_OWORD *)v21 + 1) = v31;
      *((_DWORD *)v21 + 8) = v32;
      v48 = 0;
      v49 = 0;
      v47 = 0;
      v39 = Global::g_hResource;
      v40 = v45;
      v38[1] = Global::g_isLanguageBiDi ? 0x10 : 0;
      v42 = v44;
      v41 = CPropertyPage::DialogProc;
      v37.dwFlags = Global::g_isLanguageBiDi ? 2056 : 8;
      DesktopWindow = GetDesktopWindow();
      v37.pszCaption = Buffer;
      v37.hwndParent = DesktopWindow;
      v37.hInstance = Global::g_hResource;
      v37.ppsp = (LPCPROPSHEETPAGEW)v38;
      v37.nPages = 1;
      v34 = PropertySheetW(&v37);
      v35 = 0;
      if ( v34 < 0 )
        return -2147467259;
      return v35;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006440  push    rbp
0x180006442  sub     rsp, 0DE0h
0x180006449  lea     rbp, [rsp+20h]
0x18000644e  mov     [rbp+0DC0h+arg_0], rbx
0x180006455  mov     [rbp+0DC0h+arg_8], rdi
0x18000645c  mov     rax, cs:__security_cookie
0x180006463  xor     rax, rbp
0x180006466  mov     [rbp+0DC0h+var_10], rax
0x18000646d  lea     rcx, [rbp+0DC0h+var_CF0]; this
0x180006474  call    ??0CSettings@@QEAA@XZ; CSettings::CSettings(void)
0x180006479  xor     edx, edx; Val
0x18000647b  lea     rcx, [rbp+0DC0h+var_DC0]; void *
0x18000647f  lea     r8d, [rdx+60h]; Size
0x180006483  call    memset_0
0x180006488  lea     rcx, [rbp+0DC0h+var_AC0]; this
0x18000648f  call    ??0CPspGeneral@@QEAA@XZ; CPspGeneral::CPspGeneral(void)
0x180006494  mov     eax, 1000h
0x180006499  call    _alloca_probe
0x18000649e  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x1800064a4  sub     rsp, rax
0x1800064a7  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1800064ae  inc     edx; uID
0x1800064b0  mov     r9d, 800h; cchBufferMax
0x1800064b6  lea     rdi, [rsp+1DE0h+Buffer]
0x1800064bb  mov     r8, rdi; lpBuffer
0x1800064be  call    cs:__imp_LoadStringW
0x1800064c4  movsxd  rcx, eax
0x1800064c7  mov     rdx, rdi; lpWindowName
0x1800064ca  xor     eax, eax
0x1800064cc  mov     [rdi+rcx*2], ax
0x1800064d0  xor     ecx, ecx; lpClassName
0x1800064d2  call    cs:__imp_FindWindowW
0x1800064d8  mov     rbx, rax
0x1800064db  test    rax, rax
0x1800064de  jz      short loc_180006532
0x1800064e0  mov     edx, 0FFFFFFEBh; nIndex
0x1800064e5  mov     rcx, rax; hWnd
0x1800064e8  call    cs:__imp_GetWindowLongPtrA
0x1800064ee  cmp     rax, 19980112h
0x1800064f4  jnz     short loc_180006532
0x1800064f6  mov     rcx, rbx; hWnd
0x1800064f9  call    cs:__imp_BringWindowToTop
0x1800064ff  test    eax, eax
0x180006501  jnz     short loc_18000651E
0x180006503  call    cs:__imp_GetLastError
0x180006509  test    eax, eax
0x18000650b  jle     loc_1800066E9
0x180006511  movzx   eax, ax
0x180006514  or      eax, 80070000h
0x180006519  jmp     loc_1800066E9
0x18000651e  mov     rcx, rbx; hWnd
0x180006521  call    cs:__imp_SetForegroundWindow
0x180006527  test    eax, eax
0x180006529  jz      short loc_180006503
0x18000652b  xor     eax, eax
0x18000652d  jmp     loc_1800066E9
0x180006532  lea     rcx, [rbp+0DC0h+var_CF0]; this
0x180006539  call    ?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::LoadFromRegistry(HKEY__ *)
0x18000653e  test    eax, eax
0x180006540  js      loc_1800066E9
0x180006546  mov     edx, 4
0x18000654b  mov     [rbp+0DC0h+var_A8F], 0
0x180006552  lea     rcx, [rbp+0DC0h+var_67C]
0x180006559  mov     r8d, edx
0x18000655c  lea     rax, [rbp+0DC0h+var_CF0]
0x180006563  lea     r9d, [rdx+7Ch]
0x180006567  movups  xmm0, xmmword ptr [rax]
0x18000656a  movups  xmm1, xmmword ptr [rax+10h]
0x18000656e  movups  xmmword ptr [rcx], xmm0
0x180006571  movups  xmm0, xmmword ptr [rax+20h]
0x180006575  movups  xmmword ptr [rcx+10h], xmm1
0x180006579  movups  xmm1, xmmword ptr [rax+30h]
0x18000657d  movups  xmmword ptr [rcx+20h], xmm0
0x180006581  movups  xmm0, xmmword ptr [rax+40h]
0x180006585  movups  xmmword ptr [rcx+30h], xmm1
0x180006589  movups  xmm1, xmmword ptr [rax+50h]
0x18000658d  movups  xmmword ptr [rcx+40h], xmm0
0x180006591  movups  xmm0, xmmword ptr [rax+60h]
0x180006595  movups  xmmword ptr [rcx+50h], xmm1
0x180006599  movups  xmm1, xmmword ptr [rax+70h]
0x18000659d  add     rax, r9
0x1800065a0  movups  xmmword ptr [rcx+60h], xmm0
0x1800065a4  movups  xmmword ptr [rcx+70h], xmm1
0x1800065a8  add     rcx, r9
0x1800065ab  sub     r8, 1
0x1800065af  jnz     short loc_180006567
0x1800065b1  movups  xmm0, xmmword ptr [rax]
0x1800065b4  movups  xmm1, xmmword ptr [rax+10h]
0x1800065b8  mov     eax, [rax+20h]
0x1800065bb  movups  xmmword ptr [rcx], xmm0
0x1800065be  movups  xmmword ptr [rcx+10h], xmm1
0x1800065c2  mov     [rcx+20h], eax
0x1800065c5  lea     rcx, [rbp+0DC0h+var_458]
0x1800065cc  lea     rax, [rbp+0DC0h+var_CF0]
0x1800065d3  movups  xmm0, xmmword ptr [rax]
0x1800065d6  movups  xmm1, xmmword ptr [rax+10h]
0x1800065da  movups  xmmword ptr [rcx], xmm0
0x1800065dd  movups  xmm0, xmmword ptr [rax+20h]
0x1800065e1  movups  xmmword ptr [rcx+10h], xmm1
0x1800065e5  movups  xmm1, xmmword ptr [rax+30h]
0x1800065e9  movups  xmmword ptr [rcx+20h], xmm0
0x1800065ed  movups  xmm0, xmmword ptr [rax+40h]
0x1800065f1  movups  xmmword ptr [rcx+30h], xmm1
0x1800065f5  movups  xmm1, xmmword ptr [rax+50h]
0x1800065f9  movups  xmmword ptr [rcx+40h], xmm0
0x1800065fd  movups  xmm0, xmmword ptr [rax+60h]
0x180006601  movups  xmmword ptr [rcx+50h], xmm1
0x180006605  movups  xmm1, xmmword ptr [rax+70h]
0x180006609  add     rax, r9
0x18000660c  movups  xmmword ptr [rcx+60h], xmm0
0x180006610  movups  xmmword ptr [rcx+70h], xmm1
0x180006614  add     rcx, r9
0x180006617  sub     rdx, 1
0x18000661b  jnz     short loc_1800065D3
0x18000661d  movups  xmm0, xmmword ptr [rax]
0x180006620  mov     [rbp+0DC0h+var_D60], 68h ; 'h'
0x180006627  movups  xmm1, xmmword ptr [rax+10h]
0x18000662b  mov     eax, [rax+20h]
0x18000662e  movups  xmmword ptr [rcx], xmm0
0x180006631  mov     [rbp+0DC0h+var_DC0.dwSize], 60h ; '`'
0x180006638  movups  xmmword ptr [rcx+10h], xmm1
0x18000663c  mov     [rcx+20h], eax
0x18000663f  xor     eax, eax
0x180006641  mov     [rbp+0DC0h+var_A8C], ax
0x180006648  mov     [rbp+0DC0h+var_884], ax
0x18000664f  mov     [rbp+0DC0h+var_A8E], dl
0x180006655  mov     dl, cs:?g_isLanguageBiDi@Global@@2_NA; bool Global::g_isLanguageBiDi
0x18000665b  mov     al, dl
0x18000665d  neg     al
0x18000665f  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x180006666  mov     [rbp+0DC0h+var_D58], rax
0x18000666a  sbb     ecx, ecx
0x18000666c  mov     rax, [rbp+0DC0h+var_AA0]
0x180006673  and     ecx, 10h
0x180006676  mov     [rbp+0DC0h+var_D50], rax
0x18000667a  neg     dl
0x18000667c  lea     rax, [rbp+0DC0h+var_AC0]
0x180006683  mov     [rbp+0DC0h+var_D5C], ecx
0x180006686  mov     [rbp+0DC0h+var_D30], rax
0x18000668d  lea     rax, ?DialogProc@CPropertyPage@@KA_JPEAUHWND__@@I_K_J@Z; CPropertyPage::DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x180006694  mov     [rbp+0DC0h+var_D38], rax
0x18000669b  sbb     eax, eax
0x18000669d  and     eax, 800h
0x1800066a2  add     eax, 8
0x1800066a5  mov     [rbp+0DC0h+var_DC0.dwFlags], eax
0x1800066a8  call    cs:__imp_GetDesktopWindow
0x1800066ae  lea     rcx, [rbp+0DC0h+var_DC0]; LPCPROPSHEETHEADERW
0x1800066b2  mov     [rbp+0DC0h+var_DC0.pszCaption], rdi
0x1800066b6  mov     [rbp+0DC0h+var_DC0.hwndParent], rax
0x1800066ba  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x1800066c1  mov     [rbp+0DC0h+var_DC0.hInstance], rax
0x1800066c5  lea     rax, [rbp+0DC0h+var_D60]
0x1800066c9  mov     qword ptr [rbp+0DC0h+var_DC0.38h], rax
0x1800066cd  mov     [rbp+0DC0h+var_DC0.nPages], 1
0x1800066d4  call    cs:__imp_PropertySheetW
0x1800066da  xor     ecx, ecx
0x1800066dc  mov     edx, 80004005h
0x1800066e1  test    rax, rax
0x1800066e4  cmovs   ecx, edx
0x1800066e7  mov     eax, ecx
0x1800066e9  mov     rcx, [rbp+0DC0h+var_10]
0x1800066f0  xor     rcx, rbp; StackCookie
0x1800066f3  call    __security_check_cookie
0x1800066f8  mov     rbx, [rbp+0DC0h+arg_0]
0x1800066ff  mov     rdi, [rbp+0DC0h+arg_8]
0x180006706  lea     rsp, [rbp+0DC0h]
0x18000670d  pop     rbp
0x18000670e  retn
```
