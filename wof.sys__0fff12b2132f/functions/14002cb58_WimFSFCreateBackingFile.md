# WimFSFCreateBackingFile

- ea: `0x14002cb58`
- end: `0x14002cbdd`
- name: `WimFSFCreateBackingFile`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c53c`

## callees

- `0x1400119c0`
- `0x14002cb58`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cb75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cb75`
- `FLTMGR!FltInitializePushLock` at `0x14002cbc0`
- `FLTMGR!FltInitializePushLock` at `0x14002cbc0`

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
0x14002cb58  mov     [rsp+arg_0], rbx
0x14002cb5d  push    rdi
0x14002cb5e  sub     rsp, 20h
0x14002cb62  mov     rdi, rcx
0x14002cb65  mov     edx, 440h; NumberOfBytes
0x14002cb6a  mov     ecx, 200h; PoolType
0x14002cb6f  mov     r8d, 66777077h; Tag
0x14002cb75  call    cs:__imp_ExAllocatePoolWithTag
0x14002cb7c  nop     dword ptr [rax+rax+00h]
0x14002cb81  mov     rbx, rax
0x14002cb84  test    rax, rax
0x14002cb87  jnz     short loc_14002CB90
0x14002cb89  mov     eax, 0C000009Ah
0x14002cb8e  jmp     short loc_14002CBD1
0x14002cb90  xor     edx, edx; Val
0x14002cb92  mov     r8d, 440h; Size
0x14002cb98  mov     rcx, rbx; void *
0x14002cb9b  call    memset
0x14002cba0  mov     dword ptr [rbx+38h], 1
0x14002cba7  lea     rax, [rbx+10h]
0x14002cbab  mov     [rbx+8], rbx
0x14002cbaf  lea     rcx, [rbx+3F0h]; PushLock
0x14002cbb6  mov     [rbx], rbx
0x14002cbb9  mov     [rax+8], rax
0x14002cbbd  mov     [rax], rax
0x14002cbc0  call    cs:__imp_FltInitializePushLock
0x14002cbc7  nop     dword ptr [rax+rax+00h]
0x14002cbcc  xor     eax, eax
0x14002cbce  mov     [rdi], rbx
0x14002cbd1  mov     rbx, [rsp+28h+arg_0]
0x14002cbd6  add     rsp, 20h
0x14002cbda  pop     rdi
0x14002cbdb  retn
```
