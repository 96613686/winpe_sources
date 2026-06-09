# PrepareStiAcl(_ACL * *)

- ea: `0x18002b5b0`
- end: `0x18002ba8c`
- name: `?PrepareStiAcl@@YAJPEAPEAU_ACL@@@Z`
- size: `1244`
- prototype: `__int64 __fastcall(struct _ACL **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ba94`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002b5b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x18004f008`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002ba65`
- `KERNEL32!HeapFree` at `0x18002ba65`
- `KERNEL32!LocalFree` at `0x18002b9ff`
- `KERNEL32!LocalFree` at `0x18002ba13`
- `KERNEL32!LocalFree` at `0x18002ba31`
- `KERNEL32!LocalFree` at `0x18002ba45`
- `KERNEL32!LocalFree` at `0x18002b9ff`
- `KERNEL32!LocalFree` at `0x18002ba13`
- `KERNEL32!LocalFree` at `0x18002ba31`
- `KERNEL32!LocalFree` at `0x18002ba45`
- `KERNEL32!GetProcessHeap` at `0x18002b7df`
- `KERNEL32!GetProcessHeap` at `0x18002ba57`
- `KERNEL32!GetProcessHeap` at `0x18002b7df`
- `KERNEL32!GetProcessHeap` at `0x18002ba57`
- `KERNEL32!GetLastError` at `0x18002b640`
- `KERNEL32!GetLastError` at `0x18002b6ca`
- `KERNEL32!GetLastError` at `0x18002b73b`
- `KERNEL32!GetLastError` at `0x18002b7fe`
- `KERNEL32!GetLastError` at `0x18002b84f`
- `KERNEL32!GetLastError` at `0x18002b8a7`
- `KERNEL32!GetLastError` at `0x18002b901`
- `KERNEL32!GetLastError` at `0x18002b968`
- `KERNEL32!GetLastError` at `0x18002b640`
- `KERNEL32!GetLastError` at `0x18002b6ca`
- `KERNEL32!GetLastError` at `0x18002b73b`
- `KERNEL32!GetLastError` at `0x18002b7fe`
- `KERNEL32!GetLastError` at `0x18002b84f`
- `KERNEL32!GetLastError` at `0x18002b8a7`
- `KERNEL32!GetLastError` at `0x18002b901`
- `KERNEL32!GetLastError` at `0x18002b968`
- `KERNEL32!HeapAlloc` at `0x18002b7f0`
- `KERNEL32!HeapAlloc` at `0x18002b7f0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b636`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b6c0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b636`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b6c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b9c3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b9d2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b9c3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b9d2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002b845`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002b845`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7b9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7c5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7b9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7c5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b7d4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002b89d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002b8f7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002b95e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002b89d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002b8f7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002b95e`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18002b731`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18002b731`

## string_xrefs

- `0x18002b648`: `PrepareStiAcl: failed to allocate SID for BuiltinAdministrators, RpcStatus = %d`
- `0x18002b672`: `PrepareStiAcl: failed to allocate SID for BuiltinAdministrators, RpcStatus = %d`
- `0x18002b6d2`: `PrepareStiAcl: failed to allocate SID for AuthenticatedUsers, RpcStatus = %d`
- `0x18002b6fa`: `PrepareStiAcl: failed to allocate SID for AuthenticatedUsers, RpcStatus = %d`
- `0x18002b659`: `PrepareStiAcl`
- `0x18002b6e3`: `PrepareStiAcl`
- `0x18002b754`: `PrepareStiAcl`
- `0x18002b792`: `PrepareStiAcl`
- `0x18002b817`: `PrepareStiAcl`
- `0x18002b868`: `PrepareStiAcl`
- `0x18002b8c0`: `PrepareStiAcl`
- `0x18002b91a`: `PrepareStiAcl`
- `0x18002b981`: `PrepareStiAcl`
- `0x18002b9ae`: `PrepareStiAcl`
- `0x18002b743`: `PrepareStiAcl: failed to derive isolatedWin32-Scanner capability SIDs, RpcStatus = %d`
- `0x18002b76b`: `PrepareStiAcl: failed to derive isolatedWin32-Scanner capability SIDs, RpcStatus = %d`
- `0x18002b806`: `PrepareStiAcl: failed to allocate ACL (LastError = %d)`
- `0x18002b82e`: `PrepareStiAcl: failed to allocate ACL (LastError = %d)`
- `0x18002b783`: `PrepareStiAcl: derived unexpected number of capability or group SIDs, RpcStatus = %d`
- `0x18002b7a9`: `PrepareStiAcl: derived unexpected number of capability or group SIDs, RpcStatus = %d`
- `0x18002b8af`: `PrepareStiAcl: failed to allow AuthenticatedUsers (LastError = %d)`
- `0x18002b8d7`: `PrepareStiAcl: failed to allow AuthenticatedUsers (LastError = %d)`
- `0x18002b857`: `PrepareStiAcl: failed to initialize ACL (LastError = %d)`
- `0x18002b87f`: `PrepareStiAcl: failed to initialize ACL (LastError = %d)`
- `0x18002b970`: `PrepareStiAcl: failed to allow win32-Scanner capability (LastError = %d)`
- `0x18002b998`: `PrepareStiAcl: failed to allow win32-Scanner capability (LastError = %d)`
- `0x18002b909`: `PrepareStiAcl: failed to allow BuiltinAdministrators (LastError = %d)`
- `0x18002b931`: `PrepareStiAcl: failed to allow BuiltinAdministrators (LastError = %d)`

## pseudocode

```c
__int64 __fastcall PrepareStiAcl(struct _ACL **a1)
{
  DWORD LastError; // edi
  char *v3; // rbx
  void *v4; // rdx
  void *v5; // rax
  int v6; // edx
  int v7; // ecx
  __int64 v8; // rdx
  char *v9; // rbx
  void *v10; // rdx
  char *v11; // rbx
  void *v12; // rdx
  char *v13; // rbx
  void *v14; // rdx
  DWORD LengthSid; // edi
  DWORD v16; // edi
  DWORD v17; // edi
  HANDLE ProcessHeap; // rax
  struct _ACL *v19; // rax
  char *v20; // rbx
  void *v21; // rdx
  char *v22; // rbx
  void *v23; // rdx
  char *v24; // rbx
  void *v25; // rdx
  __int64 v26; // rdx
  char *v27; // rbx
  void *v28; // rdx
  __int64 v29; // rdx
  char *v30; // rbx
  void *v31; // rdx
  HLOCAL *v32; // rax
  unsigned int i; // ebx
  HLOCAL *v34; // rax
  unsigned int j; // ebx
  PACL v36; // rbx
  HANDLE v37; // rax
  unsigned int v39; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v40; // [rsp+64h] [rbp-15h] BYREF
  HLOCAL v41; // [rsp+68h] [rbp-11h] BYREF
  PSID v42; // [rsp+70h] [rbp-9h] BYREF
  PSID pSid; // [rsp+78h] [rbp-1h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  LastError = 5;
  v42 = 0;
  pSid = 0;
  hMem = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &v42) )
    {
      LOBYTE(v8) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
        v8);
      if ( (unsigned int)DeriveCapabilitySidsFromName(L"isolatedWin32-scanner", &hMem, &v39, &v41, &v40) )
      {
        if ( v40 == 1 || v39 == 1 )
        {
          LengthSid = GetLengthSid(pSid);
          v16 = GetLengthSid(v42) + LengthSid;
          v17 = GetLengthSid(*(PSID *)v41) + 32 + v16;
          ProcessHeap = GetProcessHeap();
          v19 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v17);
          *a1 = v19;
          if ( v19 )
          {
            if ( InitializeAcl(v19, v17, 2u) )
            {
              if ( AddAccessAllowedAce(*a1, 2u, 0xC0100000, v42) )
              {
                if ( AddAccessAllowedAce(*a1, 2u, 0x10000000u, pSid) )
                {
                  LOBYTE(v26) = 1;
                  LastError = 0;
                  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
                    `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
                    v26);
                  if ( AddAccessAllowedAce(*a1, 2u, 0x10000000u, *(PSID *)v41) )
                    goto LABEL_21;
                  LastError = GetLastError();
                  v30 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to allow win32-Scanner capability (LastError = %d)");
                  WriteDbgTraceErrorWI("PrepareStiAcl", v30);
                  WiaTrcLib::Free((WiaTrcLib *)v30, v31);
                  v5 = (void *)WiaTrace_Trace(
                                 "PrepareStiAcl: failed to allow win32-Scanner capability (LastError = %d)",
                                 LastError);
                }
                else
                {
                  LastError = GetLastError();
                  v27 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to allow BuiltinAdministrators (LastError = %d)");
                  WriteDbgTraceErrorWI("PrepareStiAcl", v27);
                  WiaTrcLib::Free((WiaTrcLib *)v27, v28);
                  v5 = (void *)WiaTrace_Trace(
                                 "PrepareStiAcl: failed to allow BuiltinAdministrators (LastError = %d)",
                                 LastError);
                }
              }
              else
              {
                LastError = GetLastError();
                v24 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to allow AuthenticatedUsers (LastError = %d)");
                WriteDbgTraceErrorWI("PrepareStiAcl", v24);
                WiaTrcLib::Free((WiaTrcLib *)v24, v25);
                v5 = (void *)WiaTrace_Trace(
                               "PrepareStiAcl: failed to allow AuthenticatedUsers (LastError = %d)",
                               LastError);
              }
            }
            else
            {
              LastError = GetLastError();
              v22 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to initialize ACL (LastError = %d)");
              WriteDbgTraceErrorWI("PrepareStiAcl", v22);
              WiaTrcLib::Free((WiaTrcLib *)v22, v23);
              v5 = (void *)WiaTrace_Trace("PrepareStiAcl: failed to initialize ACL (LastError = %d)", LastError);
            }
          }
          else
          {
            LastError = GetLastError();
            v20 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to allocate ACL (LastError = %d)");
            WriteDbgTraceErrorWI("PrepareStiAcl", v20);
            WiaTrcLib::Free((WiaTrcLib *)v20, v21);
            v5 = (void *)WiaTrace_Trace("PrepareStiAcl: failed to allocate ACL (LastError = %d)", LastError);
          }
        }
        else
        {
          v13 = (char *)WiaTrace_TraceLog("PrepareStiAcl: derived unexpected number of capability or group SIDs, RpcStatus = %d");
          WriteDbgTraceErrorWI("PrepareStiAcl", v13);
          WiaTrcLib::Free((WiaTrcLib *)v13, v14);
          v5 = (void *)WiaTrace_Trace(
                         "PrepareStiAcl: derived unexpected number of capability or group SIDs, RpcStatus = %d",
                         5);
        }
      }
      else
      {
        LastError = GetLastError();
        v11 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to derive isolatedWin32-Scanner capability SIDs, RpcStatus = %d");
        WriteDbgTraceErrorWI("PrepareStiAcl", v11);
        WiaTrcLib::Free((WiaTrcLib *)v11, v12);
        v5 = (void *)WiaTrace_Trace(
                       "PrepareStiAcl: failed to derive isolatedWin32-Scanner capability SIDs, RpcStatus = %d",
                       LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to allocate SID for AuthenticatedUsers, RpcStatus = %d");
      WriteDbgTraceErrorWI("PrepareStiAcl", v9);
      WiaTrcLib::Free((WiaTrcLib *)v9, v10);
      v5 = (void *)WiaTrace_Trace(
                     "PrepareStiAcl: failed to allocate SID for AuthenticatedUsers, RpcStatus = %d",
                     LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = (char *)WiaTrace_TraceLog("PrepareStiAcl: failed to allocate SID for BuiltinAdministrators, RpcStatus = %d");
    WriteDbgTraceErrorWI("PrepareStiAcl", v3);
    WiaTrcLib::Free((WiaTrcLib *)v3, v4);
    v5 = (void *)WiaTrace_Trace(
                   "PrepareStiAcl: failed to allocate SID for BuiltinAdministrators, RpcStatus = %d",
                   LastError);
  }
  WiaTrace_ProcessTrace_Ex(v7, v6, (int)"PrepareStiAcl", 1, v5);
LABEL_21:
  if ( v42 )
    FreeSid(v42);
  if ( pSid )
    FreeSid(pSid);
  LOBYTE(v29) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
    v29);
  v32 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( i = 0; i < v39; ++i )
    {
      LocalFree(v32[i]);
      v32 = (HLOCAL *)hMem;
    }
    LocalFree(v32);
  }
  v34 = (HLOCAL *)v41;
  if ( v41 )
  {
    for ( j = 0; j < v40; ++j )
    {
      LocalFree(v34[j]);
      v34 = (HLOCAL *)v41;
    }
    LocalFree(v34);
  }
  if ( LastError )
  {
    v36 = *a1;
    if ( *a1 )
    {
      v37 = GetProcessHeap();
      HeapFree(v37, 0, v36);
      *a1 = 0;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18002b5b0  push    rbp
0x18002b5b2  push    rbx
0x18002b5b3  push    rsi
0x18002b5b4  push    rdi
0x18002b5b5  push    r14
0x18002b5b7  push    r15
0x18002b5b9  lea     rbp, [rsp-2Fh]
0x18002b5be  sub     rsp, 0A8h
0x18002b5c5  mov     rax, cs:__security_cookie
0x18002b5cc  xor     rax, rsp
0x18002b5cf  mov     [rbp+57h+var_40], rax
0x18002b5d3  xor     r15d, r15d
0x18002b5d6  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18002b5dc  lea     rax, [rbp+57h+var_58]
0x18002b5e0  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x18002b5e4  mov     [rsp+0D0h+pSid], rax; pSid
0x18002b5e9  mov     r14, rcx
0x18002b5ec  mov     [rsp+0D0h+nSubAuthority7], r15d; nSubAuthority7
0x18002b5f1  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002b5f5  mov     [rsp+0D0h+nSubAuthority6], r15d; nSubAuthority6
0x18002b5fa  lea     r8d, [r15+20h]; nSubAuthority0
0x18002b5fe  mov     [rsp+0D0h+nSubAuthority5], r15d; nSubAuthority5
0x18002b603  lea     edi, [r15+5]
0x18002b607  mov     [rsp+0D0h+nSubAuthority4], r15d; nSubAuthority4
0x18002b60c  mov     r9d, 220h; nSubAuthority1
0x18002b612  mov     [rsp+0D0h+nSubAuthority3], r15d; nSubAuthority3
0x18002b617  mov     dl, 2; nSubAuthorityCount
0x18002b619  mov     [rsp+0D0h+nSubAuthority2], r15d; nSubAuthority2
0x18002b61e  mov     [rbp+57h+var_60], r15
0x18002b622  mov     [rbp+57h+var_58], r15
0x18002b626  mov     [rbp+57h+hMem], r15
0x18002b62a  mov     [rbp+57h+var_70], r15d
0x18002b62e  mov     [rbp+57h+var_68], r15
0x18002b632  mov     [rbp+57h+var_6C], r15d
0x18002b636  call    cs:__imp_AllocateAndInitializeSid
0x18002b63c  test    eax, eax
0x18002b63e  jnz     short loc_18002B687
0x18002b640  call    cs:__imp_GetLastError
0x18002b646  mov     edx, eax
0x18002b648  lea     rcx, aPreparestiaclF; "PrepareStiAcl: failed to allocate SID f"...
0x18002b64f  mov     edi, eax
0x18002b651  call    WiaTrace_TraceLog
0x18002b656  mov     rdx, rax; char *
0x18002b659  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b660  mov     rbx, rax
0x18002b663  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b668  mov     rcx, rbx; this
0x18002b66b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b670  mov     edx, edi
0x18002b672  lea     rcx, aPreparestiaclF; "PrepareStiAcl: failed to allocate SID f"...
0x18002b679  call    WiaTrace_Trace
0x18002b67e  lea     esi, [r15+1]
0x18002b682  jmp     loc_18002B9A6
0x18002b687  xor     r9d, r9d; nSubAuthority1
0x18002b68a  lea     rax, [rbp+57h+var_60]
0x18002b68e  mov     [rsp+0D0h+pSid], rax; pSid
0x18002b693  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002b697  mov     [rsp+0D0h+nSubAuthority7], r15d; nSubAuthority7
0x18002b69c  mov     [rsp+0D0h+nSubAuthority6], r15d; nSubAuthority6
0x18002b6a1  mov     [rsp+0D0h+nSubAuthority5], r15d; nSubAuthority5
0x18002b6a6  lea     esi, [r9+1]
0x18002b6aa  mov     [rsp+0D0h+nSubAuthority4], r15d; nSubAuthority4
0x18002b6af  lea     r8d, [r9+0Bh]; nSubAuthority0
0x18002b6b3  mov     [rsp+0D0h+nSubAuthority3], r15d; nSubAuthority3
0x18002b6b8  mov     dl, sil; nSubAuthorityCount
0x18002b6bb  mov     [rsp+0D0h+nSubAuthority2], r15d; nSubAuthority2
0x18002b6c0  call    cs:__imp_AllocateAndInitializeSid
0x18002b6c6  test    eax, eax
0x18002b6c8  jnz     short loc_18002B706
0x18002b6ca  call    cs:__imp_GetLastError
0x18002b6d0  mov     edx, eax
0x18002b6d2  lea     rcx, aPreparestiaclF_3; "PrepareStiAcl: failed to allocate SID f"...
0x18002b6d9  mov     edi, eax
0x18002b6db  call    WiaTrace_TraceLog
0x18002b6e0  mov     rdx, rax; char *
0x18002b6e3  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b6ea  mov     rbx, rax
0x18002b6ed  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b6f2  mov     rcx, rbx; this
0x18002b6f5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b6fa  lea     rcx, aPreparestiaclF_3; "PrepareStiAcl: failed to allocate SID f"...
0x18002b701  jmp     loc_18002B99F
0x18002b706  mov     dl, sil
0x18002b709  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x18002b710  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002b715  lea     rax, [rbp+57h+var_6C]
0x18002b719  lea     r9, [rbp+57h+var_68]
0x18002b71d  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x18002b722  lea     r8, [rbp+57h+var_70]
0x18002b726  lea     rdx, [rbp+57h+hMem]
0x18002b72a  lea     rcx, aIsolatedwin32S; "isolatedWin32-scanner"
0x18002b731  call    cs:__imp_DeriveCapabilitySidsFromName
0x18002b737  test    eax, eax
0x18002b739  jnz     short loc_18002B777
0x18002b73b  call    cs:__imp_GetLastError
0x18002b741  mov     edx, eax
0x18002b743  lea     rcx, aPreparestiaclF_5; "PrepareStiAcl: failed to derive isolate"...
0x18002b74a  mov     edi, eax
0x18002b74c  call    WiaTrace_TraceLog
0x18002b751  mov     rdx, rax; char *
0x18002b754  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b75b  mov     rbx, rax
0x18002b75e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b763  mov     rcx, rbx; this
0x18002b766  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b76b  lea     rcx, aPreparestiaclF_5; "PrepareStiAcl: failed to derive isolate"...
0x18002b772  jmp     loc_18002B99F
0x18002b777  cmp     [rbp+57h+var_6C], esi
0x18002b77a  jz      short loc_18002B7B5
0x18002b77c  cmp     [rbp+57h+var_70], esi
0x18002b77f  jz      short loc_18002B7B5
0x18002b781  mov     edx, edi
0x18002b783  lea     rcx, aPreparestiaclD; "PrepareStiAcl: derived unexpected numbe"...
0x18002b78a  call    WiaTrace_TraceLog
0x18002b78f  mov     rdx, rax; char *
0x18002b792  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b799  mov     rbx, rax
0x18002b79c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b7a1  mov     rcx, rbx; this
0x18002b7a4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b7a9  lea     rcx, aPreparestiaclD; "PrepareStiAcl: derived unexpected numbe"...
0x18002b7b0  jmp     loc_18002B99F
0x18002b7b5  mov     rcx, [rbp+57h+var_58]; pSid
0x18002b7b9  call    cs:__imp_GetLengthSid
0x18002b7bf  mov     rcx, [rbp+57h+var_60]; pSid
0x18002b7c3  mov     edi, eax
0x18002b7c5  call    cs:__imp_GetLengthSid
0x18002b7cb  mov     rcx, [rbp+57h+var_68]
0x18002b7cf  add     edi, eax
0x18002b7d1  mov     rcx, [rcx]; pSid
0x18002b7d4  call    cs:__imp_GetLengthSid
0x18002b7da  add     eax, 20h ; ' '
0x18002b7dd  add     edi, eax
0x18002b7df  call    cs:__imp_GetProcessHeap
0x18002b7e5  mov     r8d, edi; dwBytes
0x18002b7e8  mov     edx, 8; dwFlags
0x18002b7ed  mov     rcx, rax; hHeap
0x18002b7f0  call    cs:__imp_HeapAlloc
0x18002b7f6  mov     [r14], rax
0x18002b7f9  test    rax, rax
0x18002b7fc  jnz     short loc_18002B83A
0x18002b7fe  call    cs:__imp_GetLastError
0x18002b804  mov     edx, eax
0x18002b806  lea     rcx, aPreparestiaclF_6; "PrepareStiAcl: failed to allocate ACL ("...
0x18002b80d  mov     edi, eax
0x18002b80f  call    WiaTrace_TraceLog
0x18002b814  mov     rdx, rax; char *
0x18002b817  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b81e  mov     rbx, rax
0x18002b821  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b826  mov     rcx, rbx; this
0x18002b829  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b82e  lea     rcx, aPreparestiaclF_6; "PrepareStiAcl: failed to allocate ACL ("...
0x18002b835  jmp     loc_18002B99F
0x18002b83a  mov     r8d, 2; dwAclRevision
0x18002b840  mov     edx, edi; nAclLength
0x18002b842  mov     rcx, rax; pAcl
0x18002b845  call    cs:__imp_InitializeAcl
0x18002b84b  test    eax, eax
0x18002b84d  jnz     short loc_18002B88B
0x18002b84f  call    cs:__imp_GetLastError
0x18002b855  mov     edx, eax
0x18002b857  lea     rcx, aPreparestiaclF_1; "PrepareStiAcl: failed to initialize ACL"...
0x18002b85e  mov     edi, eax
0x18002b860  call    WiaTrace_TraceLog
0x18002b865  mov     rdx, rax; char *
0x18002b868  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b86f  mov     rbx, rax
0x18002b872  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b877  mov     rcx, rbx; this
0x18002b87a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b87f  lea     rcx, aPreparestiaclF_1; "PrepareStiAcl: failed to initialize ACL"...
0x18002b886  jmp     loc_18002B99F
0x18002b88b  mov     r9, [rbp+57h+var_60]; pSid
0x18002b88f  mov     edx, 2; dwAceRevision
0x18002b894  mov     rcx, [r14]; pAcl
0x18002b897  mov     r8d, 0C0100000h; AccessMask
0x18002b89d  call    cs:__imp_AddAccessAllowedAce
0x18002b8a3  test    eax, eax
0x18002b8a5  jnz     short loc_18002B8E3
0x18002b8a7  call    cs:__imp_GetLastError
0x18002b8ad  mov     edx, eax
0x18002b8af  lea     rcx, aPreparestiaclF_4; "PrepareStiAcl: failed to allow Authenti"...
0x18002b8b6  mov     edi, eax
0x18002b8b8  call    WiaTrace_TraceLog
0x18002b8bd  mov     rdx, rax; char *
0x18002b8c0  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b8c7  mov     rbx, rax
0x18002b8ca  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b8cf  mov     rcx, rbx; this
0x18002b8d2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b8d7  lea     rcx, aPreparestiaclF_4; "PrepareStiAcl: failed to allow Authenti"...
0x18002b8de  jmp     loc_18002B99F
0x18002b8e3  mov     r9, [rbp+57h+var_58]; pSid
0x18002b8e7  mov     ebx, 10000000h
0x18002b8ec  mov     rcx, [r14]; pAcl
0x18002b8ef  mov     r8d, ebx; AccessMask
0x18002b8f2  mov     edx, 2; dwAceRevision
0x18002b8f7  call    cs:__imp_AddAccessAllowedAce
0x18002b8fd  test    eax, eax
0x18002b8ff  jnz     short loc_18002B93A
0x18002b901  call    cs:__imp_GetLastError
0x18002b907  mov     edx, eax
0x18002b909  lea     rcx, aPreparestiaclF_0; "PrepareStiAcl: failed to allow BuiltinA"...
0x18002b910  mov     edi, eax
0x18002b912  call    WiaTrace_TraceLog
0x18002b917  mov     rdx, rax; char *
0x18002b91a  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b921  mov     rbx, rax
0x18002b924  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b929  mov     rcx, rbx; this
0x18002b92c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b931  lea     rcx, aPreparestiaclF_0; "PrepareStiAcl: failed to allow BuiltinA"...
0x18002b938  jmp     short loc_18002B99F
0x18002b93a  mov     dl, sil
0x18002b93d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x18002b944  mov     edi, r15d
0x18002b947  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002b94c  mov     r9, [rbp+57h+var_68]
0x18002b950  mov     r8d, ebx; AccessMask
0x18002b953  mov     rcx, [r14]; pAcl
0x18002b956  mov     edx, 2; dwAceRevision
0x18002b95b  mov     r9, [r9]; pSid
0x18002b95e  call    cs:__imp_AddAccessAllowedAce
0x18002b964  test    eax, eax
0x18002b966  jnz     short loc_18002B9BA
0x18002b968  call    cs:__imp_GetLastError
0x18002b96e  mov     edx, eax
0x18002b970  lea     rcx, aPreparestiaclF_2; "PrepareStiAcl: failed to allow win32-Sc"...
0x18002b977  mov     edi, eax
0x18002b979  call    WiaTrace_TraceLog
0x18002b97e  mov     rdx, rax; char *
0x18002b981  lea     rcx, aPreparestiacl; "PrepareStiAcl"
0x18002b988  mov     rbx, rax
0x18002b98b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002b990  mov     rcx, rbx; this
0x18002b993  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002b998  lea     rcx, aPreparestiaclF_2; "PrepareStiAcl: failed to allow win32-Sc"...
0x18002b99f  mov     edx, edi
0x18002b9a1  call    WiaTrace_Trace
0x18002b9a6  mov     r9d, esi; int
0x18002b9a9  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; lpMem
0x18002b9ae  lea     r8, aPreparestiacl; "PrepareStiAcl"
0x18002b9b5  call    WiaTrace_ProcessTrace_Ex
0x18002b9ba  mov     rcx, [rbp+57h+var_60]; pSid
0x18002b9be  test    rcx, rcx
0x18002b9c1  jz      short loc_18002B9C9
0x18002b9c3  call    cs:__imp_FreeSid
0x18002b9c9  mov     rcx, [rbp+57h+var_58]; pSid
0x18002b9cd  test    rcx, rcx
0x18002b9d0  jz      short loc_18002B9D8
0x18002b9d2  call    cs:__imp_FreeSid
0x18002b9d8  mov     dl, sil
0x18002b9db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x18002b9e2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002b9e7  mov     rax, [rbp+57h+hMem]
0x18002b9eb  test    rax, rax
0x18002b9ee  jz      short loc_18002BA19
0x18002b9f0  mov     ebx, r15d
0x18002b9f3  cmp     [rbp+57h+var_70], r15d
0x18002b9f7  jbe     short loc_18002BA10
0x18002b9f9  mov     ecx, ebx
0x18002b9fb  mov     rcx, [rax+rcx*8]; hMem
0x18002b9ff  call    cs:__imp_LocalFree
0x18002ba05  mov     rax, [rbp+57h+hMem]
0x18002ba09  add     ebx, esi
0x18002ba0b  cmp     ebx, [rbp+57h+var_70]
0x18002ba0e  jb      short loc_18002B9F9
0x18002ba10  mov     rcx, rax; hMem
0x18002ba13  call    cs:__imp_LocalFree
0x18002ba19  mov     rax, [rbp+57h+var_68]
0x18002ba1d  test    rax, rax
0x18002ba20  jz      short loc_18002BA4B
0x18002ba22  mov     ebx, r15d
0x18002ba25  cmp     [rbp+57h+var_6C], r15d
0x18002ba29  jbe     short loc_18002BA42
0x18002ba2b  mov     ecx, ebx
0x18002ba2d  mov     rcx, [rax+rcx*8]; hMem
0x18002ba31  call    cs:__imp_LocalFree
0x18002ba37  mov     rax, [rbp+57h+var_68]
0x18002ba3b  add     ebx, esi
0x18002ba3d  cmp     ebx, [rbp+57h+var_6C]
0x18002ba40  jb      short loc_18002BA2B
0x18002ba42  mov     rcx, rax; hMem
0x18002ba45  call    cs:__imp_LocalFree
0x18002ba4b  test    edi, edi
0x18002ba4d  jz      short loc_18002BA6E
0x18002ba4f  mov     rbx, [r14]
0x18002ba52  test    rbx, rbx
0x18002ba55  jz      short loc_18002BA6E
0x18002ba57  call    cs:__imp_GetProcessHeap
0x18002ba5d  mov     r8, rbx; lpMem
0x18002ba60  xor     edx, edx; dwFlags
0x18002ba62  mov     rcx, rax; hHeap
0x18002ba65  call    cs:__imp_HeapFree
0x18002ba6b  mov     [r14], r15
0x18002ba6e  mov     eax, edi
0x18002ba70  mov     rcx, [rbp+57h+var_40]
0x18002ba74  xor     rcx, rsp; StackCookie
0x18002ba77  call    __security_check_cookie
  ... truncated ...
```
