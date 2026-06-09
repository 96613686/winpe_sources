# _HashTHQAText(uchar *,ulong,uchar * *,ulong *)

- ea: `0x1400b5404`
- end: `0x1400b5a0e`
- name: `?_HashTHQAText@@YAHPEAEKPEAPEAEPEAK@Z`
- size: `1546`
- prototype: `__int64 __fastcall(PUCHAR pbInput, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400b5068`

## callees

- `0x140049ec0`
- `0x14007b930`
- `0x14007efd0`
- `0x1400a5ba0`
- `0x1400b5404`

## import_xrefs

- `cng!BCryptCreateHash` at `0x1400b553c`
- `cng!BCryptCreateHash` at `0x1400b553c`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400b545c`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400b545c`
- `cng!BCryptGetProperty` at `0x1400b5493`
- `cng!BCryptGetProperty` at `0x1400b54e9`
- `cng!BCryptGetProperty` at `0x1400b5493`
- `cng!BCryptGetProperty` at `0x1400b54e9`
- `cng!BCryptHashData` at `0x1400b5560`
- `cng!BCryptHashData` at `0x1400b5560`
- `cng!BCryptFinishHash` at `0x1400b5584`
- `cng!BCryptFinishHash` at `0x1400b5584`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400b55e5`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400b55e5`
- `cng!BCryptDestroyHash` at `0x1400b55f3`
- `cng!BCryptDestroyHash` at `0x1400b55f3`
- `WIN32K!W32GetUserSessionState` at `0x1400b5636`
- `WIN32K!W32GetUserSessionState` at `0x1400b5673`
- `WIN32K!W32GetUserSessionState` at `0x1400b5708`
- `WIN32K!W32GetUserSessionState` at `0x1400b577c`
- `WIN32K!W32GetUserSessionState` at `0x1400b57a4`
- `WIN32K!W32GetUserSessionState` at `0x1400b5836`
- `WIN32K!W32GetUserSessionState` at `0x1400b58f7`
- `WIN32K!W32GetUserSessionState` at `0x1400b596b`
- `WIN32K!W32GetUserSessionState` at `0x1400b5636`
- `WIN32K!W32GetUserSessionState` at `0x1400b5673`
- `WIN32K!W32GetUserSessionState` at `0x1400b5708`
- `WIN32K!W32GetUserSessionState` at `0x1400b577c`
- `WIN32K!W32GetUserSessionState` at `0x1400b57a4`
- `WIN32K!W32GetUserSessionState` at `0x1400b5836`
- `WIN32K!W32GetUserSessionState` at `0x1400b58f7`
- `WIN32K!W32GetUserSessionState` at `0x1400b596b`

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
0x1400b5404  mov     [rsp-38h+arg_0], rbx
0x1400b5409  mov     [rsp-38h+arg_8], edx
0x1400b540d  push    rbp
0x1400b540e  push    rsi
0x1400b540f  push    rdi
0x1400b5410  push    r12
0x1400b5412  push    r13
0x1400b5414  push    r14
0x1400b5416  push    r15
0x1400b5418  mov     rbp, rsp
0x1400b541b  sub     rsp, 60h
0x1400b541f  xor     r13d, r13d
0x1400b5422  lea     rdx, aSha256; "SHA256"
0x1400b5429  mov     [r8], r13
0x1400b542c  mov     rbx, r9
0x1400b542f  mov     [r9], r13d
0x1400b5432  mov     r15, r8
0x1400b5435  mov     rdi, rcx
0x1400b5438  mov     [rbp+arg_18], r13d
0x1400b543c  xor     r9d, r9d; dwFlags
0x1400b543f  mov     [rbp+arg_8], r13d
0x1400b5443  xor     r8d, r8d; pszImplementation
0x1400b5446  mov     [rbp+pbOutput], r13d
0x1400b544a  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400b544e  mov     [rbp+phAlgorithm], r13
0x1400b5452  mov     r14d, r13d
0x1400b5455  mov     [rbp+phHash], r13
0x1400b5459  mov     r12d, r13d
0x1400b545c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400b5463  nop     dword ptr [rax+rax+00h]
0x1400b5468  mov     esi, eax
0x1400b546a  test    eax, eax
0x1400b546c  js      loc_1400B5601
0x1400b5472  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400b5476  lea     rax, [rbp+arg_18]
0x1400b547a  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x1400b547f  lea     r9d, [r13+4]; cbOutput
0x1400b5483  lea     r8, [rbp+pbOutput]; pbOutput
0x1400b5487  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400b548c  lea     rdx, pszProperty; "ObjectLength"
0x1400b5493  call    cs:__imp_BCryptGetProperty
0x1400b549a  nop     dword ptr [rax+rax+00h]
0x1400b549f  mov     esi, eax
0x1400b54a1  test    eax, eax
0x1400b54a3  js      loc_1400B56C4
0x1400b54a9  mov     edx, [rbp+pbOutput]; unsigned __int64
0x1400b54ac  mov     ecx, 100h; unsigned __int64
0x1400b54b1  mov     r8d, 63707355h; unsigned int
0x1400b54b7  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400b54bc  mov     r14, rax
0x1400b54bf  test    rax, rax
0x1400b54c2  jz      loc_1400B5737
0x1400b54c8  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400b54cc  lea     rax, [rbp+arg_18]
0x1400b54d0  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x1400b54d5  lea     r9d, [r13+4]; cbOutput
0x1400b54d9  lea     r8, [rbp+arg_8]; pbOutput
0x1400b54dd  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400b54e2  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400b54e9  call    cs:__imp_BCryptGetProperty
0x1400b54f0  nop     dword ptr [rax+rax+00h]
0x1400b54f5  mov     esi, eax
0x1400b54f7  test    eax, eax
0x1400b54f9  js      loc_1400B57F1
0x1400b54ff  mov     edx, [rbp+arg_8]; unsigned __int64
0x1400b5502  mov     ecx, 100h; unsigned __int64
0x1400b5507  mov     r8d, 63707355h; unsigned int
0x1400b550d  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400b5512  mov     [r15], rax
0x1400b5515  test    rax, rax
0x1400b5518  jz      loc_1400B5865
0x1400b551e  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1400b5522  lea     rdx, [rbp+phHash]; phHash
0x1400b5526  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400b552a  mov     r8, r14; pbHashObject
0x1400b552d  mov     dword ptr [rsp+60h+var_30], r13d; dwFlags
0x1400b5532  mov     [rsp+60h+dwFlags], r13d; cbSecret
0x1400b5537  mov     [rsp+60h+pcbResult], r13; pbSecret
0x1400b553c  call    cs:__imp_BCryptCreateHash
0x1400b5543  nop     dword ptr [rax+rax+00h]
0x1400b5548  mov     esi, eax
0x1400b554a  test    eax, eax
0x1400b554c  js      loc_1400B58B2
0x1400b5552  mov     rcx, [rbp+phHash]; hHash
0x1400b5556  lea     r8d, [r13+4]; cbInput
0x1400b555a  xor     r9d, r9d; dwFlags
0x1400b555d  mov     rdx, rdi; pbInput
0x1400b5560  call    cs:__imp_BCryptHashData
0x1400b5567  nop     dword ptr [rax+rax+00h]
0x1400b556c  mov     esi, eax
0x1400b556e  test    eax, eax
0x1400b5570  js      loc_1400B5926
0x1400b5576  mov     r8d, [rbp+arg_8]; cbOutput
0x1400b557a  xor     r9d, r9d; dwFlags
0x1400b557d  mov     rdx, [r15]; pbOutput
0x1400b5580  mov     rcx, [rbp+phHash]; hHash
0x1400b5584  call    cs:__imp_BCryptFinishHash
0x1400b558b  nop     dword ptr [rax+rax+00h]
0x1400b5590  mov     esi, eax
0x1400b5592  test    eax, eax
0x1400b5594  js      loc_1400B599A
0x1400b559a  mov     eax, [rbp+arg_8]
0x1400b559d  lea     r12d, [r13+1]
0x1400b55a1  mov     [rbx], eax
0x1400b55a3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400b55a7  test    rcx, rcx
0x1400b55aa  jnz     short loc_1400B55E3
0x1400b55ac  mov     rcx, [rbp+phHash]; hHash
0x1400b55b0  test    rcx, rcx
0x1400b55b3  jnz     short loc_1400B55F3
0x1400b55b5  test    r14, r14
0x1400b55b8  jnz     loc_1400B59E8
0x1400b55be  test    r12d, r12d
0x1400b55c1  jz      loc_1400B59F5
0x1400b55c7  mov     rbx, [rsp+60h+arg_0]
0x1400b55cf  mov     eax, r12d
0x1400b55d2  add     rsp, 60h
0x1400b55d6  pop     r15
0x1400b55d8  pop     r14
0x1400b55da  pop     r13
0x1400b55dc  pop     r12
0x1400b55de  pop     rdi
0x1400b55df  pop     rsi
0x1400b55e0  pop     rbp
0x1400b55e1  retn
0x1400b55e3  xor     edx, edx; dwFlags
0x1400b55e5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400b55ec  nop     dword ptr [rax+rax+00h]
0x1400b55f1  jmp     short loc_1400B55AC
0x1400b55f3  call    cs:__imp_BCryptDestroyHash
0x1400b55fa  nop     dword ptr [rax+rax+00h]
0x1400b55ff  jmp     short loc_1400B55B5
0x1400b5601  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5608  lea     rax, WPP_GLOBAL_Control
0x1400b560f  cmp     rcx, rax
0x1400b5612  jnz     short loc_1400B5662
0x1400b5614  mov     bl, r13b
0x1400b5617  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b561e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5625  setnz   dil
0x1400b5629  test    bl, bl
0x1400b562b  jnz     short loc_1400B5636
0x1400b562d  test    dil, dil
0x1400b5630  jz      loc_1400B55A3
0x1400b5636  call    cs:__imp_W32GetUserSessionState
0x1400b563d  nop     dword ptr [rax+rax+00h]
0x1400b5642  mov     dword ptr [rsp+60h+var_20], esi
0x1400b5646  mov     r9, [rax+4BD0h]
0x1400b564d  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400b5654  mov     [rsp+60h+var_28], rax
0x1400b5659  mov     [rsp+60h+var_30], 12h
0x1400b5660  jmp     short loc_1400B569D
0x1400b5662  mov     eax, [rcx+2Ch]
0x1400b5665  test    al, 1
0x1400b5667  jz      short loc_1400B5614
0x1400b5669  cmp     byte ptr [rcx+29h], 3
0x1400b566d  mov     bl, 1
0x1400b566f  jnb     short loc_1400B5617
0x1400b5671  jmp     short loc_1400B5614
0x1400b5673  call    cs:__imp_W32GetUserSessionState
0x1400b567a  nop     dword ptr [rax+rax+00h]
0x1400b567f  mov     dword ptr [rsp+60h+var_20], esi
0x1400b5683  mov     r9, [rax+4BD0h]
0x1400b568a  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400b5691  mov     [rsp+60h+var_28], rax
0x1400b5696  mov     [rsp+60h+var_30], 19h
0x1400b569d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b56a4  mov     r8b, dil
0x1400b56a7  mov     [rsp+60h+dwFlags], 1
0x1400b56af  mov     dl, bl
0x1400b56b1  mov     byte ptr [rsp+60h+pcbResult], 3
0x1400b56b6  mov     rcx, [rcx+18h]
0x1400b56ba  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400b56bf  jmp     loc_1400B55A3
0x1400b56c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b56cb  lea     rax, WPP_GLOBAL_Control
0x1400b56d2  cmp     rcx, rax
0x1400b56d5  jz      short loc_1400B56E6
0x1400b56d7  mov     eax, [rcx+2Ch]
0x1400b56da  test    al, 1
0x1400b56dc  jz      short loc_1400B56E6
0x1400b56de  cmp     byte ptr [rcx+29h], 3
0x1400b56e2  mov     bl, 1
0x1400b56e4  jnb     short loc_1400B56E9
0x1400b56e6  mov     bl, r13b
0x1400b56e9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b56f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b56f7  setnz   dil
0x1400b56fb  test    bl, bl
0x1400b56fd  jnz     short loc_1400B5708
0x1400b56ff  test    dil, dil
0x1400b5702  jz      loc_1400B55A3
0x1400b5708  call    cs:__imp_W32GetUserSessionState
0x1400b570f  nop     dword ptr [rax+rax+00h]
0x1400b5714  mov     dword ptr [rsp+60h+var_20], esi
0x1400b5718  mov     r9, [rax+4BD0h]
0x1400b571f  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400b5726  mov     [rsp+60h+var_28], rax
0x1400b572b  mov     [rsp+60h+var_30], 13h
0x1400b5732  jmp     loc_1400B569D
0x1400b5737  mov     rdx, cs:WPP_GLOBAL_Control
0x1400b573e  lea     rax, WPP_GLOBAL_Control
0x1400b5745  cmp     rdx, rax
0x1400b5748  jz      short loc_1400B575A
0x1400b574a  mov     ecx, [rdx+2Ch]
0x1400b574d  test    cl, 1
0x1400b5750  jz      short loc_1400B575A
0x1400b5752  cmp     byte ptr [rdx+29h], 3
0x1400b5756  mov     bl, 1
0x1400b5758  jnb     short loc_1400B575D
0x1400b575a  mov     bl, r13b
0x1400b575d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b5764  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b576b  setnz   dil
0x1400b576f  test    bl, bl
0x1400b5771  jnz     short loc_1400B577C
0x1400b5773  test    dil, dil
0x1400b5776  jz      loc_1400B55A3
0x1400b577c  call    cs:__imp_W32GetUserSessionState
0x1400b5783  nop     dword ptr [rax+rax+00h]
0x1400b5788  mov     r9, [rax+4BD0h]
0x1400b578f  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400b5796  mov     [rsp+60h+var_28], rax
0x1400b579b  mov     [rsp+60h+var_30], 14h
0x1400b57a2  jmp     short loc_1400B57CA
0x1400b57a4  call    cs:__imp_W32GetUserSessionState
0x1400b57ab  nop     dword ptr [rax+rax+00h]
0x1400b57b0  mov     r9, [rax+4BD0h]
0x1400b57b7  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400b57be  mov     [rsp+60h+var_28], rax
0x1400b57c3  mov     [rsp+60h+var_30], 16h
0x1400b57ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b57d1  mov     r8b, dil
0x1400b57d4  mov     [rsp+60h+dwFlags], 1
0x1400b57dc  mov     dl, bl
0x1400b57de  mov     byte ptr [rsp+60h+pcbResult], 3
0x1400b57e3  mov     rcx, [rcx+18h]
0x1400b57e7  call    WPP_RECORDER_AND_TRACE_SF_
0x1400b57ec  jmp     loc_1400B55A3
0x1400b57f1  mov     rdx, cs:WPP_GLOBAL_Control
0x1400b57f8  lea     rax, WPP_GLOBAL_Control
0x1400b57ff  cmp     rdx, rax
0x1400b5802  jz      short loc_1400B5814
0x1400b5804  mov     ecx, [rdx+2Ch]
0x1400b5807  test    cl, 1
0x1400b580a  jz      short loc_1400B5814
0x1400b580c  cmp     byte ptr [rdx+29h], 3
0x1400b5810  mov     bl, 1
0x1400b5812  jnb     short loc_1400B5817
0x1400b5814  mov     bl, r13b
0x1400b5817  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b581e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5825  setnz   dil
0x1400b5829  test    bl, bl
0x1400b582b  jnz     short loc_1400B5836
0x1400b582d  test    dil, dil
0x1400b5830  jz      loc_1400B55A3
0x1400b5836  call    cs:__imp_W32GetUserSessionState
0x1400b583d  nop     dword ptr [rax+rax+00h]
0x1400b5842  mov     dword ptr [rsp+60h+var_20], esi
0x1400b5846  mov     r9, [rax+4BD0h]
0x1400b584d  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400b5854  mov     [rsp+60h+var_28], rax
0x1400b5859  mov     [rsp+60h+var_30], 15h
0x1400b5860  jmp     loc_1400B569D
0x1400b5865  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b586c  lea     rax, WPP_GLOBAL_Control
0x1400b5873  cmp     rcx, rax
0x1400b5876  jz      short loc_1400B5887
0x1400b5878  mov     eax, [rcx+2Ch]
0x1400b587b  test    al, 1
0x1400b587d  jz      short loc_1400B5887
0x1400b587f  cmp     byte ptr [rcx+29h], 3
0x1400b5883  mov     bl, 1
0x1400b5885  jnb     short loc_1400B588A
0x1400b5887  mov     bl, r13b
0x1400b588a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b5891  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5898  setnz   dil
0x1400b589c  test    bl, bl
0x1400b589e  jnz     loc_1400B57A4
0x1400b58a4  test    dil, dil
0x1400b58a7  jz      loc_1400B55A3
0x1400b58ad  jmp     loc_1400B57A4
0x1400b58b2  mov     rdx, cs:WPP_GLOBAL_Control
0x1400b58b9  lea     rax, WPP_GLOBAL_Control
0x1400b58c0  cmp     rdx, rax
0x1400b58c3  jz      short loc_1400B58D5
0x1400b58c5  mov     ecx, [rdx+2Ch]
0x1400b58c8  test    cl, 1
0x1400b58cb  jz      short loc_1400B58D5
0x1400b58cd  cmp     byte ptr [rdx+29h], 3
0x1400b58d1  mov     bl, 1
0x1400b58d3  jnb     short loc_1400B58D8
0x1400b58d5  mov     bl, r13b
0x1400b58d8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b58df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b58e6  setnz   dil
0x1400b58ea  test    bl, bl
0x1400b58ec  jnz     short loc_1400B58F7
  ... truncated ...
```
