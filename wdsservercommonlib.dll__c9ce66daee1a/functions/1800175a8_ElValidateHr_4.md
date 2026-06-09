# ElValidateHr_4

- ea: `0x1800175a8`
- end: `0x18001769b`
- name: `ElValidateHr_4`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800167b0`
- `0x180016990`

## callees

- `0x1800063c4`
- `0x1800175a8`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180017652`
- `KERNEL32!SetLastError` at `0x18001767c`
- `KERNEL32!SetLastError` at `0x180017652`
- `KERNEL32!SetLastError` at `0x18001767c`
- `KERNEL32!GetLastError` at `0x1800175ce`
- `KERNEL32!GetLastError` at `0x18001761a`
- `KERNEL32!GetLastError` at `0x18001765e`
- `KERNEL32!GetLastError` at `0x1800175ce`
- `KERNEL32!GetLastError` at `0x18001761a`
- `KERNEL32!GetLastError` at `0x18001765e`

## string_xrefs

- `0x1800175ea`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`
- `0x180017633`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`

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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
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
0x1800175a8  mov     [rsp+arg_0], rbx
0x1800175ad  mov     [rsp+arg_8], rsi
0x1800175b2  push    rdi
0x1800175b3  sub     rsp, 40h
0x1800175b7  mov     esi, r9d
0x1800175ba  mov     edi, ecx
0x1800175bc  test    ecx, ecx
0x1800175be  jns     loc_180017688
0x1800175c4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800175cc  jz      short loc_180017610
0x1800175ce  call    cs:__imp_GetLastError
0x1800175d5  nop     dword ptr [rax+rax+00h]
0x1800175da  lea     r9, dword_1800331C4
0x1800175e1  mov     [rsp+48h+var_20], edi
0x1800175e5  mov     [rsp+48h+var_28], r9
0x1800175ea  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800175f1  mov     ebx, eax
0x1800175f3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800175fa  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180017601  mov     r9d, esi
0x180017604  mov     ecx, 80000h
0x180017609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001760e  jmp     short loc_180017650
0x180017610  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180017618  jz      short loc_18001765E
0x18001761a  call    cs:__imp_GetLastError
0x180017621  nop     dword ptr [rax+rax+00h]
0x180017626  lea     r9, dword_1800331C4
0x18001762d  mov     dword ptr [rsp+48h+var_28], edi
0x180017631  mov     ebx, eax
0x180017633  lea     rdx, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001763a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180017641  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180017648  mov     r8d, esi
0x18001764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017650  mov     ecx, ebx; dwErrCode
0x180017652  call    cs:__imp_SetLastError
0x180017659  nop     dword ptr [rax+rax+00h]
0x18001765e  call    cs:__imp_GetLastError
0x180017665  nop     dword ptr [rax+rax+00h]
0x18001766a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180017671  mov     ebx, eax
0x180017673  jz      short loc_18001767A
0x180017675  call    ElTraceErrorInfo
0x18001767a  mov     ecx, ebx; dwErrCode
0x18001767c  call    cs:__imp_SetLastError
0x180017683  nop     dword ptr [rax+rax+00h]
0x180017688  mov     rbx, [rsp+48h+arg_0]
0x18001768d  mov     eax, edi
0x18001768f  mov     rsi, [rsp+48h+arg_8]
0x180017694  add     rsp, 40h
0x180017698  pop     rdi
0x180017699  retn
```
