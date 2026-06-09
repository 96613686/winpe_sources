# PseudoEventTrap::~PseudoEventTrap(void)

- ea: `0x18006617c`
- end: `0x18006623e`
- name: `??1PseudoEventTrap@@QEAA@XZ`
- size: `194`
- prototype: `void __fastcall(PseudoEventTrap *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005c660`

## callees

- `0x180001ef0`
- `0x180054320`
- `0x180065b98`
- `0x180065bec`
- `0x180066108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800661ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800661ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066232`

## pseudocode

```c
void __fastcall PseudoEventTrap::~PseudoEventTrap(PseudoEventTrap *this)
{
  *(_QWORD *)this = &PseudoEventTrap::`vftable';
  tsched::ClearList<IdleJobList>((char *)this + 48);
  tsched::ClearList<IdleJobList>((char *)this + 64);
  std::list<std::vector<unsigned char> *,std::allocator<std::vector<unsigned char> *>>::clear((char *)this + 216);
  tsched::ClearMap<std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>>>((char *)this + 144);
  tsched::ClearMap<std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>>>((char *)this + 200);
  std::list<IdleJob *>::~list<IdleJob *>((char *)this + 216);
  std::_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>::~_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>((char *)this + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  std::_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>::~_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>((char *)this + 144);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  std::list<IdleJob *>::~list<IdleJob *>((char *)this + 64);
  std::list<IdleJob *>::~list<IdleJob *>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18006617c  push    rbx
0x18006617e  push    rbp
0x18006617f  push    rsi
0x180066180  push    rdi
0x180066181  push    r14
0x180066183  push    r15
0x180066185  sub     rsp, 28h
0x180066189  lea     rax, ??_7PseudoEventTrap@@6B@; const PseudoEventTrap::`vftable'
0x180066190  mov     r15, rcx
0x180066193  mov     [rcx], rax
0x180066196  add     rcx, 30h ; '0'
0x18006619a  call    ??$ClearList@VIdleJobList@@@tsched@@YAXAEAVIdleJobList@@@Z; tsched::ClearList<IdleJobList>(IdleJobList &)
0x18006619f  lea     rcx, [r15+40h]
0x1800661a3  call    ??$ClearList@VIdleJobList@@@tsched@@YAXAEAVIdleJobList@@@Z; tsched::ClearList<IdleJobList>(IdleJobList &)
0x1800661a8  lea     rdi, [r15+0D8h]
0x1800661af  mov     rcx, rdi
0x1800661b2  call    ?clear@?$list@PEAV?$vector@EV?$allocator@E@std@@@std@@V?$allocator@PEAV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAXXZ; std::list<std::vector<uchar> *,std::allocator<std::vector<uchar> *>>::clear(void)
0x1800661b7  lea     rsi, [r15+90h]
0x1800661be  mov     rcx, rsi
0x1800661c1  call    ??$ClearMap@V?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@tsched@@YAXAEAV?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@Z; tsched::ClearMap<std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>>>(std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>> &)
0x1800661c6  lea     rbx, [r15+0C8h]
0x1800661cd  mov     rcx, rbx
0x1800661d0  call    ??$ClearMap@V?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@tsched@@YAXAEAV?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@Z; tsched::ClearMap<std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>>>(std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>> &)
0x1800661d5  mov     rcx, rdi
0x1800661d8  call    ??1?$list@PEAUIdleJob@@V?$allocator@PEAUIdleJob@@@std@@@std@@QEAA@XZ; std::list<IdleJob *>::~list<IdleJob *>(void)
0x1800661dd  mov     rcx, rbx
0x1800661e0  call    ??1?$_Tree@V?$_Tmap_traits@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>::~_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>(void)
0x1800661e5  lea     rcx, [r15+0A0h]; lpCriticalSection
0x1800661ec  call    cs:__imp_DeleteCriticalSection
0x1800661f3  nop     dword ptr [rax+rax+00h]
0x1800661f8  mov     rcx, rsi
0x1800661fb  call    ??1?$_Tree@V?$_Tmap_traits@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>::~_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>(void)
0x180066200  lea     rcx, [r15+60h]; lpCriticalSection
0x180066204  call    cs:__imp_DeleteCriticalSection
0x18006620b  nop     dword ptr [rax+rax+00h]
0x180066210  lea     rcx, [r15+40h]
0x180066214  call    ??1?$list@PEAUIdleJob@@V?$allocator@PEAUIdleJob@@@std@@@std@@QEAA@XZ; std::list<IdleJob *>::~list<IdleJob *>(void)
0x180066219  lea     rcx, [r15+30h]
0x18006621d  call    ??1?$list@PEAUIdleJob@@V?$allocator@PEAUIdleJob@@@std@@@std@@QEAA@XZ; std::list<IdleJob *>::~list<IdleJob *>(void)
0x180066222  lea     rcx, [r15+8]
0x180066226  add     rsp, 28h
0x18006622a  pop     r15
0x18006622c  pop     r14
0x18006622e  pop     rdi
0x18006622f  pop     rsi
0x180066230  pop     rbp
0x180066231  pop     rbx
0x180066232  jmp     cs:__imp_DeleteCriticalSection
```
