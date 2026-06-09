# ElValidateWin32_2

- ea: `0x18000df94`
- end: `0x18000e056`
- name: `ElValidateWin32_2`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800099b0`

## callees

- `0x18000df94`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000e03c`
- `KERNEL32!SetLastError` at `0x18000e03c`
- `KERNEL32!GetLastError` at `0x18000dfb2`
- `KERNEL32!GetLastError` at `0x18000e001`
- `KERNEL32!GetLastError` at `0x18000dfb2`
- `KERNEL32!GetLastError` at `0x18000e001`

## string_xrefs

- `0x18000dfce`: `onecore\base\eco\wds\wdslib\common\src\bufferpool.cpp`
- `0x18000e01a`: `onecore\base\eco\wds\wdslib\common\src\bufferpool.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_2(unsigned int a1)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\bufferpool.cpp",
        177,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\bufferpool.cpp",
        177,
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
0x18000df94  mov     [rsp+arg_0], rbx
0x18000df99  push    rdi
0x18000df9a  sub     rsp, 40h
0x18000df9e  mov     edi, ecx
0x18000dfa0  test    ecx, ecx
0x18000dfa2  jz      loc_18000E048
0x18000dfa8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000dfb0  jz      short loc_18000DFF7
0x18000dfb2  call    cs:__imp_GetLastError
0x18000dfb9  nop     dword ptr [rax+rax+00h]
0x18000dfbe  lea     r9, dword_1800331C4
0x18000dfc5  mov     [rsp+48h+var_20], edi
0x18000dfc9  mov     [rsp+48h+var_28], r9
0x18000dfce  lea     r8, aOnecoreBaseEco_30; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000dfd5  mov     ebx, eax
0x18000dfd7  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000dfde  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000dfe5  mov     r9d, 0B1h
0x18000dfeb  mov     ecx, 80000h
0x18000dff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff5  jmp     short loc_18000E03A
0x18000dff7  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000dfff  jz      short loc_18000E048
0x18000e001  call    cs:__imp_GetLastError
0x18000e008  nop     dword ptr [rax+rax+00h]
0x18000e00d  lea     r9, dword_1800331C4
0x18000e014  mov     dword ptr [rsp+48h+var_28], edi
0x18000e018  mov     ebx, eax
0x18000e01a  lea     rdx, aOnecoreBaseEco_30; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000e021  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000e028  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000e02f  mov     r8d, 0B1h
0x18000e035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e03a  mov     ecx, ebx; dwErrCode
0x18000e03c  call    cs:__imp_SetLastError
0x18000e043  nop     dword ptr [rax+rax+00h]
0x18000e048  mov     rbx, [rsp+48h+arg_0]
0x18000e04d  mov     eax, edi
0x18000e04f  add     rsp, 40h
0x18000e053  pop     rdi
0x18000e054  retn
```
