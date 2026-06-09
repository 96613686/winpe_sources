# SmpHandleConnectionRequest

- ea: `0x140001f60`
- end: `0x140002795`
- name: `SmpHandleConnectionRequest`
- size: `2101`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001880`

## callees

- `0x1400010ec`
- `0x1400011b0`
- `0x140001450`
- `0x1400014a0`
- `0x140001e40`
- `0x140001f60`
- `0x1400030f0`
- `0x1400032f0`
- `0x140003390`
- `0x140004ec0`
- `0x140005998`
- `0x140005ac4`
- `0x14000aca0`
- `0x14000d4c0`
- `0x140017f58`
- `0x140018154`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x14000206d`
- `ntdll!NtQueryInformationProcess` at `0x14000206d`
- `ntdll!NtClose` at `0x140002739`
- `ntdll!NtClose` at `0x140002739`
- `ntdll!RtlAllocateHeap` at `0x1400024ea`
- `ntdll!RtlAllocateHeap` at `0x1400024ea`
- `ntdll!RtlFreeHeap` at `0x140002703`
- `ntdll!RtlFreeHeap` at `0x140002703`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400025f8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400025f8`
- `ntdll!NtSetEvent` at `0x1400026a5`
- `ntdll!NtSetEvent` at `0x1400026a5`
- `ntdll!RtlReleaseSRWLockShared` at `0x140002344`
- `ntdll!RtlReleaseSRWLockShared` at `0x140002344`
- `ntdll!RtlAcquireSRWLockShared` at `0x14000211c`
- `ntdll!RtlAcquireSRWLockShared` at `0x14000211c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000223e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000253c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000223e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000253c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140002426`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400025bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400026eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140002426`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400025bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400026eb`
- `ntdll!AlpcGetMessageAttribute` at `0x1400025a7`
- `ntdll!AlpcGetMessageAttribute` at `0x1400025a7`
- `ntdll!NtAlpcOpenSenderProcess` at `0x14000203f`
- `ntdll!NtAlpcOpenSenderProcess` at `0x14000203f`
- `ntdll!RtlInitializeSRWLock` at `0x1400024fc`
- `ntdll!RtlInitializeSRWLock` at `0x1400024fc`
- `ntdll!NtAlpcAcceptConnectPort` at `0x140002587`
- `ntdll!NtAlpcAcceptConnectPort` at `0x140002587`
- `ntdll!NtAlpcConnectPort` at `0x14000266e`
- `ntdll!NtAlpcConnectPort` at `0x14000266e`

## pseudocode

```c
__int64 __fastcall SmpHandleConnectionRequest(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int v4; // r15d
  HANDLE *v5; // r14
  PVOID v6; // rsi
  int v7; // r12d
  char v8; // r13
  HANDLE v9; // rbx
  NTSTATUS v10; // edi
  _QWORD *v11; // rbx
  _QWORD **v12; // rdi
  _QWORD *i; // rax
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // rdi
  _QWORD **v17; // r15
  _QWORD *v18; // rax
  unsigned int v19; // r9d
  _QWORD *v20; // rsi
  __int64 v21; // rcx
  _QWORD *j; // rcx
  _DWORD *v23; // r10
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *k; // rdx
  _QWORD *v27; // rax
  _QWORD *m; // rcx
  __int64 v29; // rcx
  _QWORD *v30; // rdx
  int *v31; // rdi
  char *Heap; // rax
  HANDLE v33; // rax
  __int64 v34; // rax
  int v35; // eax
  _QWORD *v36; // rdi
  const WCHAR *v37; // rdx
  int v38; // eax
  __int64 result; // rax
  char v40; // [rsp+60h] [rbp-A0h]
  PVOID BaseAddress; // [rsp+68h] [rbp-98h]
  _DWORD *BaseAddressa; // [rsp+68h] [rbp-98h]
  unsigned int v43; // [rsp+70h] [rbp-90h]
  HANDLE ProcessHandle; // [rsp+78h] [rbp-88h] BYREF
  unsigned int ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v48; // [rsp+98h] [rbp-68h]
  _QWORD *v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  _DWORD v52[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v56[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v57; // [rsp+E8h] [rbp-18h]
  __int64 v58; // [rsp+F0h] [rbp-10h]
  __int64 v59; // [rsp+F8h] [rbp-8h]
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  __int128 v61; // [rsp+110h] [rbp+10h]
  __m256i v62; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v63[4]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v64; // [rsp+150h] [rbp+50h]
  __int64 v65; // [rsp+158h] [rbp+58h]
  __int128 v66; // [rsp+160h] [rbp+60h]
  __int128 v67; // [rsp+170h] [rbp+70h]
  __int64 v68; // [rsp+180h] [rbp+80h]
  _BYTE v69[200]; // [rsp+190h] [rbp+90h] BYREF
  __int64 ProcessId; // [rsp+258h] [rbp+158h]
  __int64 v71; // [rsp+260h] [rbp+160h]
  __int64 v72; // [rsp+268h] [rbp+168h]

  v4 = 0;
  v50 = a3;
  v58 = a2;
  LODWORD(v48) = 0;
  v47 = 0;
  v40 = 0;
  v5 = 0;
  v59 = a1;
  v51 = a2 + 40;
  v6 = 0;
  v7 = 0;
  v8 = 1;
  v55 = 0;
  memset(&v62, 0, 28);
  ProcessHandle = 0;
  DestinationString = 0;
  v52[1] = 0;
  v61 = 0;
  LODWORD(v54) = 0;
  BaseAddress = 0;
  v49 = (_QWORD *)(a2 + 8);
  if ( *(_QWORD *)(a2 + 8) == SmpUniqueProcessId || a4 )
  {
    v11 = 0;
  }
  else
  {
    LODWORD(v61) = 48;
    *((_QWORD *)&v61 + 1) = 0;
    v62.m256i_i32[2] = 0;
    v62.m256i_i64[0] = 0;
    *(_OWORD *)&v62.m256i_u64[2] = 0;
    if ( (int)NtAlpcOpenSenderProcess(&ProcessHandle, a1, a2) < 0 )
    {
      v11 = 0;
      ProcessHandle = 0;
      v8 = 0;
      goto LABEL_79;
    }
    v9 = ProcessHandle;
    ProcessInformation = 0;
    v10 = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    if ( v10 >= 0 )
    {
      v4 = ProcessInformation;
    }
    else
    {
      memset_0(v69, 0, sizeof(v69));
      v72 = 0;
      ProcessId = SmpGetProcessId(v9);
      v71 = 0;
      SmpInternalLogFailure("SmpGetProcessMuSessionId", 140, (unsigned int)v10, v69);
    }
    v11 = 0;
    v52[0] = 0;
    v53 = 0;
    v43 = v4;
    v46 = *v49;
    v54 = v46;
    v56[0] = 1;
    v12 = (_QWORD **)(24LL * (v4 & 0x1F) + SmpKnownSubSysTable);
    v57 = 24LL * (v4 & 0x1F);
    v56[1] = v12;
    RtlAcquireSRWLockShared(v12 + 2);
    for ( i = *v12; i != v12; i = (_QWORD *)*i )
    {
      if ( *((_DWORD *)i - 2) == v4 )
      {
        if ( *(i - 3) == v46 )
          v11 = i - 9;
        if ( v11 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v11);
          SmpUnlockKnownSubSysList(v56);
LABEL_15:
          v14 = 0;
          goto LABEL_16;
        }
      }
    }
    SmpUnlockKnownSubSysList(v56);
    v15 = SmpLookupControlBlock(v4);
    v5 = (HANDLE *)v15;
    if ( !v15 )
      goto LABEL_15;
    v16 = *(_QWORD *)(v15 + 16);
    if ( *(_QWORD *)(v16 + 8) == *v49 )
    {
      BaseAddressa = (_DWORD *)SmpCreateKnownSubSys(1);
      v48 = (_QWORD *)(SmpKnownSubSysTable + v57);
      v53 = &v47;
      LODWORD(v47) = 0;
      RtlAcquireSRWLockExclusive(SmpKnownSubSysTable + v57 + 16);
      v17 = (_QWORD **)v48;
LABEL_24:
      v18 = *v17;
      v19 = v43;
      while ( v18 != v17 )
      {
        if ( *((_DWORD *)v18 - 2) == v43 )
        {
          v20 = v18 - 9;
          if ( v18 == (_QWORD *)72 )
            break;
          while ( 1 )
          {
            if ( (v20[1] & 1) != 0 )
            {
              if ( !(unsigned int)SmpCheckSubSysStatus(v20) )
              {
                _InterlockedIncrement((volatile signed __int32 *)v20);
                SmpWaitForStatusChange(v21, 0, &v47);
                if ( (v20[1] & 4) != 0 )
                {
                  SmpDereferenceKnownSubSys(v20);
                  goto LABEL_24;
                }
                SmpDereferenceKnownSubSys(v20);
                v19 = v43;
              }
              v18 = (_QWORD *)v20[9];
            }
            else
            {
              v18 = (_QWORD *)*v18;
            }
            if ( v18 != v17 )
            {
              v20 = v18 - 9;
              if ( *((_DWORD *)v18 - 2) == v19 )
                continue;
            }
            goto LABEL_37;
          }
        }
        v18 = (_QWORD *)*v18;
      }
LABEL_37:
      if ( *(_DWORD *)v16 || *(_QWORD *)(v16 + 8) != *v49 )
      {
LABEL_50:
        v6 = BaseAddressa;
      }
      else
      {
        v11 = 0;
        for ( j = (_QWORD *)*v48; j != v48; j = (_QWORD *)*j )
        {
          if ( *((_DWORD *)j - 2) == v19 )
          {
            if ( *(j - 3) == v46 )
              v11 = j - 9;
            if ( v11 )
            {
              _InterlockedIncrement((volatile signed __int32 *)v11);
              v24 = 1023;
LABEL_49:
              SmpLogFailure("SmpHandleConnectionRequest", v24, 0);
              v8 = 0;
              goto LABEL_50;
            }
          }
        }
        v23 = (_DWORD *)v51;
        v52[0] = 1;
        for ( k = (_QWORD *)*v48; k != v48; k = (_QWORD *)*k )
        {
          if ( *((_DWORD *)k - 2) == v19 )
          {
            if ( *((_DWORD *)k - 12) == *(_DWORD *)v51 )
              v11 = k - 9;
            if ( v11 )
            {
              _InterlockedIncrement((volatile signed __int32 *)v11);
              v24 = 1033;
              goto LABEL_49;
            }
          }
        }
        v6 = BaseAddressa;
        if ( BaseAddressa )
        {
          BaseAddressa[16] = v19;
          *((_QWORD *)BaseAddressa + 4) = ProcessHandle;
          BaseAddressa[6] = *v23;
          v27 = v48;
          ProcessHandle = 0;
          ++*BaseAddressa;
          for ( m = (_QWORD *)v27[1]; m != v27; m = (_QWORD *)m[1] )
          {
            if ( *((_DWORD *)m - 2) == BaseAddressa[16] )
              break;
          }
          v29 = *m;
          v30 = *(_QWORD **)(v29 + 8);
          if ( *v30 != v29 )
            __fastfail(3u);
          v11 = BaseAddressa;
          v40 = 1;
          v6 = 0;
          *((_QWORD *)BaseAddressa + 9) = v29;
          *((_QWORD *)BaseAddressa + 10) = v30;
          *v30 = BaseAddressa + 18;
          *(_QWORD *)(v29 + 8) = BaseAddressa + 18;
        }
        else
        {
          SmpLogFailure("SmpHandleConnectionRequest", 1043, 0);
          v8 = 0;
        }
      }
      v25 = v48 + 2;
      if ( (_DWORD)v47 == 1 )
        RtlReleaseSRWLockShared(v25);
      else
        RtlReleaseSRWLockExclusive(v25);
      v14 = v40;
    }
    else
    {
      if ( *(_QWORD *)(v15 + 56) != *v49 )
        goto LABEL_15;
      v7 = 8;
      v14 = 1;
    }
LABEL_16:
    LOBYTE(v4) = 0;
    v40 = v14;
    BaseAddress = v6;
    if ( v11 )
    {
      LOBYTE(v6) = 0;
      if ( !v8 )
      {
        v40 = v14;
        goto LABEL_79;
      }
      if ( (v11[1] & 1) == 0 )
      {
        v52[0] = 1;
        v53 = 0;
        LODWORD(v54) = *(_DWORD *)v51;
        BaseAddress = (PVOID)SmpSearchKnownSubSysDatabase(v43, v52);
        if ( BaseAddress )
        {
          v8 = 0;
          SmpLogFailure("SmpHandleConnectionRequest", 1107, 0);
LABEL_79:
          v31 = 0;
          goto LABEL_90;
        }
      }
      _m_prefetchw(v11 + 1);
      if ( (_InterlockedOr((volatile signed __int32 *)v11 + 2, 2u) & 2) != 0 )
      {
        v8 = 0;
        SmpLogFailure("SmpHandleConnectionRequest", 1127, 0);
        goto LABEL_79;
      }
    }
    else
    {
      BaseAddress = v6;
      LOBYTE(v6) = 0;
      v40 = v14;
      if ( !v8 )
        goto LABEL_79;
    }
  }
  Heap = (char *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag + 0x80000, 0x28u);
  v31 = (int *)Heap;
  if ( Heap )
  {
    RtlInitializeSRWLock(Heap + 24);
    v31[2] = 0;
    if ( v11 )
    {
      *((_QWORD *)v31 + 4) = v11;
      v7 |= 0x10u;
    }
    else
    {
      v33 = ProcessHandle;
      if ( v7 )
        v33 = v5;
      *((_QWORD *)v31 + 4) = v33;
    }
    v34 = v50;
    *v31 = v7;
    *(_DWORD *)(v34 + 4) |= 0x20000000u;
    *((_QWORD *)v31 + 2) = 0;
    RtlAcquireSRWLockExclusive(v31 + 6);
    LOBYTE(v6) = 1;
  }
  else
  {
    v8 = 0;
    if ( v40 )
      LOBYTE(v4) = 1;
  }
LABEL_90:
  v35 = NtAlpcAcceptConnectPort(&v55, v59, 0, 0, 0, v31, v58, v50, v8);
  if ( !v8 )
    goto LABEL_108;
  if ( v35 >= 0 )
  {
    v31[1] = *(_DWORD *)(AlpcGetMessageAttribute(v50, 0x20000000) + 16);
    *((_QWORD *)v31 + 2) = v55;
    RtlReleaseSRWLockExclusive(v31 + 6);
    if ( v11 )
    {
      v46 = 0;
      memset_0(v63, 0, 0x48u);
      v36 = (_QWORD *)v51;
      v37 = (const WCHAR *)(v51 + 4);
      *(_WORD *)(v51 + 242) = 0;
      RtlInitUnicodeStringEx(&DestinationString, v37);
      v63[0] = 0;
      v63[3] = 257;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v63[1] = 12;
      v63[2] = 1;
      v64 = 288;
      v38 = NtAlpcConnectPort(&v46, &DestinationString, 0, v63, 0x20000, 0, 0, 0, 0, 0, 0);
      if ( v38 >= 0 )
        v11[5] = v46;
      else
        SmpLogFailureString("SmpHandleConnectionRequest", 1261, DestinationString.Buffer, (unsigned int)v38);
      if ( v5 )
        NtSetEvent(v5[5], 0);
      if ( (v11[1] & 1) != 0 )
        v36 = v49;
      SmpReadySubSys(v11, v36);
      v11 = 0;
    }
    else if ( (v7 & 8) != 0 )
    {
      v5 = 0;
    }
    else if ( ProcessHandle )
    {
      ProcessHandle = 0;
    }
    goto LABEL_108;
  }
  if ( (_BYTE)v6 )
    RtlReleaseSRWLockExclusive(v31 + 6);
  RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v31);
  if ( !v40 )
  {
LABEL_108:
    if ( !(_BYTE)v4 )
      goto LABEL_112;
  }
  if ( v11 )
    SmpDeleteSubSys(v11);
  SmpDestroyControlBlock(v5);
LABEL_112:
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  if ( v11 )
    SmpDereferenceKnownSubSys(v11);
  result = (__int64)BaseAddress;
  if ( BaseAddress )
    result = SmpDereferenceKnownSubSys(BaseAddress);
  if ( v5 )
    return SmpReleaseControlBlock(v5);
  return result;
}

```

## disassembly

```asm
0x140001f60  mov     [rsp-8+arg_18], rbx
0x140001f65  push    rbp
0x140001f66  push    rsi
0x140001f67  push    rdi
0x140001f68  push    r12
0x140001f6a  push    r13
0x140001f6c  push    r14
0x140001f6e  push    r15
0x140001f70  lea     rbp, [rsp-180h]
0x140001f78  sub     rsp, 280h
0x140001f7f  mov     rax, cs:__security_cookie
0x140001f86  xor     rax, rsp
0x140001f89  mov     [rbp+1B0h+var_40], rax
0x140001f90  xor     r15d, r15d
0x140001f93  mov     [rbp+1B0h+var_208], r8
0x140001f97  xor     eax, eax
0x140001f99  mov     [rbp+1B0h+var_1C0], rdx
0x140001f9d  xorps   xmm0, xmm0
0x140001fa0  mov     qword ptr [rbp+1B0h+var_21C], rax
0x140001fa4  mov     [rbp-70h], rax
0x140001fa8  lea     r8, [rdx+8]
0x140001fac  mov     [rsp+2B0h+var_250], al
0x140001fb0  mov     r14d, r15d
0x140001fb3  lea     rax, [rdx+28h]
0x140001fb7  mov     [rbp+1B0h+var_1B8], rcx
0x140001fbb  mov     [rbp+1B0h+var_200], rax
0x140001fbf  mov     esi, r15d
0x140001fc2  mov     rax, cs:SmpUniqueProcessId
0x140001fc9  mov     r12d, r15d
0x140001fcc  mov     r13b, 1
0x140001fcf  mov     [rbp+1B0h+var_1E0], r15
0x140001fd3  movups  [rbp+1B0h+var_190], xmm0
0x140001fd7  mov     [rsp+2B0h+ProcessHandle], r15
0x140001fdc  movups  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm0
0x140001fe0  mov     [rbp+1B0h+var_1F4], r15d
0x140001fe4  movups  [rbp+1B0h+var_1A0], xmm0
0x140001fe8  mov     dword ptr [rbp+1B0h+var_1E8], r15d
0x140001fec  movups  [rbp+1B0h+var_190+0Ch], xmm0
0x140001ff0  mov     [rsp+2B0h+BaseAddress], r15
0x140001ff5  mov     [rbp+1B0h+var_210], r8
0x140001ff9  cmp     [r8], rax
0x140001ffc  jz      loc_1400024C8
0x140002002  test    r9d, r9d
0x140002005  jnz     loc_1400024C8
0x14000200b  lea     rax, [rbp+1B0h+var_1A0]
0x14000200f  mov     dword ptr [rbp+1B0h+var_1A0], 30h ; '0'
0x140002016  mov     r8, rdx
0x140002019  mov     [rsp+2B0h+var_288], rax
0x14000201e  mov     rdx, rcx
0x140002021  mov     dword ptr [rsp+2B0h+ReturnLength], 100441h
0x140002029  lea     rcx, [rsp+2B0h+ProcessHandle]
0x14000202e  mov     qword ptr [rbp+1B0h+var_1A0+8], r15
0x140002032  mov     dword ptr [rbp+1B0h+var_190+8], r15d
0x140002036  mov     qword ptr [rbp+1B0h+var_190], r15
0x14000203a  movdqu  [rbp+1B0h+var_180], xmm0
0x14000203f  call    cs:__imp_NtAlpcOpenSenderProcess
0x140002045  test    eax, eax
0x140002047  js      loc_1400024B6
0x14000204d  mov     rbx, [rsp+2B0h+ProcessHandle]
0x140002052  lea     r8, [rbp+1B0h+ProcessInformation]; ProcessInformation
0x140002056  mov     rcx, rbx; ProcessHandle
0x140002059  mov     [rbp+1B0h+ProcessInformation], r15d
0x14000205d  mov     r9d, 4; ProcessInformationLength
0x140002063  mov     [rsp+2B0h+ReturnLength], r15; ReturnLength
0x140002068  mov     edx, 18h; ProcessInformationClass
0x14000206d  call    cs:__imp_NtQueryInformationProcess
0x140002073  mov     edi, eax
0x140002075  test    eax, eax
0x140002077  jns     short loc_1400020C9
0x140002079  xor     edx, edx; Val
0x14000207b  lea     rcx, [rbp+1B0h+var_120]; void *
0x140002082  mov     r8d, 0C8h; Size
0x140002088  call    memset_0
0x14000208d  xor     eax, eax
0x14000208f  mov     rcx, rbx
0x140002092  mov     [rbp+1B0h+var_48], rax
0x140002099  call    SmpGetProcessId
0x14000209e  lea     r9, [rbp+1B0h+var_120]
0x1400020a5  mov     [rbp+1B0h+var_58], rax
0x1400020ac  mov     r8d, edi
0x1400020af  mov     [rbp+1B0h+var_50], r15
0x1400020b6  mov     edx, 8Ch
0x1400020bb  lea     rcx, aSmpgetprocessm; "SmpGetProcessMuSessionId"
0x1400020c2  call    SmpInternalLogFailure
0x1400020c7  jmp     short loc_1400020CD
0x1400020c9  mov     r15d, [rbp+1B0h+ProcessInformation]
0x1400020cd  mov     rdi, cs:SmpKnownSubSysTable
0x1400020d4  xor     ecx, ecx
0x1400020d6  mov     rax, [rbp+1B0h+var_210]
0x1400020da  mov     ebx, ecx
0x1400020dc  mov     [rbp+1B0h+var_1F8], ecx
0x1400020df  mov     [rbp+1B0h+var_1F0], rcx
0x1400020e3  mov     [rsp+2B0h+var_240], r15d
0x1400020e8  mov     rax, [rax]
0x1400020eb  mov     [rbp+1B0h+var_228], rax
0x1400020ef  mov     [rbp+1B0h+var_1E8], rax
0x1400020f3  mov     eax, r15d
0x1400020f6  and     eax, 1Fh
0x1400020f9  mov     [rbp+1B0h+var_1D8], 1
0x140002101  lea     rax, [rax+rax*2]
0x140002105  lea     rcx, ds:0[rax*8]
0x14000210d  add     rdi, rcx
0x140002110  mov     [rbp+1B0h+var_1C8], rcx
0x140002114  mov     [rbp+1B0h+var_1D0], rdi
0x140002118  lea     rcx, [rdi+10h]
0x14000211c  call    cs:__imp_RtlAcquireSRWLockShared
0x140002122  mov     rax, [rdi]
0x140002125  cmp     rax, rdi
0x140002128  jz      loc_1400021D6
0x14000212e  cmp     [rax-8], r15d
0x140002132  lea     rcx, [rax-48h]
0x140002136  jnz     short loc_140002149
0x140002138  mov     rdx, [rbp+1B0h+var_228]
0x14000213c  cmp     [rcx+30h], rdx
0x140002140  cmovz   rbx, rcx
0x140002144  test    rbx, rbx
0x140002147  jnz     short loc_14000214E
0x140002149  mov     rax, [rax]
0x14000214c  jmp     short loc_140002125
0x14000214e  lock inc dword ptr [rbx]
0x140002151  lea     rcx, [rbp+1B0h+var_1D8]
0x140002155  call    SmpUnlockKnownSubSysList
0x14000215a  xor     al, al
0x14000215c  xor     r15b, r15b
0x14000215f  mov     [rsp+2B0h+var_250], al
0x140002163  mov     [rsp+2B0h+BaseAddress], rsi
0x140002168  test    rbx, rbx
0x14000216b  jz      loc_1400024A3
0x140002171  xor     sil, sil
0x140002174  test    r13b, r13b
0x140002177  jz      loc_140002493
0x14000217d  test    byte ptr [rbx+8], 1
0x140002181  jnz     loc_14000244F
0x140002187  mov     rax, [rbp+1B0h+var_200]
0x14000218b  lea     rdx, [rbp+1B0h+var_1F8]
0x14000218f  mov     ecx, [rsp+2B0h+var_240]
0x140002193  mov     [rbp+1B0h+var_1F8], 1
0x14000219a  mov     [rbp+1B0h+var_1F0], 0
0x1400021a2  mov     eax, [rax]
0x1400021a4  mov     dword ptr [rbp+1B0h+var_1E8], eax
0x1400021a7  call    SmpSearchKnownSubSysDatabase
0x1400021ac  mov     [rsp+2B0h+BaseAddress], rax
0x1400021b1  test    rax, rax
0x1400021b4  jz      loc_14000244F
0x1400021ba  xor     r13b, r13b
0x1400021bd  lea     rcx, aSmphandleconne; "SmpHandleConnectionRequest"
0x1400021c4  xor     r8d, r8d
0x1400021c7  mov     edx, 453h
0x1400021cc  call    SmpLogFailure
0x1400021d1  jmp     loc_1400024C1
0x1400021d6  lea     rcx, [rbp+1B0h+var_1D8]
0x1400021da  call    SmpUnlockKnownSubSysList
0x1400021df  test    rbx, rbx
0x1400021e2  jnz     loc_14000215A
0x1400021e8  mov     ecx, r15d
0x1400021eb  call    SmpLookupControlBlock
0x1400021f0  mov     r14, rax
0x1400021f3  test    rax, rax
0x1400021f6  jz      loc_14000215A
0x1400021fc  mov     rdi, [rax+10h]
0x140002200  mov     rax, [rbp+1B0h+var_210]
0x140002204  mov     rax, [rax]
0x140002207  cmp     [rdi+8], rax
0x14000220b  jnz     loc_140002436
0x140002211  mov     ecx, 1
0x140002216  call    SmpCreateKnownSubSys
0x14000221b  mov     rcx, [rbp+1B0h+var_1C8]
0x14000221f  add     rcx, cs:SmpKnownSubSysTable
0x140002226  mov     [rsp+2B0h+BaseAddress], rax
0x14000222b  lea     rax, [rbp+1B0h+var_220]
0x14000222f  mov     qword ptr [rbp+1B0h+var_21C+4], rcx
0x140002233  add     rcx, 10h
0x140002237  mov     [rbp+1B0h+var_1F0], rax
0x14000223b  mov     [rbp+1B0h+var_220], esi
0x14000223e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140002244  mov     r15, qword ptr [rbp+1B0h+var_21C+4]
0x140002248  mov     rax, [r15]
0x14000224b  mov     r9d, [rsp+2B0h+var_240]
0x140002250  cmp     rax, r15
0x140002253  jz      short loc_1400022B4
0x140002255  cmp     [rax-8], r9d
0x140002259  jz      short loc_140002260
0x14000225b  mov     rax, [rax]
0x14000225e  jmp     short loc_140002250
0x140002260  lea     rsi, [rax-48h]
0x140002264  test    rsi, rsi
0x140002267  jz      short loc_1400022B4
0x140002269  test    [rsi+8], r13b
0x14000226d  jnz     short loc_140002274
0x14000226f  mov     rax, [rax]
0x140002272  jmp     short loc_1400022A5
0x140002274  mov     rcx, rsi
0x140002277  call    SmpCheckSubSysStatus
0x14000227c  test    eax, eax
0x14000227e  jnz     short loc_1400022A1
0x140002280  lock inc dword ptr [rsi]
0x140002283  lea     r8, [rbp+1B0h+var_220]
0x140002287  xor     edx, edx
0x140002289  call    SmpWaitForStatusChange
0x14000228e  test    byte ptr [rsi+8], 4
0x140002292  mov     rcx, rsi; BaseAddress
0x140002295  jnz     short loc_1400022F4
0x140002297  call    SmpDereferenceKnownSubSys
0x14000229c  mov     r9d, [rsp+2B0h+var_240]
0x1400022a1  mov     rax, [rsi+48h]
0x1400022a5  cmp     rax, r15
0x1400022a8  jz      short loc_1400022B4
0x1400022aa  cmp     [rax-8], r9d
0x1400022ae  lea     rsi, [rax-48h]
0x1400022b2  jz      short loc_140002269
0x1400022b4  cmp     [rdi], r12d
0x1400022b7  jnz     short loc_14000232D
0x1400022b9  mov     rax, [rbp+1B0h+var_210]
0x1400022bd  mov     rax, [rax]
0x1400022c0  cmp     [rdi+8], rax
0x1400022c4  jnz     short loc_14000232D
0x1400022c6  mov     rax, qword ptr [rbp+1B0h+var_21C+4]
0x1400022ca  xor     ebx, ebx
0x1400022cc  mov     r8, [rbp+1B0h+var_228]
0x1400022d0  mov     rcx, [rax]
0x1400022d3  cmp     rcx, rax
0x1400022d6  jz      short loc_140002303
0x1400022d8  cmp     [rcx-8], r9d
0x1400022dc  lea     rdx, [rcx-48h]
0x1400022e0  jnz     short loc_1400022EF
0x1400022e2  cmp     [rdx+30h], r8
0x1400022e6  cmovz   rbx, rdx
0x1400022ea  test    rbx, rbx
0x1400022ed  jnz     short loc_1400022FE
0x1400022ef  mov     rcx, [rcx]
0x1400022f2  jmp     short loc_1400022D3
0x1400022f4  call    SmpDereferenceKnownSubSys
0x1400022f9  jmp     loc_140002248
0x1400022fe  lock inc dword ptr [rbx]
0x140002301  jmp     short loc_140002316
0x140002303  mov     r10, [rbp+1B0h+var_200]
0x140002307  mov     [rbp+1B0h+var_1F8], 1
0x14000230e  mov     r8d, [r10]
0x140002311  test    rbx, rbx
0x140002314  jz      short loc_140002354
0x140002316  xor     r8d, r8d
0x140002319  mov     edx, 3FFh
0x14000231e  lea     rcx, aSmphandleconne; "SmpHandleConnectionRequest"
0x140002325  call    SmpLogFailure
0x14000232a  xor     r13b, r13b
0x14000232d  mov     rsi, [rsp+2B0h+BaseAddress]
0x140002332  mov     rcx, qword ptr [rbp+1B0h+var_21C+4]
0x140002336  add     rcx, 10h
0x14000233a  cmp     [rbp+1B0h+var_220], 1
0x14000233e  jnz     loc_140002426
0x140002344  call    cs:__imp_RtlReleaseSRWLockShared
0x14000234a  movzx   eax, [rsp+2B0h+var_250]
0x14000234f  jmp     loc_14000215C
0x140002354  mov     rdx, [rax]
0x140002357  cmp     rdx, rax
0x14000235a  jz      short loc_140002385
0x14000235c  cmp     [rdx-8], r9d
0x140002360  lea     rcx, [rdx-48h]
0x140002364  jnz     short loc_140002373
0x140002366  cmp     [rcx+18h], r8d
0x14000236a  cmovz   rbx, rcx
0x14000236e  test    rbx, rbx
0x140002371  jnz     short loc_140002378
0x140002373  mov     rdx, [rdx]
0x140002376  jmp     short loc_140002357
0x140002378  lock inc dword ptr [rbx]
0x14000237b  xor     r8d, r8d
0x14000237e  mov     edx, 409h
0x140002383  jmp     short loc_14000231E
0x140002385  test    rbx, rbx
0x140002388  jz      short loc_140002394
0x14000238a  xor     r8d, r8d
0x14000238d  mov     edx, 409h
0x140002392  jmp     short loc_14000231E
0x140002394  mov     rsi, [rsp+2B0h+BaseAddress]
0x140002399  test    rsi, rsi
0x14000239c  jnz     short loc_1400023BA
0x14000239e  xor     r8d, r8d
0x1400023a1  lea     rcx, aSmphandleconne; "SmpHandleConnectionRequest"
0x1400023a8  mov     edx, 413h
0x1400023ad  call    SmpLogFailure
0x1400023b2  xor     r13b, r13b
0x1400023b5  jmp     loc_140002332
0x1400023ba  mov     [rsi+40h], r9d
0x1400023be  mov     rax, [rsp+2B0h+ProcessHandle]
0x1400023c3  mov     [rsi+20h], rax
0x1400023c7  mov     eax, [r10]
0x1400023ca  mov     [rsi+18h], eax
0x1400023cd  mov     rax, qword ptr [rbp+1B0h+var_21C+4]
0x1400023d1  mov     [rsp+2B0h+ProcessHandle], r12
0x1400023d6  inc     dword ptr [rsi]
0x1400023d8  mov     rcx, [rax+8]
0x1400023dc  cmp     rcx, rax
0x1400023df  jz      short loc_1400023F2
0x1400023e1  mov     edx, [rsi+40h]
0x1400023e4  cmp     [rcx-8], edx
0x1400023e7  jz      short loc_1400023F2
0x1400023e9  mov     rcx, [rcx+8]
0x1400023ed  cmp     rcx, rax
0x1400023f0  jnz     short loc_1400023E4
  ... truncated ...
```
