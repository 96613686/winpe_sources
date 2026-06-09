# ATL::AtlAxWindowProc

- ea: `0x140002b10`
- end: `0x140002d8b`
- name: `ATL::AtlAxWindowProc`
- size: `635`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001390`
- `0x140002b10`
- `0x140009710`
- `0x14000e380`
- `0x14000e3e0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x140002c3b`
- `KERNEL32!GlobalUnlock` at `0x140002c3b`
- `KERNEL32!GlobalLock` at `0x140002c20`
- `KERNEL32!GlobalLock` at `0x140002c20`
- `KERNEL32!GlobalAlloc` at `0x140002c0b`
- `KERNEL32!GlobalAlloc` at `0x140002c0b`
- `USER32!GetWindow` at `0x140002cf1`
- `USER32!GetWindow` at `0x140002cf1`
- `USER32!DefWindowProcW` at `0x140002d68`
- `USER32!DefWindowProcW` at `0x140002d68`
- `USER32!GetWindowTextLengthW` at `0x140002b8e`
- `USER32!GetWindowTextLengthW` at `0x140002b8e`
- `USER32!GetWindowLongW` at `0x140002d08`
- `USER32!GetWindowLongW` at `0x140002d1a`
- `USER32!GetWindowLongW` at `0x140002d08`
- `USER32!GetWindowLongW` at `0x140002d1a`
- `USER32!GetWindowTextW` at `0x140002bcb`
- `USER32!GetWindowTextW` at `0x140002bcb`
- `USER32!SetWindowLongPtrW` at `0x140002ce3`
- `USER32!SetWindowLongPtrW` at `0x140002ce3`
- `USER32!SetWindowTextW` at `0x140002bdb`
- `USER32!SetWindowTextW` at `0x140002bdb`
- `USER32!GetWindowLongPtrW` at `0x140002b5b`
- `USER32!GetWindowLongPtrW` at `0x140002b5b`
- `USER32!SetWindowLongW` at `0x140002d2d`
- `USER32!SetWindowLongW` at `0x140002d2d`
- `ole32!CreateStreamOnHGlobal` at `0x140002c4b`
- `ole32!CreateStreamOnHGlobal` at `0x140002c4b`
- `ole32!OleInitialize` at `0x140002b85`
- `ole32!OleInitialize` at `0x140002b85`
- `ole32!OleUninitialize` at `0x140002b78`
- `ole32!OleUninitialize` at `0x140002b78`

## pseudocode

```c
LRESULT __fastcall ATL::AtlAxWindowProc(
        HWND hWnd,
        UINT Msg,
        int (__fastcall ***wParam)(_QWORD, GUID *, LONG_PTR *),
        unsigned __int16 **lParam)
{
  WPARAM v5; // r15
  LONG_PTR WindowLongPtrW; // rax
  int v9; // r8d
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  unsigned int v15; // ecx
  unsigned int v16; // r15d
  HGLOBAL v17; // rax
  void *v18; // rbx
  void *v19; // rax
  int (__fastcall **v20)(_QWORD, GUID *, LONG_PTR *); // rax
  int (__fastcall ***v21)(_QWORD, GUID *, LONG_PTR *); // rbx
  HWND Window; // rax
  LONG WindowLongW; // eax
  WCHAR String[4]; // [rsp+20h] [rbp+0h] BYREF
  int (__fastcall ***v26)(_QWORD, GUID *, LONG_PTR *); // [rsp+28h] [rbp+8h]
  LONG_PTR dwNewLong; // [rsp+30h] [rbp+10h] BYREF

  v26 = wParam;
  v5 = (WPARAM)wParam;
  if ( Msg != 1 )
  {
    if ( Msg == 130 )
    {
      WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
      if ( WindowLongPtrW )
        (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
      OleUninitialize();
    }
    return DefWindowProcW(hWnd, Msg, v5, (LPARAM)lParam);
  }
  OleInitialize(0);
  v9 = GetWindowTextLengthW(hWnd) + 1;
  v10 = 2LL * v9;
  v11 = v10 + 15;
  if ( v10 + 15 < v10 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  GetWindowTextW(hWnd, String, v9);
  SetWindowTextW(hWnd, &WindowName);
  dwNewLong = 0;
  if ( lParam && *lParam )
  {
    v15 = **lParam;
    *(_QWORD *)String = 0;
    if ( (_WORD)v15 )
    {
      v16 = v15;
      v17 = GlobalAlloc(0x42u, v15);
      v18 = v17;
      if ( !v17 )
        goto LABEL_21;
      v19 = GlobalLock(v17);
      memcpy_0(v19, *lParam + 1, v16);
      GlobalUnlock(v18);
      CreateStreamOnHGlobal(v18, 1, (LPSTREAM *)String);
      v5 = (WPARAM)v26;
    }
  }
  else
  {
    *(_QWORD *)String = 0;
  }
  v26 = 0;
  if ( (int)AtlAxCreateControl(String) >= 0 )
  {
    v21 = v26;
    if ( (**v26)(v26, &IID_IAxWinHostWindow, &dwNewLong) >= 0 )
    {
      SetWindowLongPtrW(hWnd, -21, dwNewLong);
      Window = GetWindow(hWnd, 5u);
      if ( Window && (GetWindowLongW(Window, -20) & 0x10000) != 0 )
      {
        WindowLongW = GetWindowLongW(hWnd, -20);
        SetWindowLongW(hWnd, -20, WindowLongW | 0x10000);
      }
      if ( v21 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, LONG_PTR *)))(*v21)[2])(v21);
      if ( *(_QWORD *)String )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
      return DefWindowProcW(hWnd, Msg, v5, (LPARAM)lParam);
    }
    if ( v21 )
    {
      v20 = *v21;
      goto LABEL_20;
    }
  }
  else if ( v26 )
  {
    v20 = *v26;
LABEL_20:
    ((void (*)(void))v20[2])();
  }
LABEL_21:
  if ( *(_QWORD *)String )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)String + 16LL))(*(_QWORD *)String);
  return -1;
}

```

## disassembly

```asm
0x140002b10  push    rbp
0x140002b12  push    rbx
0x140002b13  push    rsi
0x140002b14  push    rdi
0x140002b15  push    r12
0x140002b17  push    r13
0x140002b19  push    r14
0x140002b1b  push    r15
0x140002b1d  sub     rsp, 48h
0x140002b21  lea     rbp, [rsp+20h]
0x140002b26  mov     rax, cs:__security_cookie
0x140002b2d  xor     rax, rbp
0x140002b30  mov     [rbp+60h+var_48], rax
0x140002b34  mov     eax, edx
0x140002b36  mov     [rbp+60h+var_58], r8
0x140002b3a  mov     r14, r9
0x140002b3d  mov     r15, r8
0x140002b40  mov     r13d, edx
0x140002b43  mov     rsi, rcx
0x140002b46  sub     eax, 1
0x140002b49  jz      short loc_140002B83
0x140002b4b  cmp     eax, 81h
0x140002b50  jnz     loc_140002D5C
0x140002b56  mov     edx, 0FFFFFFEBh; nIndex
0x140002b5b  call    cs:__imp_GetWindowLongPtrW
0x140002b61  mov     r8, rax
0x140002b64  test    rax, rax
0x140002b67  jz      short loc_140002B78
0x140002b69  mov     rcx, [rax]
0x140002b6c  mov     rax, [rcx+10h]
0x140002b70  mov     rcx, r8
0x140002b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b78  call    cs:__imp_OleUninitialize
0x140002b7e  jmp     loc_140002D5C
0x140002b83  xor     ecx, ecx; pvReserved
0x140002b85  call    cs:__imp_OleInitialize
0x140002b8b  mov     rcx, rsi; hWnd
0x140002b8e  call    cs:__imp_GetWindowTextLengthW
0x140002b94  lea     r8d, [rax+1]
0x140002b98  movsxd  rax, r8d
0x140002b9b  add     rax, rax
0x140002b9e  lea     rcx, [rax+0Fh]
0x140002ba2  cmp     rcx, rax
0x140002ba5  ja      short loc_140002BB1
0x140002ba7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140002bb1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140002bb5  mov     rax, rcx
0x140002bb8  call    _alloca_probe
0x140002bbd  sub     rsp, rcx
0x140002bc0  mov     rcx, rsi; hWnd
0x140002bc3  lea     r12, [rsp+80h+String]
0x140002bc8  mov     rdx, r12; lpString
0x140002bcb  call    cs:__imp_GetWindowTextW
0x140002bd1  lea     rdx, WindowName; lpString
0x140002bd8  mov     rcx, rsi; hWnd
0x140002bdb  call    cs:__imp_SetWindowTextW
0x140002be1  xor     edi, edi
0x140002be3  mov     [rbp+60h+dwNewLong], rdi
0x140002be7  mov     r8d, edi
0x140002bea  test    r14, r14
0x140002bed  jz      short loc_140002C5B
0x140002bef  mov     rax, [r14]
0x140002bf2  test    rax, rax
0x140002bf5  jz      short loc_140002C5B
0x140002bf7  movzx   ecx, word ptr [rax]
0x140002bfa  mov     qword ptr [rbp+60h+String], rdi
0x140002bfe  test    cx, cx
0x140002c01  jz      short loc_140002C5F
0x140002c03  mov     r15d, ecx
0x140002c06  mov     edx, ecx; dwBytes
0x140002c08  lea     ecx, [rdi+42h]; uFlags
0x140002c0b  call    cs:__imp_GlobalAlloc
0x140002c11  mov     rbx, rax
0x140002c14  test    rax, rax
0x140002c17  jz      loc_140002CB9
0x140002c1d  mov     rcx, rax; hMem
0x140002c20  call    cs:__imp_GlobalLock
0x140002c26  mov     rdx, [r14]
0x140002c29  mov     r8d, r15d; Size
0x140002c2c  add     rdx, 2; Src
0x140002c30  mov     rcx, rax; void *
0x140002c33  call    memcpy_0
0x140002c38  mov     rcx, rbx; hMem
0x140002c3b  call    cs:__imp_GlobalUnlock
0x140002c41  lea     r8, [rbp+60h+String]; ppstm
0x140002c45  mov     rcx, rbx; hGlobal
0x140002c48  lea     edx, [rdi+1]; fDeleteOnRelease
0x140002c4b  call    cs:__imp_CreateStreamOnHGlobal
0x140002c51  mov     r8, qword ptr [rbp+60h+String]
0x140002c55  mov     r15, [rbp+60h+var_58]
0x140002c59  jmp     short loc_140002C5F
0x140002c5b  mov     qword ptr [rbp+60h+String], rdi
0x140002c5f  lea     r9, [rbp+60h+var_58]
0x140002c63  mov     [rbp+60h+var_58], rdi
0x140002c67  mov     rdx, rsi
0x140002c6a  mov     rcx, r12; psz
0x140002c6d  call    AtlAxCreateControl
0x140002c72  test    eax, eax
0x140002c74  jns     short loc_140002C84
0x140002c76  mov     rcx, [rbp+60h+var_58]
0x140002c7a  test    rcx, rcx
0x140002c7d  jz      short loc_140002CB9
0x140002c7f  mov     rax, [rcx]
0x140002c82  jmp     short loc_140002CB0
0x140002c84  mov     rbx, [rbp+60h+var_58]
0x140002c88  lea     r8, [rbp+60h+dwNewLong]
0x140002c8c  lea     rdx, IID_IAxWinHostWindow
0x140002c93  mov     rcx, rbx
0x140002c96  mov     rax, [rbx]
0x140002c99  mov     rax, [rax]
0x140002c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ca1  test    eax, eax
0x140002ca3  jns     short loc_140002CD7
0x140002ca5  test    rbx, rbx
0x140002ca8  jz      short loc_140002CB9
0x140002caa  mov     rax, [rbx]
0x140002cad  mov     rcx, rbx
0x140002cb0  mov     rax, [rax+10h]
0x140002cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cb9  mov     rcx, qword ptr [rbp+60h+String]
0x140002cbd  test    rcx, rcx
0x140002cc0  jz      short loc_140002CCE
0x140002cc2  mov     rax, [rcx]
0x140002cc5  mov     rax, [rax+10h]
0x140002cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cce  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002cd2  jmp     loc_140002D6E
0x140002cd7  mov     r8, [rbp+60h+dwNewLong]; dwNewLong
0x140002cdb  mov     edx, 0FFFFFFEBh; nIndex
0x140002ce0  mov     rcx, rsi; hWnd
0x140002ce3  call    cs:__imp_SetWindowLongPtrW
0x140002ce9  mov     edx, 5; uCmd
0x140002cee  mov     rcx, rsi; hWnd
0x140002cf1  call    cs:__imp_GetWindow
0x140002cf7  test    rax, rax
0x140002cfa  jz      short loc_140002D33
0x140002cfc  mov     r12d, 0FFFFFFECh
0x140002d02  mov     rcx, rax; hWnd
0x140002d05  mov     edx, r12d; nIndex
0x140002d08  call    cs:__imp_GetWindowLongW
0x140002d0e  bt      eax, 10h
0x140002d12  jnb     short loc_140002D33
0x140002d14  mov     edx, r12d; nIndex
0x140002d17  mov     rcx, rsi; hWnd
0x140002d1a  call    cs:__imp_GetWindowLongW
0x140002d20  mov     edx, r12d; nIndex
0x140002d23  mov     rcx, rsi; hWnd
0x140002d26  bts     eax, 10h
0x140002d2a  mov     r8d, eax; dwNewLong
0x140002d2d  call    cs:__imp_SetWindowLongW
0x140002d33  test    rbx, rbx
0x140002d36  jz      short loc_140002D47
0x140002d38  mov     rax, [rbx]
0x140002d3b  mov     rcx, rbx
0x140002d3e  mov     rax, [rax+10h]
0x140002d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d47  mov     rcx, qword ptr [rbp+60h+String]
0x140002d4b  test    rcx, rcx
0x140002d4e  jz      short loc_140002D5C
0x140002d50  mov     rax, [rcx]
0x140002d53  mov     rax, [rax+10h]
0x140002d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d5c  mov     r9, r14; lParam
0x140002d5f  mov     r8, r15; wParam
0x140002d62  mov     edx, r13d; Msg
0x140002d65  mov     rcx, rsi; hWnd
0x140002d68  call    cs:__imp_DefWindowProcW
0x140002d6e  mov     rcx, [rbp+60h+var_48]
0x140002d72  xor     rcx, rbp; StackCookie
0x140002d75  call    __security_check_cookie
0x140002d7a  lea     rsp, [rbp+28h]
0x140002d7e  pop     r15
0x140002d80  pop     r14
0x140002d82  pop     r13
0x140002d84  pop     r12
0x140002d86  pop     rdi
0x140002d87  pop     rsi
0x140002d88  pop     rbx
0x140002d89  pop     rbp
0x140002d8a  retn
```
