# CTSSDFarmRpc::OnLogoff(_SN_ONLOGOFF_PARAMS *)

- ea: `0x180002730`
- end: `0x180002b9b`
- name: `?OnLogoff@CTSSDFarmRpc@@EEAAJPEAU_SN_ONLOGOFF_PARAMS@@@Z`
- size: `1131`
- prototype: `__int64 __fastcall(CTSSDFarmRpc *__hidden this, struct _SN_ONLOGOFF_PARAMS *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002730`
- `0x180003f30`
- `0x1800125f0`
- `0x180012630`
- `0x180012a90`
- `0x18001a8d0`
- `0x1800382c8`
- `0x18003832c`
- `0x1800383a8`
- `0x18003842c`
- `0x1800399a4`
- `0x18005a80c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800027b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800027b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002ac4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002ad5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002ac4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180002ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002aff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002aff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000298f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000298f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002958`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002958`

## string_xrefs

- `0x1800027de`: `OpenKey REG_TS_CLUSTERSETTINGS failed: 0x%x in %s`
- `0x1800028a3`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180002827`: `ReadRegString TSSDFARM_ADDED_ASADMIN user failed: 0x%x in %s`
- `0x180002874`: `ReadRegString TSSDFARM_ADDED_USER failed: 0x%x in %s`
- `0x18000297e`: `ConvertSidToStringSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::OnLogoff(CTSSDFarmRpc *this, struct _SN_ONLOGOFF_PARAMS *a2)
{
  struct IUserName *v2; // rbx
  void *v3; // rdi
  LSTATUS v4; // eax
  signed int v5; // esi
  int v6; // eax
  int v7; // eax
  int ClientToken; // eax
  int InstanceOfUserName; // eax
  int v10; // eax
  signed int LastError; // eax
  CTSSDFarmRpc *v12; // rcx
  unsigned int v13; // r14d
  __int64 *v14; // rdx
  __int64 *v15; // rdx
  __int64 *v16; // rdx
  __int64 *v17; // rdx
  LPWSTR StringSid; // [rsp+38h] [rbp-29h] BYREF
  void *v20; // [rsp+40h] [rbp-21h] BYREF
  PSID Sid; // [rsp+48h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-11h] BYREF
  LPVOID v23; // [rsp+58h] [rbp-9h] BYREF
  struct IUserName *v24; // [rsp+60h] [rbp-1h] BYREF
  LPCWSTR lpString2; // [rsp+68h] [rbp+7h] BYREF
  void **v26; // [rsp+70h] [rbp+Fh] BYREF
  void *Block; // [rsp+78h] [rbp+17h]
  int v28; // [rsp+80h] [rbp+1Fh]
  HKEY phkResult[2]; // [rsp+88h] [rbp+27h] BYREF
  unsigned int v30; // [rsp+D8h] [rbp+77h] BYREF
  unsigned int v31; // [rsp+E0h] [rbp+7Fh] BYREF

  StringSid = 0;
  v2 = 0;
  Sid = 0;
  v24 = 0;
  v26 = &CRegistry::`vftable';
  Block = 0;
  v28 = 0;
  v3 = 0;
  phkResult[0] = 0;
  phkResult[1] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  lpString2 = 0;
  pv = 0;
  v23 = 0;
  v20 = 0;
  v30 = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\ClusterSettings",
         0,
         0x2001Fu,
         phkResult);
  v5 = v4;
  if ( !v4 )
    goto LABEL_6;
  phkResult[0] = 0;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(8, "OpenKey REG_TS_CLUSTERSETTINGS failed: 0x%x in %s", v5, "CTSSDFarmRpc::OnLogoff");
  }
  else
  {
LABEL_6:
    v6 = CRegistry::ReadRegDWord((CRegistry *)&v26, L"AddedAsAdmin", &v30);
    v5 = v6;
    if ( !v6 )
      goto LABEL_11;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(8, "ReadRegString TSSDFARM_ADDED_ASADMIN user failed: 0x%x in %s", v5, "CTSSDFarmRpc::OnLogoff");
    }
    else
    {
LABEL_11:
      v7 = CRegistry::ReadRegString((CRegistry *)&v26, L"AddedRDSUser", (unsigned __int16 **)&lpString2, &v31);
      v5 = v7;
      if ( !v7 )
        goto LABEL_16;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 < 0 )
      {
        _DbgPrintMessage(8, "ReadRegString TSSDFARM_ADDED_USER failed: 0x%x in %s", v5, "CTSSDFarmRpc::OnLogoff");
      }
      else
      {
LABEL_16:
        ClientToken = CRpcUtils::GetClientToken(&v20);
        v5 = ClientToken;
        if ( ClientToken >= 0 )
        {
          InstanceOfUserName = CUtils::GetInstanceOfUserName(&v24);
          v5 = InstanceOfUserName;
          if ( InstanceOfUserName >= 0 )
          {
            v2 = v24;
            v3 = v20;
            v10 = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, v20, 0);
            v5 = v10;
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)v2 + 72LL))(v2, &Sid),
                  v5 = v10,
                  v10 < 0) )
            {
              _DbgPrintMessage(
                8,
                "CRpcUtils::GetInstanceOfUserName failed: 0x%x in %s",
                (unsigned int)v10,
                "CTSSDFarmRpc::OnLogoff");
            }
            else
            {
              if ( ConvertSidToStringSidW(Sid, &StringSid) )
                goto LABEL_69;
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
              if ( v5 >= 0 )
              {
LABEL_69:
                if ( !lstrcmpiW(StringSid, lpString2) )
                {
                  v13 = v30;
                  v31 = 0;
                  v5 = CTSSDFarmRpc::LocalGroupRemoveUser(v12, lpString2, v30, (int *)&v31);
                  (*(void (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)v2 + 40LL))(v2, &pv);
                  (*(void (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)v2 + 48LL))(v2, &v23);
                  if ( v5 >= 0 && v31 )
                  {
                    if ( v31 == 1 )
                    {
                      if ( pv && v23 )
                      {
                        v14 = SESSENV_TSSDFARM_REVOKE_ADMIN;
                        if ( !v13 )
                          v14 = SESSENV_TSSDFARM_REVOKE_RDS;
                        CrimsonHelper::RaiseEvent<unsigned short const *,unsigned short const *>(
                          &CrimsonHelper::s_instance,
                          v14);
                      }
                      else
                      {
                        v15 = SESSENV_TSSDFARM_REVOKE_ADMIN_SID;
                        if ( !v13 )
                          v15 = SESSENV_TSSDFARM_REVOKE_RDS_SID;
                        CrimsonHelper::RaiseEvent<unsigned short *>(&CrimsonHelper::s_instance, v15, StringSid);
                      }
                    }
                  }
                  else if ( pv && v23 )
                  {
                    v16 = EVENT_SESSENV_TSSDFARM_REVOKE_ADMIN_FAILED;
                    if ( !v13 )
                      v16 = EVENT_SESSENV_TSSDFARM_REVOKE_RDS_FAILED;
                    CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,long>(
                      (unsigned int)&CrimsonHelper::s_instance,
                      (_DWORD)v16,
                      (_DWORD)v23,
                      (_DWORD)pv,
                      v5);
                  }
                  else
                  {
                    v17 = EVENT_SESSENV_TSSDFARM_REVOKE_ADMIN_FAILED_SID;
                    if ( !v13 )
                      v17 = EVENT_SESSENV_TSSDFARM_REVOKE_RDS_FAILED_SID;
                    CrimsonHelper::RaiseEvent<unsigned short *,long>(
                      &CrimsonHelper::s_instance,
                      v17,
                      StringSid,
                      (unsigned int)v5);
                  }
                  RegDeleteValueW(phkResult[0], L"AddedRDSUser");
                  RegDeleteValueW(phkResult[0], L"AddedAsAdmin");
                }
              }
              else
              {
                _DbgPrintMessage(
                  8,
                  "ConvertSidToStringSid failed: 0x%x in %s",
                  (unsigned int)v5,
                  "CTSSDFarmRpc::OnLogoff");
              }
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "CRpcUtils::GetInstanceOfUserName failed: 0x%x in %s",
              InstanceOfUserName,
              "CTSSDFarmRpc::OnLogoff");
            v2 = v24;
            v3 = v20;
          }
        }
        else
        {
          _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", ClientToken, "CTSSDFarmRpc::OnLogoff");
          v3 = v20;
        }
      }
    }
  }
  if ( Sid )
  {
    CoTaskMemFree(Sid);
    Sid = 0;
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v3 )
    CloseHandle(v3);
  v26 = &CRegistry::`vftable';
  if ( phkResult[0] )
  {
    RegCloseKey(phkResult[0]);
    phkResult[0] = 0;
  }
  if ( Block )
    operator delete(Block);
  v28 = 0;
  Block = 0;
  if ( v2 )
    (*(void (__fastcall **)(struct IUserName *))(*(_QWORD *)v2 + 16LL))(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002730  mov     rax, rsp
0x180002733  push    rbp
0x180002734  push    rbx
0x180002735  push    rsi
0x180002736  lea     rbp, [rax-5Fh]
0x18000273a  sub     rsp, 0A0h
0x180002741  mov     [rax+8], rdi
0x180002745  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18000274c  mov     [rax+10h], r12
0x180002750  mov     r9d, 2001Fh; samDesired
0x180002756  xor     r12d, r12d
0x180002759  mov     [rax-20h], r13
0x18000275d  lea     rax, [rbp+57h+phkResult]
0x180002761  mov     [rbp+57h+StringSid], r12
0x180002765  mov     ebx, r12d
0x180002768  mov     [rbp+57h+Sid], r12
0x18000276c  lea     r13, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180002773  mov     [rbp+57h+var_58], rbx
0x180002777  xor     r8d, r8d; ulOptions
0x18000277a  mov     [rbp+57h+var_48], r13
0x18000277e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002785  mov     [rbp+57h+Block], r12
0x180002789  mov     [rbp+57h+var_38], r12d
0x18000278d  mov     edi, r12d
0x180002790  mov     [rbp+57h+phkResult], r12
0x180002794  mov     [rbp+57h+var_28], 0FFFFFFFFFFFFFFFFh
0x18000279c  mov     [rbp+57h+lpString2], r12
0x1800027a0  mov     [rbp+57h+pv], r12
0x1800027a4  mov     [rbp+57h+var_60], r12
0x1800027a8  mov     [rbp+57h+var_78], r12
0x1800027ac  mov     [rbp+57h+arg_10], r12d
0x1800027b0  mov     [rsp+20h], rax; phkResult
0x1800027b5  call    cs:__imp_RegOpenKeyExW
0x1800027bb  mov     esi, eax
0x1800027bd  test    eax, eax
0x1800027bf  jz      short loc_1800027F4
0x1800027c1  mov     [rbp+57h+phkResult], r12
0x1800027c5  jle     short loc_1800027D0
0x1800027c7  movzx   esi, ax
0x1800027ca  or      esi, 80070000h
0x1800027d0  test    esi, esi
0x1800027d2  jns     short loc_1800027F4
0x1800027d4  lea     r9, aCtssdfarmrpcOn_0; "CTSSDFarmRpc::OnLogoff"
0x1800027db  mov     r8d, esi
0x1800027de  lea     rdx, aOpenkeyRegTsCl; "OpenKey REG_TS_CLUSTERSETTINGS failed: "...
0x1800027e5  mov     ecx, 8; int
0x1800027ea  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800027ef  jmp     loc_180002AE3
0x1800027f4  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x1800027f8  lea     rdx, aAddedasadmin; "AddedAsAdmin"
0x1800027ff  lea     rcx, [rbp+57h+var_48]; this
0x180002803  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180002808  mov     esi, eax
0x18000280a  test    eax, eax
0x18000280c  jz      short loc_18000283D
0x18000280e  jle     short loc_180002819
0x180002810  movzx   esi, ax
0x180002813  or      esi, 80070000h
0x180002819  test    esi, esi
0x18000281b  jns     short loc_18000283D
0x18000281d  lea     r9, aCtssdfarmrpcOn_0; "CTSSDFarmRpc::OnLogoff"
0x180002824  mov     r8d, esi
0x180002827  lea     rdx, aReadregstringT_0; "ReadRegString TSSDFARM_ADDED_ASADMIN us"...
0x18000282e  mov     ecx, 8; int
0x180002833  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002838  jmp     loc_180002AE3
0x18000283d  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x180002841  lea     r8, [rbp+57h+lpString2]; unsigned __int16 **
0x180002845  lea     rdx, ValueName; "AddedRDSUser"
0x18000284c  lea     rcx, [rbp+57h+var_48]; this
0x180002850  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180002855  mov     esi, eax
0x180002857  test    eax, eax
0x180002859  jz      short loc_18000288A
0x18000285b  jle     short loc_180002866
0x18000285d  movzx   esi, ax
0x180002860  or      esi, 80070000h
0x180002866  test    esi, esi
0x180002868  jns     short loc_18000288A
0x18000286a  lea     r9, aCtssdfarmrpcOn_0; "CTSSDFarmRpc::OnLogoff"
0x180002871  mov     r8d, esi
0x180002874  lea     rdx, aReadregstringT; "ReadRegString TSSDFARM_ADDED_USER faile"...
0x18000287b  mov     ecx, 8; int
0x180002880  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002885  jmp     loc_180002AE3
0x18000288a  lea     rcx, [rbp+57h+var_78]; void **
0x18000288e  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x180002893  mov     esi, eax
0x180002895  test    eax, eax
0x180002897  jns     short loc_1800028BD
0x180002899  lea     r9, aCtssdfarmrpcOn_0; "CTSSDFarmRpc::OnLogoff"
0x1800028a0  mov     r8d, eax
0x1800028a3  lea     rdx, aCrpcutilsGetcl_4; "CRpcUtils::GetClientToken failed: 0x%x "...
0x1800028aa  mov     ecx, 8; int
0x1800028af  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800028b4  mov     rdi, [rbp+57h+var_78]
0x1800028b8  jmp     loc_180002AE3
0x1800028bd  lea     rcx, [rbp+57h+var_58]; struct IUserName **
0x1800028c1  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x1800028c6  mov     esi, eax
0x1800028c8  test    eax, eax
0x1800028ca  jns     short loc_1800028F4
0x1800028cc  lea     r9, aCtssdfarmrpcOn_0; "CTSSDFarmRpc::OnLogoff"
0x1800028d3  mov     r8d, eax
0x1800028d6  lea     rdx, aCrpcutilsGetin; "CRpcUtils::GetInstanceOfUserName failed"...
0x1800028dd  mov     ecx, 8; int
0x1800028e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800028e7  mov     rbx, [rbp+57h+var_58]
0x1800028eb  mov     rdi, [rbp+57h+var_78]
0x1800028ef  jmp     loc_180002AE3
0x1800028f4  mov     rbx, [rbp+57h+var_58]
0x1800028f8  xor     r8d, r8d
0x1800028fb  mov     rdi, [rbp+57h+var_78]
0x1800028ff  mov     rcx, rbx
0x180002902  mov     rdx, rdi
0x180002905  mov     rax, [rbx]
0x180002908  mov     rax, [rax+18h]
0x18000290c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002911  mov     esi, eax
0x180002913  test    eax, eax
0x180002915  jns     short loc_180002937
0x180002917  mov     r8d, eax
0x18000291a  lea     rdx, aCrpcutilsGetin; "CRpcUtils::GetInstanceOfUserName failed"...
0x180002921  lea     r9, aCtssdfarmrpcOn_0; "CTSSDFarmRpc::OnLogoff"
0x180002928  mov     ecx, 8; int
0x18000292d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002932  jmp     loc_180002AE3
0x180002937  mov     rax, [rbx]
0x18000293a  lea     rdx, [rbp+57h+Sid]
0x18000293e  mov     rcx, rbx
0x180002941  mov     rax, [rax+48h]
0x180002945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294a  mov     esi, eax
0x18000294c  test    eax, eax
0x18000294e  js      short loc_180002917
0x180002950  mov     rcx, [rbp+57h+Sid]; Sid
0x180002954  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180002958  call    cs:__imp_ConvertSidToStringSidW
0x18000295e  test    eax, eax
0x180002960  jnz     short loc_180002987
0x180002962  call    cs:__imp_GetLastError
0x180002968  mov     esi, eax
0x18000296a  test    eax, eax
0x18000296c  jle     short loc_180002977
0x18000296e  movzx   esi, ax
0x180002971  or      esi, 80070000h
0x180002977  test    esi, esi
0x180002979  jns     short loc_180002987
0x18000297b  mov     r8d, esi
0x18000297e  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSid failed: 0x%x in %"...
0x180002985  jmp     short loc_180002921
0x180002987  mov     rdx, [rbp+57h+lpString2]; lpString2
0x18000298b  mov     rcx, [rbp+57h+StringSid]; lpString1
0x18000298f  call    cs:__imp_lstrcmpiW
0x180002995  test    eax, eax
0x180002997  jnz     loc_180002AE3
0x18000299d  mov     rdx, [rbp+57h+lpString2]; unsigned __int16 *
0x1800029a1  lea     r9, [rbp+57h+arg_18]; int *
0x1800029a5  mov     [rsp+0B0h+var_20], r14
0x1800029ad  mov     r14d, [rbp+57h+arg_10]
0x1800029b1  mov     r8d, r14d; int
0x1800029b4  mov     [rbp+57h+arg_18], r12d
0x1800029b8  call    ?LocalGroupRemoveUser@CTSSDFarmRpc@@AEAAJPEBGHPEAH@Z; CTSSDFarmRpc::LocalGroupRemoveUser(ushort const *,int,int *)
0x1800029bd  mov     esi, eax
0x1800029bf  lea     rdx, [rbp+57h+pv]
0x1800029c3  mov     rax, [rbx]
0x1800029c6  mov     rcx, rbx
0x1800029c9  mov     rax, [rax+28h]
0x1800029cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d2  mov     rax, [rbx]
0x1800029d5  lea     rdx, [rbp+57h+var_60]
0x1800029d9  mov     rcx, rbx
0x1800029dc  mov     rax, [rax+30h]
0x1800029e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e5  test    esi, esi
0x1800029e7  js      short loc_180002A58
0x1800029e9  mov     eax, [rbp+57h+arg_18]
0x1800029ec  test    eax, eax
0x1800029ee  jz      short loc_180002A58
0x1800029f0  cmp     eax, 1
0x1800029f3  jnz     loc_180002AB9
0x1800029f9  mov     r9, [rbp+57h+pv]
0x1800029fd  test    r9, r9
0x180002a00  jz      short loc_180002A31
0x180002a02  mov     r8, [rbp+57h+var_60]
0x180002a06  test    r8, r8
0x180002a09  jz      short loc_180002A31
0x180002a0b  test    r14d, r14d
0x180002a0e  lea     rax, SESSENV_TSSDFARM_REVOKE_RDS
0x180002a15  lea     rdx, SESSENV_TSSDFARM_REVOKE_ADMIN
0x180002a1c  cmovz   rdx, rax
0x180002a20  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180002a27  call    ??$RaiseEvent@PEBGPEBG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEBG1@Z; CrimsonHelper::RaiseEvent<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *)
0x180002a2c  jmp     loc_180002AB9
0x180002a31  mov     r8, [rbp+57h+StringSid]
0x180002a35  lea     rax, SESSENV_TSSDFARM_REVOKE_RDS_SID
0x180002a3c  test    r14d, r14d
0x180002a3f  lea     rdx, SESSENV_TSSDFARM_REVOKE_ADMIN_SID
0x180002a46  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180002a4d  cmovz   rdx, rax
0x180002a51  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180002a56  jmp     short loc_180002AB9
0x180002a58  mov     r9, [rbp+57h+pv]
0x180002a5c  test    r9, r9
0x180002a5f  jz      short loc_180002A91
0x180002a61  mov     r8, [rbp+57h+var_60]
0x180002a65  test    r8, r8
0x180002a68  jz      short loc_180002A91
0x180002a6a  test    r14d, r14d
0x180002a6d  mov     [rsp+20h], esi
0x180002a71  lea     rax, EVENT_SESSENV_TSSDFARM_REVOKE_RDS_FAILED
0x180002a78  lea     rdx, EVENT_SESSENV_TSSDFARM_REVOKE_ADMIN_FAILED
0x180002a7f  cmovz   rdx, rax
0x180002a83  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180002a8a  call    ??$RaiseEvent@PEAGPEAGJ@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG1J@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,long>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,long)
0x180002a8f  jmp     short loc_180002AB9
0x180002a91  mov     r8, [rbp+57h+StringSid]
0x180002a95  lea     rax, EVENT_SESSENV_TSSDFARM_REVOKE_RDS_FAILED_SID
0x180002a9c  test    r14d, r14d
0x180002a9f  lea     rdx, EVENT_SESSENV_TSSDFARM_REVOKE_ADMIN_FAILED_SID
0x180002aa6  mov     r9d, esi
0x180002aa9  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180002ab0  cmovz   rdx, rax
0x180002ab4  call    ??$RaiseEvent@PEAGJ@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAGJ@Z; CrimsonHelper::RaiseEvent<ushort *,long>(_EVENT_DESCRIPTOR const &,ushort *,long)
0x180002ab9  mov     rcx, [rbp+57h+phkResult]; hKey
0x180002abd  lea     rdx, ValueName; "AddedRDSUser"
0x180002ac4  call    cs:__imp_RegDeleteValueW
0x180002aca  mov     rcx, [rbp+57h+phkResult]; hKey
0x180002ace  lea     rdx, aAddedasadmin; "AddedAsAdmin"
0x180002ad5  call    cs:__imp_RegDeleteValueW
0x180002adb  mov     r14, [rsp+0B0h+var_20]
0x180002ae3  mov     rcx, [rbp+57h+Sid]; pv
0x180002ae7  test    rcx, rcx
0x180002aea  jz      short loc_180002AF6
0x180002aec  call    cs:__imp_CoTaskMemFree
0x180002af2  mov     [rbp+57h+Sid], r12
0x180002af6  mov     rcx, [rbp+57h+StringSid]; hMem
0x180002afa  test    rcx, rcx
0x180002afd  jz      short loc_180002B09
0x180002aff  call    cs:__imp_LocalFree
0x180002b05  mov     [rbp+57h+StringSid], r12
0x180002b09  mov     rcx, [rbp+57h+pv]; pv
0x180002b0d  test    rcx, rcx
0x180002b10  jz      short loc_180002B18
0x180002b12  call    cs:__imp_CoTaskMemFree
0x180002b18  mov     rcx, [rbp+57h+var_60]; pv
0x180002b1c  test    rcx, rcx
0x180002b1f  jz      short loc_180002B27
0x180002b21  call    cs:__imp_CoTaskMemFree
0x180002b27  test    rdi, rdi
0x180002b2a  jz      short loc_180002B35
0x180002b2c  mov     rcx, rdi; hObject
0x180002b2f  call    cs:__imp_CloseHandle
0x180002b35  mov     rcx, [rbp+57h+phkResult]; hKey
0x180002b39  mov     rdi, [rsp+0B0h+arg_0]
0x180002b41  mov     [rbp+57h+var_48], r13
0x180002b45  mov     r13, [rsp+98h]
0x180002b4d  test    rcx, rcx
0x180002b50  jz      short loc_180002B5C
0x180002b52  call    cs:__imp_RegCloseKey
0x180002b58  mov     [rbp+57h+phkResult], r12
0x180002b5c  mov     rcx, [rbp+57h+Block]; Block
0x180002b60  test    rcx, rcx
0x180002b63  jz      short loc_180002B6A
0x180002b65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b6a  mov     [rbp+57h+var_38], r12d
0x180002b6e  mov     [rbp+57h+Block], r12
0x180002b72  mov     r12, [rsp+0B0h+arg_8]
0x180002b7a  test    rbx, rbx
0x180002b7d  jz      short loc_180002B8E
0x180002b7f  mov     rax, [rbx]
0x180002b82  mov     rcx, rbx
0x180002b85  mov     rax, [rax+10h]
0x180002b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b8e  mov     eax, esi
0x180002b90  add     rsp, 0A0h
0x180002b97  pop     rsi
0x180002b98  pop     rbx
0x180002b99  pop     rbp
0x180002b9a  retn
```
