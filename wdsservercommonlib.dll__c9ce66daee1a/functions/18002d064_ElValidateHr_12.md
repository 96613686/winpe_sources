# ElValidateHr_12

- ea: `0x18002d064`
- end: `0x18002d157`
- name: `ElValidateHr_12`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002c8d0`

## callees

- `0x1800063c4`
- `0x18002d064`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d10e`
- `KERNEL32!SetLastError` at `0x18002d138`
- `KERNEL32!SetLastError` at `0x18002d10e`
- `KERNEL32!SetLastError` at `0x18002d138`
- `KERNEL32!GetLastError` at `0x18002d08a`
- `KERNEL32!GetLastError` at `0x18002d0d6`
- `KERNEL32!GetLastError` at `0x18002d11a`
- `KERNEL32!GetLastError` at `0x18002d08a`
- `KERNEL32!GetLastError` at `0x18002d0d6`
- `KERNEL32!GetLastError` at `0x18002d11a`

## string_xrefs

- `0x18002d0a6`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`
- `0x18002d0ef`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_12(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v7; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
      a4,
      &dword_1800331C4,
      a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
      a4,
      &dword_1800331C4,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v7 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18002d064  mov     [rsp+arg_0], rbx
0x18002d069  mov     [rsp+arg_8], rsi
0x18002d06e  push    rdi
0x18002d06f  sub     rsp, 40h
0x18002d073  mov     esi, r9d
0x18002d076  mov     edi, ecx
0x18002d078  test    ecx, ecx
0x18002d07a  jns     loc_18002D144
0x18002d080  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002d088  jz      short loc_18002D0CC
0x18002d08a  call    cs:__imp_GetLastError
0x18002d091  nop     dword ptr [rax+rax+00h]
0x18002d096  lea     r9, dword_1800331C4
0x18002d09d  mov     [rsp+48h+var_20], edi
0x18002d0a1  mov     [rsp+48h+var_28], r9
0x18002d0a6  lea     r8, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002d0ad  mov     ebx, eax
0x18002d0af  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002d0b6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002d0bd  mov     r9d, esi
0x18002d0c0  mov     ecx, 80000h
0x18002d0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0ca  jmp     short loc_18002D10C
0x18002d0cc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002d0d4  jz      short loc_18002D11A
0x18002d0d6  call    cs:__imp_GetLastError
0x18002d0dd  nop     dword ptr [rax+rax+00h]
0x18002d0e2  lea     r9, dword_1800331C4
0x18002d0e9  mov     dword ptr [rsp+48h+var_28], edi
0x18002d0ed  mov     ebx, eax
0x18002d0ef  lea     rdx, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002d0f6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002d0fd  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002d104  mov     r8d, esi
0x18002d107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d10c  mov     ecx, ebx; dwErrCode
0x18002d10e  call    cs:__imp_SetLastError
0x18002d115  nop     dword ptr [rax+rax+00h]
0x18002d11a  call    cs:__imp_GetLastError
0x18002d121  nop     dword ptr [rax+rax+00h]
0x18002d126  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18002d12d  mov     ebx, eax
0x18002d12f  jz      short loc_18002D136
0x18002d131  call    ElTraceErrorInfo
0x18002d136  mov     ecx, ebx; dwErrCode
0x18002d138  call    cs:__imp_SetLastError
0x18002d13f  nop     dword ptr [rax+rax+00h]
0x18002d144  mov     rbx, [rsp+48h+arg_0]
0x18002d149  mov     eax, edi
0x18002d14b  mov     rsi, [rsp+48h+arg_8]
0x18002d150  add     rsp, 40h
0x18002d154  pop     rdi
0x18002d155  retn
```
