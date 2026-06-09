# ClientBFEHandler::ProcessCPRequest(_CONFIGURATION_PAYLOAD_ * *)

- ea: `0x1800380cc`
- end: `0x1800389dd`
- name: `?ProcessCPRequest@ClientBFEHandler@@IEAAKPEAPEAU_CONFIGURATION_PAYLOAD_@@@Z`
- size: `2321`
- prototype: `__int64 __fastcall(void **this, struct _CONFIGURATION_PAYLOAD_ **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800367e0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x1800310b8`
- `0x1800380cc`
- `0x180039fa8`
- `0x18004b20c`
- `0x18004fca8`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003883d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038861`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003883d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038861`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003831f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003831f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003830e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003882f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003830e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003882f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038853`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::ProcessCPRequest(void **this, struct _CONFIGURATION_PAYLOAD_ **a2)
{
  PVOID *v4; // rbx
  unsigned int v5; // r13d
  char v6; // al
  unsigned int v7; // edi
  _QWORD *v8; // rax
  __int64 v9; // rax
  char *v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int128 *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r9
  PVOID v16; // rcx
  HANDLE ProcessHeap; // rax
  struct _CONFIGURATION_PAYLOAD_ *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  PVOID *v22; // rcx
  char v23; // bl
  _DWORD *v24; // rcx
  unsigned int v25; // eax
  PVOID *v26; // rdx
  __int64 v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  char *v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  __int128 *v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  unsigned int v42; // eax
  PVOID *v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  _QWORD *v48; // rdi
  HANDLE v49; // rax
  _QWORD *v50; // rbx
  HANDLE v51; // rax
  _QWORD *v52; // rax
  __int64 v53; // rax
  char *v54; // rcx
  _QWORD *v55; // rax
  __int64 v56; // rcx
  __int128 *v57; // r9
  unsigned int v59; // [rsp+30h] [rbp-D0h] BYREF
  char v60; // [rsp+34h] [rbp-CCh]
  LPVOID *v61; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v62[17]; // [rsp+40h] [rbp-C0h] BYREF
  char v63; // [rsp+51h] [rbp-AFh]
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v65; // [rsp+60h] [rbp-A0h]
  __int128 v66; // [rsp+70h] [rbp-90h]
  __int64 v67; // [rsp+80h] [rbp-80h]
  int v68; // [rsp+88h] [rbp-78h]
  int v69; // [rsp+8Ch] [rbp-74h]
  __int128 v70; // [rsp+90h] [rbp-70h] BYREF
  int v71; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v72; // [rsp+A4h] [rbp-5Ch]
  __int128 v73; // [rsp+B4h] [rbp-4Ch]
  int v74; // [rsp+C4h] [rbp-3Ch]
  int v75; // [rsp+D0h] [rbp-30h] BYREF
  char v76[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v59 = 0;
  v75 = 0;
  memset_0(v76, 0, sizeof(v76));
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v70 = 0;
  v65 = 0;
  v64 = 0;
  v66 = 0;
  v67 = 0;
  v5 = -1;
  v68 = -1;
  v69 = 0;
  v6 = byte_1800AA941;
  v7 = 8;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v64,
      L"ClientBFEHandler::ProcessCPRequest",
      &v59,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v6 = byte_1800AA941;
  }
  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v18 = (struct _CONFIGURATION_PAYLOAD_ *)HeapAlloc(ProcessHeap, 8u, 0x10u);
    *a2 = v18;
    if ( !v18 )
    {
      v59 = 8;
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_147;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 8);
        v7 = v59;
        v22 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 1) == 0 || *((_BYTE *)v22 + 25) < 6u )
        goto LABEL_147;
      v14 = 20;
      v15 = v7;
LABEL_144:
      v16 = v22[2];
      goto LABEL_145;
    }
    v23 = 0;
    v60 = 0;
    *(_DWORD *)v18 = 1;
    v61 = (LPVOID *)((char *)*a2 + 8);
    if ( (VPNIKEProtocolEngine::AvailableIPProtocols & 1) == 0
      || !IPv4Helper::DoNegotiate(*((IPv4Helper **)this[6] + 4), v19, v20, v21) )
    {
      goto LABEL_80;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
    }
    v24 = (_DWORD *)*((_QWORD *)this[6] + 4);
    if ( *v24 )
    {
      v25 = ClientBFEHandler::AddNewAttributeTLV((__int64)v24, v19, &v61, 1, 4u, *((void **)this[6] + 4));
      v59 = v25;
      if ( v25 )
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
        v26 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_60;
        }
        v27 = 22;
        goto LABEL_58;
      }
    }
    else
    {
      v25 = ClientBFEHandler::AddNewAttributeTLV((__int64)v24, v19, &v61, 1, 0, 0);
      v59 = v25;
      if ( v25 )
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
        v26 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_60;
        }
        v27 = 23;
LABEL_58:
        WPP_SF_d(v22[2], v27, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v25);
      }
    }
    v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_60:
    if ( v59 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
        goto LABEL_62;
      goto LABEL_106;
    }
    v23 = 1;
    v60 = 1;
    v35 = *((_QWORD *)this[6] + 14);
    if ( *(_DWORD *)(v35 + 4252) == 1 )
      ClientBFEHandler::AddNewAttributeTLV(v35, (__int64)v26, &v61, 20, 0, 0);
    ClientBFEHandler::AddNewAttributeTLV(v35, (__int64)v26, &v61, 3, 0, 0);
    ClientBFEHandler::AddNewAttributeTLV(v37, v36, &v61, 4, 0, 0);
    ClientBFEHandler::AddNewAttributeTLV(v39, v38, &v61, 23456, 0, 0);
LABEL_80:
    if ( (VPNIKEProtocolEngine::AvailableIPProtocols & 2) == 0
      || !IPv6Helper::DoNegotiate(*((IPv6Helper **)this[6] + 5), v19, v20, v21) )
    {
      goto LABEL_105;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
    }
    if ( IN6_IS_ADDR_UNSPECIFIED(*((const IN6_ADDR **)this[6] + 5)) )
    {
      v42 = ClientBFEHandler::AddNewAttributeTLV(v41, v40, &v61, 8, 0, 0);
      v59 = v42;
      if ( v42 )
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
        v43 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v44 = 26;
          goto LABEL_97;
        }
LABEL_99:
        if ( !v59 )
        {
          v23 = 1;
          v60 = 1;
          v45 = *((_QWORD *)this[6] + 14);
          if ( *(_DWORD *)(v45 + 4252) == 1 )
            ClientBFEHandler::AddNewAttributeTLV(v45, (__int64)v43, &v61, 21, 0, 0);
          ClientBFEHandler::AddNewAttributeTLV(v45, (__int64)v43, &v61, 10, 0, 0);
          ClientBFEHandler::AddNewAttributeTLV(v47, v46, &v61, 23457, 0, 0);
          goto LABEL_105;
        }
        if ( (byte_1800AA941 & 4) != 0 )
        {
LABEL_62:
          LOWORD(v75) = 0;
          LOWORD(v71) = 0;
          v28 = this[6];
          if ( v28 && (v29 = v28[14]) != 0 && *(_QWORD *)(v29 + 16) )
            v30 = *(unsigned int *)(v29 + 16);
          else
            v30 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v71, v30);
          FormatRRASErrorString(&v75, L"AddNewAttributeTLV failure %d", v59);
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_105;
          v31 = (char *)this[6];
          v32 = v31 + 112;
          if ( v31 )
          {
            if ( *v32 )
              v33 = *v32 + 2686LL;
            else
              v33 = 0;
            if ( *v32 )
            {
              v34 = (__int128 *)(*v32 + 2120LL);
LABEL_76:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v75,
                (_DWORD)v34,
                v33,
                (__int64)&v71);
LABEL_105:
              v22 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_106;
            }
          }
          else
          {
            v33 = 0;
          }
          v34 = &v70;
          goto LABEL_76;
        }
LABEL_106:
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 && *((_BYTE *)v22 + 25) >= 5u )
        {
          LOBYTE(v21) = v23 != 0;
          WPP_SF_c(v22[2], 27, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v21);
          v22 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v59 && v23 )
          goto LABEL_140;
        while ( 1 )
        {
          v50 = *a2;
          if ( !*((_QWORD *)*a2 + 1) )
            break;
          v48 = (_QWORD *)v50[1];
          v50[1] = *v48;
          if ( v48 )
          {
            v49 = GetProcessHeap();
            HeapFree(v49, 0, v48);
          }
        }
        if ( v50 )
        {
          v51 = GetProcessHeap();
          HeapFree(v51, 0, v50);
        }
        *a2 = 0;
        if ( v60 )
        {
LABEL_139:
          v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_140:
          if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 1) == 0 || *((_BYTE *)v22 + 25) < 6u )
            goto LABEL_146;
          v14 = 29;
          v15 = v59;
          goto LABEL_144;
        }
        v59 = 87;
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_135:
          v22 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_146:
            v7 = v59;
            goto LABEL_147;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v59);
            v22 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_140;
        }
        LOWORD(v71) = 0;
        v52 = this[6];
        if ( v52 )
        {
          v53 = v52[14];
          if ( v53 )
          {
            if ( *(_QWORD *)(v53 + 16) )
              v5 = *(_DWORD *)(v53 + 16);
          }
        }
        ConvertPortNoToString(&v71, v5);
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_134:
          if ( v59 )
            goto LABEL_135;
          goto LABEL_139;
        }
        v54 = (char *)this[6];
        v55 = v54 + 112;
        if ( v54 )
        {
          if ( *v55 )
            v56 = *v55 + 2686LL;
          else
            v56 = 0;
          if ( *v55 )
          {
            v57 = (__int128 *)(*v55 + 2120LL);
LABEL_133:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)L"Invalid param neither ipv4 or ipv6 is being negotiated ",
              (_DWORD)v57,
              v56,
              (__int64)&v71);
            goto LABEL_134;
          }
        }
        else
        {
          v56 = 0;
        }
        v57 = &v70;
        goto LABEL_133;
      }
    }
    else
    {
      *(_OWORD *)&v62[1] = 0;
      v63 = 0;
      *(_OWORD *)v62 = *(_OWORD *)v41;
      v62[16] = *(_BYTE *)(v41 + 48);
      v42 = ClientBFEHandler::AddNewAttributeTLV(v41, v40, &v61, 8, 0x11u, v62);
      v59 = v42;
      if ( v42 )
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
        v43 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v44 = 25;
LABEL_97:
          WPP_SF_d(v22[2], v44, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v42);
          goto LABEL_98;
        }
        goto LABEL_99;
      }
    }
LABEL_98:
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_99;
  }
  v7 = 87;
  v59 = 87;
  if ( (v6 & 4) == 0 )
  {
LABEL_24:
    if ( v4 == &WPP_GLOBAL_Control )
      goto LABEL_147;
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      WPP_SF_d(v4[2], 17, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v7);
      v7 = v59;
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_28;
  }
  LOWORD(v71) = 0;
  v8 = this[6];
  if ( v8 )
  {
    v9 = v8[14];
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 16) )
        v5 = *(_DWORD *)(v9 + 16);
    }
  }
  ConvertPortNoToString(&v71, v5);
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v10 = (char *)this[6];
    v11 = v10 + 112;
    if ( v10 )
    {
      if ( *v11 )
        v12 = *v11 + 2686LL;
      else
        v12 = 0;
      if ( *v11 )
      {
        v13 = (__int128 *)(*v11 + 2120LL);
LABEL_22:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid param",
          (_DWORD)v13,
          v12,
          (__int64)&v71);
        goto LABEL_23;
      }
    }
    else
    {
      v12 = 0;
    }
    v13 = &v70;
    goto LABEL_22;
  }
LABEL_23:
  v7 = v59;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( v59 )
    goto LABEL_24;
LABEL_28:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v14 = 18;
    v15 = v7;
    v16 = v4[2];
LABEL_145:
    WPP_SF_d(v16, v14, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v15);
    goto LABEL_146;
  }
LABEL_147:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v64);
  return v7;
}

```

## disassembly

```asm
0x1800380cc  mov     [rsp-8+arg_10], rbx
0x1800380d1  push    rbp
0x1800380d2  push    rsi
0x1800380d3  push    rdi
0x1800380d4  push    r12
0x1800380d6  push    r13
0x1800380d8  lea     rbp, [rsp-7E0h]
0x1800380e0  sub     rsp, 8E0h
0x1800380e7  mov     rax, cs:__security_cookie
0x1800380ee  xor     rax, rsp
0x1800380f1  mov     [rbp+800h+var_30], rax
0x1800380f8  mov     r12, rdx
0x1800380fb  mov     rsi, rcx
0x1800380fe  lea     rax, WPP_GLOBAL_Control
0x180038105  mov     rbx, cs:WPP_GLOBAL_Control
0x18003810c  cmp     rbx, rax
0x18003810f  jz      short loc_180038139
0x180038111  test    byte ptr [rbx+1Ch], 1
0x180038115  jz      short loc_180038139
0x180038117  cmp     byte ptr [rbx+19h], 6
0x18003811b  jb      short loc_180038139
0x18003811d  mov     edx, 10h
0x180038122  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180038129  mov     rcx, [rbx+10h]
0x18003812d  call    WPP_SF_
0x180038132  mov     rbx, cs:WPP_GLOBAL_Control
0x180038139  mov     [rsp+900h+var_8D0], 0
0x180038141  xor     eax, eax
0x180038143  mov     [rbp+800h+var_830], eax
0x180038146  xor     edx, edx; Val
0x180038148  mov     r8d, 7FCh; Size
0x18003814e  lea     rcx, [rbp+800h+var_82C]; void *
0x180038152  call    memset_0
0x180038157  xor     eax, eax
0x180038159  mov     [rbp+800h+var_860], eax
0x18003815c  xorps   xmm0, xmm0
0x18003815f  movups  [rbp+800h+var_85C], xmm0
0x180038163  movups  [rbp+800h+var_84C], xmm0
0x180038167  mov     [rbp+800h+var_83C], eax
0x18003816a  movups  [rbp+800h+var_870], xmm0
0x18003816e  xorps   xmm1, xmm1
0x180038171  movdqu  [rsp+900h+var_8A0], xmm1
0x180038177  mov     [rsp+900h+var_8A8], rax
0x18003817c  movdqu  [rsp+900h+var_890], xmm0
0x180038182  mov     [rbp+800h+var_880], rax
0x180038186  or      r13d, 0FFFFFFFFh
0x18003818a  mov     [rbp+800h+var_878], r13d
0x18003818e  mov     [rbp+800h+var_874], eax
0x180038191  mov     al, cs:byte_1800AA941
0x180038197  mov     edi, 8
0x18003819c  test    dil, al
0x18003819f  jz      short loc_1800381D4
0x1800381a1  mov     rax, [rsi+30h]
0x1800381a5  mov     [rsp+900h+var_8E0], rax; void *
0x1800381aa  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800381b1  lea     r8, [rsp+900h+var_8D0]; unsigned int *
0x1800381b6  lea     rdx, aClientbfehandl_2; "ClientBFEHandler::ProcessCPRequest"
0x1800381bd  lea     rcx, [rsp+900h+var_8A8]; this
0x1800381c2  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800381c7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800381ce  mov     al, cs:byte_1800AA941
0x1800381d4  test    r12, r12
0x1800381d7  jnz     loc_18003830E
0x1800381dd  lea     edi, [r12+57h]
0x1800381e2  mov     [rsp+900h+var_8D0], edi
0x1800381e6  test    al, 4
0x1800381e8  jz      loc_1800382A1
0x1800381ee  xor     eax, eax
0x1800381f0  mov     word ptr [rbp+800h+var_860], ax
0x1800381f4  mov     rax, [rsi+30h]
0x1800381f8  test    rax, rax
0x1800381fb  jz      short loc_180038210
0x1800381fd  mov     rax, [rax+70h]
0x180038201  test    rax, rax
0x180038204  jz      short loc_180038210
0x180038206  cmp     [rax+10h], r12
0x18003820a  jz      short loc_180038210
0x18003820c  mov     r13d, [rax+10h]
0x180038210  mov     edx, r13d
0x180038213  lea     rcx, [rbp+800h+var_860]
0x180038217  call    ConvertPortNoToString
0x18003821c  test    cs:byte_1800AA941, 4
0x180038223  jz      short loc_180038289
0x180038225  mov     rcx, [rsi+30h]
0x180038229  lea     rax, [rcx+70h]
0x18003822d  test    rcx, rcx
0x180038230  jz      short loc_18003825B
0x180038232  mov     rdx, [rax]
0x180038235  test    rdx, rdx
0x180038238  jz      short loc_180038243
0x18003823a  lea     rcx, [rdx+0A7Eh]
0x180038241  jmp     short loc_18003824A
0x180038243  test    rcx, rcx
0x180038246  jz      short loc_18003825B
0x180038248  xor     ecx, ecx
0x18003824a  mov     rdx, [rax]
0x18003824d  test    rdx, rdx
0x180038250  jz      short loc_18003825D
0x180038252  lea     r9, [rdx+848h]
0x180038259  jmp     short loc_180038261
0x18003825b  xor     ecx, ecx
0x18003825d  lea     r9, [rbp+800h+var_870]
0x180038261  lea     rax, [rbp+800h+var_860]
0x180038265  mov     [rsp+900h+var_8D8], rax
0x18003826a  mov     [rsp+900h+var_8E0], rcx
0x18003826f  lea     r8, aInvalidParam; "Invalid param"
0x180038276  lea     rdx, RasVpnIkeParamTraceError
0x18003827d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038284  call    McTemplateU0zjzz_EventWriteTransfer
0x180038289  mov     edi, [rsp+900h+var_8D0]
0x18003828d  mov     rbx, cs:WPP_GLOBAL_Control
0x180038294  test    edi, edi
0x180038296  jnz     short loc_1800382A1
0x180038298  lea     rsi, WPP_GLOBAL_Control
0x18003829f  jmp     short loc_1800382E0
0x1800382a1  lea     rsi, WPP_GLOBAL_Control
0x1800382a8  cmp     rbx, rsi
0x1800382ab  jz      loc_1800389AB
0x1800382b1  test    byte ptr [rbx+1Ch], 1
0x1800382b5  jz      short loc_1800382E0
0x1800382b7  cmp     byte ptr [rbx+19h], 2
0x1800382bb  jb      short loc_1800382E0
0x1800382bd  mov     edx, 11h
0x1800382c2  mov     r9d, edi
0x1800382c5  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800382cc  mov     rcx, [rbx+10h]
0x1800382d0  call    WPP_SF_d
0x1800382d5  mov     edi, [rsp+900h+var_8D0]
0x1800382d9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800382e0  cmp     rbx, rsi
0x1800382e3  jz      loc_1800389AB
0x1800382e9  test    byte ptr [rbx+1Ch], 1
0x1800382ed  jz      loc_1800389AB
0x1800382f3  cmp     byte ptr [rbx+19h], 6
0x1800382f7  jb      loc_1800389AB
0x1800382fd  mov     edx, 12h
0x180038302  mov     r9d, edi
0x180038305  mov     rcx, [rbx+10h]
0x180038309  jmp     loc_18003899B
0x18003830e  call    cs:__imp_GetProcessHeap
0x180038314  mov     rcx, rax; hHeap
0x180038317  mov     r8d, 10h; dwBytes
0x18003831d  mov     edx, edi; dwFlags
0x18003831f  call    cs:__imp_HeapAlloc
0x180038325  mov     [r12], rax
0x180038329  test    rax, rax
0x18003832c  jnz     short loc_1800383A0
0x18003832e  mov     [rsp+900h+var_8D0], edi
0x180038332  mov     rcx, cs:WPP_GLOBAL_Control
0x180038339  lea     rbx, WPP_GLOBAL_Control
0x180038340  cmp     rcx, rbx
0x180038343  jz      loc_1800389AB
0x180038349  test    byte ptr [rcx+1Ch], 1
0x18003834d  jz      short loc_180038376
0x18003834f  cmp     byte ptr [rcx+19h], 2
0x180038353  jb      short loc_180038376
0x180038355  lea     edx, [rax+13h]
0x180038358  mov     r9d, edi
0x18003835b  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180038362  mov     rcx, [rcx+10h]
0x180038366  call    WPP_SF_d
0x18003836b  mov     edi, [rsp+900h+var_8D0]
0x18003836f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038376  cmp     rcx, rbx
0x180038379  jz      loc_1800389AB
0x18003837f  test    byte ptr [rcx+1Ch], 1
0x180038383  jz      loc_1800389AB
0x180038389  cmp     byte ptr [rcx+19h], 6
0x18003838d  jb      loc_1800389AB
0x180038393  mov     edx, 14h
0x180038398  mov     r9d, edi
0x18003839b  jmp     loc_180038997
0x1800383a0  xor     bl, bl
0x1800383a2  mov     [rsp+900h+var_8CC], bl
0x1800383a6  mov     dword ptr [rax], 1
0x1800383ac  mov     rax, [r12]
0x1800383b0  add     rax, rdi
0x1800383b3  mov     [rsp+900h+var_8C8], rax
0x1800383b8  test    byte ptr cs:?AvailableIPProtocols@VPNIKEProtocolEngine@@2KA, 1; ulong VPNIKEProtocolEngine::AvailableIPProtocols
0x1800383bf  jz      loc_180038629
0x1800383c5  mov     rcx, [rsi+30h]
0x1800383c9  mov     rcx, [rcx+20h]; this
0x1800383cd  call    ?DoNegotiate@IPv4Helper@@QEAAEXZ; IPv4Helper::DoNegotiate(void)
0x1800383d2  test    al, al
0x1800383d4  jz      loc_180038629
0x1800383da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383e1  lea     rax, WPP_GLOBAL_Control
0x1800383e8  cmp     rcx, rax
0x1800383eb  jz      short loc_18003840E
0x1800383ed  test    byte ptr [rcx+1Ch], 1
0x1800383f1  jz      short loc_18003840E
0x1800383f3  cmp     byte ptr [rcx+19h], 5
0x1800383f7  jb      short loc_18003840E
0x1800383f9  mov     edx, 15h
0x1800383fe  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180038405  mov     rcx, [rcx+10h]
0x180038409  call    WPP_SF_
0x18003840e  mov     rax, [rsi+30h]
0x180038412  mov     rcx, [rax+20h]
0x180038416  xor     eax, eax
0x180038418  lea     r9d, [rax+1]
0x18003841c  lea     r8, [rsp+900h+var_8C8]
0x180038421  cmp     [rcx], eax
0x180038423  jz      short loc_180038465
0x180038425  mov     [rsp+900h+var_8D8], rcx
0x18003842a  mov     dword ptr [rsp+900h+var_8E0], 4
0x180038432  call    ?AddNewAttributeTLV@ClientBFEHandler@@IEAAKPEAU_CONFIGURATION_PAYLOAD_@@PEAPEAPEAU_CFG_ATTR_TLV_@@W4_CFG_ATTR_TYPE_@@KPEAX@Z; ClientBFEHandler::AddNewAttributeTLV(_CONFIGURATION_PAYLOAD_ *,_CFG_ATTR_TLV_ * * *,_CFG_ATTR_TYPE_,ulong,void *)
0x180038437  mov     [rsp+900h+var_8D0], eax
0x18003843b  test    eax, eax
0x18003843d  jz      short loc_1800384B2
0x18003843f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038446  lea     rdx, WPP_GLOBAL_Control
0x18003844d  cmp     rcx, rdx
0x180038450  jz      short loc_1800384B9
0x180038452  test    byte ptr [rcx+1Ch], 1
0x180038456  jz      short loc_1800384B9
0x180038458  cmp     byte ptr [rcx+19h], 2
0x18003845c  jb      short loc_1800384B9
0x18003845e  mov     edx, 16h
0x180038463  jmp     short loc_18003849F
0x180038465  mov     [rsp+900h+var_8D8], rax
0x18003846a  mov     dword ptr [rsp+900h+var_8E0], eax
0x18003846e  call    ?AddNewAttributeTLV@ClientBFEHandler@@IEAAKPEAU_CONFIGURATION_PAYLOAD_@@PEAPEAPEAU_CFG_ATTR_TLV_@@W4_CFG_ATTR_TYPE_@@KPEAX@Z; ClientBFEHandler::AddNewAttributeTLV(_CONFIGURATION_PAYLOAD_ *,_CFG_ATTR_TLV_ * * *,_CFG_ATTR_TYPE_,ulong,void *)
0x180038473  mov     [rsp+900h+var_8D0], eax
0x180038477  test    eax, eax
0x180038479  jz      short loc_1800384B2
0x18003847b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038482  lea     rdx, WPP_GLOBAL_Control
0x180038489  cmp     rcx, rdx
0x18003848c  jz      short loc_1800384B9
0x18003848e  test    byte ptr [rcx+1Ch], 1
0x180038492  jz      short loc_1800384B9
0x180038494  cmp     byte ptr [rcx+19h], 2
0x180038498  jb      short loc_1800384B9
0x18003849a  mov     edx, 17h
0x18003849f  mov     r9d, eax
0x1800384a2  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800384a9  mov     rcx, [rcx+10h]
0x1800384ad  call    WPP_SF_d
0x1800384b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384b9  cmp     [rsp+900h+var_8D0], 0
0x1800384be  jz      loc_18003858E
0x1800384c4  test    cs:byte_1800AA941, 4
0x1800384cb  jz      loc_1800387D4
0x1800384d1  xor     edi, edi
0x1800384d3  mov     word ptr [rbp+800h+var_830], di
0x1800384d7  mov     word ptr [rbp+800h+var_860], di
0x1800384db  mov     rax, [rsi+30h]
0x1800384df  test    rax, rax
0x1800384e2  jz      short loc_1800384F8
0x1800384e4  mov     rax, [rax+70h]
0x1800384e8  test    rax, rax
0x1800384eb  jz      short loc_1800384F8
0x1800384ed  cmp     [rax+10h], rdi
0x1800384f1  jz      short loc_1800384F8
0x1800384f3  mov     edx, [rax+10h]
0x1800384f6  jmp     short loc_1800384FB
0x1800384f8  mov     edx, r13d
0x1800384fb  lea     rcx, [rbp+800h+var_860]
0x1800384ff  call    ConvertPortNoToString
0x180038504  mov     r8d, [rsp+900h+var_8D0]
0x180038509  lea     rdx, aAddnewattribut; "AddNewAttributeTLV failure %d"
0x180038510  lea     rcx, [rbp+800h+var_830]
0x180038514  call    FormatRRASErrorString
0x180038519  test    cs:byte_1800AA941, 4
0x180038520  jz      loc_1800387CD
0x180038526  mov     rcx, [rsi+30h]
0x18003852a  lea     rax, [rcx+70h]
0x18003852e  test    rcx, rcx
0x180038531  jz      short loc_18003855D
0x180038533  mov     rdx, [rax]
0x180038536  test    rdx, rdx
0x180038539  jz      short loc_180038544
0x18003853b  lea     rcx, [rdx+0A7Eh]
0x180038542  jmp     short loc_18003854C
0x180038544  test    rcx, rcx
0x180038547  jz      short loc_18003855D
0x180038549  mov     rcx, rdi
0x18003854c  mov     rdx, [rax]
0x18003854f  test    rdx, rdx
0x180038552  jz      short loc_180038560
0x180038554  lea     r9, [rdx+848h]
0x18003855b  jmp     short loc_180038564
0x18003855d  mov     rcx, rdi
0x180038560  lea     r9, [rbp+800h+var_870]
0x180038564  lea     rax, [rbp+800h+var_860]
0x180038568  mov     [rsp+900h+var_8D8], rax
0x18003856d  mov     [rsp+900h+var_8E0], rcx
0x180038572  lea     r8, [rbp+800h+var_830]
0x180038576  lea     rdx, RasVpnIkeParamTraceError
0x18003857d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038584  call    McTemplateU0zjzz_EventWriteTransfer
0x180038589  jmp     loc_1800387CD
0x18003858e  mov     bl, 1
0x180038590  mov     [rsp+900h+var_8CC], bl
0x180038594  mov     rax, [rsi+30h]
0x180038598  mov     rcx, [rax+70h]
0x18003859c  cmp     dword ptr [rcx+109Ch], 1
0x1800385a3  jnz     short loc_1800385C6
0x1800385a5  mov     [rsp+900h+var_8D8], 0
  ... truncated ...
```
