# LRPC_VIEW_CACHE::GetView(unsigned __int64,void * *,void * *,unsigned __int64 *)

- ea: `0x180072538`
- end: `0x1800726a8`
- name: `?GetView@LRPC_VIEW_CACHE@@QEAAH_KPEAPEAX1PEA_K@Z`
- size: `368`
- prototype: `__int64 __fastcall(LRPC_VIEW_CACHE *__hidden this, unsigned __int64, void **, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800724c4`

## callees

- `0x180022870`
- `0x18004baec`
- `0x180072538`
- `0x18008c670`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180072649`
- `ntdll!RtlLeaveCriticalSection` at `0x180072691`
- `ntdll!RtlLeaveCriticalSection` at `0x180072649`
- `ntdll!RtlLeaveCriticalSection` at `0x180072691`
- `ntdll!RtlEnterCriticalSection` at `0x1800725c9`
- `ntdll!RtlEnterCriticalSection` at `0x1800725c9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18007259e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18007259e`

## pseudocode

```c
__int64 __fastcall LRPC_VIEW_CACHE::GetView(
        LRPC_VIEW_CACHE *this,
        unsigned __int64 a2,
        void **a3,
        void **a4,
        unsigned __int64 *a5)
{
  unsigned int BucketIndex; // eax
  struct _SLIST_ENTRY *v10; // rdx
  volatile signed __int32 *v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rsi
  PSLIST_ENTRY v14; // rbx
  struct _SLIST_ENTRY *v15; // rdx
  struct _SLIST_ENTRY *Next; // rax
  struct _SLIST_ENTRY *v17; // rcx
  struct _SLIST_ENTRY *v18; // r8
  struct _SLIST_ENTRY *v19; // rax
  PSLIST_ENTRY *v20; // rcx

  if ( a2 <= qword_1800FA3F8 )
  {
    BucketIndex = LRPC_VIEW_CACHE_BASE::GetBucketIndex(this, a2);
    v12 = 8LL * BucketIndex;
    v13 = BucketIndex;
    v14 = (PSLIST_ENTRY)_InterlockedExchange64((volatile __int64 *)&v11[v12 + 4], 0);
    if ( v14 )
    {
      if ( v14[2].Next >= v10 )
      {
LABEL_23:
        _InterlockedDecrement((volatile signed __int32 *)this + 38);
        *a3 = (void *)*((_QWORD *)&v14[2].Next + 1);
        *a4 = (void *)*((_QWORD *)&v14[1].Next + 1);
        *a5 = (unsigned __int64)v14[2].Next;
        FreeWrapper(v14);
        return 1;
      }
      _InterlockedDecrement(v11 + 38);
      LRPC_VIEW_CACHE_BASE::InsertView((LRPC_VIEW_CACHE_BASE *)v11, (struct LRPC_CACHED_VIEW_BASE *)v14, BucketIndex);
    }
    if ( (_DWORD)v13 )
    {
      if ( *((_DWORD *)this + v13) )
      {
        v14 = 0;
        RtlEnterCriticalSection(*((PRTL_CRITICAL_SECTION *)this + 18));
        v15 = (struct _SLIST_ENTRY *)((char *)this + v12 * 4 + 32);
        Next = v15->Next;
        if ( v15->Next != v15 )
        {
          do
          {
            v17 = Next;
            Next = Next->Next;
            v18 = v17[2].Next;
            if ( (unsigned __int64)v18 >= a2 )
            {
              if ( v14 )
              {
                if ( v14[2].Next > v18 )
                  v14 = v17;
              }
              else
              {
                v14 = v17;
              }
            }
          }
          while ( Next != v15 );
          if ( v14 )
          {
            v19 = v14->Next;
            if ( v14->Next )
            {
              v20 = (PSLIST_ENTRY *)*((_QWORD *)&v14->Next + 1);
              if ( v20 )
              {
                if ( *(&v19->Next + 1) != v14 || *v20 != v14 )
                  __fastfail(3u);
                *v20 = v19;
                *((_QWORD *)&v19->Next + 1) = v20;
                v14->Next = 0;
                *((_QWORD *)&v14->Next + 1) = 0;
              }
            }
            --*((_DWORD *)this + v13);
            RtlLeaveCriticalSection(*((PRTL_CRITICAL_SECTION *)this + 18));
            goto LABEL_23;
          }
        }
        RtlLeaveCriticalSection(*((PRTL_CRITICAL_SECTION *)this + 18));
      }
    }
    else
    {
      v14 = InterlockedPopEntrySList((PSLIST_HEADER)this + 2);
      if ( v14 )
        goto LABEL_23;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180072538  push    rbx
0x18007253a  push    rbp
0x18007253b  push    rsi
0x18007253c  push    rdi
0x18007253d  push    r12
0x18007253f  push    r14
0x180072541  push    r15
0x180072543  sub     rsp, 20h
0x180072547  cmp     rdx, cs:qword_1800FA3F8
0x18007254e  mov     r15, r9
0x180072551  mov     r12, r8
0x180072554  mov     rbp, rdx
0x180072557  mov     rdi, rcx
0x18007255a  ja      loc_180072697
0x180072560  call    ?GetBucketIndex@LRPC_VIEW_CACHE_BASE@@QEAAK_K@Z; LRPC_VIEW_CACHE_BASE::GetBucketIndex(unsigned __int64)
0x180072565  xor     ebx, ebx
0x180072567  mov     r14d, eax
0x18007256a  shl     r14, 5
0x18007256e  mov     esi, eax
0x180072570  xchg    rbx, [r14+rcx+10h]
0x180072575  test    rbx, rbx
0x180072578  jz      short loc_180072596
0x18007257a  cmp     [rbx+20h], rdx
0x18007257e  jnb     loc_18007264F
0x180072584  lock dec dword ptr [rcx+98h]
0x18007258b  mov     r8d, esi; unsigned int
0x18007258e  mov     rdx, rbx; struct LRPC_CACHED_VIEW_BASE *
0x180072591  call    ?InsertView@LRPC_VIEW_CACHE_BASE@@IEAAXPEAVLRPC_CACHED_VIEW_BASE@@K@Z; LRPC_VIEW_CACHE_BASE::InsertView(LRPC_CACHED_VIEW_BASE *,ulong)
0x180072596  test    esi, esi
0x180072598  jnz     short loc_1800725B5
0x18007259a  lea     rcx, [rdi+20h]; ListHead
0x18007259e  call    cs:__imp_InterlockedPopEntrySList
0x1800725a4  mov     rbx, rax
0x1800725a7  test    rax, rax
0x1800725aa  jz      loc_180072697
0x1800725b0  jmp     loc_18007264F
0x1800725b5  mov     eax, [rdi+rsi*4]
0x1800725b8  test    eax, eax
0x1800725ba  jz      loc_180072697
0x1800725c0  mov     rcx, [rdi+90h]; CriticalSection
0x1800725c7  xor     ebx, ebx
0x1800725c9  call    cs:__imp_RtlEnterCriticalSection
0x1800725cf  lea     rdx, [rdi+20h]
0x1800725d3  add     rdx, r14
0x1800725d6  mov     rax, [rdx]
0x1800725d9  cmp     rax, rdx
0x1800725dc  jz      loc_18007268A
0x1800725e2  mov     rcx, rax
0x1800725e5  mov     rax, [rax]
0x1800725e8  mov     r8, [rcx+20h]
0x1800725ec  cmp     r8, rbp
0x1800725ef  jb      short loc_180072603
0x1800725f1  test    rbx, rbx
0x1800725f4  jnz     short loc_1800725FB
0x1800725f6  mov     rbx, rcx
0x1800725f9  jmp     short loc_180072603
0x1800725fb  cmp     [rbx+20h], r8
0x1800725ff  cmova   rbx, rcx
0x180072603  cmp     rax, rdx
0x180072606  jnz     short loc_1800725E2
0x180072608  test    rbx, rbx
0x18007260b  jz      short loc_18007268A
0x18007260d  mov     rax, [rbx]
0x180072610  test    rax, rax
0x180072613  jz      short loc_18007263F
0x180072615  mov     rcx, [rbx+8]
0x180072619  test    rcx, rcx
0x18007261c  jz      short loc_18007263F
0x18007261e  cmp     [rax+8], rbx
0x180072622  jnz     short loc_180072683
0x180072624  cmp     [rcx], rbx
0x180072627  jnz     short loc_180072683
0x180072629  mov     [rcx], rax
0x18007262c  mov     [rax+8], rcx
0x180072630  mov     qword ptr [rbx], 0
0x180072637  mov     qword ptr [rbx+8], 0
0x18007263f  dec     dword ptr [rdi+rsi*4]
0x180072642  mov     rcx, [rdi+90h]; CriticalSection
0x180072649  call    cs:__imp_RtlLeaveCriticalSection
0x18007264f  lock dec dword ptr [rdi+98h]
0x180072656  mov     rcx, rbx; lpMem
0x180072659  mov     rax, [rbx+28h]
0x18007265d  mov     [r12], rax
0x180072661  mov     rax, [rbx+18h]
0x180072665  mov     [r15], rax
0x180072668  mov     rax, [rsp+58h+arg_20]
0x180072670  mov     rdx, [rbx+20h]
0x180072674  mov     [rax], rdx
0x180072677  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18007267c  mov     eax, 1
0x180072681  jmp     short loc_180072699
0x180072683  mov     ecx, 3
0x180072688  int     29h; Win8: RtlFailFast(ecx)
0x18007268a  mov     rcx, [rdi+90h]; CriticalSection
0x180072691  call    cs:__imp_RtlLeaveCriticalSection
0x180072697  xor     eax, eax
0x180072699  add     rsp, 20h
0x18007269d  pop     r15
0x18007269f  pop     r14
0x1800726a1  pop     r12
0x1800726a3  pop     rdi
0x1800726a4  pop     rsi
0x1800726a5  pop     rbp
0x1800726a6  pop     rbx
0x1800726a7  retn
```
