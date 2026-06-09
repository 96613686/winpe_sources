# ElValidateWin32_3

- ea: `0x180008748`
- end: `0x180008811`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d60`
- `0x180007ec8`
- `0x180007fd4`
- `0x18000844c`

## callees

- `0x180008748`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000876e`
- `KERNEL32!GetLastError` at `0x1800087ba`
- `KERNEL32!GetLastError` at `0x18000876e`
- `KERNEL32!GetLastError` at `0x1800087ba`
- `KERNEL32!SetLastError` at `0x1800087f2`
- `KERNEL32!SetLastError` at `0x1800087f2`

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
        "base\\eco\\wds\\wdsimage\\src\\enumimages.cpp",
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
        "base\\eco\\wds\\wdsimage\\src\\enumimages.cpp",
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
0x180008748  mov     [rsp+arg_0], rbx
0x18000874d  mov     [rsp+arg_8], rsi
0x180008752  push    rdi
0x180008753  sub     rsp, 40h
0x180008757  mov     esi, r9d
0x18000875a  mov     edi, ecx
0x18000875c  test    ecx, ecx
0x18000875e  jz      loc_1800087FE
0x180008764  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000876c  jz      short loc_1800087B0
0x18000876e  call    cs:__imp_GetLastError
0x180008775  nop     dword ptr [rax+rax+00h]
0x18000877a  lea     r9, word_180013F66
0x180008781  mov     [rsp+48h+var_20], edi
0x180008785  mov     [rsp+48h+var_28], r9
0x18000878a  lea     r8, aBaseEcoWdsWdsi_6; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x180008791  mov     ebx, eax
0x180008793  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000879a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800087a1  mov     r9d, esi
0x1800087a4  mov     ecx, 80000h
0x1800087a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ae  jmp     short loc_1800087F0
0x1800087b0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800087b8  jz      short loc_1800087FE
0x1800087ba  call    cs:__imp_GetLastError
0x1800087c1  nop     dword ptr [rax+rax+00h]
0x1800087c6  lea     r9, word_180013F66
0x1800087cd  mov     dword ptr [rsp+48h+var_28], edi
0x1800087d1  mov     ebx, eax
0x1800087d3  lea     rdx, aBaseEcoWdsWdsi_6; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x1800087da  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800087e1  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800087e8  mov     r8d, esi
0x1800087eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f0  mov     ecx, ebx; dwErrCode
0x1800087f2  call    cs:__imp_SetLastError
0x1800087f9  nop     dword ptr [rax+rax+00h]
0x1800087fe  mov     rbx, [rsp+48h+arg_0]
0x180008803  mov     eax, edi
0x180008805  mov     rsi, [rsp+48h+arg_8]
0x18000880a  add     rsp, 40h
0x18000880e  pop     rdi
0x18000880f  retn
```
