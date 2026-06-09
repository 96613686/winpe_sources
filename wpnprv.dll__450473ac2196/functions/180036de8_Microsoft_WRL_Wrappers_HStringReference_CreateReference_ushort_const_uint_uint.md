# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180036de8`
- end: `0x180036e29`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007fa6c`
- `0x180080464`
- `0x1800807c4`
- `0x1800812c4`
- `0x18008191c`
- `0x1800859dc`
- `0x180085d68`

## callees

- `0x180036de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036e1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036e07`

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
0x180036de8  sub     rsp, 28h
0x180036dec  mov     eax, r9d
0x180036def  mov     r10, rdx
0x180036df2  cmp     r9d, r8d
0x180036df5  jb      short loc_180036DFB
0x180036df7  lea     eax, [r8-1]
0x180036dfb  lea     r9, [rcx+18h]; string
0x180036dff  mov     r8, rcx; hstringHeader
0x180036e02  mov     rcx, r10; sourceString
0x180036e05  mov     edx, eax; length
0x180036e07  call    cs:__imp_WindowsCreateStringReference
0x180036e0d  test    eax, eax
0x180036e0f  jns     short loc_180036E24
0x180036e11  xor     r9d, r9d; lpArguments
0x180036e14  xor     r8d, r8d; nNumberOfArguments
0x180036e17  mov     ecx, eax; dwExceptionCode
0x180036e19  lea     edx, [r9+1]; dwExceptionFlags
0x180036e1d  call    cs:__imp_RaiseException
0x180036e23  int     3; Trap to Debugger
0x180036e24  add     rsp, 28h
0x180036e28  retn
```
