# BusChCreateAwWorkItem

- ea: `0x140006f60`
- end: `0x140006fc6`
- name: `BusChCreateAwWorkItem`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140006f60`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140006f7e`
- `ntoskrnl!ExAllocatePool2` at `0x140006f7e`

## pseudocode

```c
__int64 __fastcall BusChCreateAwWorkItem(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 Pool2; // rax

  Pool2 = ExAllocatePool2(64, 56, 1937072726);
  if ( !Pool2 )
    return 3221225626LL;
  *(_OWORD *)Pool2 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_OWORD *)(Pool2 + 32) = 0;
  *(_QWORD *)(Pool2 + 48) = 0;
  *(_DWORD *)(Pool2 + 48) = -1;
  *(_QWORD *)(Pool2 + 32) = a2;
  *a3 = Pool2;
  return 0;
}

```

## disassembly

```asm
0x140006f60  mov     [rsp+arg_0], rbx
0x140006f65  push    rdi
0x140006f66  sub     rsp, 20h
0x140006f6a  mov     rdi, rdx
0x140006f6d  mov     rbx, r8
0x140006f70  mov     edx, 38h ; '8'
0x140006f75  mov     r8d, 73756256h
0x140006f7b  lea     ecx, [rdx+8]
0x140006f7e  call    cs:__imp_ExAllocatePool2
0x140006f85  nop     dword ptr [rax+rax+00h]
0x140006f8a  test    rax, rax
0x140006f8d  jnz     short loc_140006F96
0x140006f8f  mov     eax, 0C000009Ah
0x140006f94  jmp     short loc_140006FBA
0x140006f96  xorps   xmm0, xmm0
0x140006f99  xor     ecx, ecx
0x140006f9b  movups  xmmword ptr [rax], xmm0
0x140006f9e  movups  xmmword ptr [rax+10h], xmm0
0x140006fa2  movups  xmmword ptr [rax+20h], xmm0
0x140006fa6  mov     [rax+30h], rcx
0x140006faa  mov     dword ptr [rax+30h], 0FFFFFFFFh
0x140006fb1  mov     [rax+20h], rdi
0x140006fb5  mov     [rbx], rax
0x140006fb8  xor     eax, eax
0x140006fba  mov     rbx, [rsp+28h+arg_0]
0x140006fbf  add     rsp, 20h
0x140006fc3  pop     rdi
0x140006fc4  retn
```
