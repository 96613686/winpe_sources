# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1400111a8`
- end: `0x140011223`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `123`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f508`
- `0x140035018`
- `0x1400350b0`

## callees

- `0x1400111a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400111e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001120e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400111e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001120e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400111f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400111f8`

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
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x1400111a8  mov     [rsp+arg_0], rbx
0x1400111ad  push    rdi
0x1400111ae  sub     rsp, 20h
0x1400111b2  lea     r9, [rcx+18h]; string
0x1400111b6  xor     edi, edi
0x1400111b8  mov     [r9], rdi
0x1400111bb  mov     rbx, rcx
0x1400111be  mov     rcx, [rdx]; sourceString
0x1400111c1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400111c5  inc     rdx; length
0x1400111c8  cmp     [rcx+rdx*2], di
0x1400111cc  jnz     short loc_1400111C5
0x1400111ce  mov     eax, 0FFFFFFFFh
0x1400111d3  cmp     rdx, rax
0x1400111d6  jbe     short loc_1400111EE
0x1400111d8  xor     r9d, r9d; lpArguments
0x1400111db  xor     r8d, r8d; nNumberOfArguments
0x1400111de  mov     ecx, 80070216h; dwExceptionCode
0x1400111e3  lea     edx, [r9+1]; dwExceptionFlags
0x1400111e7  call    cs:__imp_RaiseException
0x1400111ed  int     3; Trap to Debugger
0x1400111ee  lea     eax, [rdx+1]
0x1400111f1  cmp     eax, edx
0x1400111f3  jb      short loc_1400111D8
0x1400111f5  mov     r8, rbx; hstringHeader
0x1400111f8  call    cs:__imp_WindowsCreateStringReference
0x1400111fe  test    eax, eax
0x140011200  jns     short loc_140011215
0x140011202  xor     r9d, r9d; lpArguments
0x140011205  xor     r8d, r8d; nNumberOfArguments
0x140011208  mov     ecx, eax; dwExceptionCode
0x14001120a  lea     edx, [r9+1]; dwExceptionFlags
0x14001120e  call    cs:__imp_RaiseException
0x140011214  int     3; Trap to Debugger
0x140011215  mov     rax, rbx
0x140011218  mov     rbx, [rsp+28h+arg_0]
0x14001121d  add     rsp, 20h
0x140011221  pop     rdi
0x140011222  retn
```
