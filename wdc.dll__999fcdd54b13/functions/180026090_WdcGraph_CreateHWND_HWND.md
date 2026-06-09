# WdcGraph::CreateHWND(HWND__ *)

- ea: `0x180026090`
- end: `0x18002615a`
- name: `?CreateHWND@WdcGraph@@UEAAPEAUHWND__@@PEAU2@@Z`
- size: `202`
- prototype: `HWND __fastcall(WdcGraph *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b854`
- `0x180026090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800260fb`
- `KERNEL32!GetLastError` at `0x1800260fb`
- `USER32!CreateWindowExW` at `0x1800260ed`
- `USER32!CreateWindowExW` at `0x1800260ed`
- `USER32!ShowWindow` at `0x18002614b`
- `USER32!ShowWindow` at `0x18002614b`

## string_xrefs

- `0x180026128`: `WdcGraph::CreateHWND`

## pseudocode

```c
HWND __fastcall WdcGraph::CreateHWND(WdcGraph *this, HWND a2)
{
  HWND Window; // rax
  HWND v3; // rbx
  signed int LastError; // eax
  bool v5; // sf
  __int64 X; // [rsp+20h] [rbp-48h]

  Window = CreateWindowExW(0x200u, L"WdcGraphWindow", &pszTargetName, 0x50000000u, 0, 0, 10, 10, a2, 0, g_hInstance, 0);
  v3 = Window;
  if ( Window && Window != HWND_MESSAGE|0x2LL )
  {
LABEL_10:
    ShowWindow(v3, 5);
    return v3;
  }
  LastError = GetLastError();
  v5 = LastError < 0;
  if ( LastError )
  {
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError < 0;
    }
    if ( !v5 )
      goto LABEL_10;
  }
  else
  {
    LastError = -2147467259;
  }
  LODWORD(X) = LastError;
  WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\graph.cpp", "WdcGraph::CreateHWND", 0, L"FAILURE: 0x%08x", X);
  return v3;
}

```

## disassembly

```asm
0x180026090  mov     r11, rsp
0x180026093  push    rbx
0x180026094  sub     rsp, 60h
0x180026098  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18002609f  lea     r8, pszTargetName; lpWindowName
0x1800260a6  mov     qword ptr [r11-10h], 0
0x1800260ae  mov     r9d, 50000000h; dwStyle
0x1800260b4  mov     [r11-18h], rax
0x1800260b8  mov     ecx, 200h; dwExStyle
0x1800260bd  mov     qword ptr [r11-20h], 0
0x1800260c5  mov     eax, 0Ah
0x1800260ca  mov     [r11-28h], rdx
0x1800260ce  lea     rdx, ClassName; "WdcGraphWindow"
0x1800260d5  mov     [rsp+68h+nHeight], eax; nHeight
0x1800260d9  mov     [rsp+68h+nWidth], eax; nWidth
0x1800260dd  mov     [rsp+68h+Y], 0; Y
0x1800260e5  mov     dword ptr [rsp+68h+X], 0; X
0x1800260ed  call    cs:__imp_CreateWindowExW
0x1800260f3  mov     rbx, rax
0x1800260f6  test    rax, rax
0x1800260f9  jnz     short loc_18002613D
0x1800260fb  call    cs:__imp_GetLastError
0x180026101  test    eax, eax
0x180026103  jz      short loc_180026115
0x180026105  jle     short loc_180026111
0x180026107  movzx   eax, ax
0x18002610a  or      eax, 80070000h
0x18002610f  test    eax, eax
0x180026111  jns     short loc_180026143
0x180026113  jmp     short loc_18002611A
0x180026115  mov     eax, 80004005h
0x18002611a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180026121  mov     dword ptr [rsp+68h+X], eax
0x180026125  xor     r8d, r8d; int
0x180026128  lea     rdx, aWdcgraphCreate_0; "WdcGraph::CreateHWND"
0x18002612f  lea     rcx, aBaseDiagnosisP_49; "base\\diagnosis\\pdui\\perfmon\\mon\\gr"...
0x180026136  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002613b  jmp     short loc_180026151
0x18002613d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180026141  jz      short loc_1800260FB
0x180026143  mov     edx, 5; nCmdShow
0x180026148  mov     rcx, rbx; hWnd
0x18002614b  call    cs:__imp_ShowWindow
0x180026151  mov     rax, rbx
0x180026154  add     rsp, 60h
0x180026158  pop     rbx
0x180026159  retn
```
