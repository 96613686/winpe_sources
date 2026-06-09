# _FindAndUnlinkFrame

- ea: `0x140002a24`
- end: `0x140002a77`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140004670`

## callees

- `0x140002a24`
- `0x140003008`
- `0x1400056be`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd(a1, a2, a3) + 88) || (v7 = *(_QWORD *)(_vcrt_getptd(v5, v4, v6) + 88)) == 0 )
LABEL_7:
    abort();
  while ( 1 )
  {
    v10 = *(_QWORD *)(v7 + 8);
    if ( a1 == v7 )
      break;
    v7 = *(_QWORD *)(v7 + 8);
    if ( !v10 )
      goto LABEL_7;
  }
  result = _vcrt_getptd(v8, v7, v9);
  *(_QWORD *)(result + 88) = v10;
  return result;
}

```

## disassembly

```asm
0x140002a24  mov     [rsp+arg_0], rbx
0x140002a29  push    rdi
0x140002a2a  sub     rsp, 20h
0x140002a2e  mov     rdi, rcx
0x140002a31  call    __vcrt_getptd
0x140002a36  cmp     rdi, [rax+58h]
0x140002a3a  jnz     short loc_140002A71
0x140002a3c  call    __vcrt_getptd
0x140002a41  mov     rdx, [rax+58h]
0x140002a45  test    rdx, rdx
0x140002a48  jz      short loc_140002A71
0x140002a4a  mov     rbx, [rdx+8]
0x140002a4e  cmp     rdi, rdx
0x140002a51  jz      short loc_140002A5D
0x140002a53  mov     rdx, rbx
0x140002a56  test    rbx, rbx
0x140002a59  jz      short loc_140002A71
0x140002a5b  jmp     short loc_140002A4A
0x140002a5d  call    __vcrt_getptd
0x140002a62  mov     [rax+58h], rbx
0x140002a66  mov     rbx, [rsp+28h+arg_0]
0x140002a6b  add     rsp, 20h
0x140002a6f  pop     rdi
0x140002a70  retn
0x140002a71  call    abort
```
