# ElValidateHr

- ea: `0x180006cdc`
- end: `0x180006dcf`
- name: `ElValidateHr`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800055b0`
- `0x180005c80`
- `0x180005fe8`
- `0x180006210`
- `0x180006320`
- `0x180006460`
- `0x180006598`
- `0x1800068d0`

## callees

- `0x180006bf8`
- `0x180006cdc`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006d02`
- `KERNEL32!GetLastError` at `0x180006d4e`
- `KERNEL32!GetLastError` at `0x180006d92`
- `KERNEL32!GetLastError` at `0x180006d02`
- `KERNEL32!GetLastError` at `0x180006d4e`
- `KERNEL32!GetLastError` at `0x180006d92`
- `KERNEL32!SetLastError` at `0x180006d86`
- `KERNEL32!SetLastError` at `0x180006db0`
- `KERNEL32!SetLastError` at `0x180006d86`
- `KERNEL32!SetLastError` at `0x180006db0`

## pseudocode

```c
__int64 __fastcall ElValidateHr(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v7; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wdssimpledevicecontroller.cpp",
      a4,
      qword_18000F3C0,
      a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wdssimpledevicecontroller.cpp",
      a4,
      qword_18000F3C0,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v7 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180006cdc  mov     [rsp+arg_0], rbx
0x180006ce1  mov     [rsp+arg_8], rsi
0x180006ce6  push    rdi
0x180006ce7  sub     rsp, 40h
0x180006ceb  mov     esi, r9d
0x180006cee  mov     edi, ecx
0x180006cf0  test    ecx, ecx
0x180006cf2  jns     loc_180006DBC
0x180006cf8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006d00  jz      short loc_180006D44
0x180006d02  call    cs:__imp_GetLastError
0x180006d09  nop     dword ptr [rax+rax+00h]
0x180006d0e  lea     r9, qword_18000F3C0
0x180006d15  mov     [rsp+48h+var_20], edi
0x180006d19  mov     [rsp+48h+var_28], r9
0x180006d1e  lea     r8, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wd"...
0x180006d25  mov     ebx, eax
0x180006d27  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180006d2e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006d35  mov     r9d, esi
0x180006d38  mov     ecx, 80000h
0x180006d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d42  jmp     short loc_180006D84
0x180006d44  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006d4c  jz      short loc_180006D92
0x180006d4e  call    cs:__imp_GetLastError
0x180006d55  nop     dword ptr [rax+rax+00h]
0x180006d5a  lea     r9, qword_18000F3C0
0x180006d61  mov     dword ptr [rsp+48h+var_28], edi
0x180006d65  mov     ebx, eax
0x180006d67  lea     rdx, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wd"...
0x180006d6e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006d75  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180006d7c  mov     r8d, esi
0x180006d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d84  mov     ecx, ebx; dwErrCode
0x180006d86  call    cs:__imp_SetLastError
0x180006d8d  nop     dword ptr [rax+rax+00h]
0x180006d92  call    cs:__imp_GetLastError
0x180006d99  nop     dword ptr [rax+rax+00h]
0x180006d9e  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180006da5  mov     ebx, eax
0x180006da7  jz      short loc_180006DAE
0x180006da9  call    ElTraceErrorInfo
0x180006dae  mov     ecx, ebx; dwErrCode
0x180006db0  call    cs:__imp_SetLastError
0x180006db7  nop     dword ptr [rax+rax+00h]
0x180006dbc  mov     rbx, [rsp+48h+arg_0]
0x180006dc1  mov     eax, edi
0x180006dc3  mov     rsi, [rsp+48h+arg_8]
0x180006dc8  add     rsp, 40h
0x180006dcc  pop     rdi
0x180006dcd  retn
```
