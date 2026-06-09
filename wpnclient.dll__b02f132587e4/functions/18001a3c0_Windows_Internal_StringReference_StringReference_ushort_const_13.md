# Windows::Internal::StringReference::StringReference(ushort const (&)[13])

- ea: `0x18001a3c0`
- end: `0x18001a403`
- name: `??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a1a8`
- `0x18001e5a0`

## callees

- `0x18001a3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001a3f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001a3f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a3db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a3db`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0xCu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001a3c0  push    rbx
0x18001a3c2  sub     rsp, 20h
0x18001a3c6  mov     rax, rdx
0x18001a3c9  lea     r8, [rcx+8]; hstringHeader
0x18001a3cd  mov     rbx, rcx
0x18001a3d0  mov     r9, rcx; string
0x18001a3d3  mov     rcx, rax; sourceString
0x18001a3d6  mov     edx, 0Ch; length
0x18001a3db  call    cs:__imp_WindowsCreateStringReference
0x18001a3e1  test    eax, eax
0x18001a3e3  jns     short loc_18001A3FA
0x18001a3e5  xor     r9d, r9d; lpArguments
0x18001a3e8  xor     r8d, r8d; nNumberOfArguments
0x18001a3eb  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001a3f0  lea     edx, [r9+1]; dwExceptionFlags
0x18001a3f4  call    cs:__imp_RaiseException
0x18001a3fa  mov     rax, rbx
0x18001a3fd  add     rsp, 20h
0x18001a401  pop     rbx
0x18001a402  retn
```
