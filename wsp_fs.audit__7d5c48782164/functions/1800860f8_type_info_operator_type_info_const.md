# type_info::operator==(type_info const &)

- ea: `0x1800860f8`
- end: `0x18008611b`
- name: `??8type_info@@QEBA_NAEBV0@@Z`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180084dfc`
- `0x180084f48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180086104`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180086104`

## pseudocode

```c
bool __fastcall type_info::operator==(__int64 a1, __int64 a2)
{
  return (unsigned int)__std_type_info_compare(a1 + 8, a2 + 8) == 0;
}

```

## disassembly

```asm
0x1800860f8  sub     rsp, 28h
0x1800860fc  add     rdx, 8
0x180086100  add     rcx, 8
0x180086104  call    cs:__imp___std_type_info_compare
0x18008610b  nop     dword ptr [rax+rax+00h]
0x180086110  test    eax, eax
0x180086112  setz    al
0x180086115  add     rsp, 28h
0x180086119  retn
```
