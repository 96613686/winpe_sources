# ElValidateHr

- ea: `0x18001ae58`
- end: `0x18001af4b`
- name: `ElValidateHr`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d380`
- `0x18001a63c`
- `0x18001a910`
- `0x18001ac90`
- `0x18001ad9c`

## callees

- `0x180006184`
- `0x18001ae58`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001af02`
- `KERNEL32!SetLastError` at `0x18001af2c`
- `KERNEL32!SetLastError` at `0x18001af02`
- `KERNEL32!SetLastError` at `0x18001af2c`
- `KERNEL32!GetLastError` at `0x18001ae7e`
- `KERNEL32!GetLastError` at `0x18001aeca`
- `KERNEL32!GetLastError` at `0x18001af0e`
- `KERNEL32!GetLastError` at `0x18001ae7e`
- `KERNEL32!GetLastError` at `0x18001aeca`
- `KERNEL32!GetLastError` at `0x18001af0e`

## string_xrefs

- `0x18001ae9a`: `base\eco\wds\wdssrv\server\src\wdsvsswriter.cpp`
- `0x18001aee3`: `base\eco\wds\wdssrv\server\src\wdsvsswriter.cpp`

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
      "base\\eco\\wds\\wdssrv\\server\\src\\wdsvsswriter.cpp",
      a4,
      &dword_18001F974,
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
      "base\\eco\\wds\\wdssrv\\server\\src\\wdsvsswriter.cpp",
      a4,
      &dword_18001F974,
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
0x18001ae58  mov     [rsp+arg_0], rbx
0x18001ae5d  mov     [rsp+arg_8], rsi
0x18001ae62  push    rdi
0x18001ae63  sub     rsp, 40h
0x18001ae67  mov     esi, r9d
0x18001ae6a  mov     edi, ecx
0x18001ae6c  test    ecx, ecx
0x18001ae6e  jns     loc_18001AF38
0x18001ae74  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001ae7c  jz      short loc_18001AEC0
0x18001ae7e  call    cs:__imp_GetLastError
0x18001ae85  nop     dword ptr [rax+rax+00h]
0x18001ae8a  lea     r9, dword_18001F974
0x18001ae91  mov     [rsp+48h+var_20], edi
0x18001ae95  mov     [rsp+48h+var_28], r9
0x18001ae9a  lea     r8, aBaseEcoWdsWdss_19; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18001aea1  mov     ebx, eax
0x18001aea3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001aeaa  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001aeb1  mov     r9d, esi
0x18001aeb4  mov     ecx, 80000h
0x18001aeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aebe  jmp     short loc_18001AF00
0x18001aec0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001aec8  jz      short loc_18001AF0E
0x18001aeca  call    cs:__imp_GetLastError
0x18001aed1  nop     dword ptr [rax+rax+00h]
0x18001aed6  lea     r9, dword_18001F974
0x18001aedd  mov     dword ptr [rsp+48h+var_28], edi
0x18001aee1  mov     ebx, eax
0x18001aee3  lea     rdx, aBaseEcoWdsWdss_19; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18001aeea  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001aef1  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001aef8  mov     r8d, esi
0x18001aefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af00  mov     ecx, ebx; dwErrCode
0x18001af02  call    cs:__imp_SetLastError
0x18001af09  nop     dword ptr [rax+rax+00h]
0x18001af0e  call    cs:__imp_GetLastError
0x18001af15  nop     dword ptr [rax+rax+00h]
0x18001af1a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18001af21  mov     ebx, eax
0x18001af23  jz      short loc_18001AF2A
0x18001af25  call    ElTraceErrorInfo
0x18001af2a  mov     ecx, ebx; dwErrCode
0x18001af2c  call    cs:__imp_SetLastError
0x18001af33  nop     dword ptr [rax+rax+00h]
0x18001af38  mov     rbx, [rsp+48h+arg_0]
0x18001af3d  mov     eax, edi
0x18001af3f  mov     rsi, [rsp+48h+arg_8]
0x18001af44  add     rsp, 40h
0x18001af48  pop     rdi
0x18001af49  retn
```
