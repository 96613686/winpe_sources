# ElValidateHr_12

- ea: `0x18002e284`
- end: `0x18002e377`
- name: `ElValidateHr_12`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002db20`

## callees

- `0x180006ea4`
- `0x18002e284`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e32e`
- `KERNEL32!SetLastError` at `0x18002e358`
- `KERNEL32!SetLastError` at `0x18002e32e`
- `KERNEL32!SetLastError` at `0x18002e358`
- `KERNEL32!GetLastError` at `0x18002e2aa`
- `KERNEL32!GetLastError` at `0x18002e2f6`
- `KERNEL32!GetLastError` at `0x18002e33a`
- `KERNEL32!GetLastError` at `0x18002e2aa`
- `KERNEL32!GetLastError` at `0x18002e2f6`
- `KERNEL32!GetLastError` at `0x18002e33a`

## string_xrefs

- `0x18002e2c6`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`
- `0x18002e30f`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_12(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
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
0x18002e284  mov     [rsp+arg_0], rbx
0x18002e289  mov     [rsp+arg_8], rsi
0x18002e28e  push    rdi
0x18002e28f  sub     rsp, 40h
0x18002e293  mov     esi, r9d
0x18002e296  mov     edi, ecx
0x18002e298  test    ecx, ecx
0x18002e29a  jns     loc_18002E364
0x18002e2a0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e2a8  jz      short loc_18002E2EC
0x18002e2aa  call    cs:__imp_GetLastError
0x18002e2b1  nop     dword ptr [rax+rax+00h]
0x18002e2b6  lea     r9, dword_18003572C
0x18002e2bd  mov     [rsp+48h+var_20], edi
0x18002e2c1  mov     [rsp+48h+var_28], r9
0x18002e2c6  lea     r8, aOnecoreBaseEco_16; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e2cd  mov     ebx, eax
0x18002e2cf  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002e2d6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e2dd  mov     r9d, esi
0x18002e2e0  mov     ecx, 80000h
0x18002e2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2ea  jmp     short loc_18002E32C
0x18002e2ec  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e2f4  jz      short loc_18002E33A
0x18002e2f6  call    cs:__imp_GetLastError
0x18002e2fd  nop     dword ptr [rax+rax+00h]
0x18002e302  lea     r9, dword_18003572C
0x18002e309  mov     dword ptr [rsp+48h+var_28], edi
0x18002e30d  mov     ebx, eax
0x18002e30f  lea     rdx, aOnecoreBaseEco_16; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e316  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e31d  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002e324  mov     r8d, esi
0x18002e327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e32c  mov     ecx, ebx; dwErrCode
0x18002e32e  call    cs:__imp_SetLastError
0x18002e335  nop     dword ptr [rax+rax+00h]
0x18002e33a  call    cs:__imp_GetLastError
0x18002e341  nop     dword ptr [rax+rax+00h]
0x18002e346  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18002e34d  mov     ebx, eax
0x18002e34f  jz      short loc_18002E356
0x18002e351  call    ElTraceErrorInfo
0x18002e356  mov     ecx, ebx; dwErrCode
0x18002e358  call    cs:__imp_SetLastError
0x18002e35f  nop     dword ptr [rax+rax+00h]
0x18002e364  mov     rbx, [rsp+48h+arg_0]
0x18002e369  mov     eax, edi
0x18002e36b  mov     rsi, [rsp+48h+arg_8]
0x18002e370  add     rsp, 40h
0x18002e374  pop     rdi
0x18002e375  retn
```
