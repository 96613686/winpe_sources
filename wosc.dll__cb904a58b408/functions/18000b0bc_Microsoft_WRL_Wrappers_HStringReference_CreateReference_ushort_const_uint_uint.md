# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000b0bc`
- end: `0x18000b0fd`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `34`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006b9c`
- `0x18000b5d0`
- `0x180016a14`
- `0x180017714`
- `0x180017a08`
- `0x180017c50`
- `0x180024cd0`
- `0x180024dec`
- `0x180029cc8`
- `0x18002ca40`
- `0x18002d314`
- `0x18002db48`
- `0x18002eb88`
- `0x18002f094`
- `0x180030600`
- `0x180030dc0`
- `0x180031d54`
- `0x1800321f0`
- `0x180032458`
- `0x180032674`
- `0x18003c3e0`
- `0x18003cd38`
- `0x180040a58`
- `0x1800412f0`
- `0x180041f84`
- `0x180042404`
- `0x180042c7c`
- `0x180047030`
- `0x1800482b4`
- `0x18004b8a4`
- `0x18004bc1c`
- `0x18004d7a0`
- `0x180050b28`
- `0x180050fb0`

## callees

- `0x18000b0bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b0db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b0db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b0f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b0f1`

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
0x18000b0bc  sub     rsp, 28h
0x18000b0c0  mov     eax, r9d
0x18000b0c3  mov     r10, rdx
0x18000b0c6  cmp     r9d, r8d
0x18000b0c9  jb      short loc_18000B0CF
0x18000b0cb  lea     eax, [r8-1]
0x18000b0cf  lea     r9, [rcx+18h]; string
0x18000b0d3  mov     r8, rcx; hstringHeader
0x18000b0d6  mov     rcx, r10; sourceString
0x18000b0d9  mov     edx, eax; length
0x18000b0db  call    cs:__imp_WindowsCreateStringReference
0x18000b0e1  test    eax, eax
0x18000b0e3  jns     short loc_18000B0F8
0x18000b0e5  xor     r9d, r9d; lpArguments
0x18000b0e8  xor     r8d, r8d; nNumberOfArguments
0x18000b0eb  mov     ecx, eax; dwExceptionCode
0x18000b0ed  lea     edx, [r9+1]; dwExceptionFlags
0x18000b0f1  call    cs:__imp_RaiseException
0x18000b0f7  int     3; Trap to Debugger
0x18000b0f8  add     rsp, 28h
0x18000b0fc  retn
```
