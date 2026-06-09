# CreateShowAbortDialog(HWND__ *,int,int,int,int)

- ea: `0x1800455d0`
- end: `0x180045660`
- name: `?CreateShowAbortDialog@@YAXPEAUHWND__@@HHHH@Z`
- size: `144`
- prototype: `void __fastcall(HWND, int, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180075bf8`
- `0x180077e60`

## callees

- `0x1800455d0`
- `0x180064e84`
- `0x18008ec40`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180045600`
- `KERNEL32!LocalAlloc` at `0x180045600`
- `USER32!UpdateWindow` at `0x18004564f`
- `USER32!UpdateWindow` at `0x18004564f`
- `USER32!ShowWindow` at `0x180045642`
- `USER32!ShowWindow` at `0x180045642`

## pseudocode

```c
void __fastcall CreateShowAbortDialog(HWND a1, int a2, int a3, int a4)
{
  struct _tagPerThreadGlobalData *ThreadStoragePointer; // rbx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  HWND DialogParam; // rax

  ThreadStoragePointer = GetThreadStoragePointer();
  *((_DWORD *)ThreadStoragePointer + 613) = 0;
  v9 = LocalAlloc(0x40u, 0x10u);
  if ( v9 )
  {
    *v9 = a2;
    v9[1] = a4;
    v9[2] = 0;
    v9[3] = a3;
    DialogParam = SHFusionCreateDialogParam(
                    v10,
                    (const WCHAR *)0x69,
                    a1,
                    (INT_PTR (__stdcall *)(HWND, UINT, WPARAM, LPARAM))FAbortDlgProc,
                    (LPARAM)v9);
    *((_QWORD *)ThreadStoragePointer + 307) = DialogParam;
    ShowWindow(DialogParam, 1);
    UpdateWindow(*((HWND *)ThreadStoragePointer + 307));
  }
}

```

## disassembly

```asm
0x1800455d0  push    rbx
0x1800455d2  push    rbp
0x1800455d3  push    rsi
0x1800455d4  push    rdi
0x1800455d5  push    r14
0x1800455d7  sub     rsp, 30h
0x1800455db  mov     edi, r9d
0x1800455de  mov     esi, r8d
0x1800455e1  mov     ebp, edx
0x1800455e3  mov     r14, rcx
0x1800455e6  call    ?GetThreadStoragePointer@@YAPEAU_tagPerThreadGlobalData@@XZ; GetThreadStoragePointer(void)
0x1800455eb  mov     edx, 10h; uBytes
0x1800455f0  mov     rbx, rax
0x1800455f3  mov     dword ptr [rax+994h], 0
0x1800455fd  lea     ecx, [rdx+30h]; uFlags
0x180045600  call    cs:__imp_LocalAlloc
0x180045606  test    rax, rax
0x180045609  jz      short loc_180045655
0x18004560b  lea     r9, ?FAbortDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; FAbortDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180045612  mov     [rax], ebp
0x180045614  mov     r8, r14
0x180045617  mov     [rax+4], edi
0x18004561a  mov     edx, 69h ; 'i'
0x18004561f  mov     dword ptr [rax+8], 0
0x180045626  mov     [rax+0Ch], esi
0x180045629  mov     [rsp+58h+var_38], rax
0x18004562e  call    SHFusionCreateDialogParam
0x180045633  mov     edx, 1; nCmdShow
0x180045638  mov     [rbx+998h], rax
0x18004563f  mov     rcx, rax; hWnd
0x180045642  call    cs:__imp_ShowWindow
0x180045648  mov     rcx, [rbx+998h]; hWnd
0x18004564f  call    cs:__imp_UpdateWindow
0x180045655  add     rsp, 30h
0x180045659  pop     r14
0x18004565b  pop     rdi
0x18004565c  pop     rsi
0x18004565d  pop     rbp
0x18004565e  pop     rbx
0x18004565f  retn
```
