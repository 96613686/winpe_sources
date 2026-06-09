# ElValidateWin32_3

- ea: `0x1800139c4`
- end: `0x180013a8d`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d380`
- `0x180011650`
- `0x180011bb0`
- `0x180011ce0`
- `0x180011ec0`
- `0x180013638`
- `0x1800137c0`
- `0x18001385c`
- `0x18001393c`

## callees

- `0x1800139c4`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013a6e`
- `KERNEL32!SetLastError` at `0x180013a6e`
- `KERNEL32!GetLastError` at `0x1800139ea`
- `KERNEL32!GetLastError` at `0x180013a36`
- `KERNEL32!GetLastError` at `0x1800139ea`
- `KERNEL32!GetLastError` at `0x180013a36`

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
        "base\\eco\\wds\\wdssrv\\server\\src\\ifhandler.cpp",
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
        "base\\eco\\wds\\wdssrv\\server\\src\\ifhandler.cpp",
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
0x1800139c4  mov     [rsp+arg_0], rbx
0x1800139c9  mov     [rsp+arg_8], rsi
0x1800139ce  push    rdi
0x1800139cf  sub     rsp, 40h
0x1800139d3  mov     esi, r9d
0x1800139d6  mov     edi, ecx
0x1800139d8  test    ecx, ecx
0x1800139da  jz      loc_180013A7A
0x1800139e0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800139e8  jz      short loc_180013A2C
0x1800139ea  call    cs:__imp_GetLastError
0x1800139f1  nop     dword ptr [rax+rax+00h]
0x1800139f6  lea     r9, dword_18001F974
0x1800139fd  mov     [rsp+48h+var_20], edi
0x180013a01  mov     [rsp+48h+var_28], r9
0x180013a06  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\server\\src\\if"...
0x180013a0d  mov     ebx, eax
0x180013a0f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013a16  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013a1d  mov     r9d, esi
0x180013a20  mov     ecx, 80000h
0x180013a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a2a  jmp     short loc_180013A6C
0x180013a2c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013a34  jz      short loc_180013A7A
0x180013a36  call    cs:__imp_GetLastError
0x180013a3d  nop     dword ptr [rax+rax+00h]
0x180013a42  lea     r9, dword_18001F974
0x180013a49  mov     dword ptr [rsp+48h+var_28], edi
0x180013a4d  mov     ebx, eax
0x180013a4f  lea     rdx, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\server\\src\\if"...
0x180013a56  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013a5d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013a64  mov     r8d, esi
0x180013a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a6c  mov     ecx, ebx; dwErrCode
0x180013a6e  call    cs:__imp_SetLastError
0x180013a75  nop     dword ptr [rax+rax+00h]
0x180013a7a  mov     rbx, [rsp+48h+arg_0]
0x180013a7f  mov     eax, edi
0x180013a81  mov     rsi, [rsp+48h+arg_8]
0x180013a86  add     rsp, 40h
0x180013a8a  pop     rdi
0x180013a8b  retn
```
