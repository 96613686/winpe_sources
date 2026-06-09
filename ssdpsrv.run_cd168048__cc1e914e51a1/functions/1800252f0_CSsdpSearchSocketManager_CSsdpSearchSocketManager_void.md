# CSsdpSearchSocketManager::~CSsdpSearchSocketManager(void)

- ea: `0x1800252f0`
- end: `0x180025345`
- name: `??1CSsdpSearchSocketManager@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CSsdpSearchSocketManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800252a8`

## callees

- `0x18000a9ac`
- `0x18002534c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025339`

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
0x1800252f0  push    rbx
0x1800252f2  sub     rsp, 20h
0x1800252f6  mov     rbx, rcx
0x1800252f9  call    ?Shutdown@CSsdpSearchSocketManager@@QEAAXXZ; CSsdpSearchSocketManager::Shutdown(void)
0x1800252fe  mov     rcx, [rbx+40h]; void *
0x180025302  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025307  mov     qword ptr [rbx+40h], 0
0x18002530f  mov     qword ptr [rbx+48h], 0
0x180025317  mov     rcx, [rbx+30h]; void *
0x18002531b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025320  lea     rcx, [rbx+8]
0x180025324  mov     qword ptr [rbx+30h], 0
0x18002532c  mov     qword ptr [rbx+38h], 0
0x180025334  add     rsp, 20h
0x180025338  pop     rbx
0x180025339  jmp     cs:__imp_DeleteCriticalSection
```
