# ElValidateWin32_9

- ea: `0x18001784c`
- end: `0x180017915`
- name: `ElValidateWin32_9`
- size: `201`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800174b8`
- `0x1800175ec`
- `0x180018cdc`
- `0x18001a474`

## callees

- `0x18001784c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800178f6`
- `KERNEL32!SetLastError` at `0x1800178f6`
- `KERNEL32!GetLastError` at `0x180017872`
- `KERNEL32!GetLastError` at `0x1800178be`
- `KERNEL32!GetLastError` at `0x180017872`
- `KERNEL32!GetLastError` at `0x1800178be`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_9(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\server\\src\\multicasthandler.cpp",
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
        "base\\eco\\wds\\wdssrv\\server\\src\\multicasthandler.cpp",
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
0x18001784c  mov     [rsp+arg_0], rbx
0x180017851  mov     [rsp+arg_8], rsi
0x180017856  push    rdi
0x180017857  sub     rsp, 40h
0x18001785b  mov     esi, r9d
0x18001785e  mov     edi, ecx
0x180017860  test    ecx, ecx
0x180017862  jz      loc_180017902
0x180017868  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180017870  jz      short loc_1800178B4
0x180017872  call    cs:__imp_GetLastError
0x180017879  nop     dword ptr [rax+rax+00h]
0x18001787e  lea     r9, dword_18001F974
0x180017885  mov     [rsp+48h+var_20], edi
0x180017889  mov     [rsp+48h+var_28], r9
0x18001788e  lea     r8, aBaseEcoWdsWdss_18; "base\\eco\\wds\\wdssrv\\server\\src\\mu"...
0x180017895  mov     ebx, eax
0x180017897  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001789e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800178a5  mov     r9d, esi
0x1800178a8  mov     ecx, 80000h
0x1800178ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178b2  jmp     short loc_1800178F4
0x1800178b4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800178bc  jz      short loc_180017902
0x1800178be  call    cs:__imp_GetLastError
0x1800178c5  nop     dword ptr [rax+rax+00h]
0x1800178ca  lea     r9, dword_18001F974
0x1800178d1  mov     dword ptr [rsp+48h+var_28], edi
0x1800178d5  mov     ebx, eax
0x1800178d7  lea     rdx, aBaseEcoWdsWdss_18; "base\\eco\\wds\\wdssrv\\server\\src\\mu"...
0x1800178de  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800178e5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800178ec  mov     r8d, esi
0x1800178ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178f4  mov     ecx, ebx; dwErrCode
0x1800178f6  call    cs:__imp_SetLastError
0x1800178fd  nop     dword ptr [rax+rax+00h]
0x180017902  mov     rbx, [rsp+48h+arg_0]
0x180017907  mov     eax, edi
0x180017909  mov     rsi, [rsp+48h+arg_8]
0x18001790e  add     rsp, 40h
0x180017912  pop     rdi
0x180017913  retn
```
