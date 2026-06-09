# Windows::Internal::StringReference::StringReference(ushort const (&)[4])

- ea: `0x1800153b4`
- end: `0x1800153f9`
- name: `??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z`
- size: `69`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001afb0`
- `0x18001e1a4`
- `0x18001e5a0`

## callees

- `0x1800153b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800153f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800153f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800153cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800153cf`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 3u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800153b4  push    rbx
0x1800153b6  sub     rsp, 20h
0x1800153ba  mov     rax, rdx
0x1800153bd  lea     r8, [rcx+8]; hstringHeader
0x1800153c1  mov     rbx, rcx
0x1800153c4  mov     r9, rcx; string
0x1800153c7  mov     rcx, rax; sourceString
0x1800153ca  mov     edx, 3; length
0x1800153cf  call    cs:__imp_WindowsCreateStringReference
0x1800153d5  test    eax, eax
0x1800153d7  js      short loc_1800153E2
0x1800153d9  mov     rax, rbx
0x1800153dc  add     rsp, 20h
0x1800153e0  pop     rbx
0x1800153e1  retn
0x1800153e2  xor     r9d, r9d; lpArguments
0x1800153e5  xor     r8d, r8d; nNumberOfArguments
0x1800153e8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800153ed  lea     edx, [r9+1]; dwExceptionFlags
0x1800153f1  call    cs:__imp_RaiseException
0x1800153f7  jmp     short loc_1800153D9
```
