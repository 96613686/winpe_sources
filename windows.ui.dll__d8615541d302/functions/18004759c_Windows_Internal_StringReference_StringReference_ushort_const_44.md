# Windows::Internal::StringReference::StringReference(ushort const (&)[44])

- ea: `0x18004759c`
- end: `0x1800475e2`
- name: `??$?0$0CM@@StringReference@Internal@Windows@@QEAA@AEAY0CM@$$CBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[44])`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007dbe0`

## callees

- `0x18004759c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800475da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800475da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800475b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800475b8`

## string_xrefs

- `0x1800475b1`: `Windows.UI.Core.ComponentDisplayInformation`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[44])
{
  if ( WindowsCreateStringReference(
         L"Windows.UI.Core.ComponentDisplayInformation",
         0x2Bu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18004759c  push    rbx
0x18004759e  sub     rsp, 20h
0x1800475a2  mov     rbx, rcx
0x1800475a5  lea     r8, [rcx+8]; hstringHeader
0x1800475a9  mov     r9, rcx; string
0x1800475ac  mov     edx, 2Bh ; '+'; length
0x1800475b1  lea     rcx, ?RuntimeClass_Windows_UI_Core_ComponentDisplayInformation@@3QBGB; "Windows.UI.Core.ComponentDisplayInforma"...
0x1800475b8  call    cs:__imp_WindowsCreateStringReference
0x1800475be  test    eax, eax
0x1800475c0  js      short loc_1800475CB
0x1800475c2  mov     rax, rbx
0x1800475c5  add     rsp, 20h
0x1800475c9  pop     rbx
0x1800475ca  retn
0x1800475cb  xor     r9d, r9d; lpArguments
0x1800475ce  xor     r8d, r8d; nNumberOfArguments
0x1800475d1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800475d6  lea     edx, [r9+1]; dwExceptionFlags
0x1800475da  call    cs:__imp_RaiseException
0x1800475e0  jmp     short loc_1800475C2
```
