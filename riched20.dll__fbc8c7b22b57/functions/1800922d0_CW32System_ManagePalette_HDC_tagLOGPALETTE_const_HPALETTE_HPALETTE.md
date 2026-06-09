# CW32System::ManagePalette(HDC__ *,tagLOGPALETTE const *,HPALETTE__ * &,HPALETTE__ * &)

- ea: `0x1800922d0`
- end: `0x180092381`
- name: `?ManagePalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEBUtagLOGPALETTE@@AEAPEAU2@2@Z`
- size: `177`
- prototype: `HPALETTE __fastcall(HDC hdc, LOGPALETTE *plpal, HPALETTE *, HPALETTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002327c`

## callees

- `0x1800922d0`

## import_xrefs

- `GDI32!CreatePalette` at `0x1800922f1`
- `GDI32!CreatePalette` at `0x1800922f1`
- `GDI32!DeleteObject` at `0x18009235b`
- `GDI32!DeleteObject` at `0x18009235b`
- `GDI32!RealizePalette` at `0x180092323`
- `GDI32!RealizePalette` at `0x18009234c`
- `GDI32!RealizePalette` at `0x180092323`
- `GDI32!RealizePalette` at `0x18009234c`
- `GDI32!SelectPalette` at `0x180092311`
- `GDI32!SelectPalette` at `0x18009233d`
- `GDI32!SelectPalette` at `0x180092311`
- `GDI32!SelectPalette` at `0x18009233d`

## pseudocode

```c
HPALETTE __fastcall CW32System::ManagePalette(HDC hdc, LOGPALETTE *plpal, HPALETTE *a3, HPALETTE *a4)
{
  HPALETTE Palette; // rax

  if ( *a4 )
  {
    SelectPalette(hdc, *a3, 1);
    RealizePalette(hdc);
    DeleteObject(*a4);
    *a4 = 0;
  }
  else
  {
    Palette = CreatePalette(plpal);
    *a4 = Palette;
    if ( Palette )
    {
      *a3 = SelectPalette(hdc, Palette, 1);
      RealizePalette(hdc);
      return *a4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800922d0  mov     [rsp+arg_0], rbx
0x1800922d5  mov     [rsp+arg_8], rsi
0x1800922da  push    rdi
0x1800922db  sub     rsp, 20h
0x1800922df  cmp     qword ptr [r9], 0
0x1800922e3  mov     rbx, r9
0x1800922e6  mov     rsi, r8
0x1800922e9  mov     rdi, rcx
0x1800922ec  jnz     short loc_180092334
0x1800922ee  mov     rcx, rdx; plpal
0x1800922f1  call    cs:__imp_CreatePalette
0x1800922f8  nop     dword ptr [rax+rax+00h]
0x1800922fd  mov     [rbx], rax
0x180092300  test    rax, rax
0x180092303  jz      short loc_18009236E
0x180092305  mov     r8d, 1; bForceBkgd
0x18009230b  mov     rdx, rax; hPal
0x18009230e  mov     rcx, rdi; hdc
0x180092311  call    cs:__imp_SelectPalette
0x180092318  nop     dword ptr [rax+rax+00h]
0x18009231d  mov     rcx, rdi; hdc
0x180092320  mov     [rsi], rax
0x180092323  call    cs:__imp_RealizePalette
0x18009232a  nop     dword ptr [rax+rax+00h]
0x18009232f  mov     rax, [rbx]
0x180092332  jmp     short loc_180092370
0x180092334  mov     rdx, [rsi]; hPal
0x180092337  mov     r8d, 1; bForceBkgd
0x18009233d  call    cs:__imp_SelectPalette
0x180092344  nop     dword ptr [rax+rax+00h]
0x180092349  mov     rcx, rdi; hdc
0x18009234c  call    cs:__imp_RealizePalette
0x180092353  nop     dword ptr [rax+rax+00h]
0x180092358  mov     rcx, [rbx]; ho
0x18009235b  call    cs:__imp_DeleteObject
0x180092362  nop     dword ptr [rax+rax+00h]
0x180092367  mov     qword ptr [rbx], 0
0x18009236e  xor     eax, eax
0x180092370  mov     rbx, [rsp+28h+arg_0]
0x180092375  mov     rsi, [rsp+28h+arg_8]
0x18009237a  add     rsp, 20h
0x18009237e  pop     rdi
0x18009237f  retn
```
