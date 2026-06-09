# SrvAdminAliasTableCompare

- ea: `0x1400239f0`
- end: `0x140023a24`
- name: `SrvAdminAliasTableCompare`
- size: `52`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400239f0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140023a00`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140023a00`

## pseudocode

```c
__int64 __fastcall SrvAdminAliasTableCompare(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  LONG v3; // ecx

  v3 = RtlCompareUnicodeString(FirstStruct, SecondStruct, 1u);
  if ( v3 )
    return v3 >= 0;
  else
    return 2;
}

```

## disassembly

```asm
0x1400239f0  sub     rsp, 28h
0x1400239f4  mov     rax, r8
0x1400239f7  mov     rcx, rdx; String1
0x1400239fa  mov     rdx, rax; String2
0x1400239fd  mov     r8b, 1; CaseInSensitive
0x140023a00  call    cs:__imp_RtlCompareUnicodeString
0x140023a07  nop     dword ptr [rax+rax+00h]
0x140023a0c  mov     ecx, eax
0x140023a0e  test    eax, eax
0x140023a10  jnz     short loc_140023A17
0x140023a12  lea     eax, [rcx+2]
0x140023a15  jmp     short loc_140023A1E
0x140023a17  xor     eax, eax
0x140023a19  test    ecx, ecx
0x140023a1b  setns   al
0x140023a1e  add     rsp, 28h
0x140023a22  retn
```
