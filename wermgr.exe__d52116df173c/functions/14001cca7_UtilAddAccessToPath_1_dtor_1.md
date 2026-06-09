# _UtilAddAccessToPath_::_1_::dtor$1

- ea: `0x14001cca7`
- end: `0x14001ccb3`
- name: `_UtilAddAccessToPath_::_1_::dtor$1`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140004a94`

## pseudocode

```c
HLOCAL __fastcall UtilAddAccessToPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return __1__unique_ptr_U_ACL__U__generic_delete_U_ACL__U__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ((void **)(a2 + 104));
}

```

## disassembly

```asm
0x14001cca7  lea     rcx, [rdx+68h]
0x14001ccae  jmp     ??1?$unique_ptr@U_ACL@@U?$generic_delete@U_ACL@@U?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
```
