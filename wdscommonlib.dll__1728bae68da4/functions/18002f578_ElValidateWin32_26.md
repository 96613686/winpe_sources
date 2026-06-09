# ElValidateWin32_26

- ea: `0x18002f578`
- end: `0x18002f641`
- name: `ElValidateWin32_26`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ec80`
- `0x18002ed50`
- `0x18002ee00`
- `0x18002eee0`
- `0x18002ef30`
- `0x18002f260`
- `0x18002f3a0`

## callees

- `0x18002f578`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002f622`
- `KERNEL32!SetLastError` at `0x18002f622`
- `KERNEL32!GetLastError` at `0x18002f59e`
- `KERNEL32!GetLastError` at `0x18002f5ea`
- `KERNEL32!GetLastError` at `0x18002f59e`
- `KERNEL32!GetLastError` at `0x18002f5ea`

## string_xrefs

- `0x18002f5ba`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6packet.cpp`
- `0x18002f603`: `onecore\base\eco\wds\wdslib\common\src\dhcpv6packet.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcpv6packet.cpp",
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
0x18002f578  mov     [rsp+arg_0], rbx
0x18002f57d  mov     [rsp+arg_8], rsi
0x18002f582  push    rdi
0x18002f583  sub     rsp, 40h
0x18002f587  mov     esi, r9d
0x18002f58a  mov     edi, ecx
0x18002f58c  test    ecx, ecx
0x18002f58e  jz      loc_18002F62E
0x18002f594  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002f59c  jz      short loc_18002F5E0
0x18002f59e  call    cs:__imp_GetLastError
0x18002f5a5  nop     dword ptr [rax+rax+00h]
0x18002f5aa  lea     r9, dword_18003572C
0x18002f5b1  mov     [rsp+48h+var_20], edi
0x18002f5b5  mov     [rsp+48h+var_28], r9
0x18002f5ba  lea     r8, aOnecoreBaseEco_20; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002f5c1  mov     ebx, eax
0x18002f5c3  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002f5ca  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002f5d1  mov     r9d, esi
0x18002f5d4  mov     ecx, 80000h
0x18002f5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5de  jmp     short loc_18002F620
0x18002f5e0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002f5e8  jz      short loc_18002F62E
0x18002f5ea  call    cs:__imp_GetLastError
0x18002f5f1  nop     dword ptr [rax+rax+00h]
0x18002f5f6  lea     r9, dword_18003572C
0x18002f5fd  mov     dword ptr [rsp+48h+var_28], edi
0x18002f601  mov     ebx, eax
0x18002f603  lea     rdx, aOnecoreBaseEco_20; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002f60a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002f611  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002f618  mov     r8d, esi
0x18002f61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f620  mov     ecx, ebx; dwErrCode
0x18002f622  call    cs:__imp_SetLastError
0x18002f629  nop     dword ptr [rax+rax+00h]
0x18002f62e  mov     rbx, [rsp+48h+arg_0]
0x18002f633  mov     eax, edi
0x18002f635  mov     rsi, [rsp+48h+arg_8]
0x18002f63a  add     rsp, 40h
0x18002f63e  pop     rdi
0x18002f63f  retn
```
