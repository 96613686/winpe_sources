# WdcListView::OnCopy(void)

- ea: `0x18002b538`
- end: `0x18002ba24`
- name: `?OnCopy@WdcListView@@QEAAJXZ`
- size: `1260`
- prototype: `__int64 __fastcall(WdcListView *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18007ad60`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180019990`
- `0x18002b538`
- `0x18003a3c0`
- `0x18003b0ac`
- `0x180040730`
- `0x18004ab9c`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b94a`
- `KERNEL32!GetLastError` at `0x18002b94a`
- `USER32!SetClipboardData` at `0x18002b9ba`
- `USER32!SetClipboardData` at `0x18002b9ba`
- `USER32!EmptyClipboard` at `0x18002b965`
- `USER32!EmptyClipboard` at `0x18002b965`
- `USER32!CloseClipboard` at `0x18002b9c0`
- `USER32!CloseClipboard` at `0x18002b9c0`
- `USER32!OpenClipboard` at `0x18002b940`
- `USER32!OpenClipboard` at `0x18002b940`
- `USER32!SendMessageW` at `0x18002b656`
- `USER32!SendMessageW` at `0x18002b66d`
- `USER32!SendMessageW` at `0x18002b68a`
- `USER32!SendMessageW` at `0x18002b6fe`
- `USER32!SendMessageW` at `0x18002b7aa`
- `USER32!SendMessageW` at `0x18002b7c1`
- `USER32!SendMessageW` at `0x18002b81a`
- `USER32!SendMessageW` at `0x18002b893`
- `USER32!SendMessageW` at `0x18002b656`
- `USER32!SendMessageW` at `0x18002b66d`
- `USER32!SendMessageW` at `0x18002b68a`
- `USER32!SendMessageW` at `0x18002b6fe`
- `USER32!SendMessageW` at `0x18002b7aa`
- `USER32!SendMessageW` at `0x18002b7c1`
- `USER32!SendMessageW` at `0x18002b81a`
- `USER32!SendMessageW` at `0x18002b893`
- `ole32!GetHGlobalFromStream` at `0x18002b975`
- `ole32!GetHGlobalFromStream` at `0x18002b975`
- `ole32!CreateStreamOnHGlobal` at `0x18002b5d5`
- `ole32!CreateStreamOnHGlobal` at `0x18002b5d5`

## string_xrefs

- `0x18002b5ef`: `WdcListView::OnCopy`
- `0x18002b98f`: `WdcListView::OnCopy`

## pseudocode

```c
__int64 __fastcall WdcListView::OnCopy(WdcListView *this)
{
  __int64 v2; // rax
  unsigned __int16 *v3; // rdi
  unsigned __int16 *v4; // r14
  const char *v5; // rdx
  int v6; // r8d
  HWND v7; // r12
  signed int v8; // ebx
  HRESULT v9; // eax
  const char *v10; // rdx
  int v11; // r8d
  const char *v12; // rdx
  int v13; // r8d
  unsigned __int16 *v14; // rax
  HWND v15; // r15
  unsigned int v16; // ebx
  __int64 i; // rsi
  WPARAM v18; // r8
  int v19; // r13d
  LRESULT v20; // rax
  unsigned int j; // r15d
  __int64 k; // rsi
  signed int LastError; // eax
  HRESULT HGlobalFromStream; // eax
  unsigned int v26; // [rsp+30h] [rbp-D0h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  LRESULT v29; // [rsp+48h] [rbp-B8h]
  HGLOBAL phglobal; // [rsp+50h] [rbp-B0h] BYREF
  LRESULT v31; // [rsp+58h] [rbp-A8h]
  LPARAM v32; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[8]; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  LPARAM v35[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+D8h] [rbp-28h]
  LPARAM v37; // [rsp+110h] [rbp+10h] BYREF
  int v38; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v39; // [rsp+128h] [rbp+28h]
  int v40; // [rsp+130h] [rbp+30h]
  int lParam[16]; // [rsp+170h] [rbp+70h] BYREF

  v26 = 0;
  memset_0(&v32, 0, 0x58u);
  memset_0(v35, 0, 0x48u);
  v2 = *(_QWORD *)this;
  v3 = 0;
  phglobal = 0;
  v28 = 0;
  v4 = 0;
  ppstm = 0;
  v7 = (HWND)(*(__int64 (__fastcall **)(WdcListView *))(v2 + 360))(this);
  if ( !v7 )
  {
    v8 = 0;
    goto LABEL_51;
  }
  v9 = CreateStreamOnHGlobal(0, 0, &ppstm);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_4;
  v3 = (unsigned __int16 *)WdcAlloc(0x800u, v10, v11);
  if ( !v3 )
  {
    v9 = -2147024882;
    v8 = -2147024882;
LABEL_4:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
      "WdcListView::OnCopy",
      0,
      L"FAILURE: 0x%08x",
      v9);
    goto LABEL_51;
  }
  *v3 = 0;
  v14 = (unsigned __int16 *)WdcAlloc(0x800u, v12, v13);
  v4 = v14;
  if ( !v14 )
  {
    v9 = -2147024882;
    v8 = -2147024882;
    goto LABEL_4;
  }
  *v14 = 0;
  v15 = (HWND)SendMessageW(v7, 0x101Fu, 0, 0);
  v29 = SendMessageW(v15, 0x1200u, 0, 0);
  v16 = v29;
  if ( !(unsigned int)SendMessageW(v7, 0x103Bu, (unsigned int)v29, (LPARAM)lParam) )
  {
    v8 = -2147467259;
    goto LABEL_51;
  }
  *v3 = 0;
  for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
  {
    if ( (_DWORD)i )
    {
      v9 = StringCchCatW(v3, 0x400u, L"\t");
      v8 = v9;
      if ( v9 < 0 )
        goto LABEL_4;
    }
    memset_0(v35, 0, 0x48u);
    v18 = lParam[i];
    LODWORD(v35[0]) = 2;
    v36 = 1024;
    v35[1] = (LPARAM)v4;
    SendMessageW(v15, 0x120Bu, v18, (LPARAM)v35);
    v9 = StringCchCatW(v3, 0x400u, v4);
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_4;
    v16 = v29;
  }
  v9 = StringCchCatW(v3, 0x400u, L"\r\n");
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_4;
  v9 = StringCbLengthW(v3, 0x7FFFFFFFu, &v28);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_4;
  v9 = ULongLongToULong(v28, &v26);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_4;
  v9 = (*(__int64 (__fastcall **)(LPSTREAM, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
         ppstm,
         v3,
         v26,
         0);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_4;
  v19 = SendMessageW(v7, 0x1032u, 0, 0);
  v20 = SendMessageW(v7, 0x1004u, 0, 0);
  v31 = v20;
  for ( j = 0; j < (unsigned int)v20; ++j )
  {
    memset_0(v33, 0, 0x50u);
    HIDWORD(v32) = j;
    LODWORD(v32) = 4;
    if ( v19 )
    {
      LODWORD(v32) = 12;
      v34 = 2;
    }
    SendMessageW(v7, 0x104Bu, 0, (LPARAM)&v32);
    if ( !v19 || (v33[4] & 2) != 0 )
    {
      for ( k = 0; (unsigned int)k < (unsigned int)v29; k = (unsigned int)(k + 1) )
      {
        if ( (_DWORD)k )
        {
          v9 = StringCchCatW(v3, 0x400u, L"\t");
          v8 = v9;
          if ( v9 < 0 )
            goto LABEL_4;
        }
        else
        {
          *v3 = 0;
        }
        memset_0(&v37, 0, 0x58u);
        v38 = lParam[k];
        v40 = 1024;
        v39 = v4;
        SendMessageW(v7, 0x1073u, j, (LPARAM)&v37);
        v9 = StringCchCatW(v3, 0x400u, v4);
        v8 = v9;
        if ( v9 < 0 )
          goto LABEL_4;
      }
      v9 = StringCchCatW(v3, 0x400u, L"\r\n");
      v8 = v9;
      if ( v9 < 0 )
        goto LABEL_4;
      v9 = StringCbLengthW(v3, 0x7FFFFFFFu, &v28);
      v8 = v9;
      if ( v9 < 0 )
        goto LABEL_4;
      v9 = ULongLongToULong(v28, &v26);
      v8 = v9;
      if ( v9 < 0 )
        goto LABEL_4;
      v9 = (*(__int64 (__fastcall **)(LPSTREAM, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
             ppstm,
             v3,
             v26,
             0);
      v8 = v9;
      if ( v9 < 0 )
        goto LABEL_4;
    }
    LODWORD(v20) = v31;
  }
  if ( !OpenClipboard(v7) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_45;
    }
    else
    {
      v8 = -2147467259;
    }
    v9 = v8;
    goto LABEL_4;
  }
LABEL_45:
  EmptyClipboard();
  HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
  v8 = HGlobalFromStream;
  if ( HGlobalFromStream >= 0 )
    SetClipboardData(0xDu, phglobal);
  else
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
      "WdcListView::OnCopy",
      0,
      L"FAILURE: 0x%08x",
      HGlobalFromStream);
  CloseClipboard();
LABEL_51:
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v3 )
    WdcFree(v3, v5, v6);
  if ( v4 )
    WdcFree(v4, v5, v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b538  push    rbp
0x18002b53a  push    rbx
0x18002b53b  push    rsi
0x18002b53c  push    rdi
0x18002b53d  push    r12
0x18002b53f  push    r13
0x18002b541  push    r14
0x18002b543  push    r15
0x18002b545  lea     rbp, [rsp-0C8h]
0x18002b54d  sub     rsp, 1C8h
0x18002b554  mov     rax, cs:__security_cookie
0x18002b55b  xor     rax, rsp
0x18002b55e  mov     [rbp+100h+var_50], rax
0x18002b565  xor     edx, edx; Val
0x18002b567  mov     [rsp+200h+var_1D0], 0
0x18002b56f  mov     rbx, rcx
0x18002b572  lea     rcx, [rsp+200h+var_1A0]; void *
0x18002b577  lea     r8d, [rdx+58h]; Size
0x18002b57b  call    memset_0
0x18002b580  xor     edx, edx; Val
0x18002b582  lea     rcx, [rbp+100h+var_140]; void *
0x18002b586  lea     r8d, [rdx+48h]; Size
0x18002b58a  call    memset_0
0x18002b58f  mov     rax, [rbx]
0x18002b592  xor     edi, edi
0x18002b594  mov     rcx, rbx
0x18002b597  mov     [rsp+200h+phglobal], 0
0x18002b5a0  mov     [rsp+200h+var_1C0], 0
0x18002b5a9  xor     r14d, r14d
0x18002b5ac  mov     [rsp+200h+ppstm], rdi
0x18002b5b1  mov     rax, [rax+168h]
0x18002b5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5bd  mov     r12, rax
0x18002b5c0  test    rax, rax
0x18002b5c3  jnz     short loc_18002B5CC
0x18002b5c5  xor     ebx, ebx
0x18002b5c7  jmp     loc_18002B9C6
0x18002b5cc  lea     r8, [rsp+200h+ppstm]; ppstm
0x18002b5d1  xor     edx, edx; fDeleteOnRelease
0x18002b5d3  xor     ecx, ecx; hGlobal
0x18002b5d5  call    cs:__imp_CreateStreamOnHGlobal
0x18002b5db  mov     ebx, eax
0x18002b5dd  test    eax, eax
0x18002b5df  jns     short loc_18002B607
0x18002b5e1  xor     r8d, r8d; int
0x18002b5e4  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002b5eb  mov     [rsp+200h+var_1E0], eax
0x18002b5ef  lea     rdx, aWdclistviewOnc_0; "WdcListView::OnCopy"
0x18002b5f6  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002b5fd  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002b602  jmp     loc_18002B9C6
0x18002b607  mov     ebx, 800h
0x18002b60c  mov     ecx, ebx; dwBytes
0x18002b60e  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002b613  mov     rdi, rax
0x18002b616  test    rax, rax
0x18002b619  jnz     short loc_18002B624
0x18002b61b  mov     eax, 8007000Eh
0x18002b620  mov     ebx, eax
0x18002b622  jmp     short loc_18002B5E1
0x18002b624  xor     eax, eax
0x18002b626  mov     rcx, rbx; dwBytes
0x18002b629  mov     [rdi], ax
0x18002b62c  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002b631  xor     r8d, r8d; wParam
0x18002b634  mov     r14, rax
0x18002b637  test    rax, rax
0x18002b63a  jnz     short loc_18002B645
0x18002b63c  mov     eax, 8007000Eh
0x18002b641  mov     ebx, eax
0x18002b643  jmp     short loc_18002B5E4
0x18002b645  xor     eax, eax
0x18002b647  xor     r9d, r9d; lParam
0x18002b64a  mov     edx, 101Fh; Msg
0x18002b64f  mov     [r14], ax
0x18002b653  mov     rcx, r12; hWnd
0x18002b656  call    cs:__imp_SendMessageW
0x18002b65c  xor     r9d, r9d; lParam
0x18002b65f  xor     r8d, r8d; wParam
0x18002b662  mov     rcx, rax; hWnd
0x18002b665  mov     edx, 1200h; Msg
0x18002b66a  mov     r15, rax
0x18002b66d  call    cs:__imp_SendMessageW
0x18002b673  mov     r8d, eax; wParam
0x18002b676  lea     r9, [rbp+100h+lParam]; lParam
0x18002b67a  mov     edx, 103Bh; Msg
0x18002b67f  mov     [rsp+200h+var_1B8], rax
0x18002b684  mov     rcx, r12; hWnd
0x18002b687  mov     rbx, rax
0x18002b68a  call    cs:__imp_SendMessageW
0x18002b690  test    eax, eax
0x18002b692  jnz     short loc_18002B69E
0x18002b694  mov     ebx, 80004005h
0x18002b699  jmp     loc_18002B9C6
0x18002b69e  xor     eax, eax
0x18002b6a0  mov     r13d, 400h
0x18002b6a6  mov     [rdi], ax
0x18002b6a9  xor     esi, esi
0x18002b6ab  cmp     esi, ebx
0x18002b6ad  jnb     short loc_18002B725
0x18002b6af  test    esi, esi
0x18002b6b1  jz      short loc_18002B6CF
0x18002b6b3  lea     r8, asc_180094B70; "\t"
0x18002b6ba  mov     rdx, r13; unsigned __int64
0x18002b6bd  mov     rcx, rdi; unsigned __int16 *
0x18002b6c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b6c5  mov     ebx, eax
0x18002b6c7  test    eax, eax
0x18002b6c9  js      loc_18002B5E1
0x18002b6cf  xor     edx, edx; Val
0x18002b6d1  lea     rcx, [rbp+100h+var_140]; void *
0x18002b6d5  lea     r8d, [rdx+48h]; Size
0x18002b6d9  call    memset_0
0x18002b6de  movsxd  r8, [rbp+rsi*4+100h+lParam]; wParam
0x18002b6e3  lea     r9, [rbp+100h+var_140]; lParam
0x18002b6e7  mov     edx, 120Bh; Msg
0x18002b6ec  mov     dword ptr [rbp+100h+var_140], 2
0x18002b6f3  mov     rcx, r15; hWnd
0x18002b6f6  mov     [rbp+100h+var_128], r13d
0x18002b6fa  mov     [rbp+100h+var_138], r14
0x18002b6fe  call    cs:__imp_SendMessageW
0x18002b704  mov     r8, r14; unsigned __int16 *
0x18002b707  mov     rdx, r13; unsigned __int64
0x18002b70a  mov     rcx, rdi; unsigned __int16 *
0x18002b70d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b712  mov     ebx, eax
0x18002b714  test    eax, eax
0x18002b716  js      loc_18002B5E1
0x18002b71c  mov     rbx, [rsp+200h+var_1B8]
0x18002b721  inc     esi
0x18002b723  jmp     short loc_18002B6AB
0x18002b725  lea     r8, asc_18009107C; "\r\n"
0x18002b72c  mov     rdx, r13; unsigned __int64
0x18002b72f  mov     rcx, rdi; unsigned __int16 *
0x18002b732  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b737  mov     ebx, eax
0x18002b739  test    eax, eax
0x18002b73b  js      loc_18002B5E1
0x18002b741  lea     r8, [rsp+200h+var_1C0]; unsigned __int64 *
0x18002b746  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002b74b  mov     rcx, rdi; unsigned __int16 *
0x18002b74e  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002b753  mov     ebx, eax
0x18002b755  test    eax, eax
0x18002b757  js      loc_18002B5E1
0x18002b75d  mov     rcx, [rsp+200h+var_1C0]; unsigned __int64
0x18002b762  lea     rdx, [rsp+200h+var_1D0]; unsigned int *
0x18002b767  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002b76c  mov     ebx, eax
0x18002b76e  test    eax, eax
0x18002b770  js      loc_18002B5E1
0x18002b776  mov     rcx, [rsp+200h+ppstm]
0x18002b77b  xor     r9d, r9d
0x18002b77e  mov     r8d, [rsp+200h+var_1D0]
0x18002b783  mov     rdx, rdi
0x18002b786  mov     rax, [rcx]
0x18002b789  mov     rax, [rax+20h]
0x18002b78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b792  xor     r8d, r8d; wParam
0x18002b795  mov     ebx, eax
0x18002b797  test    eax, eax
0x18002b799  js      loc_18002B5E4
0x18002b79f  xor     r9d, r9d; lParam
0x18002b7a2  mov     edx, 1032h; Msg
0x18002b7a7  mov     rcx, r12; hWnd
0x18002b7aa  call    cs:__imp_SendMessageW
0x18002b7b0  xor     r9d, r9d; lParam
0x18002b7b3  xor     r8d, r8d; wParam
0x18002b7b6  mov     edx, 1004h; Msg
0x18002b7bb  mov     rcx, r12; hWnd
0x18002b7be  mov     r13, rax
0x18002b7c1  call    cs:__imp_SendMessageW
0x18002b7c7  mov     [rsp+200h+var_1A8], rax
0x18002b7cc  xor     r15d, r15d
0x18002b7cf  cmp     r15d, eax
0x18002b7d2  jnb     loc_18002B93D
0x18002b7d8  xor     edx, edx; Val
0x18002b7da  lea     rcx, [rsp+200h+var_198]; void *
0x18002b7df  lea     r8d, [rdx+50h]; Size
0x18002b7e3  call    memset_0
0x18002b7e8  mov     dword ptr [rsp+200h+var_1A0+4], r15d
0x18002b7ed  mov     dword ptr [rsp+200h+var_1A0], 4
0x18002b7f5  test    r13d, r13d
0x18002b7f8  jz      short loc_18002B80A
0x18002b7fa  mov     dword ptr [rsp+200h+var_1A0], 0Ch
0x18002b802  mov     [rsp+200h+var_190], 2
0x18002b80a  lea     r9, [rsp+200h+var_1A0]; lParam
0x18002b80f  xor     r8d, r8d; wParam
0x18002b812  mov     edx, 104Bh; Msg
0x18002b817  mov     rcx, r12; hWnd
0x18002b81a  call    cs:__imp_SendMessageW
0x18002b820  test    r13d, r13d
0x18002b823  jz      short loc_18002B831
0x18002b825  mov     eax, [rsp+200h+var_194]
0x18002b829  test    al, 2
0x18002b82b  jz      loc_18002B930
0x18002b831  xor     esi, esi
0x18002b833  cmp     esi, dword ptr [rsp+200h+var_1B8]
0x18002b837  jnb     short loc_18002B8B7
0x18002b839  test    esi, esi
0x18002b83b  jz      short loc_18002B85D
0x18002b83d  lea     r8, asc_180094B70; "\t"
0x18002b844  mov     edx, 400h; unsigned __int64
0x18002b849  mov     rcx, rdi; unsigned __int16 *
0x18002b84c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b851  mov     ebx, eax
0x18002b853  test    eax, eax
0x18002b855  js      loc_18002B5E1
0x18002b85b  jmp     short loc_18002B862
0x18002b85d  xor     eax, eax
0x18002b85f  mov     [rdi], ax
0x18002b862  xor     edx, edx; Val
0x18002b864  lea     rcx, [rbp+100h+var_F0]; void *
0x18002b868  lea     r8d, [rdx+58h]; Size
0x18002b86c  call    memset_0
0x18002b871  mov     ecx, [rbp+rsi*4+100h+lParam]
0x18002b875  lea     r9, [rbp+100h+var_F0]; lParam
0x18002b879  mov     [rbp+100h+var_E8], ecx
0x18002b87c  mov     ebx, 400h
0x18002b881  mov     rcx, r12; hWnd
0x18002b884  mov     r8d, r15d; wParam
0x18002b887  mov     edx, 1073h; Msg
0x18002b88c  mov     [rbp+100h+var_D0], ebx
0x18002b88f  mov     [rbp+100h+var_D8], r14
0x18002b893  call    cs:__imp_SendMessageW
0x18002b899  mov     r8, r14; unsigned __int16 *
0x18002b89c  mov     edx, ebx; unsigned __int64
0x18002b89e  mov     rcx, rdi; unsigned __int16 *
0x18002b8a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b8a6  mov     ebx, eax
0x18002b8a8  test    eax, eax
0x18002b8aa  js      loc_18002B5E1
0x18002b8b0  inc     esi
0x18002b8b2  jmp     loc_18002B833
0x18002b8b7  lea     r8, asc_18009107C; "\r\n"
0x18002b8be  mov     edx, 400h; unsigned __int64
0x18002b8c3  mov     rcx, rdi; unsigned __int16 *
0x18002b8c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b8cb  mov     ebx, eax
0x18002b8cd  test    eax, eax
0x18002b8cf  js      loc_18002B5E1
0x18002b8d5  lea     r8, [rsp+200h+var_1C0]; unsigned __int64 *
0x18002b8da  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002b8df  mov     rcx, rdi; unsigned __int16 *
0x18002b8e2  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002b8e7  mov     ebx, eax
0x18002b8e9  test    eax, eax
0x18002b8eb  js      loc_18002B5E1
0x18002b8f1  mov     rcx, [rsp+200h+var_1C0]; unsigned __int64
0x18002b8f6  lea     rdx, [rsp+200h+var_1D0]; unsigned int *
0x18002b8fb  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002b900  mov     ebx, eax
0x18002b902  test    eax, eax
0x18002b904  js      loc_18002B5E1
0x18002b90a  mov     rcx, [rsp+200h+ppstm]
0x18002b90f  xor     r9d, r9d
0x18002b912  mov     r8d, [rsp+200h+var_1D0]
0x18002b917  mov     rdx, rdi
0x18002b91a  mov     rax, [rcx]
0x18002b91d  mov     rax, [rax+20h]
0x18002b921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b926  mov     ebx, eax
0x18002b928  test    eax, eax
0x18002b92a  js      loc_18002B5E1
0x18002b930  mov     rax, [rsp+200h+var_1A8]
0x18002b935  inc     r15d
0x18002b938  jmp     loc_18002B7CF
0x18002b93d  mov     rcx, r12; hWndNewOwner
0x18002b940  call    cs:__imp_OpenClipboard
0x18002b946  test    eax, eax
0x18002b948  jnz     short loc_18002B965
0x18002b94a  call    cs:__imp_GetLastError
0x18002b950  mov     ebx, eax
0x18002b952  test    eax, eax
0x18002b954  jz      short loc_18002B9A4
0x18002b956  jle     short loc_18002B961
0x18002b958  movzx   ebx, ax
0x18002b95b  or      ebx, 80070000h
0x18002b961  test    ebx, ebx
0x18002b963  js      short loc_18002B9A9
0x18002b965  call    cs:__imp_EmptyClipboard
0x18002b96b  mov     rcx, [rsp+200h+ppstm]; pstm
0x18002b970  lea     rdx, [rsp+200h+phglobal]; phglobal
0x18002b975  call    cs:__imp_GetHGlobalFromStream
0x18002b97b  mov     ebx, eax
0x18002b97d  test    eax, eax
0x18002b97f  jns     short loc_18002B9B0
0x18002b981  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002b988  mov     [rsp+200h+var_1E0], eax
0x18002b98c  xor     r8d, r8d; int
0x18002b98f  lea     rdx, aWdclistviewOnc_0; "WdcListView::OnCopy"
0x18002b996  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18002b99d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002b9a2  jmp     short loc_18002B9C0
0x18002b9a4  mov     ebx, 80004005h
0x18002b9a9  mov     eax, ebx
0x18002b9ab  jmp     loc_18002B5E1
0x18002b9b0  mov     rdx, [rsp+200h+phglobal]; hMem
0x18002b9b5  mov     ecx, 0Dh; uFormat
0x18002b9ba  call    cs:__imp_SetClipboardData
  ... truncated ...
```
