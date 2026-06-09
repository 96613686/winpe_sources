# SHLoadMenuPopup

- ea: `0x180024ef0`
- end: `0x180024f48`
- name: `SHLoadMenuPopup`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180024ef0`

## import_xrefs

- `USER32!DestroyMenu` at `0x180024f34`
- `USER32!DestroyMenu` at `0x180024f34`
- `USER32!LoadMenuW` at `0x180024eff`
- `USER32!LoadMenuW` at `0x180024eff`
- `USER32!GetSubMenu` at `0x180024f12`
- `USER32!GetSubMenu` at `0x180024f12`
- `USER32!RemoveMenu` at `0x180024f2b`
- `USER32!RemoveMenu` at `0x180024f2b`

## pseudocode

```c
HMENU __fastcall SHLoadMenuPopup(HINSTANCE a1, unsigned __int16 a2)
{
  HMENU SubMenu; // rdi
  HMENU MenuW; // rax
  HMENU v4; // rbx

  SubMenu = 0;
  MenuW = LoadMenuW(a1, (LPCWSTR)a2);
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
0x180024ef0  mov     [rsp+arg_0], rbx
0x180024ef5  push    rdi
0x180024ef6  sub     rsp, 20h
0x180024efa  movzx   edx, dx; lpMenuName
0x180024efd  xor     edi, edi
0x180024eff  call    cs:__imp_LoadMenuW
0x180024f05  mov     rbx, rax
0x180024f08  test    rax, rax
0x180024f0b  jz      short loc_180024F3A
0x180024f0d  xor     edx, edx; nPos
0x180024f0f  mov     rcx, rax; hMenu
0x180024f12  call    cs:__imp_GetSubMenu
0x180024f18  mov     rdi, rax
0x180024f1b  test    rax, rax
0x180024f1e  jz      short loc_180024F31
0x180024f20  xor     edx, edx; uPosition
0x180024f22  mov     r8d, 400h; uFlags
0x180024f28  mov     rcx, rbx; hMenu
0x180024f2b  call    cs:__imp_RemoveMenu
0x180024f31  mov     rcx, rbx; hMenu
0x180024f34  call    cs:__imp_DestroyMenu
0x180024f3a  mov     rbx, [rsp+28h+arg_0]
0x180024f3f  mov     rax, rdi
0x180024f42  add     rsp, 20h
0x180024f46  pop     rdi
0x180024f47  retn
```
