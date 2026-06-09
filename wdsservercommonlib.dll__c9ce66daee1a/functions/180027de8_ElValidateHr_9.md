# ElValidateHr_9

- ea: `0x180027de8`
- end: `0x180027ecc`
- name: `ElValidateHr_9`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027cf0`

## callees

- `0x1800063c4`
- `0x180027de8`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027e8a`
- `KERNEL32!SetLastError` at `0x180027eb4`
- `KERNEL32!SetLastError` at `0x180027e8a`
- `KERNEL32!SetLastError` at `0x180027eb4`
- `KERNEL32!GetLastError` at `0x180027df8`
- `KERNEL32!GetLastError` at `0x180027e4b`
- `KERNEL32!GetLastError` at `0x180027e96`
- `KERNEL32!GetLastError` at `0x180027df8`
- `KERNEL32!GetLastError` at `0x180027e4b`
- `KERNEL32!GetLastError` at `0x180027e96`

## string_xrefs

- `0x180027e18`: `onecore\base\eco\wds\wdslib\common\src\wdscred.cpp`
- `0x180027e68`: `onecore\base\eco\wds\wdslib\common\src\wdscred.cpp`

## pseudocode

```c
__int64 ElValidateHr_9()
{
  DWORD LastError; // ebx
  DWORD v1; // ebx

  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscred.cpp",
      69,
      &dword_1800331C4,
      -2147024809);
  }
  else
  {
    if ( !g_ErrLibTraceFunction )
      goto LABEL_6;
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscred.cpp",
      69,
      &dword_1800331C4,
      -2147024809);
  }
  SetLastError(LastError);
LABEL_6:
  v1 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180027de8  push    rbx
0x180027dea  sub     rsp, 40h
0x180027dee  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027df6  jz      short loc_180027E41
0x180027df8  call    cs:__imp_GetLastError
0x180027dff  nop     dword ptr [rax+rax+00h]
0x180027e04  lea     r9, dword_1800331C4
0x180027e0b  mov     [rsp+48h+var_20], 80070057h
0x180027e13  mov     [rsp+48h+var_28], r9
0x180027e18  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027e1f  mov     ebx, eax
0x180027e21  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180027e28  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027e2f  mov     r9d, 45h ; 'E'
0x180027e35  mov     ecx, 80000h
0x180027e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e3f  jmp     short loc_180027E88
0x180027e41  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027e49  jz      short loc_180027E96
0x180027e4b  call    cs:__imp_GetLastError
0x180027e52  nop     dword ptr [rax+rax+00h]
0x180027e57  lea     r9, dword_1800331C4
0x180027e5e  mov     dword ptr [rsp+48h+var_28], 80070057h
0x180027e66  mov     ebx, eax
0x180027e68  lea     rdx, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027e6f  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027e76  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180027e7d  mov     r8d, 45h ; 'E'
0x180027e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e88  mov     ecx, ebx; dwErrCode
0x180027e8a  call    cs:__imp_SetLastError
0x180027e91  nop     dword ptr [rax+rax+00h]
0x180027e96  call    cs:__imp_GetLastError
0x180027e9d  nop     dword ptr [rax+rax+00h]
0x180027ea2  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180027ea9  mov     ebx, eax
0x180027eab  jz      short loc_180027EB2
0x180027ead  call    ElTraceErrorInfo
0x180027eb2  mov     ecx, ebx; dwErrCode
0x180027eb4  call    cs:__imp_SetLastError
0x180027ebb  nop     dword ptr [rax+rax+00h]
0x180027ec0  mov     eax, 80070057h
0x180027ec5  add     rsp, 40h
0x180027ec9  pop     rbx
0x180027eca  retn
```
