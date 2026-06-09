# VdsNotificationClientList::~VdsNotificationClientList(void)

- ea: `0x14004f928`
- end: `0x14004f9e2`
- name: `??1VdsNotificationClientList@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(VdsNotificationClientList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140036f28`
- `0x140055166`

## callees

- `0x14004f928`
- `0x140052e46`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004f988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004f988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004f996`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004f996`
- `vdsutil!??1CRtlList@@QEAA@XZ` at `0x14004f9db`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14004f93f`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14004f93f`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14004f94d`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14004f94d`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14004f9c7`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14004f9c7`
- `vdsutil!?GetEntry@CRtlListIter@@QEAAPEAVCRtlEntry@@XZ` at `0x14004f9a1`
- `vdsutil!?GetEntry@CRtlListIter@@QEAAPEAVCRtlEntry@@XZ` at `0x14004f9a1`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14004f97a`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14004f97a`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14004f9bc`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14004f9bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VdsNotificationClientList::~VdsNotificationClientList(VdsNotificationClientList *this)
{
  void *EntryPointer; // rdi
  HANDLE ProcessHeap; // rax
  struct CRtlEntry *Entry; // rax
  _BYTE Buf1[16]; // [rsp+20h] [rbp-38h] BYREF
  __int128 Buf2; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v7[24]; // [rsp+40h] [rbp-18h] BYREF

  CRtlList::Begin(this, Buf1);
  while ( 1 )
  {
    Buf2 = *(_OWORD *)CRtlList::End(this, v7);
    if ( !memcmp_0(Buf1, &Buf2, 0x10u) )
      break;
    EntryPointer = CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1);
    if ( EntryPointer )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, EntryPointer);
      Entry = CRtlListIter::GetEntry((CRtlListIter *)Buf1);
      *((_QWORD *)Entry + 1) = 0;
      *((_QWORD *)Entry + 2) = 0;
    }
    CRtlListIter::Next((CRtlListIter *)Buf1);
  }
  CRtlList::RemoveAll(this);
  CRtlList::~CRtlList(this);
}

```

## disassembly

```asm
0x14004f928  mov     [rsp+arg_8], rbx
0x14004f92d  mov     [rsp+arg_0], rcx
0x14004f932  push    rdi
0x14004f933  sub     rsp, 50h
0x14004f937  mov     rbx, rcx
0x14004f93a  lea     rdx, [rsp+58h+Buf1]
0x14004f93f  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14004f945  lea     rdx, [rsp+58h+var_18]
0x14004f94a  mov     rcx, rbx
0x14004f94d  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14004f953  movups  xmm0, xmmword ptr [rax]
0x14004f956  movdqu  [rsp+58h+Buf2], xmm0
0x14004f95c  mov     r8d, 10h; Size
0x14004f962  lea     rdx, [rsp+58h+Buf2]; Buf2
0x14004f967  lea     rcx, [rsp+58h+Buf1]; Buf1
0x14004f96c  call    memcmp_0
0x14004f971  test    eax, eax
0x14004f973  jz      short loc_14004F9C4
0x14004f975  lea     rcx, [rsp+58h+Buf1]
0x14004f97a  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14004f980  mov     rdi, rax
0x14004f983  test    rax, rax
0x14004f986  jz      short loc_14004F9B7
0x14004f988  call    cs:__imp_GetProcessHeap
0x14004f98e  mov     rcx, rax; hHeap
0x14004f991  mov     r8, rdi; lpMem
0x14004f994  xor     edx, edx; dwFlags
0x14004f996  call    cs:__imp_HeapFree
0x14004f99c  lea     rcx, [rsp+58h+Buf1]
0x14004f9a1  call    cs:__imp_?GetEntry@CRtlListIter@@QEAAPEAVCRtlEntry@@XZ; CRtlListIter::GetEntry(void)
0x14004f9a7  mov     qword ptr [rax+8], 0
0x14004f9af  mov     qword ptr [rax+10h], 0
0x14004f9b7  lea     rcx, [rsp+58h+Buf1]
0x14004f9bc  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14004f9c2  jmp     short loc_14004F945
0x14004f9c4  mov     rcx, rbx
0x14004f9c7  call    cs:__imp_?RemoveAll@CRtlList@@QEAAXXZ; CRtlList::RemoveAll(void)
0x14004f9cd  nop
0x14004f9ce  mov     rcx, rbx
0x14004f9d1  mov     rbx, [rsp+58h+arg_8]
0x14004f9d6  add     rsp, 50h
0x14004f9da  pop     rdi
0x14004f9db  jmp     cs:__imp_??1CRtlList@@QEAA@XZ; CRtlList::~CRtlList(void)
```
