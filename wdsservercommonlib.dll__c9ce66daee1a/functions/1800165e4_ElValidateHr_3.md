# ElValidateHr_3

- ea: `0x1800165e4`
- end: `0x1800166d7`
- name: `ElValidateHr_3`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014b10`
- `0x180014d10`

## callees

- `0x1800063c4`
- `0x1800165e4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001668e`
- `KERNEL32!SetLastError` at `0x1800166b8`
- `KERNEL32!SetLastError` at `0x18001668e`
- `KERNEL32!SetLastError` at `0x1800166b8`
- `KERNEL32!GetLastError` at `0x18001660a`
- `KERNEL32!GetLastError` at `0x180016656`
- `KERNEL32!GetLastError` at `0x18001669a`
- `KERNEL32!GetLastError` at `0x18001660a`
- `KERNEL32!GetLastError` at `0x180016656`
- `KERNEL32!GetLastError` at `0x18001669a`

## string_xrefs

- `0x180016626`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x18001666f`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_3(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
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
0x1800165e4  mov     [rsp+arg_0], rbx
0x1800165e9  mov     [rsp+arg_8], rsi
0x1800165ee  push    rdi
0x1800165ef  sub     rsp, 40h
0x1800165f3  mov     esi, r9d
0x1800165f6  mov     edi, ecx
0x1800165f8  test    ecx, ecx
0x1800165fa  jns     loc_1800166C4
0x180016600  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180016608  jz      short loc_18001664C
0x18001660a  call    cs:__imp_GetLastError
0x180016611  nop     dword ptr [rax+rax+00h]
0x180016616  lea     r9, dword_1800331C4
0x18001661d  mov     [rsp+48h+var_20], edi
0x180016621  mov     [rsp+48h+var_28], r9
0x180016626  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001662d  mov     ebx, eax
0x18001662f  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180016636  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001663d  mov     r9d, esi
0x180016640  mov     ecx, 80000h
0x180016645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001664a  jmp     short loc_18001668C
0x18001664c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180016654  jz      short loc_18001669A
0x180016656  call    cs:__imp_GetLastError
0x18001665d  nop     dword ptr [rax+rax+00h]
0x180016662  lea     r9, dword_1800331C4
0x180016669  mov     dword ptr [rsp+48h+var_28], edi
0x18001666d  mov     ebx, eax
0x18001666f  lea     rdx, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180016676  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001667d  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180016684  mov     r8d, esi
0x180016687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001668c  mov     ecx, ebx; dwErrCode
0x18001668e  call    cs:__imp_SetLastError
0x180016695  nop     dword ptr [rax+rax+00h]
0x18001669a  call    cs:__imp_GetLastError
0x1800166a1  nop     dword ptr [rax+rax+00h]
0x1800166a6  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800166ad  mov     ebx, eax
0x1800166af  jz      short loc_1800166B6
0x1800166b1  call    ElTraceErrorInfo
0x1800166b6  mov     ecx, ebx; dwErrCode
0x1800166b8  call    cs:__imp_SetLastError
0x1800166bf  nop     dword ptr [rax+rax+00h]
0x1800166c4  mov     rbx, [rsp+48h+arg_0]
0x1800166c9  mov     eax, edi
0x1800166cb  mov     rsi, [rsp+48h+arg_8]
0x1800166d0  add     rsp, 40h
0x1800166d4  pop     rdi
0x1800166d5  retn
```
