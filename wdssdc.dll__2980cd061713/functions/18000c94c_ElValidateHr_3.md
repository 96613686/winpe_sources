# ElValidateHr_3

- ea: `0x18000c94c`
- end: `0x18000ca3f`
- name: `ElValidateHr_3`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c7f8`

## callees

- `0x180006bf8`
- `0x18000c94c`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c972`
- `KERNEL32!GetLastError` at `0x18000c9be`
- `KERNEL32!GetLastError` at `0x18000ca02`
- `KERNEL32!GetLastError` at `0x18000c972`
- `KERNEL32!GetLastError` at `0x18000c9be`
- `KERNEL32!GetLastError` at `0x18000ca02`
- `KERNEL32!SetLastError` at `0x18000c9f6`
- `KERNEL32!SetLastError` at `0x18000ca20`
- `KERNEL32!SetLastError` at `0x18000c9f6`
- `KERNEL32!SetLastError` at `0x18000ca20`

## string_xrefs

- `0x18000c98e`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000c9d7`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_3(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
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
      "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
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
0x18000c94c  mov     [rsp+arg_0], rbx
0x18000c951  mov     [rsp+arg_8], rsi
0x18000c956  push    rdi
0x18000c957  sub     rsp, 40h
0x18000c95b  mov     esi, r9d
0x18000c95e  mov     edi, ecx
0x18000c960  test    ecx, ecx
0x18000c962  jns     loc_18000CA2C
0x18000c968  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c970  jz      short loc_18000C9B4
0x18000c972  call    cs:__imp_GetLastError
0x18000c979  nop     dword ptr [rax+rax+00h]
0x18000c97e  lea     r9, qword_18000F3C0
0x18000c985  mov     [rsp+48h+var_20], edi
0x18000c989  mov     [rsp+48h+var_28], r9
0x18000c98e  lea     r8, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c995  mov     ebx, eax
0x18000c997  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c99e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c9a5  mov     r9d, esi
0x18000c9a8  mov     ecx, 80000h
0x18000c9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9b2  jmp     short loc_18000C9F4
0x18000c9b4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c9bc  jz      short loc_18000CA02
0x18000c9be  call    cs:__imp_GetLastError
0x18000c9c5  nop     dword ptr [rax+rax+00h]
0x18000c9ca  lea     r9, qword_18000F3C0
0x18000c9d1  mov     dword ptr [rsp+48h+var_28], edi
0x18000c9d5  mov     ebx, eax
0x18000c9d7  lea     rdx, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c9de  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c9e5  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c9ec  mov     r8d, esi
0x18000c9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f4  mov     ecx, ebx; dwErrCode
0x18000c9f6  call    cs:__imp_SetLastError
0x18000c9fd  nop     dword ptr [rax+rax+00h]
0x18000ca02  call    cs:__imp_GetLastError
0x18000ca09  nop     dword ptr [rax+rax+00h]
0x18000ca0e  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000ca15  mov     ebx, eax
0x18000ca17  jz      short loc_18000CA1E
0x18000ca19  call    ElTraceErrorInfo
0x18000ca1e  mov     ecx, ebx; dwErrCode
0x18000ca20  call    cs:__imp_SetLastError
0x18000ca27  nop     dword ptr [rax+rax+00h]
0x18000ca2c  mov     rbx, [rsp+48h+arg_0]
0x18000ca31  mov     eax, edi
0x18000ca33  mov     rsi, [rsp+48h+arg_8]
0x18000ca38  add     rsp, 40h
0x18000ca3c  pop     rdi
0x18000ca3d  retn
```
