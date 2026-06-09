# SpAcceptLsaModeContext

- ea: `0x18001e4b0`
- end: `0x180020494`
- name: `SpAcceptLsaModeContext`
- size: `8164`
- prototype: ``
- caller_count: `0`
- callee_count: `47`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800061a0`
- `0x180006de0`
- `0x180007aa0`
- `0x180008498`
- `0x180008664`
- `0x180008c40`
- `0x180009770`
- `0x18000b2e0`
- `0x18000c770`
- `0x18000c850`
- `0x18000cb00`
- `0x18000cf00`
- `0x18000d9d0`
- `0x18000e580`
- `0x18000e6c0`
- `0x18000ee80`
- `0x18000eff0`
- `0x18000f3dc`
- `0x18000fa94`
- `0x1800104e0`
- `0x1800109f8`
- `0x180011b28`
- `0x180011e48`
- `0x180011fec`
- `0x180012880`
- `0x180013304`
- `0x1800185b8`
- `0x1800187bc`
- `0x180018b18`
- `0x1800192a8`
- `0x18001a394`
- `0x18001a4b4`
- `0x18001a6c0`
- `0x18001aa20`
- `0x18001ab50`
- `0x18001ad3c`
- `0x18001b2f8`
- `0x18001c8e0`
- `0x18001e4b0`
- `0x180022240`
- `0x180022500`
- `0x180024328`
- `0x18002bba8`
- `0x180033768`
- `0x1800342b8`
- `0x1800377bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020033`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001efa9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001efa9`
- `ntdll!RtlInitString` at `0x18001ed4b`
- `ntdll!RtlInitString` at `0x18001ed6f`
- `ntdll!RtlInitString` at `0x18001ed4b`
- `ntdll!RtlInitString` at `0x18001ed6f`
- `ntdll!RtlCharToInteger` at `0x18001f3c6`
- `ntdll!RtlCharToInteger` at `0x18001f3c6`
- `ntdll!NtClose` at `0x180020241`
- `ntdll!NtClose` at `0x180020241`
- `ntdll!RtlReleaseResource` at `0x18001f34b`
- `ntdll!RtlReleaseResource` at `0x18001f35d`
- `ntdll!RtlReleaseResource` at `0x18001f34b`
- `ntdll!RtlReleaseResource` at `0x18001f35d`
- `ntdll!RtlAcquireResourceShared` at `0x18001f261`
- `ntdll!RtlAcquireResourceShared` at `0x18001f261`
- `ntdll!RtlLeaveCriticalSection` at `0x1800203b5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800203b5`
- `ntdll!RtlEnterCriticalSection` at `0x18001efd5`
- `ntdll!RtlEnterCriticalSection` at `0x18001efd5`

## pseudocode

```c
__int64 __fastcall SpAcceptLsaModeContext(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 *a6,
        __int64 a7,
        int *a8,
        _QWORD *a9,
        _BYTE *a10,
        __int64 a11)
{
  __int64 v13; // r15
  int v14; // eax
  int ChannelBindings; // ebx
  PVOID *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  _DWORD *v19; // r13
  DWORD v20; // r14d
  __int64 v21; // r12
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // esi
  __int64 v26; // r13
  unsigned int *v27; // r12
  __int64 v28; // rcx
  _BYTE *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r9
  unsigned int v32; // ebx
  unsigned __int16 *v33; // rbx
  __int64 v34; // r9
  unsigned __int16 *v35; // rdi
  __int64 v36; // rcx
  __int16 v37; // ax
  int v38; // r11d
  __int64 v39; // rcx
  __int16 v40; // ax
  int v41; // esi
  PVOID *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r14
  __int64 v45; // rdx
  unsigned int v46; // r10d
  __int64 v47; // rdi
  __int64 v48; // rdx
  __int64 v49; // r9
  int v50; // eax
  __int64 v51; // rdx
  int v52; // ebx
  int v53; // eax
  __int64 v54; // r8
  unsigned int v55; // edi
  int i; // ebx
  NTSTATUS v57; // eax
  int LogSess; // eax
  int v59; // eax
  int v60; // eax
  unsigned int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  _QWORD *v64; // rcx
  _DWORD *Memory; // rax
  __int64 v66; // rdx
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r9
  PVOID *v72; // rcx
  int v73; // eax
  int v74; // eax
  __int64 v75; // r9
  unsigned __int16 *v76; // rbx
  __int16 v77; // ax
  __int64 v78; // r10
  unsigned __int16 v79; // r11
  unsigned int v80; // eax
  PVOID *v81; // rcx
  int v82; // eax
  unsigned int v83; // eax
  int v84; // eax
  __int64 v85; // rdx
  DWORD LastError; // eax
  PVOID *v87; // rcx
  __int16 *v88; // rsi
  __int16 *v89; // rdi
  void *v90; // rcx
  __int64 *v91; // rsi
  _BYTE *v92; // rax
  HLOCAL v93; // rdi
  int v94; // eax
  int v95; // edi
  int v96; // eax
  int v97; // edi
  unsigned int v99; // [rsp+60h] [rbp-A0h]
  unsigned int HttpOrSaslBufferCount; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v101[4]; // [rsp+7Ch] [rbp-84h]
  unsigned int v102; // [rsp+80h] [rbp-80h]
  size_t Size[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v104; // [rsp+98h] [rbp-68h]
  unsigned int v105; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v106; // [rsp+A0h] [rbp-60h] BYREF
  int v107; // [rsp+A8h] [rbp-58h] BYREF
  int v108; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v109; // [rsp+B0h] [rbp-50h] BYREF
  BOOL v110; // [rsp+B4h] [rbp-4Ch]
  ULONG Value[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v112; // [rsp+C0h] [rbp-40h]
  unsigned int *v113; // [rsp+C8h] [rbp-38h] BYREF
  WINBOOL v114; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v115; // [rsp+D8h] [rbp-28h] BYREF
  int v116; // [rsp+E0h] [rbp-20h]
  int v117; // [rsp+E4h] [rbp-1Ch]
  _BYTE *v118; // [rsp+E8h] [rbp-18h]
  HLOCAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  DWORD ReturnLength; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v121; // [rsp+100h] [rbp+0h] BYREF
  __int64 v122; // [rsp+108h] [rbp+8h] BYREF
  __int64 v123; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v124; // [rsp+118h] [rbp+18h] BYREF
  int *v125; // [rsp+120h] [rbp+20h]
  __int64 v126; // [rsp+128h] [rbp+28h]
  __int128 v127; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v128[2]; // [rsp+140h] [rbp+40h] BYREF
  int v129; // [rsp+144h] [rbp+44h]
  __int64 v130; // [rsp+148h] [rbp+48h]
  _QWORD *v131; // [rsp+150h] [rbp+50h]
  DWORD dwProcessId[4]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v133; // [rsp+168h] [rbp+68h]
  struct _STRING DestinationString; // [rsp+170h] [rbp+70h] BYREF
  struct _STRING v135; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v136[4]; // [rsp+190h] [rbp+90h] BYREF
  __int16 v137; // [rsp+194h] [rbp+94h]
  STRING String1; // [rsp+1C8h] [rbp+C8h] BYREF
  char v139[32]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int16 v140; // [rsp+1F8h] [rbp+F8h]
  __int16 v141; // [rsp+208h] [rbp+108h]
  _WORD v142[4]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v143; // [rsp+220h] [rbp+120h]
  _WORD v144[4]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v145; // [rsp+250h] [rbp+150h]
  unsigned __int16 v146; // [rsp+298h] [rbp+198h]
  void *Src; // [rsp+2A0h] [rbp+1A0h]
  char v148; // [rsp+358h] [rbp+258h] BYREF
  char v149; // [rsp+368h] [rbp+268h] BYREF
  __int16 v150; // [rsp+380h] [rbp+280h] BYREF
  __int16 v151; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v152[16]; // [rsp+5A0h] [rbp+4A0h] BYREF
  char v153; // [rsp+5B0h] [rbp+4B0h] BYREF
  char v154; // [rsp+5D0h] [rbp+4D0h] BYREF
  char v155; // [rsp+5E0h] [rbp+4E0h] BYREF
  char v156; // [rsp+5F0h] [rbp+4F0h] BYREF
  char String[8]; // [rsp+600h] [rbp+500h] BYREF
  __int16 v158; // [rsp+608h] [rbp+508h]
  __int64 TokenInformation[32]; // [rsp+610h] [rbp+510h] BYREF

  v112 = a6;
  v104 = a4;
  v118 = a10;
  *(_QWORD *)String = a2;
  v125 = a8;
  v131 = a9;
  v105 = 0;
  v109 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, a2);
  memset_0(v136, 0, 0x410u);
  v133 = 0;
  *(_DWORD *)v101 = 1;
  v99 = 1;
  v115 = v152;
  v102 = 1;
  *(_QWORD *)Value = &v153;
  v117 = 0;
  v121 = (unsigned __int16 *)&v154;
  v110 = 0;
  v124 = (unsigned __int16 *)&v155;
  v116 = 0;
  v113 = (unsigned int *)&v156;
  v13 = 0;
  hMem = 0;
  v106 = 0;
  v126 = 0;
  DestinationString = 0;
  v129 = 0;
  v135 = 0;
  v114 = 0;
  v127 = 0;
  v107 = 0;
  ReturnLength = 0;
  *(_OWORD *)dwProcessId = 0;
  v108 = 0;
  v123 = 0;
  v122 = 0;
  memset_0(v152, 0, 0x60u);
  *(_OWORD *)Size = 0;
  v14 = DigestInit(v136);
  ChannelBindings = v14;
  if ( v14 < 0 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 91;
LABEL_8:
      v18 = (unsigned int)v14;
LABEL_9:
      WPP_SF_d(v16[2], v17, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v18);
LABEL_10:
      v19 = 0;
LABEL_11:
      v20 = v99;
LABEL_12:
      v21 = a11;
      goto LABEL_13;
    }
    goto LABEL_400;
  }
  if ( a8 && v112 && a3 && a7 )
  {
    *v112 = 0;
    *v118 = 0;
    *a8 = 0;
    if ( a9 )
      *a9 = g_TimeForever;
    *(_QWORD *)(a11 + 8) = 0;
    *(_DWORD *)a11 = 0;
    HttpOrSaslBufferCount = DigestGetHttpOrSaslBufferCount(a3);
    if ( (int)CredHandlerHandleToPtr(a1, 0, &hMem) < 0 )
    {
      ChannelBindings = -2146893043;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 93;
LABEL_24:
        WPP_SF_(v16[2], v23, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        goto LABEL_10;
      }
      goto LABEL_25;
    }
    v117 = 1;
    if ( (*((_BYTE *)hMem + 32) & 1) == 0 )
    {
      ChannelBindings = -2146893054;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v24 = 94;
LABEL_30:
        WPP_SF_(v16[2], v24, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
LABEL_31:
        v19 = 0;
        v20 = 1;
        goto LABEL_12;
      }
      goto LABEL_402;
    }
    if ( HttpOrSaslBufferCount <= 1 )
    {
      if ( !*(_DWORD *)(a3 + 4) || !*(_DWORD *)(a7 + 4) )
      {
        ChannelBindings = -2146893048;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v24 = 96;
          goto LABEL_30;
        }
LABEL_402:
        v19 = 0;
        goto LABEL_396;
      }
      v25 = 6;
    }
    else if ( *(_DWORD *)(a3 + 4) < 5u || (v25 = 4, !*(_DWORD *)(a7 + 4)) )
    {
      ChannelBindings = -2146893048;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v24 = 95;
        goto LABEL_30;
      }
      goto LABEL_402;
    }
    LOBYTE(v22) = 1;
    if ( !(unsigned __int8)SspGetTokenBufferByIndex(a3, 0, &v115, v22)
      || (v26 = (__int64)v115, !(unsigned int)ContextIsTokenOK(v115, 4096, 0)) )
    {
      ChannelBindings = -2146893048;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          97,
          &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
          2148074248LL);
        goto LABEL_31;
      }
      v19 = 0;
LABEL_396:
      v20 = 1;
      goto LABEL_335;
    }
    if ( !(unsigned __int8)SspGetTokenBufferByIndex(a7, 0, &v113, 0)
      || (v27 = v113, !(unsigned int)ContextIsTokenOK(v113, 0, 0)) )
    {
      ChannelBindings = -2146893048;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v19 = 0;
        goto LABEL_334;
      }
      v17 = 98;
LABEL_73:
      v18 = 2148074248LL;
      goto LABEL_9;
    }
    LODWORD(v115) = v104 & 0x100;
    if ( (v104 & 0x100) != 0 )
    {
      *((_QWORD *)v27 + 1) = 0;
      *v27 = 0;
    }
    v29 = (_BYTE *)*((_QWORD *)v27 + 1);
    if ( v29 && *v27 )
      *v29 = 0;
    ChannelBindings = SspGetChannelBindings(v28, a3, &v123);
    if ( ChannelBindings < 0 || (ChannelBindings = SspGetChannelBindingsResult(v30, a7, &v122), ChannelBindings < 0) )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_385:
      v19 = 0;
      goto LABEL_149;
    }
    if ( *(_QWORD *)(v26 + 8) && *(_DWORD *)v26 > 1u )
    {
      v14 = DigestParse(v26, MD5_AUTH_NAMES, 24, DigestParser2Callback, v136);
      ChannelBindings = v14;
      if ( v14 < 0 )
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 121;
          goto LABEL_8;
        }
        goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      v32 = HttpOrSaslBufferCount;
      if ( HttpOrSaslBufferCount <= 1 )
      {
        *(_DWORD *)v101 = 4;
        v102 = 3;
        RtlInitString(&DestinationString, "AUTHENTICATE");
        StringReference(v142, &DestinationString);
        RtlInitString(&v135, "00000000000000000000000000000000");
        StringReference(v144, &v135);
      }
      else
      {
        LOBYTE(v31) = 1;
        if ( !(unsigned __int8)SspGetTokenBufferByIndex(a3, 1, Value, v31)
          || (v33 = *(unsigned __int16 **)Value, !(unsigned int)ContextIsTokenOK(*(_QWORD *)Value, 4096, 0)) )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 123;
            goto LABEL_73;
          }
          goto LABEL_385;
        }
        LOBYTE(v34) = 1;
        if ( !(unsigned __int8)SspGetTokenBufferByIndex(a3, 3, &v121, v34)
          || (v35 = v121, !(unsigned int)ContextIsTokenOK(v121, 4096, 0)) )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 125;
            goto LABEL_73;
          }
          goto LABEL_385;
        }
        v36 = *((_QWORD *)v33 + 1);
        if ( !v36 || !*(_DWORD *)v33 || (*((_DWORD *)v33 + 1) & 0xFFFFFFF) != 3 )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 126;
            goto LABEL_73;
          }
          goto LABEL_25;
        }
        v37 = strlencounted(v36, *v33);
        if ( !v37 )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 127;
            goto LABEL_73;
          }
LABEL_25:
          v19 = 0;
LABEL_334:
          v20 = v99;
          goto LABEL_335;
        }
        v142[0] = v37;
        v142[1] = *v33;
        v143 = *((_QWORD *)v33 + 1);
        if ( *(_DWORD *)v35 )
        {
          v39 = *((_QWORD *)v35 + 1);
          if ( !v39 || (v38 & *((_DWORD *)v33 + 1)) != 3 )
          {
            ChannelBindings = -2146893048;
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v17 = 128;
              goto LABEL_73;
            }
            goto LABEL_25;
          }
          v40 = strlencounted(v39, *v35);
          if ( v40 )
          {
            if ( v40 != 32 )
            {
              ChannelBindings = -2146893048;
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v17 = 129;
                goto LABEL_73;
              }
              goto LABEL_25;
            }
            v144[0] = 32;
            v144[1] = *v35;
            v145 = *((_QWORD *)v35 + 1);
          }
        }
        *(_DWORD *)v101 = 3;
        if ( (int)CheckItemInList("MD5-sess") < 0 )
        {
          if ( (int)CheckItemInList("MD5") < 0 && v140 )
          {
            ChannelBindings = -2146893046;
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v23 = 132;
              goto LABEL_24;
            }
            goto LABEL_25;
          }
          v102 = 2;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
            v16 = (PVOID *)WPP_GLOBAL_Control;
          }
          ChannelBindings = -2146893046;
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
          {
            v23 = 131;
            goto LABEL_24;
          }
          goto LABEL_385;
        }
        v102 = 3;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        v32 = HttpOrSaslBufferCount;
      }
      v20 = 1;
      v41 = v25 | 0xC;
      if ( (int)CheckItemInList("auth-conf") < 0 )
      {
        if ( (int)CheckItemInList("auth-int") < 0 )
        {
          if ( (int)CheckItemInList("auth") < 0 )
          {
            if ( v141 )
            {
              ChannelBindings = -2146893046;
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
                v19 = 0;
                goto LABEL_12;
              }
              v19 = 0;
LABEL_335:
              v21 = a11;
              goto LABEL_151;
            }
            if ( v32 <= 1 )
            {
              v99 = 2;
              v42 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v43 = 138;
                goto LABEL_132;
              }
            }
            else
            {
              v99 = 1;
              v42 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v43 = 137;
                goto LABEL_132;
              }
            }
          }
          else
          {
            v99 = 2;
            v42 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v43 = 136;
              goto LABEL_132;
            }
          }
        }
        else
        {
          v41 |= 0x20000u;
          v99 = 3;
          v42 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v43 = 135;
            goto LABEL_132;
          }
        }
      }
      else
      {
        v41 |= 0x20010u;
        v99 = 4;
        v42 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v43 = 134;
LABEL_132:
          WPP_SF_(v42[2], v43, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          v42 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      v44 = *(_QWORD *)String;
      if ( *(_QWORD *)String )
      {
        if ( (int)CtxtHandlerHandleToContext(*(_QWORD *)String, 0, &v106) < 0 )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v45 = 142;
            goto LABEL_141;
          }
          goto LABEL_147;
        }
      }
      else
      {
        if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 4) != 0 )
          WPP_SF_(v42[2], 140, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        if ( (int)CtxtHandlerReferenceToPtr(&String1) < 0 )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v45 = 141;
LABEL_141:
            WPP_SF_d(v16[2], v45, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, 2148074248LL);
            v13 = v106;
LABEL_142:
            v19 = 0;
            goto LABEL_11;
          }
LABEL_147:
          v13 = v106;
LABEL_148:
          v19 = 0;
LABEL_149:
          v20 = v99;
          goto LABEL_150;
        }
      }
      v13 = v106;
      if ( v106 )
      {
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v106 + 648));
        v126 = v13;
      }
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v13);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      v110 = 1;
      if ( *(_DWORD *)(v13 + 96) )
      {
        if ( v44 )
        {
          ChannelBindings = -1073741715;
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
          {
            WPP_SF_(v16[2], 144, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
            goto LABEL_142;
          }
LABEL_200:
          v19 = 0;
          goto LABEL_334;
        }
        if ( (*(unsigned __int8 (__fastcall **)(DWORD *, PVOID *, _QWORD))(*(_QWORD *)&g_LsaFunctions + 192LL))(
               dwProcessId,
               &WPP_GLOBAL_Control,
               0)
          && (dwProcessId[2] & 1) == 0
          && *(_DWORD *)(v13 + 640) != dwProcessId[0] )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v48 = 145;
          v49 = 2148074248LL;
          goto LABEL_172;
        }
        v21 = a11;
        v50 = SspMapDigestContext(v13, v136, 96, a11);
        ChannelBindings = v50;
        if ( v50 >= 0 )
        {
          ChannelBindings = 590611;
          *v118 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          v19 = 0;
          *v112 = v13;
          v13 = 0;
          v16 = (PVOID *)WPP_GLOBAL_Control;
        }
        else
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v51 = 146;
LABEL_177:
            WPP_SF_d(v16[2], v51, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, (unsigned int)v50);
            v19 = 0;
            v20 = v99;
            goto LABEL_13;
          }
          v19 = 0;
        }
        v20 = v99;
        goto LABEL_151;
      }
      v52 = 1;
      v53 = CheckItemInList("utf-8");
      v54 = 0;
      if ( v53 >= 0 )
      {
        if ( (*(_DWORD *)v101 != 4 || g_fParameter_UTF8SASL != 1)
          && (*(_DWORD *)v101 != 3 || g_fParameter_UTF8HTTP != 1) )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
            v16 = (PVOID *)WPP_GLOBAL_Control;
          }
          ChannelBindings = -2146893018;
          goto LABEL_200;
        }
        v52 = 2;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          v54 = 0;
        }
      }
      v55 = *(_DWORD *)v101;
      *(_DWORD *)(v13 + 44) = *(_DWORD *)v101;
      *(_QWORD *)(v13 + 52) = 3;
      *(_DWORD *)(v13 + 48) = v99;
      *(_DWORD *)(v13 + 60) = v52;
      if ( *(_DWORD *)(v13 + 48) == 4 )
      {
        RtlAcquireResourceShared(&g_RtlResource_CipherList, 1u);
        for ( i = 0; i < (unsigned __int16)g_CipherInfoListCount; ++i )
        {
          if ( (int)CheckItemInList((char *)g_CipherInfoList + 12 * i + 4) >= 0 )
          {
            *(_DWORD *)(v13 + 56) = *((_DWORD *)g_CipherInfoList + 3 * i);
            break;
          }
        }
        if ( !*(_DWORD *)(v13 + 56) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              150,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              g_strParameter_CipherList.Buffer);
          ChannelBindings = -1073741069;
          RtlReleaseResource(&g_RtlResource_CipherList);
          goto LABEL_142;
        }
        RtlReleaseResource(&g_RtlResource_CipherList);
        v55 = *(_DWORD *)v101;
        v54 = 0;
      }
      if ( v146 && Src )
      {
        if ( v146 >= 9u )
        {
          ChannelBindings = -2146893018;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_200;
          v48 = 153;
          goto LABEL_215;
        }
        Value[0] = 0;
        *(_QWORD *)String = 0;
        v158 = 0;
        memcpy_0(String, Src, v146);
        v57 = RtlCharToInteger(String, 0xAu, Value);
        v54 = 0;
        if ( v57 < 0 )
        {
          ChannelBindings = -2146893018;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v48 = 151;
LABEL_215:
          v49 = 2148074278LL;
LABEL_172:
          WPP_SF_d(v16[2], v48, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v49);
          goto LABEL_142;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, Value[0]);
        *(_DWORD *)(v13 + 100) = Value[0];
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      LogSess = DigestDirectiveCheck(v136, v55, v54);
      ChannelBindings = LogSess;
      if ( LogSess < 0 )
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v48 = 155;
        goto LABEL_227;
      }
      ChannelBindings = DigestProcessParameters(
                          v13,
                          (__int64)v136,
                          (__int64)Size,
                          (int *)&v105,
                          (int *)&v109,
                          &v107,
                          &v108);
      if ( ChannelBindings < 0 )
      {
        if ( (g_dwParameter_ServerCompat & 1) == 0 || HttpOrSaslBufferCount <= 1 || (v137 & 0x10) == 0 )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v48 = 159;
          v49 = (unsigned int)ChannelBindings;
          goto LABEL_172;
        }
        HttpOrSaslBufferCount = 0;
        LODWORD(v113) = 0;
        LODWORD(v106) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        v137 |= 8u;
        v59 = DigestParse(v26, MD5_AUTH_NAMES, 24, DigestParser2Callback, v136);
        if ( v59 < 0 )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              157,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              (unsigned int)v59,
              ChannelBindings);
            goto LABEL_142;
          }
          goto LABEL_400;
        }
        v60 = DigestProcessParameters(
                v13,
                (__int64)v136,
                (__int64)Size,
                (int *)&HttpOrSaslBufferCount,
                (int *)&v113,
                &v106,
                &v108);
        ChannelBindings = v60;
        if ( v60 < 0 )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              158,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              (unsigned int)v60);
            v16 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_148;
        }
        v105 = HttpOrSaslBufferCount;
        v109 = (unsigned int)v113;
        v107 = v106;
        *(_DWORD *)(v13 + 40) |= 8u;
      }
      v116 = 1;
      LogSess = DigestProcessUpgradedParameters(v26, v104, 0, v123, v122, (__int64)v136);
      ChannelBindings = LogSess;
      if ( LogSess >= 0 )
      {
        if ( (_DWORD)v115 )
        {
          v41 |= 0x100u;
          *((_QWORD *)v27 + 1) = Size[1];
          *v27 = Size[0];
          Size[1] = 0;
          LODWORD(Size[0]) = 0;
        }
        else
        {
          v61 = Size[0];
          if ( *v27 < LODWORD(Size[0]) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                161,
                &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
                *v27,
                Size[0]);
              v61 = Size[0];
            }
            *v27 = v61;
            ChannelBindings = -1073741789;
            v16 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_148;
          }
          memcpy_0(*((void **)v27 + 1), (const void *)Size[1], LODWORD(Size[0]));
          *v27 = Size[0];
        }
        *(_DWORD *)(v13 + 36) = v41;
        LogSess = StringDuplicate(v13 + 80, v139);
        v63 = 0;
        ChannelBindings = LogSess;
        if ( LogSess >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          LogSess = CtxtCreateLogSess(v13, v62, v63);
          ChannelBindings = LogSess;
          if ( LogSess >= 0 )
          {
            v21 = a11;
            v50 = SspMapDigestContext(v13, v136, v44 != 0 ? 64 : 96, a11);
            ChannelBindings = v50;
            if ( v50 >= 0 )
            {
              v64 = v131;
              *v118 = 1;
              ++*(_DWORD *)(v13 + 96);
              v110 = v44 != 0;
              *v112 = v13;
              *v125 = v41;
              if ( v64 )
                *v64 = *(_QWORD *)(v13 + 616);
              v16 = (PVOID *)WPP_GLOBAL_Control;
              ChannelBindings = 0;
              v19 = 0;
            }
            else
            {
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v51 = 165;
                goto LABEL_177;
              }
              v19 = 0;
            }
            v20 = v99;
            goto LABEL_151;
          }
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_400:
            v19 = 0;
            goto LABEL_149;
          }
          v48 = 164;
        }
        else
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_400;
          v48 = 162;
        }
      }
      else
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_400;
        v48 = 160;
      }
LABEL_227:
      v49 = (unsigned int)LogSess;
      goto LABEL_172;
    }
    Memory = (_DWORD *)DigestAllocateMemory(0x2B0u);
    v19 = Memory;
    if ( !Memory )
    {
      ChannelBindings = -2146893056;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_334;
      v66 = 99;
LABEL_288:
      WPP_SF_(v16[2], v66, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      goto LABEL_11;
    }
    v67 = ContextInit(Memory);
    v69 = 0;
    ChannelBindings = v67;
    if ( v67 < 0 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_334;
      v70 = 100;
      goto LABEL_293;
    }
    v72 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v19);
      v72 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( HttpOrSaslBufferCount <= 1 )
    {
      if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 4) != 0 )
        WPP_SF_(v72[2], 102, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      v73 = 4;
    }
    else
    {
      v73 = 3;
    }
    *(_DWORD *)v101 = v73;
    v19[11] = v73;
    if ( v73 == 4 && g_fParameter_UTF8SASL == 1 || v73 == 3 && g_fParameter_UTF8HTTP == 1 )
      v74 = 2;
    else
      v74 = 1;
    v19[15] = v74;
    v67 = NonceCreate(v19 + 16, v68, v69);
    ChannelBindings = v67;
    if ( v67 < 0 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_334;
      v70 = 104;
LABEL_293:
      v71 = (unsigned int)v67;
LABEL_294:
      WPP_SF_d(v16[2], v70, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v71);
      goto LABEL_11;
    }
    if ( v19[11] == 3 )
    {
      LOBYTE(v75) = 1;
      if ( !(unsigned __int8)SspGetTokenBufferByIndex(a3, 4, &v124, v75)
        || (v76 = v124, !(unsigned int)ContextIsTokenOK(v124, 4096, 0)) )
      {
        ChannelBindings = -2146893048;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_334;
        v70 = 105;
LABEL_322:
        v71 = 2148074248LL;
        goto LABEL_294;
      }
      if ( *((_QWORD *)v76 + 1) )
      {
        if ( (*((_DWORD *)v76 + 1) & 0xFFFFFFF) != 3 )
        {
          ChannelBindings = -2146893048;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_334;
          v70 = 106;
          goto LABEL_322;
        }
        if ( *(_DWORD *)v76 )
        {
          v77 = ustrlencounted(*((_QWORD *)v76 + 1), *v76);
          if ( v77 )
          {
            v128[1] = v79;
            v128[0] = 2 * v77;
            v130 = v78;
            ChannelBindings = EncodeUnicodeString(v128, 0x6FAFu, (__int64)&v127, &v114);
            if ( ChannelBindings < 0 )
            {
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_334;
              v66 = 107;
              goto LABEL_288;
            }
            if ( v114 == 1 )
            {
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
                v16 = (PVOID *)WPP_GLOBAL_Control;
              }
              ChannelBindings = -1073741470;
              goto LABEL_334;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          ChannelBindings = StringAllocate(&v127, 1);
          if ( ChannelBindings < 0 )
          {
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_334;
            v66 = 110;
            goto LABEL_288;
          }
          LOWORD(v127) = 0;
        }
      }
    }
    v80 = v104;
    v102 = 3;
    v19[13] = 3;
    if ( (v80 & 0x200000) != 0 )
    {
      v81 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        v81 = (PVOID *)WPP_GLOBAL_Control;
        v80 = v104;
      }
      v25 |= 0x200000u;
    }
    else
    {
      v81 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v80 & 0x10) != 0 )
    {
      if ( v81 != &WPP_GLOBAL_Control && (*((_BYTE *)v81 + 28) & 4) != 0 )
        WPP_SF_(v81[2], 112, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      v25 |= 0x20010u;
      v20 = 4;
    }
    else if ( (v80 & 0x20000) != 0 )
    {
      if ( v81 != &WPP_GLOBAL_Control && (*((_BYTE *)v81 + 28) & 4) != 0 )
        WPP_SF_(v81[2], 113, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      v25 |= 0x20000u;
      v20 = 3;
    }
    else
    {
      v20 = 2;
    }
    v19[12] = v20;
    v19[9] = v25;
    v82 = ContextCreateChal(v19, &v127, Size);
    ChannelBindings = v82;
    if ( v82 >= 0 )
    {
      if ( (_DWORD)v115 )
      {
        v25 |= 0x100u;
        *((_QWORD *)v27 + 1) = Size[1];
        *v27 = Size[0];
        Size[1] = 0;
        LODWORD(Size[0]) = 0;
      }
      else
      {
        v83 = Size[0];
        if ( *v27 < LODWORD(Size[0]) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              115,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              *v27,
              Size[0]);
            v83 = Size[0];
          }
          *v27 = v83;
          ChannelBindings = -1073741789;
          v16 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_150;
        }
        memcpy_0(*((void **)v27 + 1), (const void *)Size[1], LODWORD(Size[0]));
        *v27 = Size[0];
      }
      v21 = a11;
      *((_QWORD *)v19 + 77) = g_TimeForever;
      v19[9] = v25;
      v19[4] = 1;
      v84 = SspMapDigestContext(v19, v136, 112, a11);
      ChannelBindings = v84;
      if ( v84 >= 0 )
      {
        *v118 = 1;
        CtxtHandlerInsertCred(v19, v85, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        ChannelBindings = 590610;
        *v112 = (__int64)v19;
        v19 = 0;
        *v125 = v25;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_151;
      }
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_151:
        if ( v107 != 1 )
          goto LABEL_422;
        v46 = v105;
        if ( v105 )
        {
          if ( v13 )
          {
            v88 = (__int16 *)(v13 + 600);
            v89 = (__int16 *)(v13 + 568);
            if ( !*(_WORD *)(v13 + 600) )
            {
              v88 = (__int16 *)&v149;
              if ( v150 )
                v88 = &v150;
            }
            if ( !*v89 )
            {
              v89 = (__int16 *)&v148;
              if ( v151 )
                v89 = &v151;
            }
            if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
            {
              WPP_SF_ZZ(v16[2], 168, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v88, v89);
              v46 = v105;
            }
            (*(void (__fastcall **)(_QWORD, _QWORD, __int16 *, __int16 *, _QWORD, _QWORD, int, struct _TOKEN_SOURCE *, __int64))(*(_QWORD *)&g_LsaFunctions + 168LL))(
              v46,
              v109,
              v88,
              v89,
              0,
              0,
              3,
              &g_DigestSource,
              v13 + 552);
            v16 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_422;
        }
        if ( !v13 )
        {
LABEL_422:
          if ( ChannelBindings >= 0 )
          {
            v91 = v112;
          }
          else
          {
            if ( v116 == 1 )
            {
              if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)&g_LsaFunctions + 8LL))(v13 + 552) < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
              }
              v90 = *(void **)(v13 + 544);
              if ( v90 )
              {
                NtClose(v90);
                *(_QWORD *)(v13 + 544) = 0;
              }
            }
            if ( v19 )
              ContextFree(v19);
            v91 = v112;
            v92 = v118;
            *v112 = 0;
            *v92 = 0;
            if ( *(_QWORD *)(v21 + 8) )
            {
              (*(void (**)(void))(*(_QWORD *)&g_LsaFunctions + 48LL))();
              *(_QWORD *)(v21 + 8) = 0;
              *(_DWORD *)v21 = 0;
            }
            v16 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v117 )
          {
            v93 = hMem;
            if ( hMem )
            {
              if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
                WPP_SF_q(v16[2], 170, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, hMem);
              v94 = CredHandlerRelease(v93);
              v95 = v94;
              if ( v94 >= 0 )
              {
                v16 = (PVOID *)WPP_GLOBAL_Control;
              }
              else
              {
                v16 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    171,
                    &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
                    (unsigned int)v94);
                  v16 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( ChannelBindings >= 0 )
                  ChannelBindings = v95;
              }
            }
          }
          if ( v110 && v13 )
          {
            if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
              WPP_SF_q(v16[2], 172, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v13);
            v96 = CtxtHandlerRelease((HLOCAL)v13);
            v97 = v96;
            if ( v96 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  173,
                  &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
                  (unsigned int)v96);
              if ( ChannelBindings >= 0 )
                ChannelBindings = v97;
            }
          }
          else if ( v126 )
          {
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v126 + 648));
          }
          if ( Size[1] )
          {
            DigestFreeMemory((HLOCAL)Size[1]);
            Size[1] = 0;
            LODWORD(Size[0]) = 0;
          }
          DigestFree(v136);
          StringFree(&v127);
          if ( ChannelBindings != 590610 )
            DigestTelemetry::RecordDirectDigestCall(
              (DigestTelemetry *)(unsigned int)ChannelBindings,
              1,
              *(int *)v101,
              v102,
              v20,
              dwProcessId[0]);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              174,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              *v91,
              ChannelBindings);
          return (unsigned int)ChannelBindings;
        }
        if ( GetTokenInformation(
               *(HANDLE *)(v13 + 544),
               (TOKEN_INFORMATION_CLASS)(v105 + 1),
               TokenInformation,
               0x100u,
               &ReturnLength) )
        {
          v47 = TokenInformation[0];
        }
        else
        {
          v47 = 0;
          LastError = GetLastError();
          v87 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_410:
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _QWORD, __int64, int, int, struct _TOKEN_SOURCE *, __int64))(*(_QWORD *)&g_LsaFunctions + 464LL))(
              0,
              0,
              v13 + 600,
              v13 + 568,
              0,
              v47,
              3,
              v108,
              &g_DigestSource,
              v13 + 552);
            v16 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_422;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_407:
            if ( v87 != &WPP_GLOBAL_Control && (*((_BYTE *)v87 + 28) & 4) != 0 )
              WPP_SF_ZZq((TRACEHANDLE)v87[2], v13 + 568, v47);
            goto LABEL_410;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            166,
            &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
            LastError);
        }
        v87 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_407;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
        (unsigned int)v84);
LABEL_13:
      v16 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_151;
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
        (unsigned int)v82);
      goto LABEL_12;
    }
LABEL_150:
    v21 = a11;
    goto LABEL_151;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18001e4b0  push    rbp
0x18001e4b2  push    rbx
0x18001e4b3  push    rsi
0x18001e4b4  push    rdi
0x18001e4b5  push    r12
0x18001e4b7  push    r13
0x18001e4b9  push    r14
0x18001e4bb  push    r15
0x18001e4bd  lea     rbp, [rsp-628h]
0x18001e4c5  sub     rsp, 728h
0x18001e4cc  mov     rax, cs:__security_cookie
0x18001e4d3  xor     rax, rsp
0x18001e4d6  mov     [rbp+660h+var_50], rax
0x18001e4dd  mov     rax, [rbp+660h+arg_50]
0x18001e4e4  xor     ebx, ebx
0x18001e4e6  mov     r13, [rbp+660h+arg_38]
0x18001e4ed  mov     r14, r8
0x18001e4f0  mov     r12, [rbp+660h+arg_40]
0x18001e4f7  mov     rsi, rcx
0x18001e4fa  mov     rdi, [rbp+660h+arg_30]
0x18001e501  mov     [rsp+760h+var_6F8], rax
0x18001e506  mov     rax, [rbp+660h+arg_28]
0x18001e50d  mov     [rbp+660h+var_6A0], rax
0x18001e511  mov     rax, [rbp+660h+arg_48]
0x18001e518  mov     [rbp+660h+var_6C8], r9d
0x18001e51c  mov     r9, rdx
0x18001e51f  mov     [rbp+660h+var_678], rax
0x18001e523  mov     qword ptr [rbp+660h+String], rdx
0x18001e52a  mov     [rbp+660h+var_640], r13
0x18001e52e  mov     [rbp+660h+var_610], r12
0x18001e532  mov     [rbp+660h+var_6C4], ebx
0x18001e535  mov     [rbp+660h+var_6B0], ebx
0x18001e538  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e53f  lea     rax, WPP_GLOBAL_Control
0x18001e546  cmp     rcx, rax
0x18001e549  jz      short loc_18001E564
0x18001e54b  test    byte ptr [rcx+1Ch], 80h
0x18001e54f  jz      short loc_18001E564
0x18001e551  mov     rcx, [rcx+10h]
0x18001e555  lea     edx, [rbx+5Ah]
0x18001e558  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001e55f  call    WPP_SF_q
0x18001e564  xor     edx, edx; Val
0x18001e566  lea     rcx, [rbp+660h+var_5D0]; void *
0x18001e56d  mov     r8d, 410h; Size
0x18001e573  call    memset_0
0x18001e578  xor     eax, eax
0x18001e57a  mov     [rsp+760h+var_6F0], rbx
0x18001e57f  mov     [rbp+660h+var_5F8], rax
0x18001e583  mov     ecx, 1
0x18001e588  xorps   xmm0, xmm0
0x18001e58b  mov     dword ptr [rsp+760h+var_6E4], ecx
0x18001e58f  lea     rax, [rbp+660h+var_1C0]
0x18001e596  mov     [rsp+760h+var_700], ecx
0x18001e59a  mov     [rbp+660h+var_688], rax
0x18001e59e  xorps   xmm1, xmm1
0x18001e5a1  lea     rax, [rbp+660h+var_1B0]
0x18001e5a8  mov     [rbp+660h+var_6E0], ecx
0x18001e5ab  mov     qword ptr [rbp+660h+Value], rax
0x18001e5af  lea     r8d, [rcx+5Fh]; Size
0x18001e5b3  lea     rax, [rbp+660h+var_190]
0x18001e5ba  mov     [rbp+660h+var_67C], ebx
0x18001e5bd  mov     [rbp+660h+var_660], rax
0x18001e5c1  lea     rcx, [rbp+660h+var_1C0]; void *
0x18001e5c8  lea     rax, [rbp+660h+var_180]
0x18001e5cf  mov     [rbp+660h+var_6AC], ebx
0x18001e5d2  mov     [rbp+660h+var_648], rax
0x18001e5d6  xor     edx, edx; Val
0x18001e5d8  lea     rax, [rbp+660h+var_170]
0x18001e5df  mov     [rbp+660h+var_680], ebx
0x18001e5e2  mov     [rbp+660h+var_698], rax
0x18001e5e6  mov     r15, rbx
0x18001e5e9  mov     [rbp+660h+hMem], rbx
0x18001e5ed  mov     [rbp+660h+var_6C0], rbx
0x18001e5f1  mov     [rbp+660h+var_638], rbx
0x18001e5f5  movups  xmmword ptr [rbp+660h+DestinationString.Length], xmm0
0x18001e5f9  mov     [rbp+660h+var_61C], ebx
0x18001e5fc  movups  xmmword ptr [rbp+660h+var_5E0.Length], xmm1
0x18001e603  mov     [rbp+660h+var_690], ebx
0x18001e606  movups  [rbp+660h+var_630], xmm0
0x18001e60a  mov     [rbp+660h+var_6B8], ebx
0x18001e60d  mov     [rbp+660h+var_668], ebx
0x18001e610  movups  xmmword ptr [rbp+660h+var_608], xmm0
0x18001e614  mov     [rbp+660h+var_6B4], ebx
0x18001e617  mov     [rbp+660h+var_650], rbx
0x18001e61b  mov     [rbp+660h+var_658], rbx
0x18001e61f  call    memset_0
0x18001e624  xorps   xmm0, xmm0
0x18001e627  lea     rcx, [rbp+660h+var_5D0]
0x18001e62e  movups  xmmword ptr [rbp+660h+Size], xmm0
0x18001e632  call    DigestInit
0x18001e637  xor     r8d, r8d
0x18001e63a  mov     ebx, eax
0x18001e63c  test    eax, eax
0x18001e63e  jns     short loc_18001E694
0x18001e640  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e647  lea     rdi, WPP_GLOBAL_Control
0x18001e64e  cmp     rcx, rdi
0x18001e651  jz      loc_18002001B
0x18001e657  test    byte ptr [rcx+1Ch], 1
0x18001e65b  jz      loc_18002001B
0x18001e661  lea     edx, [r8+5Bh]
0x18001e665  mov     r9d, eax
0x18001e668  mov     rcx, [rcx+10h]
0x18001e66c  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001e673  call    WPP_SF_d
0x18001e678  mov     r13, r15
0x18001e67b  mov     r14d, [rsp+760h+var_700]
0x18001e680  mov     r12, [rsp+760h+var_6F8]
0x18001e685  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e68c  xor     r8d, r8d
0x18001e68f  jmp     loc_18001EF61
0x18001e694  test    r13, r13
0x18001e697  jz      loc_18002043E
0x18001e69d  mov     rax, [rbp+660h+var_6A0]
0x18001e6a1  test    rax, rax
0x18001e6a4  jz      loc_18002043E
0x18001e6aa  test    r14, r14
0x18001e6ad  jz      loc_18002043E
0x18001e6b3  test    rdi, rdi
0x18001e6b6  jz      loc_18002043E
0x18001e6bc  mov     [rax], r8
0x18001e6bf  mov     rax, [rbp+660h+var_678]
0x18001e6c3  mov     [rax], r8b
0x18001e6c6  mov     [r13+0], r8d
0x18001e6ca  test    r12, r12
0x18001e6cd  jz      short loc_18001E6DA
0x18001e6cf  mov     rax, cs:g_TimeForever
0x18001e6d6  mov     [r12], rax
0x18001e6da  mov     rax, [rsp+760h+var_6F8]
0x18001e6df  mov     rcx, r14
0x18001e6e2  mov     [rax+8], r8
0x18001e6e6  mov     [rax], r8d
0x18001e6e9  call    DigestGetHttpOrSaslBufferCount
0x18001e6ee  lea     r8, [rbp+660h+hMem]
0x18001e6f2  mov     [rsp+760h+var_6E8], eax
0x18001e6f6  xor     edx, edx
0x18001e6f8  mov     rcx, rsi
0x18001e6fb  mov     ebx, eax
0x18001e6fd  call    CredHandlerHandleToPtr
0x18001e702  xor     r8d, r8d
0x18001e705  test    eax, eax
0x18001e707  jns     short loc_18001E748
0x18001e709  mov     ebx, 8009030Dh
0x18001e70e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e715  lea     rdx, WPP_GLOBAL_Control
0x18001e71c  cmp     rcx, rdx
0x18001e71f  jz      short loc_18001E740
0x18001e721  test    byte ptr [rcx+1Ch], 1
0x18001e725  jz      short loc_18001E740
0x18001e727  lea     edx, [r8+5Dh]
0x18001e72b  mov     rcx, [rcx+10h]
0x18001e72f  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001e736  call    WPP_SF_
0x18001e73b  jmp     loc_18001E678
0x18001e740  mov     r13, r8
0x18001e743  jmp     loc_18001FC13
0x18001e748  mov     rax, [rbp+660h+hMem]
0x18001e74c  mov     r12d, 1
0x18001e752  mov     [rbp+660h+var_67C], r12d
0x18001e756  test    [rax+20h], r12b
0x18001e75a  jnz     short loc_18001E7A2
0x18001e75c  mov     ebx, 80090302h
0x18001e761  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e768  lea     rdx, WPP_GLOBAL_Control
0x18001e76f  cmp     rcx, rdx
0x18001e772  jz      loc_18002002B
0x18001e778  test    [rcx+1Ch], r12b
0x18001e77c  jz      loc_18002002B
0x18001e782  lea     edx, [r12+5Dh]
0x18001e787  mov     rcx, [rcx+10h]
0x18001e78b  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001e792  call    WPP_SF_
0x18001e797  mov     r13, r15
0x18001e79a  mov     r14d, r12d
0x18001e79d  jmp     loc_18001E680
0x18001e7a2  cmp     ebx, r12d
0x18001e7a5  jbe     short loc_18001E7E6
0x18001e7a7  cmp     dword ptr [r14+4], 5
0x18001e7ac  jb      short loc_18001E7B9
0x18001e7ae  mov     esi, 4
0x18001e7b3  cmp     [rdi+4], r12d
0x18001e7b7  jnb     short loc_18001E7FF
0x18001e7b9  mov     ebx, 80090308h
0x18001e7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7c5  lea     rdx, WPP_GLOBAL_Control
0x18001e7cc  cmp     rcx, rdx
0x18001e7cf  jz      loc_18002002B
0x18001e7d5  test    [rcx+1Ch], r12b
0x18001e7d9  jz      loc_18002002B
0x18001e7df  mov     edx, 5Fh ; '_'
0x18001e7e4  jmp     short loc_18001E787
0x18001e7e6  cmp     [r14+4], r12d
0x18001e7ea  jb      loc_18001FFD0
0x18001e7f0  cmp     [rdi+4], r12d
0x18001e7f4  jb      loc_18001FFD0
0x18001e7fa  mov     esi, 6
0x18001e7ff  mov     r9b, r12b
0x18001e802  lea     r8, [rbp+660h+var_688]
0x18001e806  xor     edx, edx
0x18001e808  mov     rcx, r14
0x18001e80b  call    SspGetTokenBufferByIndex
0x18001e810  xor     r8d, r8d
0x18001e813  test    al, al
0x18001e815  jz      loc_18001FF92
0x18001e81b  mov     r13, [rbp+660h+var_688]
0x18001e81f  mov     edx, 1000h
0x18001e824  mov     rcx, r13
0x18001e827  call    ContextIsTokenOK
0x18001e82c  xor     r8d, r8d
0x18001e82f  test    eax, eax
0x18001e831  jz      loc_18001FF92
0x18001e837  xor     r9d, r9d
0x18001e83a  lea     r8, [rbp+660h+var_698]
0x18001e83e  xor     edx, edx
0x18001e840  mov     rcx, rdi
0x18001e843  call    SspGetTokenBufferByIndex
0x18001e848  xor     r8d, r8d
0x18001e84b  test    al, al
0x18001e84d  jz      loc_18001FF66
0x18001e853  mov     r12, [rbp+660h+var_698]
0x18001e857  xor     edx, edx
0x18001e859  mov     rcx, r12
0x18001e85c  call    ContextIsTokenOK
0x18001e861  xor     r8d, r8d
0x18001e864  test    eax, eax
0x18001e866  jz      loc_18001FF60
0x18001e86c  mov     eax, [rbp+660h+var_6C8]
0x18001e86f  and     eax, 100h
0x18001e874  mov     dword ptr [rbp+660h+var_688], eax
0x18001e877  jz      short loc_18001E882
0x18001e879  mov     [r12+8], r8
0x18001e87e  mov     [r12], r8d
0x18001e882  mov     rax, [r12+8]
0x18001e887  test    rax, rax
0x18001e88a  jz      short loc_18001E896
0x18001e88c  cmp     dword ptr [r12], 1
0x18001e891  jb      short loc_18001E896
0x18001e893  mov     [rax], r8b
0x18001e896  lea     r8, [rbp+660h+var_650]
0x18001e89a  mov     rdx, r14
0x18001e89d  call    SspGetChannelBindings
0x18001e8a2  xor     r8d, r8d
0x18001e8a5  mov     ebx, eax
0x18001e8a7  test    eax, eax
0x18001e8a9  js      loc_18001FF51
0x18001e8af  lea     r8, [rbp+660h+var_658]
0x18001e8b3  mov     rdx, rdi
0x18001e8b6  call    SspGetChannelBindingsResult
0x18001e8bb  xor     r8d, r8d
0x18001e8be  mov     ebx, eax
0x18001e8c0  test    eax, eax
0x18001e8c2  js      loc_18001FF51
0x18001e8c8  cmp     [r13+8], r8
0x18001e8cc  jz      loc_18001F930
0x18001e8d2  cmp     dword ptr [r13+0], 1
0x18001e8d7  jbe     loc_18001F930
0x18001e8dd  lea     rax, [rbp+660h+var_5D0]
0x18001e8e4  mov     r8d, 18h
0x18001e8ea  lea     r9, DigestParser2Callback
0x18001e8f1  mov     [rsp+760h+ReturnLength], rax
0x18001e8f6  lea     rdx, MD5_AUTH_NAMES
0x18001e8fd  mov     rcx, r13
0x18001e900  call    DigestParse
0x18001e905  xor     r8d, r8d
0x18001e908  mov     ebx, eax
0x18001e90a  test    eax, eax
0x18001e90c  jns     short loc_18001E938
0x18001e90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e915  lea     rdx, WPP_GLOBAL_Control
0x18001e91c  cmp     rcx, rdx
0x18001e91f  jz      loc_18001E740
0x18001e925  test    byte ptr [rcx+1Ch], 1
0x18001e929  jz      loc_18001E740
0x18001e92f  lea     edx, [r8+79h]
0x18001e933  jmp     loc_18001E665
0x18001e938  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e93f  lea     rdi, WPP_GLOBAL_Control
0x18001e946  cmp     rcx, rdi
0x18001e949  jz      short loc_18001E966
0x18001e94b  test    byte ptr [rcx+1Ch], 4
0x18001e94f  jz      short loc_18001E966
0x18001e951  mov     rcx, [rcx+10h]
0x18001e955  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001e95c  mov     edx, 7Ah ; 'z'
0x18001e961  call    WPP_SF_
0x18001e966  mov     ebx, [rsp+760h+var_6E8]
0x18001e96a  cmp     ebx, 1
0x18001e96d  jbe     loc_18001ED31
0x18001e973  mov     r9b, 1
0x18001e976  lea     r8, [rbp+660h+Value]
0x18001e97a  mov     edx, 1
0x18001e97f  mov     rcx, r14
0x18001e982  call    SspGetTokenBufferByIndex
0x18001e987  xor     r8d, r8d
0x18001e98a  test    al, al
0x18001e98c  jz      loc_18001ED08
0x18001e992  mov     rbx, qword ptr [rbp+660h+Value]
0x18001e996  mov     edx, 1000h
0x18001e99b  mov     rcx, rbx
  ... truncated ...
```
