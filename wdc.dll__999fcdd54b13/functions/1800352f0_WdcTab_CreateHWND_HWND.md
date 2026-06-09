# WdcTab::CreateHWND(HWND__ *)

- ea: `0x1800352f0`
- end: `0x1800354d1`
- name: `?CreateHWND@WdcTab@@MEAAPEAUHWND__@@PEAU2@@Z`
- size: `481`
- prototype: `HWND __fastcall(WdcTab *this, HWND)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006a80`
- `0x18000b854`
- `0x1800352f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003539e`
- `KERNEL32!GetLastError` at `0x180035443`
- `KERNEL32!GetLastError` at `0x18003539e`
- `KERNEL32!GetLastError` at `0x180035443`
- `USER32!CreateWindowExW` at `0x18003538c`
- `USER32!CreateWindowExW` at `0x18003538c`
- `USER32!DestroyWindow` at `0x1800354ba`
- `USER32!DestroyWindow` at `0x1800354ba`
- `USER32!SendMessageW` at `0x1800353f9`
- `USER32!SendMessageW` at `0x1800353f9`

## string_xrefs

- `0x18003541f`: `WdcTab::CreateHWND`
- `0x180035476`: `WdcTab::CreateHWND`
- `0x180035499`: `WdcTab::CreateHWND`

## pseudocode

```c
HWND __fastcall WdcTab::CreateHWND(WdcTab *this, HWND a2)
{
  HWND Window; // rax
  WdcStringMap *v3; // rcx
  HWND v4; // rdi
  signed int LastError; // eax
  signed int v6; // ebx
  __int64 i; // rsi
  int v8; // eax
  signed int v9; // eax
  __int64 X; // [rsp+28h] [rbp-49h]
  unsigned int v12[6]; // [rsp+68h] [rbp-9h]
  LPARAM lParam[2]; // [rsp+80h] [rbp+Fh] BYREF
  __int128 v14; // [rsp+90h] [rbp+1Fh]
  __int64 v15; // [rsp+A0h] [rbp+2Fh]
  unsigned __int16 *v16; // [rsp+E8h] [rbp+77h] BYREF

  v12[0] = 32400;
  v15 = 0;
  v12[1] = 32401;
  v12[2] = 32402;
  v12[3] = 32403;
  v12[4] = 32404;
  v16 = 0;
  *(_OWORD *)lParam = 0;
  v14 = 0;
  Window = CreateWindowExW(0, L"SysTabControl32", 0, 0x50010000u, 0, 0, 0, 0, a2, (HMENU)0x7594, g_hInstance, 0);
  v4 = Window;
  if ( !Window )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_6;
    }
    else
    {
      v6 = -2147467259;
    }
    LODWORD(X) = v6;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\tab.cpp", "WdcTab::CreateHWND", 0, L"FAILURE: 0x%08x", X);
    return v4;
  }
  v6 = 0;
  if ( Window == HWND_MESSAGE|0x2LL )
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_6;
    }
    else
    {
      v6 = -2147467259;
    }
    LODWORD(X) = v6;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\tab.cpp", "WdcTab::CreateHWND", 0, L"FAILURE: 0x%08x", X);
LABEL_24:
    DestroyWindow(v4);
    return 0;
  }
LABEL_6:
  LODWORD(lParam[0]) = 1;
  for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
  {
    v8 = WdcStringMap::LoadStringW(v3, v12[i], &v16);
    v6 = v8;
    if ( v8 < 0 )
    {
      LODWORD(X) = v8;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\tab.cpp", "WdcTab::CreateHWND", 0, L"FAILURE: 0x%08x", X);
      goto LABEL_23;
    }
    *(_QWORD *)&v14 = v16;
    if ( (unsigned int)SendMessageW(v4, 0x133Eu, (int)i, (LPARAM)lParam) == -1 )
      goto LABEL_23;
  }
  if ( v6 >= 0 )
    return v4;
LABEL_23:
  if ( v4 )
    goto LABEL_24;
  return v4;
}

```

## disassembly

```asm
0x1800352f0  mov     r11, rsp
0x1800352f3  push    rbp
0x1800352f4  push    rbx
0x1800352f5  push    rsi
0x1800352f6  push    rdi
0x1800352f7  lea     rbp, [r11-5Fh]
0x1800352fb  sub     rsp, 0A8h
0x180035302  xor     eax, eax
0x180035304  mov     [rbp+57h+var_60], 7E90h
0x18003530b  mov     [r11-70h], rax
0x18003530f  xorps   xmm0, xmm0
0x180035312  mov     [rbp+57h+var_28], rax
0x180035316  mov     r9d, 50010000h; dwStyle
0x18003531c  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180035323  xor     r8d, r8d; lpWindowName
0x180035326  mov     [r11-78h], rax
0x18003532a  xor     ecx, ecx; dwExStyle
0x18003532c  mov     qword ptr [r11-80h], 7594h
0x180035334  mov     [rsp+40h], rdx; hWndParent
0x180035339  lea     rdx, aSystabcontrol3; "SysTabControl32"
0x180035340  mov     [rsp+0C0h+nHeight], 0; nHeight
0x180035348  mov     [rsp+0C0h+nWidth], 0; nWidth
0x180035350  mov     [rsp+0C0h+Y], 0; Y
0x180035358  mov     dword ptr [rsp+0C0h+X], 0; X
0x180035360  mov     [rbp+57h+var_5C], 7E91h
0x180035367  mov     [rbp+57h+var_58], 7E92h
0x18003536e  mov     [rbp+57h+var_54], 7E93h
0x180035375  mov     [rbp+57h+var_50], 7E94h
0x18003537c  mov     [rbp+57h+arg_10], 0
0x180035384  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x180035388  movups  [rbp+57h+var_38], xmm0
0x18003538c  call    cs:__imp_CreateWindowExW
0x180035392  mov     rdi, rax
0x180035395  test    rax, rax
0x180035398  jnz     loc_180035437
0x18003539e  call    cs:__imp_GetLastError
0x1800353a4  mov     ebx, eax
0x1800353a6  test    eax, eax
0x1800353a8  jz      short loc_18003540C
0x1800353aa  jle     short loc_1800353B5
0x1800353ac  movzx   ebx, ax
0x1800353af  or      ebx, 80070000h
0x1800353b5  test    ebx, ebx
0x1800353b7  js      short loc_180035411
0x1800353b9  mov     dword ptr [rbp+57h+lParam], 1
0x1800353c0  xor     esi, esi
0x1800353c2  cmp     esi, 5
0x1800353c5  jnb     loc_1800354AE
0x1800353cb  mov     edx, [rbp+rsi*4+57h+var_60]; unsigned int
0x1800353cf  lea     r8, [rbp+57h+arg_10]; unsigned __int16 **
0x1800353d3  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x1800353d8  mov     ebx, eax
0x1800353da  test    eax, eax
0x1800353dc  js      loc_18003548B
0x1800353e2  mov     rcx, [rbp+57h+arg_10]
0x1800353e6  lea     r9, [rbp+57h+lParam]; lParam
0x1800353ea  mov     qword ptr [rbp+57h+var_38], rcx
0x1800353ee  mov     edx, 133Eh; Msg
0x1800353f3  mov     rcx, rdi; hWnd
0x1800353f6  movsxd  r8, esi; wParam
0x1800353f9  call    cs:__imp_SendMessageW
0x1800353ff  cmp     eax, 0FFFFFFFFh
0x180035402  jz      loc_1800354B2
0x180035408  inc     esi
0x18003540a  jmp     short loc_1800353C2
0x18003540c  mov     ebx, 80004005h
0x180035411  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180035418  mov     dword ptr [rsp+0C0h+X], ebx
0x18003541c  xor     r8d, r8d; int
0x18003541f  lea     rdx, aWdctabCreatehw; "WdcTab::CreateHWND"
0x180035426  lea     rcx, aBaseDiagnosisP_35; "base\\diagnosis\\pdui\\perfmon\\mon\\ta"...
0x18003542d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180035432  jmp     loc_1800354C2
0x180035437  xor     ebx, ebx
0x180035439  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003543d  jnz     loc_1800353B9
0x180035443  call    cs:__imp_GetLastError
0x180035449  mov     ebx, eax
0x18003544b  test    eax, eax
0x18003544d  jz      short loc_180035463
0x18003544f  jle     short loc_18003545A
0x180035451  movzx   ebx, ax
0x180035454  or      ebx, 80070000h
0x18003545a  test    ebx, ebx
0x18003545c  js      short loc_180035468
0x18003545e  jmp     loc_1800353B9
0x180035463  mov     ebx, 80004005h
0x180035468  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18003546f  mov     dword ptr [rsp+0C0h+X], ebx
0x180035473  xor     r8d, r8d; int
0x180035476  lea     rdx, aWdctabCreatehw; "WdcTab::CreateHWND"
0x18003547d  lea     rcx, aBaseDiagnosisP_35; "base\\diagnosis\\pdui\\perfmon\\mon\\ta"...
0x180035484  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180035489  jmp     short loc_1800354B7
0x18003548b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180035492  mov     dword ptr [rsp+0C0h+X], eax
0x180035496  xor     r8d, r8d; int
0x180035499  lea     rdx, aWdctabCreatehw; "WdcTab::CreateHWND"
0x1800354a0  lea     rcx, aBaseDiagnosisP_35; "base\\diagnosis\\pdui\\perfmon\\mon\\ta"...
0x1800354a7  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800354ac  jmp     short loc_1800354B2
0x1800354ae  test    ebx, ebx
0x1800354b0  jns     short loc_1800354C2
0x1800354b2  test    rdi, rdi
0x1800354b5  jz      short loc_1800354C2
0x1800354b7  mov     rcx, rdi; hWnd
0x1800354ba  call    cs:__imp_DestroyWindow
0x1800354c0  xor     edi, edi
0x1800354c2  mov     rax, rdi
0x1800354c5  add     rsp, 0A8h
0x1800354cc  pop     rdi
0x1800354cd  pop     rsi
0x1800354ce  pop     rbx
0x1800354cf  pop     rbp
0x1800354d0  retn
```
