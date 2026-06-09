# ElValidateWin32_6

- ea: `0x1800166e0`
- end: `0x1800167a9`
- name: `ElValidateWin32_6`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800156c0`

## callees

- `0x1800166e0`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001678a`
- `KERNEL32!SetLastError` at `0x18001678a`
- `KERNEL32!GetLastError` at `0x180016706`
- `KERNEL32!GetLastError` at `0x180016752`
- `KERNEL32!GetLastError` at `0x180016706`
- `KERNEL32!GetLastError` at `0x180016752`

## string_xrefs

- `0x180016722`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x18001676b`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_6(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
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
0x1800166e0  mov     [rsp+arg_0], rbx
0x1800166e5  mov     [rsp+arg_8], rsi
0x1800166ea  push    rdi
0x1800166eb  sub     rsp, 40h
0x1800166ef  mov     esi, r9d
0x1800166f2  mov     edi, ecx
0x1800166f4  test    ecx, ecx
0x1800166f6  jz      loc_180016796
0x1800166fc  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180016704  jz      short loc_180016748
0x180016706  call    cs:__imp_GetLastError
0x18001670d  nop     dword ptr [rax+rax+00h]
0x180016712  lea     r9, dword_1800331C4
0x180016719  mov     [rsp+48h+var_20], edi
0x18001671d  mov     [rsp+48h+var_28], r9
0x180016722  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180016729  mov     ebx, eax
0x18001672b  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180016732  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180016739  mov     r9d, esi
0x18001673c  mov     ecx, 80000h
0x180016741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016746  jmp     short loc_180016788
0x180016748  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180016750  jz      short loc_180016796
0x180016752  call    cs:__imp_GetLastError
0x180016759  nop     dword ptr [rax+rax+00h]
0x18001675e  lea     r9, dword_1800331C4
0x180016765  mov     dword ptr [rsp+48h+var_28], edi
0x180016769  mov     ebx, eax
0x18001676b  lea     rdx, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180016772  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180016779  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180016780  mov     r8d, esi
0x180016783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016788  mov     ecx, ebx; dwErrCode
0x18001678a  call    cs:__imp_SetLastError
0x180016791  nop     dword ptr [rax+rax+00h]
0x180016796  mov     rbx, [rsp+48h+arg_0]
0x18001679b  mov     eax, edi
0x18001679d  mov     rsi, [rsp+48h+arg_8]
0x1800167a2  add     rsp, 40h
0x1800167a6  pop     rdi
0x1800167a7  retn
```
