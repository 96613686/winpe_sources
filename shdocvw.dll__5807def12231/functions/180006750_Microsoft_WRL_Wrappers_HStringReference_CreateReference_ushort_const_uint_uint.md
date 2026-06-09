# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180006750`
- end: `0x180006792`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `66`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005b0c`
- `0x1800060a8`
- `0x180012420`
- `0x18001d120`
- `0x180023438`

## callees

- `0x180006750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006786`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000676f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000676f`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180006750  sub     rsp, 28h
0x180006754  mov     eax, r9d
0x180006757  mov     r10, rdx
0x18000675a  cmp     r9d, r8d
0x18000675d  jb      short loc_180006763
0x18000675f  lea     eax, [r8-1]
0x180006763  lea     r9, [rcx+18h]; string
0x180006767  mov     r8, rcx; hstringHeader
0x18000676a  mov     rcx, r10; sourceString
0x18000676d  mov     edx, eax; length
0x18000676f  call    cs:__imp_WindowsCreateStringReference
0x180006775  test    eax, eax
0x180006777  jns     short loc_18000678D
0x180006779  xor     r9d, r9d; lpArguments
0x18000677c  xor     r8d, r8d; nNumberOfArguments
0x18000677f  mov     edx, 1; dwExceptionFlags
0x180006784  mov     ecx, eax; dwExceptionCode
0x180006786  call    cs:__imp_RaiseException
0x18000678c  int     3; Trap to Debugger
0x18000678d  add     rsp, 28h
0x180006791  retn
```
