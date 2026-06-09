# SetBoldFontOnControl

- ea: `0x180026538`
- end: `0x180026606`
- name: `SetBoldFontOnControl`
- size: `206`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180017264`
- `0x180019d7c`

## callees

- `0x180008320`
- `0x180009018`
- `0x180026538`

## import_xrefs

- `GDI32!GetObjectW` at `0x1800265af`
- `GDI32!GetObjectW` at `0x1800265af`
- `GDI32!CreateFontIndirectW` at `0x1800265c6`
- `GDI32!CreateFontIndirectW` at `0x1800265c6`
- `USER32!GetParent` at `0x18002657e`
- `USER32!GetParent` at `0x18002657e`
- `USER32!SendMessageW` at `0x180026572`
- `USER32!SendMessageW` at `0x1800265e1`
- `USER32!SendMessageW` at `0x180026572`
- `USER32!SendMessageW` at `0x1800265e1`

## pseudocode

```c
HFONT __fastcall SetBoldFontOnControl(HWND hWnd)
{
  HFONT v1; // rbx
  void *v3; // rdi
  HWND Parent; // rsi
  HFONT v5; // rax
  LOGFONTW pv; // [rsp+20h] [rbp-98h] BYREF

  v1 = 0;
  v3 = 0;
  Parent = hWnd;
  do
  {
    if ( !Parent )
      break;
    v3 = (void *)SendMessageW(Parent, 0x31u, 0, 0);
    Parent = GetParent(Parent);
  }
  while ( !v3 );
  if ( v3 )
  {
    memset_0(&pv, 0, sizeof(pv));
    if ( GetObjectW(v3, 92, &pv) )
    {
      pv.lfWeight = 700;
      v5 = CreateFontIndirectW(&pv);
      v1 = v5;
      if ( v5 )
        SendMessageW(hWnd, 0x30u, (WPARAM)v5, 1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180026538  push    rbx
0x18002653a  push    rbp
0x18002653b  push    rsi
0x18002653c  push    rdi
0x18002653d  sub     rsp, 98h
0x180026544  mov     rax, cs:__security_cookie
0x18002654b  xor     rax, rsp
0x18002654e  mov     [rsp+0B8h+var_38], rax
0x180026556  xor     ebx, ebx
0x180026558  mov     rbp, rcx
0x18002655b  xor     edi, edi
0x18002655d  mov     rsi, rcx
0x180026560  test    rsi, rsi
0x180026563  jz      short loc_18002658C
0x180026565  xor     r9d, r9d; lParam
0x180026568  xor     r8d, r8d; wParam
0x18002656b  mov     rcx, rsi; hWnd
0x18002656e  lea     edx, [r9+31h]; Msg
0x180026572  call    cs:__imp_SendMessageW
0x180026578  mov     rcx, rsi; hWnd
0x18002657b  mov     rdi, rax
0x18002657e  call    cs:__imp_GetParent
0x180026584  mov     rsi, rax
0x180026587  test    rdi, rdi
0x18002658a  jz      short loc_180026560
0x18002658c  test    rdi, rdi
0x18002658f  jz      short loc_1800265E7
0x180026591  mov     esi, 5Ch ; '\'
0x180026596  lea     rcx, [rsp+0B8h+pv]; void *
0x18002659b  mov     r8d, esi; Size
0x18002659e  xor     edx, edx; Val
0x1800265a0  call    memset_0
0x1800265a5  lea     r8, [rsp+0B8h+pv]; pv
0x1800265aa  mov     edx, esi; c
0x1800265ac  mov     rcx, rdi; h
0x1800265af  call    cs:__imp_GetObjectW
0x1800265b5  test    eax, eax
0x1800265b7  jz      short loc_1800265E7
0x1800265b9  lea     rcx, [rsp+0B8h+pv]; lplf
0x1800265be  mov     [rsp+0B8h+var_88], 2BCh
0x1800265c6  call    cs:__imp_CreateFontIndirectW
0x1800265cc  mov     rbx, rax
0x1800265cf  test    rax, rax
0x1800265d2  jz      short loc_1800265E7
0x1800265d4  lea     r9d, [rsi-5Bh]; lParam
0x1800265d8  mov     r8, rax; wParam
0x1800265db  lea     edx, [rsi-2Ch]; Msg
0x1800265de  mov     rcx, rbp; hWnd
0x1800265e1  call    cs:__imp_SendMessageW
0x1800265e7  mov     rax, rbx
0x1800265ea  mov     rcx, [rsp+0B8h+var_38]
0x1800265f2  xor     rcx, rsp; StackCookie
0x1800265f5  call    __security_check_cookie
0x1800265fa  add     rsp, 98h
0x180026601  pop     rdi
0x180026602  pop     rsi
0x180026603  pop     rbp
0x180026604  pop     rbx
0x180026605  retn
```
