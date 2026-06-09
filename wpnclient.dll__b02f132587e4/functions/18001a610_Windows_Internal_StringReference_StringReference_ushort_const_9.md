# Windows::Internal::StringReference::StringReference(ushort const (&)[9])

- ea: `0x18001a610`
- end: `0x18001a653`
- name: `??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180018d90`
- `0x180019b4c`
- `0x180019d04`
- `0x18001a1a8`
- `0x18001a40c`
- `0x18001df20`

## callees

- `0x18001a610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001a644`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001a644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a62b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a62b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 8u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001a610  push    rbx
0x18001a612  sub     rsp, 20h
0x18001a616  mov     rax, rdx
0x18001a619  lea     r8, [rcx+8]; hstringHeader
0x18001a61d  mov     rbx, rcx
0x18001a620  mov     r9, rcx; string
0x18001a623  mov     rcx, rax; sourceString
0x18001a626  mov     edx, 8; length
0x18001a62b  call    cs:__imp_WindowsCreateStringReference
0x18001a631  test    eax, eax
0x18001a633  jns     short loc_18001A64A
0x18001a635  xor     r9d, r9d; lpArguments
0x18001a638  xor     r8d, r8d; nNumberOfArguments
0x18001a63b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001a640  lea     edx, [r9+1]; dwExceptionFlags
0x18001a644  call    cs:__imp_RaiseException
0x18001a64a  mov     rax, rbx
0x18001a64d  add     rsp, 20h
0x18001a651  pop     rbx
0x18001a652  retn
```
