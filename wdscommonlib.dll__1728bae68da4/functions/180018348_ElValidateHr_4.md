# ElValidateHr_4

- ea: `0x180018348`
- end: `0x18001843b`
- name: `ElValidateHr_4`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017540`
- `0x180017720`

## callees

- `0x180006ea4`
- `0x180018348`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800183f2`
- `KERNEL32!SetLastError` at `0x18001841c`
- `KERNEL32!SetLastError` at `0x1800183f2`
- `KERNEL32!SetLastError` at `0x18001841c`
- `KERNEL32!GetLastError` at `0x18001836e`
- `KERNEL32!GetLastError` at `0x1800183ba`
- `KERNEL32!GetLastError` at `0x1800183fe`
- `KERNEL32!GetLastError` at `0x18001836e`
- `KERNEL32!GetLastError` at `0x1800183ba`
- `KERNEL32!GetLastError` at `0x1800183fe`

## string_xrefs

- `0x18001838a`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`
- `0x1800183d3`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_4(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
      a4,
      &dword_18003572C,
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
      a4,
      &dword_18003572C,
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
0x180018348  mov     [rsp+arg_0], rbx
0x18001834d  mov     [rsp+arg_8], rsi
0x180018352  push    rdi
0x180018353  sub     rsp, 40h
0x180018357  mov     esi, r9d
0x18001835a  mov     edi, ecx
0x18001835c  test    ecx, ecx
0x18001835e  jns     loc_180018428
0x180018364  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001836c  jz      short loc_1800183B0
0x18001836e  call    cs:__imp_GetLastError
0x180018375  nop     dword ptr [rax+rax+00h]
0x18001837a  lea     r9, dword_18003572C
0x180018381  mov     [rsp+48h+var_20], edi
0x180018385  mov     [rsp+48h+var_28], r9
0x18001838a  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180018391  mov     ebx, eax
0x180018393  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001839a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800183a1  mov     r9d, esi
0x1800183a4  mov     ecx, 80000h
0x1800183a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183ae  jmp     short loc_1800183F0
0x1800183b0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800183b8  jz      short loc_1800183FE
0x1800183ba  call    cs:__imp_GetLastError
0x1800183c1  nop     dword ptr [rax+rax+00h]
0x1800183c6  lea     r9, dword_18003572C
0x1800183cd  mov     dword ptr [rsp+48h+var_28], edi
0x1800183d1  mov     ebx, eax
0x1800183d3  lea     rdx, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800183da  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800183e1  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800183e8  mov     r8d, esi
0x1800183eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183f0  mov     ecx, ebx; dwErrCode
0x1800183f2  call    cs:__imp_SetLastError
0x1800183f9  nop     dword ptr [rax+rax+00h]
0x1800183fe  call    cs:__imp_GetLastError
0x180018405  nop     dword ptr [rax+rax+00h]
0x18001840a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180018411  mov     ebx, eax
0x180018413  jz      short loc_18001841A
0x180018415  call    ElTraceErrorInfo
0x18001841a  mov     ecx, ebx; dwErrCode
0x18001841c  call    cs:__imp_SetLastError
0x180018423  nop     dword ptr [rax+rax+00h]
0x180018428  mov     rbx, [rsp+48h+arg_0]
0x18001842d  mov     eax, edi
0x18001842f  mov     rsi, [rsp+48h+arg_8]
0x180018434  add     rsp, 40h
0x180018438  pop     rdi
0x180018439  retn
```
