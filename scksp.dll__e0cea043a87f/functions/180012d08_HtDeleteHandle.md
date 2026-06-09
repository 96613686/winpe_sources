# HtDeleteHandle

- ea: `0x180012d08`
- end: `0x1800134f4`
- name: `HtDeleteHandle`
- size: `2028`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e590`
- `0x180020ed4`
- `0x18002ada0`
- `0x18002add0`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x1800122b4`
- `0x180012d08`
- `0x18002ce34`
- `0x18002ce58`
- `0x18002d740`
- `0x180037070`
- `0x180037258`
- `0x1800374f4`
- `0x18003af5c`
- `0x18003afc0`
- `0x18003b434`
- `0x18003b920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800131ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800131ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012f2f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012f2f`
- `ncrypt!NCryptDeleteKey` at `0x18001329f`
- `ncrypt!NCryptDeleteKey` at `0x18001329f`
- `ncrypt!NCryptFreeObject` at `0x18001331a`
- `ncrypt!NCryptFreeObject` at `0x18001331a`
- `WinSCard!SCardDisconnect` at `0x1800133e2`
- `WinSCard!SCardDisconnect` at `0x1800133e2`
- `bcrypt!BCryptDestroyKey` at `0x18001333c`
- `bcrypt!BCryptDestroyKey` at `0x18001333c`

## pseudocode

```c
__int64 __fastcall HtDeleteHandle(int a1, int a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  unsigned int v6; // r12d
  __int64 v7; // r13
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r15
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 *v20; // rbx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // edx
  int v30; // r8d
  PFILETIME v31; // rbx
  __int64 v32; // rcx
  unsigned int v33; // ebx
  void **v34; // r15
  __int64 v35; // r14
  __int64 v36; // rcx
  __int64 v37; // rcx
  _QWORD *v38; // rcx
  int v39; // edx
  unsigned int v40; // esi
  void **v41; // r14
  HMODULE *v42; // rcx
  HMODULE v43; // rcx
  __int64 v44; // rcx
  char LastError; // al
  NCRYPT_KEY_HANDLE v46; // rcx
  _BYTE *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  NCRYPT_HANDLE v52; // rcx
  void *v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rdx
  SCARDHANDLE v57; // r14
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v62; // [rsp+30h] [rbp-30h]
  void **v63; // [rsp+38h] [rbp-28h] BYREF
  __int64 v64; // [rsp+40h] [rbp-20h]
  _QWORD v65[3]; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v66; // [rsp+A0h] [rbp+40h] BYREF
  int v67; // [rsp+B0h] [rbp+50h]
  unsigned int v68; // [rsp+B8h] [rbp+58h]

  v63 = 0;
  v66 = 0;
  v5 = KspEnterCriticalSection(&CriticalSection);
  if ( !v5 )
  {
    v6 = a1 - 370672441;
    v68 = a1 - 370672441;
    if ( (unsigned int)(a1 - 370672441) >= HIDWORD(qword_18004C048)
      || (v7 = 2LL * v6, v4 = *((unsigned int *)g_HandleTable + 4 * v6), (_DWORD)v4 == 6) )
    {
      WppTraceIndent(v4, 2);
      v5 = -2146893786;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_127;
      }
      v9 = 14;
LABEL_126:
      WPP_SF_d(v8[2], v9, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids, 2148073510LL);
      goto LABEL_127;
    }
    if ( a2 != (_DWORD)v4 )
    {
      WppTraceIndent(v4, 2);
      v5 = -2146893786;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_127;
      }
      v9 = 15;
      goto LABEL_126;
    }
    v67 = 0;
    v10 = 0;
    v11 = v4 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
      {
        _mm_lfence();
        v15 = *((_QWORD *)g_HandleTable + 2 * v6 + 1);
        if ( *(_DWORD *)(v15 + 1048) )
        {
          v46 = *(_QWORD *)(v15 + 1144);
          if ( v46 )
            NCryptDeleteKey(v46, 0);
          *(_QWORD *)(v15 + 1144) = 0;
        }
        v47 = *(_BYTE **)(v15 + 1160);
        if ( v47 )
        {
          v48 = *(unsigned int *)(v15 + 1168);
          if ( *(_DWORD *)(v15 + 1168) )
          {
            do
            {
              *v47++ = 0;
              --v48;
            }
            while ( v48 );
          }
          CspFreeH(*(_QWORD *)(v15 + 1160));
        }
        v49 = *(_QWORD *)(v15 + 1080);
        if ( v49 )
          CspFreeH(v49);
        v50 = *(_QWORD *)(v15 + 1072);
        if ( v50 )
          CspFreeH(v50);
        v51 = *(_QWORD *)(v15 + 1136);
        if ( v51 )
          CspFreeH(v51);
        v52 = *(_QWORD *)(v15 + 1144);
        if ( v52 )
          NCryptFreeObject(v52);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
        {
          v53 = *(void **)(v15 + 1152);
          if ( v53 )
          {
            BCryptDestroyKey(v53);
            *(_QWORD *)(v15 + 1152) = 0;
          }
        }
        v54 = *(_QWORD *)(v15 + 1088);
        if ( v54 )
        {
          if ( !(unsigned int)KspEnterCriticalSection(v54 + 624) )
          {
            v55 = *(_QWORD *)(v15 + 1088);
            v63 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
            v64 = v55 + 624;
            if ( *(_DWORD *)(v55 + 592) )
              CspEndTransaction((struct _CARD_STATE *)v55);
            v56 = *(_QWORD *)(*(_QWORD *)(v15 + 1088) + 8LL);
            if ( v56 )
            {
              v57 = *(_QWORD *)(v56 + 104);
              if ( v57 )
              {
                *(_QWORD *)(v56 + 104) = 0;
                *(_DWORD *)(*(_QWORD *)(v15 + 1088) + 688LL) = 1;
                v58 = *(_QWORD *)(v15 + 1088) + 624LL;
                v64 = 0;
                KspLeaveCriticalSection(v58);
                SCardDisconnect(v57, 0);
              }
            }
            v63 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
            Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v63);
          }
          CardStateReleaseRef(*(_QWORD *)(v15 + 1088), 0);
        }
        v59 = *(_QWORD *)(v15 + 1200);
        if ( v59 )
          CspFreeH(v59);
        goto LABEL_114;
      }
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 2 )
        {
          v14 = *((_QWORD *)g_HandleTable + 2 * v6 + 1);
LABEL_115:
          CspFreeH(v14);
          goto LABEL_82;
        }
        _mm_lfence();
        v15 = *((_QWORD *)g_HandleTable + 2 * v6 + 1);
        v16 = *(_QWORD *)(v15 + 16);
        if ( v16 )
          CspFreeH(v16);
        v17 = *(_QWORD *)(v15 + 8);
        if ( v17 )
          CspFreeH(v17);
        v18 = *(_QWORD *)(v15 + 72);
        if ( v18 )
          CspFreeH(v18);
        v19 = *(_QWORD *)(v15 + 24);
        if ( v19 )
          CardStateReleaseRef(v19, 0);
LABEL_114:
        v14 = v15;
        goto LABEL_115;
      }
      _mm_lfence();
      v20 = (__int64 *)*((_QWORD *)g_HandleTable + 2 * v6 + 1);
      v10 = *v20;
      v62 = *v20;
      v5 = KspEnterCriticalSection(*v20);
      if ( v5 )
      {
        WppTraceIndent(v21, 2);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_127;
        }
        v23 = 17;
        goto LABEL_31;
      }
      --*(_DWORD *)(v10 + 160);
      v67 = 1;
      if ( *((_DWORD *)v20 + 14) )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v20 + 2));
      v24 = v20[10];
      if ( v24 )
        CspFreeH(v24);
      v25 = v20[9];
      if ( v25 )
        CspFreeH(v25);
      v26 = v20[18];
      if ( v26 )
        CspFreeH(v26);
      v27 = v20[17];
      if ( v27 )
        CspFreeH(v27);
      v28 = v20[11];
      if ( v28 )
        CardStateReleaseRef(v28, 0);
      CspFreeH(v20);
      if ( *(_DWORD *)(v10 + 160) <= 1u )
      {
        v31 = g_pTransactionManagerState;
        if ( g_pTransactionManagerState )
        {
          I_TransactionManagerCloseThreadPool((struct _TRANSACTION_MANAGER_STATE *)g_pTransactionManagerState);
          CspFreeH(v31);
        }
        g_pTransactionManagerState = 0;
        if ( qword_18004C240 )
        {
          v5 = ScCacheEnumItems(qword_18004C240, v29, v30, (unsigned int)&v63, (__int64)&v66);
          if ( v5 )
          {
            WppTraceIndent(v32, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
                (_DWORD)WPP_pszIndent,
                v5);
            }
            goto LABEL_70;
          }
          v33 = v66;
          v34 = v63;
          if ( v66 )
          {
            while ( 1 )
            {
              v35 = *(_QWORD *)v34[2 * --v33 + 1];
              v5 = KspEnterCriticalSection(v35 + 624);
              if ( v5 )
                break;
              v65[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
              v65[1] = v35 + 624;
              TransactionManagerForceEndTransaction((struct _CARD_STATE *)v35);
              CleanupCardData(v35 + 8, 0);
              *(_QWORD *)(v35 + 600) = 0;
              v65[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
              Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v65);
              if ( !v33 )
              {
                v6 = v68;
                goto LABEL_57;
              }
            }
            WppTraceIndent(v36, 2);
            v38 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_69;
            }
            v39 = 19;
            goto LABEL_68;
          }
LABEL_57:
          ScCacheFreeEnumItems(qword_18004C240, v34, v66);
        }
        if ( qword_18004C278 )
        {
          v66 = 0;
          v5 = ScCacheEnumItems(qword_18004C278, v29, v30, (unsigned int)&v63, (__int64)&v66);
          if ( v5 )
          {
            WppTraceIndent(v37, 2);
            v38 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_69;
            }
            v39 = 20;
LABEL_68:
            WPP_SF_sd(
              v38[2],
              v39,
              (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
              (_DWORD)WPP_pszIndent,
              v5);
LABEL_69:
            v10 = v62;
LABEL_70:
            KspLeaveCriticalSection(v10);
            goto LABEL_127;
          }
          v40 = v66;
          v41 = v63;
          while ( v40 )
          {
            v42 = (HMODULE *)v41[2 * --v40 + 1];
            if ( v42 )
            {
              v43 = *v42;
              if ( v43 )
              {
                if ( !FreeLibrary(v43) )
                {
                  WppTraceIndent(v44, 2);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    LastError = GetLastError();
                    WPP_SF_sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      21,
                      (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
                      (_DWORD)WPP_pszIndent,
                      LastError);
                  }
                }
              }
            }
          }
          ScCacheFreeEnumItems(qword_18004C278, v41, v66);
          ScCacheDeleteCache(qword_18004C278);
          qword_18004C278 = 0;
        }
        v10 = v62;
      }
    }
    else
    {
      _mm_lfence();
      v10 = *((_QWORD *)g_HandleTable + 2 * v6 + 1);
      v5 = KspEnterCriticalSection(v10);
      if ( v5 )
      {
        WppTraceIndent(v60, 2);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_127;
        }
        v23 = 16;
LABEL_31:
        WPP_SF_sd(v22[2], v23, (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids, (_DWORD)WPP_pszIndent, v5);
LABEL_127:
        KspLeaveCriticalSection(&CriticalSection);
        return v5;
      }
      --*(_DWORD *)(v10 + 160);
      v67 = 1;
    }
LABEL_82:
    *((_DWORD *)g_HandleTable + 2 * v7) = 6;
    *((_DWORD *)g_HandleTable + 2 * v7 + 2) = HIDWORD(qword_18004C050);
    LODWORD(qword_18004C048) = qword_18004C048 - 1;
    ++dword_18004C058;
    HIDWORD(qword_18004C050) = v6;
    if ( !v67 )
      goto LABEL_127;
    goto LABEL_70;
  }
  WppTraceIndent(v4, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
      (_DWORD)WPP_pszIndent,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180012d08  mov     [rsp-38h+arg_8], rbx
0x180012d0d  push    rbp
0x180012d0e  push    rsi
0x180012d0f  push    rdi
0x180012d10  push    r12
0x180012d12  push    r13
0x180012d14  push    r14
0x180012d16  push    r15
0x180012d18  mov     rbp, rsp
0x180012d1b  sub     rsp, 60h
0x180012d1f  mov     rbx, rcx
0x180012d22  xor     r14d, r14d
0x180012d25  lea     rcx, CriticalSection
0x180012d2c  mov     [rbp+var_28], r14
0x180012d30  mov     [rbp+arg_0], r14d
0x180012d34  mov     esi, edx
0x180012d36  call    KspEnterCriticalSection
0x180012d3b  mov     edi, eax
0x180012d3d  test    eax, eax
0x180012d3f  jz      short loc_180012D99
0x180012d41  lea     edx, [r14+2]
0x180012d45  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d51  lea     rbx, WPP_GLOBAL_Control
0x180012d58  cmp     rcx, rbx
0x180012d5b  jz      loc_1800134DA
0x180012d61  test    byte ptr [rcx+1Ch], 1
0x180012d65  jz      loc_1800134DA
0x180012d6b  cmp     byte ptr [rcx+19h], 2
0x180012d6f  jb      loc_1800134DA
0x180012d75  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012d7c  lea     edx, [r14+0Dh]
0x180012d80  mov     rcx, [rcx+10h]
0x180012d84  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x180012d8b  mov     dword ptr [rsp+60h+var_40], edi
0x180012d8f  call    WPP_SF_sd
0x180012d94  jmp     loc_1800134DA
0x180012d99  lea     r12d, [rbx-16180339h]
0x180012da0  cmp     r12d, dword ptr cs:qword_18004C048+4
0x180012da7  mov     [rbp+arg_18], r12d
0x180012dab  jnb     loc_180013487
0x180012db1  mov     rdx, cs:g_HandleTable
0x180012db8  mov     r13d, r12d
0x180012dbb  add     r13, r13
0x180012dbe  mov     ecx, [rdx+r13*8]
0x180012dc2  cmp     ecx, 6
0x180012dc5  jz      loc_180013487
0x180012dcb  cmp     esi, ecx
0x180012dcd  jz      short loc_180012E17
0x180012dcf  mov     edx, 2
0x180012dd4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012dd9  mov     r9d, 80090026h
0x180012ddf  mov     edi, r9d
0x180012de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180012de9  lea     rbx, WPP_GLOBAL_Control
0x180012df0  cmp     rcx, rbx
0x180012df3  jz      loc_1800134CE
0x180012df9  test    byte ptr [rcx+1Ch], 1
0x180012dfd  jz      loc_1800134CE
0x180012e03  cmp     byte ptr [rcx+19h], 2
0x180012e07  jb      loc_1800134CE
0x180012e0d  mov     edx, 0Fh
0x180012e12  jmp     loc_1800134BE
0x180012e17  or      esi, 0FFFFFFFFh
0x180012e1a  mov     [rbp+arg_10], r14d
0x180012e1e  mov     r15, r14
0x180012e21  sub     ecx, 1
0x180012e24  jz      loc_180013424
0x180012e2a  sub     ecx, 1
0x180012e2d  jz      loc_180013279
0x180012e33  sub     ecx, 1
0x180012e36  jz      short loc_180012E99
0x180012e38  cmp     ecx, 2
0x180012e3b  jz      short loc_180012E47
0x180012e3d  mov     rcx, [rdx+r13*8+8]
0x180012e42  jmp     loc_18001341A
0x180012e47  lfence
0x180012e4a  mov     rax, cs:g_HandleTable
0x180012e51  mov     rbx, [rax+r13*8+8]
0x180012e56  mov     rcx, [rbx+10h]
0x180012e5a  test    rcx, rcx
0x180012e5d  jz      short loc_180012E64
0x180012e5f  call    CspFreeH
0x180012e64  mov     rcx, [rbx+8]
0x180012e68  test    rcx, rcx
0x180012e6b  jz      short loc_180012E72
0x180012e6d  call    CspFreeH
0x180012e72  mov     rcx, [rbx+48h]
0x180012e76  test    rcx, rcx
0x180012e79  jz      short loc_180012E80
0x180012e7b  call    CspFreeH
0x180012e80  mov     rcx, [rbx+18h]
0x180012e84  test    rcx, rcx
0x180012e87  jz      loc_180013417
0x180012e8d  xor     edx, edx
0x180012e8f  call    CardStateReleaseRef
0x180012e94  jmp     loc_180013417
0x180012e99  lfence
0x180012e9c  mov     rax, cs:g_HandleTable
0x180012ea3  mov     rbx, [rax+r13*8+8]
0x180012ea8  mov     r15, [rbx]
0x180012eab  mov     rcx, r15
0x180012eae  mov     [rbp+var_30], r15
0x180012eb2  call    KspEnterCriticalSection
0x180012eb7  mov     edi, eax
0x180012eb9  test    eax, eax
0x180012ebb  jz      short loc_180012F17
0x180012ebd  mov     edx, 2
0x180012ec2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ece  lea     rbx, WPP_GLOBAL_Control
0x180012ed5  cmp     rcx, rbx
0x180012ed8  jz      loc_1800134CE
0x180012ede  test    byte ptr [rcx+1Ch], 1
0x180012ee2  jz      loc_1800134CE
0x180012ee8  cmp     byte ptr [rcx+19h], 2
0x180012eec  jb      loc_1800134CE
0x180012ef2  mov     edx, 11h
0x180012ef7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012efe  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x180012f05  mov     rcx, [rcx+10h]
0x180012f09  mov     dword ptr [rsp+60h+var_40], edi
0x180012f0d  call    WPP_SF_sd
0x180012f12  jmp     loc_1800134CE
0x180012f17  add     [r15+0A0h], esi
0x180012f1e  mov     [rbp+arg_10], 1
0x180012f25  cmp     [rbx+38h], r14d
0x180012f29  jz      short loc_180012F35
0x180012f2b  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012f2f  call    cs:__imp_DeleteCriticalSection
0x180012f35  mov     rcx, [rbx+50h]
0x180012f39  test    rcx, rcx
0x180012f3c  jz      short loc_180012F43
0x180012f3e  call    CspFreeH
0x180012f43  mov     rcx, [rbx+48h]
0x180012f47  test    rcx, rcx
0x180012f4a  jz      short loc_180012F51
0x180012f4c  call    CspFreeH
0x180012f51  mov     rcx, [rbx+90h]
0x180012f58  test    rcx, rcx
0x180012f5b  jz      short loc_180012F62
0x180012f5d  call    CspFreeH
0x180012f62  mov     rcx, [rbx+88h]
0x180012f69  test    rcx, rcx
0x180012f6c  jz      short loc_180012F73
0x180012f6e  call    CspFreeH
0x180012f73  mov     rcx, [rbx+58h]
0x180012f77  test    rcx, rcx
0x180012f7a  jz      short loc_180012F83
0x180012f7c  xor     edx, edx
0x180012f7e  call    CardStateReleaseRef
0x180012f83  mov     rcx, rbx
0x180012f86  call    CspFreeH
0x180012f8b  cmp     dword ptr [r15+0A0h], 1
0x180012f93  ja      loc_180013236
0x180012f99  mov     rbx, cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA; _TRANSACTION_MANAGER_STATE * g_pTransactionManagerState
0x180012fa0  test    rbx, rbx
0x180012fa3  jz      short loc_180012FB5
0x180012fa5  mov     rcx, rbx; struct _TRANSACTION_MANAGER_STATE *
0x180012fa8  call    ?I_TransactionManagerCloseThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z; I_TransactionManagerCloseThreadPool(_TRANSACTION_MANAGER_STATE *)
0x180012fad  mov     rcx, rbx
0x180012fb0  call    CspFreeH
0x180012fb5  mov     rcx, cs:qword_18004C240
0x180012fbc  mov     cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA, r14; _TRANSACTION_MANAGER_STATE * g_pTransactionManagerState
0x180012fc3  test    rcx, rcx
0x180012fc6  jz      loc_1800130C9
0x180012fcc  lea     rax, [rbp+arg_0]
0x180012fd0  lea     r9, [rbp+var_28]
0x180012fd4  mov     [rsp+60h+var_40], rax
0x180012fd9  call    ScCacheEnumItems
0x180012fde  mov     edi, eax
0x180012fe0  test    eax, eax
0x180012fe2  jz      short loc_18001303E
0x180012fe4  mov     edx, 2
0x180012fe9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ff5  lea     rbx, WPP_GLOBAL_Control
0x180012ffc  cmp     rcx, rbx
0x180012fff  jz      loc_180013176
0x180013005  test    byte ptr [rcx+1Ch], 1
0x180013009  jz      loc_180013176
0x18001300f  cmp     byte ptr [rcx+19h], 2
0x180013013  jb      loc_180013176
0x180013019  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180013020  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x180013027  mov     rcx, [rcx+10h]
0x18001302b  mov     edx, 12h
0x180013030  mov     dword ptr [rsp+60h+var_40], edi
0x180013034  call    WPP_SF_sd
0x180013039  jmp     loc_180013176
0x18001303e  mov     ebx, [rbp+arg_0]
0x180013041  mov     r15, [rbp+var_28]
0x180013045  test    ebx, ebx
0x180013047  jz      short loc_1800130B6
0x180013049  lea     rsi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180013050  dec     ebx
0x180013052  mov     eax, ebx
0x180013054  add     rax, rax
0x180013057  mov     rax, [r15+rax*8+8]
0x18001305c  mov     r14, [rax]
0x18001305f  lea     r12, [r14+270h]
0x180013066  mov     rcx, r12
0x180013069  call    KspEnterCriticalSection
0x18001306e  mov     edi, eax
0x180013070  test    eax, eax
0x180013072  jnz     loc_180013129
0x180013078  mov     rcx, r14; struct _CARD_STATE *
0x18001307b  mov     [rbp+var_18], rsi
0x18001307f  mov     [rbp+var_10], r12
0x180013083  call    TransactionManagerForceEndTransaction
0x180013088  lea     rcx, [r14+8]
0x18001308c  xor     edx, edx
0x18001308e  call    CleanupCardData
0x180013093  mov     qword ptr [r14+258h], 0
0x18001309e  lea     rcx, [rbp+var_18]
0x1800130a2  mov     [rbp+var_18], rsi
0x1800130a6  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x1800130ab  xor     r14d, r14d
0x1800130ae  test    ebx, ebx
0x1800130b0  jnz     short loc_180013050
0x1800130b2  mov     r12d, [rbp+arg_18]
0x1800130b6  mov     r8d, [rbp+arg_0]
0x1800130ba  mov     rdx, r15
0x1800130bd  mov     rcx, cs:qword_18004C240
0x1800130c4  call    ScCacheFreeEnumItems
0x1800130c9  mov     rcx, cs:qword_18004C278
0x1800130d0  test    rcx, rcx
0x1800130d3  jz      loc_180013232
0x1800130d9  lea     rax, [rbp+arg_0]
0x1800130dd  mov     [rbp+arg_0], r14d
0x1800130e1  lea     r9, [rbp+var_28]
0x1800130e5  mov     [rsp+60h+var_40], rax
0x1800130ea  call    ScCacheEnumItems
0x1800130ef  mov     edi, eax
0x1800130f1  test    eax, eax
0x1800130f3  jz      loc_180013183
0x1800130f9  mov     edx, 2
0x1800130fe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013103  mov     rcx, cs:WPP_GLOBAL_Control
0x18001310a  lea     rbx, WPP_GLOBAL_Control
0x180013111  cmp     rcx, rbx
0x180013114  jz      short loc_180013172
0x180013116  test    byte ptr [rcx+1Ch], 1
0x18001311a  jz      short loc_180013172
0x18001311c  cmp     byte ptr [rcx+19h], 2
0x180013120  jb      short loc_180013172
0x180013122  mov     edx, 14h
0x180013127  jmp     short loc_180013157
0x180013129  mov     edx, 2
0x18001312e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013133  mov     rcx, cs:WPP_GLOBAL_Control
0x18001313a  lea     rbx, WPP_GLOBAL_Control
0x180013141  cmp     rcx, rbx
0x180013144  jz      short loc_180013172
0x180013146  test    byte ptr [rcx+1Ch], 1
0x18001314a  jz      short loc_180013172
0x18001314c  cmp     byte ptr [rcx+19h], 2
0x180013150  jb      short loc_180013172
0x180013152  mov     edx, 13h
0x180013157  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001315e  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x180013165  mov     rcx, [rcx+10h]
0x180013169  mov     dword ptr [rsp+60h+var_40], edi
0x18001316d  call    WPP_SF_sd
0x180013172  mov     r15, [rbp+var_30]
0x180013176  mov     rcx, r15
0x180013179  call    KspLeaveCriticalSection
0x18001317e  jmp     loc_1800134CE
0x180013183  mov     esi, [rbp+arg_0]
0x180013186  mov     r14, [rbp+var_28]
0x18001318a  test    esi, esi
0x18001318c  jz      short loc_180013209
0x18001318e  lea     rbx, WPP_GLOBAL_Control
0x180013195  dec     esi
0x180013197  mov     eax, esi
0x180013199  add     rax, rax
0x18001319c  mov     rcx, [r14+rax*8+8]
0x1800131a1  test    rcx, rcx
0x1800131a4  jz      short loc_180013205
0x1800131a6  mov     rcx, [rcx]; hLibModule
0x1800131a9  test    rcx, rcx
0x1800131ac  jz      short loc_180013205
0x1800131ae  call    cs:__imp_FreeLibrary
0x1800131b4  test    eax, eax
0x1800131b6  jnz     short loc_180013205
0x1800131b8  lea     edx, [rax+2]
0x1800131bb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800131c0  mov     rax, cs:WPP_GLOBAL_Control
0x1800131c7  cmp     rax, rbx
0x1800131ca  jz      short loc_180013205
0x1800131cc  test    byte ptr [rax+1Ch], 1
0x1800131d0  jz      short loc_180013205
0x1800131d2  cmp     byte ptr [rax+19h], 2
0x1800131d6  jb      short loc_180013205
0x1800131d8  call    cs:__imp_GetLastError
0x1800131de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131e5  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x1800131ec  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800131f3  mov     edx, 15h
0x1800131f8  mov     dword ptr [rsp+60h+var_40], eax
  ... truncated ...
```
