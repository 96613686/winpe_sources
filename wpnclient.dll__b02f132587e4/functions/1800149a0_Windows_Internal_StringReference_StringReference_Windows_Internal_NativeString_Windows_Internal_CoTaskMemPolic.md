# Windows::Internal::StringReference::StringReference(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x1800149a0`
- end: `0x180014a09`
- name: `??$?0V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@StringReference@Internal@Windows@@QEAA@AEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@12@Udummy_t@_StringDetail@12@@Z`
- size: `105`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180007760`

## callees

- `0x1800149a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800149f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800149f0`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, const WCHAR **a2)
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
  WindowsCreateStringReference(v2, v4, (HSTRING_HEADER *)(string + 1), string);
  return string;
}

```

## disassembly

```asm
0x1800149a0  mov     [rsp+arg_0], rbx
0x1800149a5  mov     [rsp+arg_8], rsi
0x1800149aa  push    rdi
0x1800149ab  sub     rsp, 20h
0x1800149af  mov     rsi, [rdx]
0x1800149b2  mov     rdi, rcx
0x1800149b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800149b9  inc     rbx
0x1800149bc  cmp     word ptr [rsi+rbx*2], 0
0x1800149c1  jnz     short loc_1800149B9
0x1800149c3  mov     eax, 0FFFFFFFFh
0x1800149c8  cmp     rbx, rax
0x1800149cb  jbe     short loc_1800149E4
0x1800149cd  xor     r9d, r9d; lpArguments
0x1800149d0  xor     r8d, r8d; nNumberOfArguments
0x1800149d3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800149d8  mov     ebx, eax
0x1800149da  lea     edx, [r9+1]; dwExceptionFlags
0x1800149de  call    cs:__imp_RaiseException
0x1800149e4  lea     r8, [rdi+8]; hstringHeader
0x1800149e8  mov     r9, rdi; string
0x1800149eb  mov     edx, ebx; length
0x1800149ed  mov     rcx, rsi; sourceString
0x1800149f0  call    cs:__imp_WindowsCreateStringReference
0x1800149f6  mov     rbx, [rsp+28h+arg_0]
0x1800149fb  mov     rax, rdi
0x1800149fe  mov     rsi, [rsp+28h+arg_8]
0x180014a03  add     rsp, 20h
0x180014a07  pop     rdi
0x180014a08  retn
```
