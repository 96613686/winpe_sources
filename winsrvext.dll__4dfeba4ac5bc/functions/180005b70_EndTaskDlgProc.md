# EndTaskDlgProc

- ea: `0x180005b70`
- end: `0x1800061ff`
- name: `EndTaskDlgProc`
- size: `1679`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005b70`
- `0x180006788`
- `0x180006898`
- `0x1800079d4`
- `0x18000b9a8`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `USER32!PostMessageW` at `0x180005ce3`
- `USER32!PostMessageW` at `0x180005ce3`
- `USER32!DestroyWindow` at `0x180005da5`
- `USER32!DestroyWindow` at `0x180005da5`
- `USER32!SetWindowPos` at `0x180005f24`
- `USER32!SetWindowPos` at `0x180005f24`
- `USER32!InflateRect` at `0x180006017`
- `USER32!InflateRect` at `0x180006017`
- `USER32!KillTimer` at `0x180005d55`
- `USER32!KillTimer` at `0x180005d55`
- `USER32!SetWindowTextW` at `0x180005e42`
- `USER32!SetWindowTextW` at `0x180005e42`
- `USER32!GetWindowLongPtrW` at `0x180005bfb`
- `USER32!GetWindowLongPtrW` at `0x180005d8d`
- `USER32!GetWindowLongPtrW` at `0x180005edc`
- `USER32!GetWindowLongPtrW` at `0x180005f3d`
- `USER32!GetWindowLongPtrW` at `0x18000617b`
- `USER32!GetWindowLongPtrW` at `0x180005bfb`
- `USER32!GetWindowLongPtrW` at `0x180005d8d`
- `USER32!GetWindowLongPtrW` at `0x180005edc`
- `USER32!GetWindowLongPtrW` at `0x180005f3d`
- `USER32!GetWindowLongPtrW` at `0x18000617b`
- `USER32!BeginPaint` at `0x180005f68`
- `USER32!BeginPaint` at `0x180005f68`
- `USER32!DrawIcon` at `0x180005fb6`
- `USER32!DrawIcon` at `0x180005fb6`
- `USER32!DrawEdge` at `0x180005fff`
- `USER32!DrawEdge` at `0x180005fff`
- `USER32!FillRect` at `0x180005c5c`
- `USER32!FillRect` at `0x18000604f`
- `USER32!FillRect` at `0x180005c5c`
- `USER32!FillRect` at `0x18000604f`
- `USER32!LoadBitmapW` at `0x18000609a`
- `USER32!LoadBitmapW` at `0x18000609a`
- `USER32!EndPaint` at `0x180006160`
- `USER32!EndPaint` at `0x180006160`
- `USER32!GetDC` at `0x180005c42`
- `USER32!GetDC` at `0x180005c42`
- `USER32!ReleaseDC` at `0x180005c6e`
- `USER32!ReleaseDC` at `0x180005c6e`
- `USER32!DestroyIcon` at `0x1800061c5`
- `USER32!DestroyIcon` at `0x1800061c5`
- `USER32!LoadIconW` at `0x180005e87`
- `USER32!LoadIconW` at `0x180005e87`
- `USER32!InternalGetWindowIcon` at `0x180005e5e`
- `USER32!InternalGetWindowIcon` at `0x180005e5e`
- `USER32!GetWindowTextW` at `0x180005de8`
- `USER32!GetWindowTextW` at `0x180005de8`
- `USER32!GetSystemMetrics` at `0x180005d2a`
- `USER32!GetSystemMetrics` at `0x180005d2a`
- `USER32!SetWindowLongPtrW` at `0x180005dc1`
- `USER32!SetWindowLongPtrW` at `0x180005dc1`
- `GDI32!GetObjectW` at `0x1800060b7`
- `GDI32!GetObjectW` at `0x1800060b7`
- `GDI32!GetLayout` at `0x180005f7a`
- `GDI32!GetLayout` at `0x180005f7a`
- `GDI32!CreateCompatibleDC` at `0x1800060e9`
- `GDI32!CreateCompatibleDC` at `0x1800060e9`
- `GDI32!SelectObject` at `0x1800060ff`
- `GDI32!SelectObject` at `0x1800060ff`
- `GDI32!GdiTransparentBlt` at `0x18000613e`
- `GDI32!GdiTransparentBlt` at `0x18000613e`
- `GDI32!DeleteDC` at `0x18000614d`
- `GDI32!DeleteDC` at `0x18000614d`
- `GDI32!DeleteObject` at `0x18000619b`
- `GDI32!DeleteObject` at `0x1800061b0`
- `GDI32!DeleteObject` at `0x18000619b`
- `GDI32!DeleteObject` at `0x1800061b0`
- `GDI32!SetLayout` at `0x180005f99`
- `GDI32!SetLayout` at `0x180005fcc`
- `GDI32!SetLayout` at `0x180005f99`
- `GDI32!SetLayout` at `0x180005fcc`

## pseudocode

```c
INT_PTR __fastcall EndTaskDlgProc(HWND a1, int a2, __int64 a3, LONG_PTR a4)
{
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  LONG_PTR v13; // rax
  LONG_PTR v14; // rsi
  __int64 v15; // r12
  int v16; // eax
  HDC DC; // rbx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r8
  int v22; // ebx
  int v23; // edi
  unsigned int v24; // edi
  LONG_PTR v26; // rax
  int WindowTextW; // eax
  int v28; // ebx
  WCHAR *v29; // r8
  HWND v30; // rcx
  WCHAR v31; // ax
  int v32; // ebx
  HICON WindowIcon; // rax
  HINSTANCE v34; // rcx
  __int64 v35; // rdx
  bool v36; // zf
  __int64 v37; // r8
  LONG_PTR v38; // rax
  __int64 v39; // rdx
  LONG_PTR v40; // rax
  LONG_PTR v41; // rsi
  HDC v42; // r15
  DWORD Layout; // eax
  DWORD v44; // ebx
  int left; // ecx
  LONG v46; // edx
  int v47; // eax
  HBITMAP BitmapW; // rax
  LONG right; // ecx
  int v50; // eax
  HDC CompatibleDC; // rbx
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v53; // rbx
  void *v54; // rcx
  void *v55; // rcx
  HICON v56; // rcx
  struct tagRECT qrc; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v58; // [rsp+70h] [rbp-90h]
  tagPAINTSTRUCT Paint; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String[512]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  v8 = a2 - 2;
  if ( !v8 )
  {
    WindowLongPtrW = GetWindowLongPtrW(a1, -21);
    v53 = WindowLongPtrW;
    if ( WindowLongPtrW )
    {
      *(_DWORD *)WindowLongPtrW |= 3u;
      v54 = *(void **)(WindowLongPtrW + 48);
      if ( v54 )
        DeleteObject(v54);
      v55 = *(void **)(v53 + 120);
      if ( v55 )
        DeleteObject(v55);
      v56 = *(HICON *)(v53 + 72);
      if ( v56 )
        DestroyIcon(v56);
    }
    return 0;
  }
  v9 = v8 - 13;
  if ( v9 )
  {
    v10 = v9 - 119;
    if ( v10 )
    {
      v11 = v10 - 138;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 == 2 )
          {
            v13 = GetWindowLongPtrW(a1, -21);
            v14 = v13;
            if ( v13 )
            {
              v15 = a3 - 768;
              if ( v15 )
              {
                if ( v15 == 1 )
                {
                  v16 = *(_DWORD *)(v13 + 112);
                  if ( *(_DWORD *)(v14 + 104) < v16 || (*(_DWORD *)(v14 + 104) = v16, *(_DWORD *)(v14 + 96) < v16) )
                  {
                    DC = GetDC(a1);
                    FillRect(DC, (const RECT *)(v14 + 96), *(HBRUSH *)(v14 + 120));
                    ReleaseDC(a1, DC);
                    v18 = *(_DWORD *)(v14 + 116);
                    *(_DWORD *)(v14 + 96) += v18;
                    *(_DWORD *)(v14 + 104) += v18;
                  }
                }
              }
              else
              {
                v19 = *(_QWORD *)(v13 + 16);
                ++*(_DWORD *)(v13 + 40);
                if ( (unsigned int)BoostHardError(*(_QWORD *)(v19 + 40), 2)
                  || GetInputWindow(*(_QWORD *)(v14 + 16), *(HWND *)(v14 + 32)) )
                {
                  v20 = 1;
                  v21 = 21;
                }
                else
                {
                  v20 = 0;
                  v21 = 20;
                }
                if ( (*(_DWORD *)v14 & 0x10) == 0 || v20 )
                {
                  if ( (*(_DWORD *)v14 & 0x10) != v20 )
                  {
                    *(_DWORD *)v14 = *(_DWORD *)v14 & 0xFFFFFFE7 | (8 * v20 + 8);
                    SetEndTaskDlgStatus(v14, a1, v21, 0);
                    v22 = *(_DWORD *)(v14 + 96);
                    *(_DWORD *)(v14 + 40) >>= 1;
                    v23 = v22 - *(_DWORD *)(v14 + 80);
                    v24 = (unsigned int)(v23 - GetSystemMetrics(45)) >> 1;
                    *(_DWORD *)(v14 + 104) -= v24;
                    *(_DWORD *)(v14 + 96) = v22 - v24;
                  }
                  if ( *(_DWORD *)(v14 + 40) >= (unsigned int)gdwHungToKillCount )
                  {
                    KillTimer(a1, 0x300u);
                    *(_DWORD *)v14 = *(_DWORD *)v14 & 0xFFFFFFE3 | 4;
                    SetEndTaskDlgStatus(v14, a1, 19, 0);
                  }
                }
                else
                {
                  PostMessageW(a1, 0x111u, 2u, 0);
                }
              }
            }
            return 1;
          }
        }
        else
        {
          v26 = GetWindowLongPtrW(a1, -21);
          if ( v26 )
            *(_DWORD *)(v26 + 8) = a3;
          DestroyWindow(a1);
        }
      }
      else
      {
        SetWindowLongPtrW(a1, -21, a4);
        *(_DWORD *)a4 &= ~1u;
        String[511] = 0;
        WindowTextW = GetWindowTextW(a1, String, 511);
        v28 = 511 - WindowTextW;
        v29 = &String[WindowTextW];
        v30 = *(HWND *)(a4 + 32);
        if ( (*(_BYTE *)(a4 + 4) & 0x20) != 0 )
        {
          do
          {
            if ( !v28 )
              break;
            v31 = *(_WORD *)v30;
            --v28;
            *v29 = *(_WORD *)v30;
            v30 = (HWND)((char *)v30 + 2);
            ++v29;
          }
          while ( v31 );
        }
        else
        {
          GetApplicationText(v30, *(void **)(*(_QWORD *)(a4 + 16) + 64LL), v29, v28);
        }
        SetWindowTextW(a1, String);
        v32 = *(_DWORD *)(a4 + 4);
        WindowIcon = (HICON)InternalGetWindowIcon(*(_QWORD *)(a4 + 32), 1);
        if ( !WindowIcon )
        {
          if ( (v32 & 0x20) != 0 )
          {
            v34 = ghModuleWin;
            v35 = 1;
          }
          else
          {
            v35 = 32512;
            v34 = 0;
          }
          WindowIcon = LoadIconW(v34, (LPCWSTR)v35);
        }
        v36 = (*(_BYTE *)(a4 + 4) & 0x20) == 0;
        *(_QWORD *)(a4 + 72) = WindowIcon;
        if ( v36 )
        {
          if ( (*(_DWORD *)a4 & 0x10) != 0 )
            v37 = 21;
          else
            v37 = (unsigned int)((*(_DWORD *)a4 & 8) != 0) + 19;
        }
        else
        {
          v37 = 18;
        }
        SetEndTaskDlgStatus(a4, a1, v37, 1);
      }
    }
    else
    {
      v38 = GetWindowLongPtrW(a1, -21);
      if ( v38 )
      {
        if ( a3 )
        {
          v39 = -1;
        }
        else
        {
          v39 = 0;
          if ( (*(_BYTE *)(v38 + 4) & 0x20) == 0 )
            v39 = *(_QWORD *)(v38 + 32);
        }
        SetWindowPos(a1, (HWND)v39, 0, 0, 0, 0, 3u);
      }
    }
    return 0;
  }
  v40 = GetWindowLongPtrW(a1, -21);
  v41 = v40;
  if ( !v40 || !*(_QWORD *)(v40 + 72) )
    return 0;
  v42 = BeginPaint(a1, &Paint);
  Layout = GetLayout(v42);
  v44 = Layout;
  if ( Layout != -1 )
    SetLayout(v42, Layout | 8);
  DrawIcon(v42, 10, 10, *(HICON *)(v41 + 72));
  if ( v44 != -1 )
    SetLayout(v42, v44);
  if ( (*(_BYTE *)v41 & 8) != 0 )
  {
    qrc = *(struct tagRECT *)(v41 + 80);
    DrawEdge(v42, &qrc, 2u, 0x200Fu);
    InflateRect(&qrc, -1, -1);
    left = qrc.left;
    v46 = qrc.left + *(_DWORD *)(v41 + 116) - 1;
    while ( 1 )
    {
      qrc.right = v46;
      if ( left >= *(_DWORD *)(v41 + 96) )
        break;
      v47 = *(_DWORD *)(v41 + 112);
      if ( v46 > v47 )
      {
        qrc.right = *(_DWORD *)(v41 + 112);
        if ( left >= v47 )
          break;
      }
      FillRect(v42, &qrc, *(HBRUSH *)(v41 + 120));
      left = *(_DWORD *)(v41 + 116) + qrc.left;
      v46 = *(_DWORD *)(v41 + 116) + qrc.right;
      qrc.left = left;
    }
  }
  else
  {
    if ( !*(_QWORD *)(v41 + 48) )
    {
      qrc = 0;
      v58 = 0;
      BitmapW = LoadBitmapW(ghModuleWin, (LPCWSTR)0x200);
      *(_QWORD *)(v41 + 48) = BitmapW;
      if ( GetObjectW(BitmapW, 32, &qrc) )
      {
        right = qrc.right;
        v50 = 42 - qrc.right;
        *(_DWORD *)(v41 + 56) = 10;
        *(_DWORD *)(v41 + 60) = v50;
        *(_DWORD *)(v41 + 64) = qrc.top;
        *(_DWORD *)(v41 + 68) = right;
      }
    }
    CompatibleDC = CreateCompatibleDC(v42);
    SelectObject(CompatibleDC, *(HGDIOBJ *)(v41 + 48));
    GdiTransparentBlt(
      v42,
      *(_DWORD *)(v41 + 56),
      *(_DWORD *)(v41 + 60),
      *(_DWORD *)(v41 + 64),
      *(_DWORD *)(v41 + 68),
      CompatibleDC,
      0,
      0,
      *(_DWORD *)(v41 + 64),
      *(_DWORD *)(v41 + 68),
      0xFF00FFu);
    DeleteDC(CompatibleDC);
  }
  EndPaint(a1, &Paint);
  return 1;
}

```

## disassembly

```asm
0x180005b70  mov     [rsp-8+arg_8], rbx
0x180005b75  mov     [rsp-8+arg_10], rsi
0x180005b7a  push    rbp
0x180005b7b  push    rdi
0x180005b7c  push    r12
0x180005b7e  push    r14
0x180005b80  push    r15
0x180005b82  lea     rbp, [rsp-3E0h]
0x180005b8a  sub     rsp, 4E0h
0x180005b91  mov     rax, cs:__security_cookie
0x180005b98  xor     rax, rsp
0x180005b9b  mov     [rbp+400h+var_30], rax
0x180005ba2  mov     ebx, edx
0x180005ba4  mov     r12, r8
0x180005ba7  xor     edx, edx; Val
0x180005ba9  mov     r14, rcx
0x180005bac  lea     rcx, [rbp+400h+Paint]; void *
0x180005bb0  mov     rsi, r9
0x180005bb3  lea     r8d, [rdx+48h]; Size
0x180005bb7  call    memset_0
0x180005bbc  sub     ebx, 2
0x180005bbf  jz      loc_180006173
0x180005bc5  sub     ebx, 0Dh
0x180005bc8  jz      loc_180005F35
0x180005bce  sub     ebx, 77h ; 'w'
0x180005bd1  jz      loc_180005ED4
0x180005bd7  sub     ebx, 8Ah
0x180005bdd  jz      loc_180005DB6
0x180005be3  sub     ebx, 1
0x180005be6  jz      loc_180005D85
0x180005bec  cmp     ebx, 2
0x180005bef  jnz     loc_1800061D1
0x180005bf5  lea     edx, [rbx-17h]; nIndex
0x180005bf8  mov     rcx, r14; hWnd
0x180005bfb  call    cs:__imp_GetWindowLongPtrW
0x180005c02  nop     dword ptr [rax+rax+00h]
0x180005c07  xor     edi, edi
0x180005c09  lea     r15d, [rbx-1]
0x180005c0d  mov     rsi, rax
0x180005c10  test    rax, rax
0x180005c13  jz      loc_180005D7D
0x180005c19  sub     r12, 300h
0x180005c20  jz      short loc_180005C88
0x180005c22  cmp     r12, r15
0x180005c25  jnz     loc_180005D7D
0x180005c2b  mov     eax, [rax+70h]
0x180005c2e  cmp     [rsi+68h], eax
0x180005c31  jl      short loc_180005C3F
0x180005c33  mov     [rsi+68h], eax
0x180005c36  cmp     [rsi+60h], eax
0x180005c39  jge     loc_180005D7D
0x180005c3f  mov     rcx, r14; hWnd
0x180005c42  call    cs:__imp_GetDC
0x180005c49  nop     dword ptr [rax+rax+00h]
0x180005c4e  mov     r8, [rsi+78h]; hbr
0x180005c52  lea     rdx, [rsi+60h]; lprc
0x180005c56  mov     rcx, rax; hDC
0x180005c59  mov     rbx, rax
0x180005c5c  call    cs:__imp_FillRect
0x180005c63  nop     dword ptr [rax+rax+00h]
0x180005c68  mov     rdx, rbx; hDC
0x180005c6b  mov     rcx, r14; hWnd
0x180005c6e  call    cs:__imp_ReleaseDC
0x180005c75  nop     dword ptr [rax+rax+00h]
0x180005c7a  mov     eax, [rsi+74h]
0x180005c7d  add     [rsi+60h], eax
0x180005c80  add     [rsi+68h], eax
0x180005c83  jmp     loc_180005D7D
0x180005c88  mov     rcx, [rax+10h]
0x180005c8c  mov     edx, 2
0x180005c91  add     [rax+28h], r15d
0x180005c95  mov     rcx, [rcx+28h]
0x180005c99  call    BoostHardError
0x180005c9e  test    eax, eax
0x180005ca0  jnz     short loc_180005CBE
0x180005ca2  mov     rdx, [rsi+20h]
0x180005ca6  mov     rcx, [rsi+10h]
0x180005caa  call    GetInputWindow
0x180005caf  test    rax, rax
0x180005cb2  jnz     short loc_180005CBE
0x180005cb4  mov     eax, edi
0x180005cb6  mov     r8d, 14h
0x180005cbc  jmp     short loc_180005CC7
0x180005cbe  mov     eax, r15d
0x180005cc1  mov     r8d, 15h
0x180005cc7  mov     edx, [rsi]
0x180005cc9  mov     ecx, edx
0x180005ccb  and     ecx, 10h
0x180005cce  jz      short loc_180005CF4
0x180005cd0  test    eax, eax
0x180005cd2  jnz     short loc_180005CF4
0x180005cd4  xor     r9d, r9d; lParam
0x180005cd7  lea     r8d, [rax+2]; wParam
0x180005cdb  mov     edx, 111h; Msg
0x180005ce0  mov     rcx, r14; hWnd
0x180005ce3  call    cs:__imp_PostMessageW
0x180005cea  nop     dword ptr [rax+rax+00h]
0x180005cef  jmp     loc_180005D7D
0x180005cf4  mov     r12d, 0FFFFFFE7h
0x180005cfa  cmp     ecx, eax
0x180005cfc  jz      short loc_180005D42
0x180005cfe  and     edx, r12d
0x180005d01  lea     eax, ds:8[rax*8]
0x180005d08  or      eax, edx
0x180005d0a  xor     r9d, r9d
0x180005d0d  mov     rdx, r14
0x180005d10  mov     [rsi], eax
0x180005d12  mov     rcx, rsi
0x180005d15  call    SetEndTaskDlgStatus
0x180005d1a  mov     ebx, [rsi+60h]
0x180005d1d  mov     ecx, 2Dh ; '-'; nIndex
0x180005d22  shr     dword ptr [rsi+28h], 1
0x180005d25  mov     edi, ebx
0x180005d27  sub     edi, [rsi+50h]
0x180005d2a  call    cs:__imp_GetSystemMetrics
0x180005d31  nop     dword ptr [rax+rax+00h]
0x180005d36  sub     edi, eax
0x180005d38  shr     edi, 1
0x180005d3a  sub     ebx, edi
0x180005d3c  sub     [rsi+68h], edi
0x180005d3f  mov     [rsi+60h], ebx
0x180005d42  mov     eax, cs:gdwHungToKillCount
0x180005d48  cmp     [rsi+28h], eax
0x180005d4b  jb      short loc_180005D7D
0x180005d4d  mov     edx, 300h; uIDEvent
0x180005d52  mov     rcx, r14; hWnd
0x180005d55  call    cs:__imp_KillTimer
0x180005d5c  nop     dword ptr [rax+rax+00h]
0x180005d61  mov     ecx, [rsi]
0x180005d63  xor     r9d, r9d
0x180005d66  and     ecx, r12d
0x180005d69  mov     rdx, r14
0x180005d6c  or      ecx, 4
0x180005d6f  mov     [rsi], ecx
0x180005d71  mov     rcx, rsi
0x180005d74  lea     r8d, [r9+13h]
0x180005d78  call    SetEndTaskDlgStatus
0x180005d7d  mov     rax, r15
0x180005d80  jmp     loc_1800061D3
0x180005d85  mov     edx, 0FFFFFFEBh; nIndex
0x180005d8a  mov     rcx, r14; hWnd
0x180005d8d  call    cs:__imp_GetWindowLongPtrW
0x180005d94  nop     dword ptr [rax+rax+00h]
0x180005d99  test    rax, rax
0x180005d9c  jz      short loc_180005DA2
0x180005d9e  mov     [rax+8], r12d
0x180005da2  mov     rcx, r14; hWnd
0x180005da5  call    cs:__imp_DestroyWindow
0x180005dac  nop     dword ptr [rax+rax+00h]
0x180005db1  jmp     loc_1800061D1
0x180005db6  mov     r8, rsi; dwNewLong
0x180005db9  mov     edx, 0FFFFFFEBh; nIndex
0x180005dbe  mov     rcx, r14; hWnd
0x180005dc1  call    cs:__imp_SetWindowLongPtrW
0x180005dc8  nop     dword ptr [rax+rax+00h]
0x180005dcd  and     dword ptr [rsi], 0FFFFFFFEh
0x180005dd0  lea     rdx, [rbp+400h+String]; lpString
0x180005dd4  mov     ebx, 1FFh
0x180005dd9  xor     edi, edi
0x180005ddb  mov     r8d, ebx; nMaxCount
0x180005dde  mov     [rbp+400h+var_32], di
0x180005de5  mov     rcx, r14; hWnd
0x180005de8  call    cs:__imp_GetWindowTextW
0x180005def  nop     dword ptr [rax+rax+00h]
0x180005df4  mov     ecx, eax
0x180005df6  lea     r8, [rbp+400h+String]
0x180005dfa  sub     ebx, eax
0x180005dfc  test    byte ptr [rsi+4], 20h
0x180005e00  lea     r8, [r8+rcx*2]
0x180005e04  mov     rcx, [rsi+20h]
0x180005e08  jz      short loc_180005E2B
0x180005e0a  or      r12d, 0FFFFFFFFh
0x180005e0e  test    ebx, ebx
0x180005e10  jz      short loc_180005E3B
0x180005e12  movzx   eax, word ptr [rcx]
0x180005e15  add     ebx, r12d
0x180005e18  mov     [r8], ax
0x180005e1c  add     rcx, 2
0x180005e20  add     r8, 2
0x180005e24  test    ax, ax
0x180005e27  jnz     short loc_180005E0E
0x180005e29  jmp     short loc_180005E3B
0x180005e2b  mov     rdx, [rsi+10h]
0x180005e2f  mov     r9d, ebx
0x180005e32  mov     rdx, [rdx+40h]
0x180005e36  call    GetApplicationText
0x180005e3b  lea     rdx, [rbp+400h+String]; lpString
0x180005e3f  mov     rcx, r14; hWnd
0x180005e42  call    cs:__imp_SetWindowTextW
0x180005e49  nop     dword ptr [rax+rax+00h]
0x180005e4e  mov     rcx, [rsi+20h]
0x180005e52  mov     r15d, 1
0x180005e58  mov     ebx, [rsi+4]
0x180005e5b  mov     edx, r15d
0x180005e5e  call    cs:__imp_InternalGetWindowIcon
0x180005e65  nop     dword ptr [rax+rax+00h]
0x180005e6a  test    rax, rax
0x180005e6d  jnz     short loc_180005E93
0x180005e6f  test    bl, 20h
0x180005e72  jz      short loc_180005E80
0x180005e74  mov     rcx, cs:ghModuleWin
0x180005e7b  mov     edx, r15d
0x180005e7e  jmp     short loc_180005E87
0x180005e80  mov     edx, 7F00h; lpIconName
0x180005e85  xor     ecx, ecx; hInstance
0x180005e87  call    cs:__imp_LoadIconW
0x180005e8e  nop     dword ptr [rax+rax+00h]
0x180005e93  test    byte ptr [rsi+4], 20h
0x180005e97  mov     [rsi+48h], rax
0x180005e9b  jz      short loc_180005EA5
0x180005e9d  mov     r8d, 12h
0x180005ea3  jmp     short loc_180005EC1
0x180005ea5  mov     eax, [rsi]
0x180005ea7  test    al, 10h
0x180005ea9  jz      short loc_180005EB3
0x180005eab  mov     r8d, 15h
0x180005eb1  jmp     short loc_180005EC1
0x180005eb3  and     al, 8
0x180005eb5  neg     al
0x180005eb7  sbb     r8d, r8d
0x180005eba  neg     r8d
0x180005ebd  add     r8d, 13h
0x180005ec1  mov     r9d, r15d
0x180005ec4  mov     rdx, r14
0x180005ec7  mov     rcx, rsi
0x180005eca  call    SetEndTaskDlgStatus
0x180005ecf  jmp     loc_1800061D1
0x180005ed4  mov     edx, 0FFFFFFEBh; nIndex
0x180005ed9  mov     rcx, r14; hWnd
0x180005edc  call    cs:__imp_GetWindowLongPtrW
0x180005ee3  nop     dword ptr [rax+rax+00h]
0x180005ee8  xor     edi, edi
0x180005eea  test    rax, rax
0x180005eed  jz      loc_1800061D1
0x180005ef3  test    r12, r12
0x180005ef6  jz      short loc_180005EFE
0x180005ef8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005efc  jmp     short loc_180005F0B
0x180005efe  test    byte ptr [rax+4], 20h
0x180005f02  mov     rdx, rdi
0x180005f05  jnz     short loc_180005F0B
0x180005f07  mov     rdx, [rax+20h]; hWndInsertAfter
0x180005f0b  mov     [rsp+500h+uFlags], 3; uFlags
0x180005f13  xor     r9d, r9d; Y
0x180005f16  mov     [rsp+500h+cy], edi; cy
0x180005f1a  xor     r8d, r8d; X
0x180005f1d  mov     rcx, r14; hWnd
0x180005f20  mov     [rsp+500h+hDest], edi; cx
0x180005f24  call    cs:__imp_SetWindowPos
0x180005f2b  nop     dword ptr [rax+rax+00h]
0x180005f30  jmp     loc_1800061D1
0x180005f35  mov     edx, 0FFFFFFEBh; nIndex
0x180005f3a  mov     rcx, r14; hWnd
0x180005f3d  call    cs:__imp_GetWindowLongPtrW
0x180005f44  nop     dword ptr [rax+rax+00h]
0x180005f49  xor     edi, edi
0x180005f4b  mov     rsi, rax
0x180005f4e  test    rax, rax
0x180005f51  jz      loc_1800061D1
0x180005f57  cmp     [rax+48h], rdi
0x180005f5b  jz      loc_1800061D1
0x180005f61  lea     rdx, [rbp+400h+Paint]; lpPaint
0x180005f65  mov     rcx, r14; hWnd
0x180005f68  call    cs:__imp_BeginPaint
0x180005f6f  nop     dword ptr [rax+rax+00h]
0x180005f74  mov     rcx, rax; hdc
0x180005f77  mov     r15, rax
0x180005f7a  call    cs:__imp_GetLayout
0x180005f81  nop     dword ptr [rax+rax+00h]
0x180005f86  or      r12d, 0FFFFFFFFh
0x180005f8a  mov     ebx, eax
0x180005f8c  cmp     eax, r12d
0x180005f8f  jz      short loc_180005FA5
0x180005f91  mov     edx, eax
0x180005f93  mov     rcx, r15; hdc
0x180005f96  or      edx, 8; l
0x180005f99  call    cs:__imp_SetLayout
0x180005fa0  nop     dword ptr [rax+rax+00h]
0x180005fa5  mov     r9, [rsi+48h]; hIcon
0x180005fa9  mov     eax, 0Ah
0x180005fae  mov     r8d, eax; Y
0x180005fb1  mov     edx, eax; X
0x180005fb3  mov     rcx, r15; hDC
0x180005fb6  call    cs:__imp_DrawIcon
0x180005fbd  nop     dword ptr [rax+rax+00h]
0x180005fc2  cmp     ebx, r12d
0x180005fc5  jz      short loc_180005FD8
0x180005fc7  mov     edx, ebx; l
0x180005fc9  mov     rcx, r15; hdc
0x180005fcc  call    cs:__imp_SetLayout
0x180005fd3  nop     dword ptr [rax+rax+00h]
0x180005fd8  test    byte ptr [rsi], 8
0x180005fdb  jz      loc_18000607B
0x180005fe1  movups  xmm0, xmmword ptr [rsi+50h]
0x180005fe5  mov     r9d, 200Fh; grfFlags
0x180005feb  lea     rdx, [rsp+500h+qrc]; qrc
0x180005ff0  mov     r8d, 2; edge
0x180005ff6  mov     rcx, r15; hdc
0x180005ff9  movdqu  xmmword ptr [rsp+500h+qrc.left], xmm0
0x180005fff  call    cs:__imp_DrawEdge
  ... truncated ...
```
