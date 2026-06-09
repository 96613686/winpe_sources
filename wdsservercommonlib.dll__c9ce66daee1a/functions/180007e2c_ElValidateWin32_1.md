# ElValidateWin32_1

- ea: `0x180007e2c`
- end: `0x180007ef5`
- name: `ElValidateWin32_1`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006660`
- `0x1800072f0`
- `0x1800073a0`
- `0x180007450`
- `0x1800076b0`
- `0x180007790`
- `0x180007a00`

## callees

- `0x180007e2c`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007ed6`
- `KERNEL32!SetLastError` at `0x180007ed6`
- `KERNEL32!GetLastError` at `0x180007e52`
- `KERNEL32!GetLastError` at `0x180007e9e`
- `KERNEL32!GetLastError` at `0x180007e52`
- `KERNEL32!GetLastError` at `0x180007e9e`

## string_xrefs

- `0x180007e6e`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`
- `0x180007eb7`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`

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
        &dword_1800331C4,
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
        &dword_1800331C4,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180007e2c  mov     [rsp+arg_0], rbx
0x180007e31  mov     [rsp+arg_8], rsi
0x180007e36  push    rdi
0x180007e37  sub     rsp, 40h
0x180007e3b  mov     esi, r9d
0x180007e3e  mov     edi, ecx
0x180007e40  test    ecx, ecx
0x180007e42  jz      loc_180007EE2
0x180007e48  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007e50  jz      short loc_180007E94
0x180007e52  call    cs:__imp_GetLastError
0x180007e59  nop     dword ptr [rax+rax+00h]
0x180007e5e  lea     r9, dword_1800331C4
0x180007e65  mov     [rsp+48h+var_20], edi
0x180007e69  mov     [rsp+48h+var_28], r9
0x180007e6e  lea     r8, aOnecoreBaseEco_18; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180007e75  mov     ebx, eax
0x180007e77  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180007e7e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007e85  mov     r9d, esi
0x180007e88  mov     ecx, 80000h
0x180007e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e92  jmp     short loc_180007ED4
0x180007e94  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007e9c  jz      short loc_180007EE2
0x180007e9e  call    cs:__imp_GetLastError
0x180007ea5  nop     dword ptr [rax+rax+00h]
0x180007eaa  lea     r9, dword_1800331C4
0x180007eb1  mov     dword ptr [rsp+48h+var_28], edi
0x180007eb5  mov     ebx, eax
0x180007eb7  lea     rdx, aOnecoreBaseEco_18; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180007ebe  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007ec5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180007ecc  mov     r8d, esi
0x180007ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed4  mov     ecx, ebx; dwErrCode
0x180007ed6  call    cs:__imp_SetLastError
0x180007edd  nop     dword ptr [rax+rax+00h]
0x180007ee2  mov     rbx, [rsp+48h+arg_0]
0x180007ee7  mov     eax, edi
0x180007ee9  mov     rsi, [rsp+48h+arg_8]
0x180007eee  add     rsp, 40h
0x180007ef2  pop     rdi
0x180007ef3  retn
```
