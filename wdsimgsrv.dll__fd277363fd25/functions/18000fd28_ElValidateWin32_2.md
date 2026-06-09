# ElValidateWin32_2

- ea: `0x18000fd28`
- end: `0x18000fdf1`
- name: `ElValidateWin32_2`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x1800096e8`
- `0x18000d1b8`
- `0x18000d2ac`
- `0x18000d39c`
- `0x18000d57c`
- `0x18000d638`
- `0x18000d754`
- `0x18000d8c4`
- `0x18000d980`
- `0x18000db14`
- `0x18000dd58`
- `0x18000dda0`
- `0x18000df24`
- `0x18000df74`
- `0x18000e01c`
- `0x18000e110`
- `0x18000e330`
- `0x18000e5f8`
- `0x18000e724`
- `0x18000e86c`
- `0x18000ea1c`
- `0x18000eb10`
- `0x18000ed84`
- `0x18000f06c`
- `0x18000f4b0`
- `0x18000f5f8`
- `0x18000f6b4`
- `0x18000f784`
- `0x18000fb40`

## callees

- `0x18000fd28`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000fdd2`
- `KERNEL32!SetLastError` at `0x18000fdd2`
- `KERNEL32!GetLastError` at `0x18000fd4e`
- `KERNEL32!GetLastError` at `0x18000fd9a`
- `KERNEL32!GetLastError` at `0x18000fd4e`
- `KERNEL32!GetLastError` at `0x18000fd9a`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_2(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
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
        "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
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
0x18000fd28  mov     [rsp+arg_0], rbx
0x18000fd2d  mov     [rsp+arg_8], rsi
0x18000fd32  push    rdi
0x18000fd33  sub     rsp, 40h
0x18000fd37  mov     esi, r9d
0x18000fd3a  mov     edi, ecx
0x18000fd3c  test    ecx, ecx
0x18000fd3e  jz      loc_18000FDDE
0x18000fd44  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000fd4c  jz      short loc_18000FD90
0x18000fd4e  call    cs:__imp_GetLastError
0x18000fd55  nop     dword ptr [rax+rax+00h]
0x18000fd5a  lea     r9, dword_18001A184
0x18000fd61  mov     [rsp+48h+var_20], edi
0x18000fd65  mov     [rsp+48h+var_28], r9
0x18000fd6a  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000fd71  mov     ebx, eax
0x18000fd73  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000fd7a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000fd81  mov     r9d, esi
0x18000fd84  mov     ecx, 80000h
0x18000fd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8e  jmp     short loc_18000FDD0
0x18000fd90  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000fd98  jz      short loc_18000FDDE
0x18000fd9a  call    cs:__imp_GetLastError
0x18000fda1  nop     dword ptr [rax+rax+00h]
0x18000fda6  lea     r9, dword_18001A184
0x18000fdad  mov     dword ptr [rsp+48h+var_28], edi
0x18000fdb1  mov     ebx, eax
0x18000fdb3  lea     rdx, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000fdba  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000fdc1  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000fdc8  mov     r8d, esi
0x18000fdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd0  mov     ecx, ebx; dwErrCode
0x18000fdd2  call    cs:__imp_SetLastError
0x18000fdd9  nop     dword ptr [rax+rax+00h]
0x18000fdde  mov     rbx, [rsp+48h+arg_0]
0x18000fde3  mov     eax, edi
0x18000fde5  mov     rsi, [rsp+48h+arg_8]
0x18000fdea  add     rsp, 40h
0x18000fdee  pop     rdi
0x18000fdef  retn
```
