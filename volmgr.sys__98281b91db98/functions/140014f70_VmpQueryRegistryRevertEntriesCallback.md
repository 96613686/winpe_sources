# VmpQueryRegistryRevertEntriesCallback

- ea: `0x140014f70`
- end: `0x140014fe2`
- name: `VmpQueryRegistryRevertEntriesCallback`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140005240`
- `0x140014f70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014f97`
- `ntoskrnl!ExAllocatePool2` at `0x140014f97`

## pseudocode

```c
__int64 __fastcall VmpQueryRegistryRevertEntriesCallback(
        __int64 a1,
        int a2,
        const void *a3,
        unsigned int a4,
        _QWORD *a5,
        unsigned int *a6)
{
  size_t v6; // rbx
  void *Pool2; // rax

  v6 = a4;
  if ( a2 == 3 )
  {
    Pool2 = (void *)ExAllocatePool2(258, a4, 538987862);
    *a5 = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    memmove(Pool2, a3, v6);
    *a6 = (unsigned int)v6 >> 5;
  }
  return 0;
}

```

## disassembly

```asm
0x140014f70  mov     [rsp+arg_0], rbx
0x140014f75  mov     [rsp+arg_8], rsi
0x140014f7a  push    rdi
0x140014f7b  sub     rsp, 20h
0x140014f7f  mov     ebx, r9d
0x140014f82  mov     rsi, r8
0x140014f85  cmp     edx, 3
0x140014f88  jnz     short loc_140014FCF
0x140014f8a  mov     r8d, 20204D56h
0x140014f90  mov     edx, ebx
0x140014f92  mov     ecx, 102h
0x140014f97  call    cs:__imp_ExAllocatePool2
0x140014f9e  nop     dword ptr [rax+rax+00h]
0x140014fa3  mov     rcx, [rsp+28h+arg_20]
0x140014fa8  mov     [rcx], rax
0x140014fab  test    rax, rax
0x140014fae  jnz     short loc_140014FB7
0x140014fb0  mov     eax, 0C000009Ah
0x140014fb5  jmp     short loc_140014FD1
0x140014fb7  mov     r8, rbx; Size
0x140014fba  mov     rdx, rsi; Src
0x140014fbd  mov     rcx, rax; void *
0x140014fc0  call    memmove
0x140014fc5  mov     rax, [rsp+28h+arg_28]
0x140014fca  shr     ebx, 5
0x140014fcd  mov     [rax], ebx
0x140014fcf  xor     eax, eax
0x140014fd1  mov     rbx, [rsp+28h+arg_0]
0x140014fd6  mov     rsi, [rsp+28h+arg_8]
0x140014fdb  add     rsp, 20h
0x140014fdf  pop     rdi
0x140014fe0  retn
```
