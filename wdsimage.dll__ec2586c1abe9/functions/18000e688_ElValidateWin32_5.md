# ElValidateWin32_5

- ea: `0x18000e688`
- end: `0x18000e751`
- name: `ElValidateWin32_5`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180008e70`
- `0x1800096c0`
- `0x18000bc58`
- `0x18000e39c`
- `0x18000e480`
- `0x18000e4e4`
- `0x18000e5f0`

## callees

- `0x18000e688`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e6ae`
- `KERNEL32!GetLastError` at `0x18000e6fa`
- `KERNEL32!GetLastError` at `0x18000e6ae`
- `KERNEL32!GetLastError` at `0x18000e6fa`
- `KERNEL32!SetLastError` at `0x18000e732`
- `KERNEL32!SetLastError` at `0x18000e732`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_5(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdslib\\wim\\wdswimfile.cpp",
        a4,
        &word_180013F66,
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
        "base\\eco\\wds\\wdslib\\wim\\wdswimfile.cpp",
        a4,
        &word_180013F66,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000e688  mov     [rsp+arg_0], rbx
0x18000e68d  mov     [rsp+arg_8], rsi
0x18000e692  push    rdi
0x18000e693  sub     rsp, 40h
0x18000e697  mov     esi, r9d
0x18000e69a  mov     edi, ecx
0x18000e69c  test    ecx, ecx
0x18000e69e  jz      loc_18000E73E
0x18000e6a4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000e6ac  jz      short loc_18000E6F0
0x18000e6ae  call    cs:__imp_GetLastError
0x18000e6b5  nop     dword ptr [rax+rax+00h]
0x18000e6ba  lea     r9, word_180013F66
0x18000e6c1  mov     [rsp+48h+var_20], edi
0x18000e6c5  mov     [rsp+48h+var_28], r9
0x18000e6ca  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\wim\\wdswimfile"...
0x18000e6d1  mov     ebx, eax
0x18000e6d3  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000e6da  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000e6e1  mov     r9d, esi
0x18000e6e4  mov     ecx, 80000h
0x18000e6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ee  jmp     short loc_18000E730
0x18000e6f0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000e6f8  jz      short loc_18000E73E
0x18000e6fa  call    cs:__imp_GetLastError
0x18000e701  nop     dword ptr [rax+rax+00h]
0x18000e706  lea     r9, word_180013F66
0x18000e70d  mov     dword ptr [rsp+48h+var_28], edi
0x18000e711  mov     ebx, eax
0x18000e713  lea     rdx, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\wim\\wdswimfile"...
0x18000e71a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000e721  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000e728  mov     r8d, esi
0x18000e72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e730  mov     ecx, ebx; dwErrCode
0x18000e732  call    cs:__imp_SetLastError
0x18000e739  nop     dword ptr [rax+rax+00h]
0x18000e73e  mov     rbx, [rsp+48h+arg_0]
0x18000e743  mov     eax, edi
0x18000e745  mov     rsi, [rsp+48h+arg_8]
0x18000e74a  add     rsp, 40h
0x18000e74e  pop     rdi
0x18000e74f  retn
```
