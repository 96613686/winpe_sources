# WimAllocateEmptyOverlayConfig

- ea: `0x14002b028`
- end: `0x14002b098`
- name: `WimAllocateEmptyOverlayConfig`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003c578`

## callees

- `0x14002b028`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b046`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b046`

## pseudocode

```c
__int64 __fastcall WimAllocateEmptyOverlayConfig(_QWORD *a1, _DWORD *a2)
{
  char *PoolWithTag; // rax
  __int64 result; // rax

  PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x18u, 0x66637077u);
  if ( !PoolWithTag )
    return 3221225626LL;
  *(_QWORD *)(PoolWithTag + 12) = 0;
  *((_DWORD *)PoolWithTag + 5) = 0;
  *(_DWORD *)PoolWithTag = 1715695447;
  *((_DWORD *)PoolWithTag + 1) = 1;
  *((_DWORD *)PoolWithTag + 2) = 40;
  *a1 = PoolWithTag;
  result = 0;
  *a2 = 24;
  return result;
}

```

## disassembly

```asm
0x14002b028  mov     [rsp+arg_0], rbx
0x14002b02d  push    rdi
0x14002b02e  sub     rsp, 20h
0x14002b032  mov     rbx, rdx
0x14002b035  mov     rdi, rcx
0x14002b038  mov     edx, 18h; NumberOfBytes
0x14002b03d  mov     r8d, 66637077h; Tag
0x14002b043  lea     ecx, [rdx-17h]; PoolType
0x14002b046  call    cs:__imp_ExAllocatePoolWithTag
0x14002b04d  nop     dword ptr [rax+rax+00h]
0x14002b052  test    rax, rax
0x14002b055  jnz     short loc_14002B05E
0x14002b057  mov     eax, 0C000009Ah
0x14002b05c  jmp     short loc_14002B08C
0x14002b05e  mov     qword ptr [rax+0Ch], 0
0x14002b066  mov     dword ptr [rax+14h], 0
0x14002b06d  mov     dword ptr [rax], 66436F57h
0x14002b073  mov     dword ptr [rax+4], 1
0x14002b07a  mov     dword ptr [rax+8], 28h ; '('
0x14002b081  mov     [rdi], rax
0x14002b084  xor     eax, eax
0x14002b086  mov     dword ptr [rbx], 18h
0x14002b08c  mov     rbx, [rsp+28h+arg_0]
0x14002b091  add     rsp, 20h
0x14002b095  pop     rdi
0x14002b096  retn
```
