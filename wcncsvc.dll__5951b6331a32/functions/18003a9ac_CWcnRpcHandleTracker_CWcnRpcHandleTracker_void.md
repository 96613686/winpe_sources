# CWcnRpcHandleTracker::~CWcnRpcHandleTracker(void)

- ea: `0x18003a9ac`
- end: `0x18003aa00`
- name: `??1CWcnRpcHandleTracker@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CWcnRpcHandleTracker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002e04`

## callees

- `0x18000fd10`
- `0x18003a9ac`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003a9db`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a9e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a9db`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a9e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a9f9`

## pseudocode

```c
void __fastcall CWcnRpcHandleTracker::~CWcnRpcHandleTracker(CWcnRpcHandleTracker *this)
{
  void **v2; // rbx
  char v3; // [rsp+30h] [rbp+8h] BYREF

  v2 = (void **)*((_QWORD *)this + 7);
  if ( v2 )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,CWcnEventSink *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CWcnEventSink *>>,1>>::erase(
      *((_QWORD *)this + 7),
      &v3,
      *(_QWORD *)*v2,
      *v2);
    operator delete(*v2);
    operator delete(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18003a9ac  mov     [rsp+arg_8], rbx
0x18003a9b1  push    rdi
0x18003a9b2  sub     rsp, 20h
0x18003a9b6  mov     rdi, rcx
0x18003a9b9  mov     rbx, [rcx+38h]
0x18003a9bd  test    rbx, rbx
0x18003a9c0  jz      short loc_18003A9EB
0x18003a9c2  mov     r8, [rbx]
0x18003a9c5  mov     r9, r8
0x18003a9c8  mov     r8, [r8]
0x18003a9cb  lea     rdx, [rsp+28h+arg_0]
0x18003a9d0  mov     rcx, rbx
0x18003a9d3  call    ?erase@?$_Tree@V?$_Tmap_traits@_KPEAVCWcnEventSink@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,CWcnEventSink *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CWcnEventSink *>>,1>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>>)
0x18003a9d8  mov     rcx, [rbx]
0x18003a9db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a9e1  nop
0x18003a9e2  mov     rcx, rbx
0x18003a9e5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a9eb  lea     rcx, [rdi+10h]
0x18003a9ef  mov     rbx, [rsp+28h+arg_8]
0x18003a9f4  add     rsp, 20h
0x18003a9f8  pop     rdi
0x18003a9f9  jmp     cs:__imp_DeleteCriticalSection
```
