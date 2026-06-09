# UdfCreateFcbNonPaged

- ea: `0x14002f938`
- end: `0x14002fa07`
- name: `UdfCreateFcbNonPaged`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004fc70`

## callees

- `0x14001c080`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14002f96f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002f97f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002f96f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002f97f`
- `ntoskrnl!KeInitializeEvent` at `0x14002f9b8`
- `ntoskrnl!KeInitializeEvent` at `0x14002f9f1`
- `ntoskrnl!KeInitializeEvent` at `0x14002f9b8`
- `ntoskrnl!KeInitializeEvent` at `0x14002f9f1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002f945`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002f945`

## pseudocode

```c
char *UdfCreateFcbNonPaged()
{
  char *v0; // rbx

  v0 = (char *)ExAllocateFromNPagedLookasideList(&UdfFcbNonPagedLookasideList);
  memset(v0 + 4, 0, 0x144u);
  *(_DWORD *)v0 = 21498173;
  ExInitializeResourceLite((PERESOURCE)(v0 + 112));
  ExInitializeResourceLite((PERESOURCE)(v0 + 8));
  *((_DWORD *)v0 + 54) = 1;
  *((_QWORD *)v0 + 28) = 0;
  *((_DWORD *)v0 + 58) = 0;
  KeInitializeEvent((PRKEVENT)v0 + 10, SynchronizationEvent, 0);
  *((_DWORD *)v0 + 68) = 1;
  *((_QWORD *)v0 + 35) = 0;
  *((_DWORD *)v0 + 72) = 0;
  KeInitializeEvent((PRKEVENT)(v0 + 296), SynchronizationEvent, 0);
  return v0;
}

```

## disassembly

```asm
0x14002f938  push    rbx
0x14002f93a  sub     rsp, 20h
0x14002f93e  lea     rcx, UdfFcbNonPagedLookasideList; Lookaside
0x14002f945  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002f94c  nop     dword ptr [rax+rax+00h]
0x14002f951  xor     edx, edx; Val
0x14002f953  mov     r8d, 144h; Size
0x14002f959  mov     rbx, rax
0x14002f95c  lea     rcx, [rax+4]; void *
0x14002f960  call    memset
0x14002f965  lea     rcx, [rbx+70h]; Resource
0x14002f969  mov     dword ptr [rbx], 148093Dh
0x14002f96f  call    cs:__imp_ExInitializeResourceLite
0x14002f976  nop     dword ptr [rax+rax+00h]
0x14002f97b  lea     rcx, [rbx+8]; Resource
0x14002f97f  call    cs:__imp_ExInitializeResourceLite
0x14002f986  nop     dword ptr [rax+rax+00h]
0x14002f98b  xor     r8d, r8d; State
0x14002f98e  mov     dword ptr [rbx+0D8h], 1
0x14002f998  lea     rcx, [rbx+0F0h]; Event
0x14002f99f  mov     qword ptr [rbx+0E0h], 0
0x14002f9aa  mov     dword ptr [rbx+0E8h], 0
0x14002f9b4  lea     edx, [r8+1]; Type
0x14002f9b8  call    cs:__imp_KeInitializeEvent
0x14002f9bf  nop     dword ptr [rax+rax+00h]
0x14002f9c4  xor     r8d, r8d; State
0x14002f9c7  mov     dword ptr [rbx+110h], 1
0x14002f9d1  lea     rcx, [rbx+128h]; Event
0x14002f9d8  mov     qword ptr [rbx+118h], 0
0x14002f9e3  mov     dword ptr [rbx+120h], 0
0x14002f9ed  lea     edx, [r8+1]; Type
0x14002f9f1  call    cs:__imp_KeInitializeEvent
0x14002f9f8  nop     dword ptr [rax+rax+00h]
0x14002f9fd  mov     rax, rbx
0x14002fa00  add     rsp, 20h
0x14002fa04  pop     rbx
0x14002fa05  retn
```
