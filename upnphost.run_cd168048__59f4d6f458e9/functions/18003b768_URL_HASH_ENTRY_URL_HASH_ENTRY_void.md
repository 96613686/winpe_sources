# URL_HASH_ENTRY::~URL_HASH_ENTRY(void)

- ea: `0x18003b768`
- end: `0x18003b7f9`
- name: `??1URL_HASH_ENTRY@@QEAA@XZ`
- size: `145`
- prototype: `void __fastcall(URL_HASH_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023420`

## callees

- `0x18003b768`
- `0x1800480c0`
- `0x180055380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b7c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b7e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b7c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003b7e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b7af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b7af`

## pseudocode

```c
void __fastcall URL_HASH_ENTRY::~URL_HASH_ENTRY(URL_HASH_ENTRY *this, unsigned int a2)
{
  PtrsQueue *v3; // rcx
  void *v4; // rcx

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids, this);
  if ( *((_DWORD *)this + 22) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *(_QWORD *)this )
    free(*(void **)this);
  v3 = (PtrsQueue *)*((_QWORD *)this + 3);
  if ( v3 )
    PtrsQueue::`scalar deleting destructor'(v3, a2);
  v4 = (void *)*((_QWORD *)this + 12);
  if ( v4 )
    free(v4);
}

```

## disassembly

```asm
0x18003b768  push    rbx
0x18003b76a  sub     rsp, 20h
0x18003b76e  mov     rbx, rcx
0x18003b771  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b778  lea     rax, WPP_GLOBAL_Control
0x18003b77f  cmp     rcx, rax
0x18003b782  jz      short loc_18003B7A5
0x18003b784  test    dword ptr [rcx+1Ch], 100h
0x18003b78b  jz      short loc_18003B7A5
0x18003b78d  mov     rcx, [rcx+10h]
0x18003b791  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x18003b798  mov     edx, 0Bh
0x18003b79d  mov     r9, rbx
0x18003b7a0  call    WPP_SF_q
0x18003b7a5  cmp     dword ptr [rbx+58h], 0
0x18003b7a9  jz      short loc_18003B7BB
0x18003b7ab  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003b7af  call    cs:__imp_DeleteCriticalSection
0x18003b7b6  nop     dword ptr [rax+rax+00h]
0x18003b7bb  mov     rcx, [rbx]; Block
0x18003b7be  test    rcx, rcx
0x18003b7c1  jz      short loc_18003B7CF
0x18003b7c3  call    cs:__imp_free
0x18003b7ca  nop     dword ptr [rax+rax+00h]
0x18003b7cf  mov     rcx, [rbx+18h]; this
0x18003b7d3  test    rcx, rcx
0x18003b7d6  jz      short loc_18003B7DD
0x18003b7d8  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x18003b7dd  mov     rcx, [rbx+60h]; Block
0x18003b7e1  test    rcx, rcx
0x18003b7e4  jz      short loc_18003B7F2
0x18003b7e6  call    cs:__imp_free
0x18003b7ed  nop     dword ptr [rax+rax+00h]
0x18003b7f2  add     rsp, 20h
0x18003b7f6  pop     rbx
0x18003b7f7  retn
```
