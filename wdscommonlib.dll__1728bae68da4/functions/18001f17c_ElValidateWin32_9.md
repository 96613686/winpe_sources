# ElValidateWin32_9

- ea: `0x18001f17c`
- end: `0x18001f23d`
- name: `ElValidateWin32_9`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e840`
- `0x18001ebe0`

## callees

- `0x18001f17c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001f21e`
- `KERNEL32!SetLastError` at `0x18001f21e`
- `KERNEL32!GetLastError` at `0x18001f19a`
- `KERNEL32!GetLastError` at `0x18001f1e6`
- `KERNEL32!GetLastError` at `0x18001f19a`
- `KERNEL32!GetLastError` at `0x18001f1e6`

## string_xrefs

- `0x18001f1b6`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`
- `0x18001f1ff`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_9(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, Win32 Error=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
      a4,
      &dword_18003572C,
      a1);
LABEL_5:
    SetLastError(LastError);
    return a1;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, Win32 Error=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
      a4,
      &dword_18003572C,
      a1);
    goto LABEL_5;
  }
  return a1;
}

```

## disassembly

```asm
0x18001f17c  mov     [rsp+arg_0], rbx
0x18001f181  mov     [rsp+arg_8], rsi
0x18001f186  push    rdi
0x18001f187  sub     rsp, 40h
0x18001f18b  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001f193  mov     esi, r9d
0x18001f196  mov     edi, ecx
0x18001f198  jz      short loc_18001F1DC
0x18001f19a  call    cs:__imp_GetLastError
0x18001f1a1  nop     dword ptr [rax+rax+00h]
0x18001f1a6  lea     r9, dword_18003572C
0x18001f1ad  mov     [rsp+48h+var_20], edi
0x18001f1b1  mov     [rsp+48h+var_28], r9
0x18001f1b6  lea     r8, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f1bd  mov     ebx, eax
0x18001f1bf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001f1c6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001f1cd  mov     r9d, esi
0x18001f1d0  mov     ecx, 80000h
0x18001f1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1da  jmp     short loc_18001F21C
0x18001f1dc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001f1e4  jz      short loc_18001F22A
0x18001f1e6  call    cs:__imp_GetLastError
0x18001f1ed  nop     dword ptr [rax+rax+00h]
0x18001f1f2  lea     r9, dword_18003572C
0x18001f1f9  mov     dword ptr [rsp+48h+var_28], edi
0x18001f1fd  mov     ebx, eax
0x18001f1ff  lea     rdx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f206  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001f20d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001f214  mov     r8d, esi
0x18001f217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f21c  mov     ecx, ebx; dwErrCode
0x18001f21e  call    cs:__imp_SetLastError
0x18001f225  nop     dword ptr [rax+rax+00h]
0x18001f22a  mov     rbx, [rsp+48h+arg_0]
0x18001f22f  mov     eax, edi
0x18001f231  mov     rsi, [rsp+48h+arg_8]
0x18001f236  add     rsp, 40h
0x18001f23a  pop     rdi
0x18001f23b  retn
```
