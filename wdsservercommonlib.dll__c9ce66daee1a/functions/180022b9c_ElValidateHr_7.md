# ElValidateHr_7

- ea: `0x180022b9c`
- end: `0x180022c8f`
- name: `ElValidateHr_7`
- size: `243`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020ca0`
- `0x180021cd0`
- `0x180022550`
- `0x180022770`

## callees

- `0x1800063c4`
- `0x180022b9c`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180022c46`
- `KERNEL32!SetLastError` at `0x180022c70`
- `KERNEL32!SetLastError` at `0x180022c46`
- `KERNEL32!SetLastError` at `0x180022c70`
- `KERNEL32!GetLastError` at `0x180022bc2`
- `KERNEL32!GetLastError` at `0x180022c0e`
- `KERNEL32!GetLastError` at `0x180022c52`
- `KERNEL32!GetLastError` at `0x180022bc2`
- `KERNEL32!GetLastError` at `0x180022c0e`
- `KERNEL32!GetLastError` at `0x180022c52`

## string_xrefs

- `0x180022bde`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180022c27`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_7(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v7; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
      a4,
      &dword_1800331C4,
      a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
      a4,
      &dword_1800331C4,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v7 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180022b9c  mov     [rsp+arg_0], rbx
0x180022ba1  mov     [rsp+arg_8], rsi
0x180022ba6  push    rdi
0x180022ba7  sub     rsp, 40h
0x180022bab  mov     esi, r9d
0x180022bae  mov     edi, ecx
0x180022bb0  test    ecx, ecx
0x180022bb2  jns     loc_180022C7C
0x180022bb8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180022bc0  jz      short loc_180022C04
0x180022bc2  call    cs:__imp_GetLastError
0x180022bc9  nop     dword ptr [rax+rax+00h]
0x180022bce  lea     r9, dword_1800331C4
0x180022bd5  mov     [rsp+48h+var_20], edi
0x180022bd9  mov     [rsp+48h+var_28], r9
0x180022bde  lea     r8, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180022be5  mov     ebx, eax
0x180022be7  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180022bee  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180022bf5  mov     r9d, esi
0x180022bf8  mov     ecx, 80000h
0x180022bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c02  jmp     short loc_180022C44
0x180022c04  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180022c0c  jz      short loc_180022C52
0x180022c0e  call    cs:__imp_GetLastError
0x180022c15  nop     dword ptr [rax+rax+00h]
0x180022c1a  lea     r9, dword_1800331C4
0x180022c21  mov     dword ptr [rsp+48h+var_28], edi
0x180022c25  mov     ebx, eax
0x180022c27  lea     rdx, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180022c2e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180022c35  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180022c3c  mov     r8d, esi
0x180022c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c44  mov     ecx, ebx; dwErrCode
0x180022c46  call    cs:__imp_SetLastError
0x180022c4d  nop     dword ptr [rax+rax+00h]
0x180022c52  call    cs:__imp_GetLastError
0x180022c59  nop     dword ptr [rax+rax+00h]
0x180022c5e  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180022c65  mov     ebx, eax
0x180022c67  jz      short loc_180022C6E
0x180022c69  call    ElTraceErrorInfo
0x180022c6e  mov     ecx, ebx; dwErrCode
0x180022c70  call    cs:__imp_SetLastError
0x180022c77  nop     dword ptr [rax+rax+00h]
0x180022c7c  mov     rbx, [rsp+48h+arg_0]
0x180022c81  mov     eax, edi
0x180022c83  mov     rsi, [rsp+48h+arg_8]
0x180022c88  add     rsp, 40h
0x180022c8c  pop     rdi
0x180022c8d  retn
```
