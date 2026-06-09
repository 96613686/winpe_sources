# ElValidateHr_0

- ea: `0x180007d30`
- end: `0x180007e23`
- name: `ElValidateHr_0`
- size: `243`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006810`
- `0x180007450`
- `0x180007790`
- `0x180007bb0`

## callees

- `0x1800063c4`
- `0x180007d30`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007dda`
- `KERNEL32!SetLastError` at `0x180007e04`
- `KERNEL32!SetLastError` at `0x180007dda`
- `KERNEL32!SetLastError` at `0x180007e04`
- `KERNEL32!GetLastError` at `0x180007d56`
- `KERNEL32!GetLastError` at `0x180007da2`
- `KERNEL32!GetLastError` at `0x180007de6`
- `KERNEL32!GetLastError` at `0x180007d56`
- `KERNEL32!GetLastError` at `0x180007da2`
- `KERNEL32!GetLastError` at `0x180007de6`

## string_xrefs

- `0x180007d72`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`
- `0x180007dbb`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_0(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscommon.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscommon.cpp",
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
0x180007d30  mov     [rsp+arg_0], rbx
0x180007d35  mov     [rsp+arg_8], rsi
0x180007d3a  push    rdi
0x180007d3b  sub     rsp, 40h
0x180007d3f  mov     esi, r9d
0x180007d42  mov     edi, ecx
0x180007d44  test    ecx, ecx
0x180007d46  jns     loc_180007E10
0x180007d4c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007d54  jz      short loc_180007D98
0x180007d56  call    cs:__imp_GetLastError
0x180007d5d  nop     dword ptr [rax+rax+00h]
0x180007d62  lea     r9, dword_1800331C4
0x180007d69  mov     [rsp+48h+var_20], edi
0x180007d6d  mov     [rsp+48h+var_28], r9
0x180007d72  lea     r8, aOnecoreBaseEco_18; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180007d79  mov     ebx, eax
0x180007d7b  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180007d82  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007d89  mov     r9d, esi
0x180007d8c  mov     ecx, 80000h
0x180007d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d96  jmp     short loc_180007DD8
0x180007d98  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007da0  jz      short loc_180007DE6
0x180007da2  call    cs:__imp_GetLastError
0x180007da9  nop     dword ptr [rax+rax+00h]
0x180007dae  lea     r9, dword_1800331C4
0x180007db5  mov     dword ptr [rsp+48h+var_28], edi
0x180007db9  mov     ebx, eax
0x180007dbb  lea     rdx, aOnecoreBaseEco_18; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180007dc2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007dc9  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180007dd0  mov     r8d, esi
0x180007dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd8  mov     ecx, ebx; dwErrCode
0x180007dda  call    cs:__imp_SetLastError
0x180007de1  nop     dword ptr [rax+rax+00h]
0x180007de6  call    cs:__imp_GetLastError
0x180007ded  nop     dword ptr [rax+rax+00h]
0x180007df2  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180007df9  mov     ebx, eax
0x180007dfb  jz      short loc_180007E02
0x180007dfd  call    ElTraceErrorInfo
0x180007e02  mov     ecx, ebx; dwErrCode
0x180007e04  call    cs:__imp_SetLastError
0x180007e0b  nop     dword ptr [rax+rax+00h]
0x180007e10  mov     rbx, [rsp+48h+arg_0]
0x180007e15  mov     eax, edi
0x180007e17  mov     rsi, [rsp+48h+arg_8]
0x180007e1c  add     rsp, 40h
0x180007e20  pop     rdi
0x180007e21  retn
```
