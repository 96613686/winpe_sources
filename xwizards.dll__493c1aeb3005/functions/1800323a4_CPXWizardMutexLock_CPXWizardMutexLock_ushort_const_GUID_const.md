# CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)

- ea: `0x1800323a4`
- end: `0x1800324f7`
- name: `??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z`
- size: `339`
- prototype: `CPXWizardMutexLock *__fastcall(CPXWizardMutexLock *__hidden this, unsigned __int16 *const, GUID *rguid)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003174c`

## callees

- `0x1800085a8`
- `0x18000addc`
- `0x18000ae04`
- `0x1800323a4`
- `0x180032540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032401`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032401`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180032440`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180032440`

## pseudocode

```c
CPXWizardMutexLock *__fastcall CPXWizardMutexLock::CPXWizardMutexLock(
        CPXWizardMutexLock *this,
        unsigned __int16 *const a2,
        GUID *rguid)
{
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // r14
  _WORD *v9; // rax
  PVOID *v10; // rcx
  unsigned int inited; // eax

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  LODWORD(v6) = 0;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  v7 = v6 + 39;
  if ( !rguid )
    v7 = v6;
  if ( v7 )
  {
    v8 = (unsigned int)(v7 + 1);
    v9 = CoTaskMemAlloc(2 * v8);
    *((_QWORD *)this + 2) = v9;
    if ( v9 )
    {
      *v9 = 0;
      if ( a2 )
        StringCchCatW(*((unsigned __int16 **)this + 2), (unsigned int)v8, a2);
      if ( rguid )
        StringFromGUID2(rguid, (LPOLESTR)(*((_QWORD *)this + 2) + 2LL * (unsigned int)v6), 39);
      goto LABEL_18;
    }
    *(_DWORD *)this = -2147024882;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, 2147942414LL);
LABEL_18:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids);
      goto LABEL_18;
    }
  }
  inited = *(_DWORD *)this;
  if ( *(int *)this >= 0 )
  {
    inited = CPXWizardMutexLock::HrInitMutexState(this);
    *(_DWORD *)this = inited;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
    WPP_SF_d(v10[2], 12, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, inited);
  return this;
}

```

## disassembly

```asm
0x1800323a4  push    rbx
0x1800323a6  push    rbp
0x1800323a7  push    rsi
0x1800323a8  push    rdi
0x1800323a9  push    r12
0x1800323ab  push    r14
0x1800323ad  push    r15
0x1800323af  sub     rsp, 20h
0x1800323b3  xor     r15d, r15d
0x1800323b6  mov     rbp, r8
0x1800323b9  mov     [rcx], r15d
0x1800323bc  mov     rsi, rdx
0x1800323bf  mov     [rcx+8], r15
0x1800323c3  mov     rbx, rcx
0x1800323c6  mov     [rcx+10h], r15
0x1800323ca  mov     edi, r15d
0x1800323cd  test    rdx, rdx
0x1800323d0  jz      short loc_1800323E0
0x1800323d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800323d6  inc     rdi
0x1800323d9  cmp     [rdx+rdi*2], r15w
0x1800323de  jnz     short loc_1800323D6
0x1800323e0  test    rbp, rbp
0x1800323e3  lea     eax, [rdi+27h]
0x1800323e6  lea     r12, WPP_GLOBAL_Control
0x1800323ed  cmovz   eax, edi
0x1800323f0  test    eax, eax
0x1800323f2  jz      loc_18003247D
0x1800323f8  inc     eax
0x1800323fa  mov     r14d, eax
0x1800323fd  lea     rcx, [rax+rax]; cb
0x180032401  call    cs:__imp_CoTaskMemAlloc
0x180032407  mov     [rbx+10h], rax
0x18003240b  test    rax, rax
0x18003240e  jz      short loc_180032448
0x180032410  mov     [rax], r15w
0x180032414  test    rsi, rsi
0x180032417  jz      short loc_180032428
0x180032419  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18003241d  mov     r8, rsi; unsigned __int16 *
0x180032420  mov     edx, r14d; unsigned __int64
0x180032423  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032428  test    rbp, rbp
0x18003242b  jz      short loc_1800324A4
0x18003242d  mov     rax, [rbx+10h]
0x180032431  mov     r8d, 27h ; '''; cchMax
0x180032437  mov     ecx, edi
0x180032439  lea     rdx, [rax+rcx*2]; lpsz
0x18003243d  mov     rcx, rbp; rguid
0x180032440  call    cs:__imp_StringFromGUID2
0x180032446  jmp     short loc_1800324A4
0x180032448  mov     dword ptr [rbx], 8007000Eh
0x18003244e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032455  cmp     rcx, r12
0x180032458  jz      short loc_1800324AB
0x18003245a  test    byte ptr [rcx+1Ch], 4
0x18003245e  jz      short loc_1800324AB
0x180032460  mov     rcx, [rcx+10h]
0x180032464  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18003246b  mov     edx, 0Ah
0x180032470  mov     r9d, 8007000Eh
0x180032476  call    WPP_SF_d
0x18003247b  jmp     short loc_1800324A4
0x18003247d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032484  cmp     rcx, r12
0x180032487  jz      short loc_1800324AB
0x180032489  test    byte ptr [rcx+1Ch], 10h
0x18003248d  jz      short loc_1800324AB
0x18003248f  mov     rcx, [rcx+10h]
0x180032493  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18003249a  mov     edx, 0Bh
0x18003249f  call    WPP_SF_
0x1800324a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324ab  mov     eax, [rbx]
0x1800324ad  test    eax, eax
0x1800324af  js      short loc_1800324C2
0x1800324b1  mov     rcx, rbx; this
0x1800324b4  call    ?HrInitMutexState@CPXWizardMutexLock@@AEAAJXZ; CPXWizardMutexLock::HrInitMutexState(void)
0x1800324b9  mov     [rbx], eax
0x1800324bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324c2  cmp     rcx, r12
0x1800324c5  jz      short loc_1800324E5
0x1800324c7  test    byte ptr [rcx+1Ch], 10h
0x1800324cb  jz      short loc_1800324E5
0x1800324cd  mov     rcx, [rcx+10h]
0x1800324d1  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x1800324d8  mov     edx, 0Ch
0x1800324dd  mov     r9d, eax
0x1800324e0  call    WPP_SF_d
0x1800324e5  mov     rax, rbx
0x1800324e8  add     rsp, 20h
0x1800324ec  pop     r15
0x1800324ee  pop     r14
0x1800324f0  pop     r12
0x1800324f2  pop     rdi
0x1800324f3  pop     rsi
0x1800324f4  pop     rbp
0x1800324f5  pop     rbx
0x1800324f6  retn
```
