# CThemeManager2::_OpenTheme(HWND__ *,ushort const *)

- ea: `0x180056538`
- end: `0x180056706`
- name: `?_OpenTheme@CThemeManager2@@AEAAJPEAUHWND__@@PEBG@Z`
- size: `462`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, HWND, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800547c0`
- `0x180054ad0`

## callees

- `0x18001ed40`
- `0x18002f8c0`
- `0x180056538`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800565d7`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800565d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056681`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180056681`
- `USER32!OpenIcon` at `0x1800565fe`
- `USER32!OpenIcon` at `0x1800565fe`
- `USER32!FindWindowW` at `0x180056588`
- `USER32!FindWindowW` at `0x1800565ed`
- `USER32!FindWindowW` at `0x180056588`
- `USER32!FindWindowW` at `0x1800565ed`
- `USER32!SetForegroundWindow` at `0x180056607`
- `USER32!SetForegroundWindow` at `0x180056607`
- `USER32!SendMessageW` at `0x1800565a4`
- `USER32!SendMessageW` at `0x1800565a4`
- `USER32!IsWindow` at `0x1800565ad`
- `USER32!IsWindow` at `0x1800565ad`

## string_xrefs

- `0x1800565d0`: `@%WinDir%\system32\themecpl.dll,-1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeManager2::_OpenTheme(const WCHAR *this, HWND a2, const unsigned __int16 *a3)
{
  __int64 v5; // rax
  HWND WindowW; // rax
  HWND v7; // rbx
  HWND v8; // rax
  HWND v9; // rbx
  unsigned int v10; // ebx
  int v11; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  LPARAM lParam; // [rsp+30h] [rbp-20h] BYREF
  int v17; // [rsp+38h] [rbp-18h]
  int v18; // [rsp+3Ch] [rbp-14h]
  const unsigned __int16 *v19; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HWND v21; // [rsp+78h] [rbp+28h] BYREF
  LPVOID v22; // [rsp+80h] [rbp+30h] BYREF

  v21 = a2;
  v18 = 0;
  lParam = 0;
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  v17 = 2 * v5 + 2;
  v19 = a3;
  do
  {
    WindowW = FindWindowW(L"PersonalizationThemeChangeListener", 0);
    v7 = WindowW;
    if ( !WindowW )
    {
      v11 = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)this + 160LL))(
              this,
              0,
              a3,
              0);
      v10 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x466,
          (unsigned int)"shell\\themes\\themeui\\thememanager.cpp",
          (const char *)(unsigned int)v11,
          0);
        return v10;
      }
      v22 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      v12 = CoCreateInstance(
              &CLSID_ApplicationActivationManager,
              0,
              1u,
              &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
              &v22);
      v10 = v12;
      if ( v12 >= 0 )
      {
        LODWORD(v21) = 0;
        ppv = (LPVOID *)&v21;
        v12 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v22 + 24LL))(
                v22,
                L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                L"page=SettingsPageThemes",
                0);
        v10 = v12;
        if ( v12 >= 0 )
        {
          v10 = 0;
          goto LABEL_19;
        }
        v13 = 1131;
      }
      else
      {
        v13 = 1128;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\themes\\themeui\\thememanager.cpp",
        (const char *)(unsigned int)v12,
        (int)ppv);
LABEL_19:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      return v10;
    }
    SendMessageW(WindowW, 0x4Au, 0, (LPARAM)&lParam);
  }
  while ( !IsWindow(v7) );
  if ( this[786]
    || (SHLoadIndirectString(L"@%WinDir%\\system32\\themecpl.dll,-1", (PWSTR)this + 786, 0x104u, 0), this[786]) )
  {
    v8 = FindWindowW(L"CabinetWClass", this + 786);
    v9 = v8;
    if ( v8 )
    {
      OpenIcon(v8);
      SetForegroundWindow(v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180056538  mov     [rsp-18h+arg_0], rbx
0x18005653d  mov     [rsp-18h+arg_18], rsi
0x180056542  mov     [rsp-18h+arg_8], rdx
0x180056547  push    rbp
0x180056548  push    rdi
0x180056549  push    r14
0x18005654b  mov     rbp, rsp
0x18005654e  sub     rsp, 50h
0x180056552  mov     rsi, r8
0x180056555  mov     rdi, rcx
0x180056558  xor     r14d, r14d
0x18005655b  mov     [rbp+var_14], r14d
0x18005655f  mov     [rbp+lParam], r14
0x180056563  or      rax, 0FFFFFFFFFFFFFFFFh
0x180056567  inc     rax
0x18005656a  cmp     [r8+rax*2], r14w
0x18005656f  jnz     short loc_180056567
0x180056571  lea     eax, ds:2[rax*2]
0x180056578  mov     [rbp+var_18], eax
0x18005657b  mov     [rbp+var_10], rsi
0x18005657f  xor     edx, edx; lpWindowName
0x180056581  lea     rcx, aPersonalizatio_1; "PersonalizationThemeChangeListener"
0x180056588  call    cs:__imp_FindWindowW
0x18005658e  mov     rbx, rax
0x180056591  test    rax, rax
0x180056594  jz      short loc_180056615
0x180056596  lea     r9, [rbp+lParam]; lParam
0x18005659a  xor     r8d, r8d; wParam
0x18005659d  lea     edx, [r8+4Ah]; Msg
0x1800565a1  mov     rcx, rax; hWnd
0x1800565a4  call    cs:__imp_SendMessageW
0x1800565aa  mov     rcx, rbx; hWnd
0x1800565ad  call    cs:__imp_IsWindow
0x1800565b3  test    eax, eax
0x1800565b5  jz      short loc_18005657F
0x1800565b7  lea     rbx, [rdi+624h]
0x1800565be  cmp     [rbx], r14w
0x1800565c2  jnz     short loc_1800565E3
0x1800565c4  xor     r9d, r9d; ppvReserved
0x1800565c7  mov     r8d, 104h; cchOutBuf
0x1800565cd  mov     rdx, rbx; pszOutBuf
0x1800565d0  lea     rcx, pszSource; "@%WinDir%\\system32\\themecpl.dll,-1"
0x1800565d7  call    cs:__imp_SHLoadIndirectString
0x1800565dd  cmp     [rbx], r14w
0x1800565e1  jz      short loc_18005660D
0x1800565e3  mov     rdx, rbx; lpWindowName
0x1800565e6  lea     rcx, aCabinetwclass; "CabinetWClass"
0x1800565ed  call    cs:__imp_FindWindowW
0x1800565f3  mov     rbx, rax
0x1800565f6  test    rax, rax
0x1800565f9  jz      short loc_18005660D
0x1800565fb  mov     rcx, rax; hWnd
0x1800565fe  call    cs:__imp_OpenIcon
0x180056604  mov     rcx, rbx; hWnd
0x180056607  call    cs:__imp_SetForegroundWindow
0x18005660d  mov     ebx, r14d
0x180056610  jmp     loc_1800566EF
0x180056615  mov     rax, [rdi]
0x180056618  mov     dword ptr [rsp+50h+ppv], r14d; int
0x18005661d  xor     r9d, r9d
0x180056620  mov     r8, rsi
0x180056623  xor     edx, edx
0x180056625  mov     rcx, rdi
0x180056628  mov     rax, [rax+0A0h]
0x18005662f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056634  mov     ebx, eax
0x180056636  test    eax, eax
0x180056638  jns     short loc_180056657
0x18005663a  mov     rcx, [rbp+18h]; this
0x18005663e  mov     r9d, eax; char *
0x180056641  lea     r8, aShellThemesThe_6; "shell\\themes\\themeui\\thememanager.cp"...
0x180056648  mov     edx, 466h; void *
0x18005664d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056652  jmp     loc_1800566EF
0x180056657  mov     [rbp+arg_10], r14
0x18005665b  lea     rcx, [rbp+arg_10]
0x18005665f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180056664  lea     rax, [rbp+arg_10]
0x180056668  mov     [rsp+50h+ppv], rax; ppv
0x18005666d  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x180056674  xor     edx, edx; pUnkOuter
0x180056676  lea     r8d, [rdx+1]; dwClsContext
0x18005667a  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x180056681  call    cs:__imp_CoCreateInstance
0x180056687  mov     ebx, eax
0x180056689  test    eax, eax
0x18005668b  jns     short loc_180056694
0x18005668d  mov     edx, 468h
0x180056692  jmp     short loc_1800566CD
0x180056694  mov     dword ptr [rbp+arg_8], r14d
0x180056698  mov     rcx, [rbp+arg_10]
0x18005669c  mov     rax, [rcx]
0x18005669f  lea     rdx, [rbp+arg_8]
0x1800566a3  mov     [rsp+50h+ppv], rdx; int
0x1800566a8  xor     r9d, r9d
0x1800566ab  lea     r8, aPageSettingspa; "page=SettingsPageThemes"
0x1800566b2  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1800566b9  mov     rax, [rax+18h]
0x1800566bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566c2  mov     ebx, eax
0x1800566c4  test    eax, eax
0x1800566c6  jns     short loc_1800566E3
0x1800566c8  mov     edx, 46Bh; void *
0x1800566cd  mov     r9d, eax; char *
0x1800566d0  lea     r8, aShellThemesThe_6; "shell\\themes\\themeui\\thememanager.cp"...
0x1800566d7  mov     rcx, [rbp+18h]; this
0x1800566db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800566e0  nop
0x1800566e1  jmp     short loc_1800566E6
0x1800566e3  mov     ebx, r14d
0x1800566e6  lea     rcx, [rbp+arg_10]
0x1800566ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800566ef  mov     eax, ebx
0x1800566f1  lea     r11, [rsp+50h+var_s0]
0x1800566f6  mov     rbx, [r11+20h]
0x1800566fa  mov     rsi, [r11+38h]
0x1800566fe  mov     rsp, r11
0x180056701  pop     r14
0x180056703  pop     rdi
0x180056704  pop     rbp
0x180056705  retn
```
