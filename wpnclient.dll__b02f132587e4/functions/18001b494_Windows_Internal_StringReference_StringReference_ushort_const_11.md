# Windows::Internal::StringReference::StringReference(ushort const (&)[11])

- ea: `0x18001b494`
- end: `0x18001b4d7`
- name: `??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016334`
- `0x180019d04`

## callees

- `0x18001b494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b4c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b4c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b4af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b4af`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0xAu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001b494  push    rbx
0x18001b496  sub     rsp, 20h
0x18001b49a  mov     rax, rdx
0x18001b49d  lea     r8, [rcx+8]; hstringHeader
0x18001b4a1  mov     rbx, rcx
0x18001b4a4  mov     r9, rcx; string
0x18001b4a7  mov     rcx, rax; sourceString
0x18001b4aa  mov     edx, 0Ah; length
0x18001b4af  call    cs:__imp_WindowsCreateStringReference
0x18001b4b5  test    eax, eax
0x18001b4b7  jns     short loc_18001B4CE
0x18001b4b9  xor     r9d, r9d; lpArguments
0x18001b4bc  xor     r8d, r8d; nNumberOfArguments
0x18001b4bf  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001b4c4  lea     edx, [r9+1]; dwExceptionFlags
0x18001b4c8  call    cs:__imp_RaiseException
0x18001b4ce  mov     rax, rbx
0x18001b4d1  add     rsp, 20h
0x18001b4d5  pop     rbx
0x18001b4d6  retn
```
