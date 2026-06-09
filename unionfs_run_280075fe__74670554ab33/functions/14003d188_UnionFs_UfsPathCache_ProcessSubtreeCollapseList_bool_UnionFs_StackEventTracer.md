# UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *,UnionFs::StackEventTracer &)

- ea: `0x14003d188`
- end: `0x14003d42b`
- name: `?ProcessSubtreeCollapseList@UfsPathCache@UnionFs@@SAJPEA_NAEAVStackEventTracer@2@@Z`
- size: `675`
- prototype: `static int(bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14005c130`
- `0x1400636bc`
- `0x140064454`

## callees

- `0x140005574`
- `0x14000efd0`
- `0x14000f7fc`
- `0x14003bc14`
- `0x14003c3ec`
- `0x14003d188`
- `0x14003daf4`
- `0x140056afc`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14003d1fe`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14003d1fe`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d23b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d3c6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d23b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d3c6`

## string_xrefs

- `0x14003d37c`: `UnionFs::UfsPathCache::ProcessSubtreeCollapseList`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *a1, struct UnionFs::StackEventTracer *a2)
{
  _QWORD *v4; // rbx
  PLIST_ENTRY v5; // rax
  _QWORD *v6; // rdi
  utl::_RefCountBase *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  const struct _FLT_INSTANCE *v10; // rdx
  UnionFs::UfsPathCache *v11; // rcx
  int v12; // esi
  __int16 v13; // ax
  unsigned __int16 v14; // ax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 *v17; // rcx
  utl::_RefCountBase *v18; // rcx
  const char *v20; // [rsp+28h] [rbp-D8h]
  bool v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h]
  _BYTE v27[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 (__fastcall **v29)(); // [rsp+E0h] [rbp-20h] BYREF
  wistd *v30; // [rsp+148h] [rbp+48h]

  v23 = &v22;
  *a1 = 0;
  v22 = (__int64)&v22;
  v4 = 0;
  v25 = &v22;
  v26 = 1;
  while ( 1 )
  {
    v5 = ExInterlockedRemoveHeadList(
           (PLIST_ENTRY)((char *)UnionFs::g_FilterState + 168),
           (PKSPIN_LOCK)UnionFs::g_FilterState + 23);
    v6 = (_QWORD *)((unsigned __int64)&v5[-2] & -(__int64)(v5 != 0));
    if ( v4 )
    {
      v7 = (utl::_RefCountBase *)v4[3];
      if ( v7 )
        utl::_RefCountBase::_DecStrong(v7);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088), v4);
    }
    if ( !v6 )
    {
      v26 = 0;
      lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()(&v25);
      return 0;
    }
    v29 = off_14007E9B0;
    v30 = (wistd *)&v29;
    v8 = wistd::function<void (bool)>::function<void (bool)>(v27, v28);
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a2, v8);
    v9 = v6[2];
    v10 = (const struct _FLT_INSTANCE *)*v6;
    v11 = (UnionFs::UfsPathCache *)v6[1];
    v21 = 0;
    v12 = UnionFs::UfsPathCache::CollapseSubtree(v11, v10, *(const struct UnionFs::UfsPathName **)(v9 + 200), &v21, a2);
    v13 = *((_WORD *)a2 + 245);
    if ( v13 )
    {
      v14 = v13 - 1;
      *((_WORD *)a2 + 245) = v14;
      v15 = 120 * (v14 + 1LL);
      v16 = *(_QWORD *)((char *)a2 + v15);
      *(_QWORD *)((char *)a2 + v15) = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
    }
    if ( v12 < 0 )
    {
      v24 = v12;
      if ( !v30 )
        wistd::__throw_bad_function_call(0);
      if ( !(*(unsigned __int8 (__fastcall **)(wistd *, int *))(*(_QWORD *)v30 + 32LL))(v30, &v24) )
        break;
    }
    v4 = v6;
    if ( v12 == -1073741267 )
    {
      v17 = v23;
      if ( (__int64 *)*v23 != &v22 )
        __fastfail(3u);
      v4 = 0;
      v6[5] = v23;
      v6[4] = &v22;
      *v17 = (__int64)(v6 + 4);
      v23 = v6 + 4;
    }
    if ( v21 )
      *a1 = 1;
    if ( v30 )
      (*(void (__fastcall **)(wistd *))(*(_QWORD *)v30 + 24LL))(v30);
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v12,
    (int)a2,
    (struct UnionFs::StackEventTracer *)0x34700100200LL,
    (unsigned __int64)"UnionFs::UfsPathCache::ProcessSubtreeCollapseList",
    "PUSH: Collapsing subtree",
    v20);
  if ( v30 )
    (*(void (__fastcall **)(wistd *))(*(_QWORD *)v30 + 24LL))(v30);
  v18 = (utl::_RefCountBase *)v6[3];
  if ( v18 )
    utl::_RefCountBase::_DecStrong(v18);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088), v6);
  v26 = 0;
  lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()(&v25);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14003d188  mov     [rsp-8+arg_10], rbx
0x14003d18d  push    rbp
0x14003d18e  push    rsi
0x14003d18f  push    rdi
0x14003d190  push    r12
0x14003d192  push    r13
0x14003d194  push    r14
0x14003d196  push    r15
0x14003d198  lea     rbp, [rsp-60h]
0x14003d19d  sub     rsp, 160h
0x14003d1a4  mov     rax, cs:__security_cookie
0x14003d1ab  xor     rax, rsp
0x14003d1ae  mov     [rbp+90h+var_40], rax
0x14003d1b2  xor     r12d, r12d
0x14003d1b5  lea     rax, [rsp+190h+var_158]
0x14003d1ba  mov     [rsp+190h+var_150], rax
0x14003d1bf  mov     r14, rdx
0x14003d1c2  lea     rax, [rsp+190h+var_158]
0x14003d1c7  mov     [rcx], r12b
0x14003d1ca  mov     [rsp+190h+var_158], rax
0x14003d1cf  mov     r15, rcx
0x14003d1d2  lea     rax, [rsp+190h+var_158]
0x14003d1d7  mov     ebx, r12d
0x14003d1da  lea     r13d, [r12+1]
0x14003d1df  mov     [rsp+190h+var_140], rax
0x14003d1e4  mov     [rsp+190h+var_138], r13b
0x14003d1e9  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003d1f0  lea     rdx, [rcx+0B8h]; Lock
0x14003d1f7  add     rcx, 0A8h; ListHead
0x14003d1fe  call    cs:__imp_ExInterlockedRemoveHeadList
0x14003d205  nop     dword ptr [rax+rax+00h]
0x14003d20a  lea     rcx, [rax-20h]
0x14003d20e  neg     rax
0x14003d211  sbb     rdi, rdi
0x14003d214  and     rdi, rcx
0x14003d217  test    rbx, rbx
0x14003d21a  jz      short loc_14003D247
0x14003d21c  mov     rcx, [rbx+18h]; this
0x14003d220  test    rcx, rcx
0x14003d223  jz      short loc_14003D22A
0x14003d225  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003d22a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003d231  mov     rdx, rbx; Entry
0x14003d234  add     rcx, 440h; Lookaside
0x14003d23b  call    cs:__imp_ExFreeToLookasideListEx
0x14003d242  nop     dword ptr [rax+rax+00h]
0x14003d247  test    rdi, rdi
0x14003d24a  jz      loc_14003D3EC
0x14003d250  lea     rax, off_14007E9B0
0x14003d257  mov     [rbp+90h+var_B0], rax
0x14003d25b  lea     rdx, [rbp+90h+var_B8]
0x14003d25f  lea     rax, [rbp+90h+var_B0]
0x14003d263  lea     rcx, [rsp+190h+var_130]
0x14003d268  mov     [rbp+90h+var_48], rax
0x14003d26c  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14003d271  mov     rdx, rax
0x14003d274  mov     rcx, r14
0x14003d277  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x14003d27c  mov     r8, [rdi+10h]
0x14003d280  lea     r9, [rsp+190h+var_160]; bool *
0x14003d285  mov     rdx, [rdi]; struct _FLT_INSTANCE *
0x14003d288  mov     rcx, [rdi+8]; this
0x14003d28c  mov     [rsp+190h+var_160], r12b
0x14003d291  mov     r8, [r8+0C8h]; struct UnionFs::UfsPathName *
0x14003d298  mov     [rsp+190h+var_170], r14; struct UnionFs::StackEventTracer *
0x14003d29d  call    ?CollapseSubtree@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@PEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::CollapseSubtree(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,bool *,UnionFs::StackEventTracer &)
0x14003d2a2  mov     esi, eax
0x14003d2a4  movzx   eax, word ptr [r14+1EAh]
0x14003d2ac  test    ax, ax
0x14003d2af  jz      short loc_14003D2E0
0x14003d2b1  sub     ax, r13w
0x14003d2b5  movzx   ecx, ax
0x14003d2b8  mov     [r14+1EAh], cx
0x14003d2c0  add     rcx, r13
0x14003d2c3  imul    rdx, rcx, 78h ; 'x'
0x14003d2c7  mov     rcx, [rdx+r14]
0x14003d2cb  mov     [rdx+r14], r12
0x14003d2cf  test    rcx, rcx
0x14003d2d2  jz      short loc_14003D2E0
0x14003d2d4  mov     rax, [rcx]
0x14003d2d7  mov     rax, [rax+18h]
0x14003d2db  call    _guard_dispatch_icall
0x14003d2e0  test    esi, esi
0x14003d2e2  jns     short loc_14003D30A
0x14003d2e4  mov     rcx, [rbp+90h+var_48]; this
0x14003d2e8  mov     [rsp+190h+var_148], esi
0x14003d2ec  test    rcx, rcx
0x14003d2ef  jz      loc_14003D425
0x14003d2f5  mov     rax, [rcx]
0x14003d2f8  lea     rdx, [rsp+190h+var_148]
0x14003d2fd  mov     rax, [rax+20h]
0x14003d301  call    _guard_dispatch_icall
0x14003d306  test    al, al
0x14003d308  jz      short loc_14003D36B
0x14003d30a  mov     rbx, rdi
0x14003d30d  cmp     esi, 0C000022Dh
0x14003d313  jnz     short loc_14003D343
0x14003d315  mov     rcx, [rsp+190h+var_150]
0x14003d31a  lea     rax, [rsp+190h+var_158]
0x14003d31f  cmp     [rcx], rax
0x14003d322  jnz     loc_14003D3E5
0x14003d328  lea     rax, [rdi+20h]
0x14003d32c  mov     rbx, r12
0x14003d32f  mov     [rax+8], rcx
0x14003d333  lea     rdx, [rsp+190h+var_158]
0x14003d338  mov     [rax], rdx
0x14003d33b  mov     [rcx], rax
0x14003d33e  mov     [rsp+190h+var_150], rax
0x14003d343  cmp     [rsp+190h+var_160], r12b
0x14003d348  jz      short loc_14003D34D
0x14003d34a  mov     [r15], r13b
0x14003d34d  mov     rcx, [rbp+90h+var_48]
0x14003d351  test    rcx, rcx
0x14003d354  jz      loc_14003D1E9
0x14003d35a  mov     rax, [rcx]
0x14003d35d  mov     rax, [rax+18h]
0x14003d361  call    _guard_dispatch_icall
0x14003d366  jmp     loc_14003D1E9
0x14003d36b  lea     rax, aPushCollapsing; "PUSH: Collapsing subtree"
0x14003d372  mov     r8, 34700100200h; struct UnionFs::StackEventTracer *
0x14003d37c  lea     r9, aUnionfsUfspath_38; "UnionFs::UfsPathCache::ProcessSubtreeCo"...
0x14003d383  mov     [rsp+190h+var_170], rax; char *
0x14003d388  mov     rdx, r14; int
0x14003d38b  mov     ecx, esi; this
0x14003d38d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003d392  mov     rcx, [rbp+90h+var_48]
0x14003d396  test    rcx, rcx
0x14003d399  jz      short loc_14003D3A7
0x14003d39b  mov     rax, [rcx]
0x14003d39e  mov     rax, [rax+18h]
0x14003d3a2  call    _guard_dispatch_icall
0x14003d3a7  mov     rcx, [rdi+18h]; this
0x14003d3ab  test    rcx, rcx
0x14003d3ae  jz      short loc_14003D3B5
0x14003d3b0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003d3b5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003d3bc  mov     rdx, rdi; Entry
0x14003d3bf  add     rcx, 440h; Lookaside
0x14003d3c6  call    cs:__imp_ExFreeToLookasideListEx
0x14003d3cd  nop     dword ptr [rax+rax+00h]
0x14003d3d2  lea     rcx, [rsp+190h+var_140]
0x14003d3d7  mov     [rsp+190h+var_138], r12b
0x14003d3dc  call    _lambda_b53eba2d477466c9c18b3d9d5c4fa37a___operator__
0x14003d3e1  mov     eax, esi
0x14003d3e3  jmp     short loc_14003D3FD
0x14003d3e5  mov     ecx, 3
0x14003d3ea  int     29h; Win8: RtlFailFast(ecx)
0x14003d3ec  lea     rcx, [rsp+190h+var_140]
0x14003d3f1  mov     [rsp+190h+var_138], r12b
0x14003d3f6  call    _lambda_b53eba2d477466c9c18b3d9d5c4fa37a___operator__
0x14003d3fb  xor     eax, eax
0x14003d3fd  mov     rcx, [rbp+90h+var_40]
0x14003d401  xor     rcx, rsp; StackCookie
0x14003d404  call    __security_check_cookie
0x14003d409  mov     rbx, [rsp+190h+arg_10]
0x14003d411  add     rsp, 160h
0x14003d418  pop     r15
0x14003d41a  pop     r14
0x14003d41c  pop     r13
0x14003d41e  pop     r12
0x14003d420  pop     rdi
0x14003d421  pop     rsi
0x14003d422  pop     rbp
0x14003d423  retn
0x14003d425  call    ?__throw_bad_function_call@wistd@@YAXXZ; wistd::__throw_bad_function_call(void)
```
