# PipeCreate

- ea: `0x14002f340`
- end: `0x14002f3d6`
- name: `PipeCreate`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002846c`
- `0x14002c0f0`

## callees

- `0x14002f340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002f368`
- `ntoskrnl!ExAllocatePool2` at `0x14002f368`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002f386`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002f386`

## pseudocode

```c
__int64 __fastcall PipeCreate(char a1, KSPIN_LOCK **a2)
{
  __int64 result; // rax
  KSPIN_LOCK *Pool2; // rax
  KSPIN_LOCK *v5; // rbx

  if ( a1 )
    return 3221225659LL;
  Pool2 = (KSPIN_LOCK *)ExAllocatePool2(64, 448, 1937072726);
  v5 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  KeInitializeSpinLock(Pool2);
  v5[36] = 0;
  v5[3] = (KSPIN_LOCK)(v5 + 2);
  v5[2] = (KSPIN_LOCK)(v5 + 2);
  v5[5] = (KSPIN_LOCK)(v5 + 4);
  v5[4] = (KSPIN_LOCK)(v5 + 4);
  v5[7] = (KSPIN_LOCK)(v5 + 6);
  v5[6] = (KSPIN_LOCK)(v5 + 6);
  result = 0;
  *((_DWORD *)v5 + 2) = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x14002f340  mov     [rsp+arg_0], rbx
0x14002f345  push    rdi
0x14002f346  sub     rsp, 20h
0x14002f34a  mov     rdi, rdx
0x14002f34d  test    cl, cl
0x14002f34f  jz      short loc_14002F358
0x14002f351  mov     eax, 0C00000BBh
0x14002f356  jmp     short loc_14002F3CA
0x14002f358  mov     edx, 1C0h
0x14002f35d  mov     ecx, 40h ; '@'
0x14002f362  mov     r8d, 73756256h
0x14002f368  call    cs:__imp_ExAllocatePool2
0x14002f36f  nop     dword ptr [rax+rax+00h]
0x14002f374  mov     rbx, rax
0x14002f377  test    rax, rax
0x14002f37a  jnz     short loc_14002F383
0x14002f37c  mov     eax, 0C000009Ah
0x14002f381  jmp     short loc_14002F3CA
0x14002f383  mov     rcx, rbx; SpinLock
0x14002f386  call    cs:__imp_KeInitializeSpinLock
0x14002f38d  nop     dword ptr [rax+rax+00h]
0x14002f392  lea     rax, [rbx+10h]
0x14002f396  mov     qword ptr [rbx+120h], 0
0x14002f3a1  mov     [rax+8], rax
0x14002f3a5  mov     [rax], rax
0x14002f3a8  lea     rax, [rbx+20h]
0x14002f3ac  mov     [rax+8], rax
0x14002f3b0  mov     [rax], rax
0x14002f3b3  lea     rax, [rbx+30h]
0x14002f3b7  mov     [rax+8], rax
0x14002f3bb  mov     [rax], rax
0x14002f3be  xor     eax, eax
0x14002f3c0  mov     dword ptr [rbx+8], 0
0x14002f3c7  mov     [rdi], rbx
0x14002f3ca  mov     rbx, [rsp+28h+arg_0]
0x14002f3cf  add     rsp, 20h
0x14002f3d3  pop     rdi
0x14002f3d4  retn
```
