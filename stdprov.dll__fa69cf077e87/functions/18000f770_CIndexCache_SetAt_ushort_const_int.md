# CIndexCache::SetAt(ushort const *,int)

- ea: `0x18000f770`
- end: `0x18000f899`
- name: `?SetAt@CIndexCache@@QEAAHPEBGH@Z`
- size: `297`
- prototype: `__int64 __fastcall(CIndexCache *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800040c8`

## callees

- `0x180002e10`
- `0x18000b1e8`
- `0x18000b964`
- `0x18000babc`
- `0x18000f770`

## import_xrefs

- `wbemcomn!?SetAt@CFlexArray@@QEAAXHPEAX@Z` at `0x18000f847`
- `wbemcomn!?SetAt@CFlexArray@@QEAAXHPEAX@Z` at `0x18000f847`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000f85d`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000f85d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f7b6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f7e9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f7b6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f7e9`

## pseudocode

```c
__int64 __fastcall CIndexCache::SetAt(CIndexCache *this, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // rax
  unsigned int v7; // r14d
  unsigned __int16 *v8; // rbx
  __int64 v9; // rdx
  _DWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  void *v13; // r8
  unsigned int v14; // ebx
  CFlexArray *v15; // rcx
  _BYTE v17[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-48h] BYREF

  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v6 + 1), 2u));
  MakeGuard<void (*)(unsigned short *),unsigned short *>(v18, v9, v8);
  if ( !v8 )
    goto LABEL_13;
  StringCchCopyW(v8, v7, a2);
  v10 = CWin32DefaultArena::WbemMemAlloc(0x20u);
  v12 = (__int64)v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = &CObject::`vftable';
    *(_QWORD *)v10 = &CCacheEntry::`vftable';
    v10[2] = -1;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = v8;
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
    goto LABEL_13;
  MakeGuard<void (*)(CCacheEntry const *),CCacheEntry *>((__int64)v17, v11, v12);
  v14 = 1;
  v18[0] = 1;
  v15 = (CIndexCache *)((char *)this + 8);
  if ( a3 >= *((_DWORD *)this + 2) )
  {
    if ( !CFlexArray::InsertAt(v15, a3, v13) )
      goto LABEL_10;
    ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>((__int64)v17);
LABEL_13:
    v14 = 0;
    goto LABEL_14;
  }
  CFlexArray::SetAt(v15, a3, v13);
LABEL_10:
  v17[0] = 1;
  ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>((__int64)v17);
LABEL_14:
  ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>((__int64)v18);
  return v14;
}

```

## disassembly

```asm
0x18000f770  mov     [rsp+arg_0], rbx
0x18000f775  mov     [rsp+arg_8], rbp
0x18000f77a  push    rsi
0x18000f77b  push    rdi
0x18000f77c  push    r12
0x18000f77e  push    r14
0x18000f780  push    r15
0x18000f782  sub     rsp, 60h
0x18000f786  mov     edi, r8d
0x18000f789  mov     rsi, rdx
0x18000f78c  mov     rbp, rcx
0x18000f78f  xor     r15d, r15d
0x18000f792  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000f796  mov     rax, r12
0x18000f799  inc     rax
0x18000f79c  cmp     [rdx+rax*2], r15w
0x18000f7a1  jnz     short loc_18000F799
0x18000f7a3  lea     r14d, [rax+1]
0x18000f7a7  mov     eax, 2
0x18000f7ac  mul     r14
0x18000f7af  cmovb   rax, r12
0x18000f7b3  mov     rcx, rax
0x18000f7b6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f7bc  mov     rbx, rax
0x18000f7bf  mov     r8, rax
0x18000f7c2  lea     rcx, [rsp+88h+var_48]
0x18000f7c7  call    ??$MakeGuard@P6AXPEAG@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZPEAG@@P6AXPEAG@Z0@Z; MakeGuard<void (*)(ushort *),ushort *>(void (*)(ushort *),ushort *)
0x18000f7cc  nop
0x18000f7cd  test    rbx, rbx
0x18000f7d0  jz      loc_18000F871
0x18000f7d6  mov     r8, rsi; unsigned __int16 *
0x18000f7d9  mov     edx, r14d; unsigned __int64
0x18000f7dc  mov     rcx, rbx; unsigned __int16 *
0x18000f7df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f7e4  mov     ecx, 20h ; ' '
0x18000f7e9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f7ef  mov     r8, rax
0x18000f7f2  mov     [rsp+88h+arg_18], rax
0x18000f7fa  test    rax, rax
0x18000f7fd  jz      short loc_18000F821
0x18000f7ff  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000f806  mov     [r8], rax
0x18000f809  lea     rax, ??_7CCacheEntry@@6B@; const CCacheEntry::`vftable'
0x18000f810  mov     [r8], rax
0x18000f813  mov     [r8+8], r12d
0x18000f817  mov     [r8+10h], r15
0x18000f81b  mov     [r8+18h], rbx
0x18000f81f  jmp     short loc_18000F824
0x18000f821  mov     r8, r15
0x18000f824  test    r8, r8
0x18000f827  jz      short loc_18000F871
0x18000f829  lea     rcx, [rsp+88h+var_60]
0x18000f82e  call    ??$MakeGuard@P6AXPEBVCCacheEntry@@@ZPEAV1@@@YA?AV?$ScopeGuardImpl1@P6AXPEBVCCacheEntry@@@ZPEAV1@@@P6AXPEBVCCacheEntry@@@ZPEAV1@@Z; MakeGuard<void (*)(CCacheEntry const *),CCacheEntry *>(void (*)(CCacheEntry const *),CCacheEntry *)
0x18000f833  nop
0x18000f834  mov     ebx, 1
0x18000f839  mov     [rsp+88h+var_48], bl
0x18000f83d  lea     rcx, [rbp+8]
0x18000f841  mov     edx, edi
0x18000f843  cmp     edi, [rcx]
0x18000f845  jge     short loc_18000F85D
0x18000f847  call    cs:__imp_?SetAt@CFlexArray@@QEAAXHPEAX@Z; CFlexArray::SetAt(int,void *)
0x18000f84d  mov     [rsp+88h+var_60], bl
0x18000f851  lea     rcx, [rsp+88h+var_60]
0x18000f856  call    ??1?$ScopeGuardImpl1@P6AXPEBVCCacheEntry@@@ZPEAV1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>(void)
0x18000f85b  jmp     short loc_18000F874
0x18000f85d  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18000f863  test    eax, eax
0x18000f865  jz      short loc_18000F84D
0x18000f867  lea     rcx, [rsp+88h+var_60]
0x18000f86c  call    ??1?$ScopeGuardImpl1@P6AXPEBVCCacheEntry@@@ZPEAV1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>(void)
0x18000f871  mov     ebx, r15d
0x18000f874  lea     rcx, [rsp+88h+var_48]
0x18000f879  call    ??1?$ScopeGuardImpl1@P6AXPEBVCCacheEntry@@@ZPEAV1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>(void)
0x18000f87e  mov     eax, ebx
0x18000f880  lea     r11, [rsp+88h+var_28]
0x18000f885  mov     rbx, [r11+30h]
0x18000f889  mov     rbp, [r11+38h]
0x18000f88d  mov     rsp, r11
0x18000f890  pop     r15
0x18000f892  pop     r14
0x18000f894  pop     r12
0x18000f896  pop     rdi
0x18000f897  pop     rsi
0x18000f898  retn
```
