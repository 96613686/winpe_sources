# EnumWindowProcForOwnedVisible(HWND__ *,__int64)

- ea: `0x180004010`
- end: `0x180004155`
- name: `?EnumWindowProcForOwnedVisible@@YAHPEAUHWND__@@_J@Z`
- size: `325`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800035dc`
- `0x180004010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004034`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004063`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004034`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004063`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000413b`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000413b`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x180004111`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x180004111`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800040b1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800040bf`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800040b1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800040bf`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x1800040d5`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x1800040d5`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x1800040e6`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x1800040f6`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x1800040e6`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x1800040f6`

## pseudocode

```c
__int64 __fastcall EnumWindowProcForOwnedVisible(HWND a1, HWND a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rbx
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  DWORD dwProcessId; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  dwProcessId = 0;
  if ( !IsWindow(a1) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v5 = 19;
LABEL_9:
    WPP_SF_(v4[2], v5, WPP_da26f2d1156739261f61a97d8df66789_Traceguids);
    return 0;
  }
  if ( !IsWindow(a2) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v5 = 20;
    goto LABEL_9;
  }
  v7 = 1;
  GetWindowThreadProcessId(a1, &dwProcessId);
  GetWindowThreadProcessId(a2, &v9);
  if ( dwProcessId == v9 && GetWindow(a1, 4u) == a2 && (GetWindowLongW(a1, -20) & 0x80u) == 0 )
  {
    v8 = -1;
    if ( (GetWindowLongW(a2, -20) & 8) == 0 )
      v8 = (__int64)a2;
    ShowWindow(a1, 5);
    SetWindowPos(a1, (HWND)v8, 0, 0, 0, 0, 3u);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180004010  mov     rax, rsp
0x180004013  mov     [rax+8], rbx
0x180004017  mov     [rax+20h], rsi
0x18000401b  push    rdi
0x18000401c  sub     rsp, 40h
0x180004020  mov     rsi, rdx
0x180004023  mov     dword ptr [rax+10h], 0
0x18000402a  mov     rdi, rcx
0x18000402d  mov     dword ptr [rax+18h], 0
0x180004034  call    cs:__imp_IsWindow
0x18000403a  test    eax, eax
0x18000403c  jnz     short loc_180004060
0x18000403e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004045  lea     rax, WPP_GLOBAL_Control
0x18000404c  cmp     rcx, rax
0x18000404f  jz      short loc_18000409D
0x180004051  mov     ebx, 1
0x180004056  test    [rcx+1Ch], bl
0x180004059  jz      short loc_18000409D
0x18000405b  lea     edx, [rbx+12h]
0x18000405e  jmp     short loc_18000408D
0x180004060  mov     rcx, rsi; hWnd
0x180004063  call    cs:__imp_IsWindow
0x180004069  test    eax, eax
0x18000406b  jnz     short loc_1800040A4
0x18000406d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004074  lea     rax, WPP_GLOBAL_Control
0x18000407b  cmp     rcx, rax
0x18000407e  jz      short loc_18000409D
0x180004080  mov     ebx, 1
0x180004085  test    [rcx+1Ch], bl
0x180004088  jz      short loc_18000409D
0x18000408a  lea     edx, [rbx+13h]
0x18000408d  mov     rcx, [rcx+10h]
0x180004091  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x180004098  call    WPP_SF_
0x18000409d  xor     eax, eax
0x18000409f  jmp     loc_180004145
0x1800040a4  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x1800040a9  mov     rcx, rdi; hWnd
0x1800040ac  mov     ebx, 1
0x1800040b1  call    cs:__imp_GetWindowThreadProcessId
0x1800040b7  lea     rdx, [rsp+48h+arg_8]; lpdwProcessId
0x1800040bc  mov     rcx, rsi; hWnd
0x1800040bf  call    cs:__imp_GetWindowThreadProcessId
0x1800040c5  mov     eax, [rsp+48h+arg_8]
0x1800040c9  cmp     [rsp+48h+dwProcessId], eax
0x1800040cd  jnz     short loc_180004143
0x1800040cf  lea     edx, [rbx+3]; uCmd
0x1800040d2  mov     rcx, rdi; hWnd
0x1800040d5  call    cs:__imp_GetWindow
0x1800040db  cmp     rax, rsi
0x1800040de  jnz     short loc_180004143
0x1800040e0  lea     edx, [rbx-15h]; nIndex
0x1800040e3  mov     rcx, rdi; hWnd
0x1800040e6  call    cs:__imp_GetWindowLongW
0x1800040ec  test    al, al
0x1800040ee  js      short loc_180004143
0x1800040f0  lea     edx, [rbx-15h]; nIndex
0x1800040f3  mov     rcx, rsi; hWnd
0x1800040f6  call    cs:__imp_GetWindowLongW
0x1800040fc  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004103  mov     edx, 5; nCmdShow
0x180004108  test    al, 8
0x18000410a  mov     rcx, rdi; hWnd
0x18000410d  cmovz   rbx, rsi
0x180004111  call    cs:__imp_ShowWindow
0x180004117  mov     [rsp+48h+uFlags], 3; uFlags
0x18000411f  xor     r9d, r9d; Y
0x180004122  mov     [rsp+48h+cy], 0; cy
0x18000412a  xor     r8d, r8d; X
0x18000412d  mov     rdx, rbx; hWndInsertAfter
0x180004130  mov     [rsp+48h+var_28], 0; cx
0x180004138  mov     rcx, rdi; hWnd
0x18000413b  call    cs:__imp_SetWindowPos
0x180004141  xor     ebx, ebx
0x180004143  mov     eax, ebx
0x180004145  mov     rbx, [rsp+48h+arg_0]
0x18000414a  mov     rsi, [rsp+48h+arg_18]
0x18000414f  add     rsp, 40h
0x180004153  pop     rdi
0x180004154  retn
```
