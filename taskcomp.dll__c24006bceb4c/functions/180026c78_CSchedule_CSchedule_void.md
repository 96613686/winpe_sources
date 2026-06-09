# CSchedule::~CSchedule(void)

- ea: `0x180026c78`
- end: `0x180026cbe`
- name: `??1CSchedule@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180010628`

## callees

- `0x1800074c8`
- `0x180026c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026c8f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026c8f`

## pseudocode

```c
void __fastcall CSchedule::~CSchedule(CSchedule *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CSchedule::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    operator delete(v2);
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
    operator delete(v3);
  _InterlockedDecrement((volatile signed __int32 *)&CDll::s_cObjs);
}

```

## disassembly

```asm
0x180026c78  push    rbx
0x180026c7a  sub     rsp, 20h
0x180026c7e  lea     rax, ??_7CSchedule@@6B@; const CSchedule::`vftable'
0x180026c85  mov     rbx, rcx
0x180026c88  mov     [rcx], rax
0x180026c8b  add     rcx, 8; lpCriticalSection
0x180026c8f  call    cs:__imp_DeleteCriticalSection
0x180026c95  mov     rcx, [rbx+38h]; Block
0x180026c99  test    rcx, rcx
0x180026c9c  jz      short loc_180026CA3
0x180026c9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ca3  mov     rcx, [rbx+40h]; Block
0x180026ca7  test    rcx, rcx
0x180026caa  jz      short loc_180026CB1
0x180026cac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026cb1  lock dec cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x180026cb8  add     rsp, 20h
0x180026cbc  pop     rbx
0x180026cbd  retn
```
