# CleanupDialogParam(HWND__ *,SAFEOPENDLGPARAM *)

- ea: `0x180015b28`
- end: `0x180015bbd`
- name: `?CleanupDialogParam@@YAXPEAUHWND__@@PEAUSAFEOPENDLGPARAM@@@Z`
- size: `149`
- prototype: `void __fastcall(HWND, struct SAFEOPENDLGPARAM *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019170`

## callees

- `0x180015b28`

## import_xrefs

- `SHLWAPI!__imp_SHRemoveDefaultDialogFont` at `0x180015b31`
- `SHLWAPI!__imp_SHRemoveDefaultDialogFont` at `0x180015b31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b58`
- `GDI32!DeleteObject` at `0x180015b6f`
- `GDI32!DeleteObject` at `0x180015b89`
- `GDI32!DeleteObject` at `0x180015b6f`
- `GDI32!DeleteObject` at `0x180015b89`
- `USER32!DestroyWindow` at `0x180015b49`
- `USER32!DestroyWindow` at `0x180015b49`
- `USER32!DestroyIcon` at `0x180015ba6`
- `USER32!DestroyIcon` at `0x180015ba6`
- `USER32!IsWindow` at `0x180015b3b`
- `USER32!IsWindow` at `0x180015b3b`

## pseudocode

```c
void __fastcall CleanupDialogParam(HWND a1, HWND *a2)
{
  HWND v3; // rcx
  HWND v4; // rcx
  HWND v5; // rcx
  HICON v6; // rcx

  SHRemoveDefaultDialogFont(a1);
  if ( IsWindow(a2[12]) )
    DestroyWindow(a2[12]);
  v3 = a2[13];
  if ( v3 )
  {
    LocalFree(v3);
    a2[13] = 0;
  }
  v4 = a2[15];
  if ( v4 )
  {
    DeleteObject(v4);
    a2[15] = 0;
  }
  v5 = a2[16];
  if ( v5 )
  {
    DeleteObject(v5);
    a2[16] = 0;
  }
  v6 = (HICON)a2[17];
  if ( v6 )
  {
    DestroyIcon(v6);
    a2[17] = 0;
  }
}

```

## disassembly

```asm
0x180015b28  push    rbx
0x180015b2a  sub     rsp, 20h
0x180015b2e  mov     rbx, rdx
0x180015b31  call    cs:__imp_SHRemoveDefaultDialogFont
0x180015b37  mov     rcx, [rbx+60h]; hWnd
0x180015b3b  call    cs:__imp_IsWindow
0x180015b41  test    eax, eax
0x180015b43  jz      short loc_180015B4F
0x180015b45  mov     rcx, [rbx+60h]; hWnd
0x180015b49  call    cs:__imp_DestroyWindow
0x180015b4f  mov     rcx, [rbx+68h]; hMem
0x180015b53  test    rcx, rcx
0x180015b56  jz      short loc_180015B66
0x180015b58  call    cs:__imp_LocalFree
0x180015b5e  mov     qword ptr [rbx+68h], 0
0x180015b66  mov     rcx, [rbx+78h]; ho
0x180015b6a  test    rcx, rcx
0x180015b6d  jz      short loc_180015B7D
0x180015b6f  call    cs:__imp_DeleteObject
0x180015b75  mov     qword ptr [rbx+78h], 0
0x180015b7d  mov     rcx, [rbx+80h]; ho
0x180015b84  test    rcx, rcx
0x180015b87  jz      short loc_180015B9A
0x180015b89  call    cs:__imp_DeleteObject
0x180015b8f  mov     qword ptr [rbx+80h], 0
0x180015b9a  mov     rcx, [rbx+88h]; hIcon
0x180015ba1  test    rcx, rcx
0x180015ba4  jz      short loc_180015BB7
0x180015ba6  call    cs:__imp_DestroyIcon
0x180015bac  mov     qword ptr [rbx+88h], 0
0x180015bb7  add     rsp, 20h
0x180015bbb  pop     rbx
0x180015bbc  retn
```
