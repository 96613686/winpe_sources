# CWcnService::StartSubsystems(void)

- ea: `0x180003dec`
- end: `0x1800045ca`
- name: `?StartSubsystems@CWcnService@@AEAAJXZ`
- size: `2014`
- prototype: `__int64 __fastcall(CWcnService *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003288`

## callees

- `0x180001b68`
- `0x180002be0`
- `0x180003dec`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x1800075a4`
- `0x18000b080`
- `0x18000b850`
- `0x1800113dc`
- `0x180014964`
- `0x1800208c0`
- `0x180033bcc`
- `0x180038728`
- `0x18003af3c`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180003f64`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180003f64`

## pseudocode

```c
__int64 __fastcall CWcnService::StartSubsystems(CWcnService *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  const char *v5; // rax
  __int64 v6; // r10
  tagWcnServicePrivate *v7; // rax
  tagWcnServicePrivate *v8; // rsi
  unsigned int v9; // ebx
  _BYTE *v10; // r10
  const char *v11; // rax
  __int64 v12; // r10
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  unsigned int LastError; // ebx
  unsigned int v15; // eax
  __int64 v16; // r10
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // rdx
  __int64 v20; // r9
  const char *v21; // rax
  __int64 v22; // r10
  unsigned int v23; // eax
  __int64 v24; // r10
  unsigned int v25; // eax
  __int64 v26; // r10
  char v27; // r11
  unsigned int v28; // eax
  char v29; // r11
  unsigned int v30; // eax
  __int64 v31; // r10
  struct _TP_TIMER **v32; // rsi
  const char *v33; // rax
  __int64 v34; // r10
  int Timer; // eax
  unsigned int v36; // eax
  __int64 v37; // r10
  __int64 v38; // rsi
  _QWORD *v39; // rax
  _QWORD *v40; // rbx
  int v41; // eax
  unsigned int v42; // eax
  __int64 v43; // r10

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      Indent = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v4 + 16), 33, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, Indent);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u )
    {
      v5 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v6 + 16), 34, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v5);
    }
  }
  v7 = (tagWcnServicePrivate *)operator new(0x5C8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v8 = tagWcnServicePrivate::tagWcnServicePrivate(v7);
  else
    v8 = 0;
  *((_QWORD *)this + 7) = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v9;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_127;
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, "m_pPriv");
    goto LABEL_126;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v11 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 10, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v11);
  }
  *((_DWORD *)v8 + 82) = 3;
  *((_QWORD *)v8 + 42) = 0;
  *((_QWORD *)v8 + 43) = 0;
  *((_QWORD *)v8 + 44) = 0;
  *((_QWORD *)v8 + 45) = 0;
  *((_QWORD *)v8 + 46) = 0;
  *((_QWORD *)v8 + 47) = 0;
  *((_DWORD *)v8 + 96) = 0;
  *((_DWORD *)v8 + 97) = 1;
  *((_DWORD *)v8 + 98) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)v8 + 50) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v9 = 0;
    *((_QWORD *)v8 + 43) = ThreadpoolCleanupGroup;
    *((_QWORD *)v8 + 44) = 0;
    goto LABEL_25;
  }
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0x80070000;
  else
    LastError = GetLastError();
  v9 = LastError | 0x80000000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_30;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v16 + 16), 11, (unsigned int)WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v15, v9);
LABEL_25:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v9 & 0x80000000) == 0 && v10[25] < 6u )
      goto LABEL_35;
    v17 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v18 + 16), 12, (unsigned int)WPP_476dff25f8043d358a001b332c2d8e81_Traceguids, v17, v9);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control )
      return v9;
    if ( v10[25] < 2u )
      goto LABEL_127;
    v19 = 36;
LABEL_34:
    v20 = v9;
    goto LABEL_125;
  }
LABEL_35:
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 6u )
  {
    v21 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v22 + 16), 10, WPP_e28116ee7cbe38f054101a4dc9bb00a5_Traceguids, v21);
  }
  CWcnAttributeRules::m_pDataTypeRules = 0;
  CWcnAttributeRules::m_pAttributeRules = 0;
  CWcnAttributeRules::m_pAttributeIds = 0;
  v9 = CWcnAttributeRules::InitializeHashTables();
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( *(_QWORD *)(CWcnAttributeRules::m_pAttributeRules + 8) == 100 )
    {
      if ( *(_QWORD *)(CWcnAttributeRules::m_pDataTypeRules + 8) == 39 )
      {
        CWcnAttributeRules::m_fInitialized = 1;
        goto LABEL_52;
      }
      v9 = -2147176190;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = (unsigned int)GetIndent(0);
        WPP_SF_sPd(
          *(_QWORD *)(v26 + 16),
          13,
          (unsigned int)WPP_e28116ee7cbe38f054101a4dc9bb00a5_Traceguids,
          v28,
          v29,
          39);
        goto LABEL_52;
      }
    }
    else
    {
      v9 = -2147176190;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = (unsigned int)GetIndent(0);
        WPP_SF_sPd(
          *(_QWORD *)(v26 + 16),
          12,
          (unsigned int)WPP_e28116ee7cbe38f054101a4dc9bb00a5_Traceguids,
          v25,
          v27,
          100);
        goto LABEL_52;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v9;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v24 + 16), 11, (unsigned int)WPP_e28116ee7cbe38f054101a4dc9bb00a5_Traceguids, v23, v9);
LABEL_52:
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v9 & 0x80000000) == 0 && v10[25] < 6u )
      goto LABEL_61;
    v30 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v31 + 16), 14, (unsigned int)WPP_e28116ee7cbe38f054101a4dc9bb00a5_Traceguids, v30, v9);
    v10 = WPP_GLOBAL_Control;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control )
      return v9;
    if ( v10[25] < 2u )
      goto LABEL_127;
    v19 = 37;
    goto LABEL_34;
  }
LABEL_61:
  v32 = (struct _TP_TIMER **)*((_QWORD *)this + 7);
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 6u )
  {
    v33 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v34 + 16), 10, WPP_f34e634574083547aa3a426270948a29_Traceguids, v33);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v32 == (struct _TP_TIMER **)-320LL )
  {
    if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)v10 + 2), 11, WPP_f34e634574083547aa3a426270948a29_Traceguids, "pScheduler");
      v10 = WPP_GLOBAL_Control;
    }
    v9 = -2147467261;
    goto LABEL_79;
  }
  Timer = CWcnScheduler::CreateTimer((CWcnScheduler *)(v32 + 40), WcnPeerCacheReaperThunk, v32 + 24, v32 + 38);
  v9 = Timer;
  if ( Timer >= 0 )
    goto LABEL_73;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_78;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_f34e634574083547aa3a426270948a29_Traceguids,
      (unsigned int)Timer);
LABEL_73:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && ((v9 & 0x80000000) != 0 || v10[25] >= 6u) )
  {
    v36 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v37 + 16), 13, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v36, v9);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_78:
  if ( (v9 & 0x80000000) != 0 )
  {
LABEL_79:
    if ( v10 == (_BYTE *)&WPP_GLOBAL_Control )
      return v9;
    if ( v10[25] < 2u )
      goto LABEL_127;
    v19 = 38;
    goto LABEL_34;
  }
  v38 = *((_QWORD *)this + 7);
  v39 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v40 = v39;
  if ( v39 )
  {
    *v39 = 0;
    v39[1] = 0;
    *v39 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,CWcnRpcHandleTracker::tagPER_SESSION_DATA>>>::_Buyheadnode();
  }
  else
  {
    v40 = 0;
  }
  *(_QWORD *)(v38 + 1464) = v40;
  if ( v40 )
  {
    v41 = WcnpRpcInit(
            (struct CWcnPeerCache *)(*((_QWORD *)this + 7) + 192LL),
            (struct CWcnEventManager *)(*((_QWORD *)this + 7) + 1312LL));
    v9 = v41;
    if ( v41 >= 0 )
    {
      qword_1800759B0 = *((_QWORD *)this + 7) + 432LL;
      byte_1800759B8 = 1;
      v41 = CCmWcnCrypto::Init();
      v9 = v41;
      if ( v41 >= 0 )
      {
        v41 = CWcnIdentity::InitializeToSelf((CWcnIdentity *)(*((_QWORD *)this + 7) + 1192LL));
        v9 = v41;
        if ( v41 >= 0 )
        {
          v41 = CWcnRpcManager::Init((CWcnRpcManager *)(*((_QWORD *)this + 7) + 408LL));
          v9 = v41;
          if ( v41 >= 0 )
          {
            v41 = CWcnProtocolVX::Init(*((_QWORD *)this + 7) + 552LL, 16);
            v9 = v41;
            if ( v41 >= 0 )
            {
              v41 = CWcnProtocolVX::Init(*((_QWORD *)this + 7) + 872LL, 32);
              v9 = v41;
              if ( v41 >= 0 )
              {
                v41 = CWcnProtocolVX::Init(*((_QWORD *)this + 7) + 712LL, 272);
                v9 = v41;
                if ( v41 >= 0 )
                {
                  v41 = CWcnProtocolVX::Init(*((_QWORD *)this + 7) + 1032LL, 288);
                  v9 = v41;
                  if ( v41 >= 0 )
                  {
LABEL_126:
                    v10 = WPP_GLOBAL_Control;
                    goto LABEL_127;
                  }
                  v10 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v9;
                  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    goto LABEL_127;
                  v19 = 47;
                }
                else
                {
                  v10 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v9;
                  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    goto LABEL_127;
                  v19 = 46;
                }
              }
              else
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  return v9;
                if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_127;
                v19 = 45;
              }
            }
            else
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v9;
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_127;
              v19 = 44;
            }
          }
          else
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v9;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_127;
            v19 = 43;
          }
        }
        else
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v9;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_127;
          v19 = 42;
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v9;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_127;
        v19 = 41;
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_127;
      v19 = 40;
    }
    v20 = (unsigned int)v41;
LABEL_125:
    WPP_SF_d(*((_QWORD *)v10 + 2), v19, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v20);
    goto LABEL_126;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids,
      "m_pPerSessionData");
    v10 = WPP_GLOBAL_Control;
  }
  v9 = -2147024882;
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( v10[25] < 2u )
    {
LABEL_127:
      if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && ((v9 & 0x80000000) != 0 || v10[25] >= 6u) )
      {
        v42 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v43 + 16), 48, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v42, v9);
      }
      return v9;
    }
    v19 = 39;
    goto LABEL_34;
  }
  return v9;
}

```

## disassembly

```asm
0x180003dec  push    rbx
0x180003dee  push    rbp
0x180003def  push    rsi
0x180003df0  push    rdi
0x180003df1  push    r12
0x180003df3  push    r13
0x180003df5  push    r14
0x180003df7  push    r15
0x180003df9  sub     rsp, 38h
0x180003dfd  mov     rbp, rcx
0x180003e00  lea     r15, WPP_GLOBAL_Control
0x180003e07  mov     ebx, 1
0x180003e0c  lea     r12, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003e13  mov     r10, cs:WPP_GLOBAL_Control
0x180003e1a  cmp     r10, r15
0x180003e1d  jz      short loc_180003E6D
0x180003e1f  cmp     byte ptr [r10+19h], 6
0x180003e24  jb      short loc_180003E46
0x180003e26  mov     ecx, ebx; int
0x180003e28  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003e2d  lea     edx, [rbx+20h]
0x180003e30  mov     r9, rax
0x180003e33  mov     r8, r12
0x180003e36  mov     rcx, [r10+10h]
0x180003e3a  call    WPP_SF_s
0x180003e3f  mov     r10, cs:WPP_GLOBAL_Control
0x180003e46  cmp     r10, r15
0x180003e49  jz      short loc_180003E6D
0x180003e4b  cmp     byte ptr [r10+19h], 4
0x180003e50  jb      short loc_180003E6D
0x180003e52  xor     ecx, ecx; int
0x180003e54  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003e59  mov     edx, 22h ; '"'
0x180003e5e  mov     r9, rax
0x180003e61  mov     r8, r12
0x180003e64  mov     rcx, [r10+10h]
0x180003e68  call    WPP_SF_s
0x180003e6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003e74  mov     ecx, 5C8h; unsigned __int64
0x180003e79  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003e7e  mov     [rsp+78h+arg_0], rax
0x180003e86  xor     r14d, r14d
0x180003e89  test    rax, rax
0x180003e8c  jz      short loc_180003E9B
0x180003e8e  mov     rcx, rax; this
0x180003e91  call    ??0tagWcnServicePrivate@@QEAA@XZ; tagWcnServicePrivate::tagWcnServicePrivate(void)
0x180003e96  mov     rsi, rax
0x180003e99  jmp     short loc_180003E9E
0x180003e9b  mov     rsi, r14
0x180003e9e  mov     [rbp+38h], rsi
0x180003ea2  test    rsi, rsi
0x180003ea5  jnz     short loc_180003EE4
0x180003ea7  mov     ebx, 8007000Eh
0x180003eac  mov     r10, cs:WPP_GLOBAL_Control
0x180003eb3  cmp     r10, r15
0x180003eb6  jz      loc_1800045B7
0x180003ebc  mov     dil, 2
0x180003ebf  cmp     [r10+19h], dil
0x180003ec3  jb      loc_180004587
0x180003ec9  lea     edx, [rsi+23h]
0x180003ecc  lea     r9, aMPpriv; "m_pPriv"
0x180003ed3  mov     r8, r12
0x180003ed6  mov     rcx, [r10+10h]
0x180003eda  call    WPP_SF_s
0x180003edf  jmp     loc_180004580
0x180003ee4  lea     r13, WPP_476dff25f8043d358a001b332c2d8e81_Traceguids
0x180003eeb  mov     r10, cs:WPP_GLOBAL_Control
0x180003ef2  cmp     r10, r15
0x180003ef5  jz      short loc_180003F19
0x180003ef7  cmp     byte ptr [r10+19h], 6
0x180003efc  jb      short loc_180003F19
0x180003efe  mov     ecx, ebx; int
0x180003f00  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003f05  mov     edx, 0Ah
0x180003f0a  mov     r9, rax
0x180003f0d  mov     r8, r13
0x180003f10  mov     rcx, [r10+10h]
0x180003f14  call    WPP_SF_s
0x180003f19  mov     dword ptr [rsi+148h], 3
0x180003f23  mov     [rsi+150h], r14
0x180003f2a  mov     [rsi+158h], r14
0x180003f31  mov     [rsi+160h], r14
0x180003f38  mov     [rsi+168h], r14
0x180003f3f  mov     [rsi+170h], r14
0x180003f46  mov     [rsi+178h], r14
0x180003f4d  mov     [rsi+180h], r14d
0x180003f54  mov     [rsi+184h], ebx
0x180003f5a  mov     dword ptr [rsi+188h], 48h ; 'H'
0x180003f64  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180003f6a  mov     [rsi+190h], rax
0x180003f71  mov     dil, 2
0x180003f74  test    rax, rax
0x180003f77  jnz     short loc_180003FD5
0x180003f79  call    cs:__imp_GetLastError
0x180003f7f  test    eax, eax
0x180003f81  jg      short loc_180003F8D
0x180003f83  call    cs:__imp_GetLastError
0x180003f89  mov     ebx, eax
0x180003f8b  jmp     short loc_180003F9C
0x180003f8d  call    cs:__imp_GetLastError
0x180003f93  movzx   ebx, ax
0x180003f96  or      ebx, 80070000h
0x180003f9c  or      ebx, 80000000h
0x180003fa2  mov     r10, cs:WPP_GLOBAL_Control
0x180003fa9  cmp     r10, r15
0x180003fac  jz      short loc_180004024
0x180003fae  cmp     [r10+19h], dil
0x180003fb2  jb      short loc_180003FED
0x180003fb4  xor     ecx, ecx; int
0x180003fb6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003fbb  mov     edx, 0Bh
0x180003fc0  mov     dword ptr [rsp+78h+var_58], ebx
0x180003fc4  mov     r9, rax
0x180003fc7  mov     r8, r13
0x180003fca  mov     rcx, [r10+10h]
0x180003fce  call    WPP_SF_sd
0x180003fd3  jmp     short loc_180003FE6
0x180003fd5  mov     ebx, r14d
0x180003fd8  mov     [rsi+158h], rax
0x180003fdf  mov     [rsi+160h], r14
0x180003fe6  mov     r10, cs:WPP_GLOBAL_Control
0x180003fed  cmp     r10, r15
0x180003ff0  jz      short loc_180004024
0x180003ff2  test    ebx, ebx
0x180003ff4  js      short loc_180003FFD
0x180003ff6  cmp     byte ptr [r10+19h], 6
0x180003ffb  jb      short loc_180004048
0x180003ffd  or      ecx, 0FFFFFFFFh; int
0x180004000  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180004005  mov     edx, 0Ch
0x18000400a  mov     dword ptr [rsp+78h+var_58], ebx
0x18000400e  mov     r9, rax
0x180004011  mov     r8, r13
0x180004014  mov     rcx, [r10+10h]
0x180004018  call    WPP_SF_sd
0x18000401d  mov     r10, cs:WPP_GLOBAL_Control
0x180004024  test    ebx, ebx
0x180004026  jns     short loc_180004048
0x180004028  cmp     r10, r15
0x18000402b  jz      loc_1800045B7
0x180004031  cmp     [r10+19h], dil
0x180004035  jb      loc_180004587
0x18000403b  mov     edx, 24h ; '$'
0x180004040  mov     r9d, ebx
0x180004043  jmp     loc_180004574
0x180004048  lea     rsi, WPP_e28116ee7cbe38f054101a4dc9bb00a5_Traceguids
0x18000404f  cmp     r10, r15
0x180004052  jz      short loc_180004079
0x180004054  cmp     byte ptr [r10+19h], 6
0x180004059  jb      short loc_180004079
0x18000405b  mov     ecx, 1; int
0x180004060  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180004065  mov     edx, 0Ah
0x18000406a  mov     r9, rax
0x18000406d  mov     r8, rsi
0x180004070  mov     rcx, [r10+10h]
0x180004074  call    WPP_SF_s
0x180004079  mov     cs:?m_pDataTypeRules@CWcnAttributeRules@@0PEAV?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@EA, r14; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *> * CWcnAttributeRules::m_pDataTypeRules
0x180004080  mov     cs:?m_pAttributeRules@CWcnAttributeRules@@0PEAV?$map@W4tagWCN_ATTRIBUTE_TYPE@@PEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_ATTRIBUTE_TYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_ATTRIBUTE_TYPE@@PEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@@std@@@5@@std@@EA, r14; std::map<tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *> * CWcnAttributeRules::m_pAttributeRules
0x180004087  mov     cs:?m_pAttributeIds@CWcnAttributeRules@@0PEAV?$map@IPEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@@std@@@4@@std@@EA, r14; std::map<uint,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *> * CWcnAttributeRules::m_pAttributeIds
0x18000408e  call    ?InitializeHashTables@CWcnAttributeRules@@CAJXZ; CWcnAttributeRules::InitializeHashTables(void)
0x180004093  mov     ebx, eax
0x180004095  test    eax, eax
0x180004097  jns     short loc_1800040D7
0x180004099  mov     r10, cs:WPP_GLOBAL_Control
0x1800040a0  cmp     r10, r15
0x1800040a3  jz      loc_1800045B7
0x1800040a9  cmp     [r10+19h], dil
0x1800040ad  jb      loc_18000417D
0x1800040b3  xor     ecx, ecx; int
0x1800040b5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800040ba  mov     edx, 0Bh
0x1800040bf  mov     dword ptr [rsp+78h+var_58], ebx
0x1800040c3  mov     r9, rax
0x1800040c6  mov     r8, rsi
0x1800040c9  mov     rcx, [r10+10h]
0x1800040cd  call    WPP_SF_sd
0x1800040d2  jmp     loc_180004176
0x1800040d7  mov     rax, cs:?m_pAttributeRules@CWcnAttributeRules@@0PEAV?$map@W4tagWCN_ATTRIBUTE_TYPE@@PEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_ATTRIBUTE_TYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_ATTRIBUTE_TYPE@@PEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@@std@@@5@@std@@EA; std::map<tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *> * CWcnAttributeRules::m_pAttributeRules
0x1800040de  mov     r11, [rax+8]
0x1800040e2  cmp     r11, 64h ; 'd'
0x1800040e6  jz      short loc_18000412D
0x1800040e8  mov     ebx, 8004B102h
0x1800040ed  mov     r10, cs:WPP_GLOBAL_Control
0x1800040f4  cmp     r10, r15
0x1800040f7  jz      loc_1800045B7
0x1800040fd  cmp     [r10+19h], dil
0x180004101  jb      short loc_18000417D
0x180004103  xor     ecx, ecx; int
0x180004105  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000410a  mov     edx, 0Ch
0x18000410f  mov     [rsp+78h+var_50], 64h ; 'd'
0x180004117  mov     [rsp+78h+var_58], r11
0x18000411c  mov     r9, rax
0x18000411f  mov     r8, rsi
0x180004122  mov     rcx, [r10+10h]
0x180004126  call    WPP_SF_sPd
0x18000412b  jmp     short loc_180004176
0x18000412d  mov     rax, cs:?m_pDataTypeRules@CWcnAttributeRules@@0PEAV?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@EA; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *> * CWcnAttributeRules::m_pDataTypeRules
0x180004134  mov     r11, [rax+8]
0x180004138  cmp     r11, 27h ; '''
0x18000413c  jz      short loc_18000416F
0x18000413e  mov     ebx, 8004B102h
0x180004143  mov     r10, cs:WPP_GLOBAL_Control
0x18000414a  cmp     r10, r15
0x18000414d  jz      loc_1800045B7
0x180004153  cmp     [r10+19h], dil
0x180004157  jb      short loc_18000417D
0x180004159  xor     ecx, ecx; int
0x18000415b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180004160  mov     edx, 0Dh
0x180004165  mov     [rsp+78h+var_50], 27h ; '''
0x18000416d  jmp     short loc_180004117
0x18000416f  mov     cs:?m_fInitialized@CWcnAttributeRules@@0_NA, 1; bool CWcnAttributeRules::m_fInitialized
0x180004176  mov     r10, cs:WPP_GLOBAL_Control
0x18000417d  cmp     r10, r15
0x180004180  jz      short loc_1800041B4
0x180004182  test    ebx, ebx
0x180004184  js      short loc_18000418D
0x180004186  cmp     byte ptr [r10+19h], 6
0x18000418b  jb      short loc_1800041D5
0x18000418d  or      ecx, 0FFFFFFFFh; int
0x180004190  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180004195  mov     edx, 0Eh
0x18000419a  mov     dword ptr [rsp+78h+var_58], ebx
0x18000419e  mov     r9, rax
0x1800041a1  mov     r8, rsi
0x1800041a4  mov     rcx, [r10+10h]
0x1800041a8  call    WPP_SF_sd
0x1800041ad  mov     r10, cs:WPP_GLOBAL_Control
0x1800041b4  test    ebx, ebx
0x1800041b6  jns     short loc_1800041D5
0x1800041b8  cmp     r10, r15
0x1800041bb  jz      loc_1800045B7
0x1800041c1  cmp     [r10+19h], dil
0x1800041c5  jb      loc_180004587
0x1800041cb  mov     edx, 25h ; '%'
0x1800041d0  jmp     loc_180004040
0x1800041d5  mov     rsi, [rbp+38h]
0x1800041d9  lea     rbx, [rsi+140h]
0x1800041e0  lea     r13, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x1800041e7  cmp     r10, r15
0x1800041ea  jz      short loc_180004218
0x1800041ec  cmp     byte ptr [r10+19h], 6
0x1800041f1  jb      short loc_180004218
0x1800041f3  mov     ecx, 1; int
0x1800041f8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800041fd  mov     edx, 0Ah
0x180004202  mov     r9, rax
0x180004205  mov     r8, r13
0x180004208  mov     rcx, [r10+10h]
0x18000420c  call    WPP_SF_s
0x180004211  mov     r10, cs:WPP_GLOBAL_Control
0x180004218  test    rbx, rbx
0x18000421b  jnz     short loc_18000424F
0x18000421d  cmp     r10, r15
0x180004220  jz      short loc_180004245
0x180004222  cmp     [r10+19h], dil
0x180004226  jb      short loc_180004245
0x180004228  lea     edx, [rbx+0Bh]
0x18000422b  lea     r9, aPscheduler; "pScheduler"
0x180004232  mov     r8, r13
0x180004235  mov     rcx, [r10+10h]
0x180004239  call    WPP_SF_s
0x18000423e  mov     r10, cs:WPP_GLOBAL_Control
0x180004245  mov     ebx, 80004003h
0x18000424a  jmp     loc_1800042D7
0x18000424f  lea     r8, [rsi+0C0h]; void *
0x180004256  lea     r9, [r8+70h]; struct _TP_TIMER **
0x18000425a  lea     rdx, WcnPeerCacheReaperThunk; void (*)(void *, void *, void *)
0x180004261  mov     rcx, rbx; this
0x180004264  call    ?CreateTimer@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_TIMER@@@Z; CWcnScheduler::CreateTimer(void (*)(void *,void *,void *),void *,_TP_TIMER * *)
0x180004269  mov     ebx, eax
0x18000426b  test    eax, eax
0x18000426d  jns     short loc_180004295
0x18000426f  mov     r10, cs:WPP_GLOBAL_Control
0x180004276  cmp     r10, r15
0x180004279  jz      short loc_1800042D3
0x18000427b  cmp     [r10+19h], dil
0x18000427f  jb      short loc_18000429C
0x180004281  mov     edx, 0Ch
0x180004286  mov     r9d, eax
0x180004289  mov     r8, r13
0x18000428c  mov     rcx, [r10+10h]
0x180004290  call    WPP_SF_d
0x180004295  mov     r10, cs:WPP_GLOBAL_Control
0x18000429c  cmp     r10, r15
0x18000429f  jz      short loc_1800042D3
0x1800042a1  test    ebx, ebx
0x1800042a3  js      short loc_1800042AC
0x1800042a5  cmp     byte ptr [r10+19h], 6
0x1800042aa  jb      short loc_1800042D3
0x1800042ac  or      ecx, 0FFFFFFFFh; int
0x1800042af  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800042b4  mov     edx, 0Dh
0x1800042b9  mov     dword ptr [rsp+78h+var_58], ebx
0x1800042bd  mov     r9, rax
0x1800042c0  mov     r8, r13
0x1800042c3  mov     rcx, [r10+10h]
0x1800042c7  call    WPP_SF_sd
  ... truncated ...
```
