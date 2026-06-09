# ElValidateHrLite

- ea: `0x18000785c`
- end: `0x18000792d`
- name: `ElValidateHrLite`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077f8`
- `0x180007934`
- `0x1800086e4`

## callees

- `0x18000785c`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007892`
- `KERNEL32!GetLastError` at `0x1800078d3`
- `KERNEL32!GetLastError` at `0x180007892`
- `KERNEL32!GetLastError` at `0x1800078d3`
- `KERNEL32!SetLastError` at `0x180007903`
- `KERNEL32!SetLastError` at `0x180007903`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 < 0 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, hr=0x%x", a3, a4, a2, a1);
LABEL_6:
      SetLastError(LastError);
      return (unsigned int)a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, hr=0x%x", a3, a4, a2, a1);
      goto LABEL_6;
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000785c  mov     rax, rsp
0x18000785f  mov     [rax+8], rbx
0x180007863  mov     [rax+10h], rbp
0x180007867  mov     [rax+18h], rsi
0x18000786b  mov     [rax+20h], rdi
0x18000786f  push    r14
0x180007871  sub     rsp, 40h
0x180007875  mov     esi, r9d
0x180007878  mov     rbp, r8
0x18000787b  mov     r14, rdx
0x18000787e  mov     edi, ecx
0x180007880  test    ecx, ecx
0x180007882  jns     loc_18000790F
0x180007888  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007890  jz      short loc_1800078C9
0x180007892  call    cs:__imp_GetLastError
0x180007899  nop     dword ptr [rax+rax+00h]
0x18000789e  mov     [rsp+48h+var_20], edi
0x1800078a2  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800078a9  mov     ebx, eax
0x1800078ab  mov     [rsp+48h+var_28], r14
0x1800078b0  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800078b7  mov     r9d, esi
0x1800078ba  mov     r8, rbp
0x1800078bd  mov     ecx, 80000h
0x1800078c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c7  jmp     short loc_180007901
0x1800078c9  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800078d1  jz      short loc_18000790F
0x1800078d3  call    cs:__imp_GetLastError
0x1800078da  nop     dword ptr [rax+rax+00h]
0x1800078df  mov     r9, r14
0x1800078e2  mov     dword ptr [rsp+48h+var_28], edi
0x1800078e6  mov     ebx, eax
0x1800078e8  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800078ef  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800078f6  mov     r8d, esi
0x1800078f9  mov     rdx, rbp
0x1800078fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007901  mov     ecx, ebx; dwErrCode
0x180007903  call    cs:__imp_SetLastError
0x18000790a  nop     dword ptr [rax+rax+00h]
0x18000790f  mov     rbx, [rsp+48h+arg_0]
0x180007914  mov     eax, edi
0x180007916  mov     rdi, [rsp+48h+arg_18]
0x18000791b  mov     rbp, [rsp+48h+arg_8]
0x180007920  mov     rsi, [rsp+48h+arg_10]
0x180007925  add     rsp, 40h
0x180007929  pop     r14
0x18000792b  retn
```
