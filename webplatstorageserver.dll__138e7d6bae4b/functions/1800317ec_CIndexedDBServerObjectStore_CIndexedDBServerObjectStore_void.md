# CIndexedDBServerObjectStore::~CIndexedDBServerObjectStore(void)

- ea: `0x1800317ec`
- end: `0x18003187f`
- name: `??1CIndexedDBServerObjectStore@@EEAA@XZ`
- size: `147`
- prototype: `void __fastcall(CIndexedDBServerObjectStore *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800317b0`

## callees

- `0x1800317ec`
- `0x180031890`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003182a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031840`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031872`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003182a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031840`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031872`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CIndexedDBServerObjectStore::~CIndexedDBServerObjectStore(CIndexedDBServerObjectStore *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIndexedDBServerObjectStore::`vftable'{for `CRpcObject'};
  *((_QWORD *)this + 8) = &CIndexedDBServerObjectStore::`vftable'{for `IIndexedDBServerCursorOwner'};
  *((_QWORD *)this + 9) = &CIndexedDBServerObjectStore::`vftable'{for `IIndexedDBServerIndexOwner'};
  CIndexedDBServerObjectStore::Close(this);
  if ( *((_DWORD *)this + 58) )
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  if ( *((_DWORD *)this + 40) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  *(_QWORD *)this = &CRpcObject::`vftable';
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x1800317ec  push    rbx
0x1800317ee  sub     rsp, 20h
0x1800317f2  mov     rbx, rcx
0x1800317f5  lea     rax, ??_7CIndexedDBServerObjectStore@@6BCRpcObject@@@; const CIndexedDBServerObjectStore::`vftable'{for `CRpcObject'}
0x1800317fc  mov     [rcx], rax
0x1800317ff  lea     rax, ??_7CIndexedDBServerObjectStore@@6BIIndexedDBServerCursorOwner@@@; const CIndexedDBServerObjectStore::`vftable'{for `IIndexedDBServerCursorOwner'}
0x180031806  mov     [rcx+40h], rax
0x18003180a  lea     rax, ??_7CIndexedDBServerObjectStore@@6BIIndexedDBServerIndexOwner@@@; const CIndexedDBServerObjectStore::`vftable'{for `IIndexedDBServerIndexOwner'}
0x180031811  mov     [rcx+48h], rax
0x180031815  call    ?Close@CIndexedDBServerObjectStore@@QEAAJXZ; CIndexedDBServerObjectStore::Close(void)
0x18003181a  cmp     dword ptr [rbx+0E8h], 0
0x180031821  jz      short loc_180031830
0x180031823  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x18003182a  call    cs:__imp_DeleteCriticalSection
0x180031830  cmp     dword ptr [rbx+0A0h], 0
0x180031837  jz      short loc_180031847
0x180031839  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180031840  call    cs:__imp_DeleteCriticalSection
0x180031846  nop
0x180031847  lea     rax, ??_7CRpcObject@@6B@; const CRpcObject::`vftable'
0x18003184e  mov     [rbx], rax
0x180031851  mov     rcx, [rbx+8]
0x180031855  test    rcx, rcx
0x180031858  jz      short loc_18003186E
0x18003185a  mov     rax, [rcx]
0x18003185d  mov     rax, [rax+8]
0x180031861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031866  mov     qword ptr [rbx+8], 0
0x18003186e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180031872  call    cs:__imp_DeleteCriticalSection
0x180031878  nop
0x180031879  add     rsp, 20h
0x18003187d  pop     rbx
0x18003187e  retn
```
