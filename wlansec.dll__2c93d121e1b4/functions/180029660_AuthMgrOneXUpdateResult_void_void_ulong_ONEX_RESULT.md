# AuthMgrOneXUpdateResult(void *,void *,ulong,_ONEX_RESULT *)

- ea: `0x180029660`
- end: `0x18002a02b`
- name: `?AuthMgrOneXUpdateResult@@YAKPEAX0KPEAU_ONEX_RESULT@@@Z`
- size: `2507`
- prototype: `unsigned int __fastcall(void *, void *, unsigned int, struct _ONEX_RESULT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x18000b348`
- `0x18000c444`
- `0x1800169c0`
- `0x180024ca4`
- `0x180027510`
- `0x180027c70`
- `0x180027fbc`
- `0x180029660`
- `0x18002a638`
- `0x18002b170`
- `0x18003f1cc`
- `0x180043a30`
- `0x180044554`
- `0x18004456c`
- `0x180064350`
- `0x180074048`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029b7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029b7f`
- `MobileNetworking!ReleaseWriteLock` at `0x18002983d`
- `MobileNetworking!ReleaseWriteLock` at `0x180029f7e`
- `MobileNetworking!ReleaseWriteLock` at `0x18002983d`
- `MobileNetworking!ReleaseWriteLock` at `0x180029f7e`
- `MobileNetworking!AcquireWriteLock` at `0x1800297c4`
- `MobileNetworking!AcquireWriteLock` at `0x180029c9b`
- `MobileNetworking!AcquireWriteLock` at `0x180029e27`
- `MobileNetworking!AcquireWriteLock` at `0x1800297c4`
- `MobileNetworking!AcquireWriteLock` at `0x180029c9b`
- `MobileNetworking!AcquireWriteLock` at `0x180029e27`

## string_xrefs

- `0x1800297b0`: `AuthMgrOneXUpdateResult`
- `0x180029829`: `AuthMgrOneXUpdateResult`
- `0x180029c87`: `AuthMgrOneXUpdateResult`
- `0x180029e13`: `AuthMgrOneXUpdateResult`
- `0x180029f70`: `AuthMgrOneXUpdateResult`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXUpdateResult(void *a1, void *a2, __int64 a3, struct _ONEX_RESULT *a4)
{
  unsigned int v7; // eax
  unsigned int v8; // r13d
  PVOID *v9; // rcx
  struct MSMSEC_PORT_CONTEXT *v10; // r15
  _DWORD *v11; // rcx
  enum _DOT11_BSS_TYPE v12; // eax
  int v13; // ebx
  unsigned int v14; // esi
  PVOID *v15; // rcx
  unsigned int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r9
  bool v20; // zf
  struct MSMSEC_PORT_CONTEXT *v21; // r14
  char *v22; // rdx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rcx
  struct _LUID v27; // rbx
  __int64 v28; // rbx
  int v29; // edi
  __int64 v30; // r9
  unsigned int v31; // r8d
  unsigned int v32; // edi
  char *v33; // rcx
  DWORD v34; // esi
  unsigned int v35; // eax
  size_t v36; // r8
  __int64 v37; // rbx
  int v38; // edi
  void *v39; // rax
  unsigned int v40; // ebx
  DWORD v41; // edi
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  unsigned __int8 (*v45)[6]; // [rsp+28h] [rbp-D8h]
  int v46; // [rsp+78h] [rbp-88h]
  DWORD ReturnLength; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v48; // [rsp+84h] [rbp-7Ch]
  unsigned int v49[2]; // [rsp+88h] [rbp-78h]
  struct MSMSEC_PORT_CONTEXT *v50; // [rsp+90h] [rbp-70h] BYREF
  enum _DOT11_BSS_TYPE v51; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v52; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v53; // [rsp+A8h] [rbp-58h]
  struct MSMSEC_INTF_CONTEXT *v54; // [rsp+B0h] [rbp-50h] BYREF
  void *v55; // [rsp+B8h] [rbp-48h]
  __int128 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-30h]
  struct _GUID v58; // [rsp+D8h] [rbp-28h] BYREF
  _DOT11_SSID v59; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD TokenInformation[3]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v61; // [rsp+140h] [rbp+40h]
  unsigned __int16 v62[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v63[2042]; // [rsp+154h] [rbp+54h] BYREF
  __int16 v64; // [rsp+94Eh] [rbp+84Eh]

  v55 = a1;
  v54 = 0;
  v50 = 0;
  v57 = 0;
  *(_QWORD *)v49 = 0;
  *(_DWORD *)v62 = 0;
  v56 = 0;
  memset(&v59, 0, sizeof(v59));
  v58 = 0;
  memset_0(v63, 0, 0x7FCu);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v7 = PreCallbackActions(a1, a2, &v54, &v50, (struct _AUTHMGR_LOCK_STATE *)&v56);
  v8 = v7;
  if ( !v7 )
  {
    v10 = v50;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        30,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v50 + 78));
    TraceAdapterId(*(_DWORD *)(*((_QWORD *)v10 + 3) + 2496LL), ">>> Locking >>>");
    AcquireWriteLock(*((_QWORD *)v10 + 3), *((_QWORD *)v10 + 3) + 2512LL, "AuthMgrOneXUpdateResult", 267);
    v59 = *(_DOT11_SSID *)(*((_QWORD *)v10 + 3) + 2728LL);
    v58 = *(struct _GUID *)(*((_QWORD *)v10 + 3) + 32LL);
    v11 = (_DWORD *)*((_QWORD *)v10 + 3);
    v12 = v11[691];
    v13 = v11[660];
    LODWORD(v11) = v11[624];
    v51 = v12;
    TraceAdapterId((unsigned int)v11, "<<< Unlocking <<<");
    ReleaseWriteLock(*((_QWORD *)v10 + 3), *((_QWORD *)v10 + 3) + 2512LL, "AuthMgrOneXUpdateResult", 272);
    v14 = *((_DWORD *)a4 + 1);
    v48 = v14;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        31,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v10 + 78),
        *((_DWORD *)a4 + 4));
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    switch ( *(_DWORD *)a4 )
    {
      case 1:
        if ( (*((_BYTE *)a4 + 16) & 3) != 0 )
        {
          v16 = 13;
          if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
            goto LABEL_59;
          v17 = 40;
        }
        else
        {
          v16 = 11;
          if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
            goto LABEL_59;
          v17 = 41;
        }
        break;
      case 2:
        v14 = 294927;
        v16 = 9;
        v48 = 294927;
        if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
          goto LABEL_59;
        v17 = 33;
        break;
      case 3:
        if ( (v13 & 4) != 0 )
        {
          v14 = 294933;
          v16 = 9;
          v48 = 294933;
          if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
            goto LABEL_59;
          v17 = 34;
          break;
        }
        if ( !*((_DWORD *)a4 + 9) || !*((_DWORD *)a4 + 11) )
        {
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 2) != 0 )
          {
            WPP_SF_d(v15[7], 35, WPP_20060763357235bdafa6f501eee46e60_Traceguids, *((unsigned int *)v10 + 78));
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          v8 = 87;
          if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
            goto LABEL_105;
          v18 = 36;
LABEL_37:
          v19 = *((unsigned int *)v10 + 78);
          goto LABEL_38;
        }
        if ( !*((_DWORD *)a4 + 5) )
        {
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 2) != 0 )
          {
            WPP_SF_d(v15[7], 37, WPP_20060763357235bdafa6f501eee46e60_Traceguids, *((unsigned int *)v10 + 78));
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          v8 = 87;
          if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
            goto LABEL_105;
          v18 = 38;
          goto LABEL_37;
        }
        v16 = 10;
        if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 68) & 2) == 0 )
          goto LABEL_59;
        v17 = 39;
        break;
      case 4:
        v16 = 9;
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 2) != 0 )
          WPP_SF_LLL(
            v15[7],
            32,
            WPP_20060763357235bdafa6f501eee46e60_Traceguids,
            *((unsigned int *)v10 + 78),
            *((_DWORD *)a4 + 1),
            *((_DWORD *)a4 + 2));
LABEL_59:
        v20 = *((_DWORD *)a4 + 5) == 0;
        v21 = (struct MSMSEC_PORT_CONTEXT *)&byte_18009AFB8;
        v50 = (struct MSMSEC_PORT_CONTEXT *)&byte_18009AFB8;
        v53 = (unsigned __int16 *)&byte_18009AFB8;
        v52 = (unsigned __int16 *)&byte_18009AFB8;
        if ( v20 )
          goto LABEL_72;
        v22 = (char *)a4 + *((unsigned int *)a4 + 6);
        if ( (v22[20] & 8) != 0 )
        {
          v21 = (struct MSMSEC_PORT_CONTEXT *)&v22[*((unsigned int *)v22 + 13)];
          v23 = (unsigned __int64)*((unsigned int *)v22 + 12) >> 1;
          v50 = v21;
          *((_WORD *)v21 + v23 - 1) = 0;
        }
        if ( (v22[20] & 0x10) != 0 )
        {
          v24 = (unsigned __int64)*((unsigned int *)v22 + 14) >> 1;
          v53 = (unsigned __int16 *)&v22[*((unsigned int *)v22 + 15)];
          v53[v24 - 1] = 0;
        }
        if ( (v22[20] & 0x20) != 0 )
        {
          v25 = (unsigned __int64)*((unsigned int *)v22 + 16) >> 1;
          v52 = (unsigned __int16 *)&v22[*((unsigned int *)v22 + 17)];
          v52[v25 - 1] = 0;
        }
        if ( (v22[20] & 2) != 0
          && (v26 = (void *)*((_QWORD *)v22 + 4)) != 0
          && (v61 = 0,
              ReturnLength = 0,
              memset(TokenInformation, 0, sizeof(TokenInformation)),
              GetTokenInformation(v26, TokenStatistics, TokenInformation, 0x38u, &ReturnLength)) )
        {
          v27 = *(struct _LUID *)v49;
          if ( ReturnLength == 56 )
            v27 = (struct _LUID)*((_QWORD *)&TokenInformation[0] + 1);
        }
        else
        {
LABEL_72:
          v27 = *(struct _LUID *)v49;
        }
        if ( v16 != 9 )
        {
          if ( v16 != 10 )
          {
            v8 = CreateAndQueuePortEvent(v10, v16, 1);
            goto LABEL_101;
          }
          v8 = AuthMgrNotifyAuthSuccessWithKeys(
                 v10,
                 *((_DWORD *)a4 + 9),
                 (unsigned __int8 *)a4 + *((unsigned int *)a4 + 10),
                 *((_DWORD *)a4 + 11),
                 (unsigned __int8 *)a4 + *((unsigned int *)a4 + 12),
                 *((_DWORD *)a4 + 5),
                 (unsigned __int8 *)a4 + *((unsigned int *)a4 + 6));
          AuditLogRecordOneXResult(
            1u,
            qword_1800AEFA0,
            &v59,
            (unsigned __int16 *)v21,
            v27,
            (unsigned __int8 (*)[6])((char *)v10 + 302),
            (unsigned __int8 (*)[6])((char *)v10 + 296),
            &v58,
            0,
            0,
            0,
            0,
            0);
          TraceAdapterId(*(_DWORD *)(*((_QWORD *)v10 + 3) + 2496LL), ">>> Locking >>>");
          AcquireWriteLock(*((_QWORD *)v10 + 3), *((_QWORD *)v10 + 3) + 2512LL, "AuthMgrOneXUpdateResult", 421);
          v28 = *((_QWORD *)v10 + 3);
          v29 = (*((_DWORD *)a4 + 4) >> 2) & 1;
          SecMgrCorrelateToSession(*(void **)(v28 + 2632));
          MSMSecLogOneXSuccess(
            (unsigned __int16 *)(*((_QWORD *)v10 + 3) + 48LL),
            &v58,
            (unsigned __int8 (*)[6])((char *)v10 + 296),
            &v59,
            v51,
            v45,
            (unsigned __int16 *)v21,
            v53,
            v52,
            *(void **)(v28 + 2632),
            v29);
          TraceAdapterId(*(_DWORD *)(*((_QWORD *)v10 + 3) + 2496LL), "<<< Unlocking <<<");
          v30 = 434;
LABEL_100:
          ReleaseWriteLock(*((_QWORD *)v10 + 3), *((_QWORD *)v10 + 3) + 2512LL, "AuthMgrOneXUpdateResult", v30);
LABEL_101:
          if ( !v8 )
            goto LABEL_105;
          v15 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_105;
          v18 = 45;
          v19 = v8;
LABEL_38:
          WPP_SF_d(v15[7], v18, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v19);
LABEL_105:
          PostCallbackActions(v55, v54, v10, (struct _AUTHMGR_LOCK_STATE *)&v56);
          goto LABEL_106;
        }
        v31 = *((_DWORD *)a4 + 2);
        v32 = 0;
        v49[0] = 0;
        ReturnLength = 0;
        v8 = AuthMgrNotifyAuthFailure(v10, v14, v31);
        if ( v14 == 327685 && *((_DWORD *)a4 + 7) >= 0x5Cu )
        {
          v33 = (char *)a4 + *((unsigned int *)a4 + 8);
          v20 = (v33[72] & 1) == 0;
          v32 = *((_DWORD *)v33 + 5);
          v34 = *(_DWORD *)v33;
          v49[0] = v32;
          ReturnLength = v34;
          if ( !v20 )
          {
            v35 = *((_DWORD *)v33 + 19);
            if ( v35 )
            {
              v36 = 2048;
              if ( v35 < 0x800 )
                v36 = v35;
              memcpy_0(v62, &v33[*((unsigned int *)v33 + 20)], v36);
              v64 = 0;
            }
          }
        }
        AuditLogRecordOneXResult(
          0,
          qword_1800AEFA0,
          &v59,
          (unsigned __int16 *)v50,
          v27,
          (unsigned __int8 (*)[6])((char *)v10 + 302),
          (unsigned __int8 (*)[6])((char *)v10 + 296),
          &v58,
          v48,
          *((_DWORD *)a4 + 2),
          v32,
          v62,
          ReturnLength);
        TraceAdapterId(*(_DWORD *)(*((_QWORD *)v10 + 3) + 2496LL), ">>> Locking >>>");
        AcquireWriteLock(*((_QWORD *)v10 + 3), *((_QWORD *)v10 + 3) + 2512LL, "AuthMgrOneXUpdateResult", 479);
        v37 = *((_QWORD *)v10 + 3);
        v38 = (*((_DWORD *)a4 + 4) >> 2) & 1;
        SecMgrCorrelateToSession(*(void **)(v37 + 2632));
        v39 = *(void **)(v37 + 2632);
        v40 = v49[0];
        v46 = v38;
        v41 = ReturnLength;
        MSMSecLogOneXFailure(
          (unsigned __int16 *)(*((_QWORD *)v10 + 3) + 48LL),
          &v58,
          (unsigned __int8 (*)[6])((char *)v10 + 296),
          &v59,
          v51,
          (unsigned __int8 (*)[6])((char *)v10 + 302),
          (unsigned __int16 *)v50,
          v53,
          v52,
          v48,
          *((_DWORD *)a4 + 2),
          v49[0],
          v62,
          ReturnLength,
          v39,
          v46);
        if ( v40 != -2143158016 && v40 != -2143158014 && v40 != 1078067222 )
        {
          if ( v40 == 798 )
          {
            v40 = -2143158016;
          }
          else if ( v40 != -2143156992 )
          {
            v40 = -2143157998;
            if ( v41 != -2143157998 )
            {
LABEL_99:
              TraceAdapterId(*(_DWORD *)(*((_QWORD *)v10 + 3) + 2496LL), "<<< Unlocking <<<");
              v30 = 523;
              goto LABEL_100;
            }
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
            {
LABEL_98:
              NotifyOneXEapAuthErrors(v10, v40);
              goto LABEL_99;
            }
            v43 = 44;
LABEL_97:
            WPP_SF_(v42[7], v43, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
            goto LABEL_98;
          }
        }
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
          goto LABEL_98;
        v43 = 43;
        goto LABEL_97;
      default:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 2) != 0 )
          WPP_SF_dd(
            v15[7],
            42,
            WPP_20060763357235bdafa6f501eee46e60_Traceguids,
            *((unsigned int *)v10 + 78),
            *(_DWORD *)a4);
        goto LABEL_105;
    }
    WPP_SF_d(v15[7], v17, WPP_20060763357235bdafa6f501eee46e60_Traceguids, *((unsigned int *)v10 + 78));
    goto LABEL_59;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v7);
LABEL_106:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
    WPP_SF_d(v9[7], 46, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180029660  mov     [rsp-8+arg_10], rbx
0x180029665  push    rbp
0x180029666  push    rsi
0x180029667  push    rdi
0x180029668  push    r12
0x18002966a  push    r13
0x18002966c  push    r14
0x18002966e  push    r15
0x180029670  lea     rbp, [rsp-860h]
0x180029678  sub     rsp, 960h
0x18002967f  mov     rax, cs:__security_cookie
0x180029686  xor     rax, rsp
0x180029689  mov     [rbp+890h+var_40], rax
0x180029690  xor     edi, edi
0x180029692  mov     [rbp+890h+var_8D8], rcx
0x180029696  xorps   xmm0, xmm0
0x180029699  mov     [rbp+890h+var_8E0], rdi
0x18002969d  xor     eax, eax
0x18002969f  mov     [rbp+890h+var_900], rdi
0x1800296a3  mov     rbx, rdx
0x1800296a6  mov     [rbp+890h+var_8C0], rax
0x1800296aa  mov     rsi, rcx
0x1800296ad  mov     qword ptr [rbp+890h+var_908], rdi
0x1800296b1  xor     edx, edx; Val
0x1800296b3  mov     dword ptr [rbp+890h+var_8A8.ucSSID+1Ch], eax
0x1800296b6  lea     rcx, [rbp+890h+var_83C]; void *
0x1800296ba  mov     dword ptr [rbp+890h+var_840], edi
0x1800296bd  mov     r8d, 7FCh; Size
0x1800296c3  mov     r12, r9
0x1800296c6  movups  [rbp+890h+var_8D0], xmm0
0x1800296ca  movups  xmmword ptr [rbp+890h+var_8A8.uSSIDLength], xmm0
0x1800296ce  movups  xmmword ptr [rbp+890h+var_8A8.ucSSID+0Ch], xmm0
0x1800296d2  movups  xmmword ptr [rbp+890h+var_8B8.Data1], xmm0
0x1800296d6  call    memset_0
0x1800296db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296e2  lea     r14, WPP_GLOBAL_Control
0x1800296e9  cmp     rcx, r14
0x1800296ec  jz      short loc_18002970A
0x1800296ee  test    dword ptr [rcx+44h], 100h
0x1800296f5  jz      short loc_18002970A
0x1800296f7  mov     rcx, [rcx+38h]
0x1800296fb  lea     edx, [rdi+1Ch]
0x1800296fe  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180029705  call    WPP_SF_
0x18002970a  lea     rax, [rbp+890h+var_8D0]
0x18002970e  mov     rdx, rbx; void *
0x180029711  lea     r9, [rbp+890h+var_900]; struct MSMSEC_PORT_CONTEXT **
0x180029715  mov     [rsp+990h+ReturnLength], rax; struct _AUTHMGR_LOCK_STATE *
0x18002971a  lea     r8, [rbp+890h+var_8E0]; struct MSMSEC_INTF_CONTEXT **
0x18002971e  mov     rcx, rsi; void *
0x180029721  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x180029726  mov     r13d, eax
0x180029729  test    eax, eax
0x18002972b  jz      short loc_180029764
0x18002972d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029734  cmp     rcx, r14
0x180029737  jz      loc_180029FFD
0x18002973d  test    byte ptr [rcx+44h], 1
0x180029741  jz      loc_180029FD7
0x180029747  mov     rcx, [rcx+38h]
0x18002974b  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180029752  mov     edx, 1Dh
0x180029757  mov     r9d, eax
0x18002975a  call    WPP_SF_d
0x18002975f  jmp     loc_180029FD0
0x180029764  mov     rcx, cs:WPP_GLOBAL_Control
0x18002976b  mov     r15, [rbp+890h+var_900]
0x18002976f  cmp     rcx, r14
0x180029772  jz      short loc_180029796
0x180029774  test    byte ptr [rcx+44h], 20h
0x180029778  jz      short loc_180029796
0x18002977a  mov     r9d, [r15+138h]
0x180029781  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180029788  mov     rcx, [rcx+38h]
0x18002978c  mov     edx, 1Eh
0x180029791  call    WPP_SF_d
0x180029796  mov     rcx, [r15+18h]
0x18002979a  lea     rdx, aLocking; ">>> Locking >>>"
0x1800297a1  mov     ecx, [rcx+9C0h]; unsigned int
0x1800297a7  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800297ac  mov     rcx, [r15+18h]
0x1800297b0  lea     r8, aAuthmgronexupd; "AuthMgrOneXUpdateResult"
0x1800297b7  mov     r9d, 10Bh
0x1800297bd  lea     rdx, [rcx+9D0h]
0x1800297c4  call    cs:__imp_AcquireWriteLock
0x1800297cb  nop     dword ptr [rax+rax+00h]
0x1800297d0  mov     rax, [r15+18h]
0x1800297d4  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800297db  movups  xmm0, xmmword ptr [rax+0AA8h]
0x1800297e2  movups  xmmword ptr [rbp+890h+var_8A8.uSSIDLength], xmm0
0x1800297e6  movups  xmm1, xmmword ptr [rax+0AB8h]
0x1800297ed  movups  xmmword ptr [rbp+890h+var_8A8.ucSSID+0Ch], xmm1
0x1800297f1  mov     eax, [rax+0AC8h]
0x1800297f7  mov     dword ptr [rbp+890h+var_8A8.ucSSID+1Ch], eax
0x1800297fa  mov     rax, [r15+18h]
0x1800297fe  movups  xmm0, xmmword ptr [rax+20h]
0x180029802  movdqu  xmmword ptr [rbp+890h+var_8B8.Data1], xmm0
0x180029807  mov     rcx, [r15+18h]
0x18002980b  mov     eax, [rcx+0ACCh]
0x180029811  mov     ebx, [rcx+0A50h]
0x180029817  mov     ecx, [rcx+9C0h]; unsigned int
0x18002981d  mov     [rbp+890h+var_8F8], eax
0x180029820  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180029825  mov     rcx, [r15+18h]
0x180029829  lea     r8, aAuthmgronexupd; "AuthMgrOneXUpdateResult"
0x180029830  mov     r9d, 110h
0x180029836  lea     rdx, [rcx+9D0h]
0x18002983d  call    cs:__imp_ReleaseWriteLock
0x180029844  nop     dword ptr [rax+rax+00h]
0x180029849  mov     esi, [r12+4]
0x18002984e  mov     [rbp+890h+var_90C], esi
0x180029851  mov     rcx, cs:WPP_GLOBAL_Control
0x180029858  cmp     rcx, r14
0x18002985b  jz      short loc_18002988F
0x18002985d  test    byte ptr [rcx+44h], 2
0x180029861  jz      short loc_18002988F
0x180029863  mov     eax, [r12+10h]
0x180029868  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002986f  mov     r9d, [r15+138h]
0x180029876  mov     edx, 1Fh
0x18002987b  mov     rcx, [rcx+38h]
0x18002987f  mov     dword ptr [rsp+990h+ReturnLength], eax
0x180029883  call    WPP_SF_dd
0x180029888  mov     rcx, cs:WPP_GLOBAL_Control
0x18002988f  mov     r8d, [r12]
0x180029893  mov     eax, 9
0x180029898  mov     edx, r8d
0x18002989b  sub     edx, 1
0x18002989e  jz      loc_180029A76
0x1800298a4  sub     edx, 1
0x1800298a7  jz      loc_180029A5A
0x1800298ad  sub     edx, 1
0x1800298b0  jz      loc_18002993A
0x1800298b6  cmp     edx, 1
0x1800298b9  jz      short loc_1800298F2
0x1800298bb  cmp     rcx, r14
0x1800298be  jz      loc_180029FBC
0x1800298c4  test    byte ptr [rcx+44h], 2
0x1800298c8  jz      loc_180029FBC
0x1800298ce  mov     r9d, [r15+138h]
0x1800298d5  lea     edx, [rax+21h]
0x1800298d8  mov     rcx, [rcx+38h]
0x1800298dc  mov     dword ptr [rsp+990h+ReturnLength], r8d
0x1800298e1  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x1800298e8  call    WPP_SF_dd
0x1800298ed  jmp     loc_180029FBC
0x1800298f2  mov     edi, eax
0x1800298f4  cmp     rcx, r14
0x1800298f7  jz      loc_180029ABD
0x1800298fd  test    byte ptr [rcx+44h], 2
0x180029901  jz      loc_180029ABD
0x180029907  mov     eax, [r12+8]
0x18002990c  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180029913  mov     r9d, [r15+138h]
0x18002991a  mov     edx, 20h ; ' '
0x18002991f  mov     rcx, [rcx+38h]
0x180029923  mov     dword ptr [rsp+990h+var_968], eax
0x180029927  mov     eax, [r12+4]
0x18002992c  mov     dword ptr [rsp+990h+ReturnLength], eax
0x180029930  call    WPP_SF_LLL
0x180029935  jmp     loc_180029ABD
0x18002993a  test    bl, 4
0x18002993d  jz      short loc_180029966
0x18002993f  mov     esi, 48015h
0x180029944  mov     edi, eax
0x180029946  mov     [rbp+890h+var_90C], esi
0x180029949  cmp     rcx, r14
0x18002994c  jz      loc_180029ABD
0x180029952  test    byte ptr [rcx+44h], 2
0x180029956  jz      loc_180029ABD
0x18002995c  mov     edx, 22h ; '"'
0x180029961  jmp     loc_180029AA6
0x180029966  cmp     [r12+24h], edi
0x18002996b  jz      loc_180029A0A
0x180029971  cmp     [r12+2Ch], edi
0x180029976  jz      loc_180029A0A
0x18002997c  cmp     [r12+14h], edi
0x180029981  jnz     short loc_1800299EA
0x180029983  cmp     rcx, r14
0x180029986  jz      short loc_1800299B1
0x180029988  test    byte ptr [rcx+44h], 2
0x18002998c  jz      short loc_1800299B1
0x18002998e  mov     r9d, [r15+138h]
0x180029995  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002999c  mov     rcx, [rcx+38h]
0x1800299a0  mov     edx, 25h ; '%'
0x1800299a5  call    WPP_SF_d
0x1800299aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299b1  mov     r13d, 57h ; 'W'
0x1800299b7  cmp     rcx, r14
0x1800299ba  jz      loc_180029FBC
0x1800299c0  test    byte ptr [rcx+44h], 2
0x1800299c4  jz      loc_180029FBC
0x1800299ca  lea     edx, [r13-31h]
0x1800299ce  mov     r9d, [r15+138h]
0x1800299d5  mov     rcx, [rcx+38h]
0x1800299d9  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x1800299e0  call    WPP_SF_d
0x1800299e5  jmp     loc_180029FBC
0x1800299ea  mov     edi, 0Ah
0x1800299ef  cmp     rcx, r14
0x1800299f2  jz      loc_180029ABD
0x1800299f8  test    byte ptr [rcx+44h], 2
0x1800299fc  jz      loc_180029ABD
0x180029a02  lea     edx, [rdi+1Dh]
0x180029a05  jmp     loc_180029AA6
0x180029a0a  cmp     rcx, r14
0x180029a0d  jz      short loc_180029A38
0x180029a0f  test    byte ptr [rcx+44h], 2
0x180029a13  jz      short loc_180029A38
0x180029a15  mov     r9d, [r15+138h]
0x180029a1c  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180029a23  mov     rcx, [rcx+38h]
0x180029a27  mov     edx, 23h ; '#'
0x180029a2c  call    WPP_SF_d
0x180029a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a38  mov     r13d, 57h ; 'W'
0x180029a3e  cmp     rcx, r14
0x180029a41  jz      loc_180029FBC
0x180029a47  test    byte ptr [rcx+44h], 2
0x180029a4b  jz      loc_180029FBC
0x180029a51  lea     edx, [r13-33h]
0x180029a55  jmp     loc_1800299CE
0x180029a5a  mov     esi, 4800Fh
0x180029a5f  mov     edi, eax
0x180029a61  mov     [rbp+890h+var_90C], esi
0x180029a64  cmp     rcx, r14
0x180029a67  jz      short loc_180029ABD
0x180029a69  test    byte ptr [rcx+44h], 2
0x180029a6d  jz      short loc_180029ABD
0x180029a6f  mov     edx, 21h ; '!'
0x180029a74  jmp     short loc_180029AA6
0x180029a76  test    byte ptr [r12+10h], 3
0x180029a7c  jnz     short loc_180029A93
0x180029a7e  mov     edi, 0Bh
0x180029a83  cmp     rcx, r14
0x180029a86  jz      short loc_180029ABD
0x180029a88  test    byte ptr [rcx+44h], 2
0x180029a8c  jz      short loc_180029ABD
0x180029a8e  lea     edx, [rdi+1Eh]
0x180029a91  jmp     short loc_180029AA6
0x180029a93  mov     edi, 0Dh
0x180029a98  cmp     rcx, r14
0x180029a9b  jz      short loc_180029ABD
0x180029a9d  test    byte ptr [rcx+44h], 2
0x180029aa1  jz      short loc_180029ABD
0x180029aa3  lea     edx, [rdi+1Bh]
0x180029aa6  mov     r9d, [r15+138h]
0x180029aad  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180029ab4  mov     rcx, [rcx+38h]
0x180029ab8  call    WPP_SF_d
0x180029abd  cmp     dword ptr [r12+14h], 0
0x180029ac3  lea     r14, byte_18009AFB8
0x180029aca  mov     [rbp+890h+var_900], r14
0x180029ace  mov     [rbp+890h+var_8E8], r14
0x180029ad2  mov     [rbp+890h+var_8F0], r14
0x180029ad6  jz      loc_180029B9E
0x180029adc  mov     edx, [r12+18h]
0x180029ae1  add     rdx, r12
0x180029ae4  test    byte ptr [rdx+14h], 8
0x180029ae8  jz      short loc_180029B03
0x180029aea  mov     r14d, [rdx+34h]
0x180029aee  mov     ecx, [rdx+30h]
0x180029af1  add     r14, rdx
0x180029af4  shr     rcx, 1
0x180029af7  xor     eax, eax
0x180029af9  mov     [rbp+890h+var_900], r14
0x180029afd  mov     [r14+rcx*2-2], ax
0x180029b03  test    byte ptr [rdx+14h], 10h
0x180029b07  jz      short loc_180029B22
0x180029b09  mov     r8d, [rdx+3Ch]
0x180029b0d  mov     ecx, [rdx+38h]
0x180029b10  add     r8, rdx
0x180029b13  shr     rcx, 1
0x180029b16  xor     eax, eax
0x180029b18  mov     [rbp+890h+var_8E8], r8
0x180029b1c  mov     [r8+rcx*2-2], ax
0x180029b22  test    byte ptr [rdx+14h], 20h
0x180029b26  jz      short loc_180029B41
0x180029b28  mov     r8d, [rdx+44h]
0x180029b2c  mov     ecx, [rdx+40h]
0x180029b2f  add     r8, rdx
0x180029b32  shr     rcx, 1
0x180029b35  xor     eax, eax
0x180029b37  mov     [rbp+890h+var_8F0], r8
0x180029b3b  mov     [r8+rcx*2-2], ax
0x180029b41  test    byte ptr [rdx+14h], 2
0x180029b45  jz      short loc_180029B9E
0x180029b47  mov     rcx, [rdx+20h]; TokenHandle
0x180029b4b  test    rcx, rcx
0x180029b4e  jz      short loc_180029B9E
0x180029b50  xor     eax, eax
0x180029b52  lea     r8, [rbp+890h+TokenInformation]; TokenInformation
0x180029b56  xorps   xmm0, xmm0
0x180029b59  mov     [rbp+890h+var_850], rax
0x180029b5d  mov     r9d, 38h ; '8'; TokenInformationLength
0x180029b63  mov     [rbp+890h+var_910], eax
0x180029b66  lea     rax, [rbp+890h+var_910]
0x180029b6a  movups  [rbp+890h+TokenInformation], xmm0
0x180029b6e  mov     [rsp+990h+ReturnLength], rax; ReturnLength
  ... truncated ...
```
