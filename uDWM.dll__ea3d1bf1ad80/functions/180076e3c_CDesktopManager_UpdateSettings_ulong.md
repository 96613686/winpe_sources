# CDesktopManager::UpdateSettings(ulong *)

- ea: `0x180076e3c`
- end: `0x18007714c`
- name: `?UpdateSettings@CDesktopManager@@QEAAJPEAK@Z`
- size: `784`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x180019f64`
- `0x18006e044`

## callees

- `0x18001f43c`
- `0x180020fb4`
- `0x1800391d4`
- `0x18004ebcc`
- `0x18004f070`
- `0x180059fec`
- `0x18005dd90`
- `0x18006083c`
- `0x18006aa3c`
- `0x18006b804`
- `0x18006be8c`
- `0x18006e978`
- `0x18006f0c8`
- `0x180076e3c`
- `0x180077154`
- `0x18008b2c4`
- `0x180095130`
- `0x180095b4c`
- `0x1800afdd8`

## import_xrefs

- `USER32!MonitorFromWindow` at `0x180076f90`
- `USER32!MonitorFromWindow` at `0x180076f90`
- `USER32!GetSystemMetrics` at `0x180076f4a`
- `USER32!GetSystemMetrics` at `0x180076f5b`
- `USER32!GetSystemMetrics` at `0x180076f6c`
- `USER32!GetSystemMetrics` at `0x180076f7d`
- `USER32!GetSystemMetrics` at `0x180076f4a`
- `USER32!GetSystemMetrics` at `0x180076f5b`
- `USER32!GetSystemMetrics` at `0x180076f6c`
- `USER32!GetSystemMetrics` at `0x180076f7d`
- `USER32!SystemParametersInfoW` at `0x180076efc`
- `USER32!SystemParametersInfoW` at `0x1800770de`
- `USER32!SystemParametersInfoW` at `0x180076efc`
- `USER32!SystemParametersInfoW` at `0x1800770de`
- `USER32!GetMonitorInfoW` at `0x180076fba`
- `USER32!GetMonitorInfoW` at `0x180076fba`

## pseudocode

```c
__int64 __fastcall CDesktopManager::UpdateSettings(CDesktopManager *this, unsigned int *a2)
{
  unsigned int v2; // ebx
  int Theme; // esi
  int v6; // eax
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  HMONITOR v12; // rax
  CDesktopManager *v13; // rdx
  int v14; // ecx
  int v15; // ecx
  int SystemMetrics; // eax
  CAccent *v17; // rcx
  char v18; // r14
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  struct tagMONITORINFO mi; // [rsp+38h] [rbp-C8h] BYREF
  int pvParam; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[20]; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v24; // [rsp+78h] [rbp-88h]
  __int128 v25; // [rsp+88h] [rbp-78h]
  __int128 v26; // [rsp+98h] [rbp-68h]
  __int128 v27; // [rsp+A8h] [rbp-58h]
  _OWORD v28[26]; // [rsp+B8h] [rbp-48h]

  v2 = *a2;
  Theme = 0;
  if ( (*a2 & 0x40D) != 0 )
    ColorCache::InvalidateColors();
  if ( (v2 & 0x10) != 0 && !CDesktopManager::LoadAccentColorSettings(this) )
    v2 &= ~0x10u;
  if ( (v2 & 0x20) != 0 )
  {
    v6 = CDesktopManager::ModeChange(this);
    Theme = v6;
    if ( v6 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, 0xC3Bu, 0);
      goto LABEL_35;
    }
  }
  if ( (v2 & 1) != 0 )
  {
    memset_0(v23, 0, 0x1F4u);
    pvParam = 504;
    SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0);
    v7 = v25;
    *((_OWORD *)this + 18) = v24;
    v8 = v26;
    *((_OWORD *)this + 19) = v7;
    v9 = v27;
    *((_OWORD *)this + 20) = v8;
    v10 = v28[0];
    *((_OWORD *)this + 21) = v9;
    v11 = *(_OWORD *)((char *)v28 + 12);
    *((_OWORD *)this + 22) = v10;
    *(_OWORD *)((char *)this + 364) = v11;
    *((_DWORD *)this + 95) = GetSystemMetrics(76);
    *((_DWORD *)this + 96) = GetSystemMetrics(77);
    *((_DWORD *)this + 97) = GetSystemMetrics(78);
    *((_DWORD *)this + 98) = GetSystemMetrics(79);
    v12 = MonitorFromWindow(0, 1u);
    memset(&mi, 0, sizeof(mi));
    mi.cbSize = 40;
    if ( GetMonitorInfoW(v12, &mi) )
    {
      *(RECT *)((char *)this + 396) = mi.rcMonitor;
    }
    else
    {
      v13 = CDesktopManager::s_pDesktopManagerInstance;
      v14 = *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 95);
      *((_DWORD *)this + 99) = v14;
      *((_DWORD *)this + 101) = *((_DWORD *)v13 + 97) + v14;
      v15 = *((_DWORD *)v13 + 96);
      *((_DWORD *)this + 100) = v15;
      *((_DWORD *)this + 102) = *((_DWORD *)v13 + 98) + v15;
    }
    SystemMetrics = CTopLevelWindow::ReadSystemMetrics();
    Theme = SystemMetrics;
    if ( SystemMetrics < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, SystemMetrics, 0xC5Au, 0);
      goto LABEL_35;
    }
    v17 = (CAccent *)*((_QWORD *)this + 25);
    if ( v17 )
      CAccent::UpdateLayout(v17, 0);
  }
  v18 = 0;
  if ( (v2 & 0x800) != 0 )
  {
    if ( (v2 & 4) == 0 )
    {
      CDesktopManager::InitializeHighContrast(this);
      goto LABEL_21;
    }
  }
  else if ( (v2 & 4) == 0 )
  {
    goto LABEL_21;
  }
  CDesktopManager::UnloadTheme(this);
  Theme = CDesktopManager::LoadTheme(this);
  if ( Theme < 0 )
    goto LABEL_35;
  v18 = 1;
LABEL_21:
  if ( (v2 & 0x400) != 0 || v18 )
  {
    CDesktopManager::SetupColorization(this);
    CWindowList::UpdateIsLightTheme(*((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53));
  }
  if ( (v2 & 0x808) != 0 )
    CTopLevelWindow::ReadSystemColors();
  if ( (v2 & 0x40) != 0 )
    CDesktopManager::UpdateWindowShadows(this);
  if ( (v2 & 0x80u) != 0 )
    CDesktopManager::SetupDPIValues(this);
  if ( (v2 & 0x100) != 0 )
    CContactManager::RefreshPresentationModeSettings(*((CContactManager **)this + 20));
  if ( (v2 & 0x200) != 0 )
  {
    v20 = 8;
    if ( SystemParametersInfoW(0x48u, 8u, &v20, 0) )
      CDesktopManager::SetWindowAnimation(HIDWORD(v20) != 0);
  }
LABEL_35:
  *a2 = v2;
  return (unsigned int)Theme;
}

```

## disassembly

```asm
0x180076e3c  mov     [rsp-8+arg_10], rbx
0x180076e41  push    rbp
0x180076e42  push    rsi
0x180076e43  push    rdi
0x180076e44  push    r14
0x180076e46  push    r15
0x180076e48  lea     rbp, [rsp-170h]
0x180076e50  sub     rsp, 270h
0x180076e57  mov     rax, cs:__security_cookie
0x180076e5e  xor     rax, rsp
0x180076e61  mov     [rbp+190h+var_30], rax
0x180076e68  mov     ebx, [rdx]
0x180076e6a  xor     esi, esi
0x180076e6c  mov     r15, rdx
0x180076e6f  mov     rdi, rcx
0x180076e72  test    ebx, 40Dh
0x180076e78  jz      short loc_180076E7F
0x180076e7a  call    ?InvalidateColors@ColorCache@@SAXXZ; ColorCache::InvalidateColors(void)
0x180076e7f  test    bl, 10h
0x180076e82  jz      short loc_180076E93
0x180076e84  mov     rcx, rdi; this
0x180076e87  call    ?LoadAccentColorSettings@CDesktopManager@@QEAA_NXZ; CDesktopManager::LoadAccentColorSettings(void)
0x180076e8c  test    al, al
0x180076e8e  jnz     short loc_180076E93
0x180076e90  and     ebx, 0FFFFFFEFh
0x180076e93  test    bl, 20h
0x180076e96  jz      short loc_180076ECC
0x180076e98  mov     rcx, rdi; this
0x180076e9b  call    ?ModeChange@CDesktopManager@@QEAAJXZ; CDesktopManager::ModeChange(void)
0x180076ea0  mov     esi, eax
0x180076ea2  test    eax, eax
0x180076ea4  jns     short loc_180076ECC
0x180076ea6  mov     [rsp+290h+var_268], 0; void *
0x180076eaf  mov     [rsp+290h+var_270], 0C3Bh; unsigned int
0x180076eb7  xor     edx, edx; int *
0x180076eb9  mov     r9d, eax; int
0x180076ebc  xor     r8d, r8d; unsigned int
0x180076ebf  lea     ecx, [rdx+14h]; unsigned int
0x180076ec2  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180076ec7  jmp     loc_1800770F5
0x180076ecc  test    bl, 1
0x180076ecf  jz      loc_18007702C
0x180076ed5  xor     edx, edx; Val
0x180076ed7  lea     rcx, [rsp+290h+var_22C]; void *
0x180076edc  mov     r8d, 1F4h; Size
0x180076ee2  call    memset_0
0x180076ee7  xor     r9d, r9d; fWinIni
0x180076eea  lea     r8, [rsp+290h+pvParam]; pvParam
0x180076eef  mov     edx, 1F8h; uiParam
0x180076ef4  mov     [rsp+290h+pvParam], edx
0x180076ef8  lea     ecx, [r9+29h]; uiAction
0x180076efc  call    cs:__imp_SystemParametersInfoW
0x180076f02  movups  xmm0, [rsp+290h+var_218]
0x180076f07  mov     ecx, 4Ch ; 'L'; nIndex
0x180076f0c  movups  xmm1, [rbp+190h+var_208]
0x180076f10  movups  xmmword ptr [rdi+120h], xmm0
0x180076f17  movups  xmm0, [rbp+190h+var_1F8]
0x180076f1b  movups  xmmword ptr [rdi+130h], xmm1
0x180076f22  movups  xmm1, [rbp+190h+var_1E8]
0x180076f26  movups  xmmword ptr [rdi+140h], xmm0
0x180076f2d  movups  xmm0, [rbp+190h+var_1D8]
0x180076f31  movups  xmmword ptr [rdi+150h], xmm1
0x180076f38  movups  xmm1, [rbp+190h+var_1D8+0Ch]
0x180076f3c  movups  xmmword ptr [rdi+160h], xmm0
0x180076f43  movups  xmmword ptr [rdi+16Ch], xmm1
0x180076f4a  call    cs:__imp_GetSystemMetrics
0x180076f50  mov     ecx, 4Dh ; 'M'; nIndex
0x180076f55  mov     [rdi+17Ch], eax
0x180076f5b  call    cs:__imp_GetSystemMetrics
0x180076f61  mov     ecx, 4Eh ; 'N'; nIndex
0x180076f66  mov     [rdi+180h], eax
0x180076f6c  call    cs:__imp_GetSystemMetrics
0x180076f72  mov     ecx, 4Fh ; 'O'; nIndex
0x180076f77  mov     [rdi+184h], eax
0x180076f7d  call    cs:__imp_GetSystemMetrics
0x180076f83  mov     edx, 1; dwFlags
0x180076f88  xor     ecx, ecx; hwnd
0x180076f8a  mov     [rdi+188h], eax
0x180076f90  call    cs:__imp_MonitorFromWindow
0x180076f96  xor     ecx, ecx
0x180076f98  lea     rdx, [rsp+290h+mi]; lpmi
0x180076f9d  xorps   xmm0, xmm0
0x180076fa0  mov     qword ptr [rsp+290h+mi.rcWork.bottom], rcx
0x180076fa5  movups  xmmword ptr [rsp+290h+mi.cbSize], xmm0
0x180076faa  mov     rcx, rax; hMonitor
0x180076fad  mov     [rsp+290h+mi.cbSize], 28h ; '('
0x180076fb5  movups  xmmword ptr [rsp+290h+mi.rcMonitor.bottom], xmm0
0x180076fba  call    cs:__imp_GetMonitorInfoW
0x180076fc0  test    eax, eax
0x180076fc2  jz      short loc_180076FD3
0x180076fc4  movups  xmm0, xmmword ptr [rsp+290h+mi.rcMonitor.left]
0x180076fc9  movdqu  xmmword ptr [rdi+18Ch], xmm0
0x180076fd1  jmp     short loc_18007700A
0x180076fd3  mov     rdx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180076fda  mov     ecx, [rdx+17Ch]
0x180076fe0  mov     [rdi+18Ch], ecx
0x180076fe6  add     ecx, [rdx+184h]
0x180076fec  mov     [rdi+194h], ecx
0x180076ff2  mov     ecx, [rdx+180h]
0x180076ff8  mov     [rdi+190h], ecx
0x180076ffe  add     ecx, [rdx+188h]
0x180077004  mov     [rdi+198h], ecx
0x18007700a  call    ?ReadSystemMetrics@CTopLevelWindow@@SAJXZ; CTopLevelWindow::ReadSystemMetrics(void)
0x18007700f  mov     esi, eax
0x180077011  test    eax, eax
0x180077013  js      loc_180077120
0x180077019  mov     rcx, [rdi+0C8h]; this
0x180077020  test    rcx, rcx
0x180077023  jz      short loc_18007702C
0x180077025  xor     edx, edx; bool
0x180077027  call    ?UpdateLayout@CAccent@@UEAAJ_N@Z; CAccent::UpdateLayout(bool)
0x18007702c  xor     r14b, r14b
0x18007702f  bt      ebx, 0Bh
0x180077033  jb      loc_180077136
0x180077039  mov     eax, ebx
0x18007703b  and     eax, 4
0x18007703e  jz      short loc_18007705D
0x180077040  mov     rcx, rdi; this
0x180077043  call    ?UnloadTheme@CDesktopManager@@AEAAXXZ; CDesktopManager::UnloadTheme(void)
0x180077048  mov     rcx, rdi; this
0x18007704b  call    ?LoadTheme@CDesktopManager@@AEAAJXZ; CDesktopManager::LoadTheme(void)
0x180077050  mov     esi, eax
0x180077052  test    eax, eax
0x180077054  js      loc_1800770F5
0x18007705a  mov     r14b, 1
0x18007705d  bt      ebx, 0Ah
0x180077061  jb      short loc_180077068
0x180077063  test    r14b, r14b
0x180077066  jz      short loc_180077083
0x180077068  mov     rcx, rdi; this
0x18007706b  call    ?SetupColorization@CDesktopManager@@AEAAXXZ; CDesktopManager::SetupColorization(void)
0x180077070  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180077077  mov     rcx, [rcx+1A8h]; this
0x18007707e  call    ?UpdateIsLightTheme@CWindowList@@QEAAXXZ; CWindowList::UpdateIsLightTheme(void)
0x180077083  test    ebx, 808h
0x180077089  jz      short loc_180077090
0x18007708b  call    ?ReadSystemColors@CTopLevelWindow@@SAXXZ; CTopLevelWindow::ReadSystemColors(void)
0x180077090  test    bl, 40h
0x180077093  jz      short loc_18007709D
0x180077095  mov     rcx, rdi; this
0x180077098  call    ?UpdateWindowShadows@CDesktopManager@@QEAAXXZ; CDesktopManager::UpdateWindowShadows(void)
0x18007709d  test    bl, bl
0x18007709f  jns     short loc_1800770A9
0x1800770a1  mov     rcx, rdi; this
0x1800770a4  call    ?SetupDPIValues@CDesktopManager@@QEAAXXZ; CDesktopManager::SetupDPIValues(void)
0x1800770a9  bt      ebx, 8
0x1800770ad  jnb     short loc_1800770BB
0x1800770af  mov     rcx, [rdi+0A0h]; this
0x1800770b6  call    ?RefreshPresentationModeSettings@CContactManager@@QEAAJXZ; CContactManager::RefreshPresentationModeSettings(void)
0x1800770bb  bt      ebx, 9
0x1800770bf  jnb     short loc_1800770F5
0x1800770c1  mov     edx, 8; uiParam
0x1800770c6  mov     [rsp+290h+var_260], 0
0x1800770cf  xor     r9d, r9d; fWinIni
0x1800770d2  mov     dword ptr [rsp+290h+var_260], edx
0x1800770d6  lea     r8, [rsp+290h+var_260]; pvParam
0x1800770db  lea     ecx, [rdx+40h]; uiAction
0x1800770de  call    cs:__imp_SystemParametersInfoW
0x1800770e4  test    eax, eax
0x1800770e6  jz      short loc_1800770F5
0x1800770e8  cmp     dword ptr [rsp+290h+var_260+4], 0
0x1800770ed  setnz   cl; bool
0x1800770f0  call    ?SetWindowAnimation@CDesktopManager@@SAX_N@Z; CDesktopManager::SetWindowAnimation(bool)
0x1800770f5  mov     [r15], ebx
0x1800770f8  mov     eax, esi
0x1800770fa  mov     rcx, [rbp+190h+var_30]
0x180077101  xor     rcx, rsp; StackCookie
0x180077104  call    __security_check_cookie
0x180077109  mov     rbx, [rsp+290h+arg_10]
0x180077111  add     rsp, 270h
0x180077118  pop     r15
0x18007711a  pop     r14
0x18007711c  pop     rdi
0x18007711d  pop     rsi
0x18007711e  pop     rbp
0x18007711f  retn
0x180077120  mov     [rsp+290h+var_268], 0
0x180077129  mov     [rsp+290h+var_270], 0C5Ah
0x180077131  jmp     loc_180076EB7
0x180077136  test    bl, 4
0x180077139  jnz     loc_180077040
0x18007713f  mov     rcx, rdi; this
0x180077142  call    ?InitializeHighContrast@CDesktopManager@@AEAAXXZ; CDesktopManager::InitializeHighContrast(void)
0x180077147  jmp     loc_18007705D
```
