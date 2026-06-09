# _FindAndUnlinkFrame

- ea: `0x1004280e0`
- end: `0x100428133`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1004295a0`

## callees

- `0x100427a4c`
- `0x1004280e0`
- `0x10042b134`

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
0x1004280e0  mov     [rsp+arg_0], rbx
0x1004280e5  push    rdi
0x1004280e6  sub     rsp, 20h
0x1004280ea  mov     rdi, rcx
0x1004280ed  call    __vcrt_getptd
0x1004280f2  cmp     rdi, [rax+58h]
0x1004280f6  jnz     short loc_10042812D
0x1004280f8  call    __vcrt_getptd
0x1004280fd  mov     rdx, [rax+58h]
0x100428101  test    rdx, rdx
0x100428104  jz      short loc_10042812D
0x100428106  mov     rbx, [rdx+8]
0x10042810a  cmp     rdi, rdx
0x10042810d  jz      short loc_100428119
0x10042810f  mov     rdx, rbx
0x100428112  test    rbx, rbx
0x100428115  jz      short loc_10042812D
0x100428117  jmp     short loc_100428106
0x100428119  call    __vcrt_getptd
0x10042811e  mov     [rax+58h], rbx
0x100428122  mov     rbx, [rsp+28h+arg_0]
0x100428127  add     rsp, 20h
0x10042812b  pop     rdi
0x10042812c  retn
0x10042812d  call    abort
```
