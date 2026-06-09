# ElValidateWin32_18

- ea: `0x1800280fc`
- end: `0x1800281c5`
- name: `ElValidateWin32_18`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028000`
- `0x180028080`

## callees

- `0x1800280fc`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800281a6`
- `KERNEL32!SetLastError` at `0x1800281a6`
- `KERNEL32!GetLastError` at `0x180028122`
- `KERNEL32!GetLastError` at `0x18002816e`
- `KERNEL32!GetLastError` at `0x180028122`
- `KERNEL32!GetLastError` at `0x18002816e`

## string_xrefs

- `0x18002813e`: `onecore\base\eco\wds\wdslib\common\src\disminitializer.cpp`
- `0x180028187`: `onecore\base\eco\wds\wdslib\common\src\disminitializer.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\disminitializer.cpp",
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
0x1800280fc  mov     [rsp+arg_0], rbx
0x180028101  mov     [rsp+arg_8], rsi
0x180028106  push    rdi
0x180028107  sub     rsp, 40h
0x18002810b  mov     esi, r9d
0x18002810e  mov     edi, ecx
0x180028110  test    ecx, ecx
0x180028112  jz      loc_1800281B2
0x180028118  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028120  jz      short loc_180028164
0x180028122  call    cs:__imp_GetLastError
0x180028129  nop     dword ptr [rax+rax+00h]
0x18002812e  lea     r9, dword_1800331C4
0x180028135  mov     [rsp+48h+var_20], edi
0x180028139  mov     [rsp+48h+var_28], r9
0x18002813e  lea     r8, aOnecoreBaseEco_33; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028145  mov     ebx, eax
0x180028147  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002814e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028155  mov     r9d, esi
0x180028158  mov     ecx, 80000h
0x18002815d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028162  jmp     short loc_1800281A4
0x180028164  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002816c  jz      short loc_1800281B2
0x18002816e  call    cs:__imp_GetLastError
0x180028175  nop     dword ptr [rax+rax+00h]
0x18002817a  lea     r9, dword_1800331C4
0x180028181  mov     dword ptr [rsp+48h+var_28], edi
0x180028185  mov     ebx, eax
0x180028187  lea     rdx, aOnecoreBaseEco_33; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002818e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028195  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002819c  mov     r8d, esi
0x18002819f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281a4  mov     ecx, ebx; dwErrCode
0x1800281a6  call    cs:__imp_SetLastError
0x1800281ad  nop     dword ptr [rax+rax+00h]
0x1800281b2  mov     rbx, [rsp+48h+arg_0]
0x1800281b7  mov     eax, edi
0x1800281b9  mov     rsi, [rsp+48h+arg_8]
0x1800281be  add     rsp, 40h
0x1800281c2  pop     rdi
0x1800281c3  retn
```
