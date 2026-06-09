# EnumWindowsProc(HWND__ *,__int64)

- ea: `0x1800197e0`
- end: `0x1800198b5`
- name: `?EnumWindowsProc@@YAHPEAUHWND__@@_J@Z`
- size: `213`
- prototype: `__int64 __fastcall(HWND, WdcDataMonitor *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180012420`
- `0x1800197e0`

## import_xrefs

- `USER32!IsHungAppWindow` at `0x18001986a`
- `USER32!IsHungAppWindow` at `0x18001986a`
- `USER32!IsWindowVisible` at `0x180019823`
- `USER32!IsWindowVisible` at `0x180019842`
- `USER32!IsWindowVisible` at `0x180019823`
- `USER32!IsWindowVisible` at `0x180019842`
- `USER32!GetWindowLongW` at `0x180019813`
- `USER32!GetWindowLongW` at `0x180019813`
- `USER32!GetWindowThreadProcessId` at `0x18001988c`
- `USER32!GetWindowThreadProcessId` at `0x18001988c`
- `USER32!HungWindowFromGhostWindow` at `0x180019877`
- `USER32!HungWindowFromGhostWindow` at `0x180019877`
- `USER32!GetWindow` at `0x180019802`
- `USER32!GetWindow` at `0x180019802`
- `USER32!GhostWindowFromHungWindow` at `0x18001985c`
- `USER32!GhostWindowFromHungWindow` at `0x18001985c`

## pseudocode

```c
__int64 __fastcall EnumWindowsProc(HWND a1, WdcDataMonitor *a2)
{
  HWND v3; // rbx
  HWND Window; // rdi
  LONG WindowLongW; // esi
  __int64 v7; // rax
  DWORD dwProcessId; // [rsp+50h] [rbp+18h] BYREF
  struct _WDC_DATA_INFO *v9; // [rsp+58h] [rbp+20h] BYREF

  dwProcessId = 0;
  v9 = 0;
  v3 = a1;
  Window = GetWindow(a1, 4u);
  WindowLongW = GetWindowLongW(v3, -20);
  if ( (!Window || !IsWindowVisible(Window) || (WindowLongW & 0x40000) != 0)
    && IsWindowVisible(v3)
    && (WindowLongW & 0x80u) == 0
    && !GhostWindowFromHungWindow(v3)
    && IsHungAppWindow(v3) )
  {
    v7 = HungWindowFromGhostWindow(v3);
    if ( v7 )
      v3 = (HWND)v7;
    GetWindowThreadProcessId(v3, &dwProcessId);
    if ( (int)WdcDataMonitor::InfoFind(a2, dwProcessId, &v9) >= 0 )
      *((_DWORD *)v9 + 17) |= 8u;
  }
  return 1;
}

```

## disassembly

```asm
0x1800197e0  mov     [rsp+arg_0], rbx
0x1800197e5  push    rbp
0x1800197e6  push    rsi
0x1800197e7  push    rdi
0x1800197e8  sub     rsp, 20h
0x1800197ec  xor     eax, eax
0x1800197ee  mov     rbp, rdx
0x1800197f1  mov     edx, 4; uCmd
0x1800197f6  mov     [rsp+38h+dwProcessId], eax
0x1800197fa  mov     [rsp+38h+arg_18], rax
0x1800197ff  mov     rbx, rcx
0x180019802  call    cs:__imp_GetWindow
0x180019808  mov     edx, 0FFFFFFECh; nIndex
0x18001980d  mov     rcx, rbx; hWnd
0x180019810  mov     rdi, rax
0x180019813  call    cs:__imp_GetWindowLongW
0x180019819  mov     esi, eax
0x18001981b  test    rdi, rdi
0x18001981e  jnz     short loc_18001983F
0x180019820  mov     rcx, rbx; hWnd
0x180019823  call    cs:__imp_IsWindowVisible
0x180019829  test    eax, eax
0x18001982b  jnz     short loc_180019854
0x18001982d  mov     eax, 1
0x180019832  mov     rbx, [rsp+38h+arg_0]
0x180019837  add     rsp, 20h
0x18001983b  pop     rdi
0x18001983c  pop     rsi
0x18001983d  pop     rbp
0x18001983e  retn
0x18001983f  mov     rcx, rdi; hWnd
0x180019842  call    cs:__imp_IsWindowVisible
0x180019848  test    eax, eax
0x18001984a  jz      short loc_180019820
0x18001984c  bt      esi, 12h
0x180019850  jnb     short loc_18001982D
0x180019852  jmp     short loc_180019820
0x180019854  test    sil, sil
0x180019857  js      short loc_18001982D
0x180019859  mov     rcx, rbx
0x18001985c  call    cs:__imp_GhostWindowFromHungWindow
0x180019862  test    rax, rax
0x180019865  jnz     short loc_18001982D
0x180019867  mov     rcx, rbx; hwnd
0x18001986a  call    cs:__imp_IsHungAppWindow
0x180019870  test    eax, eax
0x180019872  jz      short loc_18001982D
0x180019874  mov     rcx, rbx
0x180019877  call    cs:__imp_HungWindowFromGhostWindow
0x18001987d  test    rax, rax
0x180019880  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x180019885  cmovnz  rbx, rax
0x180019889  mov     rcx, rbx; hWnd
0x18001988c  call    cs:__imp_GetWindowThreadProcessId
0x180019892  mov     edx, [rsp+38h+dwProcessId]; unsigned __int64
0x180019896  lea     r8, [rsp+38h+arg_18]; struct _WDC_DATA_INFO **
0x18001989b  mov     rcx, rbp; this
0x18001989e  call    ?InfoFind@WdcDataMonitor@@QEAAJ_KPEAPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::InfoFind(unsigned __int64,_WDC_DATA_INFO * *)
0x1800198a3  test    eax, eax
0x1800198a5  js      short loc_18001982D
0x1800198a7  mov     rax, [rsp+38h+arg_18]
0x1800198ac  or      dword ptr [rax+44h], 8
0x1800198b0  jmp     loc_18001982D
```
