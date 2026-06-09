# CDigitalClock::_SetDefaultFont(void)

- ea: `0x180022b98`
- end: `0x180022c15`
- name: `?_SetDefaultFont@CDigitalClock@@AEAAXXZ`
- size: `125`
- prototype: `void __fastcall(CDigitalClock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021310`

## callees

- `0x180022b98`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180022bdd`
- `USER32!SystemParametersInfoW` at `0x180022bdd`
- `GDI32!CreateFontIndirectW` at `0x180022bef`
- `GDI32!CreateFontIndirectW` at `0x180022bef`

## pseudocode

```c
void __fastcall CDigitalClock::_SetDefaultFont(CDigitalClock *this)
{
  int pvParam; // [rsp+20h] [rbp-218h] BYREF
  _BYTE v3[404]; // [rsp+24h] [rbp-214h] BYREF
  LOGFONTW lf; // [rsp+1B8h] [rbp-80h] BYREF

  memset_0(v3, 0, 0x1F4u);
  pvParam = 504;
  if ( SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
    *((_QWORD *)this + 19) = CreateFontIndirectW(&lf);
}

```

## disassembly

```asm
0x180022b98  push    rbx
0x180022b9a  sub     rsp, 230h
0x180022ba1  mov     rax, cs:__security_cookie
0x180022ba8  xor     rax, rsp
0x180022bab  mov     [rsp+238h+var_18], rax
0x180022bb3  mov     rbx, rcx
0x180022bb6  xor     edx, edx; Val
0x180022bb8  lea     rcx, [rsp+238h+var_214]; void *
0x180022bbd  mov     r8d, 1F4h; Size
0x180022bc3  call    memset_0
0x180022bc8  xor     r9d, r9d; fWinIni
0x180022bcb  lea     r8, [rsp+238h+pvParam]; pvParam
0x180022bd0  mov     edx, 1F8h; uiParam
0x180022bd5  mov     [rsp+238h+pvParam], edx
0x180022bd9  lea     ecx, [r9+29h]; uiAction
0x180022bdd  call    cs:__imp_SystemParametersInfoW
0x180022be3  test    eax, eax
0x180022be5  jz      short loc_180022BFC
0x180022be7  lea     rcx, [rsp+238h+lf]; lplf
0x180022bef  call    cs:__imp_CreateFontIndirectW
0x180022bf5  mov     [rbx+98h], rax
0x180022bfc  mov     rcx, [rsp+238h+var_18]
0x180022c04  xor     rcx, rsp; StackCookie
0x180022c07  call    __security_check_cookie
0x180022c0c  add     rsp, 230h
0x180022c13  pop     rbx
0x180022c14  retn
```
