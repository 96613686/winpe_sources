# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180013740`
- end: `0x1800137bc`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d4cc`
- `0x18001dccc`

## callees

- `0x180013740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001378b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800137b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001378b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800137b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013795`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013795`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  HSTRING *v2; // r9
  const WCHAR *v4; // rcx
  unsigned __int64 v5; // rdx
  HRESULT StringReference; // eax

  v2 = (HSTRING *)&a1[1];
  a1[1].Reserved.Reserved1 = 0;
  v4 = *a2;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  if ( v5 > 0xFFFFFFFF || (int)v5 + 1 < (unsigned int)v5 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(v4, v5, a1, v2);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    JUMPOUT(0x1800137BBLL);
  }
  return a1;
}

```

## disassembly

```asm
0x180013740  push    rbx
0x180013742  sub     rsp, 20h
0x180013746  lea     r9, [rcx+18h]; string
0x18001374a  mov     rbx, rcx
0x18001374d  mov     qword ptr [r9], 0
0x180013754  mov     rcx, [rdx]; sourceString
0x180013757  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18001375e  xchg    ax, ax
0x180013760  inc     rdx; length
0x180013763  cmp     word ptr [rcx+rdx*2], 0
0x180013768  jnz     short loc_180013760
0x18001376a  mov     eax, 0FFFFFFFFh
0x18001376f  cmp     rdx, rax
0x180013772  ja      short loc_18001377B
0x180013774  lea     eax, [rdx+1]
0x180013777  cmp     eax, edx
0x180013779  jnb     short loc_180013792
0x18001377b  xor     r9d, r9d; lpArguments
0x18001377e  xor     r8d, r8d; nNumberOfArguments
0x180013781  mov     edx, 1; dwExceptionFlags
0x180013786  mov     ecx, 80070216h; dwExceptionCode
0x18001378b  call    cs:__imp_RaiseException
0x180013791  int     3; Trap to Debugger
0x180013792  mov     r8, rbx; hstringHeader
0x180013795  call    cs:__imp_WindowsCreateStringReference
0x18001379b  test    eax, eax
0x18001379d  js      short loc_1800137A8
0x18001379f  mov     rax, rbx
0x1800137a2  add     rsp, 20h
0x1800137a6  pop     rbx
0x1800137a7  retn
0x1800137a8  xor     r9d, r9d; lpArguments
0x1800137ab  xor     r8d, r8d; nNumberOfArguments
0x1800137ae  mov     edx, 1; dwExceptionFlags
0x1800137b3  mov     ecx, eax; dwExceptionCode
0x1800137b5  call    cs:__imp_RaiseException
```
