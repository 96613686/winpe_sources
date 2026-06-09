# ElValidateHr

- ea: `0x180006f7c`
- end: `0x18000706f`
- name: `ElValidateHr`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800066c0`
- `0x1800068f0`
- `0x180006b50`
- `0x180006cb0`
- `0x180006d20`

## callees

- `0x180006ea4`
- `0x180006f7c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007026`
- `KERNEL32!SetLastError` at `0x180007050`
- `KERNEL32!SetLastError` at `0x180007026`
- `KERNEL32!SetLastError` at `0x180007050`
- `KERNEL32!GetLastError` at `0x180006fa2`
- `KERNEL32!GetLastError` at `0x180006fee`
- `KERNEL32!GetLastError` at `0x180007032`
- `KERNEL32!GetLastError` at `0x180006fa2`
- `KERNEL32!GetLastError` at `0x180006fee`
- `KERNEL32!GetLastError` at `0x180007032`

## string_xrefs

- `0x180006fbe`: `onecore\base\eco\wds\wdslib\common\src\firewall.cpp`
- `0x180007007`: `onecore\base\eco\wds\wdslib\common\src\firewall.cpp`

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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\firewall.cpp",
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
0x180006f7c  mov     [rsp+arg_0], rbx
0x180006f81  mov     [rsp+arg_8], rsi
0x180006f86  push    rdi
0x180006f87  sub     rsp, 40h
0x180006f8b  mov     esi, r9d
0x180006f8e  mov     edi, ecx
0x180006f90  test    ecx, ecx
0x180006f92  jns     loc_18000705C
0x180006f98  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006fa0  jz      short loc_180006FE4
0x180006fa2  call    cs:__imp_GetLastError
0x180006fa9  nop     dword ptr [rax+rax+00h]
0x180006fae  lea     r9, dword_18003572C
0x180006fb5  mov     [rsp+48h+var_20], edi
0x180006fb9  mov     [rsp+48h+var_28], r9
0x180006fbe  lea     r8, aOnecoreBaseEco_23; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180006fc5  mov     ebx, eax
0x180006fc7  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180006fce  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006fd5  mov     r9d, esi
0x180006fd8  mov     ecx, 80000h
0x180006fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe2  jmp     short loc_180007024
0x180006fe4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006fec  jz      short loc_180007032
0x180006fee  call    cs:__imp_GetLastError
0x180006ff5  nop     dword ptr [rax+rax+00h]
0x180006ffa  lea     r9, dword_18003572C
0x180007001  mov     dword ptr [rsp+48h+var_28], edi
0x180007005  mov     ebx, eax
0x180007007  lea     rdx, aOnecoreBaseEco_23; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000700e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007015  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000701c  mov     r8d, esi
0x18000701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007024  mov     ecx, ebx; dwErrCode
0x180007026  call    cs:__imp_SetLastError
0x18000702d  nop     dword ptr [rax+rax+00h]
0x180007032  call    cs:__imp_GetLastError
0x180007039  nop     dword ptr [rax+rax+00h]
0x18000703e  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180007045  mov     ebx, eax
0x180007047  jz      short loc_18000704E
0x180007049  call    ElTraceErrorInfo
0x18000704e  mov     ecx, ebx; dwErrCode
0x180007050  call    cs:__imp_SetLastError
0x180007057  nop     dword ptr [rax+rax+00h]
0x18000705c  mov     rbx, [rsp+48h+arg_0]
0x180007061  mov     eax, edi
0x180007063  mov     rsi, [rsp+48h+arg_8]
0x180007068  add     rsp, 40h
0x18000706c  pop     rdi
0x18000706d  retn
```
