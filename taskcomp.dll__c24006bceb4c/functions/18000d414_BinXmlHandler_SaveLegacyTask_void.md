# BinXmlHandler::SaveLegacyTask(void)

- ea: `0x18000d414`
- end: `0x18000d8d3`
- name: `?SaveLegacyTask@BinXmlHandler@@QEAAJXZ`
- size: `1215`
- prototype: `__int64 __fastcall(BinXmlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011f40`

## callees

- `0x180001e40`
- `0x180003060`
- `0x1800045e0`
- `0x1800058f0`
- `0x180005f7c`
- `0x1800074c8`
- `0x1800074d4`
- `0x180009afc`
- `0x180009cd4`
- `0x18000cd58`
- `0x18000d414`
- `0x1800143b4`
- `0x180015220`
- `0x180023794`
- `0x180025090`
- `0x18002e572`
- `0x18002e5b0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d52a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d52a`
- `RPCRT4!RpcRevertToSelf` at `0x18000d833`
- `RPCRT4!RpcRevertToSelf` at `0x18000d833`

## string_xrefs

- `0x18000d7a2`: `BinXmlHandler::ProcessElementEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BinXmlHandler::SaveLegacyTask(BinXmlHandler *this)
{
  __int64 result; // rax
  struct CompatibilityAdapter *Adapter; // rbx
  __int64 v4; // r9
  int v5; // esi
  __int64 v6; // rbx
  __int64 v7; // r9
  unsigned int *v8; // rcx
  unsigned int v9; // edx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rax
  unsigned int v13; // eax
  JobBucket *v14; // rcx
  unsigned int ExecutionTimeLimit; // eax
  JobBucket *v16; // rcx
  __int64 v17; // r8
  __int64 (__fastcall *v18)(__int64, __int64); // r9
  int v19; // edx
  __int64 v20; // rdx
  int v21; // ebx
  tsched *v22; // rax
  unsigned __int16 *v23; // rdx
  WCHAR *v24; // rbx
  int v25; // r8d
  unsigned int v26; // edx
  int v27; // eax
  bool v28; // zf
  WCHAR *v29; // rcx
  CJob *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // r8d
  const unsigned __int16 *v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-C8h] BYREF
  struct _RTL_CRITICAL_SECTION *v36; // [rsp+40h] [rbp-C0h]
  _AT_INFO v37; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+60h] [rbp-A0h]
  __m128i si128; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v40[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( *((_DWORD *)this + 135) == 0x10000 )
  {
    *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 2u;
    *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x200000u;
    v35 = 260;
    memset(&v37, 0, sizeof(v37));
    result = CJob::GetAtInfo(*((CJob **)this + 64), &v37, v40, &v35);
    if ( (int)result < 0 )
      return result;
    v37.Command = v40;
    Adapter = CompatibilityAdapter::GetAdapter();
    if ( !Adapter )
      return 2147549183LL;
    v36 = &gcsNetScheduleCritSection;
    EnterCriticalSection(&gcsNetScheduleCritSection);
    LODWORD(v34) = 0;
    LOBYTE(v4) = 1;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _AT_INFO *, __int64 *, __int64))(**((_QWORD **)Adapter + 1) + 104LL))(
           *((_QWORD *)Adapter + 1),
           &v37,
           &v34,
           v4);
    if ( v5 >= 0 )
      StringCchPrintfW(*((unsigned __int16 **)this + 66), 0x105u, L"At%d", (unsigned int)v34);
    LeaveCriticalSection(&gcsNetScheduleCritSection);
    return (unsigned int)v5;
  }
  v6 = *((_QWORD *)this + 5);
  v34 = v6;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = *((_QWORD *)this + 64);
  v8 = *(unsigned int **)(v6 + 208);
  if ( v8 )
    v9 = v8[1];
  else
    v9 = -1;
  v10 = v9 / 0x3C;
  if ( v8 )
    v11 = *v8;
  else
    v11 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 80LL))(v7, v11 / 0x3C, v10);
  if ( v5 >= 0 )
  {
    if ( (*(_DWORD *)(v6 + 16) & 0x400000) == 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 4u;
    if ( (*(_DWORD *)(v6 + 16) & 0x800000) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x200u;
    if ( (*(_DWORD *)(v6 + 16) & 0x10000) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x2000u;
    if ( (*(_DWORD *)(v6 + 16) & 2) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x10u;
    if ( (*(_DWORD *)(v6 + 16) & 0x200) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x1000u;
    if ( (*(_DWORD *)(v6 + 16) & 8) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x20u;
    if ( (*(_DWORD *)(v6 + 16) & 4) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x800u;
    if ( (*(_DWORD *)(v6 + 16) & 0x10) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x40u;
    if ( (*(_BYTE *)(v6 + 16) & 0x20) != 0 )
      *(_DWORD *)(*((_QWORD *)this + 64) + 88LL) |= 0x80u;
    v37.JobTime = 0x8000000100LL;
    v37.DaysOfMonth = 128;
    *(_DWORD *)&v37.DaysOfWeek = 128;
    v37.Command = (LPWSTR)0x2000000020LL;
    v38 = 32;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v12 = *(_QWORD *)(v6 + 208);
    v13 = v12 ? *(_DWORD *)(v12 + 16) : 7;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 64) + 304LL))(
           *((_QWORD *)this + 64),
           *((unsigned int *)&v37.JobTime + v13));
    if ( v5 >= 0 )
    {
      if ( JobBucket::GetExecutionTimeLimit((JobBucket *)v6) )
      {
        JobBucket::GetExecutionTimeLimit(v14);
        ExecutionTimeLimit = JobBucket::GetExecutionTimeLimit((JobBucket *)v6);
        v20 = v19 == ExecutionTimeLimit ? 1000 * JobBucket::GetExecutionTimeLimit(v16) : 0xFFFFFFFFLL;
        v21 = v18(v17, v20);
        if ( v21 < 0 )
        {
          wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v34);
          return (unsigned int)v21;
        }
      }
      memset_0(v40, 0, 0x20Au);
      v5 = UriToFilename(*((wchar_t **)this + 65), v40);
      if ( v5 >= 0 )
      {
        v22 = (tsched *)operator new[](0x20Au);
        v24 = (WCHAR *)v22;
        v36 = (struct _RTL_CRITICAL_SECTION *)v22;
        if ( !v22 )
        {
          operator delete(0);
          v5 = -2147024882;
          goto LABEL_65;
        }
        v5 = tsched::SafePathAppend(v22, v23, (unsigned int)g_TasksFolderInfo, v40, v33);
        if ( v5 < 0 )
          goto LABEL_64;
        RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v35, L"BinXmlHandler::ProcessElementEnd", v25);
        v27 = *((_DWORD *)this + 134);
        if ( (v27 & 2) != 0 )
        {
          v5 = CJob::SaveWithRetry(*((CJob **)this + 64), v24, 1, 1u);
          if ( v5 != -2147024816 )
          {
LABEL_55:
            if ( v35 )
              RpcRevertToSelf();
            if ( v5 < 0 )
              goto LABEL_64;
            v5 = CJob::Sign(*((CJob **)this + 64), v26);
            if ( v5 < 0 )
              goto LABEL_64;
            v30 = (CJob *)*((_QWORD *)this + 64);
            if ( *((_QWORD *)v30 + 26) )
            {
              v5 = CJob::Fingerprint(v30);
              if ( v5 < 0 )
                goto LABEL_64;
              v31 = *((_QWORD *)this + 64);
              v32 = *(_DWORD *)(v31 + 216);
              if ( v32 )
              {
                v5 = SignatureStore::Save(v40, *(BYTE **)(v31 + 208), v32);
                goto LABEL_64;
              }
            }
            v5 = -2147418113;
LABEL_64:
            operator delete(v24);
            goto LABEL_65;
          }
          v28 = (*((_BYTE *)this + 536) & 4) == 0;
        }
        else
        {
          v28 = (v27 & 4) == 0;
        }
        if ( !v28 )
        {
          *(_DWORD *)(*((_QWORD *)this + 64) + 160LL) = 1;
          v29 = v24;
          v24 = 0;
          *(_QWORD *)(*((_QWORD *)this + 64) + 152LL) = v29;
          v36 = 0;
          v5 = CJob::SaveWithRetry(*((CJob **)this + 64), 0, 0, 1u);
        }
        goto LABEL_55;
      }
    }
  }
LABEL_65:
  wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d414  mov     [rsp-8+arg_8], rbx
0x18000d419  mov     [rsp-8+arg_10], rsi
0x18000d41e  push    rbp
0x18000d41f  push    rdi
0x18000d420  push    r15
0x18000d422  lea     rbp, [rsp-1A0h]
0x18000d42a  sub     rsp, 2A0h
0x18000d431  mov     rax, cs:__security_cookie
0x18000d438  xor     rax, rsp
0x18000d43b  mov     [rbp+1B0h+var_20], rax
0x18000d442  mov     rdi, rcx
0x18000d445  mov     r15d, 10000h
0x18000d44b  cmp     [rcx+21Ch], r15d
0x18000d452  jnz     loc_18000D535
0x18000d458  mov     rax, [rcx+200h]
0x18000d45f  or      dword ptr [rax+58h], 2
0x18000d463  mov     rax, [rcx+200h]
0x18000d46a  bts     dword ptr [rax+58h], 15h
0x18000d46f  mov     [rsp+2B0h+var_278], 104h
0x18000d477  xorps   xmm0, xmm0
0x18000d47a  xor     eax, eax
0x18000d47c  movups  xmmword ptr [rsp+2B0h+var_268.JobTime], xmm0
0x18000d481  mov     [rsp+2B0h+var_268.Command], rax
0x18000d486  lea     r9, [rsp+2B0h+var_278]; unsigned int *
0x18000d48b  lea     r8, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000d48f  lea     rdx, [rsp+2B0h+var_268]; struct _AT_INFO *
0x18000d494  mov     rcx, [rcx+200h]; this
0x18000d49b  call    ?GetAtInfo@CJob@@QEAAJPEAU_AT_INFO@@PEAGPEAK@Z; CJob::GetAtInfo(_AT_INFO *,ushort *,ulong *)
0x18000d4a0  test    eax, eax
0x18000d4a2  js      loc_18000D8AC
0x18000d4a8  lea     rax, [rbp+1B0h+var_230]
0x18000d4ac  mov     [rsp+2B0h+var_268.Command], rax
0x18000d4b1  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18000d4b6  mov     rbx, rax
0x18000d4b9  test    rax, rax
0x18000d4bc  jnz     short loc_18000D4C8
0x18000d4be  mov     eax, 8000FFFFh
0x18000d4c3  jmp     loc_18000D8AC
0x18000d4c8  lea     r15, ?gcsNetScheduleCritSection@@3VCStaticCritSec@@A; CStaticCritSec gcsNetScheduleCritSection
0x18000d4cf  mov     [rsp+2B0h+var_270], r15
0x18000d4d4  mov     rcx, r15; lpCriticalSection
0x18000d4d7  call    cs:__imp_EnterCriticalSection
0x18000d4dd  nop
0x18000d4de  mov     dword ptr [rsp+2B0h+var_280], 0
0x18000d4e6  mov     rcx, [rbx+8]
0x18000d4ea  mov     rax, [rcx]
0x18000d4ed  mov     r9b, 1
0x18000d4f0  lea     r8, [rsp+2B0h+var_280]
0x18000d4f5  lea     rdx, [rsp+2B0h+var_268]
0x18000d4fa  mov     rax, [rax+68h]
0x18000d4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d503  mov     esi, eax
0x18000d505  test    eax, eax
0x18000d507  js      short loc_18000D527
0x18000d509  mov     r9d, dword ptr [rsp+2B0h+var_280]
0x18000d50e  lea     r8, aAtD; "At%d"
0x18000d515  mov     edx, 105h; unsigned __int64
0x18000d51a  mov     rcx, [rdi+210h]; unsigned __int16 *
0x18000d521  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d526  nop
0x18000d527  mov     rcx, r15; lpCriticalSection
0x18000d52a  call    cs:__imp_LeaveCriticalSection
0x18000d530  jmp     loc_18000D8AA
0x18000d535  mov     rbx, [rcx+28h]
0x18000d539  mov     [rsp+2B0h+var_280], rbx
0x18000d53e  test    rbx, rbx
0x18000d541  jz      short loc_18000D547
0x18000d543  lock inc dword ptr [rbx+8]
0x18000d547  mov     r9, [rcx+200h]
0x18000d54e  mov     rax, [r9]
0x18000d551  mov     r10, [rax+50h]
0x18000d555  mov     rcx, [rbx+0D0h]
0x18000d55c  test    rcx, rcx
0x18000d55f  jz      short loc_18000D566
0x18000d561  mov     edx, [rcx+4]
0x18000d564  jmp     short loc_18000D569
0x18000d566  or      edx, 0FFFFFFFFh
0x18000d569  mov     r11d, 88888889h
0x18000d56f  mov     eax, r11d
0x18000d572  mul     edx
0x18000d574  mov     r8d, edx
0x18000d577  shr     r8d, 5
0x18000d57b  test    rcx, rcx
0x18000d57e  jz      short loc_18000D584
0x18000d580  mov     edx, [rcx]
0x18000d582  jmp     short loc_18000D586
0x18000d584  xor     edx, edx
0x18000d586  mov     eax, r11d
0x18000d589  mul     edx
0x18000d58b  shr     edx, 5
0x18000d58e  mov     rcx, r9
0x18000d591  mov     rax, r10
0x18000d594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d599  mov     esi, eax
0x18000d59b  test    eax, eax
0x18000d59d  js      loc_18000D8A0
0x18000d5a3  test    dword ptr [rbx+10h], 400000h
0x18000d5aa  jnz     short loc_18000D5B7
0x18000d5ac  mov     rax, [rdi+200h]
0x18000d5b3  or      dword ptr [rax+58h], 4
0x18000d5b7  mov     ecx, 200h
0x18000d5bc  test    dword ptr [rbx+10h], 800000h
0x18000d5c3  jz      short loc_18000D5CF
0x18000d5c5  mov     rax, [rdi+200h]
0x18000d5cc  or      [rax+58h], ecx
0x18000d5cf  test    [rbx+10h], r15d
0x18000d5d3  jz      short loc_18000D5E1
0x18000d5d5  mov     rax, [rdi+200h]
0x18000d5dc  bts     dword ptr [rax+58h], 0Dh
0x18000d5e1  mov     eax, [rbx+10h]
0x18000d5e4  test    al, 2
0x18000d5e6  jz      short loc_18000D5F3
0x18000d5e8  mov     rax, [rdi+200h]
0x18000d5ef  or      dword ptr [rax+58h], 10h
0x18000d5f3  test    [rbx+10h], ecx
0x18000d5f6  jz      short loc_18000D604
0x18000d5f8  mov     rax, [rdi+200h]
0x18000d5ff  bts     dword ptr [rax+58h], 0Ch
0x18000d604  mov     eax, [rbx+10h]
0x18000d607  mov     ecx, 20h ; ' '
0x18000d60c  test    al, 8
0x18000d60e  jz      short loc_18000D61A
0x18000d610  mov     rax, [rdi+200h]
0x18000d617  or      [rax+58h], ecx
0x18000d61a  mov     eax, [rbx+10h]
0x18000d61d  test    al, 4
0x18000d61f  jz      short loc_18000D62D
0x18000d621  mov     rax, [rdi+200h]
0x18000d628  bts     dword ptr [rax+58h], 0Bh
0x18000d62d  mov     eax, [rbx+10h]
0x18000d630  test    al, 10h
0x18000d632  jz      short loc_18000D63F
0x18000d634  mov     rax, [rdi+200h]
0x18000d63b  or      dword ptr [rax+58h], 40h
0x18000d63f  mov     eax, [rbx+10h]
0x18000d642  and     eax, ecx
0x18000d644  mov     edx, 80h
0x18000d649  test    al, al
0x18000d64b  jz      short loc_18000D657
0x18000d64d  mov     rax, [rdi+200h]
0x18000d654  or      [rax+58h], edx
0x18000d657  mov     dword ptr [rsp+2B0h+var_268.JobTime], 100h
0x18000d65f  mov     dword ptr [rsp+2B0h+var_268.JobTime+4], edx
0x18000d663  mov     [rsp+2B0h+var_268.DaysOfMonth], edx
0x18000d667  mov     dword ptr [rsp+2B0h+var_268.DaysOfWeek], edx
0x18000d66b  mov     dword ptr [rsp+2B0h+var_268.Command], ecx
0x18000d66f  mov     dword ptr [rsp+2B0h+var_268.Command+4], ecx
0x18000d673  mov     [rsp+2B0h+var_250], ecx
0x18000d677  movdqa  xmm0, cs:__xmm@00000040000000400000004000000040
0x18000d67f  movups  [rsp+2B0h+var_24C], xmm0
0x18000d684  mov     rcx, [rdi+200h]
0x18000d68b  mov     rax, [rcx]
0x18000d68e  mov     r8, [rax+130h]
0x18000d695  mov     rax, [rbx+0D0h]
0x18000d69c  test    rax, rax
0x18000d69f  jz      short loc_18000D6A6
0x18000d6a1  mov     eax, [rax+10h]
0x18000d6a4  jmp     short loc_18000D6AB
0x18000d6a6  mov     eax, 7
0x18000d6ab  mov     edx, eax
0x18000d6ad  mov     edx, dword ptr [rsp+rdx*4+2B0h+var_268.JobTime]
0x18000d6b1  mov     rax, r8
0x18000d6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b9  mov     esi, eax
0x18000d6bb  test    eax, eax
0x18000d6bd  js      loc_18000D8A0
0x18000d6c3  mov     rcx, rbx; this
0x18000d6c6  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000d6cb  test    eax, eax
0x18000d6cd  jz      short loc_18000D733
0x18000d6cf  mov     r8, [rdi+200h]
0x18000d6d6  mov     rax, [r8]
0x18000d6d9  mov     r9, [rax+150h]
0x18000d6e0  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000d6e5  imul    ecx, eax, 3E8h
0x18000d6eb  mov     eax, 10624DD3h
0x18000d6f0  mul     ecx
0x18000d6f2  shr     edx, 6
0x18000d6f5  mov     rcx, rbx; this
0x18000d6f8  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000d6fd  cmp     edx, eax
0x18000d6ff  jnz     short loc_18000D70E
0x18000d701  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000d706  imul    edx, eax, 3E8h
0x18000d70c  jmp     short loc_18000D711
0x18000d70e  or      edx, 0FFFFFFFFh
0x18000d711  mov     rcx, r8
0x18000d714  mov     rax, r9
0x18000d717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d71c  mov     ebx, eax
0x18000d71e  test    eax, eax
0x18000d720  jns     short loc_18000D733
0x18000d722  lea     rcx, [rsp+2B0h+var_280]
0x18000d727  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x18000d72c  mov     eax, ebx
0x18000d72e  jmp     loc_18000D8AC
0x18000d733  mov     ebx, 20Ah
0x18000d738  mov     r8d, ebx; Size
0x18000d73b  xor     edx, edx; Val
0x18000d73d  lea     rcx, [rbp+1B0h+var_230]; void *
0x18000d741  call    memset_0
0x18000d746  lea     rdx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000d74a  mov     rcx, [rdi+208h]; Str
0x18000d751  call    ?UriToFilename@@YAJPEBGPEAG@Z; UriToFilename(ushort const *,ushort *)
0x18000d756  mov     esi, eax
0x18000d758  test    eax, eax
0x18000d75a  js      loc_18000D8A0
0x18000d760  mov     ecx, ebx; unsigned __int64
0x18000d762  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d767  mov     rbx, rax
0x18000d76a  mov     [rsp+2B0h+var_270], rax
0x18000d76f  test    rax, rax
0x18000d772  jnz     short loc_18000D785
0x18000d774  xor     ecx, ecx; Block
0x18000d776  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d77b  mov     esi, 8007000Eh
0x18000d780  jmp     loc_18000D8A0
0x18000d785  lea     r9, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000d789  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned int
0x18000d790  mov     rcx, rbx; this
0x18000d793  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18000d798  mov     esi, eax
0x18000d79a  test    eax, eax
0x18000d79c  js      loc_18000D897
0x18000d7a2  lea     rdx, aBinxmlhandlerP; "BinXmlHandler::ProcessElementEnd"
0x18000d7a9  lea     rcx, [rsp+2B0h+var_278]; this
0x18000d7ae  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18000d7b3  nop
0x18000d7b4  mov     eax, [rdi+218h]
0x18000d7ba  test    al, 2
0x18000d7bc  jz      short loc_18000D7E8
0x18000d7be  mov     r9d, 1; unsigned int
0x18000d7c4  mov     r8d, r9d; int
0x18000d7c7  mov     rdx, rbx; lpFileName
0x18000d7ca  mov     rcx, [rdi+200h]; this
0x18000d7d1  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x18000d7d6  mov     esi, eax
0x18000d7d8  cmp     eax, 80070050h
0x18000d7dd  jnz     short loc_18000D82C
0x18000d7df  test    byte ptr [rdi+218h], 4
0x18000d7e6  jmp     short loc_18000D7EA
0x18000d7e8  test    al, 4
0x18000d7ea  jz      short loc_18000D82C
0x18000d7ec  mov     rax, [rdi+200h]
0x18000d7f3  mov     dword ptr [rax+0A0h], 1
0x18000d7fd  mov     rcx, rbx
0x18000d800  mov     rax, [rdi+200h]
0x18000d807  xor     ebx, ebx
0x18000d809  mov     [rax+98h], rcx
0x18000d810  mov     [rsp+2B0h+var_270], rbx
0x18000d815  lea     r9d, [rbx+1]; unsigned int
0x18000d819  xor     r8d, r8d; int
0x18000d81c  xor     edx, edx; lpFileName
0x18000d81e  mov     rcx, [rdi+200h]; this
0x18000d825  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x18000d82a  mov     esi, eax
0x18000d82c  cmp     [rsp+2B0h+var_278], 0
0x18000d831  jz      short loc_18000D839
0x18000d833  call    cs:__imp_RpcRevertToSelf
0x18000d839  test    esi, esi
0x18000d83b  js      short loc_18000D897
0x18000d83d  mov     rcx, [rdi+200h]; this
0x18000d844  call    ?Sign@CJob@@QEAAJK@Z; CJob::Sign(ulong)
0x18000d849  mov     esi, eax
0x18000d84b  test    eax, eax
0x18000d84d  js      short loc_18000D897
0x18000d84f  mov     rcx, [rdi+200h]; this
0x18000d856  cmp     qword ptr [rcx+0D0h], 0
0x18000d85e  jnz     short loc_18000D867
0x18000d860  mov     esi, 8000FFFFh
0x18000d865  jmp     short loc_18000D897
0x18000d867  call    ?Fingerprint@CJob@@QEAAJXZ; CJob::Fingerprint(void)
0x18000d86c  mov     esi, eax
0x18000d86e  test    eax, eax
0x18000d870  js      short loc_18000D897
0x18000d872  mov     rdx, [rdi+200h]
0x18000d879  mov     r8d, [rdx+0D8h]; unsigned int
0x18000d880  test    r8d, r8d
0x18000d883  jz      short loc_18000D860
0x18000d885  mov     rdx, [rdx+0D0h]; lpData
0x18000d88c  lea     rcx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000d890  call    ?Save@SignatureStore@@SAJPEBGPEAEK@Z; SignatureStore::Save(ushort const *,uchar *,ulong)
0x18000d895  mov     esi, eax
0x18000d897  mov     rcx, rbx; Block
0x18000d89a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d89f  nop
0x18000d8a0  lea     rcx, [rsp+2B0h+var_280]
0x18000d8a5  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x18000d8aa  mov     eax, esi
0x18000d8ac  mov     rcx, [rbp+1B0h+var_20]
0x18000d8b3  xor     rcx, rsp; StackCookie
0x18000d8b6  call    __security_check_cookie
0x18000d8bb  lea     r11, [rsp+2B0h+var_10]
0x18000d8c3  mov     rbx, [r11+28h]
0x18000d8c7  mov     rsi, [r11+30h]
0x18000d8cb  mov     rsp, r11
0x18000d8ce  pop     r15
0x18000d8d0  pop     rdi
0x18000d8d1  pop     rbp
0x18000d8d2  retn
  ... truncated ...
```
