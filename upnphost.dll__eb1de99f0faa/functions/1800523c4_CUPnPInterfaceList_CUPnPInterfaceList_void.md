# CUPnPInterfaceList::~CUPnPInterfaceList(void)

- ea: `0x1800523c4`
- end: `0x1800524b9`
- name: `??1CUPnPInterfaceList@@QEAA@XZ`
- size: `245`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180054590`

## callees

- `0x180018738`
- `0x180039a84`
- `0x1800523c4`
- `0x1800527d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052495`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005249f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052495`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005249f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800524b2`

## pseudocode

```c
void __fastcall CUPnPInterfaceList::~CUPnPInterfaceList(LPCRITICAL_SECTION lpCriticalSection)
{
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids);
  if ( *(_QWORD *)&lpCriticalSection[5].LockCount )
    CUPnPInterfaceList::HrShutdown(lpCriticalSection);
  operator delete(lpCriticalSection[4].LockSemaphore);
  lpCriticalSection[4].LockSemaphore = 0;
  lpCriticalSection[4].SpinCount = 0;
  operator delete(*(void **)&lpCriticalSection[4].LockCount);
  *(_QWORD *)&lpCriticalSection[4].LockCount = 0;
  lpCriticalSection[4].OwningThread = 0;
  operator delete((void *)lpCriticalSection[3].SpinCount);
  lpCriticalSection[3].SpinCount = 0;
  lpCriticalSection[4].DebugInfo = 0;
  operator delete(lpCriticalSection[3].OwningThread);
  lpCriticalSection[3].OwningThread = 0;
  lpCriticalSection[3].LockSemaphore = 0;
  operator delete(lpCriticalSection[3].DebugInfo);
  lpCriticalSection[3].DebugInfo = 0;
  *(_QWORD *)&lpCriticalSection[3].LockCount = 0;
  DeleteCriticalSection(lpCriticalSection + 2);
  DeleteCriticalSection(lpCriticalSection + 1);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800523c4  mov     [rsp+arg_0], rbx
0x1800523c9  push    rdi
0x1800523ca  sub     rsp, 20h
0x1800523ce  mov     rbx, rcx
0x1800523d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523d8  lea     rax, WPP_GLOBAL_Control
0x1800523df  cmp     rcx, rax
0x1800523e2  jz      short loc_180052402
0x1800523e4  test    dword ptr [rcx+1Ch], 200h
0x1800523eb  jz      short loc_180052402
0x1800523ed  mov     rcx, [rcx+10h]
0x1800523f1  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x1800523f8  mov     edx, 0Ah
0x1800523fd  call    WPP_SF_
0x180052402  xor     edi, edi
0x180052404  cmp     [rbx+0D0h], rdi
0x18005240b  jz      short loc_180052415
0x18005240d  mov     rcx, rbx; lpCriticalSection
0x180052410  call    ?HrShutdown@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrShutdown(void)
0x180052415  mov     rcx, [rbx+0B8h]; void *
0x18005241c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052421  mov     [rbx+0B8h], rdi
0x180052428  mov     [rbx+0C0h], rdi
0x18005242f  mov     rcx, [rbx+0A8h]; void *
0x180052436  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005243b  mov     [rbx+0A8h], rdi
0x180052442  mov     [rbx+0B0h], rdi
0x180052449  mov     rcx, [rbx+98h]; void *
0x180052450  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052455  mov     [rbx+98h], rdi
0x18005245c  mov     [rbx+0A0h], rdi
0x180052463  mov     rcx, [rbx+88h]; void *
0x18005246a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005246f  mov     [rbx+88h], rdi
0x180052476  mov     [rbx+90h], rdi
0x18005247d  mov     rcx, [rbx+78h]; void *
0x180052481  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052486  lea     rcx, [rbx+50h]; lpCriticalSection
0x18005248a  mov     [rbx+78h], rdi
0x18005248e  mov     [rbx+80h], rdi
0x180052495  call    cs:__imp_DeleteCriticalSection
0x18005249b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18005249f  call    cs:__imp_DeleteCriticalSection
0x1800524a5  mov     rcx, rbx
0x1800524a8  mov     rbx, [rsp+28h+arg_0]
0x1800524ad  add     rsp, 20h
0x1800524b1  pop     rdi
0x1800524b2  jmp     cs:__imp_DeleteCriticalSection
```
