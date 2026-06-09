# ElValidateWin32_18

- ea: `0x18002925c`
- end: `0x180029325`
- name: `ElValidateWin32_18`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029160`
- `0x1800291e0`

## callees

- `0x18002925c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180029306`
- `KERNEL32!SetLastError` at `0x180029306`
- `KERNEL32!GetLastError` at `0x180029282`
- `KERNEL32!GetLastError` at `0x1800292ce`
- `KERNEL32!GetLastError` at `0x180029282`
- `KERNEL32!GetLastError` at `0x1800292ce`

## string_xrefs

- `0x18002929e`: `onecore\base\eco\wds\wdslib\common\src\disminitializer.cpp`
- `0x1800292e7`: `onecore\base\eco\wds\wdslib\common\src\disminitializer.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_18(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\disminitializer.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\disminitializer.cpp",
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
0x18002925c  mov     [rsp+arg_0], rbx
0x180029261  mov     [rsp+arg_8], rsi
0x180029266  push    rdi
0x180029267  sub     rsp, 40h
0x18002926b  mov     esi, r9d
0x18002926e  mov     edi, ecx
0x180029270  test    ecx, ecx
0x180029272  jz      loc_180029312
0x180029278  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029280  jz      short loc_1800292C4
0x180029282  call    cs:__imp_GetLastError
0x180029289  nop     dword ptr [rax+rax+00h]
0x18002928e  lea     r9, dword_18003572C
0x180029295  mov     [rsp+48h+var_20], edi
0x180029299  mov     [rsp+48h+var_28], r9
0x18002929e  lea     r8, aOnecoreBaseEco_32; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800292a5  mov     ebx, eax
0x1800292a7  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800292ae  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800292b5  mov     r9d, esi
0x1800292b8  mov     ecx, 80000h
0x1800292bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292c2  jmp     short loc_180029304
0x1800292c4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800292cc  jz      short loc_180029312
0x1800292ce  call    cs:__imp_GetLastError
0x1800292d5  nop     dword ptr [rax+rax+00h]
0x1800292da  lea     r9, dword_18003572C
0x1800292e1  mov     dword ptr [rsp+48h+var_28], edi
0x1800292e5  mov     ebx, eax
0x1800292e7  lea     rdx, aOnecoreBaseEco_32; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800292ee  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800292f5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800292fc  mov     r8d, esi
0x1800292ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029304  mov     ecx, ebx; dwErrCode
0x180029306  call    cs:__imp_SetLastError
0x18002930d  nop     dword ptr [rax+rax+00h]
0x180029312  mov     rbx, [rsp+48h+arg_0]
0x180029317  mov     eax, edi
0x180029319  mov     rsi, [rsp+48h+arg_8]
0x18002931e  add     rsp, 40h
0x180029322  pop     rdi
0x180029323  retn
```
