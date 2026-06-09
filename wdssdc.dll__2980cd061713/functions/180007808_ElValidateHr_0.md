# ElValidateHr_0

- ea: `0x180007808`
- end: `0x1800078fb`
- name: `ElValidateHr_0`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006f84`
- `0x1800070d0`
- `0x180007214`
- `0x1800075e0`
- `0x180007710`
- `0x180007790`

## callees

- `0x180006bf8`
- `0x180007808`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000782e`
- `KERNEL32!GetLastError` at `0x18000787a`
- `KERNEL32!GetLastError` at `0x1800078be`
- `KERNEL32!GetLastError` at `0x18000782e`
- `KERNEL32!GetLastError` at `0x18000787a`
- `KERNEL32!GetLastError` at `0x1800078be`
- `KERNEL32!SetLastError` at `0x1800078b2`
- `KERNEL32!SetLastError` at `0x1800078dc`
- `KERNEL32!SetLastError` at `0x1800078b2`
- `KERNEL32!SetLastError` at `0x1800078dc`

## pseudocode

```c
__int64 __fastcall ElValidateHr_0(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wdssimpledevicequeryresult.cpp",
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
      "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wdssimpledevicequeryresult.cpp",
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
0x180007808  mov     [rsp+arg_0], rbx
0x18000780d  mov     [rsp+arg_8], rsi
0x180007812  push    rdi
0x180007813  sub     rsp, 40h
0x180007817  mov     esi, r9d
0x18000781a  mov     edi, ecx
0x18000781c  test    ecx, ecx
0x18000781e  jns     loc_1800078E8
0x180007824  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000782c  jz      short loc_180007870
0x18000782e  call    cs:__imp_GetLastError
0x180007835  nop     dword ptr [rax+rax+00h]
0x18000783a  lea     r9, qword_18000F3C0
0x180007841  mov     [rsp+48h+var_20], edi
0x180007845  mov     [rsp+48h+var_28], r9
0x18000784a  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wd"...
0x180007851  mov     ebx, eax
0x180007853  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000785a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007861  mov     r9d, esi
0x180007864  mov     ecx, 80000h
0x180007869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000786e  jmp     short loc_1800078B0
0x180007870  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007878  jz      short loc_1800078BE
0x18000787a  call    cs:__imp_GetLastError
0x180007881  nop     dword ptr [rax+rax+00h]
0x180007886  lea     r9, qword_18000F3C0
0x18000788d  mov     dword ptr [rsp+48h+var_28], edi
0x180007891  mov     ebx, eax
0x180007893  lea     rdx, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdssdc\\src\\wd"...
0x18000789a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800078a1  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800078a8  mov     r8d, esi
0x1800078ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b0  mov     ecx, ebx; dwErrCode
0x1800078b2  call    cs:__imp_SetLastError
0x1800078b9  nop     dword ptr [rax+rax+00h]
0x1800078be  call    cs:__imp_GetLastError
0x1800078c5  nop     dword ptr [rax+rax+00h]
0x1800078ca  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800078d1  mov     ebx, eax
0x1800078d3  jz      short loc_1800078DA
0x1800078d5  call    ElTraceErrorInfo
0x1800078da  mov     ecx, ebx; dwErrCode
0x1800078dc  call    cs:__imp_SetLastError
0x1800078e3  nop     dword ptr [rax+rax+00h]
0x1800078e8  mov     rbx, [rsp+48h+arg_0]
0x1800078ed  mov     eax, edi
0x1800078ef  mov     rsi, [rsp+48h+arg_8]
0x1800078f4  add     rsp, 40h
0x1800078f8  pop     rdi
0x1800078f9  retn
```
