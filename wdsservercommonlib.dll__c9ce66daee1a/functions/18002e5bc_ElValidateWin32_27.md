# ElValidateWin32_27

- ea: `0x18002e5bc`
- end: `0x18002e685`
- name: `ElValidateWin32_27`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e4a0`

## callees

- `0x18002e5bc`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e666`
- `KERNEL32!SetLastError` at `0x18002e666`
- `KERNEL32!GetLastError` at `0x18002e5e2`
- `KERNEL32!GetLastError` at `0x18002e62e`
- `KERNEL32!GetLastError` at `0x18002e5e2`
- `KERNEL32!GetLastError` at `0x18002e62e`

## string_xrefs

- `0x18002e5fe`: `onecore\base\eco\wds\wdslib\common\src\hpallocator.cpp`
- `0x18002e647`: `onecore\base\eco\wds\wdslib\common\src\hpallocator.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_27(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\hpallocator.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\hpallocator.cpp",
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
0x18002e5bc  mov     [rsp+arg_0], rbx
0x18002e5c1  mov     [rsp+arg_8], rsi
0x18002e5c6  push    rdi
0x18002e5c7  sub     rsp, 40h
0x18002e5cb  mov     esi, r9d
0x18002e5ce  mov     edi, ecx
0x18002e5d0  test    ecx, ecx
0x18002e5d2  jz      loc_18002E672
0x18002e5d8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e5e0  jz      short loc_18002E624
0x18002e5e2  call    cs:__imp_GetLastError
0x18002e5e9  nop     dword ptr [rax+rax+00h]
0x18002e5ee  lea     r9, dword_1800331C4
0x18002e5f5  mov     [rsp+48h+var_20], edi
0x18002e5f9  mov     [rsp+48h+var_28], r9
0x18002e5fe  lea     r8, aOnecoreBaseEco_12; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e605  mov     ebx, eax
0x18002e607  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002e60e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e615  mov     r9d, esi
0x18002e618  mov     ecx, 80000h
0x18002e61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e622  jmp     short loc_18002E664
0x18002e624  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e62c  jz      short loc_18002E672
0x18002e62e  call    cs:__imp_GetLastError
0x18002e635  nop     dword ptr [rax+rax+00h]
0x18002e63a  lea     r9, dword_1800331C4
0x18002e641  mov     dword ptr [rsp+48h+var_28], edi
0x18002e645  mov     ebx, eax
0x18002e647  lea     rdx, aOnecoreBaseEco_12; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e64e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e655  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002e65c  mov     r8d, esi
0x18002e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e664  mov     ecx, ebx; dwErrCode
0x18002e666  call    cs:__imp_SetLastError
0x18002e66d  nop     dword ptr [rax+rax+00h]
0x18002e672  mov     rbx, [rsp+48h+arg_0]
0x18002e677  mov     eax, edi
0x18002e679  mov     rsi, [rsp+48h+arg_8]
0x18002e67e  add     rsp, 40h
0x18002e682  pop     rdi
0x18002e683  retn
```
