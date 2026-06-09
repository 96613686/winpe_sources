# ElValidateWin32_10

- ea: `0x18001e468`
- end: `0x18001e531`
- name: `ElValidateWin32_10`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e300`

## callees

- `0x18001e468`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001e512`
- `KERNEL32!SetLastError` at `0x18001e512`
- `KERNEL32!GetLastError` at `0x18001e48e`
- `KERNEL32!GetLastError` at `0x18001e4da`
- `KERNEL32!GetLastError` at `0x18001e48e`
- `KERNEL32!GetLastError` at `0x18001e4da`

## string_xrefs

- `0x18001e4aa`: `onecore\base\eco\wds\wdslib\common\src\ldapconnection.cpp`
- `0x18001e4f3`: `onecore\base\eco\wds\wdslib\common\src\ldapconnection.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_10(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldapconnection.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldapconnection.cpp",
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
0x18001e468  mov     [rsp+arg_0], rbx
0x18001e46d  mov     [rsp+arg_8], rsi
0x18001e472  push    rdi
0x18001e473  sub     rsp, 40h
0x18001e477  mov     esi, r9d
0x18001e47a  mov     edi, ecx
0x18001e47c  test    ecx, ecx
0x18001e47e  jz      loc_18001E51E
0x18001e484  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e48c  jz      short loc_18001E4D0
0x18001e48e  call    cs:__imp_GetLastError
0x18001e495  nop     dword ptr [rax+rax+00h]
0x18001e49a  lea     r9, dword_1800331C4
0x18001e4a1  mov     [rsp+48h+var_20], edi
0x18001e4a5  mov     [rsp+48h+var_28], r9
0x18001e4aa  lea     r8, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001e4b1  mov     ebx, eax
0x18001e4b3  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001e4ba  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001e4c1  mov     r9d, esi
0x18001e4c4  mov     ecx, 80000h
0x18001e4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ce  jmp     short loc_18001E510
0x18001e4d0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001e4d8  jz      short loc_18001E51E
0x18001e4da  call    cs:__imp_GetLastError
0x18001e4e1  nop     dword ptr [rax+rax+00h]
0x18001e4e6  lea     r9, dword_1800331C4
0x18001e4ed  mov     dword ptr [rsp+48h+var_28], edi
0x18001e4f1  mov     ebx, eax
0x18001e4f3  lea     rdx, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001e4fa  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001e501  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001e508  mov     r8d, esi
0x18001e50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e510  mov     ecx, ebx; dwErrCode
0x18001e512  call    cs:__imp_SetLastError
0x18001e519  nop     dword ptr [rax+rax+00h]
0x18001e51e  mov     rbx, [rsp+48h+arg_0]
0x18001e523  mov     eax, edi
0x18001e525  mov     rsi, [rsp+48h+arg_8]
0x18001e52a  add     rsp, 40h
0x18001e52e  pop     rdi
0x18001e52f  retn
```
