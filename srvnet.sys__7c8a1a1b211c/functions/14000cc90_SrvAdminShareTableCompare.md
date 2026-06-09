# SrvAdminShareTableCompare

- ea: `0x14000cc90`
- end: `0x14000ccfa`
- name: `SrvAdminShareTableCompare`
- size: `106`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000cc90`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cca9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000ccc4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cca9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000ccc4`

## pseudocode

```c
__int64 __fastcall SrvAdminShareTableCompare(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  LONG v5; // eax

  v5 = RtlCompareUnicodeString(FirstStruct, SecondStruct, 1u);
  if ( v5 )
    return v5 >= 0;
  v5 = -RtlCompareUnicodeString(FirstStruct + 1, SecondStruct + 1, 1u);
  if ( v5 )
    return v5 >= 0;
  else
    return 2;
}

```

## disassembly

```asm
0x14000cc90  mov     [rsp+arg_0], rbx
0x14000cc95  push    rdi
0x14000cc96  sub     rsp, 20h
0x14000cc9a  mov     rbx, r8
0x14000cc9d  mov     rdi, rdx
0x14000cca0  mov     rdx, rbx; String2
0x14000cca3  mov     rcx, rdi; String1
0x14000cca6  mov     r8b, 1; CaseInSensitive
0x14000cca9  call    cs:__imp_RtlCompareUnicodeString
0x14000ccb0  nop     dword ptr [rax+rax+00h]
0x14000ccb5  test    eax, eax
0x14000ccb7  jnz     short loc_14000CCE5
0x14000ccb9  lea     rdx, [rbx+10h]; String2
0x14000ccbd  mov     r8b, 1; CaseInSensitive
0x14000ccc0  lea     rcx, [rdi+10h]; String1
0x14000ccc4  call    cs:__imp_RtlCompareUnicodeString
0x14000cccb  nop     dword ptr [rax+rax+00h]
0x14000ccd0  neg     eax
0x14000ccd2  jnz     short loc_14000CCE5
0x14000ccd4  mov     eax, 2
0x14000ccd9  mov     rbx, [rsp+28h+arg_0]
0x14000ccde  add     rsp, 20h
0x14000cce2  pop     rdi
0x14000cce3  retn
0x14000cce5  mov     rbx, [rsp+28h+arg_0]
0x14000ccea  xor     ecx, ecx
0x14000ccec  test    eax, eax
0x14000ccee  setns   cl
0x14000ccf1  mov     eax, ecx
0x14000ccf3  add     rsp, 20h
0x14000ccf7  pop     rdi
0x14000ccf8  retn
```
