# AccessibilityDialog::GetMonitorRect(void)

- ea: `0x1400203d8`
- end: `0x14002046e`
- name: `?GetMonitorRect@AccessibilityDialog@@AEAA?AUtagRECT@@XZ`
- size: `150`
- prototype: `struct tagRECT *__fastcall(AccessibilityDialog *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001f948`

## callees

- `0x140002480`
- `0x1400203d8`
- `0x140022dcc`

## import_xrefs

- `USER32!MonitorFromWindow` at `0x140020413`
- `USER32!MonitorFromWindow` at `0x140020413`
- `USER32!GetMonitorInfoW` at `0x140020427`
- `USER32!GetMonitorInfoW` at `0x140020427`

## string_xrefs

- `0x14002043c`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
struct tagRECT *__fastcall AccessibilityDialog::GetMonitorRect(
        AccessibilityDialog *this,
        struct tagRECT *__return_ptr retstr)
{
  HWND v2; // rcx
  HMONITOR v4; // rax
  const char *v5; // r9
  struct tagRECT *result; // rax
  tagMONITORINFO mi; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (HWND)*((_QWORD *)this + 5);
  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  v4 = MonitorFromWindow(v2, 2u);
  if ( !GetMonitorInfoW(v4, &mi) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xFB,
      (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
      v5);
  result = retstr;
  *retstr = mi.rcMonitor;
  return result;
}

```

## disassembly

```asm
0x1400203d8  push    rbx
0x1400203da  sub     rsp, 50h
0x1400203de  mov     rax, cs:__security_cookie
0x1400203e5  xor     rax, rsp
0x1400203e8  mov     [rsp+58h+var_10], rax
0x1400203ed  mov     rcx, [rcx+28h]; hwnd
0x1400203f1  xor     eax, eax
0x1400203f3  xorps   xmm0, xmm0
0x1400203f6  mov     qword ptr [rsp+58h+mi.rcWork.bottom], rax
0x1400203fb  mov     rbx, rdx
0x1400203fe  movups  xmmword ptr [rsp+58h+mi.cbSize], xmm0
0x140020403  lea     edx, [rax+2]; dwFlags
0x140020406  mov     [rsp+58h+mi.cbSize], 28h ; '('
0x14002040e  movups  xmmword ptr [rsp+58h+mi.rcMonitor.bottom], xmm0
0x140020413  call    cs:__imp_MonitorFromWindow
0x14002041a  nop     dword ptr [rax+rax+00h]
0x14002041f  mov     rcx, rax; hMonitor
0x140020422  lea     rdx, [rsp+58h+mi]; lpmi
0x140020427  call    cs:__imp_GetMonitorInfoW
0x14002042e  nop     dword ptr [rax+rax+00h]
0x140020433  test    eax, eax
0x140020435  jnz     short loc_14002044E
0x140020437  mov     rcx, [rsp+58h]; this
0x14002043c  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140020443  mov     edx, 0FBh; void *
0x140020448  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14002044e  movups  xmm0, xmmword ptr [rsp+58h+mi.rcMonitor.left]
0x140020453  mov     rax, rbx
0x140020456  movdqu  xmmword ptr [rbx], xmm0
0x14002045a  mov     rcx, [rsp+58h+var_10]
0x14002045f  xor     rcx, rsp; StackCookie
0x140020462  call    __security_check_cookie
0x140020467  add     rsp, 50h
0x14002046b  pop     rbx
0x14002046c  retn
```
