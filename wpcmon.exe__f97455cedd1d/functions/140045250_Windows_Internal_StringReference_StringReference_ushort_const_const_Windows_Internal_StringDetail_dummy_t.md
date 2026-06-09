# Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x140045250`
- end: `0x1400452b9`
- name: `??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z`
- size: `105`
- prototype: `__int64 __fastcall(__int64, const WCHAR **)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140045940`
- `0x140072ab0`
- `0x140073388`
- `0x140074930`
- `0x140074a28`
- `0x140074b24`
- `0x1400758ec`
- `0x140076530`
- `0x140076cc0`
- `0x140076ecc`
- `0x140078260`
- `0x1400789a0`

## callees

- `0x140045250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004528e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004528e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400452a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400452a0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StringReference::StringReference(__int64 a1, const WCHAR **a2)
{
  const WCHAR *v2; // rsi
  unsigned __int64 v4; // rbx

  v2 = *a2;
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    LODWORD(v4) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v2, v4, (HSTRING_HEADER *)(a1 + 8), (HSTRING *)a1);
  return a1;
}

```

## disassembly

```asm
0x140045250  mov     [rsp+arg_0], rbx
0x140045255  mov     [rsp+arg_8], rsi
0x14004525a  push    rdi
0x14004525b  sub     rsp, 20h
0x14004525f  mov     rsi, [rdx]
0x140045262  mov     rdi, rcx
0x140045265  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140045269  inc     rbx
0x14004526c  cmp     word ptr [rsi+rbx*2], 0
0x140045271  jnz     short loc_140045269
0x140045273  mov     eax, 0FFFFFFFFh
0x140045278  cmp     rbx, rax
0x14004527b  jbe     short loc_140045294
0x14004527d  xor     r9d, r9d; lpArguments
0x140045280  xor     r8d, r8d; nNumberOfArguments
0x140045283  mov     ecx, 0C000000Dh; dwExceptionCode
0x140045288  mov     ebx, eax
0x14004528a  lea     edx, [r9+1]; dwExceptionFlags
0x14004528e  call    cs:__imp_RaiseException
0x140045294  lea     r8, [rdi+8]; hstringHeader
0x140045298  mov     r9, rdi; string
0x14004529b  mov     edx, ebx; length
0x14004529d  mov     rcx, rsi; sourceString
0x1400452a0  call    cs:__imp_WindowsCreateStringReference
0x1400452a6  mov     rbx, [rsp+28h+arg_0]
0x1400452ab  mov     rax, rdi
0x1400452ae  mov     rsi, [rsp+28h+arg_8]
0x1400452b3  add     rsp, 20h
0x1400452b7  pop     rdi
0x1400452b8  retn
```
