# std::_Ref_count_resource<void *,WFDSConMgr::WlanHandleDeleter>::_Get_deleter(type_info const &)

- ea: `0x18002b170`
- end: `0x18002b19c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAXUWlanHandleDeleter@WFDSConMgr@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002b170`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b184`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b184`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<void *,WFDSConMgr::WlanHandleDeleter>::_Get_deleter(__int64 a1, __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180092188) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x18002b170  push    rbx
0x18002b172  sub     rsp, 20h
0x18002b176  mov     rbx, rcx
0x18002b179  lea     rcx, [rdx+8]
0x18002b17d  lea     rdx, qword_180092188
0x18002b184  call    cs:__imp___std_type_info_compare
0x18002b18a  test    eax, eax
0x18002b18c  jnz     short loc_18002B194
0x18002b18e  lea     rax, [rbx+10h]
0x18002b192  jmp     short loc_18002B196
0x18002b194  xor     eax, eax
0x18002b196  add     rsp, 20h
0x18002b19a  pop     rbx
0x18002b19b  retn
```
