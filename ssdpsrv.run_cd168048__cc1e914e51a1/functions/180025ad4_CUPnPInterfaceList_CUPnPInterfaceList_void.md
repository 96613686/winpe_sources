# CUPnPInterfaceList::~CUPnPInterfaceList(void)

- ea: `0x180025ad4`
- end: `0x180025bda`
- name: `??1CUPnPInterfaceList@@QEAA@XZ`
- size: `262`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180038160`

## callees

- `0x18000a9ac`
- `0x180025ad4`
- `0x180029df0`
- `0x180035930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025ba5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025bb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025ba5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025bb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025bce`

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
0x180025ad4  mov     [rsp+arg_0], rbx
0x180025ad9  push    rdi
0x180025ada  sub     rsp, 20h
0x180025ade  mov     rbx, rcx
0x180025ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ae8  lea     rax, WPP_GLOBAL_Control
0x180025aef  cmp     rcx, rax
0x180025af2  jz      short loc_180025B12
0x180025af4  test    dword ptr [rcx+1Ch], 200h
0x180025afb  jz      short loc_180025B12
0x180025afd  mov     rcx, [rcx+10h]
0x180025b01  lea     r8, WPP_be91c1c7b6083381c2d2431ae6263e74_Traceguids
0x180025b08  mov     edx, 0Ah
0x180025b0d  call    WPP_SF_
0x180025b12  xor     edi, edi
0x180025b14  cmp     [rbx+0D0h], rdi
0x180025b1b  jz      short loc_180025B25
0x180025b1d  mov     rcx, rbx; lpCriticalSection
0x180025b20  call    ?HrShutdown@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrShutdown(void)
0x180025b25  mov     rcx, [rbx+0B8h]; void *
0x180025b2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b31  mov     [rbx+0B8h], rdi
0x180025b38  mov     [rbx+0C0h], rdi
0x180025b3f  mov     rcx, [rbx+0A8h]; void *
0x180025b46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b4b  mov     [rbx+0A8h], rdi
0x180025b52  mov     [rbx+0B0h], rdi
0x180025b59  mov     rcx, [rbx+98h]; void *
0x180025b60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b65  mov     [rbx+98h], rdi
0x180025b6c  mov     [rbx+0A0h], rdi
0x180025b73  mov     rcx, [rbx+88h]; void *
0x180025b7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b7f  mov     [rbx+88h], rdi
0x180025b86  mov     [rbx+90h], rdi
0x180025b8d  mov     rcx, [rbx+78h]; void *
0x180025b91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b96  lea     rcx, [rbx+50h]; lpCriticalSection
0x180025b9a  mov     [rbx+78h], rdi
0x180025b9e  mov     [rbx+80h], rdi
0x180025ba5  call    cs:__imp_DeleteCriticalSection
0x180025bac  nop     dword ptr [rax+rax+00h]
0x180025bb1  lea     rcx, [rbx+28h]; lpCriticalSection
0x180025bb5  call    cs:__imp_DeleteCriticalSection
0x180025bbc  nop     dword ptr [rax+rax+00h]
0x180025bc1  mov     rcx, rbx
0x180025bc4  mov     rbx, [rsp+28h+arg_0]
0x180025bc9  add     rsp, 20h
0x180025bcd  pop     rdi
0x180025bce  jmp     cs:__imp_DeleteCriticalSection
```
