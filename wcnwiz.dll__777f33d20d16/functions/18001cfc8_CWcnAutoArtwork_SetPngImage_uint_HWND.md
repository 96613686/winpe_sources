# CWcnAutoArtwork::SetPngImage(uint,HWND__ *)

- ea: `0x18001cfc8`
- end: `0x18001d026`
- name: `?SetPngImage@CWcnAutoArtwork@@QEAAXIPEAUHWND__@@@Z`
- size: `94`
- prototype: `void __fastcall(HBITMAP *this, unsigned int, HWND)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009aa8`
- `0x180009e70`

## callees

- `0x18001cfc8`
- `0x18001d02c`
- `0x18002e284`

## import_xrefs

- `USER32!SendMessageW` at `0x18001d009`
- `USER32!SendMessageW` at `0x18001d009`
- `GDI32!DeleteObject` at `0x18001d017`
- `GDI32!DeleteObject` at `0x18001d017`

## pseudocode

```c
void __fastcall CWcnAutoArtwork::SetPngImage(HBITMAP *this, unsigned __int16 a2, HWND a3)
{
  void *v3; // rbp

  v3 = *this;
  CWcnAutoArtwork::SetStaticType((CWcnAutoArtwork *)this, a3, (int)a3);
  LoadImageScaled(hModule, (unsigned __int16 *)a2, this);
  SendMessageW(a3, 0x172u, 0, (LPARAM)*this);
  if ( v3 )
    DeleteObject(v3);
}

```

## disassembly

```asm
0x18001cfc8  push    rbx
0x18001cfca  push    rbp
0x18001cfcb  push    rsi
0x18001cfcc  push    rdi
0x18001cfcd  sub     rsp, 38h
0x18001cfd1  mov     rbp, [rcx]
0x18001cfd4  mov     rsi, r8
0x18001cfd7  mov     ebx, edx
0x18001cfd9  mov     rdi, rcx
0x18001cfdc  mov     rdx, r8; HWND
0x18001cfdf  call    ?SetStaticType@CWcnAutoArtwork@@AEAAXPEAUHWND__@@J@Z; CWcnAutoArtwork::SetStaticType(HWND__ *,long)
0x18001cfe4  mov     rcx, cs:hModule; HINSTANCE
0x18001cfeb  xor     r8d, r8d
0x18001cfee  movzx   edx, bx; unsigned __int16 *
0x18001cff1  mov     [rsp+58h+var_38], rdi; HBITMAP *
0x18001cff6  call    LoadImageScaled
0x18001cffb  mov     r9, [rdi]; lParam
0x18001cffe  xor     r8d, r8d; wParam
0x18001d001  mov     edx, 172h; Msg
0x18001d006  mov     rcx, rsi; hWnd
0x18001d009  call    cs:__imp_SendMessageW
0x18001d00f  test    rbp, rbp
0x18001d012  jz      short loc_18001D01D
0x18001d014  mov     rcx, rbp; ho
0x18001d017  call    cs:__imp_DeleteObject
0x18001d01d  add     rsp, 38h
0x18001d021  pop     rdi
0x18001d022  pop     rsi
0x18001d023  pop     rbp
0x18001d024  pop     rbx
0x18001d025  retn
```
