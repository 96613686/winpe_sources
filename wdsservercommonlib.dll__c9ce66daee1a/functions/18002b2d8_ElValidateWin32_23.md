# ElValidateWin32_23

- ea: `0x18002b2d8`
- end: `0x18002b3a1`
- name: `ElValidateWin32_23`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ac40`

## callees

- `0x18002b2d8`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002b382`
- `KERNEL32!SetLastError` at `0x18002b382`
- `KERNEL32!GetLastError` at `0x18002b2fe`
- `KERNEL32!GetLastError` at `0x18002b34a`
- `KERNEL32!GetLastError` at `0x18002b2fe`
- `KERNEL32!GetLastError` at `0x18002b34a`

## string_xrefs

- `0x18002b31a`: `onecore\base\eco\wds\wdslib\common\src\dhcpoptions.cpp`
- `0x18002b363`: `onecore\base\eco\wds\wdslib\common\src\dhcpoptions.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_23(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpoptions.cpp",
        a4,
        &dword_1800331C4,
        a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpoptions.cpp",
        a4,
        &dword_1800331C4,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002b2d8  mov     [rsp+arg_0], rbx
0x18002b2dd  mov     [rsp+arg_8], rsi
0x18002b2e2  push    rdi
0x18002b2e3  sub     rsp, 40h
0x18002b2e7  mov     esi, r9d
0x18002b2ea  mov     edi, ecx
0x18002b2ec  test    ecx, ecx
0x18002b2ee  jz      loc_18002B38E
0x18002b2f4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002b2fc  jz      short loc_18002B340
0x18002b2fe  call    cs:__imp_GetLastError
0x18002b305  nop     dword ptr [rax+rax+00h]
0x18002b30a  lea     r9, dword_1800331C4
0x18002b311  mov     [rsp+48h+var_20], edi
0x18002b315  mov     [rsp+48h+var_28], r9
0x18002b31a  lea     r8, aOnecoreBaseEco_23; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002b321  mov     ebx, eax
0x18002b323  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002b32a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002b331  mov     r9d, esi
0x18002b334  mov     ecx, 80000h
0x18002b339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b33e  jmp     short loc_18002B380
0x18002b340  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002b348  jz      short loc_18002B38E
0x18002b34a  call    cs:__imp_GetLastError
0x18002b351  nop     dword ptr [rax+rax+00h]
0x18002b356  lea     r9, dword_1800331C4
0x18002b35d  mov     dword ptr [rsp+48h+var_28], edi
0x18002b361  mov     ebx, eax
0x18002b363  lea     rdx, aOnecoreBaseEco_23; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002b36a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002b371  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002b378  mov     r8d, esi
0x18002b37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b380  mov     ecx, ebx; dwErrCode
0x18002b382  call    cs:__imp_SetLastError
0x18002b389  nop     dword ptr [rax+rax+00h]
0x18002b38e  mov     rbx, [rsp+48h+arg_0]
0x18002b393  mov     eax, edi
0x18002b395  mov     rsi, [rsp+48h+arg_8]
0x18002b39a  add     rsp, 40h
0x18002b39e  pop     rdi
0x18002b39f  retn
```
