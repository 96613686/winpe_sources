# CListenerEx::~CListenerEx(void)

- ea: `0x180007738`
- end: `0x180007912`
- name: `??1CListenerEx@@UEAA@XZ`
- size: `474`
- prototype: `void __fastcall(CListenerEx *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800074d0`
- `0x180040fe0`
- `0x1800caf60`

## callees

- `0x180007738`
- `0x1800095a0`
- `0x1800168c0`
- `0x18003440c`
- `0x18008d310`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800077be`
- `ntdll!RtlDeleteResource` at `0x18000787c`
- `ntdll!RtlDeleteResource` at `0x1800077be`
- `ntdll!RtlDeleteResource` at `0x18000787c`
- `ntdll!RtlReleaseResource` at `0x1800078ed`
- `ntdll!RtlReleaseResource` at `0x1800078ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007859`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007859`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000775e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000775e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007773`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CListenerEx::~CListenerEx(CListenerEx *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // edi
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rax
  PRTL_RESOURCE Resource; // [rsp+20h] [rbp-18h] BYREF
  int v13; // [rsp+28h] [rbp-10h]

  *(_QWORD *)this = &CListenerEx::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2984);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2984));
  v3 = *((_DWORD *)this + 424);
  LeaveCriticalSection(v2);
  if ( v3 )
    CListenerEx::Stop(this);
  v4 = *((_QWORD *)this + 390);
  *((_QWORD *)this + 390) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_DWORD *)this + 824) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 3200));
  *((_DWORD *)this + 824) = 0;
  *((_QWORD *)this + 392) = &CTSSecurityDescriptor::`vftable';
  v5 = (void *)*((_QWORD *)this + 393);
  if ( v5 )
  {
    CUtils::CleanupSD(v5);
    *((_QWORD *)this + 393) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 394);
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 394) = 0;
  }
  v7 = *((_QWORD *)this + 391);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 390);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( *((_DWORD *)this + 756) == 1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2984));
    *((_DWORD *)this + 756) = 0;
  }
  if ( *((_DWORD *)this + 422) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1592));
  *((_DWORD *)this + 422) = 0;
  *(_QWORD *)this = &CTSPrivateObject<IListenerItem>::`vftable';
  if ( g_pObjectTracker )
  {
    v9 = (_QWORD *)((char *)this + 1576);
    CAutoExclusiveLock::CAutoExclusiveLock(
      (CAutoExclusiveLock *)&Resource,
      (struct CResource *)((char *)g_pObjectTracker + 24));
    v10 = *v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v11 = (_QWORD *)v9[1], (_QWORD *)*v11 != v9) )
      __fastfail(3u);
    *v11 = v10;
    *(_QWORD *)(v10 + 8) = v11;
    if ( v13 )
    {
      v13 = 0;
      if ( LODWORD(Resource[1].Lock.DebugInfo) )
        RtlReleaseResource(Resource);
    }
  }
}

```

## disassembly

```asm
0x180007738  mov     [rsp+arg_0], rbx
0x18000773d  mov     [rsp+arg_8], rsi
0x180007742  push    rdi
0x180007743  sub     rsp, 30h
0x180007747  mov     rsi, rcx
0x18000774a  lea     rax, ??_7CListenerEx@@6B@; const CListenerEx::`vftable'
0x180007751  mov     [rcx], rax
0x180007754  lea     rbx, [rcx+0BA8h]
0x18000775b  mov     rcx, rbx; lpCriticalSection
0x18000775e  call    cs:__imp_EnterCriticalSection
0x180007765  nop     dword ptr [rax+rax+00h]
0x18000776a  mov     edi, [rsi+6A0h]
0x180007770  mov     rcx, rbx; lpCriticalSection
0x180007773  call    cs:__imp_LeaveCriticalSection
0x18000777a  nop     dword ptr [rax+rax+00h]
0x18000777f  test    edi, edi
0x180007781  jz      short loc_18000778B
0x180007783  mov     rcx, rsi; this
0x180007786  call    ?Stop@CListenerEx@@UEAAJXZ; CListenerEx::Stop(void)
0x18000778b  mov     rcx, [rsi+0C30h]
0x180007792  mov     qword ptr [rsi+0C30h], 0
0x18000779d  test    rcx, rcx
0x1800077a0  jz      short loc_1800077AE
0x1800077a2  mov     rax, [rcx]
0x1800077a5  mov     rax, [rax+10h]
0x1800077a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ae  lea     rbx, [rsi+0C80h]
0x1800077b5  cmp     dword ptr [rbx+60h], 0
0x1800077b9  jz      short loc_1800077CA
0x1800077bb  mov     rcx, rbx; Resource
0x1800077be  call    cs:__imp_RtlDeleteResource
0x1800077c5  nop     dword ptr [rax+rax+00h]
0x1800077ca  mov     dword ptr [rbx+60h], 0
0x1800077d1  lea     rax, ??_7CTSSecurityDescriptor@@6B@; const CTSSecurityDescriptor::`vftable'
0x1800077d8  mov     [rsi+0C40h], rax
0x1800077df  mov     rcx, [rsi+0C48h]; hMem
0x1800077e6  test    rcx, rcx
0x1800077e9  jz      short loc_1800077FB
0x1800077eb  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800077f0  mov     qword ptr [rsi+0C48h], 0
0x1800077fb  mov     rcx, [rsi+0C50h]; Block
0x180007802  test    rcx, rcx
0x180007805  jz      short loc_180007817
0x180007807  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000780c  mov     qword ptr [rsi+0C50h], 0
0x180007817  mov     rcx, [rsi+0C38h]
0x18000781e  test    rcx, rcx
0x180007821  jz      short loc_180007830
0x180007823  mov     rax, [rcx]
0x180007826  mov     rax, [rax+10h]
0x18000782a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782f  nop
0x180007830  mov     rcx, [rsi+0C30h]
0x180007837  test    rcx, rcx
0x18000783a  jz      short loc_180007849
0x18000783c  mov     rax, [rcx]
0x18000783f  mov     rax, [rax+10h]
0x180007843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007848  nop
0x180007849  lea     rbx, [rsi+0BA8h]
0x180007850  cmp     dword ptr [rbx+28h], 1
0x180007854  jnz     short loc_18000786C
0x180007856  mov     rcx, rbx; lpCriticalSection
0x180007859  call    cs:__imp_DeleteCriticalSection
0x180007860  nop     dword ptr [rax+rax+00h]
0x180007865  mov     dword ptr [rbx+28h], 0
0x18000786c  lea     rbx, [rsi+638h]
0x180007873  cmp     dword ptr [rbx+60h], 0
0x180007877  jz      short loc_180007888
0x180007879  mov     rcx, rbx; Resource
0x18000787c  call    cs:__imp_RtlDeleteResource
0x180007883  nop     dword ptr [rax+rax+00h]
0x180007888  mov     dword ptr [rbx+60h], 0
0x18000788f  lea     rax, ??_7?$CTSPrivateObject@VIListenerItem@@@@6B@; const CTSPrivateObject<IListenerItem>::`vftable'
0x180007896  mov     [rsi], rax
0x180007899  mov     rdx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x1800078a0  test    rdx, rdx
0x1800078a3  jz      short loc_1800078FA
0x1800078a5  add     rsi, 628h
0x1800078ac  add     rdx, 18h; struct CResource *
0x1800078b0  lea     rcx, [rsp+38h+Resource]; this
0x1800078b5  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800078ba  mov     rcx, [rsi]
0x1800078bd  cmp     [rcx+8], rsi
0x1800078c1  jnz     short loc_18000790B
0x1800078c3  mov     rax, [rsi+8]
0x1800078c7  cmp     [rax], rsi
0x1800078ca  jnz     short loc_18000790B
0x1800078cc  mov     [rax], rcx
0x1800078cf  mov     [rcx+8], rax
0x1800078d3  cmp     [rsp+38h+var_10], 0
0x1800078d8  jz      short loc_1800078FA
0x1800078da  mov     [rsp+38h+var_10], 0
0x1800078e2  mov     rcx, [rsp+38h+Resource]; Resource
0x1800078e7  cmp     dword ptr [rcx+60h], 0
0x1800078eb  jz      short loc_1800078FA
0x1800078ed  call    cs:__imp_RtlReleaseResource
0x1800078f4  nop     dword ptr [rax+rax+00h]
0x1800078f9  nop
0x1800078fa  mov     rbx, [rsp+38h+arg_0]
0x1800078ff  mov     rsi, [rsp+38h+arg_8]
0x180007904  add     rsp, 30h
0x180007908  pop     rdi
0x180007909  retn
0x18000790b  mov     ecx, 3
0x180007910  int     29h; Win8: RtlFailFast(ecx)
```
