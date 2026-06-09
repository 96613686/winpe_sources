# ElValidateWin32_4

- ea: `0x180011068`
- end: `0x180011131`
- name: `ElValidateWin32_4`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18000abe4`
- `0x18000adf8`
- `0x18000af5c`
- `0x18000b01c`
- `0x18000b7c4`
- `0x18000bdc0`
- `0x18000c494`
- `0x18000d13c`
- `0x18000e314`
- `0x18000ea3c`
- `0x18000eda0`
- `0x18000eecc`
- `0x18000f224`
- `0x18000fb80`
- `0x1800104f4`

## callees

- `0x180011068`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011112`
- `KERNEL32!SetLastError` at `0x180011112`
- `KERNEL32!GetLastError` at `0x18001108e`
- `KERNEL32!GetLastError` at `0x1800110da`
- `KERNEL32!GetLastError` at `0x18001108e`
- `KERNEL32!GetLastError` at `0x1800110da`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_4(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeroguedetection.cpp",
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
        "base\\eco\\wds\\wdssrv\\wdspxe\\src\\pxeroguedetection.cpp",
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
0x180011068  mov     [rsp+arg_0], rbx
0x18001106d  mov     [rsp+arg_8], rsi
0x180011072  push    rdi
0x180011073  sub     rsp, 40h
0x180011077  mov     esi, r9d
0x18001107a  mov     edi, ecx
0x18001107c  test    ecx, ecx
0x18001107e  jz      loc_18001111E
0x180011084  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001108c  jz      short loc_1800110D0
0x18001108e  call    cs:__imp_GetLastError
0x180011095  nop     dword ptr [rax+rax+00h]
0x18001109a  lea     r9, word_1800160FE
0x1800110a1  mov     [rsp+48h+var_20], edi
0x1800110a5  mov     [rsp+48h+var_28], r9
0x1800110aa  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x1800110b1  mov     ebx, eax
0x1800110b3  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800110ba  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800110c1  mov     r9d, esi
0x1800110c4  mov     ecx, 80000h
0x1800110c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ce  jmp     short loc_180011110
0x1800110d0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800110d8  jz      short loc_18001111E
0x1800110da  call    cs:__imp_GetLastError
0x1800110e1  nop     dword ptr [rax+rax+00h]
0x1800110e6  lea     r9, word_1800160FE
0x1800110ed  mov     dword ptr [rsp+48h+var_28], edi
0x1800110f1  mov     ebx, eax
0x1800110f3  lea     rdx, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdspxe\\src\\px"...
0x1800110fa  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011101  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180011108  mov     r8d, esi
0x18001110b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011110  mov     ecx, ebx; dwErrCode
0x180011112  call    cs:__imp_SetLastError
0x180011119  nop     dword ptr [rax+rax+00h]
0x18001111e  mov     rbx, [rsp+48h+arg_0]
0x180011123  mov     eax, edi
0x180011125  mov     rsi, [rsp+48h+arg_8]
0x18001112a  add     rsp, 40h
0x18001112e  pop     rdi
0x18001112f  retn
```
