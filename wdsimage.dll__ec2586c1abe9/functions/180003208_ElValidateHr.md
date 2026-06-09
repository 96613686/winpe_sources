# ElValidateHr

- ea: `0x180003208`
- end: `0x1800032fb`
- name: `ElValidateHr`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800024f8`
- `0x180002664`
- `0x18000284c`
- `0x180002edc`
- `0x180003010`
- `0x180003680`
- `0x1800037c0`
- `0x180003880`

## callees

- `0x180003130`
- `0x180003208`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000322e`
- `KERNEL32!GetLastError` at `0x18000327a`
- `KERNEL32!GetLastError` at `0x1800032be`
- `KERNEL32!GetLastError` at `0x18000322e`
- `KERNEL32!GetLastError` at `0x18000327a`
- `KERNEL32!GetLastError` at `0x1800032be`
- `KERNEL32!SetLastError` at `0x1800032b2`
- `KERNEL32!SetLastError` at `0x1800032dc`
- `KERNEL32!SetLastError` at `0x1800032b2`
- `KERNEL32!SetLastError` at `0x1800032dc`

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
      "base\\eco\\wds\\wdsimage\\src\\wdsimage.cpp",
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
      "base\\eco\\wds\\wdsimage\\src\\wdsimage.cpp",
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
0x180003208  mov     [rsp+arg_0], rbx
0x18000320d  mov     [rsp+arg_8], rsi
0x180003212  push    rdi
0x180003213  sub     rsp, 40h
0x180003217  mov     esi, r9d
0x18000321a  mov     edi, ecx
0x18000321c  test    ecx, ecx
0x18000321e  jns     loc_1800032E8
0x180003224  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000322c  jz      short loc_180003270
0x18000322e  call    cs:__imp_GetLastError
0x180003235  nop     dword ptr [rax+rax+00h]
0x18000323a  lea     r9, word_180013F66
0x180003241  mov     [rsp+48h+var_20], edi
0x180003245  mov     [rsp+48h+var_28], r9
0x18000324a  lea     r8, aBaseEcoWdsWdsi_7; "base\\eco\\wds\\wdsimage\\src\\wdsimage"...
0x180003251  mov     ebx, eax
0x180003253  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000325a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003261  mov     r9d, esi
0x180003264  mov     ecx, 80000h
0x180003269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000326e  jmp     short loc_1800032B0
0x180003270  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003278  jz      short loc_1800032BE
0x18000327a  call    cs:__imp_GetLastError
0x180003281  nop     dword ptr [rax+rax+00h]
0x180003286  lea     r9, word_180013F66
0x18000328d  mov     dword ptr [rsp+48h+var_28], edi
0x180003291  mov     ebx, eax
0x180003293  lea     rdx, aBaseEcoWdsWdsi_7; "base\\eco\\wds\\wdsimage\\src\\wdsimage"...
0x18000329a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800032a1  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800032a8  mov     r8d, esi
0x1800032ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b0  mov     ecx, ebx; dwErrCode
0x1800032b2  call    cs:__imp_SetLastError
0x1800032b9  nop     dword ptr [rax+rax+00h]
0x1800032be  call    cs:__imp_GetLastError
0x1800032c5  nop     dword ptr [rax+rax+00h]
0x1800032ca  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800032d1  mov     ebx, eax
0x1800032d3  jz      short loc_1800032DA
0x1800032d5  call    ElTraceErrorInfo
0x1800032da  mov     ecx, ebx; dwErrCode
0x1800032dc  call    cs:__imp_SetLastError
0x1800032e3  nop     dword ptr [rax+rax+00h]
0x1800032e8  mov     rbx, [rsp+48h+arg_0]
0x1800032ed  mov     eax, edi
0x1800032ef  mov     rsi, [rsp+48h+arg_8]
0x1800032f4  add     rsp, 40h
0x1800032f8  pop     rdi
0x1800032f9  retn
```
