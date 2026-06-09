# PipeCreate

- ea: `0x14002f2f0`
- end: `0x14002f386`
- name: `PipeCreate`
- size: `150`
- prototype: `__int64 __fastcall(char, KSPIN_LOCK **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002841c`
- `0x14002c0a0`

## callees

- `0x14002f2f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002f318`
- `ntoskrnl!ExAllocatePool2` at `0x14002f318`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002f336`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002f336`

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
0x14002f2f0  mov     [rsp+arg_0], rbx
0x14002f2f5  push    rdi
0x14002f2f6  sub     rsp, 20h
0x14002f2fa  mov     rdi, rdx
0x14002f2fd  test    cl, cl
0x14002f2ff  jz      short loc_14002F308
0x14002f301  mov     eax, 0C00000BBh
0x14002f306  jmp     short loc_14002F37A
0x14002f308  mov     edx, 1C0h
0x14002f30d  mov     ecx, 40h ; '@'
0x14002f312  mov     r8d, 73756256h
0x14002f318  call    cs:__imp_ExAllocatePool2
0x14002f31f  nop     dword ptr [rax+rax+00h]
0x14002f324  mov     rbx, rax
0x14002f327  test    rax, rax
0x14002f32a  jnz     short loc_14002F333
0x14002f32c  mov     eax, 0C000009Ah
0x14002f331  jmp     short loc_14002F37A
0x14002f333  mov     rcx, rbx; SpinLock
0x14002f336  call    cs:__imp_KeInitializeSpinLock
0x14002f33d  nop     dword ptr [rax+rax+00h]
0x14002f342  lea     rax, [rbx+10h]
0x14002f346  mov     qword ptr [rbx+120h], 0
0x14002f351  mov     [rax+8], rax
0x14002f355  mov     [rax], rax
0x14002f358  lea     rax, [rbx+20h]
0x14002f35c  mov     [rax+8], rax
0x14002f360  mov     [rax], rax
0x14002f363  lea     rax, [rbx+30h]
0x14002f367  mov     [rax+8], rax
0x14002f36b  mov     [rax], rax
0x14002f36e  xor     eax, eax
0x14002f370  mov     dword ptr [rbx+8], 0
0x14002f377  mov     [rdi], rbx
0x14002f37a  mov     rbx, [rsp+28h+arg_0]
0x14002f37f  add     rsp, 20h
0x14002f383  pop     rdi
0x14002f384  retn
```
