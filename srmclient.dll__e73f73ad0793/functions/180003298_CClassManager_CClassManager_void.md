# CClassManager::~CClassManager(void)

- ea: `0x180003298`
- end: `0x1800033f7`
- name: `??1CClassManager@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(CClassManager *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002ed0`
- `0x1800b0dad`
- `0x1800b1128`

## callees

- `0x180001350`
- `0x18000311c`
- `0x180003298`
- `0x18000369c`
- `0x18000a320`
- `0x18006ad30`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800032e6`
- `KERNEL32!DeleteCriticalSection` at `0x180003300`
- `KERNEL32!DeleteCriticalSection` at `0x18000335a`
- `KERNEL32!DeleteCriticalSection` at `0x1800033e9`
- `KERNEL32!DeleteCriticalSection` at `0x1800032e6`
- `KERNEL32!DeleteCriticalSection` at `0x180003300`
- `KERNEL32!DeleteCriticalSection` at `0x18000335a`
- `KERNEL32!DeleteCriticalSection` at `0x1800033e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CClassManager::~CClassManager(CClassManager *this)
{
  void *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = (void *)*((_QWORD *)this + 27);
  if ( v2 )
  {
    CGlobalReportSettings::~CGlobalReportSettings(*((CGlobalReportSettings **)this + 27));
    operator delete(v2);
    *((_QWORD *)this + 27) = 0;
  }
  CClassManager::Teardown(this);
  if ( *((_BYTE *)this + 320) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
    *((_BYTE *)this + 320) = 0;
  }
  if ( *((_BYTE *)this + 272) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    *((_BYTE *)this + 272) = 0;
  }
  v3 = *((_QWORD *)this + 28);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::clear((char *)this + 184);
  operator delete(*((void **)this + 24));
  if ( *((_BYTE *)this + 168) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    *((_BYTE *)this + 168) = 0;
  }
  v4 = *((_QWORD *)this + 15);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 13);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  ATL::IConnectionPointImpl<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424,ATL::CComDynamicUnkArray>((__int64)this + 16);
  if ( *((_BYTE *)this + 96) )
  {
    *((_BYTE *)this + 96) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  }
}

```

## disassembly

```asm
0x180003298  mov     [rsp+arg_0], rcx
0x18000329d  push    rbx
0x18000329e  push    rdi
0x18000329f  sub     rsp, 38h
0x1800032a3  mov     rdi, rcx
0x1800032a6  mov     rbx, [rcx+0D8h]
0x1800032ad  test    rbx, rbx
0x1800032b0  jz      short loc_1800032CD
0x1800032b2  mov     rcx, rbx; this
0x1800032b5  call    ??1CGlobalReportSettings@@QEAA@XZ; CGlobalReportSettings::~CGlobalReportSettings(void)
0x1800032ba  mov     rcx, rbx; Block
0x1800032bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800032c2  mov     qword ptr [rdi+0D8h], 0
0x1800032cd  mov     rcx, rdi; this
0x1800032d0  call    ?Teardown@CClassManager@@AEAAXXZ; CClassManager::Teardown(void)
0x1800032d5  nop
0x1800032d6  lea     rbx, [rdi+118h]
0x1800032dd  cmp     byte ptr [rbx+28h], 0
0x1800032e1  jz      short loc_1800032F0
0x1800032e3  mov     rcx, rbx; lpCriticalSection
0x1800032e6  call    cs:__imp_DeleteCriticalSection
0x1800032ec  mov     byte ptr [rbx+28h], 0
0x1800032f0  lea     rbx, [rdi+0E8h]
0x1800032f7  cmp     byte ptr [rbx+28h], 0
0x1800032fb  jz      short loc_18000330A
0x1800032fd  mov     rcx, rbx; lpCriticalSection
0x180003300  call    cs:__imp_DeleteCriticalSection
0x180003306  mov     byte ptr [rbx+28h], 0
0x18000330a  lea     rax, [rdi+0E0h]
0x180003311  mov     [rsp+48h+arg_8], rax
0x180003316  mov     rcx, [rax]
0x180003319  test    rcx, rcx
0x18000331c  jz      short loc_18000332B
0x18000331e  mov     rax, [rcx]
0x180003321  mov     rax, [rax+10h]
0x180003325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332a  nop
0x18000332b  lea     rbx, [rdi+0B8h]
0x180003332  mov     [rsp+48h+var_28], rbx
0x180003337  mov     rcx, rbx
0x18000333a  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x18000333f  nop
0x180003340  mov     rcx, [rbx+8]; Block
0x180003344  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003349  nop
0x18000334a  lea     rbx, [rdi+80h]
0x180003351  cmp     byte ptr [rbx+28h], 0
0x180003355  jz      short loc_180003364
0x180003357  mov     rcx, rbx; lpCriticalSection
0x18000335a  call    cs:__imp_DeleteCriticalSection
0x180003360  mov     byte ptr [rbx+28h], 0
0x180003364  lea     rax, [rdi+78h]
0x180003368  mov     [rsp+48h+arg_8], rax
0x18000336d  mov     rcx, [rax]
0x180003370  test    rcx, rcx
0x180003373  jz      short loc_180003382
0x180003375  mov     rax, [rcx]
0x180003378  mov     rax, [rax+10h]
0x18000337c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003381  nop
0x180003382  lea     rax, [rdi+70h]
0x180003386  mov     [rsp+48h+arg_8], rax
0x18000338b  mov     rcx, [rax]
0x18000338e  test    rcx, rcx
0x180003391  jz      short loc_1800033A0
0x180003393  mov     rax, [rcx]
0x180003396  mov     rax, [rax+10h]
0x18000339a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339f  nop
0x1800033a0  lea     rax, [rdi+68h]
0x1800033a4  mov     [rsp+48h+arg_8], rax
0x1800033a9  mov     rcx, [rax]
0x1800033ac  test    rcx, rcx
0x1800033af  jz      short loc_1800033BE
0x1800033b1  mov     rax, [rcx]
0x1800033b4  mov     rax, [rax+10h]
0x1800033b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033bd  nop
0x1800033be  lea     rcx, [rdi+10h]
0x1800033c2  mov     [rsp+48h+arg_8], rcx
0x1800033c7  call    ??1?$IConnectionPointImpl@VCClassManager@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ; ATL::IConnectionPointImpl<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<CClassManager,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424,ATL::CComDynamicUnkArray>(void)
0x1800033cc  nop
0x1800033cd  lea     rax, [rdi+30h]
0x1800033d1  mov     [rsp+48h+arg_10], rax
0x1800033d6  lea     rcx, [rax+8]; lpCriticalSection
0x1800033da  mov     [rsp+48h+arg_18], rcx
0x1800033df  cmp     byte ptr [rcx+28h], 0
0x1800033e3  jz      short loc_1800033F0
0x1800033e5  mov     byte ptr [rcx+28h], 0
0x1800033e9  call    cs:__imp_DeleteCriticalSection
0x1800033ef  nop
0x1800033f0  add     rsp, 38h
0x1800033f4  pop     rdi
0x1800033f5  pop     rbx
0x1800033f6  retn
```
