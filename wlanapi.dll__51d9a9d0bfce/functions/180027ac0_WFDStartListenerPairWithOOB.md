# WFDStartListenerPairWithOOB

- ea: `0x180027ac0`
- end: `0x1800280f6`
- name: `WFDStartListenerPairWithOOB`
- size: `1590`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18001a5bc`
- `0x1800278a0`
- `0x180027ac0`
- `0x180038670`
- `0x180038938`
- `0x180038c50`
- `0x180038e00`
- `0x180038f20`
- `0x180038fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180027f75`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180027f75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028003`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028003`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028013`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028020`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180027fa6`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180028040`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180027fa6`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180028040`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180027f09`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180027f09`

## pseudocode

```c
__int64 __fastcall WFDStartListenerPairWithOOB(
        unsigned int a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  struct _WFD_OOB_SESSION_CONTEXT *v10; // rdi
  union DOT11_OUI_HEADER *v12; // rcx
  __int64 v13; // r14
  _QWORD *v14; // rsi
  DWORD v15; // eax
  DWORD LastError; // ebx
  __int64 v17; // rdx
  DWORD Context; // eax
  _QWORD *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // rax
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  _OWORD *v24; // rcx
  __m128i v25; // xmm2
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  char *v32; // rax
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  unsigned int CanNewOOBSessionStart; // eax
  union DOT11_OUI_HEADER *v41; // rcx
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdx
  HANDLE Thread; // rax
  void *v46; // rcx
  LPVOID lpParameter[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v49[8]; // [rsp+40h] [rbp-C0h] BYREF
  __m128i v50; // [rsp+48h] [rbp-B8h]
  __int128 v51; // [rsp+58h] [rbp-A8h]
  __int128 v52; // [rsp+68h] [rbp-98h]
  __int128 v53; // [rsp+78h] [rbp-88h]
  __int128 v54; // [rsp+88h] [rbp-78h]
  __int128 v55; // [rsp+98h] [rbp-68h]
  __int128 v56; // [rsp+A8h] [rbp-58h]
  __int128 v57; // [rsp+B8h] [rbp-48h]
  __int128 v58; // [rsp+C8h] [rbp-38h]
  int v59; // [rsp+D8h] [rbp-28h]
  _BYTE v60[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v61; // [rsp+1D8h] [rbp+D8h] BYREF
  int v62; // [rsp+3B0h] [rbp+2B0h] BYREF

  v10 = 0;
  lpParameter[0] = 0;
  memset_0(v49, 0, 0x190u);
  memset_0(v60, 0, 0x190u);
  v62 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 187, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 || !a3 || !a4 || (v13 = a6) == 0 || (v14 = a7) == 0 )
  {
    LastError = 87;
    if ( v12 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return LastError;
    if ( !*((_BYTE *)v12 + 105) || (*((_BYTE *)v12 + 108) & 2) == 0 )
      goto LABEL_69;
    WPP_SF_(*((_QWORD *)v12 + 12), 188, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
    goto LABEL_78;
  }
  *a7 = 0;
  v15 = WFDParseOOBBlob(a3, a4, (struct _WFD_OOB_BLOB_DATA *)v49);
  LastError = v15;
  if ( v15 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
    {
      goto LABEL_79;
    }
    v17 = 189;
    goto LABEL_16;
  }
  v15 = WFDParseOOBBlob(a1, a2, (struct _WFD_OOB_BLOB_DATA *)v60);
  LastError = v15;
  if ( v15 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
    {
      goto LABEL_79;
    }
    v17 = 190;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v12 + 12), v17, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v15);
    goto LABEL_78;
  }
  if ( (unsigned int)WFDListenerValidateOOB((struct _WFD_OOB_BLOB_DATA *)v49, (struct _WFD_OOB_BLOB_DATA *)v60) )
  {
    Context = WFDOOBClientCreateContext((struct _WFD_OOB_SESSION_CONTEXT **)lpParameter);
    LastError = Context;
    if ( Context )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        v10 = (struct _WFD_OOB_SESSION_CONTEXT *)lpParameter[0];
LABEL_79:
        if ( !v10 )
          goto LABEL_69;
        WFDOOBClientDestroyContext(v10);
        goto LABEL_67;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 192, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, Context);
      v10 = (struct _WFD_OOB_SESSION_CONTEXT *)lpParameter[0];
LABEL_78:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_79;
    }
    v19 = lpParameter[0];
    v20 = 2;
    v21 = a5;
    v22 = v51;
    v23 = v52;
    *((_DWORD *)lpParameter[0] + 24) = 0;
    v24 = v19 + 31;
    v25 = v50;
    v19[10] = v13;
    v19[11] = v21;
    LODWORD(v21) = v59;
    *(__m128i *)((char *)v19 + 100) = v25;
    *(_OWORD *)((char *)v19 + 116) = v22;
    v26 = v53;
    *(_OWORD *)((char *)v19 + 132) = v23;
    v27 = v54;
    *(_OWORD *)((char *)v19 + 148) = v26;
    v28 = v55;
    *(_OWORD *)((char *)v19 + 164) = v27;
    v29 = v56;
    *(_OWORD *)((char *)v19 + 180) = v28;
    v30 = v57;
    *(_OWORD *)((char *)v19 + 196) = v29;
    v31 = v58;
    *(_OWORD *)((char *)v19 + 212) = v30;
    *(_OWORD *)((char *)v19 + 228) = v31;
    *((_DWORD *)v19 + 61) = v21;
    v32 = &v61;
    do
    {
      v33 = *((_OWORD *)v32 + 1);
      *v24 = *(_OWORD *)v32;
      v34 = *((_OWORD *)v32 + 2);
      v24[1] = v33;
      v35 = *((_OWORD *)v32 + 3);
      v24[2] = v34;
      v36 = *((_OWORD *)v32 + 4);
      v24[3] = v35;
      v37 = *((_OWORD *)v32 + 5);
      v24[4] = v36;
      v38 = *((_OWORD *)v32 + 6);
      v24[5] = v37;
      v39 = *((_OWORD *)v32 + 7);
      v32 += 128;
      v24[6] = v38;
      v24[7] = v39;
      v24 += 8;
      --v20;
    }
    while ( v20 );
    *(_QWORD *)v24 = *(_QWORD *)v32;
    *((_DWORD *)v19 + 128) = v25.m128i_i32[0];
    *((_WORD *)v19 + 258) = _mm_extract_epi16(v25, 2);
    CanNewOOBSessionStart = WFDOOBHelperCanNewOOBSessionStart(
                              (struct _WFD_OOB_SESSION_CONTEXT *)v19,
                              (enum _WFD_OOB_SESSION_ACTION *)&v62);
    LastError = CanNewOOBSessionStart;
    if ( CanNewOOBSessionStart )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_63;
      }
      v42 = 193;
    }
    else
    {
      v43 = v62;
      *((_DWORD *)v19 + 233) = v62;
      if ( v43 == 1
        && (CanNewOOBSessionStart = WFDOobHelperRegisterForNotification(1, (struct _WFD_OOB_SESSION_CONTEXT *)v19),
            (LastError = CanNewOOBSessionStart) != 0) )
      {
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
        {
          goto LABEL_63;
        }
        v42 = 194;
      }
      else
      {
        CanNewOOBSessionStart = WFDOobHelperSetPCDiscoverable(1, (struct _WFD_OOB_SESSION_CONTEXT *)v19);
        LastError = CanNewOOBSessionStart;
        if ( CanNewOOBSessionStart )
        {
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
          {
            goto LABEL_63;
          }
          v42 = 195;
        }
        else
        {
          v44 = *v19;
          lpParameter[0] = 0;
          CanNewOOBSessionStart = HtReferenceHandleWithTag(g_hHandleTable, v44, 269488144, 0, 1, lpParameter);
          LastError = CanNewOOBSessionStart;
          if ( !CanNewOOBSessionStart )
          {
            Thread = CreateThread(0, 0, ListenerWorkerThreadProc, v19, 0, 0);
            v19[123] = Thread;
            if ( Thread )
            {
              *v14 = *v19;
              v12 = WPP_GLOBAL_Control;
              goto LABEL_69;
            }
            LastError = GetLastError();
            HtDereferenceHandleWithTag(g_hHandleTable, *v19, 0, 1);
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                197,
                WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids,
                LastError);
              v12 = WPP_GLOBAL_Control;
            }
            if ( !LastError )
              goto LABEL_69;
            goto LABEL_63;
          }
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
          {
LABEL_63:
            v46 = (void *)v19[121];
            if ( v46 && v19[123] )
            {
              SetEvent(v46);
              WaitForSingleObject((HANDLE)v19[123], 0xFFFFFFFF);
              CloseHandle((HANDLE)v19[123]);
              v19[123] = 0;
            }
            HtDereferenceHandleWithTag(g_hHandleTable, *v19, 0, 1);
            goto LABEL_67;
          }
          v42 = 196;
        }
      }
    }
    WPP_SF_d(*((_QWORD *)v41 + 12), v42, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, CanNewOOBSessionStart);
    goto LABEL_63;
  }
  LastError = 87;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return LastError;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 191, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
LABEL_67:
    v12 = WPP_GLOBAL_Control;
  }
LABEL_69:
  if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v12 + 105) >= 4u
    && (*((_BYTE *)v12 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v12 + 12), 198, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180027ac0  push    rbp
0x180027ac2  push    rbx
0x180027ac3  push    rsi
0x180027ac4  push    rdi
0x180027ac5  push    r12
0x180027ac7  push    r13
0x180027ac9  push    r14
0x180027acb  push    r15
0x180027acd  lea     rbp, [rsp-268h]
0x180027ad5  sub     rsp, 368h
0x180027adc  mov     r15d, r8d
0x180027adf  mov     r12, rdx
0x180027ae2  mov     r13d, ecx
0x180027ae5  mov     esi, 190h
0x180027aea  xor     edi, edi
0x180027aec  lea     rcx, [rsp+3A0h+var_360]; void *
0x180027af1  mov     r8d, esi; Size
0x180027af4  mov     [rsp+3A0h+lpParameter], rdi
0x180027af9  xor     edx, edx; Val
0x180027afb  mov     rbx, r9
0x180027afe  call    memset_0
0x180027b03  mov     r8d, esi; Size
0x180027b06  lea     rcx, [rbp+2A0h+var_1D0]; void *
0x180027b0d  xor     edx, edx; Val
0x180027b0f  call    memset_0
0x180027b14  mov     [rbp+2A0h+arg_0], edi
0x180027b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b21  lea     rsi, WPP_GLOBAL_Control
0x180027b28  cmp     rcx, rsi
0x180027b2b  jz      short loc_180027B55
0x180027b2d  cmp     byte ptr [rcx+69h], 4
0x180027b31  jb      short loc_180027B55
0x180027b33  test    byte ptr [rcx+6Ch], 2
0x180027b37  jz      short loc_180027B55
0x180027b39  mov     rcx, [rcx+60h]
0x180027b3d  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180027b44  mov     edx, 0BBh
0x180027b49  call    WPP_SF_
0x180027b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b55  test    r13d, r13d
0x180027b58  jz      loc_1800280A9
0x180027b5e  test    r12, r12
0x180027b61  jz      loc_1800280A9
0x180027b67  test    r15d, r15d
0x180027b6a  jz      loc_1800280A9
0x180027b70  test    rbx, rbx
0x180027b73  jz      loc_1800280A9
0x180027b79  mov     r14, [rbp+2A0h+arg_28]
0x180027b80  test    r14, r14
0x180027b83  jz      loc_1800280A9
0x180027b89  mov     rsi, [rbp+2A0h+arg_30]
0x180027b90  test    rsi, rsi
0x180027b93  jz      loc_1800280A2
0x180027b99  lea     r8, [rsp+3A0h+var_360]; struct _WFD_OOB_BLOB_DATA *
0x180027b9e  mov     [rsi], rdi
0x180027ba1  mov     rdx, rbx; unsigned __int8 *
0x180027ba4  mov     ecx, r15d; unsigned int
0x180027ba7  call    WFDParseOOBBlob
0x180027bac  xor     r15d, r15d
0x180027baf  mov     ebx, eax
0x180027bb1  test    eax, eax
0x180027bb3  jz      short loc_180027BFD
0x180027bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bbc  lea     rsi, WPP_GLOBAL_Control
0x180027bc3  cmp     rcx, rsi
0x180027bc6  jz      loc_1800280E0
0x180027bcc  cmp     byte ptr [rcx+69h], 1
0x180027bd0  jb      loc_1800280E0
0x180027bd6  test    byte ptr [rcx+6Ch], 2
0x180027bda  jz      loc_1800280E0
0x180027be0  mov     edx, 0BDh
0x180027be5  mov     rcx, [rcx+60h]
0x180027be9  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180027bf0  mov     r9d, eax
0x180027bf3  call    WPP_SF_d
0x180027bf8  jmp     loc_1800280D9
0x180027bfd  lea     r8, [rbp+2A0h+var_1D0]; struct _WFD_OOB_BLOB_DATA *
0x180027c04  mov     rdx, r12; unsigned __int8 *
0x180027c07  mov     ecx, r13d; unsigned int
0x180027c0a  call    WFDParseOOBBlob
0x180027c0f  mov     ebx, eax
0x180027c11  test    eax, eax
0x180027c13  jz      short loc_180027C47
0x180027c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c1c  lea     rsi, WPP_GLOBAL_Control
0x180027c23  cmp     rcx, rsi
0x180027c26  jz      loc_1800280E0
0x180027c2c  cmp     byte ptr [rcx+69h], 1
0x180027c30  jb      loc_1800280E0
0x180027c36  test    byte ptr [rcx+6Ch], 2
0x180027c3a  jz      loc_1800280E0
0x180027c40  mov     edx, 0BEh
0x180027c45  jmp     short loc_180027BE5
0x180027c47  lea     rdx, [rbp+2A0h+var_1D0]; struct _WFD_OOB_BLOB_DATA *
0x180027c4e  lea     rcx, [rsp+3A0h+var_360]; struct _WFD_OOB_BLOB_DATA *
0x180027c53  call    ?WFDListenerValidateOOB@@YAHPEAU_WFD_OOB_BLOB_DATA@@0@Z; WFDListenerValidateOOB(_WFD_OOB_BLOB_DATA *,_WFD_OOB_BLOB_DATA *)
0x180027c58  test    eax, eax
0x180027c5a  jnz     short loc_180027CA2
0x180027c5c  lea     ebx, [rax+57h]
0x180027c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c66  lea     rsi, WPP_GLOBAL_Control
0x180027c6d  cmp     rcx, rsi
0x180027c70  jz      loc_18002808C
0x180027c76  cmp     byte ptr [rcx+69h], 1
0x180027c7a  jb      loc_180028063
0x180027c80  test    byte ptr [rcx+6Ch], 2
0x180027c84  jz      loc_180028063
0x180027c8a  mov     rcx, [rcx+60h]
0x180027c8e  lea     edx, [rbx+68h]
0x180027c91  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180027c98  call    WPP_SF_
0x180027c9d  jmp     loc_180028046
0x180027ca2  lea     rcx, [rsp+3A0h+lpParameter]; struct _WFD_OOB_SESSION_CONTEXT **
0x180027ca7  call    ?WFDOOBClientCreateContext@@YAKPEAPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOOBClientCreateContext(_WFD_OOB_SESSION_CONTEXT * *)
0x180027cac  mov     ebx, eax
0x180027cae  test    eax, eax
0x180027cb0  jz      short loc_180027CFD
0x180027cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cb9  lea     rsi, WPP_GLOBAL_Control
0x180027cc0  cmp     rcx, rsi
0x180027cc3  jz      short loc_180027CF3
0x180027cc5  cmp     byte ptr [rcx+69h], 1
0x180027cc9  jb      short loc_180027CF3
0x180027ccb  test    byte ptr [rcx+6Ch], 2
0x180027ccf  jz      short loc_180027CF3
0x180027cd1  mov     rcx, [rcx+60h]
0x180027cd5  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180027cdc  mov     edx, 0C0h
0x180027ce1  mov     r9d, eax
0x180027ce4  call    WPP_SF_d
0x180027ce9  mov     rdi, [rsp+3A0h+lpParameter]
0x180027cee  jmp     loc_1800280D9
0x180027cf3  mov     rdi, [rsp+3A0h+lpParameter]
0x180027cf8  jmp     loc_1800280E0
0x180027cfd  mov     rdi, [rsp+3A0h+lpParameter]
0x180027d02  mov     edx, 2
0x180027d07  mov     rax, [rbp+2A0h+arg_20]
0x180027d0e  movups  xmm0, [rsp+3A0h+var_348]
0x180027d13  movups  xmm1, [rsp+3A0h+var_338]
0x180027d18  mov     [rdi+60h], r15d
0x180027d1c  lea     rcx, [rdi+0F8h]
0x180027d23  movups  xmm2, [rsp+3A0h+var_358]
0x180027d28  mov     [rdi+50h], r14
0x180027d2c  lea     r8d, [rdx+7Eh]
0x180027d30  mov     [rdi+58h], rax
0x180027d34  mov     eax, [rbp+2A0h+var_2C8]
0x180027d37  movups  xmmword ptr [rdi+64h], xmm2
0x180027d3b  movups  xmmword ptr [rdi+74h], xmm0
0x180027d3f  movups  xmm0, [rsp+3A0h+var_328]
0x180027d44  movups  xmmword ptr [rdi+84h], xmm1
0x180027d4b  movups  xmm1, [rbp+2A0h+var_318]
0x180027d4f  movups  xmmword ptr [rdi+94h], xmm0
0x180027d56  movups  xmm0, [rbp+2A0h+var_308]
0x180027d5a  movups  xmmword ptr [rdi+0A4h], xmm1
0x180027d61  movups  xmm1, [rbp+2A0h+var_2F8]
0x180027d65  movups  xmmword ptr [rdi+0B4h], xmm0
0x180027d6c  movups  xmm0, [rbp+2A0h+var_2E8]
0x180027d70  movups  xmmword ptr [rdi+0C4h], xmm1
0x180027d77  movups  xmm1, [rbp+2A0h+var_2D8]
0x180027d7b  movups  xmmword ptr [rdi+0D4h], xmm0
0x180027d82  movups  xmmword ptr [rdi+0E4h], xmm1
0x180027d89  mov     [rdi+0F4h], eax
0x180027d8f  lea     rax, [rbp+2A0h+var_1C8]
0x180027d96  movups  xmm0, xmmword ptr [rax]
0x180027d99  movups  xmm1, xmmword ptr [rax+10h]
0x180027d9d  movups  xmmword ptr [rcx], xmm0
0x180027da0  movups  xmm0, xmmword ptr [rax+20h]
0x180027da4  movups  xmmword ptr [rcx+10h], xmm1
0x180027da8  movups  xmm1, xmmword ptr [rax+30h]
0x180027dac  movups  xmmword ptr [rcx+20h], xmm0
0x180027db0  movups  xmm0, xmmword ptr [rax+40h]
0x180027db4  movups  xmmword ptr [rcx+30h], xmm1
0x180027db8  movups  xmm1, xmmword ptr [rax+50h]
0x180027dbc  movups  xmmword ptr [rcx+40h], xmm0
0x180027dc0  movups  xmm0, xmmword ptr [rax+60h]
0x180027dc4  movups  xmmword ptr [rcx+50h], xmm1
0x180027dc8  movups  xmm1, xmmword ptr [rax+70h]
0x180027dcc  add     rax, r8
0x180027dcf  movups  xmmword ptr [rcx+60h], xmm0
0x180027dd3  movups  xmmword ptr [rcx+70h], xmm1
0x180027dd7  add     rcx, r8
0x180027dda  sub     rdx, 1
0x180027dde  jnz     short loc_180027D96
0x180027de0  mov     rax, [rax]
0x180027de3  lea     rdx, [rbp+2A0h+arg_0]; enum _WFD_OOB_SESSION_ACTION *
0x180027dea  mov     [rcx], rax
0x180027ded  mov     rcx, rdi; struct _WFD_OOB_SESSION_CONTEXT *
0x180027df0  pextrw  eax, xmm2, 2
0x180027df5  movss   dword ptr [rdi+200h], xmm2
0x180027dfd  mov     [rdi+204h], ax
0x180027e04  call    ?WFDOOBHelperCanNewOOBSessionStart@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@PEAW4_WFD_OOB_SESSION_ACTION@@@Z; WFDOOBHelperCanNewOOBSessionStart(_WFD_OOB_SESSION_CONTEXT *,_WFD_OOB_SESSION_ACTION *)
0x180027e09  mov     ebx, eax
0x180027e0b  test    eax, eax
0x180027e0d  jz      short loc_180027E44
0x180027e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e16  lea     rsi, WPP_GLOBAL_Control
0x180027e1d  cmp     rcx, rsi
0x180027e20  jz      loc_180027FEE
0x180027e26  cmp     byte ptr [rcx+69h], 1
0x180027e2a  jb      loc_180027FEE
0x180027e30  test    byte ptr [rcx+6Ch], 2
0x180027e34  jz      loc_180027FEE
0x180027e3a  mov     edx, 0C1h
0x180027e3f  jmp     loc_180027F45
0x180027e44  mov     eax, [rbp+2A0h+arg_0]
0x180027e4a  mov     [rdi+3A4h], eax
0x180027e50  cmp     eax, 1
0x180027e53  jnz     short loc_180027E9A
0x180027e55  mov     rdx, rdi; struct _WFD_OOB_SESSION_CONTEXT *
0x180027e58  mov     ecx, eax; int
0x180027e5a  call    ?WFDOobHelperRegisterForNotification@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperRegisterForNotification(int,_WFD_OOB_SESSION_CONTEXT *)
0x180027e5f  mov     ebx, eax
0x180027e61  test    eax, eax
0x180027e63  jz      short loc_180027E9A
0x180027e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e6c  lea     rsi, WPP_GLOBAL_Control
0x180027e73  cmp     rcx, rsi
0x180027e76  jz      loc_180027FEE
0x180027e7c  cmp     byte ptr [rcx+69h], 1
0x180027e80  jb      loc_180027FEE
0x180027e86  test    byte ptr [rcx+6Ch], 2
0x180027e8a  jz      loc_180027FEE
0x180027e90  mov     edx, 0C2h
0x180027e95  jmp     loc_180027F45
0x180027e9a  mov     rdx, rdi; struct _WFD_OOB_SESSION_CONTEXT *
0x180027e9d  mov     ecx, 1; int
0x180027ea2  call    ?WFDOobHelperSetPCDiscoverable@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperSetPCDiscoverable(int,_WFD_OOB_SESSION_CONTEXT *)
0x180027ea7  mov     ebx, eax
0x180027ea9  test    eax, eax
0x180027eab  jz      short loc_180027EDF
0x180027ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180027eb4  lea     rsi, WPP_GLOBAL_Control
0x180027ebb  cmp     rcx, rsi
0x180027ebe  jz      loc_180027FEE
0x180027ec4  cmp     byte ptr [rcx+69h], 1
0x180027ec8  jb      loc_180027FEE
0x180027ece  test    byte ptr [rcx+6Ch], 2
0x180027ed2  jz      loc_180027FEE
0x180027ed8  mov     edx, 0C3h
0x180027edd  jmp     short loc_180027F45
0x180027edf  mov     rdx, [rdi]
0x180027ee2  lea     rax, [rsp+3A0h+lpParameter]
0x180027ee7  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180027eee  xor     r9d, r9d
0x180027ef1  mov     [rsp+3A0h+lpThreadId], rax
0x180027ef6  mov     r8d, 10101010h
0x180027efc  mov     [rsp+3A0h+dwCreationFlags], 1
0x180027f04  mov     [rsp+3A0h+lpParameter], r15
0x180027f09  call    cs:__imp_HtReferenceHandleWithTag
0x180027f0f  mov     ebx, eax
0x180027f11  test    eax, eax
0x180027f13  jz      short loc_180027F5D
0x180027f15  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f1c  lea     rsi, WPP_GLOBAL_Control
0x180027f23  cmp     rcx, rsi
0x180027f26  jz      loc_180027FEE
0x180027f2c  cmp     byte ptr [rcx+69h], 1
0x180027f30  jb      loc_180027FEE
0x180027f36  test    byte ptr [rcx+6Ch], 2
0x180027f3a  jz      loc_180027FEE
0x180027f40  mov     edx, 0C4h
0x180027f45  mov     rcx, [rcx+60h]
0x180027f49  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180027f50  mov     r9d, eax
0x180027f53  call    WPP_SF_d
0x180027f58  jmp     loc_180027FEE
0x180027f5d  mov     [rsp+3A0h+lpThreadId], r15; lpThreadId
0x180027f62  lea     r8, ?ListenerWorkerThreadProc@@YAKPEAX@Z; lpStartAddress
0x180027f69  mov     r9, rdi; lpParameter
0x180027f6c  mov     [rsp+3A0h+dwCreationFlags], r15d; dwCreationFlags
0x180027f71  xor     edx, edx; dwStackSize
0x180027f73  xor     ecx, ecx; lpThreadAttributes
0x180027f75  call    cs:__imp_CreateThread
0x180027f7b  mov     [rdi+3D8h], rax
0x180027f82  test    rax, rax
0x180027f85  jnz     loc_18002804F
0x180027f8b  call    cs:__imp_GetLastError
0x180027f91  mov     rdx, [rdi]
0x180027f94  mov     r9d, 1
0x180027f9a  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180027fa1  xor     r8d, r8d
0x180027fa4  mov     ebx, eax
0x180027fa6  call    cs:__imp_HtDereferenceHandleWithTag
0x180027fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fb3  lea     rsi, WPP_GLOBAL_Control
0x180027fba  cmp     rcx, rsi
0x180027fbd  jz      short loc_180027FEA
0x180027fbf  cmp     byte ptr [rcx+69h], 1
0x180027fc3  jb      short loc_180027FEA
0x180027fc5  test    byte ptr [rcx+6Ch], 2
0x180027fc9  jz      short loc_180027FEA
0x180027fcb  mov     rcx, [rcx+60h]
0x180027fcf  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180027fd6  mov     edx, 0C5h
0x180027fdb  mov     r9d, ebx
0x180027fde  call    WPP_SF_d
0x180027fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fea  test    ebx, ebx
0x180027fec  jz      short loc_180028063
0x180027fee  mov     rcx, [rdi+3C8h]; hEvent
  ... truncated ...
```
