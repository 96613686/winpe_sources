# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x140013568`
- end: `0x1400135b6`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002063c`

## callees

- `0x140013568`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400135a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400135a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013587`

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
0x140013568  sub     rsp, 28h
0x14001356c  mov     eax, r9d
0x14001356f  mov     r10, rdx
0x140013572  cmp     r9d, r8d
0x140013575  jb      short loc_14001357B
0x140013577  lea     eax, [r8-1]
0x14001357b  lea     r9, [rcx+18h]; string
0x14001357f  mov     r8, rcx; hstringHeader
0x140013582  mov     rcx, r10; sourceString
0x140013585  mov     edx, eax; length
0x140013587  call    cs:__imp_WindowsCreateStringReference
0x14001358e  nop     dword ptr [rax+rax+00h]
0x140013593  test    eax, eax
0x140013595  jns     short loc_1400135B0
0x140013597  xor     r9d, r9d; lpArguments
0x14001359a  xor     r8d, r8d; nNumberOfArguments
0x14001359d  mov     ecx, eax; dwExceptionCode
0x14001359f  lea     edx, [r9+1]; dwExceptionFlags
0x1400135a3  call    cs:__imp_RaiseException
0x1400135aa  nop     dword ptr [rax+rax+00h]
0x1400135af  int     3; Trap to Debugger
0x1400135b0  add     rsp, 28h
0x1400135b4  retn
```
