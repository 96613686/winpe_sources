# CListenerEx::~CListenerEx(void)

- ea: `0x1800076b0`
- end: `0x180007865`
- name: `??1CListenerEx@@UEAA@XZ`
- size: `437`
- prototype: `void __fastcall(CListenerEx *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007460`
- `0x18003ed90`
- `0x1800c4e90`

## callees

- `0x1800076b0`
- `0x180009ee0`
- `0x180015dcc`
- `0x18003269c`
- `0x180089810`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18000772a`
- `ntdll!RtlDeleteResource` at `0x1800077dc`
- `ntdll!RtlDeleteResource` at `0x18000772a`
- `ntdll!RtlDeleteResource` at `0x1800077dc`
- `ntdll!RtlReleaseResource` at `0x180007847`
- `ntdll!RtlReleaseResource` at `0x180007847`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800077bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800077bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076e5`

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
0x1800076b0  mov     [rsp+arg_0], rbx
0x1800076b5  mov     [rsp+arg_8], rsi
0x1800076ba  push    rdi
0x1800076bb  sub     rsp, 30h
0x1800076bf  mov     rsi, rcx
0x1800076c2  lea     rax, ??_7CListenerEx@@6B@; const CListenerEx::`vftable'
0x1800076c9  mov     [rcx], rax
0x1800076cc  lea     rbx, [rcx+0BA8h]
0x1800076d3  mov     rcx, rbx; lpCriticalSection
0x1800076d6  call    cs:__imp_EnterCriticalSection
0x1800076dc  mov     edi, [rsi+6A0h]
0x1800076e2  mov     rcx, rbx; lpCriticalSection
0x1800076e5  call    cs:__imp_LeaveCriticalSection
0x1800076eb  test    edi, edi
0x1800076ed  jz      short loc_1800076F7
0x1800076ef  mov     rcx, rsi; this
0x1800076f2  call    ?Stop@CListenerEx@@UEAAJXZ; CListenerEx::Stop(void)
0x1800076f7  mov     rcx, [rsi+0C30h]
0x1800076fe  mov     qword ptr [rsi+0C30h], 0
0x180007709  test    rcx, rcx
0x18000770c  jz      short loc_18000771A
0x18000770e  mov     rax, [rcx]
0x180007711  mov     rax, [rax+10h]
0x180007715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771a  lea     rbx, [rsi+0C80h]
0x180007721  cmp     dword ptr [rbx+60h], 0
0x180007725  jz      short loc_180007730
0x180007727  mov     rcx, rbx; Resource
0x18000772a  call    cs:__imp_RtlDeleteResource
0x180007730  mov     dword ptr [rbx+60h], 0
0x180007737  lea     rax, ??_7CTSSecurityDescriptor@@6B@; const CTSSecurityDescriptor::`vftable'
0x18000773e  mov     [rsi+0C40h], rax
0x180007745  mov     rcx, [rsi+0C48h]; hMem
0x18000774c  test    rcx, rcx
0x18000774f  jz      short loc_180007761
0x180007751  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180007756  mov     qword ptr [rsi+0C48h], 0
0x180007761  mov     rcx, [rsi+0C50h]; Block
0x180007768  test    rcx, rcx
0x18000776b  jz      short loc_18000777D
0x18000776d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007772  mov     qword ptr [rsi+0C50h], 0
0x18000777d  mov     rcx, [rsi+0C38h]
0x180007784  test    rcx, rcx
0x180007787  jz      short loc_180007796
0x180007789  mov     rax, [rcx]
0x18000778c  mov     rax, [rax+10h]
0x180007790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007795  nop
0x180007796  mov     rcx, [rsi+0C30h]
0x18000779d  test    rcx, rcx
0x1800077a0  jz      short loc_1800077AF
0x1800077a2  mov     rax, [rcx]
0x1800077a5  mov     rax, [rax+10h]
0x1800077a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ae  nop
0x1800077af  lea     rbx, [rsi+0BA8h]
0x1800077b6  cmp     dword ptr [rbx+28h], 1
0x1800077ba  jnz     short loc_1800077CC
0x1800077bc  mov     rcx, rbx; lpCriticalSection
0x1800077bf  call    cs:__imp_DeleteCriticalSection
0x1800077c5  mov     dword ptr [rbx+28h], 0
0x1800077cc  lea     rbx, [rsi+638h]
0x1800077d3  cmp     dword ptr [rbx+60h], 0
0x1800077d7  jz      short loc_1800077E2
0x1800077d9  mov     rcx, rbx; Resource
0x1800077dc  call    cs:__imp_RtlDeleteResource
0x1800077e2  mov     dword ptr [rbx+60h], 0
0x1800077e9  lea     rax, ??_7?$CTSPrivateObject@VIListenerItem@@@@6B@; const CTSPrivateObject<IListenerItem>::`vftable'
0x1800077f0  mov     [rsi], rax
0x1800077f3  mov     rdx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x1800077fa  test    rdx, rdx
0x1800077fd  jz      short loc_18000784E
0x1800077ff  add     rsi, 628h
0x180007806  add     rdx, 18h; struct CResource *
0x18000780a  lea     rcx, [rsp+38h+Resource]; this
0x18000780f  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180007814  mov     rcx, [rsi]
0x180007817  cmp     [rcx+8], rsi
0x18000781b  jnz     short loc_18000785E
0x18000781d  mov     rax, [rsi+8]
0x180007821  cmp     [rax], rsi
0x180007824  jnz     short loc_18000785E
0x180007826  mov     [rax], rcx
0x180007829  mov     [rcx+8], rax
0x18000782d  cmp     [rsp+38h+var_10], 0
0x180007832  jz      short loc_18000784E
0x180007834  mov     [rsp+38h+var_10], 0
0x18000783c  mov     rcx, [rsp+38h+Resource]; Resource
0x180007841  cmp     dword ptr [rcx+60h], 0
0x180007845  jz      short loc_18000784E
0x180007847  call    cs:__imp_RtlReleaseResource
0x18000784d  nop
0x18000784e  mov     rbx, [rsp+38h+arg_0]
0x180007853  mov     rsi, [rsp+38h+arg_8]
0x180007858  add     rsp, 30h
0x18000785c  pop     rdi
0x18000785d  retn
0x18000785e  mov     ecx, 3
0x180007863  int     29h; Win8: RtlFailFast(ecx)
```
