# TetheringService::ConfigureCellularImsiSubscription(void)

- ea: `0x18001670c`
- end: `0x180016b62`
- name: `?ConfigureCellularImsiSubscription@TetheringService@@AEAAJXZ`
- size: `1110`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019034`
- `0x180019ec0`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18001670c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167bf`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180016a94`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180016a94`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016acc`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016acc`
- `ntdll!NtQueryWnfStateData` at `0x1800167e9`
- `ntdll!NtQueryWnfStateData` at `0x18001689f`
- `ntdll!NtQueryWnfStateData` at `0x18001698a`
- `ntdll!NtQueryWnfStateData` at `0x180016a29`
- `ntdll!NtQueryWnfStateData` at `0x1800167e9`
- `ntdll!NtQueryWnfStateData` at `0x18001689f`
- `ntdll!NtQueryWnfStateData` at `0x18001698a`
- `ntdll!NtQueryWnfStateData` at `0x180016a29`

## pseudocode

```c
__int64 __fastcall TetheringService::ConfigureCellularImsiSubscription(TetheringService *this)
{
  int v2; // ebx
  unsigned int v3; // ebx
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx
  TetheringServiceTelemetry *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  int v18[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h]
  _OWORD v22[4]; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v27[2]; // [rsp+F8h] [rbp-8h] BYREF
  int v28; // [rsp+118h] [rbp+18h]
  _OWORD v29[7]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v30; // [rsp+190h] [rbp+90h]
  _BYTE v31[80]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v32[96]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v33; // [rsp+250h] [rbp+150h]

  v15 = 36;
  v28 = 0;
  v14 = 0;
  v25 = 0;
  memset(v27, 0, sizeof(v27));
  memset_0(v29, 0, 0x78u);
  v16 = 120;
  v26 = 0;
  memset_0(v32, 0, 0xC8u);
  v17 = 200;
  v24 = 0;
  memset_0(v31, 0, 0x44u);
  v18[0] = 68;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  v2 = NtQueryWnfStateData(&WNF_CELL_SYSTEM_CONFIG, 0, 0, &v14, v27, &v15);
  if ( v2 >= 0 )
  {
    v3 = 0;
    if ( v15 != 36 )
    {
      v3 = -2147019873;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_36;
      }
      v7 = 341;
      goto LABEL_35;
    }
  }
  else
  {
    v3 = v2 | 0x10000000;
    if ( (v3 & 0x80000000) != 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 340;
LABEL_6:
        WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v3);
        goto LABEL_36;
      }
      goto LABEL_36;
    }
  }
  v25 = *(_QWORD *)((char *)v27 + 4);
  v14 = 0;
  v8 = NtQueryWnfStateData(&v25, 0, 0, &v14, v29, &v16);
  if ( v8 >= 0 )
  {
    if ( v16 == 120 )
    {
      v9 = *((unsigned __int8 *)this + 1664);
      v19 = v29[0];
      v20 = v29[1];
      v21 = v29[2];
      v22[0] = v29[3];
      v22[1] = v29[4];
      v22[2] = v29[5];
      v22[3] = v29[6];
      v23 = v30;
      v26 = *((_QWORD *)v22 + v9 + 1);
      v14 = 0;
      v10 = NtQueryWnfStateData(&v26, 0, 0, &v14, v32, &v17);
      if ( v10 < 0 )
      {
        v3 = v10 | 0x10000000;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 344;
          goto LABEL_6;
        }
        goto LABEL_36;
      }
      if ( v17 == 200 )
      {
        v24 = v33;
        v14 = 0;
        v11 = NtQueryWnfStateData(&v24, 0, 0, &v14, v31, v18);
        if ( v11 < 0 )
        {
          v3 = v11 | 0x10000000;
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = 346;
            goto LABEL_6;
          }
          goto LABEL_36;
        }
        if ( v18[0] == 68 )
          goto LABEL_36;
        v3 = -2147019873;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_36;
        }
        v7 = 347;
      }
      else
      {
        v3 = -2147019873;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_36;
        }
        v7 = 345;
      }
    }
    else
    {
      v3 = -2147019873;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_36;
      }
      v7 = 343;
    }
LABEL_35:
    WPP_SF_(*((_QWORD *)v6 + 2), v7, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_36;
  }
  v3 = v8 | 0x10000000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 342;
    goto LABEL_6;
  }
LABEL_36:
  if ( *((_QWORD *)this + 210) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 210) = 0;
  }
  v12 = RtlSubscribeWnfStateChangeNotification(
          (char *)this + 1680,
          v24,
          v14,
          TetheringService::CellularImsiWnfCallback,
          0,
          0,
          0,
          0);
  if ( v12 )
  {
    v3 = v12 | 0x10000000;
    if ( v12 < 0
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 348, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v3);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 349, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18001670c  mov     [rsp-8+arg_8], rbx
0x180016711  mov     [rsp-8+arg_10], rsi
0x180016716  push    rbp
0x180016717  push    rdi
0x180016718  push    r12
0x18001671a  push    r14
0x18001671c  push    r15
0x18001671e  lea     rbp, [rsp-1D0h]
0x180016726  sub     rsp, 2D0h
0x18001672d  mov     rax, cs:__security_cookie
0x180016734  xor     rax, rsp
0x180016737  mov     [rbp+1F0h+var_30], rax
0x18001673e  xor     eax, eax
0x180016740  mov     [rsp+2F0h+var_2AC], 24h ; '$'
0x180016748  xorps   xmm0, xmm0
0x18001674b  mov     [rbp+1F0h+var_1D8], eax
0x18001674e  mov     rdi, rcx
0x180016751  xor     r14d, r14d
0x180016754  xor     edx, edx; Val
0x180016756  mov     [rsp+2F0h+var_2B0], r14d
0x18001675b  lea     ebx, [rax+78h]
0x18001675e  mov     [rbp+1F0h+var_208], r14
0x180016762  mov     r8d, ebx; Size
0x180016765  lea     rcx, [rbp+1F0h+var_1D0]; void *
0x180016769  movups  [rbp+1F0h+var_1F8], xmm0
0x18001676d  movups  [rbp+1F0h+var_1E8], xmm0
0x180016771  call    memset_0
0x180016776  mov     [rsp+2F0h+var_2A8], ebx
0x18001677a  lea     rcx, [rbp+1F0h+var_100]; void *
0x180016781  mov     ebx, 0C8h
0x180016786  mov     [rbp+1F0h+var_200], r14
0x18001678a  mov     r8d, ebx; Size
0x18001678d  xor     edx, edx; Val
0x18001678f  call    memset_0
0x180016794  mov     [rsp+2F0h+var_2A4], ebx
0x180016798  lea     rcx, [rbp+1F0h+var_150]; void *
0x18001679f  lea     ebx, [r14+44h]
0x1800167a3  mov     [rbp+1F0h+var_210], r14
0x1800167a7  mov     r8d, ebx; Size
0x1800167aa  xor     edx, edx; Val
0x1800167ac  call    memset_0
0x1800167b1  lea     rsi, [rdi+5D0h]
0x1800167b8  mov     [rsp+2F0h+var_2A0], ebx
0x1800167bc  mov     rcx, rsi; lpCriticalSection
0x1800167bf  call    cs:__imp_EnterCriticalSection
0x1800167c5  lea     rax, [rsp+2F0h+var_2AC]
0x1800167ca  xor     r8d, r8d
0x1800167cd  mov     [rsp+2F0h+var_2C8], rax
0x1800167d2  lea     r9, [rsp+2F0h+var_2B0]
0x1800167d7  lea     rax, [rbp+1F0h+var_1F8]
0x1800167db  xor     edx, edx
0x1800167dd  lea     rcx, WNF_CELL_SYSTEM_CONFIG
0x1800167e4  mov     [rsp+2F0h+var_2D0], rax
0x1800167e9  call    cs:__imp_NtQueryWnfStateData
0x1800167ef  lea     r15, WPP_GLOBAL_Control
0x1800167f6  mov     ebx, eax
0x1800167f8  lea     r12, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800167ff  test    eax, eax
0x180016801  jns     short loc_18001683E
0x180016803  or      ebx, 10000000h
0x180016809  jge     short loc_180016871
0x18001680b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016812  cmp     rcx, r15
0x180016815  jz      loc_180016A88
0x18001681b  test    byte ptr [rcx+1Ch], 1
0x18001681f  jz      loc_180016A88
0x180016825  mov     edx, 154h
0x18001682a  mov     rcx, [rcx+10h]
0x18001682e  mov     r9d, ebx
0x180016831  mov     r8, r12
0x180016834  call    WPP_SF_d
0x180016839  jmp     loc_180016A88
0x18001683e  cmp     [rsp+2F0h+var_2AC], 24h ; '$'
0x180016843  mov     ebx, r14d
0x180016846  jz      short loc_180016871
0x180016848  mov     ebx, 8007139Fh
0x18001684d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016854  cmp     rcx, r15
0x180016857  jz      loc_180016A88
0x18001685d  test    byte ptr [rcx+1Ch], 1
0x180016861  jz      loc_180016A88
0x180016867  mov     edx, 155h
0x18001686c  jmp     loc_180016A7C
0x180016871  mov     rax, qword ptr [rbp+1F0h+var_1F8+4]
0x180016875  lea     r9, [rsp+2F0h+var_2B0]
0x18001687a  mov     [rbp+1F0h+var_208], rax
0x18001687e  lea     rcx, [rbp+1F0h+var_208]
0x180016882  lea     rax, [rsp+2F0h+var_2A8]
0x180016887  mov     [rsp+2F0h+var_2B0], r14d
0x18001688c  mov     [rsp+2F0h+var_2C8], rax
0x180016891  xor     r8d, r8d
0x180016894  lea     rax, [rbp+1F0h+var_1D0]
0x180016898  xor     edx, edx
0x18001689a  mov     [rsp+2F0h+var_2D0], rax
0x18001689f  call    cs:__imp_NtQueryWnfStateData
0x1800168a5  test    eax, eax
0x1800168a7  jns     short loc_1800168D7
0x1800168a9  mov     ebx, eax
0x1800168ab  or      ebx, 10000000h
0x1800168b1  jge     short loc_180016907
0x1800168b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168ba  cmp     rcx, r15
0x1800168bd  jz      loc_180016A88
0x1800168c3  test    byte ptr [rcx+1Ch], 1
0x1800168c7  jz      loc_180016A88
0x1800168cd  mov     edx, 156h
0x1800168d2  jmp     loc_18001682A
0x1800168d7  cmp     [rsp+2F0h+var_2A8], 78h ; 'x'
0x1800168dc  jz      short loc_180016907
0x1800168de  mov     ebx, 8007139Fh
0x1800168e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168ea  cmp     rcx, r15
0x1800168ed  jz      loc_180016A88
0x1800168f3  test    byte ptr [rcx+1Ch], 1
0x1800168f7  jz      loc_180016A88
0x1800168fd  mov     edx, 157h
0x180016902  jmp     loc_180016A7C
0x180016907  movaps  xmm0, [rbp+1F0h+var_1D0]
0x18001690b  lea     r9, [rsp+2F0h+var_2B0]
0x180016910  movaps  xmm1, [rbp+1F0h+var_1C0]
0x180016914  xor     r8d, r8d
0x180016917  movzx   eax, byte ptr [rdi+680h]
0x18001691e  xor     edx, edx
0x180016920  movaps  [rsp+2F0h+var_290], xmm0
0x180016925  movaps  xmm0, [rbp+1F0h+var_1B0]
0x180016929  movaps  [rsp+2F0h+var_280], xmm1
0x18001692e  movaps  xmm1, [rbp+1F0h+var_1A0]
0x180016932  movaps  [rbp+1F0h+var_270], xmm0
0x180016936  movaps  xmm0, [rbp+1F0h+var_190]
0x18001693a  movaps  [rbp+1F0h+var_260], xmm1
0x18001693e  movaps  xmm1, [rbp+1F0h+var_180]
0x180016942  movaps  [rbp+1F0h+var_250], xmm0
0x180016946  movaps  xmm0, [rbp+1F0h+var_170]
0x18001694d  movaps  [rbp+1F0h+var_240], xmm1
0x180016951  movsd   xmm1, [rbp+1F0h+var_160]
0x180016959  movaps  [rbp+1F0h+var_230], xmm0
0x18001695d  movsd   [rbp+1F0h+var_220], xmm1
0x180016962  mov     rcx, qword ptr [rbp+rax*8+1F0h+var_260+8]
0x180016967  lea     rax, [rsp+2F0h+var_2A4]
0x18001696c  mov     [rsp+2F0h+var_2C8], rax
0x180016971  lea     rax, [rbp+1F0h+var_100]
0x180016978  mov     [rbp+1F0h+var_200], rcx
0x18001697c  lea     rcx, [rbp+1F0h+var_200]
0x180016980  mov     [rsp+2F0h+var_2D0], rax
0x180016985  mov     [rsp+2F0h+var_2B0], r14d
0x18001698a  call    cs:__imp_NtQueryWnfStateData
0x180016990  test    eax, eax
0x180016992  jns     short loc_1800169C2
0x180016994  mov     ebx, eax
0x180016996  or      ebx, 10000000h
0x18001699c  jge     short loc_1800169F5
0x18001699e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169a5  cmp     rcx, r15
0x1800169a8  jz      loc_180016A88
0x1800169ae  test    byte ptr [rcx+1Ch], 1
0x1800169b2  jz      loc_180016A88
0x1800169b8  mov     edx, 158h
0x1800169bd  jmp     loc_18001682A
0x1800169c2  cmp     [rsp+2F0h+var_2A4], 0C8h
0x1800169ca  jz      short loc_1800169F5
0x1800169cc  mov     ebx, 8007139Fh
0x1800169d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169d8  cmp     rcx, r15
0x1800169db  jz      loc_180016A88
0x1800169e1  test    byte ptr [rcx+1Ch], 1
0x1800169e5  jz      loc_180016A88
0x1800169eb  mov     edx, 159h
0x1800169f0  jmp     loc_180016A7C
0x1800169f5  mov     rax, [rbp+1F0h+var_A0]
0x1800169fc  lea     r9, [rsp+2F0h+var_2B0]
0x180016a01  mov     [rbp+1F0h+var_210], rax
0x180016a05  lea     rcx, [rbp+1F0h+var_210]
0x180016a09  lea     rax, [rsp+2F0h+var_2A0]
0x180016a0e  mov     [rsp+2F0h+var_2B0], r14d
0x180016a13  mov     [rsp+2F0h+var_2C8], rax
0x180016a18  xor     r8d, r8d
0x180016a1b  lea     rax, [rbp+1F0h+var_150]
0x180016a22  xor     edx, edx
0x180016a24  mov     [rsp+2F0h+var_2D0], rax
0x180016a29  call    cs:__imp_NtQueryWnfStateData
0x180016a2f  test    eax, eax
0x180016a31  jns     short loc_180016A59
0x180016a33  mov     ebx, eax
0x180016a35  or      ebx, 10000000h
0x180016a3b  jge     short loc_180016A88
0x180016a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a44  cmp     rcx, r15
0x180016a47  jz      short loc_180016A88
0x180016a49  test    byte ptr [rcx+1Ch], 1
0x180016a4d  jz      short loc_180016A88
0x180016a4f  mov     edx, 15Ah
0x180016a54  jmp     loc_18001682A
0x180016a59  cmp     [rsp+2F0h+var_2A0], 44h ; 'D'
0x180016a5e  jz      short loc_180016A88
0x180016a60  mov     ebx, 8007139Fh
0x180016a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a6c  cmp     rcx, r15
0x180016a6f  jz      short loc_180016A88
0x180016a71  test    byte ptr [rcx+1Ch], 1
0x180016a75  jz      short loc_180016A88
0x180016a77  mov     edx, 15Bh
0x180016a7c  mov     rcx, [rcx+10h]
0x180016a80  mov     r8, r12
0x180016a83  call    WPP_SF_
0x180016a88  mov     rcx, [rdi+690h]
0x180016a8f  test    rcx, rcx
0x180016a92  jz      short loc_180016AA1
0x180016a94  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180016a9a  mov     [rdi+690h], r14
0x180016aa1  mov     r8d, [rsp+2F0h+var_2B0]
0x180016aa6  lea     r9, ?CellularImsiWnfCallback@TetheringService@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; TetheringService::CellularImsiWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180016aad  mov     rdx, [rbp+1F0h+var_210]
0x180016ab1  lea     rcx, [rdi+690h]
0x180016ab8  mov     [rsp+2F0h+var_2B8], r14d
0x180016abd  mov     [rsp+2F0h+var_2C0], r14d
0x180016ac2  mov     [rsp+2F0h+var_2C8], r14
0x180016ac7  mov     [rsp+2F0h+var_2D0], r14
0x180016acc  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180016ad2  test    eax, eax
0x180016ad4  jz      short loc_180016B06
0x180016ad6  mov     ebx, eax
0x180016ad8  or      ebx, 10000000h
0x180016ade  jge     short loc_180016B06
0x180016ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ae7  cmp     rcx, r15
0x180016aea  jz      short loc_180016B06
0x180016aec  test    byte ptr [rcx+1Ch], 1
0x180016af0  jz      short loc_180016B06
0x180016af2  mov     rcx, [rcx+10h]
0x180016af6  mov     edx, 15Ch
0x180016afb  mov     r9d, ebx
0x180016afe  mov     r8, r12
0x180016b01  call    WPP_SF_d
0x180016b06  mov     rcx, rsi; lpCriticalSection
0x180016b09  call    cs:__imp_LeaveCriticalSection
0x180016b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b16  cmp     rcx, r15
0x180016b19  jz      short loc_180016B35
0x180016b1b  test    byte ptr [rcx+1Ch], 8
0x180016b1f  jz      short loc_180016B35
0x180016b21  mov     rcx, [rcx+10h]
0x180016b25  mov     edx, 15Dh
0x180016b2a  mov     r9d, ebx
0x180016b2d  mov     r8, r12
0x180016b30  call    WPP_SF_d
0x180016b35  mov     eax, ebx
0x180016b37  mov     rcx, [rbp+1F0h+var_30]
0x180016b3e  xor     rcx, rsp; StackCookie
0x180016b41  call    __security_check_cookie
0x180016b46  lea     r11, [rsp+2F0h+var_20]
0x180016b4e  mov     rbx, [r11+38h]
0x180016b52  mov     rsi, [r11+40h]
0x180016b56  mov     rsp, r11
0x180016b59  pop     r15
0x180016b5b  pop     r14
0x180016b5d  pop     r12
0x180016b5f  pop     rdi
0x180016b60  pop     rbp
0x180016b61  retn
```
