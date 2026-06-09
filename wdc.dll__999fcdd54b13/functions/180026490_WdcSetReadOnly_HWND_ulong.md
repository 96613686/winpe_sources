# WdcSetReadOnly(HWND__ *,ulong)

- ea: `0x180026490`
- end: `0x18002662c`
- name: `?WdcSetReadOnly@@YAJPEAUHWND__@@K@Z`
- size: `412`
- prototype: `__int64 __fastcall(HWND, unsigned int)`
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x180025ec0`
- `0x18004c568`
- `0x180054320`
- `0x180054664`
- `0x18005b594`
- `0x18005b874`
- `0x18005bb50`
- `0x18005c058`
- `0x18005f050`
- `0x18005f218`
- `0x18005f548`
- `0x18005f6bc`
- `0x18005f830`
- `0x1800620a4`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180026490`
- `0x180084e04`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026508`
- `KERNEL32!GetLastError` at `0x1800265d9`
- `KERNEL32!GetLastError` at `0x180026508`
- `KERNEL32!GetLastError` at `0x1800265d9`
- `USER32!GetClassNameW` at `0x1800264fe`
- `USER32!GetClassNameW` at `0x1800265cf`
- `USER32!GetClassNameW` at `0x1800264fe`
- `USER32!GetClassNameW` at `0x1800265cf`
- `USER32!GetWindowLongPtrW` at `0x180026539`
- `USER32!GetWindowLongPtrW` at `0x180026539`
- `USER32!SetWindowLongPtrW` at `0x18002654f`
- `USER32!SetWindowLongPtrW` at `0x18002654f`
- `USER32!EnableWindow` at `0x1800264ab`
- `USER32!EnableWindow` at `0x180026611`
- `USER32!EnableWindow` at `0x1800264ab`
- `USER32!EnableWindow` at `0x180026611`
- `USER32!SendMessageW` at `0x1800265a7`
- `USER32!SendMessageW` at `0x1800265a7`
- `USER32!GetDlgItem` at `0x18002649a`
- `USER32!GetDlgItem` at `0x18002649a`
- `USER32!GetWindow` at `0x1800265b5`
- `USER32!GetWindow` at `0x1800265b5`

## string_xrefs

- `0x1800264d5`: `WdcSetReadOnly`
- `0x18002656d`: `WdcSetReadOnly`

## pseudocode

```c
__int64 __fastcall WdcSetReadOnly(HWND a1, int a2)
{
  HWND DlgItem; // rdi
  const char *v3; // rdx
  int v4; // r8d
  WCHAR *v5; // rbx
  signed int LastError; // eax
  bool v7; // sf
  LONG_PTR WindowLongPtrW; // rax
  const char *v9; // rdx
  int v10; // r8d
  HWND Window; // rax
  HWND v12; // rdi
  bool v13; // sf

  DlgItem = GetDlgItem(a1, a2);
  EnableWindow(DlgItem, 1);
  v5 = (WCHAR *)WdcAlloc(0x100u, v3, v4);
  if ( v5 )
  {
    *v5 = 0;
    if ( GetClassNameW(DlgItem, v5, 128) <= 0 )
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( !LastError )
        goto LABEL_10;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v7 = LastError < 0;
      }
      if ( v7 )
        goto LABEL_11;
    }
    if ( !wcscmp_0(v5, L"SysListView32") )
    {
      WindowLongPtrW = GetWindowLongPtrW(DlgItem, -16);
      SetWindowLongPtrW(DlgItem, -16, WindowLongPtrW & 0xFFFFFFFFFFFFFDFFuLL);
LABEL_21:
      WdcFree(v5, v9, v10);
      return 0;
    }
    if ( wcscmp_0(v5, L"Edit") )
      goto LABEL_21;
    SendMessageW(DlgItem, 0xCFu, 1u, 0);
    Window = GetWindow(DlgItem, 2u);
    v12 = Window;
    if ( !Window )
      goto LABEL_21;
    if ( GetClassNameW(Window, v5, 128) > 0 )
    {
LABEL_19:
      if ( !wcscmp_0(v5, L"msctls_updown32") )
        EnableWindow(v12, 0);
      goto LABEL_21;
    }
    LastError = GetLastError();
    v13 = LastError < 0;
    if ( LastError )
    {
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v13 = LastError < 0;
      }
      if ( !v13 )
        goto LABEL_19;
LABEL_11:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
        "WdcSetReadOnly",
        0,
        L"FAILURE: 0x%08x",
        LastError);
      goto LABEL_21;
    }
LABEL_10:
    LastError = -2147467259;
    goto LABEL_11;
  }
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
    "WdcSetReadOnly",
    0,
    L"FAILURE: 0x%08x",
    -2147024882);
  return 0;
}

```

## disassembly

```asm
0x180026490  mov     [rsp+arg_0], rbx
0x180026495  push    rdi
0x180026496  sub     rsp, 30h
0x18002649a  call    cs:__imp_GetDlgItem
0x1800264a0  mov     rcx, rax; hWnd
0x1800264a3  mov     edx, 1; bEnable
0x1800264a8  mov     rdi, rax
0x1800264ab  call    cs:__imp_EnableWindow
0x1800264b1  mov     ecx, 100h; dwBytes
0x1800264b6  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800264bb  mov     rbx, rax
0x1800264be  test    rax, rax
0x1800264c1  jnz     short loc_1800264ED
0x1800264c3  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800264ca  mov     [rsp+38h+var_18], 8007000Eh
0x1800264d2  xor     r8d, r8d; int
0x1800264d5  lea     rdx, aWdcsetreadonly; "WdcSetReadOnly"
0x1800264dc  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x1800264e3  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800264e8  jmp     loc_18002661F
0x1800264ed  xor     eax, eax
0x1800264ef  mov     r8d, 80h; nMaxCount
0x1800264f5  mov     rdx, rbx; lpClassName
0x1800264f8  mov     [rbx], ax
0x1800264fb  mov     rcx, rdi; hWnd
0x1800264fe  call    cs:__imp_GetClassNameW
0x180026504  test    eax, eax
0x180026506  jg      short loc_180026520
0x180026508  call    cs:__imp_GetLastError
0x18002650e  test    eax, eax
0x180026510  jz      short loc_18002655A
0x180026512  jle     short loc_18002651E
0x180026514  movzx   eax, ax
0x180026517  or      eax, 80070000h
0x18002651c  test    eax, eax
0x18002651e  js      short loc_18002655F
0x180026520  lea     rdx, aSyslistview32; "SysListView32"
0x180026527  mov     rcx, rbx; String1
0x18002652a  call    wcscmp_0
0x18002652f  test    eax, eax
0x180026531  jnz     short loc_180026585
0x180026533  lea     edx, [rax-10h]; nIndex
0x180026536  mov     rcx, rdi; hWnd
0x180026539  call    cs:__imp_GetWindowLongPtrW
0x18002653f  mov     edx, 0FFFFFFF0h; nIndex
0x180026544  mov     rcx, rdi; hWnd
0x180026547  btr     rax, 9
0x18002654c  mov     r8, rax; dwNewLong
0x18002654f  call    cs:__imp_SetWindowLongPtrW
0x180026555  jmp     loc_180026617
0x18002655a  mov     eax, 80004005h
0x18002655f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180026566  mov     [rsp+38h+var_18], eax
0x18002656a  xor     r8d, r8d; int
0x18002656d  lea     rdx, aWdcsetreadonly; "WdcSetReadOnly"
0x180026574  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x18002657b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026580  jmp     loc_180026617
0x180026585  lea     rdx, aEdit; "Edit"
0x18002658c  mov     rcx, rbx; String1
0x18002658f  call    wcscmp_0
0x180026594  test    eax, eax
0x180026596  jnz     short loc_180026617
0x180026598  xor     r9d, r9d; lParam
0x18002659b  lea     r8d, [rax+1]; wParam
0x18002659f  mov     edx, 0CFh; Msg
0x1800265a4  mov     rcx, rdi; hWnd
0x1800265a7  call    cs:__imp_SendMessageW
0x1800265ad  mov     edx, 2; uCmd
0x1800265b2  mov     rcx, rdi; hWnd
0x1800265b5  call    cs:__imp_GetWindow
0x1800265bb  mov     rdi, rax
0x1800265be  test    rax, rax
0x1800265c1  jz      short loc_180026617
0x1800265c3  mov     r8d, 80h; nMaxCount
0x1800265c9  mov     rdx, rbx; lpClassName
0x1800265cc  mov     rcx, rax; hWnd
0x1800265cf  call    cs:__imp_GetClassNameW
0x1800265d5  test    eax, eax
0x1800265d7  jg      short loc_1800265F9
0x1800265d9  call    cs:__imp_GetLastError
0x1800265df  test    eax, eax
0x1800265e1  jz      loc_18002655A
0x1800265e7  jle     short loc_1800265F3
0x1800265e9  movzx   eax, ax
0x1800265ec  or      eax, 80070000h
0x1800265f1  test    eax, eax
0x1800265f3  js      loc_18002655F
0x1800265f9  lea     rdx, aMsctlsUpdown32; "msctls_updown32"
0x180026600  mov     rcx, rbx; String1
0x180026603  call    wcscmp_0
0x180026608  test    eax, eax
0x18002660a  jnz     short loc_180026617
0x18002660c  xor     edx, edx; bEnable
0x18002660e  mov     rcx, rdi; hWnd
0x180026611  call    cs:__imp_EnableWindow
0x180026617  mov     rcx, rbx; void *
0x18002661a  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002661f  mov     rbx, [rsp+38h+arg_0]
0x180026624  xor     eax, eax
0x180026626  add     rsp, 30h
0x18002662a  pop     rdi
0x18002662b  retn
```
