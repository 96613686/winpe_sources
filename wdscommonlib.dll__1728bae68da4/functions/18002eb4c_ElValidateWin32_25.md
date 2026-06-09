# ElValidateWin32_25

- ea: `0x18002eb4c`
- end: `0x18002ec15`
- name: `ElValidateWin32_25`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e5b0`
- `0x18002e650`

## callees

- `0x18002eb4c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002ebf6`
- `KERNEL32!SetLastError` at `0x18002ebf6`
- `KERNEL32!GetLastError` at `0x18002eb72`
- `KERNEL32!GetLastError` at `0x18002ebbe`
- `KERNEL32!GetLastError` at `0x18002eb72`
- `KERNEL32!GetLastError` at `0x18002ebbe`

## string_xrefs

- `0x18002eb8e`: `onecore\base\eco\wds\wdslib\common\src\dhcppacket.cpp`
- `0x18002ebd7`: `onecore\base\eco\wds\wdslib\common\src\dhcppacket.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_25(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcppacket.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcppacket.cpp",
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
0x18002eb4c  mov     [rsp+arg_0], rbx
0x18002eb51  mov     [rsp+arg_8], rsi
0x18002eb56  push    rdi
0x18002eb57  sub     rsp, 40h
0x18002eb5b  mov     esi, r9d
0x18002eb5e  mov     edi, ecx
0x18002eb60  test    ecx, ecx
0x18002eb62  jz      loc_18002EC02
0x18002eb68  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002eb70  jz      short loc_18002EBB4
0x18002eb72  call    cs:__imp_GetLastError
0x18002eb79  nop     dword ptr [rax+rax+00h]
0x18002eb7e  lea     r9, dword_18003572C
0x18002eb85  mov     [rsp+48h+var_20], edi
0x18002eb89  mov     [rsp+48h+var_28], r9
0x18002eb8e  lea     r8, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002eb95  mov     ebx, eax
0x18002eb97  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002eb9e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002eba5  mov     r9d, esi
0x18002eba8  mov     ecx, 80000h
0x18002ebad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebb2  jmp     short loc_18002EBF4
0x18002ebb4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002ebbc  jz      short loc_18002EC02
0x18002ebbe  call    cs:__imp_GetLastError
0x18002ebc5  nop     dword ptr [rax+rax+00h]
0x18002ebca  lea     r9, dword_18003572C
0x18002ebd1  mov     dword ptr [rsp+48h+var_28], edi
0x18002ebd5  mov     ebx, eax
0x18002ebd7  lea     rdx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002ebde  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002ebe5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002ebec  mov     r8d, esi
0x18002ebef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf4  mov     ecx, ebx; dwErrCode
0x18002ebf6  call    cs:__imp_SetLastError
0x18002ebfd  nop     dword ptr [rax+rax+00h]
0x18002ec02  mov     rbx, [rsp+48h+arg_0]
0x18002ec07  mov     eax, edi
0x18002ec09  mov     rsi, [rsp+48h+arg_8]
0x18002ec0e  add     rsp, 40h
0x18002ec12  pop     rdi
0x18002ec13  retn
```
