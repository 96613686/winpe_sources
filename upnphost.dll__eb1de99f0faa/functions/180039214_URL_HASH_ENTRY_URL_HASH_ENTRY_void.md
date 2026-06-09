# URL_HASH_ENTRY::~URL_HASH_ENTRY(void)

- ea: `0x180039214`
- end: `0x180039292`
- name: `??1URL_HASH_ENTRY@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(URL_HASH_ENTRY *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x180039214`
- `0x1800454d0`
- `0x180051b8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039269`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039286`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039269`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039286`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003925b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003925b`

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
0x180039214  push    rbx
0x180039216  sub     rsp, 20h
0x18003921a  mov     rbx, rcx
0x18003921d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039224  lea     rax, WPP_GLOBAL_Control
0x18003922b  cmp     rcx, rax
0x18003922e  jz      short loc_180039251
0x180039230  test    dword ptr [rcx+1Ch], 100h
0x180039237  jz      short loc_180039251
0x180039239  mov     rcx, [rcx+10h]
0x18003923d  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x180039244  mov     edx, 0Bh
0x180039249  mov     r9, rbx
0x18003924c  call    WPP_SF_q
0x180039251  cmp     dword ptr [rbx+58h], 0
0x180039255  jz      short loc_180039261
0x180039257  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003925b  call    cs:__imp_DeleteCriticalSection
0x180039261  mov     rcx, [rbx]; Block
0x180039264  test    rcx, rcx
0x180039267  jz      short loc_18003926F
0x180039269  call    cs:__imp_free
0x18003926f  mov     rcx, [rbx+18h]; this
0x180039273  test    rcx, rcx
0x180039276  jz      short loc_18003927D
0x180039278  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x18003927d  mov     rcx, [rbx+60h]; Block
0x180039281  test    rcx, rcx
0x180039284  jz      short loc_18003928C
0x180039286  call    cs:__imp_free
0x18003928c  add     rsp, 20h
0x180039290  pop     rbx
0x180039291  retn
```
