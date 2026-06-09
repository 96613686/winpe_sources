# CCurrentWindowTracker::_UpdateForegroundWindow(void)

- ea: `0x180049ab0`
- end: `0x180049b22`
- name: `?_UpdateForegroundWindow@CCurrentWindowTracker@@AEAA_NXZ`
- size: `114`
- prototype: `bool __fastcall(CCurrentWindowTracker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800498fc`
- `0x180049a50`

## callees

- `0x180049ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049afc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049afc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180049ac5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180049ac5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180049af6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180049af6`

## pseudocode

```c
char __fastcall CCurrentWindowTracker::_UpdateForegroundWindow(HWND *this)
{
  char v2; // si
  HWND ForegroundWindow; // rax
  HWND v4; // rbx
  bool v6; // zf
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  ForegroundWindow = GetForegroundWindow();
  v4 = ForegroundWindow;
  if ( ForegroundWindow )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
    if ( dwProcessId != GetCurrentProcessId() )
      v4 = 0;
    if ( v4 != this[13] )
    {
      v6 = v4 == this[12];
      this[13] = v4;
      return !v6;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180049ab0  mov     [rsp+arg_0], rbx
0x180049ab5  mov     [rsp+arg_10], rsi
0x180049aba  push    rdi
0x180049abb  sub     rsp, 20h
0x180049abf  mov     rdi, rcx
0x180049ac2  xor     sil, sil
0x180049ac5  call    cs:__imp_GetForegroundWindow
0x180049acb  mov     rbx, rax
0x180049ace  test    rax, rax
0x180049ad1  jnz     short loc_180049AE6
0x180049ad3  mov     rbx, [rsp+28h+arg_0]
0x180049ad8  mov     al, sil
0x180049adb  mov     rsi, [rsp+28h+arg_10]
0x180049ae0  add     rsp, 20h
0x180049ae4  pop     rdi
0x180049ae5  retn
0x180049ae6  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180049aeb  mov     [rsp+28h+dwProcessId], 0
0x180049af3  mov     rcx, rbx; hWnd
0x180049af6  call    cs:__imp_GetWindowThreadProcessId
0x180049afc  call    cs:__imp_GetCurrentProcessId
0x180049b02  mov     edx, eax
0x180049b04  xor     eax, eax
0x180049b06  cmp     [rsp+28h+dwProcessId], edx
0x180049b0a  cmovnz  rbx, rax
0x180049b0e  cmp     rbx, [rdi+68h]
0x180049b12  jz      short loc_180049AD3
0x180049b14  cmp     rbx, [rdi+60h]
0x180049b18  mov     [rdi+68h], rbx
0x180049b1c  setnz   sil
0x180049b20  jmp     short loc_180049AD3
```
