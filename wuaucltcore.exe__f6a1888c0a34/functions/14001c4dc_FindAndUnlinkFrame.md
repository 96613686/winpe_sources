# _FindAndUnlinkFrame

- ea: `0x14001c4dc`
- end: `0x14001c52f`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001f090`
- `0x14001f290`

## callees

- `0x14001a9f4`
- `0x14001c4dc`
- `0x14001cbf8`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
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
0x14001c4dc  mov     [rsp+arg_0], rbx
0x14001c4e1  push    rdi
0x14001c4e2  sub     rsp, 20h
0x14001c4e6  mov     rdi, rcx
0x14001c4e9  call    __vcrt_getptd
0x14001c4ee  cmp     rdi, [rax+58h]
0x14001c4f2  jnz     short loc_14001C529
0x14001c4f4  call    __vcrt_getptd
0x14001c4f9  mov     rdx, [rax+58h]
0x14001c4fd  test    rdx, rdx
0x14001c500  jz      short loc_14001C529
0x14001c502  mov     rbx, [rdx+8]
0x14001c506  cmp     rdi, rdx
0x14001c509  jz      short loc_14001C515
0x14001c50b  mov     rdx, rbx
0x14001c50e  test    rbx, rbx
0x14001c511  jz      short loc_14001C529
0x14001c513  jmp     short loc_14001C502
0x14001c515  call    __vcrt_getptd
0x14001c51a  mov     [rax+58h], rbx
0x14001c51e  mov     rbx, [rsp+28h+arg_0]
0x14001c523  add     rsp, 20h
0x14001c527  pop     rdi
0x14001c528  retn
0x14001c529  call    abort
```
