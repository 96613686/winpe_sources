# re2::Prog::GetDFA(re2::Prog::MatchKind)

- ea: `0x180142e50`
- end: `0x18014305e`
- name: `?GetDFA@Prog@re2@@AEAAPEAVDFA@2@W4MatchKind@12@@Z`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180143c00`

## callees

- `0x18012de64`
- `0x180141fc0`
- `0x180142e50`
- `0x180159968`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180142e77`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180142f0e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180142f87`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180142e77`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180142f0e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180142f87`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180142edd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180142f68`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18014302b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180142edd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180142f68`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18014302b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall re2::Prog::GetDFA(__int64 a1, int a2)
{
  union _RTL_RUN_ONCE *v3; // rdi
  void *v4; // rax
  union _RTL_RUN_ONCE *v6; // rdi
  void *v7; // rax
  union _RTL_RUN_ONCE *v8; // rdi
  void *v9; // rax
  __int64 v10; // rbx
  WINBOOL fPending; // [rsp+48h] [rbp+10h] BYREF
  void *v12; // [rsp+50h] [rbp+18h]

  if ( !a2 )
  {
    v3 = (union _RTL_RUN_ONCE *)(a1 + 424);
    if ( __std_init_once_begin_initialize((LPINIT_ONCE)(a1 + 424), 0, &fPending, 0) )
    {
      if ( fPending )
      {
        v4 = operator new(0xD0u);
        v12 = v4;
        if ( v4 )
          v4 = (void *)re2::DFA::DFA(v4, a1, 0, *(_QWORD *)(a1 + 144) / 2LL, v3, 4);
        *(_QWORD *)(a1 + 152) = v4;
        if ( !InitOnceComplete(v3, 0, 0) )
          _std_init_once_link_alternate_names_and_abort();
      }
      return *(_QWORD *)(a1 + 152);
    }
    goto LABEL_16;
  }
  if ( a2 == 3 )
  {
    v6 = (union _RTL_RUN_ONCE *)(a1 + 424);
    if ( __std_init_once_begin_initialize((LPINIT_ONCE)(a1 + 424), 0, &fPending, 0) )
    {
      if ( fPending )
      {
        v7 = operator new(0xD0u);
        v12 = v7;
        if ( v7 )
          v7 = (void *)re2::DFA::DFA(v7, a1, 3, *(_QWORD *)(a1 + 144), v6, 4);
        *(_QWORD *)(a1 + 152) = v7;
        if ( !InitOnceComplete(v6, 0, 0) )
          _std_init_once_link_alternate_names_and_abort();
      }
      return *(_QWORD *)(a1 + 152);
    }
LABEL_16:
    __fastfail(5u);
  }
  v8 = (union _RTL_RUN_ONCE *)(a1 + 432);
  if ( !__std_init_once_begin_initialize((LPINIT_ONCE)(a1 + 432), 0, &fPending, 0) )
    goto LABEL_16;
  if ( fPending )
  {
    if ( *(_BYTE *)(a1 + 2) )
    {
      v9 = operator new(0xD0u);
      v12 = v9;
      if ( v9 )
        v9 = (void *)re2::DFA::DFA(v9, a1, 1, *(_QWORD *)(a1 + 144), v8, 4);
    }
    else
    {
      v9 = operator new(0xD0u);
      v12 = v9;
      if ( v9 )
        v9 = (void *)re2::DFA::DFA(v9, a1, 1, *(_QWORD *)(a1 + 144) / 2LL, v8, 4);
    }
    v10 = a1 + 160;
    *(_QWORD *)v10 = v9;
    if ( !InitOnceComplete(v8, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  else
  {
    v10 = a1 + 160;
  }
  return *(_QWORD *)v10;
}

```

## disassembly

```asm
0x180142e50  mov     [rsp+arg_0], rbx
0x180142e55  push    rdi
0x180142e56  sub     rsp, 30h
0x180142e5a  mov     rbx, rcx
0x180142e5d  xor     r9d, r9d; lpContext
0x180142e60  lea     r8, [rsp+38h+fPending]; fPending
0x180142e65  test    edx, edx
0x180142e67  jnz     loc_180142EFD
0x180142e6d  lea     rdi, [rcx+1A8h]
0x180142e74  mov     rcx, rdi; lpInitOnce
0x180142e77  call    cs:__imp___std_init_once_begin_initialize
0x180142e7d  test    eax, eax
0x180142e7f  jz      loc_180142F91
0x180142e85  cmp     [rsp+38h+fPending], 0
0x180142e8a  jz      short loc_180142EEB
0x180142e8c  mov     [rsp+38h+var_18], rdi
0x180142e91  mov     [rsp+38h+var_10], 4
0x180142e99  mov     ecx, 0D0h; Size
0x180142e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180142ea3  mov     rcx, rax
0x180142ea6  mov     [rsp+38h+arg_10], rax
0x180142eab  test    rax, rax
0x180142eae  jz      short loc_180142ECE
0x180142eb0  mov     rax, [rbx+90h]
0x180142eb7  cqo
0x180142eb9  sub     rax, rdx
0x180142ebc  sar     rax, 1
0x180142ebf  mov     r9, rax
0x180142ec2  xor     r8d, r8d
0x180142ec5  mov     rdx, rbx
0x180142ec8  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x180142ecd  nop
0x180142ece  mov     [rbx+98h], rax
0x180142ed5  xor     r8d, r8d; lpContext
0x180142ed8  xor     edx, edx; dwFlags
0x180142eda  mov     rcx, rdi; lpInitOnce
0x180142edd  call    cs:__imp_InitOnceComplete
0x180142ee3  test    eax, eax
0x180142ee5  jz      loc_18014304C
0x180142eeb  mov     rax, [rbx+98h]
0x180142ef2  mov     rbx, [rsp+38h+arg_0]
0x180142ef7  add     rsp, 30h
0x180142efb  pop     rdi
0x180142efc  retn
0x180142efd  cmp     edx, 3
0x180142f00  jnz     short loc_180142F7B
0x180142f02  lea     rdi, [rcx+1A8h]
0x180142f09  xor     edx, edx; dwFlags
0x180142f0b  mov     rcx, rdi; lpInitOnce
0x180142f0e  call    cs:__imp___std_init_once_begin_initialize
0x180142f14  test    eax, eax
0x180142f16  jz      short loc_180142F91
0x180142f18  cmp     [rsp+38h+fPending], 0
0x180142f1d  jz      short loc_180142EEB
0x180142f1f  mov     [rsp+38h+var_18], rdi
0x180142f24  mov     [rsp+38h+var_10], 4
0x180142f2c  mov     ecx, 0D0h; Size
0x180142f31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180142f36  mov     [rsp+38h+arg_10], rax
0x180142f3b  test    rax, rax
0x180142f3e  jz      short loc_180142F59
0x180142f40  mov     r9, [rbx+90h]
0x180142f47  mov     r8d, 3
0x180142f4d  mov     rdx, rbx
0x180142f50  mov     rcx, rax
0x180142f53  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x180142f58  nop
0x180142f59  mov     [rbx+98h], rax
0x180142f60  xor     r8d, r8d; lpContext
0x180142f63  xor     edx, edx; dwFlags
0x180142f65  mov     rcx, rdi; lpInitOnce
0x180142f68  call    cs:__imp_InitOnceComplete
0x180142f6e  test    eax, eax
0x180142f70  jz      loc_180143052
0x180142f76  jmp     loc_180142EEB
0x180142f7b  lea     rdi, [rcx+1B0h]
0x180142f82  xor     edx, edx; dwFlags
0x180142f84  mov     rcx, rdi; lpInitOnce
0x180142f87  call    cs:__imp___std_init_once_begin_initialize
0x180142f8d  test    eax, eax
0x180142f8f  jnz     short loc_180142F98
0x180142f91  mov     ecx, 5
0x180142f96  int     29h; Win8: RtlFailFast(ecx)
0x180142f98  cmp     [rsp+38h+fPending], 0
0x180142f9d  jz      loc_180143037
0x180142fa3  mov     [rsp+38h+var_18], rdi
0x180142fa8  mov     [rsp+38h+var_10], 4
0x180142fb0  mov     ecx, 0D0h; Size
0x180142fb5  cmp     byte ptr [rbx+2], 0
0x180142fb9  jnz     short loc_180142FF0
0x180142fbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180142fc0  mov     rcx, rax
0x180142fc3  mov     [rsp+38h+arg_10], rax
0x180142fc8  test    rax, rax
0x180142fcb  jz      short loc_180142FEE
0x180142fcd  mov     rax, [rbx+90h]
0x180142fd4  cqo
0x180142fd6  sub     rax, rdx
0x180142fd9  sar     rax, 1
0x180142fdc  mov     r9, rax
0x180142fdf  mov     r8d, 1
0x180142fe5  mov     rdx, rbx
0x180142fe8  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x180142fed  nop
0x180142fee  jmp     short loc_180143018
0x180142ff0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180142ff5  mov     [rsp+38h+arg_10], rax
0x180142ffa  test    rax, rax
0x180142ffd  jz      short loc_180143018
0x180142fff  mov     r9, [rbx+90h]
0x180143006  mov     r8d, 1
0x18014300c  mov     rdx, rbx
0x18014300f  mov     rcx, rax
0x180143012  call    ??0DFA@re2@@QEAA@PEAVProg@1@W4MatchKind@21@_J@Z; re2::DFA::DFA(re2::Prog *,re2::Prog::MatchKind,__int64)
0x180143017  nop
0x180143018  mov     ecx, 0A0h
0x18014301d  add     rbx, rcx
0x180143020  mov     [rbx], rax
0x180143023  xor     r8d, r8d; lpContext
0x180143026  xor     edx, edx; dwFlags
0x180143028  mov     rcx, rdi; lpInitOnce
0x18014302b  call    cs:__imp_InitOnceComplete
0x180143031  test    eax, eax
0x180143033  jz      short loc_180143058
0x180143035  jmp     short loc_18014303E
0x180143037  add     rbx, 0A0h
0x18014303e  mov     rax, [rbx]
0x180143041  mov     rbx, [rsp+38h+arg_0]
0x180143046  add     rsp, 30h
0x18014304a  pop     rdi
0x18014304b  retn
0x18014304c  call    __std_init_once_link_alternate_names_and_abort
0x180143052  call    __std_init_once_link_alternate_names_and_abort
0x180143058  call    __std_init_once_link_alternate_names_and_abort
```
