# _FindAndUnlinkFrame

- ea: `0x18001185c`
- end: `0x1800118af`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180014480`
- `0x180014680`

## callees

- `0x18000fc84`
- `0x18001185c`
- `0x180011fe8`

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
0x18001185c  mov     [rsp+arg_0], rbx
0x180011861  push    rdi
0x180011862  sub     rsp, 20h
0x180011866  mov     rdi, rcx
0x180011869  call    __vcrt_getptd
0x18001186e  cmp     rdi, [rax+58h]
0x180011872  jnz     short loc_1800118A9
0x180011874  call    __vcrt_getptd
0x180011879  mov     rdx, [rax+58h]
0x18001187d  test    rdx, rdx
0x180011880  jz      short loc_1800118A9
0x180011882  mov     rbx, [rdx+8]
0x180011886  cmp     rdi, rdx
0x180011889  jz      short loc_180011895
0x18001188b  mov     rdx, rbx
0x18001188e  test    rbx, rbx
0x180011891  jz      short loc_1800118A9
0x180011893  jmp     short loc_180011882
0x180011895  call    __vcrt_getptd
0x18001189a  mov     [rax+58h], rbx
0x18001189e  mov     rbx, [rsp+28h+arg_0]
0x1800118a3  add     rsp, 20h
0x1800118a7  pop     rdi
0x1800118a8  retn
0x1800118a9  call    abort
```
