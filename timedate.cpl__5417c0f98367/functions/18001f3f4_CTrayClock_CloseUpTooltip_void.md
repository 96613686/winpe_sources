# CTrayClock::_CloseUpTooltip(void)

- ea: `0x18001f3f4`
- end: `0x18001f484`
- name: `?_CloseUpTooltip@CTrayClock@@AEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(CTrayClock *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f220`
- `0x18001ff04`
- `0x180020410`

## callees

- `0x18001f3f4`
- `0x1800202bc`

## import_xrefs

- `USER32!DestroyWindow` at `0x18001f452`
- `USER32!DestroyWindow` at `0x18001f452`
- `USER32!SetWindowLongPtrW` at `0x18001f448`
- `USER32!SetWindowLongPtrW` at `0x18001f448`
- `USER32!KillTimer` at `0x18001f40c`
- `USER32!KillTimer` at `0x18001f40c`
- `UxTheme!CloseThemeData` at `0x18001f41b`
- `UxTheme!CloseThemeData` at `0x18001f41b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18001f42e`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18001f42e`

## pseudocode

```c
__int64 __fastcall CTrayClock::_CloseUpTooltip(HWND *this)
{
  unsigned int v2; // edi
  HWND v3; // rcx
  DirectUI::DUIXmlParser *v4; // rcx
  HWND v5; // rcx
  BOOL v6; // eax

  v2 = 0;
  KillTimer(this[3], 0xCBu);
  v3 = this[5];
  if ( v3 )
  {
    CloseThemeData(v3);
    this[5] = 0;
  }
  v4 = (DirectUI::DUIXmlParser *)this[11];
  if ( v4 )
  {
    DirectUI::DUIXmlParser::Destroy(v4);
    this[11] = 0;
  }
  v5 = this[3];
  if ( v5 )
  {
    SetWindowLongPtrW(v5, -21, 0);
    v6 = DestroyWindow(this[3]);
    this[3] = 0;
    v2 = !v6 ? 0x80004005 : 0;
  }
  if ( *((int *)this + 19) >= 0 )
    CTrayClock::s_Uninitialize();
  return v2;
}

```

## disassembly

```asm
0x18001f3f4  mov     [rsp+arg_0], rbx
0x18001f3f9  push    rdi
0x18001f3fa  sub     rsp, 20h
0x18001f3fe  mov     rbx, rcx
0x18001f401  mov     edx, 0CBh; uIDEvent
0x18001f406  mov     rcx, [rcx+18h]; hWnd
0x18001f40a  xor     edi, edi
0x18001f40c  call    cs:__imp_KillTimer
0x18001f412  mov     rcx, [rbx+28h]; hTheme
0x18001f416  test    rcx, rcx
0x18001f419  jz      short loc_18001F425
0x18001f41b  call    cs:__imp_CloseThemeData
0x18001f421  mov     [rbx+28h], rdi
0x18001f425  mov     rcx, [rbx+58h]
0x18001f429  test    rcx, rcx
0x18001f42c  jz      short loc_18001F438
0x18001f42e  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18001f434  mov     [rbx+58h], rdi
0x18001f438  mov     rcx, [rbx+18h]; hWnd
0x18001f43c  test    rcx, rcx
0x18001f43f  jz      short loc_18001F46C
0x18001f441  xor     r8d, r8d; dwNewLong
0x18001f444  lea     edx, [r8-15h]; nIndex
0x18001f448  call    cs:__imp_SetWindowLongPtrW
0x18001f44e  mov     rcx, [rbx+18h]; hWnd
0x18001f452  call    cs:__imp_DestroyWindow
0x18001f458  neg     eax
0x18001f45a  mov     qword ptr [rbx+18h], 0
0x18001f462  sbb     edi, edi
0x18001f464  not     edi
0x18001f466  and     edi, 80004005h
0x18001f46c  cmp     dword ptr [rbx+4Ch], 0
0x18001f470  jl      short loc_18001F477
0x18001f472  call    ?s_Uninitialize@CTrayClock@@CAXXZ; CTrayClock::s_Uninitialize(void)
0x18001f477  mov     rbx, [rsp+28h+arg_0]
0x18001f47c  mov     eax, edi
0x18001f47e  add     rsp, 20h
0x18001f482  pop     rdi
0x18001f483  retn
```
