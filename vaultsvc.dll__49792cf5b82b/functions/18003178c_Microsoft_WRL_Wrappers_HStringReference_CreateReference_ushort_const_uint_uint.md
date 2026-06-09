# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003178c`
- end: `0x1800317cf`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180041b3c`
- `0x18004518c`

## callees

- `0x18003178c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800317c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800317c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800317a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800317a7`

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
    JUMPOUT(0x1800317CELL);
  }
}

```

## disassembly

```asm
0x18003178c  sub     rsp, 28h
0x180031790  mov     eax, r9d
0x180031793  mov     r10, rdx
0x180031796  cmp     r9d, r8d
0x180031799  jnb     short loc_1800317B6
0x18003179b  lea     r9, [rcx+18h]; string
0x18003179f  mov     r8, rcx; hstringHeader
0x1800317a2  mov     rcx, r10; sourceString
0x1800317a5  mov     edx, eax; length
0x1800317a7  call    cs:__imp_WindowsCreateStringReference
0x1800317ad  test    eax, eax
0x1800317af  js      short loc_1800317BC
0x1800317b1  add     rsp, 28h
0x1800317b5  retn
0x1800317b6  lea     eax, [r8-1]
0x1800317ba  jmp     short loc_18003179B
0x1800317bc  xor     r9d, r9d; lpArguments
0x1800317bf  xor     r8d, r8d; nNumberOfArguments
0x1800317c2  mov     ecx, eax; dwExceptionCode
0x1800317c4  lea     edx, [r9+1]; dwExceptionFlags
0x1800317c8  call    cs:__imp_RaiseException
```
