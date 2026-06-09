# CSsdpSearchSocketManager::~CSsdpSearchSocketManager(void)

- ea: `0x1800238dc`
- end: `0x18002392c`
- name: `??1CSsdpSearchSocketManager@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CSsdpSearchSocketManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002389c`

## callees

- `0x18000936c`
- `0x180023934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023925`

## pseudocode

```c
void __fastcall CSsdpSearchSocketManager::~CSsdpSearchSocketManager(CSsdpSearchSocketManager *this)
{
  CSsdpSearchSocketManager::Shutdown(this);
  operator delete(*((void **)this + 8));
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  operator delete(*((void **)this + 6));
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800238dc  push    rbx
0x1800238de  sub     rsp, 20h
0x1800238e2  mov     rbx, rcx
0x1800238e5  call    ?Shutdown@CSsdpSearchSocketManager@@QEAAXXZ; CSsdpSearchSocketManager::Shutdown(void)
0x1800238ea  mov     rcx, [rbx+40h]; void *
0x1800238ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800238f3  mov     qword ptr [rbx+40h], 0
0x1800238fb  mov     qword ptr [rbx+48h], 0
0x180023903  mov     rcx, [rbx+30h]; void *
0x180023907  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002390c  lea     rcx, [rbx+8]
0x180023910  mov     qword ptr [rbx+30h], 0
0x180023918  mov     qword ptr [rbx+38h], 0
0x180023920  add     rsp, 20h
0x180023924  pop     rbx
0x180023925  jmp     cs:__imp_DeleteCriticalSection
```
