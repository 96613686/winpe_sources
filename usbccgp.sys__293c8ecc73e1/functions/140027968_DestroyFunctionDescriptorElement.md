# DestroyFunctionDescriptorElement

- ea: `0x140027968`
- end: `0x1400279e2`
- name: `DestroyFunctionDescriptorElement`
- size: `122`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400275b0`
- `0x1400281ac`
- `0x1400282e4`
- `0x1400283ac`

## callees

- `0x140015100`
- `0x140027968`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002797c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027993`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002797c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027993`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400279c1`

## pseudocode

```c
void *__fastcall DestroyFunctionDescriptorElement(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)a1[1];
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  v3 = (void *)a1[3];
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  v4 = (void *)a1[5];
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  v5 = (void *)a1[7];
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return memset(a1, 0, 0x50u);
}

```

## disassembly

```asm
0x140027968  push    rbx
0x14002796a  sub     rsp, 20h
0x14002796e  mov     rbx, rcx
0x140027971  mov     rcx, [rcx+8]; P
0x140027975  test    rcx, rcx
0x140027978  jz      short loc_140027988
0x14002797a  xor     edx, edx; Tag
0x14002797c  call    cs:__imp_ExFreePoolWithTag
0x140027983  nop     dword ptr [rax+rax+00h]
0x140027988  mov     rcx, [rbx+18h]; P
0x14002798c  test    rcx, rcx
0x14002798f  jz      short loc_14002799F
0x140027991  xor     edx, edx; Tag
0x140027993  call    cs:__imp_ExFreePoolWithTag
0x14002799a  nop     dword ptr [rax+rax+00h]
0x14002799f  mov     rcx, [rbx+28h]; P
0x1400279a3  test    rcx, rcx
0x1400279a6  jz      short loc_1400279B6
0x1400279a8  xor     edx, edx; Tag
0x1400279aa  call    cs:__imp_ExFreePoolWithTag
0x1400279b1  nop     dword ptr [rax+rax+00h]
0x1400279b6  mov     rcx, [rbx+38h]; P
0x1400279ba  test    rcx, rcx
0x1400279bd  jz      short loc_1400279CD
0x1400279bf  xor     edx, edx; Tag
0x1400279c1  call    cs:__imp_ExFreePoolWithTag
0x1400279c8  nop     dword ptr [rax+rax+00h]
0x1400279cd  xor     edx, edx; Val
0x1400279cf  mov     rcx, rbx; void *
0x1400279d2  lea     r8d, [rdx+50h]; Size
0x1400279d6  call    memset
0x1400279db  add     rsp, 20h
0x1400279df  pop     rbx
0x1400279e0  retn
```
