# ElValidateHr

- ea: `0x18000649c`
- end: `0x18000658f`
- name: `ElValidateHr`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005be0`
- `0x180005e10`
- `0x180006070`
- `0x1800061d0`
- `0x180006240`

## callees

- `0x1800063c4`
- `0x18000649c`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006546`
- `KERNEL32!SetLastError` at `0x180006570`
- `KERNEL32!SetLastError` at `0x180006546`
- `KERNEL32!SetLastError` at `0x180006570`
- `KERNEL32!GetLastError` at `0x1800064c2`
- `KERNEL32!GetLastError` at `0x18000650e`
- `KERNEL32!GetLastError` at `0x180006552`
- `KERNEL32!GetLastError` at `0x1800064c2`
- `KERNEL32!GetLastError` at `0x18000650e`
- `KERNEL32!GetLastError` at `0x180006552`

## string_xrefs

- `0x1800064de`: `onecore\base\eco\wds\wdslib\common\src\firewall.cpp`
- `0x180006527`: `onecore\base\eco\wds\wdslib\common\src\firewall.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\firewall.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\firewall.cpp",
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
0x18000649c  mov     [rsp+arg_0], rbx
0x1800064a1  mov     [rsp+arg_8], rsi
0x1800064a6  push    rdi
0x1800064a7  sub     rsp, 40h
0x1800064ab  mov     esi, r9d
0x1800064ae  mov     edi, ecx
0x1800064b0  test    ecx, ecx
0x1800064b2  jns     loc_18000657C
0x1800064b8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800064c0  jz      short loc_180006504
0x1800064c2  call    cs:__imp_GetLastError
0x1800064c9  nop     dword ptr [rax+rax+00h]
0x1800064ce  lea     r9, dword_1800331C4
0x1800064d5  mov     [rsp+48h+var_20], edi
0x1800064d9  mov     [rsp+48h+var_28], r9
0x1800064de  lea     r8, aOnecoreBaseEco_24; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800064e5  mov     ebx, eax
0x1800064e7  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800064ee  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800064f5  mov     r9d, esi
0x1800064f8  mov     ecx, 80000h
0x1800064fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006502  jmp     short loc_180006544
0x180006504  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000650c  jz      short loc_180006552
0x18000650e  call    cs:__imp_GetLastError
0x180006515  nop     dword ptr [rax+rax+00h]
0x18000651a  lea     r9, dword_1800331C4
0x180006521  mov     dword ptr [rsp+48h+var_28], edi
0x180006525  mov     ebx, eax
0x180006527  lea     rdx, aOnecoreBaseEco_24; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000652e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006535  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000653c  mov     r8d, esi
0x18000653f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006544  mov     ecx, ebx; dwErrCode
0x180006546  call    cs:__imp_SetLastError
0x18000654d  nop     dword ptr [rax+rax+00h]
0x180006552  call    cs:__imp_GetLastError
0x180006559  nop     dword ptr [rax+rax+00h]
0x18000655e  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180006565  mov     ebx, eax
0x180006567  jz      short loc_18000656E
0x180006569  call    ElTraceErrorInfo
0x18000656e  mov     ecx, ebx; dwErrCode
0x180006570  call    cs:__imp_SetLastError
0x180006577  nop     dword ptr [rax+rax+00h]
0x18000657c  mov     rbx, [rsp+48h+arg_0]
0x180006581  mov     eax, edi
0x180006583  mov     rsi, [rsp+48h+arg_8]
0x180006588  add     rsp, 40h
0x18000658c  pop     rdi
0x18000658d  retn
```
