# Windows::Internal::StringReference::StringReference(ushort const (&)[125])

- ea: `0x18005a0d0`
- end: `0x18005a114`
- name: `??$?0$0HN@@StringReference@Internal@Windows@@QEAA@AEAY0HN@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[125])`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059c90`

## callees

- `0x18005a0d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005a105`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005a105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a0ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a0ec`

## string_xrefs

- `0x18005a0e5`: `A Windows.UI.Composition.Visual has already been configured, and DirectComposition may no longer be used on this CoreWindow.`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[125])
{
  if ( WindowsCreateStringReference(
         L"A Windows.UI.Composition.Visual has already been configured, and DirectComposition may no longer be used on this CoreWindow.",
         0x7Cu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18005a0d0  push    rbx
0x18005a0d2  sub     rsp, 20h
0x18005a0d6  mov     rbx, rcx
0x18005a0d9  lea     r8, [rcx+8]; hstringHeader
0x18005a0dd  mov     r9, rcx; string
0x18005a0e0  mov     edx, 7Ch ; '|'; length
0x18005a0e5  lea     rcx, aAWindowsUiComp; "A Windows.UI.Composition.Visual has alr"...
0x18005a0ec  call    cs:__imp_WindowsCreateStringReference
0x18005a0f2  test    eax, eax
0x18005a0f4  jns     short loc_18005A10B
0x18005a0f6  xor     r9d, r9d; lpArguments
0x18005a0f9  xor     r8d, r8d; nNumberOfArguments
0x18005a0fc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005a101  lea     edx, [r9+1]; dwExceptionFlags
0x18005a105  call    cs:__imp_RaiseException
0x18005a10b  mov     rax, rbx
0x18005a10e  add     rsp, 20h
0x18005a112  pop     rbx
0x18005a113  retn
```
