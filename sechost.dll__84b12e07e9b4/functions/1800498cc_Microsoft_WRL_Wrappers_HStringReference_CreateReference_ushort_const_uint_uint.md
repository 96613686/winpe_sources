# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800498cc`
- end: `0x18004990d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004834c`
- `0x180048468`
- `0x1800492d8`
- `0x180049688`
- `0x180049914`
- `0x18004a380`

## callees

- `0x1800498cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049901`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800498eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800498eb`

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
0x1800498cc  sub     rsp, 28h
0x1800498d0  mov     eax, r9d
0x1800498d3  mov     r10, rdx
0x1800498d6  cmp     r9d, r8d
0x1800498d9  jb      short loc_1800498DF
0x1800498db  lea     eax, [r8-1]
0x1800498df  lea     r9, [rcx+18h]; string
0x1800498e3  mov     r8, rcx; hstringHeader
0x1800498e6  mov     rcx, r10; sourceString
0x1800498e9  mov     edx, eax; length
0x1800498eb  call    cs:__imp_WindowsCreateStringReference
0x1800498f1  test    eax, eax
0x1800498f3  jns     short loc_180049908
0x1800498f5  xor     r9d, r9d; lpArguments
0x1800498f8  xor     r8d, r8d; nNumberOfArguments
0x1800498fb  mov     ecx, eax; dwExceptionCode
0x1800498fd  lea     edx, [r9+1]; dwExceptionFlags
0x180049901  call    cs:__imp_RaiseException
0x180049907  int     3; Trap to Debugger
0x180049908  add     rsp, 28h
0x18004990c  retn
```
