# CApSrvDataState::~CApSrvDataState(void)

- ea: `0x18000cde0`
- end: `0x18000ce30`
- name: `??1CApSrvDataState@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CApSrvDataState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a83c`

## callees

- `0x18000a3c4`
- `0x18000a97c`
- `0x180025850`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000ce29`

## pseudocode

```c
void __fastcall CApSrvDataState::~CApSrvDataState(CApSrvDataState *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  unsigned int v2; // eax
  const char *v3; // rdx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &CApSrvDataState::`vftable';
  v2 = CContentCache::Shutdown((LPCRITICAL_SECTION)((char *)this + 32));
  ElValidateWin32(v2, v3, "base\\eco\\wds\\transport\\server\\mc\\apsrvdatastate.cpp", 0x6Fu);
  CContentCache::Shutdown(v1);
  CChildCount<CMulticastNotification>::~CChildCount<CMulticastNotification>(&v1[1].SpinCount);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x18000cde0  push    rbx
0x18000cde2  sub     rsp, 20h
0x18000cde6  lea     rax, ??_7CApSrvDataState@@6B@; const CApSrvDataState::`vftable'
0x18000cded  lea     rbx, [rcx+20h]
0x18000cdf1  mov     [rcx], rax
0x18000cdf4  mov     rcx, rbx; lpCriticalSection
0x18000cdf7  call    ?Shutdown@CContentCache@@QEAAKXZ; CContentCache::Shutdown(void)
0x18000cdfc  mov     ecx, eax; unsigned int
0x18000cdfe  lea     r8, aBaseEcoWdsTran_24; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000ce05  mov     r9d, 6Fh ; 'o'; unsigned int
0x18000ce0b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ce10  mov     rcx, rbx; lpCriticalSection
0x18000ce13  call    ?Shutdown@CContentCache@@QEAAKXZ; CContentCache::Shutdown(void)
0x18000ce18  lea     rcx, [rbx+48h]
0x18000ce1c  call    ??1?$CChildCount@VCMulticastNotification@@@@QEAA@XZ; CChildCount<CMulticastNotification>::~CChildCount<CMulticastNotification>(void)
0x18000ce21  mov     rcx, rbx
0x18000ce24  add     rsp, 20h
0x18000ce28  pop     rbx
0x18000ce29  jmp     cs:__imp_DeleteCriticalSection
```
