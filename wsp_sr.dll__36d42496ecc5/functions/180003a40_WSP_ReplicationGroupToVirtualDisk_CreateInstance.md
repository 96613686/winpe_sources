# WSP_ReplicationGroupToVirtualDisk_CreateInstance

- ea: `0x180003a40`
- end: `0x180003a69`
- name: `WSP_ReplicationGroupToVirtualDisk_CreateInstance`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003a40`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroupToVirtualDisk_CreateInstance(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 result; // rax

  result = (__int64)a2;
  if ( a2 )
  {
    if ( *a2 )
      return (**a2)(a2, 7);
  }
  return result;
}

```

## disassembly

```asm
0x180003a40  sub     rsp, 28h
0x180003a44  mov     rax, rdx
0x180003a47  test    rdx, rdx
0x180003a4a  jz      short loc_180003A64
0x180003a4c  mov     r8, [rdx]
0x180003a4f  test    r8, r8
0x180003a52  jz      short loc_180003A64
0x180003a54  mov     rcx, rax
0x180003a57  mov     edx, 7
0x180003a5c  mov     rax, [r8]
0x180003a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a64  add     rsp, 28h
0x180003a68  retn
```
