# ElValidateWin32_23

- ea: `0x18002c4c8`
- end: `0x18002c591`
- name: `ElValidateWin32_23`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002be30`

## callees

- `0x18002c4c8`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002c572`
- `KERNEL32!SetLastError` at `0x18002c572`
- `KERNEL32!GetLastError` at `0x18002c4ee`
- `KERNEL32!GetLastError` at `0x18002c53a`
- `KERNEL32!GetLastError` at `0x18002c4ee`
- `KERNEL32!GetLastError` at `0x18002c53a`

## string_xrefs

- `0x18002c50a`: `onecore\base\eco\wds\wdslib\common\src\dhcpoptions.cpp`
- `0x18002c553`: `onecore\base\eco\wds\wdslib\common\src\dhcpoptions.cpp`

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
        &dword_18003572C,
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
        &dword_18003572C,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002c4c8  mov     [rsp+arg_0], rbx
0x18002c4cd  mov     [rsp+arg_8], rsi
0x18002c4d2  push    rdi
0x18002c4d3  sub     rsp, 40h
0x18002c4d7  mov     esi, r9d
0x18002c4da  mov     edi, ecx
0x18002c4dc  test    ecx, ecx
0x18002c4de  jz      loc_18002C57E
0x18002c4e4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002c4ec  jz      short loc_18002C530
0x18002c4ee  call    cs:__imp_GetLastError
0x18002c4f5  nop     dword ptr [rax+rax+00h]
0x18002c4fa  lea     r9, dword_18003572C
0x18002c501  mov     [rsp+48h+var_20], edi
0x18002c505  mov     [rsp+48h+var_28], r9
0x18002c50a  lea     r8, aOnecoreBaseEco_22; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002c511  mov     ebx, eax
0x18002c513  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002c51a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002c521  mov     r9d, esi
0x18002c524  mov     ecx, 80000h
0x18002c529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c52e  jmp     short loc_18002C570
0x18002c530  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002c538  jz      short loc_18002C57E
0x18002c53a  call    cs:__imp_GetLastError
0x18002c541  nop     dword ptr [rax+rax+00h]
0x18002c546  lea     r9, dword_18003572C
0x18002c54d  mov     dword ptr [rsp+48h+var_28], edi
0x18002c551  mov     ebx, eax
0x18002c553  lea     rdx, aOnecoreBaseEco_22; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002c55a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002c561  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002c568  mov     r8d, esi
0x18002c56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c570  mov     ecx, ebx; dwErrCode
0x18002c572  call    cs:__imp_SetLastError
0x18002c579  nop     dword ptr [rax+rax+00h]
0x18002c57e  mov     rbx, [rsp+48h+arg_0]
0x18002c583  mov     eax, edi
0x18002c585  mov     rsi, [rsp+48h+arg_8]
0x18002c58a  add     rsp, 40h
0x18002c58e  pop     rdi
0x18002c58f  retn
```
