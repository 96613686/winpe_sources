# ElValidateHrLite_9

- ea: `0x180014760`
- end: `0x180014829`
- name: `ElValidateHrLite_9`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001470c`

## callees

- `0x180014760`
- `0x180020010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001480a`
- `KERNEL32!SetLastError` at `0x18001480a`
- `KERNEL32!GetLastError` at `0x180014786`
- `KERNEL32!GetLastError` at `0x1800147d2`
- `KERNEL32!GetLastError` at `0x180014786`
- `KERNEL32!GetLastError` at `0x1800147d2`

## string_xrefs

- `0x1800147a2`: `base\eco\wds\wdstptmgmt\src\wdstransportnamespacescheduledcastautostart.cpp`
- `0x1800147eb`: `base\eco\wds\wdstptmgmt\src\wdstransportnamespacescheduledcastautostart.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite_9(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportnamespacescheduledcastautostart.cpp",
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportnamespacescheduledcastautostart.cpp",
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
0x180014760  mov     [rsp+arg_0], rbx
0x180014765  mov     [rsp+arg_8], rsi
0x18001476a  push    rdi
0x18001476b  sub     rsp, 40h
0x18001476f  mov     esi, r9d
0x180014772  mov     edi, ecx
0x180014774  test    ecx, ecx
0x180014776  jns     loc_180014816
0x18001477c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014784  jz      short loc_1800147C8
0x180014786  call    cs:__imp_GetLastError
0x18001478d  nop     dword ptr [rax+rax+00h]
0x180014792  lea     r9, word_1800257AA
0x180014799  mov     [rsp+48h+var_20], edi
0x18001479d  mov     [rsp+48h+var_28], r9
0x1800147a2  lea     r8, aBaseEcoWdsWdst_19; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x1800147a9  mov     ebx, eax
0x1800147ab  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800147b2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800147b9  mov     r9d, esi
0x1800147bc  mov     ecx, 80000h
0x1800147c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147c6  jmp     short loc_180014808
0x1800147c8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800147d0  jz      short loc_180014816
0x1800147d2  call    cs:__imp_GetLastError
0x1800147d9  nop     dword ptr [rax+rax+00h]
0x1800147de  lea     r9, word_1800257AA
0x1800147e5  mov     dword ptr [rsp+48h+var_28], edi
0x1800147e9  mov     ebx, eax
0x1800147eb  lea     rdx, aBaseEcoWdsWdst_19; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x1800147f2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800147f9  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180014800  mov     r8d, esi
0x180014803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014808  mov     ecx, ebx; dwErrCode
0x18001480a  call    cs:__imp_SetLastError
0x180014811  nop     dword ptr [rax+rax+00h]
0x180014816  mov     rbx, [rsp+48h+arg_0]
0x18001481b  mov     eax, edi
0x18001481d  mov     rsi, [rsp+48h+arg_8]
0x180014822  add     rsp, 40h
0x180014826  pop     rdi
0x180014827  retn
```
