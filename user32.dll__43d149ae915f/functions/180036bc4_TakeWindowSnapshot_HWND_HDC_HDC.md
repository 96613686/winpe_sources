# TakeWindowSnapshot(HWND__ *,HDC__ *,HDC__ *)

- ea: `0x180036bc4`
- end: `0x180036cc7`
- name: `?TakeWindowSnapshot@@YAPEAUHBITMAP__@@PEAUHWND__@@PEAUHDC__@@1@Z`
- size: `259`
- prototype: `HBITMAP __fastcall(HWND hWnd, HDC hdc, HDC)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035be0`

## callees

- `0x18000cf20`
- `0x18000d210`
- `0x180036bc4`
- `0x180096e00`

## import_xrefs

- `GDI32!SelectObject` at `0x180036c30`
- `GDI32!SelectObject` at `0x180036ca0`
- `GDI32!SelectObject` at `0x180036c30`
- `GDI32!SelectObject` at `0x180036ca0`
- `GDI32!GetBoundsRect` at `0x180036c7f`
- `GDI32!GetBoundsRect` at `0x180036c7f`
- `GDI32!SetLayout` at `0x180036c46`
- `GDI32!SetLayout` at `0x180036c94`
- `GDI32!SetLayout` at `0x180036c46`
- `GDI32!SetLayout` at `0x180036c94`
- `GDI32!SetBoundsRect` at `0x180036c58`
- `GDI32!SetBoundsRect` at `0x180036c58`
- `GDI32!CreateCompatibleBitmap` at `0x180036c02`
- `GDI32!CreateCompatibleBitmap` at `0x180036c02`
- `GDI32!DeleteObject` at `0x180036cbd`
- `GDI32!DeleteObject` at `0x180036cbd`

## pseudocode

```c
HBITMAP __fastcall TakeWindowSnapshot(HWND hWnd, HDC hdc, HDC a3)
{
  struct tagWND *v6; // rax
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v8; // rbx
  HGDIOBJ v10; // rbp
  DWORD v11; // r14d
  char BoundsRect; // al
  int v13; // esi
  struct tagRECT rect; // [rsp+20h] [rbp-48h] BYREF

  v6 = ValidateHwnd(hWnd);
  if ( !v6 )
    return 0;
  CompatibleBitmap = CreateCompatibleBitmap(
                       hdc,
                       *((_DWORD *)v6 + 24) - *((_DWORD *)v6 + 22),
                       *((_DWORD *)v6 + 25) - *((_DWORD *)v6 + 23));
  v8 = CompatibleBitmap;
  if ( !CompatibleBitmap )
    return 0;
  v10 = SelectObject(a3, CompatibleBitmap);
  rect = 0;
  v11 = SetLayout(a3, 0);
  SetBoundsRect(a3, 0, 5u);
  SendMessageW(hWnd, 0x317u, (WPARAM)a3, 30);
  BoundsRect = GetBoundsRect(a3, &rect, 0);
  if ( (BoundsRect & 1) == 0 || (v13 = 0, (BoundsRect & 2) != 0) )
    v13 = 1;
  SetLayout(a3, v11);
  SelectObject(a3, v10);
  if ( !v13 )
  {
    DeleteObject(v8);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180036bc4  push    rbx
0x180036bc6  push    rbp
0x180036bc7  push    rsi
0x180036bc8  push    rdi
0x180036bc9  push    r14
0x180036bcb  sub     rsp, 40h
0x180036bcf  mov     rax, cs:__security_cookie
0x180036bd6  xor     rax, rsp
0x180036bd9  mov     [rsp+68h+var_38], rax
0x180036bde  mov     rdi, r8
0x180036be1  mov     rbx, rdx
0x180036be4  mov     rsi, rcx
0x180036be7  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180036bec  test    rax, rax
0x180036bef  jz      short loc_180036C10
0x180036bf1  mov     r8d, [rax+64h]
0x180036bf5  mov     rcx, rbx; hdc
0x180036bf8  mov     edx, [rax+60h]
0x180036bfb  sub     r8d, [rax+5Ch]; cy
0x180036bff  sub     edx, [rax+58h]; cx
0x180036c02  call    cs:__imp_CreateCompatibleBitmap
0x180036c08  mov     rbx, rax
0x180036c0b  test    rax, rax
0x180036c0e  jnz     short loc_180036C2A
0x180036c10  xor     eax, eax
0x180036c12  mov     rcx, [rsp+68h+var_38]
0x180036c17  xor     rcx, rsp; StackCookie
0x180036c1a  call    __security_check_cookie
0x180036c1f  add     rsp, 40h
0x180036c23  pop     r14
0x180036c25  pop     rdi
0x180036c26  pop     rsi
0x180036c27  pop     rbp
0x180036c28  pop     rbx
0x180036c29  retn
0x180036c2a  mov     rdx, rbx; h
0x180036c2d  mov     rcx, rdi; hdc
0x180036c30  call    cs:__imp_SelectObject
0x180036c36  xorps   xmm0, xmm0
0x180036c39  xor     edx, edx; l
0x180036c3b  mov     rcx, rdi; hdc
0x180036c3e  mov     rbp, rax
0x180036c41  movups  xmmword ptr [rsp+68h+rect.left], xmm0
0x180036c46  call    cs:__imp_SetLayout
0x180036c4c  xor     edx, edx; lprect
0x180036c4e  mov     rcx, rdi; hdc
0x180036c51  mov     r14d, eax
0x180036c54  lea     r8d, [rdx+5]; flags
0x180036c58  call    cs:__imp_SetBoundsRect
0x180036c5e  mov     r9d, 1Eh; lParam
0x180036c64  mov     r8, rdi; wParam
0x180036c67  mov     edx, 317h; Msg
0x180036c6c  mov     rcx, rsi; hWnd
0x180036c6f  call    SendMessageW
0x180036c74  xor     r8d, r8d; flags
0x180036c77  lea     rdx, [rsp+68h+rect]; lprect
0x180036c7c  mov     rcx, rdi; hdc
0x180036c7f  call    cs:__imp_GetBoundsRect
0x180036c85  test    al, 1
0x180036c87  jnz     short loc_180036CB2
0x180036c89  mov     esi, 1
0x180036c8e  mov     edx, r14d; l
0x180036c91  mov     rcx, rdi; hdc
0x180036c94  call    cs:__imp_SetLayout
0x180036c9a  mov     rdx, rbp; h
0x180036c9d  mov     rcx, rdi; hdc
0x180036ca0  call    cs:__imp_SelectObject
0x180036ca6  test    esi, esi
0x180036ca8  jz      short loc_180036CBA
0x180036caa  mov     rax, rbx
0x180036cad  jmp     loc_180036C12
0x180036cb2  xor     esi, esi
0x180036cb4  test    al, 2
0x180036cb6  jz      short loc_180036C8E
0x180036cb8  jmp     short loc_180036C89
0x180036cba  mov     rcx, rbx; ho
0x180036cbd  call    cs:__imp_DeleteObject
0x180036cc3  xor     ebx, ebx
0x180036cc5  jmp     short loc_180036CAA
```
