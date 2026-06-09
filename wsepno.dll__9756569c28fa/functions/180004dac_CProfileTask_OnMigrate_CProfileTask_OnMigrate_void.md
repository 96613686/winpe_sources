# CProfileTask_OnMigrate::~CProfileTask_OnMigrate(void)

- ea: `0x180004dac`
- end: `0x180004e02`
- name: `??1CProfileTask_OnMigrate@@UEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CProfileTask_OnMigrate *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005550`

## callees

- `0x180003be0`

## pseudocode

```c
void __fastcall CProfileTask_OnMigrate::~CProfileTask_OnMigrate(void **this, void *a2)
{
  void *v3; // rcx
  void *v4; // rdx
  void *v5; // rcx
  void *v6; // rdx

  *this = &CProfileTask_OnMigrate::`vftable';
  ProfNotif_HeapFree(this[1], a2);
  v3 = this[2];
  this[1] = 0;
  ProfNotif_HeapFree(v3, v4);
  v5 = this[3];
  this[2] = 0;
  ProfNotif_HeapFree(v5, v6);
  this[3] = 0;
  *this = &CProfileTask::`vftable';
}

```

## disassembly

```asm
0x180004dac  push    rbx
0x180004dae  sub     rsp, 20h
0x180004db2  lea     rax, ??_7CProfileTask_OnMigrate@@6B@; const CProfileTask_OnMigrate::`vftable'
0x180004db9  mov     rbx, rcx
0x180004dbc  mov     [rcx], rax
0x180004dbf  mov     rcx, [rcx+8]; lpMem
0x180004dc3  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180004dc8  mov     rcx, [rbx+10h]; lpMem
0x180004dcc  mov     qword ptr [rbx+8], 0
0x180004dd4  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180004dd9  mov     rcx, [rbx+18h]; lpMem
0x180004ddd  mov     qword ptr [rbx+10h], 0
0x180004de5  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180004dea  lea     rax, ??_7CProfileTask@@6B@; const CProfileTask::`vftable'
0x180004df1  mov     qword ptr [rbx+18h], 0
0x180004df9  mov     [rbx], rax
0x180004dfc  add     rsp, 20h
0x180004e00  pop     rbx
0x180004e01  retn
```
