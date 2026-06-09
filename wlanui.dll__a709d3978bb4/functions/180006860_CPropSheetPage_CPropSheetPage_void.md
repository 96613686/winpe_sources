# CPropSheetPage::~CPropSheetPage(void)

- ea: `0x180006860`
- end: `0x1800068a3`
- name: `??1CPropSheetPage@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CPropSheetPage *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800068b0`
- `0x180006cd8`
- `0x18000dac8`
- `0x180011940`
- `0x180012964`

## callees

- `0x180006860`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x180006897`
- `USER32!SetWindowLongPtrW` at `0x180006897`
- `USER32!GetWindowLongPtrW` at `0x180006881`
- `USER32!GetWindowLongPtrW` at `0x180006881`

## pseudocode

```c
void __fastcall CPropSheetPage::~CPropSheetPage(CPropSheetPage *this)
{
  HWND v2; // rcx

  *(_QWORD *)this = &CPropSheetPage::`vftable';
  v2 = (HWND)*((_QWORD *)this + 1);
  if ( v2 )
  {
    if ( GetWindowLongPtrW(v2, 16) )
      SetWindowLongPtrW(*((HWND *)this + 1), 16, 0);
  }
}

```

## disassembly

```asm
0x180006860  push    rbx
0x180006862  sub     rsp, 20h
0x180006866  lea     rax, ??_7CPropSheetPage@@6B@; const CPropSheetPage::`vftable'
0x18000686d  mov     rbx, rcx
0x180006870  mov     [rcx], rax
0x180006873  mov     rcx, [rcx+8]; hWnd
0x180006877  test    rcx, rcx
0x18000687a  jz      short loc_18000689D
0x18000687c  mov     edx, 10h; nIndex
0x180006881  call    cs:__imp_GetWindowLongPtrW
0x180006887  test    rax, rax
0x18000688a  jz      short loc_18000689D
0x18000688c  mov     rcx, [rbx+8]; hWnd
0x180006890  xor     r8d, r8d; dwNewLong
0x180006893  lea     edx, [r8+10h]; nIndex
0x180006897  call    cs:__imp_SetWindowLongPtrW
0x18000689d  add     rsp, 20h
0x1800068a1  pop     rbx
0x1800068a2  retn
```
