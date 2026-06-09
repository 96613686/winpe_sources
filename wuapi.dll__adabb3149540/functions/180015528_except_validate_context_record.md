# __except_validate_context_record

- ea: `0x180015528`
- end: `0x18001555f`
- name: `__except_validate_context_record`
- size: `55`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011c94`
- `0x180013d10`
- `0x180013f44`
- `0x180014480`
- `0x180014680`

## callees

- `0x180015528`

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
0x180015528  mov     rax, cs:__guard_check_icall_fptr
0x18001552f  lea     rdx, _guard_check_icall_nop
0x180015536  cmp     rax, rdx
0x180015539  jz      short locret_18001555E
0x18001553b  mov     rax, gs:30h
0x180015544  mov     rcx, [rcx+98h]
0x18001554b  cmp     rcx, [rax+10h]
0x18001554f  jb      short loc_180015557
0x180015551  cmp     rcx, [rax+8]
0x180015555  jbe     short locret_18001555E
0x180015557  mov     ecx, 0Dh
0x18001555c  int     29h; Win8: RtlFailFast(ecx)
0x18001555e  retn
```
