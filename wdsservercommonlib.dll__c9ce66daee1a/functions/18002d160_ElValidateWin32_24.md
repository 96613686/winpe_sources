# ElValidateWin32_24

- ea: `0x18002d160`
- end: `0x18002d229`
- name: `ElValidateWin32_24`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002b480`
- `0x18002b570`
- `0x18002b650`
- `0x18002b72c`
- `0x18002c45c`
- `0x18002c4ec`
- `0x18002c5d0`
- `0x18002c620`
- `0x18002c73c`
- `0x18002cce0`
- `0x18002cd9c`
- `0x18002cfa0`

## callees

- `0x18002d160`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d20a`
- `KERNEL32!SetLastError` at `0x18002d20a`
- `KERNEL32!GetLastError` at `0x18002d186`
- `KERNEL32!GetLastError` at `0x18002d1d2`
- `KERNEL32!GetLastError` at `0x18002d186`
- `KERNEL32!GetLastError` at `0x18002d1d2`

## string_xrefs

- `0x18002d1a2`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`
- `0x18002d1eb`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_24(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
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
0x18002d160  mov     [rsp+arg_0], rbx
0x18002d165  mov     [rsp+arg_8], rsi
0x18002d16a  push    rdi
0x18002d16b  sub     rsp, 40h
0x18002d16f  mov     esi, r9d
0x18002d172  mov     edi, ecx
0x18002d174  test    ecx, ecx
0x18002d176  jz      loc_18002D216
0x18002d17c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002d184  jz      short loc_18002D1C8
0x18002d186  call    cs:__imp_GetLastError
0x18002d18d  nop     dword ptr [rax+rax+00h]
0x18002d192  lea     r9, dword_1800331C4
0x18002d199  mov     [rsp+48h+var_20], edi
0x18002d19d  mov     [rsp+48h+var_28], r9
0x18002d1a2  lea     r8, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002d1a9  mov     ebx, eax
0x18002d1ab  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002d1b2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002d1b9  mov     r9d, esi
0x18002d1bc  mov     ecx, 80000h
0x18002d1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1c6  jmp     short loc_18002D208
0x18002d1c8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002d1d0  jz      short loc_18002D216
0x18002d1d2  call    cs:__imp_GetLastError
0x18002d1d9  nop     dword ptr [rax+rax+00h]
0x18002d1de  lea     r9, dword_1800331C4
0x18002d1e5  mov     dword ptr [rsp+48h+var_28], edi
0x18002d1e9  mov     ebx, eax
0x18002d1eb  lea     rdx, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002d1f2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002d1f9  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002d200  mov     r8d, esi
0x18002d203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d208  mov     ecx, ebx; dwErrCode
0x18002d20a  call    cs:__imp_SetLastError
0x18002d211  nop     dword ptr [rax+rax+00h]
0x18002d216  mov     rbx, [rsp+48h+arg_0]
0x18002d21b  mov     eax, edi
0x18002d21d  mov     rsi, [rsp+48h+arg_8]
0x18002d222  add     rsp, 40h
0x18002d226  pop     rdi
0x18002d227  retn
```
