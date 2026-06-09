# MDIRemoveSysMenu(HMENU__ *,HWND__ *)

- ea: `0x180066e58`
- end: `0x180066f38`
- name: `?MDIRemoveSysMenu@@YAHPEAUHMENU__@@PEAUHWND__@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(HMENU hMenu, HWND)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180012580`
- `0x180018214`
- `0x1800559c4`
- `0x180055da4`

## callees

- `0x18000d210`
- `0x180016c30`
- `0x180016de0`
- `0x180052258`
- `0x180066e58`
- `0x180074c14`

## import_xrefs

- `win32u!NtUserRemoveMenu` at `0x180066ed1`
- `win32u!NtUserRemoveMenu` at `0x180066ed1`
- `win32u!NtUserDeleteMenu` at `0x180066ee1`
- `win32u!NtUserDeleteMenu` at `0x180066f04`
- `win32u!NtUserDeleteMenu` at `0x180066f14`
- `win32u!NtUserDeleteMenu` at `0x180066ee1`
- `win32u!NtUserDeleteMenu` at `0x180066f04`
- `win32u!NtUserDeleteMenu` at `0x180066f14`

## pseudocode

```c
__int64 __fastcall MDIRemoveSysMenu(HMENU hMenu, HWND a2)
{
  struct tagWND *v4; // rbp
  int v5; // r14d
  int v6; // ebx
  struct tagWND *v7; // rax

  if ( !hMenu )
    return 0;
  v4 = ValidateHwnd(a2);
  if ( !v4 )
    return 0;
  v5 = GetMenuItemCount(hMenu) - 1;
  v6 = (*((_BYTE *)v4 + 20) & 8) != 0 ? 61728 : 61536;
  if ( GetMenuItemID(hMenu, v5) != v6 )
    return 0;
  SetWindowState(v4, 0xE08u);
  NtUserRemoveMenu(hMenu, 0, 1024);
  NtUserDeleteMenu(hMenu, (unsigned int)(v5 - 1), 1024);
  v7 = ValidateHwnd(a2);
  if ( !v7 )
    return 0;
  if ( (*((_BYTE *)v7 + 20) & 8) == 0 )
  {
    NtUserDeleteMenu(hMenu, (unsigned int)(v5 - 2), 1024);
    NtUserDeleteMenu(hMenu, (unsigned int)(v5 - 3), 1024);
  }
  MDIRedrawFrame(a2, 0);
  return 1;
}

```

## disassembly

```asm
0x180066e58  push    rbx
0x180066e5a  push    rbp
0x180066e5b  push    rsi
0x180066e5c  push    rdi
0x180066e5d  push    r14
0x180066e5f  sub     rsp, 20h
0x180066e63  mov     rsi, rdx
0x180066e66  mov     rdi, rcx
0x180066e69  test    rcx, rcx
0x180066e6c  jz      loc_180066F2B
0x180066e72  mov     rcx, rdx; HWND
0x180066e75  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180066e7a  mov     rbp, rax
0x180066e7d  test    rax, rax
0x180066e80  jz      loc_180066F2B
0x180066e86  mov     rcx, rdi; hMenu
0x180066e89  call    GetMenuItemCount
0x180066e8e  mov     cl, [rbp+14h]
0x180066e91  and     cl, 8
0x180066e94  neg     cl
0x180066e96  lea     r14d, [rax-1]
0x180066e9a  mov     rcx, rdi; hMenu
0x180066e9d  sbb     ebx, ebx
0x180066e9f  mov     edx, r14d; nPos
0x180066ea2  and     ebx, 0C0h
0x180066ea8  add     ebx, 0F060h
0x180066eae  call    GetMenuItemID
0x180066eb3  cmp     eax, ebx
0x180066eb5  jnz     short loc_180066F2B
0x180066eb7  mov     edx, 0E08h; unsigned int
0x180066ebc  mov     rcx, rbp; struct tagWND *
0x180066ebf  call    ?SetWindowState@@YAXPEAUtagWND@@I@Z; SetWindowState(tagWND *,uint)
0x180066ec4  mov     ebx, 400h
0x180066ec9  xor     edx, edx
0x180066ecb  mov     r8d, ebx
0x180066ece  mov     rcx, rdi
0x180066ed1  call    cs:__imp_NtUserRemoveMenu
0x180066ed7  lea     edx, [r14-1]
0x180066edb  mov     r8d, ebx
0x180066ede  mov     rcx, rdi
0x180066ee1  call    cs:__imp_NtUserDeleteMenu
0x180066ee7  mov     rcx, rsi; HWND
0x180066eea  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180066eef  test    rax, rax
0x180066ef2  jz      short loc_180066F2B
0x180066ef4  test    byte ptr [rax+14h], 8
0x180066ef8  jnz     short loc_180066F1A
0x180066efa  lea     edx, [r14-2]
0x180066efe  mov     r8d, ebx
0x180066f01  mov     rcx, rdi
0x180066f04  call    cs:__imp_NtUserDeleteMenu
0x180066f0a  lea     edx, [r14-3]
0x180066f0e  mov     r8d, ebx
0x180066f11  mov     rcx, rdi
0x180066f14  call    cs:__imp_NtUserDeleteMenu
0x180066f1a  xor     edx, edx; int
0x180066f1c  mov     rcx, rsi; HWND
0x180066f1f  call    ?MDIRedrawFrame@@YAXPEAUHWND__@@H@Z; MDIRedrawFrame(HWND__ *,int)
0x180066f24  mov     eax, 1
0x180066f29  jmp     short loc_180066F2D
0x180066f2b  xor     eax, eax
0x180066f2d  add     rsp, 20h
0x180066f31  pop     r14
0x180066f33  pop     rdi
0x180066f34  pop     rsi
0x180066f35  pop     rbp
0x180066f36  pop     rbx
0x180066f37  retn
```
