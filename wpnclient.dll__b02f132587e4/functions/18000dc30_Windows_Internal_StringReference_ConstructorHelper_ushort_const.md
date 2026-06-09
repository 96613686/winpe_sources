# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x18000dc30`
- end: `0x18000dc9e`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `110`
- prototype: `void __fastcall(Windows::Internal::StringReference *__hidden this, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180007760`
- `0x180009380`
- `0x18000d0d0`
- `0x18000da20`
- `0x18001780c`
- `0x180018d90`
- `0x1800192d4`
- `0x18001a65c`
- `0x18001afb0`
- `0x18001d9d4`
- `0x18001df20`
- `0x18001e1a4`
- `0x180026d70`
- `0x18002d1ac`
- `0x18002d370`
- `0x18002d73c`

## callees

- `0x18000dc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dc76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dc76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dc97`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::_ConstructorHelper(
        Windows::Internal::StringReference *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v4; // rbx

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    LODWORD(v4) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v4, (HSTRING_HEADER *)((char *)this + 8), (HSTRING *)this);
}

```

## disassembly

```asm
0x18000dc30  mov     [rsp+arg_0], rbx
0x18000dc35  mov     [rsp+arg_8], rsi
0x18000dc3a  push    rdi
0x18000dc3b  sub     rsp, 20h
0x18000dc3f  mov     rdi, rdx
0x18000dc42  mov     rsi, rcx
0x18000dc45  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000dc4c  nop     dword ptr [rax+00h]
0x18000dc50  inc     rbx
0x18000dc53  cmp     word ptr [rdx+rbx*2], 0
0x18000dc58  jnz     short loc_18000DC50
0x18000dc5a  mov     eax, 0FFFFFFFFh
0x18000dc5f  cmp     rbx, rax
0x18000dc62  jbe     short loc_18000DC7C
0x18000dc64  xor     r9d, r9d; lpArguments
0x18000dc67  xor     r8d, r8d; nNumberOfArguments
0x18000dc6a  mov     edx, 1; dwExceptionFlags
0x18000dc6f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000dc74  mov     ebx, eax
0x18000dc76  call    cs:__imp_RaiseException
0x18000dc7c  lea     r8, [rsi+8]
0x18000dc80  mov     r9, rsi
0x18000dc83  mov     edx, ebx
0x18000dc85  mov     rcx, rdi
0x18000dc88  mov     rbx, [rsp+28h+arg_0]
0x18000dc8d  mov     rsi, [rsp+28h+arg_8]
0x18000dc92  add     rsp, 20h
0x18000dc96  pop     rdi
0x18000dc97  jmp     cs:__imp_WindowsCreateStringReference
```
