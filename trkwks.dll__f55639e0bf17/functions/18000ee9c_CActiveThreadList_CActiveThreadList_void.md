# CActiveThreadList::~CActiveThreadList(void)

- ea: `0x18000ee9c`
- end: `0x18000eed2`
- name: `??1CActiveThreadList@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CActiveThreadList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d864`

## callees

- `0x18000db28`
- `0x18000ee9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eecb`

## pseudocode

```c
void __fastcall CActiveThreadList::~CActiveThreadList(CActiveThreadList *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    operator delete(v2);
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000ee9c  push    rbx
0x18000ee9e  sub     rsp, 20h
0x18000eea2  mov     rbx, rcx
0x18000eea5  mov     rcx, [rcx+8]; Block
0x18000eea9  test    rcx, rcx
0x18000eeac  jz      short loc_18000EEB3
0x18000eeae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eeb3  lea     rcx, [rbx+10h]
0x18000eeb7  mov     qword ptr [rbx+8], 0
0x18000eebf  mov     qword ptr [rbx], 0
0x18000eec6  add     rsp, 20h
0x18000eeca  pop     rbx
0x18000eecb  jmp     cs:__imp_DeleteCriticalSection
```
