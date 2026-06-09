# URL_HASH_ENTRY::~URL_HASH_ENTRY(void)

- ea: `0x18002026c`
- end: `0x1800202fd`
- name: `??1URL_HASH_ENTRY@@QEAA@XZ`
- size: `145`
- prototype: `void __fastcall(URL_HASH_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020240`

## callees

- `0x18002026c`
- `0x18002e8ac`
- `0x180034060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800202c7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800202ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800202c7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800202ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800202b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800202b3`

## pseudocode

```c
void __fastcall URL_HASH_ENTRY::~URL_HASH_ENTRY(URL_HASH_ENTRY *this, unsigned int a2)
{
  PtrsQueue *v3; // rcx
  void *v4; // rcx

  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids);
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
0x18002026c  push    rbx
0x18002026e  sub     rsp, 20h
0x180020272  mov     rbx, rcx
0x180020275  mov     rcx, cs:WPP_GLOBAL_Control
0x18002027c  lea     rax, WPP_GLOBAL_Control
0x180020283  cmp     rcx, rax
0x180020286  jz      short loc_1800202A9
0x180020288  test    dword ptr [rcx+1Ch], 100h
0x18002028f  jz      short loc_1800202A9
0x180020291  mov     rcx, [rcx+10h]
0x180020295  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x18002029c  mov     edx, 0Bh
0x1800202a1  mov     r9, rbx
0x1800202a4  call    WPP_SF_q
0x1800202a9  cmp     dword ptr [rbx+58h], 0
0x1800202ad  jz      short loc_1800202BF
0x1800202af  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800202b3  call    cs:__imp_DeleteCriticalSection
0x1800202ba  nop     dword ptr [rax+rax+00h]
0x1800202bf  mov     rcx, [rbx]; Block
0x1800202c2  test    rcx, rcx
0x1800202c5  jz      short loc_1800202D3
0x1800202c7  call    cs:__imp_free
0x1800202ce  nop     dword ptr [rax+rax+00h]
0x1800202d3  mov     rcx, [rbx+18h]; this
0x1800202d7  test    rcx, rcx
0x1800202da  jz      short loc_1800202E1
0x1800202dc  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x1800202e1  mov     rcx, [rbx+60h]; Block
0x1800202e5  test    rcx, rcx
0x1800202e8  jz      short loc_1800202F6
0x1800202ea  call    cs:__imp_free
0x1800202f1  nop     dword ptr [rax+rax+00h]
0x1800202f6  add     rsp, 20h
0x1800202fa  pop     rbx
0x1800202fb  retn
```
