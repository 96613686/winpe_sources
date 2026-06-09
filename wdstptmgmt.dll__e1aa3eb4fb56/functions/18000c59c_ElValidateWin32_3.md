# ElValidateWin32_3

- ea: `0x18000c59c`
- end: `0x18000c665`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b620`
- `0x18000b740`
- `0x18000bb50`
- `0x18000be40`
- `0x18000bf60`
- `0x18000c320`

## callees

- `0x18000c59c`
- `0x180020010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c646`
- `KERNEL32!SetLastError` at `0x18000c646`
- `KERNEL32!GetLastError` at `0x18000c5c2`
- `KERNEL32!GetLastError` at `0x18000c60e`
- `KERNEL32!GetLastError` at `0x18000c5c2`
- `KERNEL32!GetLastError` at `0x18000c60e`

## string_xrefs

- `0x18000c5de`: `base\eco\wds\wdstptmgmt\src\wdstransportconfigurationmanager.cpp`
- `0x18000c627`: `base\eco\wds\wdstptmgmt\src\wdstransportconfigurationmanager.cpp`

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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportconfigurationmanager.cpp",
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
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportconfigurationmanager.cpp",
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
0x18000c59c  mov     [rsp+arg_0], rbx
0x18000c5a1  mov     [rsp+arg_8], rsi
0x18000c5a6  push    rdi
0x18000c5a7  sub     rsp, 40h
0x18000c5ab  mov     esi, r9d
0x18000c5ae  mov     edi, ecx
0x18000c5b0  test    ecx, ecx
0x18000c5b2  jz      loc_18000C652
0x18000c5b8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c5c0  jz      short loc_18000C604
0x18000c5c2  call    cs:__imp_GetLastError
0x18000c5c9  nop     dword ptr [rax+rax+00h]
0x18000c5ce  lea     r9, word_1800257AA
0x18000c5d5  mov     [rsp+48h+var_20], edi
0x18000c5d9  mov     [rsp+48h+var_28], r9
0x18000c5de  lea     r8, aBaseEcoWdsWdst_7; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000c5e5  mov     ebx, eax
0x18000c5e7  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c5ee  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c5f5  mov     r9d, esi
0x18000c5f8  mov     ecx, 80000h
0x18000c5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c602  jmp     short loc_18000C644
0x18000c604  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c60c  jz      short loc_18000C652
0x18000c60e  call    cs:__imp_GetLastError
0x18000c615  nop     dword ptr [rax+rax+00h]
0x18000c61a  lea     r9, word_1800257AA
0x18000c621  mov     dword ptr [rsp+48h+var_28], edi
0x18000c625  mov     ebx, eax
0x18000c627  lea     rdx, aBaseEcoWdsWdst_7; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000c62e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c635  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c63c  mov     r8d, esi
0x18000c63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c644  mov     ecx, ebx; dwErrCode
0x18000c646  call    cs:__imp_SetLastError
0x18000c64d  nop     dword ptr [rax+rax+00h]
0x18000c652  mov     rbx, [rsp+48h+arg_0]
0x18000c657  mov     eax, edi
0x18000c659  mov     rsi, [rsp+48h+arg_8]
0x18000c65e  add     rsp, 40h
0x18000c662  pop     rdi
0x18000c663  retn
```
