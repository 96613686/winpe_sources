# GpaAccessTracker::Query(Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation const &,void *)

- ea: `0x1400f6bac`
- end: `0x1400f6f28`
- name: `?Query@GpaAccessTracker@@AEAAJAEBUGuestMemoryAccessTrackingQueryOperation@Memory@Resources@Schema@@PEAX@Z`
- size: `892`
- prototype: `__int64 __fastcall(GpaAccessTracker *__hidden this, const struct Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation *, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1400f68fc`

## callees

- `0x1400314a4`
- `0x140035238`
- `0x140035c9c`
- `0x140078628`
- `0x1400ba144`
- `0x1400f6bac`
- `0x14011ea40`
- `0x140161200`
- `0x14020280c`
- `0x140202af0`
- `0x140202bfc`
- `0x140202f90`
- `0x1402031c4`
- `0x140203384`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f6c21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f6c21`

## string_xrefs

- `0x1400f6f15`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x1400f6e4a`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6e5e`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6e76`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6e8d`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6ea5`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6ebc`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6ecd`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6ede`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1400f6ef5`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GpaAccessTracker::Query(
        GpaAccessTracker *this,
        const struct Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation *a2,
        void *a3)
{
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdx
  int v8; // eax
  DWORD CurrentThreadId; // esi
  __int64 v10; // r8
  unsigned __int32 v11; // eax
  unsigned __int32 v12; // edx
  unsigned int v13; // r14d
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // r11
  bool v16; // si
  unsigned int Physical; // r14d
  struct MemoryRange *ContainingMemoryRange; // rax
  wil *v19; // rcx
  __int64 result; // rax
  int v21; // ebx
  const struct _tlgProvider_t *v22; // rax
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // [rsp+20h] [rbp-78h]
  const struct Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation *v26; // [rsp+40h] [rbp-58h] BYREF
  std::_Ref_count_base *v27[2]; // [rsp+48h] [rbp-50h] BYREF
  GpaAccessTracker *v28; // [rsp+58h] [rbp-40h] BYREF
  __int64 v29; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v26 = a2;
    v29 = 0;
    v6 = *((_QWORD *)a2 + 2);
    v7 = (v6 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v7 < v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x60B,
        (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
        (const char *)0x8007006FLL,
        v25);
    v8 = GpaAccessTrackerUtilities::MapTrackingBufferFromSection(a3, v7 >> 3, &v29);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x613,
        (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
        (const char *)(unsigned int)v8,
        v25);
    CurrentThreadId = GetCurrentThreadId();
    v11 = _InterlockedCompareExchange((volatile signed __int32 *)this, 1, 0);
    if ( v11 )
    {
      if ( *((_DWORD *)this + 1) == CurrentThreadId )
      {
        _InterlockedAdd((volatile signed __int32 *)this + 2, 1u);
LABEL_11:
        v28 = this;
        if ( !*((_DWORD *)this + 20) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x617,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            (const char *)0x8007139FLL,
            v25);
        if ( !*((_QWORD *)this + 12) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x618,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            (const char *)0x8007139FLL,
            v25);
        *(_OWORD *)v27 = 0;
        GpaAccessTracker::FindContainingTrackedRange(this, v27, *((_QWORD *)a2 + 1));
        v13 = *((_DWORD *)v27[0] + 6);
        v14 = *((_QWORD *)a2 + 2) * (1LL << (9 * (unsigned __int8)v13));
        if ( v14 < *((_QWORD *)a2 + 2) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x627,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            (const char *)0x8007006FLL,
            v25);
        v15 = *((_QWORD *)a2 + 1) >> 12;
        if ( v15 % (1LL << (9 * (unsigned __int8)v13)) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x62B,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            (const char *)0x800701E7LL,
            v25);
        if ( v14 + v15 < v15 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x638,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            v14 + v15 < v15 ? (const char *)0xC0000095LL : 0,
            v25);
        if ( !(v14 + v15) )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x63A,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            (const char *)0xC0000095LL,
            v25);
        if ( *(_QWORD *)v27[0] + *((_QWORD *)v27[0] + 1) - 1LL < v14 + v15 - 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x63E,
            (unsigned int)"onecore\\vm\\worker\\memory\\gpaaccesstracker.cpp",
            (const char *)0x8000000BLL,
            v25);
        v16 = *(_BYTE *)a2 & 1;
        if ( *((_DWORD *)v27[0] + 5) == 2 )
        {
          Physical = 0;
          ContainingMemoryRange = GpaAccessTracker::FindContainingMemoryRange(this, *((_QWORD *)a2 + 1), v14 << 12);
          TrackedMemoryRange::VaPatQuery(
            v27[0],
            a3,
            ContainingMemoryRange,
            *((_QWORD *)a2 + 1),
            *((_QWORD *)a2 + 2),
            v16);
        }
        else
        {
          Physical = MemoryRange::QueryPhysical(v27[0], v15, v13, *((_QWORD *)a2 + 2), v29);
        }
        if ( v27[1] )
          std::_Ref_count_base::_Decref(v27[1]);
        RrwLockRelease(this);
        std::unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>>::~unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>>(&v29);
        return Physical;
      }
      do
      {
        while ( (v11 & 1) != 0 || v11 >= 4 )
        {
          LOBYTE(v10) = 1;
          if ( !(unsigned int)RrwpLockWait(this, 0xFFFFFFFFLL, v10) )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x2FE,
              (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
              (const char *)0x102,
              v25);
          _m_prefetchw(this);
          v11 = *(_DWORD *)this;
        }
        v12 = v11;
        v11 = _InterlockedCompareExchange((volatile signed __int32 *)this, v11 + 1, v11);
      }
      while ( v11 != v12 );
    }
    _InterlockedExchange((volatile __int32 *)this + 1, CurrentThreadId);
    goto LABEL_11;
  }
  catch ( ... )
  {
    v21 = wil::ResultFromCaughtException(v19);
    LODWORD(v29) = v21;
    v22 = VmWorkerTrace::Provider();
    if ( *(_DWORD *)v22 > 5u )
    {
      v27[0] = *((std::_Ref_count_base **)v26 + 2);
      v28 = (GpaAccessTracker *)*((_QWORD *)v26 + 1);
      LODWORD(v26) = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v22,
        (unsigned int)byte_14035AEF1,
        v23,
        v24,
        (__int64)&v26,
        (__int64)&v28,
        (__int64)v27);
    }
    return (unsigned int)v29;
  }
  return result;
}

```

## disassembly

```asm
0x1400f6bac  mov     [rsp+arg_18], rbx
0x1400f6bb1  push    rsi
0x1400f6bb2  push    rdi
0x1400f6bb3  push    r13
0x1400f6bb5  push    r14
0x1400f6bb7  push    r15
0x1400f6bb9  sub     rsp, 70h
0x1400f6bbd  mov     rax, cs:__security_cookie
0x1400f6bc4  xor     rax, rsp
0x1400f6bc7  mov     [rsp+98h+var_30], rax
0x1400f6bcc  mov     r15, r8
0x1400f6bcf  mov     rdi, rdx
0x1400f6bd2  mov     rbx, rcx
0x1400f6bd5  mov     [rsp+98h+var_58], rdx
0x1400f6bda  mov     [rsp+98h+var_38], 0
0x1400f6be3  mov     rax, [rdx+10h]
0x1400f6be7  lea     rdx, [rax+7]
0x1400f6beb  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400f6bef  mov     rcx, [rsp+98h]; this
0x1400f6bf7  cmp     rdx, rax
0x1400f6bfa  jb      loc_1400F6E44
0x1400f6c00  shr     rdx, 3
0x1400f6c04  lea     r8, [rsp+98h+var_38]
0x1400f6c09  mov     rcx, r15
0x1400f6c0c  call    ?MapTrackingBufferFromSection@GpaAccessTrackerUtilities@@YAJPEAX_KAEAV?$unique_ptr@_KU?$DeleteByUnmapViewOfFile@_K@@@std@@@Z; GpaAccessTrackerUtilities::MapTrackingBufferFromSection(void *,unsigned __int64,std::unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>> &)
0x1400f6c11  mov     rcx, [rsp+98h]; this
0x1400f6c19  test    eax, eax
0x1400f6c1b  js      loc_1400F6E5B
0x1400f6c21  call    cs:__imp_GetCurrentThreadId
0x1400f6c28  nop     dword ptr [rax+rax+00h]
0x1400f6c2d  mov     esi, eax
0x1400f6c2f  xor     eax, eax
0x1400f6c31  lea     r13d, [rax+1]
0x1400f6c35  lock cmpxchg [rbx], r13d
0x1400f6c3a  jz      short loc_1400F6C69
0x1400f6c3c  mov     ecx, [rbx+4]
0x1400f6c3f  cmp     ecx, esi
0x1400f6c41  jnz     short loc_1400F6C4A
0x1400f6c43  lock add [rbx+8], r13d
0x1400f6c48  jmp     short loc_1400F6C6C
0x1400f6c4a  test    r13b, al
0x1400f6c4d  jnz     loc_1400F6DFD
0x1400f6c53  cmp     eax, 4
0x1400f6c56  jnb     loc_1400F6DFD
0x1400f6c5c  mov     edx, eax
0x1400f6c5e  lea     ecx, [rax+1]
0x1400f6c61  lock cmpxchg [rbx], ecx
0x1400f6c65  cmp     eax, edx
0x1400f6c67  jnz     short loc_1400F6C4A
0x1400f6c69  xchg    esi, [rbx+4]
0x1400f6c6c  mov     [rsp+98h+var_40], rbx
0x1400f6c71  mov     rcx, [rsp+98h]; this
0x1400f6c79  cmp     dword ptr [rbx+50h], 0
0x1400f6c7d  jz      loc_1400F6E70
0x1400f6c83  mov     rcx, [rsp+98h]; this
0x1400f6c8b  cmp     qword ptr [rbx+60h], 0
0x1400f6c90  jz      loc_1400F6E87
0x1400f6c96  xorps   xmm0, xmm0
0x1400f6c99  movups  xmmword ptr [rsp+98h+var_50], xmm0
0x1400f6c9e  mov     r8, [rdi+8]
0x1400f6ca2  lea     rdx, [rsp+98h+var_50]
0x1400f6ca7  mov     rcx, rbx
0x1400f6caa  call    ?FindContainingTrackedRange@GpaAccessTracker@@AEAA?AV?$shared_ptr@VTrackedMemoryRange@@@std@@_K0@Z; GpaAccessTracker::FindContainingTrackedRange(unsigned __int64,unsigned __int64)
0x1400f6caf  nop
0x1400f6cb0  mov     r10, [rsp+98h+var_50]
0x1400f6cb5  mov     r14d, [r10+18h]
0x1400f6cb9  lea     ecx, [r14+r14*8]
0x1400f6cbd  mov     r9, r13
0x1400f6cc0  shl     r9, cl
0x1400f6cc3  mov     r8, r9
0x1400f6cc6  imul    r8, [rdi+10h]
0x1400f6ccb  mov     rcx, [rsp+98h]; this
0x1400f6cd3  cmp     r8, [rdi+10h]
0x1400f6cd7  jb      loc_1400F6E9F
0x1400f6cdd  mov     r11, [rdi+8]
0x1400f6ce1  shr     r11, 0Ch
0x1400f6ce5  mov     rcx, [rsp+98h]; this
0x1400f6ced  xor     edx, edx
0x1400f6cef  mov     rax, r11
0x1400f6cf2  div     r9
0x1400f6cf5  test    rdx, rdx
0x1400f6cf8  jnz     loc_1400F6EB6
0x1400f6cfe  lea     rax, [r8+r11]
0x1400f6d02  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400f6d06  cmp     rax, r11
0x1400f6d09  cmovnb  rdx, rax
0x1400f6d0d  sbb     r9d, r9d
0x1400f6d10  mov     esi, 0C0000095h
0x1400f6d15  and     r9d, esi; char *
0x1400f6d18  mov     rcx, [rsp+98h]; this
0x1400f6d20  cmp     rax, r11
0x1400f6d23  jb      loc_1400F6ECD
0x1400f6d29  cmp     rdx, r13
0x1400f6d2c  sbb     r9d, r9d
0x1400f6d2f  and     r9d, esi; char *
0x1400f6d32  lea     rsi, [rdx-1]
0x1400f6d36  cmp     rdx, r13
0x1400f6d39  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400f6d40  cmovb   rsi, rax
0x1400f6d44  mov     rcx, [rsp+98h]; this
0x1400f6d4c  jb      loc_1400F6EDE
0x1400f6d52  mov     rcx, [rsp+98h]; this
0x1400f6d5a  mov     rdx, [r10+8]
0x1400f6d5e  dec     rdx
0x1400f6d61  add     rdx, [r10]
0x1400f6d64  cmp     rdx, rsi
0x1400f6d67  jb      loc_1400F6EEF
0x1400f6d6d  mov     sil, [rdi]
0x1400f6d70  and     sil, r13b
0x1400f6d73  cmp     dword ptr [r10+14h], 2
0x1400f6d78  jnz     short loc_1400F6DB1
0x1400f6d7a  xor     r14d, r14d
0x1400f6d7d  shl     r8, 0Ch; unsigned __int64
0x1400f6d81  mov     rdx, [rdi+8]; unsigned __int64
0x1400f6d85  mov     rcx, rbx; this
0x1400f6d88  call    ?FindContainingMemoryRange@GpaAccessTracker@@QEAAPEAVMemoryRange@@_K0@Z; GpaAccessTracker::FindContainingMemoryRange(unsigned __int64,unsigned __int64)
0x1400f6d8d  mov     [rsp+98h+var_70], sil; bool
0x1400f6d92  mov     rcx, [rdi+10h]
0x1400f6d96  mov     [rsp+98h+var_78], rcx; unsigned __int64
0x1400f6d9b  mov     r9, [rdi+8]; unsigned __int64
0x1400f6d9f  mov     r8, rax; struct MemoryRange *
0x1400f6da2  mov     rdx, r15; void *
0x1400f6da5  mov     rcx, [rsp+98h+var_50]; this
0x1400f6daa  call    ?VaPatQuery@TrackedMemoryRange@@QEAAXPEAXPEAVMemoryRange@@_K2_N@Z; TrackedMemoryRange::VaPatQuery(void *,MemoryRange *,unsigned __int64,unsigned __int64,bool)
0x1400f6daf  jmp     short loc_1400F6DD5
0x1400f6db1  mov     [rsp+98h+var_68], sil
0x1400f6db6  mov     rax, [rsp+98h+var_38]
0x1400f6dbb  mov     [rsp+98h+var_78], rax
0x1400f6dc0  mov     r9, [rdi+10h]
0x1400f6dc4  mov     r8d, r14d
0x1400f6dc7  mov     rdx, r11
0x1400f6dca  mov     rcx, r10
0x1400f6dcd  call    ?QueryPhysical@MemoryRange@@QEAAJ_KW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@0PEA_K0_N@Z; MemoryRange::QueryPhysical(unsigned __int64,_HV_GPA_ACCESS_TRACKING_RANGE_SIZE,unsigned __int64,unsigned __int64 *,unsigned __int64,bool)
0x1400f6dd2  mov     r14d, eax
0x1400f6dd5  mov     rcx, [rsp+98h+var_50+8]; this
0x1400f6dda  test    rcx, rcx
0x1400f6ddd  jz      short loc_1400F6DE5
0x1400f6ddf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400f6de4  nop
0x1400f6de5  mov     rcx, rbx
0x1400f6de8  call    RrwLockRelease
0x1400f6ded  nop
0x1400f6dee  lea     rcx, [rsp+98h+var_38]
0x1400f6df3  call    ??1?$unique_ptr@_KU?$DeleteByUnmapViewOfFile@_K@@@std@@QEAA@XZ; std::unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>>::~unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>>(void)
0x1400f6df8  mov     eax, r14d
0x1400f6dfb  jmp     short loc_1400F6E21
0x1400f6dfd  mov     r8b, r13b
0x1400f6e00  or      edx, 0FFFFFFFFh
0x1400f6e03  mov     rcx, rbx
0x1400f6e06  call    RrwpLockWait
0x1400f6e0b  test    eax, eax
0x1400f6e0d  jz      loc_1400F6F07
0x1400f6e13  prefetchw byte ptr [rbx]
0x1400f6e16  mov     eax, [rbx]
0x1400f6e18  jmp     loc_1400F6C4A
0x1400f6e1d  mov     eax, dword ptr [rsp+98h+var_38]
0x1400f6e21  mov     rcx, [rsp+98h+var_30]
0x1400f6e26  xor     rcx, rsp; StackCookie
0x1400f6e29  call    __security_check_cookie
0x1400f6e2e  mov     rbx, [rsp+98h+arg_18]
0x1400f6e36  add     rsp, 70h
0x1400f6e3a  pop     r15
0x1400f6e3c  pop     r14
0x1400f6e3e  pop     r13
0x1400f6e40  pop     rdi
0x1400f6e41  pop     rsi
0x1400f6e42  retn
0x1400f6e44  mov     r9d, 8007006Fh; char *
0x1400f6e4a  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6e51  mov     edx, 60Bh; void *
0x1400f6e56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6e5b  mov     r9d, eax; char *
0x1400f6e5e  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6e65  mov     edx, 613h; void *
0x1400f6e6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6e70  mov     r9d, 8007139Fh; char *
0x1400f6e76  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6e7d  mov     edx, 617h; void *
0x1400f6e82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6e87  mov     r9d, 8007139Fh; char *
0x1400f6e8d  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6e94  mov     edx, 618h; void *
0x1400f6e99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6e9f  mov     r9d, 8007006Fh; char *
0x1400f6ea5  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6eac  mov     edx, 627h; void *
0x1400f6eb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6eb6  mov     r9d, 800701E7h; char *
0x1400f6ebc  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6ec3  mov     edx, 62Bh; void *
0x1400f6ec8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6ecd  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6ed4  mov     edx, 638h; void *
0x1400f6ed9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400f6ede  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6ee5  mov     edx, 63Ah; void *
0x1400f6eea  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400f6eef  mov     r9d, 8000000Bh; char *
0x1400f6ef5  lea     r8, aOnecoreVmWorke_25; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1400f6efc  mov     edx, 63Eh; void *
0x1400f6f01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f6f07  mov     rcx, [rsp+98h]; this
0x1400f6f0f  mov     r9d, 102h; char *
0x1400f6f15  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400f6f1c  mov     edx, 2FEh; void *
0x1400f6f21  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
