# ElValidateHr_2

- ea: `0x180011c88`
- end: `0x180011d7b`
- name: `ElValidateHr_2`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010ec0`
- `0x1800111e0`

## callees

- `0x180006ea4`
- `0x180011c88`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011d32`
- `KERNEL32!SetLastError` at `0x180011d5c`
- `KERNEL32!SetLastError` at `0x180011d32`
- `KERNEL32!SetLastError` at `0x180011d5c`
- `KERNEL32!GetLastError` at `0x180011cae`
- `KERNEL32!GetLastError` at `0x180011cfa`
- `KERNEL32!GetLastError` at `0x180011d3e`
- `KERNEL32!GetLastError` at `0x180011cae`
- `KERNEL32!GetLastError` at `0x180011cfa`
- `KERNEL32!GetLastError` at `0x180011d3e`

## string_xrefs

- `0x180011cca`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`
- `0x180011d13`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_2(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
      a4,
      &dword_18003572C,
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
      a4,
      &dword_18003572C,
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
0x180011c88  mov     [rsp+arg_0], rbx
0x180011c8d  mov     [rsp+arg_8], rsi
0x180011c92  push    rdi
0x180011c93  sub     rsp, 40h
0x180011c97  mov     esi, r9d
0x180011c9a  mov     edi, ecx
0x180011c9c  test    ecx, ecx
0x180011c9e  jns     loc_180011D68
0x180011ca4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180011cac  jz      short loc_180011CF0
0x180011cae  call    cs:__imp_GetLastError
0x180011cb5  nop     dword ptr [rax+rax+00h]
0x180011cba  lea     r9, dword_18003572C
0x180011cc1  mov     [rsp+48h+var_20], edi
0x180011cc5  mov     [rsp+48h+var_28], r9
0x180011cca  lea     r8, aOnecoreBaseEco_30; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180011cd1  mov     ebx, eax
0x180011cd3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180011cda  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180011ce1  mov     r9d, esi
0x180011ce4  mov     ecx, 80000h
0x180011ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cee  jmp     short loc_180011D30
0x180011cf0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011cf8  jz      short loc_180011D3E
0x180011cfa  call    cs:__imp_GetLastError
0x180011d01  nop     dword ptr [rax+rax+00h]
0x180011d06  lea     r9, dword_18003572C
0x180011d0d  mov     dword ptr [rsp+48h+var_28], edi
0x180011d11  mov     ebx, eax
0x180011d13  lea     rdx, aOnecoreBaseEco_30; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180011d1a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011d21  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180011d28  mov     r8d, esi
0x180011d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d30  mov     ecx, ebx; dwErrCode
0x180011d32  call    cs:__imp_SetLastError
0x180011d39  nop     dword ptr [rax+rax+00h]
0x180011d3e  call    cs:__imp_GetLastError
0x180011d45  nop     dword ptr [rax+rax+00h]
0x180011d4a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180011d51  mov     ebx, eax
0x180011d53  jz      short loc_180011D5A
0x180011d55  call    ElTraceErrorInfo
0x180011d5a  mov     ecx, ebx; dwErrCode
0x180011d5c  call    cs:__imp_SetLastError
0x180011d63  nop     dword ptr [rax+rax+00h]
0x180011d68  mov     rbx, [rsp+48h+arg_0]
0x180011d6d  mov     eax, edi
0x180011d6f  mov     rsi, [rsp+48h+arg_8]
0x180011d74  add     rsp, 40h
0x180011d78  pop     rdi
0x180011d79  retn
```
