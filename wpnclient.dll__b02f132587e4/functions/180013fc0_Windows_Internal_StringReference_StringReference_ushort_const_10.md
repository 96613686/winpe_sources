# Windows::Internal::StringReference::StringReference(ushort const (&)[10])

- ea: `0x180013fc0`
- end: `0x180014006`
- name: `??$?0$09@StringReference@Internal@Windows@@QEAA@AEAY09$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800199dc`
- `0x180019b4c`
- `0x18001a40c`
- `0x18001acfc`
- `0x18001afb0`

## callees

- `0x180013fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013ffe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013fdb`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 9u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180013fc0  push    rbx
0x180013fc2  sub     rsp, 20h
0x180013fc6  mov     rax, rdx
0x180013fc9  lea     r8, [rcx+8]; hstringHeader
0x180013fcd  mov     rbx, rcx
0x180013fd0  mov     r9, rcx; string
0x180013fd3  mov     rcx, rax; sourceString
0x180013fd6  mov     edx, 9; length
0x180013fdb  call    cs:__imp_WindowsCreateStringReference
0x180013fe1  test    eax, eax
0x180013fe3  js      short loc_180013FEE
0x180013fe5  mov     rax, rbx
0x180013fe8  add     rsp, 20h
0x180013fec  pop     rbx
0x180013fed  retn
0x180013fee  xor     r9d, r9d; lpArguments
0x180013ff1  xor     r8d, r8d; nNumberOfArguments
0x180013ff4  mov     edx, 1; dwExceptionFlags
0x180013ff9  mov     ecx, 0C000000Dh; dwExceptionCode
0x180013ffe  call    cs:__imp_RaiseException
0x180014004  jmp     short loc_180013FE5
```
