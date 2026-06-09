# std::unique_ptr<web::json::details::_Object,std::default_delete<web::json::details::_Object>>::~unique_ptr<web::json::details::_Object,std::default_delete<web::json::details::_Object>>(void)

- ea: `0x180009c0c`
- end: `0x180009c31`
- name: `??1?$unique_ptr@V_Object@details@json@web@@U?$default_delete@V_Object@details@json@web@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180048a2a`
- `0x180048bac`
- `0x180048bd8`
- `0x180048ccc`
- `0x18004a35a`
- `0x18004a4ad`
- `0x18004a4d9`
- `0x18004a54d`
- `0x18004a594`
- `0x18004a5a6`
- `0x18004a5b8`
- `0x18004a6b3`
- `0x18004a6c9`
- `0x18004a7e3`
- `0x18004a7f5`
- `0x18004a972`
- `0x18004aa45`
- `0x18004aa7b`
- `0x18004af4c`
- `0x18004b7bc`

## callees

- `0x180009c0c`
- `0x180047a30`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 192LL))(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180009c0c  sub     rsp, 28h
0x180009c10  mov     rcx, [rcx]
0x180009c13  test    rcx, rcx
0x180009c16  jz      short loc_180009C2C
0x180009c18  mov     rax, [rcx]
0x180009c1b  mov     edx, 1
0x180009c20  mov     rax, [rax+0C0h]
0x180009c27  call    _guard_dispatch_icall
0x180009c2c  add     rsp, 28h
0x180009c30  retn
```
