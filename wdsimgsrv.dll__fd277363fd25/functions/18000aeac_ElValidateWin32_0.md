# ElValidateWin32_0

- ea: `0x18000aeac`
- end: `0x18000af7a`
- name: `ElValidateWin32_0`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800081d0`
- `0x180008364`
- `0x180008494`
- `0x18000891c`
- `0x180008de8`
- `0x180008f9c`
- `0x1800092ec`
- `0x180009490`
- `0x1800096e8`
- `0x18000a944`
- `0x18000abac`
- `0x18000ace0`
- `0x18000ad60`
- `0x18000af80`
- `0x18000c69c`
- `0x180011160`
- `0x1800111a0`

## callees

- `0x18000aeac`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000af56`
- `KERNEL32!SetLastError` at `0x18000af56`
- `KERNEL32!GetLastError` at `0x18000aeda`
- `KERNEL32!GetLastError` at `0x18000af22`
- `KERNEL32!GetLastError` at `0x18000aeda`
- `KERNEL32!GetLastError` at `0x18000af22`

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
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &dword_18001A184, a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &dword_18001A184, a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000aeac  mov     [rsp+arg_0], rbx
0x18000aeb1  mov     [rsp+arg_8], rbp
0x18000aeb6  mov     [rsp+arg_10], rsi
0x18000aebb  push    rdi
0x18000aebc  sub     rsp, 40h
0x18000aec0  mov     esi, r9d
0x18000aec3  mov     rbp, r8
0x18000aec6  mov     edi, ecx
0x18000aec8  test    ecx, ecx
0x18000aeca  jz      loc_18000AF62
0x18000aed0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000aed8  jz      short loc_18000AF18
0x18000aeda  call    cs:__imp_GetLastError
0x18000aee1  nop     dword ptr [rax+rax+00h]
0x18000aee6  lea     r9, dword_18001A184
0x18000aeed  mov     [rsp+48h+var_20], edi
0x18000aef1  mov     [rsp+48h+var_28], r9
0x18000aef6  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000aefd  mov     ebx, eax
0x18000aeff  mov     r9d, esi
0x18000af02  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000af09  mov     r8, rbp
0x18000af0c  mov     ecx, 80000h
0x18000af11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af16  jmp     short loc_18000AF54
0x18000af18  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000af20  jz      short loc_18000AF62
0x18000af22  call    cs:__imp_GetLastError
0x18000af29  nop     dword ptr [rax+rax+00h]
0x18000af2e  lea     r9, dword_18001A184
0x18000af35  mov     dword ptr [rsp+48h+var_28], edi
0x18000af39  mov     ebx, eax
0x18000af3b  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000af42  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000af49  mov     r8d, esi
0x18000af4c  mov     rdx, rbp
0x18000af4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af54  mov     ecx, ebx; dwErrCode
0x18000af56  call    cs:__imp_SetLastError
0x18000af5d  nop     dword ptr [rax+rax+00h]
0x18000af62  mov     rbx, [rsp+48h+arg_0]
0x18000af67  mov     eax, edi
0x18000af69  mov     rbp, [rsp+48h+arg_8]
0x18000af6e  mov     rsi, [rsp+48h+arg_10]
0x18000af73  add     rsp, 40h
0x18000af77  pop     rdi
0x18000af78  retn
```
