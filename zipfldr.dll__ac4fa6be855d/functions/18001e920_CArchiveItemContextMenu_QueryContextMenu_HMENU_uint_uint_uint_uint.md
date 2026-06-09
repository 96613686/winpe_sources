# CArchiveItemContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x18001e920`
- end: `0x18001ea2a`
- name: `?QueryContextMenu@CArchiveItemContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `266`
- prototype: `__int64 __fastcall(CArchiveItemContextMenu *this, HMENU, UINT, UINT, UINT uIDAdjustMax, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001e920`
- `0x18001f724`
- `0x18001fe04`

## import_xrefs

- `SHELL32!__imp_Shell_MergeMenus` at `0x18001e98d`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18001e98d`
- `USER32!DestroyMenu` at `0x18001e998`
- `USER32!DestroyMenu` at `0x18001e998`
- `USER32!SetMenuDefaultItem` at `0x18001ea0b`
- `USER32!SetMenuDefaultItem` at `0x18001ea0b`
- `USER32!DeleteMenu` at `0x18001e9cb`
- `USER32!DeleteMenu` at `0x18001e9da`
- `USER32!DeleteMenu` at `0x18001e9f0`
- `USER32!DeleteMenu` at `0x18001e9cb`
- `USER32!DeleteMenu` at `0x18001e9da`
- `USER32!DeleteMenu` at `0x18001e9f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CArchiveItemContextMenu::QueryContextMenu(
        CArchiveItemContextMenu *this,
        HMENU a2,
        UINT a3,
        UINT a4,
        UINT uIDAdjustMax,
        unsigned int a6)
{
  UINT v10; // esi
  HMENU PopupMenu; // r14
  _BYTE *Ptr; // r14
  UINT v13; // edx

  if ( (a6 & 2) == 0 )
  {
    v10 = -1;
    PopupMenu = LoadPopupMenu((HINSTANCE)this, (a6 & 0x10000) != 0 ? 105 : 102);
    if ( PopupMenu )
    {
      v10 = Shell_MergeMenus(a2, PopupMenu, a3, a4, uIDAdjustMax, 3u);
      DestroyMenu(PopupMenu);
    }
    Ptr = DPA_GetPtr(*(HDPA *)(*((_QWORD *)this + 4) + 40LL), 0);
    if ( !Ptr )
      return v10 - a4;
    if ( *(_DWORD *)(*((_QWORD *)this + 3) + 1132LL) )
    {
      DeleteMenu(a2, a4 + 111, 0);
      DeleteMenu(a2, a4 + 113, 0);
    }
    v13 = a4 + 103;
    if ( (Ptr[32] & 0x10) != 0 )
    {
      if ( (a6 & 4) != 0 )
      {
LABEL_11:
        SetMenuDefaultItem(a2, v13, 0);
        return v10 - a4;
      }
    }
    else
    {
      DeleteMenu(a2, v13, 0);
    }
    v13 = a4 + 102;
    goto LABEL_11;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001e920  push    rbx
0x18001e922  push    rsi
0x18001e923  push    rdi
0x18001e924  push    r12
0x18001e926  push    r14
0x18001e928  push    r15
0x18001e92a  sub     rsp, 38h
0x18001e92e  test    byte ptr [rsp+68h+arg_28], 2
0x18001e936  mov     ebx, r9d
0x18001e939  mov     r12d, r8d
0x18001e93c  mov     rdi, rdx
0x18001e93f  mov     r15, rcx
0x18001e942  jnz     loc_18001EA17
0x18001e948  mov     eax, [rsp+68h+arg_28]
0x18001e94f  or      esi, 0FFFFFFFFh
0x18001e952  and     eax, 10000h
0x18001e957  neg     eax
0x18001e959  sbb     edx, edx
0x18001e95b  and     edx, 3
0x18001e95e  add     edx, 66h ; 'f'; unsigned int
0x18001e961  call    ?LoadPopupMenu@@YAPEAUHMENU__@@PEAUHINSTANCE__@@I@Z; LoadPopupMenu(HINSTANCE__ *,uint)
0x18001e966  mov     r14, rax
0x18001e969  test    rax, rax
0x18001e96c  jz      short loc_18001E99E
0x18001e96e  mov     eax, [rsp+68h+arg_20]
0x18001e975  mov     r9d, ebx; uIDAdjust
0x18001e978  mov     [rsp+68h+uFlags], 3; uFlags
0x18001e980  mov     r8d, r12d; uInsert
0x18001e983  mov     rdx, r14; hmSrc
0x18001e986  mov     [rsp+68h+uIDAdjustMax], eax; uIDAdjustMax
0x18001e98a  mov     rcx, rdi; hmDst
0x18001e98d  call    cs:__imp_Shell_MergeMenus
0x18001e993  mov     rcx, r14; hMenu
0x18001e996  mov     esi, eax
0x18001e998  call    cs:__imp_DestroyMenu
0x18001e99e  mov     rcx, [r15+20h]
0x18001e9a2  xor     edx, edx; i
0x18001e9a4  mov     rcx, [rcx+28h]; hdpa
0x18001e9a8  call    DPA_GetPtr
0x18001e9ad  mov     r14, rax
0x18001e9b0  test    rax, rax
0x18001e9b3  jz      short loc_18001EA11
0x18001e9b5  mov     rcx, [r15+18h]
0x18001e9b9  cmp     dword ptr [rcx+46Ch], 0
0x18001e9c0  jz      short loc_18001E9E0
0x18001e9c2  lea     edx, [rbx+6Fh]; uPosition
0x18001e9c5  xor     r8d, r8d; uFlags
0x18001e9c8  mov     rcx, rdi; hMenu
0x18001e9cb  call    cs:__imp_DeleteMenu
0x18001e9d1  lea     edx, [rbx+71h]; uPosition
0x18001e9d4  xor     r8d, r8d; uFlags
0x18001e9d7  mov     rcx, rdi; hMenu
0x18001e9da  call    cs:__imp_DeleteMenu
0x18001e9e0  test    byte ptr [r14+20h], 10h
0x18001e9e5  lea     edx, [rbx+67h]; uPosition
0x18001e9e8  jnz     short loc_18001E9F8
0x18001e9ea  xor     r8d, r8d; uFlags
0x18001e9ed  mov     rcx, rdi; hMenu
0x18001e9f0  call    cs:__imp_DeleteMenu
0x18001e9f6  jmp     short loc_18001EA02
0x18001e9f8  test    byte ptr [rsp+68h+arg_28], 4
0x18001ea00  jnz     short loc_18001EA05
0x18001ea02  lea     edx, [rbx+66h]; uItem
0x18001ea05  xor     r8d, r8d; fByPos
0x18001ea08  mov     rcx, rdi; hMenu
0x18001ea0b  call    cs:__imp_SetMenuDefaultItem
0x18001ea11  sub     esi, ebx
0x18001ea13  mov     eax, esi
0x18001ea15  jmp     short loc_18001EA1C
0x18001ea17  mov     eax, 80004005h
0x18001ea1c  add     rsp, 38h
0x18001ea20  pop     r15
0x18001ea22  pop     r14
0x18001ea24  pop     r12
0x18001ea26  pop     rdi
0x18001ea27  pop     rsi
0x18001ea28  pop     rbx
0x18001ea29  retn
```
