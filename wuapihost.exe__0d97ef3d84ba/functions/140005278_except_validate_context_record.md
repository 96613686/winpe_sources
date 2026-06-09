# __except_validate_context_record

- ea: `0x140005278`
- end: `0x1400052af`
- name: `__except_validate_context_record`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d48`
- `0x1400040e0`
- `0x140004670`

## callees

- `0x140005278`

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
0x140005278  mov     rax, cs:__guard_check_icall_fptr
0x14000527f  lea     rdx, _guard_check_icall_nop
0x140005286  cmp     rax, rdx
0x140005289  jz      short locret_1400052AE
0x14000528b  mov     rax, gs:30h
0x140005294  mov     rcx, [rcx+98h]
0x14000529b  cmp     rcx, [rax+10h]
0x14000529f  jb      short loc_1400052A7
0x1400052a1  cmp     rcx, [rax+8]
0x1400052a5  jbe     short locret_1400052AE
0x1400052a7  mov     ecx, 0Dh
0x1400052ac  int     29h; Win8: RtlFailFast(ecx)
0x1400052ae  retn
```
