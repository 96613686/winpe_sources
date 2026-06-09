# CSusFileRequestList::~CSusFileRequestList(void)

- ea: `0x18003a76c`
- end: `0x18003a7c0`
- name: `??1CSusFileRequestList@@UEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CSusFileRequestList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a6a8`

## callees

- `0x18003a8b8`
- `0x18003b684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a7a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a7a9`

## pseudocode

```c
void __fastcall CSusFileRequestList::~CSusFileRequestList(CSusFileRequestList *this)
{
  *(_QWORD *)this = &CSusFileRequestList::`vftable'{for `ISusFileRequestList'};
  *((_QWORD *)this + 1) = &CSusFileRequestList::`vftable'{for `CSusBaseAllocTag<959473781>'};
  CSusFileRequestList::Cleanup(this, 0);
  CSusArrayList<tagSusFileRequest *,CFileListOps>::~CSusArrayList<tagSusFileRequest *,CFileListOps>((char *)this + 64);
  *((_QWORD *)this + 2) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 1) = &CSusBaseAllocTag<959473781>::`vftable';
}

```

## disassembly

```asm
0x18003a76c  push    rbx
0x18003a76e  sub     rsp, 20h
0x18003a772  mov     rbx, rcx
0x18003a775  lea     rax, ??_7CSusFileRequestList@@6BISusFileRequestList@@@; const CSusFileRequestList::`vftable'{for `ISusFileRequestList'}
0x18003a77c  mov     [rcx], rax
0x18003a77f  lea     rax, ??_7CSusFileRequestList@@6B?$CSusBaseAllocTag@$0DJDAGIHF@@@@; const CSusFileRequestList::`vftable'{for `CSusBaseAllocTag<959473781>'}
0x18003a786  mov     [rcx+8], rax
0x18003a78a  xor     edx, edx; int
0x18003a78c  call    ?Cleanup@CSusFileRequestList@@AEAAXH@Z; CSusFileRequestList::Cleanup(int)
0x18003a791  lea     rcx, [rbx+40h]
0x18003a795  call    ??1?$CSusArrayList@PEAUtagSusFileRequest@@VCFileListOps@@@@UEAA@XZ; CSusArrayList<tagSusFileRequest *,CFileListOps>::~CSusArrayList<tagSusFileRequest *,CFileListOps>(void)
0x18003a79a  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18003a7a1  mov     [rbx+10h], rax
0x18003a7a5  lea     rcx, [rbx+18h]; lpCriticalSection
0x18003a7a9  call    cs:__imp_DeleteCriticalSection
0x18003a7af  lea     rax, ??_7?$CSusBaseAllocTag@$0DJDAGIHF@@@6B@; const CSusBaseAllocTag<959473781>::`vftable'
0x18003a7b6  mov     [rbx+8], rax
0x18003a7ba  add     rsp, 20h
0x18003a7be  pop     rbx
0x18003a7bf  retn
```
