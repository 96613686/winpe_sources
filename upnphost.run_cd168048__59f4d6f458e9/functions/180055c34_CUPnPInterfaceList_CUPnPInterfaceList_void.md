# CUPnPInterfaceList::~CUPnPInterfaceList(void)

- ea: `0x180055c34`
- end: `0x180055d3a`
- name: `??1CUPnPInterfaceList@@QEAA@XZ`
- size: `262`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180057f40`

## callees

- `0x18000c8e0`
- `0x18003c018`
- `0x180055c34`
- `0x1800560ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055d05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055d15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055d05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055d15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055d2e`

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
0x180055c34  mov     [rsp+arg_0], rbx
0x180055c39  push    rdi
0x180055c3a  sub     rsp, 20h
0x180055c3e  mov     rbx, rcx
0x180055c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c48  lea     rax, WPP_GLOBAL_Control
0x180055c4f  cmp     rcx, rax
0x180055c52  jz      short loc_180055C72
0x180055c54  test    dword ptr [rcx+1Ch], 200h
0x180055c5b  jz      short loc_180055C72
0x180055c5d  mov     rcx, [rcx+10h]
0x180055c61  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180055c68  mov     edx, 0Ah
0x180055c6d  call    WPP_SF_
0x180055c72  xor     edi, edi
0x180055c74  cmp     [rbx+0D0h], rdi
0x180055c7b  jz      short loc_180055C85
0x180055c7d  mov     rcx, rbx; lpCriticalSection
0x180055c80  call    ?HrShutdown@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrShutdown(void)
0x180055c85  mov     rcx, [rbx+0B8h]; void *
0x180055c8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055c91  mov     [rbx+0B8h], rdi
0x180055c98  mov     [rbx+0C0h], rdi
0x180055c9f  mov     rcx, [rbx+0A8h]; void *
0x180055ca6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055cab  mov     [rbx+0A8h], rdi
0x180055cb2  mov     [rbx+0B0h], rdi
0x180055cb9  mov     rcx, [rbx+98h]; void *
0x180055cc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055cc5  mov     [rbx+98h], rdi
0x180055ccc  mov     [rbx+0A0h], rdi
0x180055cd3  mov     rcx, [rbx+88h]; void *
0x180055cda  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055cdf  mov     [rbx+88h], rdi
0x180055ce6  mov     [rbx+90h], rdi
0x180055ced  mov     rcx, [rbx+78h]; void *
0x180055cf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055cf6  lea     rcx, [rbx+50h]; lpCriticalSection
0x180055cfa  mov     [rbx+78h], rdi
0x180055cfe  mov     [rbx+80h], rdi
0x180055d05  call    cs:__imp_DeleteCriticalSection
0x180055d0c  nop     dword ptr [rax+rax+00h]
0x180055d11  lea     rcx, [rbx+28h]; lpCriticalSection
0x180055d15  call    cs:__imp_DeleteCriticalSection
0x180055d1c  nop     dword ptr [rax+rax+00h]
0x180055d21  mov     rcx, rbx
0x180055d24  mov     rbx, [rsp+28h+arg_0]
0x180055d29  add     rsp, 20h
0x180055d2d  pop     rdi
0x180055d2e  jmp     cs:__imp_DeleteCriticalSection
```
