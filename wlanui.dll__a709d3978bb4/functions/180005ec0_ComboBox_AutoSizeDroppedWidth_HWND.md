# ComboBox_AutoSizeDroppedWidth(HWND__ *)

- ea: `0x180005ec0`
- end: `0x18000609a`
- name: `?ComboBox_AutoSizeDroppedWidth@@YAXPEAUHWND__@@@Z`
- size: `474`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008944`
- `0x180014370`

## callees

- `0x180001d8c`
- `0x180005ec0`
- `0x18001bf40`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005fc1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005fc1`
- `GDI32!GetTextExtentPoint32W` at `0x180005fab`
- `GDI32!GetTextExtentPoint32W` at `0x180005fab`
- `GDI32!SelectObject` at `0x180005f28`
- `GDI32!SelectObject` at `0x180005f28`
- `USER32!GetSystemMetrics` at `0x180006054`
- `USER32!GetSystemMetrics` at `0x180006054`
- `USER32!GetWindowRect` at `0x180005ff6`
- `USER32!GetWindowRect` at `0x180005ff6`
- `USER32!ReleaseDC` at `0x180005fd5`
- `USER32!ReleaseDC` at `0x180005fd5`
- `USER32!GetDC` at `0x180005f10`
- `USER32!GetDC` at `0x180005f10`
- `USER32!SendMessageW` at `0x180005efb`
- `USER32!SendMessageW` at `0x180005f49`
- `USER32!SendMessageW` at `0x180005f8c`
- `USER32!SendMessageW` at `0x18000600c`
- `USER32!SendMessageW` at `0x180006020`
- `USER32!SendMessageW` at `0x180006045`
- `USER32!SendMessageW` at `0x18000606e`
- `USER32!SendMessageW` at `0x180005efb`
- `USER32!SendMessageW` at `0x180005f49`
- `USER32!SendMessageW` at `0x180005f8c`
- `USER32!SendMessageW` at `0x18000600c`
- `USER32!SendMessageW` at `0x180006020`
- `USER32!SendMessageW` at `0x180006045`
- `USER32!SendMessageW` at `0x18000606e`

## pseudocode

```c
void __fastcall ComboBox_AutoSizeDroppedWidth(HWND hWnd)
{
  void *v2; // rbx
  HDC DC; // rax
  HDC v4; // rbp
  unsigned int cx; // esi
  int i; // r14d
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  __int64 v12; // r8
  unsigned int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  tagSIZE psizl; // [rsp+20h] [rbp-58h] BYREF
  LPARAM lParam[2]; // [rsp+28h] [rbp-50h] BYREF
  tagRECT Rect; // [rsp+38h] [rbp-40h] BYREF

  psizl = 0;
  v2 = (void *)SendMessageW(hWnd, 0x31u, 0, 0);
  if ( v2 )
  {
    DC = GetDC(hWnd);
    v4 = DC;
    if ( DC )
    {
      SelectObject(DC, v2);
      cx = 0;
      for ( i = 0; ; ++i )
      {
        v7 = SendMessageW(hWnd, 0x149u, i, 0);
        if ( v7 < 0 )
          break;
        v8 = v7 + 1LL;
        v9 = 2 * v8;
        if ( !is_mul_ok(v8, 2u) )
          v9 = -1;
        v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
        v11 = v10;
        if ( !v10 )
          break;
        *v10 = 0;
        SendMessageW(hWnd, 0x148u, i, (LPARAM)v10);
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        if ( GetTextExtentPoint32W(v4, v11, v12, &psizl) )
        {
          if ( cx < psizl.cx )
            cx = psizl.cx;
        }
        operator delete[](v11);
      }
      ReleaseDC(hWnd, v4);
      *(_OWORD *)lParam = 0;
      v13 = cx + 6;
      Rect = 0;
      GetWindowRect(hWnd, &Rect);
      SendMessageW(hWnd, 0x152u, 0, (LPARAM)lParam);
      v14 = SendMessageW(hWnd, 0x154u, 0, 0);
      v15 = (HIDWORD(lParam[1]) - Rect.bottom) / v14;
      if ( v15 >= (unsigned int)SendMessageW(hWnd, 0x146u, 0, 0) )
        v16 = v13;
      else
        v16 = v13 + GetSystemMetrics(2);
      SendMessageW(hWnd, 0x160u, v16, 0);
    }
  }
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_8], rbx
0x180005ec5  mov     [rsp+arg_10], rbp
0x180005eca  push    rsi
0x180005ecb  push    rdi
0x180005ecc  push    r12
0x180005ece  push    r14
0x180005ed0  push    r15
0x180005ed2  sub     rsp, 50h
0x180005ed6  mov     rax, cs:__security_cookie
0x180005edd  xor     rax, rsp
0x180005ee0  mov     [rsp+78h+var_30], rax
0x180005ee5  xor     r12d, r12d
0x180005ee8  xor     r9d, r9d; lParam
0x180005eeb  xor     r8d, r8d; wParam
0x180005eee  mov     qword ptr [rsp+78h+psizl.cx], r12
0x180005ef3  mov     rdi, rcx
0x180005ef6  lea     edx, [r12+31h]; Msg
0x180005efb  call    cs:__imp_SendMessageW
0x180005f01  mov     rbx, rax
0x180005f04  test    rax, rax
0x180005f07  jz      loc_180006074
0x180005f0d  mov     rcx, rdi; hWnd
0x180005f10  call    cs:__imp_GetDC
0x180005f16  mov     rbp, rax
0x180005f19  test    rax, rax
0x180005f1c  jz      loc_180006074
0x180005f22  mov     rdx, rbx; h
0x180005f25  mov     rcx, rax; hdc
0x180005f28  call    cs:__imp_SelectObject
0x180005f2e  mov     esi, r12d
0x180005f31  mov     r14d, r12d
0x180005f34  movsxd  r15, r14d
0x180005f37  xor     r9d, r9d; lParam
0x180005f3a  mov     r8, r15; wParam
0x180005f3d  mov     edx, 149h; Msg
0x180005f42  mov     rcx, rdi; hWnd
0x180005f45  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005f49  call    cs:__imp_SendMessageW
0x180005f4f  test    eax, eax
0x180005f51  js      short loc_180005FCF
0x180005f53  movsxd  rcx, eax
0x180005f56  lea     eax, [rbx+3]
0x180005f59  inc     rcx
0x180005f5c  mul     rcx
0x180005f5f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f66  cmovb   rax, rbx
0x180005f6a  mov     rcx, rax; unsigned __int64
0x180005f6d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005f72  mov     rbx, rax
0x180005f75  test    rax, rax
0x180005f78  jz      short loc_180005FCF
0x180005f7a  mov     r9, rax; lParam
0x180005f7d  mov     [rax], r12w
0x180005f81  mov     r8, r15; wParam
0x180005f84  mov     edx, 148h; Msg
0x180005f89  mov     rcx, rdi; hWnd
0x180005f8c  call    cs:__imp_SendMessageW
0x180005f92  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005f96  inc     r8; c
0x180005f99  cmp     [rbx+r8*2], r12w
0x180005f9e  jnz     short loc_180005F96
0x180005fa0  lea     r9, [rsp+78h+psizl]; psizl
0x180005fa5  mov     rdx, rbx; lpString
0x180005fa8  mov     rcx, rbp; hdc
0x180005fab  call    cs:__imp_GetTextExtentPoint32W
0x180005fb1  test    eax, eax
0x180005fb3  jz      short loc_180005FBE
0x180005fb5  cmp     esi, [rsp+78h+psizl.cx]
0x180005fb9  cmovb   esi, [rsp+78h+psizl.cx]
0x180005fbe  mov     rcx, rbx
0x180005fc1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005fc7  inc     r14d
0x180005fca  jmp     loc_180005F34
0x180005fcf  mov     rdx, rbp; hDC
0x180005fd2  mov     rcx, rdi; hWnd
0x180005fd5  call    cs:__imp_ReleaseDC
0x180005fdb  xorps   xmm0, xmm0
0x180005fde  lea     rdx, [rsp+78h+Rect]; lpRect
0x180005fe3  xorps   xmm1, xmm1
0x180005fe6  mov     rcx, rdi; hWnd
0x180005fe9  movups  xmmword ptr [rsp+78h+lParam], xmm0
0x180005fee  add     esi, 6
0x180005ff1  movups  xmmword ptr [rsp+78h+Rect.left], xmm1
0x180005ff6  call    cs:__imp_GetWindowRect
0x180005ffc  lea     r9, [rsp+78h+lParam]; lParam
0x180006001  xor     r8d, r8d; wParam
0x180006004  mov     edx, 152h; Msg
0x180006009  mov     rcx, rdi; hWnd
0x18000600c  call    cs:__imp_SendMessageW
0x180006012  xor     r9d, r9d; lParam
0x180006015  xor     r8d, r8d; wParam
0x180006018  mov     edx, 154h; Msg
0x18000601d  mov     rcx, rdi; hWnd
0x180006020  call    cs:__imp_SendMessageW
0x180006026  xor     edx, edx
0x180006028  xor     r9d, r9d; lParam
0x18000602b  mov     rcx, rax
0x18000602e  xor     r8d, r8d; wParam
0x180006031  mov     eax, dword ptr [rsp+78h+lParam+0Ch]
0x180006035  sub     eax, [rsp+78h+Rect.bottom]
0x180006039  div     ecx
0x18000603b  mov     edx, 146h; Msg
0x180006040  mov     rcx, rdi; hWnd
0x180006043  mov     ebx, eax
0x180006045  call    cs:__imp_SendMessageW
0x18000604b  cmp     ebx, eax
0x18000604d  jnb     short loc_18000605E
0x18000604f  mov     ecx, 2; nIndex
0x180006054  call    cs:__imp_GetSystemMetrics
0x18000605a  add     eax, esi
0x18000605c  jmp     short loc_180006060
0x18000605e  mov     eax, esi
0x180006060  mov     r8d, eax; wParam
0x180006063  xor     r9d, r9d; lParam
0x180006066  mov     edx, 160h; Msg
0x18000606b  mov     rcx, rdi; hWnd
0x18000606e  call    cs:__imp_SendMessageW
0x180006074  mov     rcx, [rsp+78h+var_30]
0x180006079  xor     rcx, rsp; StackCookie
0x18000607c  call    __security_check_cookie
0x180006081  lea     r11, [rsp+78h+var_28]
0x180006086  mov     rbx, [r11+38h]
0x18000608a  mov     rbp, [r11+40h]
0x18000608e  mov     rsp, r11
0x180006091  pop     r15
0x180006093  pop     r14
0x180006095  pop     r12
0x180006097  pop     rdi
0x180006098  pop     rsi
0x180006099  retn
```
