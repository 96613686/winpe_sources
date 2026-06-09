# SlbNatCreateExternalAddress

- ea: `0x14003005c`
- end: `0x1400300bb`
- name: `SlbNatCreateExternalAddress`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14002f880`
- `0x140035580`

## callees

- `0x14001448c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400300a1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400300a1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140030073`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140030073`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddress(__int64 a1, __int16 *a2)
{
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  LODWORD(a2) = SlbNatCreateExternalAddressWithLock(a1, a2, 0, 1, 0);
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x14003005c  mov     [rsp+arg_0], rbx
0x140030061  push    rdi
0x140030062  sub     rsp, 30h
0x140030066  mov     rdi, rcx
0x140030069  mov     rbx, rdx
0x14003006c  lea     rcx, Resource; Resource
0x140030073  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14003007a  nop     dword ptr [rax+rax+00h]
0x14003007f  mov     r9b, 1
0x140030082  mov     [rsp+38h+var_18], 0
0x14003008a  xor     r8d, r8d
0x14003008d  mov     rdx, rbx
0x140030090  mov     rcx, rdi
0x140030093  call    SlbNatCreateExternalAddressWithLock
0x140030098  lea     rcx, Resource; Resource
0x14003009f  mov     ebx, eax
0x1400300a1  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400300a8  nop     dword ptr [rax+rax+00h]
0x1400300ad  mov     eax, ebx
0x1400300af  mov     rbx, [rsp+38h+arg_0]
0x1400300b4  add     rsp, 30h
0x1400300b8  pop     rdi
0x1400300b9  retn
```
