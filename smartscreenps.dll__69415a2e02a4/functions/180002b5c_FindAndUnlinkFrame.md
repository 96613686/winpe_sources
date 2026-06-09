# _FindAndUnlinkFrame

- ea: `0x180002b5c`
- end: `0x180002baf`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005670`
- `0x180005890`

## callees

- `0x180002b5c`
- `0x1800033d8`
- `0x18000693e`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort_0();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x180002b5c  mov     [rsp+arg_0], rbx
0x180002b61  push    rdi
0x180002b62  sub     rsp, 20h
0x180002b66  mov     rdi, rcx
0x180002b69  call    __vcrt_getptd
0x180002b6e  cmp     rdi, [rax+58h]
0x180002b72  jnz     short loc_180002BA9
0x180002b74  call    __vcrt_getptd
0x180002b79  mov     rdx, [rax+58h]
0x180002b7d  test    rdx, rdx
0x180002b80  jz      short loc_180002BA9
0x180002b82  mov     rbx, [rdx+8]
0x180002b86  cmp     rdi, rdx
0x180002b89  jz      short loc_180002B95
0x180002b8b  mov     rdx, rbx
0x180002b8e  test    rbx, rbx
0x180002b91  jz      short loc_180002BA9
0x180002b93  jmp     short loc_180002B82
0x180002b95  call    __vcrt_getptd
0x180002b9a  mov     [rax+58h], rbx
0x180002b9e  mov     rbx, [rsp+28h+arg_0]
0x180002ba3  add     rsp, 20h
0x180002ba7  pop     rdi
0x180002ba8  retn
0x180002ba9  call    abort_0
```
