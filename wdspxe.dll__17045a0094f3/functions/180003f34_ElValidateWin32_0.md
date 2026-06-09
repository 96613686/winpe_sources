# ElValidateWin32_0

- ea: `0x180003f34`
- end: `0x180003ffd`
- name: `ElValidateWin32_0`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bc0`
- `0x180002f00`
- `0x180003384`
- `0x180003924`
- `0x180003b78`
- `0x180003db8`
- `0x180003eac`

## callees

- `0x180003f34`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180003fde`
- `KERNEL32!SetLastError` at `0x180003fde`
- `KERNEL32!GetLastError` at `0x180003f5a`
- `KERNEL32!GetLastError` at `0x180003fa6`
- `KERNEL32!GetLastError` at `0x180003f5a`
- `KERNEL32!GetLastError` at `0x180003fa6`

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
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeep.cpp",
        a4,
        &word_1800160FE,
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
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeep.cpp",
        a4,
        &word_1800160FE,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180003f34  mov     [rsp+arg_0], rbx
0x180003f39  mov     [rsp+arg_8], rsi
0x180003f3e  push    rdi
0x180003f3f  sub     rsp, 40h
0x180003f43  mov     esi, r9d
0x180003f46  mov     edi, ecx
0x180003f48  test    ecx, ecx
0x180003f4a  jz      loc_180003FEA
0x180003f50  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003f58  jz      short loc_180003F9C
0x180003f5a  call    cs:__imp_GetLastError
0x180003f61  nop     dword ptr [rax+rax+00h]
0x180003f66  lea     r9, word_1800160FE
0x180003f6d  mov     [rsp+48h+var_20], edi
0x180003f71  mov     [rsp+48h+var_28], r9
0x180003f76  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x180003f7d  mov     ebx, eax
0x180003f7f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180003f86  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003f8d  mov     r9d, esi
0x180003f90  mov     ecx, 80000h
0x180003f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f9a  jmp     short loc_180003FDC
0x180003f9c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003fa4  jz      short loc_180003FEA
0x180003fa6  call    cs:__imp_GetLastError
0x180003fad  nop     dword ptr [rax+rax+00h]
0x180003fb2  lea     r9, word_1800160FE
0x180003fb9  mov     dword ptr [rsp+48h+var_28], edi
0x180003fbd  mov     ebx, eax
0x180003fbf  lea     rdx, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x180003fc6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003fcd  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180003fd4  mov     r8d, esi
0x180003fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdc  mov     ecx, ebx; dwErrCode
0x180003fde  call    cs:__imp_SetLastError
0x180003fe5  nop     dword ptr [rax+rax+00h]
0x180003fea  mov     rbx, [rsp+48h+arg_0]
0x180003fef  mov     eax, edi
0x180003ff1  mov     rsi, [rsp+48h+arg_8]
0x180003ff6  add     rsp, 40h
0x180003ffa  pop     rdi
0x180003ffb  retn
```
