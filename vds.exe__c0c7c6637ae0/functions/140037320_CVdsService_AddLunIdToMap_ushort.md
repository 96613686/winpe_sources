# CVdsService::AddLunIdToMap(ushort *)

- ea: `0x140037320`
- end: `0x14003766c`
- name: `?AddLunIdToMap@CVdsService@@CAJPEAG@Z`
- size: `844`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400078a0`
- `0x140037a0c`

## callees

- `0x140006e60`
- `0x14002c7a0`
- `0x140037320`
- `0x1400383cc`
- `0x14003bdec`
- `0x14003c938`
- `0x140052e80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14003749b`
- `msvcrt!_wcsicmp` at `0x14003749b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140037638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140037638`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140037382`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140037382`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400374c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400374c7`
- `vdsutil!VdsTrace` at `0x1400373c8`
- `vdsutil!VdsTrace` at `0x140037400`
- `vdsutil!VdsTrace` at `0x140037478`
- `vdsutil!VdsTrace` at `0x140037612`
- `vdsutil!VdsTrace` at `0x1400373c8`
- `vdsutil!VdsTrace` at `0x140037400`
- `vdsutil!VdsTrace` at `0x140037478`
- `vdsutil!VdsTrace` at `0x140037612`
- `vdsutil!?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x14003756c`
- `vdsutil!?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x14003756c`
- `vdsutil!VdsTraceEx` at `0x1400374e9`
- `vdsutil!VdsTraceEx` at `0x1400375f8`
- `vdsutil!VdsTraceEx` at `0x14003762a`
- `vdsutil!VdsTraceEx` at `0x1400374e9`
- `vdsutil!VdsTraceEx` at `0x1400375f8`
- `vdsutil!VdsTraceEx` at `0x14003762a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037374`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037374`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037643`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037643`

## string_xrefs

- `0x140037364`: `CVdsService::AddLunIdToMap()`
- `0x140037609`: `CVdsService::AddLunIdToMap, 1, hr=%lX`
- `0x1400373bc`: `CVdsService::AddLunIdToMap, 2, path=%S, %s`
- `0x1400373f4`: `CVdsService::AddLunIdToMap, 3 LunId: path=%S, %s, hr=%lX`
- `0x14003746c`: `CVdsService::AddLunIdToMap, 4 LunId: {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}path=%S, %s`
- `0x1400374dd`: `CVdsService::AddLunIdToMap, 5`
- `0x14003757c`: `CVdsService::AddLunIdToMap, 6`
- `0x14003761b`: `EXIT CVdsService::AddLunIdToMap, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::AddLunIdToMap(LPCWSTR lpFileName)
{
  __int64 v2; // r13
  __int64 v3; // rax
  unsigned int LunIdFromProviders; // eax
  unsigned int v5; // r15d
  const wchar_t *LunFromId; // rax
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r12
  __int64 v11; // [rsp+20h] [rbp-B9h]
  __int64 v12; // [rsp+28h] [rbp-B1h]
  __int64 v13; // [rsp+30h] [rbp-A9h]
  __int64 v14; // [rsp+38h] [rbp-A1h]
  __int64 v15; // [rsp+40h] [rbp-99h]
  __int64 v16; // [rsp+48h] [rbp-91h]
  __int64 v17; // [rsp+50h] [rbp-89h]
  __int64 v18; // [rsp+58h] [rbp-81h]
  __int64 v19; // [rsp+60h] [rbp-79h]
  __int64 v20; // [rsp+68h] [rbp-71h]
  _BYTE v21[16]; // [rsp+80h] [rbp-59h] BYREF
  struct _GUID v22; // [rsp+90h] [rbp-49h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-39h] BYREF
  struct _GUID v24; // [rsp+B0h] [rbp-29h]
  __int128 v25; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v26; // [rsp+D0h] [rbp-9h]

  v22 = 0;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v21, 0x5Eu, "CVdsService::AddLunIdToMap()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  v22 = 0;
  if ( !lpFileName )
    goto LABEL_20;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( lpFileName[v3] );
  if ( !v3 )
  {
LABEL_20:
    v5 = -2147024809;
    VdsTrace(0, "CVdsService::AddLunIdToMap, 1, hr=%lX", -2147024809);
    goto LABEL_21;
  }
  VdsTrace(2, "CVdsService::AddLunIdToMap, 2, path=%S, %s", lpFileName, (const char *)lpFileName);
  LunIdFromProviders = CVdsService::GetLunIdFromProviders(lpFileName, &v22);
  v5 = LunIdFromProviders;
  if ( LunIdFromProviders )
  {
    if ( LunIdFromProviders != 1 )
      VdsTrace(
        2,
        "CVdsService::AddLunIdToMap, 3 LunId: path=%S, %s, hr=%lX",
        lpFileName,
        (const char *)lpFileName,
        LunIdFromProviders);
  }
  else
  {
    VdsTrace(
      2,
      "CVdsService::AddLunIdToMap, 4 LunId: {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}path=%S, %s",
      v22.Data1,
      v22.Data2,
      v22.Data3,
      v22.Data4[0],
      v22.Data4[1],
      v22.Data4[2],
      v22.Data4[3],
      v22.Data4[4],
      v22.Data4[5],
      v22.Data4[6],
      v22.Data4[7],
      lpFileName,
      (const char *)lpFileName);
    CVdsService::ResetLunWrapper(&v22);
    LunFromId = CVdsService::FindLunFromId(&v22);
    if ( LunFromId )
    {
      if ( !_wcsicmp(lpFileName, LunFromId) )
        goto LABEL_21;
      CVdsService::RemoveFromLunIdMap(&v22);
    }
    v7 = -1;
    do
      ++v7;
    while ( lpFileName[v7] );
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7 + 2);
    v9 = v8;
    if ( v8 )
    {
      do
        ++v2;
      while ( lpFileName[v2] );
      StringCchCopyW(v8, v2 + 1, lpFileName);
      v24 = v22;
      *((_QWORD *)&v25 + 1) = 0;
      *(_QWORD *)&v26 = v9;
      if ( CRtlMap::Insert((CRtlMap *)CVdsService::m_mapLunIds, (struct CRtlEntry *)&v23, (struct CRtlEntry *)&v25) )
      {
        LODWORD(v20) = v22.Data4[7];
        LODWORD(v19) = v22.Data4[6];
        LODWORD(v18) = v22.Data4[5];
        LODWORD(v17) = v22.Data4[4];
        LODWORD(v16) = v22.Data4[3];
        LODWORD(v15) = v22.Data4[2];
        LODWORD(v14) = v22.Data4[1];
        LODWORD(v13) = v22.Data4[0];
        LODWORD(v12) = v22.Data3;
        LODWORD(v11) = v22.Data2;
        VdsTraceEx(
          94,
          3,
          "Added LUN {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}[%ws] to LUN-disk map",
          v22.Data1,
          v11,
          v12,
          v13,
          v14,
          v15,
          v16,
          v17,
          v18,
          v19,
          v20,
          v9);
      }
      else
      {
        v5 = -2147212259;
        VdsTraceEx(94, 0, "CVdsService::AddLunIdToMap, 6");
      }
    }
    else
    {
      v5 = -2147024882;
      VdsTraceEx(94, 0, "CVdsService::AddLunIdToMap, 5");
    }
  }
LABEL_21:
  VdsTraceEx(94, 2, "EXIT CVdsService::AddLunIdToMap, hr=%lX", v5);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
  return v5;
}

```

## disassembly

```asm
0x140037320  push    rbp
0x140037322  push    rbx
0x140037323  push    rsi
0x140037324  push    rdi
0x140037325  push    r12
0x140037327  push    r13
0x140037329  push    r14
0x14003732b  push    r15
0x14003732d  lea     rbp, [rsp-1Fh]
0x140037332  sub     rsp, 0F8h
0x140037339  mov     rax, cs:__security_cookie
0x140037340  xor     rax, rsp
0x140037343  mov     [rbp+57h+var_48], rax
0x140037347  mov     r14, rcx
0x14003734a  xorps   xmm0, xmm0
0x14003734d  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x140037351  xorps   xmm1, xmm1
0x140037354  movups  [rbp+57h+var_70], xmm1
0x140037358  movups  [rbp+57h+var_60], xmm1
0x14003735c  movups  [rbp+57h+var_90], xmm0
0x140037360  movups  [rbp+57h+var_80], xmm0
0x140037364  lea     r8, aCvdsserviceAdd_7; "CVdsService::AddLunIdToMap()"
0x14003736b  mov     edx, 5Eh ; '^'
0x140037370  lea     rcx, [rbp+57h+var_B0]
0x140037374  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003737a  nop
0x14003737b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140037382  call    cs:__imp_EnterCriticalSection
0x140037388  nop
0x140037389  xorps   xmm0, xmm0
0x14003738c  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x140037390  xor     r12d, r12d
0x140037393  test    r14, r14
0x140037396  jz      loc_140037600
0x14003739c  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400373a0  mov     rax, r13
0x1400373a3  inc     rax
0x1400373a6  cmp     [r14+rax*2], r12w
0x1400373ab  jnz     short loc_1400373A3
0x1400373ad  test    rax, rax
0x1400373b0  jz      loc_140037600
0x1400373b6  mov     r9, r14
0x1400373b9  mov     r8, r14
0x1400373bc  lea     rdx, aCvdsserviceAdd; "CVdsService::AddLunIdToMap, 2, path=%S,"...
0x1400373c3  mov     ecx, 2
0x1400373c8  call    cs:__imp_VdsTrace
0x1400373ce  lea     rdx, [rbp+57h+var_A0]; struct _GUID *
0x1400373d2  mov     rcx, r14; lpFileName
0x1400373d5  call    ?GetLunIdFromProviders@CVdsService@@CAJPEAGPEAU_GUID@@@Z; CVdsService::GetLunIdFromProviders(ushort *,_GUID *)
0x1400373da  mov     r15d, eax
0x1400373dd  test    eax, eax
0x1400373df  jz      short loc_14003740B
0x1400373e1  cmp     eax, 1
0x1400373e4  jz      loc_140037618
0x1400373ea  mov     dword ptr [rsp+130h+var_110], eax
0x1400373ee  mov     r9, r14
0x1400373f1  mov     r8, r14
0x1400373f4  lea     rdx, aCvdsserviceAdd_3; "CVdsService::AddLunIdToMap, 3 LunId: pa"...
0x1400373fb  mov     ecx, 2
0x140037400  call    cs:__imp_VdsTrace
0x140037406  jmp     loc_140037618
0x14003740b  movzx   eax, [rbp+57h+var_A0.Data4+7]
0x14003740f  movzx   ecx, [rbp+57h+var_A0.Data4+6]
0x140037413  movzx   edx, [rbp+57h+var_A0.Data4+5]
0x140037417  movzx   r8d, [rbp+57h+var_A0.Data4+4]
0x14003741c  movzx   r10d, [rbp+57h+var_A0.Data4+3]
0x140037421  movzx   r11d, [rbp+57h+var_A0.Data4+2]
0x140037426  movzx   ebx, [rbp+57h+var_A0.Data4+1]
0x14003742a  movzx   edi, [rbp+57h+var_A0.Data4]
0x14003742e  movzx   esi, [rbp+57h+var_A0.Data3]
0x140037432  movzx   r9d, [rbp+57h+var_A0.Data2]
0x140037437  mov     [rsp+130h+var_C0], r14
0x14003743c  mov     [rsp+130h+var_C8], r14
0x140037441  mov     dword ptr [rsp+130h+var_D0], eax
0x140037445  mov     dword ptr [rsp+130h+var_D8], ecx
0x140037449  mov     dword ptr [rsp+130h+var_E0], edx
0x14003744d  mov     dword ptr [rsp+130h+var_E8], r8d
0x140037452  mov     dword ptr [rsp+130h+var_F0], r10d
0x140037457  mov     dword ptr [rsp+130h+var_F8], r11d
0x14003745c  mov     dword ptr [rsp+130h+var_100], ebx
0x140037460  mov     dword ptr [rsp+130h+var_108], edi
0x140037464  mov     dword ptr [rsp+130h+var_110], esi
0x140037468  mov     r8d, [rbp+57h+var_A0.Data1]
0x14003746c  lea     rdx, aCvdsserviceAdd_8; "CVdsService::AddLunIdToMap, 4 LunId: {%"...
0x140037473  mov     ecx, 2
0x140037478  call    cs:__imp_VdsTrace
0x14003747e  lea     rcx, [rbp+57h+var_A0]; struct _GUID *
0x140037482  call    ?ResetLunWrapper@CVdsService@@SAXAEAU_GUID@@@Z; CVdsService::ResetLunWrapper(_GUID &)
0x140037487  lea     rcx, [rbp+57h+var_A0]; struct _GUID *
0x14003748b  call    ?FindLunFromId@CVdsService@@CAPEAGAEAU_GUID@@@Z; CVdsService::FindLunFromId(_GUID &)
0x140037490  test    rax, rax
0x140037493  jz      short loc_1400374B2
0x140037495  mov     rdx, rax; String2
0x140037498  mov     rcx, r14; String1
0x14003749b  call    cs:__imp__wcsicmp
0x1400374a1  test    eax, eax
0x1400374a3  jz      loc_140037618
0x1400374a9  lea     rcx, [rbp+57h+var_A0]; struct _GUID *
0x1400374ad  call    ?RemoveFromLunIdMap@CVdsService@@CAXAEAU_GUID@@@Z; CVdsService::RemoveFromLunIdMap(_GUID &)
0x1400374b2  mov     rcx, r13
0x1400374b5  inc     rcx
0x1400374b8  cmp     [r14+rcx*2], r12w
0x1400374bd  jnz     short loc_1400374B5
0x1400374bf  lea     rcx, ds:2[rcx*2]; cb
0x1400374c7  call    cs:__imp_CoTaskMemAlloc
0x1400374cd  mov     r12, rax
0x1400374d0  xor     ebx, ebx
0x1400374d2  test    rax, rax
0x1400374d5  jnz     short loc_1400374F4
0x1400374d7  mov     r15d, 8007000Eh
0x1400374dd  lea     r8, aCvdsserviceAdd_6; "CVdsService::AddLunIdToMap, 5"
0x1400374e4  xor     edx, edx
0x1400374e6  lea     ecx, [rdx+5Eh]
0x1400374e9  call    cs:__imp_VdsTraceEx
0x1400374ef  jmp     loc_140037618
0x1400374f4  inc     r13
0x1400374f7  cmp     [r14+r13*2], bx
0x1400374fc  jnz     short loc_1400374F4
0x1400374fe  lea     rdx, [r13+1]; unsigned __int64
0x140037502  mov     r8, r14; unsigned __int16 *
0x140037505  mov     rcx, r12; unsigned __int16 *
0x140037508  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003750d  mov     r10d, [rbp+57h+var_A0.Data1]
0x140037511  mov     dword ptr [rbp+57h+var_80], r10d
0x140037515  movzx   eax, [rbp+57h+var_A0.Data2]
0x140037519  mov     word ptr [rbp+57h+var_80+4], ax
0x14003751d  movzx   eax, [rbp+57h+var_A0.Data3]
0x140037521  mov     word ptr [rbp+57h+var_80+6], ax
0x140037525  mov     al, [rbp+57h+var_A0.Data4]
0x140037528  mov     byte ptr [rbp+57h+var_80+8], al
0x14003752b  mov     al, [rbp+57h+var_A0.Data4+1]
0x14003752e  mov     byte ptr [rbp+57h+var_80+9], al
0x140037531  mov     al, [rbp+57h+var_A0.Data4+2]
0x140037534  mov     byte ptr [rbp+57h+var_80+0Ah], al
0x140037537  mov     al, [rbp+57h+var_A0.Data4+3]
0x14003753a  mov     byte ptr [rbp+57h+var_80+0Bh], al
0x14003753d  mov     al, [rbp+57h+var_A0.Data4+4]
0x140037540  mov     byte ptr [rbp+57h+var_80+0Ch], al
0x140037543  mov     al, [rbp+57h+var_A0.Data4+5]
0x140037546  mov     byte ptr [rbp+57h+var_80+0Dh], al
0x140037549  mov     al, [rbp+57h+var_A0.Data4+6]
0x14003754c  mov     byte ptr [rbp+57h+var_80+0Eh], al
0x14003754f  mov     al, [rbp+57h+var_A0.Data4+7]
0x140037552  mov     byte ptr [rbp+57h+var_80+0Fh], al
0x140037555  mov     qword ptr [rbp+57h+var_70+8], rbx
0x140037559  mov     qword ptr [rbp+57h+var_60], r12
0x14003755d  lea     r8, [rbp+57h+var_70]
0x140037561  lea     rdx, [rbp+57h+var_90]
0x140037565  lea     rcx, ?m_mapLunIds@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapLunIds
0x14003756c  call    cs:__imp_?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z; CRtlMap::Insert(CRtlEntry &,CRtlEntry &)
0x140037572  test    eax, eax
0x140037574  jnz     short loc_140037588
0x140037576  mov     r15d, 8004241Dh
0x14003757c  lea     r8, aCvdsserviceAdd_12; "CVdsService::AddLunIdToMap, 6"
0x140037583  jmp     loc_1400374E4
0x140037588  movzx   eax, [rbp+57h+var_A0.Data4+7]
0x14003758c  movzx   ecx, [rbp+57h+var_A0.Data4+6]
0x140037590  movzx   edx, [rbp+57h+var_A0.Data4+5]
0x140037594  movzx   r8d, [rbp+57h+var_A0.Data4+4]
0x140037599  movzx   r9d, [rbp+57h+var_A0.Data4+3]
0x14003759e  movzx   r10d, [rbp+57h+var_A0.Data4+2]
0x1400375a3  movzx   r11d, [rbp+57h+var_A0.Data4+1]
0x1400375a8  movzx   ebx, [rbp+57h+var_A0.Data4]
0x1400375ac  movzx   edi, [rbp+57h+var_A0.Data3]
0x1400375b0  movzx   esi, [rbp+57h+var_A0.Data2]
0x1400375b4  mov     [rsp+130h+var_C0], r12
0x1400375b9  mov     dword ptr [rsp+130h+var_C8], eax
0x1400375bd  mov     dword ptr [rsp+130h+var_D0], ecx
0x1400375c1  mov     dword ptr [rsp+130h+var_D8], edx
0x1400375c5  mov     dword ptr [rsp+130h+var_E0], r8d
0x1400375ca  mov     dword ptr [rsp+130h+var_E8], r9d
0x1400375cf  mov     dword ptr [rsp+130h+var_F0], r10d
0x1400375d4  mov     dword ptr [rsp+130h+var_F8], r11d
0x1400375d9  mov     dword ptr [rsp+130h+var_100], ebx
0x1400375dd  mov     dword ptr [rsp+130h+var_108], edi
0x1400375e1  mov     dword ptr [rsp+130h+var_110], esi
0x1400375e5  mov     r9d, [rbp+57h+var_A0.Data1]
0x1400375e9  lea     r8, aAddedLun8x4x4x; "Added LUN {%.8x-%.4x-%.4x-%.2x%.2x-%.2x"...
0x1400375f0  mov     edx, 3
0x1400375f5  lea     ecx, [rdx+5Bh]
0x1400375f8  call    cs:__imp_VdsTraceEx
0x1400375fe  jmp     short loc_140037618
0x140037600  mov     r15d, 80070057h
0x140037606  mov     r8d, r15d
0x140037609  lea     rdx, aCvdsserviceAdd_0; "CVdsService::AddLunIdToMap, 1, hr=%lX"
0x140037610  xor     ecx, ecx
0x140037612  call    cs:__imp_VdsTrace
0x140037618  mov     r9d, r15d
0x14003761b  lea     r8, aExitCvdsservic_6; "EXIT CVdsService::AddLunIdToMap, hr=%lX"
0x140037622  mov     edx, 2
0x140037627  lea     ecx, [rdx+5Ch]
0x14003762a  call    cs:__imp_VdsTraceEx
0x140037630  nop
0x140037631  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140037638  call    cs:__imp_LeaveCriticalSection
0x14003763e  nop
0x14003763f  lea     rcx, [rbp+57h+var_B0]
0x140037643  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140037649  mov     eax, r15d
0x14003764c  mov     rcx, [rbp+57h+var_48]
0x140037650  xor     rcx, rsp; StackCookie
0x140037653  call    __security_check_cookie
0x140037658  add     rsp, 0F8h
0x14003765f  pop     r15
0x140037661  pop     r14
0x140037663  pop     r13
0x140037665  pop     r12
0x140037667  pop     rdi
0x140037668  pop     rsi
0x140037669  pop     rbx
0x14003766a  pop     rbp
0x14003766b  retn
```
