# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180030224`
- end: `0x18003025a`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `54`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002f8f8`
- `0x18002f964`
- `0x180030b0c`
- `0x180030cb0`
- `0x180030e24`

## callees

- `0x180030224`
- `0x180030fcc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030243`

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
  int v6; // edx
  unsigned int v7; // r8d

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180030224  sub     rsp, 28h
0x180030228  mov     eax, r9d
0x18003022b  mov     r10, rdx
0x18003022e  cmp     r9d, r8d
0x180030231  jb      short loc_180030237
0x180030233  lea     eax, [r8-1]
0x180030237  lea     r9, [rcx+18h]; string
0x18003023b  mov     r8, rcx; hstringHeader
0x18003023e  mov     rcx, r10; sourceString
0x180030241  mov     edx, eax; length
0x180030243  call    cs:__imp_WindowsCreateStringReference
0x180030249  test    eax, eax
0x18003024b  jns     short loc_180030255
0x18003024d  mov     ecx, eax; this
0x18003024f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180030254  int     3; Trap to Debugger
0x180030255  add     rsp, 28h
0x180030259  retn
```
