# std::_Ref_count_resource<WFDSConMgr::IWorkQueueJob *,std::default_delete<WFDSConMgr::IWorkQueueJob>>::_Get_deleter(type_info const &)

- ea: `0x1800354f0`
- end: `0x18003551c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVIWorkQueueJob@WFDSConMgr@@U?$default_delete@VIWorkQueueJob@WFDSConMgr@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800354f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180035504`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180035504`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<WFDSConMgr::IWorkQueueJob *,std::default_delete<WFDSConMgr::IWorkQueueJob>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_1800921C8) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x1800354f0  push    rbx
0x1800354f2  sub     rsp, 20h
0x1800354f6  mov     rbx, rcx
0x1800354f9  lea     rcx, [rdx+8]
0x1800354fd  lea     rdx, qword_1800921C8
0x180035504  call    cs:__imp___std_type_info_compare
0x18003550a  test    eax, eax
0x18003550c  jnz     short loc_180035514
0x18003550e  lea     rax, [rbx+10h]
0x180035512  jmp     short loc_180035516
0x180035514  xor     eax, eax
0x180035516  add     rsp, 20h
0x18003551a  pop     rbx
0x18003551b  retn
```
