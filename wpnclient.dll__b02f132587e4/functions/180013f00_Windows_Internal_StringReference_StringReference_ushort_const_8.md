# Windows::Internal::StringReference::StringReference(ushort const (&)[8])

- ea: `0x180013f00`
- end: `0x180013f46`
- name: `??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001780c`
- `0x18001a40c`
- `0x18001acfc`
- `0x18001e1a4`
- `0x18001e9a4`
- `0x18002d73c`

## callees

- `0x180013f00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013f3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013f1b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 7u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180013f00  push    rbx
0x180013f02  sub     rsp, 20h
0x180013f06  mov     rax, rdx
0x180013f09  lea     r8, [rcx+8]; hstringHeader
0x180013f0d  mov     rbx, rcx
0x180013f10  mov     r9, rcx; string
0x180013f13  mov     rcx, rax; sourceString
0x180013f16  mov     edx, 7; length
0x180013f1b  call    cs:__imp_WindowsCreateStringReference
0x180013f21  test    eax, eax
0x180013f23  js      short loc_180013F2E
0x180013f25  mov     rax, rbx
0x180013f28  add     rsp, 20h
0x180013f2c  pop     rbx
0x180013f2d  retn
0x180013f2e  xor     r9d, r9d; lpArguments
0x180013f31  xor     r8d, r8d; nNumberOfArguments
0x180013f34  mov     edx, 1; dwExceptionFlags
0x180013f39  mov     ecx, 0C000000Dh; dwExceptionCode
0x180013f3e  call    cs:__imp_RaiseException
0x180013f44  jmp     short loc_180013F25
```
