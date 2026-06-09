# WdfDevNode::SetRegKeySecurity(HKEY__ *,void *,ulong,int)

- ea: `0x1400240d4`
- end: `0x14002485b`
- name: `?SetRegKeySecurity@WdfDevNode@@AEAAXPEAUHKEY__@@PEAXKH@Z`
- size: `1927`
- prototype: `void(WdfDevNode *__hidden this, HKEY, void *, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002ba14`
- `0x14002e734`

## callees

- `0x140004c58`
- `0x14001f99c`
- `0x140022c34`
- `0x1400240d4`
- `0x140044300`
- `0x140091f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002433b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400246d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002433b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400246d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024815`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400241bc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400241bc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x140024850`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x140024850`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x140024397`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x140024397`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002420a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140024466`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002420a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140024466`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x14002417c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x14002417c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400243bd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400243bd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140024223`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140024223`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400243d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400243d8`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002448d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002448d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400242f4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400242f4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400242c2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400242c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400241e9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140024386`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400241e9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140024386`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400243ff`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400243ff`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14002412f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140024163`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14002412f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140024163`

## pseudocode

```c
void __fastcall WdfDevNode::SetRegKeySecurity(WdfDevNode *this, HKEY a2, void *a3, int a4, WINBOOL bDaclPresent)
{
  struct _ACL *v5; // r14
  DWORD KeySecurity; // eax
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rax
  void *v12; // rbx
  int AclSize; // r15d
  const struct std::nothrow_t *v14; // rdx
  DWORD v15; // esi
  PRPC_ASYNC_STATE v16; // rcx
  DWORD v17; // esi
  struct _ACL *v18; // rax
  struct _ACL *v19; // rsi
  DWORD v20; // eax
  PRPC_ASYNC_STATE v21; // rcx
  PRPC_ASYNC_STATE v22; // rcx
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v24; // rcx
  __int64 v25; // rdx
  DWORD i; // esi
  __int64 v27; // rdx
  PRPC_ASYNC_STATE v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  struct _ACL *pAcl; // [rsp+30h] [rbp-51h]
  DWORD cbSecurityDescriptor; // [rsp+38h] [rbp-49h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-41h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-39h] BYREF
  DWORD dwRevision; // [rsp+50h] [rbp-31h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+54h] [rbp-2Dh] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-29h]
  _OWORD v39[2]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v40; // [rsp+80h] [rbp-1h]
  WORD pControl; // [rsp+F8h] [rbp+77h] BYREF
  __int16 v42; // [rsp+FAh] [rbp+79h]

  v42 = HIWORD(a4);
  v5 = 0;
  pControl = 0;
  dwRevision = 0;
  bDaclPresent = 0;
  pDacl = 0;
  pAce = 0;
  pAcl = 0;
  bDaclDefaulted = 0;
  cbSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(a2, 4u, 0, &cbSecurityDescriptor);
  if ( KeySecurity != 122 )
  {
    pSecurityDescriptor = 0;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_17;
    }
    v27 = 21;
LABEL_103:
    WPP_SF_d(v22->u.APC.hThread, v27, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, KeySecurity);
    goto LABEL_17;
  }
  v11 = operator new(cbSecurityDescriptor, v10);
  pSecurityDescriptor = v11;
  v12 = v11;
  if ( !v11 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_17;
    }
    v29 = 22;
LABEL_59:
    WPP_SF_(v28->u.APC.hThread, v29, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
    goto LABEL_17;
  }
  KeySecurity = RegGetKeySecurity(a2, 4u, v11, &cbSecurityDescriptor);
  if ( KeySecurity )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_17;
    }
    v27 = 23;
    goto LABEL_103;
  }
  if ( !GetSecurityDescriptorControl(v12, &pControl, &dwRevision) )
  {
    KeySecurity = GetLastError();
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_17;
    }
    v27 = 24;
    goto LABEL_103;
  }
  bDaclPresent = pControl & 4;
  if ( (pControl & 4) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
    {
      WPP_SF_SS(
        WPP_GLOBAL_Control->u.APC.hThread,
        30,
        (unsigned int)&WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
        *((_QWORD *)this + 12),
        *((_QWORD *)this + 35));
    }
    pDacl = 0;
    v15 = GetLengthSid(a3) + 16;
LABEL_20:
    if ( v15 )
    {
      v17 = (_DWORD)v5 + v15;
      v18 = (struct _ACL *)operator new(v17, v14);
      pAcl = v18;
      if ( !v18 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          v5 = 0;
          goto LABEL_17;
        }
        v30 = 31;
LABEL_82:
        WPP_SF_(v16->u.APC.hThread, v30, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
        goto LABEL_16;
      }
      if ( !InitializeAcl(v18, v17, 2u) )
      {
        LastError = GetLastError();
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_16;
        }
        v25 = 32;
        goto LABEL_45;
      }
      if ( bDaclPresent )
      {
        v5 = pAcl;
        for ( i = 0; i < pDacl->AceCount; ++i )
        {
          if ( !GetAce(pDacl, i, &pAce) )
          {
            KeySecurity = GetLastError();
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
              && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
            {
              v27 = 33;
              goto LABEL_103;
            }
            goto LABEL_17;
          }
          if ( !AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
          {
            KeySecurity = GetLastError();
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
              && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
            {
              v27 = 34;
              goto LABEL_103;
            }
            goto LABEL_17;
          }
        }
      }
      v19 = pAcl;
      if ( !AddAccessAllowedAceEx(pAcl, 2u, 2u, 0x20019u, a3) )
      {
        v20 = GetLastError();
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_26;
        }
        v31 = 35;
LABEL_107:
        WPP_SF_d(v21->u.APC.hThread, v31, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v20);
LABEL_26:
        v5 = pAcl;
        goto LABEL_17;
      }
      if ( !IsValidAcl(pAcl) )
      {
        v20 = GetLastError();
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_26;
        }
        v31 = 36;
        goto LABEL_107;
      }
    }
    else
    {
      v19 = 0;
    }
    v40 = 0;
    memset(v39, 0, sizeof(v39));
    if ( InitializeSecurityDescriptor(v39, 1u) )
    {
      if ( SetSecurityDescriptorDacl(v39, bDaclPresent, v19, 0) )
      {
        if ( (pControl & 0x1000) != 0 )
          SetSecurityDescriptorControl(v39, 0x1000u, 0x1000u);
        LastError = RegSetKeySecurity(a2, 4u, v39);
        if ( !LastError )
          goto LABEL_16;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_16;
        }
        v25 = 39;
      }
      else
      {
        LastError = GetLastError();
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_16;
        }
        v25 = 38;
      }
    }
    else
    {
      LastError = GetLastError();
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_16;
      }
      v25 = 37;
    }
LABEL_45:
    WPP_SF_d(v24->u.APC.hThread, v25, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, LastError);
LABEL_16:
    v5 = pAcl;
    goto LABEL_17;
  }
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    KeySecurity = GetLastError();
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_17;
    }
    v27 = 25;
    goto LABEL_103;
  }
  if ( !bDaclPresent )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_17;
    }
    v29 = 26;
    goto LABEL_59;
  }
  if ( pDacl )
  {
    AclSize = pDacl->AclSize;
    v15 = GetLengthSid(a3) + 8;
    while ( 1 )
    {
      if ( (unsigned int)v5 >= pDacl->AceCount )
        goto LABEL_19;
      if ( !GetAce(pDacl, (DWORD)v5, &pAce) )
      {
        LastError = GetLastError();
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          v25 = 28;
          goto LABEL_45;
        }
        goto LABEL_16;
      }
      if ( EqualSid((char *)pAce + 8, a3) )
        break;
      LODWORD(v5) = (_DWORD)v5 + 1;
    }
    v14 = (const struct std::nothrow_t *)pAce;
    if ( (*((_DWORD *)pAce + 1) & 0x20019) != 0x20019 )
    {
      v15 = 0;
      *((_DWORD *)pAce + 1) |= 0x20019u;
LABEL_19:
      LODWORD(v5) = AclSize;
      goto LABEL_20;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
    {
      v30 = 29;
      goto LABEL_82;
    }
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
  {
    WPP_SF_SS(
      WPP_GLOBAL_Control->u.APC.hThread,
      27,
      (unsigned int)&WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
      *((_QWORD *)this + 12),
      *((_QWORD *)this + 35));
  }
LABEL_17:
  operator delete(pSecurityDescriptor);
  operator delete(v5);
}

```

## disassembly

```asm
0x1400240d4  mov     dword ptr [rsp-8+pControl], r9d
0x1400240d9  push    rbp
0x1400240da  push    rbx
0x1400240db  push    rsi
0x1400240dc  push    rdi
0x1400240dd  push    r12
0x1400240df  push    r13
0x1400240e1  push    r14
0x1400240e3  push    r15
0x1400240e5  lea     rbp, [rsp-17h]
0x1400240ea  sub     rsp, 98h
0x1400240f1  xor     r14d, r14d
0x1400240f4  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1400240f8  mov     r13, rdx
0x1400240fb  mov     [rbp+4Fh+pControl], r14w
0x140024100  mov     r12, r8
0x140024103  mov     [rbp+4Fh+dwRevision], r14d
0x140024107  mov     rsi, rcx
0x14002410a  mov     [rbp+4Fh+bDaclPresent], r14d
0x14002410e  lea     r15d, [r14+4]
0x140024112  mov     [rbp+4Fh+pDacl], r14
0x140024116  mov     edx, r15d; SecurityInformation
0x140024119  mov     [rbp+4Fh+pAce], r14
0x14002411d  xor     r8d, r8d; pSecurityDescriptor
0x140024120  mov     [rbp+4Fh+pAcl], r14
0x140024124  mov     rcx, r13; hKey
0x140024127  mov     [rbp+4Fh+bDaclDefaulted], r14d
0x14002412b  mov     [rbp+4Fh+cbSecurityDescriptor], r14d
0x14002412f  call    cs:__imp_RegGetKeySecurity
0x140024135  cmp     eax, 7Ah ; 'z'
0x140024138  jnz     loc_14002449F
0x14002413e  mov     ecx, [rbp+4Fh+cbSecurityDescriptor]; Size
0x140024141  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x140024146  mov     [rbp+4Fh+pSecurityDescriptor], rax
0x14002414a  mov     rbx, rax
0x14002414d  test    rax, rax
0x140024150  jz      loc_1400244FC
0x140024156  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14002415a  mov     r8, rax; pSecurityDescriptor
0x14002415d  mov     edx, r15d; SecurityInformation
0x140024160  mov     rcx, r13; hKey
0x140024163  call    cs:__imp_RegGetKeySecurity
0x140024169  test    eax, eax
0x14002416b  jnz     loc_14002454B
0x140024171  lea     r8, [rbp+4Fh+dwRevision]; lpdwRevision
0x140024175  mov     rcx, rbx; pSecurityDescriptor
0x140024178  lea     rdx, [rbp+4Fh+pControl]; pControl
0x14002417c  call    cs:__imp_GetSecurityDescriptorControl
0x140024182  test    eax, eax
0x140024184  jz      loc_140024580
0x14002418a  movzx   eax, [rbp+4Fh+pControl]
0x14002418e  lea     rbx, WPP_GLOBAL_Control
0x140024195  and     eax, r15d
0x140024198  lea     rdi, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14002419f  mov     [rbp+4Fh+bDaclPresent], eax
0x1400241a2  test    byte ptr [rbp+4Fh+pControl], r15b
0x1400241a6  jz      loc_14002436F
0x1400241ac  mov     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1400241b0  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x1400241b4  lea     r8, [rbp+4Fh+pDacl]; pDacl
0x1400241b8  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x1400241bc  call    cs:__imp_GetSecurityDescriptorDacl
0x1400241c2  test    eax, eax
0x1400241c4  jz      loc_140024320
0x1400241ca  cmp     [rbp+4Fh+bDaclPresent], r14d
0x1400241ce  jz      loc_1400245CF
0x1400241d4  mov     rax, [rbp+4Fh+pDacl]
0x1400241d8  test    rax, rax
0x1400241db  jz      loc_1400245F8
0x1400241e1  movzx   r15d, word ptr [rax+2]
0x1400241e6  mov     rcx, r12; pSid
0x1400241e9  call    cs:__imp_GetLengthSid
0x1400241ef  lea     esi, [rax+8]
0x1400241f2  mov     rcx, [rbp+4Fh+pDacl]; pAcl
0x1400241f6  movzx   eax, word ptr [rcx+4]
0x1400241fa  cmp     r14d, eax
0x1400241fd  jnb     loc_14002428F
0x140024203  lea     r8, [rbp+4Fh+pAce]; pAce
0x140024207  mov     edx, r14d; dwAceIndex
0x14002420a  call    cs:__imp_GetAce
0x140024210  test    eax, eax
0x140024212  jz      loc_14002433B
0x140024218  mov     rcx, [rbp+4Fh+pAce]
0x14002421c  mov     rdx, r12; pSid2
0x14002421f  add     rcx, 8; pSid1
0x140024223  call    cs:__imp_EqualSid
0x140024229  test    eax, eax
0x14002422b  jz      short loc_140024287
0x14002422d  mov     rdx, [rbp+4Fh+pAce]
0x140024231  mov     r8d, 20019h
0x140024237  mov     ecx, [rdx+4]
0x14002423a  mov     eax, ecx
0x14002423c  and     eax, r8d
0x14002423f  cmp     eax, r8d
0x140024242  jnz     loc_140024669
0x140024248  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002424f  cmp     rcx, rbx
0x140024252  jz      short loc_14002425E
0x140024254  test    byte ptr [rcx+44h], 4
0x140024258  jnz     loc_140024642
0x14002425e  mov     r14, [rbp+4Fh+pAcl]
0x140024262  mov     rcx, [rbp+4Fh+pSecurityDescriptor]; void *
0x140024266  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002426b  mov     rcx, r14; void *
0x14002426e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140024273  add     rsp, 98h
0x14002427a  pop     r15
0x14002427c  pop     r14
0x14002427e  pop     r13
0x140024280  pop     r12
0x140024282  pop     rdi
0x140024283  pop     rsi
0x140024284  pop     rbx
0x140024285  pop     rbp
0x140024286  retn
0x140024287  inc     r14d
0x14002428a  jmp     loc_1400241F2
0x14002428f  mov     r14d, r15d
0x140024292  mov     r15d, 4
0x140024298  test    esi, esi
0x14002429a  jz      loc_1400247D8
0x1400242a0  add     esi, r14d
0x1400242a3  mov     ecx, esi; Size
0x1400242a5  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x1400242aa  mov     [rbp+4Fh+pAcl], rax
0x1400242ae  test    rax, rax
0x1400242b1  jz      loc_1400246B0
0x1400242b7  mov     r8d, 2; dwAclRevision
0x1400242bd  mov     edx, esi; nAclLength
0x1400242bf  mov     rcx, rax; pAcl
0x1400242c2  call    cs:__imp_InitializeAcl
0x1400242c8  test    eax, eax
0x1400242ca  jz      loc_1400246D0
0x1400242d0  cmp     [rbp+4Fh+bDaclPresent], 0
0x1400242d4  jnz     loc_14002444A
0x1400242da  mov     rsi, [rbp+4Fh+pAcl]
0x1400242de  mov     edx, 2; dwAceRevision
0x1400242e3  mov     r8d, edx; AceFlags
0x1400242e6  mov     [rsp+0D0h+pSid], r12; pSid
0x1400242eb  mov     rcx, rsi; pAcl
0x1400242ee  mov     r9d, 20019h; AccessMask
0x1400242f4  call    cs:__imp_AddAccessAllowedAceEx
0x1400242fa  test    eax, eax
0x1400242fc  jnz     loc_140024394
0x140024302  call    cs:__imp_GetLastError
0x140024308  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002430f  cmp     rcx, rbx
0x140024312  jnz     loc_140024778
0x140024318  mov     r14, rsi
0x14002431b  jmp     loc_140024262
0x140024320  call    cs:__imp_GetLastError
0x140024326  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002432d  cmp     rcx, rbx
0x140024330  jnz     loc_1400245B6
0x140024336  jmp     loc_140024262
0x14002433b  call    cs:__imp_GetLastError
0x140024341  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024348  cmp     rcx, rbx
0x14002434b  jz      loc_14002425E
0x140024351  test    byte ptr [rcx+44h], 4
0x140024355  jz      loc_14002425E
0x14002435b  cmp     byte ptr [rcx+41h], 2
0x14002435f  jb      loc_14002425E
0x140024365  mov     edx, 1Ch
0x14002436a  jmp     loc_140024436
0x14002436f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024376  cmp     rcx, rbx
0x140024379  jnz     loc_140024676
0x14002437f  mov     rcx, r12; pSid
0x140024382  mov     [rbp+4Fh+pDacl], r14
0x140024386  call    cs:__imp_GetLengthSid
0x14002438c  lea     esi, [rax+10h]
0x14002438f  jmp     loc_140024298
0x140024394  mov     rcx, rsi; pAcl
0x140024397  call    cs:__imp_IsValidAcl
0x14002439d  test    eax, eax
0x14002439f  jz      loc_1400247AC
0x1400243a5  xor     eax, eax
0x1400243a7  lea     rcx, [rbp+4Fh+var_70]; pSecurityDescriptor
0x1400243ab  xorps   xmm0, xmm0
0x1400243ae  mov     [rbp+4Fh+var_50], rax
0x1400243b2  movups  [rbp+4Fh+var_70], xmm0
0x1400243b6  lea     edx, [rax+1]; dwRevision
0x1400243b9  movups  [rbp+4Fh+var_60], xmm0
0x1400243bd  call    cs:__imp_InitializeSecurityDescriptor
0x1400243c3  test    eax, eax
0x1400243c5  jz      loc_1400247E1
0x1400243cb  mov     edx, [rbp+4Fh+bDaclPresent]; bDaclPresent
0x1400243ce  lea     rcx, [rbp+4Fh+var_70]; pSecurityDescriptor
0x1400243d2  xor     r9d, r9d; bDaclDefaulted
0x1400243d5  mov     r8, rsi; pDacl
0x1400243d8  call    cs:__imp_SetSecurityDescriptorDacl
0x1400243de  test    eax, eax
0x1400243e0  jz      loc_140024815
0x1400243e6  mov     edx, 1000h; ControlBitsOfInterest
0x1400243eb  test    [rbp+4Fh+pControl], dx
0x1400243ef  jnz     loc_140024849
0x1400243f5  lea     r8, [rbp+4Fh+var_70]; pSecurityDescriptor
0x1400243f9  mov     edx, r15d; SecurityInformation
0x1400243fc  mov     rcx, r13; hKey
0x1400243ff  call    cs:__imp_RegSetKeySecurity
0x140024405  test    eax, eax
0x140024407  jz      loc_14002425E
0x14002440d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024414  cmp     rcx, rbx
0x140024417  jz      loc_14002425E
0x14002441d  test    [rcx+44h], r15b
0x140024421  jz      loc_14002425E
0x140024427  cmp     byte ptr [rcx+41h], 2
0x14002442b  jb      loc_14002425E
0x140024431  mov     edx, 27h ; '''
0x140024436  mov     rcx, [rcx+38h]
0x14002443a  mov     r9d, eax
0x14002443d  mov     r8, rdi
0x140024440  call    WPP_SF_d
0x140024445  jmp     loc_14002425E
0x14002444a  mov     r14, [rbp+4Fh+pAcl]
0x14002444e  xor     esi, esi
0x140024450  mov     rcx, [rbp+4Fh+pDacl]; pAcl
0x140024454  movzx   eax, word ptr [rcx+4]
0x140024458  cmp     esi, eax
0x14002445a  jnb     loc_1400242DA
0x140024460  lea     r8, [rbp+4Fh+pAce]; pAce
0x140024464  mov     edx, esi; dwAceIndex
0x140024466  call    cs:__imp_GetAce
0x14002446c  test    eax, eax
0x14002446e  jz      loc_140024735
0x140024474  mov     r9, [rbp+4Fh+pAce]; pAceList
0x140024478  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14002447c  mov     edx, 2; dwAceRevision
0x140024481  mov     rcx, r14; pAcl
0x140024484  movzx   eax, word ptr [r9+2]
0x140024489  mov     dword ptr [rsp+0D0h+pSid], eax; nAceListLength
0x14002448d  call    cs:__imp_AddAce
0x140024493  test    eax, eax
0x140024495  jz      loc_140024704
0x14002449b  inc     esi
0x14002449d  jmp     short loc_140024450
0x14002449f  mov     [rbp+4Fh+pSecurityDescriptor], r14
0x1400244a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400244aa  lea     rbx, WPP_GLOBAL_Control
0x1400244b1  cmp     rcx, rbx
0x1400244b4  jz      loc_140024336
0x1400244ba  test    [rcx+44h], r15b
0x1400244be  jz      loc_140024336
0x1400244c4  cmp     byte ptr [rcx+41h], 2
0x1400244c8  jb      loc_140024336
0x1400244ce  mov     edx, 15h
0x1400244d3  jmp     short loc_1400244DA
0x1400244d5  mov     edx, 18h
0x1400244da  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x1400244e1  jmp     short loc_1400244EB
0x1400244e3  mov     edx, 19h
0x1400244e8  mov     r8, rdi
0x1400244eb  mov     rcx, [rcx+38h]
0x1400244ef  mov     r9d, eax
0x1400244f2  call    WPP_SF_d
0x1400244f7  jmp     loc_140024336
0x1400244fc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024503  lea     rbx, WPP_GLOBAL_Control
0x14002450a  cmp     rcx, rbx
0x14002450d  jz      loc_140024336
0x140024513  test    [rcx+44h], r15b
0x140024517  jz      loc_140024336
0x14002451d  cmp     byte ptr [rcx+41h], 2
0x140024521  jb      loc_140024336
0x140024527  mov     edx, 16h
0x14002452c  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x140024533  jmp     short loc_14002453D
0x140024535  mov     edx, 1Ah
0x14002453a  mov     r8, rdi
0x14002453d  mov     rcx, [rcx+38h]
0x140024541  call    WPP_SF_
0x140024546  jmp     loc_140024336
0x14002454b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024552  lea     rbx, WPP_GLOBAL_Control
0x140024559  cmp     rcx, rbx
0x14002455c  jz      loc_140024336
0x140024562  test    [rcx+44h], r15b
0x140024566  jz      loc_140024336
0x14002456c  cmp     byte ptr [rcx+41h], 2
0x140024570  jb      loc_140024336
0x140024576  mov     edx, 17h
0x14002457b  jmp     loc_1400244DA
0x140024580  call    cs:__imp_GetLastError
0x140024586  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002458d  lea     rbx, WPP_GLOBAL_Control
0x140024594  cmp     rcx, rbx
0x140024597  jz      loc_140024336
0x14002459d  test    [rcx+44h], r15b
0x1400245a1  jz      loc_140024336
0x1400245a7  cmp     byte ptr [rcx+41h], 2
0x1400245ab  jb      loc_140024336
0x1400245b1  jmp     loc_1400244D5
0x1400245b6  test    [rcx+44h], r15b
0x1400245ba  jz      loc_140024336
0x1400245c0  cmp     byte ptr [rcx+41h], 2
0x1400245c4  jb      loc_140024336
0x1400245ca  jmp     loc_1400244E3
0x1400245cf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
  ... truncated ...
```
