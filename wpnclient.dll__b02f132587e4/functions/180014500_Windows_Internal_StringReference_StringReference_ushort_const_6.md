# Windows::Internal::StringReference::StringReference(ushort const (&)[6])

- ea: `0x180014500`
- end: `0x180014546`
- name: `??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180018d90`
- `0x18001a1a8`
- `0x18001afb0`
- `0x18001e1a4`
- `0x18002d73c`

## callees

- `0x180014500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001453e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001453e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001451b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001451b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 5u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180014500  push    rbx
0x180014502  sub     rsp, 20h
0x180014506  mov     rax, rdx
0x180014509  lea     r8, [rcx+8]; hstringHeader
0x18001450d  mov     rbx, rcx
0x180014510  mov     r9, rcx; string
0x180014513  mov     rcx, rax; sourceString
0x180014516  mov     edx, 5; length
0x18001451b  call    cs:__imp_WindowsCreateStringReference
0x180014521  test    eax, eax
0x180014523  js      short loc_18001452E
0x180014525  mov     rax, rbx
0x180014528  add     rsp, 20h
0x18001452c  pop     rbx
0x18001452d  retn
0x18001452e  xor     r9d, r9d; lpArguments
0x180014531  xor     r8d, r8d; nNumberOfArguments
0x180014534  mov     edx, 1; dwExceptionFlags
0x180014539  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001453e  call    cs:__imp_RaiseException
0x180014544  jmp     short loc_180014525
```
