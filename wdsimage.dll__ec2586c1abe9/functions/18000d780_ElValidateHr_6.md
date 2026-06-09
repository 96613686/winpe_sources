# ElValidateHr_6

- ea: `0x18000d780`
- end: `0x18000d873`
- name: `ElValidateHr_6`
- size: `243`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d950`
- `0x18000da10`
- `0x18000db50`
- `0x18000dbd0`

## callees

- `0x180003130`
- `0x18000d780`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d7a6`
- `KERNEL32!GetLastError` at `0x18000d7f2`
- `KERNEL32!GetLastError` at `0x18000d836`
- `KERNEL32!GetLastError` at `0x18000d7a6`
- `KERNEL32!GetLastError` at `0x18000d7f2`
- `KERNEL32!GetLastError` at `0x18000d836`
- `KERNEL32!SetLastError` at `0x18000d82a`
- `KERNEL32!SetLastError` at `0x18000d854`
- `KERNEL32!SetLastError` at `0x18000d82a`
- `KERNEL32!SetLastError` at `0x18000d854`

## pseudocode

```c
__int64 __fastcall ElValidateHr_6(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "base\\eco\\wds\\wdsimage\\src\\imagestore.cpp",
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
      "base\\eco\\wds\\wdsimage\\src\\imagestore.cpp",
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
0x18000d780  mov     [rsp+arg_0], rbx
0x18000d785  mov     [rsp+arg_8], rsi
0x18000d78a  push    rdi
0x18000d78b  sub     rsp, 40h
0x18000d78f  mov     esi, r9d
0x18000d792  mov     edi, ecx
0x18000d794  test    ecx, ecx
0x18000d796  jns     loc_18000D860
0x18000d79c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d7a4  jz      short loc_18000D7E8
0x18000d7a6  call    cs:__imp_GetLastError
0x18000d7ad  nop     dword ptr [rax+rax+00h]
0x18000d7b2  lea     r9, word_180013F66
0x18000d7b9  mov     [rsp+48h+var_20], edi
0x18000d7bd  mov     [rsp+48h+var_28], r9
0x18000d7c2  lea     r8, aBaseEcoWdsWdsi_2; "base\\eco\\wds\\wdsimage\\src\\imagesto"...
0x18000d7c9  mov     ebx, eax
0x18000d7cb  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000d7d2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d7d9  mov     r9d, esi
0x18000d7dc  mov     ecx, 80000h
0x18000d7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e6  jmp     short loc_18000D828
0x18000d7e8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000d7f0  jz      short loc_18000D836
0x18000d7f2  call    cs:__imp_GetLastError
0x18000d7f9  nop     dword ptr [rax+rax+00h]
0x18000d7fe  lea     r9, word_180013F66
0x18000d805  mov     dword ptr [rsp+48h+var_28], edi
0x18000d809  mov     ebx, eax
0x18000d80b  lea     rdx, aBaseEcoWdsWdsi_2; "base\\eco\\wds\\wdsimage\\src\\imagesto"...
0x18000d812  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000d819  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000d820  mov     r8d, esi
0x18000d823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d828  mov     ecx, ebx; dwErrCode
0x18000d82a  call    cs:__imp_SetLastError
0x18000d831  nop     dword ptr [rax+rax+00h]
0x18000d836  call    cs:__imp_GetLastError
0x18000d83d  nop     dword ptr [rax+rax+00h]
0x18000d842  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000d849  mov     ebx, eax
0x18000d84b  jz      short loc_18000D852
0x18000d84d  call    ElTraceErrorInfo
0x18000d852  mov     ecx, ebx; dwErrCode
0x18000d854  call    cs:__imp_SetLastError
0x18000d85b  nop     dword ptr [rax+rax+00h]
0x18000d860  mov     rbx, [rsp+48h+arg_0]
0x18000d865  mov     eax, edi
0x18000d867  mov     rsi, [rsp+48h+arg_8]
0x18000d86c  add     rsp, 40h
0x18000d870  pop     rdi
0x18000d871  retn
```
