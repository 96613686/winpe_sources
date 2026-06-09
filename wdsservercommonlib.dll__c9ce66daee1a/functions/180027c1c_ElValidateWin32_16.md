# ElValidateWin32_16

- ea: `0x180027c1c`
- end: `0x180027ce5`
- name: `ElValidateWin32_16`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027b30`

## callees

- `0x180027c1c`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027cc6`
- `KERNEL32!SetLastError` at `0x180027cc6`
- `KERNEL32!GetLastError` at `0x180027c42`
- `KERNEL32!GetLastError` at `0x180027c8e`
- `KERNEL32!GetLastError` at `0x180027c42`
- `KERNEL32!GetLastError` at `0x180027c8e`

## string_xrefs

- `0x180027c5e`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`
- `0x180027ca7`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_16(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp",
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
0x180027c1c  mov     [rsp+arg_0], rbx
0x180027c21  mov     [rsp+arg_8], rsi
0x180027c26  push    rdi
0x180027c27  sub     rsp, 40h
0x180027c2b  mov     esi, r9d
0x180027c2e  mov     edi, ecx
0x180027c30  test    ecx, ecx
0x180027c32  jz      loc_180027CD2
0x180027c38  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027c40  jz      short loc_180027C84
0x180027c42  call    cs:__imp_GetLastError
0x180027c49  nop     dword ptr [rax+rax+00h]
0x180027c4e  lea     r9, dword_1800331C4
0x180027c55  mov     [rsp+48h+var_20], edi
0x180027c59  mov     [rsp+48h+var_28], r9
0x180027c5e  lea     r8, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027c65  mov     ebx, eax
0x180027c67  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180027c6e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027c75  mov     r9d, esi
0x180027c78  mov     ecx, 80000h
0x180027c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c82  jmp     short loc_180027CC4
0x180027c84  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027c8c  jz      short loc_180027CD2
0x180027c8e  call    cs:__imp_GetLastError
0x180027c95  nop     dword ptr [rax+rax+00h]
0x180027c9a  lea     r9, dword_1800331C4
0x180027ca1  mov     dword ptr [rsp+48h+var_28], edi
0x180027ca5  mov     ebx, eax
0x180027ca7  lea     rdx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027cae  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027cb5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180027cbc  mov     r8d, esi
0x180027cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cc4  mov     ecx, ebx; dwErrCode
0x180027cc6  call    cs:__imp_SetLastError
0x180027ccd  nop     dword ptr [rax+rax+00h]
0x180027cd2  mov     rbx, [rsp+48h+arg_0]
0x180027cd7  mov     eax, edi
0x180027cd9  mov     rsi, [rsp+48h+arg_8]
0x180027cde  add     rsp, 40h
0x180027ce2  pop     rdi
0x180027ce3  retn
```
