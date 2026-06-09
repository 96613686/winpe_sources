# ElValidateWin32_2

- ea: `0x1800070c8`
- end: `0x180007191`
- name: `ElValidateWin32_2`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050e4`
- `0x18000523c`
- `0x1800054e4`
- `0x180005860`
- `0x180005aa4`
- `0x180005e44`
- `0x180006430`
- `0x1800065b4`
- `0x180006770`
- `0x180006adc`
- `0x180006d2c`
- `0x1800076b0`

## callees

- `0x1800070c8`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007172`
- `KERNEL32!SetLastError` at `0x180007172`
- `KERNEL32!GetLastError` at `0x1800070ee`
- `KERNEL32!GetLastError` at `0x18000713a`
- `KERNEL32!GetLastError` at `0x1800070ee`
- `KERNEL32!GetLastError` at `0x18000713a`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_2(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeprovhdl.cpp",
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
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeprovhdl.cpp",
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
0x1800070c8  mov     [rsp+arg_0], rbx
0x1800070cd  mov     [rsp+arg_8], rsi
0x1800070d2  push    rdi
0x1800070d3  sub     rsp, 40h
0x1800070d7  mov     esi, r9d
0x1800070da  mov     edi, ecx
0x1800070dc  test    ecx, ecx
0x1800070de  jz      loc_18000717E
0x1800070e4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800070ec  jz      short loc_180007130
0x1800070ee  call    cs:__imp_GetLastError
0x1800070f5  nop     dword ptr [rax+rax+00h]
0x1800070fa  lea     r9, word_1800160FE
0x180007101  mov     [rsp+48h+var_20], edi
0x180007105  mov     [rsp+48h+var_28], r9
0x18000710a  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x180007111  mov     ebx, eax
0x180007113  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000711a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007121  mov     r9d, esi
0x180007124  mov     ecx, 80000h
0x180007129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000712e  jmp     short loc_180007170
0x180007130  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007138  jz      short loc_18000717E
0x18000713a  call    cs:__imp_GetLastError
0x180007141  nop     dword ptr [rax+rax+00h]
0x180007146  lea     r9, word_1800160FE
0x18000714d  mov     dword ptr [rsp+48h+var_28], edi
0x180007151  mov     ebx, eax
0x180007153  lea     rdx, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x18000715a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007161  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180007168  mov     r8d, esi
0x18000716b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007170  mov     ecx, ebx; dwErrCode
0x180007172  call    cs:__imp_SetLastError
0x180007179  nop     dword ptr [rax+rax+00h]
0x18000717e  mov     rbx, [rsp+48h+arg_0]
0x180007183  mov     eax, edi
0x180007185  mov     rsi, [rsp+48h+arg_8]
0x18000718a  add     rsp, 40h
0x18000718e  pop     rdi
0x18000718f  retn
```
