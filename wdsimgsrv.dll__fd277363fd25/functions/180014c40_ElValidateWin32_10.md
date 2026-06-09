# ElValidateWin32_10

- ea: `0x180014c40`
- end: `0x180014d09`
- name: `ElValidateWin32_10`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013ed0`
- `0x180014050`
- `0x1800141b0`
- `0x1800142e0`
- `0x180014494`
- `0x180014590`
- `0x180014740`
- `0x180014990`
- `0x180014b30`

## callees

- `0x180014c40`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180014cea`
- `KERNEL32!SetLastError` at `0x180014cea`
- `KERNEL32!GetLastError` at `0x180014c66`
- `KERNEL32!GetLastError` at `0x180014cb2`
- `KERNEL32!GetLastError` at `0x180014c66`
- `KERNEL32!GetLastError` at `0x180014cb2`

## string_xrefs

- `0x180014c82`: `base\eco\wds\lib\metadata\com\wdsinprocdevicecontrollerclient.cpp`
- `0x180014ccb`: `base\eco\wds\lib\metadata\com\wdsinprocdevicecontrollerclient.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_10(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsinprocdevicecontrollerclient.cpp",
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsinprocdevicecontrollerclient.cpp",
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
0x180014c40  mov     [rsp+arg_0], rbx
0x180014c45  mov     [rsp+arg_8], rsi
0x180014c4a  push    rdi
0x180014c4b  sub     rsp, 40h
0x180014c4f  mov     esi, r9d
0x180014c52  mov     edi, ecx
0x180014c54  test    ecx, ecx
0x180014c56  jz      loc_180014CF6
0x180014c5c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014c64  jz      short loc_180014CA8
0x180014c66  call    cs:__imp_GetLastError
0x180014c6d  nop     dword ptr [rax+rax+00h]
0x180014c72  lea     r9, dword_18001A184
0x180014c79  mov     [rsp+48h+var_20], edi
0x180014c7d  mov     [rsp+48h+var_28], r9
0x180014c82  lea     r8, aBaseEcoWdsLibM_3; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180014c89  mov     ebx, eax
0x180014c8b  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180014c92  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014c99  mov     r9d, esi
0x180014c9c  mov     ecx, 80000h
0x180014ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca6  jmp     short loc_180014CE8
0x180014ca8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014cb0  jz      short loc_180014CF6
0x180014cb2  call    cs:__imp_GetLastError
0x180014cb9  nop     dword ptr [rax+rax+00h]
0x180014cbe  lea     r9, dword_18001A184
0x180014cc5  mov     dword ptr [rsp+48h+var_28], edi
0x180014cc9  mov     ebx, eax
0x180014ccb  lea     rdx, aBaseEcoWdsLibM_3; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180014cd2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014cd9  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180014ce0  mov     r8d, esi
0x180014ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ce8  mov     ecx, ebx; dwErrCode
0x180014cea  call    cs:__imp_SetLastError
0x180014cf1  nop     dword ptr [rax+rax+00h]
0x180014cf6  mov     rbx, [rsp+48h+arg_0]
0x180014cfb  mov     eax, edi
0x180014cfd  mov     rsi, [rsp+48h+arg_8]
0x180014d02  add     rsp, 40h
0x180014d06  pop     rdi
0x180014d07  retn
```
