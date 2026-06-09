# OSF_CCONNECTION::OSF_CCONNECTION(OSF_CASSOCIATION *,RPC_CONNECTION_TRANSPORT *,uint,CLIENT_AUTH_INFO *,int,int,OSF_CCALL *,long *)

- ea: `0x180013460`
- end: `0x180013826`
- name: `??0OSF_CCONNECTION@@QEAA@PEAVOSF_CASSOCIATION@@PEAURPC_CONNECTION_TRANSPORT@@IPEAUCLIENT_AUTH_INFO@@HHPEAVOSF_CCALL@@PEAJ@Z`
- size: `966`
- prototype: `OSF_CCONNECTION *__usercall@<rax>(OSF_CCONNECTION *__hidden this@<rcx>, struct OSF_CASSOCIATION *@<rdx>, struct RPC_CONNECTION_TRANSPORT *@<r8>, unsigned int@<r9d>, struct CLIENT_AUTH_INFO *, int, int, struct OSF_CCALL *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013244`

## callees

- `0x18000fd70`
- `0x180013460`
- `0x1800141ec`
- `0x180022e80`
- `0x180023020`
- `0x18002cab0`
- `0x18005ba30`
- `0x18005bed4`
- `0x1800936d8`
- `0x1800970ac`
- `0x1800aef14`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800134d3`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800134d3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800136ca`
- `ntdll!RtlLeaveCriticalSection` at `0x1800136ca`
- `ntdll!RtlEnterCriticalSection` at `0x18001369b`
- `ntdll!RtlEnterCriticalSection` at `0x18001369b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137ab`

## pseudocode

```c
OSF_CCONNECTION *__fastcall OSF_CCONNECTION::OSF_CCONNECTION(
        OSF_CCONNECTION *this,
        struct OSF_CASSOCIATION *a2,
        struct RPC_CONNECTION_TRANSPORT *a3,
        int a4,
        struct CLIENT_AUTH_INFO *a5,
        int a6,
        int a7,
        struct OSF_CCALL *a8,
        int *a9)
{
  __int64 v13; // rcx
  char *v14; // rcx
  OSF_CCALL *v15; // rbx
  __int64 (__fastcall *v16)(char *, _QWORD, _QWORD, _QWORD); // rax
  int v17; // ecx
  int v18; // eax
  CSECURITY_CONTEXT *v19; // rax
  unsigned int v20; // r8d
  int v21; // r9d
  CSECURITY_CONTEXT *v22; // rax
  unsigned int v23; // edx
  CSECURITY_CONTEXT *v24; // rcx
  SIZE_T v25; // rcx
  OSF_CCALL *v26; // rax
  OSF_CCONNECTION *result; // rax
  DWORD CurrentThreadId; // edx
  OSF_CCALL *v29; // rax
  signed __int32 v30[8]; // [rsp+0h] [rbp-78h] BYREF
  int *v31; // [rsp+20h] [rbp-58h]
  int v32; // [rsp+28h] [rbp-50h]
  int v33; // [rsp+30h] [rbp-48h]

  *((_DWORD *)this + 2) = -1985229329;
  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)this = &OSF_CCONNECTION::`vftable';
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = (char *)this + 132;
  *((_DWORD *)this + 33) = 0;
  *((_DWORD *)this + 32) = 1;
  *((_QWORD *)this + 17) = (char *)this + 152;
  *((_QWORD *)this + 18) = 4;
  RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 216), 0);
  SIMPLE_DICT2::SIMPLE_DICT2((OSF_CCONNECTION *)((char *)this + 256));
  *(_DWORD *)(v13 + 88) = 0;
  *((_QWORD *)this + 46) = 4;
  *((_QWORD *)this + 45) = (char *)this + 376;
  *(_OWORD *)((char *)this + 376) = 0;
  v31 = 0;
  *(_OWORD *)((char *)this + 392) = 0;
  LogEvent(0x6Eu, 0x43u, this, 0, (unsigned __int64)v31, v32, v33);
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 28) = *((_DWORD *)this + 28);
  *((_QWORD *)this + 3) = a2;
  REFERENCED_OBJECT::AddReference(a2);
  *((_DWORD *)this + 3) = 128;
  *((_QWORD *)this + 51) = a3;
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 21) = a4;
  v14 = (char *)this + *((unsigned int *)a3 + 15) + 480;
  *((_QWORD *)this + 52) = v14;
  *((_QWORD *)v14 - 1) = this;
  *((_WORD *)this + 24) = 512;
  *((_DWORD *)this + 10) = -1;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 117) = 0;
  if ( a7 )
    *((_DWORD *)this + 28) |= 0x20u;
  v15 = a8;
  if ( a6 )
  {
    *((_DWORD *)this + 28) |= 0x40u;
    if ( !a7 )
    {
      if ( a8 )
        CurrentThreadId = *(_DWORD *)(*((_QWORD *)a8 + 78) + 328LL);
      else
        CurrentThreadId = GetCurrentThreadId();
      OSF_CCONNECTION::AcquireCausalOrder(this, CurrentThreadId);
    }
  }
  *((_DWORD *)this + 27) = 1;
  *((_DWORD *)this + 4) = 2;
  _InterlockedOr(v30, 0);
  *((_QWORD *)this + 54) = 0;
  if ( *a9 )
    goto LABEL_21;
  v16 = *(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 51) + 80LL);
  if ( v16 )
    v17 = v16(
            (char *)this + 472,
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL) + 8LL),
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL) + 24LL),
            *((_DWORD *)this + 28) & 0x40);
  else
    v17 = 0;
  v18 = *((_DWORD *)this + 28) | 8;
  *a9 = v17;
  *((_DWORD *)this + 28) = v18;
  if ( v17 )
    goto LABEL_13;
  v19 = (CSECURITY_CONTEXT *)AllocWrapper(0x138u);
  if ( !v19 )
  {
    *((_QWORD *)this + 44) = 0;
    goto LABEL_24;
  }
  v22 = CSECURITY_CONTEXT::CSECURITY_CONTEXT(v19, a5, v20, v21, a9);
  *((_QWORD *)this + 44) = v22;
  if ( !v22 )
LABEL_24:
    *a9 = 14;
  if ( *a9 )
  {
LABEL_21:
    *((_QWORD *)this + 9) = 0;
LABEL_22:
    v15 = 0;
    goto LABEL_19;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 3) + 184LL));
  *(_DWORD *)(*((_QWORD *)this + 44) + 208LL) = SIMPLE_DICT::Insert(
                                                  (OSF_CCONNECTION *)((char *)this + 360),
                                                  *((void **)this + 44));
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 3) + 184LL));
  v24 = (CSECURITY_CONTEXT *)*((_QWORD *)this + 44);
  if ( *((_DWORD *)v24 + 52) == -1 )
  {
    if ( v24 )
      CSECURITY_CONTEXT::`scalar deleting destructor'(v24, v23);
    *((_QWORD *)this + 44) = 0;
    *a9 = 14;
    goto LABEL_21;
  }
  CSECURITY_CONTEXT::Lock(v24);
LABEL_13:
  if ( *a9 )
    goto LABEL_21;
  if ( a8 )
  {
    *((_QWORD *)this + 9) = a8;
    goto LABEL_19;
  }
  v25 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 51) + 68LL) + 8) + 640LL;
  if ( !gfRPCVerifierEnabled )
  {
    v26 = (OSF_CCALL *)AllocWrapper(v25);
    if ( v26 )
    {
      v15 = OSF_CCALL::OSF_CCALL(v26, a9);
      goto LABEL_18;
    }
    goto LABEL_20;
  }
  v29 = (OSF_CCALL *)AllocWrapper(v25);
  v15 = v29;
  if ( !v29 )
  {
LABEL_20:
    v15 = 0;
    goto LABEL_18;
  }
  OSF_CCALL::OSF_CCALL(v29, a9);
  *(_QWORD *)v15 = &OSF_CCALL_AVRF::`vftable';
LABEL_18:
  *((_QWORD *)this + 9) = v15;
  if ( !v15 )
  {
    *a9 = 14;
    goto LABEL_22;
  }
LABEL_19:
  *((_DWORD *)this + 16) = 0;
  result = this;
  *((_QWORD *)this + 4) = v15;
  *((_DWORD *)this + 116) = 0;
  return result;
}

```

## disassembly

```asm
0x180013460  push    rbx
0x180013462  push    rsi
0x180013463  push    rdi
0x180013464  push    r12
0x180013466  push    r14
0x180013468  push    r15
0x18001346a  sub     rsp, 48h
0x18001346e  mov     dword ptr [rcx+8], 89ABCDEFh
0x180013475  lea     rax, ??_7OSF_CCONNECTION@@6B@; const OSF_CCONNECTION::`vftable'
0x18001347c  mov     dword ptr [rcx+10h], 1
0x180013483  xor     r12d, r12d
0x180013486  mov     [rcx], rax
0x180013489  mov     rbx, rdx
0x18001348c  mov     [rcx+70h], r12d
0x180013490  lea     rax, [rcx+84h]
0x180013497  mov     [rcx+78h], rax
0x18001349b  mov     r14, rcx
0x18001349e  mov     [rax], r12d
0x1800134a1  xor     edx, edx; SpinCount
0x1800134a3  mov     dword ptr [rcx+80h], 1
0x1800134ad  lea     rax, [rcx+98h]
0x1800134b4  mov     [rcx+88h], rax
0x1800134bb  mov     edi, r9d
0x1800134be  mov     qword ptr [rcx+90h], 4
0x1800134c9  mov     rsi, r8
0x1800134cc  add     rcx, 0D8h; CriticalSection
0x1800134d3  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x1800134da  nop     dword ptr [rax+rax+00h]
0x1800134df  lea     rcx, [r14+100h]; this
0x1800134e6  call    ??0SIMPLE_DICT2@@QEAA@XZ; SIMPLE_DICT2::SIMPLE_DICT2(void)
0x1800134eb  mov     [rcx+58h], r12d
0x1800134ef  lea     r15, [r14+168h]
0x1800134f6  lea     rax, [r15+10h]
0x1800134fa  mov     qword ptr [r15+8], 4
0x180013502  xorps   xmm0, xmm0
0x180013505  mov     [r15], rax
0x180013508  movups  xmmword ptr [rax], xmm0
0x18001350b  xor     r9d, r9d; void *
0x18001350e  mov     [rsp+78h+var_58], r12; unsigned __int64
0x180013513  mov     r8, r14; void *
0x180013516  mov     dl, 43h ; 'C'; unsigned __int8
0x180013518  mov     cl, 6Eh ; 'n'; unsigned __int8
0x18001351a  movups  xmmword ptr [rax+10h], xmm0
0x18001351e  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180013523  mov     [r14+70h], r12d
0x180013527  mov     rcx, rbx; this
0x18001352a  mov     eax, [r14+70h]
0x18001352e  mov     [r14+70h], eax
0x180013532  mov     [r14+18h], rbx
0x180013536  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x18001353b  mov     dword ptr [r14+0Ch], 80h
0x180013543  lea     rcx, [r14+1E0h]
0x18001354a  mov     [r14+198h], rsi
0x180013551  mov     [r14+2Ch], r12d
0x180013555  mov     [r14+54h], edi
0x180013559  mov     eax, [rsi+3Ch]
0x18001355c  add     rcx, rax
0x18001355f  mov     [r14+1A0h], rcx
0x180013566  mov     [rcx-8], r14
0x18001356a  mov     ecx, [rsp+78h+arg_30]
0x180013571  mov     word ptr [r14+30h], 200h
0x180013578  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x180013580  mov     [r14+60h], r12
0x180013584  mov     [r14+58h], r12
0x180013588  mov     [r14+50h], r12d
0x18001358c  mov     [r14+44h], r12d
0x180013590  mov     [r14+1C8h], r12
0x180013597  mov     [r14+160h], r12
0x18001359e  mov     [r14+68h], r12d
0x1800135a2  mov     [r14+38h], r12
0x1800135a6  mov     [r14+1D4h], r12d
0x1800135ad  test    ecx, ecx
0x1800135af  jz      short loc_1800135BC
0x1800135b1  mov     eax, [r14+70h]
0x1800135b5  or      eax, 20h
0x1800135b8  mov     [r14+70h], eax
0x1800135bc  mov     rbx, [rsp+78h+arg_38]
0x1800135c4  cmp     [rsp+78h+arg_28], r12d
0x1800135cc  jnz     loc_180013784
0x1800135d2  mov     dword ptr [r14+6Ch], 1
0x1800135da  mov     dword ptr [r14+10h], 2
0x1800135e2  lock or [rsp+78h+var_78], r12d
0x1800135e7  mov     rdi, [rsp+78h+arg_40]
0x1800135ef  mov     [r14+1B0h], r12
0x1800135f6  cmp     [rdi], r12d
0x1800135f9  jnz     loc_180013769
0x1800135ff  mov     rax, [r14+198h]
0x180013606  mov     rax, [rax+50h]
0x18001360a  test    rax, rax
0x18001360d  jz      loc_1800137C6
0x180013613  mov     rcx, [r14+18h]
0x180013617  mov     r9d, [r14+70h]
0x18001361b  and     r9d, 40h
0x18001361f  mov     rdx, [rcx+18h]
0x180013623  lea     rcx, [r14+1D8h]
0x18001362a  mov     r8, [rdx+18h]
0x18001362e  mov     rdx, [rdx+8]
0x180013632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013637  mov     ecx, eax
0x180013639  mov     eax, [r14+70h]
0x18001363d  or      eax, 8
0x180013640  mov     [rdi], ecx
0x180013642  mov     [r14+70h], eax
0x180013646  test    ecx, ecx
0x180013648  jnz     loc_1800136EF
0x18001364e  mov     ecx, 138h; dwBytes
0x180013653  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180013658  test    rax, rax
0x18001365b  jz      loc_180013772
0x180013661  mov     rdx, [rsp+78h+arg_20]; struct CLIENT_AUTH_INFO *
0x180013669  mov     rcx, rax; this
0x18001366c  mov     [rsp+78h+var_58], rdi; int *
0x180013671  call    ??0CSECURITY_CONTEXT@@QEAA@PEAUCLIENT_AUTH_INFO@@IHPEAJ@Z; CSECURITY_CONTEXT::CSECURITY_CONTEXT(CLIENT_AUTH_INFO *,uint,int,long *)
0x180013676  mov     [r14+160h], rax
0x18001367d  test    rax, rax
0x180013680  jz      loc_180013779
0x180013686  cmp     [rdi], r12d
0x180013689  jnz     loc_180013769
0x18001368f  mov     rcx, [r14+18h]
0x180013693  mov     esi, 0B8h
0x180013698  add     rcx, rsi; CriticalSection
0x18001369b  call    cs:__imp_RtlEnterCriticalSection
0x1800136a2  nop     dword ptr [rax+rax+00h]
0x1800136a7  mov     rdx, [r14+160h]; void *
0x1800136ae  mov     rcx, r15; this
0x1800136b1  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x1800136b6  mov     rcx, [r14+160h]
0x1800136bd  mov     [rcx+0D0h], eax
0x1800136c3  mov     rcx, [r14+18h]
0x1800136c7  add     rcx, rsi; CriticalSection
0x1800136ca  call    cs:__imp_RtlLeaveCriticalSection
0x1800136d1  nop     dword ptr [rax+rax+00h]
0x1800136d6  mov     rcx, [r14+160h]; this
0x1800136dd  cmp     dword ptr [rcx+0D0h], 0FFFFFFFFh
0x1800136e4  jz      loc_1800137CE
0x1800136ea  call    ?Lock@CSECURITY_CONTEXT@@QEAAXXZ; CSECURITY_CONTEXT::Lock(void)
0x1800136ef  cmp     [rdi], r12d
0x1800136f2  jnz     short loc_180013769
0x1800136f4  test    rbx, rbx
0x1800136f7  jnz     loc_1800137E7
0x1800136fd  mov     rax, [r14+198h]
0x180013704  mov     ecx, [rax+44h]
0x180013707  add     ecx, 8
0x18001370a  add     rcx, 280h; dwBytes
0x180013711  cmp     cs:?gfRPCVerifierEnabled@@3HA, r12d; int gfRPCVerifierEnabled
0x180013718  jnz     loc_1800137F0
0x18001371e  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180013723  test    rax, rax
0x180013726  jz      short loc_180013764
0x180013728  mov     rdx, rdi; int *
0x18001372b  mov     rcx, rax; this
0x18001372e  call    ??0OSF_CCALL@@AEAA@PEAJ@Z; OSF_CCALL::OSF_CCALL(long *)
0x180013733  mov     rbx, rax
0x180013736  mov     [r14+48h], rbx
0x18001373a  test    rbx, rbx
0x18001373d  jz      loc_18001381B
0x180013743  mov     [r14+40h], r12d
0x180013747  mov     rax, r14
0x18001374a  mov     [r14+20h], rbx
0x18001374e  mov     [r14+1D0h], r12d
0x180013755  add     rsp, 48h
0x180013759  pop     r15
0x18001375b  pop     r14
0x18001375d  pop     r12
0x18001375f  pop     rdi
0x180013760  pop     rsi
0x180013761  pop     rbx
0x180013762  retn
0x180013764  mov     rbx, r12
0x180013767  jmp     short loc_180013736
0x180013769  mov     [r14+48h], r12
0x18001376d  mov     rbx, r12
0x180013770  jmp     short loc_180013743
0x180013772  mov     [r14+160h], r12
0x180013779  mov     dword ptr [rdi], 0Eh
0x18001377f  jmp     loc_180013686
0x180013784  mov     eax, [r14+70h]
0x180013788  or      eax, 40h
0x18001378b  mov     [r14+70h], eax
0x18001378f  test    ecx, ecx
0x180013791  jnz     loc_1800135D2
0x180013797  test    rbx, rbx
0x18001379a  jz      short loc_1800137AB
0x18001379c  mov     rdx, [rbx+270h]
0x1800137a3  mov     edx, [rdx+148h]
0x1800137a9  jmp     short loc_1800137B9
0x1800137ab  call    cs:__imp_GetCurrentThreadId
0x1800137b2  nop     dword ptr [rax+rax+00h]
0x1800137b7  mov     edx, eax; unsigned int
0x1800137b9  mov     rcx, r14; this
0x1800137bc  call    ?AcquireCausalOrder@OSF_CCONNECTION@@QEAAHK@Z; OSF_CCONNECTION::AcquireCausalOrder(ulong)
0x1800137c1  jmp     loc_1800135D2
0x1800137c6  mov     ecx, r12d
0x1800137c9  jmp     loc_180013639
0x1800137ce  test    rcx, rcx
0x1800137d1  jz      short loc_1800137D8
0x1800137d3  call    ??_GCSECURITY_CONTEXT@@QEAAPEAXI@Z; CSECURITY_CONTEXT::`scalar deleting destructor'(uint)
0x1800137d8  mov     [r14+160h], r12
0x1800137df  mov     dword ptr [rdi], 0Eh
0x1800137e5  jmp     short loc_180013769
0x1800137e7  mov     [r14+48h], rbx
0x1800137eb  jmp     loc_180013743
0x1800137f0  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800137f5  mov     rbx, rax
0x1800137f8  test    rax, rax
0x1800137fb  jz      loc_180013764
0x180013801  mov     rdx, rdi; int *
0x180013804  mov     rcx, rax; this
0x180013807  call    ??0OSF_CCALL@@AEAA@PEAJ@Z; OSF_CCALL::OSF_CCALL(long *)
0x18001380c  lea     rax, ??_7OSF_CCALL_AVRF@@6B@; const OSF_CCALL_AVRF::`vftable'
0x180013813  mov     [rbx], rax
0x180013816  jmp     loc_180013736
0x18001381b  mov     dword ptr [rdi], 0Eh
0x180013821  jmp     loc_18001376D
```
