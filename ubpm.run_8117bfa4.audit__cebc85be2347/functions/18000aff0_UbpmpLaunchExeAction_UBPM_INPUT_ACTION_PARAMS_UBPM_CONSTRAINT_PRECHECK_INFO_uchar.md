# UbpmpLaunchExeAction(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)

- ea: `0x18000aff0`
- end: `0x18000b931`
- name: `?UbpmpLaunchExeAction@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z`
- size: `2369`
- prototype: `unsigned int __fastcall(struct _UBPM_INPUT_ACTION_PARAMS *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ae00`
- `0x18000d0d0`

## callees

- `0x180007000`
- `0x18000aff0`
- `0x18000b938`
- `0x18000bd60`
- `0x18000c270`
- `0x18000e5b0`
- `0x18000fbf0`
- `0x18001af64`
- `0x18001ba64`
- `0x18001bcdc`
- `0x180023b50`
- `0x180024740`
- `0x180037508`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b810`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b810`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b858`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b858`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000b5cb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000b5cb`
- `ntdll!RtlIsMultiSessionSku` at `0x18000b34a`
- `ntdll!RtlIsMultiSessionSku` at `0x18000b34a`
- `ntdll!RtlFreeHeap` at `0x18000b178`
- `ntdll!RtlFreeHeap` at `0x18000b1a3`
- `ntdll!RtlFreeHeap` at `0x18000b178`
- `ntdll!RtlFreeHeap` at `0x18000b1a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b868`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b128`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b128`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b822`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b822`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b322`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b322`

## string_xrefs

- `0x18000b2fb`: `NT TASK`

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
  unsigned __int8 v27; // si
  unsigned int v28; // r15d
  unsigned __int64 v29; // r12
  unsigned int v30; // r13d
  void **p_hObject; // rcx
  struct _GUID *v32; // r9
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  unsigned int v37; // eax
  _QWORD *v38; // rcx
  __int64 v39; // r15
  const struct _EVENT_DESCRIPTOR *v40; // rdx
  void *v41; // rcx
  unsigned __int16 *v42; // r9
  unsigned int v43; // eax
  unsigned __int16 *v44; // r9
  int v45; // r8d
  void *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  PSID *v50; // rcx
  __int64 v51; // r15
  unsigned int v52; // eax
  unsigned __int16 *v53; // r9
  int InteractiveToken; // eax
  PSID v55; // rsi
  DWORD LengthSid; // edi
  HLOCAL v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  DWORD LastError; // eax
  unsigned __int64 v62; // [rsp+58h] [rbp-D8h]
  __int64 v63; // [rsp+B0h] [rbp-80h] BYREF
  unsigned __int16 *v64; // [rsp+B8h] [rbp-78h] BYREF
  PSID pSid; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-68h] BYREF
  PSID *v67; // [rsp+D0h] [rbp-60h] BYREF
  HANDLE hObject; // [rsp+D8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp-50h] BYREF
  PSID v70; // [rsp+E8h] [rbp-48h]
  unsigned __int16 **v71; // [rsp+F0h] [rbp-40h]
  void **v72; // [rsp+F8h] [rbp-38h]
  unsigned int v76; // [rsp+168h] [rbp+38h]

  v76 = -1;
  hObject = 0;
  v6 = 0;
  hMem = 0;
  v7 = 0;
  v70 = 0;
  v64 = 0;
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
    v76 = 0;
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
      v45 = *((_DWORD *)a1 + 9);
      v46 = (void *)*((_QWORD *)a1 + 5);
      v67 = 0;
      LODWORD(v63) = 0;
      InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(v46, 0, v45, &v67, (unsigned int *)&v63);
      if ( !InteractiveUserSidAndToken )
      {
        if ( (_DWORD)v63 )
        {
          hObject = v67[1];
          v6 = *v67;
          v67[1] = 0;
          v70 = v6;
          *v67 = 0;
        }
        else
        {
          InteractiveUserSidAndToken = 1168;
        }
      }
      v50 = v67;
      if ( v67 )
      {
        if ( (_DWORD)v63 )
        {
          do
          {
            v51 = 4LL * (unsigned int)v7;
            if ( v50[v51 + 1] )
            {
              CloseHandle(v50[v51 + 1]);
              v50 = v67;
            }
            UBPM_MIDL_user_free(v50[v51], v47, v48, v49);
            v50 = v67;
            LODWORD(v7) = (_DWORD)v7 + 1;
          }
          while ( (unsigned int)v7 < (unsigned int)v63 );
        }
        UBPM_MIDL_user_free(v50, v47, v48, v49);
      }
      if ( !InteractiveUserSidAndToken )
      {
        v76 = *((_DWORD *)a1 + 9);
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
      UbpmUtilsGetAccountNamesFromSid(*((_QWORD *)a1 + 5), 1, 0, 0, (__int64)&v64);
      if ( InteractiveUserSidAndToken != 1008 )
      {
LABEL_82:
        if ( InteractiveUserSidAndToken > 0 )
          v52 = (unsigned __int16)InteractiveUserSidAndToken | 0x80070000;
        else
          v52 = InteractiveUserSidAndToken;
        v7 = v64;
        v53 = L"(NONE)";
        if ( v64 )
          v53 = v64;
        ReportTaskEvent(g_hTaskEventManager, &JOB_START_FAILED, v8, v53, v52);
        goto LABEL_15;
      }
    }
    else
    {
      v33 = *((_QWORD *)a1 + 1);
      pSid = 0;
      LODWORD(v66) = 0;
      InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(
                                     *(PSID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v33 + 24) + 32LL) + 8LL) + 8LL),
                                     0,
                                     -1,
                                     &pSid,
                                     (unsigned int *)&v66);
      if ( !InteractiveUserSidAndToken )
      {
        if ( (_DWORD)v66 )
        {
          hObject = (HANDLE)*((_QWORD *)pSid + 1);
          v37 = *((_DWORD *)pSid + 4);
          v6 = *(PSID *)pSid;
          *((_QWORD *)pSid + 1) = 0;
          v76 = v37;
          v70 = v6;
          *(_QWORD *)pSid = 0;
        }
        else
        {
          InteractiveUserSidAndToken = 1168;
        }
      }
      v38 = pSid;
      if ( pSid )
      {
        if ( (_DWORD)v66 )
        {
          do
          {
            v39 = 4LL * (unsigned int)v7;
            if ( v38[v39 + 1] )
            {
              CloseHandle((HANDLE)v38[v39 + 1]);
              v38 = pSid;
            }
            UBPM_MIDL_user_free(v38[4 * (unsigned int)v7], v34, v35, v36);
            v38 = pSid;
            LODWORD(v7) = (_DWORD)v7 + 1;
          }
          while ( (unsigned int)v7 < (unsigned int)v66 );
        }
        UBPM_MIDL_user_free(v38, v34, v35, v36);
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
        (__int64)&v64);
      if ( InteractiveUserSidAndToken != 1168 )
        goto LABEL_82;
    }
    v7 = v64;
    v42 = L"(NONE)";
    if ( v64 )
      v42 = v64;
    ReportTaskEvent(v41, v40, v8, v42);
    goto LABEL_15;
  }
  v76 = 0;
  LODWORD(v63) = 0;
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
                       (unsigned int)&v63,
                       (__int64)&pSid);
  if ( InteractiveToken )
  {
    InteractiveUserSidAndToken = 0;
    if ( InteractiveToken != 1168 )
      InteractiveUserSidAndToken = InteractiveToken;
    if ( !InteractiveUserSidAndToken )
    {
      v76 = v63;
LABEL_56:
      InteractiveUserSidAndToken = UbpmpTokenGetNonInteractiveToken(v11, 0, 0, v8, &hObject, &hMem);
      goto LABEL_57;
    }
  }
  else
  {
    v55 = pSid;
    LengthSid = GetLengthSid(pSid);
    v57 = LocalAlloc(0, LengthSid);
    hMem = v57;
    if ( v57 )
    {
      if ( CopySid(LengthSid, v57, v55) )
      {
        v76 = v63;
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
      v76 = v63;
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
      v71 = v19;
      p_hObject = &hObject;
      if ( !hObject )
        p_hObject = 0;
      v32 = (struct _GUID *)*((_QWORD *)a1 + 6);
      v72 = p_hObject;
      v62 = v23;
      v6 = v70;
      InteractiveUserSidAndToken = UbpmpLaunchOneTask(
                                     *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)a1,
                                     a2,
                                     *((struct _UBPM_ACTION_PARAMS **)a1 + 1),
                                     v76,
                                     v70,
                                     p_hObject,
                                     hMem,
                                     v32,
                                     v30,
                                     v29,
                                     v28,
                                     v62,
                                     v27,
                                     v26,
                                     v22,
                                     v25,
                                     v24,
                                     v21,
                                     v20,
                                     (const unsigned __int16 **)v71,
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
      v7 = v64;
      goto LABEL_15;
    }
    InteractiveUserSidAndToken = 14;
    UBPM_MIDL_user_free(v55, v58, v59, v60);
  }
LABEL_58:
  UbpmUtilsGetAccountNamesFromSid(
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL) + 32LL) + 8LL) + 8LL),
    1,
    0,
    0,
    (__int64)&v64);
  if ( InteractiveUserSidAndToken > 0 )
    v43 = (unsigned __int16)InteractiveUserSidAndToken | 0x80070000;
  else
    v43 = InteractiveUserSidAndToken;
  v7 = v64;
  v44 = L"(NONE)";
  if ( v64 )
    v44 = v64;
  ReportTaskEvent(g_hTaskEventManager, &JOB_START_FAILED, v8, v44, v43);
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
0x18000aff0  mov     rax, rsp
0x18000aff3  mov     [rax+18h], r8
0x18000aff7  mov     [rax+10h], rdx
0x18000affb  mov     [rax+8], rcx
0x18000afff  push    rbp
0x18000b000  push    rsi
0x18000b001  push    rdi
0x18000b002  mov     rbp, rsp
0x18000b005  sub     rsp, 130h
0x18000b00c  mov     [rax-20h], rbx
0x18000b010  mov     rdi, r8
0x18000b013  mov     [rax-30h], r13
0x18000b017  mov     r13, rcx
0x18000b01a  mov     [rax-38h], r14
0x18000b01e  mov     [rax-40h], r15
0x18000b022  mov     r15, rdx
0x18000b025  xor     eax, eax
0x18000b027  mov     [rbp+arg_18], 0FFFFFFFFh
0x18000b02e  mov     [rbp+hObject], rax
0x18000b032  mov     r14d, eax
0x18000b035  mov     [rbp+hMem], rax
0x18000b039  mov     esi, eax
0x18000b03b  mov     [rbp+var_48], rax
0x18000b03f  mov     [rbp+var_78], rax
0x18000b043  mov     rax, [rcx]
0x18000b046  mov     r9, [rax+18h]
0x18000b04a  mov     rbx, [r9+8]
0x18000b04e  test    rbx, rbx
0x18000b051  jz      short loc_18000B072
0x18000b053  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b05a  nop     word ptr [rax+rax+00h]
0x18000b060  inc     rax
0x18000b063  cmp     [rbx+rax*2], si
0x18000b067  jnz     short loc_18000B060
0x18000b069  cmp     eax, 8
0x18000b06c  ja      loc_18000B2FB
0x18000b072  mov     ecx, [r13+38h]
0x18000b076  test    cl, 6
0x18000b079  jnz     loc_18000B10C
0x18000b07f  mov     rax, [r13+8]
0x18000b083  mov     [rsp+130h+var_10], r12
0x18000b08b  mov     r12, [rax+18h]
0x18000b08f  mov     rdx, [r12+20h]
0x18000b094  test    rdx, rdx
0x18000b097  jz      loc_18000B1BD
0x18000b09d  mov     r8d, [rdx+20h]
0x18000b0a1  lea     eax, [r8-4]
0x18000b0a5  cmp     eax, 1
0x18000b0a8  jbe     loc_18000B4BE
0x18000b0ae  cmp     dword ptr [rdx], 2
0x18000b0b1  jnz     loc_18000B38E
0x18000b0b7  bt      ecx, 11h
0x18000b0bb  jb      loc_18000B340
0x18000b0c1  mov     r8, rdi; unsigned __int8 *
0x18000b0c4  mov     rdx, r15; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000b0c7  mov     rcx, r13; struct _UBPM_INPUT_ACTION_PARAMS *
0x18000b0ca  call    ?UbpmpHandleGroupSid@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z; UbpmpHandleGroupSid(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)
0x18000b0cf  mov     edi, eax
0x18000b0d1  test    eax, eax
0x18000b0d3  jz      loc_18000B2A8
0x18000b0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0e0  lea     rax, WPP_GLOBAL_Control
0x18000b0e7  cmp     rcx, rax
0x18000b0ea  jz      loc_18000B2A8
0x18000b0f0  test    byte ptr [rcx+1Ch], 1
0x18000b0f4  jz      loc_18000B2A8
0x18000b0fa  mov     rdx, [r13+0]
0x18000b0fe  mov     r9, [rdx+18h]
0x18000b102  mov     edx, 38h ; '8'
0x18000b107  jmp     loc_18000B599
0x18000b10c  mov     r8, rdi; unsigned __int8 *
0x18000b10f  mov     rdx, r15; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000b112  mov     rcx, r13; struct _UBPM_INPUT_ACTION_PARAMS *
0x18000b115  call    ?UbpmpRunConsumerAction@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z; UbpmpRunConsumerAction(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)
0x18000b11a  mov     edi, eax
0x18000b11c  test    eax, eax
0x18000b11e  jnz     loc_18000B8E6
0x18000b124  mov     rcx, [rbp+hMem]; hMem
0x18000b128  call    cs:__imp_LocalFree
0x18000b12f  nop     dword ptr [rax+rax+00h]
0x18000b134  mov     rcx, [rbp+hObject]; hObject
0x18000b138  mov     r15, [rsp+130h+var_28]
0x18000b140  mov     r13, [rsp+130h+var_18]
0x18000b148  mov     rbx, [rsp+130h+var_8]
0x18000b150  test    rcx, rcx
0x18000b153  jz      short loc_18000B161
0x18000b155  call    cs:__imp_CloseHandle
0x18000b15c  nop     dword ptr [rax+rax+00h]
0x18000b161  test    r14, r14
0x18000b164  jz      short loc_18000B184
0x18000b166  mov     rcx, gs:60h
0x18000b16f  mov     r8, r14; P
0x18000b172  xor     edx, edx; Flags
0x18000b174  mov     rcx, [rcx+30h]; HeapHandle
0x18000b178  call    cs:__imp_RtlFreeHeap
0x18000b17f  nop     dword ptr [rax+rax+00h]
0x18000b184  mov     r14, [rsp+130h+var_20]
0x18000b18c  test    rsi, rsi
0x18000b18f  jz      short loc_18000B1AF
0x18000b191  mov     rcx, gs:60h
0x18000b19a  mov     r8, rsi; P
0x18000b19d  xor     edx, edx; Flags
0x18000b19f  mov     rcx, [rcx+30h]; HeapHandle
0x18000b1a3  call    cs:__imp_RtlFreeHeap
0x18000b1aa  nop     dword ptr [rax+rax+00h]
0x18000b1af  mov     eax, edi
0x18000b1b1  add     rsp, 130h
0x18000b1b8  pop     rdi
0x18000b1b9  pop     rsi
0x18000b1ba  pop     rbp
0x18000b1bb  retn
0x18000b1bd  mov     [rbp+arg_18], esi
0x18000b1c0  mov     rcx, [r13+70h]
0x18000b1c4  xor     eax, eax
0x18000b1c6  cmp     [rbp+hObject], rax
0x18000b1ca  movzx   edx, byte ptr [r13+6Ch]
0x18000b1cf  mov     r8, [r13+28h]
0x18000b1d3  mov     ebx, [r13+20h]
0x18000b1d7  mov     r14, [r13+50h]
0x18000b1db  mov     r10d, [r13+68h]
0x18000b1df  mov     r11, [r13+18h]
0x18000b1e3  mov     rdi, [r13+60h]
0x18000b1e7  movzx   esi, byte ptr [r13+58h]
0x18000b1ec  mov     r15d, [r13+48h]
0x18000b1f0  mov     r12, [r13+40h]
0x18000b1f4  mov     r13d, [r13+38h]
0x18000b1f8  mov     r9, [rbp+arg_0]
0x18000b1fc  mov     [rbp+var_40], rcx
0x18000b200  lea     rcx, [rbp+hObject]
0x18000b204  cmovz   rcx, rax
0x18000b208  mov     rax, [rbp+arg_10]
0x18000b20c  mov     [rsp+130h+var_90], rax; unsigned __int8 *
0x18000b214  mov     r9, [r9+30h]
0x18000b218  mov     rax, [rbp+hMem]
0x18000b21c  mov     [rbp+var_38], rcx
0x18000b220  mov     rcx, [rbp+var_40]
0x18000b224  mov     [rsp+130h+var_98], rcx; unsigned __int16 **
0x18000b22c  mov     [rsp+130h+var_A0], dl; unsigned __int8
0x18000b233  mov     rdx, [rbp+arg_8]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000b237  mov     [rsp+130h+var_A8], r8; void *
0x18000b23f  mov     [rsp+130h+var_B0], r10d; unsigned int
0x18000b247  mov     [rsp+130h+var_B8], r11; unsigned __int8 *
0x18000b24c  mov     [rsp+130h+var_C0], ebx; unsigned int
0x18000b250  mov     rbx, [rbp+arg_0]
0x18000b254  mov     [rsp+130h+var_C8], rdi; unsigned __int16 **
0x18000b259  mov     [rsp+130h+var_D0], sil; char
0x18000b25e  mov     [rsp+130h+var_D8], r14; unsigned __int64
0x18000b263  mov     r14, [rbp+var_48]
0x18000b267  mov     r8, [rbx+8]; struct _UBPM_ACTION_PARAMS *
0x18000b26b  mov     rcx, [rbx]; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000b26e  mov     [rsp+130h+var_E0], r15d; unsigned int
0x18000b273  mov     [rsp+130h+var_E8], r12; unsigned __int64
0x18000b278  mov     [rsp+130h+var_F0], r13d; unsigned int
0x18000b27d  mov     [rsp+130h+var_F8], r9; struct _GUID *
0x18000b282  mov     r9d, [rbp+arg_18]; unsigned int
0x18000b286  mov     [rsp+130h+var_100], rax; void *
0x18000b28b  mov     rax, [rbp+var_38]
0x18000b28f  mov     qword ptr [rsp+130h+cchCount2], rax; void **
0x18000b294  mov     [rsp+130h+lpString2], r14; pSid
0x18000b299  call    ?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z; UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)
0x18000b29e  mov     edi, eax
0x18000b2a0  test    eax, eax
0x18000b2a2  jnz     short loc_18000B2B5
0x18000b2a4  mov     rsi, [rbp+var_78]
0x18000b2a8  mov     r12, [rsp+130h+var_10]
0x18000b2b0  jmp     loc_18000B124
0x18000b2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2bc  lea     rax, WPP_GLOBAL_Control
0x18000b2c3  cmp     rcx, rax
0x18000b2c6  jz      short loc_18000B2A4
0x18000b2c8  test    byte ptr [rcx+1Ch], 10h
0x18000b2cc  jz      short loc_18000B2A4
0x18000b2ce  mov     rax, [rbx]
0x18000b2d1  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000b2d8  mov     rcx, [rcx+10h]
0x18000b2dc  mov     edx, 3Bh ; ';'
0x18000b2e1  mov     [rsp+130h+cchCount2], edi
0x18000b2e5  mov     r9, [rax+18h]
0x18000b2e9  mov     eax, [rbx+24h]
0x18000b2ec  mov     dword ptr [rsp+130h+lpString2], eax
0x18000b2f0  mov     r9, [r9+8]
0x18000b2f4  call    WPP_SF_Sdd
0x18000b2f9  jmp     short loc_18000B2A4
0x18000b2fb  lea     rax, String2; "NT TASK"
0x18000b302  mov     [rsp+130h+cchCount2], 7; cchCount2
0x18000b30a  mov     r9d, 7; cchCount1
0x18000b310  mov     [rsp+130h+lpString2], rax; lpString2
0x18000b315  mov     r8, rbx; lpString1
0x18000b318  mov     edx, 1; dwCmpFlags
0x18000b31d  mov     ecx, 7Fh; Locale
0x18000b322  call    cs:__imp_CompareStringW
0x18000b329  nop     dword ptr [rax+rax+00h]
0x18000b32e  cmp     eax, 2
0x18000b331  jnz     loc_18000B072
0x18000b337  add     rbx, 0Eh
0x18000b33b  jmp     loc_18000B072
0x18000b340  cmp     [r13+24h], esi
0x18000b344  jnz     loc_18000B0C1
0x18000b34a  call    cs:__imp_RtlIsMultiSessionSku
0x18000b351  nop     dword ptr [rax+rax+00h]
0x18000b356  test    al, al
0x18000b358  jz      loc_18000B0C1
0x18000b35e  mov     edi, 10E0h
0x18000b363  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b36a  lea     rax, WPP_GLOBAL_Control
0x18000b371  cmp     rcx, rax
0x18000b374  jz      loc_18000B2A8
0x18000b37a  test    byte ptr [rcx+1Ch], 2
0x18000b37e  jz      loc_18000B2A8
0x18000b384  mov     edx, 37h ; '7'
0x18000b389  jmp     loc_18000B591
0x18000b38e  mov     rax, [r13+28h]
0x18000b392  test    rax, rax
0x18000b395  jnz     loc_18000B5C0
0x18000b39b  mov     rax, [r13+8]
0x18000b39f  lea     r9, [rbp+pSid]
0x18000b3a3  xor     edx, edx; SidToCheck
0x18000b3a5  mov     [rbp+pSid], rsi
0x18000b3a9  mov     r8d, 0FFFFFFFFh
0x18000b3af  mov     dword ptr [rbp+var_68], esi
0x18000b3b2  mov     rcx, [rax+18h]
0x18000b3b6  mov     rax, [rcx+20h]
0x18000b3ba  mov     rcx, [rax+8]
0x18000b3be  lea     rax, [rbp+var_68]
0x18000b3c2  mov     [rsp+130h+lpString2], rax; __int64
0x18000b3c7  mov     rcx, [rcx+8]; pSid2
0x18000b3cb  call    UbpmGetInteractiveUserSidAndToken
0x18000b3d0  mov     edi, eax
0x18000b3d2  test    eax, eax
0x18000b3d4  jnz     short loc_18000B403
0x18000b3d6  cmp     dword ptr [rbp+var_68], esi
0x18000b3d9  jz      loc_18000B5B6
0x18000b3df  mov     rcx, [rbp+pSid]
0x18000b3e3  mov     rax, [rcx+8]
0x18000b3e7  mov     [rbp+hObject], rax
0x18000b3eb  mov     eax, [rcx+10h]
0x18000b3ee  mov     r14, [rcx]
0x18000b3f1  mov     [rcx+8], rsi
0x18000b3f5  mov     [rbp+arg_18], eax
0x18000b3f8  mov     rax, [rbp+pSid]
0x18000b3fc  mov     [rbp+var_48], r14
0x18000b400  mov     [rax], rsi
0x18000b403  mov     rcx, [rbp+pSid]
0x18000b407  test    rcx, rcx
0x18000b40a  jz      short loc_18000B43F
0x18000b40c  cmp     dword ptr [rbp+var_68], esi
0x18000b40f  jbe     short loc_18000B43A
0x18000b411  mov     r15d, esi
0x18000b414  shl     r15, 5
0x18000b418  mov     rax, [rcx+r15+8]
0x18000b41d  test    rax, rax
0x18000b420  jnz     loc_18000B7C6
0x18000b426  mov     rcx, [rcx+r15]
0x18000b42a  call    UBPM_MIDL_user_free
0x18000b42f  mov     rcx, [rbp+pSid]
0x18000b433  inc     esi
0x18000b435  cmp     esi, dword ptr [rbp+var_68]
0x18000b438  jb      short loc_18000B411
0x18000b43a  call    UBPM_MIDL_user_free
0x18000b43f  test    edi, edi
0x18000b441  jz      loc_18000B1C0
0x18000b447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b44e  lea     rax, WPP_GLOBAL_Control
0x18000b455  cmp     rcx, rax
0x18000b458  jnz     loc_18000B6DD
0x18000b45e  mov     rax, [r13+8]
0x18000b462  xor     r9d, r9d
0x18000b465  xor     r8d, r8d
0x18000b468  mov     edx, 1
0x18000b46d  mov     rcx, [rax+18h]
0x18000b471  mov     rax, [rcx+20h]
0x18000b475  mov     rcx, [rax+8]
0x18000b479  lea     rax, [rbp+var_78]
0x18000b47d  mov     [rsp+130h+lpString2], rax
0x18000b482  mov     rcx, [rcx+8]
0x18000b486  call    UbpmUtilsGetAccountNamesFromSid
0x18000b48b  cmp     edi, 490h
0x18000b491  jnz     loc_18000B69A
0x18000b497  mov     rsi, [rbp+var_78]
0x18000b49b  lea     r9, aNone; "(NONE)"
0x18000b4a2  test    rsi, rsi
0x18000b4a5  mov     r8, rbx; unsigned __int16 *
0x18000b4a8  cmovnz  r9, rsi; unsigned __int16 *
0x18000b4ac  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x18000b4b1  mov     r12, [rsp+130h+var_10]
0x18000b4b9  jmp     loc_18000B124
0x18000b4be  mov     [rbp+arg_18], esi
0x18000b4c1  mov     dword ptr [rbp+var_80], esi
0x18000b4c4  mov     [rbp+pSid], rsi
0x18000b4c8  cmp     r8d, 4
0x18000b4cc  jnz     loc_18000B67F
0x18000b4d2  test    byte ptr [rdx+4Ch], 4
0x18000b4d6  jnz     loc_18000B7DE
0x18000b4dc  lea     rax, [rbp+hMem]
0x18000b4e0  mov     r9, rbx
0x18000b4e3  mov     qword ptr [rsp+130h+cchCount2], rax
0x18000b4e8  xor     r8d, r8d
0x18000b4eb  lea     rax, [rbp+hObject]
0x18000b4ef  xor     edx, edx
0x18000b4f1  mov     rcx, r12
  ... truncated ...
```
