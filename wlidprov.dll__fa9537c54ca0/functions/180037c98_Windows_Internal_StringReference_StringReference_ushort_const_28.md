# Windows::Internal::StringReference::StringReference(ushort const (&)[28])

- ea: `0x180037c98`
- end: `0x180037cdb`
- name: `??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180038e80`
- `0x18004d77c`

## callees

- `0x180037c98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037ccc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037ccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037cb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037cb3`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x1Bu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180037c98  push    rbx
0x180037c9a  sub     rsp, 20h
0x180037c9e  mov     rax, rdx
0x180037ca1  lea     r8, [rcx+8]; hstringHeader
0x180037ca5  mov     rbx, rcx
0x180037ca8  mov     r9, rcx; string
0x180037cab  mov     rcx, rax; sourceString
0x180037cae  mov     edx, 1Bh; length
0x180037cb3  call    cs:__imp_WindowsCreateStringReference
0x180037cb9  test    eax, eax
0x180037cbb  jns     short loc_180037CD2
0x180037cbd  xor     r9d, r9d; lpArguments
0x180037cc0  xor     r8d, r8d; nNumberOfArguments
0x180037cc3  mov     ecx, 0C000000Dh; dwExceptionCode
0x180037cc8  lea     edx, [r9+1]; dwExceptionFlags
0x180037ccc  call    cs:__imp_RaiseException
0x180037cd2  mov     rax, rbx
0x180037cd5  add     rsp, 20h
0x180037cd9  pop     rbx
0x180037cda  retn
```
