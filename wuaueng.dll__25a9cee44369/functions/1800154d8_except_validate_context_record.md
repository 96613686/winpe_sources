# __except_validate_context_record

- ea: `0x1800154d8`
- end: `0x18001550f`
- name: `__except_validate_context_record`
- size: `55`
- prototype: `struct _TEB *__fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011c44`
- `0x180013cc0`
- `0x180013ef4`
- `0x180014430`
- `0x180014630`

## callees

- `0x1800154d8`

## pseudocode

```c
struct _TEB *__fastcall _except_validate_context_record(__int64 a1)
{
  struct _TEB *result; // rax
  PVOID v2; // rcx

  result = (struct _TEB *)_guard_check_icall_fptr[0];
  if ( _guard_check_icall_fptr[0] != guard_check_icall_nop )
  {
    result = NtCurrentTeb();
    v2 = *(PVOID *)(a1 + 152);
    if ( v2 < result->NtTib.StackLimit || v2 > result->NtTib.StackBase )
      __fastfail(0xDu);
  }
  return result;
}

```

## disassembly

```asm
0x1800154d8  mov     rax, cs:__guard_check_icall_fptr
0x1800154df  lea     rdx, _guard_check_icall_nop
0x1800154e6  cmp     rax, rdx
0x1800154e9  jz      short locret_18001550E
0x1800154eb  mov     rax, gs:30h
0x1800154f4  mov     rcx, [rcx+98h]
0x1800154fb  cmp     rcx, [rax+10h]
0x1800154ff  jb      short loc_180015507
0x180015501  cmp     rcx, [rax+8]
0x180015505  jbe     short locret_18001550E
0x180015507  mov     ecx, 0Dh
0x18001550c  int     29h; Win8: RtlFailFast(ecx)
0x18001550e  retn
```
