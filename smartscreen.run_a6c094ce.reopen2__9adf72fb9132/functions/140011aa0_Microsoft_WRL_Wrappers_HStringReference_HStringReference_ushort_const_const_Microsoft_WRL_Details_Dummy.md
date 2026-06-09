# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x140011aa0`
- end: `0x140011b2e`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f2ac`
- `0x14002063c`
- `0x140036548`
- `0x1400365e0`

## callees

- `0x140011aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011adf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011b12`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011adf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140011b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140011af6`

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
  if ( v5 <= 0xFFFFFFFF )
    goto LABEL_5;
  do
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
LABEL_5:
    ;
  }
  while ( (int)v5 + 1 < (unsigned int)v5 );
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
0x140011aa0  mov     [rsp+arg_0], rbx
0x140011aa5  push    rdi
0x140011aa6  sub     rsp, 20h
0x140011aaa  lea     r9, [rcx+18h]
0x140011aae  xor     edi, edi
0x140011ab0  mov     [r9], rdi
0x140011ab3  mov     rbx, rcx
0x140011ab6  mov     rcx, [rdx]
0x140011ab9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140011abd  inc     rdx
0x140011ac0  cmp     [rcx+rdx*2], di
0x140011ac4  jnz     short loc_140011ABD
0x140011ac6  mov     eax, 0FFFFFFFFh
0x140011acb  cmp     rdx, rax
0x140011ace  jbe     short loc_140011AEC
0x140011ad0  xor     r9d, r9d; lpArguments
0x140011ad3  xor     r8d, r8d; nNumberOfArguments
0x140011ad6  mov     ecx, 80070216h; dwExceptionCode
0x140011adb  lea     edx, [r9+1]; dwExceptionFlags
0x140011adf  call    cs:__imp_RaiseException
0x140011ae6  nop     dword ptr [rax+rax+00h]
0x140011aeb  int     3; Trap to Debugger
0x140011aec  lea     eax, [rdx+1]
0x140011aef  cmp     eax, edx
0x140011af1  jb      short loc_140011AD0
0x140011af3  mov     r8, rbx; hstringHeader
0x140011af6  call    cs:__imp_WindowsCreateStringReference
0x140011afd  nop     dword ptr [rax+rax+00h]
0x140011b02  test    eax, eax
0x140011b04  jns     short loc_140011B1F
0x140011b06  xor     r9d, r9d; lpArguments
0x140011b09  xor     r8d, r8d; nNumberOfArguments
0x140011b0c  mov     ecx, eax; dwExceptionCode
0x140011b0e  lea     edx, [r9+1]; dwExceptionFlags
0x140011b12  call    cs:__imp_RaiseException
0x140011b19  nop     dword ptr [rax+rax+00h]
0x140011b1e  int     3; Trap to Debugger
0x140011b1f  mov     rax, rbx
0x140011b22  mov     rbx, [rsp+28h+arg_0]
0x140011b27  add     rsp, 20h
0x140011b2b  pop     rdi
0x140011b2c  retn
```
