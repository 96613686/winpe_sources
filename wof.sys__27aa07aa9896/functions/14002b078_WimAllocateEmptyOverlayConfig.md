# WimAllocateEmptyOverlayConfig

- ea: `0x14002b078`
- end: `0x14002b0e8`
- name: `WimAllocateEmptyOverlayConfig`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003c5c8`

## callees

- `0x14002b078`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b096`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b096`

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
0x14002b078  mov     [rsp+arg_0], rbx
0x14002b07d  push    rdi
0x14002b07e  sub     rsp, 20h
0x14002b082  mov     rbx, rdx
0x14002b085  mov     rdi, rcx
0x14002b088  mov     edx, 18h; NumberOfBytes
0x14002b08d  mov     r8d, 66637077h; Tag
0x14002b093  lea     ecx, [rdx-17h]; PoolType
0x14002b096  call    cs:__imp_ExAllocatePoolWithTag
0x14002b09d  nop     dword ptr [rax+rax+00h]
0x14002b0a2  test    rax, rax
0x14002b0a5  jnz     short loc_14002B0AE
0x14002b0a7  mov     eax, 0C000009Ah
0x14002b0ac  jmp     short loc_14002B0DC
0x14002b0ae  mov     qword ptr [rax+0Ch], 0
0x14002b0b6  mov     dword ptr [rax+14h], 0
0x14002b0bd  mov     dword ptr [rax], 66436F57h
0x14002b0c3  mov     dword ptr [rax+4], 1
0x14002b0ca  mov     dword ptr [rax+8], 28h ; '('
0x14002b0d1  mov     [rdi], rax
0x14002b0d4  xor     eax, eax
0x14002b0d6  mov     dword ptr [rbx], 18h
0x14002b0dc  mov     rbx, [rsp+28h+arg_0]
0x14002b0e1  add     rsp, 20h
0x14002b0e5  pop     rdi
0x14002b0e6  retn
```
