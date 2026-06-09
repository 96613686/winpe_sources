# ElValidateWin32

- ea: `0x180003d64`
- end: `0x180003e2d`
- name: `ElValidateWin32`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ff0`
- `0x180005ad0`
- `0x180006090`

## callees

- `0x180003d64`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003d8a`
- `KERNEL32!GetLastError` at `0x180003dd6`
- `KERNEL32!GetLastError` at `0x180003d8a`
- `KERNEL32!GetLastError` at `0x180003dd6`
- `KERNEL32!SetLastError` at `0x180003e0e`
- `KERNEL32!SetLastError` at `0x180003e0e`

## pseudocode

```c
__int64 __fastcall ElValidateWin32(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdsimage\\src\\imageapis.cpp",
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
        "base\\eco\\wds\\wdsimage\\src\\imageapis.cpp",
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
0x180003d64  mov     [rsp+arg_0], rbx
0x180003d69  mov     [rsp+arg_8], rsi
0x180003d6e  push    rdi
0x180003d6f  sub     rsp, 40h
0x180003d73  mov     esi, r9d
0x180003d76  mov     edi, ecx
0x180003d78  test    ecx, ecx
0x180003d7a  jz      loc_180003E1A
0x180003d80  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003d88  jz      short loc_180003DCC
0x180003d8a  call    cs:__imp_GetLastError
0x180003d91  nop     dword ptr [rax+rax+00h]
0x180003d96  lea     r9, word_180013F66
0x180003d9d  mov     [rsp+48h+var_20], edi
0x180003da1  mov     [rsp+48h+var_28], r9
0x180003da6  lea     r8, aBaseEcoWdsWdsi_1; "base\\eco\\wds\\wdsimage\\src\\imageapi"...
0x180003dad  mov     ebx, eax
0x180003daf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180003db6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003dbd  mov     r9d, esi
0x180003dc0  mov     ecx, 80000h
0x180003dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dca  jmp     short loc_180003E0C
0x180003dcc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003dd4  jz      short loc_180003E1A
0x180003dd6  call    cs:__imp_GetLastError
0x180003ddd  nop     dword ptr [rax+rax+00h]
0x180003de2  lea     r9, word_180013F66
0x180003de9  mov     dword ptr [rsp+48h+var_28], edi
0x180003ded  mov     ebx, eax
0x180003def  lea     rdx, aBaseEcoWdsWdsi_1; "base\\eco\\wds\\wdsimage\\src\\imageapi"...
0x180003df6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003dfd  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180003e04  mov     r8d, esi
0x180003e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0c  mov     ecx, ebx; dwErrCode
0x180003e0e  call    cs:__imp_SetLastError
0x180003e15  nop     dword ptr [rax+rax+00h]
0x180003e1a  mov     rbx, [rsp+48h+arg_0]
0x180003e1f  mov     eax, edi
0x180003e21  mov     rsi, [rsp+48h+arg_8]
0x180003e26  add     rsp, 40h
0x180003e2a  pop     rdi
0x180003e2b  retn
```
