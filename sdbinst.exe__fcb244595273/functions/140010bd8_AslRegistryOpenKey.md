# AslRegistryOpenKey

- ea: `0x140010bd8`
- end: `0x140010c4d`
- name: `AslRegistryOpenKey`
- size: `117`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a9ec`
- `0x14000d8e8`

## callees

- `0x14001008c`
- `0x140010bd8`
- `0x140010c54`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140010bf9`
- `ntdll!RtlInitUnicodeStringEx` at `0x140010bf9`

## string_xrefs

- `0x140010c05`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x140010c16`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  inited = RtlInitUnicodeStringEx(&v8, a2);
  v6 = inited;
  if ( inited >= 0 )
    return (unsigned int)AslRegistryOpenKey_UStr(a1, &v8, a3);
  else
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  return v6;
}

```

## disassembly

```asm
0x140010bd8  mov     rax, rsp
0x140010bdb  mov     [rax+8], rbx
0x140010bdf  mov     [rax+10h], rsi
0x140010be3  push    rdi
0x140010be4  sub     rsp, 40h
0x140010be8  mov     rsi, rcx
0x140010beb  xorps   xmm0, xmm0
0x140010bee  lea     rcx, [rax-18h]; DestinationString
0x140010bf2  mov     edi, r8d
0x140010bf5  movups  xmmword ptr [rax-18h], xmm0
0x140010bf9  call    cs:__imp_RtlInitUnicodeStringEx
0x140010bff  mov     ebx, eax
0x140010c01  test    eax, eax
0x140010c03  jns     short loc_140010C29
0x140010c05  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x140010c0c  mov     [rsp+48h+var_28], eax
0x140010c10  mov     r8d, 388h
0x140010c16  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x140010c1d  mov     ecx, 1
0x140010c22  call    AslLogCallPrintf
0x140010c27  jmp     short loc_140010C3B
0x140010c29  mov     r8d, edi
0x140010c2c  lea     rdx, [rsp+48h+var_18]
0x140010c31  mov     rcx, rsi
0x140010c34  call    AslRegistryOpenKey_UStr
0x140010c39  mov     ebx, eax
0x140010c3b  mov     rsi, [rsp+48h+arg_8]
0x140010c40  mov     eax, ebx
0x140010c42  mov     rbx, [rsp+48h+arg_0]
0x140010c47  add     rsp, 40h
0x140010c4b  pop     rdi
0x140010c4c  retn
```
