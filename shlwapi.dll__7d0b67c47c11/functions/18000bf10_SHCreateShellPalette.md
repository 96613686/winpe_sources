# SHCreateShellPalette

- ea: `0x18000bf10`
- end: `0x18000c01d`
- name: `SHCreateShellPalette`
- size: `269`
- prototype: `HPALETTE __stdcall(HDC hdc)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000bf10`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `GDI32!CreateHalftonePalette` at `0x18000bf37`
- `GDI32!CreateHalftonePalette` at `0x18000bf37`
- `GDI32!DeleteDC` at `0x18000bfef`
- `GDI32!DeleteDC` at `0x18000bfef`
- `GDI32!CreatePalette` at `0x18000bfd9`
- `GDI32!CreatePalette` at `0x18000bfd9`
- `GDI32!GetSystemPaletteEntries` at `0x18000bfb5`
- `GDI32!GetSystemPaletteEntries` at `0x18000bfce`
- `GDI32!GetSystemPaletteEntries` at `0x18000bfb5`
- `GDI32!GetSystemPaletteEntries` at `0x18000bfce`
- `GDI32!CreateCompatibleDC` at `0x18000bf90`
- `GDI32!CreateCompatibleDC` at `0x18000bf90`
- `GDI32!DeleteObject` at `0x18000bf83`
- `GDI32!DeleteObject` at `0x18000bf83`
- `GDI32!GetPaletteEntries` at `0x18000bf6b`
- `GDI32!GetPaletteEntries` at `0x18000bf6b`

## pseudocode

```c
HPALETTE __stdcall SHCreateShellPalette(HDC hdc)
{
  HPALETTE HalftonePalette; // rdi
  HDC CompatibleDC; // rbx
  LOGPALETTE plpal; // [rsp+20h] [rbp-428h] BYREF
  struct tagPALETTEENTRY v6; // [rsp+3FCh] [rbp-4Ch] BYREF

  HalftonePalette = CreateHalftonePalette(hdc);
  if ( !HalftonePalette )
    return HalftonePalette;
  memset_0(&plpal, 0, 0x404u);
  plpal.palNumEntries = GetPaletteEntries(HalftonePalette, 0, 0x100u, plpal.palPalEntry);
  plpal.palVersion = 768;
  DeleteObject(HalftonePalette);
  if ( hdc )
  {
    CompatibleDC = hdc;
  }
  else
  {
    CompatibleDC = CreateCompatibleDC(0);
    if ( !CompatibleDC )
      goto LABEL_7;
  }
  GetSystemPaletteEntries(CompatibleDC, 0, 0xAu, plpal.palPalEntry);
  GetSystemPaletteEntries(CompatibleDC, 0xF6u, 0xAu, &v6);
LABEL_7:
  HalftonePalette = CreatePalette(&plpal);
  if ( !hdc && CompatibleDC )
    DeleteDC(CompatibleDC);
  return HalftonePalette;
}

```

## disassembly

```asm
0x18000bf10  mov     [rsp+arg_8], rbx
0x18000bf15  mov     [rsp+arg_10], rsi
0x18000bf1a  push    rdi
0x18000bf1b  sub     rsp, 440h
0x18000bf22  mov     rax, cs:__security_cookie
0x18000bf29  xor     rax, rsp
0x18000bf2c  mov     [rsp+448h+var_18], rax
0x18000bf34  mov     rsi, rcx
0x18000bf37  call    cs:__imp_CreateHalftonePalette
0x18000bf3d  mov     rdi, rax
0x18000bf40  test    rax, rax
0x18000bf43  jz      loc_18000BFF5
0x18000bf49  xor     edx, edx; Val
0x18000bf4b  lea     rcx, [rsp+448h+plpal]; void *
0x18000bf50  mov     r8d, 404h; Size
0x18000bf56  call    memset_0
0x18000bf5b  lea     r9, [rsp+448h+plpal.palPalEntry]; pPalEntries
0x18000bf60  xor     edx, edx; iStart
0x18000bf62  mov     r8d, 100h; cEntries
0x18000bf68  mov     rcx, rdi; hpal
0x18000bf6b  call    cs:__imp_GetPaletteEntries
0x18000bf71  mov     [rsp+448h+plpal.palNumEntries], ax
0x18000bf76  mov     rcx, rdi; ho
0x18000bf79  mov     eax, 300h
0x18000bf7e  mov     [rsp+448h+plpal.palVersion], ax
0x18000bf83  call    cs:__imp_DeleteObject
0x18000bf89  test    rsi, rsi
0x18000bf8c  jnz     short loc_18000BFA0
0x18000bf8e  xor     ecx, ecx; hdc
0x18000bf90  call    cs:__imp_CreateCompatibleDC
0x18000bf96  mov     rbx, rax
0x18000bf99  test    rax, rax
0x18000bf9c  jnz     short loc_18000BFA3
0x18000bf9e  jmp     short loc_18000BFD4
0x18000bfa0  mov     rbx, rsi
0x18000bfa3  mov     edi, 0Ah
0x18000bfa8  lea     r9, [rsp+448h+plpal.palPalEntry]; pPalEntries
0x18000bfad  mov     r8d, edi; cEntries
0x18000bfb0  xor     edx, edx; iStart
0x18000bfb2  mov     rcx, rbx; hdc
0x18000bfb5  call    cs:__imp_GetSystemPaletteEntries
0x18000bfbb  lea     r9, [rsp+448h+var_4C]; pPalEntries
0x18000bfc3  mov     r8d, edi; cEntries
0x18000bfc6  mov     edx, 0F6h; iStart
0x18000bfcb  mov     rcx, rbx; hdc
0x18000bfce  call    cs:__imp_GetSystemPaletteEntries
0x18000bfd4  lea     rcx, [rsp+448h+plpal]; plpal
0x18000bfd9  call    cs:__imp_CreatePalette
0x18000bfdf  mov     rdi, rax
0x18000bfe2  test    rsi, rsi
0x18000bfe5  jnz     short loc_18000BFF5
0x18000bfe7  test    rbx, rbx
0x18000bfea  jz      short loc_18000BFF5
0x18000bfec  mov     rcx, rbx; hdc
0x18000bfef  call    cs:__imp_DeleteDC
0x18000bff5  mov     rax, rdi
0x18000bff8  mov     rcx, [rsp+448h+var_18]
0x18000c000  xor     rcx, rsp; StackCookie
0x18000c003  call    __security_check_cookie
0x18000c008  lea     r11, [rsp+448h+var_8]
0x18000c010  mov     rbx, [r11+18h]
0x18000c014  mov     rsi, [r11+20h]
0x18000c018  mov     rsp, r11
0x18000c01b  pop     rdi
0x18000c01c  retn
```
