# Windows::Internal::StringReference::StringReference(ushort const (&)[14])

- ea: `0x1800146f0`
- end: `0x180014736`
- name: `??$?0$0O@@StringReference@Internal@Windows@@QEAA@AEAY0O@$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800199dc`
- `0x18001acfc`

## callees

- `0x1800146f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001472e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001472e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001470b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001470b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0xDu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800146f0  push    rbx
0x1800146f2  sub     rsp, 20h
0x1800146f6  mov     rax, rdx
0x1800146f9  lea     r8, [rcx+8]; hstringHeader
0x1800146fd  mov     rbx, rcx
0x180014700  mov     r9, rcx; string
0x180014703  mov     rcx, rax; sourceString
0x180014706  mov     edx, 0Dh; length
0x18001470b  call    cs:__imp_WindowsCreateStringReference
0x180014711  test    eax, eax
0x180014713  js      short loc_18001471E
0x180014715  mov     rax, rbx
0x180014718  add     rsp, 20h
0x18001471c  pop     rbx
0x18001471d  retn
0x18001471e  xor     r9d, r9d; lpArguments
0x180014721  xor     r8d, r8d; nNumberOfArguments
0x180014724  mov     edx, 1; dwExceptionFlags
0x180014729  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001472e  call    cs:__imp_RaiseException
0x180014734  jmp     short loc_180014715
```
