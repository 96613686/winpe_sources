# ElValidateWin32_20

- ea: `0x180028ed4`
- end: `0x180028f9d`
- name: `ElValidateWin32_20`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028990`

## callees

- `0x180028ed4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180028f7e`
- `KERNEL32!SetLastError` at `0x180028f7e`
- `KERNEL32!GetLastError` at `0x180028efa`
- `KERNEL32!GetLastError` at `0x180028f46`
- `KERNEL32!GetLastError` at `0x180028efa`
- `KERNEL32!GetLastError` at `0x180028f46`

## string_xrefs

- `0x180028f16`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`
- `0x180028f5f`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_20(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
0x180028ed4  mov     [rsp+arg_0], rbx
0x180028ed9  mov     [rsp+arg_8], rsi
0x180028ede  push    rdi
0x180028edf  sub     rsp, 40h
0x180028ee3  mov     esi, r9d
0x180028ee6  mov     edi, ecx
0x180028ee8  test    ecx, ecx
0x180028eea  jz      loc_180028F8A
0x180028ef0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028ef8  jz      short loc_180028F3C
0x180028efa  call    cs:__imp_GetLastError
0x180028f01  nop     dword ptr [rax+rax+00h]
0x180028f06  lea     r9, dword_1800331C4
0x180028f0d  mov     [rsp+48h+var_20], edi
0x180028f11  mov     [rsp+48h+var_28], r9
0x180028f16  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028f1d  mov     ebx, eax
0x180028f1f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180028f26  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028f2d  mov     r9d, esi
0x180028f30  mov     ecx, 80000h
0x180028f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f3a  jmp     short loc_180028F7C
0x180028f3c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028f44  jz      short loc_180028F8A
0x180028f46  call    cs:__imp_GetLastError
0x180028f4d  nop     dword ptr [rax+rax+00h]
0x180028f52  lea     r9, dword_1800331C4
0x180028f59  mov     dword ptr [rsp+48h+var_28], edi
0x180028f5d  mov     ebx, eax
0x180028f5f  lea     rdx, aOnecoreBaseEco_26; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028f66  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028f6d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180028f74  mov     r8d, esi
0x180028f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f7c  mov     ecx, ebx; dwErrCode
0x180028f7e  call    cs:__imp_SetLastError
0x180028f85  nop     dword ptr [rax+rax+00h]
0x180028f8a  mov     rbx, [rsp+48h+arg_0]
0x180028f8f  mov     eax, edi
0x180028f91  mov     rsi, [rsp+48h+arg_8]
0x180028f96  add     rsp, 40h
0x180028f9a  pop     rdi
0x180028f9b  retn
```
