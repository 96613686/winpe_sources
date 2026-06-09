# ElValidateHr_9

- ea: `0x180028f4c`
- end: `0x180029030`
- name: `ElValidateHr_9`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028e40`

## callees

- `0x180006ea4`
- `0x180028f4c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180028fee`
- `KERNEL32!SetLastError` at `0x180029018`
- `KERNEL32!SetLastError` at `0x180028fee`
- `KERNEL32!SetLastError` at `0x180029018`
- `KERNEL32!GetLastError` at `0x180028f5c`
- `KERNEL32!GetLastError` at `0x180028faf`
- `KERNEL32!GetLastError` at `0x180028ffa`
- `KERNEL32!GetLastError` at `0x180028f5c`
- `KERNEL32!GetLastError` at `0x180028faf`
- `KERNEL32!GetLastError` at `0x180028ffa`

## string_xrefs

- `0x180028f7c`: `onecore\base\eco\wds\wdslib\common\src\wdscred.cpp`
- `0x180028fcc`: `onecore\base\eco\wds\wdslib\common\src\wdscred.cpp`

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
      &dword_18003572C,
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
      &dword_18003572C,
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
0x180028f4c  push    rbx
0x180028f4e  sub     rsp, 40h
0x180028f52  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028f5a  jz      short loc_180028FA5
0x180028f5c  call    cs:__imp_GetLastError
0x180028f63  nop     dword ptr [rax+rax+00h]
0x180028f68  lea     r9, dword_18003572C
0x180028f6f  mov     [rsp+48h+var_20], 80070057h
0x180028f77  mov     [rsp+48h+var_28], r9
0x180028f7c  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028f83  mov     ebx, eax
0x180028f85  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028f8c  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028f93  mov     r9d, 45h ; 'E'
0x180028f99  mov     ecx, 80000h
0x180028f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fa3  jmp     short loc_180028FEC
0x180028fa5  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028fad  jz      short loc_180028FFA
0x180028faf  call    cs:__imp_GetLastError
0x180028fb6  nop     dword ptr [rax+rax+00h]
0x180028fbb  lea     r9, dword_18003572C
0x180028fc2  mov     dword ptr [rsp+48h+var_28], 80070057h
0x180028fca  mov     ebx, eax
0x180028fcc  lea     rdx, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028fd3  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028fda  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028fe1  mov     r8d, 45h ; 'E'
0x180028fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fec  mov     ecx, ebx; dwErrCode
0x180028fee  call    cs:__imp_SetLastError
0x180028ff5  nop     dword ptr [rax+rax+00h]
0x180028ffa  call    cs:__imp_GetLastError
0x180029001  nop     dword ptr [rax+rax+00h]
0x180029006  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18002900d  mov     ebx, eax
0x18002900f  jz      short loc_180029016
0x180029011  call    ElTraceErrorInfo
0x180029016  mov     ecx, ebx; dwErrCode
0x180029018  call    cs:__imp_SetLastError
0x18002901f  nop     dword ptr [rax+rax+00h]
0x180029024  mov     eax, 80070057h
0x180029029  add     rsp, 40h
0x18002902d  pop     rbx
0x18002902e  retn
```
