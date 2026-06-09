# GpaAccessTracker::Query(Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation const &,void *)

- ea: `0x140106e4c`
- end: `0x1401071c8`
- name: `?Query@GpaAccessTracker@@AEAAJAEBUGuestMemoryAccessTrackingQueryOperation@Memory@Resources@Schema@@PEAX@Z`
- size: `892`
- prototype: `__int64 __fastcall(GpaAccessTracker *__hidden this, const struct Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation *, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140106b9c`

## callees

- `0x140033634`
- `0x140040ff8`
- `0x140041a5c`
- `0x14006af58`
- `0x14009d7cc`
- `0x140106e4c`
- `0x140132960`
- `0x140172bf0`
- `0x140210f2c`
- `0x140211210`
- `0x14021131c`
- `0x140211460`
- `0x140211694`
- `0x140211854`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140106ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140106ec1`

## string_xrefs

- `0x1401071b5`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x1401070ea`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x1401070fe`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x140107116`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x14010712d`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x140107145`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x14010715c`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x14010716d`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x14010717e`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`
- `0x140107195`: `onecore\vm\worker\memory\gpaaccesstracker.cpp`

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
        (unsigned int)&byte_1403503F7,
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
0x140106e4c  mov     [rsp+arg_18], rbx
0x140106e51  push    rsi
0x140106e52  push    rdi
0x140106e53  push    r13
0x140106e55  push    r14
0x140106e57  push    r15
0x140106e59  sub     rsp, 70h
0x140106e5d  mov     rax, cs:__security_cookie
0x140106e64  xor     rax, rsp
0x140106e67  mov     [rsp+98h+var_30], rax
0x140106e6c  mov     r15, r8
0x140106e6f  mov     rdi, rdx
0x140106e72  mov     rbx, rcx
0x140106e75  mov     [rsp+98h+var_58], rdx
0x140106e7a  mov     [rsp+98h+var_38], 0
0x140106e83  mov     rax, [rdx+10h]
0x140106e87  lea     rdx, [rax+7]
0x140106e8b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140106e8f  mov     rcx, [rsp+98h]; this
0x140106e97  cmp     rdx, rax
0x140106e9a  jb      loc_1401070E4
0x140106ea0  shr     rdx, 3
0x140106ea4  lea     r8, [rsp+98h+var_38]
0x140106ea9  mov     rcx, r15
0x140106eac  call    ?MapTrackingBufferFromSection@GpaAccessTrackerUtilities@@YAJPEAX_KAEAV?$unique_ptr@_KU?$DeleteByUnmapViewOfFile@_K@@@std@@@Z; GpaAccessTrackerUtilities::MapTrackingBufferFromSection(void *,unsigned __int64,std::unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>> &)
0x140106eb1  mov     rcx, [rsp+98h]; this
0x140106eb9  test    eax, eax
0x140106ebb  js      loc_1401070FB
0x140106ec1  call    cs:__imp_GetCurrentThreadId
0x140106ec8  nop     dword ptr [rax+rax+00h]
0x140106ecd  mov     esi, eax
0x140106ecf  xor     eax, eax
0x140106ed1  lea     r13d, [rax+1]
0x140106ed5  lock cmpxchg [rbx], r13d
0x140106eda  jz      short loc_140106F09
0x140106edc  mov     ecx, [rbx+4]
0x140106edf  cmp     ecx, esi
0x140106ee1  jnz     short loc_140106EEA
0x140106ee3  lock add [rbx+8], r13d
0x140106ee8  jmp     short loc_140106F0C
0x140106eea  test    r13b, al
0x140106eed  jnz     loc_14010709D
0x140106ef3  cmp     eax, 4
0x140106ef6  jnb     loc_14010709D
0x140106efc  mov     edx, eax
0x140106efe  lea     ecx, [rax+1]
0x140106f01  lock cmpxchg [rbx], ecx
0x140106f05  cmp     eax, edx
0x140106f07  jnz     short loc_140106EEA
0x140106f09  xchg    esi, [rbx+4]
0x140106f0c  mov     [rsp+98h+var_40], rbx
0x140106f11  mov     rcx, [rsp+98h]; this
0x140106f19  cmp     dword ptr [rbx+50h], 0
0x140106f1d  jz      loc_140107110
0x140106f23  mov     rcx, [rsp+98h]; this
0x140106f2b  cmp     qword ptr [rbx+60h], 0
0x140106f30  jz      loc_140107127
0x140106f36  xorps   xmm0, xmm0
0x140106f39  movups  xmmword ptr [rsp+98h+var_50], xmm0
0x140106f3e  mov     r8, [rdi+8]
0x140106f42  lea     rdx, [rsp+98h+var_50]
0x140106f47  mov     rcx, rbx
0x140106f4a  call    ?FindContainingTrackedRange@GpaAccessTracker@@AEAA?AV?$shared_ptr@VTrackedMemoryRange@@@std@@_K0@Z; GpaAccessTracker::FindContainingTrackedRange(unsigned __int64,unsigned __int64)
0x140106f4f  nop
0x140106f50  mov     r10, [rsp+98h+var_50]
0x140106f55  mov     r14d, [r10+18h]
0x140106f59  lea     ecx, [r14+r14*8]
0x140106f5d  mov     r9, r13
0x140106f60  shl     r9, cl
0x140106f63  mov     r8, r9
0x140106f66  imul    r8, [rdi+10h]
0x140106f6b  mov     rcx, [rsp+98h]; this
0x140106f73  cmp     r8, [rdi+10h]
0x140106f77  jb      loc_14010713F
0x140106f7d  mov     r11, [rdi+8]
0x140106f81  shr     r11, 0Ch
0x140106f85  mov     rcx, [rsp+98h]; this
0x140106f8d  xor     edx, edx
0x140106f8f  mov     rax, r11
0x140106f92  div     r9
0x140106f95  test    rdx, rdx
0x140106f98  jnz     loc_140107156
0x140106f9e  lea     rax, [r8+r11]
0x140106fa2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140106fa6  cmp     rax, r11
0x140106fa9  cmovnb  rdx, rax
0x140106fad  sbb     r9d, r9d
0x140106fb0  mov     esi, 0C0000095h
0x140106fb5  and     r9d, esi; char *
0x140106fb8  mov     rcx, [rsp+98h]; this
0x140106fc0  cmp     rax, r11
0x140106fc3  jb      loc_14010716D
0x140106fc9  cmp     rdx, r13
0x140106fcc  sbb     r9d, r9d
0x140106fcf  and     r9d, esi; char *
0x140106fd2  lea     rsi, [rdx-1]
0x140106fd6  cmp     rdx, r13
0x140106fd9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140106fe0  cmovb   rsi, rax
0x140106fe4  mov     rcx, [rsp+98h]; this
0x140106fec  jb      loc_14010717E
0x140106ff2  mov     rcx, [rsp+98h]; this
0x140106ffa  mov     rdx, [r10+8]
0x140106ffe  dec     rdx
0x140107001  add     rdx, [r10]
0x140107004  cmp     rdx, rsi
0x140107007  jb      loc_14010718F
0x14010700d  mov     sil, [rdi]
0x140107010  and     sil, r13b
0x140107013  cmp     dword ptr [r10+14h], 2
0x140107018  jnz     short loc_140107051
0x14010701a  xor     r14d, r14d
0x14010701d  shl     r8, 0Ch; unsigned __int64
0x140107021  mov     rdx, [rdi+8]; unsigned __int64
0x140107025  mov     rcx, rbx; this
0x140107028  call    ?FindContainingMemoryRange@GpaAccessTracker@@QEAAPEAVMemoryRange@@_K0@Z; GpaAccessTracker::FindContainingMemoryRange(unsigned __int64,unsigned __int64)
0x14010702d  mov     [rsp+98h+var_70], sil; bool
0x140107032  mov     rcx, [rdi+10h]
0x140107036  mov     [rsp+98h+var_78], rcx; unsigned __int64
0x14010703b  mov     r9, [rdi+8]; unsigned __int64
0x14010703f  mov     r8, rax; struct MemoryRange *
0x140107042  mov     rdx, r15; void *
0x140107045  mov     rcx, [rsp+98h+var_50]; this
0x14010704a  call    ?VaPatQuery@TrackedMemoryRange@@QEAAXPEAXPEAVMemoryRange@@_K2_N@Z; TrackedMemoryRange::VaPatQuery(void *,MemoryRange *,unsigned __int64,unsigned __int64,bool)
0x14010704f  jmp     short loc_140107075
0x140107051  mov     [rsp+98h+var_68], sil
0x140107056  mov     rax, [rsp+98h+var_38]
0x14010705b  mov     [rsp+98h+var_78], rax
0x140107060  mov     r9, [rdi+10h]
0x140107064  mov     r8d, r14d
0x140107067  mov     rdx, r11
0x14010706a  mov     rcx, r10
0x14010706d  call    ?QueryPhysical@MemoryRange@@QEAAJ_KW4_HV_GPA_ACCESS_TRACKING_RANGE_SIZE@@0PEA_K0_N@Z; MemoryRange::QueryPhysical(unsigned __int64,_HV_GPA_ACCESS_TRACKING_RANGE_SIZE,unsigned __int64,unsigned __int64 *,unsigned __int64,bool)
0x140107072  mov     r14d, eax
0x140107075  mov     rcx, [rsp+98h+var_50+8]; this
0x14010707a  test    rcx, rcx
0x14010707d  jz      short loc_140107085
0x14010707f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140107084  nop
0x140107085  mov     rcx, rbx
0x140107088  call    RrwLockRelease
0x14010708d  nop
0x14010708e  lea     rcx, [rsp+98h+var_38]
0x140107093  call    ??1?$unique_ptr@_KU?$DeleteByUnmapViewOfFile@_K@@@std@@QEAA@XZ; std::unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>>::~unique_ptr<unsigned __int64,DeleteByUnmapViewOfFile<unsigned __int64>>(void)
0x140107098  mov     eax, r14d
0x14010709b  jmp     short loc_1401070C1
0x14010709d  mov     r8b, r13b
0x1401070a0  or      edx, 0FFFFFFFFh
0x1401070a3  mov     rcx, rbx
0x1401070a6  call    RrwpLockWait
0x1401070ab  test    eax, eax
0x1401070ad  jz      loc_1401071A7
0x1401070b3  prefetchw byte ptr [rbx]
0x1401070b6  mov     eax, [rbx]
0x1401070b8  jmp     loc_140106EEA
0x1401070bd  mov     eax, dword ptr [rsp+98h+var_38]
0x1401070c1  mov     rcx, [rsp+98h+var_30]
0x1401070c6  xor     rcx, rsp; StackCookie
0x1401070c9  call    __security_check_cookie
0x1401070ce  mov     rbx, [rsp+98h+arg_18]
0x1401070d6  add     rsp, 70h
0x1401070da  pop     r15
0x1401070dc  pop     r14
0x1401070de  pop     r13
0x1401070e0  pop     rdi
0x1401070e1  pop     rsi
0x1401070e2  retn
0x1401070e4  mov     r9d, 8007006Fh; char *
0x1401070ea  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x1401070f1  mov     edx, 60Bh; void *
0x1401070f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401070fb  mov     r9d, eax; char *
0x1401070fe  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x140107105  mov     edx, 613h; void *
0x14010710a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140107110  mov     r9d, 8007139Fh; char *
0x140107116  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x14010711d  mov     edx, 617h; void *
0x140107122  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140107127  mov     r9d, 8007139Fh; char *
0x14010712d  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x140107134  mov     edx, 618h; void *
0x140107139  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010713f  mov     r9d, 8007006Fh; char *
0x140107145  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x14010714c  mov     edx, 627h; void *
0x140107151  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140107156  mov     r9d, 800701E7h; char *
0x14010715c  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x140107163  mov     edx, 62Bh; void *
0x140107168  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010716d  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x140107174  mov     edx, 638h; void *
0x140107179  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14010717e  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x140107185  mov     edx, 63Ah; void *
0x14010718a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14010718f  mov     r9d, 8000000Bh; char *
0x140107195  lea     r8, aOnecoreVmWorke_24; "onecore\\vm\\worker\\memory\\gpaaccesst"...
0x14010719c  mov     edx, 63Eh; void *
0x1401071a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401071a7  mov     rcx, [rsp+98h]; this
0x1401071af  mov     r9d, 102h; char *
0x1401071b5  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1401071bc  mov     edx, 2FEh; void *
0x1401071c1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
