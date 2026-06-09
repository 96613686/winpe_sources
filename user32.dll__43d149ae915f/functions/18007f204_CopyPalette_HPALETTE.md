# CopyPalette(HPALETTE__ *)

- ea: `0x18007f204`
- end: `0x18007f2dc`
- name: `?CopyPalette@@YAPEAUHPALETTE__@@PEAU1@@Z`
- size: `216`
- prototype: `HPALETTE __fastcall(HPALETTE hpal)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007f094`

## callees

- `0x18007f204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f24e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f24e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f277`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f2d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f277`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f2d1`
- `GDI32!GetObjectW` at `0x18007f227`
- `GDI32!GetObjectW` at `0x18007f227`
- `GDI32!SetPaletteEntries` at `0x18007f2b9`
- `GDI32!SetPaletteEntries` at `0x18007f2b9`
- `GDI32!CreatePalette` at `0x18007f29d`
- `GDI32!CreatePalette` at `0x18007f29d`
- `GDI32!GetPaletteEntries` at `0x18007f26a`
- `GDI32!GetPaletteEntries` at `0x18007f26a`
- `GDI32!DeleteObject` at `0x18007f2c6`
- `GDI32!DeleteObject` at `0x18007f2c6`

## pseudocode

```c
HPALETTE __fastcall CopyPalette(HPALETTE hpal)
{
  struct tagPALETTEENTRY *v2; // rax
  LOGPALETTE *v3; // rbx
  HPALETTE Palette; // rax
  HPALETTE v6; // rdi
  UINT cEntries; // [rsp+38h] [rbp+10h] BYREF

  cEntries = 0;
  if ( !GetObjectW(hpal, 4, &cEntries) )
    return 0;
  if ( (int)cEntries > 0x10000 )
    return 0;
  v2 = (struct tagPALETTEENTRY *)LocalAlloc(0x40u, 4LL * (int)(cEntries - 1) + 8);
  v3 = (LOGPALETTE *)v2;
  if ( !v2 )
    return 0;
  if ( !GetPaletteEntries(hpal, 0, cEntries, v2 + 1) )
  {
    LocalFree(v3);
    return 0;
  }
  v3->palVersion = 768;
  v3->palNumEntries = cEntries;
  Palette = CreatePalette(v3);
  v6 = Palette;
  if ( Palette )
  {
    if ( !SetPaletteEntries(Palette, 0, cEntries, v3->palPalEntry) )
    {
      DeleteObject(v6);
      v6 = 0;
    }
  }
  LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x18007f204  mov     rax, rsp
0x18007f207  mov     [rax+8], rbx
0x18007f20b  mov     [rax+18h], rsi
0x18007f20f  push    rdi
0x18007f210  sub     rsp, 20h
0x18007f214  lea     r8, [rax+10h]; pv
0x18007f218  mov     dword ptr [rax+10h], 0
0x18007f21f  mov     edx, 4; c
0x18007f224  mov     rdi, rcx
0x18007f227  call    cs:__imp_GetObjectW
0x18007f22d  test    eax, eax
0x18007f22f  jz      short loc_18007F27D
0x18007f231  mov     eax, [rsp+28h+cEntries]
0x18007f235  cmp     eax, 10000h
0x18007f23a  jg      short loc_18007F27D
0x18007f23c  dec     eax
0x18007f23e  mov     ecx, 40h ; '@'; uFlags
0x18007f243  movsxd  rdx, eax
0x18007f246  lea     rdx, ds:8[rdx*4]; uBytes
0x18007f24e  call    cs:__imp_LocalAlloc
0x18007f254  mov     rbx, rax
0x18007f257  test    rax, rax
0x18007f25a  jz      short loc_18007F27D
0x18007f25c  mov     r8d, [rsp+28h+cEntries]; cEntries
0x18007f261  lea     r9, [rax+4]; pPalEntries
0x18007f265  xor     edx, edx; iStart
0x18007f267  mov     rcx, rdi; hpal
0x18007f26a  call    cs:__imp_GetPaletteEntries
0x18007f270  mov     rcx, rbx; plpal
0x18007f273  test    eax, eax
0x18007f275  jnz     short loc_18007F28F
0x18007f277  call    cs:__imp_LocalFree
0x18007f27d  xor     eax, eax
0x18007f27f  mov     rbx, [rsp+28h+arg_0]
0x18007f284  mov     rsi, [rsp+28h+arg_10]
0x18007f289  add     rsp, 20h
0x18007f28d  pop     rdi
0x18007f28e  retn
0x18007f28f  mov     word ptr [rbx], 300h
0x18007f294  movzx   eax, word ptr [rsp+28h+cEntries]
0x18007f299  mov     [rbx+2], ax
0x18007f29d  call    cs:__imp_CreatePalette
0x18007f2a3  mov     rdi, rax
0x18007f2a6  test    rax, rax
0x18007f2a9  jz      short loc_18007F2CE
0x18007f2ab  mov     r8d, [rsp+28h+cEntries]; cEntries
0x18007f2b0  lea     r9, [rbx+4]; pPalEntries
0x18007f2b4  xor     edx, edx; iStart
0x18007f2b6  mov     rcx, rax; hpal
0x18007f2b9  call    cs:__imp_SetPaletteEntries
0x18007f2bf  test    eax, eax
0x18007f2c1  jnz     short loc_18007F2CE
0x18007f2c3  mov     rcx, rdi; ho
0x18007f2c6  call    cs:__imp_DeleteObject
0x18007f2cc  xor     edi, edi
0x18007f2ce  mov     rcx, rbx; hMem
0x18007f2d1  call    cs:__imp_LocalFree
0x18007f2d7  mov     rax, rdi
0x18007f2da  jmp     short loc_18007F27F
```
