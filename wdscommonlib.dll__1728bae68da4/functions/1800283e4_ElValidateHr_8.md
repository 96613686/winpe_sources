# ElValidateHr_8

- ea: `0x1800283e4`
- end: `0x1800284d7`
- name: `ElValidateHr_8`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027580`
- `0x180027ac0`
- `0x180027c80`

## callees

- `0x180006ea4`
- `0x1800283e4`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002848e`
- `KERNEL32!SetLastError` at `0x1800284b8`
- `KERNEL32!SetLastError` at `0x18002848e`
- `KERNEL32!SetLastError` at `0x1800284b8`
- `KERNEL32!GetLastError` at `0x18002840a`
- `KERNEL32!GetLastError` at `0x180028456`
- `KERNEL32!GetLastError` at `0x18002849a`
- `KERNEL32!GetLastError` at `0x18002840a`
- `KERNEL32!GetLastError` at `0x180028456`
- `KERNEL32!GetLastError` at `0x18002849a`

## string_xrefs

- `0x180028426`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x18002846f`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

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
      "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
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
0x1800283e4  mov     [rsp+arg_0], rbx
0x1800283e9  mov     [rsp+arg_8], rsi
0x1800283ee  push    rdi
0x1800283ef  sub     rsp, 40h
0x1800283f3  mov     esi, r9d
0x1800283f6  mov     edi, ecx
0x1800283f8  test    ecx, ecx
0x1800283fa  jns     loc_1800284C4
0x180028400  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028408  jz      short loc_18002844C
0x18002840a  call    cs:__imp_GetLastError
0x180028411  nop     dword ptr [rax+rax+00h]
0x180028416  lea     r9, dword_18003572C
0x18002841d  mov     [rsp+48h+var_20], edi
0x180028421  mov     [rsp+48h+var_28], r9
0x180028426  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x18002842d  mov     ebx, eax
0x18002842f  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028436  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002843d  mov     r9d, esi
0x180028440  mov     ecx, 80000h
0x180028445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002844a  jmp     short loc_18002848C
0x18002844c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028454  jz      short loc_18002849A
0x180028456  call    cs:__imp_GetLastError
0x18002845d  nop     dword ptr [rax+rax+00h]
0x180028462  lea     r9, dword_18003572C
0x180028469  mov     dword ptr [rsp+48h+var_28], edi
0x18002846d  mov     ebx, eax
0x18002846f  lea     rdx, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180028476  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002847d  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028484  mov     r8d, esi
0x180028487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002848c  mov     ecx, ebx; dwErrCode
0x18002848e  call    cs:__imp_SetLastError
0x180028495  nop     dword ptr [rax+rax+00h]
0x18002849a  call    cs:__imp_GetLastError
0x1800284a1  nop     dword ptr [rax+rax+00h]
0x1800284a6  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800284ad  mov     ebx, eax
0x1800284af  jz      short loc_1800284B6
0x1800284b1  call    ElTraceErrorInfo
0x1800284b6  mov     ecx, ebx; dwErrCode
0x1800284b8  call    cs:__imp_SetLastError
0x1800284bf  nop     dword ptr [rax+rax+00h]
0x1800284c4  mov     rbx, [rsp+48h+arg_0]
0x1800284c9  mov     eax, edi
0x1800284cb  mov     rsi, [rsp+48h+arg_8]
0x1800284d0  add     rsp, 40h
0x1800284d4  pop     rdi
0x1800284d5  retn
```
