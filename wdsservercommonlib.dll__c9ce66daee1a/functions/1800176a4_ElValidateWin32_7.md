# ElValidateWin32_7

- ea: `0x1800176a4`
- end: `0x18001776d`
- name: `ElValidateWin32_7`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800167b0`
- `0x180016990`
- `0x180016d10`
- `0x180016e80`
- `0x180017060`
- `0x180017120`
- `0x1800174c0`

## callees

- `0x1800176a4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001774e`
- `KERNEL32!SetLastError` at `0x18001774e`
- `KERNEL32!GetLastError` at `0x1800176ca`
- `KERNEL32!GetLastError` at `0x180017716`
- `KERNEL32!GetLastError` at `0x1800176ca`
- `KERNEL32!GetLastError` at `0x180017716`

## string_xrefs

- `0x1800176e6`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`
- `0x18001772f`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_7(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
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
0x1800176a4  mov     [rsp+arg_0], rbx
0x1800176a9  mov     [rsp+arg_8], rsi
0x1800176ae  push    rdi
0x1800176af  sub     rsp, 40h
0x1800176b3  mov     esi, r9d
0x1800176b6  mov     edi, ecx
0x1800176b8  test    ecx, ecx
0x1800176ba  jz      loc_18001775A
0x1800176c0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800176c8  jz      short loc_18001770C
0x1800176ca  call    cs:__imp_GetLastError
0x1800176d1  nop     dword ptr [rax+rax+00h]
0x1800176d6  lea     r9, dword_1800331C4
0x1800176dd  mov     [rsp+48h+var_20], edi
0x1800176e1  mov     [rsp+48h+var_28], r9
0x1800176e6  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800176ed  mov     ebx, eax
0x1800176ef  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800176f6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800176fd  mov     r9d, esi
0x180017700  mov     ecx, 80000h
0x180017705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001770a  jmp     short loc_18001774C
0x18001770c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180017714  jz      short loc_18001775A
0x180017716  call    cs:__imp_GetLastError
0x18001771d  nop     dword ptr [rax+rax+00h]
0x180017722  lea     r9, dword_1800331C4
0x180017729  mov     dword ptr [rsp+48h+var_28], edi
0x18001772d  mov     ebx, eax
0x18001772f  lea     rdx, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180017736  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001773d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180017744  mov     r8d, esi
0x180017747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001774c  mov     ecx, ebx; dwErrCode
0x18001774e  call    cs:__imp_SetLastError
0x180017755  nop     dword ptr [rax+rax+00h]
0x18001775a  mov     rbx, [rsp+48h+arg_0]
0x18001775f  mov     eax, edi
0x180017761  mov     rsi, [rsp+48h+arg_8]
0x180017766  add     rsp, 40h
0x18001776a  pop     rdi
0x18001776b  retn
```
