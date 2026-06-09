# _HashTHQAText(uchar *,ulong,uchar * *,ulong *)

- ea: `0x1400dacb4`
- end: `0x1400db2be`
- name: `?_HashTHQAText@@YAHPEAEKPEAPEAEPEAK@Z`
- size: `1546`
- prototype: `__int64 __fastcall(PUCHAR pbInput, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400da918`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x1400718f0`
- `0x1400cb450`
- `0x1400dacb4`

## import_xrefs

- `cng!BCryptCreateHash` at `0x1400dadec`
- `cng!BCryptCreateHash` at `0x1400dadec`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400dad0c`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400dad0c`
- `cng!BCryptGetProperty` at `0x1400dad43`
- `cng!BCryptGetProperty` at `0x1400dad99`
- `cng!BCryptGetProperty` at `0x1400dad43`
- `cng!BCryptGetProperty` at `0x1400dad99`
- `cng!BCryptHashData` at `0x1400dae10`
- `cng!BCryptHashData` at `0x1400dae10`
- `cng!BCryptFinishHash` at `0x1400dae34`
- `cng!BCryptFinishHash` at `0x1400dae34`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400dae95`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400dae95`
- `cng!BCryptDestroyHash` at `0x1400daea3`
- `cng!BCryptDestroyHash` at `0x1400daea3`
- `WIN32K!W32GetUserSessionState` at `0x1400daee6`
- `WIN32K!W32GetUserSessionState` at `0x1400daf23`
- `WIN32K!W32GetUserSessionState` at `0x1400dafb8`
- `WIN32K!W32GetUserSessionState` at `0x1400db02c`
- `WIN32K!W32GetUserSessionState` at `0x1400db054`
- `WIN32K!W32GetUserSessionState` at `0x1400db0e6`
- `WIN32K!W32GetUserSessionState` at `0x1400db1a7`
- `WIN32K!W32GetUserSessionState` at `0x1400db21b`
- `WIN32K!W32GetUserSessionState` at `0x1400daee6`
- `WIN32K!W32GetUserSessionState` at `0x1400daf23`
- `WIN32K!W32GetUserSessionState` at `0x1400dafb8`
- `WIN32K!W32GetUserSessionState` at `0x1400db02c`
- `WIN32K!W32GetUserSessionState` at `0x1400db054`
- `WIN32K!W32GetUserSessionState` at `0x1400db0e6`
- `WIN32K!W32GetUserSessionState` at `0x1400db1a7`
- `WIN32K!W32GetUserSessionState` at `0x1400db21b`

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
0x1400dacb4  mov     [rsp-38h+arg_0], rbx
0x1400dacb9  mov     [rsp-38h+arg_8], edx
0x1400dacbd  push    rbp
0x1400dacbe  push    rsi
0x1400dacbf  push    rdi
0x1400dacc0  push    r12
0x1400dacc2  push    r13
0x1400dacc4  push    r14
0x1400dacc6  push    r15
0x1400dacc8  mov     rbp, rsp
0x1400daccb  sub     rsp, 60h
0x1400daccf  xor     r13d, r13d
0x1400dacd2  lea     rdx, aSha256; "SHA256"
0x1400dacd9  mov     [r8], r13
0x1400dacdc  mov     rbx, r9
0x1400dacdf  mov     [r9], r13d
0x1400dace2  mov     r15, r8
0x1400dace5  mov     rdi, rcx
0x1400dace8  mov     [rbp+arg_18], r13d
0x1400dacec  xor     r9d, r9d; dwFlags
0x1400dacef  mov     [rbp+arg_8], r13d
0x1400dacf3  xor     r8d, r8d; pszImplementation
0x1400dacf6  mov     [rbp+pbOutput], r13d
0x1400dacfa  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400dacfe  mov     [rbp+phAlgorithm], r13
0x1400dad02  mov     r14d, r13d
0x1400dad05  mov     [rbp+phHash], r13
0x1400dad09  mov     r12d, r13d
0x1400dad0c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400dad13  nop     dword ptr [rax+rax+00h]
0x1400dad18  mov     esi, eax
0x1400dad1a  test    eax, eax
0x1400dad1c  js      loc_1400DAEB1
0x1400dad22  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400dad26  lea     rax, [rbp+arg_18]
0x1400dad2a  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x1400dad2f  lea     r9d, [r13+4]; cbOutput
0x1400dad33  lea     r8, [rbp+pbOutput]; pbOutput
0x1400dad37  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400dad3c  lea     rdx, pszProperty; "ObjectLength"
0x1400dad43  call    cs:__imp_BCryptGetProperty
0x1400dad4a  nop     dword ptr [rax+rax+00h]
0x1400dad4f  mov     esi, eax
0x1400dad51  test    eax, eax
0x1400dad53  js      loc_1400DAF74
0x1400dad59  mov     edx, [rbp+pbOutput]; unsigned __int64
0x1400dad5c  mov     ecx, 100h; unsigned __int64
0x1400dad61  mov     r8d, 63707355h; unsigned int
0x1400dad67  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400dad6c  mov     r14, rax
0x1400dad6f  test    rax, rax
0x1400dad72  jz      loc_1400DAFE7
0x1400dad78  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400dad7c  lea     rax, [rbp+arg_18]
0x1400dad80  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x1400dad85  lea     r9d, [r13+4]; cbOutput
0x1400dad89  lea     r8, [rbp+arg_8]; pbOutput
0x1400dad8d  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1400dad92  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400dad99  call    cs:__imp_BCryptGetProperty
0x1400dada0  nop     dword ptr [rax+rax+00h]
0x1400dada5  mov     esi, eax
0x1400dada7  test    eax, eax
0x1400dada9  js      loc_1400DB0A1
0x1400dadaf  mov     edx, [rbp+arg_8]; unsigned __int64
0x1400dadb2  mov     ecx, 100h; unsigned __int64
0x1400dadb7  mov     r8d, 63707355h; unsigned int
0x1400dadbd  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400dadc2  mov     [r15], rax
0x1400dadc5  test    rax, rax
0x1400dadc8  jz      loc_1400DB115
0x1400dadce  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1400dadd2  lea     rdx, [rbp+phHash]; phHash
0x1400dadd6  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400dadda  mov     r8, r14; pbHashObject
0x1400daddd  mov     dword ptr [rsp+60h+var_30], r13d; dwFlags
0x1400dade2  mov     [rsp+60h+dwFlags], r13d; cbSecret
0x1400dade7  mov     [rsp+60h+pcbResult], r13; pbSecret
0x1400dadec  call    cs:__imp_BCryptCreateHash
0x1400dadf3  nop     dword ptr [rax+rax+00h]
0x1400dadf8  mov     esi, eax
0x1400dadfa  test    eax, eax
0x1400dadfc  js      loc_1400DB162
0x1400dae02  mov     rcx, [rbp+phHash]; hHash
0x1400dae06  lea     r8d, [r13+4]; cbInput
0x1400dae0a  xor     r9d, r9d; dwFlags
0x1400dae0d  mov     rdx, rdi; pbInput
0x1400dae10  call    cs:__imp_BCryptHashData
0x1400dae17  nop     dword ptr [rax+rax+00h]
0x1400dae1c  mov     esi, eax
0x1400dae1e  test    eax, eax
0x1400dae20  js      loc_1400DB1D6
0x1400dae26  mov     r8d, [rbp+arg_8]; cbOutput
0x1400dae2a  xor     r9d, r9d; dwFlags
0x1400dae2d  mov     rdx, [r15]; pbOutput
0x1400dae30  mov     rcx, [rbp+phHash]; hHash
0x1400dae34  call    cs:__imp_BCryptFinishHash
0x1400dae3b  nop     dword ptr [rax+rax+00h]
0x1400dae40  mov     esi, eax
0x1400dae42  test    eax, eax
0x1400dae44  js      loc_1400DB24A
0x1400dae4a  mov     eax, [rbp+arg_8]
0x1400dae4d  lea     r12d, [r13+1]
0x1400dae51  mov     [rbx], eax
0x1400dae53  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400dae57  test    rcx, rcx
0x1400dae5a  jnz     short loc_1400DAE93
0x1400dae5c  mov     rcx, [rbp+phHash]; hHash
0x1400dae60  test    rcx, rcx
0x1400dae63  jnz     short loc_1400DAEA3
0x1400dae65  test    r14, r14
0x1400dae68  jnz     loc_1400DB298
0x1400dae6e  test    r12d, r12d
0x1400dae71  jz      loc_1400DB2A5
0x1400dae77  mov     rbx, [rsp+60h+arg_0]
0x1400dae7f  mov     eax, r12d
0x1400dae82  add     rsp, 60h
0x1400dae86  pop     r15
0x1400dae88  pop     r14
0x1400dae8a  pop     r13
0x1400dae8c  pop     r12
0x1400dae8e  pop     rdi
0x1400dae8f  pop     rsi
0x1400dae90  pop     rbp
0x1400dae91  retn
0x1400dae93  xor     edx, edx; dwFlags
0x1400dae95  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400dae9c  nop     dword ptr [rax+rax+00h]
0x1400daea1  jmp     short loc_1400DAE5C
0x1400daea3  call    cs:__imp_BCryptDestroyHash
0x1400daeaa  nop     dword ptr [rax+rax+00h]
0x1400daeaf  jmp     short loc_1400DAE65
0x1400daeb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400daeb8  lea     rax, WPP_GLOBAL_Control
0x1400daebf  cmp     rcx, rax
0x1400daec2  jnz     short loc_1400DAF12
0x1400daec4  mov     bl, r13b
0x1400daec7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400daece  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400daed5  setnz   dil
0x1400daed9  test    bl, bl
0x1400daedb  jnz     short loc_1400DAEE6
0x1400daedd  test    dil, dil
0x1400daee0  jz      loc_1400DAE53
0x1400daee6  call    cs:__imp_W32GetUserSessionState
0x1400daeed  nop     dword ptr [rax+rax+00h]
0x1400daef2  mov     dword ptr [rsp+60h+var_20], esi
0x1400daef6  mov     r9, [rax+4BD0h]
0x1400daefd  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400daf04  mov     [rsp+60h+var_28], rax
0x1400daf09  mov     [rsp+60h+var_30], 12h
0x1400daf10  jmp     short loc_1400DAF4D
0x1400daf12  mov     eax, [rcx+2Ch]
0x1400daf15  test    al, 1
0x1400daf17  jz      short loc_1400DAEC4
0x1400daf19  cmp     byte ptr [rcx+29h], 3
0x1400daf1d  mov     bl, 1
0x1400daf1f  jnb     short loc_1400DAEC7
0x1400daf21  jmp     short loc_1400DAEC4
0x1400daf23  call    cs:__imp_W32GetUserSessionState
0x1400daf2a  nop     dword ptr [rax+rax+00h]
0x1400daf2f  mov     dword ptr [rsp+60h+var_20], esi
0x1400daf33  mov     r9, [rax+4BD0h]
0x1400daf3a  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400daf41  mov     [rsp+60h+var_28], rax
0x1400daf46  mov     [rsp+60h+var_30], 19h
0x1400daf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400daf54  mov     r8b, dil
0x1400daf57  mov     [rsp+60h+dwFlags], 1
0x1400daf5f  mov     dl, bl
0x1400daf61  mov     byte ptr [rsp+60h+pcbResult], 3
0x1400daf66  mov     rcx, [rcx+18h]
0x1400daf6a  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400daf6f  jmp     loc_1400DAE53
0x1400daf74  mov     rcx, cs:WPP_GLOBAL_Control
0x1400daf7b  lea     rax, WPP_GLOBAL_Control
0x1400daf82  cmp     rcx, rax
0x1400daf85  jz      short loc_1400DAF96
0x1400daf87  mov     eax, [rcx+2Ch]
0x1400daf8a  test    al, 1
0x1400daf8c  jz      short loc_1400DAF96
0x1400daf8e  cmp     byte ptr [rcx+29h], 3
0x1400daf92  mov     bl, 1
0x1400daf94  jnb     short loc_1400DAF99
0x1400daf96  mov     bl, r13b
0x1400daf99  lea     rax, WPP_RECORDER_INITIALIZED
0x1400dafa0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400dafa7  setnz   dil
0x1400dafab  test    bl, bl
0x1400dafad  jnz     short loc_1400DAFB8
0x1400dafaf  test    dil, dil
0x1400dafb2  jz      loc_1400DAE53
0x1400dafb8  call    cs:__imp_W32GetUserSessionState
0x1400dafbf  nop     dword ptr [rax+rax+00h]
0x1400dafc4  mov     dword ptr [rsp+60h+var_20], esi
0x1400dafc8  mov     r9, [rax+4BD0h]
0x1400dafcf  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400dafd6  mov     [rsp+60h+var_28], rax
0x1400dafdb  mov     [rsp+60h+var_30], 13h
0x1400dafe2  jmp     loc_1400DAF4D
0x1400dafe7  mov     rdx, cs:WPP_GLOBAL_Control
0x1400dafee  lea     rax, WPP_GLOBAL_Control
0x1400daff5  cmp     rdx, rax
0x1400daff8  jz      short loc_1400DB00A
0x1400daffa  mov     ecx, [rdx+2Ch]
0x1400daffd  test    cl, 1
0x1400db000  jz      short loc_1400DB00A
0x1400db002  cmp     byte ptr [rdx+29h], 3
0x1400db006  mov     bl, 1
0x1400db008  jnb     short loc_1400DB00D
0x1400db00a  mov     bl, r13b
0x1400db00d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400db014  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400db01b  setnz   dil
0x1400db01f  test    bl, bl
0x1400db021  jnz     short loc_1400DB02C
0x1400db023  test    dil, dil
0x1400db026  jz      loc_1400DAE53
0x1400db02c  call    cs:__imp_W32GetUserSessionState
0x1400db033  nop     dword ptr [rax+rax+00h]
0x1400db038  mov     r9, [rax+4BD0h]
0x1400db03f  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400db046  mov     [rsp+60h+var_28], rax
0x1400db04b  mov     [rsp+60h+var_30], 14h
0x1400db052  jmp     short loc_1400DB07A
0x1400db054  call    cs:__imp_W32GetUserSessionState
0x1400db05b  nop     dword ptr [rax+rax+00h]
0x1400db060  mov     r9, [rax+4BD0h]
0x1400db067  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400db06e  mov     [rsp+60h+var_28], rax
0x1400db073  mov     [rsp+60h+var_30], 16h
0x1400db07a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400db081  mov     r8b, dil
0x1400db084  mov     [rsp+60h+dwFlags], 1
0x1400db08c  mov     dl, bl
0x1400db08e  mov     byte ptr [rsp+60h+pcbResult], 3
0x1400db093  mov     rcx, [rcx+18h]
0x1400db097  call    WPP_RECORDER_AND_TRACE_SF_
0x1400db09c  jmp     loc_1400DAE53
0x1400db0a1  mov     rdx, cs:WPP_GLOBAL_Control
0x1400db0a8  lea     rax, WPP_GLOBAL_Control
0x1400db0af  cmp     rdx, rax
0x1400db0b2  jz      short loc_1400DB0C4
0x1400db0b4  mov     ecx, [rdx+2Ch]
0x1400db0b7  test    cl, 1
0x1400db0ba  jz      short loc_1400DB0C4
0x1400db0bc  cmp     byte ptr [rdx+29h], 3
0x1400db0c0  mov     bl, 1
0x1400db0c2  jnb     short loc_1400DB0C7
0x1400db0c4  mov     bl, r13b
0x1400db0c7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400db0ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400db0d5  setnz   dil
0x1400db0d9  test    bl, bl
0x1400db0db  jnz     short loc_1400DB0E6
0x1400db0dd  test    dil, dil
0x1400db0e0  jz      loc_1400DAE53
0x1400db0e6  call    cs:__imp_W32GetUserSessionState
0x1400db0ed  nop     dword ptr [rax+rax+00h]
0x1400db0f2  mov     dword ptr [rsp+60h+var_20], esi
0x1400db0f6  mov     r9, [rax+4BD0h]
0x1400db0fd  lea     rax, WPP_f41d733443e9349cb6109e16b66b7a0d_Traceguids
0x1400db104  mov     [rsp+60h+var_28], rax
0x1400db109  mov     [rsp+60h+var_30], 15h
0x1400db110  jmp     loc_1400DAF4D
0x1400db115  mov     rcx, cs:WPP_GLOBAL_Control
0x1400db11c  lea     rax, WPP_GLOBAL_Control
0x1400db123  cmp     rcx, rax
0x1400db126  jz      short loc_1400DB137
0x1400db128  mov     eax, [rcx+2Ch]
0x1400db12b  test    al, 1
0x1400db12d  jz      short loc_1400DB137
0x1400db12f  cmp     byte ptr [rcx+29h], 3
0x1400db133  mov     bl, 1
0x1400db135  jnb     short loc_1400DB13A
0x1400db137  mov     bl, r13b
0x1400db13a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400db141  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400db148  setnz   dil
0x1400db14c  test    bl, bl
0x1400db14e  jnz     loc_1400DB054
0x1400db154  test    dil, dil
0x1400db157  jz      loc_1400DAE53
0x1400db15d  jmp     loc_1400DB054
0x1400db162  mov     rdx, cs:WPP_GLOBAL_Control
0x1400db169  lea     rax, WPP_GLOBAL_Control
0x1400db170  cmp     rdx, rax
0x1400db173  jz      short loc_1400DB185
0x1400db175  mov     ecx, [rdx+2Ch]
0x1400db178  test    cl, 1
0x1400db17b  jz      short loc_1400DB185
0x1400db17d  cmp     byte ptr [rdx+29h], 3
0x1400db181  mov     bl, 1
0x1400db183  jnb     short loc_1400DB188
0x1400db185  mov     bl, r13b
0x1400db188  lea     rax, WPP_RECORDER_INITIALIZED
0x1400db18f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400db196  setnz   dil
0x1400db19a  test    bl, bl
0x1400db19c  jnz     short loc_1400DB1A7
  ... truncated ...
```
