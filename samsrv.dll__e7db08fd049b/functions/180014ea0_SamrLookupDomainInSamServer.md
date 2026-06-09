# SamrLookupDomainInSamServer

- ea: `0x180014ea0`
- end: `0x1800153d7`
- name: `SamrLookupDomainInSamServer`
- size: `1335`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, struct _RPC_UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008590`
- `0x1800096c0`
- `0x18000ae10`
- `0x180012a28`
- `0x180013e00`
- `0x180014ea0`
- `0x1800153e0`
- `0x180016240`
- `0x180024dc0`
- `0x1800270b4`
- `0x180027e24`
- `0x1800372ac`
- `0x180078fb4`
- `0x18008fc14`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800151e4`
- `ntdll!RtlEqualUnicodeString` at `0x1800151e4`
- `ntdll!RtlEqualDomainName` at `0x1800151c6`
- `ntdll!RtlEqualDomainName` at `0x1800151c6`
- `ntdll!RtlEnterCriticalSection` at `0x180014ffb`
- `ntdll!RtlEnterCriticalSection` at `0x180014ffb`
- `ntdll!RtlCopySid` at `0x180015241`
- `ntdll!RtlCopySid` at `0x180015241`
- `ntdll!RtlLengthSid` at `0x18001520f`
- `ntdll!RtlLengthSid` at `0x18001520f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014f32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015184`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001521e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014f32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015184`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001521e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015160`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001528e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001529c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001530c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015160`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001528e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001529c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800152f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001530c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014fe5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015008`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014fe5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015008`
- `DNSAPI!DnsNameCompare_W` at `0x1800151f9`
- `DNSAPI!DnsNameCompare_W` at `0x1800151f9`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x180015071`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x180015071`

## pseudocode

```c
__int64 __fastcall SamrLookupDomainInSamServer(struct _SAMP_OBJECT *a1, struct _RPC_UNICODE_STRING *a2, HLOCAL *a3)
{
  unsigned int v4; // edi
  HLOCAL *v5; // r12
  _WORD *v7; // rax
  _WORD *v8; // r15
  NTSTATUS v9; // ebx
  unsigned __int8 v10; // r14
  DWORD TickCount; // ebx
  DWORD v12; // eax
  unsigned int v13; // ecx
  DWORD v14; // eax
  unsigned int v15; // eax
  void *v16; // r14
  char v17; // al
  __int64 v18; // rbp
  unsigned __int16 v19; // cx
  const void *v20; // r12
  HLOCAL v21; // rax
  ULONG v22; // ebx
  HLOCAL v23; // rax
  void *v24; // r12
  PUNICODE_STRING v25; // rcx
  unsigned __int8 v27; // [rsp+30h] [rbp-48h]
  unsigned __int16 v28; // [rsp+32h] [rbp-46h]
  int v29; // [rsp+34h] [rbp-44h] BYREF
  size_t Size; // [rsp+38h] [rbp-40h]
  char v32; // [rsp+98h] [rbp+20h]

  v4 = 0;
  v5 = a3;
  v29 = 0;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_qZ(WPP_GLOBAL_Control[3].Buffer, (_DWORD)a2, (_DWORD)a3, (_DWORD)a1, (__int64)a2);
  SampTraceEvent(1);
  *v5 = 0;
  if ( !SampValidateRpcUnicodeString(a2) || !*((_QWORD *)a2 + 1) )
  {
    v9 = -1073741811;
LABEL_63:
    if ( *v5 )
    {
      LocalFree(*v5);
      *v5 = 0;
    }
    goto LABEL_65;
  }
  v7 = LocalAlloc(0x40u, *(unsigned __int16 *)a2 + 2LL);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -1073741801;
    goto LABEL_63;
  }
  memcpy_0(v7, *((const void **)a2 + 1), *(unsigned __int16 *)a2);
  v8[(unsigned __int64)*(unsigned __int16 *)a2 >> 1] = 0;
  if ( !a1 )
    goto LABEL_13;
  v10 = 0;
  v27 = 0;
  if ( (int)SampValidateContext(a1) < 0 )
    goto LABEL_26;
  if ( (*((_BYTE *)a1 + 192) & 2) != 0 && (*((_BYTE *)a1 + 28) & 1) != 0 )
  {
    SampIncrementActiveThreads();
  }
  else
  {
LABEL_13:
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    if ( !SampUseDsData || !(unsigned int)SampExtIsWriteLockHeldByDs() )
    {
      TickCount = GetTickCount();
      _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
      RtlEnterCriticalSection(&SampLock);
      _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
      v12 = GetTickCount();
      v13 = SamLockTotalAquisitions + 1;
      SamLockCurrentHoldStartTime = v12;
      ++SamLockTotalAquisitions;
      v14 = v12 - TickCount;
      if ( v14 && v13 )
        SamCumulativeWaitTime += v14;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
      if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
        NtdsaExtSetGlobalTransactionType(0);
    }
    v10 = 1;
    v27 = 1;
  }
LABEL_26:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
  if ( SampUseDsData == 1 )
    v4 = 2;
  v15 = SampLookupContextEx((__int64)a1, 0x20u, 0, 0, &v29);
  v9 = v15;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v15, v15);
  if ( v9 < 0 )
  {
    SampMaybeReleaseReadLock(v10);
    LocalFree(v8);
  }
  else
  {
    v16 = 0;
    v9 = -1073741601;
    v17 = 0;
    v32 = 0;
    while ( v4 < SampDefinedDomainsCount && !v17 )
    {
      v18 = 1360LL * v4;
      v19 = *(_WORD *)((char *)SampDefinedDomains + v18 + 1320);
      v20 = *(const void **)((char *)SampDefinedDomains + v18 + 1328);
      v28 = v19;
      if ( v16 )
      {
        LocalFree(v16);
        v19 = v28;
        v16 = 0;
      }
      if ( v20 )
      {
        Size = v19;
        v21 = LocalAlloc(0x40u, v19 + 2LL);
        v16 = v21;
        if ( !v21 )
        {
          v9 = -1073741801;
LABEL_51:
          SampDeReferenceContext(a1, 0);
          goto LABEL_52;
        }
        memcpy_0(v21, v20, Size);
        *((_WORD *)v16 + (Size >> 1)) = 0;
      }
      if ( RtlEqualDomainName((PUNICODE_STRING)((char *)SampDefinedDomains + v18 + 16), (PUNICODE_STRING)a2)
        || RtlEqualUnicodeString((PCUNICODE_STRING)((char *)SampDefinedDomains + v18 + 16), (PCUNICODE_STRING)a2, 1u)
        || v16 && DnsNameCompare_W((PCWSTR)v16, v8) )
      {
        v22 = RtlLengthSid(*(PSID *)((char *)SampDefinedDomains + v18 + 8));
        v23 = LocalAlloc(0x40u, v22);
        v24 = v23;
        if ( !v23 )
        {
          v9 = -1073741670;
          goto LABEL_51;
        }
        v9 = RtlCopySid(v22, v23, *(PSID *)((char *)SampDefinedDomains + v18 + 8));
        if ( v9 < 0 )
        {
          LocalFree(v24);
          v9 = -1073741595;
          goto LABEL_51;
        }
        v17 = 1;
        v32 = 1;
        *a3 = v24;
      }
      else
      {
        v17 = v32;
      }
      ++v4;
    }
    if ( v9 < 0 )
      goto LABEL_51;
    v9 = SampDeReferenceContext(a1, 0);
LABEL_52:
    SampMaybeReleaseReadLock(v27);
    LocalFree(v8);
    if ( v16 )
      LocalFree(v16);
    v5 = a3;
  }
  if ( v9 < 0 )
    goto LABEL_63;
LABEL_65:
  SampTraceEvent(2);
  if ( v9 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 41, WPP_a5e011badb8432b034189f08c175cf46_Traceguids, (unsigned int)v9);
      goto LABEL_72;
    }
  }
  else
  {
    v25 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF__sid_(
        (__int64)WPP_GLOBAL_Control[3].Buffer,
        0x28u,
        (__int64)WPP_a5e011badb8432b034189f08c175cf46_Traceguids,
        (char *)*v5);
LABEL_72:
      v25 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_DWORD *)(&v25[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v25[3].Buffer, 42, WPP_a5e011badb8432b034189f08c175cf46_Traceguids, (unsigned int)v9, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180014ea0  mov     rax, rsp
0x180014ea3  mov     [rax+18h], r8
0x180014ea7  push    rbx
0x180014ea8  sub     rsp, 70h
0x180014eac  mov     [rax+8], rbp
0x180014eb0  mov     [rax-10h], rsi
0x180014eb4  mov     rsi, rdx
0x180014eb7  mov     [rax-18h], rdi
0x180014ebb  xor     edi, edi
0x180014ebd  mov     [rax-20h], r12
0x180014ec1  mov     r12, r8
0x180014ec4  mov     [rax-28h], r13
0x180014ec8  mov     r13, rcx
0x180014ecb  mov     [rax-44h], edi
0x180014ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ed5  test    byte ptr [rcx+44h], 8
0x180014ed9  jz      short loc_180014EF1
0x180014edb  cmp     byte ptr [rcx+41h], 4
0x180014edf  jb      short loc_180014EF1
0x180014ee1  mov     rcx, [rcx+38h]
0x180014ee5  mov     r9, r13
0x180014ee8  mov     [rax-58h], rdx
0x180014eec  call    WPP_SF_qZ
0x180014ef1  xor     r8d, r8d
0x180014ef4  mov     [rsp+78h+var_38], r15
0x180014ef9  mov     edx, 5
0x180014efe  mov     ecx, 1
0x180014f03  call    SampTraceEvent
0x180014f08  mov     rcx, rsi; struct _RPC_UNICODE_STRING *
0x180014f0b  mov     [r12], rdi
0x180014f0f  call    ?SampValidateRpcUnicodeString@@YAEPEAU_RPC_UNICODE_STRING@@@Z; SampValidateRpcUnicodeString(_RPC_UNICODE_STRING *)
0x180014f14  test    al, al
0x180014f16  jz      loc_1800152F9
0x180014f1c  cmp     [rsi+8], rdi
0x180014f20  jz      loc_1800152F9
0x180014f26  movzx   edx, word ptr [rsi]
0x180014f29  mov     ecx, 40h ; '@'; uFlags
0x180014f2e  add     rdx, 2; uBytes
0x180014f32  call    cs:__imp_LocalAlloc
0x180014f38  mov     r15, rax
0x180014f3b  test    rax, rax
0x180014f3e  jnz     short loc_180014F4A
0x180014f40  mov     ebx, 0C0000017h
0x180014f45  jmp     loc_1800152FE
0x180014f4a  movzx   r8d, word ptr [rsi]; Size
0x180014f4e  mov     rcx, r15; void *
0x180014f51  mov     rdx, [rsi+8]; Src
0x180014f55  mov     [rsp+78h+var_30], r14
0x180014f5a  call    memcpy_0
0x180014f5f  movzx   ecx, word ptr [rsi]
0x180014f62  shr     rcx, 1
0x180014f65  mov     [r15+rcx*2], di
0x180014f6a  test    r13, r13
0x180014f6d  jz      short loc_180014FA2
0x180014f6f  xor     r14b, r14b
0x180014f72  mov     rcx, r13; struct _SAMP_OBJECT *
0x180014f75  mov     [rsp+78h+var_48], r14b
0x180014f7a  call    ?SampValidateContext@@YAJPEAU_SAMP_OBJECT@@@Z; SampValidateContext(_SAMP_OBJECT *)
0x180014f7f  test    eax, eax
0x180014f81  js      loc_18001507F
0x180014f87  test    byte ptr [r13+0C0h], 2
0x180014f8f  jz      short loc_180014FA2
0x180014f91  test    byte ptr [r13+1Ch], 1
0x180014f96  jz      short loc_180014FA2
0x180014f98  call    SampIncrementActiveThreads
0x180014f9d  jmp     loc_18001507F
0x180014fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fa9  test    dword ptr [rcx+44h], 20000h
0x180014fb0  jz      short loc_180014FCF
0x180014fb2  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180014fba  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180014fc1  mov     rcx, [rcx+38h]
0x180014fc5  mov     edx, 49h ; 'I'
0x180014fca  call    WPP_SF_d
0x180014fcf  cmp     cs:?SampUseDsData@@3EA, dil; uchar SampUseDsData
0x180014fd6  jz      short loc_180014FE5
0x180014fd8  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x180014fdd  test    eax, eax
0x180014fdf  jnz     loc_180015077
0x180014fe5  call    cs:__imp_GetTickCount
0x180014feb  mov     ebx, eax
0x180014fed  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180014ff4  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180014ffb  call    cs:__imp_RtlEnterCriticalSection
0x180015001  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180015008  call    cs:__imp_GetTickCount
0x18001500e  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x180015014  inc     ecx
0x180015016  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x18001501c  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x180015022  sub     eax, ebx
0x180015024  jz      short loc_180015030
0x180015026  test    ecx, ecx
0x180015028  jz      short loc_180015030
0x18001502a  add     cs:?SamCumulativeWaitTime@@3KA, eax; ulong SamCumulativeWaitTime
0x180015030  mov     rcx, cs:WPP_GLOBAL_Control
0x180015037  test    dword ptr [rcx+44h], 20000h
0x18001503e  jz      short loc_18001505D
0x180015040  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180015048  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18001504f  mov     rcx, [rcx+38h]
0x180015053  mov     edx, 49h ; 'I'
0x180015058  call    WPP_SF_d
0x18001505d  cmp     cs:?SampUseDsData@@3EA, dil; uchar SampUseDsData
0x180015064  jz      short loc_180015077
0x180015066  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18001506b  test    eax, eax
0x18001506d  js      short loc_180015077
0x18001506f  xor     ecx, ecx
0x180015071  call    cs:__imp_NtdsaExtSetGlobalTransactionType
0x180015077  mov     r14b, 1
0x18001507a  mov     [rsp+78h+var_48], r14b
0x18001507f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015086  test    dword ptr [rcx+44h], 20000h
0x18001508d  jz      short loc_1800150AC
0x18001508f  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180015097  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18001509e  mov     rcx, [rcx+38h]
0x1800150a2  mov     edx, 49h ; 'I'
0x1800150a7  call    WPP_SF_d
0x1800150ac  cmp     cs:?SampUseDsData@@3EA, 1; uchar SampUseDsData
0x1800150b3  lea     rax, [rsp+78h+var_44]
0x1800150b8  mov     ebp, 2
0x1800150bd  mov     [rsp+78h+var_58], rax
0x1800150c2  cmovz   edi, ebp
0x1800150c5  mov     edx, 20h ; ' '
0x1800150ca  xor     r9d, r9d
0x1800150cd  xor     r8d, r8d
0x1800150d0  mov     rcx, r13
0x1800150d3  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x1800150d8  mov     ebx, eax
0x1800150da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150e1  test    dword ptr [rcx+44h], 20000h
0x1800150e8  jz      short loc_180015106
0x1800150ea  mov     rcx, [rcx+38h]
0x1800150ee  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x1800150f5  mov     edx, 10h
0x1800150fa  mov     dword ptr [rsp+78h+var_58], eax
0x1800150fe  mov     r9d, eax
0x180015101  call    WPP_SF_Dd
0x180015106  test    ebx, ebx
0x180015108  js      loc_1800152E5
0x18001510e  xor     r14d, r14d
0x180015111  mov     ebx, 0C00000DFh
0x180015116  xor     al, al
0x180015118  mov     [rsp+78h+arg_18], al
0x18001511f  cmp     edi, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x180015125  jnb     loc_1800152D3
0x18001512b  test    al, al
0x18001512d  jnz     loc_1800152D3
0x180015133  mov     eax, edi
0x180015135  imul    rbp, rax, 550h
0x18001513c  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180015143  movzx   ecx, word ptr [rax+rbp+528h]
0x18001514b  mov     r12, [rax+rbp+530h]
0x180015153  mov     [rsp+78h+var_46], cx
0x180015158  test    r14, r14
0x18001515b  jz      short loc_18001516E
0x18001515d  mov     rcx, r14; hMem
0x180015160  call    cs:__imp_LocalFree
0x180015166  movzx   ecx, [rsp+78h+var_46]
0x18001516b  xor     r14d, r14d
0x18001516e  test    r12, r12
0x180015171  jz      short loc_1800151B5
0x180015173  movzx   eax, cx
0x180015176  mov     ecx, 40h ; '@'; uFlags
0x18001517b  mov     [rsp+78h+Size], rax
0x180015180  lea     rdx, [rax+2]; uBytes
0x180015184  call    cs:__imp_LocalAlloc
0x18001518a  mov     r14, rax
0x18001518d  test    rax, rax
0x180015190  jz      loc_180015272
0x180015196  mov     r8, [rsp+78h+Size]; Size
0x18001519b  mov     rdx, r12; Src
0x18001519e  mov     rcx, rax; void *
0x1800151a1  call    memcpy_0
0x1800151a6  mov     rcx, [rsp+78h+Size]
0x1800151ab  shr     rcx, 1
0x1800151ae  xor     eax, eax
0x1800151b0  mov     [r14+rcx*2], ax
0x1800151b5  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800151bc  mov     rdx, rsi; DomainName2
0x1800151bf  add     rcx, 10h
0x1800151c3  add     rcx, rbp; DomainName1
0x1800151c6  call    cs:__imp_RtlEqualDomainName
0x1800151cc  test    al, al
0x1800151ce  jnz     short loc_180015203
0x1800151d0  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800151d7  mov     r8b, 1; CaseInsensitive
0x1800151da  add     rcx, 10h
0x1800151de  mov     rdx, rsi; String2
0x1800151e1  add     rcx, rbp; String1
0x1800151e4  call    cs:__imp_RtlEqualUnicodeString
0x1800151ea  test    al, al
0x1800151ec  jnz     short loc_180015203
0x1800151ee  test    r14, r14
0x1800151f1  jz      short loc_180015263
0x1800151f3  mov     rdx, r15; pName2
0x1800151f6  mov     rcx, r14; pName1
0x1800151f9  call    cs:__imp_DnsNameCompare_W
0x1800151ff  test    eax, eax
0x180015201  jz      short loc_180015263
0x180015203  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18001520a  mov     rcx, [rcx+rbp+8]; Sid
0x18001520f  call    cs:__imp_RtlLengthSid
0x180015215  mov     edx, eax; uBytes
0x180015217  mov     ecx, 40h ; '@'; uFlags
0x18001521c  mov     ebx, eax
0x18001521e  call    cs:__imp_LocalAlloc
0x180015224  mov     r12, rax
0x180015227  test    rax, rax
0x18001522a  jz      loc_1800152CC
0x180015230  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180015237  mov     rdx, rax; DestinationSid
0x18001523a  mov     ecx, ebx; DestinationSidLength
0x18001523c  mov     r8, [r8+rbp+8]; SourceSid
0x180015241  call    cs:__imp_RtlCopySid
0x180015247  mov     ebx, eax
0x180015249  test    eax, eax
0x18001524b  js      short loc_1800152BC
0x18001524d  mov     rcx, [rsp+78h+arg_10]
0x180015255  mov     al, 1
0x180015257  mov     [rsp+78h+arg_18], al
0x18001525e  mov     [rcx], r12
0x180015261  jmp     short loc_18001526B
0x180015263  movzx   eax, [rsp+78h+arg_18]
0x18001526b  inc     edi
0x18001526d  jmp     loc_18001511F
0x180015272  mov     ebx, 0C0000017h
0x180015277  xor     edx, edx
0x180015279  mov     rcx, r13
0x18001527c  call    SampDeReferenceContext
0x180015281  movzx   ecx, [rsp+78h+var_48]; unsigned __int8
0x180015286  call    ?SampMaybeReleaseReadLock@@YAXE@Z; SampMaybeReleaseReadLock(uchar)
0x18001528b  mov     rcx, r15; hMem
0x18001528e  call    cs:__imp_LocalFree
0x180015294  test    r14, r14
0x180015297  jz      short loc_1800152A2
0x180015299  mov     rcx, r14; hMem
0x18001529c  call    cs:__imp_LocalFree
0x1800152a2  mov     r12, [rsp+78h+arg_10]
0x1800152aa  mov     ebp, 2
0x1800152af  mov     r14, [rsp+78h+var_30]
0x1800152b4  test    ebx, ebx
0x1800152b6  jns     short loc_180015316
0x1800152b8  xor     edi, edi
0x1800152ba  jmp     short loc_180015303
0x1800152bc  mov     rcx, r12; hMem
0x1800152bf  call    cs:__imp_LocalFree
0x1800152c5  mov     ebx, 0C00000E5h
0x1800152ca  jmp     short loc_180015277
0x1800152cc  mov     ebx, 0C000009Ah
0x1800152d1  jmp     short loc_180015277
0x1800152d3  test    ebx, ebx
0x1800152d5  js      short loc_180015277
0x1800152d7  xor     edx, edx
0x1800152d9  mov     rcx, r13
0x1800152dc  call    SampDeReferenceContext
0x1800152e1  mov     ebx, eax
0x1800152e3  jmp     short loc_180015281
0x1800152e5  movzx   ecx, r14b; unsigned __int8
0x1800152e9  call    ?SampMaybeReleaseReadLock@@YAXE@Z; SampMaybeReleaseReadLock(uchar)
0x1800152ee  mov     rcx, r15; hMem
0x1800152f1  call    cs:__imp_LocalFree
0x1800152f7  jmp     short loc_1800152AF
0x1800152f9  mov     ebx, 0C000000Dh
0x1800152fe  mov     ebp, 2
0x180015303  mov     rcx, [r12]; hMem
0x180015307  test    rcx, rcx
0x18001530a  jz      short loc_180015316
0x18001530c  call    cs:__imp_LocalFree
0x180015312  mov     [r12], rdi
0x180015316  mov     r8d, ebx
0x180015319  mov     edx, 5
0x18001531e  mov     ecx, ebp
0x180015320  call    SampTraceEvent
0x180015325  mov     r15, [rsp+78h+var_38]
0x18001532a  mov     r13, [rsp+78h+var_28]
0x18001532f  mov     rdi, [rsp+78h+var_18]
0x180015334  mov     rsi, [rsp+78h+var_10]
0x180015339  mov     rbp, [rsp+78h+arg_0]
0x180015341  test    ebx, ebx
0x180015343  js      short loc_180015373
0x180015345  mov     rcx, cs:WPP_GLOBAL_Control
0x18001534c  test    byte ptr [rcx+44h], 8
0x180015350  jz      short loc_1800153A5
0x180015352  cmp     byte ptr [rcx+41h], 4
0x180015356  jb      short loc_1800153A5
0x180015358  mov     r9, [r12]
0x18001535c  lea     r8, WPP_a5e011badb8432b034189f08c175cf46_Traceguids
0x180015363  mov     rcx, [rcx+38h]
0x180015367  mov     edx, 28h ; '('
0x18001536c  call    WPP_SF__sid_
0x180015371  jmp     short loc_18001539E
0x180015373  mov     rcx, cs:WPP_GLOBAL_Control
0x18001537a  test    byte ptr [rcx+44h], 8
0x18001537e  jz      short loc_1800153A5
0x180015380  cmp     byte ptr [rcx+41h], 2
0x180015384  jb      short loc_1800153A5
0x180015386  mov     rcx, [rcx+38h]
  ... truncated ...
```
