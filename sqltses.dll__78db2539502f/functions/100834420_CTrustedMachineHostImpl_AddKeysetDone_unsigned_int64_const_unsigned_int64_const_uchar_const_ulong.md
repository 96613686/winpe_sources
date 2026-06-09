# CTrustedMachineHostImpl::AddKeysetDone(unsigned __int64 const &,unsigned __int64 const &,uchar const *,ulong)

- ea: `0x100834420`
- end: `0x1008348ba`
- name: `?AddKeysetDone@CTrustedMachineHostImpl@@QEAAXAEB_K0PEBEK@Z`
- size: `1178`
- prototype: `void __fastcall(CTrustedMachineHostImpl *__hidden this, const unsigned __int64 *, const unsigned __int64 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x100835dc0`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x10049f780`
- `0x1008109c0`
- `0x100832710`
- `0x100832880`
- `0x100834190`
- `0x100834420`
- `0x100836980`
- `0x100836bb0`
- `0x100838470`

## import_xrefs

- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100834817`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100834817`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100834744`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100834744`
- `sqldk!SystemThread_TlsIndex` at `0x100834612`
- `sqldk!SystemThread_TlsIndex` at `0x100834696`
- `sqldk!SystemThread_TlsOffset` at `0x10083461b`
- `sqldk!SystemThread_TlsOffset` at `0x10083469f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100834636`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008346bb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100834636`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008346bb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1008346ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1008346ec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1008344c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1008344c2`

## string_xrefs

- `0x1008346d9`: `Sql\DkTemp\sos\include\sossync.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CTrustedMachineHostImpl::AddKeysetDone(
        CTrustedMachineHostImpl *this,
        const unsigned __int64 *a2,
        const unsigned __int64 *a3,
        const unsigned __int8 *a4,
        unsigned int a5)
{
  __int64 v9; // rcx
  bool v10; // zf
  int v11; // ecx
  unsigned __int64 *v12; // rax
  unsigned __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // r15
  int v16; // ecx
  __int64 v17; // r14
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi
  unsigned int v22; // edi
  unsigned int i; // esi
  CSessionCEKSet *v24; // r14
  int v25; // ebx
  char *v26; // rdi
  int v27; // ebx
  char *v28; // rdi
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  char *v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  __int128 v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  _QWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v39; // [rsp+90h] [rbp-70h]
  unsigned int *v40; // [rsp+98h] [rbp-68h]
  _DWORD *v41; // [rsp+A0h] [rbp-60h]
  _DWORD *v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+B0h] [rbp-50h]
  int v44; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  __int64 v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  __int64 v49; // [rsp+E0h] [rbp-20h]
  __int128 v50; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h]
  char v52; // [rsp+100h] [rbp+0h]
  _DWORD v53[28]; // [rsp+110h] [rbp+10h] BYREF
  char v54; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v55[2]; // [rsp+580h] [rbp+480h] BYREF
  _DWORD v56[1536]; // [rsp+590h] [rbp+490h] BYREF

  v49 = -2;
  v30 = (char *)this + 32832;
  v31 = 0;
  TAutoMutex<SOS_Mutex,1>::GetAccess(&v30, 4195809);
  v9 = *(_QWORD *)this;
  if ( !*(_QWORD *)this
    || (((*(_DWORD *)(v9 + 24) - 1) & 0xFFFFFFFD) == 0
      ? (v10 = *(_QWORD *)(v9 + 8) == 0)
      : (v10 = *(_QWORD *)(v9 + 16) == 0),
        v10) )
  {
    ex_raise(335, 45, 16, 14);
    v9 = *(_QWORD *)this;
  }
  v53[0] = 0;
  v53[17] = 0;
  v55[0] = &v54;
  v55[1] = v55;
  v29 = 0;
  v38[0] = a3;
  v38[1] = a4;
  v39 = a5;
  v40 = &v29;
  v41 = v56;
  v42 = v53;
  v43 = 2;
  CEnclave::CallEnclave(v9, 0, 8, v38);
  if ( v43 )
  {
    while ( 1 )
    {
      if ( v53[0] <= 0 || v53[1] != 331 || v53[0] <= 1 || v53[2] != 89 )
      {
        CTrustedMachineHostImpl::RaiseException(this, (const struct CTMException *)v53);
        goto LABEL_25;
      }
      v11 = *((_DWORD *)this + 8204);
      if ( !v11 )
        break;
      if ( a2 && *((_QWORD *)this + 6) == *a2 )
      {
        if ( v11 == 1 )
          break;
        if ( v11 == 2 || (v12 = (unsigned __int64 *)((char *)this + 80), *((_QWORD *)this + 9) < *((_QWORD *)this + 11)) )
          v12 = (unsigned __int64 *)((char *)this + 64);
        v13 = *v12;
      }
      else
      {
        v13 = *((_QWORD *)this + 6);
      }
      v32 = v13;
      if ( v13 == -1 )
        break;
      CTrustedMachineHostImpl::ClearSessionInternal(this, &v32);
      ++*((_QWORD *)this + 1);
      v43 = 2;
LABEL_25:
      CEnclave::CallEnclave(*(_QWORD *)this, 0, 8, v38);
      if ( !v43 )
        goto LABEL_26;
    }
    CTrustedMachineHostImpl::RaiseException(this, (const struct CTMException *)v53);
    v43 = 2;
    goto LABEL_25;
  }
LABEL_26:
  v34 = 0;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v35 = v15;
  v16 = *(_DWORD *)(v15 + 616);
  v34 = !(*(_BYTE *)(v15 + 616) & 1);
  *(_DWORD *)(v15 + 616) = v16 | 1;
  v32 = (unsigned __int64)this + 32944;
  v33 = 0;
  v44 = 4195885;
  v45 = 0;
  v47 = 0;
  v46 = 0;
  v48 = 0;
  v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v18 = *(_QWORD *)(v17 + 256);
  if ( !v18 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v18 = *(_QWORD *)(v17 + 256);
  }
  if ( *((_QWORD *)this + 4121) == v18 )
    utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
  v19 = *(_QWORD *)(v18 + 600);
  if ( v19
    && *(_QWORD *)(v19 + 152)
    && (*(_DWORD *)(v19 + 188) & 4) != 0
    && (v20 = *(_QWORD *)(v19 + 152), (*(_BYTE *)(v20 + 616) & 1) == 0)
    && (*(_DWORD *)(v20 + 800) & 0x180) == 0
    || (unsigned int)SOS_RWLock::GetLongWait((char *)this + 32944, 2, 0xFFFFFFFFLL, &v44) )
  {
    *(_DWORD *)(v15 + 616) &= ~v34;
    v27 = v31;
    if ( v31 )
    {
      v28 = v30;
      do
      {
        *((_QWORD *)v28 + 6) = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v28, 0);
        v10 = v27-- == 1;
        v31 = v27;
      }
      while ( !v10 );
    }
  }
  else
  {
    *((_QWORD *)this + 4121) = v18;
    v33 = 2;
    v21 = *((_QWORD *)this + 4122);
    if ( *(_DWORD *)(v21 + 24) > 0x4000u )
    {
      CTHashTableBase<Pair<SessionCEKInfo,bool>,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::DestroyBuckets(*((_QWORD *)this + 4122));
      *(_DWORD *)(v21 + 24) = 0;
    }
    v22 = 0;
    for ( i = v29; v22 < i; ++v22 )
    {
      *(_QWORD *)&v36 = *a2;
      *((_QWORD *)&v36 + 1) = *(_QWORD *)&v56[6 * v22 + 2];
      LODWORD(v37) = v56[6 * v22];
      WORD2(v37) = v56[6 * v22 + 4];
      v24 = (CSessionCEKSet *)*((_QWORD *)this + 4122);
      if ( !CSessionCEKSet::FContains(v24, (const struct SessionCEKInfo *)&v36) )
      {
        v50 = v36;
        v51 = v37;
        v52 = 1;
        CTHashTable<Pair<SessionCEKInfo,bool>,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::PrivateEnter(
          v24,
          &v50,
          0);
        i = v29;
      }
    }
    SOS_RWLock::ReleaseLock(v32, 2);
    v33 = 0;
    *(_DWORD *)(v15 + 616) &= ~v34;
    v25 = v31;
    if ( v31 )
    {
      v26 = v30;
      do
      {
        *((_QWORD *)v26 + 6) = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v26, 0);
        v10 = v25-- == 1;
        v31 = v25;
      }
      while ( !v10 );
    }
  }
}

```

## disassembly

```asm
0x100834420  push    rbp
0x100834422  push    rbx
0x100834423  push    rsi
0x100834424  push    rdi
0x100834425  push    r12
0x100834427  push    r13
0x100834429  push    r14
0x10083442b  push    r15
0x10083442d  lea     rbp, [rsp-1CA8h]
0x100834435  mov     eax, 1DA8h
0x10083443a  call    _alloca_probe
0x10083443f  sub     rsp, rax
0x100834442  mov     [rbp+1CE0h+var_1D00], 0FFFFFFFFFFFFFFFEh
0x10083444a  mov     rax, cs:__security_cookie
0x100834451  xor     rax, rsp
0x100834454  mov     [rbp+1CE0h+var_50], rax
0x10083445b  mov     rsi, r9
0x10083445e  mov     rdi, r8
0x100834461  mov     r12, rdx
0x100834464  mov     rbx, rcx
0x100834467  lea     rax, [rcx+8040h]
0x10083446e  mov     [rsp+1DE0h+var_1DA8], rax
0x100834473  xor     r13d, r13d
0x100834476  mov     [rsp+1DE0h+var_1DA0], r13d
0x10083447b  mov     edx, 4005E1h
0x100834480  lea     rcx, [rsp+1DE0h+var_1DA8]
0x100834485  call    ?GetAccess@?$TAutoMutex@VSOS_Mutex@@$00@@QEAAXI@Z; TAutoMutex<SOS_Mutex,1>::GetAccess(uint)
0x10083448a  mov     rcx, [rbx]
0x10083448d  test    rcx, rcx
0x100834490  jz      short loc_1008344B0
0x100834492  mov     eax, [rcx+18h]
0x100834495  dec     eax
0x100834497  test    eax, 0FFFFFFFDh
0x10083449c  jz      short loc_1008344A4
0x10083449e  cmp     [rcx+10h], r13
0x1008344a2  jmp     short loc_1008344A9
0x1008344a4  cmp     qword ptr [rcx+8], 0
0x1008344a9  setnz   al
0x1008344ac  test    al, al
0x1008344ae  jnz     short loc_1008344CB
0x1008344b0  mov     edx, 2Dh ; '-'
0x1008344b5  mov     ecx, 14Fh
0x1008344ba  lea     r9d, [rdx-1Fh]
0x1008344be  lea     r8d, [rdx-1Dh]
0x1008344c2  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1008344c8  mov     rcx, [rbx]
0x1008344cb  mov     [rbp+1CE0h+var_1CD0], r13d
0x1008344cf  mov     [rbp+1CE0h+var_1C8C], r13d
0x1008344d3  lea     rax, [rbp+1CE0h+var_1C60]
0x1008344da  mov     [rbp+1CE0h+var_1860], rax
0x1008344e1  lea     rax, [rbp+1CE0h+var_1860]
0x1008344e8  mov     [rbp+1CE0h+var_1858], rax
0x1008344ef  mov     [rsp+1DE0h+var_1DB0], r13d
0x1008344f4  mov     [rbp+1CE0h+var_1D60], rdi
0x1008344f8  mov     [rbp+1CE0h+var_1D58], rsi
0x1008344fc  mov     eax, [rbp+1CE0h+arg_20]
0x100834502  mov     [rbp+1CE0h+var_1D50], eax
0x100834505  lea     rax, [rsp+1DE0h+var_1DB0]
0x10083450a  mov     [rbp+1CE0h+var_1D48], rax
0x10083450e  lea     rax, [rbp+1CE0h+var_1850]
0x100834515  mov     [rbp+1CE0h+var_1D40], rax
0x100834519  lea     rax, [rbp+1CE0h+var_1CD0]
0x10083451d  mov     [rbp+1CE0h+var_1D38], rax
0x100834521  mov     [rbp+1CE0h+var_1D30], 2
0x100834528  lea     r9, [rbp+1CE0h+var_1D60]
0x10083452c  xor     edx, edx
0x10083452e  lea     r8d, [rdx+8]
0x100834532  call    ?CallEnclave@CEnclave@@QEAAXHW4EnclaveMethodId@@PEAX@Z; CEnclave::CallEnclave(int,EnclaveMethodId,void *)
0x100834537  cmp     [rbp+1CE0h+var_1D30], 0
0x10083453b  jz      loc_100834604
0x100834541  mov     eax, [rbp+1CE0h+var_1CD0]
0x100834544  test    eax, eax
0x100834546  jle     loc_1008345DC
0x10083454c  cmp     [rbp+1CE0h+var_1CCC], 14Bh
0x100834553  jnz     loc_1008345DC
0x100834559  cmp     eax, 1
0x10083455c  jle     short loc_1008345DC
0x10083455e  cmp     [rbp+1CE0h+var_1CC8], 59h ; 'Y'
0x100834562  jnz     short loc_1008345DC
0x100834564  mov     ecx, [rbx+8030h]
0x10083456a  test    ecx, ecx
0x10083456c  jz      short loc_1008345C7
0x10083456e  test    r12, r12
0x100834571  jz      short loc_10083459E
0x100834573  mov     rax, [r12]
0x100834577  cmp     [rbx+30h], rax
0x10083457b  jnz     short loc_10083459E
0x10083457d  cmp     ecx, 1
0x100834580  jz      short loc_1008345C7
0x100834582  cmp     ecx, 2
0x100834585  jz      short loc_100834595
0x100834587  mov     rax, [rbx+58h]
0x10083458b  cmp     [rbx+48h], rax
0x10083458f  lea     rax, [rbx+50h]
0x100834593  jnb     short loc_100834599
0x100834595  lea     rax, [rbx+40h]
0x100834599  mov     rax, [rax]
0x10083459c  jmp     short loc_1008345A2
0x10083459e  mov     rax, [rbx+30h]
0x1008345a2  mov     [rsp+1DE0h+var_1D98], rax
0x1008345a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1008345ab  jz      short loc_1008345C7
0x1008345ad  lea     rdx, [rsp+1DE0h+var_1D98]; unsigned __int64 *
0x1008345b2  mov     rcx, rbx; this
0x1008345b5  call    ?ClearSessionInternal@CTrustedMachineHostImpl@@AEAAXAEB_K@Z; CTrustedMachineHostImpl::ClearSessionInternal(unsigned __int64 const &)
0x1008345ba  inc     qword ptr [rbx+8]
0x1008345be  mov     [rbp+1CE0h+var_1D30], 2
0x1008345c5  jmp     short loc_1008345E8
0x1008345c7  lea     rdx, [rbp+1CE0h+var_1CD0]; struct CTMException *
0x1008345cb  mov     rcx, rbx; this
0x1008345ce  call    ?RaiseException@CTrustedMachineHostImpl@@AEAAXAEBVCTMException@@@Z; CTrustedMachineHostImpl::RaiseException(CTMException const &)
0x1008345d3  mov     [rbp+1CE0h+var_1D30], 2
0x1008345da  jmp     short loc_1008345E8
0x1008345dc  lea     rdx, [rbp+1CE0h+var_1CD0]; struct CTMException *
0x1008345e0  mov     rcx, rbx; this
0x1008345e3  call    ?RaiseException@CTrustedMachineHostImpl@@AEAAXAEBVCTMException@@@Z; CTrustedMachineHostImpl::RaiseException(CTMException const &)
0x1008345e8  lea     r9, [rbp+1CE0h+var_1D60]
0x1008345ec  xor     edx, edx
0x1008345ee  lea     r8d, [rdx+8]
0x1008345f2  mov     rcx, [rbx]
0x1008345f5  call    ?CallEnclave@CEnclave@@QEAAXHW4EnclaveMethodId@@PEAX@Z; CEnclave::CallEnclave(int,EnclaveMethodId,void *)
0x1008345fa  cmp     [rbp+1CE0h+var_1D30], 0
0x1008345fe  jnz     loc_100834541
0x100834604  mov     [rsp+1DE0h+var_1D88], r13d
0x100834609  mov     rdx, gs:58h
0x100834612  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100834619  mov     ecx, [rax]
0x10083461b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100834622  mov     edi, [rax]
0x100834624  add     rdi, [rdx+rcx*8]
0x100834628  mov     r15, [rdi+100h]
0x10083462f  test    r15, r15
0x100834632  jnz     short loc_100834643
0x100834634  xor     ecx, ecx
0x100834636  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10083463c  mov     r15, [rdi+100h]
0x100834643  mov     [rsp+1DE0h+var_1D80], r15
0x100834648  mov     ecx, [r15+268h]
0x10083464f  mov     eax, ecx
0x100834651  and     eax, 1
0x100834654  xor     eax, 1
0x100834657  mov     [rsp+1DE0h+var_1D88], eax
0x10083465b  or      ecx, 1
0x10083465e  mov     [r15+268h], ecx
0x100834665  lea     rsi, [rbx+80B0h]
0x10083466c  mov     [rsp+1DE0h+var_1D98], rsi
0x100834671  mov     [rsp+1DE0h+var_1D90], r13d
0x100834676  mov     [rbp+1CE0h+var_1D28], 40062Dh
0x10083467d  mov     [rbp+1CE0h+var_1D20], r13
0x100834681  mov     [rbp+1CE0h+var_1D10], r13
0x100834685  mov     [rbp+1CE0h+var_1D18], r13
0x100834689  mov     [rbp+1CE0h+var_1D08], r13
0x10083468d  mov     rdx, gs:58h
0x100834696  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10083469d  mov     ecx, [rax]
0x10083469f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1008346a6  mov     r14d, [rax]
0x1008346a9  add     r14, [rdx+rcx*8]
0x1008346ad  mov     rdi, [r14+100h]
0x1008346b4  test    rdi, rdi
0x1008346b7  jnz     short loc_1008346C8
0x1008346b9  xor     ecx, ecx
0x1008346bb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1008346c1  mov     rdi, [r14+100h]
0x1008346c8  cmp     [rsi+18h], rdi
0x1008346cc  jnz     short loc_1008346F2
0x1008346ce  mov     [rsp+1DE0h+var_1DC0], r13
0x1008346d3  mov     r9d, 729h
0x1008346d9  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x1008346e0  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x1008346e7  mov     ecx, 1
0x1008346ec  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1008346f2  mov     rcx, [rdi+258h]
0x1008346f9  test    rcx, rcx
0x1008346fc  jz      short loc_100834732
0x1008346fe  cmp     qword ptr [rcx+98h], 0
0x100834706  jz      short loc_100834732
0x100834708  mov     eax, [rcx+0BCh]
0x10083470e  test    al, 4
0x100834710  jz      short loc_100834732
0x100834712  mov     rax, [rcx+98h]
0x100834719  test    byte ptr [rax+268h], 1
0x100834720  jnz     short loc_100834732
0x100834722  test    dword ptr [rax+320h], 180h
0x10083472c  jz      loc_100834859
0x100834732  lea     r9, [rbp+1CE0h+var_1D28]
0x100834736  mov     edx, 2
0x10083473b  mov     r8d, 0FFFFFFFFh
0x100834741  mov     rcx, rsi
0x100834744  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x10083474a  test    eax, eax
0x10083474c  jnz     loc_100834859
0x100834752  mov     [rsi+18h], rdi
0x100834756  mov     [rsp+1DE0h+var_1D90], 2
0x10083475e  mov     rdi, [rbx+80D0h]
0x100834765  cmp     dword ptr [rdi+18h], 4000h
0x10083476c  jbe     short loc_10083477A
0x10083476e  mov     rcx, rdi
0x100834771  call    ?DestroyBuckets@?$CTHashTableBase@U?$Pair@USessionCEKInfo@@_N@@VCEntryHashFn@?$CTMap@USessionCEKInfo@@_NUSessionCEKHash@@V?$CFnC_Default@USessionCEKInfo@@@@V?$CFnI_Default@_N@@V?$CFnD_Noop@USessionCEKInfo@@@@V?$CFnD_Noop@_N@@V?$CMemObjAlloc@$0A@@@@@VCEntryCmpFn@3@VCEntryInvalidFn@3@VCEntryDestroyFn@3@V?$CMemObjAlloc@$0A@@@@@IEAAXXZ; CTHashTableBase<Pair<SessionCEKInfo,bool>,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::DestroyBuckets(void)
0x100834776  mov     [rdi+18h], r13d
0x10083477a  mov     edi, r13d
0x10083477d  mov     esi, [rsp+1DE0h+var_1DB0]
0x100834781  test    esi, esi
0x100834783  jz      loc_10083480D
0x100834789  nop     dword ptr [rax]
0x10083478c  nop     dword ptr [rax+00h]
0x100834790  mov     rax, [r12]
0x100834794  mov     qword ptr [rsp+1DE0h+var_1D78], rax
0x100834799  mov     eax, edi
0x10083479b  lea     rcx, [rax+rax*2]
0x10083479f  mov     rax, [rbp+rcx*8+1CE0h+var_1848]
0x1008347a7  mov     qword ptr [rsp+1DE0h+var_1D78+8], rax
0x1008347ac  mov     eax, [rbp+rcx*8+1CE0h+var_1850]
0x1008347b3  mov     dword ptr [rsp+1DE0h+var_1D68], eax
0x1008347b7  movzx   eax, [rbp+rcx*8+1CE0h+var_1840]
0x1008347bf  mov     word ptr [rsp+1DE0h+var_1D68+4], ax
0x1008347c4  mov     r14, [rbx+80D0h]
0x1008347cb  lea     rdx, [rsp+1DE0h+var_1D78]; struct SessionCEKInfo *
0x1008347d0  mov     rcx, r14; this
0x1008347d3  call    ?FContains@CSessionCEKSet@@QEBA_NAEBUSessionCEKInfo@@@Z; CSessionCEKSet::FContains(SessionCEKInfo const &)
0x1008347d8  test    al, al
0x1008347da  jnz     short loc_100834807
0x1008347dc  movups  xmm0, [rsp+1DE0h+var_1D78]
0x1008347e1  movups  [rbp+1CE0h+var_1CF8], xmm0
0x1008347e5  movsd   xmm1, [rsp+1DE0h+var_1D68]
0x1008347eb  movsd   [rbp+1CE0h+var_1CE8], xmm1
0x1008347f0  mov     [rbp+1CE0h+var_1CE0], 1
0x1008347f4  xor     r8d, r8d
0x1008347f7  lea     rdx, [rbp+1CE0h+var_1CF8]
0x1008347fb  mov     rcx, r14
0x1008347fe  call    ?PrivateEnter@?$CTHashTable@U?$Pair@USessionCEKInfo@@_N@@VCEntryHashFn@?$CTMap@USessionCEKInfo@@_NUSessionCEKHash@@V?$CFnC_Default@USessionCEKInfo@@@@V?$CFnI_Default@_N@@V?$CFnD_Noop@USessionCEKInfo@@@@V?$CFnD_Noop@_N@@V?$CMemObjAlloc@$0A@@@@@VCEntryCmpFn@3@VCEntryInvalidFn@3@VCEntryDestroyFn@3@V?$CMemObjAlloc@$0A@@@@@AEAA_NAEBU?$Pair@USessionCEKInfo@@_N@@PEAU2@@Z; CTHashTable<Pair<SessionCEKInfo,bool>,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<SessionCEKInfo,bool,SessionCEKHash,CFnC_Default<SessionCEKInfo>,CFnI_Default<bool>,CFnD_Noop<SessionCEKInfo>,CFnD_Noop<bool>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::PrivateEnter(Pair<SessionCEKInfo,bool> const &,Pair<SessionCEKInfo,bool> *)
0x100834803  mov     esi, [rsp+1DE0h+var_1DB0]
0x100834807  inc     edi
0x100834809  cmp     edi, esi
0x10083480b  jb      short loc_100834790
0x10083480d  mov     edx, 2
0x100834812  mov     rcx, [rsp+1DE0h+var_1D98]
0x100834817  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x10083481d  mov     [rsp+1DE0h+var_1D90], r13d
0x100834822  mov     eax, [rsp+1DE0h+var_1D88]
0x100834826  not     eax
0x100834828  and     [r15+268h], eax
0x10083482f  mov     ebx, [rsp+1DE0h+var_1DA0]
0x100834833  test    ebx, ebx
0x100834835  jz      short loc_100834897
0x100834837  mov     rdi, [rsp+1DE0h+var_1DA8]
0x10083483c  nop     dword ptr [rax+00h]
0x100834840  mov     [rdi+30h], r13
0x100834844  xor     edx, edx
0x100834846  mov     rcx, rdi
0x100834849  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x10083484e  add     ebx, 0FFFFFFFFh
0x100834851  mov     [rsp+1DE0h+var_1DA0], ebx
0x100834855  jnz     short loc_100834840
0x100834857  jmp     short loc_100834897
0x100834859  mov     eax, [rsp+1DE0h+var_1D88]
0x10083485d  not     eax
0x10083485f  and     [r15+268h], eax
0x100834866  mov     ebx, [rsp+1DE0h+var_1DA0]
0x10083486a  test    ebx, ebx
0x10083486c  jz      short loc_100834897
0x10083486e  mov     rdi, [rsp+1DE0h+var_1DA8]
0x100834873  nop     dword ptr [rax+00h]
0x100834877  nop     word ptr [rax+rax+00000000h]
0x100834880  mov     [rdi+30h], r13
0x100834884  xor     edx, edx
0x100834886  mov     rcx, rdi
0x100834889  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x10083488e  add     ebx, 0FFFFFFFFh
0x100834891  mov     [rsp+1DE0h+var_1DA0], ebx
0x100834895  jnz     short loc_100834880
0x100834897  mov     rcx, [rbp+1CE0h+var_50]
0x10083489e  xor     rcx, rsp; StackCookie
0x1008348a1  call    __security_check_cookie
0x1008348a6  add     rsp, 1DA8h
0x1008348ad  pop     r15
0x1008348af  pop     r14
0x1008348b1  pop     r13
0x1008348b3  pop     r12
0x1008348b5  pop     rdi
0x1008348b6  pop     rsi
0x1008348b7  pop     rbx
0x1008348b8  pop     rbp
0x1008348b9  retn
```
