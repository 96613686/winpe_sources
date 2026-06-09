# _anonymous_namespace_::NotificationIconImpl::NotifyIcon

- ea: `0x1400446e0`
- end: `0x140044822`
- name: `_anonymous_namespace_::NotificationIconImpl::NotifyIcon`
- size: `322`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400429e0`
- `0x140043cd4`
- `0x140044f40`

## callees

- `0x140005530`
- `0x140006314`
- `0x1400446e0`
- `0x14005ba98`
- `0x140091a58`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140044737`
- `KERNEL32!GetModuleHandleW` at `0x140044737`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1400447da`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1400447da`
- `api-ms-win-shcore-scaling-l1-1-2!GetDpiForShellUIComponent` at `0x140044710`
- `api-ms-win-shcore-scaling-l1-1-2!GetDpiForShellUIComponent` at `0x140044710`
- `SHELL32!Shell_NotifyIconW` at `0x1400447ea`
- `SHELL32!Shell_NotifyIconW` at `0x140044801`
- `SHELL32!Shell_NotifyIconW` at `0x1400447ea`
- `SHELL32!Shell_NotifyIconW` at `0x140044801`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x140044725`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x140044725`

## pseudocode

```c
BOOL __fastcall anonymous_namespace_::NotificationIconImpl::NotifyIcon(__int64 a1, unsigned __int8 a2)
{
  int v3; // esi
  int DpiForShellUIComponent; // eax
  HICON v5; // rcx
  int v6; // edi
  HMODULE ModuleHandleW; // rax
  __int64 Value; // rax
  _QWORD *v9; // r8
  bool v10; // cc
  BOOL result; // eax
  struct _NOTIFYICONDATAW Data; // [rsp+30h] [rbp-D0h] BYREF

  v3 = a2;
  DpiForShellUIComponent = GetDpiForShellUIComponent(1);
  v5 = *(HICON *)(a1 + 8);
  v6 = DpiForShellUIComponent;
  if ( v5 )
  {
    if ( *(_DWORD *)a1 == DpiForShellUIComponent )
      goto LABEL_5;
    DestroyIcon(v5);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)a1 = v6;
  ModuleHandleW = GetModuleHandleW(0);
  *(_QWORD *)(a1 + 8) = SHLoadNativeIconSize(ModuleHandleW, v6);
LABEL_5:
  *(_QWORD *)&Data.cbSize = 976;
  memset_0(&Data.hWnd, 0, 0x3C8u);
  Value = Lazy<MessageWindow,Optional>::GetValue(*(_QWORD *)(a1 + 16) + 72LL);
  v9 = (_QWORD *)(a1 + 32);
  v10 = *(_QWORD *)(a1 + 56) <= 7u;
  Data.hWnd = **(HWND **)(Value + 16);
  Data.hIcon = *(HICON *)(a1 + 8);
  Data.uID = 100;
  Data.uFlags = 175;
  Data.uCallbackMessage = 32769;
  Data.guidItem = (GUID)SCAID_ParentalControls;
  Data.dwState = 0;
  Data.uTimeout = 4;
  if ( !v10 )
    v9 = (_QWORD *)*v9;
  _o_wcscpy_s(Data.szTip, 128, v9);
  result = Shell_NotifyIconW(v3 ^ 1, &Data);
  if ( !result )
  {
    if ( (_BYTE)v3 )
      return Shell_NotifyIconW(1u, &Data);
  }
  return result;
}

```

## disassembly

```asm
0x1400446e0  push    rbp
0x1400446e2  push    rbx
0x1400446e3  push    rsi
0x1400446e4  push    rdi
0x1400446e5  lea     rbp, [rsp-318h]
0x1400446ed  sub     rsp, 418h
0x1400446f4  mov     rax, cs:__security_cookie
0x1400446fb  xor     rax, rsp
0x1400446fe  mov     [rbp+330h+var_30], rax
0x140044705  mov     rbx, rcx
0x140044708  movzx   esi, dl
0x14004470b  mov     ecx, 1
0x140044710  call    cs:__imp_GetDpiForShellUIComponent
0x140044716  mov     rcx, [rbx+8]; hIcon
0x14004471a  mov     edi, eax
0x14004471c  test    rcx, rcx
0x14004471f  jz      short loc_140044733
0x140044721  cmp     [rbx], eax
0x140044723  jz      short loc_14004474D
0x140044725  call    cs:__imp_DestroyIcon
0x14004472b  mov     qword ptr [rbx+8], 0
0x140044733  xor     ecx, ecx; lpModuleName
0x140044735  mov     [rbx], edi
0x140044737  call    cs:__imp_GetModuleHandleW
0x14004473d  mov     rcx, rax; hInst
0x140044740  mov     [rsp+430h+var_410], edi; int
0x140044744  call    SHLoadNativeIconSize
0x140044749  mov     [rbx+8], rax
0x14004474d  xor     edx, edx; Val
0x14004474f  mov     qword ptr [rsp+430h+Data.cbSize], 3D0h
0x140044758  mov     r8d, 3C8h; Size
0x14004475e  lea     rcx, [rsp+430h+Data.hWnd]; void *
0x140044763  call    memset_0
0x140044768  mov     rcx, [rbx+10h]
0x14004476c  add     rcx, 48h ; 'H'
0x140044770  call    ?GetValue@?$Lazy@VMessageWindow@@VOptional@@@@AEBAAEAVMessageWindow@@XZ; Lazy<MessageWindow,Optional>::GetValue(void)
0x140044775  movups  xmm0, cs:SCAID_ParentalControls
0x14004477c  lea     r8, [rbx+20h]
0x140044780  cmp     qword ptr [r8+18h], 7
0x140044785  mov     rcx, [rax+10h]
0x140044789  mov     rax, [rcx]
0x14004478c  mov     [rsp+430h+Data.hWnd], rax
0x140044791  mov     rax, [rbx+8]
0x140044795  mov     [rsp+430h+Data.hIcon], rax
0x14004479a  mov     [rsp+430h+Data.uID], 64h ; 'd'
0x1400447a2  mov     [rsp+430h+Data.uFlags], 0AFh
0x1400447aa  mov     [rsp+430h+Data.uCallbackMessage], 8001h
0x1400447b2  movdqu  xmmword ptr [rbp+330h+Data.guidItem.Data1], xmm0
0x1400447ba  mov     [rbp+330h+Data.dwState], 0
0x1400447c1  mov     dword ptr [rbp+330h+Data.330h], 4
0x1400447cb  jbe     short loc_1400447D0
0x1400447cd  mov     r8, [r8]
0x1400447d0  mov     edx, 80h
0x1400447d5  lea     rcx, [rsp+430h+Data.szTip]
0x1400447da  call    cs:__imp__o_wcscpy_s
0x1400447e0  mov     ecx, esi
0x1400447e2  lea     rdx, [rsp+430h+Data]; lpData
0x1400447e7  xor     ecx, 1; dwMessage
0x1400447ea  call    cs:__imp_Shell_NotifyIconW
0x1400447f0  test    eax, eax
0x1400447f2  jnz     short loc_140044807
0x1400447f4  test    sil, sil
0x1400447f7  jz      short loc_140044807
0x1400447f9  lea     rdx, [rsp+430h+Data]; lpData
0x1400447fe  lea     ecx, [rax+1]; dwMessage
0x140044801  call    cs:__imp_Shell_NotifyIconW
0x140044807  mov     rcx, [rbp+330h+var_30]
0x14004480e  xor     rcx, rsp; StackCookie
0x140044811  call    __security_check_cookie
0x140044816  add     rsp, 418h
0x14004481d  pop     rdi
0x14004481e  pop     rsi
0x14004481f  pop     rbx
0x140044820  pop     rbp
0x140044821  retn
```
