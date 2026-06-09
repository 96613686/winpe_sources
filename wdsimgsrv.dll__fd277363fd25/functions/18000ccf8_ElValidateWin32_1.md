# ElValidateWin32_1

- ea: `0x18000ccf8`
- end: `0x18000cdc1`
- name: `ElValidateWin32_1`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b034`
- `0x18000b858`
- `0x18000b9bc`
- `0x18000bee0`
- `0x18000c69c`

## callees

- `0x18000ccf8`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000cda2`
- `KERNEL32!SetLastError` at `0x18000cda2`
- `KERNEL32!GetLastError` at `0x18000cd1e`
- `KERNEL32!GetLastError` at `0x18000cd6a`
- `KERNEL32!GetLastError` at `0x18000cd1e`
- `KERNEL32!GetLastError` at `0x18000cd6a`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_1(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\utils.cpp",
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
        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\utils.cpp",
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
0x18000ccf8  mov     [rsp+arg_0], rbx
0x18000ccfd  mov     [rsp+arg_8], rsi
0x18000cd02  push    rdi
0x18000cd03  sub     rsp, 40h
0x18000cd07  mov     esi, r9d
0x18000cd0a  mov     edi, ecx
0x18000cd0c  test    ecx, ecx
0x18000cd0e  jz      loc_18000CDAE
0x18000cd14  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000cd1c  jz      short loc_18000CD60
0x18000cd1e  call    cs:__imp_GetLastError
0x18000cd25  nop     dword ptr [rax+rax+00h]
0x18000cd2a  lea     r9, dword_18001A184
0x18000cd31  mov     [rsp+48h+var_20], edi
0x18000cd35  mov     [rsp+48h+var_28], r9
0x18000cd3a  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000cd41  mov     ebx, eax
0x18000cd43  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000cd4a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000cd51  mov     r9d, esi
0x18000cd54  mov     ecx, 80000h
0x18000cd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd5e  jmp     short loc_18000CDA0
0x18000cd60  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000cd68  jz      short loc_18000CDAE
0x18000cd6a  call    cs:__imp_GetLastError
0x18000cd71  nop     dword ptr [rax+rax+00h]
0x18000cd76  lea     r9, dword_18001A184
0x18000cd7d  mov     dword ptr [rsp+48h+var_28], edi
0x18000cd81  mov     ebx, eax
0x18000cd83  lea     rdx, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000cd8a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000cd91  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000cd98  mov     r8d, esi
0x18000cd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda0  mov     ecx, ebx; dwErrCode
0x18000cda2  call    cs:__imp_SetLastError
0x18000cda9  nop     dword ptr [rax+rax+00h]
0x18000cdae  mov     rbx, [rsp+48h+arg_0]
0x18000cdb3  mov     eax, edi
0x18000cdb5  mov     rsi, [rsp+48h+arg_8]
0x18000cdba  add     rsp, 40h
0x18000cdbe  pop     rdi
0x18000cdbf  retn
```
