# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000f970`
- end: `0x18000f9c2`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800056d0`
- `0x18000cf30`
- `0x18000e890`
- `0x18000ea20`
- `0x18000f8d4`
- `0x180012058`
- `0x1800120b0`
- `0x180012130`
- `0x180013f4c`
- `0x180013fb0`
- `0x1800140f0`

## callees

- `0x18000f970`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000f9b7`
- `ntdll!EtwEventWriteTransfer` at `0x18000f9b7`

## pseudocode

```c

```

## disassembly

```asm
0x18000f970  sub     rsp, 38h
0x18000f974  mov     rcx, cs:qword_180023018
0x18000f97b  mov     rax, [rsp+38h+arg_20]
0x18000f980  test    rcx, rcx
0x18000f983  jnz     short loc_18000F98D
0x18000f985  mov     [rax], rcx
0x18000f988  xor     r8d, r8d
0x18000f98b  jmp     short loc_18000F999
0x18000f98d  mov     [rax], rcx
0x18000f990  mov     r8d, 2
0x18000f996  movzx   ecx, word ptr [rcx]
0x18000f999  mov     [rax+8], ecx
0x18000f99c  mov     [rax+0Ch], r8d
0x18000f9a0  xor     r8d, r8d
0x18000f9a3  mov     rcx, cs:userpnp_Context
0x18000f9aa  mov     [rsp+38h+var_10], rax
0x18000f9af  mov     [rsp+38h+var_18], r9d
0x18000f9b4  xor     r9d, r9d
0x18000f9b7  call    cs:__imp_EtwEventWriteTransfer
0x18000f9bd  add     rsp, 38h
0x18000f9c1  retn
```
