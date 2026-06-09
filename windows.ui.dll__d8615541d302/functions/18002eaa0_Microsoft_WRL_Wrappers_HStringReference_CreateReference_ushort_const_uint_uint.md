# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18002eaa0`
- end: `0x18002eae4`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `68`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `29`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800243fc`
- `0x180036820`
- `0x1800500bc`
- `0x180050380`
- `0x1800508e4`
- `0x1800518cc`
- `0x18006e3b0`
- `0x180082870`
- `0x180096818`
- `0x18009ae28`
- `0x18009d5b8`
- `0x18009e730`
- `0x18009ffc4`
- `0x1800a0f78`
- `0x1800a3374`
- `0x1800b2624`
- `0x1800b7190`
- `0x1800bb1f0`
- `0x1800bc260`
- `0x1800bded0`
- `0x1800be16c`
- `0x1800be790`
- `0x1800bf630`
- `0x1800bfd30`
- `0x1800bfda0`
- `0x1800c35f8`
- `0x1800c4704`
- `0x1800c48f8`
- `0x1800c6c20`

## callees

- `0x18002eaa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002eadd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002eadd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002eabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002eabb`

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
    JUMPOUT(0x18002EAE3LL);
  }
}

```

## disassembly

```asm
0x18002eaa0  sub     rsp, 28h
0x18002eaa4  mov     eax, r9d
0x18002eaa7  mov     r10, rdx
0x18002eaaa  cmp     r9d, r8d
0x18002eaad  jnb     short loc_18002EACA
0x18002eaaf  lea     r9, [rcx+18h]; string
0x18002eab3  mov     r8, rcx; hstringHeader
0x18002eab6  mov     rcx, r10; sourceString
0x18002eab9  mov     edx, eax; length
0x18002eabb  call    cs:__imp_WindowsCreateStringReference
0x18002eac1  test    eax, eax
0x18002eac3  js      short loc_18002EAD0
0x18002eac5  add     rsp, 28h
0x18002eac9  retn
0x18002eaca  lea     eax, [r8-1]
0x18002eace  jmp     short loc_18002EAAF
0x18002ead0  xor     r9d, r9d; lpArguments
0x18002ead3  xor     r8d, r8d; nNumberOfArguments
0x18002ead6  mov     edx, 1; dwExceptionFlags
0x18002eadb  mov     ecx, eax; dwExceptionCode
0x18002eadd  call    cs:__imp_RaiseException
```
