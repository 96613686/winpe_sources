# AslRegistryGetUInt32

- ea: `0x140010a68`
- end: `0x140010ae0`
- name: `AslRegistryGetUInt32`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c0ac`
- `0x140016c98`
- `0x140017498`

## callees

- `0x14001008c`
- `0x140010a68`
- `0x140010ae8`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140010a8c`
- `ntdll!RtlInitUnicodeStringEx` at `0x140010a8c`

## string_xrefs

- `0x140010aa9`: `AslRegistryGetUInt32`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32(__int64 a1, __int64 a2, const WCHAR *a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  inited = RtlInitUnicodeStringEx(&v8, a3);
  v6 = inited;
  if ( inited >= 0 )
    return (unsigned int)AslRegistryGetUInt32_UStr(a1, a2, &v8);
  else
    AslLogCallPrintf(1, "AslRegistryGetUInt32", 1148, "RtlInitUnicodeStringEx failed [%x]", inited);
  return v6;
}

```

## disassembly

```asm
0x140010a68  mov     rax, rsp
0x140010a6b  mov     [rax+8], rbx
0x140010a6f  mov     [rax+10h], rsi
0x140010a73  push    rdi
0x140010a74  sub     rsp, 40h
0x140010a78  mov     rdi, rdx
0x140010a7b  mov     rsi, rcx
0x140010a7e  xorps   xmm0, xmm0
0x140010a81  lea     rcx, [rax-18h]; DestinationString
0x140010a85  mov     rdx, r8; SourceString
0x140010a88  movups  xmmword ptr [rax-18h], xmm0
0x140010a8c  call    cs:__imp_RtlInitUnicodeStringEx
0x140010a92  mov     ebx, eax
0x140010a94  test    eax, eax
0x140010a96  jns     short loc_140010ABC
0x140010a98  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed [%x]"
0x140010a9f  mov     [rsp+48h+var_28], eax
0x140010aa3  mov     r8d, 47Ch
0x140010aa9  lea     rdx, aAslregistryget_4; "AslRegistryGetUInt32"
0x140010ab0  mov     ecx, 1
0x140010ab5  call    AslLogCallPrintf
0x140010aba  jmp     short loc_140010ACE
0x140010abc  lea     r8, [rsp+48h+var_18]
0x140010ac1  mov     rdx, rdi
0x140010ac4  mov     rcx, rsi
0x140010ac7  call    AslRegistryGetUInt32_UStr
0x140010acc  mov     ebx, eax
0x140010ace  mov     rsi, [rsp+48h+arg_8]
0x140010ad3  mov     eax, ebx
0x140010ad5  mov     rbx, [rsp+48h+arg_0]
0x140010ada  add     rsp, 40h
0x140010ade  pop     rdi
0x140010adf  retn
```
