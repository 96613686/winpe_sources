# ElValidateWin32_0

- ea: `0x180006810`
- end: `0x1800068d9`
- name: `ElValidateWin32_0`
- size: `201`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800062a0`
- `0x180006470`
- `0x180006544`
- `0x180006a20`

## callees

- `0x180006810`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006836`
- `KERNEL32!GetLastError` at `0x180006882`
- `KERNEL32!GetLastError` at `0x180006836`
- `KERNEL32!GetLastError` at `0x180006882`
- `KERNEL32!SetLastError` at `0x1800068ba`
- `KERNEL32!SetLastError` at `0x1800068ba`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_0(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdsimage\\src\\imagegroup.cpp",
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
        "base\\eco\\wds\\wdsimage\\src\\imagegroup.cpp",
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
0x180006810  mov     [rsp+arg_0], rbx
0x180006815  mov     [rsp+arg_8], rsi
0x18000681a  push    rdi
0x18000681b  sub     rsp, 40h
0x18000681f  mov     esi, r9d
0x180006822  mov     edi, ecx
0x180006824  test    ecx, ecx
0x180006826  jz      loc_1800068C6
0x18000682c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006834  jz      short loc_180006878
0x180006836  call    cs:__imp_GetLastError
0x18000683d  nop     dword ptr [rax+rax+00h]
0x180006842  lea     r9, word_180013F66
0x180006849  mov     [rsp+48h+var_20], edi
0x18000684d  mov     [rsp+48h+var_28], r9
0x180006852  lea     r8, aBaseEcoWdsWdsi; "base\\eco\\wds\\wdsimage\\src\\imagegro"...
0x180006859  mov     ebx, eax
0x18000685b  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180006862  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006869  mov     r9d, esi
0x18000686c  mov     ecx, 80000h
0x180006871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006876  jmp     short loc_1800068B8
0x180006878  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006880  jz      short loc_1800068C6
0x180006882  call    cs:__imp_GetLastError
0x180006889  nop     dword ptr [rax+rax+00h]
0x18000688e  lea     r9, word_180013F66
0x180006895  mov     dword ptr [rsp+48h+var_28], edi
0x180006899  mov     ebx, eax
0x18000689b  lea     rdx, aBaseEcoWdsWdsi; "base\\eco\\wds\\wdsimage\\src\\imagegro"...
0x1800068a2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800068a9  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800068b0  mov     r8d, esi
0x1800068b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b8  mov     ecx, ebx; dwErrCode
0x1800068ba  call    cs:__imp_SetLastError
0x1800068c1  nop     dword ptr [rax+rax+00h]
0x1800068c6  mov     rbx, [rsp+48h+arg_0]
0x1800068cb  mov     eax, edi
0x1800068cd  mov     rsi, [rsp+48h+arg_8]
0x1800068d2  add     rsp, 40h
0x1800068d6  pop     rdi
0x1800068d7  retn
```
