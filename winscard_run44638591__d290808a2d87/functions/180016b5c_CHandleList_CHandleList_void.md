# CHandleList::~CHandleList(void)

- ea: `0x180016b5c`
- end: `0x180016b8b`
- name: `??1CHandleList@@UEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CHandleList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016b20`

## callees

- `0x180016b5c`
- `0x180016b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016b7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016b7e`

## pseudocode

```c
void __fastcall CHandleList::~CHandleList(CHandleList *this)
{
  *(_QWORD *)this = &CHandleList::`vftable';
  if ( !*((_DWORD *)this + 18) )
  {
    CHandleList::Clear(this);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
}

```

## disassembly

```asm
0x180016b5c  push    rbx
0x180016b5e  sub     rsp, 20h
0x180016b62  mov     rbx, rcx
0x180016b65  lea     rax, ??_7CHandleList@@6B@; const CHandleList::`vftable'
0x180016b6c  mov     [rcx], rax
0x180016b6f  cmp     dword ptr [rcx+48h], 0
0x180016b73  jnz     short loc_180016B85
0x180016b75  call    ?Clear@CHandleList@@QEAAXXZ; CHandleList::Clear(void)
0x180016b7a  lea     rcx, [rbx+20h]; lpCriticalSection
0x180016b7e  call    cs:__imp_DeleteCriticalSection
0x180016b84  nop
0x180016b85  add     rsp, 20h
0x180016b89  pop     rbx
0x180016b8a  retn
```
