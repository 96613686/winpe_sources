# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001478c`
- end: `0x1800147cf`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010a54`
- `0x180010f1c`
- `0x180018bb8`
- `0x18001c5c0`
- `0x18001d4cc`
- `0x18001dccc`
- `0x18001e528`
- `0x18002e190`
- `0x18002e480`
- `0x18002ec5c`
- `0x18002f7e4`
- `0x1800300f0`

## callees

- `0x18001478c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800147c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800147c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800147a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800147a7`

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
    JUMPOUT(0x1800147CELL);
  }
}

```

## disassembly

```asm
0x18001478c  sub     rsp, 28h
0x180014790  mov     eax, r9d
0x180014793  mov     r10, rdx
0x180014796  cmp     r9d, r8d
0x180014799  jnb     short loc_1800147B6
0x18001479b  lea     r9, [rcx+18h]; string
0x18001479f  mov     r8, rcx; hstringHeader
0x1800147a2  mov     rcx, r10; sourceString
0x1800147a5  mov     edx, eax; length
0x1800147a7  call    cs:__imp_WindowsCreateStringReference
0x1800147ad  test    eax, eax
0x1800147af  js      short loc_1800147BC
0x1800147b1  add     rsp, 28h
0x1800147b5  retn
0x1800147b6  lea     eax, [r8-1]
0x1800147ba  jmp     short loc_18001479B
0x1800147bc  xor     r9d, r9d; lpArguments
0x1800147bf  xor     r8d, r8d; nNumberOfArguments
0x1800147c2  mov     ecx, eax; dwExceptionCode
0x1800147c4  lea     edx, [r9+1]; dwExceptionFlags
0x1800147c8  call    cs:__imp_RaiseException
```
