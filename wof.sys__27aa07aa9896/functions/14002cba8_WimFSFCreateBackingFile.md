# WimFSFCreateBackingFile

- ea: `0x14002cba8`
- end: `0x14002cc2d`
- name: `WimFSFCreateBackingFile`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c58c`

## callees

- `0x1400119c0`
- `0x14002cba8`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cbc5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cbc5`
- `FLTMGR!FltInitializePushLock` at `0x14002cc10`
- `FLTMGR!FltInitializePushLock` at `0x14002cc10`

## pseudocode

```c
__int64 __fastcall WimFSFCreateBackingFile(_QWORD *a1)
{
  char *PoolWithTag; // rax
  char *v3; // rbx
  __int64 result; // rax

  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x440u, 0x66777077u);
  v3 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0x440u);
  *((_DWORD *)v3 + 14) = 1;
  *((_QWORD *)v3 + 1) = v3;
  *(_QWORD *)v3 = v3;
  *((_QWORD *)v3 + 3) = v3 + 16;
  *((_QWORD *)v3 + 2) = v3 + 16;
  FltInitializePushLock((PULONG_PTR)v3 + 126);
  result = 0;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x14002cba8  mov     [rsp+arg_0], rbx
0x14002cbad  push    rdi
0x14002cbae  sub     rsp, 20h
0x14002cbb2  mov     rdi, rcx
0x14002cbb5  mov     edx, 440h; NumberOfBytes
0x14002cbba  mov     ecx, 200h; PoolType
0x14002cbbf  mov     r8d, 66777077h; Tag
0x14002cbc5  call    cs:__imp_ExAllocatePoolWithTag
0x14002cbcc  nop     dword ptr [rax+rax+00h]
0x14002cbd1  mov     rbx, rax
0x14002cbd4  test    rax, rax
0x14002cbd7  jnz     short loc_14002CBE0
0x14002cbd9  mov     eax, 0C000009Ah
0x14002cbde  jmp     short loc_14002CC21
0x14002cbe0  xor     edx, edx; Val
0x14002cbe2  mov     r8d, 440h; Size
0x14002cbe8  mov     rcx, rbx; void *
0x14002cbeb  call    memset
0x14002cbf0  mov     dword ptr [rbx+38h], 1
0x14002cbf7  lea     rax, [rbx+10h]
0x14002cbfb  mov     [rbx+8], rbx
0x14002cbff  lea     rcx, [rbx+3F0h]; PushLock
0x14002cc06  mov     [rbx], rbx
0x14002cc09  mov     [rax+8], rax
0x14002cc0d  mov     [rax], rax
0x14002cc10  call    cs:__imp_FltInitializePushLock
0x14002cc17  nop     dword ptr [rax+rax+00h]
0x14002cc1c  xor     eax, eax
0x14002cc1e  mov     [rdi], rbx
0x14002cc21  mov     rbx, [rsp+28h+arg_0]
0x14002cc26  add     rsp, 20h
0x14002cc2a  pop     rdi
0x14002cc2b  retn
```
