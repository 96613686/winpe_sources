# CSchedule::~CSchedule(void)

- ea: `0x180028450`
- end: `0x18002849d`
- name: `??1CSchedule@@QEAA@XZ`
- size: `77`
- prototype: `void __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180011028`

## callees

- `0x180007988`
- `0x180028450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028467`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028467`

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
0x180028450  push    rbx
0x180028452  sub     rsp, 20h
0x180028456  lea     rax, ??_7CSchedule@@6B@; const CSchedule::`vftable'
0x18002845d  mov     rbx, rcx
0x180028460  mov     [rcx], rax
0x180028463  add     rcx, 8; lpCriticalSection
0x180028467  call    cs:__imp_DeleteCriticalSection
0x18002846e  nop     dword ptr [rax+rax+00h]
0x180028473  mov     rcx, [rbx+38h]; Block
0x180028477  test    rcx, rcx
0x18002847a  jz      short loc_180028481
0x18002847c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028481  mov     rcx, [rbx+40h]; Block
0x180028485  test    rcx, rcx
0x180028488  jz      short loc_18002848F
0x18002848a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002848f  lock dec cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x180028496  add     rsp, 20h
0x18002849a  pop     rbx
0x18002849b  retn
```
