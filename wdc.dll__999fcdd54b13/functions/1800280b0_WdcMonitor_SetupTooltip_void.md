# WdcMonitor::SetupTooltip(void)

- ea: `0x1800280b0`
- end: `0x1800281bc`
- name: `?SetupTooltip@WdcMonitor@@QEAAJXZ`
- size: `268`
- prototype: `__int64 __fastcall(WdcMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18006f888`

## callees

- `0x18000b854`
- `0x1800280b0`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002812d`
- `KERNEL32!GetLastError` at `0x18002814e`
- `KERNEL32!GetLastError` at `0x18002812d`
- `KERNEL32!GetLastError` at `0x18002814e`
- `USER32!CreateWindowExW` at `0x180028116`
- `USER32!CreateWindowExW` at `0x180028116`
- `USER32!SendMessageW` at `0x18002817a`
- `USER32!SendMessageW` at `0x18002817a`

## pseudocode

```c
__int64 __fastcall WdcMonitor::SetupTooltip(WdcMonitor *this)
{
  HINSTANCE hInstance; // rbx
  signed int v3; // edi
  HWND hWndParent; // rax
  HWND Window; // rax
  signed int LastError; // eax
  signed int v7; // eax
  __int64 X; // [rsp+20h] [rbp-48h]

  hInstance = g_hInstance;
  v3 = 0;
  hWndParent = (HWND)(*(__int64 (__fastcall **)(WdcMonitor *))(*(_QWORD *)this + 360LL))(this);
  Window = CreateWindowExW(
             8u,
             L"tooltips_class32",
             0,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             hInstance,
             0);
  *((_QWORD *)this + 177) = Window;
  if ( !Window )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( !LastError )
      goto LABEL_13;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_14;
  }
  if ( *((_QWORD *)this + 177) == -1 )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 >= 0 )
        goto LABEL_11;
LABEL_14:
      LODWORD(X) = v3;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\monitor.cpp",
        "WdcMonitor::SetupTooltip",
        0,
        L"FAILURE: 0x%08x",
        X);
      return (unsigned int)v3;
    }
LABEL_13:
    v3 = -2147467259;
    goto LABEL_14;
  }
LABEL_11:
  SendMessageW(*((HWND *)this + 177), 0x418u, 0, 200);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800280b0  mov     [rsp+arg_0], rbx
0x1800280b5  mov     [rsp+arg_8], rsi
0x1800280ba  push    rdi
0x1800280bb  sub     rsp, 60h
0x1800280bf  mov     rax, [rcx]
0x1800280c2  mov     rsi, rcx
0x1800280c5  mov     rbx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800280cc  xor     edi, edi
0x1800280ce  mov     rax, [rax+168h]
0x1800280d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280da  mov     [rsp+68h+lpParam], rdi; lpParam
0x1800280df  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x1800280e6  mov     [rsp+68h+hInstance], rbx; hInstance
0x1800280eb  lea     ecx, [rdi+8]; dwExStyle
0x1800280ee  mov     [rsp+68h+hMenu], rdi; hMenu
0x1800280f3  mov     r9d, 80000000h; dwStyle
0x1800280f9  mov     [rsp+68h+hWndParent], rax; hWndParent
0x1800280fe  xor     r8d, r8d; lpWindowName
0x180028101  mov     eax, 80000000h
0x180028106  mov     [rsp+68h+nHeight], eax; nHeight
0x18002810a  mov     [rsp+68h+nWidth], eax; nWidth
0x18002810e  mov     [rsp+68h+Y], eax; Y
0x180028112  mov     dword ptr [rsp+68h+X], eax; X
0x180028116  call    cs:__imp_CreateWindowExW
0x18002811c  mov     [rsi+588h], rax
0x180028123  mov     ebx, 80070000h
0x180028128  test    rax, rax
0x18002812b  jnz     short loc_180028144
0x18002812d  call    cs:__imp_GetLastError
0x180028133  mov     edi, eax
0x180028135  test    eax, eax
0x180028137  jz      short loc_180028192
0x180028139  jle     short loc_180028140
0x18002813b  movzx   edi, ax
0x18002813e  or      edi, ebx
0x180028140  test    edi, edi
0x180028142  js      short loc_180028197
0x180028144  cmp     qword ptr [rsi+588h], 0FFFFFFFFFFFFFFFFh
0x18002814c  jnz     short loc_180028165
0x18002814e  call    cs:__imp_GetLastError
0x180028154  mov     edi, eax
0x180028156  test    eax, eax
0x180028158  jz      short loc_180028192
0x18002815a  jle     short loc_180028161
0x18002815c  movzx   edi, ax
0x18002815f  or      edi, ebx
0x180028161  test    edi, edi
0x180028163  js      short loc_180028197
0x180028165  mov     rcx, [rsi+588h]; hWnd
0x18002816c  mov     r9d, 0C8h; lParam
0x180028172  xor     r8d, r8d; wParam
0x180028175  mov     edx, 418h; Msg
0x18002817a  call    cs:__imp_SendMessageW
0x180028180  mov     rbx, [rsp+68h+arg_0]
0x180028185  mov     eax, edi
0x180028187  mov     rsi, [rsp+68h+arg_8]
0x18002818c  add     rsp, 60h
0x180028190  pop     rdi
0x180028191  retn
0x180028192  mov     edi, 80004005h
0x180028197  mov     eax, edi
0x180028199  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800281a0  xor     r8d, r8d; int
0x1800281a3  mov     dword ptr [rsp+68h+X], eax
0x1800281a7  lea     rdx, aWdcmonitorSetu; "WdcMonitor::SetupTooltip"
0x1800281ae  lea     rcx, aBaseDiagnosisP_4; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x1800281b5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800281ba  jmp     short loc_180028180
```
