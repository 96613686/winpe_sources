# BinXmlHandler::SaveLegacyTask(void)

- ea: `0x18000dca8`
- end: `0x18000e16c`
- name: `?SaveLegacyTask@BinXmlHandler@@QEAAJXZ`
- size: `1220`
- prototype: `__int64 __fastcall(BinXmlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012a70`

## callees

- `0x180001ee0`
- `0x1800031d0`
- `0x1800047f0`
- `0x180005c10`
- `0x180006314`
- `0x180007988`
- `0x180007994`
- `0x18000a044`
- `0x18000a230`
- `0x18000d5b4`
- `0x18000d5d4`
- `0x18000dca8`
- `0x180015028`
- `0x180015fec`
- `0x180024e04`
- `0x1800267fc`
- `0x1800306c2`
- `0x180030700`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddc4`
- `RPCRT4!RpcRevertToSelf` at `0x18000e0c5`
- `RPCRT4!RpcRevertToSelf` at `0x18000e0c5`

## string_xrefs

- `0x18000e034`: `BinXmlHandler::ProcessElementEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall BinXmlHandler::SaveLegacyTask(BinXmlHandler *this)
{
  int result; // eax
  struct CompatibilityAdapter *Adapter; // rbx
  __int64 v4; // r9
  int v5; // esi
  __int64 v6; // rbx
  __int64 v7; // r9
  unsigned int *v8; // rcx
  unsigned int v9; // edx
  __int64 v10; // r8
  unsigned int v11; // edx
  unsigned int Priority; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  JobBucket *v15; // rcx
  unsigned int ExecutionTimeLimit; // eax
  JobBucket *v17; // rcx
  __int64 v18; // r8
  __int64 (__fastcall *v19)(__int64, __int64); // r9
  int v20; // edx
  __int64 v21; // rdx
  int v22; // ebx
  tsched *v23; // rax
  unsigned __int16 *v24; // rdx
  WCHAR *v25; // rbx
  unsigned int v26; // edx
  int v27; // eax
  bool v28; // zf
  WCHAR *v29; // rcx
  CJob *v30; // rcx
  __int64 v31; // rdx
  int v32; // r8d
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
    if ( result < 0 )
      return result;
    v37.Command = v40;
    Adapter = CompatibilityAdapter::GetAdapter();
    if ( !Adapter )
      return -2147418113;
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
    return v5;
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
    Priority = JobBucket::GetPriority((JobBucket *)v6);
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v13 + 304))(v14, *((unsigned int *)&v37.JobTime + Priority));
    if ( v5 >= 0 )
    {
      if ( JobBucket::GetExecutionTimeLimit((JobBucket *)v6) )
      {
        JobBucket::GetExecutionTimeLimit(v15);
        ExecutionTimeLimit = JobBucket::GetExecutionTimeLimit((JobBucket *)v6);
        v21 = v20 == ExecutionTimeLimit ? 1000 * JobBucket::GetExecutionTimeLimit(v17) : 0xFFFFFFFFLL;
        v22 = v19(v18, v21);
        if ( v22 < 0 )
        {
          wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v34);
          return v22;
        }
      }
      memset_0(v40, 0, 0x20Au);
      v5 = UriToFilename(*((wchar_t **)this + 65), v40);
      if ( v5 >= 0 )
      {
        v23 = (tsched *)operator new[](0x20Au);
        v25 = (WCHAR *)v23;
        v36 = (struct _RTL_CRITICAL_SECTION *)v23;
        if ( !v23 )
        {
          operator delete(0);
          v5 = -2147024882;
          goto LABEL_62;
        }
        v5 = tsched::SafePathAppend(v23, v24, (unsigned int)g_TasksFolderInfo, v40, v33);
        if ( v5 < 0 )
          goto LABEL_61;
        RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v35, L"BinXmlHandler::ProcessElementEnd");
        v27 = *((_DWORD *)this + 134);
        if ( (v27 & 2) != 0 )
        {
          v5 = CJob::SaveWithRetry(*((CJob **)this + 64), v25, 1, 1u);
          if ( v5 != -2147024816 )
          {
LABEL_52:
            if ( v35 )
              RpcRevertToSelf();
            if ( v5 < 0 )
              goto LABEL_61;
            v5 = CJob::Sign(*((CJob **)this + 64), v26);
            if ( v5 < 0 )
              goto LABEL_61;
            v30 = (CJob *)*((_QWORD *)this + 64);
            if ( *((_QWORD *)v30 + 26) )
            {
              v5 = CJob::Fingerprint(v30);
              if ( v5 < 0 )
                goto LABEL_61;
              v31 = *((_QWORD *)this + 64);
              v32 = *(_DWORD *)(v31 + 216);
              if ( v32 )
              {
                v5 = SignatureStore::Save(v40, *(BYTE **)(v31 + 208), v32);
                goto LABEL_61;
              }
            }
            v5 = -2147418113;
LABEL_61:
            operator delete(v25);
            goto LABEL_62;
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
          v29 = v25;
          v25 = 0;
          *(_QWORD *)(*((_QWORD *)this + 64) + 152LL) = v29;
          v36 = 0;
          v5 = CJob::SaveWithRetry(*((CJob **)this + 64), 0, 0, 1u);
        }
        goto LABEL_52;
      }
    }
  }
LABEL_62:
  wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v34);
  return v5;
}

```

## disassembly

```asm
0x18000dca8  mov     [rsp-8+arg_8], rbx
0x18000dcad  mov     [rsp-8+arg_10], rsi
0x18000dcb2  push    rbp
0x18000dcb3  push    rdi
0x18000dcb4  push    r15
0x18000dcb6  lea     rbp, [rsp-1A0h]
0x18000dcbe  sub     rsp, 2A0h
0x18000dcc5  mov     rax, cs:__security_cookie
0x18000dccc  xor     rax, rsp
0x18000dccf  mov     [rbp+1B0h+var_20], rax
0x18000dcd6  mov     rdi, rcx
0x18000dcd9  mov     r15d, 10000h
0x18000dcdf  cmp     [rcx+21Ch], r15d
0x18000dce6  jnz     loc_18000DDD5
0x18000dcec  mov     rax, [rcx+200h]
0x18000dcf3  or      dword ptr [rax+58h], 2
0x18000dcf7  mov     rax, [rcx+200h]
0x18000dcfe  bts     dword ptr [rax+58h], 15h
0x18000dd03  mov     [rsp+2B0h+var_278], 104h
0x18000dd0b  xorps   xmm0, xmm0
0x18000dd0e  xor     eax, eax
0x18000dd10  movups  xmmword ptr [rsp+2B0h+var_268.JobTime], xmm0
0x18000dd15  mov     [rsp+2B0h+var_268.Command], rax
0x18000dd1a  lea     r9, [rsp+2B0h+var_278]; unsigned int *
0x18000dd1f  lea     r8, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000dd23  lea     rdx, [rsp+2B0h+var_268]; struct _AT_INFO *
0x18000dd28  mov     rcx, [rcx+200h]; this
0x18000dd2f  call    ?GetAtInfo@CJob@@QEAAJPEAU_AT_INFO@@PEAGPEAK@Z; CJob::GetAtInfo(_AT_INFO *,ushort *,ulong *)
0x18000dd34  test    eax, eax
0x18000dd36  js      loc_18000E144
0x18000dd3c  lea     rax, [rbp+1B0h+var_230]
0x18000dd40  mov     [rsp+2B0h+var_268.Command], rax
0x18000dd45  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18000dd4a  mov     rbx, rax
0x18000dd4d  test    rax, rax
0x18000dd50  jnz     short loc_18000DD5C
0x18000dd52  mov     eax, 8000FFFFh
0x18000dd57  jmp     loc_18000E144
0x18000dd5c  lea     r15, ?gcsNetScheduleCritSection@@3VCStaticCritSec@@A; CStaticCritSec gcsNetScheduleCritSection
0x18000dd63  mov     [rsp+2B0h+var_270], r15
0x18000dd68  mov     rcx, r15; lpCriticalSection
0x18000dd6b  call    cs:__imp_EnterCriticalSection
0x18000dd72  nop     dword ptr [rax+rax+00h]
0x18000dd77  nop
0x18000dd78  mov     dword ptr [rsp+2B0h+var_280], 0
0x18000dd80  mov     rcx, [rbx+8]
0x18000dd84  mov     rax, [rcx]
0x18000dd87  mov     r9b, 1
0x18000dd8a  lea     r8, [rsp+2B0h+var_280]
0x18000dd8f  lea     rdx, [rsp+2B0h+var_268]
0x18000dd94  mov     rax, [rax+68h]
0x18000dd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd9d  mov     esi, eax
0x18000dd9f  test    eax, eax
0x18000dda1  js      short loc_18000DDC1
0x18000dda3  mov     r9d, dword ptr [rsp+2B0h+var_280]
0x18000dda8  lea     r8, aAtD; "At%d"
0x18000ddaf  mov     edx, 105h; unsigned __int64
0x18000ddb4  mov     rcx, [rdi+210h]; unsigned __int16 *
0x18000ddbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ddc0  nop
0x18000ddc1  mov     rcx, r15; lpCriticalSection
0x18000ddc4  call    cs:__imp_LeaveCriticalSection
0x18000ddcb  nop     dword ptr [rax+rax+00h]
0x18000ddd0  jmp     loc_18000E142
0x18000ddd5  mov     rbx, [rcx+28h]
0x18000ddd9  mov     [rsp+2B0h+var_280], rbx
0x18000ddde  test    rbx, rbx
0x18000dde1  jz      short loc_18000DDE7
0x18000dde3  lock inc dword ptr [rbx+8]
0x18000dde7  mov     r9, [rcx+200h]
0x18000ddee  mov     rax, [r9]
0x18000ddf1  mov     r10, [rax+50h]
0x18000ddf5  mov     rcx, [rbx+0D0h]
0x18000ddfc  test    rcx, rcx
0x18000ddff  jz      short loc_18000DE06
0x18000de01  mov     edx, [rcx+4]
0x18000de04  jmp     short loc_18000DE09
0x18000de06  or      edx, 0FFFFFFFFh
0x18000de09  mov     r11d, 88888889h
0x18000de0f  mov     eax, r11d
0x18000de12  mul     edx
0x18000de14  mov     r8d, edx
0x18000de17  shr     r8d, 5
0x18000de1b  test    rcx, rcx
0x18000de1e  jz      short loc_18000DE24
0x18000de20  mov     edx, [rcx]
0x18000de22  jmp     short loc_18000DE26
0x18000de24  xor     edx, edx
0x18000de26  mov     eax, r11d
0x18000de29  mul     edx
0x18000de2b  shr     edx, 5
0x18000de2e  mov     rcx, r9
0x18000de31  mov     rax, r10
0x18000de34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de39  mov     esi, eax
0x18000de3b  test    eax, eax
0x18000de3d  js      loc_18000E138
0x18000de43  test    dword ptr [rbx+10h], 400000h
0x18000de4a  jnz     short loc_18000DE57
0x18000de4c  mov     rax, [rdi+200h]
0x18000de53  or      dword ptr [rax+58h], 4
0x18000de57  mov     ecx, 200h
0x18000de5c  test    dword ptr [rbx+10h], 800000h
0x18000de63  jz      short loc_18000DE6F
0x18000de65  mov     rax, [rdi+200h]
0x18000de6c  or      [rax+58h], ecx
0x18000de6f  test    [rbx+10h], r15d
0x18000de73  jz      short loc_18000DE81
0x18000de75  mov     rax, [rdi+200h]
0x18000de7c  bts     dword ptr [rax+58h], 0Dh
0x18000de81  mov     eax, [rbx+10h]
0x18000de84  test    al, 2
0x18000de86  jz      short loc_18000DE93
0x18000de88  mov     rax, [rdi+200h]
0x18000de8f  or      dword ptr [rax+58h], 10h
0x18000de93  test    [rbx+10h], ecx
0x18000de96  jz      short loc_18000DEA4
0x18000de98  mov     rax, [rdi+200h]
0x18000de9f  bts     dword ptr [rax+58h], 0Ch
0x18000dea4  mov     eax, [rbx+10h]
0x18000dea7  mov     ecx, 20h ; ' '
0x18000deac  test    al, 8
0x18000deae  jz      short loc_18000DEBA
0x18000deb0  mov     rax, [rdi+200h]
0x18000deb7  or      [rax+58h], ecx
0x18000deba  mov     eax, [rbx+10h]
0x18000debd  test    al, 4
0x18000debf  jz      short loc_18000DECD
0x18000dec1  mov     rax, [rdi+200h]
0x18000dec8  bts     dword ptr [rax+58h], 0Bh
0x18000decd  mov     eax, [rbx+10h]
0x18000ded0  test    al, 10h
0x18000ded2  jz      short loc_18000DEDF
0x18000ded4  mov     rax, [rdi+200h]
0x18000dedb  or      dword ptr [rax+58h], 40h
0x18000dedf  mov     eax, [rbx+10h]
0x18000dee2  and     eax, ecx
0x18000dee4  mov     edx, 80h
0x18000dee9  test    al, al
0x18000deeb  jz      short loc_18000DEF7
0x18000deed  mov     rax, [rdi+200h]
0x18000def4  or      [rax+58h], edx
0x18000def7  mov     dword ptr [rsp+2B0h+var_268.JobTime], 100h
0x18000deff  mov     dword ptr [rsp+2B0h+var_268.JobTime+4], edx
0x18000df03  mov     [rsp+2B0h+var_268.DaysOfMonth], edx
0x18000df07  mov     dword ptr [rsp+2B0h+var_268.DaysOfWeek], edx
0x18000df0b  mov     dword ptr [rsp+2B0h+var_268.Command], ecx
0x18000df0f  mov     dword ptr [rsp+2B0h+var_268.Command+4], ecx
0x18000df13  mov     [rsp+2B0h+var_250], ecx
0x18000df17  movdqa  xmm0, cs:__xmm@00000040000000400000004000000040
0x18000df1f  movups  [rsp+2B0h+var_24C], xmm0
0x18000df24  mov     r9, [rdi+200h]
0x18000df2b  mov     r8, [r9]
0x18000df2e  mov     rcx, rbx; this
0x18000df31  call    ?GetPriority@JobBucket@@QEBAKXZ; JobBucket::GetPriority(void)
0x18000df36  mov     edx, eax
0x18000df38  mov     edx, dword ptr [rsp+rdx*4+2B0h+var_268.JobTime]
0x18000df3c  mov     rcx, r9
0x18000df3f  mov     rax, [r8+130h]
0x18000df46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df4b  mov     esi, eax
0x18000df4d  test    eax, eax
0x18000df4f  js      loc_18000E138
0x18000df55  mov     rcx, rbx; this
0x18000df58  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000df5d  test    eax, eax
0x18000df5f  jz      short loc_18000DFC5
0x18000df61  mov     r8, [rdi+200h]
0x18000df68  mov     rax, [r8]
0x18000df6b  mov     r9, [rax+150h]
0x18000df72  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000df77  imul    ecx, eax, 3E8h
0x18000df7d  mov     eax, 10624DD3h
0x18000df82  mul     ecx
0x18000df84  shr     edx, 6
0x18000df87  mov     rcx, rbx; this
0x18000df8a  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000df8f  cmp     edx, eax
0x18000df91  jnz     short loc_18000DFA0
0x18000df93  call    ?GetExecutionTimeLimit@JobBucket@@QEBAKXZ; JobBucket::GetExecutionTimeLimit(void)
0x18000df98  imul    edx, eax, 3E8h
0x18000df9e  jmp     short loc_18000DFA3
0x18000dfa0  or      edx, 0FFFFFFFFh
0x18000dfa3  mov     rcx, r8
0x18000dfa6  mov     rax, r9
0x18000dfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfae  mov     ebx, eax
0x18000dfb0  test    eax, eax
0x18000dfb2  jns     short loc_18000DFC5
0x18000dfb4  lea     rcx, [rsp+2B0h+var_280]
0x18000dfb9  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x18000dfbe  mov     eax, ebx
0x18000dfc0  jmp     loc_18000E144
0x18000dfc5  mov     ebx, 20Ah
0x18000dfca  mov     r8d, ebx; Size
0x18000dfcd  xor     edx, edx; Val
0x18000dfcf  lea     rcx, [rbp+1B0h+var_230]; void *
0x18000dfd3  call    memset_0
0x18000dfd8  lea     rdx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000dfdc  mov     rcx, [rdi+208h]; Str
0x18000dfe3  call    ?UriToFilename@@YAJPEBGPEAG@Z; UriToFilename(ushort const *,ushort *)
0x18000dfe8  mov     esi, eax
0x18000dfea  test    eax, eax
0x18000dfec  js      loc_18000E138
0x18000dff2  mov     ecx, ebx; unsigned __int64
0x18000dff4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dff9  mov     rbx, rax
0x18000dffc  mov     [rsp+2B0h+var_270], rax
0x18000e001  test    rax, rax
0x18000e004  jnz     short loc_18000E017
0x18000e006  xor     ecx, ecx; Block
0x18000e008  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e00d  mov     esi, 8007000Eh
0x18000e012  jmp     loc_18000E138
0x18000e017  lea     r9, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000e01b  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned int
0x18000e022  mov     rcx, rbx; this
0x18000e025  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18000e02a  mov     esi, eax
0x18000e02c  test    eax, eax
0x18000e02e  js      loc_18000E12F
0x18000e034  lea     rdx, aBinxmlhandlerP; "BinXmlHandler::ProcessElementEnd"
0x18000e03b  lea     rcx, [rsp+2B0h+var_278]; this
0x18000e040  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18000e045  nop
0x18000e046  mov     eax, [rdi+218h]
0x18000e04c  test    al, 2
0x18000e04e  jz      short loc_18000E07A
0x18000e050  mov     r9d, 1; unsigned int
0x18000e056  mov     r8d, r9d; int
0x18000e059  mov     rdx, rbx; lpFileName
0x18000e05c  mov     rcx, [rdi+200h]; this
0x18000e063  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x18000e068  mov     esi, eax
0x18000e06a  cmp     eax, 80070050h
0x18000e06f  jnz     short loc_18000E0BE
0x18000e071  test    byte ptr [rdi+218h], 4
0x18000e078  jmp     short loc_18000E07C
0x18000e07a  test    al, 4
0x18000e07c  jz      short loc_18000E0BE
0x18000e07e  mov     rax, [rdi+200h]
0x18000e085  mov     dword ptr [rax+0A0h], 1
0x18000e08f  mov     rcx, rbx
0x18000e092  mov     rax, [rdi+200h]
0x18000e099  xor     ebx, ebx
0x18000e09b  mov     [rax+98h], rcx
0x18000e0a2  mov     [rsp+2B0h+var_270], rbx
0x18000e0a7  lea     r9d, [rbx+1]; unsigned int
0x18000e0ab  xor     r8d, r8d; int
0x18000e0ae  xor     edx, edx; lpFileName
0x18000e0b0  mov     rcx, [rdi+200h]; this
0x18000e0b7  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x18000e0bc  mov     esi, eax
0x18000e0be  cmp     [rsp+2B0h+var_278], 0
0x18000e0c3  jz      short loc_18000E0D1
0x18000e0c5  call    cs:__imp_RpcRevertToSelf
0x18000e0cc  nop     dword ptr [rax+rax+00h]
0x18000e0d1  test    esi, esi
0x18000e0d3  js      short loc_18000E12F
0x18000e0d5  mov     rcx, [rdi+200h]; this
0x18000e0dc  call    ?Sign@CJob@@QEAAJK@Z; CJob::Sign(ulong)
0x18000e0e1  mov     esi, eax
0x18000e0e3  test    eax, eax
0x18000e0e5  js      short loc_18000E12F
0x18000e0e7  mov     rcx, [rdi+200h]; this
0x18000e0ee  cmp     qword ptr [rcx+0D0h], 0
0x18000e0f6  jnz     short loc_18000E0FF
0x18000e0f8  mov     esi, 8000FFFFh
0x18000e0fd  jmp     short loc_18000E12F
0x18000e0ff  call    ?Fingerprint@CJob@@QEAAJXZ; CJob::Fingerprint(void)
0x18000e104  mov     esi, eax
0x18000e106  test    eax, eax
0x18000e108  js      short loc_18000E12F
0x18000e10a  mov     rdx, [rdi+200h]
0x18000e111  mov     r8d, [rdx+0D8h]; unsigned int
0x18000e118  test    r8d, r8d
0x18000e11b  jz      short loc_18000E0F8
0x18000e11d  mov     rdx, [rdx+0D0h]; lpData
0x18000e124  lea     rcx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18000e128  call    ?Save@SignatureStore@@SAJPEBGPEAEK@Z; SignatureStore::Save(ushort const *,uchar *,ulong)
0x18000e12d  mov     esi, eax
0x18000e12f  mov     rcx, rbx; Block
0x18000e132  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e137  nop
0x18000e138  lea     rcx, [rsp+2B0h+var_280]
0x18000e13d  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x18000e142  mov     eax, esi
0x18000e144  mov     rcx, [rbp+1B0h+var_20]
0x18000e14b  xor     rcx, rsp; StackCookie
0x18000e14e  call    __security_check_cookie
0x18000e153  lea     r11, [rsp+2B0h+var_10]
0x18000e15b  mov     rbx, [r11+28h]
0x18000e15f  mov     rsi, [r11+30h]
0x18000e163  mov     rsp, r11
0x18000e166  pop     r15
0x18000e168  pop     rdi
0x18000e169  pop     rbp
0x18000e16a  retn
```
