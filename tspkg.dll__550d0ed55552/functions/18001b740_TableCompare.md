# TableCompare

- ea: `0x18001b740`
- end: `0x18001b774`
- name: `TableCompare`
- size: `52`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b740`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18001b750`
- `ntdll!RtlCompareUnicodeString` at `0x18001b750`

## pseudocode

```c
__int64 __fastcall TableCompare(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  LONG v3; // edx
  __int64 result; // rax

  v3 = RtlCompareUnicodeString(FirstStruct, SecondStruct, 1u);
  if ( v3 > 0 )
    return 1;
  result = 2;
  if ( v3 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001b740  sub     rsp, 28h
0x18001b744  mov     r9, r8
0x18001b747  mov     rcx, rdx; String1
0x18001b74a  mov     rdx, r9; String2
0x18001b74d  mov     r8b, 1; CaseInsensitive
0x18001b750  call    cs:__imp_RtlCompareUnicodeString
0x18001b756  mov     edx, eax
0x18001b758  test    eax, eax
0x18001b75a  jle     short loc_18001B763
0x18001b75c  mov     eax, 1
0x18001b761  jmp     short loc_18001B76F
0x18001b763  xor     ecx, ecx
0x18001b765  mov     eax, 2
0x18001b76a  test    edx, edx
0x18001b76c  cmovs   eax, ecx
0x18001b76f  add     rsp, 28h
0x18001b773  retn
```
