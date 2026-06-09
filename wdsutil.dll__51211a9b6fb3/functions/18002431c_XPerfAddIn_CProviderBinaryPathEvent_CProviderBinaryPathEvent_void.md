# XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(void)

- ea: `0x18002431c`
- end: `0x18002437b`
- name: `??1CProviderBinaryPathEvent@XPerfAddIn@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180033585`

## callees

- `0x18002431c`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180024351`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024351`

## pseudocode

```c
void __fastcall XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this)
{
  volatile signed __int32 *v2; // rdx

  v2 = (volatile signed __int32 *)(*((_QWORD *)this + 3) - 24LL);
  if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  if ( *(_QWORD *)this )
  {
    operator delete(*(void **)this);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18002431c  push    rbx
0x18002431e  sub     rsp, 20h
0x180024322  mov     rdx, [rcx+18h]
0x180024326  mov     rbx, rcx
0x180024329  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002432d  or      eax, 0FFFFFFFFh
0x180024330  lock xadd [rdx+10h], eax
0x180024335  sub     eax, 1
0x180024338  jg      short loc_180024349
0x18002433a  mov     rcx, [rdx]
0x18002433d  mov     rax, [rcx]
0x180024340  mov     rax, [rax+8]
0x180024344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024349  mov     rcx, [rbx]
0x18002434c  test    rcx, rcx
0x18002434f  jz      short loc_180024374
0x180024351  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024358  nop     dword ptr [rax+rax+00h]
0x18002435d  mov     qword ptr [rbx], 0
0x180024364  mov     qword ptr [rbx+8], 0
0x18002436c  mov     qword ptr [rbx+10h], 0
0x180024374  add     rsp, 20h
0x180024378  pop     rbx
0x180024379  retn
```
