# ElValidateWin32_9

- ea: `0x180013d84`
- end: `0x180013e4d`
- name: `ElValidateWin32_9`
- size: `201`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012890`
- `0x1800139a8`
- `0x180013adc`
- `0x180013b90`
- `0x180013ca0`

## callees

- `0x180013d84`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013e2e`
- `KERNEL32!SetLastError` at `0x180013e2e`
- `KERNEL32!GetLastError` at `0x180013daa`
- `KERNEL32!GetLastError` at `0x180013df6`
- `KERNEL32!GetLastError` at `0x180013daa`
- `KERNEL32!GetLastError` at `0x180013df6`

## string_xrefs

- `0x180013dc6`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`
- `0x180013e0f`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_9(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp",
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp",
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
0x180013d84  mov     [rsp+arg_0], rbx
0x180013d89  mov     [rsp+arg_8], rsi
0x180013d8e  push    rdi
0x180013d8f  sub     rsp, 40h
0x180013d93  mov     esi, r9d
0x180013d96  mov     edi, ecx
0x180013d98  test    ecx, ecx
0x180013d9a  jz      loc_180013E3A
0x180013da0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013da8  jz      short loc_180013DEC
0x180013daa  call    cs:__imp_GetLastError
0x180013db1  nop     dword ptr [rax+rax+00h]
0x180013db6  lea     r9, dword_18001A184
0x180013dbd  mov     [rsp+48h+var_20], edi
0x180013dc1  mov     [rsp+48h+var_28], r9
0x180013dc6  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180013dcd  mov     ebx, eax
0x180013dcf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013dd6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013ddd  mov     r9d, esi
0x180013de0  mov     ecx, 80000h
0x180013de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dea  jmp     short loc_180013E2C
0x180013dec  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013df4  jz      short loc_180013E3A
0x180013df6  call    cs:__imp_GetLastError
0x180013dfd  nop     dword ptr [rax+rax+00h]
0x180013e02  lea     r9, dword_18001A184
0x180013e09  mov     dword ptr [rsp+48h+var_28], edi
0x180013e0d  mov     ebx, eax
0x180013e0f  lea     rdx, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180013e16  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013e1d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013e24  mov     r8d, esi
0x180013e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e2c  mov     ecx, ebx; dwErrCode
0x180013e2e  call    cs:__imp_SetLastError
0x180013e35  nop     dword ptr [rax+rax+00h]
0x180013e3a  mov     rbx, [rsp+48h+arg_0]
0x180013e3f  mov     eax, edi
0x180013e41  mov     rsi, [rsp+48h+arg_8]
0x180013e46  add     rsp, 40h
0x180013e4a  pop     rdi
0x180013e4b  retn
```
