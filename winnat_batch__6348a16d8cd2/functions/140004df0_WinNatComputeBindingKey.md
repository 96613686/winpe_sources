# WinNatComputeBindingKey

- ea: `0x140004df0`
- end: `0x140004e54`
- name: `WinNatComputeBindingKey`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140008df0`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x140004e17`
- `NETIO!RtlComputeToeplitzHash` at `0x140004e36`
- `NETIO!RtlComputeToeplitzHash` at `0x140004e17`
- `NETIO!RtlComputeToeplitzHash` at `0x140004e36`

## pseudocode

```c
int __fastcall WinNatComputeBindingKey(__int64 a1, unsigned __int8 a2, __int64 a3, __int16 a4)
{
  __int64 v4; // rdi
  int v5; // ebx
  __int16 v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = a4;
  v4 = a1 + 400;
  v5 = RtlComputeToeplitzHash(a1 + 400, a3, a2, 0);
  return v5 ^ RtlComputeToeplitzHash(v4, &v7, 2, 0) | 0x80000000;
}

```

## disassembly

```asm
0x140004df0  mov     [rsp+arg_0], rbx
0x140004df5  mov     [rsp+arg_18], r9w
0x140004dfb  push    rdi
0x140004dfc  sub     rsp, 20h
0x140004e00  mov     rax, r8
0x140004e03  lea     rdi, [rcx+190h]
0x140004e0a  movzx   r8d, dl
0x140004e0e  mov     rcx, rdi
0x140004e11  mov     rdx, rax
0x140004e14  xor     r9d, r9d
0x140004e17  call    cs:__imp_RtlComputeToeplitzHash
0x140004e1e  nop     dword ptr [rax+rax+00h]
0x140004e23  xor     r9d, r9d
0x140004e26  lea     rdx, [rsp+28h+arg_18]
0x140004e2b  mov     r8d, 2
0x140004e31  mov     rcx, rdi
0x140004e34  mov     ebx, eax
0x140004e36  call    cs:__imp_RtlComputeToeplitzHash
0x140004e3d  nop     dword ptr [rax+rax+00h]
0x140004e42  xor     eax, ebx
0x140004e44  mov     rbx, [rsp+28h+arg_0]
0x140004e49  bts     eax, 1Fh
0x140004e4d  add     rsp, 20h
0x140004e51  pop     rdi
0x140004e52  retn
```
