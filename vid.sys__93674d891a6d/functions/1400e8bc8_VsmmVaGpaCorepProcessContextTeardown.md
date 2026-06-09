# VsmmVaGpaCorepProcessContextTeardown

- ea: `0x1400e8bc8`
- end: `0x1400e8c5c`
- name: `VsmmVaGpaCorepProcessContextTeardown`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140079b90`
- `0x1400e8154`
- `0x1400ede88`

## callees

- `0x140030990`
- `0x1400309d0`
- `0x1400e8bc8`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400e8bff`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400e8c1d`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400e8bff`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400e8c1d`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400e8c32`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400e8c32`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e8c46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e8c46`

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
0x1400e8bc8  push    rbx
0x1400e8bca  push    rbp
0x1400e8bcb  push    rsi
0x1400e8bcc  push    rdi
0x1400e8bcd  sub     rsp, 28h
0x1400e8bd1  mov     rdi, cs:VidDeviceExtension
0x1400e8bd8  mov     rbp, rcx
0x1400e8bdb  mov     rbx, rdx
0x1400e8bde  lea     rsi, [rdi+730h]
0x1400e8be5  mov     rcx, rsi
0x1400e8be8  call    VidLockAcquireExclusive
0x1400e8bed  cmp     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1400e8bf2  jz      short loc_1400E8C0B
0x1400e8bf4  lea     rdx, [rbx+18h]
0x1400e8bf8  lea     rcx, [rdi+720h]
0x1400e8bff  call    cs:__imp_RtlRbRemoveNode
0x1400e8c06  nop     dword ptr [rax+rax+00h]
0x1400e8c0b  mov     rcx, rsi
0x1400e8c0e  call    VidLockRelease
0x1400e8c13  lea     rcx, [rbp+2A38h]
0x1400e8c1a  mov     rdx, rbx
0x1400e8c1d  call    cs:__imp_RtlRbRemoveNode
0x1400e8c24  nop     dword ptr [rax+rax+00h]
0x1400e8c29  mov     rcx, [rbx+38h]; Object
0x1400e8c2d  mov     edx, 72446456h; Tag
0x1400e8c32  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400e8c39  nop     dword ptr [rax+rax+00h]
0x1400e8c3e  mov     edx, 6D4D6456h; Tag
0x1400e8c43  mov     rcx, rbx; P
0x1400e8c46  call    cs:__imp_ExFreePoolWithTag
0x1400e8c4d  nop     dword ptr [rax+rax+00h]
0x1400e8c52  add     rsp, 28h
0x1400e8c56  pop     rdi
0x1400e8c57  pop     rsi
0x1400e8c58  pop     rbp
0x1400e8c59  pop     rbx
0x1400e8c5a  retn
```
