# ElValidateHr_11

- ea: `0x180028dd8`
- end: `0x180028ecb`
- name: `ElValidateHr_11`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028990`
- `0x180028ce0`

## callees

- `0x1800063c4`
- `0x180028dd8`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180028e82`
- `KERNEL32!SetLastError` at `0x180028eac`
- `KERNEL32!SetLastError` at `0x180028e82`
- `KERNEL32!SetLastError` at `0x180028eac`
- `KERNEL32!GetLastError` at `0x180028dfe`
- `KERNEL32!GetLastError` at `0x180028e4a`
- `KERNEL32!GetLastError` at `0x180028e8e`
- `KERNEL32!GetLastError` at `0x180028dfe`
- `KERNEL32!GetLastError` at `0x180028e4a`
- `KERNEL32!GetLastError` at `0x180028e8e`

## string_xrefs

- `0x180028e1a`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`
- `0x180028e63`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_11(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
0x180028dd8  mov     [rsp+arg_0], rbx
0x180028ddd  mov     [rsp+arg_8], rsi
0x180028de2  push    rdi
0x180028de3  sub     rsp, 40h
0x180028de7  mov     esi, r9d
0x180028dea  mov     edi, ecx
0x180028dec  test    ecx, ecx
0x180028dee  jns     loc_180028EB8
0x180028df4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028dfc  jz      short loc_180028E40
0x180028dfe  call    cs:__imp_GetLastError
0x180028e05  nop     dword ptr [rax+rax+00h]
0x180028e0a  lea     r9, dword_1800331C4
0x180028e11  mov     [rsp+48h+var_20], edi
0x180028e15  mov     [rsp+48h+var_28], r9
0x180028e1a  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028e21  mov     ebx, eax
0x180028e23  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028e2a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028e31  mov     r9d, esi
0x180028e34  mov     ecx, 80000h
0x180028e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e3e  jmp     short loc_180028E80
0x180028e40  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028e48  jz      short loc_180028E8E
0x180028e4a  call    cs:__imp_GetLastError
0x180028e51  nop     dword ptr [rax+rax+00h]
0x180028e56  lea     r9, dword_1800331C4
0x180028e5d  mov     dword ptr [rsp+48h+var_28], edi
0x180028e61  mov     ebx, eax
0x180028e63  lea     rdx, aOnecoreBaseEco_26; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028e6a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028e71  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028e78  mov     r8d, esi
0x180028e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e80  mov     ecx, ebx; dwErrCode
0x180028e82  call    cs:__imp_SetLastError
0x180028e89  nop     dword ptr [rax+rax+00h]
0x180028e8e  call    cs:__imp_GetLastError
0x180028e95  nop     dword ptr [rax+rax+00h]
0x180028e9a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180028ea1  mov     ebx, eax
0x180028ea3  jz      short loc_180028EAA
0x180028ea5  call    ElTraceErrorInfo
0x180028eaa  mov     ecx, ebx; dwErrCode
0x180028eac  call    cs:__imp_SetLastError
0x180028eb3  nop     dword ptr [rax+rax+00h]
0x180028eb8  mov     rbx, [rsp+48h+arg_0]
0x180028ebd  mov     eax, edi
0x180028ebf  mov     rsi, [rsp+48h+arg_8]
0x180028ec4  add     rsp, 40h
0x180028ec8  pop     rdi
0x180028ec9  retn
```
