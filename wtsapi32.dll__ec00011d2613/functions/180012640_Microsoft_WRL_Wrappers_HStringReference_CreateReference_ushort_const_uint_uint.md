# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180012640`
- end: `0x180012681`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012230`
- `0x180013600`
- `0x180013990`
- `0x180013c70`
- `0x180013e30`

## callees

- `0x180012640`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180012675`
- `KERNEL32!RaiseException` at `0x180012675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001265f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001265f`

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
0x180012640  sub     rsp, 28h
0x180012644  mov     eax, r9d
0x180012647  mov     r10, rdx
0x18001264a  cmp     r9d, r8d
0x18001264d  jb      short loc_180012653
0x18001264f  lea     eax, [r8-1]
0x180012653  lea     r9, [rcx+18h]; string
0x180012657  mov     r8, rcx; hstringHeader
0x18001265a  mov     rcx, r10; sourceString
0x18001265d  mov     edx, eax; length
0x18001265f  call    cs:__imp_WindowsCreateStringReference
0x180012665  test    eax, eax
0x180012667  jns     short loc_18001267C
0x180012669  xor     r9d, r9d; lpArguments
0x18001266c  xor     r8d, r8d; nNumberOfArguments
0x18001266f  mov     ecx, eax; dwExceptionCode
0x180012671  lea     edx, [r9+1]; dwExceptionFlags
0x180012675  call    cs:__imp_RaiseException
0x18001267b  int     3; Trap to Debugger
0x18001267c  add     rsp, 28h
0x180012680  retn
```
