# ElValidateWin32_22

- ea: `0x18002ae70`
- end: `0x18002af39`
- name: `ElValidateWin32_22`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ab80`
- `0x18002ad10`
- `0x18002adb0`

## callees

- `0x18002ae70`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002af1a`
- `KERNEL32!SetLastError` at `0x18002af1a`
- `KERNEL32!GetLastError` at `0x18002ae96`
- `KERNEL32!GetLastError` at `0x18002aee2`
- `KERNEL32!GetLastError` at `0x18002ae96`
- `KERNEL32!GetLastError` at `0x18002aee2`

## string_xrefs

- `0x18002aeb2`: `onecore\base\eco\wds\wdslib\common\src\dhcplib.cpp`
- `0x18002aefb`: `onecore\base\eco\wds\wdslib\common\src\dhcplib.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_22(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcplib.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\dhcplib.cpp",
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
0x18002ae70  mov     [rsp+arg_0], rbx
0x18002ae75  mov     [rsp+arg_8], rsi
0x18002ae7a  push    rdi
0x18002ae7b  sub     rsp, 40h
0x18002ae7f  mov     esi, r9d
0x18002ae82  mov     edi, ecx
0x18002ae84  test    ecx, ecx
0x18002ae86  jz      loc_18002AF26
0x18002ae8c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002ae94  jz      short loc_18002AED8
0x18002ae96  call    cs:__imp_GetLastError
0x18002ae9d  nop     dword ptr [rax+rax+00h]
0x18002aea2  lea     r9, dword_18003572C
0x18002aea9  mov     [rsp+48h+var_20], edi
0x18002aead  mov     [rsp+48h+var_28], r9
0x18002aeb2  lea     r8, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002aeb9  mov     ebx, eax
0x18002aebb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002aec2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002aec9  mov     r9d, esi
0x18002aecc  mov     ecx, 80000h
0x18002aed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed6  jmp     short loc_18002AF18
0x18002aed8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002aee0  jz      short loc_18002AF26
0x18002aee2  call    cs:__imp_GetLastError
0x18002aee9  nop     dword ptr [rax+rax+00h]
0x18002aeee  lea     r9, dword_18003572C
0x18002aef5  mov     dword ptr [rsp+48h+var_28], edi
0x18002aef9  mov     ebx, eax
0x18002aefb  lea     rdx, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002af02  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002af09  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002af10  mov     r8d, esi
0x18002af13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af18  mov     ecx, ebx; dwErrCode
0x18002af1a  call    cs:__imp_SetLastError
0x18002af21  nop     dword ptr [rax+rax+00h]
0x18002af26  mov     rbx, [rsp+48h+arg_0]
0x18002af2b  mov     eax, edi
0x18002af2d  mov     rsi, [rsp+48h+arg_8]
0x18002af32  add     rsp, 40h
0x18002af36  pop     rdi
0x18002af37  retn
```
