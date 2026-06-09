# Windows::Internal::StringReference::StringReference(ushort const (&)[70])

- ea: `0x180037ce4`
- end: `0x180037d27`
- name: `??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180038e80`
- `0x18004d77c`

## callees

- `0x180037ce4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037d18`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037cff`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x45u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180037ce4  push    rbx
0x180037ce6  sub     rsp, 20h
0x180037cea  mov     rax, rdx
0x180037ced  lea     r8, [rcx+8]; hstringHeader
0x180037cf1  mov     rbx, rcx
0x180037cf4  mov     r9, rcx; string
0x180037cf7  mov     rcx, rax; sourceString
0x180037cfa  mov     edx, 45h ; 'E'; length
0x180037cff  call    cs:__imp_WindowsCreateStringReference
0x180037d05  test    eax, eax
0x180037d07  jns     short loc_180037D1E
0x180037d09  xor     r9d, r9d; lpArguments
0x180037d0c  xor     r8d, r8d; nNumberOfArguments
0x180037d0f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180037d14  lea     edx, [r9+1]; dwExceptionFlags
0x180037d18  call    cs:__imp_RaiseException
0x180037d1e  mov     rax, rbx
0x180037d21  add     rsp, 20h
0x180037d25  pop     rbx
0x180037d26  retn
```
