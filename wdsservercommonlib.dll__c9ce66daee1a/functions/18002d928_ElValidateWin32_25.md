# ElValidateWin32_25

- ea: `0x18002d928`
- end: `0x18002d9f1`
- name: `ElValidateWin32_25`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d390`
- `0x18002d430`

## callees

- `0x18002d928`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d9d2`
- `KERNEL32!SetLastError` at `0x18002d9d2`
- `KERNEL32!GetLastError` at `0x18002d94e`
- `KERNEL32!GetLastError` at `0x18002d99a`
- `KERNEL32!GetLastError` at `0x18002d94e`
- `KERNEL32!GetLastError` at `0x18002d99a`

## string_xrefs

- `0x18002d96a`: `onecore\base\eco\wds\wdslib\common\src\dhcppacket.cpp`
- `0x18002d9b3`: `onecore\base\eco\wds\wdslib\common\src\dhcppacket.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_25(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcppacket.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcppacket.cpp",
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
0x18002d928  mov     [rsp+arg_0], rbx
0x18002d92d  mov     [rsp+arg_8], rsi
0x18002d932  push    rdi
0x18002d933  sub     rsp, 40h
0x18002d937  mov     esi, r9d
0x18002d93a  mov     edi, ecx
0x18002d93c  test    ecx, ecx
0x18002d93e  jz      loc_18002D9DE
0x18002d944  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002d94c  jz      short loc_18002D990
0x18002d94e  call    cs:__imp_GetLastError
0x18002d955  nop     dword ptr [rax+rax+00h]
0x18002d95a  lea     r9, dword_1800331C4
0x18002d961  mov     [rsp+48h+var_20], edi
0x18002d965  mov     [rsp+48h+var_28], r9
0x18002d96a  lea     r8, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002d971  mov     ebx, eax
0x18002d973  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002d97a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002d981  mov     r9d, esi
0x18002d984  mov     ecx, 80000h
0x18002d989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d98e  jmp     short loc_18002D9D0
0x18002d990  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002d998  jz      short loc_18002D9DE
0x18002d99a  call    cs:__imp_GetLastError
0x18002d9a1  nop     dword ptr [rax+rax+00h]
0x18002d9a6  lea     r9, dword_1800331C4
0x18002d9ad  mov     dword ptr [rsp+48h+var_28], edi
0x18002d9b1  mov     ebx, eax
0x18002d9b3  lea     rdx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002d9ba  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002d9c1  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002d9c8  mov     r8d, esi
0x18002d9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9d0  mov     ecx, ebx; dwErrCode
0x18002d9d2  call    cs:__imp_SetLastError
0x18002d9d9  nop     dword ptr [rax+rax+00h]
0x18002d9de  mov     rbx, [rsp+48h+arg_0]
0x18002d9e3  mov     eax, edi
0x18002d9e5  mov     rsi, [rsp+48h+arg_8]
0x18002d9ea  add     rsp, 40h
0x18002d9ee  pop     rdi
0x18002d9ef  retn
```
