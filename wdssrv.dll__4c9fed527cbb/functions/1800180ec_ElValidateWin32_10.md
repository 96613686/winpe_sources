# ElValidateWin32_10

- ea: `0x1800180ec`
- end: `0x1800181b5`
- name: `ElValidateWin32_10`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180014c24`
- `0x18001791c`
- `0x180017c5c`
- `0x180017f24`

## callees

- `0x1800180ec`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180018196`
- `KERNEL32!SetLastError` at `0x180018196`
- `KERNEL32!GetLastError` at `0x180018112`
- `KERNEL32!GetLastError` at `0x18001815e`
- `KERNEL32!GetLastError` at `0x180018112`
- `KERNEL32!GetLastError` at `0x18001815e`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_10(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\server\\src\\udpportrange.cpp",
        a4,
        &dword_18001F974,
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
        "base\\eco\\wds\\wdssrv\\server\\src\\udpportrange.cpp",
        a4,
        &dword_18001F974,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800180ec  mov     [rsp+arg_0], rbx
0x1800180f1  mov     [rsp+arg_8], rsi
0x1800180f6  push    rdi
0x1800180f7  sub     rsp, 40h
0x1800180fb  mov     esi, r9d
0x1800180fe  mov     edi, ecx
0x180018100  test    ecx, ecx
0x180018102  jz      loc_1800181A2
0x180018108  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180018110  jz      short loc_180018154
0x180018112  call    cs:__imp_GetLastError
0x180018119  nop     dword ptr [rax+rax+00h]
0x18001811e  lea     r9, dword_18001F974
0x180018125  mov     [rsp+48h+var_20], edi
0x180018129  mov     [rsp+48h+var_28], r9
0x18001812e  lea     r8, aBaseEcoWdsWdss_13; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180018135  mov     ebx, eax
0x180018137  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001813e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180018145  mov     r9d, esi
0x180018148  mov     ecx, 80000h
0x18001814d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018152  jmp     short loc_180018194
0x180018154  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001815c  jz      short loc_1800181A2
0x18001815e  call    cs:__imp_GetLastError
0x180018165  nop     dword ptr [rax+rax+00h]
0x18001816a  lea     r9, dword_18001F974
0x180018171  mov     dword ptr [rsp+48h+var_28], edi
0x180018175  mov     ebx, eax
0x180018177  lea     rdx, aBaseEcoWdsWdss_13; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x18001817e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180018185  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001818c  mov     r8d, esi
0x18001818f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018194  mov     ecx, ebx; dwErrCode
0x180018196  call    cs:__imp_SetLastError
0x18001819d  nop     dword ptr [rax+rax+00h]
0x1800181a2  mov     rbx, [rsp+48h+arg_0]
0x1800181a7  mov     eax, edi
0x1800181a9  mov     rsi, [rsp+48h+arg_8]
0x1800181ae  add     rsp, 40h
0x1800181b2  pop     rdi
0x1800181b3  retn
```
