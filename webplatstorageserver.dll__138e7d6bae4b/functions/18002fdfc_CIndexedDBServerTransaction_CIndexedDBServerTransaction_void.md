# CIndexedDBServerTransaction::~CIndexedDBServerTransaction(void)

- ea: `0x18002fdfc`
- end: `0x18002fe73`
- name: `??1CIndexedDBServerTransaction@@EEAA@XZ`
- size: `119`
- prototype: `void __fastcall(CIndexedDBServerTransaction *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800247ac`
- `0x18002fd20`

## callees

- `0x18000e1c0`
- `0x18002fdb4`
- `0x18002fdfc`
- `0x180031080`
- `0x1800810a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe52`

## pseudocode

```c
void __fastcall CIndexedDBServerTransaction::~CIndexedDBServerTransaction(CIndexedDBServerTransaction *this)
{
  void *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &CIndexedDBServerTransaction::`vftable';
  CIndexedDBServerTransaction::Close(this);
  v2 = (void *)*((_QWORD *)this + 21);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 21) = 0;
  }
  if ( *((_DWORD *)this + 64) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 9);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  CRpcObject::~CRpcObject(this);
}

```

## disassembly

```asm
0x18002fdfc  push    rbx
0x18002fdfe  sub     rsp, 20h
0x18002fe02  mov     rbx, rcx
0x18002fe05  lea     rax, ??_7CIndexedDBServerTransaction@@6B@; const CIndexedDBServerTransaction::`vftable'
0x18002fe0c  mov     [rcx], rax
0x18002fe0f  call    ?Close@CIndexedDBServerTransaction@@AEAAXXZ; CIndexedDBServerTransaction::Close(void)
0x18002fe14  mov     rcx, [rbx+0A8h]; Block
0x18002fe1b  test    rcx, rcx
0x18002fe1e  jz      short loc_18002FE35
0x18002fe20  mov     edx, 28h ; '('
0x18002fe25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fe2a  mov     qword ptr [rbx+0A8h], 0
0x18002fe35  cmp     dword ptr [rbx+100h], 0
0x18002fe3c  jz      short loc_18002FE4B
0x18002fe3e  lea     rcx, [rbx+108h]; lpCriticalSection
0x18002fe45  call    cs:__imp_DeleteCriticalSection
0x18002fe4b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18002fe52  call    cs:__imp_DeleteCriticalSection
0x18002fe58  mov     rcx, [rbx+48h]; this
0x18002fe5c  test    rcx, rcx
0x18002fe5f  jz      short loc_18002FE66
0x18002fe61  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fe66  mov     rcx, rbx; this
0x18002fe69  add     rsp, 20h
0x18002fe6d  pop     rbx
0x18002fe6e  jmp     ??1CRpcObject@@UEAA@XZ; CRpcObject::~CRpcObject(void)
```
