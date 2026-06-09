# _FindAndUnlinkFrame

- ea: `0x18001180c`
- end: `0x18001185f`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180014430`
- `0x180014630`

## callees

- `0x18000fc34`
- `0x18001180c`
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
0x18001180c  mov     [rsp+arg_0], rbx
0x180011811  push    rdi
0x180011812  sub     rsp, 20h
0x180011816  mov     rdi, rcx
0x180011819  call    __vcrt_getptd
0x18001181e  cmp     rdi, [rax+58h]
0x180011822  jnz     short loc_180011859
0x180011824  call    __vcrt_getptd
0x180011829  mov     rdx, [rax+58h]
0x18001182d  test    rdx, rdx
0x180011830  jz      short loc_180011859
0x180011832  mov     rbx, [rdx+8]
0x180011836  cmp     rdi, rdx
0x180011839  jz      short loc_180011845
0x18001183b  mov     rdx, rbx
0x18001183e  test    rbx, rbx
0x180011841  jz      short loc_180011859
0x180011843  jmp     short loc_180011832
0x180011845  call    __vcrt_getptd
0x18001184a  mov     [rax+58h], rbx
0x18001184e  mov     rbx, [rsp+28h+arg_0]
0x180011853  add     rsp, 20h
0x180011857  pop     rdi
0x180011858  retn
0x180011859  call    abort
```
