# Windows::Internal::StringReference::StringReference(ushort const (&)[7])

- ea: `0x180014550`
- end: `0x180014596`
- name: `??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001780c`
- `0x180019d04`
- `0x18001afb0`
- `0x18001e1a4`

## callees

- `0x180014550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001458e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001458e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001456b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001456b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 6u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180014550  push    rbx
0x180014552  sub     rsp, 20h
0x180014556  mov     rax, rdx
0x180014559  lea     r8, [rcx+8]; hstringHeader
0x18001455d  mov     rbx, rcx
0x180014560  mov     r9, rcx; string
0x180014563  mov     rcx, rax; sourceString
0x180014566  mov     edx, 6; length
0x18001456b  call    cs:__imp_WindowsCreateStringReference
0x180014571  test    eax, eax
0x180014573  js      short loc_18001457E
0x180014575  mov     rax, rbx
0x180014578  add     rsp, 20h
0x18001457c  pop     rbx
0x18001457d  retn
0x18001457e  xor     r9d, r9d; lpArguments
0x180014581  xor     r8d, r8d; nNumberOfArguments
0x180014584  mov     edx, 1; dwExceptionFlags
0x180014589  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001458e  call    cs:__imp_RaiseException
0x180014594  jmp     short loc_180014575
```
