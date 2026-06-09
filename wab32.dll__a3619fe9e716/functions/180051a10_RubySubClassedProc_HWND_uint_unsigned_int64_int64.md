# RubySubClassedProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180051a10`
- end: `0x180051c45`
- name: `?RubySubClassedProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `565`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001d778`
- `0x180051a10`
- `0x180091eaa`
- `0x180091ef0`
- `0x180091f80`

## import_xrefs

- `KERNEL32!LCMapStringW` at `0x180051af6`
- `KERNEL32!LCMapStringW` at `0x180051af6`
- `USER32!SendMessageW` at `0x180051b6f`
- `USER32!SendMessageW` at `0x180051b6f`
- `USER32!GetDlgItem` at `0x180051b41`
- `USER32!GetDlgItem` at `0x180051b41`
- `USER32!GetWindowLongPtrW` at `0x180051a54`
- `USER32!GetWindowLongPtrW` at `0x180051b1c`
- `USER32!GetWindowLongPtrW` at `0x180051a54`
- `USER32!GetWindowLongPtrW` at `0x180051b1c`
- `USER32!GetWindowTextW` at `0x180051b83`
- `USER32!GetWindowTextW` at `0x180051baa`
- `USER32!GetWindowTextW` at `0x180051b83`
- `USER32!GetWindowTextW` at `0x180051baa`
- `USER32!SetWindowTextW` at `0x180051c05`
- `USER32!SetWindowTextW` at `0x180051c05`
- `USER32!GetParent` at `0x180051b0b`
- `USER32!GetParent` at `0x180051b0b`
- `USER32!CallWindowProcW` at `0x180051c1c`
- `USER32!CallWindowProcW` at `0x180051c1c`
- `IMM32!ImmGetContext` at `0x180051a6d`
- `IMM32!ImmGetContext` at `0x180051a6d`
- `IMM32!ImmGetCompositionStringW` at `0x180051ab5`
- `IMM32!ImmGetCompositionStringW` at `0x180051ab5`
- `IMM32!ImmReleaseContext` at `0x180051b02`
- `IMM32!ImmReleaseContext` at `0x180051b02`

## pseudocode

```c
LRESULT __fastcall RubySubClassedProc(HWND a1, UINT a2, WPARAM a3, LPARAM a4)
{
  LRESULT (__stdcall *WindowLongPtrW)(HWND, UINT, WPARAM, LPARAM); // r13
  HIMC Context; // rbx
  __int64 v10; // rdi
  __int64 v11; // r9
  HWND Parent; // rbx
  int v13; // eax
  int v14; // edx
  HWND DlgItem; // rbx
  __int64 v16; // rax
  WCHAR *v17; // rdx
  WPARAM wParam[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buf[1024]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR DestStr[1024]; // [rsp+840h] [rbp+740h] BYREF

  WindowLongPtrW = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))GetWindowLongPtrW(a1, -21);
  if ( a2 == 271 )
  {
    Context = ImmGetContext(a1);
    if ( Context )
    {
      memset_0(Buf, 0, sizeof(Buf));
      memset_0(DestStr, 0, sizeof(DestStr));
      ImmGetCompositionStringW(Context, 0x200u, Buf, 0x7FEu);
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( Buf[v11] );
      LCMapStringW(0x411u, 0x900000u, Buf, v11, DestStr, 1023);
      ImmReleaseContext(a1, Context);
      Parent = GetParent(a1);
      v13 = GetWindowLongPtrW(a1, -12) - 2765;
      if ( v13 )
      {
        if ( v13 != 1 )
          return CallWindowProcW(WindowLongPtrW, a1, a2, a3, a4);
        v14 = 6036;
      }
      else
      {
        v14 = 6037;
      }
      DlgItem = GetDlgItem(Parent, v14);
      if ( DlgItem )
      {
        wParam[0] = 0;
        SendMessageW(a1, 0xB0u, (WPARAM)wParam, (LPARAM)wParam + 4);
        GetWindowTextW(a1, Buf, 1023);
        if ( HIDWORD(wParam[0]) > LODWORD(wParam[0]) )
          goto LABEL_17;
        if ( !Buf[0] )
          goto LABEL_17;
        GetWindowTextW(DlgItem, Buf, 1023);
        v16 = -1;
        do
          ++v16;
        while ( Buf[v16] );
        do
          ++v10;
        while ( DestStr[v10] );
        if ( (unsigned __int64)(v10 + v16 + 1) < 0x400 )
        {
          StringCchCatW(Buf, 0x400u, DestStr);
          v17 = Buf;
        }
        else
        {
LABEL_17:
          v17 = DestStr;
        }
        SetWindowTextW(DlgItem, v17);
      }
    }
  }
  return CallWindowProcW(WindowLongPtrW, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180051a10  push    rbp
0x180051a12  push    rbx
0x180051a13  push    rsi
0x180051a14  push    rdi
0x180051a15  push    r12
0x180051a17  push    r13
0x180051a19  push    r14
0x180051a1b  push    r15
0x180051a1d  lea     rbp, [rsp-0F58h]
0x180051a25  mov     eax, 1058h
0x180051a2a  call    _alloca_probe
0x180051a2f  sub     rsp, rax
0x180051a32  mov     rax, cs:__security_cookie
0x180051a39  xor     rax, rsp
0x180051a3c  mov     [rbp+0F90h+var_50], rax
0x180051a43  mov     r14d, edx
0x180051a46  mov     r12, r9
0x180051a49  mov     edx, 0FFFFFFEBh; nIndex
0x180051a4e  mov     r15, r8
0x180051a51  mov     rsi, rcx
0x180051a54  call    cs:__imp_GetWindowLongPtrW
0x180051a5a  mov     r13, rax
0x180051a5d  cmp     r14d, 10Fh
0x180051a64  jnz     loc_180051C0B
0x180051a6a  mov     rcx, rsi; HWND
0x180051a6d  call    cs:__imp_ImmGetContext
0x180051a73  mov     rbx, rax
0x180051a76  test    rax, rax
0x180051a79  jz      loc_180051C0B
0x180051a7f  mov     edi, 800h
0x180051a84  lea     rcx, [rsp+1090h+Buf]; void *
0x180051a89  mov     r8d, edi; Size
0x180051a8c  xor     edx, edx; Val
0x180051a8e  call    memset_0
0x180051a93  mov     r8d, edi; Size
0x180051a96  lea     rcx, [rbp+0F90h+DestStr]; void *
0x180051a9d  xor     edx, edx; Val
0x180051a9f  call    memset_0
0x180051aa4  lea     r9d, [rdi-2]; dwBufLen
0x180051aa8  mov     edx, 200h; DWORD
0x180051aad  lea     r8, [rsp+1090h+Buf]; lpBuf
0x180051ab2  mov     rcx, rbx; HIMC
0x180051ab5  call    cs:__imp_ImmGetCompositionStringW
0x180051abb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180051abf  lea     rcx, [rsp+1090h+Buf]
0x180051ac4  mov     r9, rdi
0x180051ac7  xor     eax, eax
0x180051ac9  inc     r9; cchSrc
0x180051acc  cmp     [rcx+r9*2], ax
0x180051ad1  jnz     short loc_180051AC9
0x180051ad3  lea     rax, [rbp+0F90h+DestStr]
0x180051ada  mov     [rsp+1090h+cchDest], 3FFh; cchDest
0x180051ae2  lea     r8, [rsp+1090h+Buf]; lpSrcStr
0x180051ae7  mov     [rsp+1090h+lpDestStr], rax; lpDestStr
0x180051aec  mov     edx, 900000h; dwMapFlags
0x180051af1  mov     ecx, 411h; Locale
0x180051af6  call    cs:__imp_LCMapStringW
0x180051afc  mov     rdx, rbx; HIMC
0x180051aff  mov     rcx, rsi; HWND
0x180051b02  call    cs:__imp_ImmReleaseContext
0x180051b08  mov     rcx, rsi; hWnd
0x180051b0b  call    cs:__imp_GetParent
0x180051b11  mov     edx, 0FFFFFFF4h; nIndex
0x180051b16  mov     rcx, rsi; hWnd
0x180051b19  mov     rbx, rax
0x180051b1c  call    cs:__imp_GetWindowLongPtrW
0x180051b22  sub     eax, 0ACDh
0x180051b27  jz      short loc_180051B39
0x180051b29  cmp     eax, 1
0x180051b2c  jnz     loc_180051C0B
0x180051b32  mov     edx, 1794h
0x180051b37  jmp     short loc_180051B3E
0x180051b39  mov     edx, 1795h; nIDDlgItem
0x180051b3e  mov     rcx, rbx; hDlg
0x180051b41  call    cs:__imp_GetDlgItem
0x180051b47  mov     rbx, rax
0x180051b4a  xor     eax, eax
0x180051b4c  test    rbx, rbx
0x180051b4f  jz      loc_180051C0B
0x180051b55  lea     r9, [rsp+1090h+wParam+4]; lParam
0x180051b5a  mov     dword ptr [rsp+1090h+wParam], eax
0x180051b5e  lea     r8, [rsp+1090h+wParam]; wParam
0x180051b63  mov     dword ptr [rsp+1090h+wParam+4], eax
0x180051b67  mov     edx, 0B0h; Msg
0x180051b6c  mov     rcx, rsi; hWnd
0x180051b6f  call    cs:__imp_SendMessageW
0x180051b75  mov     r8d, 3FFh; nMaxCount
0x180051b7b  lea     rdx, [rsp+1090h+Buf]; lpString
0x180051b80  mov     rcx, rsi; hWnd
0x180051b83  call    cs:__imp_GetWindowTextW
0x180051b89  mov     eax, dword ptr [rsp+1090h+wParam]
0x180051b8d  cmp     dword ptr [rsp+1090h+wParam+4], eax
0x180051b91  ja      short loc_180051BFB
0x180051b93  xor     eax, eax
0x180051b95  cmp     [rsp+1090h+Buf], ax
0x180051b9a  jz      short loc_180051BFB
0x180051b9c  mov     r8d, 3FFh; nMaxCount
0x180051ba2  lea     rdx, [rsp+1090h+Buf]; lpString
0x180051ba7  mov     rcx, rbx; hWnd
0x180051baa  call    cs:__imp_GetWindowTextW
0x180051bb0  lea     rdx, [rsp+1090h+Buf]
0x180051bb5  mov     rax, rdi
0x180051bb8  xor     ecx, ecx
0x180051bba  inc     rax
0x180051bbd  cmp     [rdx+rax*2], cx
0x180051bc1  jnz     short loc_180051BBA
0x180051bc3  lea     rdx, [rbp+0F90h+DestStr]
0x180051bca  inc     rdi
0x180051bcd  cmp     [rdx+rdi*2], cx
0x180051bd1  jnz     short loc_180051BCA
0x180051bd3  inc     rax
0x180051bd6  mov     edx, 400h; unsigned __int64
0x180051bdb  add     rax, rdi
0x180051bde  cmp     rax, rdx
0x180051be1  jnb     short loc_180051BFB
0x180051be3  lea     r8, [rbp+0F90h+DestStr]; unsigned __int16 *
0x180051bea  lea     rcx, [rsp+1090h+Buf]; unsigned __int16 *
0x180051bef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180051bf4  lea     rdx, [rsp+1090h+Buf]
0x180051bf9  jmp     short loc_180051C02
0x180051bfb  lea     rdx, [rbp+0F90h+DestStr]; lpString
0x180051c02  mov     rcx, rbx; hWnd
0x180051c05  call    cs:__imp_SetWindowTextW
0x180051c0b  mov     r9, r15; wParam
0x180051c0e  mov     [rsp+1090h+lpDestStr], r12; lParam
0x180051c13  mov     r8d, r14d; Msg
0x180051c16  mov     rdx, rsi; hWnd
0x180051c19  mov     rcx, r13; lpPrevWndFunc
0x180051c1c  call    cs:__imp_CallWindowProcW
0x180051c22  mov     rcx, [rbp+0F90h+var_50]
0x180051c29  xor     rcx, rsp; StackCookie
0x180051c2c  call    __security_check_cookie
0x180051c31  add     rsp, 1058h
0x180051c38  pop     r15
0x180051c3a  pop     r14
0x180051c3c  pop     r13
0x180051c3e  pop     r12
0x180051c40  pop     rdi
0x180051c41  pop     rsi
0x180051c42  pop     rbx
0x180051c43  pop     rbp
0x180051c44  retn
```
