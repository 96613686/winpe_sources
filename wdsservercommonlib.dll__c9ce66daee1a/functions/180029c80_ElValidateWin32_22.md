# ElValidateWin32_22

- ea: `0x180029c80`
- end: `0x180029d49`
- name: `ElValidateWin32_22`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029998`
- `0x180029b20`
- `0x180029bc0`

## callees

- `0x180029c80`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180029d2a`
- `KERNEL32!SetLastError` at `0x180029d2a`
- `KERNEL32!GetLastError` at `0x180029ca6`
- `KERNEL32!GetLastError` at `0x180029cf2`
- `KERNEL32!GetLastError` at `0x180029ca6`
- `KERNEL32!GetLastError` at `0x180029cf2`

## string_xrefs

- `0x180029cc2`: `onecore\base\eco\wds\wdslib\common\src\dhcplib.cpp`
- `0x180029d0b`: `onecore\base\eco\wds\wdslib\common\src\dhcplib.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_22(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcplib.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcplib.cpp",
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
0x180029c80  mov     [rsp+arg_0], rbx
0x180029c85  mov     [rsp+arg_8], rsi
0x180029c8a  push    rdi
0x180029c8b  sub     rsp, 40h
0x180029c8f  mov     esi, r9d
0x180029c92  mov     edi, ecx
0x180029c94  test    ecx, ecx
0x180029c96  jz      loc_180029D36
0x180029c9c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029ca4  jz      short loc_180029CE8
0x180029ca6  call    cs:__imp_GetLastError
0x180029cad  nop     dword ptr [rax+rax+00h]
0x180029cb2  lea     r9, dword_1800331C4
0x180029cb9  mov     [rsp+48h+var_20], edi
0x180029cbd  mov     [rsp+48h+var_28], r9
0x180029cc2  lea     r8, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029cc9  mov     ebx, eax
0x180029ccb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180029cd2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029cd9  mov     r9d, esi
0x180029cdc  mov     ecx, 80000h
0x180029ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ce6  jmp     short loc_180029D28
0x180029ce8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029cf0  jz      short loc_180029D36
0x180029cf2  call    cs:__imp_GetLastError
0x180029cf9  nop     dword ptr [rax+rax+00h]
0x180029cfe  lea     r9, dword_1800331C4
0x180029d05  mov     dword ptr [rsp+48h+var_28], edi
0x180029d09  mov     ebx, eax
0x180029d0b  lea     rdx, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029d12  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029d19  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180029d20  mov     r8d, esi
0x180029d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d28  mov     ecx, ebx; dwErrCode
0x180029d2a  call    cs:__imp_SetLastError
0x180029d31  nop     dword ptr [rax+rax+00h]
0x180029d36  mov     rbx, [rsp+48h+arg_0]
0x180029d3b  mov     eax, edi
0x180029d3d  mov     rsi, [rsp+48h+arg_8]
0x180029d42  add     rsp, 40h
0x180029d46  pop     rdi
0x180029d47  retn
```
