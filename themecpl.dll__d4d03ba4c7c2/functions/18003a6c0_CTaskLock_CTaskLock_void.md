# CTaskLock::~CTaskLock(void)

- ea: `0x18003a6c0`
- end: `0x18003a73a`
- name: `??1CTaskLock@@MEAA@XZ`
- size: `122`
- prototype: `void __fastcall(CTaskLock *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18003aa70`
- `0x18003ab70`

## callees

- `0x18003a6c0`
- `0x18004f490`
- `0x180054f64`
- `0x180054fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a6d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a6e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a6d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a6e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTaskLock::~CTaskLock(CTaskLock *this)
{
  struct _DPA *v2; // rcx

  *(_QWORD *)this = &CTaskLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_QWORD *)this + 11) && !IsProcessShutdownInProgress() )
  {
    v2 = (struct _DPA *)*((_QWORD *)this + 11);
    if ( v2 )
    {
      DPA_DestroyCallback(v2, CDPA_Base<ITheme,CTContainer_PolicyRelease<ITheme>>::_StandardDestroyCB, 0);
      *((_QWORD *)this + 11) = 0;
      DPA_Destroy(0);
      *((_QWORD *)this + 11) = 0;
    }
  }
}

```

## disassembly

```asm
0x18003a6c0  push    rbx
0x18003a6c2  sub     rsp, 20h
0x18003a6c6  mov     rbx, rcx
0x18003a6c9  lea     rax, ??_7CTaskLock@@6B@; const CTaskLock::`vftable'
0x18003a6d0  mov     [rcx], rax
0x18003a6d3  add     rcx, 8; lpCriticalSection
0x18003a6d7  call    cs:__imp_DeleteCriticalSection
0x18003a6de  nop     dword ptr [rax+rax+00h]
0x18003a6e3  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003a6e7  call    cs:__imp_DeleteCriticalSection
0x18003a6ee  nop     dword ptr [rax+rax+00h]
0x18003a6f3  nop
0x18003a6f4  cmp     qword ptr [rbx+58h], 0
0x18003a6f9  jz      short loc_18003A733
0x18003a6fb  call    ?IsProcessShutdownInProgress@@YA_NXZ; IsProcessShutdownInProgress(void)
0x18003a700  test    al, al
0x18003a702  jnz     short loc_18003A733
0x18003a704  mov     rcx, [rbx+58h]; hdpa
0x18003a708  test    rcx, rcx
0x18003a70b  jz      short loc_18003A733
0x18003a70d  xor     r8d, r8d; pData
0x18003a710  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UITheme@@V?$CTContainer_PolicyRelease@UITheme@@@@@@CAHPEAUITheme@@PEAX@Z; pfnCB
0x18003a717  call    DPA_DestroyCallback
0x18003a71c  mov     qword ptr [rbx+58h], 0
0x18003a724  xor     ecx, ecx; hdpa
0x18003a726  call    DPA_Destroy
0x18003a72b  mov     qword ptr [rbx+58h], 0
0x18003a733  add     rsp, 20h
0x18003a737  pop     rbx
0x18003a738  retn
```
