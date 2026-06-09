# ElValidateHrLite(long,char const *,char const *,ulong)

- ea: `0x180025914`
- end: `0x1800259d1`
- name: `?ElValidateHrLite@@YAJJPEBD0K@Z`
- size: `189`
- prototype: `__int64 __fastcall(int, const char *, const char *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800206e0`
- `0x180022f20`
- `0x1800244bc`
- `0x1800245a4`
- `0x180025450`

## callees

- `0x180025914`
- `0x180026d70`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800259b4`
- `KERNEL32!SetLastError` at `0x1800259b4`
- `KERNEL32!GetLastError` at `0x180025942`
- `KERNEL32!GetLastError` at `0x180025985`
- `KERNEL32!GetLastError` at `0x180025942`
- `KERNEL32!GetLastError` at `0x180025985`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite(int a1, const char *a2, const char *a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 < 0 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, hr=0x%x", a3, a4, word_180029FDA, a1);
LABEL_6:
      SetLastError(LastError);
      return (unsigned int)a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, hr=0x%x", a3, a4, word_180029FDA, a1);
      goto LABEL_6;
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180025914  mov     [rsp+arg_0], rbx
0x180025919  mov     [rsp+arg_8], rbp
0x18002591e  mov     [rsp+arg_10], rsi
0x180025923  push    rdi
0x180025924  sub     rsp, 40h
0x180025928  mov     esi, r9d
0x18002592b  mov     rbp, r8
0x18002592e  mov     edi, ecx
0x180025930  test    ecx, ecx
0x180025932  jns     loc_1800259BA
0x180025938  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025940  jz      short loc_18002597B
0x180025942  call    cs:__imp_GetLastError
0x180025948  lea     r9, word_180029FDA
0x18002594f  mov     [rsp+48h+var_20], edi
0x180025953  mov     [rsp+48h+var_28], r9
0x180025958  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002595f  mov     ebx, eax
0x180025961  mov     r9d, esi
0x180025964  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002596b  mov     r8, rbp
0x18002596e  mov     ecx, 80000h
0x180025973  call    cs:__guard_dispatch_icall_fptr
0x180025979  jmp     short loc_1800259B2
0x18002597b  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025983  jz      short loc_1800259BA
0x180025985  call    cs:__imp_GetLastError
0x18002598b  lea     r9, word_180029FDA
0x180025992  mov     dword ptr [rsp+48h+var_28], edi
0x180025996  mov     ebx, eax
0x180025998  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002599f  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800259a6  mov     r8d, esi
0x1800259a9  mov     rdx, rbp
0x1800259ac  call    cs:__guard_dispatch_icall_fptr
0x1800259b2  mov     ecx, ebx; dwErrCode
0x1800259b4  call    cs:__imp_SetLastError
0x1800259ba  mov     rbx, [rsp+48h+arg_0]
0x1800259bf  mov     eax, edi
0x1800259c1  mov     rbp, [rsp+48h+arg_8]
0x1800259c6  mov     rsi, [rsp+48h+arg_10]
0x1800259cb  add     rsp, 40h
0x1800259cf  pop     rdi
0x1800259d0  retn
```
