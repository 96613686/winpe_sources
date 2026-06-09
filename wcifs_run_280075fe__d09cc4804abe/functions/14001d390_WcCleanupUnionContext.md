# WcCleanupUnionContext

- ea: `0x14001d390`
- end: `0x14001d424`
- name: `WcCleanupUnionContext`
- size: `148`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002ee54`

## callees

- `0x14001d390`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001d3ab`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001d3ab`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d3bc`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001d3bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d40c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d40c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d3db`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d3db`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d3f8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d3f8`

## pseudocode

```c
void __fastcall WcCleanupUnionContext(_DWORD *P)
{
  struct _RTL_AVL_TABLE *v2; // rdi
  BOOLEAN i; // dl
  PVOID v4; // rax

  v2 = (struct _RTL_AVL_TABLE *)(P + 16);
  for ( i = 1; ; i = 0 )
  {
    v4 = RtlEnumerateGenericTableAvl(v2, i);
    if ( !v4 )
      break;
    RtlDeleteElementGenericTableAvl(v2, v4);
  }
  if ( (P[8] & 1) != 0 )
  {
    ExAcquireFastMutex(&FastMutex);
    --dword_14000E244;
    P[8] &= ~1u;
    ExReleaseFastMutex(&FastMutex);
  }
  ExFreePoolWithTag(P, 0x63754357u);
}

```

## disassembly

```asm
0x14001d390  mov     [rsp+arg_0], rbx
0x14001d395  push    rdi
0x14001d396  sub     rsp, 20h
0x14001d39a  mov     rbx, rcx
0x14001d39d  lea     rdi, [rcx+40h]
0x14001d3a1  mov     dl, 1
0x14001d3a3  jmp     short loc_14001D3B9
0x14001d3a5  mov     rdx, rax; Buffer
0x14001d3a8  mov     rcx, rdi; Table
0x14001d3ab  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14001d3b2  nop     dword ptr [rax+rax+00h]
0x14001d3b7  xor     edx, edx; Restart
0x14001d3b9  mov     rcx, rdi; Table
0x14001d3bc  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14001d3c3  nop     dword ptr [rax+rax+00h]
0x14001d3c8  test    rax, rax
0x14001d3cb  jnz     short loc_14001D3A5
0x14001d3cd  mov     eax, [rbx+20h]
0x14001d3d0  test    al, 1
0x14001d3d2  jz      short loc_14001D404
0x14001d3d4  lea     rcx, FastMutex; FastMutex
0x14001d3db  call    cs:__imp_ExAcquireFastMutex
0x14001d3e2  nop     dword ptr [rax+rax+00h]
0x14001d3e7  dec     cs:dword_14000E244
0x14001d3ed  lea     rcx, FastMutex; FastMutex
0x14001d3f4  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x14001d3f8  call    cs:__imp_ExReleaseFastMutex
0x14001d3ff  nop     dword ptr [rax+rax+00h]
0x14001d404  mov     edx, 63754357h; Tag
0x14001d409  mov     rcx, rbx; P
0x14001d40c  call    cs:__imp_ExFreePoolWithTag
0x14001d413  nop     dword ptr [rax+rax+00h]
0x14001d418  mov     rbx, [rsp+28h+arg_0]
0x14001d41d  add     rsp, 20h
0x14001d421  pop     rdi
0x14001d422  retn
```
