# CUPnPInterfaceList::~CUPnPInterfaceList(void)

- ea: `0x180023fd4`
- end: `0x1800240c9`
- name: `??1CUPnPInterfaceList@@QEAA@XZ`
- size: `245`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180035610`

## callees

- `0x18000936c`
- `0x180023fd4`
- `0x180028000`
- `0x180032f2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800240a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800240af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800240a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800240af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800240c2`

## pseudocode

```c
void __fastcall CUPnPInterfaceList::~CUPnPInterfaceList(LPCRITICAL_SECTION lpCriticalSection)
{
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
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
0x180023fd4  mov     [rsp+arg_0], rbx
0x180023fd9  push    rdi
0x180023fda  sub     rsp, 20h
0x180023fde  mov     rbx, rcx
0x180023fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fe8  lea     rax, WPP_GLOBAL_Control
0x180023fef  cmp     rcx, rax
0x180023ff2  jz      short loc_180024012
0x180023ff4  test    dword ptr [rcx+1Ch], 200h
0x180023ffb  jz      short loc_180024012
0x180023ffd  mov     rcx, [rcx+10h]
0x180024001  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180024008  mov     edx, 0Ah
0x18002400d  call    WPP_SF_
0x180024012  xor     edi, edi
0x180024014  cmp     [rbx+0D0h], rdi
0x18002401b  jz      short loc_180024025
0x18002401d  mov     rcx, rbx; lpCriticalSection
0x180024020  call    ?HrShutdown@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrShutdown(void)
0x180024025  mov     rcx, [rbx+0B8h]; void *
0x18002402c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024031  mov     [rbx+0B8h], rdi
0x180024038  mov     [rbx+0C0h], rdi
0x18002403f  mov     rcx, [rbx+0A8h]; void *
0x180024046  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002404b  mov     [rbx+0A8h], rdi
0x180024052  mov     [rbx+0B0h], rdi
0x180024059  mov     rcx, [rbx+98h]; void *
0x180024060  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024065  mov     [rbx+98h], rdi
0x18002406c  mov     [rbx+0A0h], rdi
0x180024073  mov     rcx, [rbx+88h]; void *
0x18002407a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002407f  mov     [rbx+88h], rdi
0x180024086  mov     [rbx+90h], rdi
0x18002408d  mov     rcx, [rbx+78h]; void *
0x180024091  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024096  lea     rcx, [rbx+50h]; lpCriticalSection
0x18002409a  mov     [rbx+78h], rdi
0x18002409e  mov     [rbx+80h], rdi
0x1800240a5  call    cs:__imp_DeleteCriticalSection
0x1800240ab  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800240af  call    cs:__imp_DeleteCriticalSection
0x1800240b5  mov     rcx, rbx
0x1800240b8  mov     rbx, [rsp+28h+arg_0]
0x1800240bd  add     rsp, 20h
0x1800240c1  pop     rdi
0x1800240c2  jmp     cs:__imp_DeleteCriticalSection
```
