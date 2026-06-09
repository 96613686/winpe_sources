# MoveControlsCallback(HWND__ *,__int64)

- ea: `0x18001bd00`
- end: `0x18001be2b`
- name: `?MoveControlsCallback@@YAHPEAUHWND__@@_J@Z`
- size: `299`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001bd00`
- `0x18001bf40`

## import_xrefs

- `USER32!MoveWindow` at `0x18001bdf0`
- `USER32!MoveWindow` at `0x18001bdf0`
- `USER32!GetWindowInfo` at `0x18001bd8e`
- `USER32!GetWindowInfo` at `0x18001bd9f`
- `USER32!GetWindowInfo` at `0x18001bd8e`
- `USER32!GetWindowInfo` at `0x18001bd9f`
- `USER32!InvalidateRect` at `0x18001bdff`
- `USER32!InvalidateRect` at `0x18001bdff`

## pseudocode

```c
__int64 __fastcall MoveControlsCallback(HWND a1, __int64 a2)
{
  _QWORD *v3; // rdx
  int v5; // ecx
  HWND v6; // rcx
  int v7; // edx
  struct tagWINDOWINFO v9; // [rsp+30h] [rbp-39h] BYREF
  struct tagWINDOWINFO pwi; // [rsp+70h] [rbp+7h] BYREF

  v3 = *(_QWORD **)(a2 + 16);
  memset(&v9, 0, sizeof(v9));
  memset(&pwi, 0, sizeof(pwi));
  if ( v3 && *v3 )
  {
    v5 = 0;
    while ( a1 != (HWND)v3[v5] )
    {
      if ( !v3[++v5] )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    v6 = *(HWND *)a2;
    v9.cbSize = 60;
    pwi.cbSize = 60;
    if ( GetWindowInfo(v6, &pwi) && GetWindowInfo(a1, &v9) )
    {
      if ( *(_DWORD *)(a2 + 24) )
        v7 = pwi.rcWindow.right - v9.rcWindow.right;
      else
        v7 = v9.rcWindow.left - pwi.rcWindow.left;
      MoveWindow(
        a1,
        *(_DWORD *)(a2 + 8) + v7,
        v9.rcWindow.top + *(_DWORD *)(a2 + 12) - pwi.rcWindow.top,
        v9.rcWindow.right - v9.rcWindow.left,
        v9.rcWindow.bottom - v9.rcWindow.top,
        1);
      InvalidateRect(*(HWND *)a2, 0, 1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001bd00  mov     [rsp-8+arg_10], rbx
0x18001bd05  mov     [rsp-8+arg_18], rdi
0x18001bd0a  push    rbp
0x18001bd0b  lea     rbp, [rsp-57h]
0x18001bd10  sub     rsp, 0C0h
0x18001bd17  mov     rax, cs:__security_cookie
0x18001bd1e  xor     rax, rsp
0x18001bd21  mov     [rbp+57h+var_10], rax
0x18001bd25  xorps   xmm0, xmm0
0x18001bd28  xorps   xmm1, xmm1
0x18001bd2b  mov     rbx, rdx
0x18001bd2e  xor     eax, eax
0x18001bd30  mov     rdx, [rdx+10h]
0x18001bd34  mov     rdi, rcx
0x18001bd37  movups  xmmword ptr [rbp+57h+var_90.rcClient.bottom], xmm0
0x18001bd3b  movups  xmmword ptr [rbp+57h+pwi.rcClient.bottom], xmm1
0x18001bd3f  movups  xmmword ptr [rbp+57h+var_90.cbSize], xmm0
0x18001bd43  movups  xmmword ptr [rbp+57h+var_90.rcWindow.bottom], xmm0
0x18001bd47  movups  xmmword ptr [rbp+57h+var_90.dwWindowStatus], xmm0
0x18001bd4b  movups  xmmword ptr [rbp+57h+pwi.cbSize], xmm1
0x18001bd4f  movups  xmmword ptr [rbp+57h+pwi.rcWindow.bottom], xmm1
0x18001bd53  movups  xmmword ptr [rbp+57h+pwi.dwWindowStatus], xmm1
0x18001bd57  test    rdx, rdx
0x18001bd5a  jz      short loc_18001BD7C
0x18001bd5c  cmp     [rdx], rax
0x18001bd5f  jz      short loc_18001BD7C
0x18001bd61  xor     ecx, ecx
0x18001bd63  movsxd  rax, ecx
0x18001bd66  cmp     rdi, [rdx+rax*8]
0x18001bd6a  jz      loc_18001BE05
0x18001bd70  inc     ecx
0x18001bd72  movsxd  rax, ecx
0x18001bd75  cmp     qword ptr [rdx+rax*8], 0
0x18001bd7a  jnz     short loc_18001BD63
0x18001bd7c  mov     rcx, [rbx]; hwnd
0x18001bd7f  lea     rdx, [rbp+57h+pwi]; pwi
0x18001bd83  mov     eax, 3Ch ; '<'
0x18001bd88  mov     [rbp+57h+var_90.cbSize], eax
0x18001bd8b  mov     [rbp+57h+pwi.cbSize], eax
0x18001bd8e  call    cs:__imp_GetWindowInfo
0x18001bd94  test    eax, eax
0x18001bd96  jz      short loc_18001BE05
0x18001bd98  lea     rdx, [rbp+57h+var_90]; pwi
0x18001bd9c  mov     rcx, rdi; hwnd
0x18001bd9f  call    cs:__imp_GetWindowInfo
0x18001bda5  test    eax, eax
0x18001bda7  jz      short loc_18001BE05
0x18001bda9  mov     r10d, [rbx+0Ch]
0x18001bdad  sub     r10d, [rbp+57h+pwi.rcWindow.top]
0x18001bdb1  mov     r8d, [rbp+57h+var_90.rcWindow.bottom]
0x18001bdb5  mov     r9d, [rbp+57h+var_90.rcWindow.right]
0x18001bdb9  mov     edx, [rbp+57h+var_90.rcWindow.left]
0x18001bdbc  sub     r9d, edx; nWidth
0x18001bdbf  add     r10d, [rbp+57h+var_90.rcWindow.top]
0x18001bdc3  sub     r8d, [rbp+57h+var_90.rcWindow.top]
0x18001bdc7  cmp     dword ptr [rbx+18h], 0
0x18001bdcb  mov     eax, [rbx+8]
0x18001bdce  jz      short loc_18001BDD8
0x18001bdd0  mov     edx, [rbp+57h+pwi.rcWindow.right]
0x18001bdd3  sub     edx, [rbp+57h+var_90.rcWindow.right]
0x18001bdd6  jmp     short loc_18001BDDB
0x18001bdd8  sub     edx, [rbp+57h+pwi.rcWindow.left]
0x18001bddb  mov     [rsp+0C0h+bRepaint], 1; bRepaint
0x18001bde3  add     edx, eax; X
0x18001bde5  mov     [rsp+0C0h+nHeight], r8d; nHeight
0x18001bdea  mov     rcx, rdi; hWnd
0x18001bded  mov     r8d, r10d; Y
0x18001bdf0  call    cs:__imp_MoveWindow
0x18001bdf6  mov     rcx, [rbx]; hWnd
0x18001bdf9  xor     edx, edx; lpRect
0x18001bdfb  lea     r8d, [rdx+1]; bErase
0x18001bdff  call    cs:__imp_InvalidateRect
0x18001be05  mov     eax, 1
0x18001be0a  mov     rcx, [rbp+57h+var_10]
0x18001be0e  xor     rcx, rsp; StackCookie
0x18001be11  call    __security_check_cookie
0x18001be16  lea     r11, [rsp+0C0h+var_s0]
0x18001be1e  mov     rbx, [r11+20h]
0x18001be22  mov     rdi, [r11+28h]
0x18001be26  mov     rsp, r11
0x18001be29  pop     rbp
0x18001be2a  retn
```
