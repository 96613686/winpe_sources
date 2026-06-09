# ElValidateWin32_26

- ea: `0x18002e348`
- end: `0x18002e411`
- name: `ElValidateWin32_26`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002da60`
- `0x18002db30`
- `0x18002dbe0`
- `0x18002dcc0`
- `0x18002dd10`
- `0x18002e050`
- `0x18002e190`

## callees

- `0x18002e348`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e3f2`
- `KERNEL32!SetLastError` at `0x18002e3f2`
- `KERNEL32!GetLastError` at `0x18002e36e`
- `KERNEL32!GetLastError` at `0x18002e3ba`
- `KERNEL32!GetLastError` at `0x18002e36e`
- `KERNEL32!GetLastError` at `0x18002e3ba`

## string_xrefs

- `0x18002e38a`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6packet.cpp`
- `0x18002e3d3`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6packet.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_26(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6packet.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6packet.cpp",
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
0x18002e348  mov     [rsp+arg_0], rbx
0x18002e34d  mov     [rsp+arg_8], rsi
0x18002e352  push    rdi
0x18002e353  sub     rsp, 40h
0x18002e357  mov     esi, r9d
0x18002e35a  mov     edi, ecx
0x18002e35c  test    ecx, ecx
0x18002e35e  jz      loc_18002E3FE
0x18002e364  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e36c  jz      short loc_18002E3B0
0x18002e36e  call    cs:__imp_GetLastError
0x18002e375  nop     dword ptr [rax+rax+00h]
0x18002e37a  lea     r9, dword_1800331C4
0x18002e381  mov     [rsp+48h+var_20], edi
0x18002e385  mov     [rsp+48h+var_28], r9
0x18002e38a  lea     r8, aOnecoreBaseEco_21; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e391  mov     ebx, eax
0x18002e393  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002e39a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e3a1  mov     r9d, esi
0x18002e3a4  mov     ecx, 80000h
0x18002e3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3ae  jmp     short loc_18002E3F0
0x18002e3b0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e3b8  jz      short loc_18002E3FE
0x18002e3ba  call    cs:__imp_GetLastError
0x18002e3c1  nop     dword ptr [rax+rax+00h]
0x18002e3c6  lea     r9, dword_1800331C4
0x18002e3cd  mov     dword ptr [rsp+48h+var_28], edi
0x18002e3d1  mov     ebx, eax
0x18002e3d3  lea     rdx, aOnecoreBaseEco_21; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e3da  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e3e1  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002e3e8  mov     r8d, esi
0x18002e3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3f0  mov     ecx, ebx; dwErrCode
0x18002e3f2  call    cs:__imp_SetLastError
0x18002e3f9  nop     dword ptr [rax+rax+00h]
0x18002e3fe  mov     rbx, [rsp+48h+arg_0]
0x18002e403  mov     eax, edi
0x18002e405  mov     rsi, [rsp+48h+arg_8]
0x18002e40a  add     rsp, 40h
0x18002e40e  pop     rdi
0x18002e40f  retn
```
