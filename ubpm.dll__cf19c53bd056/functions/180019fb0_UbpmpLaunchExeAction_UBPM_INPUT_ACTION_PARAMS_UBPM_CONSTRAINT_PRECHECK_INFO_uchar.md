# UbpmpLaunchExeAction(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)

- ea: `0x180019fb0`
- end: `0x18001a8a2`
- name: `?UbpmpLaunchExeAction@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z`
- size: `2290`
- prototype: `__int64 __fastcall(struct _UBPM_INPUT_ACTION_PARAMS *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019dc0`
- `0x18001c400`

## callees

- `0x180001fb0`
- `0x180004240`
- `0x180006650`
- `0x1800189f4`
- `0x180019d90`
- `0x180019fb0`
- `0x18001a8a8`
- `0x18001acb0`
- `0x18001b190`
- `0x18001e9f4`
- `0x18001f440`
- `0x18001f764`
- `0x180035000`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a799`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a799`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a7d5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a7d5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a566`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a566`
- `ntdll!RtlIsMultiSessionSku` at `0x18001a2eb`
- `ntdll!RtlIsMultiSessionSku` at `0x18001a2eb`
- `ntdll!RtlFreeHeap` at `0x18001a12c`
- `ntdll!RtlFreeHeap` at `0x18001a151`
- `ntdll!RtlFreeHeap` at `0x18001a12c`
- `ntdll!RtlFreeHeap` at `0x18001a151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a10f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a758`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a10f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a0e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a0e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a7a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a7a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001a2c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001a2c9`

## string_xrefs

- `0x18001a2a2`: `NT TASK`

## pseudocode

```c
__int64 __fastcall UbpmpLaunchExeAction(
        struct _UBPM_INPUT_ACTION_PARAMS *a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        unsigned __int8 *a3)
{
  PSID v6; // r14
  unsigned __int16 *v7; // rsi
  const WCHAR *v8; // rbx
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // r12
  __int64 v12; // rdx
  int v13; // r8d
  int InteractiveUserSidAndToken; // edi
  _QWORD *v15; // rcx
  __int64 v16; // r9
  int v17; // edx
  unsigned __int16 **v19; // rcx
  unsigned __int8 v20; // dl
  void *v21; // r8
  unsigned int v22; // ebx
  unsigned __int64 v23; // r14
  unsigned int v24; // r10d
  unsigned __int8 *v25; // r11
  const unsigned __int16 **v26; // rdi
  char v27; // si
  unsigned int v28; // r15d
  unsigned __int64 v29; // r12
  unsigned int v30; // r13d
  void **p_hObject; // rcx
  struct _GUID *v32; // r9
  __int64 v33; // rax
  unsigned int v34; // eax
  _QWORD *v35; // rcx
  __int64 v36; // r15
  const struct _EVENT_DESCRIPTOR *v37; // rdx
  void *v38; // rcx
  unsigned __int16 *v39; // r9
  unsigned int v40; // eax
  unsigned __int16 *v41; // r9
  void *v42; // rcx
  PSID *v43; // rcx
  __int64 v44; // r15
  unsigned int v45; // eax
  unsigned __int16 *v46; // r9
  int InteractiveToken; // eax
  PSID v48; // rsi
  DWORD LengthSid; // edi
  HLOCAL v50; // rax
  DWORD LastError; // eax
  unsigned __int64 v52; // [rsp+58h] [rbp-D8h]
  __int64 v53; // [rsp+B0h] [rbp-80h] BYREF
  unsigned __int16 *v54; // [rsp+B8h] [rbp-78h] BYREF
  PSID pSid; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-68h] BYREF
  PSID *v57; // [rsp+D0h] [rbp-60h]
  HANDLE hObject; // [rsp+D8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp-50h] BYREF
  PSID v60; // [rsp+E8h] [rbp-48h]
  unsigned __int16 **v61; // [rsp+F0h] [rbp-40h]
  void **v62; // [rsp+F8h] [rbp-38h]
  unsigned int v66; // [rsp+168h] [rbp+38h]

  v66 = -1;
  hObject = 0;
  v6 = 0;
  hMem = 0;
  v7 = 0;
  v60 = 0;
  v54 = 0;
  v8 = *(const WCHAR **)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL);
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( (unsigned int)v9 > 8 && CompareStringW(0x7Fu, 1u, v8, 7, L"NT TASK", 7) == 2 )
      v8 += 7;
  }
  v10 = *((_DWORD *)a1 + 14);
  if ( (v10 & 6) != 0 )
  {
    InteractiveUserSidAndToken = UbpmpRunConsumerAction(a1, a2, a3);
    if ( InteractiveUserSidAndToken
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
        InteractiveUserSidAndToken);
    }
    goto LABEL_15;
  }
  v11 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL);
  v12 = *(_QWORD *)(v11 + 32);
  if ( !v12 )
  {
    v66 = 0;
    goto LABEL_23;
  }
  v13 = *(_DWORD *)(v12 + 32);
  if ( (unsigned int)(v13 - 4) > 1 )
  {
    if ( *(_DWORD *)v12 == 2 )
    {
      if ( (v10 & 0x20000) != 0 && !*((_DWORD *)a1 + 9) && (unsigned __int8)RtlIsMultiSessionSku() )
      {
        InteractiveUserSidAndToken = 4320;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v17 = 55;
LABEL_65:
          v16 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
          goto LABEL_66;
        }
      }
      else
      {
        InteractiveUserSidAndToken = UbpmpHandleGroupSid(a1, a2, a3);
        if ( InteractiveUserSidAndToken )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
            v17 = 56;
LABEL_66:
            WPP_SF_Sd(
              v15[2],
              v17,
              (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
              *(_QWORD *)(v16 + 8),
              InteractiveUserSidAndToken);
            goto LABEL_15;
          }
        }
      }
      goto LABEL_15;
    }
    if ( *((_QWORD *)a1 + 5) && EqualSid(*(PSID *)(*(_QWORD *)(v12 + 8) + 8LL), *((PSID *)a1 + 5)) )
    {
      v42 = (void *)*((_QWORD *)a1 + 5);
      v57 = 0;
      LODWORD(v53) = 0;
      InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(v42, 0, (__int64)&v53);
      if ( !InteractiveUserSidAndToken )
      {
        if ( (_DWORD)v53 )
        {
          hObject = v57[1];
          v6 = *v57;
          v57[1] = 0;
          v60 = v6;
          *v57 = 0;
        }
        else
        {
          InteractiveUserSidAndToken = 1168;
        }
      }
      v43 = v57;
      if ( v57 )
      {
        if ( (_DWORD)v53 )
        {
          do
          {
            v44 = 4LL * (unsigned int)v7;
            if ( v43[v44 + 1] )
            {
              CloseHandle(v43[v44 + 1]);
              v43 = v57;
            }
            UBPM_MIDL_user_free(v43[v44]);
            v43 = v57;
            LODWORD(v7) = (_DWORD)v7 + 1;
          }
          while ( (unsigned int)v7 < (unsigned int)v53 );
        }
        UBPM_MIDL_user_free(v43);
      }
      if ( !InteractiveUserSidAndToken )
      {
        v66 = *((_DWORD *)a1 + 9);
        goto LABEL_23;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
          *((_DWORD *)a1 + 9),
          InteractiveUserSidAndToken);
      UbpmUtilsGetAccountNamesFromSid(*((_QWORD *)a1 + 5), 1, 0, 0, (__int64)&v54);
      if ( InteractiveUserSidAndToken != 1008 )
      {
LABEL_82:
        if ( InteractiveUserSidAndToken > 0 )
          v45 = (unsigned __int16)InteractiveUserSidAndToken | 0x80070000;
        else
          v45 = InteractiveUserSidAndToken;
        v7 = v54;
        v46 = L"(NONE)";
        if ( v54 )
          v46 = v54;
        ReportTaskEvent(g_hTaskEventManager, &JOB_START_FAILED, v8, v46, v45);
        goto LABEL_15;
      }
    }
    else
    {
      v33 = *((_QWORD *)a1 + 1);
      pSid = 0;
      LODWORD(v56) = 0;
      InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(
                                     *(PSID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v33 + 24) + 32LL) + 8LL) + 8LL),
                                     0,
                                     (__int64)&v56);
      if ( !InteractiveUserSidAndToken )
      {
        if ( (_DWORD)v56 )
        {
          hObject = (HANDLE)*((_QWORD *)pSid + 1);
          v34 = *((_DWORD *)pSid + 4);
          v6 = *(PSID *)pSid;
          *((_QWORD *)pSid + 1) = 0;
          v66 = v34;
          v60 = v6;
          *(_QWORD *)pSid = 0;
        }
        else
        {
          InteractiveUserSidAndToken = 1168;
        }
      }
      v35 = pSid;
      if ( pSid )
      {
        if ( (_DWORD)v56 )
        {
          do
          {
            v36 = 4LL * (unsigned int)v7;
            if ( v35[v36 + 1] )
            {
              CloseHandle((HANDLE)v35[v36 + 1]);
              v35 = pSid;
            }
            UBPM_MIDL_user_free(v35[4 * (unsigned int)v7]);
            v35 = pSid;
            LODWORD(v7) = (_DWORD)v7 + 1;
          }
          while ( (unsigned int)v7 < (unsigned int)v56 );
        }
        UBPM_MIDL_user_free(v35);
      }
      if ( !InteractiveUserSidAndToken )
        goto LABEL_23;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
          InteractiveUserSidAndToken);
      UbpmUtilsGetAccountNamesFromSid(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL) + 32LL) + 8LL) + 8LL),
        1,
        0,
        0,
        (__int64)&v54);
      if ( InteractiveUserSidAndToken != 1168 )
        goto LABEL_82;
    }
    v7 = v54;
    v39 = L"(NONE)";
    if ( v54 )
      v39 = v54;
    ReportTaskEvent(v38, v37, v8, v39);
    goto LABEL_15;
  }
  v66 = 0;
  LODWORD(v53) = 0;
  pSid = 0;
  if ( v13 != 4 && v13 != 5 )
  {
    InteractiveUserSidAndToken = 87;
    goto LABEL_58;
  }
  if ( (*(_BYTE *)(v12 + 76) & 4) == 0 )
    goto LABEL_56;
  InteractiveToken = UbpmTokenGetInteractiveToken(
                       *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL),
                       -1,
                       (unsigned int)&hObject,
                       (unsigned int)&v53,
                       (__int64)&pSid);
  if ( InteractiveToken )
  {
    InteractiveUserSidAndToken = 0;
    if ( InteractiveToken != 1168 )
      InteractiveUserSidAndToken = InteractiveToken;
    if ( !InteractiveUserSidAndToken )
    {
      v66 = v53;
LABEL_56:
      InteractiveUserSidAndToken = UbpmpTokenGetNonInteractiveToken(v11, 0, 0, v8, &hObject, &hMem);
      goto LABEL_57;
    }
  }
  else
  {
    v48 = pSid;
    LengthSid = GetLengthSid(pSid);
    v50 = LocalAlloc(0, LengthSid);
    hMem = v50;
    if ( v50 )
    {
      if ( CopySid(LengthSid, v50, v48) )
      {
        v66 = v53;
        goto LABEL_23;
      }
      LastError = GetLastError();
      InteractiveUserSidAndToken = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
          (_DWORD)v8,
          LastError);
      v66 = v53;
LABEL_57:
      if ( InteractiveUserSidAndToken )
        goto LABEL_58;
LABEL_23:
      v19 = (unsigned __int16 **)*((_QWORD *)a1 + 14);
      v20 = *((_BYTE *)a1 + 108);
      v21 = (void *)*((_QWORD *)a1 + 5);
      v22 = *((_DWORD *)a1 + 8);
      v23 = *((_QWORD *)a1 + 10);
      v24 = *((_DWORD *)a1 + 26);
      v25 = (unsigned __int8 *)*((_QWORD *)a1 + 3);
      v26 = (const unsigned __int16 **)*((_QWORD *)a1 + 12);
      v27 = *((_BYTE *)a1 + 88);
      v28 = *((_DWORD *)a1 + 18);
      v29 = *((_QWORD *)a1 + 8);
      v30 = *((_DWORD *)a1 + 14);
      v61 = v19;
      p_hObject = &hObject;
      if ( !hObject )
        p_hObject = 0;
      v32 = (struct _GUID *)*((_QWORD *)a1 + 6);
      v62 = p_hObject;
      v52 = v23;
      v6 = v60;
      InteractiveUserSidAndToken = UbpmpLaunchOneTask(
                                     *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)a1,
                                     a2,
                                     *((struct _UBPM_ACTION_PARAMS **)a1 + 1),
                                     v66,
                                     v60,
                                     p_hObject,
                                     hMem,
                                     v32,
                                     v30,
                                     v29,
                                     v28,
                                     v52,
                                     v27,
                                     v26,
                                     v22,
                                     v25,
                                     v24,
                                     v21,
                                     v20,
                                     (const unsigned __int16 **)v61,
                                     a3);
      if ( InteractiveUserSidAndToken
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
          *((_DWORD *)a1 + 9),
          InteractiveUserSidAndToken);
      }
      v7 = v54;
      goto LABEL_15;
    }
    InteractiveUserSidAndToken = 14;
    UBPM_MIDL_user_free(v48);
  }
LABEL_58:
  UbpmUtilsGetAccountNamesFromSid(
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL) + 32LL) + 8LL) + 8LL),
    1,
    0,
    0,
    (__int64)&v54);
  if ( InteractiveUserSidAndToken > 0 )
    v40 = (unsigned __int16)InteractiveUserSidAndToken | 0x80070000;
  else
    v40 = InteractiveUserSidAndToken;
  v7 = v54;
  v41 = L"(NONE)";
  if ( v54 )
    v41 = v54;
  ReportTaskEvent(g_hTaskEventManager, &JOB_START_FAILED, v8, v41, v40);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 54;
    goto LABEL_65;
  }
LABEL_15:
  LocalFree(hMem);
  if ( hObject )
    CloseHandle(hObject);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return (unsigned int)InteractiveUserSidAndToken;
}

```

## disassembly

```asm
0x180019fb0  mov     rax, rsp
0x180019fb3  mov     [rax+18h], r8
0x180019fb7  mov     [rax+10h], rdx
0x180019fbb  mov     [rax+8], rcx
0x180019fbf  push    rbp
0x180019fc0  push    rsi
0x180019fc1  push    rdi
0x180019fc2  mov     rbp, rsp
0x180019fc5  sub     rsp, 130h
0x180019fcc  mov     [rax-20h], rbx
0x180019fd0  mov     rdi, r8
0x180019fd3  mov     [rax-30h], r13
0x180019fd7  mov     r13, rcx
0x180019fda  mov     [rax-38h], r14
0x180019fde  mov     [rax-40h], r15
0x180019fe2  mov     r15, rdx
0x180019fe5  xor     eax, eax
0x180019fe7  mov     [rbp+arg_18], 0FFFFFFFFh
0x180019fee  mov     [rbp+hObject], rax
0x180019ff2  mov     r14d, eax
0x180019ff5  mov     [rbp+hMem], rax
0x180019ff9  mov     esi, eax
0x180019ffb  mov     [rbp+var_48], rax
0x180019fff  mov     [rbp+var_78], rax
0x18001a003  mov     rax, [rcx]
0x18001a006  mov     r9, [rax+18h]
0x18001a00a  mov     rbx, [r9+8]
0x18001a00e  test    rbx, rbx
0x18001a011  jz      short loc_18001A032
0x18001a013  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001a01a  nop     word ptr [rax+rax+00h]
0x18001a020  inc     rax
0x18001a023  cmp     [rbx+rax*2], si
0x18001a027  jnz     short loc_18001A020
0x18001a029  cmp     eax, 8
0x18001a02c  ja      loc_18001A2A2
0x18001a032  mov     ecx, [r13+38h]
0x18001a036  test    cl, 6
0x18001a039  jnz     loc_18001A0CC
0x18001a03f  mov     rax, [r13+8]
0x18001a043  mov     [rsp+130h+var_10], r12
0x18001a04b  mov     r12, [rax+18h]
0x18001a04f  mov     rdx, [r12+20h]
0x18001a054  test    rdx, rdx
0x18001a057  jz      loc_18001A164
0x18001a05d  mov     r8d, [rdx+20h]
0x18001a061  lea     eax, [r8-4]
0x18001a065  cmp     eax, 1
0x18001a068  jbe     loc_18001A459
0x18001a06e  cmp     dword ptr [rdx], 2
0x18001a071  jnz     loc_18001A329
0x18001a077  bt      ecx, 11h
0x18001a07b  jb      loc_18001A2E1
0x18001a081  mov     r8, rdi; unsigned __int8 *
0x18001a084  mov     rdx, r15; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18001a087  mov     rcx, r13; struct _UBPM_INPUT_ACTION_PARAMS *
0x18001a08a  call    ?UbpmpHandleGroupSid@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z; UbpmpHandleGroupSid(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)
0x18001a08f  mov     edi, eax
0x18001a091  test    eax, eax
0x18001a093  jz      loc_18001A24F
0x18001a099  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0a0  lea     rax, WPP_GLOBAL_Control
0x18001a0a7  cmp     rcx, rax
0x18001a0aa  jz      loc_18001A24F
0x18001a0b0  test    byte ptr [rcx+1Ch], 1
0x18001a0b4  jz      loc_18001A24F
0x18001a0ba  mov     rdx, [r13+0]
0x18001a0be  mov     r9, [rdx+18h]
0x18001a0c2  mov     edx, 38h ; '8'
0x18001a0c7  jmp     loc_18001A534
0x18001a0cc  mov     r8, rdi; unsigned __int8 *
0x18001a0cf  mov     rdx, r15; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18001a0d2  mov     rcx, r13; struct _UBPM_INPUT_ACTION_PARAMS *
0x18001a0d5  call    ?UbpmpRunConsumerAction@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z; UbpmpRunConsumerAction(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)
0x18001a0da  mov     edi, eax
0x18001a0dc  test    eax, eax
0x18001a0de  jnz     loc_18001A857
0x18001a0e4  mov     rcx, [rbp+hMem]; hMem
0x18001a0e8  call    cs:__imp_LocalFree
0x18001a0ee  mov     rcx, [rbp+hObject]; hObject
0x18001a0f2  mov     r15, [rsp+130h+var_28]
0x18001a0fa  mov     r13, [rsp+130h+var_18]
0x18001a102  mov     rbx, [rsp+130h+var_8]
0x18001a10a  test    rcx, rcx
0x18001a10d  jz      short loc_18001A115
0x18001a10f  call    cs:__imp_CloseHandle
0x18001a115  test    r14, r14
0x18001a118  jz      short loc_18001A132
0x18001a11a  mov     rcx, gs:60h
0x18001a123  mov     r8, r14; P
0x18001a126  xor     edx, edx; Flags
0x18001a128  mov     rcx, [rcx+30h]; HeapHandle
0x18001a12c  call    cs:__imp_RtlFreeHeap
0x18001a132  mov     r14, [rsp+130h+var_20]
0x18001a13a  test    rsi, rsi
0x18001a13d  jz      short loc_18001A157
0x18001a13f  mov     rcx, gs:60h
0x18001a148  mov     r8, rsi; P
0x18001a14b  xor     edx, edx; Flags
0x18001a14d  mov     rcx, [rcx+30h]; HeapHandle
0x18001a151  call    cs:__imp_RtlFreeHeap
0x18001a157  mov     eax, edi
0x18001a159  add     rsp, 130h
0x18001a160  pop     rdi
0x18001a161  pop     rsi
0x18001a162  pop     rbp
0x18001a163  retn
0x18001a164  mov     [rbp+arg_18], esi
0x18001a167  mov     rcx, [r13+70h]
0x18001a16b  xor     eax, eax
0x18001a16d  cmp     [rbp+hObject], rax
0x18001a171  movzx   edx, byte ptr [r13+6Ch]
0x18001a176  mov     r8, [r13+28h]
0x18001a17a  mov     ebx, [r13+20h]
0x18001a17e  mov     r14, [r13+50h]
0x18001a182  mov     r10d, [r13+68h]
0x18001a186  mov     r11, [r13+18h]
0x18001a18a  mov     rdi, [r13+60h]
0x18001a18e  movzx   esi, byte ptr [r13+58h]
0x18001a193  mov     r15d, [r13+48h]
0x18001a197  mov     r12, [r13+40h]
0x18001a19b  mov     r13d, [r13+38h]
0x18001a19f  mov     r9, [rbp+arg_0]
0x18001a1a3  mov     [rbp+var_40], rcx
0x18001a1a7  lea     rcx, [rbp+hObject]
0x18001a1ab  cmovz   rcx, rax
0x18001a1af  mov     rax, [rbp+arg_10]
0x18001a1b3  mov     [rsp+130h+var_90], rax; unsigned __int8 *
0x18001a1bb  mov     r9, [r9+30h]
0x18001a1bf  mov     rax, [rbp+hMem]
0x18001a1c3  mov     [rbp+var_38], rcx
0x18001a1c7  mov     rcx, [rbp+var_40]
0x18001a1cb  mov     [rsp+130h+var_98], rcx; unsigned __int16 **
0x18001a1d3  mov     [rsp+130h+var_A0], dl; unsigned __int8
0x18001a1da  mov     rdx, [rbp+arg_8]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18001a1de  mov     [rsp+130h+var_A8], r8; void *
0x18001a1e6  mov     [rsp+130h+var_B0], r10d; unsigned int
0x18001a1ee  mov     [rsp+130h+var_B8], r11; unsigned __int8 *
0x18001a1f3  mov     [rsp+130h+var_C0], ebx; unsigned int
0x18001a1f7  mov     rbx, [rbp+arg_0]
0x18001a1fb  mov     [rsp+130h+var_C8], rdi; unsigned __int16 **
0x18001a200  mov     [rsp+130h+var_D0], sil; char
0x18001a205  mov     [rsp+130h+var_D8], r14; unsigned __int64
0x18001a20a  mov     r14, [rbp+var_48]
0x18001a20e  mov     r8, [rbx+8]; struct _UBPM_ACTION_PARAMS *
0x18001a212  mov     rcx, [rbx]; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18001a215  mov     [rsp+130h+var_E0], r15d; unsigned int
0x18001a21a  mov     [rsp+130h+var_E8], r12; unsigned __int64
0x18001a21f  mov     [rsp+130h+var_F0], r13d; unsigned int
0x18001a224  mov     [rsp+130h+var_F8], r9; struct _GUID *
0x18001a229  mov     r9d, [rbp+arg_18]; unsigned int
0x18001a22d  mov     [rsp+130h+var_100], rax; void *
0x18001a232  mov     rax, [rbp+var_38]
0x18001a236  mov     qword ptr [rsp+130h+cchCount2], rax; void **
0x18001a23b  mov     [rsp+130h+lpString2], r14; pSid
0x18001a240  call    ?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z; UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)
0x18001a245  mov     edi, eax
0x18001a247  test    eax, eax
0x18001a249  jnz     short loc_18001A25C
0x18001a24b  mov     rsi, [rbp+var_78]
0x18001a24f  mov     r12, [rsp+130h+var_10]
0x18001a257  jmp     loc_18001A0E4
0x18001a25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a263  lea     rax, WPP_GLOBAL_Control
0x18001a26a  cmp     rcx, rax
0x18001a26d  jz      short loc_18001A24B
0x18001a26f  test    byte ptr [rcx+1Ch], 10h
0x18001a273  jz      short loc_18001A24B
0x18001a275  mov     rax, [rbx]
0x18001a278  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001a27f  mov     rcx, [rcx+10h]
0x18001a283  mov     edx, 3Bh ; ';'
0x18001a288  mov     [rsp+130h+cchCount2], edi
0x18001a28c  mov     r9, [rax+18h]
0x18001a290  mov     eax, [rbx+24h]
0x18001a293  mov     dword ptr [rsp+130h+lpString2], eax
0x18001a297  mov     r9, [r9+8]
0x18001a29b  call    WPP_SF_Sdd
0x18001a2a0  jmp     short loc_18001A24B
0x18001a2a2  lea     rax, String2; "NT TASK"
0x18001a2a9  mov     [rsp+130h+cchCount2], 7; cchCount2
0x18001a2b1  mov     r9d, 7; cchCount1
0x18001a2b7  mov     [rsp+130h+lpString2], rax; lpString2
0x18001a2bc  mov     r8, rbx; lpString1
0x18001a2bf  mov     edx, 1; dwCmpFlags
0x18001a2c4  mov     ecx, 7Fh; Locale
0x18001a2c9  call    cs:__imp_CompareStringW
0x18001a2cf  cmp     eax, 2
0x18001a2d2  jnz     loc_18001A032
0x18001a2d8  add     rbx, 0Eh
0x18001a2dc  jmp     loc_18001A032
0x18001a2e1  cmp     [r13+24h], esi
0x18001a2e5  jnz     loc_18001A081
0x18001a2eb  call    cs:__imp_RtlIsMultiSessionSku
0x18001a2f1  test    al, al
0x18001a2f3  jz      loc_18001A081
0x18001a2f9  mov     edi, 10E0h
0x18001a2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a305  lea     rax, WPP_GLOBAL_Control
0x18001a30c  cmp     rcx, rax
0x18001a30f  jz      loc_18001A24F
0x18001a315  test    byte ptr [rcx+1Ch], 2
0x18001a319  jz      loc_18001A24F
0x18001a31f  mov     edx, 37h ; '7'
0x18001a324  jmp     loc_18001A52C
0x18001a329  mov     rax, [r13+28h]
0x18001a32d  test    rax, rax
0x18001a330  jnz     loc_18001A55B
0x18001a336  mov     rax, [r13+8]
0x18001a33a  lea     r9, [rbp+pSid]
0x18001a33e  xor     edx, edx; SidToCheck
0x18001a340  mov     [rbp+pSid], rsi
0x18001a344  mov     r8d, 0FFFFFFFFh
0x18001a34a  mov     dword ptr [rbp+var_68], esi
0x18001a34d  mov     rcx, [rax+18h]
0x18001a351  mov     rax, [rcx+20h]
0x18001a355  mov     rcx, [rax+8]
0x18001a359  lea     rax, [rbp+var_68]
0x18001a35d  mov     [rsp+130h+lpString2], rax; __int64
0x18001a362  mov     rcx, [rcx+8]; pSid2
0x18001a366  call    UbpmGetInteractiveUserSidAndToken
0x18001a36b  mov     edi, eax
0x18001a36d  test    eax, eax
0x18001a36f  jnz     short loc_18001A39E
0x18001a371  cmp     dword ptr [rbp+var_68], esi
0x18001a374  jz      loc_18001A551
0x18001a37a  mov     rcx, [rbp+pSid]
0x18001a37e  mov     rax, [rcx+8]
0x18001a382  mov     [rbp+hObject], rax
0x18001a386  mov     eax, [rcx+10h]
0x18001a389  mov     r14, [rcx]
0x18001a38c  mov     [rcx+8], rsi
0x18001a390  mov     [rbp+arg_18], eax
0x18001a393  mov     rax, [rbp+pSid]
0x18001a397  mov     [rbp+var_48], r14
0x18001a39b  mov     [rax], rsi
0x18001a39e  mov     rcx, [rbp+pSid]
0x18001a3a2  test    rcx, rcx
0x18001a3a5  jz      short loc_18001A3DA
0x18001a3a7  cmp     dword ptr [rbp+var_68], esi
0x18001a3aa  jbe     short loc_18001A3D5
0x18001a3ac  mov     r15d, esi
0x18001a3af  shl     r15, 5
0x18001a3b3  mov     rax, [rcx+r15+8]
0x18001a3b8  test    rax, rax
0x18001a3bb  jnz     loc_18001A755
0x18001a3c1  mov     rcx, [rcx+r15]
0x18001a3c5  call    UBPM_MIDL_user_free
0x18001a3ca  mov     rcx, [rbp+pSid]
0x18001a3ce  inc     esi
0x18001a3d0  cmp     esi, dword ptr [rbp+var_68]
0x18001a3d3  jb      short loc_18001A3AC
0x18001a3d5  call    UBPM_MIDL_user_free
0x18001a3da  test    edi, edi
0x18001a3dc  jz      loc_18001A167
0x18001a3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3e9  lea     rax, WPP_GLOBAL_Control
0x18001a3f0  cmp     rcx, rax
0x18001a3f3  jnz     loc_18001A672
0x18001a3f9  mov     rax, [r13+8]
0x18001a3fd  xor     r9d, r9d
0x18001a400  xor     r8d, r8d
0x18001a403  mov     edx, 1
0x18001a408  mov     rcx, [rax+18h]
0x18001a40c  mov     rax, [rcx+20h]
0x18001a410  mov     rcx, [rax+8]
0x18001a414  lea     rax, [rbp+var_78]
0x18001a418  mov     [rsp+130h+lpString2], rax
0x18001a41d  mov     rcx, [rcx+8]
0x18001a421  call    UbpmUtilsGetAccountNamesFromSid
0x18001a426  cmp     edi, 490h
0x18001a42c  jnz     loc_18001A62F
0x18001a432  mov     rsi, [rbp+var_78]
0x18001a436  lea     r9, aNone; "(NONE)"
0x18001a43d  test    rsi, rsi
0x18001a440  mov     r8, rbx; unsigned __int16 *
0x18001a443  cmovnz  r9, rsi; unsigned __int16 *
0x18001a447  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x18001a44c  mov     r12, [rsp+130h+var_10]
0x18001a454  jmp     loc_18001A0E4
0x18001a459  mov     [rbp+arg_18], esi
0x18001a45c  mov     dword ptr [rbp+var_80], esi
0x18001a45f  mov     [rbp+pSid], rsi
0x18001a463  cmp     r8d, 4
0x18001a467  jnz     loc_18001A614
0x18001a46d  test    byte ptr [rdx+4Ch], 4
0x18001a471  jnz     loc_18001A767
0x18001a477  lea     rax, [rbp+hMem]
0x18001a47b  mov     r9, rbx
0x18001a47e  mov     qword ptr [rsp+130h+cchCount2], rax
0x18001a483  xor     r8d, r8d
0x18001a486  lea     rax, [rbp+hObject]
0x18001a48a  xor     edx, edx
0x18001a48c  mov     rcx, r12
0x18001a48f  mov     [rsp+130h+lpString2], rax
0x18001a494  call    UbpmpTokenGetNonInteractiveToken
0x18001a499  mov     edi, eax
0x18001a49b  lea     r15, WPP_GLOBAL_Control
0x18001a4a2  test    edi, edi
0x18001a4a4  jz      loc_18001A167
  ... truncated ...
```
