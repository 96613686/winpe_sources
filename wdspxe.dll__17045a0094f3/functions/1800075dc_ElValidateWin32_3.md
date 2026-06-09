# ElValidateWin32_3

- ea: `0x1800075dc`
- end: `0x1800076a5`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180007198`
- `0x1800076b0`
- `0x180007cf0`
- `0x180007e70`
- `0x180007fe0`
- `0x180008150`
- `0x180008250`
- `0x180008450`
- `0x180008570`
- `0x1800086b0`
- `0x180008a30`
- `0x180008aa0`
- `0x180008b80`
- `0x180008be0`
- `0x180008c30`
- `0x180008c90`
- `0x180008d20`
- `0x180008df0`
- `0x180008e50`
- `0x180008f00`

## callees

- `0x1800075dc`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007686`
- `KERNEL32!SetLastError` at `0x180007686`
- `KERNEL32!GetLastError` at `0x180007602`
- `KERNEL32!GetLastError` at `0x18000764e`
- `KERNEL32!GetLastError` at `0x180007602`
- `KERNEL32!GetLastError` at `0x18000764e`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_3(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeapi.cpp",
        a4,
        &word_1800160FE,
        a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeapi.cpp",
        a4,
        &word_1800160FE,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800075dc  mov     [rsp+arg_0], rbx
0x1800075e1  mov     [rsp+arg_8], rsi
0x1800075e6  push    rdi
0x1800075e7  sub     rsp, 40h
0x1800075eb  mov     esi, r9d
0x1800075ee  mov     edi, ecx
0x1800075f0  test    ecx, ecx
0x1800075f2  jz      loc_180007692
0x1800075f8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007600  jz      short loc_180007644
0x180007602  call    cs:__imp_GetLastError
0x180007609  nop     dword ptr [rax+rax+00h]
0x18000760e  lea     r9, word_1800160FE
0x180007615  mov     [rsp+48h+var_20], edi
0x180007619  mov     [rsp+48h+var_28], r9
0x18000761e  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x180007625  mov     ebx, eax
0x180007627  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000762e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007635  mov     r9d, esi
0x180007638  mov     ecx, 80000h
0x18000763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007642  jmp     short loc_180007684
0x180007644  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000764c  jz      short loc_180007692
0x18000764e  call    cs:__imp_GetLastError
0x180007655  nop     dword ptr [rax+rax+00h]
0x18000765a  lea     r9, word_1800160FE
0x180007661  mov     dword ptr [rsp+48h+var_28], edi
0x180007665  mov     ebx, eax
0x180007667  lea     rdx, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x18000766e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007675  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000767c  mov     r8d, esi
0x18000767f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007684  mov     ecx, ebx; dwErrCode
0x180007686  call    cs:__imp_SetLastError
0x18000768d  nop     dword ptr [rax+rax+00h]
0x180007692  mov     rbx, [rsp+48h+arg_0]
0x180007697  mov     eax, edi
0x180007699  mov     rsi, [rsp+48h+arg_8]
0x18000769e  add     rsp, 40h
0x1800076a2  pop     rdi
0x1800076a3  retn
```
