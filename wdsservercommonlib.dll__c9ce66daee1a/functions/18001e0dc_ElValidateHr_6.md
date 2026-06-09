# ElValidateHr_6

- ea: `0x18001e0dc`
- end: `0x18001e1cf`
- name: `ElValidateHr_6`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001da50`
- `0x18001dc40`

## callees

- `0x1800063c4`
- `0x18001e0dc`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001e186`
- `KERNEL32!SetLastError` at `0x18001e1b0`
- `KERNEL32!SetLastError` at `0x18001e186`
- `KERNEL32!SetLastError` at `0x18001e1b0`
- `KERNEL32!GetLastError` at `0x18001e102`
- `KERNEL32!GetLastError` at `0x18001e14e`
- `KERNEL32!GetLastError` at `0x18001e192`
- `KERNEL32!GetLastError` at `0x18001e102`
- `KERNEL32!GetLastError` at `0x18001e14e`
- `KERNEL32!GetLastError` at `0x18001e192`

## string_xrefs

- `0x18001e11e`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`
- `0x18001e167`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_6(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
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
0x18001e0dc  mov     [rsp+arg_0], rbx
0x18001e0e1  mov     [rsp+arg_8], rsi
0x18001e0e6  push    rdi
0x18001e0e7  sub     rsp, 40h
0x18001e0eb  mov     esi, r9d
0x18001e0ee  mov     edi, ecx
0x18001e0f0  test    ecx, ecx
0x18001e0f2  jns     loc_18001E1BC
0x18001e0f8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e100  jz      short loc_18001E144
0x18001e102  call    cs:__imp_GetLastError
0x18001e109  nop     dword ptr [rax+rax+00h]
0x18001e10e  lea     r9, dword_1800331C4
0x18001e115  mov     [rsp+48h+var_20], edi
0x18001e119  mov     [rsp+48h+var_28], r9
0x18001e11e  lea     r8, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001e125  mov     ebx, eax
0x18001e127  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001e12e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e135  mov     r9d, esi
0x18001e138  mov     ecx, 80000h
0x18001e13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e142  jmp     short loc_18001E184
0x18001e144  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001e14c  jz      short loc_18001E192
0x18001e14e  call    cs:__imp_GetLastError
0x18001e155  nop     dword ptr [rax+rax+00h]
0x18001e15a  lea     r9, dword_1800331C4
0x18001e161  mov     dword ptr [rsp+48h+var_28], edi
0x18001e165  mov     ebx, eax
0x18001e167  lea     rdx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001e16e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001e175  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001e17c  mov     r8d, esi
0x18001e17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e184  mov     ecx, ebx; dwErrCode
0x18001e186  call    cs:__imp_SetLastError
0x18001e18d  nop     dword ptr [rax+rax+00h]
0x18001e192  call    cs:__imp_GetLastError
0x18001e199  nop     dword ptr [rax+rax+00h]
0x18001e19e  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18001e1a5  mov     ebx, eax
0x18001e1a7  jz      short loc_18001E1AE
0x18001e1a9  call    ElTraceErrorInfo
0x18001e1ae  mov     ecx, ebx; dwErrCode
0x18001e1b0  call    cs:__imp_SetLastError
0x18001e1b7  nop     dword ptr [rax+rax+00h]
0x18001e1bc  mov     rbx, [rsp+48h+arg_0]
0x18001e1c1  mov     eax, edi
0x18001e1c3  mov     rsi, [rsp+48h+arg_8]
0x18001e1c8  add     rsp, 40h
0x18001e1cc  pop     rdi
0x18001e1cd  retn
```
