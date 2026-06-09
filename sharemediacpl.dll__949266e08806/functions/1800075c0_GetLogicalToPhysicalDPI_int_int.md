# GetLogicalToPhysicalDPI(int *,int *)

- ea: `0x1800075c0`
- end: `0x180007647`
- name: `?GetLogicalToPhysicalDPI@@YAXPEAH0@Z`
- size: `135`
- prototype: `void __fastcall(int *, int *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000553c`
- `0x180007778`
- `0x180008c54`
- `0x180009df8`

## callees

- `0x1800075c0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180007612`
- `KERNEL32!MulDiv` at `0x180007629`
- `KERNEL32!MulDiv` at `0x180007612`
- `KERNEL32!MulDiv` at `0x180007629`
- `GDI32!GetDeviceCaps` at `0x1800075e9`
- `GDI32!GetDeviceCaps` at `0x1800075fa`
- `GDI32!GetDeviceCaps` at `0x1800075e9`
- `GDI32!GetDeviceCaps` at `0x1800075fa`
- `USER32!ReleaseDC` at `0x180007636`
- `USER32!ReleaseDC` at `0x180007636`
- `USER32!GetDC` at `0x1800075d3`
- `USER32!GetDC` at `0x1800075d3`

## pseudocode

```c
void __fastcall GetLogicalToPhysicalDPI(int *a1, int *a2)
{
  HDC DC; // rax
  HDC v5; // rbx
  int DeviceCaps; // r14d
  int v7; // ebp

  DC = GetDC(0);
  v5 = DC;
  if ( DC )
  {
    DeviceCaps = GetDeviceCaps(DC, 88);
    v7 = GetDeviceCaps(v5, 90);
    if ( a1 )
      *a1 = MulDiv(*a1, DeviceCaps, 96);
    if ( a2 )
      *a2 = MulDiv(*a2, v7, 96);
    ReleaseDC(0, v5);
  }
}

```

## disassembly

```asm
0x1800075c0  push    rbx
0x1800075c2  push    rbp
0x1800075c3  push    rsi
0x1800075c4  push    rdi
0x1800075c5  push    r14
0x1800075c7  sub     rsp, 20h
0x1800075cb  mov     rsi, rcx
0x1800075ce  mov     rdi, rdx
0x1800075d1  xor     ecx, ecx; hWnd
0x1800075d3  call    cs:__imp_GetDC
0x1800075d9  mov     rbx, rax
0x1800075dc  test    rax, rax
0x1800075df  jz      short loc_18000763C
0x1800075e1  mov     edx, 58h ; 'X'; index
0x1800075e6  mov     rcx, rax; hdc
0x1800075e9  call    cs:__imp_GetDeviceCaps
0x1800075ef  mov     edx, 5Ah ; 'Z'; index
0x1800075f4  mov     rcx, rbx; hdc
0x1800075f7  mov     r14d, eax
0x1800075fa  call    cs:__imp_GetDeviceCaps
0x180007600  mov     ebp, eax
0x180007602  test    rsi, rsi
0x180007605  jz      short loc_18000761A
0x180007607  mov     ecx, [rsi]; nNumber
0x180007609  mov     r8d, 60h ; '`'; nDenominator
0x18000760f  mov     edx, r14d; nNumerator
0x180007612  call    cs:__imp_MulDiv
0x180007618  mov     [rsi], eax
0x18000761a  test    rdi, rdi
0x18000761d  jz      short loc_180007631
0x18000761f  mov     ecx, [rdi]; nNumber
0x180007621  mov     r8d, 60h ; '`'; nDenominator
0x180007627  mov     edx, ebp; nNumerator
0x180007629  call    cs:__imp_MulDiv
0x18000762f  mov     [rdi], eax
0x180007631  mov     rdx, rbx; hDC
0x180007634  xor     ecx, ecx; hWnd
0x180007636  call    cs:__imp_ReleaseDC
0x18000763c  add     rsp, 20h
0x180007640  pop     r14
0x180007642  pop     rdi
0x180007643  pop     rsi
0x180007644  pop     rbp
0x180007645  pop     rbx
0x180007646  retn
```
