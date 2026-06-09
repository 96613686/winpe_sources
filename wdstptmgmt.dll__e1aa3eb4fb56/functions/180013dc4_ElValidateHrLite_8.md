# ElValidateHrLite_8

- ea: `0x180013dc4`
- end: `0x180013e86`
- name: `ElValidateHrLite_8`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180013cb0`

## callees

- `0x180013dc4`
- `0x180020010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013e6c`
- `KERNEL32!SetLastError` at `0x180013e6c`
- `KERNEL32!GetLastError` at `0x180013de2`
- `KERNEL32!GetLastError` at `0x180013e31`
- `KERNEL32!GetLastError` at `0x180013de2`
- `KERNEL32!GetLastError` at `0x180013e31`

## string_xrefs

- `0x180013dfe`: `base\eco\wds\wdstptmgmt\src\wdstransportnamespacescheduledcast.cpp`
- `0x180013e4a`: `base\eco\wds\wdstptmgmt\src\wdstransportnamespacescheduledcast.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite_8(int a1)
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportnamespacescheduledcast.cpp",
        140,
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportnamespacescheduledcast.cpp",
        140,
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
0x180013dc4  mov     [rsp+arg_0], rbx
0x180013dc9  push    rdi
0x180013dca  sub     rsp, 40h
0x180013dce  mov     edi, ecx
0x180013dd0  test    ecx, ecx
0x180013dd2  jns     loc_180013E78
0x180013dd8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013de0  jz      short loc_180013E27
0x180013de2  call    cs:__imp_GetLastError
0x180013de9  nop     dword ptr [rax+rax+00h]
0x180013dee  lea     r9, word_1800257AA
0x180013df5  mov     [rsp+48h+var_20], edi
0x180013df9  mov     [rsp+48h+var_28], r9
0x180013dfe  lea     r8, aBaseEcoWdsWdst_9; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x180013e05  mov     ebx, eax
0x180013e07  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180013e0e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013e15  mov     r9d, 8Ch
0x180013e1b  mov     ecx, 80000h
0x180013e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e25  jmp     short loc_180013E6A
0x180013e27  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013e2f  jz      short loc_180013E78
0x180013e31  call    cs:__imp_GetLastError
0x180013e38  nop     dword ptr [rax+rax+00h]
0x180013e3d  lea     r9, word_1800257AA
0x180013e44  mov     dword ptr [rsp+48h+var_28], edi
0x180013e48  mov     ebx, eax
0x180013e4a  lea     rdx, aBaseEcoWdsWdst_9; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x180013e51  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013e58  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180013e5f  mov     r8d, 8Ch
0x180013e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e6a  mov     ecx, ebx; dwErrCode
0x180013e6c  call    cs:__imp_SetLastError
0x180013e73  nop     dword ptr [rax+rax+00h]
0x180013e78  mov     rbx, [rsp+48h+arg_0]
0x180013e7d  mov     eax, edi
0x180013e7f  add     rsp, 40h
0x180013e83  pop     rdi
0x180013e84  retn
```
