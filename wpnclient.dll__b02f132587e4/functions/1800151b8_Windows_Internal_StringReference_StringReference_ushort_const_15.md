# Windows::Internal::StringReference::StringReference(ushort const (&)[15])

- ea: `0x1800151b8`
- end: `0x1800151fd`
- name: `??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z`
- size: `69`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018d90`
- `0x180019d04`

## callees

- `0x1800151b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800151d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800151d3`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0xEu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800151b8  push    rbx
0x1800151ba  sub     rsp, 20h
0x1800151be  mov     rax, rdx
0x1800151c1  lea     r8, [rcx+8]; hstringHeader
0x1800151c5  mov     rbx, rcx
0x1800151c8  mov     r9, rcx; string
0x1800151cb  mov     rcx, rax; sourceString
0x1800151ce  mov     edx, 0Eh; length
0x1800151d3  call    cs:__imp_WindowsCreateStringReference
0x1800151d9  test    eax, eax
0x1800151db  js      short loc_1800151E6
0x1800151dd  mov     rax, rbx
0x1800151e0  add     rsp, 20h
0x1800151e4  pop     rbx
0x1800151e5  retn
0x1800151e6  xor     r9d, r9d; lpArguments
0x1800151e9  xor     r8d, r8d; nNumberOfArguments
0x1800151ec  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800151f1  lea     edx, [r9+1]; dwExceptionFlags
0x1800151f5  call    cs:__imp_RaiseException
0x1800151fb  jmp     short loc_1800151DD
```
