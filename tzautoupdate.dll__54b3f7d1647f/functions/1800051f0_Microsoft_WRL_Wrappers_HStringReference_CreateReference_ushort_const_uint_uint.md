# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800051f0`
- end: `0x180005231`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800031fc`
- `0x18000bf20`
- `0x18000c4e0`
- `0x1800117d0`
- `0x1800140a0`
- `0x180015a3c`
- `0x180015f68`

## callees

- `0x1800051f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005225`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000520f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000520f`

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
0x1800051f0  sub     rsp, 28h
0x1800051f4  mov     eax, r9d
0x1800051f7  mov     r10, rdx
0x1800051fa  cmp     r9d, r8d
0x1800051fd  jb      short loc_180005203
0x1800051ff  lea     eax, [r8-1]
0x180005203  lea     r9, [rcx+18h]; string
0x180005207  mov     r8, rcx; hstringHeader
0x18000520a  mov     rcx, r10; sourceString
0x18000520d  mov     edx, eax; length
0x18000520f  call    cs:__imp_WindowsCreateStringReference
0x180005215  test    eax, eax
0x180005217  jns     short loc_18000522C
0x180005219  xor     r9d, r9d; lpArguments
0x18000521c  xor     r8d, r8d; nNumberOfArguments
0x18000521f  mov     ecx, eax; dwExceptionCode
0x180005221  lea     edx, [r9+1]; dwExceptionFlags
0x180005225  call    cs:__imp_RaiseException
0x18000522b  int     3; Trap to Debugger
0x18000522c  add     rsp, 28h
0x180005230  retn
```
