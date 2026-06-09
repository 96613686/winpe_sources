# SetFilenameToolTip(HWND__ *,ushort const *,ushort * *,HWND__ * *)

- ea: `0x180019ef8`
- end: `0x18001a06f`
- name: `?SetFilenameToolTip@@YAHPEAUHWND__@@PEBGPEAPEAGPEAPEAU1@@Z`
- size: `375`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, unsigned __int16 **, HWND *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180019d7c`

## callees

- `0x180002b60`
- `0x180008320`
- `0x180009018`
- `0x18000bf78`
- `0x180019ef8`
- `0x180027c30`

## import_xrefs

- `SHLWAPI!StrDupW` at `0x180019f88`
- `SHLWAPI!StrDupW` at `0x180019f88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019f63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019f63`
- `USER32!GetWindowRect` at `0x18001a016`
- `USER32!GetWindowRect` at `0x18001a016`
- `USER32!GetDlgItem` at `0x180019ff0`
- `USER32!GetDlgItem` at `0x180019ff0`
- `USER32!SendMessageW` at `0x18001a02c`
- `USER32!SendMessageW` at `0x18001a043`
- `USER32!SendMessageW` at `0x18001a02c`
- `USER32!SendMessageW` at `0x18001a043`

## pseudocode

```c
__int64 __fastcall SetFilenameToolTip(HWND a1, const unsigned __int16 *a2, unsigned __int16 **a3, HWND *a4)
{
  unsigned int v8; // r15d
  unsigned __int16 *v9; // rax
  __int64 v10; // r9
  HWND Window; // rax
  HWND DlgItem; // rax
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+28h] [rbp-D8h]
  int v16; // [rsp+30h] [rbp-D0h]
  ULONG_PTR v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+48h] [rbp-B8h]
  LPARAM lParam[3]; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp-88h] BYREF
  HINSTANCE v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h]
  WCHAR Buffer; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[4094]; // [rsp+B2h] [rbp-4Eh] BYREF
  WCHAR pszSrch[2048]; // [rsp+10B0h] [rbp+FB0h] BYREF

  Buffer = 0;
  v8 = 0;
  memset_0(v24, 0, sizeof(v24));
  LoadStringW(g_hinst, 0x8508u, &Buffer, 2048);
  StringCchPrintfW(pszSrch, 0x800u, &Buffer, a2);
  v9 = StrDupW(pszSrch);
  *a3 = v9;
  if ( v9 )
  {
    Window = SHFusionCreateWindow(L"tooltips_class32", 0, 0x80000001, v10, v14, v15, v16, a1, v17, v18, 0);
    *a4 = Window;
    if ( Window )
    {
      memset_0(lParam, 0, 0x48u);
      lParam[0] = 0x1100000048LL;
      lParam[1] = (LPARAM)a1;
      DlgItem = GetDlgItem(a1, 4419);
      v22 = -1;
      lParam[2] = (LPARAM)DlgItem;
      v21 = g_hinst;
      GetWindowRect(DlgItem, &Rect);
      SendMessageW(*a4, 0x432u, 0, (LPARAM)lParam);
      SendMessageW(*a4, 0x418u, 0, 300);
      return 1;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180019ef8  push    rbp
0x180019efa  push    rbx
0x180019efb  push    rsi
0x180019efc  push    rdi
0x180019efd  push    r14
0x180019eff  push    r15
0x180019f01  lea     rbp, [rsp-1FC8h]
0x180019f09  mov     eax, 20C8h
0x180019f0e  call    _alloca_probe
0x180019f13  sub     rsp, rax
0x180019f16  mov     rax, cs:__security_cookie
0x180019f1d  xor     rax, rsp
0x180019f20  mov     [rbp+1FF0h+var_40], rax
0x180019f27  mov     rdi, r8
0x180019f2a  mov     rbx, rdx
0x180019f2d  mov     rsi, rcx
0x180019f30  xor     eax, eax
0x180019f32  xor     edx, edx; Val
0x180019f34  mov     [rbp+1FF0h+Buffer], ax
0x180019f38  mov     r8d, 0FFEh; Size
0x180019f3e  lea     rcx, [rbp+1FF0h+var_203E]; void *
0x180019f42  mov     r14, r9
0x180019f45  xor     r15d, r15d
0x180019f48  call    memset_0
0x180019f4d  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180019f54  lea     r8, [rbp+1FF0h+Buffer]; lpBuffer
0x180019f58  mov     r9d, 800h; cchBufferMax
0x180019f5e  mov     edx, 8508h; uID
0x180019f63  call    cs:__imp_LoadStringW
0x180019f69  mov     r9, rbx
0x180019f6c  lea     r8, [rbp+1FF0h+Buffer]; unsigned __int16 *
0x180019f70  mov     edx, 800h; unsigned __int64
0x180019f75  lea     rcx, [rbp+1FF0h+pszSrch]; unsigned __int16 *
0x180019f7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019f81  lea     rcx, [rbp+1FF0h+pszSrch]; pszSrch
0x180019f88  call    cs:__imp_StrDupW
0x180019f8e  mov     [rdi], rax
0x180019f91  test    rax, rax
0x180019f94  jz      loc_18001A04D
0x180019f9a  mov     [rsp+20F0h+var_20A0], r15; LPVOID
0x180019f9f  lea     rcx, aTooltipsClass3; "tooltips_class32"
0x180019fa6  xor     edx, edx; lpWindowName
0x180019fa8  mov     [rsp+20F0h+var_20B8], rsi; HWND
0x180019fad  mov     r8d, 80000001h; dwStyle
0x180019fb3  call    SHFusionCreateWindow
0x180019fb8  mov     [r14], rax
0x180019fbb  test    rax, rax
0x180019fbe  jz      loc_18001A04D
0x180019fc4  lea     ebx, [r15+48h]
0x180019fc8  xor     edx, edx; Val
0x180019fca  mov     r8d, ebx; Size
0x180019fcd  lea     rcx, [rsp+20F0h+lParam]; void *
0x180019fd2  call    memset_0
0x180019fd7  mov     edx, 1143h; nIDDlgItem
0x180019fdc  mov     dword ptr [rsp+20F0h+lParam], ebx
0x180019fe0  mov     rcx, rsi; hDlg
0x180019fe3  mov     dword ptr [rsp+20F0h+lParam+4], 11h
0x180019feb  mov     [rsp+20F0h+var_2088], rsi
0x180019ff0  call    cs:__imp_GetDlgItem
0x180019ff6  lea     rdx, [rsp+20F0h+Rect]; lpRect
0x180019ffb  mov     [rbp+1FF0h+var_2060], 0FFFFFFFFFFFFFFFFh
0x18001a003  mov     rcx, rax; hWnd
0x18001a006  mov     [rsp+20F0h+var_2080], rax
0x18001a00b  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18001a012  mov     [rbp+1FF0h+var_2068], rax
0x18001a016  call    cs:__imp_GetWindowRect
0x18001a01c  mov     rcx, [r14]; hWnd
0x18001a01f  lea     r9, [rsp+20F0h+lParam]; lParam
0x18001a024  xor     r8d, r8d; wParam
0x18001a027  mov     edx, 432h; Msg
0x18001a02c  call    cs:__imp_SendMessageW
0x18001a032  mov     rcx, [r14]; hWnd
0x18001a035  mov     r9d, 12Ch; lParam
0x18001a03b  xor     r8d, r8d; wParam
0x18001a03e  mov     edx, 418h; Msg
0x18001a043  call    cs:__imp_SendMessageW
0x18001a049  lea     r15d, [rbx-47h]
0x18001a04d  mov     eax, r15d
0x18001a050  mov     rcx, [rbp+1FF0h+var_40]
0x18001a057  xor     rcx, rsp; StackCookie
0x18001a05a  call    __security_check_cookie
0x18001a05f  add     rsp, 20C8h
0x18001a066  pop     r15
0x18001a068  pop     r14
0x18001a06a  pop     rdi
0x18001a06b  pop     rsi
0x18001a06c  pop     rbx
0x18001a06d  pop     rbp
0x18001a06e  retn
```
