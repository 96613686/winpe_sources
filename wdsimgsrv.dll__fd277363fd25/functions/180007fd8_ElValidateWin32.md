# ElValidateWin32

- ea: `0x180007fd8`
- end: `0x1800080a1`
- name: `ElValidateWin32`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a0c`
- `0x180002e64`
- `0x1800036b0`
- `0x180003838`
- `0x180003af4`
- `0x180003dc4`
- `0x180006020`
- `0x180006548`
- `0x180006e50`
- `0x180007120`
- `0x180007700`
- `0x180007b18`
- `0x180007c28`

## callees

- `0x180007fd8`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008082`
- `KERNEL32!SetLastError` at `0x180008082`
- `KERNEL32!GetLastError` at `0x180007ffe`
- `KERNEL32!GetLastError` at `0x18000804a`
- `KERNEL32!GetLastError` at `0x180007ffe`
- `KERNEL32!GetLastError` at `0x18000804a`

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
        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imgsrvprovider.cpp",
        a4,
        &dword_18001A184,
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
        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imgsrvprovider.cpp",
        a4,
        &dword_18001A184,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180007fd8  mov     [rsp+arg_0], rbx
0x180007fdd  mov     [rsp+arg_8], rsi
0x180007fe2  push    rdi
0x180007fe3  sub     rsp, 40h
0x180007fe7  mov     esi, r9d
0x180007fea  mov     edi, ecx
0x180007fec  test    ecx, ecx
0x180007fee  jz      loc_18000808E
0x180007ff4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007ffc  jz      short loc_180008040
0x180007ffe  call    cs:__imp_GetLastError
0x180008005  nop     dword ptr [rax+rax+00h]
0x18000800a  lea     r9, dword_18001A184
0x180008011  mov     [rsp+48h+var_20], edi
0x180008015  mov     [rsp+48h+var_28], r9
0x18000801a  lea     r8, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008021  mov     ebx, eax
0x180008023  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000802a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180008031  mov     r9d, esi
0x180008034  mov     ecx, 80000h
0x180008039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000803e  jmp     short loc_180008080
0x180008040  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008048  jz      short loc_18000808E
0x18000804a  call    cs:__imp_GetLastError
0x180008051  nop     dword ptr [rax+rax+00h]
0x180008056  lea     r9, dword_18001A184
0x18000805d  mov     dword ptr [rsp+48h+var_28], edi
0x180008061  mov     ebx, eax
0x180008063  lea     rdx, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000806a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008071  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180008078  mov     r8d, esi
0x18000807b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008080  mov     ecx, ebx; dwErrCode
0x180008082  call    cs:__imp_SetLastError
0x180008089  nop     dword ptr [rax+rax+00h]
0x18000808e  mov     rbx, [rsp+48h+arg_0]
0x180008093  mov     eax, edi
0x180008095  mov     rsi, [rsp+48h+arg_8]
0x18000809a  add     rsp, 40h
0x18000809e  pop     rdi
0x18000809f  retn
```
