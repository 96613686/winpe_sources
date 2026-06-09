# SampCreateContextEx

- ea: `0x180006800`
- end: `0x18000706b`
- name: `SampCreateContextEx`
- size: `2155`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char, char, char, char, _DWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006170`
- `0x180007bd0`
- `0x180012d60`
- `0x180024d6c`
- `0x180028bec`
- `0x18005c2e0`
- `0x18005c4a0`
- `0x180072b30`
- `0x1800799a8`

## callees

- `0x180006800`
- `0x18001e900`
- `0x180024054`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a80`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180006a5c`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180006a5c`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180006a36`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180006a36`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006a24`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006a24`
- `ntdll!RtlInitializeBitMap` at `0x180006981`
- `ntdll!RtlInitializeBitMap` at `0x1800069a3`
- `ntdll!RtlInitializeBitMap` at `0x1800069c7`
- `ntdll!RtlInitializeBitMap` at `0x180006981`
- `ntdll!RtlInitializeBitMap` at `0x1800069a3`
- `ntdll!RtlInitializeBitMap` at `0x1800069c7`
- `ntdll!RtlClearAllBits` at `0x18000698b`
- `ntdll!RtlClearAllBits` at `0x1800069ad`
- `ntdll!RtlClearAllBits` at `0x1800069d4`
- `ntdll!RtlClearAllBits` at `0x18000698b`
- `ntdll!RtlClearAllBits` at `0x1800069ad`
- `ntdll!RtlClearAllBits` at `0x1800069d4`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b1e`
- `ntdll!RtlLeaveCriticalSection` at `0x180006ba8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006c1b`
- `ntdll!RtlLeaveCriticalSection` at `0x180006e60`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b1e`
- `ntdll!RtlLeaveCriticalSection` at `0x180006ba8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006c1b`
- `ntdll!RtlLeaveCriticalSection` at `0x180006e60`
- `ntdll!RtlEnterCriticalSection` at `0x180006ae9`
- `ntdll!RtlEnterCriticalSection` at `0x180006b73`
- `ntdll!RtlEnterCriticalSection` at `0x180006be6`
- `ntdll!RtlEnterCriticalSection` at `0x180006e2b`
- `ntdll!RtlEnterCriticalSection` at `0x180006ae9`
- `ntdll!RtlEnterCriticalSection` at `0x180006b73`
- `ntdll!RtlEnterCriticalSection` at `0x180006be6`
- `ntdll!RtlEnterCriticalSection` at `0x180006e2b`
- `ntdll!RtlInitUnicodeString` at `0x18000688d`
- `ntdll!RtlInitUnicodeString` at `0x18000688d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006ee7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006ee7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000683d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000683d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007045`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007045`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180006f28`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180006f28`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtClassFromSamObjectType` at `0x180006f45`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtClassFromSamObjectType` at `0x180006f45`

## string_xrefs

- `0x180006ec3`: `DirectoryServiceExtPt`
- `0x180006edb`: `SYSTEM\CurrentControlSet\Services\NTDS`

## pseudocode

```c
__int64 __fastcall SampCreateContextEx(
        unsigned int a1,
        char a2,
        char a3,
        char a4,
        char a5,
        char a6,
        char a7,
        char a8,
        unsigned int a9)
{
  HLOCAL v13; // rax
  __int64 v14; // rbx
  bool v15; // r12
  char v16; // r8
  char v17; // r8
  bool v18; // cl
  char v19; // al
  char v20; // cl
  int v21; // eax
  int v22; // edi
  int v23; // edi
  unsigned int v24; // esi
  unsigned int v25; // esi
  __int64 *v26; // rcx
  __int64 *v27; // rcx
  __int64 *v28; // rcx
  __int64 *v30; // rcx
  __int64 v31; // rax
  unsigned __int8 NewElement[8]; // [rsp+50h] [rbp-278h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-270h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-268h] BYREF

  v13 = LocalAlloc(0x40u, 0x5B8u);
  v14 = (__int64)v13;
  if ( !v13 )
    return v14;
  memset_0(v13, 0, 0x5B8u);
  if ( a2 || a4 || (int)SampIncrementActiveContextCount((struct _SAMP_OBJECT *)v14) >= 0 )
  {
    *(_DWORD *)(v14 + 16) = a1;
    *(_QWORD *)(v14 + 144) = 1;
    *(_QWORD *)(v14 + 152) = -1;
    RtlInitUnicodeString((PUNICODE_STRING)(v14 + 160), 0);
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    v15 = 0;
    if ( SampUseDsData )
    {
      if ( SampDefinedDomains )
      {
        v31 = *((_QWORD *)SampDefinedDomains + 170 * a9);
        if ( v31 )
        {
          if ( (*(_BYTE *)(v31 + 192) & 2) != 0 )
            v15 = 1;
        }
      }
    }
    v16 = *(_BYTE *)(v14 + 20);
    *(_BYTE *)(v14 + 208) = 0;
    *(_QWORD *)(v14 + 112) = 0;
    *(_QWORD *)(v14 + 136) = 0;
    v17 = (a4 << 7) | ((32 * a2) ^ v16 & 0xC) & 0x2C;
    *(_DWORD *)(v14 + 120) = 0;
    v18 = a3 || a4;
    v19 = v18 | *(_BYTE *)(v14 + 28) & 0xFE;
    *(_BYTE *)(v14 + 29) &= 0xE1u;
    *(_BYTE *)(v14 + 20) = v17 & 0xF3;
    *(_DWORD *)(v14 + 204) = 1;
    v20 = v19 & 0xFD ^ (v19 & 0xFD ^ (4 * a5)) & 4;
    *(_BYTE *)(v14 + 28) = (a8 << 7) | ((16 * a7) ^ (v20 ^ (v20 ^ (8 * a6)) & 8) & 0xF) & 0x1F;
    *(_QWORD *)(v14 + 124) = 0;
    RtlInitializeBitMap((PRTL_BITMAP)(v14 + 96), (PULONG)(v14 + 72), 0x8Cu);
    RtlClearAllBits((PRTL_BITMAP)(v14 + 96));
    *(_BYTE *)(v14 + 29) &= ~1u;
    RtlInitializeBitMap((PRTL_BITMAP)(v14 + 56), (PULONG)(v14 + 32), 0x8Cu);
    RtlClearAllBits((PRTL_BITMAP)(v14 + 56));
    RtlInitializeBitMap((PRTL_BITMAP)(v14 + 232), (PULONG)(v14 + 212), 0x8Cu);
    RtlClearAllBits((PRTL_BITMAP)(v14 + 232));
    v21 = *(_DWORD *)(v14 + 192);
    if ( !v15 )
    {
      *(_DWORD *)(v14 + 192) = v21 & 0xFFFFFFFC | 1;
      v22 = 0;
      goto LABEL_11;
    }
    *(_DWORD *)(v14 + 192) = v21 & 0xFFFFFFFC | 2;
    v22 = -1;
    memset_0(String1, 0, 0x208u);
    LODWORD(Buffer) = 520;
    if ( !SampDsStopped )
    {
      if ( g_ShouldCallNtdsaApiset )
      {
LABEL_52:
        v22 = NtdsaExtClassFromSamObjectType(a1);
        goto LABEL_11;
      }
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\NTDS",
              L"DirectoryServiceExtPt",
              6u,
              0,
              String1,
              (LPDWORD)&Buffer)
        && (CompareStringEx(&Annotation, 1u, String1, -1, &Annotation, -1, 0, 0, 0) & 0xFFFFFFFD) != 0 )
      {
        g_ShouldCallNtdsaApiset = 1;
        goto LABEL_52;
      }
    }
LABEL_11:
    *(_DWORD *)(v14 + 196) = v22;
    *(_BYTE *)(v14 + 21) |= 1u;
    *(_QWORD *)(v14 + 176) = 0;
    *(_DWORD *)(v14 + 24) = -294125688;
    Buffer = v14;
    NewElement[0] = 0;
    RtlAcquireSRWLockExclusive(&SampClientContextLock);
    if ( RtlLookupElementGenericTableAvl(&SampClientContextTableAVL, &Buffer) )
    {
      v23 = -1073740008;
    }
    else if ( RtlInsertElementGenericTableAvl(&SampClientContextTableAVL, &Buffer, 8u, NewElement) )
    {
      v23 = 0;
      if ( !NewElement[0] )
        v23 = -1073741595;
    }
    else
    {
      v23 = -1073741801;
    }
    ReleaseSRWLockExclusive(&SampClientContextLock);
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        50,
        WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
        (unsigned int)v23,
        v23);
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          40,
          WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
          (unsigned int)v23,
          v23);
    }
    if ( v23 < 0 )
    {
      if ( !a2 && !a4 )
        SampDecrementActiveContextCount(*(void **)(v14 + 184));
      goto LABEL_66;
    }
    *(_DWORD *)(v14 + 200) = a9;
    if ( a1 == 2 )
    {
      if ( (*(_BYTE *)(v14 + 28) & ((*(_BYTE *)(v14 + 192) & 2) != 0)) == 0 && !a8 )
      {
        RtlEnterCriticalSection(&SampContextListCritSect);
        v27 = (__int64 *)qword_1800EEEC0;
        if ( *(struct _SAMP_OBJECT ***)qword_1800EEEC0 != &SampContextListHead )
          goto LABEL_69;
        *(_QWORD *)(v14 + 8) = qword_1800EEEC0;
        *(_QWORD *)v14 = &SampContextListHead;
        *v27 = v14;
        qword_1800EEEC0 = v14;
        RtlLeaveCriticalSection(&SampContextListCritSect);
      }
      *(_DWORD *)(v14 + 252) = 2;
      *(_DWORD *)(v14 + 256) = 2;
      goto LABEL_26;
    }
    if ( a1 )
    {
      v24 = a1 - 1;
      if ( v24 )
      {
        v25 = v24 - 2;
        if ( v25 )
        {
          if ( v25 != 1 )
            return v14;
          if ( ((*(_BYTE *)(v14 + 28) & 1) == 0 || (*(_BYTE *)(v14 + 192) & 2) == 0) && !a8 )
          {
            RtlEnterCriticalSection(&SampContextListCritSect);
            v28 = (__int64 *)qword_1800EEEC0;
            if ( *(struct _SAMP_OBJECT ***)qword_1800EEEC0 != &SampContextListHead )
              goto LABEL_69;
            *(_QWORD *)(v14 + 8) = qword_1800EEEC0;
            *(_QWORD *)v14 = &SampContextListHead;
            *v28 = v14;
            qword_1800EEEC0 = v14;
            RtlLeaveCriticalSection(&SampContextListCritSect);
          }
          *(_WORD *)(v14 + 326) = 0;
          *(_QWORD *)(v14 + 288) = 0;
          *(_OWORD *)(v14 + 252) = xmmword_1800CA310;
          *(_DWORD *)(v14 + 296) = 0;
          *(_BYTE *)(v14 + 300) = 0;
          *(_QWORD *)(v14 + 304) = 0;
          *(_QWORD *)(v14 + 328) = 0;
          *(_QWORD *)(v14 + 312) = 0;
          *(_DWORD *)(v14 + 320) = 0;
          *(_BYTE *)(v14 + 324) = 0;
          *(_OWORD *)(v14 + 336) = 0;
          *(_BYTE *)(v14 + 352) = 1;
          *(_BYTE *)(v14 + 385) = 0;
          *(_QWORD *)(v14 + 528) = 0;
          *(_BYTE *)(v14 + 536) = 0;
          *(_QWORD *)(v14 + 544) = 0;
          *(_BYTE *)(v14 + 552) = 0;
          *(_DWORD *)(v14 + 556) = 1;
          *(_BYTE *)(v14 + 560) = 0;
          *(_DWORD *)(v14 + 564) = 0;
          *(_BYTE *)(v14 + 568) = 0;
          *(_DWORD *)(v14 + 572) = 0;
          *(_BYTE *)(v14 + 576) = 0;
          *(_QWORD *)(v14 + 584) = 0;
          *(_BYTE *)(v14 + 592) = 0;
          *(_QWORD *)(v14 + 600) = 0;
          *(_DWORD *)(v14 + 596) = 0;
          *(_WORD *)(v14 + 608) = 0;
          *(_OWORD *)(v14 + 616) = 0;
          *(_BYTE *)(v14 + 632) = 0;
          *(_OWORD *)(v14 + 640) = 0;
          *(_QWORD *)(v14 + 656) = 0;
          *(_QWORD *)(v14 + 664) = 0;
          *(_QWORD *)(v14 + 672) = 0;
          *(_BYTE *)(v14 + 728) = 0;
          *(_QWORD *)(v14 + 736) = 0;
          *(_BYTE *)(v14 + 752) = 0;
          *(_DWORD *)(v14 + 772) = 0;
          *(_OWORD *)(v14 + 756) = xmmword_1800CA310;
          *(_BYTE *)(v14 + 776) = 0;
          *(_DWORD *)(v14 + 796) = 0;
          *(_BYTE *)(v14 + 800) = 0;
          *(_OWORD *)(v14 + 780) = xmmword_1800CA310;
          *(_QWORD *)(v14 + 832) = 0;
          *(_DWORD *)(v14 + 840) = 0;
          *(_QWORD *)(v14 + 816) = 0;
          *(_DWORD *)(v14 + 824) = 0;
          *(_DWORD *)(v14 + 808) = 30;
          *(_BYTE *)(v14 + 812) = 0;
          *(_DWORD *)(v14 + 848) = 0;
          return v14;
        }
        if ( (*(_BYTE *)(v14 + 28) & ((*(_BYTE *)(v14 + 192) & 2) != 0)) != 0 || a8 )
          goto LABEL_25;
        RtlEnterCriticalSection(&SampContextListCritSect);
        v26 = (__int64 *)qword_1800EEEC0;
        if ( *(struct _SAMP_OBJECT ***)qword_1800EEEC0 == &SampContextListHead )
        {
          *(_QWORD *)(v14 + 8) = qword_1800EEEC0;
          *(_QWORD *)v14 = &SampContextListHead;
          *v26 = v14;
          qword_1800EEEC0 = v14;
          RtlLeaveCriticalSection(&SampContextListCritSect);
LABEL_25:
          *(_DWORD *)(v14 + 252) = 1;
          *(_DWORD *)(v14 + 256) = 1;
LABEL_26:
          *(_QWORD *)(v14 + 272) = 0;
          *(_QWORD *)(v14 + 264) = 0;
          *(_BYTE *)(v14 + 260) = 1;
          return v14;
        }
LABEL_69:
        __fastfail(3u);
      }
      *(_QWORD *)(v14 + 256) = 0;
      *(_QWORD *)(v14 + 268) = 0;
      *(_DWORD *)(v14 + 264) = 0;
      *(_DWORD *)(v14 + 276) = 0;
      *(_QWORD *)(v14 + 288) = v14 + 280;
      *(_QWORD *)(v14 + 280) = v14 + 280;
    }
    if ( (*(_BYTE *)(v14 + 28) & ((*(_BYTE *)(v14 + 192) & 2) != 0)) != 0 || a8 )
      return v14;
    RtlEnterCriticalSection(&SampContextListCritSect);
    v30 = (__int64 *)qword_1800EEEC0;
    if ( *(struct _SAMP_OBJECT ***)qword_1800EEEC0 == &SampContextListHead )
    {
      *(_QWORD *)(v14 + 8) = qword_1800EEEC0;
      *(_QWORD *)v14 = &SampContextListHead;
      *v30 = v14;
      qword_1800EEEC0 = v14;
      RtlLeaveCriticalSection(&SampContextListCritSect);
      return v14;
    }
    goto LABEL_69;
  }
LABEL_66:
  LocalFree((HLOCAL)v14);
  return 0;
}

```

## disassembly

```asm
0x180006800  push    rbx
0x180006802  push    rbp
0x180006803  push    rsi
0x180006804  push    rdi
0x180006805  push    r12
0x180006807  push    r13
0x180006809  push    r14
0x18000680b  push    r15
0x18000680d  sub     rsp, 288h
0x180006814  mov     rax, cs:__security_cookie
0x18000681b  xor     rax, rsp
0x18000681e  mov     [rsp+2C8h+var_58], rax
0x180006826  movzx   ebp, dl
0x180006829  mov     esi, ecx
0x18000682b  mov     edx, 5B8h; uBytes
0x180006830  mov     ecx, 40h ; '@'; uFlags
0x180006835  movzx   r15d, r9b
0x180006839  movzx   edi, r8b
0x18000683d  call    cs:__imp_LocalAlloc
0x180006843  mov     rbx, rax
0x180006846  test    rax, rax
0x180006849  jz      loc_180006D93
0x18000684f  xor     edx, edx; Val
0x180006851  mov     r8d, 5B8h; Size
0x180006857  mov     rcx, rax; void *
0x18000685a  call    memset_0
0x18000685f  test    bpl, bpl
0x180006862  jz      loc_180006DBA
0x180006868  xor     r13d, r13d
0x18000686b  mov     [rbx+10h], esi
0x18000686e  lea     rcx, [rbx+0A0h]; DestinationString
0x180006875  mov     qword ptr [rbx+90h], 1
0x180006880  xor     edx, edx; SourceString
0x180006882  mov     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x18000688d  call    cs:__imp_RtlInitUnicodeString
0x180006893  mov     rcx, cs:WPP_GLOBAL_Control
0x18000689a  test    dword ptr [rcx+44h], 20000h
0x1800068a1  jnz     loc_180006F52
0x1800068a7  cmp     cs:?SampUseDsData@@3EA, r13b; uchar SampUseDsData
0x1800068ae  mov     r14d, [rsp+2C8h+arg_40]
0x1800068b6  jnz     loc_180006F74
0x1800068bc  xor     r12b, r12b
0x1800068bf  movzx   r8d, byte ptr [rbx+14h]
0x1800068c4  movzx   eax, bpl
0x1800068c8  and     r8b, 0Ch
0x1800068cc  shl     al, 5
0x1800068cf  xor     r8b, al
0x1800068d2  mov     [rbx+0D0h], r13b
0x1800068d9  and     r8b, 2Ch
0x1800068dd  mov     [rbx+70h], r13
0x1800068e1  movzx   eax, r15b
0x1800068e5  mov     [rbx+88h], r13
0x1800068ec  shl     al, 7
0x1800068ef  or      r8b, al
0x1800068f2  mov     [rbx+78h], r13d
0x1800068f6  test    dil, dil
0x1800068f9  jz      loc_180006FAD
0x1800068ff  mov     cl, 1
0x180006901  movzx   eax, byte ptr [rbx+1Ch]
0x180006905  and     r8b, 0F3h
0x180006909  movzx   edx, [rsp+2C8h+arg_28]
0x180006911  and     al, 0FEh
0x180006913  movzx   r13d, [rsp+2C8h+arg_38]
0x18000691c  or      al, cl
0x18000691e  movzx   ecx, [rsp+2C8h+arg_20]
0x180006926  and     al, 0FDh
0x180006928  and     byte ptr [rbx+1Dh], 0E1h
0x18000692c  shl     dl, 3
0x18000692f  shl     cl, 2
0x180006932  xor     cl, al
0x180006934  mov     [rbx+14h], r8b
0x180006938  and     cl, 4
0x18000693b  mov     dword ptr [rbx+0CCh], 1
0x180006945  xor     cl, al
0x180006947  mov     r8d, 8Ch; SizeOfBitMap
0x18000694d  movzx   eax, [rsp+2C8h+arg_30]
0x180006955  xor     dl, cl
0x180006957  and     dl, 8
0x18000695a  shl     al, 4
0x18000695d  xor     dl, cl
0x18000695f  lea     rcx, [rbx+60h]; BitMapHeader
0x180006963  and     dl, 0Fh
0x180006966  xor     dl, al
0x180006968  movzx   eax, r13b
0x18000696c  shl     al, 7
0x18000696f  and     dl, 1Fh
0x180006972  or      dl, al
0x180006974  xor     eax, eax
0x180006976  mov     [rbx+1Ch], dl
0x180006979  lea     rdx, [rbx+48h]; BitMapBuffer
0x18000697d  mov     [rbx+7Ch], rax
0x180006981  call    cs:__imp_RtlInitializeBitMap
0x180006987  lea     rcx, [rbx+60h]; BitMapHeader
0x18000698b  call    cs:__imp_RtlClearAllBits
0x180006991  and     byte ptr [rbx+1Dh], 0FEh
0x180006995  lea     rdx, [rbx+20h]; BitMapBuffer
0x180006999  mov     r8d, 8Ch; SizeOfBitMap
0x18000699f  lea     rcx, [rbx+38h]; BitMapHeader
0x1800069a3  call    cs:__imp_RtlInitializeBitMap
0x1800069a9  lea     rcx, [rbx+38h]; BitMapHeader
0x1800069ad  call    cs:__imp_RtlClearAllBits
0x1800069b3  lea     rdx, [rbx+0D4h]; BitMapBuffer
0x1800069ba  mov     r8d, 8Ch; SizeOfBitMap
0x1800069c0  lea     rcx, [rbx+0E8h]; BitMapHeader
0x1800069c7  call    cs:__imp_RtlInitializeBitMap
0x1800069cd  lea     rcx, [rbx+0E8h]; BitMapHeader
0x1800069d4  call    cs:__imp_RtlClearAllBits
0x1800069da  mov     eax, [rbx+0C0h]
0x1800069e0  test    r12b, r12b
0x1800069e3  jnz     loc_180006E6B
0x1800069e9  and     eax, 0FFFFFFFDh
0x1800069ec  or      eax, 1
0x1800069ef  xor     r12d, r12d
0x1800069f2  mov     [rbx+0C0h], eax
0x1800069f8  mov     edi, r12d
0x1800069fb  mov     [rbx+0C4h], edi
0x180006a01  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x180006a08  or      byte ptr [rbx+15h], 1
0x180006a0c  mov     [rbx+0B0h], r12
0x180006a13  mov     dword ptr [rbx+18h], 0EE77FF88h
0x180006a1a  mov     [rsp+2C8h+Buffer], rbx
0x180006a1f  mov     [rsp+2C8h+NewElement], 0
0x180006a24  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180006a2a  lea     rdx, [rsp+2C8h+Buffer]; Buffer
0x180006a2f  lea     rcx, ?SampClientContextTableAVL@@3U_RTL_AVL_TABLE@@A; Table
0x180006a36  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180006a3c  test    rax, rax
0x180006a3f  jnz     loc_180006FBD
0x180006a45  lea     r9, [rsp+2C8h+NewElement]; NewElement
0x180006a4a  mov     r8d, 8; BufferSize
0x180006a50  lea     rdx, [rsp+2C8h+Buffer]; Buffer
0x180006a55  lea     rcx, ?SampClientContextTableAVL@@3U_RTL_AVL_TABLE@@A; Table
0x180006a5c  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180006a62  test    rax, rax
0x180006a65  jz      loc_180006FC7
0x180006a6b  cmp     [rsp+2C8h+NewElement], 0
0x180006a70  mov     edi, r12d
0x180006a73  jz      loc_180006FD1
0x180006a79  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180006a80  call    cs:__imp_ReleaseSRWLockExclusive
0x180006a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a8d  test    dword ptr [rcx+44h], 20000h
0x180006a94  jnz     loc_180006FDB
0x180006a9a  test    edi, edi
0x180006a9c  js      loc_18000702C
0x180006aa2  mov     [rbx+0C8h], r14d
0x180006aa9  cmp     esi, 2
0x180006aac  jz      loc_180006B56
0x180006ab2  test    esi, esi
0x180006ab4  jz      loc_180006E06
0x180006aba  sub     esi, 1
0x180006abd  jz      loc_180006DD8
0x180006ac3  sub     esi, 2
0x180006ac6  jnz     loc_180006BC7
0x180006acc  test    byte ptr [rbx+0C0h], 2
0x180006ad3  setnz   al
0x180006ad6  and     al, [rbx+1Ch]
0x180006ad9  test    al, 1
0x180006adb  jnz     short loc_180006B24
0x180006add  test    r13b, r13b
0x180006ae0  jnz     short loc_180006B24
0x180006ae2  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180006ae9  call    cs:__imp_RtlEnterCriticalSection
0x180006aef  mov     rcx, cs:qword_1800EEEC0
0x180006af6  lea     rax, ?SampContextListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY SampContextListHead
0x180006afd  cmp     [rcx], rax
0x180006b00  jnz     loc_180007064
0x180006b06  mov     [rbx+8], rcx
0x180006b0a  mov     [rbx], rax
0x180006b0d  mov     [rcx], rbx
0x180006b10  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180006b17  mov     cs:qword_1800EEEC0, rbx
0x180006b1e  call    cs:__imp_RtlLeaveCriticalSection
0x180006b24  mov     dword ptr [rbx+0FCh], 1
0x180006b2e  mov     dword ptr [rbx+100h], 1
0x180006b38  mov     [rbx+110h], r12
0x180006b3f  mov     qword ptr [rbx+108h], 0
0x180006b4a  mov     byte ptr [rbx+104h], 1
0x180006b51  jmp     loc_180006D93
0x180006b56  test    byte ptr [rbx+0C0h], 2
0x180006b5d  setnz   al
0x180006b60  and     al, [rbx+1Ch]
0x180006b63  test    al, 1
0x180006b65  jnz     short loc_180006BAE
0x180006b67  test    r13b, r13b
0x180006b6a  jnz     short loc_180006BAE
0x180006b6c  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180006b73  call    cs:__imp_RtlEnterCriticalSection
0x180006b79  mov     rcx, cs:qword_1800EEEC0
0x180006b80  lea     rax, ?SampContextListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY SampContextListHead
0x180006b87  cmp     [rcx], rax
0x180006b8a  jnz     loc_180007064
0x180006b90  mov     [rbx+8], rcx
0x180006b94  mov     [rbx], rax
0x180006b97  mov     [rcx], rbx
0x180006b9a  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180006ba1  mov     cs:qword_1800EEEC0, rbx
0x180006ba8  call    cs:__imp_RtlLeaveCriticalSection
0x180006bae  mov     dword ptr [rbx+0FCh], 2
0x180006bb8  mov     dword ptr [rbx+100h], 2
0x180006bc2  jmp     loc_180006B38
0x180006bc7  cmp     esi, 1
0x180006bca  jnz     loc_180006D93
0x180006bd0  test    [rbx+1Ch], sil
0x180006bd4  jnz     loc_180007052
0x180006bda  test    r13b, r13b
0x180006bdd  jnz     short loc_180006C21
0x180006bdf  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180006be6  call    cs:__imp_RtlEnterCriticalSection
0x180006bec  mov     rcx, cs:qword_1800EEEC0
0x180006bf3  lea     rax, ?SampContextListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY SampContextListHead
0x180006bfa  cmp     [rcx], rax
0x180006bfd  jnz     loc_180007064
0x180006c03  mov     [rbx+8], rcx
0x180006c07  mov     [rbx], rax
0x180006c0a  mov     [rcx], rbx
0x180006c0d  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180006c14  mov     cs:qword_1800EEEC0, rbx
0x180006c1b  call    cs:__imp_RtlLeaveCriticalSection
0x180006c21  movups  xmm1, cs:xmmword_1800CA310
0x180006c28  mov     word ptr [rbx+146h], 0
0x180006c31  xorps   xmm0, xmm0
0x180006c34  mov     [rbx+120h], r12
0x180006c3b  movups  xmmword ptr [rbx+0FCh], xmm1
0x180006c42  mov     [rbx+128h], r12d
0x180006c49  mov     byte ptr [rbx+12Ch], 0
0x180006c50  mov     [rbx+130h], r12
0x180006c57  mov     [rbx+148h], r12
0x180006c5e  mov     [rbx+138h], r12
0x180006c65  mov     [rbx+140h], r12d
0x180006c6c  mov     byte ptr [rbx+144h], 0
0x180006c73  movups  xmmword ptr [rbx+150h], xmm0
0x180006c7a  mov     byte ptr [rbx+160h], 1
0x180006c81  mov     byte ptr [rbx+181h], 0
0x180006c88  mov     [rbx+210h], r12
0x180006c8f  mov     byte ptr [rbx+218h], 0
0x180006c96  mov     [rbx+220h], r12
0x180006c9d  mov     byte ptr [rbx+228h], 0
0x180006ca4  mov     dword ptr [rbx+22Ch], 1
0x180006cae  mov     byte ptr [rbx+230h], 0
0x180006cb5  mov     [rbx+234h], r12d
0x180006cbc  mov     byte ptr [rbx+238h], 0
0x180006cc3  mov     [rbx+23Ch], r12d
0x180006cca  mov     byte ptr [rbx+240h], 0
0x180006cd1  mov     [rbx+248h], r12
0x180006cd8  mov     byte ptr [rbx+250h], 0
0x180006cdf  mov     [rbx+258h], r12
0x180006ce6  mov     [rbx+254h], r12d
0x180006ced  mov     word ptr [rbx+260h], 0
0x180006cf6  movups  xmmword ptr [rbx+268h], xmm0
0x180006cfd  mov     byte ptr [rbx+278h], 0
0x180006d04  movups  xmmword ptr [rbx+280h], xmm0
0x180006d0b  mov     [rbx+290h], r12
0x180006d12  mov     [rbx+298h], r12
0x180006d19  mov     [rbx+2A0h], r12
0x180006d20  mov     byte ptr [rbx+2D8h], 0
0x180006d27  mov     [rbx+2E0h], r12
0x180006d2e  mov     byte ptr [rbx+2F0h], 0
0x180006d35  mov     [rbx+304h], r12d
0x180006d3c  movups  xmmword ptr [rbx+2F4h], xmm1
0x180006d43  mov     byte ptr [rbx+308h], 0
0x180006d4a  mov     [rbx+31Ch], r12d
0x180006d51  mov     byte ptr [rbx+320h], 0
0x180006d58  movups  xmmword ptr [rbx+30Ch], xmm1
0x180006d5f  mov     [rbx+340h], r12
0x180006d66  mov     [rbx+348h], r12d
0x180006d6d  mov     [rbx+330h], r12
0x180006d74  mov     [rbx+338h], r12d
0x180006d7b  mov     dword ptr [rbx+328h], 1Eh
0x180006d85  mov     byte ptr [rbx+32Ch], 0
0x180006d8c  mov     [rbx+350h], r12d
0x180006d93  mov     rax, rbx
0x180006d96  mov     rcx, [rsp+2C8h+var_58]
0x180006d9e  xor     rcx, rsp; StackCookie
0x180006da1  call    __security_check_cookie
0x180006da6  add     rsp, 288h
0x180006dad  pop     r15
0x180006daf  pop     r14
0x180006db1  pop     r13
0x180006db3  pop     r12
0x180006db5  pop     rdi
0x180006db6  pop     rsi
0x180006db7  pop     rbp
0x180006db8  pop     rbx
0x180006db9  retn
0x180006dba  test    r15b, r15b
0x180006dbd  jnz     loc_180006868
0x180006dc3  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180006dc6  call    ?SampIncrementActiveContextCount@@YAJPEAU_SAMP_OBJECT@@@Z; SampIncrementActiveContextCount(_SAMP_OBJECT *)
0x180006dcb  test    eax, eax
0x180006dcd  jns     loc_180006868
0x180006dd3  jmp     loc_180007042
0x180006dd8  lea     rax, [rbx+118h]
0x180006ddf  mov     [rbx+100h], r12
0x180006de6  mov     qword ptr [rbx+10Ch], 0
0x180006df1  mov     [rbx+108h], r12d
0x180006df8  mov     [rbx+114h], r12d
0x180006dff  mov     [rax+8], rax
0x180006e03  mov     [rax], rax
0x180006e06  test    byte ptr [rbx+0C0h], 2
  ... truncated ...
```
