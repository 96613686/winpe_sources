# CWindowsLiveIdentity::~CWindowsLiveIdentity(void)

- ea: `0x180011268`
- end: `0x1800112b2`
- name: `??1CWindowsLiveIdentity@@UEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CWindowsLiveIdentity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cc68`
- `0x18001cf00`

## callees

- `0x180011268`
- `0x18001a164`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011278`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800112a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011278`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800112a5`

## pseudocode

```c
void __fastcall CWindowsLiveIdentity::~CWindowsLiveIdentity(CWindowsLiveIdentity *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  `eh vector destructor iterator'(
    (char *)this + 64,
    8u,
    9u,
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180011268  push    rbx
0x18001126a  sub     rsp, 20h
0x18001126e  mov     rbx, rcx
0x180011271  add     rcx, 88h; lpCriticalSection
0x180011278  call    cs:__imp_DeleteCriticalSection
0x18001127e  lea     rcx, [rbx+40h]; void *
0x180011282  lea     r9, ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; void (*)(void *)
0x180011289  mov     edx, 8; unsigned __int64
0x18001128e  lea     r8d, [rdx+1]; unsigned __int64
0x180011292  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011297  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001129b  cmp     byte ptr [rcx+28h], 0
0x18001129f  jz      short loc_1800112AC
0x1800112a1  mov     byte ptr [rcx+28h], 0
0x1800112a5  call    cs:__imp_DeleteCriticalSection
0x1800112ab  nop
0x1800112ac  add     rsp, 20h
0x1800112b0  pop     rbx
0x1800112b1  retn
```
