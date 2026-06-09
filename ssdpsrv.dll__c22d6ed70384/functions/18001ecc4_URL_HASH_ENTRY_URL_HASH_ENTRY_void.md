# URL_HASH_ENTRY::~URL_HASH_ENTRY(void)

- ea: `0x18001ecc4`
- end: `0x18001ed42`
- name: `??1URL_HASH_ENTRY@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(URL_HASH_ENTRY *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ec98`

## callees

- `0x18001ecc4`
- `0x18002c8cc`
- `0x18003179c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ed19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ed36`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ed19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ed36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ed0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ed0b`

## pseudocode

```c
void __fastcall URL_HASH_ENTRY::~URL_HASH_ENTRY(URL_HASH_ENTRY *this, unsigned int a2)
{
  PtrsQueue *v3; // rcx
  void *v4; // rcx

  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
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
0x18001ecc4  push    rbx
0x18001ecc6  sub     rsp, 20h
0x18001ecca  mov     rbx, rcx
0x18001eccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecd4  lea     rax, WPP_GLOBAL_Control
0x18001ecdb  cmp     rcx, rax
0x18001ecde  jz      short loc_18001ED01
0x18001ece0  test    dword ptr [rcx+1Ch], 100h
0x18001ece7  jz      short loc_18001ED01
0x18001ece9  mov     rcx, [rcx+10h]
0x18001eced  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x18001ecf4  mov     edx, 0Bh
0x18001ecf9  mov     r9, rbx
0x18001ecfc  call    WPP_SF_q
0x18001ed01  cmp     dword ptr [rbx+58h], 0
0x18001ed05  jz      short loc_18001ED11
0x18001ed07  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001ed0b  call    cs:__imp_DeleteCriticalSection
0x18001ed11  mov     rcx, [rbx]; Block
0x18001ed14  test    rcx, rcx
0x18001ed17  jz      short loc_18001ED1F
0x18001ed19  call    cs:__imp_free
0x18001ed1f  mov     rcx, [rbx+18h]; this
0x18001ed23  test    rcx, rcx
0x18001ed26  jz      short loc_18001ED2D
0x18001ed28  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x18001ed2d  mov     rcx, [rbx+60h]; Block
0x18001ed31  test    rcx, rcx
0x18001ed34  jz      short loc_18001ED3C
0x18001ed36  call    cs:__imp_free
0x18001ed3c  add     rsp, 20h
0x18001ed40  pop     rbx
0x18001ed41  retn
```
