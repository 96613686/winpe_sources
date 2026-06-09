# LRPC_VIEW_CACHE::GetView(unsigned __int64,void * *,void * *,unsigned __int64 *)

- ea: `0x1800713ec`
- end: `0x180071579`
- name: `?GetView@LRPC_VIEW_CACHE@@QEAAH_KPEAPEAX1PEA_K@Z`
- size: `397`
- prototype: `__int64 __fastcall(LRPC_VIEW_CACHE *__hidden this, unsigned __int64, void **, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180071378`

## callees

- `0x180017ba0`
- `0x180023a40`
- `0x1800713ec`
- `0x18008e2cc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18007150d`
- `ntdll!RtlLeaveCriticalSection` at `0x18007155b`
- `ntdll!RtlLeaveCriticalSection` at `0x18007150d`
- `ntdll!RtlLeaveCriticalSection` at `0x18007155b`
- `ntdll!RtlEnterCriticalSection` at `0x180071483`
- `ntdll!RtlEnterCriticalSection` at `0x180071483`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180071452`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180071452`

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

  if ( a2 <= qword_1800FF3F8 )
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
0x1800713ec  push    rbx
0x1800713ee  push    rbp
0x1800713ef  push    rsi
0x1800713f0  push    rdi
0x1800713f1  push    r12
0x1800713f3  push    r14
0x1800713f5  push    r15
0x1800713f7  sub     rsp, 20h
0x1800713fb  cmp     rdx, cs:qword_1800FF3F8
0x180071402  mov     r15, r9
0x180071405  mov     r12, r8
0x180071408  mov     rbp, rdx
0x18007140b  mov     rdi, rcx
0x18007140e  ja      loc_180071567
0x180071414  call    ?GetBucketIndex@LRPC_VIEW_CACHE_BASE@@QEAAK_K@Z; LRPC_VIEW_CACHE_BASE::GetBucketIndex(unsigned __int64)
0x180071419  xor     ebx, ebx
0x18007141b  mov     r14d, eax
0x18007141e  shl     r14, 5
0x180071422  mov     esi, eax
0x180071424  xchg    rbx, [r14+rcx+10h]
0x180071429  test    rbx, rbx
0x18007142c  jz      short loc_18007144A
0x18007142e  cmp     [rbx+20h], rdx
0x180071432  jnb     loc_180071519
0x180071438  lock dec dword ptr [rcx+98h]
0x18007143f  mov     r8d, esi; unsigned int
0x180071442  mov     rdx, rbx; struct LRPC_CACHED_VIEW_BASE *
0x180071445  call    ?InsertView@LRPC_VIEW_CACHE_BASE@@IEAAXPEAVLRPC_CACHED_VIEW_BASE@@K@Z; LRPC_VIEW_CACHE_BASE::InsertView(LRPC_CACHED_VIEW_BASE *,ulong)
0x18007144a  test    esi, esi
0x18007144c  jnz     short loc_18007146F
0x18007144e  lea     rcx, [rdi+20h]; ListHead
0x180071452  call    cs:__imp_InterlockedPopEntrySList
0x180071459  nop     dword ptr [rax+rax+00h]
0x18007145e  mov     rbx, rax
0x180071461  test    rax, rax
0x180071464  jz      loc_180071567
0x18007146a  jmp     loc_180071519
0x18007146f  mov     eax, [rdi+rsi*4]
0x180071472  test    eax, eax
0x180071474  jz      loc_180071567
0x18007147a  mov     rcx, [rdi+90h]; CriticalSection
0x180071481  xor     ebx, ebx
0x180071483  call    cs:__imp_RtlEnterCriticalSection
0x18007148a  nop     dword ptr [rax+rax+00h]
0x18007148f  lea     rdx, [rdi+20h]
0x180071493  add     rdx, r14
0x180071496  mov     rax, [rdx]
0x180071499  cmp     rax, rdx
0x18007149c  jz      loc_180071554
0x1800714a2  mov     rcx, rax
0x1800714a5  mov     rax, [rax]
0x1800714a8  mov     r8, [rcx+20h]
0x1800714ac  cmp     r8, rbp
0x1800714af  jb      short loc_1800714C3
0x1800714b1  test    rbx, rbx
0x1800714b4  jnz     short loc_1800714BB
0x1800714b6  mov     rbx, rcx
0x1800714b9  jmp     short loc_1800714C3
0x1800714bb  cmp     [rbx+20h], r8
0x1800714bf  cmova   rbx, rcx
0x1800714c3  cmp     rax, rdx
0x1800714c6  jnz     short loc_1800714A2
0x1800714c8  test    rbx, rbx
0x1800714cb  jz      loc_180071554
0x1800714d1  mov     rax, [rbx]
0x1800714d4  test    rax, rax
0x1800714d7  jz      short loc_180071503
0x1800714d9  mov     rcx, [rbx+8]
0x1800714dd  test    rcx, rcx
0x1800714e0  jz      short loc_180071503
0x1800714e2  cmp     [rax+8], rbx
0x1800714e6  jnz     short loc_18007154D
0x1800714e8  cmp     [rcx], rbx
0x1800714eb  jnz     short loc_18007154D
0x1800714ed  mov     [rcx], rax
0x1800714f0  mov     [rax+8], rcx
0x1800714f4  mov     qword ptr [rbx], 0
0x1800714fb  mov     qword ptr [rbx+8], 0
0x180071503  dec     dword ptr [rdi+rsi*4]
0x180071506  mov     rcx, [rdi+90h]; CriticalSection
0x18007150d  call    cs:__imp_RtlLeaveCriticalSection
0x180071514  nop     dword ptr [rax+rax+00h]
0x180071519  lock dec dword ptr [rdi+98h]
0x180071520  mov     rcx, rbx; lpMem
0x180071523  mov     rax, [rbx+28h]
0x180071527  mov     [r12], rax
0x18007152b  mov     rax, [rbx+18h]
0x18007152f  mov     [r15], rax
0x180071532  mov     rax, [rsp+58h+arg_20]
0x18007153a  mov     rdx, [rbx+20h]
0x18007153e  mov     [rax], rdx
0x180071541  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180071546  mov     eax, 1
0x18007154b  jmp     short loc_180071569
0x18007154d  mov     ecx, 3
0x180071552  int     29h; Win8: RtlFailFast(ecx)
0x180071554  mov     rcx, [rdi+90h]; CriticalSection
0x18007155b  call    cs:__imp_RtlLeaveCriticalSection
0x180071562  nop     dword ptr [rax+rax+00h]
0x180071567  xor     eax, eax
0x180071569  add     rsp, 20h
0x18007156d  pop     r15
0x18007156f  pop     r14
0x180071571  pop     r12
0x180071573  pop     rdi
0x180071574  pop     rsi
0x180071575  pop     rbp
0x180071576  pop     rbx
0x180071577  retn
```
