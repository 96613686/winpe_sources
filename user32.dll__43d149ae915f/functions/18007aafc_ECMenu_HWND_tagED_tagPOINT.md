# ECMenu(HWND__ *,tagED *,tagPOINT *)

- ea: `0x18007aafc`
- end: `0x18007ae1d`
- name: `?ECMenu@@YAXPEAUHWND__@@PEAUtagED@@PEAUtagPOINT@@@Z`
- size: `801`
- prototype: `void __fastcall(HWND, struct tagED *, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180033af0`

## callees

- `0x18000cf20`
- `0x180016cc0`
- `0x180016d50`
- `0x180016de0`
- `0x1800309a0`
- `0x180034c90`
- `0x18007a70c`
- `0x18007aafc`
- `0x18007ae24`
- `0x18007b4c0`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserIsClipboardFormatAvailable` at `0x18007abc1`
- `win32u!NtUserIsClipboardFormatAvailable` at `0x18007abc1`
- `win32u!NtUserTrackPopupMenuEx` at `0x18007ada5`
- `win32u!NtUserTrackPopupMenuEx` at `0x18007ada5`
- `win32u!NtUserSetFocus` at `0x18007ab55`
- `win32u!NtUserSetFocus` at `0x18007ab55`
- `win32u!NtUserDestroyMenu` at `0x18007adb0`
- `win32u!NtUserDestroyMenu` at `0x18007adb0`
- `win32u!NtUserDeleteMenu` at `0x18007ac74`
- `win32u!NtUserDeleteMenu` at `0x18007ac85`
- `win32u!NtUserDeleteMenu` at `0x18007ac96`
- `win32u!NtUserDeleteMenu` at `0x18007acc7`
- `win32u!NtUserDeleteMenu` at `0x18007ac74`
- `win32u!NtUserDeleteMenu` at `0x18007ac85`
- `win32u!NtUserDeleteMenu` at `0x18007ac96`
- `win32u!NtUserDeleteMenu` at `0x18007acc7`

## pseudocode

```c
void __fastcall ECMenu(HWND a1, struct tagED *a2, struct tagPOINT *a3)
{
  int v6; // edi
  HMENU MenuW; // rax
  HMENU v8; // rbp
  _DWORD *v9; // r15
  _DWORD *v10; // r14
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rdx
  HMENU SubMenu; // rdi
  int MenuItemCount; // eax
  int v16; // edi
  unsigned int x; // r14d
  unsigned int y; // r15d
  __int64 v19; // rdx
  unsigned int v20; // ebx
  HMENU v21; // rax
  UINT v22; // ebx
  __int64 v23; // rax
  LPARAM v24; // r9
  struct tagRECT Rect; // [rsp+30h] [rbp-58h] BYREF

  if ( (*(_BYTE *)gpsi & 4) == 0
    || (v6 = 14, !((unsigned int (__fastcall *)(SIZE_T))off_1800C85E0[0])(NtCurrentTeb()->Win32ClientInfo[18])) )
  {
    v6 = 6;
  }
  if ( (*((_BYTE *)a2 + 116) & 8) == 0 )
    NtUserSetFocus(a1);
  MenuW = LoadMenuW(hmodUser, (LPCWSTR)1);
  v8 = MenuW;
  if ( MenuW )
  {
    if ( !*((_DWORD *)a2 + 40) )
      EnableMenuItem(MenuW, 0x304u, 3u);
    if ( (*((_DWORD *)a2 + 29) & 0x80000) != 0 || *((_DWORD *)a2 + 13) )
    {
      v9 = (_DWORD *)((char *)a2 + 28);
      v10 = (_DWORD *)((char *)a2 + 24);
    }
    else
    {
      v9 = (_DWORD *)((char *)a2 + 28);
      v10 = (_DWORD *)((char *)a2 + 24);
      if ( *((_DWORD *)a2 + 6) != *((_DWORD *)a2 + 7) )
        goto LABEL_15;
    }
    v6 |= 1u;
LABEL_15:
    v11 = v6 & 0xFFFFFFFD;
    if ( !(unsigned int)NtUserIsClipboardFormatAvailable(1) )
      v11 = v6;
    if ( (v11 & 1) != 0 )
    {
      EnableMenuItem(v8, 0x300u, 3u);
      EnableMenuItem(v8, 0x303u, 3u);
    }
    if ( (v11 & 2) != 0 )
      EnableMenuItem(v8, 0x302u, 3u);
    if ( *v10 == *v9 || *((_DWORD *)a2 + 13) )
      EnableMenuItem(v8, 0x301u, 3u);
    if ( !*v10 && *v9 == *((_DWORD *)a2 + 4) )
      EnableMenuItem(v8, 0xB1u, 3u);
    v12 = *((_QWORD *)a2 + 36);
    if ( v12 )
    {
      (*(void (__fastcall **)(struct tagED *, HMENU))(v12 + 80))(a2, v8);
    }
    else
    {
      NtUserDeleteMenu(v8, 32769, 0);
      NtUserDeleteMenu(v8, 0x8000, 0);
      NtUserDeleteMenu(v8, 32787, 0);
      if ( v11 < 8 )
      {
        SubMenu = GetSubMenu(v8, 0);
        MenuItemCount = GetMenuItemCount(SubMenu);
        NtUserDeleteMenu(SubMenu, (unsigned int)(MenuItemCount - 1), 1024);
      }
      else
      {
        v11 &= ~4u;
      }
    }
    v16 = v11 & 8;
    if ( (v11 & 8) != 0 )
      ECSetIMEMenu(v8, a1, v11);
    x = a3->x;
    if ( *a3 == -1 )
    {
      Rect = 0;
      GetWindowRect(a1, &Rect);
      x = Rect.left + (Rect.right - Rect.left) / 2;
      v13 = (unsigned int)((Rect.bottom - Rect.top) >> 31);
      LODWORD(v13) = (Rect.bottom - Rect.top) % 2;
      y = Rect.top + (Rect.bottom - Rect.top) / 2;
    }
    else
    {
      y = a3->y;
    }
    if ( (unsigned int)IS_UI_LANGID(1025, v13)
      || *(_WORD *)(gpsi + 7012) == 1025
      || (unsigned int)IS_UI_LANGID(1037, v19)
      || (v20 = 386, *(_WORD *)(gpsi + 7012) == 1037) )
    {
      v20 = 33154;
    }
    v21 = GetSubMenu(v8, 0);
    v22 = NtUserTrackPopupMenuEx(v21, v20, x, y, a1, 0);
    NtUserDestroyMenu(v8);
    if ( v22 + 1 > 1 )
    {
      v23 = *((_QWORD *)a2 + 36);
      if ( v23 )
        (*(void (__fastcall **)(struct tagED *, _QWORD))(v23 + 88))(a2, v22);
      if ( !v16 || !(unsigned int)ECDoIMEMenuCommand(a2, v22, a1) )
      {
        v24 = 0xFFFFFFFFLL;
        if ( v22 != 177 )
          v24 = 0;
        SendMessageW(a1, v22, 0, v24);
      }
    }
  }
}

```

## disassembly

```asm
0x18007aafc  push    rbx
0x18007aafe  push    rbp
0x18007aaff  push    rsi
0x18007ab00  push    rdi
0x18007ab01  push    r12
0x18007ab03  push    r13
0x18007ab05  push    r14
0x18007ab07  push    r15
0x18007ab09  sub     rsp, 48h
0x18007ab0d  mov     rax, cs:gpsi
0x18007ab14  mov     r13, r8
0x18007ab17  mov     rsi, rdx
0x18007ab1a  mov     r12, rcx
0x18007ab1d  test    byte ptr [rax], 4
0x18007ab20  jz      short loc_18007AB47
0x18007ab22  mov     rcx, gs:30h
0x18007ab2b  mov     rax, cs:off_1800C85E0
0x18007ab32  mov     rcx, [rcx+890h]
0x18007ab39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab3e  mov     edi, 0Eh
0x18007ab43  test    eax, eax
0x18007ab45  jnz     short loc_18007AB4C
0x18007ab47  mov     edi, 6
0x18007ab4c  test    byte ptr [rsi+74h], 8
0x18007ab50  jnz     short loc_18007AB5B
0x18007ab52  mov     rcx, r12
0x18007ab55  call    cs:__imp_NtUserSetFocus
0x18007ab5b  mov     rcx, cs:hmodUser; hInstance
0x18007ab62  mov     ebx, 1
0x18007ab67  mov     edx, ebx; lpMenuName
0x18007ab69  call    LoadMenuW
0x18007ab6e  mov     rbp, rax
0x18007ab71  test    rax, rax
0x18007ab74  jz      loc_18007AE0C
0x18007ab7a  cmp     dword ptr [rsi+0A0h], 0
0x18007ab81  jnz     short loc_18007AB94
0x18007ab83  mov     edx, 304h; uIDEnableItem
0x18007ab88  lea     r8d, [rbx+2]; uEnable
0x18007ab8c  mov     rcx, rax; hMenu
0x18007ab8f  call    EnableMenuItem
0x18007ab94  test    dword ptr [rsi+74h], 80000h
0x18007ab9b  jnz     short loc_18007ABB5
0x18007ab9d  cmp     dword ptr [rsi+34h], 0
0x18007aba1  jnz     short loc_18007ABB5
0x18007aba3  lea     r15, [rsi+1Ch]
0x18007aba7  mov     eax, [r15]
0x18007abaa  lea     r14, [rsi+18h]
0x18007abae  cmp     [r14], eax
0x18007abb1  jz      short loc_18007ABBD
0x18007abb3  jmp     short loc_18007ABBF
0x18007abb5  lea     r15, [rsi+1Ch]
0x18007abb9  lea     r14, [rsi+18h]
0x18007abbd  or      edi, ebx
0x18007abbf  mov     ecx, ebx
0x18007abc1  call    cs:__imp_NtUserIsClipboardFormatAvailable
0x18007abc7  mov     ebx, edi
0x18007abc9  and     ebx, 0FFFFFFFDh
0x18007abcc  test    eax, eax
0x18007abce  cmovz   ebx, edi
0x18007abd1  mov     edi, 3
0x18007abd6  test    bl, 1
0x18007abd9  jz      short loc_18007ABFB
0x18007abdb  mov     r8d, edi; uEnable
0x18007abde  mov     edx, 300h; uIDEnableItem
0x18007abe3  mov     rcx, rbp; hMenu
0x18007abe6  call    EnableMenuItem
0x18007abeb  mov     r8d, edi; uEnable
0x18007abee  mov     edx, 303h; uIDEnableItem
0x18007abf3  mov     rcx, rbp; hMenu
0x18007abf6  call    EnableMenuItem
0x18007abfb  test    bl, 2
0x18007abfe  jz      short loc_18007AC10
0x18007ac00  mov     r8d, edi; uEnable
0x18007ac03  mov     edx, 302h; uIDEnableItem
0x18007ac08  mov     rcx, rbp; hMenu
0x18007ac0b  call    EnableMenuItem
0x18007ac10  mov     eax, [r15]
0x18007ac13  cmp     [r14], eax
0x18007ac16  jz      short loc_18007AC1E
0x18007ac18  cmp     dword ptr [rsi+34h], 0
0x18007ac1c  jz      short loc_18007AC2E
0x18007ac1e  mov     r8d, edi; uEnable
0x18007ac21  mov     edx, 301h; uIDEnableItem
0x18007ac26  mov     rcx, rbp; hMenu
0x18007ac29  call    EnableMenuItem
0x18007ac2e  cmp     dword ptr [r14], 0
0x18007ac32  jnz     short loc_18007AC4C
0x18007ac34  mov     eax, [rsi+10h]
0x18007ac37  cmp     [r15], eax
0x18007ac3a  jnz     short loc_18007AC4C
0x18007ac3c  mov     r8d, edi; uEnable
0x18007ac3f  mov     edx, 0B1h; uIDEnableItem
0x18007ac44  mov     rcx, rbp; hMenu
0x18007ac47  call    EnableMenuItem
0x18007ac4c  mov     rax, [rsi+120h]
0x18007ac53  test    rax, rax
0x18007ac56  jz      short loc_18007AC69
0x18007ac58  mov     rax, [rax+50h]
0x18007ac5c  mov     rdx, rbp
0x18007ac5f  mov     rcx, rsi
0x18007ac62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac67  jmp     short loc_18007ACCD
0x18007ac69  xor     r8d, r8d
0x18007ac6c  mov     edx, 8001h
0x18007ac71  mov     rcx, rbp
0x18007ac74  call    cs:__imp_NtUserDeleteMenu
0x18007ac7a  xor     r8d, r8d
0x18007ac7d  mov     edx, 8000h
0x18007ac82  mov     rcx, rbp
0x18007ac85  call    cs:__imp_NtUserDeleteMenu
0x18007ac8b  xor     r8d, r8d
0x18007ac8e  mov     edx, 8013h
0x18007ac93  mov     rcx, rbp
0x18007ac96  call    cs:__imp_NtUserDeleteMenu
0x18007ac9c  cmp     ebx, 8
0x18007ac9f  jb      short loc_18007ACA6
0x18007aca1  and     ebx, 0FFFFFFFBh
0x18007aca4  jmp     short loc_18007ACCD
0x18007aca6  xor     edx, edx; nPos
0x18007aca8  mov     rcx, rbp; hMenu
0x18007acab  call    GetSubMenu
0x18007acb0  mov     rcx, rax; hMenu
0x18007acb3  mov     rdi, rax
0x18007acb6  call    GetMenuItemCount
0x18007acbb  mov     r8d, 400h
0x18007acc1  mov     rcx, rdi
0x18007acc4  lea     edx, [rax-1]
0x18007acc7  call    cs:__imp_NtUserDeleteMenu
0x18007accd  mov     edi, ebx
0x18007accf  and     edi, 8
0x18007acd2  jz      short loc_18007ACE2
0x18007acd4  mov     r8d, ebx
0x18007acd7  mov     rdx, r12
0x18007acda  mov     rcx, rbp
0x18007acdd  call    ?ECSetIMEMenu@@YAHPEAUHMENU__@@PEAUHWND__@@UEditMenuItemState@@@Z; ECSetIMEMenu(HMENU__ *,HWND__ *,EditMenuItemState)
0x18007ace2  mov     r14d, [r13+0]
0x18007ace6  cmp     r14d, 0FFFFFFFFh
0x18007acea  jnz     short loc_18007AD33
0x18007acec  cmp     [r13+4], r14d
0x18007acf0  jnz     short loc_18007AD33
0x18007acf2  xorps   xmm0, xmm0
0x18007acf5  lea     rdx, [rsp+88h+Rect]; lpRect
0x18007acfa  mov     rcx, r12; hWnd
0x18007acfd  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x18007ad02  call    GetWindowRect
0x18007ad07  mov     eax, [rsp+88h+Rect.right]
0x18007ad0b  lea     ecx, [r14+3]
0x18007ad0f  sub     eax, [rsp+88h+Rect.left]
0x18007ad13  cdq
0x18007ad14  idiv    ecx
0x18007ad16  mov     r14d, eax
0x18007ad19  mov     eax, [rsp+88h+Rect.bottom]
0x18007ad1d  sub     eax, [rsp+88h+Rect.top]
0x18007ad21  add     r14d, [rsp+88h+Rect.left]
0x18007ad26  cdq
0x18007ad27  idiv    ecx
0x18007ad29  mov     r15d, eax
0x18007ad2c  add     r15d, [rsp+88h+Rect.top]
0x18007ad31  jmp     short loc_18007AD37
0x18007ad33  mov     r15d, [r13+4]
0x18007ad37  mov     ebx, 401h
0x18007ad3c  mov     ecx, ebx
0x18007ad3e  call    IS_UI_LANGID
0x18007ad43  test    eax, eax
0x18007ad45  jnz     short loc_18007AD7D
0x18007ad47  mov     rax, cs:gpsi
0x18007ad4e  cmp     [rax+1B64h], bx
0x18007ad55  jz      short loc_18007AD7D
0x18007ad57  lea     r13d, [rbx+0Ch]
0x18007ad5b  mov     ecx, r13d
0x18007ad5e  call    IS_UI_LANGID
0x18007ad63  test    eax, eax
0x18007ad65  jnz     short loc_18007AD7D
0x18007ad67  mov     rax, cs:gpsi
0x18007ad6e  mov     ebx, 182h
0x18007ad73  cmp     [rax+1B64h], r13w
0x18007ad7b  jnz     short loc_18007AD82
0x18007ad7d  mov     ebx, 8182h
0x18007ad82  xor     edx, edx; nPos
0x18007ad84  mov     rcx, rbp; hMenu
0x18007ad87  call    GetSubMenu
0x18007ad8c  mov     rcx, rax
0x18007ad8f  mov     [rsp+88h+var_60], 0
0x18007ad98  mov     r9d, r15d
0x18007ad9b  mov     [rsp+88h+var_68], r12
0x18007ada0  mov     r8d, r14d
0x18007ada3  mov     edx, ebx
0x18007ada5  call    cs:__imp_NtUserTrackPopupMenuEx
0x18007adab  mov     rcx, rbp
0x18007adae  mov     ebx, eax
0x18007adb0  call    cs:__imp_NtUserDestroyMenu
0x18007adb6  lea     ecx, [rbx+1]
0x18007adb9  cmp     ecx, 1
0x18007adbc  jbe     short loc_18007AE0C
0x18007adbe  mov     rax, [rsi+120h]
0x18007adc5  test    rax, rax
0x18007adc8  jz      short loc_18007ADD8
0x18007adca  mov     rax, [rax+58h]
0x18007adce  mov     edx, ebx
0x18007add0  mov     rcx, rsi
0x18007add3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007add8  test    edi, edi
0x18007adda  jz      short loc_18007ADED
0x18007addc  mov     r8, r12; HWND
0x18007addf  mov     edx, ebx; int
0x18007ade1  mov     rcx, rsi; struct tagED *
0x18007ade4  call    ?ECDoIMEMenuCommand@@YAHPEAUtagED@@HPEAUHWND__@@@Z; ECDoIMEMenuCommand(tagED *,int,HWND__ *)
0x18007ade9  test    eax, eax
0x18007adeb  jnz     short loc_18007AE0C
0x18007aded  xor     eax, eax
0x18007adef  mov     r9d, 0FFFFFFFFh
0x18007adf5  cmp     ebx, 0B1h
0x18007adfb  mov     edx, ebx; Msg
0x18007adfd  mov     rcx, r12; hWnd
0x18007ae00  cmovnz  r9d, eax; lParam
0x18007ae04  xor     r8d, r8d; wParam
0x18007ae07  call    SendMessageW
0x18007ae0c  add     rsp, 48h
0x18007ae10  pop     r15
0x18007ae12  pop     r14
0x18007ae14  pop     r13
0x18007ae16  pop     r12
0x18007ae18  pop     rdi
0x18007ae19  pop     rsi
0x18007ae1a  pop     rbp
0x18007ae1b  pop     rbx
0x18007ae1c  retn
```
