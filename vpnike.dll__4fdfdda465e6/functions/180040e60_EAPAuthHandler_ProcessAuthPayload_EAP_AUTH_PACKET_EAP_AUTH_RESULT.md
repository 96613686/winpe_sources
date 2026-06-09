# EAPAuthHandler::ProcessAuthPayload(_EAP_AUTH_PACKET_ *,_EAP_AUTH_RESULT_ * *)

- ea: `0x180040e60`
- end: `0x180041954`
- name: `?ProcessAuthPayload@EAPAuthHandler@@UEAAKPEAU_EAP_AUTH_PACKET_@@PEAPEAU_EAP_AUTH_RESULT_@@@Z`
- size: `2804`
- prototype: `__int64 __fastcall(EAPAuthHandler *this, struct _EAP_AUTH_PACKET_ *, struct _EAP_AUTH_RESULT_ **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180040e60`
- `0x180042028`
- `0x180071470`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800417f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800417f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800417e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800417e4`

## string_xrefs

- `0x1800416b1`: `ProcessAuthResult() completed with new data`

## pseudocode

```c
__int64 __fastcall EAPAuthHandler::ProcessAuthPayload(
        EAPAuthHandler *this,
        struct _EAP_AUTH_PACKET_ *a2,
        struct _EAP_AUTH_RESULT_ **a3)
{
  _BYTE *v6; // rsi
  unsigned int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int128 *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int128 *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // r15d
  __int64 v23; // r13
  char v24; // r10
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int128 *v31; // r9
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  __int128 *v38; // r9
  PVOID *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rdx
  _QWORD *v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rax
  __int64 v46; // rcx
  __int128 *v47; // r9
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  __int128 *v54; // r9
  _QWORD *v55; // rcx
  void *v56; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v58; // ebx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rcx
  _QWORD *v63; // rax
  __int64 v64; // rcx
  __int128 *v65; // r9
  _BYTE v66[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Message; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v68; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v69; // [rsp+40h] [rbp-C0h]
  __int128 v70; // [rsp+50h] [rbp-B0h]
  __int64 v71; // [rsp+60h] [rbp-A0h]
  int v72; // [rsp+68h] [rbp-98h]
  int v73; // [rsp+6Ch] [rbp-94h]
  _DWORD v74[102]; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPCSTR pszSrc; // [rsp+208h] [rbp+108h]
  __int128 v76; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v77[272]; // [rsp+230h] [rbp+130h] BYREF
  int v78; // [rsp+340h] [rbp+240h] BYREF
  __int128 v79; // [rsp+344h] [rbp+244h]
  __int128 v80; // [rsp+354h] [rbp+254h]
  int v81; // [rsp+364h] [rbp+264h]
  int v82; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v83[2044]; // [rsp+374h] [rbp+274h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_5364768e245538abba3e081d07fe101f_Traceguids);
  }
  v6 = 0;
  Message = 0;
  memset_0(v74, 0, 0x1A8u);
  memset_0(v77, 0, 0x108u);
  v66[0] = 0;
  v82 = 0;
  memset_0(v83, 0, sizeof(v83));
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v76 = 0;
  v69 = 0;
  v68 = 0;
  v70 = 0;
  v71 = 0;
  v7 = -1;
  v72 = -1;
  v73 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v68,
      L"EAPAuthHandler::ProcessAuthPayload",
      &Message,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      *((void **)this + 70));
  *a3 = 0;
  if ( a2 && (*(_DWORD *)a2 < 4u || *((unsigned __int8 *)a2 + 7) + (*((unsigned __int8 *)a2 + 6) << 8) > *(_DWORD *)a2) )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_25;
    LOWORD(v78) = 0;
    v8 = *((_QWORD *)this + 70);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v8 + 112);
      if ( v9 )
      {
        if ( *(_QWORD *)(v9 + 16) )
          v7 = *(_DWORD *)(v9 + 16);
      }
    }
    ConvertPortNoToString(&v78, v7);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_25;
    v10 = *((_QWORD *)this + 70);
    v11 = (_QWORD *)(v10 + 112);
    if ( v10 )
    {
      if ( *v11 )
        v12 = *v11 + 2686LL;
      else
        v12 = 0;
      if ( *v11 )
      {
        v13 = (__int128 *)(*v11 + 2120LL);
LABEL_24:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Bad EAP packet length received.",
          (_DWORD)v13,
          v12,
          (__int64)&v78);
LABEL_25:
        Message = 13;
        goto LABEL_155;
      }
    }
    else
    {
      v12 = 0;
    }
    v13 = &v76;
    goto LABEL_24;
  }
  if ( !*((_BYTE *)this + 568) )
  {
    Message = (*(__int64 (__fastcall **)(EAPAuthHandler *))(*(_QWORD *)this + 64LL))(this);
    if ( Message )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_155;
      LOWORD(v82) = 0;
      LOWORD(v78) = 0;
      v14 = *((_QWORD *)this + 70);
      if ( v14 )
      {
        v15 = *(_QWORD *)(v14 + 112);
        if ( v15 )
        {
          if ( *(_QWORD *)(v15 + 16) )
            v7 = *(_DWORD *)(v15 + 16);
        }
      }
      ConvertPortNoToString(&v78, v7);
      FormatRRASErrorString(&v82, L"Start() failed: %d", Message);
LABEL_34:
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_155;
      v16 = *((_QWORD *)this + 70);
      v17 = (_QWORD *)(v16 + 112);
      if ( v16 )
      {
        if ( *v17 )
          v18 = *v17 + 2686LL;
        else
          v18 = 0;
        if ( *v17 )
        {
          v19 = (__int128 *)(*v17 + 2120LL);
LABEL_43:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v82,
            (_DWORD)v19,
            v18,
            (__int64)&v78);
          goto LABEL_155;
        }
      }
      else
      {
        v18 = 0;
      }
      v19 = &v76;
      goto LABEL_43;
    }
    *((_BYTE *)this + 568) = 1;
  }
  Message = (*(__int64 (__fastcall **)(EAPAuthHandler *, struct _EAP_AUTH_RESULT_ **))(*(_QWORD *)this + 56LL))(
              this,
              a3);
  if ( Message )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_155;
    LOWORD(v82) = 0;
    LOWORD(v78) = 0;
    v20 = *((_QWORD *)this + 70);
    if ( v20 )
    {
      v21 = *(_QWORD *)(v20 + 112);
      if ( v21 )
      {
        if ( *(_QWORD *)(v21 + 16) )
          v7 = *(_DWORD *)(v21 + 16);
      }
    }
    ConvertPortNoToString(&v78, v7);
    FormatRRASErrorString(&v82, L"InitializeReplyBuffer: %d", Message);
    goto LABEL_34;
  }
  v22 = (_DWORD)a2 + 4;
  v23 = *((_QWORD *)*a3 + 1);
  while ( 1 )
  {
    memset_0(v74, 0, 0x1A8u);
    Message = EapMakeMessage(
                *((_QWORD *)this + 72),
                v22,
                (int)v23 + 4,
                *((_DWORD *)this + 146),
                (__int64)v74,
                (__int64)v6);
    v6 = 0;
    v66[0] = 0;
    if ( !pszSrc )
      goto LABEL_70;
    StringCbCopyA((STRSAFE_LPSTR)this + 661, 0x400u, pszSrc);
    v24 = byte_1800AA941;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v82) = 0;
      LOWORD(v78) = 0;
      v25 = *((_QWORD *)this + 70);
      if ( v25 && (v26 = *(_QWORD *)(v25 + 112)) != 0 && *(_QWORD *)(v26 + 16) )
        v27 = *(unsigned int *)(v26 + 16);
      else
        v27 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v78, v27);
      FormatRRASErrorString(&v82, L"EapMakeMessage() AuthReplyMessage: %S", (char *)this + 661);
      v24 = byte_1800AA941;
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v28 = *((_QWORD *)this + 70);
        v29 = (_QWORD *)(v28 + 112);
        if ( v28 )
        {
          if ( *v29 )
            v30 = *v29 + 2686LL;
          else
            v30 = 0;
          if ( *v29 )
          {
            v31 = (__int128 *)(*v29 + 2120LL);
LABEL_69:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v82,
              (_DWORD)v31,
              v30,
              (__int64)&v78);
LABEL_70:
            v24 = byte_1800AA941;
            goto LABEL_71;
          }
        }
        else
        {
          v30 = 0;
        }
        v31 = &v76;
        goto LABEL_69;
      }
    }
LABEL_71:
    if ( Message )
      break;
    if ( (v24 & 8) != 0 )
    {
      LOWORD(v82) = 0;
      LOWORD(v78) = 0;
      v32 = *((_QWORD *)this + 70);
      if ( v32 && (v33 = *(_QWORD *)(v32 + 112)) != 0 && *(_QWORD *)(v33 + 16) )
        v34 = *(unsigned int *)(v33 + 16);
      else
        v34 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v78, v34);
      FormatRRASErrorString(&v82, L"EapMakeMessage() returned action: %d", v74[0]);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v35 = *((_QWORD *)this + 70);
        v36 = (_QWORD *)(v35 + 112);
        if ( v35 )
        {
          if ( *v36 )
            v37 = *v36 + 2686LL;
          else
            v37 = 0;
          if ( *v36 )
          {
            v38 = (__int128 *)(*v36 + 2120LL);
LABEL_87:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v82,
              (_DWORD)v38,
              v37,
              (__int64)&v78);
            goto LABEL_88;
          }
        }
        else
        {
          v37 = 0;
        }
        v38 = &v76;
        goto LABEL_87;
      }
    }
LABEL_88:
    if ( !v74[0] )
      goto LABEL_118;
    if ( v74[0] != 1 )
    {
      if ( v74[0] != 2 && v74[0] != 3 && (unsigned int)(v74[0] - 4) >= 2 )
      {
        v39 = (PVOID *)WPP_GLOBAL_Control;
LABEL_94:
        if ( v39 != &WPP_GLOBAL_Control && (*((_BYTE *)v39 + 28) & 1) != 0 && *((_BYTE *)v39 + 25) >= 5u )
          WPP_SF_(v39[2], 20, WPP_5364768e245538abba3e081d07fe101f_Traceguids);
        Message = (*(__int64 (__fastcall **)(EAPAuthHandler *, _DWORD *, _BYTE *, _BYTE *))(*(_QWORD *)this + 80LL))(
                    this,
                    v74,
                    v77,
                    v66);
        if ( Message )
        {
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_154;
          LOWORD(v82) = 0;
          LOWORD(v78) = 0;
          v48 = *((_QWORD *)this + 70);
          if ( v48 && (v49 = *(_QWORD *)(v48 + 112)) != 0 && *(_QWORD *)(v49 + 16) )
            v50 = *(unsigned int *)(v49 + 16);
          else
            v50 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v78, v50);
          FormatRRASErrorString(&v82, L"ProcessAuthResult() failed: %d", Message);
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_154;
          v51 = *((_QWORD *)this + 70);
          v52 = (_QWORD *)(v51 + 112);
          if ( v51 )
          {
            if ( *v52 )
              v53 = *v52 + 2686LL;
            else
              v53 = 0;
            if ( *v52 )
            {
              v54 = (__int128 *)(*v52 + 2120LL);
LABEL_153:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v82,
                (_DWORD)v54,
                v53,
                (__int64)&v78);
              goto LABEL_154;
            }
          }
          else
          {
            v53 = 0;
          }
          v54 = &v76;
          goto LABEL_153;
        }
        if ( !v66[0] )
          goto LABEL_155;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v78) = 0;
          v40 = *((_QWORD *)this + 70);
          if ( v40 && (v41 = *(_QWORD *)(v40 + 112)) != 0 && *(_QWORD *)(v41 + 16) )
            v42 = *(unsigned int *)(v41 + 16);
          else
            v42 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v78, v42);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v44 = *((_QWORD *)this + 70);
            v45 = (_QWORD *)(v44 + 112);
            if ( v44 )
            {
              if ( *v45 )
                v46 = *v45 + 2686LL;
              else
                v46 = 0;
              if ( *v45 )
              {
                v47 = (__int128 *)(*v45 + 2120LL);
                goto LABEL_136;
              }
            }
            else
            {
              v46 = 0;
            }
            v47 = &v76;
LABEL_136:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)L"ProcessAuthResult() completed with new data",
              (_DWORD)v47,
              v46,
              (__int64)&v78);
          }
        }
        v6 = v77;
        v22 = 0;
        goto LABEL_154;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_5364768e245538abba3e081d07fe101f_Traceguids);
      }
      **((_DWORD **)*a3 + 1) = *(unsigned __int8 *)(v23 + 7) + (*(unsigned __int8 *)(v23 + 6) << 8);
      v43 = *a3;
      if ( v74[0] != 2 )
      {
        *(_DWORD *)v43 = 2;
        goto LABEL_154;
      }
      *(_DWORD *)v43 = 3;
    }
    v39 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5364768e245538abba3e081d07fe101f_Traceguids);
      v39 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v74[0] == 1 )
    {
      *(_DWORD *)*a3 = 1;
LABEL_118:
      v39 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v39 != &WPP_GLOBAL_Control && (*((_BYTE *)v39 + 28) & 1) != 0 && *((_BYTE *)v39 + 25) >= 5u )
    {
      WPP_SF_(v39[2], 19, WPP_5364768e245538abba3e081d07fe101f_Traceguids);
      v39 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v74[0] || v74[82] )
      goto LABEL_94;
    *(_DWORD *)*a3 = 0;
    Message = 691;
LABEL_154:
    if ( !v66[0] )
      goto LABEL_155;
  }
  if ( (v24 & 4) != 0 )
  {
    LOWORD(v82) = 0;
    LOWORD(v78) = 0;
    v60 = *((_QWORD *)this + 70);
    if ( v60 )
    {
      v61 = *(_QWORD *)(v60 + 112);
      if ( v61 )
      {
        if ( *(_QWORD *)(v61 + 16) )
          v7 = *(_DWORD *)(v61 + 16);
      }
    }
    ConvertPortNoToString(&v78, v7);
    FormatRRASErrorString(&v82, L"EapMakeMessage() failed: %d", Message);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v62 = *((_QWORD *)this + 70);
      v63 = (_QWORD *)(v62 + 112);
      if ( v62 )
      {
        if ( *v63 )
          v64 = *v63 + 2686LL;
        else
          v64 = 0;
        if ( *v63 )
        {
          v65 = (__int128 *)(*v63 + 2120LL);
          goto LABEL_179;
        }
      }
      else
      {
        v64 = 0;
      }
      v65 = &v76;
LABEL_179:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v82,
        (_DWORD)v65,
        v64,
        (__int64)&v78);
    }
  }
LABEL_155:
  v55 = *a3;
  if ( *a3 && (unsigned int)(*(_DWORD *)v55 - 2) > 1 )
  {
    v56 = (void *)v55[1];
    if ( v56 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v56);
      *((_QWORD *)*a3 + 1) = 0;
    }
    *((_QWORD *)*a3 + 1) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_5364768e245538abba3e081d07fe101f_Traceguids, Message);
  }
  v58 = Message;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v68);
  return v58;
}

```

## disassembly

```asm
0x180040e60  mov     [rsp-8+arg_18], rbx
0x180040e65  push    rbp
0x180040e66  push    rsi
0x180040e67  push    rdi
0x180040e68  push    r12
0x180040e6a  push    r13
0x180040e6c  push    r14
0x180040e6e  push    r15
0x180040e70  lea     rbp, [rsp-0A80h]
0x180040e78  sub     rsp, 0B80h
0x180040e7f  mov     rax, cs:__security_cookie
0x180040e86  xor     rax, rsp
0x180040e89  mov     [rbp+0AB0h+var_40], rax
0x180040e90  mov     r12, r8
0x180040e93  mov     rdi, rdx
0x180040e96  mov     rbx, rcx
0x180040e99  lea     r15, WPP_GLOBAL_Control
0x180040ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ea7  cmp     rcx, r15
0x180040eaa  jz      short loc_180040ECD
0x180040eac  test    byte ptr [rcx+1Ch], 1
0x180040eb0  jz      short loc_180040ECD
0x180040eb2  cmp     byte ptr [rcx+19h], 6
0x180040eb6  jb      short loc_180040ECD
0x180040eb8  mov     edx, 10h
0x180040ebd  lea     r8, WPP_5364768e245538abba3e081d07fe101f_Traceguids
0x180040ec4  mov     rcx, [rcx+10h]
0x180040ec8  call    WPP_SF_
0x180040ecd  xor     esi, esi
0x180040ecf  mov     [rsp+0BB0h+var_B7C], esi
0x180040ed3  xor     edx, edx; Val
0x180040ed5  mov     r8d, 1A8h; Size
0x180040edb  lea     rcx, [rsp+0BB0h+var_B40]; void *
0x180040ee0  call    memset_0
0x180040ee5  xor     edx, edx; Val
0x180040ee7  mov     r8d, 108h; Size
0x180040eed  lea     rcx, [rbp+0AB0h+var_980]; void *
0x180040ef4  call    memset_0
0x180040ef9  mov     [rsp+0BB0h+var_B80], sil
0x180040efe  mov     [rbp+0AB0h+var_840], esi
0x180040f04  xor     edx, edx; Val
0x180040f06  mov     r8d, 7FCh; Size
0x180040f0c  lea     rcx, [rbp+0AB0h+var_83C]; void *
0x180040f13  call    memset_0
0x180040f18  mov     [rbp+0AB0h+var_870], esi
0x180040f1e  xorps   xmm0, xmm0
0x180040f21  xor     eax, eax
0x180040f23  movups  [rbp+0AB0h+var_86C], xmm0
0x180040f2a  movups  [rbp+0AB0h+var_85C], xmm0
0x180040f31  mov     [rbp+0AB0h+var_84C], eax
0x180040f37  movups  [rbp+0AB0h+var_990], xmm0
0x180040f3e  xorps   xmm1, xmm1
0x180040f41  movdqu  [rsp+0BB0h+var_B70], xmm1
0x180040f47  mov     [rsp+0BB0h+var_B78], rsi
0x180040f4c  movdqu  [rsp+0BB0h+var_B60], xmm0
0x180040f52  mov     [rsp+0BB0h+var_B50], rsi
0x180040f57  or      r14d, 0FFFFFFFFh
0x180040f5b  mov     [rsp+0BB0h+var_B48], r14d
0x180040f60  mov     [rsp+0BB0h+var_B44], esi
0x180040f64  test    cs:byte_1800AA941, 8
0x180040f6b  jz      short loc_180040F96
0x180040f6d  mov     rax, [rbx+230h]
0x180040f74  mov     [rsp+0BB0h+var_B90], rax; void *
0x180040f79  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180040f80  lea     r8, [rsp+0BB0h+var_B7C]; unsigned int *
0x180040f85  lea     rdx, aEapauthhandler_0; "EAPAuthHandler::ProcessAuthPayload"
0x180040f8c  lea     rcx, [rsp+0BB0h+var_B78]; this
0x180040f91  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180040f96  mov     [r12], rsi
0x180040f9a  test    rdi, rdi
0x180040f9d  jz      loc_180041084
0x180040fa3  cmp     dword ptr [rdi], 4
0x180040fa6  jb      short loc_180040FBD
0x180040fa8  movzx   ecx, byte ptr [rdi+6]
0x180040fac  shl     ecx, 8
0x180040faf  movzx   eax, byte ptr [rdi+7]
0x180040fb3  add     ecx, eax
0x180040fb5  cmp     ecx, [rdi]
0x180040fb7  jbe     loc_180041084
0x180040fbd  test    cs:byte_1800AA941, 4
0x180040fc4  jz      loc_180041077
0x180040fca  mov     word ptr [rbp+0AB0h+var_870], si
0x180040fd1  mov     rax, [rbx+230h]
0x180040fd8  test    rax, rax
0x180040fdb  jz      short loc_180040FF0
0x180040fdd  mov     rax, [rax+70h]
0x180040fe1  test    rax, rax
0x180040fe4  jz      short loc_180040FF0
0x180040fe6  cmp     [rax+10h], rsi
0x180040fea  jz      short loc_180040FF0
0x180040fec  mov     r14d, [rax+10h]
0x180040ff0  mov     edx, r14d
0x180040ff3  lea     rcx, [rbp+0AB0h+var_870]
0x180040ffa  call    ConvertPortNoToString
0x180040fff  test    cs:byte_1800AA941, 4
0x180041006  jz      short loc_180041077
0x180041008  mov     rcx, [rbx+230h]
0x18004100f  lea     rax, [rcx+70h]
0x180041013  test    rcx, rcx
0x180041016  jz      short loc_180041042
0x180041018  mov     rdx, [rax]
0x18004101b  test    rdx, rdx
0x18004101e  jz      short loc_180041029
0x180041020  lea     rcx, [rdx+0A7Eh]
0x180041027  jmp     short loc_180041031
0x180041029  test    rcx, rcx
0x18004102c  jz      short loc_180041042
0x18004102e  mov     rcx, rsi
0x180041031  mov     rdx, [rax]
0x180041034  test    rdx, rdx
0x180041037  jz      short loc_180041045
0x180041039  lea     r9, [rdx+848h]
0x180041040  jmp     short loc_18004104C
0x180041042  mov     rcx, rsi
0x180041045  lea     r9, [rbp+0AB0h+var_990]
0x18004104c  lea     rax, [rbp+0AB0h+var_870]
0x180041053  mov     [rsp+0BB0h+var_B88], rax
0x180041058  mov     [rsp+0BB0h+var_B90], rcx
0x18004105d  lea     r8, aBadEapPacketLe; "Bad EAP packet length received."
0x180041064  lea     rdx, RasVpnIkeParamTraceError
0x18004106b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041072  call    McTemplateU0zjzz_EventWriteTransfer
0x180041077  mov     [rsp+0BB0h+var_B7C], 0Dh
0x18004107f  jmp     loc_1800417C8
0x180041084  cmp     [rbx+238h], sil
0x18004108b  jnz     loc_180041195
0x180041091  mov     rax, [rbx]
0x180041094  mov     rcx, rbx
0x180041097  mov     rax, [rax+40h]
0x18004109b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410a0  mov     [rsp+0BB0h+var_B7C], eax
0x1800410a4  test    eax, eax
0x1800410a6  jz      loc_18004118E
0x1800410ac  test    cs:byte_1800AA941, 4
0x1800410b3  jz      loc_1800417C8
0x1800410b9  mov     word ptr [rbp+0AB0h+var_840], si
0x1800410c0  mov     word ptr [rbp+0AB0h+var_870], si
0x1800410c7  mov     rax, [rbx+230h]
0x1800410ce  test    rax, rax
0x1800410d1  jz      short loc_1800410E6
0x1800410d3  mov     rax, [rax+70h]
0x1800410d7  test    rax, rax
0x1800410da  jz      short loc_1800410E6
0x1800410dc  cmp     [rax+10h], rsi
0x1800410e0  jz      short loc_1800410E6
0x1800410e2  mov     r14d, [rax+10h]
0x1800410e6  mov     edx, r14d
0x1800410e9  lea     rcx, [rbp+0AB0h+var_870]
0x1800410f0  call    ConvertPortNoToString
0x1800410f5  lea     rdx, aStartFailedD; "Start() failed: %d"
0x1800410fc  mov     r8d, [rsp+0BB0h+var_B7C]
0x180041101  lea     rcx, [rbp+0AB0h+var_840]
0x180041108  call    FormatRRASErrorString
0x18004110d  test    cs:byte_1800AA941, 4
0x180041114  jz      loc_1800417C8
0x18004111a  mov     rcx, [rbx+230h]
0x180041121  lea     rax, [rcx+70h]
0x180041125  test    rcx, rcx
0x180041128  jz      short loc_180041154
0x18004112a  mov     rdx, [rax]
0x18004112d  test    rdx, rdx
0x180041130  jz      short loc_18004113B
0x180041132  lea     rcx, [rdx+0A7Eh]
0x180041139  jmp     short loc_180041143
0x18004113b  test    rcx, rcx
0x18004113e  jz      short loc_180041154
0x180041140  mov     rcx, rsi
0x180041143  mov     rdx, [rax]
0x180041146  test    rdx, rdx
0x180041149  jz      short loc_180041157
0x18004114b  lea     r9, [rdx+848h]
0x180041152  jmp     short loc_18004115E
0x180041154  mov     rcx, rsi
0x180041157  lea     r9, [rbp+0AB0h+var_990]
0x18004115e  lea     rax, [rbp+0AB0h+var_870]
0x180041165  mov     [rsp+0BB0h+var_B88], rax
0x18004116a  mov     [rsp+0BB0h+var_B90], rcx
0x18004116f  lea     r8, [rbp+0AB0h+var_840]
0x180041176  lea     rdx, RasVpnIkeParamTraceError
0x18004117d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041184  call    McTemplateU0zjzz_EventWriteTransfer
0x180041189  jmp     loc_1800417C8
0x18004118e  mov     byte ptr [rbx+238h], 1
0x180041195  mov     rax, [rbx]
0x180041198  mov     rdx, r12
0x18004119b  mov     rcx, rbx
0x18004119e  mov     rax, [rax+38h]
0x1800411a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411a7  mov     [rsp+0BB0h+var_B7C], eax
0x1800411ab  test    eax, eax
0x1800411ad  jz      short loc_180041204
0x1800411af  test    cs:byte_1800AA941, 4
0x1800411b6  jz      loc_1800417C8
0x1800411bc  mov     word ptr [rbp+0AB0h+var_840], si
0x1800411c3  mov     word ptr [rbp+0AB0h+var_870], si
0x1800411ca  mov     rax, [rbx+230h]
0x1800411d1  test    rax, rax
0x1800411d4  jz      short loc_1800411E9
0x1800411d6  mov     rax, [rax+70h]
0x1800411da  test    rax, rax
0x1800411dd  jz      short loc_1800411E9
0x1800411df  cmp     [rax+10h], rsi
0x1800411e3  jz      short loc_1800411E9
0x1800411e5  mov     r14d, [rax+10h]
0x1800411e9  mov     edx, r14d
0x1800411ec  lea     rcx, [rbp+0AB0h+var_870]
0x1800411f3  call    ConvertPortNoToString
0x1800411f8  lea     rdx, aInitializerepl; "InitializeReplyBuffer: %d"
0x1800411ff  jmp     loc_1800410FC
0x180041204  lea     r15, [rdi+4]
0x180041208  mov     rax, [r12]
0x18004120c  mov     r13, [rax+8]
0x180041210  xor     edx, edx; Val
0x180041212  mov     r8d, 1A8h; Size
0x180041218  lea     rcx, [rsp+0BB0h+var_B40]; void *
0x18004121d  call    memset_0
0x180041222  mov     [rsp+0BB0h+var_B88], rsi
0x180041227  lea     rax, [rsp+0BB0h+var_B40]
0x18004122c  mov     [rsp+0BB0h+var_B90], rax
0x180041231  mov     r9d, [rbx+248h]
0x180041238  lea     r8, [r13+4]
0x18004123c  mov     rdx, r15
0x18004123f  mov     rcx, [rbx+240h]
0x180041246  call    EapMakeMessage
0x18004124b  mov     [rsp+0BB0h+var_B7C], eax
0x18004124f  xor     esi, esi
0x180041251  mov     [rsp+0BB0h+var_B80], sil
0x180041256  mov     r8, [rbp+0AB0h+pszSrc]; pszSrc
0x18004125d  test    r8, r8
0x180041260  jz      loc_18004135A
0x180041266  lea     rdi, [rbx+295h]
0x18004126d  mov     edx, 400h; cbDest
0x180041272  mov     rcx, rdi; pszDest
0x180041275  call    StringCbCopyA
0x18004127a  mov     r10b, cs:byte_1800AA941
0x180041281  test    r10b, 8
0x180041285  jz      loc_180041361
0x18004128b  mov     word ptr [rbp+0AB0h+var_840], si
0x180041292  mov     word ptr [rbp+0AB0h+var_870], si
0x180041299  mov     rax, [rbx+230h]
0x1800412a0  test    rax, rax
0x1800412a3  jz      short loc_1800412B9
0x1800412a5  mov     rax, [rax+70h]
0x1800412a9  test    rax, rax
0x1800412ac  jz      short loc_1800412B9
0x1800412ae  cmp     [rax+10h], rsi
0x1800412b2  jz      short loc_1800412B9
0x1800412b4  mov     edx, [rax+10h]
0x1800412b7  jmp     short loc_1800412BC
0x1800412b9  mov     edx, r14d
0x1800412bc  lea     rcx, [rbp+0AB0h+var_870]
0x1800412c3  call    ConvertPortNoToString
0x1800412c8  mov     r8, rdi
0x1800412cb  lea     rdx, aEapmakemessage_1; "EapMakeMessage() AuthReplyMessage: %S"
0x1800412d2  lea     rcx, [rbp+0AB0h+var_840]
0x1800412d9  call    FormatRRASErrorString
0x1800412de  mov     r10b, cs:byte_1800AA941
0x1800412e5  test    r10b, 8
0x1800412e9  jz      short loc_180041361
0x1800412eb  mov     rcx, [rbx+230h]
0x1800412f2  lea     rax, [rcx+70h]
0x1800412f6  test    rcx, rcx
0x1800412f9  jz      short loc_180041325
0x1800412fb  mov     rdx, [rax]
0x1800412fe  test    rdx, rdx
0x180041301  jz      short loc_18004130C
0x180041303  lea     rcx, [rdx+0A7Eh]
0x18004130a  jmp     short loc_180041314
0x18004130c  test    rcx, rcx
0x18004130f  jz      short loc_180041325
0x180041311  mov     rcx, rsi
0x180041314  mov     rdx, [rax]
0x180041317  test    rdx, rdx
0x18004131a  jz      short loc_180041328
0x18004131c  lea     r9, [rdx+848h]
0x180041323  jmp     short loc_18004132F
0x180041325  mov     rcx, rsi
0x180041328  lea     r9, [rbp+0AB0h+var_990]
0x18004132f  lea     rax, [rbp+0AB0h+var_870]
0x180041336  mov     [rsp+0BB0h+var_B88], rax
0x18004133b  mov     [rsp+0BB0h+var_B90], rcx
0x180041340  lea     r8, [rbp+0AB0h+var_840]
0x180041347  lea     rdx, RasVpnIkeParamTraceInfo
0x18004134e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041355  call    McTemplateU0zjzz_EventWriteTransfer
0x18004135a  mov     r10b, cs:byte_1800AA941
0x180041361  cmp     [rsp+0BB0h+var_B7C], esi
0x180041365  jnz     loc_180041874
0x18004136b  test    r10b, 8
0x18004136f  jz      loc_180041442
0x180041375  mov     word ptr [rbp+0AB0h+var_840], si
0x18004137c  mov     word ptr [rbp+0AB0h+var_870], si
0x180041383  mov     rax, [rbx+230h]
0x18004138a  test    rax, rax
0x18004138d  jz      short loc_1800413A3
0x18004138f  mov     rax, [rax+70h]
0x180041393  test    rax, rax
0x180041396  jz      short loc_1800413A3
0x180041398  cmp     [rax+10h], rsi
0x18004139c  jz      short loc_1800413A3
  ... truncated ...
```
