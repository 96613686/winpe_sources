# SHRemoveDefaultDialogFont

- ea: `0x180025580`
- end: `0x1800255ba`
- name: `SHRemoveDefaultDialogFont`
- size: `58`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180025580`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002559e`
- `GDI32!DeleteObject` at `0x18002559e`
- `USER32!GetPropW` at `0x180025590`
- `USER32!GetPropW` at `0x180025590`
- `USER32!RemovePropW` at `0x1800255ae`
- `USER32!RemovePropW` at `0x1800255ae`

## pseudocode

```c
HANDLE __fastcall SHRemoveDefaultDialogFont(HWND hWnd)
{
  HANDLE result; // rax

  result = GetPropW(hWnd, L"PropDlgFont");
  if ( result )
  {
    DeleteObject(result);
    return RemovePropW(hWnd, L"PropDlgFont");
  }
  return result;
}

```

## disassembly

```asm
0x180025580  push    rbx
0x180025582  sub     rsp, 20h
0x180025586  lea     rdx, aPropdlgfont; "PropDlgFont"
0x18002558d  mov     rbx, rcx
0x180025590  call    cs:__imp_GetPropW
0x180025596  test    rax, rax
0x180025599  jz      short loc_1800255B4
0x18002559b  mov     rcx, rax; ho
0x18002559e  call    cs:__imp_DeleteObject
0x1800255a4  lea     rdx, aPropdlgfont; "PropDlgFont"
0x1800255ab  mov     rcx, rbx; hWnd
0x1800255ae  call    cs:__imp_RemovePropW
0x1800255b4  add     rsp, 20h
0x1800255b8  pop     rbx
0x1800255b9  retn
```
