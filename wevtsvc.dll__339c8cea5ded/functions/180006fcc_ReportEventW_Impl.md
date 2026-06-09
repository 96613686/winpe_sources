# ReportEventW_Impl

- ea: `0x180006fcc`
- end: `0x180007976`
- name: `ReportEventW_Impl`
- size: `2474`
- prototype: `__int64 __fastcall(__int64, __int16, __int16, int, unsigned __int16, unsigned int, __int64, void *Src, __int64, void *, __int16, int, __int64)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035518`
- `0x180082df0`
- `0x1800c4830`

## callees

- `0x180003de0`
- `0x180006824`
- `0x180006fb0`
- `0x180006fcc`
- `0x18000797c`
- `0x180007edc`
- `0x180008b5c`
- `0x18000a180`
- `0x180017c44`
- `0x18001c320`
- `0x18002de70`
- `0x180030374`
- `0x180092008`
- `0x180092ee4`
- `0x180098c50`
- `0x1800c4a0c`
- `0x1800c4b14`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800078e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800078e6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800075ed`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800075ed`

## pseudocode

```c
__int64 __fastcall ReportEventW_Impl(
        __int64 a1,
        __int16 a2,
        __int16 a3,
        int a4,
        unsigned __int16 a5,
        unsigned int a6,
        __int64 a7,
        void *Src,
        __int64 a9,
        void *a10,
        __int16 a11,
        int a12,
        __int64 a13)
{
  __int64 v13; // r14
  int v14; // eax
  __int64 v15; // rdx
  int v16; // esi
  int v17; // eax
  unsigned int i; // esi
  __int64 v19; // r15
  struct LOGFILE *v20; // rcx
  unsigned __int16 *v21; // rdx
  DWORD LengthSid; // eax
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 j; // r8
  __int64 v26; // rax
  size_t v27; // r15
  int v28; // r12d
  _DWORD *v29; // rax
  _DWORD *v30; // rsi
  unsigned int v31; // ebx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // r15d
  char *v36; // r14
  unsigned int k; // r15d
  char *v38; // rbx
  size_t v39; // r13
  char *v40; // rbx
  __int64 v41; // rax
  __int64 v43; // rax
  __int64 v44; // r10
  __int64 v45; // r8
  size_t v46; // rdx
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  PVOID *v49; // rcx
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  EvtException *v52; // rbx
  unsigned int v53; // eax
  DWORD v54; // [rsp+30h] [rbp-E8h]
  unsigned int v55; // [rsp+34h] [rbp-E4h]
  unsigned int v56; // [rsp+38h] [rbp-E0h]
  char *v57; // [rsp+38h] [rbp-E0h]
  const WCHAR *v58; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v59; // [rsp+48h] [rbp-D0h]
  void *v60; // [rsp+50h] [rbp-C8h]
  size_t v61; // [rsp+58h] [rbp-C0h] BYREF
  int v62; // [rsp+60h] [rbp-B8h] BYREF
  __int128 v63; // [rsp+68h] [rbp-B0h] BYREF
  void *v64; // [rsp+78h] [rbp-A0h]
  const WCHAR *v65; // [rsp+80h] [rbp-98h] BYREF
  __int64 v66; // [rsp+88h] [rbp-90h] BYREF
  _DWORD *v67; // [rsp+90h] [rbp-88h] BYREF
  int v68; // [rsp+98h] [rbp-80h]
  int v69; // [rsp+9Ch] [rbp-7Ch]
  __int64 v70; // [rsp+A0h] [rbp-78h]
  size_t Size[2]; // [rsp+B0h] [rbp-68h] BYREF
  _QWORD v72[2]; // [rsp+C0h] [rbp-58h] BYREF
  EvtException *v73; // [rsp+D0h] [rbp-48h] BYREF
  const WCHAR *v74; // [rsp+D8h] [rbp-40h]

  v13 = a1;
  v62 = 0;
  v14 = VerifyElfHandle(a1);
  v16 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
        (unsigned int)v14);
    }
    return (unsigned int)v16;
  }
  if ( !(unsigned __int8)AreAnyRestrictionsEnabled(4, v15) )
  {
    v58 = &pszFormat;
    v59 = 0;
    v60 = 0;
    v17 = VerifyString<_RPC_UNICODE_STRING,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(a7, &v58);
    v16 = v17;
    if ( v17 >= 0 )
    {
      if ( !a9 && a5 )
      {
        v50 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v51 = 63;
        goto LABEL_75;
      }
      if ( Src && !IsValidSid(Src) )
      {
        v50 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v51 = 64;
LABEL_75:
        WPP_SF_d(v50[2], v51, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, 3221225485LL);
LABEL_57:
        if ( v60 )
          operator delete(v60);
        return 3221225485LL;
      }
      v63 = 0;
      v64 = 0;
      for ( i = 0; i < a5; ++i )
      {
        v32 = VerifyString<_RPC_UNICODE_STRING,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
                *(_QWORD *)(a9 + 8LL * i),
                &v63);
        v35 = v32;
        if ( v32 < 0 )
        {
          v49 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, v34, i, v32);
              v49 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x1000) != 0 && *((_BYTE *)v49 + 25) >= 2u )
              WPP_SF_d(v49[2], 66, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, v35);
          }
          if ( v64 )
            operator delete(v64);
          if ( v60 )
            operator delete(v60);
          return v35;
        }
      }
      if ( (*(_BYTE *)(v13 + 32) & 2) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = -1073741816;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
            3221225480LL);
          goto LABEL_35;
        }
      }
      else
      {
        if ( !a10 && a6 )
        {
          v47 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v48 = 68;
LABEL_108:
            WPP_SF_d(v47[2], v48, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, 3221225485LL);
            goto LABEL_55;
          }
          goto LABEL_55;
        }
        if ( !a13 )
        {
          v47 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v48 = 69;
            goto LABEL_108;
          }
LABEL_55:
          if ( v64 )
            operator delete(v64);
          goto LABEL_57;
        }
        if ( *(__int64 *)a13 < 116444736010000000LL )
        {
          v47 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v48 = 70;
            goto LABEL_108;
          }
          goto LABEL_55;
        }
        v19 = *(_QWORD *)(v13 + 16);
        v74 = (const WCHAR *)v19;
        if ( v19 )
        {
          v20 = *(struct LOGFILE **)(v19 + 32);
          if ( v20 )
          {
            v16 = ((int (__stdcall *)(struct LOGFILE *, struct _IELF_HANDLE *, unsigned int, bool))LegacyAccessCheck)(
                    v20,
                    (struct _IELF_HANDLE *)v13,
                    2u,
                    0);
            if ( v16 >= 0 )
            {
              if ( !*(_QWORD *)(v13 + 8) )
              {
                v43 = *(_QWORD *)(v19 + 32);
                v44 = *(_QWORD *)(v43 + 88);
                v45 = (*(_QWORD *)(v43 + 96) - v44) >> 1;
                v46 = -1;
                do
                  ++v46;
                while ( *(_WORD *)(v13 + 52 + 2 * v46) );
                if ( __eh34_try(-1, 0) )
                {
                  __eh34_scope_strut(0);
                  v65 = v58;
                  v66 = v59;
                  v72[0] = v44;
                  v72[1] = v45;
                  Size[0] = v13 + 52;
                  Size[1] = v46;
                  PublisherManager::CreateLegacyPublisher(
                    (_QWORD *)((int)g_service + 232),
                    (__int64 *)(unsigned int)&v61,
                    (unsigned int)Size,
                    (unsigned int)v72,
                    (__int64 *)&v65);
                  *(_QWORD *)(v13 + 8) = v61;
                }
                if ( __eh34_catch(0) )
                {
                  if ( __eh34_catch_type(0, &EvtException `RTTI Type Descriptor', &v73) )
                  {
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      v52 = v73;
                    }
                    else
                    {
                      v52 = v73;
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        71,
                        &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
                        *((unsigned int *)v73 + 6));
                    }
                    v53 = DosErrorToNtStatus(*((_DWORD *)v52 + 6));
                    v55 = v53;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        72,
                        &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
                        v53);
                    }
                    __eh34_try_continuation(0, &EvtException `RTTI Type Descriptor', &loc_1800078C1);
                    if ( v64 )
                      operator delete(v64);
                    if ( v60 )
                      operator delete(v60);
                    return v55;
                  }
                }
              }
              LengthSid = 0;
              v54 = 0;
              if ( Src )
              {
                LengthSid = GetLengthSid(Src);
                v54 = LengthSid;
              }
              Size[0] = LengthSid;
              v23 = LengthSid + 64LL;
              v56 = v23;
              v24 = 0;
              for ( j = 0; (unsigned int)j < a5; j = (unsigned int)(j + 1) )
              {
                v21 = *(unsigned __int16 **)(a9 + 8LL * (unsigned int)j);
                v24 += *v21 + 2LL;
              }
              v70 = v24 + v23;
              v61 = a6;
              v26 = v24 + v23 + a6 + 4LL;
              v27 = -(int)v26 & 3;
              v72[0] = v27;
              v28 = v27 + v26;
              v65 = (const WCHAR *)(v27 + v26);
              if ( v27 + v26 >= 0x10000 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, j, v27 + v26);
                }
                goto LABEL_55;
              }
              v29 = MIDL_user_allocate(v27 + v26);
              v30 = v29;
              if ( v29 )
              {
                *v29 = v28;
                v29[1] = 1699505740;
                v29[3] = *(_DWORD *)a13;
                v29[4] = *(_DWORD *)(a13 + 4);
                v29[5] = a4;
                *((_WORD *)v29 + 12) = a2;
                *((_WORD *)v29 + 13) = a5;
                *((_WORD *)v29 + 14) = a3;
                *((_WORD *)v29 + 15) = a11;
                v29[8] = 0;
                v29[9] = v56;
                v29[10] = v54;
                v29[11] = 64;
                v29[12] = a6;
                v29[13] = v70;
                v29[14] = 120;
                v29[15] = 121;
                memcpy_0(v29 + 16, Src, Size[0]);
                v57 = (char *)v30 + v56;
                if ( a5 )
                {
                  v36 = v57;
                  for ( k = 0; k < a5; v36 += **(unsigned __int16 **)(a9 + 8LL * k++) + 2 )
                  {
                    memcpy_0(
                      v36,
                      *(const void **)(*(_QWORD *)(a9 + 8LL * k) + 8LL),
                      **(unsigned __int16 **)(a9 + 8LL * k));
                    *(_WORD *)&v36[2 * ((unsigned __int64)**(unsigned __int16 **)(a9 + 8LL * k) >> 1)] = 0;
                  }
                  v13 = a1;
                  v27 = v72[0];
                  v28 = (int)v65;
                }
                v38 = (char *)v30 + v70;
                v39 = v61;
                if ( a10 )
                  memcpy_0((char *)v30 + v70, a10, v61);
                v40 = &v38[v39];
                memcpy_0(v40, &v62, v27);
                *(_DWORD *)&v40[v27] = v28;
                v65 = v74;
                v67 = v30;
                v41 = *(_QWORD *)(v13 + 8);
                if ( v41 )
                  _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
                v66 = v41;
                v68 = a12;
                v69 = 0;
                v31 = PerformWriteRequest((struct WRITE_PKT *)&v65);
                utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v67);
                wmi::AutoRef<PublisherMetadata>::Release(&v66);
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids);
                }
                v31 = -1073741801;
              }
LABEL_35:
              if ( v64 )
                operator delete(v64);
              if ( v60 )
                operator delete(v60);
              return v31;
            }
            if ( v64 )
              operator delete(v64);
            goto LABEL_49;
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, v13 + 52);
        }
      }
      v31 = -1073741816;
      goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids,
        (unsigned int)v17);
    }
LABEL_49:
    if ( v60 )
      operator delete(v60);
    return (unsigned int)v16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_34e363d74db23d35a65b27eda4c444e6_Traceguids, 3221225659LL);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x180006fcc  mov     rax, rsp
0x180006fcf  mov     [rax+20h], r9d
0x180006fd3  mov     [rax+18h], r8w
0x180006fd8  mov     [rax+10h], dx
0x180006fdc  mov     [rax+8], rcx
0x180006fe0  push    rbx
0x180006fe1  push    rsi
0x180006fe2  push    rdi
0x180006fe3  push    r12
0x180006fe5  push    r13
0x180006fe7  push    r14
0x180006fe9  push    r15
0x180006feb  sub     rsp, 0E0h
0x180006ff2  mov     r14, rcx
0x180006ff5  xor     edi, edi
0x180006ff7  mov     [rsp+118h+var_B8], edi
0x180006ffb  call    VerifyElfHandle
0x180007000  mov     esi, eax
0x180007002  test    eax, eax
0x180007004  js      loc_180007676
0x18000700a  lea     ecx, [rdi+4]
0x18000700d  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x180007012  test    al, al
0x180007014  jnz     loc_1800076C1
0x18000701a  lea     rax, pszFormat
0x180007021  mov     [rsp+118h+var_D8], rax
0x180007026  mov     [rsp+118h+var_D0], rdi
0x18000702b  mov     [rsp+118h+var_C8], rdi
0x180007030  lea     rdx, [rsp+118h+var_D8]
0x180007035  mov     rcx, [rsp+118h+arg_30]
0x18000703d  call    ??$VerifyString@U_RPC_UNICODE_STRING@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@@YAJPEAU_RPC_UNICODE_STRING@@AEAV?$RpcString@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@@@Z; VerifyString<_RPC_UNICODE_STRING,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_RPC_UNICODE_STRING *,RpcString<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>> &)
0x180007042  mov     esi, eax
0x180007044  test    eax, eax
0x180007046  js      loc_1800074D9
0x18000704c  mov     r13, [rsp+118h+arg_40]
0x180007054  movzx   r15d, [rsp+118h+arg_20]
0x18000705d  test    r13, r13
0x180007060  jz      loc_180007746
0x180007066  mov     rbx, [rsp+118h+Src]
0x18000706e  test    rbx, rbx
0x180007071  jnz     loc_1800075EA
0x180007077  xorps   xmm0, xmm0
0x18000707a  movdqu  [rsp+118h+var_B0], xmm0
0x180007080  mov     [rsp+118h+var_A0], rdi
0x180007085  mov     esi, edi
0x180007087  movzx   r12d, r15w
0x18000708b  mov     [rsp+118h+var_E4], r12d
0x180007090  cmp     esi, r12d
0x180007093  jb      loc_1800071DD
0x180007099  test    byte ptr [r14+20h], 2
0x18000709e  jnz     loc_180007505
0x1800070a4  cmp     [rsp+118h+arg_48], rdi
0x1800070ac  jz      loc_1800074A0
0x1800070b2  mov     rax, [rsp+118h+arg_60]
0x1800070ba  test    rax, rax
0x1800070bd  jz      loc_180007859
0x1800070c3  mov     rcx, 19DB1DED5D71680h
0x1800070cd  cmp     [rax], rcx
0x1800070d0  jl      loc_18000788E
0x1800070d6  mov     r15, [r14+10h]
0x1800070da  mov     [rsp+118h+var_40], r15
0x1800070e2  test    r15, r15
0x1800070e5  jz      loc_18000759E
0x1800070eb  mov     rcx, [r15+20h]; struct LOGFILE *
0x1800070ef  test    rcx, rcx
0x1800070f2  jz      loc_18000759E
0x1800070f8  xor     r9d, r9d; bool
0x1800070fb  lea     r8d, [r9+2]; unsigned int
0x1800070ff  mov     rdx, r14; struct _IELF_HANDLE *
0x180007102  call    ?LegacyAccessCheck@@YAJPEAULOGFILE@@PEAU_IELF_HANDLE@@K_N@Z; LegacyAccessCheck(LOGFILE *,_IELF_HANDLE *,ulong,bool)
0x180007107  mov     esi, eax
0x180007109  test    eax, eax
0x18000710b  js      loc_180007647
0x180007111  cmp     [r14+8], rdi
0x180007115  jz      loc_1800073FF
0x18000711b  mov     eax, edi
0x18000711d  mov     [rsp+118h+var_E8], eax
0x180007121  test    rbx, rbx
0x180007124  jnz     loc_1800078E3
0x18000712a  mov     eax, eax
0x18000712c  mov     [rsp+118h+Size], rax
0x180007134  add     rax, 40h ; '@'
0x180007138  mov     [rsp+118h+var_E0], rax
0x18000713d  mov     r9, rdi
0x180007140  mov     r8d, edi
0x180007143  test    r12d, r12d
0x180007146  jz      short loc_180007162
0x180007148  mov     ecx, r8d
0x18000714b  mov     rdx, [r13+rcx*8+0]
0x180007150  movzx   ecx, word ptr [rdx]
0x180007153  add     r9, 2
0x180007157  add     r9, rcx
0x18000715a  inc     r8d
0x18000715d  cmp     r8d, r12d
0x180007160  jb      short loc_180007148
0x180007162  lea     rcx, [r9+rax]
0x180007166  mov     [rsp+118h+var_78], rcx
0x18000716e  mov     eax, [rsp+118h+arg_28]
0x180007175  mov     [rsp+118h+var_C0], rax
0x18000717a  add     rax, 4
0x18000717e  add     rax, rcx
0x180007181  mov     r15, rax
0x180007184  neg     r15
0x180007187  and     r15d, 3
0x18000718b  mov     [rsp+118h+var_58], r15
0x180007193  lea     r12, [r15+rax]
0x180007197  mov     [rsp+118h+var_98], r12
0x18000719f  cmp     r12, 10000h
0x1800071a6  jnb     loc_180007526
0x1800071ac  mov     rcx, r12; size
0x1800071af  call    MIDL_user_allocate
0x1800071b4  mov     rsi, rax
0x1800071b7  test    rax, rax
0x1800071ba  jnz     short loc_180007200
0x1800071bc  lea     rbx, WPP_GLOBAL_Control
0x1800071c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071ca  cmp     rcx, rbx
0x1800071cd  jnz     loc_180007931
0x1800071d3  mov     ebx, 0C0000017h
0x1800071d8  jmp     loc_1800073CE
0x1800071dd  mov     ecx, esi
0x1800071df  lea     rdx, [rsp+118h+var_B0]
0x1800071e4  mov     rcx, [r13+rcx*8+0]
0x1800071e9  call    ??$VerifyString@U_RPC_UNICODE_STRING@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@YAJPEAU_RPC_UNICODE_STRING@@AEAV?$RpcString@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@@Z; VerifyString<_RPC_UNICODE_STRING,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(_RPC_UNICODE_STRING *,RpcString<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>> &)
0x1800071ee  mov     r15d, eax
0x1800071f1  test    eax, eax
0x1800071f3  js      loc_180007563
0x1800071f9  inc     esi
0x1800071fb  jmp     loc_180007090
0x180007200  mov     [rax], r12d
0x180007203  mov     dword ptr [rax+4], 654C664Ch
0x18000720a  mov     rcx, [rsp+118h+arg_60]
0x180007212  mov     eax, [rcx]
0x180007214  mov     [rsi+0Ch], eax
0x180007217  mov     eax, [rcx+4]
0x18000721a  mov     [rsi+10h], eax
0x18000721d  mov     eax, [rsp+118h+arg_18]
0x180007224  mov     [rsi+14h], eax
0x180007227  movzx   eax, [rsp+118h+arg_8]
0x18000722f  mov     [rsi+18h], ax
0x180007233  movzx   eax, [rsp+118h+arg_20]
0x18000723b  mov     [rsi+1Ah], ax
0x18000723f  movzx   eax, [rsp+118h+arg_10]
0x180007247  mov     [rsi+1Ch], ax
0x18000724b  movzx   eax, [rsp+118h+arg_50]
0x180007253  mov     [rsi+1Eh], ax
0x180007257  mov     [rsi+20h], edi
0x18000725a  mov     eax, dword ptr [rsp+118h+var_E0]
0x18000725e  mov     [rsp+118h+var_E0], rax
0x180007263  mov     [rsi+24h], eax
0x180007266  mov     eax, [rsp+118h+var_E8]
0x18000726a  mov     [rsi+28h], eax
0x18000726d  mov     dword ptr [rsi+2Ch], 40h ; '@'
0x180007274  mov     eax, [rsp+118h+arg_28]
0x18000727b  mov     [rsi+30h], eax
0x18000727e  mov     rax, [rsp+118h+var_78]
0x180007286  mov     [rsi+34h], eax
0x180007289  mov     dword ptr [rsi+38h], 78h ; 'x'
0x180007290  mov     dword ptr [rsi+3Ch], 79h ; 'y'
0x180007297  lea     rcx, [rsi+40h]; void *
0x18000729b  mov     r8, [rsp+118h+Size]; Size
0x1800072a3  mov     rdx, rbx; Src
0x1800072a6  call    memcpy_0
0x1800072ab  add     [rsp+118h+var_E0], rsi
0x1800072b0  mov     [rsp+118h+var_E8], edi
0x1800072b4  cmp     [rsp+118h+var_E4], edi
0x1800072b8  jbe     short loc_18000731E
0x1800072ba  mov     r14, [rsp+118h+var_E0]
0x1800072bf  mov     r15d, edi
0x1800072c2  mov     r12d, [rsp+118h+var_E4]
0x1800072c7  mov     ebx, r15d
0x1800072ca  mov     rdx, [r13+rbx*8+0]
0x1800072cf  movzx   r8d, word ptr [rdx]; Size
0x1800072d3  mov     rdx, [rdx+8]; Src
0x1800072d7  mov     rcx, r14; void *
0x1800072da  call    memcpy_0
0x1800072df  mov     rax, [r13+rbx*8+0]
0x1800072e4  movzx   ecx, word ptr [rax]
0x1800072e7  shr     rcx, 1
0x1800072ea  mov     [r14+rcx*2], di
0x1800072ef  mov     rax, [r13+rbx*8+0]
0x1800072f4  movzx   ecx, word ptr [rax]
0x1800072f7  add     r14, 2
0x1800072fb  add     r14, rcx
0x1800072fe  inc     r15d
0x180007301  cmp     r15d, r12d
0x180007304  jb      short loc_1800072C7
0x180007306  mov     r14, [rsp+118h+arg_0]
0x18000730e  mov     r15, [rsp+118h+var_58]
0x180007316  mov     r12, [rsp+118h+var_98]
0x18000731e  mov     rbx, [rsp+118h+var_78]
0x180007326  add     rbx, rsi
0x180007329  mov     r13, [rsp+118h+var_C0]
0x18000732e  cmp     [rsp+118h+arg_48], rdi
0x180007336  jz      short loc_18000734B
0x180007338  mov     r8, r13; Size
0x18000733b  mov     rdx, [rsp+118h+arg_48]; Src
0x180007343  mov     rcx, rbx; void *
0x180007346  call    memcpy_0
0x18000734b  add     rbx, r13
0x18000734e  mov     r8, r15; Size
0x180007351  lea     rdx, [rsp+118h+var_B8]; Src
0x180007356  mov     rcx, rbx; void *
0x180007359  call    memcpy_0
0x18000735e  mov     [rbx+r15], r12d
0x180007362  mov     rax, [rsp+118h+var_40]
0x18000736a  mov     [rsp+118h+var_98], rax
0x180007372  mov     [rsp+118h+var_88], rsi
0x18000737a  mov     rax, [r14+8]
0x18000737e  test    rax, rax
0x180007381  jz      short loc_180007387
0x180007383  lock inc dword ptr [rax+8]
0x180007387  mov     [rsp+118h+var_90], rax
0x18000738f  mov     eax, [rsp+118h+arg_58]
0x180007396  mov     [rsp+118h+var_80], eax
0x18000739d  mov     [rsp+118h+var_7C], edi
0x1800073a4  lea     rcx, [rsp+118h+var_98]; struct WRITE_PKT *
0x1800073ac  call    ?PerformWriteRequest@@YAJAEAUWRITE_PKT@@@Z; PerformWriteRequest(WRITE_PKT &)
0x1800073b1  mov     ebx, eax
0x1800073b3  lea     rcx, [rsp+118h+var_88]
0x1800073bb  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800073c0  lea     rcx, [rsp+118h+var_90]
0x1800073c8  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x1800073cd  nop
0x1800073ce  mov     rcx, [rsp+118h+var_A0]; void *
0x1800073d3  test    rcx, rcx
0x1800073d6  jnz     loc_180007962
0x1800073dc  mov     rcx, [rsp+118h+var_C8]; void *
0x1800073e1  test    rcx, rcx
0x1800073e4  jnz     loc_18000796C
0x1800073ea  mov     eax, ebx
0x1800073ec  add     rsp, 0E0h
0x1800073f3  pop     r15
0x1800073f5  pop     r14
0x1800073f7  pop     r13
0x1800073f9  pop     r12
0x1800073fb  pop     rdi
0x1800073fc  pop     rsi
0x1800073fd  pop     rbx
0x1800073fe  retn
0x1800073ff  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x180007406  add     rcx, 0E8h
0x18000740d  mov     rax, [r15+20h]
0x180007411  mov     r10, [rax+58h]
0x180007415  mov     r8, [rax+60h]
0x180007419  sub     r8, r10
0x18000741c  sar     r8, 1
0x18000741f  lea     r9, [r14+34h]
0x180007423  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007427  inc     rdx
0x18000742a  cmp     [r9+rdx*2], di
0x18000742f  jnz     short loc_180007427
0x180007431  mov     rax, [rsp+118h+var_D8]
0x180007436  mov     [rsp+118h+var_98], rax
0x18000743e  mov     rax, [rsp+118h+var_D0]
0x180007443  mov     [rsp+118h+var_90], rax
0x18000744b  mov     [rsp+118h+var_58], r10
0x180007453  mov     [rsp+118h+var_50], r8
0x18000745b  mov     [rsp+118h+Size], r9
0x180007463  mov     [rsp+118h+var_60], rdx
0x18000746b  lea     rax, [rsp+118h+var_98]
0x180007473  mov     [rsp+118h+var_F8], rax
0x180007478  lea     r9, [rsp+118h+var_58]
0x180007480  lea     r8, [rsp+118h+Size]
0x180007488  lea     rdx, [rsp+118h+var_C0]
0x18000748d  call    ?CreateLegacyPublisher@PublisherManager@@QEAA?AV?$AutoRef@VPublisher@@@wmi@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@00@Z; PublisherManager::CreateLegacyPublisher(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180007492  mov     rax, [rsp+118h+var_C0]
0x180007497  mov     [r14+8], rax
0x18000749b  jmp     loc_18000711B
0x1800074a0  cmp     [rsp+118h+arg_28], edi
0x1800074a7  jz      loc_1800070B2
0x1800074ad  lea     rbx, WPP_GLOBAL_Control
0x1800074b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074bb  cmp     rcx, rbx
0x1800074be  jz      short loc_18000753D
0x1800074c0  test    dword ptr [rcx+1Ch], 1000h
0x1800074c7  jz      short loc_18000753D
0x1800074c9  cmp     byte ptr [rcx+19h], 2
0x1800074cd  jb      short loc_18000753D
0x1800074cf  mov     edx, 44h ; 'D'
0x1800074d4  jmp     loc_18000783E
0x1800074d9  lea     rbx, WPP_GLOBAL_Control
0x1800074e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074e7  cmp     rcx, rbx
0x1800074ea  jnz     loc_180007708
0x1800074f0  mov     rcx, [rsp+118h+var_C8]; void *
0x1800074f5  test    rcx, rcx
0x1800074f8  jnz     loc_18000773C
0x1800074fe  mov     eax, esi
0x180007500  jmp     loc_1800073EC
0x180007505  lea     rbx, WPP_GLOBAL_Control
0x18000750c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007513  cmp     rcx, rbx
0x180007516  jnz     loc_180007800
0x18000751c  mov     ebx, 0C0000008h
0x180007521  jmp     loc_1800073CE
0x180007526  lea     rbx, WPP_GLOBAL_Control
0x18000752d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007534  cmp     rcx, rbx
0x180007537  jnz     loc_1800078F5
  ... truncated ...
```
