# ElValidateWin32_9

- ea: `0x18001e1d8`
- end: `0x18001e299`
- name: `ElValidateWin32_9`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d8c0`
- `0x18001dc40`

## callees

- `0x18001e1d8`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001e27a`
- `KERNEL32!SetLastError` at `0x18001e27a`
- `KERNEL32!GetLastError` at `0x18001e1f6`
- `KERNEL32!GetLastError` at `0x18001e242`
- `KERNEL32!GetLastError` at `0x18001e1f6`
- `KERNEL32!GetLastError` at `0x18001e242`

## string_xrefs

- `0x18001e212`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`
- `0x18001e25b`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_9(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, Win32 Error=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
      a4,
      &dword_1800331C4,
      a1);
LABEL_5:
    SetLastError(LastError);
    return a1;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, Win32 Error=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
      a4,
      &dword_1800331C4,
      a1);
    goto LABEL_5;
  }
  return a1;
}

```

## disassembly

```asm
0x18001e1d8  mov     [rsp+arg_0], rbx
0x18001e1dd  mov     [rsp+arg_8], rsi
0x18001e1e2  push    rdi
0x18001e1e3  sub     rsp, 40h
0x18001e1e7  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e1ef  mov     esi, r9d
0x18001e1f2  mov     edi, ecx
0x18001e1f4  jz      short loc_18001E238
0x18001e1f6  call    cs:__imp_GetLastError
0x18001e1fd  nop     dword ptr [rax+rax+00h]
0x18001e202  lea     r9, dword_1800331C4
0x18001e209  mov     [rsp+48h+var_20], edi
0x18001e20d  mov     [rsp+48h+var_28], r9
0x18001e212  lea     r8, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001e219  mov     ebx, eax
0x18001e21b  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001e222  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e229  mov     r9d, esi
0x18001e22c  mov     ecx, 80000h
0x18001e231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e236  jmp     short loc_18001E278
0x18001e238  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001e240  jz      short loc_18001E286
0x18001e242  call    cs:__imp_GetLastError
0x18001e249  nop     dword ptr [rax+rax+00h]
0x18001e24e  lea     r9, dword_1800331C4
0x18001e255  mov     dword ptr [rsp+48h+var_28], edi
0x18001e259  mov     ebx, eax
0x18001e25b  lea     rdx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001e262  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001e269  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001e270  mov     r8d, esi
0x18001e273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e278  mov     ecx, ebx; dwErrCode
0x18001e27a  call    cs:__imp_SetLastError
0x18001e281  nop     dword ptr [rax+rax+00h]
0x18001e286  mov     rbx, [rsp+48h+arg_0]
0x18001e28b  mov     eax, edi
0x18001e28d  mov     rsi, [rsp+48h+arg_8]
0x18001e292  add     rsp, 40h
0x18001e296  pop     rdi
0x18001e297  retn
```
