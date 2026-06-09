# std::_Ref_count_resource<WFDSConMgr::ISessionWork *,std::default_delete<WFDSConMgr::ISessionWork>>::_Get_deleter(type_info const &)

- ea: `0x180040ab0`
- end: `0x180040adc`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVISessionWork@WFDSConMgr@@U?$default_delete@VISessionWork@WFDSConMgr@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180040ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180040ac4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180040ac4`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<WFDSConMgr::ISessionWork *,std::default_delete<WFDSConMgr::ISessionWork>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180092218) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180040ab0  push    rbx
0x180040ab2  sub     rsp, 20h
0x180040ab6  mov     rbx, rcx
0x180040ab9  lea     rcx, [rdx+8]
0x180040abd  lea     rdx, qword_180092218
0x180040ac4  call    cs:__imp___std_type_info_compare
0x180040aca  test    eax, eax
0x180040acc  jnz     short loc_180040AD4
0x180040ace  lea     rax, [rbx+10h]
0x180040ad2  jmp     short loc_180040AD6
0x180040ad4  xor     eax, eax
0x180040ad6  add     rsp, 20h
0x180040ada  pop     rbx
0x180040adb  retn
```
