# Windows::Internal::StringReference::StringReference(ushort const (&)[5])

- ea: `0x180014740`
- end: `0x180014786`
- name: `??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001acfc`
- `0x18001df20`
- `0x18001e5a0`
- `0x18001e9a4`

## callees

- `0x180014740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001477e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001477e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001475b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001475b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 4u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180014740  push    rbx
0x180014742  sub     rsp, 20h
0x180014746  mov     rax, rdx
0x180014749  lea     r8, [rcx+8]; hstringHeader
0x18001474d  mov     rbx, rcx
0x180014750  mov     r9, rcx; string
0x180014753  mov     rcx, rax; sourceString
0x180014756  mov     edx, 4; length
0x18001475b  call    cs:__imp_WindowsCreateStringReference
0x180014761  test    eax, eax
0x180014763  js      short loc_18001476E
0x180014765  mov     rax, rbx
0x180014768  add     rsp, 20h
0x18001476c  pop     rbx
0x18001476d  retn
0x18001476e  xor     r9d, r9d; lpArguments
0x180014771  xor     r8d, r8d; nNumberOfArguments
0x180014774  mov     edx, 1; dwExceptionFlags
0x180014779  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001477e  call    cs:__imp_RaiseException
0x180014784  jmp     short loc_180014765
```
