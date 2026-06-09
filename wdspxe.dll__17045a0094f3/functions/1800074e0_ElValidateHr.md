# ElValidateHr

- ea: `0x1800074e0`
- end: `0x1800075d3`
- name: `ElValidateHr`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180007198`
- `0x180007cf0`
- `0x180007e70`
- `0x180007fe0`
- `0x180008450`

## callees

- `0x180007408`
- `0x1800074e0`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000758a`
- `KERNEL32!SetLastError` at `0x1800075b4`
- `KERNEL32!SetLastError` at `0x18000758a`
- `KERNEL32!SetLastError` at `0x1800075b4`
- `KERNEL32!GetLastError` at `0x180007506`
- `KERNEL32!GetLastError` at `0x180007552`
- `KERNEL32!GetLastError` at `0x180007596`
- `KERNEL32!GetLastError` at `0x180007506`
- `KERNEL32!GetLastError` at `0x180007552`
- `KERNEL32!GetLastError` at `0x180007596`

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
      "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeapi.cpp",
      a4,
      &word_1800160FE,
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
      "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeapi.cpp",
      a4,
      &word_1800160FE,
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
0x1800074e0  mov     [rsp+arg_0], rbx
0x1800074e5  mov     [rsp+arg_8], rsi
0x1800074ea  push    rdi
0x1800074eb  sub     rsp, 40h
0x1800074ef  mov     esi, r9d
0x1800074f2  mov     edi, ecx
0x1800074f4  test    ecx, ecx
0x1800074f6  jns     loc_1800075C0
0x1800074fc  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007504  jz      short loc_180007548
0x180007506  call    cs:__imp_GetLastError
0x18000750d  nop     dword ptr [rax+rax+00h]
0x180007512  lea     r9, word_1800160FE
0x180007519  mov     [rsp+48h+var_20], edi
0x18000751d  mov     [rsp+48h+var_28], r9
0x180007522  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x180007529  mov     ebx, eax
0x18000752b  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180007532  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007539  mov     r9d, esi
0x18000753c  mov     ecx, 80000h
0x180007541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007546  jmp     short loc_180007588
0x180007548  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007550  jz      short loc_180007596
0x180007552  call    cs:__imp_GetLastError
0x180007559  nop     dword ptr [rax+rax+00h]
0x18000755e  lea     r9, word_1800160FE
0x180007565  mov     dword ptr [rsp+48h+var_28], edi
0x180007569  mov     ebx, eax
0x18000756b  lea     rdx, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x180007572  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007579  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180007580  mov     r8d, esi
0x180007583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007588  mov     ecx, ebx; dwErrCode
0x18000758a  call    cs:__imp_SetLastError
0x180007591  nop     dword ptr [rax+rax+00h]
0x180007596  call    cs:__imp_GetLastError
0x18000759d  nop     dword ptr [rax+rax+00h]
0x1800075a2  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800075a9  mov     ebx, eax
0x1800075ab  jz      short loc_1800075B2
0x1800075ad  call    ElTraceErrorInfo
0x1800075b2  mov     ecx, ebx; dwErrCode
0x1800075b4  call    cs:__imp_SetLastError
0x1800075bb  nop     dword ptr [rax+rax+00h]
0x1800075c0  mov     rbx, [rsp+48h+arg_0]
0x1800075c5  mov     eax, edi
0x1800075c7  mov     rsi, [rsp+48h+arg_8]
0x1800075cc  add     rsp, 40h
0x1800075d0  pop     rdi
0x1800075d1  retn
```
