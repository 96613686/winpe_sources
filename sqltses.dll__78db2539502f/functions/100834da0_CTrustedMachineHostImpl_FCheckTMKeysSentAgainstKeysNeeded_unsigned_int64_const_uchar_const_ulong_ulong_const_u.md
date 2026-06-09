# CTrustedMachineHostImpl::FCheckTMKeysSentAgainstKeysNeeded(unsigned __int64 const &,uchar const *,ulong,ulong const *,ulong const *,unsigned __int64 const *,ulong)

- ea: `0x100834da0`
- end: `0x10083504b`
- name: `?FCheckTMKeysSentAgainstKeysNeeded@CTrustedMachineHostImpl@@QEAA_NAEB_KPEBEKPEBK2PEB_KK@Z`
- size: `683`
- prototype: `bool __fastcall(CTrustedMachineHostImpl *__hidden this, const unsigned __int64 *, const unsigned __int8 *, unsigned int, const unsigned int *, const unsigned int *, const unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100836690`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x1008348c0`
- `0x100834da0`

## import_xrefs

- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x10083501c`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x10083501c`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100834f82`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100834f82`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100834e55`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100834e55`
- `sqldk!SystemThread_TlsIndex` at `0x100834ed8`
- `sqldk!SystemThread_TlsOffset` at `0x100834ee1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100834efc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100834efc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834e7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834f2b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834e7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834f2b`

## string_xrefs

- `0x100834f1a`: `Sql\DkTemp\sos\include\sossync.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTrustedMachineHostImpl::FCheckTMKeysSentAgainstKeysNeeded(
        CTrustedMachineHostImpl *this,
        const unsigned __int64 *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        char *a5,
        char *a6,
        const unsigned __int64 *a7,
        unsigned int a8)
{
  __int64 v12; // rdx
  unsigned int v13; // r15d
  int v14; // ecx
  bool v15; // zf
  char *v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // ebx
  char *v23; // r8
  int v24; // eax
  unsigned __int8 v25; // bl
  char v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  char *v29; // [rsp+38h] [rbp-C8h]
  int v30; // [rsp+40h] [rbp-C0h]
  int v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  _DWORD v42[1536]; // [rsp+A0h] [rbp-60h] BYREF

  v41 = -2;
  v12 = *(_QWORD *)this;
  v13 = 1;
  if ( !*(_QWORD *)this
    || ((v14 = *(_DWORD *)(v12 + 24), ((v14 - 1) & 0xFFFFFFFD) == 0)
      ? (v15 = *(_QWORD *)(v12 + 8) == 0)
      : (v15 = *(_QWORD *)(v12 + 16) == 0),
        v15 || !v14 || !*((_BYTE *)this + 32888)) )
  {
    v31 = 4195793;
    v32 = 0;
    v34 = 0;
    v33 = 0;
    v35 = 0;
    v27 = 1;
    if ( (unsigned int)WaitableBase::Wait((char *)this + 32896, 0xFFFFFFFFLL, &v31, 0, v27) )
      utassert_fail(1u, "SOS_OK == res", "aetmhost.cpp", 1420, 0);
  }
  CTrustedMachineHostImpl::GetAddKeyInfo(this, a2, a3, a4, &v28, (struct CEKInfo *)v42);
  v16 = (char *)this + 32944;
  v29 = (char *)this + 32944;
  v30 = 0;
  v36 = 4195885;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  v40 = 0;
  v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v18 = *(_QWORD *)(v17 + 256);
  if ( !v18 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v18 = *(_QWORD *)(v17 + 256);
  }
  if ( *((_QWORD *)v16 + 3) == v18 )
    utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
  v19 = *(_QWORD *)(v18 + 600);
  if ( v19
    && *(_QWORD *)(v19 + 152)
    && (*(_DWORD *)(v19 + 188) & 4) != 0
    && (v20 = *(_QWORD *)(v19 + 152), (*(_BYTE *)(v20 + 616) & 1) == 0)
    && (*(_DWORD *)(v20 + 800) & 0x180) == 0
    || (unsigned int)SOS_RWLock::GetLongWait(v16, 1, 0xFFFFFFFFLL, &v36) )
  {
    v13 = v30;
  }
  else
  {
    v30 = 1;
    if ( a8 <= v28 )
    {
      v21 = 0;
      if ( !a8 )
      {
LABEL_30:
        v25 = 1;
        goto LABEL_33;
      }
      v23 = a6;
      while ( 1 )
      {
        v24 = 0;
        if ( !v28 )
          break;
        while ( *(_DWORD *)&v23[a5 - a6] != v42[6 * v24]
             || *(_DWORD *)v23 != LOWORD(v42[6 * v24 + 4])
             || *a7 != *(_QWORD *)&v42[6 * v24 + 2] )
        {
          if ( ++v24 >= v28 )
            goto LABEL_32;
        }
        ++v21;
        v23 += 4;
        ++a7;
        if ( v21 >= a8 )
          goto LABEL_30;
      }
    }
  }
LABEL_32:
  v25 = 0;
LABEL_33:
  if ( v13 )
  {
    SOS_RWLock::ReleaseLock(v29, v13);
    v30 = 0;
  }
  return v25;
}

```

## disassembly

```asm
0x100834da0  push    rbp
0x100834da2  push    rbx
0x100834da3  push    rsi
0x100834da4  push    rdi
0x100834da5  push    r12
0x100834da7  push    r14
0x100834da9  push    r15
0x100834dab  lea     rbp, [rsp-17B0h]
0x100834db3  mov     eax, 18B0h
0x100834db8  call    _alloca_probe
0x100834dbd  sub     rsp, rax
0x100834dc0  mov     [rbp+17E0h+var_1848], 0FFFFFFFFFFFFFFFEh
0x100834dc8  mov     rax, cs:__security_cookie
0x100834dcf  xor     rax, rsp
0x100834dd2  mov     [rbp+17E0h+var_40], rax
0x100834dd9  mov     r14d, r9d
0x100834ddc  mov     rsi, r8
0x100834ddf  mov     rdi, rdx
0x100834de2  mov     rbx, rcx
0x100834de5  mov     rdx, [rcx]
0x100834de8  xor     r12d, r12d
0x100834deb  lea     r15d, [r12+1]
0x100834df0  test    rdx, rdx
0x100834df3  jz      short loc_100834E20
0x100834df5  mov     ecx, [rdx+18h]
0x100834df8  lea     eax, [rcx-1]
0x100834dfb  test    eax, 0FFFFFFFDh
0x100834e00  jz      short loc_100834E08
0x100834e02  cmp     [rdx+10h], r12
0x100834e06  jmp     short loc_100834E0C
0x100834e08  cmp     [rdx+8], r12
0x100834e0c  setnz   al
0x100834e0f  test    al, al
0x100834e11  jz      short loc_100834E20
0x100834e13  test    ecx, ecx
0x100834e15  jz      short loc_100834E20
0x100834e17  cmp     [rbx+8078h], r12b
0x100834e1e  jnz     short loc_100834E81
0x100834e20  mov     [rsp+18E0h+var_1898], 4005D1h
0x100834e28  mov     [rsp+18E0h+var_1890], r12
0x100834e2d  mov     [rsp+18E0h+var_1880], r12
0x100834e32  mov     [rsp+18E0h+var_1888], r12
0x100834e37  mov     [rsp+18E0h+var_1878], r12
0x100834e3c  lea     rcx, [rbx+8080h]
0x100834e43  mov     byte ptr [rsp+18E0h+var_18C0], r15b
0x100834e48  xor     r9d, r9d
0x100834e4b  lea     r8, [rsp+18E0h+var_1898]
0x100834e50  mov     edx, 0FFFFFFFFh
0x100834e55  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100834e5b  test    eax, eax
0x100834e5d  jz      short loc_100834E81
0x100834e5f  mov     [rsp+18E0h+var_18C0], r12
0x100834e64  mov     r9d, 58Ch
0x100834e6a  lea     r8, aAetmhostCpp; "aetmhost.cpp"
0x100834e71  lea     rdx, aSosOkRes; "SOS_OK == res"
0x100834e78  mov     ecx, r15d
0x100834e7b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100834e81  lea     rax, [rbp+17E0h+var_1840]
0x100834e85  mov     [rsp+18E0h+var_18B8], rax; struct CEKInfo *
0x100834e8a  lea     rax, [rsp+18E0h+var_18B0]
0x100834e8f  mov     [rsp+18E0h+var_18C0], rax; unsigned int *
0x100834e94  mov     r9d, r14d; unsigned int
0x100834e97  mov     r8, rsi; unsigned __int8 *
0x100834e9a  mov     rdx, rdi; unsigned __int64 *
0x100834e9d  mov     rcx, rbx; this
0x100834ea0  call    ?GetAddKeyInfo@CTrustedMachineHostImpl@@QEAAXAEB_KPEBEKPEAKPEAUCEKInfo@@@Z; CTrustedMachineHostImpl::GetAddKeyInfo(unsigned __int64 const &,uchar const *,ulong,ulong *,CEKInfo *)
0x100834ea5  lea     rdi, [rbx+80B0h]
0x100834eac  mov     [rsp+18E0h+var_18A8], rdi
0x100834eb1  mov     [rsp+18E0h+var_18A0], r12d
0x100834eb6  mov     [rsp+18E0h+var_1870], 40062Dh
0x100834ebe  mov     [rsp+18E0h+var_1868], r12
0x100834ec3  mov     [rbp+17E0h+var_1858], r12
0x100834ec7  mov     [rbp+17E0h+var_1860], r12
0x100834ecb  mov     [rbp+17E0h+var_1850], r12
0x100834ecf  mov     rdx, gs:58h
0x100834ed8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100834edf  mov     ecx, [rax]
0x100834ee1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100834ee8  mov     esi, [rax]
0x100834eea  add     rsi, [rdx+rcx*8]
0x100834eee  mov     rbx, [rsi+100h]
0x100834ef5  test    rbx, rbx
0x100834ef8  jnz     short loc_100834F09
0x100834efa  xor     ecx, ecx
0x100834efc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100834f02  mov     rbx, [rsi+100h]
0x100834f09  cmp     [rdi+18h], rbx
0x100834f0d  jnz     short loc_100834F31
0x100834f0f  mov     [rsp+18E0h+var_18C0], r12
0x100834f14  mov     r9d, 729h
0x100834f1a  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x100834f21  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x100834f28  mov     ecx, r15d
0x100834f2b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100834f31  mov     rdx, [rbx+258h]
0x100834f38  test    rdx, rdx
0x100834f3b  jz      short loc_100834F71
0x100834f3d  cmp     qword ptr [rdx+98h], 0
0x100834f45  jz      short loc_100834F71
0x100834f47  mov     eax, [rdx+0BCh]
0x100834f4d  test    al, 4
0x100834f4f  jz      short loc_100834F71
0x100834f51  mov     rax, [rdx+98h]
0x100834f58  test    byte ptr [rax+268h], 1
0x100834f5f  jnz     short loc_100834F71
0x100834f61  test    dword ptr [rax+320h], 180h
0x100834f6b  jz      loc_100835008
0x100834f71  lea     r9, [rsp+18E0h+var_1870]
0x100834f76  mov     r8d, 0FFFFFFFFh
0x100834f7c  mov     edx, r15d
0x100834f7f  mov     rcx, rdi
0x100834f82  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x100834f88  test    eax, eax
0x100834f8a  jnz     short loc_100835008
0x100834f8c  mov     [rsp+18E0h+var_18A0], r15d
0x100834f91  mov     edi, [rbp+17E0h+arg_38]
0x100834f97  mov     r10d, [rsp+18E0h+var_18B0]
0x100834f9c  cmp     edi, r10d
0x100834f9f  ja      short loc_10083500D
0x100834fa1  mov     ebx, r12d
0x100834fa4  test    edi, edi
0x100834fa6  jz      short loc_100835004
0x100834fa8  mov     r9, [rbp+17E0h+arg_30]
0x100834faf  mov     r8, [rbp+17E0h+arg_28]
0x100834fb6  mov     rsi, [rbp+17E0h+arg_20]
0x100834fbd  sub     rsi, r8
0x100834fc0  mov     eax, r12d
0x100834fc3  test    r10d, r10d
0x100834fc6  jz      short loc_10083500D
0x100834fc8  mov     r11d, [rsi+r8]
0x100834fcc  mov     ecx, eax
0x100834fce  lea     rdx, [rcx+rcx*2]
0x100834fd2  cmp     r11d, [rbp+rdx*8+17E0h+var_1840]
0x100834fd7  jnz     short loc_100834FED
0x100834fd9  movzx   ecx, [rbp+rdx*8+17E0h+var_1830]
0x100834fde  cmp     [r8], ecx
0x100834fe1  jnz     short loc_100834FED
0x100834fe3  mov     rcx, [rbp+rdx*8+17E0h+var_1838]
0x100834fe8  cmp     [r9], rcx
0x100834feb  jz      short loc_100834FF6
0x100834fed  inc     eax
0x100834fef  cmp     eax, r10d
0x100834ff2  jnb     short loc_10083500D
0x100834ff4  jmp     short loc_100834FCC
0x100834ff6  inc     ebx
0x100834ff8  add     r8, 4
0x100834ffc  add     r9, 8
0x100835000  cmp     ebx, edi
0x100835002  jb      short loc_100834FC0
0x100835004  mov     bl, 1
0x100835006  jmp     short loc_10083500F
0x100835008  mov     r15d, [rsp+18E0h+var_18A0]
0x10083500d  xor     bl, bl
0x10083500f  test    r15d, r15d
0x100835012  jz      short loc_100835027
0x100835014  mov     edx, r15d
0x100835017  mov     rcx, [rsp+18E0h+var_18A8]
0x10083501c  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x100835022  mov     [rsp+18E0h+var_18A0], r12d
0x100835027  movzx   eax, bl
0x10083502a  mov     rcx, [rbp+17E0h+var_40]
0x100835031  xor     rcx, rsp; StackCookie
0x100835034  call    __security_check_cookie
0x100835039  add     rsp, 18B0h
0x100835040  pop     r15
0x100835042  pop     r14
0x100835044  pop     r12
0x100835046  pop     rdi
0x100835047  pop     rsi
0x100835048  pop     rbx
0x100835049  pop     rbp
0x10083504a  retn
```
