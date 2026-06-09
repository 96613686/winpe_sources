# Windows::Internal::StringReference::StringReference(ushort const (&)[33])

- ea: `0x180014160`
- end: `0x1800141a6`
- name: `??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019d04`
- `0x18001cfac`

## callees

- `0x180014160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001419e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001419e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001417b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001417b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x20u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180014160  push    rbx
0x180014162  sub     rsp, 20h
0x180014166  mov     rax, rdx
0x180014169  lea     r8, [rcx+8]; hstringHeader
0x18001416d  mov     rbx, rcx
0x180014170  mov     r9, rcx; string
0x180014173  mov     rcx, rax; sourceString
0x180014176  mov     edx, 20h ; ' '; length
0x18001417b  call    cs:__imp_WindowsCreateStringReference
0x180014181  test    eax, eax
0x180014183  js      short loc_18001418E
0x180014185  mov     rax, rbx
0x180014188  add     rsp, 20h
0x18001418c  pop     rbx
0x18001418d  retn
0x18001418e  xor     r9d, r9d; lpArguments
0x180014191  xor     r8d, r8d; nNumberOfArguments
0x180014194  mov     edx, 1; dwExceptionFlags
0x180014199  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001419e  call    cs:__imp_RaiseException
0x1800141a4  jmp     short loc_180014185
```
