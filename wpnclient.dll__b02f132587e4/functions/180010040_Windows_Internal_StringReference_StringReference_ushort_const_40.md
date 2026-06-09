# Windows::Internal::StringReference::StringReference(ushort const (&)[40])

- ea: `0x180010040`
- end: `0x180010087`
- name: `??$?0$0CI@@StringReference@Internal@Windows@@QEAA@AEAY0CI@$$CBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[40])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cfac`

## callees

- `0x180010040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001007f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001007f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001005c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001005c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[40])
{
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Collections.ValueSet",
         0x27u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180010040  push    rbx
0x180010042  sub     rsp, 20h
0x180010046  mov     rbx, rcx
0x180010049  lea     r8, [rcx+8]; hstringHeader
0x18001004d  mov     r9, rcx; string
0x180010050  mov     edx, 27h ; '''; length
0x180010055  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18001005c  call    cs:__imp_WindowsCreateStringReference
0x180010062  test    eax, eax
0x180010064  js      short loc_18001006F
0x180010066  mov     rax, rbx
0x180010069  add     rsp, 20h
0x18001006d  pop     rbx
0x18001006e  retn
0x18001006f  xor     r9d, r9d; lpArguments
0x180010072  xor     r8d, r8d; nNumberOfArguments
0x180010075  mov     edx, 1; dwExceptionFlags
0x18001007a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001007f  call    cs:__imp_RaiseException
0x180010085  jmp     short loc_180010066
```
