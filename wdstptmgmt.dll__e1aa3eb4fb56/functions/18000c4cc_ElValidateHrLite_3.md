# ElValidateHrLite_3

- ea: `0x18000c4cc`
- end: `0x18000c595`
- name: `ElValidateHrLite_3`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c478`

## callees

- `0x18000c4cc`
- `0x180020010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c576`
- `KERNEL32!SetLastError` at `0x18000c576`
- `KERNEL32!GetLastError` at `0x18000c4f2`
- `KERNEL32!GetLastError` at `0x18000c53e`
- `KERNEL32!GetLastError` at `0x18000c4f2`
- `KERNEL32!GetLastError` at `0x18000c53e`

## string_xrefs

- `0x18000c50e`: `base\eco\wds\wdstptmgmt\src\wdstransportconfigurationmanager.cpp`
- `0x18000c557`: `base\eco\wds\wdstptmgmt\src\wdstransportconfigurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite_3(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 < 0 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportconfigurationmanager.cpp",
        a4,
        word_1800257AA,
        a1);
LABEL_6:
      SetLastError(LastError);
      return (unsigned int)a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportconfigurationmanager.cpp",
        a4,
        word_1800257AA,
        a1);
      goto LABEL_6;
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000c4cc  mov     [rsp+arg_0], rbx
0x18000c4d1  mov     [rsp+arg_8], rsi
0x18000c4d6  push    rdi
0x18000c4d7  sub     rsp, 40h
0x18000c4db  mov     esi, r9d
0x18000c4de  mov     edi, ecx
0x18000c4e0  test    ecx, ecx
0x18000c4e2  jns     loc_18000C582
0x18000c4e8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c4f0  jz      short loc_18000C534
0x18000c4f2  call    cs:__imp_GetLastError
0x18000c4f9  nop     dword ptr [rax+rax+00h]
0x18000c4fe  lea     r9, word_1800257AA
0x18000c505  mov     [rsp+48h+var_20], edi
0x18000c509  mov     [rsp+48h+var_28], r9
0x18000c50e  lea     r8, aBaseEcoWdsWdst_7; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000c515  mov     ebx, eax
0x18000c517  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c51e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c525  mov     r9d, esi
0x18000c528  mov     ecx, 80000h
0x18000c52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c532  jmp     short loc_18000C574
0x18000c534  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c53c  jz      short loc_18000C582
0x18000c53e  call    cs:__imp_GetLastError
0x18000c545  nop     dword ptr [rax+rax+00h]
0x18000c54a  lea     r9, word_1800257AA
0x18000c551  mov     dword ptr [rsp+48h+var_28], edi
0x18000c555  mov     ebx, eax
0x18000c557  lea     rdx, aBaseEcoWdsWdst_7; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000c55e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c565  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c56c  mov     r8d, esi
0x18000c56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c574  mov     ecx, ebx; dwErrCode
0x18000c576  call    cs:__imp_SetLastError
0x18000c57d  nop     dword ptr [rax+rax+00h]
0x18000c582  mov     rbx, [rsp+48h+arg_0]
0x18000c587  mov     eax, edi
0x18000c589  mov     rsi, [rsp+48h+arg_8]
0x18000c58e  add     rsp, 40h
0x18000c592  pop     rdi
0x18000c593  retn
```
