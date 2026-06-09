# ElValidateWin32_24

- ea: `0x18002e380`
- end: `0x18002e449`
- name: `ElValidateWin32_24`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c660`
- `0x18002c750`
- `0x18002c830`
- `0x18002c93c`
- `0x18002d6ac`
- `0x18002d73c`
- `0x18002d820`
- `0x18002d870`
- `0x18002d97c`
- `0x18002df30`
- `0x18002dffc`
- `0x18002e200`

## callees

- `0x18002e380`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e42a`
- `KERNEL32!SetLastError` at `0x18002e42a`
- `KERNEL32!GetLastError` at `0x18002e3a6`
- `KERNEL32!GetLastError` at `0x18002e3f2`
- `KERNEL32!GetLastError` at `0x18002e3a6`
- `KERNEL32!GetLastError` at `0x18002e3f2`

## string_xrefs

- `0x18002e3c2`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`
- `0x18002e40b`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6options.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_24(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
        a4,
        &dword_18003572C,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6options.cpp",
        a4,
        &dword_18003572C,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e380  mov     [rsp+arg_0], rbx
0x18002e385  mov     [rsp+arg_8], rsi
0x18002e38a  push    rdi
0x18002e38b  sub     rsp, 40h
0x18002e38f  mov     esi, r9d
0x18002e392  mov     edi, ecx
0x18002e394  test    ecx, ecx
0x18002e396  jz      loc_18002E436
0x18002e39c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e3a4  jz      short loc_18002E3E8
0x18002e3a6  call    cs:__imp_GetLastError
0x18002e3ad  nop     dword ptr [rax+rax+00h]
0x18002e3b2  lea     r9, dword_18003572C
0x18002e3b9  mov     [rsp+48h+var_20], edi
0x18002e3bd  mov     [rsp+48h+var_28], r9
0x18002e3c2  lea     r8, aOnecoreBaseEco_16; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e3c9  mov     ebx, eax
0x18002e3cb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002e3d2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002e3d9  mov     r9d, esi
0x18002e3dc  mov     ecx, 80000h
0x18002e3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3e6  jmp     short loc_18002E428
0x18002e3e8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e3f0  jz      short loc_18002E436
0x18002e3f2  call    cs:__imp_GetLastError
0x18002e3f9  nop     dword ptr [rax+rax+00h]
0x18002e3fe  lea     r9, dword_18003572C
0x18002e405  mov     dword ptr [rsp+48h+var_28], edi
0x18002e409  mov     ebx, eax
0x18002e40b  lea     rdx, aOnecoreBaseEco_16; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002e412  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002e419  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002e420  mov     r8d, esi
0x18002e423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e428  mov     ecx, ebx; dwErrCode
0x18002e42a  call    cs:__imp_SetLastError
0x18002e431  nop     dword ptr [rax+rax+00h]
0x18002e436  mov     rbx, [rsp+48h+arg_0]
0x18002e43b  mov     eax, edi
0x18002e43d  mov     rsi, [rsp+48h+arg_8]
0x18002e442  add     rsp, 40h
0x18002e446  pop     rdi
0x18002e447  retn
```
