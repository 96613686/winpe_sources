# PseudoEventTrap::~PseudoEventTrap(void)

- ea: `0x180063188`
- end: `0x180063239`
- name: `??1PseudoEventTrap@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(PseudoEventTrap *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180059cf0`

## callees

- `0x18002dd6c`
- `0x180051c80`
- `0x180062bac`
- `0x180062bfc`
- `0x180063114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800631f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006320a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800631f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006320a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063232`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
0x180063188  push    rbx
0x18006318a  push    rbp
0x18006318b  push    rsi
0x18006318c  push    rdi
0x18006318d  push    r14
0x18006318f  push    r15
0x180063191  sub     rsp, 28h
0x180063195  lea     rax, ??_7PseudoEventTrap@@6B@; const PseudoEventTrap::`vftable'
0x18006319c  mov     r15, rcx
0x18006319f  mov     [rcx], rax
0x1800631a2  add     rcx, 30h ; '0'
0x1800631a6  call    ??$ClearList@VIdleJobList@@@tsched@@YAXAEAVIdleJobList@@@Z; tsched::ClearList<IdleJobList>(IdleJobList &)
0x1800631ab  lea     rcx, [r15+40h]
0x1800631af  call    ??$ClearList@VIdleJobList@@@tsched@@YAXAEAVIdleJobList@@@Z; tsched::ClearList<IdleJobList>(IdleJobList &)
0x1800631b4  lea     rdi, [r15+0D8h]
0x1800631bb  mov     rcx, rdi
0x1800631be  call    ?clear@?$list@PEAV?$vector@EV?$allocator@E@std@@@std@@V?$allocator@PEAV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAXXZ; std::list<std::vector<uchar> *,std::allocator<std::vector<uchar> *>>::clear(void)
0x1800631c3  lea     rsi, [r15+90h]
0x1800631ca  mov     rcx, rsi
0x1800631cd  call    ??$ClearMap@V?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@tsched@@YAXAEAV?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@Z; tsched::ClearMap<std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>>>(std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>> &)
0x1800631d2  lea     rbx, [r15+0C8h]
0x1800631d9  mov     rcx, rbx
0x1800631dc  call    ??$ClearMap@V?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@tsched@@YAXAEAV?$multimap@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@@std@@@Z; tsched::ClearMap<std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>>>(std::multimap<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>> &)
0x1800631e1  mov     rcx, rdi
0x1800631e4  call    ??1?$list@PEAUIdleJob@@V?$allocator@PEAUIdleJob@@@std@@@std@@QEAA@XZ; std::list<IdleJob *>::~list<IdleJob *>(void)
0x1800631e9  mov     rcx, rbx
0x1800631ec  call    ??1?$_Tree@V?$_Tmap_traits@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>::~_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>(void)
0x1800631f1  lea     rcx, [r15+0A0h]; lpCriticalSection
0x1800631f8  call    cs:__imp_DeleteCriticalSection
0x1800631fe  mov     rcx, rsi
0x180063201  call    ??1?$_Tree@V?$_Tmap_traits@VUser@@PEAUSessionChangeJob@@Uless@1@V?$allocator@U?$pair@$$CBVUser@@PEAUSessionChangeJob@@@std@@@std@@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>::~_Tree<std::_Tmap_traits<User,SessionChangeJob *,User::less,std::allocator<std::pair<User const,SessionChangeJob *>>,1>>(void)
0x180063206  lea     rcx, [r15+60h]; lpCriticalSection
0x18006320a  call    cs:__imp_DeleteCriticalSection
0x180063210  lea     rcx, [r15+40h]
0x180063214  call    ??1?$list@PEAUIdleJob@@V?$allocator@PEAUIdleJob@@@std@@@std@@QEAA@XZ; std::list<IdleJob *>::~list<IdleJob *>(void)
0x180063219  lea     rcx, [r15+30h]
0x18006321d  call    ??1?$list@PEAUIdleJob@@V?$allocator@PEAUIdleJob@@@std@@@std@@QEAA@XZ; std::list<IdleJob *>::~list<IdleJob *>(void)
0x180063222  lea     rcx, [r15+8]
0x180063226  add     rsp, 28h
0x18006322a  pop     r15
0x18006322c  pop     r14
0x18006322e  pop     rdi
0x18006322f  pop     rsi
0x180063230  pop     rbp
0x180063231  pop     rbx
0x180063232  jmp     cs:__imp_DeleteCriticalSection
```
