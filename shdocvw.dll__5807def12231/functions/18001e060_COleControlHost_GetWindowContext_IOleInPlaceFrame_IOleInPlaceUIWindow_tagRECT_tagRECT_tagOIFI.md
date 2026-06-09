# COleControlHost::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x18001e060`
- end: `0x18001e0e6`
- name: `?GetWindowContext@COleControlHost@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `134`
- prototype: `int(COleControlHost *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001e060`

## import_xrefs

- `USER32!CopyRect` at `0x18001e0b0`
- `USER32!CopyRect` at `0x18001e0b0`
- `USER32!SetRectEmpty` at `0x18001e0a2`
- `USER32!SetRectEmpty` at `0x18001e0a2`
- `USER32!GetClientRect` at `0x18001e095`
- `USER32!GetClientRect` at `0x18001e095`

## pseudocode

```c
__int64 __fastcall COleControlHost::GetWindowContext(
        COleControlHost *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lprcDst,
        struct tagOIFI *a6)
{
  __int64 result; // rax

  *a2 = (struct IOleInPlaceFrame *)(((unsigned __int64)this + 8) & -(__int64)(this != (COleControlHost *)16));
  ++*((_DWORD *)this + 10);
  *a3 = 0;
  if ( !GetClientRect(*((HWND *)this + 8), a4) )
    SetRectEmpty(a4);
  CopyRect(lprcDst, a4);
  *(_QWORD *)&a6->cb = 32;
  a6->hwndFrame = (HWND)*((_QWORD *)this + 8);
  result = 0;
  a6->haccel = 0;
  a6->cAccelEntries = 0;
  return result;
}

```

## disassembly

```asm
0x18001e060  mov     [rsp+arg_0], rbx
0x18001e065  push    rdi
0x18001e066  sub     rsp, 20h
0x18001e06a  lea     rax, [rcx-10h]
0x18001e06e  mov     rdi, rcx
0x18001e071  lea     r11, [rcx+8]
0x18001e075  neg     rax
0x18001e078  mov     rbx, r9
0x18001e07b  sbb     r10, r10
0x18001e07e  and     r10, r11
0x18001e081  mov     [rdx], r10
0x18001e084  mov     rdx, r9; lpRect
0x18001e087  inc     dword ptr [rcx+28h]
0x18001e08a  mov     qword ptr [r8], 0
0x18001e091  mov     rcx, [rcx+40h]; hWnd
0x18001e095  call    cs:__imp_GetClientRect
0x18001e09b  test    eax, eax
0x18001e09d  jnz     short loc_18001E0A8
0x18001e09f  mov     rcx, rbx; lprc
0x18001e0a2  call    cs:__imp_SetRectEmpty
0x18001e0a8  mov     rcx, [rsp+28h+lprcDst]; lprcDst
0x18001e0ad  mov     rdx, rbx; lprcSrc
0x18001e0b0  call    cs:__imp_CopyRect
0x18001e0b6  mov     rcx, [rsp+28h+arg_28]
0x18001e0bb  mov     rbx, [rsp+28h+arg_0]
0x18001e0c0  mov     qword ptr [rcx], 20h ; ' '
0x18001e0c7  mov     rax, [rdi+40h]
0x18001e0cb  mov     [rcx+8], rax
0x18001e0cf  xor     eax, eax
0x18001e0d1  mov     qword ptr [rcx+10h], 0
0x18001e0d9  mov     dword ptr [rcx+18h], 0
0x18001e0e0  add     rsp, 20h
0x18001e0e4  pop     rdi
0x18001e0e5  retn
```
