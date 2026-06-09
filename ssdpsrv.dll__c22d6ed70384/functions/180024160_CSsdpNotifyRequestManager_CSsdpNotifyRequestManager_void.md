# CSsdpNotifyRequestManager::~CSsdpNotifyRequestManager(void)

- ea: `0x180024160`
- end: `0x180024226`
- name: `??1CSsdpNotifyRequestManager@@QEAA@XZ`
- size: `198`
- prototype: `void __fastcall(CSsdpNotifyRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180035670`

## callees

- `0x1800092f4`
- `0x18000a6b8`
- `0x180024160`
- `0x18002de68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002418c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002418c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800241fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002421f`

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
    CUList<void *>::Node::`scalar deleting destructor'(v6);
  *((_QWORD *)this + 5) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180024160  push    rbx
0x180024162  sub     rsp, 20h
0x180024166  mov     rbx, rcx
0x180024169  mov     rcx, [rcx+0E8h]; Block
0x180024170  test    rcx, rcx
0x180024173  jz      short loc_18002417A
0x180024175  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x18002417a  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180024181  mov     qword ptr [rbx+0E8h], 0
0x18002418c  call    cs:__imp_DeleteCriticalSection
0x180024192  mov     rcx, [rbx+0B8h]; void *
0x180024199  test    rcx, rcx
0x18002419c  jz      short loc_1800241A3
0x18002419e  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x1800241a3  lea     rcx, [rbx+90h]; lpCriticalSection
0x1800241aa  mov     qword ptr [rbx+0B8h], 0
0x1800241b5  call    cs:__imp_DeleteCriticalSection
0x1800241bb  mov     rcx, [rbx+88h]; void *
0x1800241c2  test    rcx, rcx
0x1800241c5  jz      short loc_1800241CC
0x1800241c7  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x1800241cc  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800241d0  mov     qword ptr [rbx+88h], 0
0x1800241db  call    cs:__imp_DeleteCriticalSection
0x1800241e1  mov     rcx, [rbx+58h]; void *
0x1800241e5  test    rcx, rcx
0x1800241e8  jz      short loc_1800241EF
0x1800241ea  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x1800241ef  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800241f3  mov     qword ptr [rbx+58h], 0
0x1800241fb  call    cs:__imp_DeleteCriticalSection
0x180024201  mov     rcx, [rbx+28h]; void *
0x180024205  test    rcx, rcx
0x180024208  jz      short loc_18002420F
0x18002420a  call    ??_GNode@?$CUList@PEAX@@QEAAPEAXI@Z; CUList<void *>::Node::`scalar deleting destructor'(uint)
0x18002420f  mov     rcx, rbx
0x180024212  mov     qword ptr [rbx+28h], 0
0x18002421a  add     rsp, 20h
0x18002421e  pop     rbx
0x18002421f  jmp     cs:__imp_DeleteCriticalSection
```
