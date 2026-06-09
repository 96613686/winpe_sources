# Windows::Internal::StringReference::StringReference(ushort const (&)[52])

- ea: `0x180026d20`
- end: `0x180026d64`
- name: `??$?0$0DE@@StringReference@Internal@Windows@@QEAA@AEAY0DE@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[52])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800082b8`
- `0x180026d70`

## callees

- `0x180026d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026d55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026d3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026d3c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[52])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Notifications.ToastActivatorSwitch",
         0x33u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180026d20  push    rbx
0x180026d22  sub     rsp, 20h
0x180026d26  mov     rbx, rcx
0x180026d29  lea     r8, [rcx+8]; hstringHeader
0x180026d2d  mov     r9, rcx; string
0x180026d30  mov     edx, 33h ; '3'; length
0x180026d35  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivatorSwitch@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180026d3c  call    cs:__imp_WindowsCreateStringReference
0x180026d42  test    eax, eax
0x180026d44  jns     short loc_180026D5B
0x180026d46  xor     r9d, r9d; lpArguments
0x180026d49  xor     r8d, r8d; nNumberOfArguments
0x180026d4c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180026d51  lea     edx, [r9+1]; dwExceptionFlags
0x180026d55  call    cs:__imp_RaiseException
0x180026d5b  mov     rax, rbx
0x180026d5e  add     rsp, 20h
0x180026d62  pop     rbx
0x180026d63  retn
```
