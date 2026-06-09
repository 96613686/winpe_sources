# ElValidateWin32

- ea: `0x180006dd8`
- end: `0x180006ea1`
- name: `ElValidateWin32`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1800055b0`
- `0x18000592c`
- `0x180005b10`
- `0x180005c80`
- `0x180005dac`
- `0x180005ef0`
- `0x180005f70`
- `0x180005fe8`
- `0x180006320`
- `0x180006460`
- `0x180006598`
- `0x1800068d0`
- `0x180006a60`

## callees

- `0x180006dd8`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006dfe`
- `KERNEL32!GetLastError` at `0x180006e4a`
- `KERNEL32!GetLastError` at `0x180006dfe`
- `KERNEL32!GetLastError` at `0x180006e4a`
- `KERNEL32!SetLastError` at `0x180006e82`
- `KERNEL32!SetLastError` at `0x180006e82`

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
        "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wdssimpledevicecontroller.cpp",
        a4,
        qword_18000F3C0,
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
        "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wdssimpledevicecontroller.cpp",
        a4,
        qword_18000F3C0,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180006dd8  mov     [rsp+arg_0], rbx
0x180006ddd  mov     [rsp+arg_8], rsi
0x180006de2  push    rdi
0x180006de3  sub     rsp, 40h
0x180006de7  mov     esi, r9d
0x180006dea  mov     edi, ecx
0x180006dec  test    ecx, ecx
0x180006dee  jz      loc_180006E8E
0x180006df4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006dfc  jz      short loc_180006E40
0x180006dfe  call    cs:__imp_GetLastError
0x180006e05  nop     dword ptr [rax+rax+00h]
0x180006e0a  lea     r9, qword_18000F3C0
0x180006e11  mov     [rsp+48h+var_20], edi
0x180006e15  mov     [rsp+48h+var_28], r9
0x180006e1a  lea     r8, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wd"...
0x180006e21  mov     ebx, eax
0x180006e23  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180006e2a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006e31  mov     r9d, esi
0x180006e34  mov     ecx, 80000h
0x180006e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3e  jmp     short loc_180006E80
0x180006e40  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006e48  jz      short loc_180006E8E
0x180006e4a  call    cs:__imp_GetLastError
0x180006e51  nop     dword ptr [rax+rax+00h]
0x180006e56  lea     r9, qword_18000F3C0
0x180006e5d  mov     dword ptr [rsp+48h+var_28], edi
0x180006e61  mov     ebx, eax
0x180006e63  lea     rdx, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wd"...
0x180006e6a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006e71  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180006e78  mov     r8d, esi
0x180006e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e80  mov     ecx, ebx; dwErrCode
0x180006e82  call    cs:__imp_SetLastError
0x180006e89  nop     dword ptr [rax+rax+00h]
0x180006e8e  mov     rbx, [rsp+48h+arg_0]
0x180006e93  mov     eax, edi
0x180006e95  mov     rsi, [rsp+48h+arg_8]
0x180006e9a  add     rsp, 40h
0x180006e9e  pop     rdi
0x180006e9f  retn
```
