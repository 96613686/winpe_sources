# __except_validate_context_record

- ea: `0x1800066b8`
- end: `0x1800066ef`
- name: `__except_validate_context_record`
- size: `55`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fb0`
- `0x180004f94`
- `0x1800051a8`
- `0x180005670`
- `0x180005890`

## callees

- `0x1800066b8`

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
0x1800066b8  mov     rax, cs:__guard_check_icall_fptr
0x1800066bf  lea     rdx, _guard_check_icall_nop
0x1800066c6  cmp     rax, rdx
0x1800066c9  jz      short locret_1800066EE
0x1800066cb  mov     rax, gs:30h
0x1800066d4  mov     rcx, [rcx+98h]
0x1800066db  cmp     rcx, [rax+10h]
0x1800066df  jb      short loc_1800066E7
0x1800066e1  cmp     rcx, [rax+8]
0x1800066e5  jbe     short locret_1800066EE
0x1800066e7  mov     ecx, 0Dh
0x1800066ec  int     29h; Win8: RtlFailFast(ecx)
0x1800066ee  retn
```
