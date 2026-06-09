# ElValidateHr_1

- ea: `0x180006714`
- end: `0x180006807`
- name: `ElValidateHr_1`
- size: `243`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x1800062a0`
- `0x180006388`
- `0x180006470`
- `0x180006544`
- `0x1800068e0`
- `0x180006a20`
- `0x180006aa0`
- `0x180006bc0`
- `0x180006c60`
- `0x180006cb0`
- `0x180006d60`
- `0x180006e70`

## callees

- `0x180003130`
- `0x180006714`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000673a`
- `KERNEL32!GetLastError` at `0x180006786`
- `KERNEL32!GetLastError` at `0x1800067ca`
- `KERNEL32!GetLastError` at `0x18000673a`
- `KERNEL32!GetLastError` at `0x180006786`
- `KERNEL32!GetLastError` at `0x1800067ca`
- `KERNEL32!SetLastError` at `0x1800067be`
- `KERNEL32!SetLastError` at `0x1800067e8`
- `KERNEL32!SetLastError` at `0x1800067be`
- `KERNEL32!SetLastError` at `0x1800067e8`

## pseudocode

```c
__int64 __fastcall ElValidateHr_1(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "base\\eco\\wds\\wdsimage\\src\\imagegroup.cpp",
      a4,
      &word_180013F66,
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
      "base\\eco\\wds\\wdsimage\\src\\imagegroup.cpp",
      a4,
      &word_180013F66,
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
0x180006714  mov     [rsp+arg_0], rbx
0x180006719  mov     [rsp+arg_8], rsi
0x18000671e  push    rdi
0x18000671f  sub     rsp, 40h
0x180006723  mov     esi, r9d
0x180006726  mov     edi, ecx
0x180006728  test    ecx, ecx
0x18000672a  jns     loc_1800067F4
0x180006730  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006738  jz      short loc_18000677C
0x18000673a  call    cs:__imp_GetLastError
0x180006741  nop     dword ptr [rax+rax+00h]
0x180006746  lea     r9, word_180013F66
0x18000674d  mov     [rsp+48h+var_20], edi
0x180006751  mov     [rsp+48h+var_28], r9
0x180006756  lea     r8, aBaseEcoWdsWdsi; "base\\eco\\wds\\wdsimage\\src\\imagegro"...
0x18000675d  mov     ebx, eax
0x18000675f  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180006766  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000676d  mov     r9d, esi
0x180006770  mov     ecx, 80000h
0x180006775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677a  jmp     short loc_1800067BC
0x18000677c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006784  jz      short loc_1800067CA
0x180006786  call    cs:__imp_GetLastError
0x18000678d  nop     dword ptr [rax+rax+00h]
0x180006792  lea     r9, word_180013F66
0x180006799  mov     dword ptr [rsp+48h+var_28], edi
0x18000679d  mov     ebx, eax
0x18000679f  lea     rdx, aBaseEcoWdsWdsi; "base\\eco\\wds\\wdsimage\\src\\imagegro"...
0x1800067a6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800067ad  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800067b4  mov     r8d, esi
0x1800067b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067bc  mov     ecx, ebx; dwErrCode
0x1800067be  call    cs:__imp_SetLastError
0x1800067c5  nop     dword ptr [rax+rax+00h]
0x1800067ca  call    cs:__imp_GetLastError
0x1800067d1  nop     dword ptr [rax+rax+00h]
0x1800067d6  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800067dd  mov     ebx, eax
0x1800067df  jz      short loc_1800067E6
0x1800067e1  call    ElTraceErrorInfo
0x1800067e6  mov     ecx, ebx; dwErrCode
0x1800067e8  call    cs:__imp_SetLastError
0x1800067ef  nop     dword ptr [rax+rax+00h]
0x1800067f4  mov     rbx, [rsp+48h+arg_0]
0x1800067f9  mov     eax, edi
0x1800067fb  mov     rsi, [rsp+48h+arg_8]
0x180006800  add     rsp, 40h
0x180006804  pop     rdi
0x180006805  retn
```
