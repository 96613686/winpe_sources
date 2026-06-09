# MergePopupMenu

- ea: `0x18001cf7c`
- end: `0x18001d030`
- name: `MergePopupMenu`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f620`

## callees

- `0x18001cf7c`

## import_xrefs

- `USER32!CreatePopupMenu` at `0x18001cf93`
- `USER32!CreatePopupMenu` at `0x18001cf93`
- `USER32!RemoveMenu` at `0x18001cfd8`
- `USER32!RemoveMenu` at `0x18001cfd8`
- `USER32!GetSubMenu` at `0x18001cfc4`
- `USER32!GetSubMenu` at `0x18001cfc4`
- `USER32!DestroyMenu` at `0x18001cfe1`
- `USER32!DestroyMenu` at `0x18001d01b`
- `USER32!DestroyMenu` at `0x18001cfe1`
- `USER32!DestroyMenu` at `0x18001d01b`
- `USER32!LoadMenuW` at `0x18001cfb1`
- `USER32!LoadMenuW` at `0x18001cfb1`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18001d010`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18001d010`

## pseudocode

```c
__int64 __fastcall MergePopupMenu(
        HMENU *a1,
        unsigned __int16 a2,
        __int64 a3,
        UINT a4,
        UINT uIDAdjust,
        UINT uIDAdjustMax)
{
  HMENU PopupMenu; // rax
  HMENU MenuW; // rax
  HMENU v11; // rdi
  HMENU SubMenu; // rbp
  UINT v13; // ebx

  if ( !*a1 )
  {
    PopupMenu = CreatePopupMenu();
    *a1 = PopupMenu;
    if ( !PopupMenu )
      return 0;
    a4 = 0;
  }
  MenuW = LoadMenuW(g_hinstMUI, (LPCWSTR)a2);
  v11 = MenuW;
  if ( MenuW )
  {
    SubMenu = GetSubMenu(MenuW, 0);
    RemoveMenu(v11, 0, 0x400u);
    DestroyMenu(v11);
    if ( SubMenu )
    {
      v13 = Shell_MergeMenus(*a1, SubMenu, a4, uIDAdjust, uIDAdjustMax, 1u);
      DestroyMenu(SubMenu);
      return v13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001cf7c  push    rbx
0x18001cf7e  push    rbp
0x18001cf7f  push    rsi
0x18001cf80  push    rdi
0x18001cf81  sub     rsp, 38h
0x18001cf85  cmp     qword ptr [rcx], 0
0x18001cf89  mov     esi, r9d
0x18001cf8c  mov     edi, edx
0x18001cf8e  mov     rbx, rcx
0x18001cf91  jnz     short loc_18001CFA7
0x18001cf93  call    cs:__imp_CreatePopupMenu
0x18001cf99  mov     [rbx], rax
0x18001cf9c  test    rax, rax
0x18001cf9f  jz      loc_18001D025
0x18001cfa5  xor     esi, esi
0x18001cfa7  mov     rcx, cs:g_hinstMUI; hInstance
0x18001cfae  movzx   edx, di; lpMenuName
0x18001cfb1  call    cs:__imp_LoadMenuW
0x18001cfb7  mov     rdi, rax
0x18001cfba  test    rax, rax
0x18001cfbd  jz      short loc_18001D025
0x18001cfbf  xor     edx, edx; nPos
0x18001cfc1  mov     rcx, rax; hMenu
0x18001cfc4  call    cs:__imp_GetSubMenu
0x18001cfca  xor     edx, edx; uPosition
0x18001cfcc  mov     r8d, 400h; uFlags
0x18001cfd2  mov     rcx, rdi; hMenu
0x18001cfd5  mov     rbp, rax
0x18001cfd8  call    cs:__imp_RemoveMenu
0x18001cfde  mov     rcx, rdi; hMenu
0x18001cfe1  call    cs:__imp_DestroyMenu
0x18001cfe7  test    rbp, rbp
0x18001cfea  jz      short loc_18001D025
0x18001cfec  mov     ecx, [rsp+58h+arg_28]
0x18001cff3  mov     r8d, esi; uInsert
0x18001cff6  mov     r9d, [rsp+58h+uIDAdjust]; uIDAdjust
0x18001cffe  mov     rdx, rbp; hmSrc
0x18001d001  mov     [rsp+58h+uFlags], 1; uFlags
0x18001d009  mov     [rsp+58h+uIDAdjustMax], ecx; uIDAdjustMax
0x18001d00d  mov     rcx, [rbx]; hmDst
0x18001d010  call    cs:__imp_Shell_MergeMenus
0x18001d016  mov     rcx, rbp; hMenu
0x18001d019  mov     ebx, eax
0x18001d01b  call    cs:__imp_DestroyMenu
0x18001d021  mov     eax, ebx
0x18001d023  jmp     short loc_18001D027
0x18001d025  xor     eax, eax
0x18001d027  add     rsp, 38h
0x18001d02b  pop     rdi
0x18001d02c  pop     rsi
0x18001d02d  pop     rbp
0x18001d02e  pop     rbx
0x18001d02f  retn
```
