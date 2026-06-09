# WsDfsNetLuidTableCompareRoutine

- ea: `0x18000a060`
- end: `0x18000a0b4`
- name: `WsDfsNetLuidTableCompareRoutine`
- size: `84`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a060`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000a07c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000a07c`

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
0x18000a060  mov     [rsp+arg_0], rbx
0x18000a065  push    rdi
0x18000a066  sub     rsp, 20h
0x18000a06a  mov     rbx, r8
0x18000a06d  mov     rdi, rdx
0x18000a070  mov     rdx, rbx; Source2
0x18000a073  mov     rcx, rdi; Source1
0x18000a076  mov     r8d, 8; Length
0x18000a07c  call    cs:__imp_RtlCompareMemory
0x18000a082  cmp     rax, 8
0x18000a086  jb      short loc_18000A098
0x18000a088  mov     eax, 2
0x18000a08d  mov     rbx, [rsp+28h+arg_0]
0x18000a092  add     rsp, 20h
0x18000a096  pop     rdi
0x18000a097  retn
0x18000a098  movzx   ecx, byte ptr [rax+rbx]
0x18000a09c  xor     r9d, r9d
0x18000a09f  cmp     [rax+rdi], cl
0x18000a0a2  mov     rbx, [rsp+28h+arg_0]
0x18000a0a7  setnbe  r9b
0x18000a0ab  mov     eax, r9d
0x18000a0ae  add     rsp, 20h
0x18000a0b2  pop     rdi
0x18000a0b3  retn
```
