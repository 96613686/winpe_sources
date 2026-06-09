# SHRemoveAllSubMenus

- ea: `0x180025530`
- end: `0x180025578`
- name: `SHRemoveAllSubMenus`
- size: `72`
- prototype: `__int64 __fastcall(HMENU hMenu)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180025530`

## import_xrefs

- `USER32!GetSubMenu` at `0x18002554c`
- `USER32!GetSubMenu` at `0x18002554c`
- `USER32!RemoveMenu` at `0x180025562`
- `USER32!RemoveMenu` at `0x180025562`
- `USER32!GetMenuItemCount` at `0x18002553d`
- `USER32!GetMenuItemCount` at `0x18002553d`

## pseudocode

```c
int __fastcall SHRemoveAllSubMenus(HMENU hMenu)
{
  HMENU SubMenu; // rax
  UINT v3; // ebx

  LODWORD(SubMenu) = GetMenuItemCount(hMenu);
  v3 = (unsigned int)SubMenu;
  while ( (--v3 & 0x80000000) == 0 )
  {
    SubMenu = GetSubMenu(hMenu, v3);
    if ( SubMenu )
      LODWORD(SubMenu) = RemoveMenu(hMenu, v3, 0x400u);
  }
  return (int)SubMenu;
}

```

## disassembly

```asm
0x180025530  mov     [rsp+arg_0], rbx
0x180025535  push    rdi
0x180025536  sub     rsp, 20h
0x18002553a  mov     rdi, rcx
0x18002553d  call    cs:__imp_GetMenuItemCount
0x180025543  mov     ebx, eax
0x180025545  jmp     short loc_180025568
0x180025547  mov     edx, ebx; nPos
0x180025549  mov     rcx, rdi; hMenu
0x18002554c  call    cs:__imp_GetSubMenu
0x180025552  test    rax, rax
0x180025555  jz      short loc_180025568
0x180025557  mov     r8d, 400h; uFlags
0x18002555d  mov     edx, ebx; uPosition
0x18002555f  mov     rcx, rdi; hMenu
0x180025562  call    cs:__imp_RemoveMenu
0x180025568  sub     ebx, 1
0x18002556b  jns     short loc_180025547
0x18002556d  mov     rbx, [rsp+28h+arg_0]
0x180025572  add     rsp, 20h
0x180025576  pop     rdi
0x180025577  retn
```
