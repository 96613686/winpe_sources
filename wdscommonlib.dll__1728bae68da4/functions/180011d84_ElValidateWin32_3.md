# ElValidateWin32_3

- ea: `0x180011d84`
- end: `0x180011e4d`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010ec0`
- `0x1800111e0`
- `0x1800115d0`

## callees

- `0x180011d84`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011e2e`
- `KERNEL32!SetLastError` at `0x180011e2e`
- `KERNEL32!GetLastError` at `0x180011daa`
- `KERNEL32!GetLastError` at `0x180011df6`
- `KERNEL32!GetLastError` at `0x180011daa`
- `KERNEL32!GetLastError` at `0x180011df6`

## string_xrefs

- `0x180011dc6`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`
- `0x180011e0f`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_3(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
        a4,
        &dword_18003572C,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
        a4,
        &dword_18003572C,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180011d84  mov     [rsp+arg_0], rbx
0x180011d89  mov     [rsp+arg_8], rsi
0x180011d8e  push    rdi
0x180011d8f  sub     rsp, 40h
0x180011d93  mov     esi, r9d
0x180011d96  mov     edi, ecx
0x180011d98  test    ecx, ecx
0x180011d9a  jz      loc_180011E3A
0x180011da0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180011da8  jz      short loc_180011DEC
0x180011daa  call    cs:__imp_GetLastError
0x180011db1  nop     dword ptr [rax+rax+00h]
0x180011db6  lea     r9, dword_18003572C
0x180011dbd  mov     [rsp+48h+var_20], edi
0x180011dc1  mov     [rsp+48h+var_28], r9
0x180011dc6  lea     r8, aOnecoreBaseEco_30; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180011dcd  mov     ebx, eax
0x180011dcf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180011dd6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180011ddd  mov     r9d, esi
0x180011de0  mov     ecx, 80000h
0x180011de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dea  jmp     short loc_180011E2C
0x180011dec  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011df4  jz      short loc_180011E3A
0x180011df6  call    cs:__imp_GetLastError
0x180011dfd  nop     dword ptr [rax+rax+00h]
0x180011e02  lea     r9, dword_18003572C
0x180011e09  mov     dword ptr [rsp+48h+var_28], edi
0x180011e0d  mov     ebx, eax
0x180011e0f  lea     rdx, aOnecoreBaseEco_30; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180011e16  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011e1d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180011e24  mov     r8d, esi
0x180011e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e2c  mov     ecx, ebx; dwErrCode
0x180011e2e  call    cs:__imp_SetLastError
0x180011e35  nop     dword ptr [rax+rax+00h]
0x180011e3a  mov     rbx, [rsp+48h+arg_0]
0x180011e3f  mov     eax, edi
0x180011e41  mov     rsi, [rsp+48h+arg_8]
0x180011e46  add     rsp, 40h
0x180011e4a  pop     rdi
0x180011e4b  retn
```
