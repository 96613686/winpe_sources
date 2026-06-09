# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x140012a84`
- end: `0x140012ac5`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001e228`
- `0x14001f508`

## callees

- `0x140012a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012ab9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012ab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012aa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012aa3`

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
0x140012a84  sub     rsp, 28h
0x140012a88  mov     eax, r9d
0x140012a8b  mov     r10, rdx
0x140012a8e  cmp     r9d, r8d
0x140012a91  jb      short loc_140012A97
0x140012a93  lea     eax, [r8-1]
0x140012a97  lea     r9, [rcx+18h]; string
0x140012a9b  mov     r8, rcx; hstringHeader
0x140012a9e  mov     rcx, r10; sourceString
0x140012aa1  mov     edx, eax; length
0x140012aa3  call    cs:__imp_WindowsCreateStringReference
0x140012aa9  test    eax, eax
0x140012aab  jns     short loc_140012AC0
0x140012aad  xor     r9d, r9d; lpArguments
0x140012ab0  xor     r8d, r8d; nNumberOfArguments
0x140012ab3  mov     ecx, eax; dwExceptionCode
0x140012ab5  lea     edx, [r9+1]; dwExceptionFlags
0x140012ab9  call    cs:__imp_RaiseException
0x140012abf  int     3; Trap to Debugger
0x140012ac0  add     rsp, 28h
0x140012ac4  retn
```
