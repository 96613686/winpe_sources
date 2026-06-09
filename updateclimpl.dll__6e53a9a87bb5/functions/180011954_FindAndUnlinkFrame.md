# _FindAndUnlinkFrame

- ea: `0x180011954`
- end: `0x1800119a7`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180013600`

## callees

- `0x180010238`
- `0x180011954`
- `0x180011f98`

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
0x180011954  mov     [rsp+arg_0], rbx
0x180011959  push    rdi
0x18001195a  sub     rsp, 20h
0x18001195e  mov     rdi, rcx
0x180011961  call    __vcrt_getptd
0x180011966  cmp     rdi, [rax+58h]
0x18001196a  jnz     short loc_1800119A1
0x18001196c  call    __vcrt_getptd
0x180011971  mov     rdx, [rax+58h]
0x180011975  test    rdx, rdx
0x180011978  jz      short loc_1800119A1
0x18001197a  mov     rbx, [rdx+8]
0x18001197e  cmp     rdi, rdx
0x180011981  jz      short loc_18001198D
0x180011983  mov     rdx, rbx
0x180011986  test    rbx, rbx
0x180011989  jz      short loc_1800119A1
0x18001198b  jmp     short loc_18001197A
0x18001198d  call    __vcrt_getptd
0x180011992  mov     [rax+58h], rbx
0x180011996  mov     rbx, [rsp+28h+arg_0]
0x18001199b  add     rsp, 20h
0x18001199f  pop     rdi
0x1800119a0  retn
0x1800119a1  call    abort
```
