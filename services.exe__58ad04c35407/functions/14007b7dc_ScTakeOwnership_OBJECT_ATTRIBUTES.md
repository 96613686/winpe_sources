# ScTakeOwnership(_OBJECT_ATTRIBUTES *)

- ea: `0x14007b7dc`
- end: `0x14007be21`
- name: `?ScTakeOwnership@@YAKPEAU_OBJECT_ATTRIBUTES@@@Z`
- size: `1605`
- prototype: `unsigned int __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000a050`
- `0x14000bcc4`
- `0x14000bebc`
- `0x140015020`

## callees

- `0x140004c58`
- `0x140013b0c`
- `0x1400188fc`
- `0x14007b7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007b891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007b8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bbef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bc7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bcd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bd5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007b891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007b8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bbef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bc7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bcd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bd5a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14007bb19`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14007bb19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14007b8dc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x14007b8dc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14007b887`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14007bd11`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14007b887`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14007bd11`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14007bd50`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14007bd50`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14007bcc6`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14007bcc6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14007bbe5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14007bbe5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14007bc72`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14007bc72`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14007bb56`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14007bbd5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14007bb56`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14007bbd5`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14007b920`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14007bd93`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14007b920`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14007bd93`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14007b9b6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14007ba61`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14007b9b6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14007ba61`
- `ntdll!NtClose` at `0x14007b962`
- `ntdll!NtClose` at `0x14007bae7`
- `ntdll!NtClose` at `0x14007b962`
- `ntdll!NtClose` at `0x14007bae7`
- `ntdll!RtlNtStatusToDosError` at `0x14007b871`
- `ntdll!RtlNtStatusToDosError` at `0x14007b871`
- `ntdll!RtlFreeHeap` at `0x14007baac`
- `ntdll!RtlFreeHeap` at `0x14007bac4`
- `ntdll!RtlFreeHeap` at `0x14007badd`
- `ntdll!RtlFreeHeap` at `0x14007baac`
- `ntdll!RtlFreeHeap` at `0x14007bac4`
- `ntdll!RtlFreeHeap` at `0x14007badd`
- `ntdll!NtOpenKey` at `0x14007b82d`
- `ntdll!NtOpenKey` at `0x14007b974`
- `ntdll!NtOpenKey` at `0x14007b82d`
- `ntdll!NtOpenKey` at `0x14007b974`
- `ntdll!RtlAllocateHeap` at `0x14007ba09`
- `ntdll!RtlAllocateHeap` at `0x14007bb7b`
- `ntdll!RtlAllocateHeap` at `0x14007bc31`
- `ntdll!RtlAllocateHeap` at `0x14007ba09`
- `ntdll!RtlAllocateHeap` at `0x14007bb7b`
- `ntdll!RtlAllocateHeap` at `0x14007bc31`

## pseudocode

```c
ULONG __fastcall ScTakeOwnership(POBJECT_ATTRIBUTES ObjectAttributes)
{
  unsigned __int16 *v1; // r12
  int v3; // ebx
  PRPC_ASYNC_STATE v4; // rcx
  __int64 v5; // rdx
  DWORD LastError; // ebx
  PRPC_ASYNC_STATE v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // eax
  unsigned int KeySecurity; // eax
  PVOID Heap; // rax
  void *v14; // r15
  DWORD v15; // eax
  PRPC_ASYNC_STATE v16; // rcx
  __int64 v17; // rdx
  struct _ACL *v18; // r15
  DWORD v19; // ebx
  unsigned __int16 *v20; // rax
  PRPC_ASYNC_STATE v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  PSID v24; // rbx
  DWORD LengthSid; // eax
  DWORD v26; // eax
  DWORD v27; // ebx
  struct _ACL *v28; // rax
  DWORD v29; // eax
  PRPC_ASYNC_STATE v30; // rcx
  __int64 v31; // rdx
  DWORD v32; // [rsp+30h] [rbp-50h]
  struct _ACL *pAcl; // [rsp+38h] [rbp-48h]
  void *KeyHandle; // [rsp+40h] [rbp-40h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-38h] BYREF
  PVOID P; // [rsp+50h] [rbp-30h]
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v38; // [rsp+78h] [rbp-8h]
  DWORD cbSecurityDescriptor; // [rsp+C8h] [rbp+48h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+D0h] [rbp+50h] BYREF
  WINBOOL bDaclPresent; // [rsp+D8h] [rbp+58h] BYREF

  v1 = 0;
  KeyHandle = 0;
  cbSecurityDescriptor = 0;
  v38 = 0;
  bDaclPresent = 0;
  pDacl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  bDaclDefaulted = 0;
  v3 = NtOpenKey(&KeyHandle, 0x80000u, ObjectAttributes);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return RtlNtStatusToDosError(v3);
    v5 = 140;
LABEL_5:
    WPP_SF_d(v4->StubInfo, v5, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v3);
    return RtlNtStatusToDosError(v3);
  }
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_41;
    v9 = 141;
    goto LABEL_11;
  }
  if ( SetSecurityDescriptorOwner(pSecurityDescriptor, LocalSystemSid, 0) )
  {
    v11 = RegSetKeySecurity((HKEY)KeyHandle, 1u, pSecurityDescriptor);
    if ( v11
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 143, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v11);
    }
    NtClose(KeyHandle);
    v3 = NtOpenKey(&KeyHandle, 0x60000u, ObjectAttributes);
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return RtlNtStatusToDosError(v3);
      v5 = 144;
      goto LABEL_5;
    }
    KeySecurity = RegGetKeySecurity((HKEY)KeyHandle, 4u, 0, &cbSecurityDescriptor);
    LastError = KeySecurity;
    if ( KeySecurity != 122 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_41;
      v9 = 145;
      v10 = KeySecurity;
      goto LABEL_28;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, cbSecurityDescriptor);
    P = Heap;
    v14 = Heap;
    if ( !Heap )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 146, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, 8);
      LastError = 8;
      goto LABEL_41;
    }
    pAcl = 0;
    v15 = RegGetKeySecurity((HKEY)KeyHandle, 4u, Heap, &cbSecurityDescriptor);
    LastError = v15;
    if ( v15 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_39;
      v17 = 147;
LABEL_38:
      WPP_SF_d(v16->StubInfo, v17, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v15);
LABEL_39:
      v18 = 0;
      goto LABEL_40;
    }
    if ( !GetSecurityDescriptorDacl(v14, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v15 = GetLastError();
      LastError = v15;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_39;
      v17 = 148;
      goto LABEL_38;
    }
    v19 = GetLengthSid(LocalSystemSid) + 8;
    v32 = v19;
    v20 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v19);
    v1 = v20;
    if ( !v20 )
    {
      LastError = 8;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_52;
      v22 = 149;
      goto LABEL_50;
    }
    *v20 = 512;
    v20[1] = v19;
    *((_DWORD *)v20 + 1) = 0x10000000;
    v24 = LocalSystemSid;
    LengthSid = GetLengthSid(LocalSystemSid);
    if ( CopySid(LengthSid, v1 + 4, v24) )
    {
      v27 = v32 + pDacl->AclSize;
      v28 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v27);
      pAcl = v28;
      if ( !v28 )
      {
        LastError = 8;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          v18 = 0;
          goto LABEL_40;
        }
        v22 = 151;
LABEL_50:
        v23 = 8;
LABEL_51:
        WPP_SF_d(v21->StubInfo, v22, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v23);
        goto LABEL_52;
      }
      if ( InitializeAcl(v28, v27, 2u) )
      {
        v18 = pAcl;
        if ( AddAce(pAcl, pDacl->AclRevision, 0, v1, v1[1]) )
        {
          if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pAcl, 0) )
            {
              v29 = RegSetKeySecurity((HKEY)KeyHandle, 4u, pSecurityDescriptor);
              LastError = v29;
              if ( !v29 )
              {
                if ( *(_DWORD *)&g_fEnableTakeOwnershipEvent == 1 )
                {
                  ScLogEvent(0x1Cu, ObjectAttributes->ObjectName->Buffer);
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x20) != 0 )
                  {
                    WPP_SF_S(
                      WPP_GLOBAL_Control->StubInfo,
                      157,
                      WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
                      ObjectAttributes->ObjectName->Buffer);
                  }
                }
                goto LABEL_40;
              }
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
LABEL_40:
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                goto LABEL_41;
              }
              v31 = 156;
            }
            else
            {
              v29 = GetLastError();
              LastError = v29;
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
                goto LABEL_40;
              }
              v31 = 155;
            }
          }
          else
          {
            v29 = GetLastError();
            LastError = v29;
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v31 = 154;
          }
        }
        else
        {
          v29 = GetLastError();
          LastError = v29;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_40;
          }
          v31 = 153;
        }
        WPP_SF_d(v30->StubInfo, v31, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v29);
        goto LABEL_40;
      }
      v26 = GetLastError();
      LastError = v26;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      {
LABEL_52:
        v18 = pAcl;
        goto LABEL_40;
      }
      v22 = 152;
    }
    else
    {
      v26 = GetLastError();
      LastError = v26;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_52;
      v22 = 150;
    }
    v23 = v26;
    goto LABEL_51;
  }
  LastError = GetLastError();
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
    goto LABEL_41;
  v9 = 142;
LABEL_11:
  v10 = LastError;
LABEL_28:
  WPP_SF_d(v8->StubInfo, v9, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v10);
LABEL_41:
  NtClose(KeyHandle);
  return LastError;
}

```

## disassembly

```asm
0x14007b7dc  mov     [rsp-38h+arg_0], rbx
0x14007b7e1  push    rbp
0x14007b7e2  push    rsi
0x14007b7e3  push    rdi
0x14007b7e4  push    r12
0x14007b7e6  push    r13
0x14007b7e8  push    r14
0x14007b7ea  push    r15
0x14007b7ec  mov     rbp, rsp
0x14007b7ef  sub     rsp, 80h
0x14007b7f6  xor     r12d, r12d
0x14007b7f9  xorps   xmm0, xmm0
0x14007b7fc  mov     r13, rcx
0x14007b7ff  mov     [rbp+KeyHandle], r12
0x14007b803  xor     eax, eax
0x14007b805  mov     [rbp+cbSecurityDescriptor], r12d
0x14007b809  mov     r8, rcx; ObjectAttributes
0x14007b80c  mov     [rbp+var_8], rax
0x14007b810  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14007b814  mov     [rbp+bDaclPresent], r12d
0x14007b818  mov     edx, 80000h; DesiredAccess
0x14007b81d  mov     [rbp+pDacl], r12
0x14007b821  movups  [rbp+pSecurityDescriptor], xmm0
0x14007b825  mov     [rbp+bDaclDefaulted], r12d
0x14007b829  movups  [rbp+var_18], xmm0
0x14007b82d  call    cs:__imp_NtOpenKey
0x14007b833  mov     ebx, eax
0x14007b835  test    eax, eax
0x14007b837  jns     short loc_14007B87C
0x14007b839  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b840  lea     rsi, WPP_GLOBAL_Control
0x14007b847  cmp     rcx, rsi
0x14007b84a  jz      short loc_14007B86F
0x14007b84c  lea     edi, [r12+1]
0x14007b851  test    [rcx+1Ch], dil
0x14007b855  jz      short loc_14007B86F
0x14007b857  mov     edx, 8Ch
0x14007b85c  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007b863  mov     rcx, [rcx+10h]
0x14007b867  mov     r9d, ebx
0x14007b86a  call    WPP_SF_d
0x14007b86f  mov     ecx, ebx; Status
0x14007b871  call    cs:__imp_RtlNtStatusToDosError
0x14007b877  jmp     loc_14007BAEF
0x14007b87c  mov     edi, 1
0x14007b881  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14007b885  mov     edx, edi; dwRevision
0x14007b887  call    cs:__imp_InitializeSecurityDescriptor
0x14007b88d  test    eax, eax
0x14007b88f  jnz     short loc_14007B8CE
0x14007b891  call    cs:__imp_GetLastError
0x14007b897  mov     ebx, eax
0x14007b899  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b8a0  lea     rsi, WPP_GLOBAL_Control
0x14007b8a7  cmp     rcx, rsi
0x14007b8aa  jz      loc_14007BAE3
0x14007b8b0  test    [rcx+1Ch], dil
0x14007b8b4  jz      loc_14007BAE3
0x14007b8ba  mov     edx, 8Dh
0x14007b8bf  mov     r9d, ebx
0x14007b8c2  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007b8c9  jmp     loc_14007B9E8
0x14007b8ce  mov     rdx, cs:LocalSystemSid; pOwner
0x14007b8d5  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14007b8d9  xor     r8d, r8d; bOwnerDefaulted
0x14007b8dc  call    cs:__imp_SetSecurityDescriptorOwner
0x14007b8e2  test    eax, eax
0x14007b8e4  jnz     short loc_14007B916
0x14007b8e6  call    cs:__imp_GetLastError
0x14007b8ec  mov     ebx, eax
0x14007b8ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b8f5  lea     rsi, WPP_GLOBAL_Control
0x14007b8fc  cmp     rcx, rsi
0x14007b8ff  jz      loc_14007BAE3
0x14007b905  test    [rcx+1Ch], dil
0x14007b909  jz      loc_14007BAE3
0x14007b90f  mov     edx, 8Eh
0x14007b914  jmp     short loc_14007B8BF
0x14007b916  mov     rcx, [rbp+KeyHandle]; hKey
0x14007b91a  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14007b91e  mov     edx, edi; SecurityInformation
0x14007b920  call    cs:__imp_RegSetKeySecurity
0x14007b926  lea     r14, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007b92d  lea     rsi, WPP_GLOBAL_Control
0x14007b934  test    eax, eax
0x14007b936  jz      short loc_14007B95E
0x14007b938  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b93f  cmp     rcx, rsi
0x14007b942  jz      short loc_14007B95E
0x14007b944  test    [rcx+1Ch], dil
0x14007b948  jz      short loc_14007B95E
0x14007b94a  mov     rcx, [rcx+10h]
0x14007b94e  mov     edx, 8Fh
0x14007b953  mov     r9d, eax
0x14007b956  mov     r8, r14
0x14007b959  call    WPP_SF_d
0x14007b95e  mov     rcx, [rbp+KeyHandle]; Handle
0x14007b962  call    cs:__imp_NtClose
0x14007b968  mov     r8, r13; ObjectAttributes
0x14007b96b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14007b96f  mov     edx, 60000h; DesiredAccess
0x14007b974  call    cs:__imp_NtOpenKey
0x14007b97a  mov     ebx, eax
0x14007b97c  test    eax, eax
0x14007b97e  jns     short loc_14007B9A7
0x14007b980  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b987  cmp     rcx, rsi
0x14007b98a  jz      loc_14007B86F
0x14007b990  test    [rcx+1Ch], dil
0x14007b994  jz      loc_14007B86F
0x14007b99a  mov     edx, 90h
0x14007b99f  mov     r8, r14
0x14007b9a2  jmp     loc_14007B863
0x14007b9a7  mov     rcx, [rbp+KeyHandle]; hKey
0x14007b9ab  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14007b9af  xor     r8d, r8d; pSecurityDescriptor
0x14007b9b2  lea     edx, [r8+4]; SecurityInformation
0x14007b9b6  call    cs:__imp_RegGetKeySecurity
0x14007b9bc  mov     ebx, eax
0x14007b9be  cmp     eax, 7Ah ; 'z'
0x14007b9c1  jz      short loc_14007B9F6
0x14007b9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b9ca  cmp     rcx, rsi
0x14007b9cd  jz      loc_14007BAE3
0x14007b9d3  test    [rcx+1Ch], dil
0x14007b9d7  jz      loc_14007BAE3
0x14007b9dd  mov     edx, 91h
0x14007b9e2  mov     r9d, eax
0x14007b9e5  mov     r8, r14
0x14007b9e8  mov     rcx, [rcx+10h]
0x14007b9ec  call    WPP_SF_d
0x14007b9f1  jmp     loc_14007BAE3
0x14007b9f6  mov     rcx, gs:60h
0x14007b9ff  xor     edx, edx; Flags
0x14007ba01  mov     r8d, [rbp+cbSecurityDescriptor]; Size
0x14007ba05  mov     rcx, [rcx+30h]; HeapHandle
0x14007ba09  call    cs:__imp_RtlAllocateHeap
0x14007ba0f  mov     [rbp+P], rax
0x14007ba13  mov     r15, rax
0x14007ba16  test    rax, rax
0x14007ba19  jnz     short loc_14007BA4D
0x14007ba1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ba22  lea     r15d, [rax+8]
0x14007ba26  cmp     rcx, rsi
0x14007ba29  jz      short loc_14007BA45
0x14007ba2b  test    [rcx+1Ch], dil
0x14007ba2f  jz      short loc_14007BA45
0x14007ba31  mov     rcx, [rcx+10h]
0x14007ba35  mov     edx, 92h
0x14007ba3a  mov     r9d, r15d
0x14007ba3d  mov     r8, r14
0x14007ba40  call    WPP_SF_d
0x14007ba45  mov     ebx, r15d
0x14007ba48  jmp     loc_14007BAE3
0x14007ba4d  mov     rcx, [rbp+KeyHandle]; hKey
0x14007ba51  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14007ba55  mov     r8, r15; pSecurityDescriptor
0x14007ba58  mov     [rbp+pAcl], r12
0x14007ba5c  mov     edx, 4; SecurityInformation
0x14007ba61  call    cs:__imp_RegGetKeySecurity
0x14007ba67  mov     ebx, eax
0x14007ba69  test    eax, eax
0x14007ba6b  jz      loc_14007BB0A
0x14007ba71  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ba78  cmp     rcx, rsi
0x14007ba7b  jz      short loc_14007BA97
0x14007ba7d  test    [rcx+1Ch], dil
0x14007ba81  jz      short loc_14007BA97
0x14007ba83  mov     edx, 93h
0x14007ba88  mov     rcx, [rcx+10h]
0x14007ba8c  mov     r9d, eax
0x14007ba8f  mov     r8, r14
0x14007ba92  call    WPP_SF_d
0x14007ba97  mov     r15, r12
0x14007ba9a  mov     rcx, gs:60h
0x14007baa3  mov     r8, r15; P
0x14007baa6  xor     edx, edx; Flags
0x14007baa8  mov     rcx, [rcx+30h]; HeapHandle
0x14007baac  call    cs:__imp_RtlFreeHeap
0x14007bab2  mov     rcx, gs:60h
0x14007babb  mov     r8, r12; P
0x14007babe  xor     edx, edx; Flags
0x14007bac0  mov     rcx, [rcx+30h]; HeapHandle
0x14007bac4  call    cs:__imp_RtlFreeHeap
0x14007baca  mov     rcx, gs:60h
0x14007bad3  xor     edx, edx; Flags
0x14007bad5  mov     r8, [rbp+P]; P
0x14007bad9  mov     rcx, [rcx+30h]; HeapHandle
0x14007badd  call    cs:__imp_RtlFreeHeap
0x14007bae3  mov     rcx, [rbp+KeyHandle]; Handle
0x14007bae7  call    cs:__imp_NtClose
0x14007baed  mov     eax, ebx
0x14007baef  mov     rbx, [rsp+80h+arg_0]
0x14007baf7  add     rsp, 80h
0x14007bafe  pop     r15
0x14007bb00  pop     r14
0x14007bb02  pop     r13
0x14007bb04  pop     r12
0x14007bb06  pop     rdi
0x14007bb07  pop     rsi
0x14007bb08  pop     rbp
0x14007bb09  retn
0x14007bb0a  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x14007bb0e  mov     rcx, r15; pSecurityDescriptor
0x14007bb11  lea     r8, [rbp+pDacl]; pDacl
0x14007bb15  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x14007bb19  call    cs:__imp_GetSecurityDescriptorDacl
0x14007bb1f  test    eax, eax
0x14007bb21  jnz     short loc_14007BB4F
0x14007bb23  call    cs:__imp_GetLastError
0x14007bb29  mov     ebx, eax
0x14007bb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb32  cmp     rcx, rsi
0x14007bb35  jz      loc_14007BA97
0x14007bb3b  test    [rcx+1Ch], dil
0x14007bb3f  jz      loc_14007BA97
0x14007bb45  mov     edx, 94h
0x14007bb4a  jmp     loc_14007BA88
0x14007bb4f  mov     rcx, cs:LocalSystemSid; pSid
0x14007bb56  call    cs:__imp_GetLengthSid
0x14007bb5c  mov     rcx, gs:60h
0x14007bb65  mov     r15d, 8
0x14007bb6b  mov     edx, r15d; Flags
0x14007bb6e  lea     ebx, [rax+8]
0x14007bb71  mov     rcx, [rcx+30h]; HeapHandle
0x14007bb75  mov     r8d, ebx; Size
0x14007bb78  mov     [rbp+var_50], ebx
0x14007bb7b  call    cs:__imp_RtlAllocateHeap
0x14007bb81  mov     r12, rax
0x14007bb84  test    rax, rax
0x14007bb87  jnz     short loc_14007BBBB
0x14007bb89  mov     ebx, r15d
0x14007bb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb93  cmp     rcx, rsi
0x14007bb96  jz      short loc_14007BBB2
0x14007bb98  test    [rcx+1Ch], dil
0x14007bb9c  jz      short loc_14007BBB2
0x14007bb9e  mov     edx, 95h
0x14007bba3  mov     r9d, r15d
0x14007bba6  mov     rcx, [rcx+10h]
0x14007bbaa  mov     r8, r14
0x14007bbad  call    WPP_SF_d
0x14007bbb2  mov     r15, [rbp+pAcl]
0x14007bbb6  jmp     loc_14007BA9A
0x14007bbbb  mov     word ptr [rax], 200h
0x14007bbc0  mov     [rax+2], bx
0x14007bbc4  mov     dword ptr [rax+4], 10000000h
0x14007bbcb  mov     rbx, cs:LocalSystemSid
0x14007bbd2  mov     rcx, rbx; pSid
0x14007bbd5  call    cs:__imp_GetLengthSid
0x14007bbdb  lea     rdx, [r12+8]; pDestinationSid
0x14007bbe0  mov     r8, rbx; pSourceSid
0x14007bbe3  mov     ecx, eax; nDestinationSidLength
0x14007bbe5  call    cs:__imp_CopySid
0x14007bbeb  test    eax, eax
0x14007bbed  jnz     short loc_14007BC13
0x14007bbef  call    cs:__imp_GetLastError
0x14007bbf5  mov     ebx, eax
0x14007bbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bbfe  cmp     rcx, rsi
0x14007bc01  jz      short loc_14007BBB2
0x14007bc03  test    [rcx+1Ch], dil
0x14007bc07  jz      short loc_14007BBB2
0x14007bc09  mov     edx, 96h
0x14007bc0e  mov     r9d, eax
0x14007bc11  jmp     short loc_14007BBA6
0x14007bc13  mov     rax, [rbp+pDacl]
0x14007bc17  mov     edx, r15d; Flags
0x14007bc1a  mov     rcx, gs:60h
0x14007bc23  movzx   ebx, word ptr [rax+2]
0x14007bc27  add     ebx, [rbp+var_50]
0x14007bc2a  mov     rcx, [rcx+30h]; HeapHandle
0x14007bc2e  mov     r8d, ebx; Size
0x14007bc31  call    cs:__imp_RtlAllocateHeap
0x14007bc37  mov     [rbp+pAcl], rax
0x14007bc3b  mov     rcx, rax; pAcl
0x14007bc3e  test    rax, rax
0x14007bc41  jnz     short loc_14007BC6A
0x14007bc43  mov     ebx, r15d
0x14007bc46  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bc4d  cmp     rcx, rsi
0x14007bc50  jz      loc_14007BE19
0x14007bc56  test    [rcx+1Ch], dil
0x14007bc5a  jz      loc_14007BE19
0x14007bc60  mov     edx, 97h
0x14007bc65  jmp     loc_14007BBA3
0x14007bc6a  mov     r8d, 2; dwAclRevision
0x14007bc70  mov     edx, ebx; nAclLength
0x14007bc72  call    cs:__imp_InitializeAcl
0x14007bc78  test    eax, eax
0x14007bc7a  jnz     short loc_14007BCA8
0x14007bc7c  call    cs:__imp_GetLastError
0x14007bc82  mov     ebx, eax
0x14007bc84  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bc8b  cmp     rcx, rsi
0x14007bc8e  jz      loc_14007BBB2
0x14007bc94  test    [rcx+1Ch], dil
0x14007bc98  jz      loc_14007BBB2
0x14007bc9e  mov     edx, 98h
0x14007bca3  jmp     loc_14007BC0E
  ... truncated ...
```
