# VsmmVaGpaCorepProcessContextTeardown

- ea: `0x1400e6030`
- end: `0x1400e60c4`
- name: `VsmmVaGpaCorepProcessContextTeardown`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140078cb4`
- `0x1400e55bc`
- `0x1400eb1a8`

## callees

- `0x140030790`
- `0x1400307d0`
- `0x1400e6030`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400e6067`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400e6085`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400e6067`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400e6085`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400e609a`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400e609a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e60ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e60ae`

## pseudocode

```c
void __fastcall VsmmVaGpaCorepProcessContextTeardown(__int64 a1, __int64 a2)
{
  char *v2; // rdi
  char *v5; // rsi

  v2 = (char *)VidDeviceExtension;
  v5 = (char *)VidDeviceExtension + 1840;
  VidLockAcquireExclusive((char *)VidDeviceExtension + 1840);
  if ( *(_QWORD *)(a2 + 40) != -1 )
    RtlRbRemoveNode(v2 + 1824, a2 + 24);
  VidLockRelease(v5);
  RtlRbRemoveNode(a1 + 10808, a2);
  ObfDereferenceObjectWithTag(*(PVOID *)(a2 + 56), 0x72446456u);
  ExFreePoolWithTag((PVOID)a2, 0x6D4D6456u);
}

```

## disassembly

```asm
0x1400e6030  push    rbx
0x1400e6032  push    rbp
0x1400e6033  push    rsi
0x1400e6034  push    rdi
0x1400e6035  sub     rsp, 28h
0x1400e6039  mov     rdi, cs:VidDeviceExtension
0x1400e6040  mov     rbp, rcx
0x1400e6043  mov     rbx, rdx
0x1400e6046  lea     rsi, [rdi+730h]
0x1400e604d  mov     rcx, rsi
0x1400e6050  call    VidLockAcquireExclusive
0x1400e6055  cmp     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1400e605a  jz      short loc_1400E6073
0x1400e605c  lea     rdx, [rbx+18h]
0x1400e6060  lea     rcx, [rdi+720h]
0x1400e6067  call    cs:__imp_RtlRbRemoveNode
0x1400e606e  nop     dword ptr [rax+rax+00h]
0x1400e6073  mov     rcx, rsi
0x1400e6076  call    VidLockRelease
0x1400e607b  lea     rcx, [rbp+2A38h]
0x1400e6082  mov     rdx, rbx
0x1400e6085  call    cs:__imp_RtlRbRemoveNode
0x1400e608c  nop     dword ptr [rax+rax+00h]
0x1400e6091  mov     rcx, [rbx+38h]; Object
0x1400e6095  mov     edx, 72446456h; Tag
0x1400e609a  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400e60a1  nop     dword ptr [rax+rax+00h]
0x1400e60a6  mov     edx, 6D4D6456h; Tag
0x1400e60ab  mov     rcx, rbx; P
0x1400e60ae  call    cs:__imp_ExFreePoolWithTag
0x1400e60b5  nop     dword ptr [rax+rax+00h]
0x1400e60ba  add     rsp, 28h
0x1400e60be  pop     rdi
0x1400e60bf  pop     rsi
0x1400e60c0  pop     rbp
0x1400e60c1  pop     rbx
0x1400e60c2  retn
```
