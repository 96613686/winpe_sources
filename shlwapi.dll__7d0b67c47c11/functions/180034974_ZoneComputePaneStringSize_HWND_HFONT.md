# _ZoneComputePaneStringSize(HWND__ *,HFONT__ *)

- ea: `0x180034974`
- end: `0x180034bca`
- name: `?_ZoneComputePaneStringSize@@YAHPEAUHWND__@@PEAUHFONT__@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(HWND hWnd, HFONT h)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035020`

## callees

- `0x180012550`
- `0x180013066`
- `0x180034974`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800349fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800349fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034a09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034b17`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034a09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034b17`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180034b70`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180034b70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034a86`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034a86`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034a2c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034a49`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034a2c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034a49`
- `GDI32!GetTextExtentPoint32W` at `0x180034a1f`
- `GDI32!GetTextExtentPoint32W` at `0x180034b2d`
- `GDI32!GetTextExtentPoint32W` at `0x180034a1f`
- `GDI32!GetTextExtentPoint32W` at `0x180034b2d`
- `GDI32!SelectObject` at `0x1800349bb`
- `GDI32!SelectObject` at `0x180034b7c`
- `GDI32!SelectObject` at `0x1800349bb`
- `GDI32!SelectObject` at `0x180034b7c`
- `USER32!GetDC` at `0x1800349ac`
- `USER32!GetDC` at `0x1800349ac`
- `USER32!ReleaseDC` at `0x180034b88`
- `USER32!ReleaseDC` at `0x180034b88`

## pseudocode

```c
__int64 __fastcall _ZoneComputePaneStringSize(HWND hWnd, HFONT h)
{
  HDC DC; // rsi
  HGDIOBJ v5; // r12
  int v6; // eax
  LONG cx; // edi
  HRESULT v8; // eax
  HRESULT v9; // ebx
  unsigned int i; // r14d
  int v11; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v15; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  struct tagSIZE v17; // [rsp+48h] [rbp-B8h] BYREF
  struct tagSIZE psizl; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[734]; // [rsp+64h] [rbp-9Ch] BYREF

  DC = GetDC(hWnd);
  v17 = 0;
  psizl = 0;
  v5 = SelectObject(DC, h);
  memset_0(&v19, 0, 0x5B4u);
  LoadStringW(g_hinst, 0x119u, Buffer, 260);
  v6 = lstrlenW(Buffer);
  GetTextExtentPoint32W(DC, Buffer, v6, &psizl);
  cx = 0;
  v8 = CoInitializeEx(0, 6u);
  v9 = v8;
  if ( v8 == 1 )
    goto LABEL_4;
  if ( v8 != -2147417850 )
    goto LABEL_7;
  v9 = CoInitializeEx(0, 4u);
  if ( v9 == 1 )
  {
LABEL_4:
    v9 = 0;
  }
  else if ( v9 == -2147417850 )
  {
    v9 = 1;
  }
LABEL_7:
  ppv = 0;
  if ( CoCreateInstance(&CLSID_InternetZoneManager, 0, 1u, &IID_IInternetZoneManager, &ppv) >= 0 )
  {
    v15 = 0;
    v14 = 0;
    if ( (*(int (__fastcall **)(LPVOID, unsigned int *, unsigned int *, _QWORD))(*(_QWORD *)ppv + 88LL))(
           ppv,
           &v15,
           &v14,
           0) >= 0 )
    {
      for ( i = 0; i < v14; ++i )
      {
        v16 = 0;
        v19 = 1460;
        (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)ppv + 96LL))(ppv, v15, i, &v16);
        (*(void (__fastcall **)(LPVOID, _QWORD, int *))(*(_QWORD *)ppv + 24LL))(ppv, v16, &v19);
        v11 = lstrlenW(Buffer);
        GetTextExtentPoint32W(DC, Buffer, v11, &v17);
        if ( cx < v17.cx )
          cx = v17.cx;
      }
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 104LL))(ppv, v15);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( !v9 )
    CoUninitialize();
  SelectObject(DC, v5);
  ReleaseDC(hWnd, DC);
  if ( cx )
    return (unsigned int)(cx + psizl.cx);
  else
    return 220;
}

```

## disassembly

```asm
0x180034974  mov     [rsp-8+arg_10], rbx
0x180034979  mov     [rsp-8+arg_18], rsi
0x18003497e  push    rbp
0x18003497f  push    rdi
0x180034980  push    r12
0x180034982  push    r14
0x180034984  push    r15
0x180034986  lea     rbp, [rsp-530h]
0x18003498e  sub     rsp, 630h
0x180034995  mov     rax, cs:__security_cookie
0x18003499c  xor     rax, rsp
0x18003499f  mov     [rbp+550h+var_30], rax
0x1800349a6  mov     rbx, rdx
0x1800349a9  mov     r15, rcx
0x1800349ac  call    cs:__imp_GetDC
0x1800349b2  mov     rcx, rax; hdc
0x1800349b5  mov     rdx, rbx; h
0x1800349b8  mov     rsi, rax
0x1800349bb  call    cs:__imp_SelectObject
0x1800349c1  xor     edx, edx; Val
0x1800349c3  mov     qword ptr [rsp+650h+var_608.cx], 0
0x1800349cc  mov     r8d, 5B4h; Size
0x1800349d2  mov     qword ptr [rsp+650h+psizl.cx], 0
0x1800349db  lea     rcx, [rsp+650h+var_5F0]; void *
0x1800349e0  mov     r12, rax
0x1800349e3  call    memset_0
0x1800349e8  mov     rcx, cs:g_hinst; hInstance
0x1800349ef  lea     r8, [rsp+650h+Buffer]; lpBuffer
0x1800349f4  mov     r9d, 104h; cchBufferMax
0x1800349fa  lea     edx, [r9+15h]; uID
0x1800349fe  call    cs:__imp_LoadStringW
0x180034a04  lea     rcx, [rsp+650h+Buffer]; lpString
0x180034a09  call    cs:__imp_lstrlenW
0x180034a0f  lea     r9, [rsp+650h+psizl]; psizl
0x180034a14  mov     rcx, rsi; hdc
0x180034a17  mov     r8d, eax; c
0x180034a1a  lea     rdx, [rsp+650h+Buffer]; lpString
0x180034a1f  call    cs:__imp_GetTextExtentPoint32W
0x180034a25  xor     edi, edi
0x180034a27  xor     ecx, ecx; pvReserved
0x180034a29  lea     edx, [rdi+6]; dwCoInit
0x180034a2c  call    cs:__imp_CoInitializeEx
0x180034a32  lea     r14d, [rdi+1]
0x180034a36  mov     ebx, eax
0x180034a38  cmp     eax, r14d
0x180034a3b  jz      short loc_180034A56
0x180034a3d  cmp     eax, 80010106h
0x180034a42  jnz     short loc_180034A64
0x180034a44  lea     edx, [rdi+4]; dwCoInit
0x180034a47  xor     ecx, ecx; pvReserved
0x180034a49  call    cs:__imp_CoInitializeEx
0x180034a4f  mov     ebx, eax
0x180034a51  cmp     eax, r14d
0x180034a54  jnz     short loc_180034A5A
0x180034a56  xor     ebx, ebx
0x180034a58  jmp     short loc_180034A64
0x180034a5a  cmp     ebx, 80010106h
0x180034a60  cmovz   ebx, r14d
0x180034a64  lea     rax, [rsp+650h+var_620]
0x180034a69  mov     [rsp+650h+var_620], rdi
0x180034a6e  lea     r9, IID_IInternetZoneManager; riid
0x180034a75  mov     [rsp+650h+ppv], rax; ppv
0x180034a7a  mov     r8d, r14d; dwClsContext
0x180034a7d  lea     rcx, CLSID_InternetZoneManager; rclsid
0x180034a84  xor     edx, edx; pUnkOuter
0x180034a86  call    cs:__imp_CoCreateInstance
0x180034a8c  test    eax, eax
0x180034a8e  js      loc_180034B6C
0x180034a94  mov     rcx, [rsp+650h+var_620]
0x180034a99  lea     r8, [rsp+650h+var_618]
0x180034a9e  mov     [rsp+650h+var_614], edi
0x180034aa2  lea     rdx, [rsp+650h+var_614]
0x180034aa7  mov     [rsp+650h+var_618], edi
0x180034aab  xor     r9d, r9d
0x180034aae  mov     rax, [rcx]
0x180034ab1  mov     rax, [rax+58h]
0x180034ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034aba  test    eax, eax
0x180034abc  js      loc_180034B5B
0x180034ac2  xor     r14d, r14d
0x180034ac5  cmp     [rsp+650h+var_618], edi
0x180034ac9  jbe     short loc_180034B46
0x180034acb  mov     rcx, [rsp+650h+var_620]
0x180034ad0  lea     r9, [rsp+650h+var_610]
0x180034ad5  mov     edx, [rsp+650h+var_614]
0x180034ad9  mov     r8d, r14d
0x180034adc  mov     [rsp+650h+var_610], 0
0x180034ae4  mov     [rsp+650h+var_5F0], 5B4h
0x180034aec  mov     rax, [rcx]
0x180034aef  mov     rax, [rax+60h]
0x180034af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034af8  mov     rcx, [rsp+650h+var_620]
0x180034afd  lea     r8, [rsp+650h+var_5F0]
0x180034b02  mov     edx, [rsp+650h+var_610]
0x180034b06  mov     rax, [rcx]
0x180034b09  mov     rax, [rax+18h]
0x180034b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b12  lea     rcx, [rsp+650h+Buffer]; lpString
0x180034b17  call    cs:__imp_lstrlenW
0x180034b1d  lea     r9, [rsp+650h+var_608]; psizl
0x180034b22  mov     rcx, rsi; hdc
0x180034b25  mov     r8d, eax; c
0x180034b28  lea     rdx, [rsp+650h+Buffer]; lpString
0x180034b2d  call    cs:__imp_GetTextExtentPoint32W
0x180034b33  cmp     edi, [rsp+650h+var_608.cx]
0x180034b37  cmovl   edi, [rsp+650h+var_608.cx]
0x180034b3c  inc     r14d
0x180034b3f  cmp     r14d, [rsp+650h+var_618]
0x180034b44  jb      short loc_180034ACB
0x180034b46  mov     rcx, [rsp+650h+var_620]
0x180034b4b  mov     edx, [rsp+650h+var_614]
0x180034b4f  mov     rax, [rcx]
0x180034b52  mov     rax, [rax+68h]
0x180034b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b5b  mov     rcx, [rsp+650h+var_620]
0x180034b60  mov     rax, [rcx]
0x180034b63  mov     rax, [rax+10h]
0x180034b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b6c  test    ebx, ebx
0x180034b6e  jnz     short loc_180034B76
0x180034b70  call    cs:__imp_CoUninitialize
0x180034b76  mov     rdx, r12; h
0x180034b79  mov     rcx, rsi; hdc
0x180034b7c  call    cs:__imp_SelectObject
0x180034b82  mov     rdx, rsi; hDC
0x180034b85  mov     rcx, r15; hWnd
0x180034b88  call    cs:__imp_ReleaseDC
0x180034b8e  test    edi, edi
0x180034b90  jnz     short loc_180034B99
0x180034b92  mov     eax, 0DCh
0x180034b97  jmp     short loc_180034B9F
0x180034b99  mov     eax, [rsp+650h+psizl.cx]
0x180034b9d  add     eax, edi
0x180034b9f  mov     rcx, [rbp+550h+var_30]
0x180034ba6  xor     rcx, rsp; StackCookie
0x180034ba9  call    __security_check_cookie
0x180034bae  lea     r11, [rsp+650h+var_20]
0x180034bb6  mov     rbx, [r11+40h]
0x180034bba  mov     rsi, [r11+48h]
0x180034bbe  mov     rsp, r11
0x180034bc1  pop     r15
0x180034bc3  pop     r14
0x180034bc5  pop     r12
0x180034bc7  pop     rdi
0x180034bc8  pop     rbp
0x180034bc9  retn
```
