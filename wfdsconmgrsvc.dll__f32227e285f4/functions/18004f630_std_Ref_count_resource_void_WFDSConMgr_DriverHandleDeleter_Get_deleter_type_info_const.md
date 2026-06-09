# std::_Ref_count_resource<void *,WFDSConMgr::DriverHandleDeleter>::_Get_deleter(type_info const &)

- ea: `0x18004f630`
- end: `0x18004f65c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAXUDriverHandleDeleter@WFDSConMgr@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18004f630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004f644`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004f644`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<void *,WFDSConMgr::DriverHandleDeleter>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_1800922B0) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x18004f630  push    rbx
0x18004f632  sub     rsp, 20h
0x18004f636  mov     rbx, rcx
0x18004f639  lea     rcx, [rdx+8]
0x18004f63d  lea     rdx, qword_1800922B0
0x18004f644  call    cs:__imp___std_type_info_compare
0x18004f64a  test    eax, eax
0x18004f64c  jnz     short loc_18004F654
0x18004f64e  lea     rax, [rbx+10h]
0x18004f652  jmp     short loc_18004F656
0x18004f654  xor     eax, eax
0x18004f656  add     rsp, 20h
0x18004f65a  pop     rbx
0x18004f65b  retn
```
