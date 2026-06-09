# ElValidateWin32_7

- ea: `0x180015e4c`
- end: `0x180015f15`
- name: `ElValidateWin32_7`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157c0`
- `0x1800159fc`
- `0x180015b70`
- `0x180015c50`

## callees

- `0x180015e4c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180015ef6`
- `KERNEL32!SetLastError` at `0x180015ef6`
- `KERNEL32!GetLastError` at `0x180015e72`
- `KERNEL32!GetLastError` at `0x180015ebe`
- `KERNEL32!GetLastError` at `0x180015e72`
- `KERNEL32!GetLastError` at `0x180015ebe`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_7(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\server\\src\\regrpcendpoint.cpp",
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
        "base\\eco\\wds\\wdssrv\\server\\src\\regrpcendpoint.cpp",
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
0x180015e4c  mov     [rsp+arg_0], rbx
0x180015e51  mov     [rsp+arg_8], rsi
0x180015e56  push    rdi
0x180015e57  sub     rsp, 40h
0x180015e5b  mov     esi, r9d
0x180015e5e  mov     edi, ecx
0x180015e60  test    ecx, ecx
0x180015e62  jz      loc_180015F02
0x180015e68  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180015e70  jz      short loc_180015EB4
0x180015e72  call    cs:__imp_GetLastError
0x180015e79  nop     dword ptr [rax+rax+00h]
0x180015e7e  lea     r9, dword_18001F974
0x180015e85  mov     [rsp+48h+var_20], edi
0x180015e89  mov     [rsp+48h+var_28], r9
0x180015e8e  lea     r8, aBaseEcoWdsWdss_15; "base\\eco\\wds\\wdssrv\\server\\src\\re"...
0x180015e95  mov     ebx, eax
0x180015e97  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180015e9e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180015ea5  mov     r9d, esi
0x180015ea8  mov     ecx, 80000h
0x180015ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb2  jmp     short loc_180015EF4
0x180015eb4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180015ebc  jz      short loc_180015F02
0x180015ebe  call    cs:__imp_GetLastError
0x180015ec5  nop     dword ptr [rax+rax+00h]
0x180015eca  lea     r9, dword_18001F974
0x180015ed1  mov     dword ptr [rsp+48h+var_28], edi
0x180015ed5  mov     ebx, eax
0x180015ed7  lea     rdx, aBaseEcoWdsWdss_15; "base\\eco\\wds\\wdssrv\\server\\src\\re"...
0x180015ede  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180015ee5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180015eec  mov     r8d, esi
0x180015eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef4  mov     ecx, ebx; dwErrCode
0x180015ef6  call    cs:__imp_SetLastError
0x180015efd  nop     dword ptr [rax+rax+00h]
0x180015f02  mov     rbx, [rsp+48h+arg_0]
0x180015f07  mov     eax, edi
0x180015f09  mov     rsi, [rsp+48h+arg_8]
0x180015f0e  add     rsp, 40h
0x180015f12  pop     rdi
0x180015f13  retn
```
