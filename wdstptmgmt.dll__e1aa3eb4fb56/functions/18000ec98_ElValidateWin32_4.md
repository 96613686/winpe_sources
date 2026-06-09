# ElValidateWin32_4

- ea: `0x18000ec98`
- end: `0x18000ed61`
- name: `ElValidateWin32_4`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000c790`
- `0x18000d2c0`
- `0x18000d9e8`

## callees

- `0x18000ec98`
- `0x180020010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000ed42`
- `KERNEL32!SetLastError` at `0x18000ed42`
- `KERNEL32!GetLastError` at `0x18000ecbe`
- `KERNEL32!GetLastError` at `0x18000ed0a`
- `KERNEL32!GetLastError` at `0x18000ecbe`
- `KERNEL32!GetLastError` at `0x18000ed0a`

## string_xrefs

- `0x18000ecda`: `base\eco\wds\wdstptmgmt\src\wdstransportservicepolicy.cpp`
- `0x18000ed23`: `base\eco\wds\wdstptmgmt\src\wdstransportservicepolicy.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_4(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportservicepolicy.cpp",
        a4,
        word_1800257AA,
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportservicepolicy.cpp",
        a4,
        word_1800257AA,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000ec98  mov     [rsp+arg_0], rbx
0x18000ec9d  mov     [rsp+arg_8], rsi
0x18000eca2  push    rdi
0x18000eca3  sub     rsp, 40h
0x18000eca7  mov     esi, r9d
0x18000ecaa  mov     edi, ecx
0x18000ecac  test    ecx, ecx
0x18000ecae  jz      loc_18000ED4E
0x18000ecb4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ecbc  jz      short loc_18000ED00
0x18000ecbe  call    cs:__imp_GetLastError
0x18000ecc5  nop     dword ptr [rax+rax+00h]
0x18000ecca  lea     r9, word_1800257AA
0x18000ecd1  mov     [rsp+48h+var_20], edi
0x18000ecd5  mov     [rsp+48h+var_28], r9
0x18000ecda  lea     r8, aBaseEcoWdsWdst_12; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000ece1  mov     ebx, eax
0x18000ece3  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000ecea  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ecf1  mov     r9d, esi
0x18000ecf4  mov     ecx, 80000h
0x18000ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecfe  jmp     short loc_18000ED40
0x18000ed00  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ed08  jz      short loc_18000ED4E
0x18000ed0a  call    cs:__imp_GetLastError
0x18000ed11  nop     dword ptr [rax+rax+00h]
0x18000ed16  lea     r9, word_1800257AA
0x18000ed1d  mov     dword ptr [rsp+48h+var_28], edi
0x18000ed21  mov     ebx, eax
0x18000ed23  lea     rdx, aBaseEcoWdsWdst_12; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000ed2a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ed31  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000ed38  mov     r8d, esi
0x18000ed3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed40  mov     ecx, ebx; dwErrCode
0x18000ed42  call    cs:__imp_SetLastError
0x18000ed49  nop     dword ptr [rax+rax+00h]
0x18000ed4e  mov     rbx, [rsp+48h+arg_0]
0x18000ed53  mov     eax, edi
0x18000ed55  mov     rsi, [rsp+48h+arg_8]
0x18000ed5a  add     rsp, 40h
0x18000ed5e  pop     rdi
0x18000ed5f  retn
```
