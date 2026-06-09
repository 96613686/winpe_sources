# WsDfsNetLuidTableCompareRoutine

- ea: `0x18000a7c0`
- end: `0x18000a81c`
- name: `WsDfsNetLuidTableCompareRoutine`
- size: `92`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a7c0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000a7dc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000a7dc`

## pseudocode

```c
__int64 __fastcall WsDfsNetLuidTableCompareRoutine(
        struct _RTL_GENERIC_TABLE *Table,
        PVOID FirstStruct,
        PVOID SecondStruct)
{
  SIZE_T v5; // rax

  v5 = RtlCompareMemory(FirstStruct, SecondStruct, 8u);
  if ( v5 < 8 )
    return *((_BYTE *)FirstStruct + v5) > *((_BYTE *)SecondStruct + v5);
  else
    return 2;
}

```

## disassembly

```asm
0x18000a7c0  mov     [rsp+arg_0], rbx
0x18000a7c5  push    rdi
0x18000a7c6  sub     rsp, 20h
0x18000a7ca  mov     rbx, r8
0x18000a7cd  mov     rdi, rdx
0x18000a7d0  mov     rdx, rbx; Source2
0x18000a7d3  mov     rcx, rdi; Source1
0x18000a7d6  mov     r8d, 8; Length
0x18000a7dc  call    cs:__imp_RtlCompareMemory
0x18000a7e3  nop     dword ptr [rax+rax+00h]
0x18000a7e8  cmp     rax, 8
0x18000a7ec  jb      short loc_18000A7FF
0x18000a7ee  mov     eax, 2
0x18000a7f3  mov     rbx, [rsp+28h+arg_0]
0x18000a7f8  add     rsp, 20h
0x18000a7fc  pop     rdi
0x18000a7fd  retn
0x18000a7ff  movzx   ecx, byte ptr [rax+rbx]
0x18000a803  xor     r9d, r9d
0x18000a806  cmp     [rax+rdi], cl
0x18000a809  mov     rbx, [rsp+28h+arg_0]
0x18000a80e  setnbe  r9b
0x18000a812  mov     eax, r9d
0x18000a815  add     rsp, 20h
0x18000a819  pop     rdi
0x18000a81a  retn
```
