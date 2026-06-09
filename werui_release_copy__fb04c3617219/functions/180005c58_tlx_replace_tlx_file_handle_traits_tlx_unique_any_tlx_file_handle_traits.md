# tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)

- ea: `0x180005c58`
- end: `0x180005c71`
- name: `??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e00`
- `0x180006ee0`
- `0x18000b1b4`
- `0x180010938`
- `0x180012598`

## callees

- `0x18000983c`

## pseudocode

```c
__int64 __fastcall tlx::replace<tlx::file_handle_traits>(__int64 a1)
{
  tlx::unique_any<tlx::file_handle_traits>::reset(a1, 0);
  return a1;
}

```

## disassembly

```asm
0x180005c58  push    rbx
0x180005c5a  sub     rsp, 20h
0x180005c5e  xor     edx, edx
0x180005c60  mov     rbx, rcx
0x180005c63  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z
0x180005c68  mov     rax, rbx
0x180005c6b  add     rsp, 20h
0x180005c6f  pop     rbx
0x180005c70  retn
```
