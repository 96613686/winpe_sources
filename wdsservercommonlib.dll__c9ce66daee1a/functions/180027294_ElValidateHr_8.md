# ElValidateHr_8

- ea: `0x180027294`
- end: `0x180027387`
- name: `ElValidateHr_8`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026450`
- `0x180026980`
- `0x180026b40`

## callees

- `0x1800063c4`
- `0x180027294`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002733e`
- `KERNEL32!SetLastError` at `0x180027368`
- `KERNEL32!SetLastError` at `0x18002733e`
- `KERNEL32!SetLastError` at `0x180027368`
- `KERNEL32!GetLastError` at `0x1800272ba`
- `KERNEL32!GetLastError` at `0x180027306`
- `KERNEL32!GetLastError` at `0x18002734a`
- `KERNEL32!GetLastError` at `0x1800272ba`
- `KERNEL32!GetLastError` at `0x180027306`
- `KERNEL32!GetLastError` at `0x18002734a`

## string_xrefs

- `0x1800272d6`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x18002731f`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall ElValidateHr_8(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
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
      "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
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
0x180027294  mov     [rsp+arg_0], rbx
0x180027299  mov     [rsp+arg_8], rsi
0x18002729e  push    rdi
0x18002729f  sub     rsp, 40h
0x1800272a3  mov     esi, r9d
0x1800272a6  mov     edi, ecx
0x1800272a8  test    ecx, ecx
0x1800272aa  jns     loc_180027374
0x1800272b0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800272b8  jz      short loc_1800272FC
0x1800272ba  call    cs:__imp_GetLastError
0x1800272c1  nop     dword ptr [rax+rax+00h]
0x1800272c6  lea     r9, dword_1800331C4
0x1800272cd  mov     [rsp+48h+var_20], edi
0x1800272d1  mov     [rsp+48h+var_28], r9
0x1800272d6  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800272dd  mov     ebx, eax
0x1800272df  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800272e6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800272ed  mov     r9d, esi
0x1800272f0  mov     ecx, 80000h
0x1800272f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272fa  jmp     short loc_18002733C
0x1800272fc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027304  jz      short loc_18002734A
0x180027306  call    cs:__imp_GetLastError
0x18002730d  nop     dword ptr [rax+rax+00h]
0x180027312  lea     r9, dword_1800331C4
0x180027319  mov     dword ptr [rsp+48h+var_28], edi
0x18002731d  mov     ebx, eax
0x18002731f  lea     rdx, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027326  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002732d  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180027334  mov     r8d, esi
0x180027337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002733c  mov     ecx, ebx; dwErrCode
0x18002733e  call    cs:__imp_SetLastError
0x180027345  nop     dword ptr [rax+rax+00h]
0x18002734a  call    cs:__imp_GetLastError
0x180027351  nop     dword ptr [rax+rax+00h]
0x180027356  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18002735d  mov     ebx, eax
0x18002735f  jz      short loc_180027366
0x180027361  call    ElTraceErrorInfo
0x180027366  mov     ecx, ebx; dwErrCode
0x180027368  call    cs:__imp_SetLastError
0x18002736f  nop     dword ptr [rax+rax+00h]
0x180027374  mov     rbx, [rsp+48h+arg_0]
0x180027379  mov     eax, edi
0x18002737b  mov     rsi, [rsp+48h+arg_8]
0x180027380  add     rsp, 40h
0x180027384  pop     rdi
0x180027385  retn
```
