# Windows::Internal::StringReference::StringReference(ushort const (&)[103])

- ea: `0x18005a11c`
- end: `0x18005a160`
- name: `??$?0$0GH@@StringReference@Internal@Windows@@QEAA@AEAY0GH@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[103])`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059c90`

## callees

- `0x18005a11c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005a151`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005a151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a138`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a138`

## string_xrefs

- `0x18005a131`: `The IDCompositionVisual has already been configured, and may not longer be changed on this CoreWindow.`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[103])
{
  if ( WindowsCreateStringReference(
         L"The IDCompositionVisual has already been configured, and may not longer be changed on this CoreWindow.",
         0x66u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18005a11c  push    rbx
0x18005a11e  sub     rsp, 20h
0x18005a122  mov     rbx, rcx
0x18005a125  lea     r8, [rcx+8]; hstringHeader
0x18005a129  mov     r9, rcx; string
0x18005a12c  mov     edx, 66h ; 'f'; length
0x18005a131  lea     rcx, aTheIdcompositi; "The IDCompositionVisual has already bee"...
0x18005a138  call    cs:__imp_WindowsCreateStringReference
0x18005a13e  test    eax, eax
0x18005a140  jns     short loc_18005A157
0x18005a142  xor     r9d, r9d; lpArguments
0x18005a145  xor     r8d, r8d; nNumberOfArguments
0x18005a148  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005a14d  lea     edx, [r9+1]; dwExceptionFlags
0x18005a151  call    cs:__imp_RaiseException
0x18005a157  mov     rax, rbx
0x18005a15a  add     rsp, 20h
0x18005a15e  pop     rbx
0x18005a15f  retn
```
