# CWcnEventManager::~CWcnEventManager(void)

- ea: `0x180039b8c`
- end: `0x180039c2b`
- name: `??1CWcnEventManager@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CWcnEventManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002e04`

## callees

- `0x18000fd10`
- `0x180039b8c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180039bd7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039be8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039bf1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039c14`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039bd7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039be8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039bf1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039c14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039ba2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039ba2`

## pseudocode

```c
void __fastcall CWcnEventManager::~CWcnEventManager(CWcnEventManager *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (_QWORD *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    v3 = *(_QWORD **)*v2;
    *(_QWORD *)*v2 = *v2;
    *(_QWORD *)(*v2 + 8LL) = *v2;
    v2[1] = 0;
    v4 = (_QWORD *)*v2;
    if ( v3 != (_QWORD *)*v2 )
    {
      do
      {
        v5 = (_QWORD *)*v3;
        operator delete(v3);
        v3 = v5;
        v4 = (_QWORD *)*v2;
      }
      while ( v5 != (_QWORD *)*v2 );
    }
    operator delete(v4);
    operator delete(v2);
  }
  std::_Tree<std::_Tmap_traits<unsigned __int64,CWcnEventSink *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CWcnEventSink *>>,1>>::erase(
    (char *)this + 16,
    &v6,
    **((_QWORD **)this + 2),
    *((_QWORD *)this + 2));
  operator delete(*((void **)this + 2));
}

```

## disassembly

```asm
0x180039b8c  mov     [rsp+arg_8], rbx
0x180039b91  mov     [rsp+arg_10], rsi
0x180039b96  push    rdi
0x180039b97  sub     rsp, 20h
0x180039b9b  mov     rsi, rcx
0x180039b9e  add     rcx, 30h ; '0'; lpCriticalSection
0x180039ba2  call    cs:__imp_DeleteCriticalSection
0x180039ba8  mov     rdi, [rsi+20h]
0x180039bac  test    rdi, rdi
0x180039baf  jz      short loc_180039BF7
0x180039bb1  mov     rax, [rdi]
0x180039bb4  mov     rdx, [rax]
0x180039bb7  mov     [rax], rax
0x180039bba  mov     rax, [rdi]
0x180039bbd  mov     [rax+8], rax
0x180039bc1  mov     qword ptr [rdi+8], 0
0x180039bc9  mov     rcx, [rdi]
0x180039bcc  cmp     rdx, rcx
0x180039bcf  jz      short loc_180039BE8
0x180039bd1  mov     rbx, [rdx]
0x180039bd4  mov     rcx, rdx
0x180039bd7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039bdd  mov     rdx, rbx
0x180039be0  mov     rcx, [rdi]
0x180039be3  cmp     rbx, rcx
0x180039be6  jnz     short loc_180039BD1
0x180039be8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039bee  mov     rcx, rdi
0x180039bf1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039bf7  lea     rbx, [rsi+10h]
0x180039bfb  mov     r8, [rbx]
0x180039bfe  mov     r9, r8
0x180039c01  mov     r8, [r8]
0x180039c04  lea     rdx, [rsp+28h+arg_0]
0x180039c09  mov     rcx, rbx
0x180039c0c  call    ?erase@?$_Tree@V?$_Tmap_traits@_KPEAVCWcnEventSink@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,CWcnEventSink *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CWcnEventSink *>>,1>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>>)
0x180039c11  mov     rcx, [rbx]
0x180039c14  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039c1a  nop
0x180039c1b  mov     rbx, [rsp+28h+arg_8]
0x180039c20  mov     rsi, [rsp+28h+arg_10]
0x180039c25  add     rsp, 20h
0x180039c29  pop     rdi
0x180039c2a  retn
```
