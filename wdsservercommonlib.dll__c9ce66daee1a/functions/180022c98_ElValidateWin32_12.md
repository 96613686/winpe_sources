# ElValidateWin32_12

- ea: `0x180022c98`
- end: `0x180022d61`
- name: `ElValidateWin32_12`
- size: `201`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020670`
- `0x180020960`
- `0x180020ca0`
- `0x180020f80`
- `0x180021010`
- `0x1800211f8`
- `0x180021398`
- `0x1800215a0`
- `0x180021610`
- `0x180021730`
- `0x180021f10`
- `0x1800221a0`
- `0x180022a30`

## callees

- `0x180022c98`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180022d42`
- `KERNEL32!SetLastError` at `0x180022d42`
- `KERNEL32!GetLastError` at `0x180022cbe`
- `KERNEL32!GetLastError` at `0x180022d0a`
- `KERNEL32!GetLastError` at `0x180022cbe`
- `KERNEL32!GetLastError` at `0x180022d0a`

## string_xrefs

- `0x180022cda`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180022d23`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_12(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
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
0x180022c98  mov     [rsp+arg_0], rbx
0x180022c9d  mov     [rsp+arg_8], rsi
0x180022ca2  push    rdi
0x180022ca3  sub     rsp, 40h
0x180022ca7  mov     esi, r9d
0x180022caa  mov     edi, ecx
0x180022cac  test    ecx, ecx
0x180022cae  jz      loc_180022D4E
0x180022cb4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180022cbc  jz      short loc_180022D00
0x180022cbe  call    cs:__imp_GetLastError
0x180022cc5  nop     dword ptr [rax+rax+00h]
0x180022cca  lea     r9, dword_1800331C4
0x180022cd1  mov     [rsp+48h+var_20], edi
0x180022cd5  mov     [rsp+48h+var_28], r9
0x180022cda  lea     r8, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180022ce1  mov     ebx, eax
0x180022ce3  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180022cea  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180022cf1  mov     r9d, esi
0x180022cf4  mov     ecx, 80000h
0x180022cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cfe  jmp     short loc_180022D40
0x180022d00  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180022d08  jz      short loc_180022D4E
0x180022d0a  call    cs:__imp_GetLastError
0x180022d11  nop     dword ptr [rax+rax+00h]
0x180022d16  lea     r9, dword_1800331C4
0x180022d1d  mov     dword ptr [rsp+48h+var_28], edi
0x180022d21  mov     ebx, eax
0x180022d23  lea     rdx, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180022d2a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180022d31  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180022d38  mov     r8d, esi
0x180022d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d40  mov     ecx, ebx; dwErrCode
0x180022d42  call    cs:__imp_SetLastError
0x180022d49  nop     dword ptr [rax+rax+00h]
0x180022d4e  mov     rbx, [rsp+48h+arg_0]
0x180022d53  mov     eax, edi
0x180022d55  mov     rsi, [rsp+48h+arg_8]
0x180022d5a  add     rsp, 40h
0x180022d5e  pop     rdi
0x180022d5f  retn
```
