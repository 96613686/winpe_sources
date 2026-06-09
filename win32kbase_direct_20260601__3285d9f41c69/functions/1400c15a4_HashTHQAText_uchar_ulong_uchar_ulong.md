# _HashTHQAText(uchar *,ulong,uchar * *,ulong *)

- ea: `0x1400c15a4`
- end: `0x1400c1bae`
- name: `?_HashTHQAText@@YAHPEAEKPEAPEAEPEAK@Z`
- size: `1546`
- prototype: `__int64 __fastcall(PUCHAR pbInput, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400c1208`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x140072a90`
- `0x1400b1d40`
- `0x1400c15a4`

## import_xrefs

- `cng!BCryptCreateHash` at `0x1400c16dc`
- `cng!BCryptCreateHash` at `0x1400c16dc`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c15fc`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c15fc`
- `cng!BCryptGetProperty` at `0x1400c1633`
- `cng!BCryptGetProperty` at `0x1400c1689`
- `cng!BCryptGetProperty` at `0x1400c1633`
- `cng!BCryptGetProperty` at `0x1400c1689`
- `cng!BCryptHashData` at `0x1400c1700`
- `cng!BCryptHashData` at `0x1400c1700`
- `cng!BCryptFinishHash` at `0x1400c1724`
- `cng!BCryptFinishHash` at `0x1400c1724`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c1785`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c1785`
- `cng!BCryptDestroyHash` at `0x1400c1793`
- `cng!BCryptDestroyHash` at `0x1400c1793`
- `WIN32K!W32GetUserSessionState` at `0x1400c17d6`
- `WIN32K!W32GetUserSessionState` at `0x1400c1813`
- `WIN32K!W32GetUserSessionState` at `0x1400c18a8`
- `WIN32K!W32GetUserSessionState` at `0x1400c191c`
- `WIN32K!W32GetUserSessionState` at `0x1400c1944`
- `WIN32K!W32GetUserSessionState` at `0x1400c19d6`
- `WIN32K!W32GetUserSessionState` at `0x1400c1a97`
- `WIN32K!W32GetUserSessionState` at `0x1400c1b0b`
- `WIN32K!W32GetUserSessionState` at `0x1400c17d6`
- `WIN32K!W32GetUserSessionState` at `0x1400c1813`
- `WIN32K!W32GetUserSessionState` at `0x1400c18a8`
- `WIN32K!W32GetUserSessionState` at `0x1400c191c`
- `WIN32K!W32GetUserSessionState` at `0x1400c1944`
- `WIN32K!W32GetUserSessionState` at `0x1400c19d6`
- `WIN32K!W32GetUserSessionState` at `0x1400c1a97`
- `WIN32K!W32GetUserSessionState` at `0x1400c1b0b`

## pseudocode

```c
__int64 __fastcall _HashTHQAText(PUCHAR pbInput, __int64 a2, unsigned __int8 **a3, unsigned int *a4)
{
  UCHAR *v7; // r14
  unsigned int v8; // r12d
  __int64 v9; // rdx
  NTSTATUS v10; // esi
  __int64 v11; // r8
  __int64 v12; // rdx
  NTSTATUS Property; // esi
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  NTSTATUS v18; // esi
  __int64 v19; // r8
  unsigned __int8 *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  NTSTATUS v24; // esi
  __int64 v25; // r8
  __int64 v26; // rcx
  NTSTATUS v27; // esi
  __int64 v28; // r8
  __int64 v29; // rcx
  NTSTATUS v30; // esi
  __int64 v31; // r8
  char v33; // bl
  bool v34; // di
  int v35; // edx
  int v36; // r8d
  __int64 v37; // r9
  char v38; // bl
  bool v39; // di
  int v40; // edx
  int v41; // r8d
  __int64 v42; // r9
  __int16 v43; // [rsp+30h] [rbp-30h]
  __int16 v44; // [rsp+30h] [rbp-30h]
  char v45; // [rsp+40h] [rbp-20h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-8h] BYREF
  ULONG v48; // [rsp+A8h] [rbp+48h] BYREF
  ULONG pbOutput; // [rsp+B0h] [rbp+50h] BYREF
  ULONG pcbResult; // [rsp+B8h] [rbp+58h] BYREF

  *a3 = 0;
  *a4 = 0;
  pcbResult = 0;
  v48 = 0;
  pbOutput = 0;
  phAlgorithm = 0;
  v7 = 0;
  phHash = 0;
  v8 = 0;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v10 >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v33 = 0;
      }
      v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v45 = Property;
        v37 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v12, v14) + 19408);
        v43 = 19;
        goto LABEL_27;
      }
      goto LABEL_10;
    }
    v7 = (UCHAR *)Win32AllocPoolZInitImpl(0x100u, pbOutput, 0x63707355u);
    if ( v7 )
    {
      v18 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&v48, 4u, &pcbResult, 0);
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (v17 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v17 & 1) == 0)
          || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
        {
          v33 = 0;
        }
        v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v45 = v18;
          v37 = *(_QWORD *)(W32GetUserSessionState(v17, WPP_GLOBAL_Control, v19) + 19408);
          v43 = 21;
          goto LABEL_27;
        }
        goto LABEL_10;
      }
      v20 = (unsigned __int8 *)Win32AllocPoolZInitImpl(0x100u, v48, 0x63707355u);
      *a3 = v20;
      if ( v20 )
      {
        v24 = BCryptCreateHash(phAlgorithm, &phHash, v7, pbOutput, 0, 0, 0);
        if ( v24 < 0 )
        {
          if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
            || (v23 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v23 & 1) == 0)
            || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
          {
            v33 = 0;
          }
          v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v45 = v24;
            v37 = *(_QWORD *)(W32GetUserSessionState(v23, WPP_GLOBAL_Control, v25) + 19408);
            v43 = 23;
            goto LABEL_27;
          }
        }
        else
        {
          v27 = BCryptHashData(phHash, pbInput, 4u, 0);
          if ( v27 < 0 )
          {
            if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
              || (v26 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v26 & 1) == 0)
              || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
            {
              v33 = 0;
            }
            v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v45 = v27;
              v37 = *(_QWORD *)(W32GetUserSessionState(v26, WPP_GLOBAL_Control, v28) + 19408);
              v43 = 24;
              goto LABEL_27;
            }
          }
          else
          {
            v30 = BCryptFinishHash(phHash, *a3, v48, 0);
            if ( v30 >= 0 )
            {
              v8 = 1;
              *a4 = v48;
              goto LABEL_10;
            }
            if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
              || (v29 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v29 & 1) == 0)
              || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
            {
              v33 = 0;
            }
            v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v45 = v30;
              v37 = *(_QWORD *)(W32GetUserSessionState(v29, WPP_GLOBAL_Control, v31) + 19408);
              v43 = 25;
              goto LABEL_27;
            }
          }
        }
        goto LABEL_10;
      }
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v38 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v38 = 0;
      }
      v39 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v38 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_10;
      v42 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v21, v22) + 19408);
      v44 = 22;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (v15 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v15 & 1) == 0)
        || (v38 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v38 = 0;
      }
      v39 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v38 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_10;
      v42 = *(_QWORD *)(W32GetUserSessionState(v15, WPP_GLOBAL_Control, v16) + 19408);
      v44 = 20;
    }
    LOBYTE(v41) = v39;
    LOBYTE(v40) = v38;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v40,
      v41,
      v42,
      3,
      1,
      v44,
      (__int64)WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids);
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
  {
    v33 = 0;
  }
  v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v45 = v10;
    v37 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v9, v11) + 19408);
    v43 = 18;
LABEL_27:
    LOBYTE(v36) = v34;
    LOBYTE(v35) = v33;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v35,
      v36,
      v37,
      3,
      1,
      v43,
      (__int64)WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids,
      v45);
  }
LABEL_10:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v7 )
    GreDeleteFastMutex(v7);
  if ( !v8 && *a3 )
  {
    GreDeleteFastMutex(*a3);
    *a3 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1400c15a4  mov     [rsp-38h+arg_0], rbx
0x1400c15a9  mov     [rsp-38h+arg_8], edx
0x1400c15ad  push    rbp
0x1400c15ae  push    rsi
0x1400c15af  push    rdi
0x1400c15b0  push    r12
0x1400c15b2  push    r13
0x1400c15b4  push    r14
0x1400c15b6  push    r15
0x1400c15b8  mov     rbp, rsp
0x1400c15bb  sub     rsp, 60h
0x1400c15bf  xor     r13d, r13d
0x1400c15c2  lea     rdx, aSha256; "SHA256"
0x1400c15c9  mov     [r8], r13
0x1400c15cc  mov     rbx, r9
0x1400c15cf  mov     [r9], r13d
0x1400c15d2  mov     r15, r8
0x1400c15d5  mov     rdi, rcx
0x1400c15d8  mov     [rbp+arg_18], r13d
0x1400c15dc  xor     r9d, r9d; dwFlags
0x1400c15df  mov     [rbp+arg_8], r13d
0x1400c15e3  xor     r8d, r8d; pszImplementation
0x1400c15e6  mov     [rbp+pbOutput], r13d
0x1400c15ea  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400c15ee  mov     [rbp+phAlgorithm], r13
0x1400c15f2  mov     r14d, r13d
0x1400c15f5  mov     [rbp+phHash], r13
0x1400c15f9  mov     r12d, r13d
0x1400c15fc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c1603  nop     dword ptr [rax+rax+00h]
0x1400c1608  mov     esi, eax
0x1400c160a  test    eax, eax
0x1400c160c  js      loc_1400C17A1
0x1400c1612  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400c1616  lea     rax, [rbp+arg_18]
0x1400c161a  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x1400c161f  lea     r9d, [r13+4]; cbOutput
0x1400c1623  lea     r8, [rbp+pbOutput]; pbOutput
0x1400c1627  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400c162c  lea     rdx, pszProperty; "ObjectLength"
0x1400c1633  call    cs:__imp_BCryptGetProperty
0x1400c163a  nop     dword ptr [rax+rax+00h]
0x1400c163f  mov     esi, eax
0x1400c1641  test    eax, eax
0x1400c1643  js      loc_1400C1864
0x1400c1649  mov     edx, [rbp+pbOutput]; unsigned __int64
0x1400c164c  mov     ecx, 100h; unsigned __int64
0x1400c1651  mov     r8d, 63707355h; unsigned int
0x1400c1657  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400c165c  mov     r14, rax
0x1400c165f  test    rax, rax
0x1400c1662  jz      loc_1400C18D7
0x1400c1668  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400c166c  lea     rax, [rbp+arg_18]
0x1400c1670  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x1400c1675  lea     r9d, [r13+4]; cbOutput
0x1400c1679  lea     r8, [rbp+arg_8]; pbOutput
0x1400c167d  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400c1682  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400c1689  call    cs:__imp_BCryptGetProperty
0x1400c1690  nop     dword ptr [rax+rax+00h]
0x1400c1695  mov     esi, eax
0x1400c1697  test    eax, eax
0x1400c1699  js      loc_1400C1991
0x1400c169f  mov     edx, [rbp+arg_8]; unsigned __int64
0x1400c16a2  mov     ecx, 100h; unsigned __int64
0x1400c16a7  mov     r8d, 63707355h; unsigned int
0x1400c16ad  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400c16b2  mov     [r15], rax
0x1400c16b5  test    rax, rax
0x1400c16b8  jz      loc_1400C1A05
0x1400c16be  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1400c16c2  lea     rdx, [rbp+phHash]; phHash
0x1400c16c6  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400c16ca  mov     r8, r14; pbHashObject
0x1400c16cd  mov     dword ptr [rsp+60h+var_30], r13d; dwFlags
0x1400c16d2  mov     [rsp+60h+dwFlags], r13d; cbSecret
0x1400c16d7  mov     [rsp+60h+pcbResult], r13; pbSecret
0x1400c16dc  call    cs:__imp_BCryptCreateHash
0x1400c16e3  nop     dword ptr [rax+rax+00h]
0x1400c16e8  mov     esi, eax
0x1400c16ea  test    eax, eax
0x1400c16ec  js      loc_1400C1A52
0x1400c16f2  mov     rcx, [rbp+phHash]; hHash
0x1400c16f6  lea     r8d, [r13+4]; cbInput
0x1400c16fa  xor     r9d, r9d; dwFlags
0x1400c16fd  mov     rdx, rdi; pbInput
0x1400c1700  call    cs:__imp_BCryptHashData
0x1400c1707  nop     dword ptr [rax+rax+00h]
0x1400c170c  mov     esi, eax
0x1400c170e  test    eax, eax
0x1400c1710  js      loc_1400C1AC6
0x1400c1716  mov     r8d, [rbp+arg_8]; cbOutput
0x1400c171a  xor     r9d, r9d; dwFlags
0x1400c171d  mov     rdx, [r15]; pbOutput
0x1400c1720  mov     rcx, [rbp+phHash]; hHash
0x1400c1724  call    cs:__imp_BCryptFinishHash
0x1400c172b  nop     dword ptr [rax+rax+00h]
0x1400c1730  mov     esi, eax
0x1400c1732  test    eax, eax
0x1400c1734  js      loc_1400C1B3A
0x1400c173a  mov     eax, [rbp+arg_8]
0x1400c173d  lea     r12d, [r13+1]
0x1400c1741  mov     [rbx], eax
0x1400c1743  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400c1747  test    rcx, rcx
0x1400c174a  jnz     short loc_1400C1783
0x1400c174c  mov     rcx, [rbp+phHash]; hHash
0x1400c1750  test    rcx, rcx
0x1400c1753  jnz     short loc_1400C1793
0x1400c1755  test    r14, r14
0x1400c1758  jnz     loc_1400C1B88
0x1400c175e  test    r12d, r12d
0x1400c1761  jz      loc_1400C1B95
0x1400c1767  mov     rbx, [rsp+60h+arg_0]
0x1400c176f  mov     eax, r12d
0x1400c1772  add     rsp, 60h
0x1400c1776  pop     r15
0x1400c1778  pop     r14
0x1400c177a  pop     r13
0x1400c177c  pop     r12
0x1400c177e  pop     rdi
0x1400c177f  pop     rsi
0x1400c1780  pop     rbp
0x1400c1781  retn
0x1400c1783  xor     edx, edx; dwFlags
0x1400c1785  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c178c  nop     dword ptr [rax+rax+00h]
0x1400c1791  jmp     short loc_1400C174C
0x1400c1793  call    cs:__imp_BCryptDestroyHash
0x1400c179a  nop     dword ptr [rax+rax+00h]
0x1400c179f  jmp     short loc_1400C1755
0x1400c17a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c17a8  lea     rax, WPP_GLOBAL_Control
0x1400c17af  cmp     rcx, rax
0x1400c17b2  jnz     short loc_1400C1802
0x1400c17b4  mov     bl, r13b
0x1400c17b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c17be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c17c5  setnz   dil
0x1400c17c9  test    bl, bl
0x1400c17cb  jnz     short loc_1400C17D6
0x1400c17cd  test    dil, dil
0x1400c17d0  jz      loc_1400C1743
0x1400c17d6  call    cs:__imp_W32GetUserSessionState
0x1400c17dd  nop     dword ptr [rax+rax+00h]
0x1400c17e2  mov     dword ptr [rsp+60h+var_20], esi
0x1400c17e6  mov     r9, [rax+4BD0h]
0x1400c17ed  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400c17f4  mov     [rsp+60h+var_28], rax
0x1400c17f9  mov     [rsp+60h+var_30], 12h
0x1400c1800  jmp     short loc_1400C183D
0x1400c1802  mov     eax, [rcx+2Ch]
0x1400c1805  test    al, 1
0x1400c1807  jz      short loc_1400C17B4
0x1400c1809  cmp     byte ptr [rcx+29h], 3
0x1400c180d  mov     bl, 1
0x1400c180f  jnb     short loc_1400C17B7
0x1400c1811  jmp     short loc_1400C17B4
0x1400c1813  call    cs:__imp_W32GetUserSessionState
0x1400c181a  nop     dword ptr [rax+rax+00h]
0x1400c181f  mov     dword ptr [rsp+60h+var_20], esi
0x1400c1823  mov     r9, [rax+4BD0h]
0x1400c182a  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400c1831  mov     [rsp+60h+var_28], rax
0x1400c1836  mov     [rsp+60h+var_30], 19h
0x1400c183d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1844  mov     r8b, dil
0x1400c1847  mov     [rsp+60h+dwFlags], 1
0x1400c184f  mov     dl, bl
0x1400c1851  mov     byte ptr [rsp+60h+pcbResult], 3
0x1400c1856  mov     rcx, [rcx+18h]
0x1400c185a  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400c185f  jmp     loc_1400C1743
0x1400c1864  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c186b  lea     rax, WPP_GLOBAL_Control
0x1400c1872  cmp     rcx, rax
0x1400c1875  jz      short loc_1400C1886
0x1400c1877  mov     eax, [rcx+2Ch]
0x1400c187a  test    al, 1
0x1400c187c  jz      short loc_1400C1886
0x1400c187e  cmp     byte ptr [rcx+29h], 3
0x1400c1882  mov     bl, 1
0x1400c1884  jnb     short loc_1400C1889
0x1400c1886  mov     bl, r13b
0x1400c1889  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c1890  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c1897  setnz   dil
0x1400c189b  test    bl, bl
0x1400c189d  jnz     short loc_1400C18A8
0x1400c189f  test    dil, dil
0x1400c18a2  jz      loc_1400C1743
0x1400c18a8  call    cs:__imp_W32GetUserSessionState
0x1400c18af  nop     dword ptr [rax+rax+00h]
0x1400c18b4  mov     dword ptr [rsp+60h+var_20], esi
0x1400c18b8  mov     r9, [rax+4BD0h]
0x1400c18bf  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400c18c6  mov     [rsp+60h+var_28], rax
0x1400c18cb  mov     [rsp+60h+var_30], 13h
0x1400c18d2  jmp     loc_1400C183D
0x1400c18d7  mov     rdx, cs:WPP_GLOBAL_Control
0x1400c18de  lea     rax, WPP_GLOBAL_Control
0x1400c18e5  cmp     rdx, rax
0x1400c18e8  jz      short loc_1400C18FA
0x1400c18ea  mov     ecx, [rdx+2Ch]
0x1400c18ed  test    cl, 1
0x1400c18f0  jz      short loc_1400C18FA
0x1400c18f2  cmp     byte ptr [rdx+29h], 3
0x1400c18f6  mov     bl, 1
0x1400c18f8  jnb     short loc_1400C18FD
0x1400c18fa  mov     bl, r13b
0x1400c18fd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c1904  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c190b  setnz   dil
0x1400c190f  test    bl, bl
0x1400c1911  jnz     short loc_1400C191C
0x1400c1913  test    dil, dil
0x1400c1916  jz      loc_1400C1743
0x1400c191c  call    cs:__imp_W32GetUserSessionState
0x1400c1923  nop     dword ptr [rax+rax+00h]
0x1400c1928  mov     r9, [rax+4BD0h]
0x1400c192f  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400c1936  mov     [rsp+60h+var_28], rax
0x1400c193b  mov     [rsp+60h+var_30], 14h
0x1400c1942  jmp     short loc_1400C196A
0x1400c1944  call    cs:__imp_W32GetUserSessionState
0x1400c194b  nop     dword ptr [rax+rax+00h]
0x1400c1950  mov     r9, [rax+4BD0h]
0x1400c1957  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400c195e  mov     [rsp+60h+var_28], rax
0x1400c1963  mov     [rsp+60h+var_30], 16h
0x1400c196a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1971  mov     r8b, dil
0x1400c1974  mov     [rsp+60h+dwFlags], 1
0x1400c197c  mov     dl, bl
0x1400c197e  mov     byte ptr [rsp+60h+pcbResult], 3
0x1400c1983  mov     rcx, [rcx+18h]
0x1400c1987  call    WPP_RECORDER_AND_TRACE_SF_
0x1400c198c  jmp     loc_1400C1743
0x1400c1991  mov     rdx, cs:WPP_GLOBAL_Control
0x1400c1998  lea     rax, WPP_GLOBAL_Control
0x1400c199f  cmp     rdx, rax
0x1400c19a2  jz      short loc_1400C19B4
0x1400c19a4  mov     ecx, [rdx+2Ch]
0x1400c19a7  test    cl, 1
0x1400c19aa  jz      short loc_1400C19B4
0x1400c19ac  cmp     byte ptr [rdx+29h], 3
0x1400c19b0  mov     bl, 1
0x1400c19b2  jnb     short loc_1400C19B7
0x1400c19b4  mov     bl, r13b
0x1400c19b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c19be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c19c5  setnz   dil
0x1400c19c9  test    bl, bl
0x1400c19cb  jnz     short loc_1400C19D6
0x1400c19cd  test    dil, dil
0x1400c19d0  jz      loc_1400C1743
0x1400c19d6  call    cs:__imp_W32GetUserSessionState
0x1400c19dd  nop     dword ptr [rax+rax+00h]
0x1400c19e2  mov     dword ptr [rsp+60h+var_20], esi
0x1400c19e6  mov     r9, [rax+4BD0h]
0x1400c19ed  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400c19f4  mov     [rsp+60h+var_28], rax
0x1400c19f9  mov     [rsp+60h+var_30], 15h
0x1400c1a00  jmp     loc_1400C183D
0x1400c1a05  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1a0c  lea     rax, WPP_GLOBAL_Control
0x1400c1a13  cmp     rcx, rax
0x1400c1a16  jz      short loc_1400C1A27
0x1400c1a18  mov     eax, [rcx+2Ch]
0x1400c1a1b  test    al, 1
0x1400c1a1d  jz      short loc_1400C1A27
0x1400c1a1f  cmp     byte ptr [rcx+29h], 3
0x1400c1a23  mov     bl, 1
0x1400c1a25  jnb     short loc_1400C1A2A
0x1400c1a27  mov     bl, r13b
0x1400c1a2a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c1a31  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c1a38  setnz   dil
0x1400c1a3c  test    bl, bl
0x1400c1a3e  jnz     loc_1400C1944
0x1400c1a44  test    dil, dil
0x1400c1a47  jz      loc_1400C1743
0x1400c1a4d  jmp     loc_1400C1944
0x1400c1a52  mov     rdx, cs:WPP_GLOBAL_Control
0x1400c1a59  lea     rax, WPP_GLOBAL_Control
0x1400c1a60  cmp     rdx, rax
0x1400c1a63  jz      short loc_1400C1A75
0x1400c1a65  mov     ecx, [rdx+2Ch]
0x1400c1a68  test    cl, 1
0x1400c1a6b  jz      short loc_1400C1A75
0x1400c1a6d  cmp     byte ptr [rdx+29h], 3
0x1400c1a71  mov     bl, 1
0x1400c1a73  jnb     short loc_1400C1A78
0x1400c1a75  mov     bl, r13b
0x1400c1a78  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c1a7f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c1a86  setnz   dil
0x1400c1a8a  test    bl, bl
0x1400c1a8c  jnz     short loc_1400C1A97
  ... truncated ...
```
