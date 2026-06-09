# ElValidateWin32_1

- ea: `0x180008974`
- end: `0x180008a3d`
- name: `ElValidateWin32_1`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007150`
- `0x180007e20`
- `0x180007ed0`
- `0x180007f80`
- `0x1800081e0`
- `0x1800082c0`
- `0x180008540`

## callees

- `0x180008974`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008a1e`
- `KERNEL32!SetLastError` at `0x180008a1e`
- `KERNEL32!GetLastError` at `0x18000899a`
- `KERNEL32!GetLastError` at `0x1800089e6`
- `KERNEL32!GetLastError` at `0x18000899a`
- `KERNEL32!GetLastError` at `0x1800089e6`

## string_xrefs

- `0x1800089b6`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`
- `0x1800089ff`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscommon.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscommon.cpp",
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
0x180008974  mov     [rsp+arg_0], rbx
0x180008979  mov     [rsp+arg_8], rsi
0x18000897e  push    rdi
0x18000897f  sub     rsp, 40h
0x180008983  mov     esi, r9d
0x180008986  mov     edi, ecx
0x180008988  test    ecx, ecx
0x18000898a  jz      loc_180008A2A
0x180008990  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180008998  jz      short loc_1800089DC
0x18000899a  call    cs:__imp_GetLastError
0x1800089a1  nop     dword ptr [rax+rax+00h]
0x1800089a6  lea     r9, dword_18003572C
0x1800089ad  mov     [rsp+48h+var_20], edi
0x1800089b1  mov     [rsp+48h+var_28], r9
0x1800089b6  lea     r8, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800089bd  mov     ebx, eax
0x1800089bf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800089c6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800089cd  mov     r9d, esi
0x1800089d0  mov     ecx, 80000h
0x1800089d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089da  jmp     short loc_180008A1C
0x1800089dc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800089e4  jz      short loc_180008A2A
0x1800089e6  call    cs:__imp_GetLastError
0x1800089ed  nop     dword ptr [rax+rax+00h]
0x1800089f2  lea     r9, dword_18003572C
0x1800089f9  mov     dword ptr [rsp+48h+var_28], edi
0x1800089fd  mov     ebx, eax
0x1800089ff  lea     rdx, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180008a06  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008a0d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180008a14  mov     r8d, esi
0x180008a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a1c  mov     ecx, ebx; dwErrCode
0x180008a1e  call    cs:__imp_SetLastError
0x180008a25  nop     dword ptr [rax+rax+00h]
0x180008a2a  mov     rbx, [rsp+48h+arg_0]
0x180008a2f  mov     eax, edi
0x180008a31  mov     rsi, [rsp+48h+arg_8]
0x180008a36  add     rsp, 40h
0x180008a3a  pop     rdi
0x180008a3b  retn
```
