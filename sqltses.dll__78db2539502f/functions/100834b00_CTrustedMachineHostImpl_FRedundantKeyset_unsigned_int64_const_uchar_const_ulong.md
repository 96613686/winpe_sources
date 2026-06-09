# CTrustedMachineHostImpl::FRedundantKeyset(unsigned __int64 const &,uchar const *,ulong)

- ea: `0x100834b00`
- end: `0x100834d94`
- name: `?FRedundantKeyset@CTrustedMachineHostImpl@@QEAA_NAEB_KPEBEK@Z`
- size: `660`
- prototype: `bool __fastcall(CTrustedMachineHostImpl *__hidden this, const unsigned __int64 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x100836670`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x100832710`
- `0x1008348c0`
- `0x100834b00`

## import_xrefs

- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100834d63`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100834d63`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100834ce2`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100834ce2`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100834bb7`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100834bb7`
- `sqldk!SystemThread_TlsIndex` at `0x100834c39`
- `sqldk!SystemThread_TlsOffset` at `0x100834c42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100834c5e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100834c5e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834bdc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834c8c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834bdc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100834c8c`

## string_xrefs

- `0x100834c7c`: `Sql\DkTemp\sos\include\sossync.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTrustedMachineHostImpl::FRedundantKeyset(
        CTrustedMachineHostImpl *this,
        const unsigned __int64 *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v8; // r8
  unsigned int v9; // esi
  int v10; // ecx
  bool v11; // zf
  __int64 v12; // r15
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // ebx
  unsigned int v17; // edi
  unsigned __int64 v18; // r15
  CSessionCEKSet *v19; // r14
  unsigned __int8 v20; // bl
  char v22; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  char *v24; // [rsp+38h] [rbp-C8h]
  int v25; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  _DWORD v37[1536]; // [rsp+A0h] [rbp-60h] BYREF

  v36 = -2;
  v8 = *(_QWORD *)this;
  v9 = 1;
  if ( !*(_QWORD *)this
    || ((v10 = *(_DWORD *)(v8 + 24), ((v10 - 1) & 0xFFFFFFFD) == 0)
      ? (v11 = *(_QWORD *)(v8 + 8) == 0)
      : (v11 = *(_QWORD *)(v8 + 16) == 0),
        v11 || !v10 || !*((_BYTE *)this + 32888)) )
  {
    LODWORD(v26) = 4195793;
    v27 = 0;
    v29 = 0;
    v28 = 0;
    v30 = 0;
    v22 = 1;
    if ( (unsigned int)WaitableBase::Wait((char *)this + 32896, 0xFFFFFFFFLL, &v26, 0, v22) )
      utassert_fail(1u, "SOS_OK == res", "aetmhost.cpp", 1379, 0);
  }
  CTrustedMachineHostImpl::GetAddKeyInfo(this, a2, a3, a4, &v23, (struct CEKInfo *)v37);
  v24 = (char *)this + 32944;
  v25 = 0;
  v31 = 4195885;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  if ( *((_QWORD *)this + 4121) == v13 )
    utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
  v14 = *(_QWORD *)(v13 + 600);
  if ( v14
    && *(_QWORD *)(v14 + 152)
    && (*(_DWORD *)(v14 + 188) & 4) != 0
    && (v15 = *(_QWORD *)(v14 + 152), (*(_BYTE *)(v15 + 616) & 1) == 0)
    && (*(_DWORD *)(v15 + 800) & 0x180) == 0
    || (unsigned int)SOS_RWLock::GetLongWait((char *)this + 32944, 1, 0xFFFFFFFFLL, &v31) )
  {
    v9 = v25;
  }
  else
  {
    v25 = 1;
    v16 = 0;
    v17 = v23;
    if ( !v23 )
    {
LABEL_24:
      v20 = 1;
      goto LABEL_27;
    }
    v18 = *a2;
    v19 = (CSessionCEKSet *)*((_QWORD *)this + 4122);
    while ( 1 )
    {
      v26 = v18;
      v27 = *(_QWORD *)&v37[6 * v16 + 2];
      LODWORD(v28) = v37[6 * v16];
      WORD2(v28) = v37[6 * v16 + 4];
      if ( !CSessionCEKSet::FContains(v19, (const struct SessionCEKInfo *)&v26) )
        break;
      if ( ++v16 >= v17 )
        goto LABEL_24;
    }
  }
  v20 = 0;
LABEL_27:
  if ( v9 )
  {
    SOS_RWLock::ReleaseLock(v24, v9);
    v25 = 0;
  }
  return v20;
}

```

## disassembly

```asm
0x100834b00  push    rbp
0x100834b02  push    rbx
0x100834b03  push    rsi
0x100834b04  push    rdi
0x100834b05  push    r12
0x100834b07  push    r13
0x100834b09  push    r14
0x100834b0b  push    r15
0x100834b0d  lea     rbp, [rsp-17B8h]
0x100834b15  mov     eax, 18B8h
0x100834b1a  call    _alloca_probe
0x100834b1f  sub     rsp, rax
0x100834b22  mov     [rbp+17F0h+var_1858], 0FFFFFFFFFFFFFFFEh
0x100834b2a  mov     rax, cs:__security_cookie
0x100834b31  xor     rax, rsp
0x100834b34  mov     [rbp+17F0h+var_50], rax
0x100834b3b  mov     edi, r9d
0x100834b3e  mov     rbx, r8
0x100834b41  mov     r12, rdx
0x100834b44  mov     r14, rcx
0x100834b47  mov     r8, [rcx]
0x100834b4a  xor     r13d, r13d
0x100834b4d  lea     esi, [r13+1]
0x100834b51  test    r8, r8
0x100834b54  jz      short loc_100834B82
0x100834b56  mov     ecx, [r8+18h]
0x100834b5a  lea     eax, [rcx-1]
0x100834b5d  test    eax, 0FFFFFFFDh
0x100834b62  jz      short loc_100834B6A
0x100834b64  cmp     [r8+10h], r13
0x100834b68  jmp     short loc_100834B6E
0x100834b6a  cmp     [r8+8], r13
0x100834b6e  setnz   al
0x100834b71  test    al, al
0x100834b73  jz      short loc_100834B82
0x100834b75  test    ecx, ecx
0x100834b77  jz      short loc_100834B82
0x100834b79  cmp     [r14+8078h], r13b
0x100834b80  jnz     short loc_100834BE2
0x100834b82  mov     dword ptr [rsp+18F0h+var_18A8], 4005D1h
0x100834b8a  mov     [rsp+18F0h+var_18A0], r13
0x100834b8f  mov     [rsp+18F0h+var_1890], r13
0x100834b94  mov     [rsp+18F0h+var_1898], r13
0x100834b99  mov     [rsp+18F0h+var_1888], r13
0x100834b9e  lea     rcx, [r14+8080h]
0x100834ba5  mov     byte ptr [rsp+18F0h+var_18D0], sil
0x100834baa  xor     r9d, r9d
0x100834bad  lea     r8, [rsp+18F0h+var_18A8]
0x100834bb2  mov     edx, 0FFFFFFFFh
0x100834bb7  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100834bbd  test    eax, eax
0x100834bbf  jz      short loc_100834BE2
0x100834bc1  mov     [rsp+18F0h+var_18D0], r13
0x100834bc6  mov     r9d, 563h
0x100834bcc  lea     r8, aAetmhostCpp; "aetmhost.cpp"
0x100834bd3  lea     rdx, aSosOkRes; "SOS_OK == res"
0x100834bda  mov     ecx, esi
0x100834bdc  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100834be2  lea     rax, [rbp+17F0h+var_1850]
0x100834be6  mov     [rsp+18F0h+var_18C8], rax; struct CEKInfo *
0x100834beb  lea     rax, [rsp+18F0h+var_18C0]
0x100834bf0  mov     [rsp+18F0h+var_18D0], rax; unsigned int *
0x100834bf5  mov     r9d, edi; unsigned int
0x100834bf8  mov     r8, rbx; unsigned __int8 *
0x100834bfb  mov     rdx, r12; unsigned __int64 *
0x100834bfe  mov     rcx, r14; this
0x100834c01  call    ?GetAddKeyInfo@CTrustedMachineHostImpl@@QEAAXAEB_KPEBEKPEAKPEAUCEKInfo@@@Z; CTrustedMachineHostImpl::GetAddKeyInfo(unsigned __int64 const &,uchar const *,ulong,ulong *,CEKInfo *)
0x100834c06  lea     rdi, [r14+80B0h]
0x100834c0d  mov     [rsp+18F0h+var_18B8], rdi
0x100834c12  mov     [rsp+18F0h+var_18B0], r13d
0x100834c17  mov     [rsp+18F0h+var_1880], 40062Dh
0x100834c1f  mov     [rsp+18F0h+var_1878], r13
0x100834c24  mov     [rbp+17F0h+var_1868], r13
0x100834c28  mov     [rbp+17F0h+var_1870], r13
0x100834c2c  mov     [rbp+17F0h+var_1860], r13
0x100834c30  mov     rdx, gs:58h
0x100834c39  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100834c40  mov     ecx, [rax]
0x100834c42  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100834c49  mov     r15d, [rax]
0x100834c4c  add     r15, [rdx+rcx*8]
0x100834c50  mov     rbx, [r15+100h]
0x100834c57  test    rbx, rbx
0x100834c5a  jnz     short loc_100834C6B
0x100834c5c  xor     ecx, ecx
0x100834c5e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100834c64  mov     rbx, [r15+100h]
0x100834c6b  cmp     [rdi+18h], rbx
0x100834c6f  jnz     short loc_100834C92
0x100834c71  mov     [rsp+18F0h+var_18D0], r13
0x100834c76  mov     r9d, 729h
0x100834c7c  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x100834c83  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x100834c8a  mov     ecx, esi
0x100834c8c  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100834c92  mov     rdx, [rbx+258h]
0x100834c99  test    rdx, rdx
0x100834c9c  jz      short loc_100834CD2
0x100834c9e  cmp     qword ptr [rdx+98h], 0
0x100834ca6  jz      short loc_100834CD2
0x100834ca8  mov     eax, [rdx+0BCh]
0x100834cae  test    al, 4
0x100834cb0  jz      short loc_100834CD2
0x100834cb2  mov     rax, [rdx+98h]
0x100834cb9  test    byte ptr [rax+268h], 1
0x100834cc0  jnz     short loc_100834CD2
0x100834cc2  test    dword ptr [rax+320h], 180h
0x100834ccc  jz      loc_100834D52
0x100834cd2  lea     r9, [rsp+18F0h+var_1880]
0x100834cd7  mov     r8d, 0FFFFFFFFh
0x100834cdd  mov     edx, esi
0x100834cdf  mov     rcx, rdi
0x100834ce2  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x100834ce8  test    eax, eax
0x100834cea  jnz     short loc_100834D52
0x100834cec  mov     [rsp+18F0h+var_18B0], esi
0x100834cf0  mov     ebx, r13d
0x100834cf3  mov     edi, [rsp+18F0h+var_18C0]
0x100834cf7  test    edi, edi
0x100834cf9  jz      short loc_100834D4E
0x100834cfb  mov     r15, [r12]
0x100834cff  mov     r14, [r14+80D0h]
0x100834d06  nop     word ptr [rax+rax+00000000h]
0x100834d10  mov     [rsp+18F0h+var_18A8], r15
0x100834d15  mov     eax, ebx
0x100834d17  lea     rcx, [rax+rax*2]
0x100834d1b  mov     rax, [rbp+rcx*8+17F0h+var_1848]
0x100834d20  mov     [rsp+18F0h+var_18A0], rax
0x100834d25  mov     eax, [rbp+rcx*8+17F0h+var_1850]
0x100834d29  mov     dword ptr [rsp+18F0h+var_1898], eax
0x100834d2d  movzx   eax, [rbp+rcx*8+17F0h+var_1840]
0x100834d32  mov     word ptr [rsp+18F0h+var_1898+4], ax
0x100834d37  lea     rdx, [rsp+18F0h+var_18A8]; struct SessionCEKInfo *
0x100834d3c  mov     rcx, r14; this
0x100834d3f  call    ?FContains@CSessionCEKSet@@QEBA_NAEBUSessionCEKInfo@@@Z; CSessionCEKSet::FContains(SessionCEKInfo const &)
0x100834d44  test    al, al
0x100834d46  jz      short loc_100834D56
0x100834d48  inc     ebx
0x100834d4a  cmp     ebx, edi
0x100834d4c  jb      short loc_100834D10
0x100834d4e  mov     bl, 1
0x100834d50  jmp     short loc_100834D58
0x100834d52  mov     esi, [rsp+18F0h+var_18B0]
0x100834d56  xor     bl, bl
0x100834d58  test    esi, esi
0x100834d5a  jz      short loc_100834D6E
0x100834d5c  mov     edx, esi
0x100834d5e  mov     rcx, [rsp+18F0h+var_18B8]
0x100834d63  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x100834d69  mov     [rsp+18F0h+var_18B0], r13d
0x100834d6e  movzx   eax, bl
0x100834d71  mov     rcx, [rbp+17F0h+var_50]
0x100834d78  xor     rcx, rsp; StackCookie
0x100834d7b  call    __security_check_cookie
0x100834d80  add     rsp, 18B8h
0x100834d87  pop     r15
0x100834d89  pop     r14
0x100834d8b  pop     r13
0x100834d8d  pop     r12
0x100834d8f  pop     rdi
0x100834d90  pop     rsi
0x100834d91  pop     rbx
0x100834d92  pop     rbp
0x100834d93  retn
```
