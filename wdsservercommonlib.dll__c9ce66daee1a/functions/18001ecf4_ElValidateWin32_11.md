# ElValidateWin32_11

- ea: `0x18001ecf4`
- end: `0x18001edbd`
- name: `ElValidateWin32_11`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e9b0`

## callees

- `0x18001ecf4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001ed9e`
- `KERNEL32!SetLastError` at `0x18001ed9e`
- `KERNEL32!GetLastError` at `0x18001ed1a`
- `KERNEL32!GetLastError` at `0x18001ed66`
- `KERNEL32!GetLastError` at `0x18001ed1a`
- `KERNEL32!GetLastError` at `0x18001ed66`

## string_xrefs

- `0x18001ed36`: `onecore\base\eco\wds\wdslib\common\src\errormessage.cpp`
- `0x18001ed7f`: `onecore\base\eco\wds\wdslib\common\src\errormessage.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_11(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\errormessage.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\errormessage.cpp",
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
0x18001ecf4  mov     [rsp+arg_0], rbx
0x18001ecf9  mov     [rsp+arg_8], rsi
0x18001ecfe  push    rdi
0x18001ecff  sub     rsp, 40h
0x18001ed03  mov     esi, r9d
0x18001ed06  mov     edi, ecx
0x18001ed08  test    ecx, ecx
0x18001ed0a  jz      loc_18001EDAA
0x18001ed10  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001ed18  jz      short loc_18001ED5C
0x18001ed1a  call    cs:__imp_GetLastError
0x18001ed21  nop     dword ptr [rax+rax+00h]
0x18001ed26  lea     r9, dword_1800331C4
0x18001ed2d  mov     [rsp+48h+var_20], edi
0x18001ed31  mov     [rsp+48h+var_28], r9
0x18001ed36  lea     r8, aOnecoreBaseEco_16; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001ed3d  mov     ebx, eax
0x18001ed3f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001ed46  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001ed4d  mov     r9d, esi
0x18001ed50  mov     ecx, 80000h
0x18001ed55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed5a  jmp     short loc_18001ED9C
0x18001ed5c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001ed64  jz      short loc_18001EDAA
0x18001ed66  call    cs:__imp_GetLastError
0x18001ed6d  nop     dword ptr [rax+rax+00h]
0x18001ed72  lea     r9, dword_1800331C4
0x18001ed79  mov     dword ptr [rsp+48h+var_28], edi
0x18001ed7d  mov     ebx, eax
0x18001ed7f  lea     rdx, aOnecoreBaseEco_16; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001ed86  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001ed8d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001ed94  mov     r8d, esi
0x18001ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed9c  mov     ecx, ebx; dwErrCode
0x18001ed9e  call    cs:__imp_SetLastError
0x18001eda5  nop     dword ptr [rax+rax+00h]
0x18001edaa  mov     rbx, [rsp+48h+arg_0]
0x18001edaf  mov     eax, edi
0x18001edb1  mov     rsi, [rsp+48h+arg_8]
0x18001edb6  add     rsp, 40h
0x18001edba  pop     rdi
0x18001edbb  retn
```
