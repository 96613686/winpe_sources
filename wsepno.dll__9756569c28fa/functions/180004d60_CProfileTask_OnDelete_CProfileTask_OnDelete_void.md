# CProfileTask_OnDelete::~CProfileTask_OnDelete(void)

- ea: `0x180004d60`
- end: `0x180004da5`
- name: `??1CProfileTask_OnDelete@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CProfileTask_OnDelete *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005510`

## callees

- `0x180003be0`

## pseudocode

```c
void __fastcall CProfileTask_OnDelete::~CProfileTask_OnDelete(void **this, void *a2)
{
  void *v3; // rcx
  void *v4; // rdx

  *this = &CProfileTask_OnDelete::`vftable';
  ProfNotif_HeapFree(this[2], a2);
  v3 = this[3];
  this[2] = 0;
  ProfNotif_HeapFree(v3, v4);
  this[3] = 0;
  *this = &CProfileTask::`vftable';
}

```

## disassembly

```asm
0x180004d60  push    rbx
0x180004d62  sub     rsp, 20h
0x180004d66  lea     rax, ??_7CProfileTask_OnDelete@@6B@; const CProfileTask_OnDelete::`vftable'
0x180004d6d  mov     rbx, rcx
0x180004d70  mov     [rcx], rax
0x180004d73  mov     rcx, [rcx+10h]; lpMem
0x180004d77  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180004d7c  mov     rcx, [rbx+18h]; lpMem
0x180004d80  mov     qword ptr [rbx+10h], 0
0x180004d88  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180004d8d  lea     rax, ??_7CProfileTask@@6B@; const CProfileTask::`vftable'
0x180004d94  mov     qword ptr [rbx+18h], 0
0x180004d9c  mov     [rbx], rax
0x180004d9f  add     rsp, 20h
0x180004da3  pop     rbx
0x180004da4  retn
```
