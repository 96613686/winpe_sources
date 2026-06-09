# CDimmedWindow::OnCreate(tagCREATESTRUCTW const *)

- ea: `0x180034fb0`
- end: `0x180035256`
- name: `?OnCreate@CDimmedWindow@@AEAAHPEBUtagCREATESTRUCTW@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(CDimmedWindow *__hidden this, const struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f3d0`

## callees

- `0x18001a930`
- `0x180034fb0`
- `0x1800358c0`
- `0x18003d818`
- `0x18003d858`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035222`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035222`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035078`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035078`
- `GDI32!DeleteObject` at `0x18003515a`
- `GDI32!DeleteObject` at `0x1800351db`
- `GDI32!DeleteObject` at `0x18003515a`
- `GDI32!DeleteObject` at `0x1800351db`
- `GDI32!CreateSolidBrush` at `0x1800351b9`
- `GDI32!CreateSolidBrush` at `0x1800351b9`
- `GDI32!SelectObject` at `0x180035147`
- `GDI32!SelectObject` at `0x180035147`
- `GDI32!CreateDIBSection` at `0x180035131`
- `GDI32!CreateDIBSection` at `0x180035131`
- `GDI32!CreateCompatibleDC` at `0x1800350db`
- `GDI32!CreateCompatibleDC` at `0x1800350db`
- `GDI32!DeleteDC` at `0x18003516e`
- `GDI32!DeleteDC` at `0x18003516e`
- `USER32!ReleaseDC` at `0x18003520c`
- `USER32!ReleaseDC` at `0x18003520c`
- `USER32!GetDC` at `0x1800350c6`
- `USER32!GetDC` at `0x1800350c6`
- `USER32!GetSystemMetrics` at `0x180034fe1`
- `USER32!GetSystemMetrics` at `0x180034fe1`
- `USER32!GetClientRect` at `0x1800351b0`
- `USER32!GetClientRect` at `0x1800351b0`
- `USER32!FillRect` at `0x1800351d2`
- `USER32!FillRect` at `0x1800351d2`
- `USER32!ShowWindow` at `0x1800351ea`
- `USER32!ShowWindow` at `0x1800351ea`
- `USER32!SetForegroundWindow` at `0x1800351f4`
- `USER32!SetForegroundWindow` at `0x1800351f4`
- `USER32!ValidateRect` at `0x180035218`
- `USER32!ValidateRect` at `0x180035218`

## pseudocode

```c
_BOOL8 __fastcall CDimmedWindow::OnCreate(CDimmedWindow *this, const struct tagCREATESTRUCTW *a2)
{
  unsigned int v4; // r9d
  unsigned int v5; // r9d
  LSTATUS v6; // eax
  unsigned int v7; // r9d
  bool v8; // sf
  HDC DC; // rax
  HDC v10; // rdi
  HDC CompatibleDC; // rax
  HBITMAP v12; // rax
  HGDIOBJ v13; // rax
  __int64 Color; // rax
  HWND v15; // rcx
  HBRUSH SolidBrush; // rax
  HBRUSH v17; // rsi
  int v19; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-48h] BYREF
  BITMAPINFO pbmi; // [rsp+48h] [rbp-38h] BYREF

  if ( !GetSystemMetrics(4096) )
  {
    v19 = 0;
    SHRegGetBOOLWithREGSAM(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
      L"LaunchUserOOBE",
      v4,
      &v19);
    if ( !v19 )
    {
      v19 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
        L"LaunchCflScenario",
        v5,
        &v19);
      if ( !v19 )
      {
        v19 = 0;
        hKey[0] = 0;
        v6 = RegOpenKeyExW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
               0,
               0x20019u,
               hKey);
        v8 = v6 < 0;
        if ( v6 > 0 )
          v8 = 1;
        if ( v8
          || (SHRegGetBOOLWithREGSAM(hKey[0], L"Fullscreen", L"FullscreenCXHRunning", v7, &v19),
              RegCloseKey(hKey[0]),
              !v19) )
        {
          DC = GetDC(*((HWND *)this + 3));
          v10 = DC;
          if ( DC )
          {
            CompatibleDC = CreateCompatibleDC(DC);
            *((_QWORD *)this + 5) = CompatibleDC;
            if ( CompatibleDC )
            {
              pbmi.bmiHeader.biWidth = a2->cx;
              pbmi.bmiHeader.biHeight = a2->cy;
              pbmi.bmiHeader.biSize = 44;
              *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
              memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
              v12 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)this + 8, 0, 0);
              *((_QWORD *)this + 6) = v12;
              if ( v12 )
              {
                v13 = SelectObject(*((HDC *)this + 5), v12);
                *((_QWORD *)this + 7) = v13;
                if ( !v13 )
                {
                  DeleteObject(*((HGDIOBJ *)this + 6));
                  *((_QWORD *)this + 6) = 0;
                }
              }
              if ( !*((_QWORD *)this + 6) )
              {
                DeleteDC(*((HDC *)this + 5));
                *((_QWORD *)this + 5) = 0;
              }
            }
            if ( *((_QWORD *)this + 5) )
            {
              *((_DWORD *)this + 18) = CImmersiveColor::GetColor(41) & 0xFFFFFF;
              Color = CImmersiveColor::GetColor(255);
              v15 = (HWND)*((_QWORD *)this + 3);
              *((_DWORD *)this + 19) = Color & 0xFFFFFF;
              *(_OWORD *)hKey = 0;
              GetClientRect(v15, (LPRECT)hKey);
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 18));
              v17 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(*((HDC *)this + 5), (const RECT *)hKey, SolidBrush);
                DeleteObject(v17);
              }
            }
            ShowWindow(*((HWND *)this + 3), 5);
            SetForegroundWindow(*((HWND *)this + 3));
            CDimmedWindow::OnPaint(this, v10);
            ReleaseDC(*((HWND *)this + 3), v10);
            ValidateRect(*((HWND *)this + 3), 0);
          }
        }
      }
    }
  }
  SetEvent(*((HANDLE *)this + 4));
  return *((_QWORD *)this + 5) != 0;
}

```

## disassembly

```asm
0x180034fb0  mov     [rsp-18h+arg_10], rbx
0x180034fb5  mov     [rsp-18h+arg_18], rsi
0x180034fba  push    rbp
0x180034fbb  push    rdi
0x180034fbc  push    r14
0x180034fbe  mov     rbp, rsp
0x180034fc1  sub     rsp, 80h
0x180034fc8  mov     rax, cs:__security_cookie
0x180034fcf  xor     rax, rsp
0x180034fd2  mov     [rbp+var_8], rax
0x180034fd6  mov     rbx, rcx
0x180034fd9  mov     rsi, rdx
0x180034fdc  mov     ecx, 1000h; nIndex
0x180034fe1  call    cs:__imp_GetSystemMetrics
0x180034fe7  xor     r14d, r14d
0x180034fea  test    eax, eax
0x180034fec  jnz     loc_18003521E
0x180034ff2  lea     rax, [rbp+var_50]
0x180034ff6  mov     [rbp+var_50], r14d
0x180034ffa  mov     rdi, 0FFFFFFFF80000002h
0x180035001  mov     [rsp+80h+phkResult], rax; int *
0x180035006  mov     rcx, rdi; HKEY
0x180035009  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x180035010  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180035017  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18003501c  cmp     [rbp+var_50], r14d
0x180035020  jnz     loc_18003521E
0x180035026  lea     rax, [rbp+var_50]
0x18003502a  mov     [rbp+var_50], r14d
0x18003502e  lea     r8, aLaunchcflscena; "LaunchCflScenario"
0x180035035  mov     [rsp+80h+phkResult], rax; int *
0x18003503a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180035041  mov     rcx, rdi; HKEY
0x180035044  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180035049  cmp     [rbp+var_50], r14d
0x18003504d  jnz     loc_18003521E
0x180035053  lea     rax, [rbp+hKey]
0x180035057  mov     [rbp+var_50], r14d
0x18003505b  mov     r9d, 20019h; samDesired
0x180035061  mov     [rsp+80h+phkResult], rax; phkResult
0x180035066  xor     r8d, r8d; ulOptions
0x180035069  mov     [rbp+hKey], r14
0x18003506d  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180035074  lea     rcx, [rdi-1]; hKey
0x180035078  call    cs:__imp_RegOpenKeyExW
0x18003507e  test    eax, eax
0x180035080  jle     short loc_18003508C
0x180035082  movzx   eax, ax
0x180035085  or      eax, 80070000h
0x18003508a  test    eax, eax
0x18003508c  js      short loc_1800350C2
0x18003508e  mov     rcx, [rbp+hKey]; HKEY
0x180035092  lea     rax, [rbp+var_50]
0x180035096  lea     r8, aFullscreencxhr; "FullscreenCXHRunning"
0x18003509d  mov     [rsp+80h+phkResult], rax; int *
0x1800350a2  lea     rdx, aFullscreen; "Fullscreen"
0x1800350a9  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800350ae  mov     rcx, [rbp+hKey]; hKey
0x1800350b2  call    cs:__imp_RegCloseKey
0x1800350b8  cmp     [rbp+var_50], r14d
0x1800350bc  jnz     loc_18003521E
0x1800350c2  mov     rcx, [rbx+18h]; hWnd
0x1800350c6  call    cs:__imp_GetDC
0x1800350cc  mov     rdi, rax
0x1800350cf  test    rax, rax
0x1800350d2  jz      loc_18003521E
0x1800350d8  mov     rcx, rax; hdc
0x1800350db  call    cs:__imp_CreateCompatibleDC
0x1800350e1  mov     [rbx+28h], rax
0x1800350e5  test    rax, rax
0x1800350e8  jz      loc_180035178
0x1800350ee  mov     ecx, [rsi+24h]
0x1800350f1  lea     r9, [rbx+40h]; ppvBits
0x1800350f5  mov     [rbp+pbmi.bmiHeader.biWidth], ecx
0x1800350f8  lea     rdx, [rbp+pbmi]; pbmi
0x1800350fc  mov     ecx, [rsi+20h]
0x1800350ff  xorps   xmm0, xmm0
0x180035102  mov     [rbp+pbmi.bmiHeader.biHeight], ecx
0x180035105  xor     r8d, r8d; usage
0x180035108  mov     rcx, rax; hdc
0x18003510b  mov     [rsp+80h+offset], r14d; offset
0x180035110  movdqu  xmmword ptr [rbp+pbmi.bmiHeader.biXPelsPerMeter], xmm0
0x180035115  mov     dword ptr [rbp+pbmi.bmiColors.rgbBlue], r14d
0x180035119  mov     [rbp+pbmi.bmiHeader.biSize], 2Ch ; ','
0x180035120  mov     qword ptr [rbp+pbmi.bmiHeader.biPlanes], 200001h
0x180035128  mov     [rbp+pbmi.bmiHeader.biSizeImage], r14d
0x18003512c  mov     [rsp+80h+phkResult], r14; hSection
0x180035131  call    cs:__imp_CreateDIBSection
0x180035137  mov     [rbx+30h], rax
0x18003513b  test    rax, rax
0x18003513e  jz      short loc_180035164
0x180035140  mov     rcx, [rbx+28h]; hdc
0x180035144  mov     rdx, rax; h
0x180035147  call    cs:__imp_SelectObject
0x18003514d  mov     [rbx+38h], rax
0x180035151  test    rax, rax
0x180035154  jnz     short loc_180035164
0x180035156  mov     rcx, [rbx+30h]; ho
0x18003515a  call    cs:__imp_DeleteObject
0x180035160  mov     [rbx+30h], r14
0x180035164  cmp     [rbx+30h], r14
0x180035168  jnz     short loc_180035178
0x18003516a  mov     rcx, [rbx+28h]; hdc
0x18003516e  call    cs:__imp_DeleteDC
0x180035174  mov     [rbx+28h], r14
0x180035178  cmp     [rbx+28h], r14
0x18003517c  jz      short loc_1800351E1
0x18003517e  mov     ecx, 29h ; ')'
0x180035183  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x180035188  mov     esi, 0FFFFFFh
0x18003518d  mov     ecx, 0FFh
0x180035192  and     eax, esi
0x180035194  mov     [rbx+48h], eax
0x180035197  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x18003519c  mov     rcx, [rbx+18h]; hWnd
0x1800351a0  lea     rdx, [rbp+hKey]; lpRect
0x1800351a4  and     eax, esi
0x1800351a6  xorps   xmm0, xmm0
0x1800351a9  mov     [rbx+4Ch], eax
0x1800351ac  movups  xmmword ptr [rbp+hKey], xmm0
0x1800351b0  call    cs:__imp_GetClientRect
0x1800351b6  mov     ecx, [rbx+48h]; color
0x1800351b9  call    cs:__imp_CreateSolidBrush
0x1800351bf  mov     rsi, rax
0x1800351c2  test    rax, rax
0x1800351c5  jz      short loc_1800351E1
0x1800351c7  mov     rcx, [rbx+28h]; hDC
0x1800351cb  lea     rdx, [rbp+hKey]; lprc
0x1800351cf  mov     r8, rax; hbr
0x1800351d2  call    cs:__imp_FillRect
0x1800351d8  mov     rcx, rsi; ho
0x1800351db  call    cs:__imp_DeleteObject
0x1800351e1  mov     rcx, [rbx+18h]; hWnd
0x1800351e5  mov     edx, 5; nCmdShow
0x1800351ea  call    cs:__imp_ShowWindow
0x1800351f0  mov     rcx, [rbx+18h]; hWnd
0x1800351f4  call    cs:__imp_SetForegroundWindow
0x1800351fa  mov     rdx, rdi; HDC
0x1800351fd  mov     rcx, rbx; this
0x180035200  call    ?OnPaint@CDimmedWindow@@AEAAXPEAUHDC__@@@Z; CDimmedWindow::OnPaint(HDC__ *)
0x180035205  mov     rcx, [rbx+18h]; hWnd
0x180035209  mov     rdx, rdi; hDC
0x18003520c  call    cs:__imp_ReleaseDC
0x180035212  mov     rcx, [rbx+18h]; hWnd
0x180035216  xor     edx, edx; lpRect
0x180035218  call    cs:__imp_ValidateRect
0x18003521e  mov     rcx, [rbx+20h]; hEvent
0x180035222  call    cs:__imp_SetEvent
0x180035228  cmp     [rbx+28h], r14
0x18003522c  mov     eax, r14d
0x18003522f  setnz   al
0x180035232  mov     rcx, [rbp+var_8]
0x180035236  xor     rcx, rsp; StackCookie
0x180035239  call    __security_check_cookie
0x18003523e  lea     r11, [rsp+80h+var_s0]
0x180035246  mov     rbx, [r11+30h]
0x18003524a  mov     rsi, [r11+38h]
0x18003524e  mov     rsp, r11
0x180035251  pop     r14
0x180035253  pop     rdi
0x180035254  pop     rbp
0x180035255  retn
```
