# type_info::operator==(type_info const &)

- ea: `0x180048f84`
- end: `0x180048fa7`
- name: `??8type_info@@QEBA_NAEBV0@@Z`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180047bc8`
- `0x180047d14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180048f90`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180048f90`

## pseudocode

```c
bool __fastcall type_info::operator==(__int64 a1, __int64 a2)
{
  return (unsigned int)__std_type_info_compare(a1 + 8, a2 + 8) == 0;
}

```

## disassembly

```asm
0x180048f84  sub     rsp, 28h
0x180048f88  add     rdx, 8
0x180048f8c  add     rcx, 8
0x180048f90  call    cs:__imp___std_type_info_compare
0x180048f97  nop     dword ptr [rax+rax+00h]
0x180048f9c  test    eax, eax
0x180048f9e  setz    al
0x180048fa1  add     rsp, 28h
0x180048fa5  retn
```
