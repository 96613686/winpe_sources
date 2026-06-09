# MDIClientWndProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)

- ea: `0x180012580`
- end: `0x180012b39`
- name: `?MDIClientWndProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z`
- size: `1465`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, installer_update`

## callers

- `0x1800124c0`
- `0x180012520`

## callees

- `0x180006c18`
- `0x180007640`
- `0x18000cf20`
- `0x18000d210`
- `0x18000ec50`
- `0x180010950`
- `0x180012580`
- `0x180016980`
- `0x180016de0`
- `0x180018214`
- `0x18002d6c0`
- `0x18002dd20`
- `0x180055b24`
- `0x180055d38`
- `0x180055da4`
- `0x180055f30`
- `0x180055fc8`
- `0x18005cc64`
- `0x180060c98`
- `0x180066e58`
- `0x18008705c`
- `0x1800875f0`

## import_xrefs

- `win32u!NtUserDefSetText` at `0x180012655`
- `win32u!NtUserDefSetText` at `0x180012655`
- `win32u!NtUserUpdateClientRect` at `0x180012a60`
- `win32u!NtUserUpdateClientRect` at `0x180012a60`
- `win32u!NtUserSetWindowLongPtr` at `0x18001280e`
- `win32u!NtUserSetWindowLongPtr` at `0x18001280e`
- `win32u!NtUserShowScrollBar` at `0x1800992d2`
- `win32u!NtUserShowScrollBar` at `0x1800993de`
- `win32u!NtUserShowScrollBar` at `0x1800992d2`
- `win32u!NtUserShowScrollBar` at `0x1800993de`
- `win32u!NtUserArrangeIconicWindows` at `0x180012b1d`
- `win32u!NtUserArrangeIconicWindows` at `0x180012b1d`
- `win32u!NtUserSetWindowFNID` at `0x1800128c2`
- `win32u!NtUserSetWindowFNID` at `0x180012929`
- `win32u!NtUserSetWindowFNID` at `0x1800128c2`
- `win32u!NtUserSetWindowFNID` at `0x180012929`
- `win32u!NtUserShowWindow` at `0x18009932f`
- `win32u!NtUserShowWindow` at `0x18009932f`
- `win32u!NtUserSetWindowPos` at `0x1800993c4`
- `win32u!NtUserSetWindowPos` at `0x1800993c4`
- `win32u!NtUserSetFocus` at `0x1800128eb`
- `win32u!NtUserSetFocus` at `0x1800128eb`
- `win32u!NtUserMoveWindow` at `0x1800127d1`
- `win32u!NtUserMoveWindow` at `0x1800127d1`
- `win32u!NtUserGetSystemMenu` at `0x180012692`
- `win32u!NtUserGetSystemMenu` at `0x180012692`
- `win32u!NtUserDeleteMenu` at `0x1800991fe`
- `win32u!NtUserDeleteMenu` at `0x1800991fe`
- `win32u!NtUserChildWindowFromPointEx` at `0x180012a09`
- `win32u!NtUserChildWindowFromPointEx` at `0x180012a09`
- `ntdll!RtlFreeHeap` at `0x1800128b4`
- `ntdll!RtlFreeHeap` at `0x180012a89`
- `ntdll!RtlFreeHeap` at `0x1800128b4`
- `ntdll!RtlFreeHeap` at `0x180012a89`
- `ntdll!RtlAllocateHeap` at `0x1800127f1`
- `ntdll!RtlAllocateHeap` at `0x1800127f1`

## pseudocode

```c
__int64 __fastcall MDIClientWndProcWorker(HWND *a1, unsigned int a2, HWND a3, __int64 a4, unsigned int a5)
{
  HWND hWndParent; // rbx
  unsigned int *v10; // rsi
  __int64 result; // rax
  char *v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  HMENU v15; // r9
  int v16; // edx
  HMENU v17; // r8
  HWND v18; // rcx
  HWND v19; // rcx
  struct tagWND *v20; // rax
  int v21; // ebx
  int v22; // edi
  unsigned int DpiForSystem; // eax
  const CHAR *v24; // r15
  _QWORD *Heap; // rax
  _QWORD *v26; // rdi
  HWND v27; // rcx
  HWND v28; // rsi
  struct tagWND *v29; // rsi
  __int64 v30; // rcx
  HWND v31; // rdx
  void *v32; // r8
  PVOID v33; // rcx
  HWND v34; // rcx
  struct tagWND *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  HWND v38; // rax
  char *v39; // rax
  unsigned int v40; // eax
  unsigned int v41; // ecx
  __int64 v42; // rcx
  HMENU *v43; // rcx
  HMENU v44; // rcx
  unsigned int MenuItemCount; // edi
  unsigned int v46; // eax
  DWORD v47; // ecx
  DWORD v48; // r9d
  const CHAR *v49; // r8
  const CHAR *v50; // rdx
  struct tagWND *v51; // rax
  __int64 v52; // rdx
  struct tagWND *v53; // rax
  int X; // [rsp+20h] [rbp-88h]
  int Y; // [rsp+28h] [rbp-80h]
  int nWidth; // [rsp+30h] [rbp-78h]
  int nHeight; // [rsp+38h] [rbp-70h]
  HINSTANCE hInstance; // [rsp+50h] [rbp-58h]
  void *lpParam; // [rsp+58h] [rbp-50h]
  __int128 v60; // [rsp+60h] [rbp-48h] BYREF
  __int64 v61; // [rsp+B0h] [rbp+8h]
  __int16 v62; // [rsp+CAh] [rbp+22h]

  v62 = WORD1(a4);
  hWndParent = *a1;
  if ( *((_WORD *)a1 + 21) )
  {
    if ( *((_WORD *)a1 + 21) != 679 )
      return 0;
  }
  else
  {
    if ( *((_DWORD *)a1 + 50) < (int)*(unsigned __int16 *)(gpsi + 354) )
      return 0;
    NtUserSetWindowFNID(hWndParent, 679);
  }
  v10 = (unsigned int *)*((_QWORD *)a1[37] + 1);
  if ( !v10 && a2 != 1 && a2 != 528 && a2 != 544 && a2 != 549 )
    return DefWindowProcWorker((struct tagWND *)a1, a2, (unsigned __int64)a3, a4, a5);
  if ( a2 <= 0x221 )
  {
    if ( a2 == 545 )
    {
      xxxMDIDestroy((struct tagWND *)a1, a3);
      return 0;
    }
    if ( a2 > 0x70 )
    {
      if ( a2 == 134 )
      {
        v18 = (HWND)*((_QWORD *)v10 + 2);
        if ( v18 )
          SendMessageW(v18, 0x86u, (WPARAM)a3, a4);
        return DefWindowProcWorker((struct tagWND *)a1, a2, (unsigned __int64)a3, a4, a5);
      }
      if ( a2 == 276 || a2 == 277 )
      {
        v10[9] |= 3u;
        ScrollMDIChildren(hWndParent, a2 == 277, (unsigned __int16)a3, SWORD1(a3));
        *((_BYTE *)v10 + 36) = 0;
        return 0;
      }
      if ( a2 != 528 )
      {
        if ( a2 == 544 )
        {
          v47 = (_DWORD)a1[3] & 0x7000 | 0x40;
          v48 = *(_DWORD *)(a4 + 40);
          v49 = *(const CHAR **)(a4 + 8);
          v50 = *(const CHAR **)a4;
          lpParam = *(void **)(a4 + 48);
          hInstance = *(HINSTANCE *)(a4 + 16);
          nHeight = *(_DWORD *)(a4 + 36);
          nWidth = *(_DWORD *)(a4 + 32);
          Y = *(_DWORD *)(a4 + 28);
          X = *(_DWORD *)(a4 + 24);
          if ( a5 )
            return (__int64)CreateWindowExA(
                              v47,
                              v50,
                              v49,
                              v48,
                              X,
                              Y,
                              nWidth,
                              nHeight,
                              hWndParent,
                              0,
                              hInstance,
                              lpParam);
          else
            return (__int64)CreateWindowExW(
                              v47,
                              (LPCWSTR)v50,
                              (LPCWSTR)v49,
                              v48,
                              X,
                              Y,
                              nWidth,
                              nHeight,
                              hWndParent,
                              0,
                              hInstance,
                              lpParam);
        }
        return DefWindowProcWorker((struct tagWND *)a1, a2, (unsigned __int64)a3, a4, a5);
      }
      if ( a3 != (HWND)513 )
        return 0;
      v35 = ValidateHwnd(hWndParent);
      if ( !v35 )
        return 0;
      LODWORD(v61) = (__int16)a4;
      HIDWORD(v61) = v62;
      if ( (*((_BYTE *)v35 + 26) & 0x40) != 0 )
        LODWORD(v61) = *((_DWORD *)v35 + 28) - *((_DWORD *)v35 + 26) - (__int16)a4;
      v36 = NtUserChildWindowFromPointEx(hWndParent, v61, 3);
      if ( !v36 || (HWND)v36 == hWndParent || v36 == *((_QWORD *)v10 + 2) )
        return 0;
      v37 = v36;
LABEL_120:
      NtUserSetWindowPos(v37, 0, 0, 0, 0, 0, 3);
      return 0;
    }
    if ( a2 != 112 )
    {
      if ( a2 == 1 )
      {
        v24 = *(const CHAR **)a4;
        Heap = RtlAllocateHeap(pUserHeap, 8u, 0x38u);
        v26 = Heap;
        v27 = hWndParent;
        if ( Heap )
        {
          NtUserSetWindowLongPtr(hWndParent, 8, Heap, 0);
          v28 = a1[6];
          if ( v28 )
            v29 = (struct tagWND *)((char *)a1 + (char *)v28 - (char *)a1[1]);
          else
            v29 = 0;
          v26[2] = 0;
          v26[1] = 0;
          *(_DWORD *)v26 = 0;
          v26[3] = *(_QWORD *)v24;
          v26[4] = *((unsigned int *)v24 + 2);
          v30 = *((_QWORD *)v29 + 24);
          if ( v30 )
            v12 = (char *)v29 + v30 - *((_QWORD *)v29 + 1);
          else
            v12 = 0;
          v26[5] = TextAlloc(v12);
          v13 = *(_QWORD *)v29;
          v60 = 0;
          NtUserDefSetText(v13, 0);
          xxxSetFrameTitle(v29, (struct tagWND *)a1, (unsigned __int16 *)2);
          v14 = *((_DWORD *)v26 + 9);
          if ( (*((_BYTE *)a1 + 30) & 0x20) != 0 )
          {
            v14 |= 0x100u;
            *((_DWORD *)v26 + 9) = v14;
          }
          if ( (*((_BYTE *)a1 + 30) & 0x10) != 0 )
          {
            v14 |= 0x200u;
            *((_DWORD *)v26 + 9) = v14;
          }
          if ( v14 )
            ClearWindowState((struct tagWND *)a1, 0xE30u);
          NtUserGetSystemMenu(*(_QWORD *)v29, 0);
          if ( *((_DWORD *)v26 + 9) )
            NtUserUpdateClientRect(hWndParent);
          return 0;
        }
        goto LABEL_52;
      }
      if ( a2 != 2 )
      {
        switch ( a2 )
        {
          case 5u:
            v19 = (HWND)*((_QWORD *)v10 + 2);
            if ( v19 && (v20 = ValidateHwnd(v19)) != 0 && (*((_BYTE *)v20 + 31) & 1) != 0 )
            {
              v21 = *((_DWORD *)v20 + 6);
              v22 = *((_DWORD *)v20 + 7);
              DWORD2(v60) = (__int16)a4;
              HIDWORD(v60) = v62;
              *(_QWORD *)&v60 = 0;
              DpiForSystem = GetDpiForSystem();
              AdjustWindowRectExForDpi((unsigned int)&v60, v22, 0, v21, DpiForSystem);
              NtUserMoveWindow(
                *((_QWORD *)v10 + 2),
                (unsigned int)v60,
                DWORD1(v60),
                (unsigned int)(DWORD2(v60) - v60),
                HIDWORD(v60) - DWORD1(v60),
                1);
            }
            else
            {
              RecalculateScrollRanges((struct tagWND *)a1, 0);
            }
            return DefWindowProcWorker((struct tagWND *)a1, a2, (unsigned __int64)a3, a4, a5);
          case 7u:
            v34 = (HWND)*((_QWORD *)v10 + 2);
            if ( v34 && !IsIconic(v34) )
              NtUserSetFocus(*((_QWORD *)v10 + 2));
            break;
          case 0x3Fu:
            if ( !*((_BYTE *)v10 + 36) && (v10[9] & 0x300) != 0 )
            {
              CalcClientScrolling(hWndParent, v10[9] & 0x300, (int)a3);
              v10[9] &= ~0x800u;
            }
            break;
          default:
            return DefWindowProcWorker((struct tagWND *)a1, a2, (unsigned __int64)a3, a4, a5);
        }
        return 0;
      }
    }
    v31 = (HWND)*((_QWORD *)v10 + 1);
    if ( v31 )
    {
      v38 = a1[6];
      if ( v38 )
        v39 = (char *)a1 + (char *)v38 - (char *)a1[1];
      else
        v39 = 0;
      v42 = *((_QWORD *)v39 + 19);
      if ( v42 && (v43 = (HMENU *)&v39[v42 - *((_QWORD *)v39 + 1)]) != 0 )
        v44 = *v43;
      else
        v44 = 0;
      MDIRemoveSysMenu(v44, v31);
    }
    v32 = (void *)*((_QWORD *)v10 + 5);
    if ( v32 )
    {
      RtlFreeHeap(pUserHeap, 0, v32);
      *((_QWORD *)v10 + 5) = 0;
    }
    if ( IsMenu(*((HMENU *)v10 + 3)) )
    {
      v40 = *v10;
      v41 = *v10 + 1;
      *v10 = v41;
      if ( v40 )
      {
        if ( v41 > 0xB )
          *v10 = 11;
        MenuItemCount = GetMenuItemCount(*((HMENU *)v10 + 3));
        v46 = *v10;
        if ( *v10 )
        {
          do
          {
            --MenuItemCount;
            *v10 = v46 - 1;
            NtUserDeleteMenu(*((_QWORD *)v10 + 3), MenuItemCount, 1024);
            v46 = *v10;
          }
          while ( *v10 );
        }
        else
        {
          v46 = 0;
        }
        *v10 = v46 - 1;
      }
    }
    v33 = pUserHeap;
    *((_QWORD *)v10 + 1) = 0;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    RtlFreeHeap(v33, 0, v10);
    v27 = hWndParent;
LABEL_52:
    NtUserSetWindowFNID(v27, 0x4000);
    return 0;
  }
  if ( a2 <= 0x227 )
  {
    if ( a2 == 551 )
    {
      v10[9] |= 3u;
      NtUserShowScrollBar(hWndParent, 3);
      result = ArrangeWindows(hWndParent, (unsigned int)a3, 0, 0, 0, CascadeWindowsEnum);
      *((_BYTE *)v10 + 36) = 0;
      return result;
    }
    if ( a2 != 546 )
    {
      if ( a2 == 547 )
      {
        if ( !ValidateHwnd(a3) )
          return 0;
        v52 = 1;
        goto LABEL_110;
      }
      if ( a2 == 548 )
      {
        if ( !a3 )
          a3 = (HWND)*((_QWORD *)v10 + 2);
        v53 = ValidateHwnd(a3);
        if ( v53 )
          xxxMDINext((struct tagWND *)a1, v53, a4 != 0);
        return 0;
      }
      if ( a2 != 549 )
      {
        v10[9] |= 3u;
        NtUserShowScrollBar(hWndParent, 3);
        result = ArrangeWindows(
                   hWndParent,
                   (unsigned int)a3,
                   0,
                   0,
                   0,
                   (int (*)(HMONITOR, HDC, struct tagRECT *, __int64))TileWindowsEnum);
        *((_BYTE *)v10 + 36) = 0;
        return result;
      }
      v51 = ValidateHwnd(a3);
      if ( v51 && (*((_BYTE *)v51 + 30) & 1) != 0 )
      {
        v52 = 3;
LABEL_110:
        NtUserShowWindow(a3, v52);
        return 0;
      }
      return 0;
    }
    if ( !ValidateHwnd(a3) || *((_WORD *)v10 + 8) == (unsigned __int16)a3 )
      return 0;
    v37 = (__int64)a3;
    goto LABEL_120;
  }
  if ( a2 == 552 )
  {
    v10[9] |= 3u;
    NtUserArrangeIconicWindows(hWndParent);
    *((_BYTE *)v10 + 36) = 0;
    RecalculateScrollRanges((struct tagWND *)a1, 1);
    return 0;
  }
  if ( a2 != 553 )
  {
    if ( a2 == 560 )
    {
      v15 = (HMENU)a4;
      v17 = (HMENU)a3;
      v16 = 0;
      return (__int64)MDISetMenu((struct tagWND *)a1, v16, v17, v15);
    }
    if ( a2 == 564 )
    {
      v15 = 0;
      v16 = 1;
      v17 = 0;
      return (__int64)MDISetMenu((struct tagWND *)a1, v16, v17, v15);
    }
    return DefWindowProcWorker((struct tagWND *)a1, a2, (unsigned __int64)a3, a4, a5);
  }
  if ( a4 )
    *(_DWORD *)a4 = *((_QWORD *)v10 + 1) != 0;
  return *((_QWORD *)v10 + 2);
}

```

## disassembly

```asm
0x180012580  mov     [rsp+arg_8], rbx
0x180012585  mov     [rsp+arg_18], r9
0x18001258a  push    rbp
0x18001258b  push    rsi
0x18001258c  push    rdi
0x18001258d  push    r12
0x18001258f  push    r13
0x180012591  push    r14
0x180012593  push    r15
0x180012595  sub     rsp, 70h
0x180012599  mov     rbx, [rcx]
0x18001259c  xor     r13d, r13d
0x18001259f  mov     r15, r9
0x1800125a2  mov     rbp, r8
0x1800125a5  mov     r12d, edx
0x1800125a8  mov     r14, rcx
0x1800125ab  cmp     [rcx+2Ah], r13w
0x1800125b0  jz      loc_180012906
0x1800125b6  mov     edx, 2A7h
0x1800125bb  cmp     [rcx+2Ah], dx
0x1800125bf  jnz     loc_1800126A2
0x1800125c5  mov     rax, [r14+128h]
0x1800125cc  mov     rsi, [rax+8]
0x1800125d0  test    rsi, rsi
0x1800125d3  jz      loc_180012934
0x1800125d9  mov     eax, 221h
0x1800125de  cmp     r12d, eax
0x1800125e1  jbe     loc_1800126A9
0x1800125e7  mov     eax, 227h
0x1800125ec  cmp     r12d, eax
0x1800125ef  jbe     loc_180099291
0x1800125f5  mov     eax, r12d
0x1800125f8  sub     eax, 228h
0x1800125fd  jz      loc_180012B16
0x180012603  sub     eax, 1
0x180012606  jnz     loc_180012708
0x18001260c  test    r15, r15
0x18001260f  jnz     short loc_18001262D
0x180012611  mov     rax, [rsi+10h]
0x180012615  mov     rbx, [rsp+0A8h+arg_8]
0x18001261d  add     rsp, 70h
0x180012621  pop     r15
0x180012623  pop     r14
0x180012625  pop     r13
0x180012627  pop     r12
0x180012629  pop     rdi
0x18001262a  pop     rsi
0x18001262b  pop     rbp
0x18001262c  retn
0x18001262d  cmp     [rsi+8], r13
0x180012631  mov     eax, r13d
0x180012634  setnz   al
0x180012637  mov     [r15], eax
0x18001263a  jmp     short loc_180012611
0x18001263c  mov     rcx, r13; Src
0x18001263f  call    TextAlloc
0x180012644  mov     [rdi+28h], rax
0x180012648  xorps   xmm0, xmm0
0x18001264b  mov     rcx, [rsi]
0x18001264e  xor     edx, edx
0x180012650  movups  [rsp+0A8h+var_48], xmm0
0x180012655  call    cs:__imp_NtUserDefSetText
0x18001265b  mov     r8d, 2; unsigned __int16 *
0x180012661  mov     rdx, r14; struct tagWND *
0x180012664  mov     rcx, rsi; struct tagWND *
0x180012667  call    ?xxxSetFrameTitle@@YAXPEAUtagWND@@0PEAG@Z; xxxSetFrameTitle(tagWND *,tagWND *,ushort *)
0x18001266c  test    byte ptr [r14+1Eh], 20h
0x180012671  mov     eax, [rdi+24h]
0x180012674  jnz     loc_180012A33
0x18001267a  test    byte ptr [r14+1Eh], 10h
0x18001267f  jnz     loc_180012A3F
0x180012685  test    eax, eax
0x180012687  jnz     loc_180012A4B
0x18001268d  mov     rcx, [rsi]
0x180012690  xor     edx, edx
0x180012692  call    cs:__imp_NtUserGetSystemMenu
0x180012698  cmp     [rdi+24h], r13d
0x18001269c  jnz     loc_180012A5D
0x1800126a2  xor     eax, eax
0x1800126a4  jmp     loc_180012615
0x1800126a9  jz      loc_1800128F6
0x1800126af  cmp     r12d, 70h ; 'p'
0x1800126b3  ja      short loc_180012724
0x1800126b5  jz      loc_180012871
0x1800126bb  mov     eax, r12d
0x1800126be  sub     eax, 1
0x1800126c1  jz      loc_1800127DC
0x1800126c7  sub     eax, 1
0x1800126ca  jz      loc_180012871
0x1800126d0  sub     eax, 3
0x1800126d3  jz      short loc_18001274A
0x1800126d5  sub     eax, 2
0x1800126d8  jz      loc_1800128CD
0x1800126de  cmp     eax, 38h ; '8'
0x1800126e1  jz      loc_180012962
0x1800126e7  mov     eax, [rsp+0A8h+arg_20]
0x1800126ee  mov     r9, r15; __int64
0x1800126f1  mov     r8, rbp; unsigned __int64
0x1800126f4  mov     [rsp+0A8h+X], eax; unsigned int
0x1800126f8  mov     edx, r12d; unsigned int
0x1800126fb  mov     rcx, r14; struct tagWND *
0x1800126fe  call    ?DefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z; DefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)
0x180012703  jmp     loc_180012615
0x180012708  sub     eax, 7
0x18001270b  jz      loc_180012B01
0x180012711  cmp     eax, 4
0x180012714  jnz     short loc_1800126E7
0x180012716  xor     r9d, r9d
0x180012719  lea     edx, [rax-3]
0x18001271c  xor     r8d, r8d
0x18001271f  jmp     loc_180012B09
0x180012724  mov     eax, r12d
0x180012727  mov     edx, 86h; Msg
0x18001272c  sub     eax, edx
0x18001272e  jnz     loc_180012993
0x180012734  mov     rcx, [rsi+10h]; hWnd
0x180012738  test    rcx, rcx
0x18001273b  jz      short loc_1800126E7
0x18001273d  mov     r9, r15; lParam
0x180012740  mov     r8, rbp; wParam
0x180012743  call    SendMessageW
0x180012748  jmp     short loc_1800126E7
0x18001274a  mov     rcx, [rsi+10h]; HWND
0x18001274e  test    rcx, rcx
0x180012751  jz      loc_180012859
0x180012757  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18001275c  test    rax, rax
0x18001275f  jz      loc_180012859
0x180012765  test    byte ptr [rax+1Fh], 1
0x180012769  jz      loc_180012859
0x18001276f  mov     ebx, [rax+18h]
0x180012772  mov     edi, [rax+1Ch]
0x180012775  movsx   ecx, r15w
0x180012779  mov     dword ptr [rsp+0A8h+var_48+8], ecx
0x18001277d  movsx   ecx, word ptr [rsp+0A8h+arg_18+2]
0x180012785  mov     dword ptr [rsp+0A8h+var_48+0Ch], ecx
0x180012789  mov     qword ptr [rsp+0A8h+var_48], r13
0x18001278e  call    GetDpiForSystem
0x180012793  mov     r9d, ebx
0x180012796  mov     [rsp+0A8h+X], eax
0x18001279a  xor     r8d, r8d
0x18001279d  lea     rcx, [rsp+0A8h+var_48]
0x1800127a2  mov     edx, edi
0x1800127a4  call    _AdjustWindowRectExForDpi
0x1800127a9  mov     eax, dword ptr [rsp+0A8h+var_48+0Ch]
0x1800127ad  mov     r8d, dword ptr [rsp+0A8h+var_48+4]
0x1800127b2  sub     eax, r8d
0x1800127b5  mov     r9d, dword ptr [rsp+0A8h+var_48+8]
0x1800127ba  mov     edx, dword ptr [rsp+0A8h+var_48]
0x1800127be  sub     r9d, edx
0x1800127c1  mov     rcx, [rsi+10h]
0x1800127c5  mov     [rsp+0A8h+Y], 1
0x1800127cd  mov     [rsp+0A8h+X], eax
0x1800127d1  call    cs:__imp_NtUserMoveWindow
0x1800127d7  jmp     loc_1800126E7
0x1800127dc  mov     rcx, cs:pUserHeap; HeapHandle
0x1800127e3  mov     esi, 8
0x1800127e8  mov     r15, [r15]
0x1800127eb  mov     edx, esi; Flags
0x1800127ed  lea     r8d, [rsi+30h]; Size
0x1800127f1  call    cs:__imp_RtlAllocateHeap
0x1800127f7  mov     rdi, rax
0x1800127fa  mov     rcx, rbx
0x1800127fd  test    rax, rax
0x180012800  jz      loc_1800128BD
0x180012806  xor     r9d, r9d
0x180012809  mov     r8, rax
0x18001280c  mov     edx, esi
0x18001280e  call    cs:__imp_NtUserSetWindowLongPtr
0x180012814  mov     rsi, [r14+30h]
0x180012818  test    rsi, rsi
0x18001281b  jnz     short loc_180012868
0x18001281d  mov     rsi, r13
0x180012820  mov     [rdi+10h], r13
0x180012824  mov     [rdi+8], r13
0x180012828  mov     [rdi], r13d
0x18001282b  mov     rax, [r15]
0x18001282e  mov     [rdi+18h], rax
0x180012832  mov     eax, [r15+8]
0x180012836  mov     [rdi+20h], eax
0x180012839  mov     [rdi+24h], r13d
0x18001283d  mov     rcx, [rsi+0C0h]
0x180012844  test    rcx, rcx
0x180012847  jz      loc_18001263C
0x18001284d  sub     rcx, [rsi+8]
0x180012851  add     rcx, rsi
0x180012854  jmp     loc_18001263F
0x180012859  xor     edx, edx; int
0x18001285b  mov     rcx, r14; struct tagWND *
0x18001285e  call    ?RecalculateScrollRanges@@YAXPEAUtagWND@@H@Z; RecalculateScrollRanges(tagWND *,int)
0x180012863  jmp     loc_1800126E7
0x180012868  sub     rsi, [r14+8]
0x18001286c  add     rsi, r14
0x18001286f  jmp     short loc_180012820
0x180012871  mov     rdx, [rsi+8]; HWND
0x180012875  test    rdx, rdx
0x180012878  jnz     loc_180012A6B
0x18001287e  mov     r8, [rsi+28h]; P
0x180012882  test    r8, r8
0x180012885  jnz     loc_180012A80
0x18001288b  mov     rcx, [rsi+18h]; hMenu
0x18001288f  call    IsMenu
0x180012894  test    eax, eax
0x180012896  jnz     loc_180012A98
0x18001289c  mov     rcx, cs:pUserHeap; HeapHandle
0x1800128a3  mov     r8, rsi; P
0x1800128a6  xor     edx, edx; Flags
0x1800128a8  mov     [rsi+8], r13
0x1800128ac  mov     [rsi+10h], r13
0x1800128b0  mov     [rsi+18h], r13
0x1800128b4  call    cs:__imp_RtlFreeHeap
0x1800128ba  mov     rcx, rbx
0x1800128bd  mov     edx, 4000h
0x1800128c2  call    cs:__imp_NtUserSetWindowFNID
0x1800128c8  jmp     loc_1800126A2
0x1800128cd  mov     rcx, [rsi+10h]; hWnd
0x1800128d1  test    rcx, rcx
0x1800128d4  jz      loc_1800126A2
0x1800128da  call    IsIconic
0x1800128df  test    eax, eax
0x1800128e1  jnz     loc_1800126A2
0x1800128e7  mov     rcx, [rsi+10h]
0x1800128eb  call    cs:__imp_NtUserSetFocus
0x1800128f1  jmp     loc_1800126A2
0x1800128f6  mov     rdx, rbp; HWND
0x1800128f9  mov     rcx, r14; struct tagWND *
0x1800128fc  call    ?xxxMDIDestroy@@YAXPEAUtagWND@@PEAUHWND__@@@Z; xxxMDIDestroy(tagWND *,HWND__ *)
0x180012901  jmp     loc_1800126A2
0x180012906  mov     rax, cs:gpsi
0x18001290d  movzx   ecx, word ptr [rax+162h]
0x180012914  cmp     [r14+0C8h], ecx
0x18001291b  jl      loc_1800126A2
0x180012921  mov     edx, 2A7h
0x180012926  mov     rcx, rbx
0x180012929  call    cs:__imp_NtUserSetWindowFNID
0x18001292f  jmp     loc_1800125C5
0x180012934  mov     eax, r12d
0x180012937  sub     eax, 1
0x18001293a  jz      loc_1800125D9
0x180012940  sub     eax, 20Fh
0x180012945  jz      loc_1800125D9
0x18001294b  sub     eax, 10h
0x18001294e  jz      loc_1800125D9
0x180012954  cmp     eax, 5
0x180012957  jnz     loc_1800126E7
0x18001295d  jmp     loc_1800125D9
0x180012962  cmp     [rsi+24h], r13b
0x180012966  jnz     loc_1800126A2
0x18001296c  mov     eax, 300h
0x180012971  and     ax, [rsi+24h]
0x180012975  jz      loc_1800126A2
0x18001297b  mov     r8d, ebp; int
0x18001297e  movzx   edx, ax; unsigned int
0x180012981  mov     rcx, rbx; HWND
0x180012984  call    ?CalcClientScrolling@@YAXPEAUHWND__@@IH@Z; CalcClientScrolling(HWND__ *,uint,int)
0x180012989  btr     dword ptr [rsi+24h], 0Bh
0x18001298e  jmp     loc_1800126A2
0x180012993  sub     eax, 8Eh
0x180012998  jz      loc_180012AD0
0x18001299e  sub     eax, 1
0x1800129a1  jz      loc_180012AD0
0x1800129a7  sub     eax, 0FBh
0x1800129ac  jnz     loc_180099213
0x1800129b2  cmp     rbp, 201h
0x1800129b9  jnz     loc_1800126A2
0x1800129bf  mov     rcx, rbx; HWND
0x1800129c2  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800129c7  mov     rdx, rax
0x1800129ca  test    rax, rax
0x1800129cd  jz      loc_1800126A2
0x1800129d3  test    byte ptr [rax+1Ah], 40h
0x1800129d7  movsx   ecx, word ptr [rsp+0A8h+arg_18+2]
0x1800129df  movsx   r8d, r15w
0x1800129e3  mov     dword ptr [rsp+0A8h+arg_0], r8d
0x1800129eb  mov     dword ptr [rsp+0A8h+arg_0+4], ecx
0x1800129f2  jnz     loc_180012ABB
0x1800129f8  mov     rdx, [rsp+0A8h+arg_0]
0x180012a00  mov     r8d, 3
0x180012a06  mov     rcx, rbx
0x180012a09  call    cs:__imp_NtUserChildWindowFromPointEx
0x180012a0f  test    rax, rax
0x180012a12  jz      loc_1800126A2
0x180012a18  cmp     rax, rbx
0x180012a1b  jz      loc_1800126A2
0x180012a21  cmp     rax, [rsi+10h]
0x180012a25  jz      loc_1800126A2
0x180012a2b  mov     rcx, rax
0x180012a2e  jmp     loc_1800993AA
0x180012a33  bts     eax, 8
0x180012a37  mov     [rdi+24h], eax
0x180012a3a  jmp     loc_18001267A
0x180012a3f  bts     eax, 9
0x180012a43  mov     [rdi+24h], eax
0x180012a46  jmp     loc_180012685
0x180012a4b  mov     edx, 0E30h; unsigned int
0x180012a50  mov     rcx, r14; struct tagWND *
0x180012a53  call    ?ClearWindowState@@YAXPEAUtagWND@@I@Z; ClearWindowState(tagWND *,uint)
0x180012a58  jmp     loc_18001268D
0x180012a5d  mov     rcx, rbx
0x180012a60  call    cs:__imp_NtUserUpdateClientRect
  ... truncated ...
```
