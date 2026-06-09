# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000b158`
- end: `0x18000b1a6`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ac90`

## callees

- `0x18000b158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b193`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b177`

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
0x18000b158  sub     rsp, 28h
0x18000b15c  mov     eax, r9d
0x18000b15f  mov     r10, rdx
0x18000b162  cmp     r9d, r8d
0x18000b165  jb      short loc_18000B16B
0x18000b167  lea     eax, [r8-1]
0x18000b16b  lea     r9, [rcx+18h]; string
0x18000b16f  mov     r8, rcx; hstringHeader
0x18000b172  mov     rcx, r10; sourceString
0x18000b175  mov     edx, eax; length
0x18000b177  call    cs:__imp_WindowsCreateStringReference
0x18000b17e  nop     dword ptr [rax+rax+00h]
0x18000b183  test    eax, eax
0x18000b185  jns     short loc_18000B1A0
0x18000b187  xor     r9d, r9d; lpArguments
0x18000b18a  xor     r8d, r8d; nNumberOfArguments
0x18000b18d  mov     ecx, eax; dwExceptionCode
0x18000b18f  lea     edx, [r9+1]; dwExceptionFlags
0x18000b193  call    cs:__imp_RaiseException
0x18000b19a  nop     dword ptr [rax+rax+00h]
0x18000b19f  int     3; Trap to Debugger
0x18000b1a0  add     rsp, 28h
0x18000b1a4  retn
```
