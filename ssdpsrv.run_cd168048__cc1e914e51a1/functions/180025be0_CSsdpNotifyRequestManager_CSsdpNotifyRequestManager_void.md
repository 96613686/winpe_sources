# CSsdpNotifyRequestManager::~CSsdpNotifyRequestManager(void)

- ea: `0x180025be0`
- end: `0x180025cc3`
- name: `??1CSsdpNotifyRequestManager@@QEAA@XZ`
- size: `227`
- prototype: `void __fastcall(CSsdpNotifyRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800381c0`

## callees

- `0x18000a934`
- `0x18000ae2c`
- `0x180025be0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025cb7`

## pseudocode

```c
void __fastcall CSsdpNotifyRequestManager::~CSsdpNotifyRequestManager(CSsdpNotifyRequestManager *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = (void *)*((_QWORD *)this + 29);
  if ( v2 )
    CUList<__int64>::Node::`scalar deleting destructor'(v2);
  *((_QWORD *)this + 29) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v3 = (void *)*((_QWORD *)this + 23);
  if ( v3 )
    CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(v3);
  *((_QWORD *)this + 23) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 )
    CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(v4);
  *((_QWORD *)this + 17) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
    CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(v5);
  *((_QWORD *)this + 11) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 )
    CUList<__int64>::Node::`scalar deleting destructor'(v6);
  *((_QWORD *)this + 5) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180025be0  push    rbx
0x180025be2  sub     rsp, 20h
0x180025be6  mov     rbx, rcx
0x180025be9  mov     rcx, [rcx+0E8h]; void *
0x180025bf0  test    rcx, rcx
0x180025bf3  jz      short loc_180025BFA
0x180025bf5  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x180025bfa  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180025c01  mov     qword ptr [rbx+0E8h], 0
0x180025c0c  call    cs:__imp_DeleteCriticalSection
0x180025c13  nop     dword ptr [rax+rax+00h]
0x180025c18  mov     rcx, [rbx+0B8h]; void *
0x180025c1f  test    rcx, rcx
0x180025c22  jz      short loc_180025C29
0x180025c24  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x180025c29  lea     rcx, [rbx+90h]; lpCriticalSection
0x180025c30  mov     qword ptr [rbx+0B8h], 0
0x180025c3b  call    cs:__imp_DeleteCriticalSection
0x180025c42  nop     dword ptr [rax+rax+00h]
0x180025c47  mov     rcx, [rbx+88h]; void *
0x180025c4e  test    rcx, rcx
0x180025c51  jz      short loc_180025C58
0x180025c53  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x180025c58  lea     rcx, [rbx+60h]; lpCriticalSection
0x180025c5c  mov     qword ptr [rbx+88h], 0
0x180025c67  call    cs:__imp_DeleteCriticalSection
0x180025c6e  nop     dword ptr [rax+rax+00h]
0x180025c73  mov     rcx, [rbx+58h]; void *
0x180025c77  test    rcx, rcx
0x180025c7a  jz      short loc_180025C81
0x180025c7c  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x180025c81  lea     rcx, [rbx+30h]; lpCriticalSection
0x180025c85  mov     qword ptr [rbx+58h], 0
0x180025c8d  call    cs:__imp_DeleteCriticalSection
0x180025c94  nop     dword ptr [rax+rax+00h]
0x180025c99  mov     rcx, [rbx+28h]; void *
0x180025c9d  test    rcx, rcx
0x180025ca0  jz      short loc_180025CA7
0x180025ca2  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x180025ca7  mov     rcx, rbx
0x180025caa  mov     qword ptr [rbx+28h], 0
0x180025cb2  add     rsp, 20h
0x180025cb6  pop     rbx
0x180025cb7  jmp     cs:__imp_DeleteCriticalSection
```
