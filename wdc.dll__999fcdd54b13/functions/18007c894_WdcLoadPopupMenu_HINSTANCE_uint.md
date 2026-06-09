# WdcLoadPopupMenu(HINSTANCE__ *,uint)

- ea: `0x18007c894`
- end: `0x18007c8f3`
- name: `?WdcLoadPopupMenu@@YAPEAUHMENU__@@PEAUHINSTANCE__@@I@Z`
- size: `95`
- prototype: `HMENU __fastcall(HINSTANCE, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180021c10`
- `0x1800715f0`

## callees

- `0x18007c894`

## import_xrefs

- `USER32!RemoveMenu` at `0x18007c8d6`
- `USER32!RemoveMenu` at `0x18007c8d6`
- `USER32!DestroyMenu` at `0x18007c8df`
- `USER32!DestroyMenu` at `0x18007c8df`
- `USER32!GetSubMenu` at `0x18007c8bd`
- `USER32!GetSubMenu` at `0x18007c8bd`
- `USER32!LoadMenuW` at `0x18007c8aa`
- `USER32!LoadMenuW` at `0x18007c8aa`

## pseudocode

```c
HMENU __fastcall WdcLoadPopupMenu(HINSTANCE a1, unsigned __int16 a2)
{
  HMENU SubMenu; // rdi
  HMENU MenuW; // rax
  HMENU v4; // rbx

  SubMenu = 0;
  MenuW = LoadMenuW(g_hInstance, (LPCWSTR)a2);
  v4 = MenuW;
  if ( MenuW )
  {
    SubMenu = GetSubMenu(MenuW, 0);
    if ( SubMenu )
      RemoveMenu(v4, 0, 0x400u);
    DestroyMenu(v4);
  }
  return SubMenu;
}

```

## disassembly

```asm
0x18007c894  mov     [rsp+arg_0], rbx
0x18007c899  push    rdi
0x18007c89a  sub     rsp, 20h
0x18007c89e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18007c8a5  xor     edi, edi
0x18007c8a7  movzx   edx, dx; lpMenuName
0x18007c8aa  call    cs:__imp_LoadMenuW
0x18007c8b0  mov     rbx, rax
0x18007c8b3  test    rax, rax
0x18007c8b6  jz      short loc_18007C8E5
0x18007c8b8  xor     edx, edx; nPos
0x18007c8ba  mov     rcx, rax; hMenu
0x18007c8bd  call    cs:__imp_GetSubMenu
0x18007c8c3  mov     rdi, rax
0x18007c8c6  test    rax, rax
0x18007c8c9  jz      short loc_18007C8DC
0x18007c8cb  xor     edx, edx; uPosition
0x18007c8cd  mov     r8d, 400h; uFlags
0x18007c8d3  mov     rcx, rbx; hMenu
0x18007c8d6  call    cs:__imp_RemoveMenu
0x18007c8dc  mov     rcx, rbx; hMenu
0x18007c8df  call    cs:__imp_DestroyMenu
0x18007c8e5  mov     rbx, [rsp+28h+arg_0]
0x18007c8ea  mov     rax, rdi
0x18007c8ed  add     rsp, 20h
0x18007c8f1  pop     rdi
0x18007c8f2  retn
```
