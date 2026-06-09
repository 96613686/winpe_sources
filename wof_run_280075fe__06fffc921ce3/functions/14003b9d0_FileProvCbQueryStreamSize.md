# FileProvCbQueryStreamSize

- ea: `0x14003b9d0`
- end: `0x14003b9f5`
- name: `FileProvCbQueryStreamSize`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140023150`
- `0x14003b9d0`

## pseudocode

```c
__int64 __fastcall FileProvCbQueryStreamSize(__int64 a1, __int64 *a2, char a3)
{
  __int64 v4; // rdx

  v4 = *(_QWORD *)(a1 + 8);
  if ( a3 )
    RtlWriteULong64ToUser(a2, v4);
  else
    *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x14003b9d0  sub     rsp, 28h
0x14003b9d4  mov     rax, rdx
0x14003b9d7  mov     rdx, [rcx+8]
0x14003b9db  test    r8b, r8b
0x14003b9de  jz      short loc_14003B9F0
0x14003b9e0  mov     rcx, rax
0x14003b9e3  call    RtlWriteULong64ToUser
0x14003b9e8  xor     eax, eax
0x14003b9ea  add     rsp, 28h
0x14003b9ee  retn
0x14003b9f0  mov     [rax], rdx
0x14003b9f3  jmp     short loc_14003B9E8
```
