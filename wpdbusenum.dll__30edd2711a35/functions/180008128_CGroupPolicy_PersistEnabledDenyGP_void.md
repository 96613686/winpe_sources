# CGroupPolicy::PersistEnabledDenyGP(void)

- ea: `0x180008128`
- end: `0x180008617`
- name: `?PersistEnabledDenyGP@CGroupPolicy@@IEAAXXZ`
- size: `1263`
- prototype: `void __fastcall(CGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180001730`
- `0x180002fa0`
- `0x180007160`
- `0x180008128`
- `0x1800097d0`
- `0x18000a192`
- `0x18000e53c`
- `0x18000e838`
- `0x180010f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008573`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000858f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000858f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000822e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000822e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008207`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008352`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008207`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000856b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000856b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085cd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800082d0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800082d0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800082fd`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800082fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180008517`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180008517`

## string_xrefs

- `0x180008211`: `Failed to open the EnabledDenyGP root key with (%d)\n`
- `0x180008525`: `SecurityDescriptor`
- `0x1800083d5`: `AccessBitMask`
- `0x1800082da`: `Failed to create GUIDKeyName\n`
- `0x18000830b`: `RegDeleteKeyW failed with (%d)\n`
- `0x180008558`: `WPDLibSetRegistryValue failed to set the security descriptor with (%d)\n`
- `0x180008579`: `ConvertSecurityDescriptorToStringSecurityDescriptor failed with (%d)\n`
- `0x180008597`: `Failed to create the storageguid key with (%d)\n`

## pseudocode

```c
void __fastcall CGroupPolicy::PersistEnabledDenyGP(CGroupPolicy *this)
{
  int v2; // eax
  unsigned int v3; // eax
  __int64 v4; // rdx
  CGroupPolicy *v5; // rcx
  const GUID *i; // rdi
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  CGroupPolicy *v11; // rcx
  __int64 v12; // rdx
  CGroupPolicy *v13; // rcx
  __int64 v14; // rdx
  CGroupPolicy *v15; // rcx
  unsigned int v16; // edx
  CGroupPolicy *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  DWORD LastError; // eax
  HLOCAL *v21; // rdi
  HLOCAL *v22; // rbx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(SubKey, 0, 0x208u);
  memset_0(sz, 0, 0x208u);
  hKey = 0;
  v2 = StringCchPrintfW(SubKey, 0x104u, L"%ws\\%ws", L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"EnabledDenyGP");
  if ( v2 >= 0 )
  {
    v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    if ( v3 )
    {
      GPDebugPrintX(2, "Failed to open the EnabledDenyGP root key with (%d)\n", v3);
    }
    else if ( *((_DWORD *)this + 6) == 2 && RegDeleteTreeW(hKey, 0) )
    {
      CGroupPolicy::SetRegCacheUpdated(v5, v4);
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, SubKey);
      }
    }
    else
    {
      WPDLibSetRegistryValue(hKey, v4, 0, L"DenyAllGPState", 4, (char *)this + 24, 4);
      if ( *((_DWORD *)this + 6) != 2 )
      {
        for ( i = (const GUID *)*((_QWORD *)this + 2); i; i = *(const GUID **)&i->Data1 )
        {
          if ( StringFromGUID2(i + 1, sz, 260) )
          {
            if ( i[3].Data1 )
            {
              v7 = RegDeleteKeyW(hKey, sz);
              if ( v7 )
                GPDebugPrintX(8, "RegDeleteKeyW failed with (%d)\n", v7);
            }
            else
            {
              StringSecurityDescriptor = 0;
              StringSecurityDescriptorLen = 0;
              phkResult = 0;
              v8 = RegCreateKeyExW(hKey, sz, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
              if ( v8 )
              {
                GPDebugPrintX(2, "Failed to create the storageguid key with (%d)\n", v8);
              }
              else
              {
                if ( (unsigned int)WPDLibSetRegistryValue(phkResult, v9, 0, L"EnumerateDevices", 4, &i[2].Data2, 4) )
                {
                  CGroupPolicy::SetRegCacheUpdated(v11, v10);
                  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      28,
                      (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
                      (unsigned int)SubKey,
                      (__int64)sz);
                  }
                }
                if ( (unsigned int)WPDLibSetRegistryValue(phkResult, v10, 0, L"AccessBitMask", 4, &i[2], 4) )
                {
                  CGroupPolicy::SetRegCacheUpdated(v13, v12);
                  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      29,
                      (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
                      (unsigned int)SubKey,
                      (__int64)sz);
                  }
                }
                if ( (unsigned int)WPDLibSetRegistryValue(phkResult, v12, 0, L"UserPolicy", 4, i[2].Data4, 4) )
                {
                  CGroupPolicy::SetRegCacheUpdated(v15, v14);
                  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      30,
                      (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
                      (unsigned int)SubKey,
                      (__int64)sz);
                  }
                }
                if ( (unsigned int)WPDLibSetRegistryValue(phkResult, v14, 0, L"AuditPolicyOnly", 4, &i[2].Data4[4], 4) )
                {
                  CGroupPolicy::SetRegCacheUpdated(v17, v16);
                  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      31,
                      (unsigned int)WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
                      (unsigned int)SubKey,
                      (__int64)sz);
                  }
                }
                if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
                       *(PSECURITY_DESCRIPTOR *)i->Data4,
                       1u,
                       4u,
                       &StringSecurityDescriptor,
                       &StringSecurityDescriptorLen) )
                {
                  v19 = WPDLibSetRegistryValue(
                          phkResult,
                          v18,
                          0,
                          L"SecurityDescriptor",
                          1,
                          StringSecurityDescriptor,
                          2 * StringSecurityDescriptorLen);
                  if ( v19 )
                    GPDebugPrintX(2, "WPDLibSetRegistryValue failed to set the security descriptor with (%d)\n", v19);
                  LocalFree(StringSecurityDescriptor);
                }
                else
                {
                  LastError = GetLastError();
                  GPDebugPrintX(2, "ConvertSecurityDescriptorToStringSecurityDescriptor failed with (%d)\n", LastError);
                }
                RegCloseKey(phkResult);
              }
            }
          }
          else
          {
            GPDebugPrintX(2, "Failed to create GUIDKeyName\n");
          }
        }
        v21 = (HLOCAL *)*((_QWORD *)this + 2);
        while ( v21 )
        {
          v22 = v21;
          v21 = (HLOCAL *)*v21;
          LocalFree(v22[1]);
          LocalFree(v22);
        }
        *((_QWORD *)this + 2) = 0;
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  else
  {
    GPDebugPrintX(2, "StringCchPrintfW failed with (%d)hr\n", (unsigned int)v2);
  }
}

```

## disassembly

```asm
0x180008128  mov     [rsp-8+arg_8], rbx
0x18000812d  mov     [rsp-8+arg_10], rsi
0x180008132  push    rbp
0x180008133  push    rdi
0x180008134  push    r12
0x180008136  push    r13
0x180008138  push    r15
0x18000813a  lea     rbp, [rsp-3A0h]
0x180008142  sub     rsp, 4A0h
0x180008149  mov     rax, cs:__security_cookie
0x180008150  xor     rax, rsp
0x180008153  mov     [rbp+3C0h+var_30], rax
0x18000815a  mov     r15, rcx
0x18000815d  mov     ebx, 208h
0x180008162  mov     r8d, ebx; Size
0x180008165  lea     rcx, [rbp+3C0h+SubKey]; void *
0x18000816c  xor     edx, edx; Val
0x18000816e  call    memset_0
0x180008173  mov     r8d, ebx; Size
0x180008176  lea     rcx, [rsp+4C0h+sz]; void *
0x18000817b  xor     edx, edx; Val
0x18000817d  call    memset_0
0x180008182  lea     rax, aEnableddenygp; "EnabledDenyGP"
0x180008189  xor     r12d, r12d
0x18000818c  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180008193  mov     qword ptr [rsp+4C0h+dwOptions], rax
0x180008198  lea     r8, aWsWs; "%ws\\%ws"
0x18000819f  mov     [rsp+4C0h+hKey], r12
0x1800081a4  mov     edx, 104h; unsigned __int64
0x1800081a9  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x1800081b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800081b5  test    eax, eax
0x1800081b7  jns     short loc_1800081D2
0x1800081b9  lea     rdx, aStringcchprint; "StringCchPrintfW failed with (%d)hr\n"
0x1800081c0  mov     r8d, eax
0x1800081c3  mov     ecx, 2; unsigned int
0x1800081c8  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800081cd  jmp     loc_1800085EC
0x1800081d2  mov     [rsp+4C0h+lpdwDisposition], r12; lpdwDisposition
0x1800081d7  lea     rax, [rsp+4C0h+hKey]
0x1800081dc  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800081e1  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x1800081e8  mov     [rsp+4C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800081ed  xor     r9d, r9d; lpClass
0x1800081f0  mov     [rsp+4C0h+samDesired], 2001Fh; samDesired
0x1800081f8  xor     r8d, r8d; Reserved
0x1800081fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008202  mov     [rsp+4C0h+dwOptions], r12d; dwOptions
0x180008207  call    cs:__imp_RegCreateKeyExW
0x18000820d  test    eax, eax
0x18000820f  jz      short loc_18000821A
0x180008211  lea     rdx, aFailedToOpenTh; "Failed to open the EnabledDenyGP root k"...
0x180008218  jmp     short loc_1800081C0
0x18000821a  lea     rdi, [r15+18h]
0x18000821e  mov     ebx, 2
0x180008223  cmp     [rdi], ebx
0x180008225  jnz     short loc_18000827C
0x180008227  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18000822c  xor     edx, edx; lpSubKey
0x18000822e  call    cs:__imp_RegDeleteTreeW
0x180008234  test    eax, eax
0x180008236  jz      short loc_18000827C
0x180008238  call    ?SetRegCacheUpdated@CGroupPolicy@@IEAAJK@Z; CGroupPolicy::SetRegCacheUpdated(ulong)
0x18000823d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008244  lea     rsi, WPP_GLOBAL_Control
0x18000824b  cmp     rcx, rsi
0x18000824e  jz      loc_1800085EC
0x180008254  test    [rcx+1Ch], bl
0x180008257  jz      loc_1800085EC
0x18000825d  mov     rcx, [rcx+10h]
0x180008261  lea     edx, [rbx+19h]
0x180008264  lea     r9, [rbp+3C0h+SubKey]
0x18000826b  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180008272  call    WPP_SF_S
0x180008277  jmp     loc_1800085EC
0x18000827c  mov     rcx, [rsp+4C0h+hKey]
0x180008281  lea     r9, aDenyallgpstate; "DenyAllGPState"
0x180008288  mov     r13d, 4
0x18000828e  xor     r8d, r8d
0x180008291  mov     dword ptr [rsp+4C0h+lpSecurityAttributes], r13d
0x180008296  mov     qword ptr [rsp+4C0h+samDesired], rdi
0x18000829b  mov     [rsp+4C0h+dwOptions], r13d
0x1800082a0  call    WPDLibSetRegistryValue
0x1800082a5  cmp     [rdi], ebx
0x1800082a7  jz      loc_1800085DC
0x1800082ad  mov     rdi, [r15+10h]
0x1800082b1  test    rdi, rdi
0x1800082b4  jz      loc_1800085B4
0x1800082ba  lea     rsi, WPP_GLOBAL_Control
0x1800082c1  lea     rcx, [rdi+10h]; rguid
0x1800082c5  mov     r8d, 104h; cchMax
0x1800082cb  lea     rdx, [rsp+4C0h+sz]; lpsz
0x1800082d0  call    cs:__imp_StringFromGUID2
0x1800082d6  test    eax, eax
0x1800082d8  jnz     short loc_1800082ED
0x1800082da  lea     rdx, aFailedToCreate_1; "Failed to create GUIDKeyName\n"
0x1800082e1  mov     ecx, ebx; unsigned int
0x1800082e3  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800082e8  jmp     loc_1800085A8
0x1800082ed  lea     rdx, [rsp+4C0h+sz]; lpSubKey
0x1800082f2  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800082f7  cmp     [rdi+30h], r12d
0x1800082fb  jz      short loc_18000831C
0x1800082fd  call    cs:__imp_RegDeleteKeyW
0x180008303  test    eax, eax
0x180008305  jz      loc_1800085A8
0x18000830b  lea     rdx, aRegdeletekeywF; "RegDeleteKeyW failed with (%d)\n"
0x180008312  mov     ecx, 8
0x180008317  jmp     loc_1800085A0
0x18000831c  mov     [rsp+4C0h+lpdwDisposition], r12; lpdwDisposition
0x180008321  lea     rax, [rsp+4C0h+var_470]
0x180008326  mov     [rsp+4C0h+phkResult], rax; phkResult
0x18000832b  xor     r9d, r9d; lpClass
0x18000832e  mov     [rsp+4C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180008333  xor     r8d, r8d; Reserved
0x180008336  mov     [rsp+4C0h+samDesired], 20006h; samDesired
0x18000833e  mov     [rsp+4C0h+dwOptions], r12d; dwOptions
0x180008343  mov     [rsp+4C0h+StringSecurityDescriptor], r12
0x180008348  mov     [rsp+4C0h+StringSecurityDescriptorLen], r12d
0x18000834d  mov     [rsp+4C0h+var_470], r12
0x180008352  call    cs:__imp_RegCreateKeyExW
0x180008358  test    eax, eax
0x18000835a  jnz     loc_180008597
0x180008360  mov     rcx, [rsp+4C0h+var_470]
0x180008365  lea     rax, [rdi+24h]
0x180008369  mov     dword ptr [rsp+4C0h+lpSecurityAttributes], r13d
0x18000836e  lea     r9, aEnumeratedevic; "EnumerateDevices"
0x180008375  mov     qword ptr [rsp+4C0h+samDesired], rax
0x18000837a  xor     r8d, r8d
0x18000837d  mov     [rsp+4C0h+dwOptions], r13d
0x180008382  call    WPDLibSetRegistryValue
0x180008387  test    eax, eax
0x180008389  jz      short loc_1800083C7
0x18000838b  call    ?SetRegCacheUpdated@CGroupPolicy@@IEAAJK@Z; CGroupPolicy::SetRegCacheUpdated(ulong)
0x180008390  mov     rcx, cs:WPP_GLOBAL_Control
0x180008397  cmp     rcx, rsi
0x18000839a  jz      short loc_1800083C7
0x18000839c  test    [rcx+1Ch], bl
0x18000839f  jz      short loc_1800083C7
0x1800083a1  mov     rcx, [rcx+10h]
0x1800083a5  lea     rax, [rsp+4C0h+sz]
0x1800083aa  mov     edx, 1Ch
0x1800083af  mov     qword ptr [rsp+4C0h+dwOptions], rax
0x1800083b4  lea     r9, [rbp+3C0h+SubKey]
0x1800083bb  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x1800083c2  call    WPP_SF_SS
0x1800083c7  mov     rcx, [rsp+4C0h+var_470]
0x1800083cc  lea     rax, [rdi+20h]
0x1800083d0  mov     dword ptr [rsp+4C0h+lpSecurityAttributes], r13d
0x1800083d5  lea     r9, aAccessbitmask; "AccessBitMask"
0x1800083dc  mov     qword ptr [rsp+4C0h+samDesired], rax
0x1800083e1  xor     r8d, r8d
0x1800083e4  mov     [rsp+4C0h+dwOptions], r13d
0x1800083e9  call    WPDLibSetRegistryValue
0x1800083ee  test    eax, eax
0x1800083f0  jz      short loc_18000842E
0x1800083f2  call    ?SetRegCacheUpdated@CGroupPolicy@@IEAAJK@Z; CGroupPolicy::SetRegCacheUpdated(ulong)
0x1800083f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083fe  cmp     rcx, rsi
0x180008401  jz      short loc_18000842E
0x180008403  test    [rcx+1Ch], bl
0x180008406  jz      short loc_18000842E
0x180008408  mov     rcx, [rcx+10h]
0x18000840c  lea     rax, [rsp+4C0h+sz]
0x180008411  mov     edx, 1Dh
0x180008416  mov     qword ptr [rsp+4C0h+dwOptions], rax
0x18000841b  lea     r9, [rbp+3C0h+SubKey]
0x180008422  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180008429  call    WPP_SF_SS
0x18000842e  mov     rcx, [rsp+4C0h+var_470]
0x180008433  lea     rax, [rdi+28h]
0x180008437  mov     dword ptr [rsp+4C0h+lpSecurityAttributes], r13d
0x18000843c  lea     r9, aUserpolicy; "UserPolicy"
0x180008443  mov     qword ptr [rsp+4C0h+samDesired], rax
0x180008448  xor     r8d, r8d
0x18000844b  mov     [rsp+4C0h+dwOptions], r13d
0x180008450  call    WPDLibSetRegistryValue
0x180008455  test    eax, eax
0x180008457  jz      short loc_180008495
0x180008459  call    ?SetRegCacheUpdated@CGroupPolicy@@IEAAJK@Z; CGroupPolicy::SetRegCacheUpdated(ulong)
0x18000845e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008465  cmp     rcx, rsi
0x180008468  jz      short loc_180008495
0x18000846a  test    [rcx+1Ch], bl
0x18000846d  jz      short loc_180008495
0x18000846f  mov     rcx, [rcx+10h]
0x180008473  lea     rax, [rsp+4C0h+sz]
0x180008478  mov     edx, 1Eh
0x18000847d  mov     qword ptr [rsp+4C0h+dwOptions], rax
0x180008482  lea     r9, [rbp+3C0h+SubKey]
0x180008489  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180008490  call    WPP_SF_SS
0x180008495  mov     rcx, [rsp+4C0h+var_470]
0x18000849a  lea     rax, [rdi+2Ch]
0x18000849e  mov     dword ptr [rsp+4C0h+lpSecurityAttributes], r13d
0x1800084a3  lea     r9, aAuditpolicyonl; "AuditPolicyOnly"
0x1800084aa  mov     qword ptr [rsp+4C0h+samDesired], rax
0x1800084af  xor     r8d, r8d
0x1800084b2  mov     [rsp+4C0h+dwOptions], r13d
0x1800084b7  call    WPDLibSetRegistryValue
0x1800084bc  test    eax, eax
0x1800084be  jz      short loc_1800084FC
0x1800084c0  call    ?SetRegCacheUpdated@CGroupPolicy@@IEAAJK@Z; CGroupPolicy::SetRegCacheUpdated(ulong)
0x1800084c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084cc  cmp     rcx, rsi
0x1800084cf  jz      short loc_1800084FC
0x1800084d1  test    [rcx+1Ch], bl
0x1800084d4  jz      short loc_1800084FC
0x1800084d6  mov     rcx, [rcx+10h]
0x1800084da  lea     rax, [rsp+4C0h+sz]
0x1800084df  mov     edx, 1Fh
0x1800084e4  mov     qword ptr [rsp+4C0h+dwOptions], rax
0x1800084e9  lea     r9, [rbp+3C0h+SubKey]
0x1800084f0  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x1800084f7  call    WPP_SF_SS
0x1800084fc  mov     rcx, [rdi+8]; SecurityDescriptor
0x180008500  lea     rax, [rsp+4C0h+StringSecurityDescriptorLen]
0x180008505  lea     r9, [rsp+4C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000850a  mov     qword ptr [rsp+4C0h+dwOptions], rax; StringSecurityDescriptorLen
0x18000850f  mov     r8d, r13d; SecurityInformation
0x180008512  mov     edx, 1; RequestedStringSDRevision
0x180008517  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000851d  test    eax, eax
0x18000851f  jz      short loc_180008573
0x180008521  mov     eax, [rsp+4C0h+StringSecurityDescriptorLen]
0x180008525  lea     r9, Value; "SecurityDescriptor"
0x18000852c  mov     rcx, [rsp+4C0h+var_470]
0x180008531  add     eax, eax
0x180008533  mov     dword ptr [rsp+4C0h+lpSecurityAttributes], eax
0x180008537  xor     r8d, r8d
0x18000853a  mov     rax, [rsp+4C0h+StringSecurityDescriptor]
0x18000853f  mov     qword ptr [rsp+4C0h+samDesired], rax
0x180008544  mov     [rsp+4C0h+dwOptions], 1
0x18000854c  call    WPDLibSetRegistryValue
0x180008551  test    eax, eax
0x180008553  jz      short loc_180008566
0x180008555  mov     r8d, eax
0x180008558  lea     rdx, aWpdlibsetregis; "WPDLibSetRegistryValue failed to set th"...
0x18000855f  mov     ecx, ebx; unsigned int
0x180008561  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180008566  mov     rcx, [rsp+4C0h+StringSecurityDescriptor]; hMem
0x18000856b  call    cs:__imp_LocalFree
0x180008571  jmp     short loc_18000858A
0x180008573  call    cs:__imp_GetLastError
0x180008579  lea     rdx, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x180008580  mov     ecx, ebx; unsigned int
0x180008582  mov     r8d, eax
0x180008585  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000858a  mov     rcx, [rsp+4C0h+var_470]; hKey
0x18000858f  call    cs:__imp_RegCloseKey
0x180008595  jmp     short loc_1800085A8
0x180008597  lea     rdx, aFailedToCreate; "Failed to create the storageguid key wi"...
0x18000859e  mov     ecx, ebx; unsigned int
0x1800085a0  mov     r8d, eax
0x1800085a3  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800085a8  mov     rdi, [rdi]
0x1800085ab  test    rdi, rdi
0x1800085ae  jnz     loc_1800082C1
0x1800085b4  mov     rdi, [r15+10h]
0x1800085b8  jmp     short loc_1800085D3
0x1800085ba  mov     rbx, rdi
0x1800085bd  mov     rdi, [rdi]
0x1800085c0  mov     rcx, [rbx+8]; hMem
0x1800085c4  call    cs:__imp_LocalFree
0x1800085ca  mov     rcx, rbx; hMem
0x1800085cd  call    cs:__imp_LocalFree
0x1800085d3  test    rdi, rdi
0x1800085d6  jnz     short loc_1800085BA
0x1800085d8  mov     [r15+10h], r12
0x1800085dc  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800085e1  test    rcx, rcx
0x1800085e4  jz      short loc_1800085EC
0x1800085e6  call    cs:__imp_RegCloseKey
0x1800085ec  mov     rcx, [rbp+3C0h+var_30]
0x1800085f3  xor     rcx, rsp; StackCookie
0x1800085f6  call    __security_check_cookie
0x1800085fb  lea     r11, [rsp+4C0h+var_20]
0x180008603  mov     rbx, [r11+38h]
0x180008607  mov     rsi, [r11+40h]
0x18000860b  mov     rsp, r11
0x18000860e  pop     r15
0x180008610  pop     r13
0x180008612  pop     r12
0x180008614  pop     rdi
0x180008615  pop     rbp
0x180008616  retn
```
