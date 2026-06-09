# CWSHExtension::DoPropertySheetA(void)

- ea: `0x180006160`
- end: `0x18000642d`
- name: `?DoPropertySheetA@CWSHExtension@@EEAAJXZ`
- size: `717`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006160`
- `0x180007264`
- `0x18000ac84`
- `0x18000adfc`
- `0x18000d17e`
- `0x18000d1c0`

## import_xrefs

- `USER32!BringWindowToTop` at `0x180006217`
- `USER32!BringWindowToTop` at `0x180006217`
- `USER32!GetDesktopWindow` at `0x1800063c6`
- `USER32!GetDesktopWindow` at `0x1800063c6`
- `USER32!GetWindowLongPtrA` at `0x180006206`
- `USER32!GetWindowLongPtrA` at `0x180006206`
- `USER32!FindWindowA` at `0x1800061f0`
- `USER32!FindWindowA` at `0x1800061f0`
- `USER32!SetForegroundWindow` at `0x18000623f`
- `USER32!SetForegroundWindow` at `0x18000623f`
- `USER32!LoadStringA` at `0x1800061de`
- `USER32!LoadStringA` at `0x1800061de`
- `KERNEL32!GetLastError` at `0x180006221`
- `KERNEL32!GetLastError` at `0x180006221`
- `COMCTL32!PropertySheetA` at `0x1800063f2`
- `COMCTL32!PropertySheetA` at `0x1800063f2`

## pseudocode

```c
signed int __fastcall CWSHExtension::DoPropertySheetA(CWSHExtension *this)
{
  void *v1; // rsp
  HWND WindowA; // rax
  HKEY v3; // rdx
  HWND v4; // rbx
  signed int result; // eax
  __int64 v6; // rdx
  char *v7; // rcx
  __int64 v8; // r8
  _OWORD *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  int v19; // eax
  char *v20; // rcx
  _OWORD *v21; // rax
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  int v31; // eax
  HWND DesktopWindow; // rax
  INT_PTR v33; // rax
  int v34; // ecx
  CHAR Buffer[2016]; // [rsp+0h] [rbp-800h] BYREF
  PROPSHEETHEADERA_V2 v36; // [rsp+800h] [rbp+0h] BYREF
  _DWORD v37[2]; // [rsp+860h] [rbp+60h] BYREF
  HMODULE v38; // [rsp+868h] [rbp+68h]
  __int64 v39; // [rsp+870h] [rbp+70h]
  __int64 (__fastcall *v40)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+888h] [rbp+88h]
  _BYTE *v41; // [rsp+890h] [rbp+90h]
  _BYTE v42[560]; // [rsp+8D0h] [rbp+D0h] BYREF
  _BYTE v43[24]; // [rsp+B00h] [rbp+300h] BYREF
  __int64 v44; // [rsp+B18h] [rbp+318h]
  char v45; // [rsp+B31h] [rbp+331h]
  char v46; // [rsp+B32h] [rbp+332h]
  __int16 v47; // [rsp+B34h] [rbp+334h]
  __int16 v48; // [rsp+D3Ch] [rbp+53Ch]
  char v49; // [rsp+F44h] [rbp+744h] BYREF
  char v50; // [rsp+1168h] [rbp+968h] BYREF

  CSettings::CSettings((CSettings *)v42);
  memset_0(&v36, 0, sizeof(v36));
  CPspGeneral::CPspGeneral((CPspGeneral *)v43);
  v1 = alloca(2048);
  Buffer[LoadStringA(Global::g_hResource, Global::g_lResourceBase + 1, Buffer, 2048)] = 0;
  WindowA = FindWindowA(0, Buffer);
  v4 = WindowA;
  if ( WindowA && GetWindowLongPtrA(WindowA, -21) == 429392146 )
  {
    if ( BringWindowToTop(v4) && SetForegroundWindow(v4) )
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
    result = CSettings::LoadFromRegistry((CSettings *)v42, v3);
    if ( result >= 0 )
    {
      v6 = 4;
      v45 = 0;
      v7 = &v49;
      v8 = 4;
      v9 = v42;
      do
      {
        v10 = v9[1];
        *(_OWORD *)v7 = *v9;
        v11 = v9[2];
        *((_OWORD *)v7 + 1) = v10;
        v12 = v9[3];
        *((_OWORD *)v7 + 2) = v11;
        v13 = v9[4];
        *((_OWORD *)v7 + 3) = v12;
        v14 = v9[5];
        *((_OWORD *)v7 + 4) = v13;
        v15 = v9[6];
        *((_OWORD *)v7 + 5) = v14;
        v16 = v9[7];
        v9 += 8;
        *((_OWORD *)v7 + 6) = v15;
        *((_OWORD *)v7 + 7) = v16;
        v7 += 128;
        --v8;
      }
      while ( v8 );
      v17 = *v9;
      v18 = v9[1];
      v19 = *((_DWORD *)v9 + 8);
      *(_OWORD *)v7 = v17;
      *((_OWORD *)v7 + 1) = v18;
      *((_DWORD *)v7 + 8) = v19;
      v20 = &v50;
      v21 = v42;
      do
      {
        v22 = v21[1];
        *(_OWORD *)v20 = *v21;
        v23 = v21[2];
        *((_OWORD *)v20 + 1) = v22;
        v24 = v21[3];
        *((_OWORD *)v20 + 2) = v23;
        v25 = v21[4];
        *((_OWORD *)v20 + 3) = v24;
        v26 = v21[5];
        *((_OWORD *)v20 + 4) = v25;
        v27 = v21[6];
        *((_OWORD *)v20 + 5) = v26;
        v28 = v21[7];
        v21 += 8;
        *((_OWORD *)v20 + 6) = v27;
        *((_OWORD *)v20 + 7) = v28;
        v20 += 128;
        --v6;
      }
      while ( v6 );
      v29 = *v21;
      v37[0] = 104;
      v30 = v21[1];
      v31 = *((_DWORD *)v21 + 8);
      *(_OWORD *)v20 = v29;
      v36.dwSize = 96;
      *((_OWORD *)v20 + 1) = v30;
      *((_DWORD *)v20 + 8) = v31;
      v47 = 0;
      v48 = 0;
      v46 = 0;
      v38 = Global::g_hResource;
      v39 = v44;
      v37[1] = Global::g_isLanguageBiDi ? 0x10 : 0;
      v41 = v43;
      v40 = CPropertyPage::DialogProc;
      v36.dwFlags = Global::g_isLanguageBiDi ? 2056 : 8;
      DesktopWindow = GetDesktopWindow();
      v36.pszCaption = Buffer;
      v36.hwndParent = DesktopWindow;
      v36.hInstance = Global::g_hResource;
      v36.ppsp = (LPCPROPSHEETPAGEA)v37;
      v36.nPages = 1;
      v33 = PropertySheetA(&v36);
      v34 = 0;
      if ( v33 < 0 )
        return -2147467259;
      return v34;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006160  push    rbp
0x180006162  sub     rsp, 0DE0h
0x180006169  lea     rbp, [rsp+20h]
0x18000616e  mov     [rbp+0DC0h+arg_0], rbx
0x180006175  mov     [rbp+0DC0h+arg_8], rdi
0x18000617c  mov     rax, cs:__security_cookie
0x180006183  xor     rax, rbp
0x180006186  mov     [rbp+0DC0h+var_10], rax
0x18000618d  lea     rcx, [rbp+0DC0h+var_CF0]; this
0x180006194  call    ??0CSettings@@QEAA@XZ; CSettings::CSettings(void)
0x180006199  xor     edx, edx; Val
0x18000619b  lea     rcx, [rbp+0DC0h+var_DC0]; void *
0x18000619f  lea     r8d, [rdx+60h]; Size
0x1800061a3  call    memset_0
0x1800061a8  lea     rcx, [rbp+0DC0h+var_AC0]; this
0x1800061af  call    ??0CPspGeneral@@QEAA@XZ; CPspGeneral::CPspGeneral(void)
0x1800061b4  mov     eax, [rsp+0DE0h+var_DE0]
0x1800061b7  mov     eax, 800h
0x1800061bc  sub     rsp, rax
0x1800061bf  lea     rdi, [rsp+15E0h+Buffer]
0x1800061c4  mov     eax, [rdi]
0x1800061c6  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x1800061cc  mov     r9d, 800h; cchBufferMax
0x1800061d2  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1800061d9  inc     edx; uID
0x1800061db  mov     r8, rdi; lpBuffer
0x1800061de  call    cs:__imp_LoadStringA
0x1800061e4  movsxd  rcx, eax
0x1800061e7  mov     rdx, rdi; lpWindowName
0x1800061ea  mov     byte ptr [rcx+rdi], 0
0x1800061ee  xor     ecx, ecx; lpClassName
0x1800061f0  call    cs:__imp_FindWindowA
0x1800061f6  mov     rbx, rax
0x1800061f9  test    rax, rax
0x1800061fc  jz      short loc_180006250
0x1800061fe  mov     edx, 0FFFFFFEBh; nIndex
0x180006203  mov     rcx, rax; hWnd
0x180006206  call    cs:__imp_GetWindowLongPtrA
0x18000620c  cmp     rax, 19980112h
0x180006212  jnz     short loc_180006250
0x180006214  mov     rcx, rbx; hWnd
0x180006217  call    cs:__imp_BringWindowToTop
0x18000621d  test    eax, eax
0x18000621f  jnz     short loc_18000623C
0x180006221  call    cs:__imp_GetLastError
0x180006227  test    eax, eax
0x180006229  jle     loc_180006407
0x18000622f  movzx   eax, ax
0x180006232  or      eax, 80070000h
0x180006237  jmp     loc_180006407
0x18000623c  mov     rcx, rbx; hWnd
0x18000623f  call    cs:__imp_SetForegroundWindow
0x180006245  test    eax, eax
0x180006247  jz      short loc_180006221
0x180006249  xor     eax, eax
0x18000624b  jmp     loc_180006407
0x180006250  lea     rcx, [rbp+0DC0h+var_CF0]; this
0x180006257  call    ?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::LoadFromRegistry(HKEY__ *)
0x18000625c  test    eax, eax
0x18000625e  js      loc_180006407
0x180006264  mov     edx, 4
0x180006269  mov     [rbp+0DC0h+var_A8F], 0
0x180006270  lea     rcx, [rbp+0DC0h+var_67C]
0x180006277  mov     r8d, edx
0x18000627a  lea     rax, [rbp+0DC0h+var_CF0]
0x180006281  lea     r9d, [rdx+7Ch]
0x180006285  movups  xmm0, xmmword ptr [rax]
0x180006288  movups  xmm1, xmmword ptr [rax+10h]
0x18000628c  movups  xmmword ptr [rcx], xmm0
0x18000628f  movups  xmm0, xmmword ptr [rax+20h]
0x180006293  movups  xmmword ptr [rcx+10h], xmm1
0x180006297  movups  xmm1, xmmword ptr [rax+30h]
0x18000629b  movups  xmmword ptr [rcx+20h], xmm0
0x18000629f  movups  xmm0, xmmword ptr [rax+40h]
0x1800062a3  movups  xmmword ptr [rcx+30h], xmm1
0x1800062a7  movups  xmm1, xmmword ptr [rax+50h]
0x1800062ab  movups  xmmword ptr [rcx+40h], xmm0
0x1800062af  movups  xmm0, xmmword ptr [rax+60h]
0x1800062b3  movups  xmmword ptr [rcx+50h], xmm1
0x1800062b7  movups  xmm1, xmmword ptr [rax+70h]
0x1800062bb  add     rax, r9
0x1800062be  movups  xmmword ptr [rcx+60h], xmm0
0x1800062c2  movups  xmmword ptr [rcx+70h], xmm1
0x1800062c6  add     rcx, r9
0x1800062c9  sub     r8, 1
0x1800062cd  jnz     short loc_180006285
0x1800062cf  movups  xmm0, xmmword ptr [rax]
0x1800062d2  movups  xmm1, xmmword ptr [rax+10h]
0x1800062d6  mov     eax, [rax+20h]
0x1800062d9  movups  xmmword ptr [rcx], xmm0
0x1800062dc  movups  xmmword ptr [rcx+10h], xmm1
0x1800062e0  mov     [rcx+20h], eax
0x1800062e3  lea     rcx, [rbp+0DC0h+var_458]
0x1800062ea  lea     rax, [rbp+0DC0h+var_CF0]
0x1800062f1  movups  xmm0, xmmword ptr [rax]
0x1800062f4  movups  xmm1, xmmword ptr [rax+10h]
0x1800062f8  movups  xmmword ptr [rcx], xmm0
0x1800062fb  movups  xmm0, xmmword ptr [rax+20h]
0x1800062ff  movups  xmmword ptr [rcx+10h], xmm1
0x180006303  movups  xmm1, xmmword ptr [rax+30h]
0x180006307  movups  xmmword ptr [rcx+20h], xmm0
0x18000630b  movups  xmm0, xmmword ptr [rax+40h]
0x18000630f  movups  xmmword ptr [rcx+30h], xmm1
0x180006313  movups  xmm1, xmmword ptr [rax+50h]
0x180006317  movups  xmmword ptr [rcx+40h], xmm0
0x18000631b  movups  xmm0, xmmword ptr [rax+60h]
0x18000631f  movups  xmmword ptr [rcx+50h], xmm1
0x180006323  movups  xmm1, xmmword ptr [rax+70h]
0x180006327  add     rax, r9
0x18000632a  movups  xmmword ptr [rcx+60h], xmm0
0x18000632e  movups  xmmword ptr [rcx+70h], xmm1
0x180006332  add     rcx, r9
0x180006335  sub     rdx, 1
0x180006339  jnz     short loc_1800062F1
0x18000633b  movups  xmm0, xmmword ptr [rax]
0x18000633e  mov     [rbp+0DC0h+var_D60], 68h ; 'h'
0x180006345  movups  xmm1, xmmword ptr [rax+10h]
0x180006349  mov     eax, [rax+20h]
0x18000634c  movups  xmmword ptr [rcx], xmm0
0x18000634f  mov     [rbp+0DC0h+var_DC0.dwSize], 60h ; '`'
0x180006356  movups  xmmword ptr [rcx+10h], xmm1
0x18000635a  mov     [rcx+20h], eax
0x18000635d  xor     eax, eax
0x18000635f  mov     [rbp+0DC0h+var_A8C], ax
0x180006366  mov     [rbp+0DC0h+var_884], ax
0x18000636d  mov     [rbp+0DC0h+var_A8E], dl
0x180006373  mov     dl, cs:?g_isLanguageBiDi@Global@@2_NA; bool Global::g_isLanguageBiDi
0x180006379  mov     al, dl
0x18000637b  neg     al
0x18000637d  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x180006384  mov     [rbp+0DC0h+var_D58], rax
0x180006388  sbb     ecx, ecx
0x18000638a  mov     rax, [rbp+0DC0h+var_AA8]
0x180006391  and     ecx, 10h
0x180006394  mov     [rbp+0DC0h+var_D50], rax
0x180006398  neg     dl
0x18000639a  lea     rax, [rbp+0DC0h+var_AC0]
0x1800063a1  mov     [rbp+0DC0h+var_D5C], ecx
0x1800063a4  mov     [rbp+0DC0h+var_D30], rax
0x1800063ab  lea     rax, ?DialogProc@CPropertyPage@@KA_JPEAUHWND__@@I_K_J@Z; CPropertyPage::DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800063b2  mov     [rbp+0DC0h+var_D38], rax
0x1800063b9  sbb     eax, eax
0x1800063bb  and     eax, 800h
0x1800063c0  add     eax, 8
0x1800063c3  mov     [rbp+0DC0h+var_DC0.dwFlags], eax
0x1800063c6  call    cs:__imp_GetDesktopWindow
0x1800063cc  lea     rcx, [rbp+0DC0h+var_DC0]; LPCPROPSHEETHEADERA
0x1800063d0  mov     [rbp+0DC0h+var_DC0.pszCaption], rdi
0x1800063d4  mov     [rbp+0DC0h+var_DC0.hwndParent], rax
0x1800063d8  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x1800063df  mov     [rbp+0DC0h+var_DC0.hInstance], rax
0x1800063e3  lea     rax, [rbp+0DC0h+var_D60]
0x1800063e7  mov     qword ptr [rbp+0DC0h+var_DC0.38h], rax
0x1800063eb  mov     [rbp+0DC0h+var_DC0.nPages], 1
0x1800063f2  call    cs:__imp_PropertySheetA
0x1800063f8  xor     ecx, ecx
0x1800063fa  mov     edx, 80004005h
0x1800063ff  test    rax, rax
0x180006402  cmovs   ecx, edx
0x180006405  mov     eax, ecx
0x180006407  mov     rcx, [rbp+0DC0h+var_10]
0x18000640e  xor     rcx, rbp; StackCookie
0x180006411  call    __security_check_cookie
0x180006416  mov     rbx, [rbp+0DC0h+arg_0]
0x18000641d  mov     rdi, [rbp+0DC0h+arg_8]
0x180006424  lea     rsp, [rbp+0DC0h]
0x18000642b  pop     rbp
0x18000642c  retn
```
