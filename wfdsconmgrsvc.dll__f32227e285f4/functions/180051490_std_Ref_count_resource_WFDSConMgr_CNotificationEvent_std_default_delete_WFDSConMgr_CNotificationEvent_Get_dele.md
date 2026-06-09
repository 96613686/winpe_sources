# std::_Ref_count_resource<WFDSConMgr::CNotificationEvent *,std::default_delete<WFDSConMgr::CNotificationEvent>>::_Get_deleter(type_info const &)

- ea: `0x180051490`
- end: `0x1800514bc`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180051490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800514a4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800514a4`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<WFDSConMgr::CNotificationEvent *,std::default_delete<WFDSConMgr::CNotificationEvent>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_1800922E8) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180051490  push    rbx
0x180051492  sub     rsp, 20h
0x180051496  mov     rbx, rcx
0x180051499  lea     rcx, [rdx+8]
0x18005149d  lea     rdx, qword_1800922E8
0x1800514a4  call    cs:__imp___std_type_info_compare
0x1800514aa  test    eax, eax
0x1800514ac  jnz     short loc_1800514B4
0x1800514ae  lea     rax, [rbx+10h]
0x1800514b2  jmp     short loc_1800514B6
0x1800514b4  xor     eax, eax
0x1800514b6  add     rsp, 20h
0x1800514ba  pop     rbx
0x1800514bb  retn
```
