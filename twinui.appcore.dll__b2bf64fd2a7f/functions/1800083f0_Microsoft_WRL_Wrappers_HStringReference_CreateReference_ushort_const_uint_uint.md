# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800083f0`
- end: `0x180008434`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `68`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `27`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005f74`
- `0x180006420`
- `0x180006dac`
- `0x180006f30`
- `0x1800081e0`
- `0x18000876c`
- `0x180010680`
- `0x180010b00`
- `0x180011058`
- `0x180011c6c`
- `0x180017cd0`
- `0x18001d5ec`
- `0x18001e360`
- `0x18001e9f4`
- `0x18001ed80`
- `0x18001f0e0`
- `0x18001f350`
- `0x180024c0c`
- `0x1800347a0`
- `0x180052cc0`
- `0x18005c488`
- `0x18006d660`
- `0x18006edb0`
- `0x18006f230`
- `0x180070684`
- `0x180070828`
- `0x1800759f0`

## callees

- `0x1800083f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000842d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000842d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000840b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000840b`

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
    JUMPOUT(0x180008433LL);
  }
}

```

## disassembly

```asm
0x1800083f0  sub     rsp, 28h
0x1800083f4  mov     eax, r9d
0x1800083f7  mov     r10, rdx
0x1800083fa  cmp     r9d, r8d
0x1800083fd  jnb     short loc_18000841A
0x1800083ff  lea     r9, [rcx+18h]; string
0x180008403  mov     r8, rcx; hstringHeader
0x180008406  mov     rcx, r10; sourceString
0x180008409  mov     edx, eax; length
0x18000840b  call    cs:__imp_WindowsCreateStringReference
0x180008411  test    eax, eax
0x180008413  js      short loc_180008420
0x180008415  add     rsp, 28h
0x180008419  retn
0x18000841a  lea     eax, [r8-1]
0x18000841e  jmp     short loc_1800083FF
0x180008420  xor     r9d, r9d; lpArguments
0x180008423  xor     r8d, r8d; nNumberOfArguments
0x180008426  mov     edx, 1; dwExceptionFlags
0x18000842b  mov     ecx, eax; dwExceptionCode
0x18000842d  call    cs:__imp_RaiseException
```
