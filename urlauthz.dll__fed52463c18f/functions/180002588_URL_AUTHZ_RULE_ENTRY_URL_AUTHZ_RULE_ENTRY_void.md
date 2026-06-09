# URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(void)

- ea: `0x180002588`
- end: `0x1800026ac`
- name: `??1URL_AUTHZ_RULE_ENTRY@@QEAA@XZ`
- size: `292`
- prototype: `void __fastcall(URL_AUTHZ_RULE_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800026c0`
- `0x180002768`

## callees

- `0x180001048`
- `0x180002578`
- `0x180002588`
- `0x180004010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180002679`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800025b1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002634`

## pseudocode

```c
void __fastcall URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(URL_AUTHZ_RULE_ENTRY *this)
{
  __int64 v1; // rax
  void *v3; // r14
  __int64 v4; // rdi
  __int64 i; // rsi
  __int64 v6; // rax
  void *v7; // r14
  __int64 v8; // rdi
  CACHED_USER_SID *j; // rsi
  __int64 v10; // rax
  void *v11; // r14
  __int64 v12; // rdi
  __int64 k; // rsi
  __int64 v14; // rax
  void *v15; // r14
  __int64 v16; // rdi
  __int64 m; // rsi

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
  {
    v3 = (void *)(v1 - 8);
    v4 = *(_QWORD *)(v1 - 8);
    for ( i = v1 + 56 * v4; v4; --v4 )
    {
      i -= 56;
      ((void (__fastcall *)(__int64))STRU::~STRU)(i);
    }
    operator delete(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = *((_QWORD *)this + 5);
  if ( v6 )
  {
    v7 = (void *)(v6 - 8);
    v8 = *(_QWORD *)(v6 - 8);
    for ( j = (CACHED_USER_SID *)(v6 + 56 * v8); v8; --v8 )
    {
      j = (CACHED_USER_SID *)((char *)j - 56);
      CACHED_USER_SID::~CACHED_USER_SID(j);
    }
    operator delete(v7);
    *((_QWORD *)this + 5) = 0;
  }
  v10 = *((_QWORD *)this + 7);
  if ( v10 )
  {
    v11 = (void *)(v10 - 8);
    v12 = *(_QWORD *)(v10 - 8);
    for ( k = v10 + 56 * v12; v12; --v12 )
    {
      k -= 56;
      ((void (__fastcall *)(__int64))STRU::~STRU)(k);
    }
    operator delete(v11);
    *((_QWORD *)this + 7) = 0;
  }
  v14 = *((_QWORD *)this + 9);
  if ( v14 )
  {
    v15 = (void *)(v14 - 8);
    v16 = *(_QWORD *)(v14 - 8);
    for ( m = v14 + 56 * v16; v16; --v16 )
    {
      m -= 56;
      ((void (__fastcall *)(__int64))STRA::~STRA)(m);
    }
    operator delete(v15);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x180002588  push    rbx
0x18000258a  push    rsi
0x18000258b  push    rdi
0x18000258c  push    r14
0x18000258e  sub     rsp, 28h
0x180002592  mov     rax, [rcx+18h]
0x180002596  mov     rbx, rcx
0x180002599  test    rax, rax
0x18000259c  jz      short loc_1800025DA
0x18000259e  lea     r14, [rax-8]
0x1800025a2  mov     rdi, [r14]
0x1800025a5  imul    rsi, rdi, 38h ; '8'
0x1800025a9  add     rsi, rax
0x1800025ac  test    rdi, rdi
0x1800025af  jz      short loc_1800025CA
0x1800025b1  mov     rax, cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800025b8  sub     rsi, 38h ; '8'
0x1800025bc  mov     rcx, rsi
0x1800025bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c4  sub     rdi, 1
0x1800025c8  jnz     short loc_1800025B1
0x1800025ca  mov     rcx, r14; Block
0x1800025cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800025d2  mov     qword ptr [rbx+18h], 0
0x1800025da  mov     rax, [rbx+28h]
0x1800025de  test    rax, rax
0x1800025e1  jz      short loc_180002618
0x1800025e3  lea     r14, [rax-8]
0x1800025e7  mov     rdi, [r14]
0x1800025ea  imul    rsi, rdi, 38h ; '8'
0x1800025ee  add     rsi, rax
0x1800025f1  test    rdi, rdi
0x1800025f4  jz      short loc_180002608
0x1800025f6  sub     rsi, 38h ; '8'
0x1800025fa  mov     rcx, rsi; this
0x1800025fd  call    ??1CACHED_USER_SID@@QEAA@XZ; CACHED_USER_SID::~CACHED_USER_SID(void)
0x180002602  sub     rdi, 1
0x180002606  jnz     short loc_1800025F6
0x180002608  mov     rcx, r14; Block
0x18000260b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002610  mov     qword ptr [rbx+28h], 0
0x180002618  mov     rax, [rbx+38h]
0x18000261c  test    rax, rax
0x18000261f  jz      short loc_18000265D
0x180002621  lea     r14, [rax-8]
0x180002625  mov     rdi, [r14]
0x180002628  imul    rsi, rdi, 38h ; '8'
0x18000262c  add     rsi, rax
0x18000262f  test    rdi, rdi
0x180002632  jz      short loc_18000264D
0x180002634  mov     rax, cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000263b  sub     rsi, 38h ; '8'
0x18000263f  mov     rcx, rsi
0x180002642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002647  sub     rdi, 1
0x18000264b  jnz     short loc_180002634
0x18000264d  mov     rcx, r14; Block
0x180002650  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002655  mov     qword ptr [rbx+38h], 0
0x18000265d  mov     rax, [rbx+48h]
0x180002661  test    rax, rax
0x180002664  jz      short loc_1800026A2
0x180002666  lea     r14, [rax-8]
0x18000266a  mov     rdi, [r14]
0x18000266d  imul    rsi, rdi, 38h ; '8'
0x180002671  add     rsi, rax
0x180002674  test    rdi, rdi
0x180002677  jz      short loc_180002692
0x180002679  mov     rax, cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002680  sub     rsi, 38h ; '8'
0x180002684  mov     rcx, rsi
0x180002687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268c  sub     rdi, 1
0x180002690  jnz     short loc_180002679
0x180002692  mov     rcx, r14; Block
0x180002695  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000269a  mov     qword ptr [rbx+48h], 0
0x1800026a2  add     rsp, 28h
0x1800026a6  pop     r14
0x1800026a8  pop     rdi
0x1800026a9  pop     rsi
0x1800026aa  pop     rbx
0x1800026ab  retn
```
