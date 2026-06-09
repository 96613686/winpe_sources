# ElValidateHr_5

- ea: `0x18000d5b0`
- end: `0x18000d6a8`
- name: `ElValidateHr_5`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `37`
- callee_count: `3`
- tags: ``

## callers

- `0x180003eb0`
- `0x180003f40`
- `0x1800041a0`
- `0x180005920`
- `0x180008cc0`
- `0x180008e70`
- `0x1800092fc`
- `0x1800093d8`
- `0x1800094b8`
- `0x1800096c0`
- `0x180009c30`
- `0x180009cb4`
- `0x18000a01c`
- `0x18000a13c`
- `0x18000a570`
- `0x18000a70c`
- `0x18000a814`
- `0x18000a948`
- `0x18000abe0`
- `0x18000ae64`
- `0x18000b108`
- `0x18000b17c`
- `0x18000b8b0`
- `0x18000ba2c`
- `0x18000bc58`
- `0x18000bd94`
- `0x18000bef8`
- `0x18000bfcc`
- `0x18000c148`
- `0x18000c2d8`
- `0x18000c35c`
- `0x18000c46c`
- `0x18000c77c`
- `0x18000c9f0`
- `0x18000ce00`
- `0x18000cf80`
- `0x18000d0e8`

## callees

- `0x180003130`
- `0x18000d5b0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d5de`
- `KERNEL32!GetLastError` at `0x18000d626`
- `KERNEL32!GetLastError` at `0x18000d666`
- `KERNEL32!GetLastError` at `0x18000d5de`
- `KERNEL32!GetLastError` at `0x18000d626`
- `KERNEL32!GetLastError` at `0x18000d666`
- `KERNEL32!SetLastError` at `0x18000d65a`
- `KERNEL32!SetLastError` at `0x18000d684`
- `KERNEL32!SetLastError` at `0x18000d65a`
- `KERNEL32!SetLastError` at `0x18000d684`

## pseudocode

```c
__int64 __fastcall ElValidateHr_5(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v8; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, hr=0x%x", a3, a4, &word_180013F66, a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, hr=0x%x", a3, a4, &word_180013F66, a1);
    goto LABEL_6;
  }
LABEL_7:
  v8 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v8);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000d5b0  mov     [rsp+arg_0], rbx
0x18000d5b5  mov     [rsp+arg_8], rbp
0x18000d5ba  mov     [rsp+arg_10], rsi
0x18000d5bf  push    rdi
0x18000d5c0  sub     rsp, 40h
0x18000d5c4  mov     esi, r9d
0x18000d5c7  mov     rbp, r8
0x18000d5ca  mov     edi, ecx
0x18000d5cc  test    ecx, ecx
0x18000d5ce  jns     loc_18000D690
0x18000d5d4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d5dc  jz      short loc_18000D61C
0x18000d5de  call    cs:__imp_GetLastError
0x18000d5e5  nop     dword ptr [rax+rax+00h]
0x18000d5ea  lea     r9, word_180013F66
0x18000d5f1  mov     [rsp+48h+var_20], edi
0x18000d5f5  mov     [rsp+48h+var_28], r9
0x18000d5fa  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000d601  mov     ebx, eax
0x18000d603  mov     r9d, esi
0x18000d606  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d60d  mov     r8, rbp
0x18000d610  mov     ecx, 80000h
0x18000d615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61a  jmp     short loc_18000D658
0x18000d61c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000d624  jz      short loc_18000D666
0x18000d626  call    cs:__imp_GetLastError
0x18000d62d  nop     dword ptr [rax+rax+00h]
0x18000d632  lea     r9, word_180013F66
0x18000d639  mov     dword ptr [rsp+48h+var_28], edi
0x18000d63d  mov     ebx, eax
0x18000d63f  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000d646  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000d64d  mov     r8d, esi
0x18000d650  mov     rdx, rbp
0x18000d653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d658  mov     ecx, ebx; dwErrCode
0x18000d65a  call    cs:__imp_SetLastError
0x18000d661  nop     dword ptr [rax+rax+00h]
0x18000d666  call    cs:__imp_GetLastError
0x18000d66d  nop     dword ptr [rax+rax+00h]
0x18000d672  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000d679  mov     ebx, eax
0x18000d67b  jz      short loc_18000D682
0x18000d67d  call    ElTraceErrorInfo
0x18000d682  mov     ecx, ebx; dwErrCode
0x18000d684  call    cs:__imp_SetLastError
0x18000d68b  nop     dword ptr [rax+rax+00h]
0x18000d690  mov     rbx, [rsp+48h+arg_0]
0x18000d695  mov     eax, edi
0x18000d697  mov     rbp, [rsp+48h+arg_8]
0x18000d69c  mov     rsi, [rsp+48h+arg_10]
0x18000d6a1  add     rsp, 40h
0x18000d6a5  pop     rdi
0x18000d6a6  retn
```
