# ElValidateWin32_0

- ea: `0x180005ac4`
- end: `0x180005b8d`
- name: `ElValidateWin32_0`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058c0`
- `0x180005960`

## callees

- `0x180005ac4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005b6e`
- `KERNEL32!SetLastError` at `0x180005b6e`
- `KERNEL32!GetLastError` at `0x180005aea`
- `KERNEL32!GetLastError` at `0x180005b36`
- `KERNEL32!GetLastError` at `0x180005aea`
- `KERNEL32!GetLastError` at `0x180005b36`

## string_xrefs

- `0x180005b06`: `onecore\base\eco\wds\wdslib\common\src\eventlog2.cpp`
- `0x180005b4f`: `onecore\base\eco\wds\wdslib\common\src\eventlog2.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_0(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\eventlog2.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\eventlog2.cpp",
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
0x180005ac4  mov     [rsp+arg_0], rbx
0x180005ac9  mov     [rsp+arg_8], rsi
0x180005ace  push    rdi
0x180005acf  sub     rsp, 40h
0x180005ad3  mov     esi, r9d
0x180005ad6  mov     edi, ecx
0x180005ad8  test    ecx, ecx
0x180005ada  jz      loc_180005B7A
0x180005ae0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180005ae8  jz      short loc_180005B2C
0x180005aea  call    cs:__imp_GetLastError
0x180005af1  nop     dword ptr [rax+rax+00h]
0x180005af6  lea     r9, dword_1800331C4
0x180005afd  mov     [rsp+48h+var_20], edi
0x180005b01  mov     [rsp+48h+var_28], r9
0x180005b06  lea     r8, aOnecoreBaseEco_10; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180005b0d  mov     ebx, eax
0x180005b0f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180005b16  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180005b1d  mov     r9d, esi
0x180005b20  mov     ecx, 80000h
0x180005b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2a  jmp     short loc_180005B6C
0x180005b2c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005b34  jz      short loc_180005B7A
0x180005b36  call    cs:__imp_GetLastError
0x180005b3d  nop     dword ptr [rax+rax+00h]
0x180005b42  lea     r9, dword_1800331C4
0x180005b49  mov     dword ptr [rsp+48h+var_28], edi
0x180005b4d  mov     ebx, eax
0x180005b4f  lea     rdx, aOnecoreBaseEco_10; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180005b56  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005b5d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180005b64  mov     r8d, esi
0x180005b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b6c  mov     ecx, ebx; dwErrCode
0x180005b6e  call    cs:__imp_SetLastError
0x180005b75  nop     dword ptr [rax+rax+00h]
0x180005b7a  mov     rbx, [rsp+48h+arg_0]
0x180005b7f  mov     eax, edi
0x180005b81  mov     rsi, [rsp+48h+arg_8]
0x180005b86  add     rsp, 40h
0x180005b8a  pop     rdi
0x180005b8b  retn
```
