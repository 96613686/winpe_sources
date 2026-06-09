# InitializeSystemSecurityDescriptors(void)

- ea: `0x180083810`
- end: `0x180083db9`
- name: `?InitializeSystemSecurityDescriptors@@YAKXZ`
- size: `1449`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ed100`

## callees

- `0x180034540`
- `0x180040918`
- `0x1800672dc`
- `0x180083810`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x1800e95a0`
- `0x18010a000`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008385a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800838ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008385a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800838ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083cba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083b4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083be2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083c71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083cf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083b4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083be2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083c71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180083cf8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083b6c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083bff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083c8e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083d11`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083b6c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083bff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083c8e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180083d11`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083aff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083b92`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083c21`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083cb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083aff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083b92`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083c21`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180083cb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180083850`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800838c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180083850`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800838c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180083d50`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180083d5a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180083d50`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180083d5a`

## string_xrefs

- `0x1800838a1`: `InitializeSystemSecurityDescriptors`
- `0x1800838a8`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`

## pseudocode

```c
__int64 InitializeSystemSecurityDescriptors(void)
{
  WCHAR *p_SecurityDescriptorSize; // r14
  WCHAR *p_SecurityDescriptor; // rdi
  DWORD LastError; // esi
  int v3; // r8d
  __int64 v4; // rax
  __int64 v5; // rcx
  LPWSTR v6; // rdx
  int v7; // eax
  __int64 v8; // r15
  __int64 v9; // r12
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  WCHAR *v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  WCHAR *v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // r8
  struct CSecDescriptor *v23; // rax
  struct CSecDescriptor *v24; // r15
  PSECURITY_DESCRIPTOR v25; // rbx
  PSECURITY_DESCRIPTOR v26; // rcx
  DWORD SecurityDescriptorLength; // eax
  struct CSecDescriptor *v28; // rax
  struct CSecDescriptor *v29; // r15
  PSECURITY_DESCRIPTOR v30; // rbx
  PSECURITY_DESCRIPTOR v31; // rcx
  DWORD v32; // eax
  CSecDescriptor *v33; // rax
  CSecDescriptor *v34; // r15
  PSECURITY_DESCRIPTOR v35; // rbx
  PSECURITY_DESCRIPTOR v36; // rcx
  DWORD v37; // eax
  CSecDescriptor *v38; // rax
  CSecDescriptor *v39; // r15
  PSECURITY_DESCRIPTOR v40; // rbx
  PSECURITY_DESCRIPTOR v41; // rcx
  DWORD v42; // eax
  _BYTE v44[32]; // [rsp+0h] [rbp-30h] BYREF
  LPWSTR v45; // [rsp+20h] [rbp-10h]
  __int64 v46; // [rsp+28h] [rbp-8h]
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp+0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp+10h] BYREF
  LPWSTR v50; // [rsp+48h] [rbp+18h] BYREF

  p_SecurityDescriptorSize = 0;
  StringSid = 0;
  p_SecurityDescriptor = 0;
  v50 = 0;
  if ( ConvertSidToStringSidW(gSidDCOMUsers, &StringSid) )
  {
    if ( ConvertSidToStringSidW(gSidPerfLoggingUsers, &v50) )
    {
      v4 = -1;
      v5 = -1;
      LastError = 14;
      do
        ++v5;
      while ( StringSid[v5] );
      v6 = v50;
      do
        ++v4;
      while ( v50[v4] );
      v7 = 2 * (v5 + v4);
      v8 = (unsigned int)(v7 + 730);
      v9 = (unsigned int)(v7 + 742);
      if ( v7 == -730 )
        goto LABEL_82;
      if ( (unsigned int)v8 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_82;
      v10 = (unsigned int)v8 + g_ulAdditionalProbeSize + 8;
      if ( v10 < (unsigned int)v8 || !(unsigned int)VerifyStackAvailable(v10, v50) )
        goto LABEL_82;
      v11 = v8 + 23;
      if ( v8 + 23 <= (unsigned __int64)(v8 + 8) )
        v11 = 0xFFFFFFFFFFFFFF0LL;
      v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      v13 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      p_SecurityDescriptorSize = (WCHAR *)&SecurityDescriptorSize;
      if ( v44 == (_BYTE *)-48LL
        || (SecurityDescriptorSize = 1801679955, (p_SecurityDescriptorSize = (WCHAR *)&SecurityDescriptor) == 0) )
      {
LABEL_82:
        if ( v8 + 8 >= (unsigned __int64)(unsigned int)v8 )
        {
          v14 = (WCHAR *)((__int64 (__fastcall *)(__int64, LPWSTR))g_pfnAllocate)(v8 + 8, v6);
          p_SecurityDescriptorSize = v14;
          if ( v14 )
          {
            *(_DWORD *)v14 = 1885431112;
            p_SecurityDescriptorSize = v14 + 4;
          }
        }
      }
      p_SecurityDescriptor = 0;
      if ( !(_DWORD)v9 )
        goto LABEL_83;
      if ( (unsigned int)v9 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_83;
      v15 = (unsigned int)v9 + g_ulAdditionalProbeSize + 8;
      if ( v15 < (unsigned int)v9 || !(unsigned int)VerifyStackAvailable(v15, v6) )
        goto LABEL_83;
      v16 = v9 + 23;
      if ( v9 + 23 <= (unsigned __int64)(v9 + 8) )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
      v18 = alloca(v17);
      v19 = alloca(v17);
      p_SecurityDescriptor = (WCHAR *)&SecurityDescriptorSize;
      if ( v44 == (_BYTE *)-48LL
        || (SecurityDescriptorSize = 1801679955, (p_SecurityDescriptor = (WCHAR *)&SecurityDescriptor) == 0) )
      {
LABEL_83:
        if ( v9 + 8 >= (unsigned __int64)(unsigned int)v9 )
        {
          v20 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_SecurityDescriptor = v20;
          if ( v20 )
          {
            *(_DWORD *)v20 = 1885431112;
            p_SecurityDescriptor = v20 + 4;
          }
        }
      }
      if ( p_SecurityDescriptorSize && p_SecurityDescriptor )
      {
        v21 = IsWorkstationOS();
        v22 = L"O:BAG:BAD:(A;;0x7;;;WD)(A;;0x3;;;AN)(A;;0x7;;;%s)(A;;0x7;;;%s)(A;;0x3;;;AC)(A;;0x3;;;S-1-15-3-1024-2405443"
               "489-874036122-4286035555-1823921565-1746547431-2453885448-3625952902-991631256)";
        v45 = v50;
        if ( !v21 )
          v22 = L"O:BAG:BAD:(A;;0x7;;;WD)(A;;0x7;;;AN)(A;;0x7;;;%s)(A;;0x7;;;%s)(A;;0x3;;;AC)(A;;0x3;;;S-1-15-3-1024-24054"
                 "43489-874036122-4286035555-1823921565-1746547431-2453885448-3625952902-991631256)";
        if ( (int)StringCbPrintfW(p_SecurityDescriptorSize, (unsigned int)v8, v22, StringSid, v45) >= 0
          && (int)StringCbPrintfW(
                    p_SecurityDescriptor,
                    (unsigned int)v9,
                    L"O:BAG:BAD:(A;;0x1f;;;BA)(A;;0xb;;;WD)(A;;0x1f;;;%s)(A;;0x1f;;;%s)(A;;0xb;;;AC)(A;;0xb;;;S-1-15-3-102"
                     "4-2405443489-874036122-4286035555-1823921565-1746547431-2453885448-3625952902-991631256)",
                    StringSid,
                    v50) >= 0 )
        {
          SecurityDescriptor = 0;
          SecurityDescriptorSize = 0;
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 L"O:BAG:BAD:(A;;0x1f;;;BA)(A;;0xb;;;IU)(A;;0xb;;;SY)",
                 1u,
                 &SecurityDescriptor,
                 &SecurityDescriptorSize) )
          {
            v23 = (struct CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
            v24 = v23;
            if ( !v23 )
            {
              gpNoRegLaunchPermissionsSD = 0;
              goto LABEL_73;
            }
            v25 = SecurityDescriptor;
            v26 = SecurityDescriptor;
            *((_DWORD *)v23 + 3) = 1;
            SecurityDescriptorLength = GetSecurityDescriptorLength(v26);
            *(_QWORD *)v24 = v25;
            *((_DWORD *)v24 + 2) = SecurityDescriptorLength;
            gpNoRegLaunchPermissionsSD = v24;
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                   L"O:BAG:BAD:(A;;0x7;;;PS)(A;;0x3;;;SY)(A;;0x7;;;BA)",
                   1u,
                   &SecurityDescriptor,
                   &SecurityDescriptorSize) )
            {
              v28 = (struct CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
              v29 = v28;
              if ( !v28 )
              {
                gpNoRegAccessPermissionsSD = 0;
                goto LABEL_73;
              }
              v30 = SecurityDescriptor;
              v31 = SecurityDescriptor;
              *((_DWORD *)v28 + 3) = 1;
              v32 = GetSecurityDescriptorLength(v31);
              *(_QWORD *)v29 = v30;
              *((_DWORD *)v29 + 2) = v32;
              gpNoRegAccessPermissionsSD = v29;
              if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                     p_SecurityDescriptor,
                     1u,
                     &SecurityDescriptor,
                     &SecurityDescriptorSize) )
              {
                v33 = (CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
                v34 = v33;
                if ( !v33 )
                {
                  gpNoRegLaunchRestrictionsSD = 0;
                  goto LABEL_73;
                }
                v35 = SecurityDescriptor;
                v36 = SecurityDescriptor;
                *((_DWORD *)v33 + 3) = 1;
                v37 = GetSecurityDescriptorLength(v36);
                *(_QWORD *)v34 = v35;
                *((_DWORD *)v34 + 2) = v37;
                gpNoRegLaunchRestrictionsSD = v34;
                if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                       p_SecurityDescriptorSize,
                       1u,
                       &SecurityDescriptor,
                       &SecurityDescriptorSize) )
                {
                  v38 = (CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
                  v39 = v38;
                  if ( v38 )
                  {
                    v40 = SecurityDescriptor;
                    v41 = SecurityDescriptor;
                    *((_DWORD *)v38 + 3) = 1;
                    v42 = GetSecurityDescriptorLength(v41);
                    *(_QWORD *)v39 = v40;
                    LastError = 0;
                    *((_DWORD *)v39 + 2) = v42;
                    gpNoRegAccessRestrictionsSD = v39;
                  }
                  else
                  {
                    gpNoRegAccessRestrictionsSD = 0;
                  }
                }
                else
                {
                  LastError = GetLastError();
                  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v3 = 340;
                    goto LABEL_6;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                {
                  v3 = 329;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v3 = 318;
                goto LABEL_6;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            {
              v3 = 307;
              goto LABEL_6;
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v3 = 235;
        goto LABEL_6;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v3 = 227;
LABEL_6:
      LODWORD(v46) = LastError;
      ComTraceMessageT<int>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
        (unsigned int)"InitializeSystemSecurityDescriptors",
        v3,
        0,
        (__int64)L"%!WINERROR!",
        v46);
    }
  }
LABEL_73:
  LocalFree(StringSid);
  LocalFree(v50);
  if ( p_SecurityDescriptorSize && *((_DWORD *)p_SecurityDescriptorSize - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( p_SecurityDescriptor && *((_DWORD *)p_SecurityDescriptor - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return LastError;
}

```

## disassembly

```asm
0x180083810  push    rbp
0x180083812  push    rbx
0x180083813  push    rsi
0x180083814  push    rdi
0x180083815  push    r12
0x180083817  push    r13
0x180083819  push    r14
0x18008381b  push    r15
0x18008381d  sub     rsp, 68h
0x180083821  lea     rbp, [rsp+30h]
0x180083826  mov     rax, cs:__security_cookie
0x18008382d  xor     rax, rbp
0x180083830  mov     [rbp+70h+var_48], rax
0x180083834  mov     rcx, cs:?gSidDCOMUsers@@3PEAXEA; Sid
0x18008383b  lea     rdx, [rbp+70h+StringSid]; StringSid
0x18008383f  xor     r13d, r13d
0x180083842  mov     r14d, r13d
0x180083845  mov     [rbp+70h+StringSid], r13
0x180083849  mov     edi, r13d
0x18008384c  mov     [rbp+70h+var_58], r13
0x180083850  call    cs:__imp_ConvertSidToStringSidW
0x180083856  test    eax, eax
0x180083858  jnz     short loc_1800838B9
0x18008385a  call    cs:__imp_GetLastError
0x180083860  mov     esi, eax
0x180083862  mov     eax, cs:dword_18014E4B8
0x180083868  test    eax, eax
0x18008386a  jnz     short loc_180083888
0x18008386c  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180083873  jz      loc_180083D4C
0x180083879  xor     ecx, ecx
0x18008387b  call    IsWppLevelEnabled
0x180083880  test    al, al
0x180083882  jz      loc_180083D4C
0x180083888  mov     r8d, 0E3h
0x18008388e  lea     rax, aWinerror; "%!WINERROR!"
0x180083895  mov     dword ptr [rsp+0A0h+var_78], esi
0x180083899  xor     r9d, r9d
0x18008389c  mov     [rsp+0A0h+var_80], rax
0x1800838a1  lea     rdx, aInitializesyst; "InitializeSystemSecurityDescriptors"
0x1800838a8  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800838af  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800838b4  jmp     loc_180083D4C
0x1800838b9  mov     rcx, cs:?gSidPerfLoggingUsers@@3PEAXEA; Sid
0x1800838c0  lea     rdx, [rbp+70h+var_58]; StringSid
0x1800838c4  call    cs:__imp_ConvertSidToStringSidW
0x1800838ca  test    eax, eax
0x1800838cc  jnz     short loc_180083904
0x1800838ce  call    cs:__imp_GetLastError
0x1800838d4  mov     esi, eax
0x1800838d6  mov     eax, cs:dword_18014E4B8
0x1800838dc  test    eax, eax
0x1800838de  jnz     short loc_1800838FC
0x1800838e0  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800838e7  jz      loc_180083D4C
0x1800838ed  xor     ecx, ecx
0x1800838ef  call    IsWppLevelEnabled
0x1800838f4  test    al, al
0x1800838f6  jz      loc_180083D4C
0x1800838fc  mov     r8d, 0EBh
0x180083902  jmp     short loc_18008388E
0x180083904  mov     rdx, [rbp+70h+StringSid]
0x180083908  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008390c  mov     rcx, rax
0x18008390f  mov     esi, 0Eh
0x180083914  inc     rcx
0x180083917  cmp     [rdx+rcx*2], r13w
0x18008391c  jnz     short loc_180083914
0x18008391e  mov     rdx, [rbp+70h+var_58]
0x180083922  inc     rax
0x180083925  cmp     [rdx+rax*2], r13w
0x18008392a  jnz     short loc_180083922
0x18008392c  add     eax, ecx
0x18008392e  mov     rdi, 0FFFFFFFFFFFFFF0h
0x180083938  add     eax, eax
0x18008393a  lea     r15d, [rax+2DAh]
0x180083941  lea     r12d, [rax+2E6h]
0x180083948  test    r15d, r15d
0x18008394b  jz      short loc_1800839AB
0x18008394d  mov     ebx, r15d
0x180083950  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180083957  ja      short loc_1800839AB
0x180083959  mov     rcx, cs:g_ulAdditionalProbeSize
0x180083960  add     rcx, 8
0x180083964  add     rcx, rbx
0x180083967  cmp     rcx, rbx
0x18008396a  jb      short loc_1800839AB
0x18008396c  call    VerifyStackAvailable
0x180083971  test    eax, eax
0x180083973  jz      short loc_1800839AB
0x180083975  lea     rax, [r15+8]
0x180083979  lea     rcx, [rax+0Fh]
0x18008397d  cmp     rcx, rax
0x180083980  ja      short loc_180083985
0x180083982  mov     rcx, rdi
0x180083985  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180083989  mov     rax, rcx
0x18008398c  call    _alloca_probe
0x180083991  sub     rsp, rcx
0x180083994  lea     r14, [rsp+0A0h+SecurityDescriptorSize]
0x180083999  test    r14, r14
0x18008399c  jz      short loc_1800839AB
0x18008399e  mov     dword ptr [r14], 6B637453h
0x1800839a5  add     r14, 8
0x1800839a9  jnz     short loc_1800839D5
0x1800839ab  mov     eax, r15d
0x1800839ae  lea     rcx, [r15+8]
0x1800839b2  cmp     rcx, rax
0x1800839b5  jb      short loc_1800839D5
0x1800839b7  mov     rax, cs:g_pfnAllocate
0x1800839be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839c3  mov     r14, rax
0x1800839c6  test    rax, rax
0x1800839c9  jz      short loc_1800839D5
0x1800839cb  mov     dword ptr [rax], 70616548h
0x1800839d1  add     r14, 8
0x1800839d5  mov     rdi, r13
0x1800839d8  test    r12d, r12d
0x1800839db  jz      short loc_180083A42
0x1800839dd  mov     ebx, r12d
0x1800839e0  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800839e7  ja      short loc_180083A42
0x1800839e9  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800839f0  add     rcx, 8
0x1800839f4  add     rcx, rbx
0x1800839f7  cmp     rcx, rbx
0x1800839fa  jb      short loc_180083A42
0x1800839fc  call    VerifyStackAvailable
0x180083a01  test    eax, eax
0x180083a03  jz      short loc_180083A42
0x180083a05  lea     rax, [r12+8]
0x180083a0a  lea     rcx, [rax+0Fh]
0x180083a0e  cmp     rcx, rax
0x180083a11  ja      short loc_180083A1D
0x180083a13  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180083a1d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180083a21  mov     rax, rcx
0x180083a24  call    _alloca_probe
0x180083a29  sub     rsp, rcx
0x180083a2c  lea     rdi, [rsp+0A0h+SecurityDescriptorSize]
0x180083a31  test    rdi, rdi
0x180083a34  jz      short loc_180083A42
0x180083a36  mov     dword ptr [rdi], 6B637453h
0x180083a3c  add     rdi, 8
0x180083a40  jnz     short loc_180083A6D
0x180083a42  mov     eax, r12d
0x180083a45  lea     rcx, [r12+8]
0x180083a4a  cmp     rcx, rax
0x180083a4d  jb      short loc_180083A6D
0x180083a4f  mov     rax, cs:g_pfnAllocate
0x180083a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a5b  mov     rdi, rax
0x180083a5e  test    rax, rax
0x180083a61  jz      short loc_180083A6D
0x180083a63  mov     dword ptr [rax], 70616548h
0x180083a69  add     rdi, 8
0x180083a6d  test    r14, r14
0x180083a70  jz      loc_180083D4C
0x180083a76  test    rdi, rdi
0x180083a79  jz      loc_180083D4C
0x180083a7f  mov     ebx, r15d
0x180083a82  call    ?IsWorkstationOS@@YAHXZ; IsWorkstationOS(void)
0x180083a87  mov     r9, [rbp+70h+StringSid]
0x180083a8b  lea     r8, aOBagBadA0x7WdA_0; "O:BAG:BAD:(A;;0x7;;;WD)(A;;0x3;;;AN)(A;"...
0x180083a92  test    eax, eax
0x180083a94  mov     edx, ebx; unsigned __int64
0x180083a96  mov     rax, [rbp+70h+var_58]
0x180083a9a  mov     rcx, r14; unsigned __int16 *
0x180083a9d  mov     [rsp+0A0h+var_80], rax
0x180083aa2  jnz     short loc_180083AAB
0x180083aa4  lea     r8, aOBagBadA0x7WdA; "O:BAG:BAD:(A;;0x7;;;WD)(A;;0x7;;;AN)(A;"...
0x180083aab  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083ab0  test    eax, eax
0x180083ab2  js      loc_180083D4C
0x180083ab8  mov     rax, [rbp+70h+var_58]
0x180083abc  lea     r8, aOBagBadA0x1fBa; "O:BAG:BAD:(A;;0x1f;;;BA)(A;;0xb;;;WD)(A"...
0x180083ac3  mov     r9, [rbp+70h+StringSid]
0x180083ac7  mov     rcx, rdi; unsigned __int16 *
0x180083aca  mov     edx, r12d; unsigned __int64
0x180083acd  mov     [rsp+0A0h+var_80], rax
0x180083ad2  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083ad7  test    eax, eax
0x180083ad9  js      loc_180083D4C
0x180083adf  mov     r12d, 1
0x180083ae5  mov     [rbp+70h+SecurityDescriptor], r13
0x180083ae9  mov     edx, r12d; StringSDRevision
0x180083aec  mov     [rbp+70h+SecurityDescriptorSize], r13d
0x180083af0  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180083af4  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x180083af8  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1f;;;BA)(A;;0xb;;;IU)(A"...
0x180083aff  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180083b05  test    eax, eax
0x180083b07  jnz     short loc_180083B42
0x180083b09  call    cs:__imp_GetLastError
0x180083b0f  mov     esi, eax
0x180083b11  mov     eax, cs:dword_18014E4B8
0x180083b17  test    eax, eax
0x180083b19  jnz     short loc_180083B37
0x180083b1b  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180083b22  jz      loc_180083D4C
0x180083b28  xor     ecx, ecx
0x180083b2a  call    IsWppLevelEnabled
0x180083b2f  test    al, al
0x180083b31  jz      loc_180083D4C
0x180083b37  mov     r8d, 133h
0x180083b3d  jmp     loc_18008388E
0x180083b42  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180083b49  xor     edx, edx; dwFlags
0x180083b4b  lea     r8d, [rdx+10h]; dwBytes
0x180083b4f  call    cs:__imp_HeapAlloc
0x180083b55  mov     r15, rax
0x180083b58  test    rax, rax
0x180083b5b  jz      loc_180083D45
0x180083b61  mov     rbx, [rbp+70h+SecurityDescriptor]
0x180083b65  mov     rcx, rbx; pSecurityDescriptor
0x180083b68  mov     [rax+0Ch], r12d
0x180083b6c  call    cs:__imp_GetSecurityDescriptorLength
0x180083b72  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180083b76  mov     [r15], rbx
0x180083b79  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x180083b7d  mov     [r15+8], eax
0x180083b81  mov     edx, r12d; StringSDRevision
0x180083b84  mov     cs:?gpNoRegLaunchPermissionsSD@@3PEAVCSecDescriptor@@EA, r15; CSecDescriptor * gpNoRegLaunchPermissionsSD
0x180083b8b  lea     rcx, aOBagBadA0x7PsA; "O:BAG:BAD:(A;;0x7;;;PS)(A;;0x3;;;SY)(A;"...
0x180083b92  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180083b98  test    eax, eax
0x180083b9a  jnz     short loc_180083BD5
0x180083b9c  call    cs:__imp_GetLastError
0x180083ba2  mov     esi, eax
0x180083ba4  mov     eax, cs:dword_18014E4B8
0x180083baa  test    eax, eax
0x180083bac  jnz     short loc_180083BCA
0x180083bae  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180083bb5  jz      loc_180083D4C
0x180083bbb  xor     ecx, ecx
0x180083bbd  call    IsWppLevelEnabled
0x180083bc2  test    al, al
0x180083bc4  jz      loc_180083D4C
0x180083bca  mov     r8d, 13Eh
0x180083bd0  jmp     loc_18008388E
0x180083bd5  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180083bdc  xor     edx, edx; dwFlags
0x180083bde  lea     r8d, [rdx+10h]; dwBytes
0x180083be2  call    cs:__imp_HeapAlloc
0x180083be8  mov     r15, rax
0x180083beb  test    rax, rax
0x180083bee  jz      loc_180083D3C
0x180083bf4  mov     rbx, [rbp+70h+SecurityDescriptor]
0x180083bf8  mov     rcx, rbx; pSecurityDescriptor
0x180083bfb  mov     [rax+0Ch], r12d
0x180083bff  call    cs:__imp_GetSecurityDescriptorLength
0x180083c05  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180083c09  mov     [r15], rbx
0x180083c0c  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x180083c10  mov     [r15+8], eax
0x180083c14  mov     edx, r12d; StringSDRevision
0x180083c17  mov     cs:?gpNoRegAccessPermissionsSD@@3PEAVCSecDescriptor@@EA, r15; CSecDescriptor * gpNoRegAccessPermissionsSD
0x180083c1e  mov     rcx, rdi; StringSecurityDescriptor
0x180083c21  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180083c27  test    eax, eax
0x180083c29  jnz     short loc_180083C64
0x180083c2b  call    cs:__imp_GetLastError
0x180083c31  mov     esi, eax
0x180083c33  mov     eax, cs:dword_18014E4B8
0x180083c39  test    eax, eax
0x180083c3b  jnz     short loc_180083C59
0x180083c3d  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180083c44  jz      loc_180083D4C
0x180083c4a  xor     ecx, ecx
0x180083c4c  call    IsWppLevelEnabled
0x180083c51  test    al, al
0x180083c53  jz      loc_180083D4C
0x180083c59  mov     r8d, 149h
0x180083c5f  jmp     loc_18008388E
0x180083c64  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180083c6b  xor     edx, edx; dwFlags
0x180083c6d  lea     r8d, [rdx+10h]; dwBytes
0x180083c71  call    cs:__imp_HeapAlloc
0x180083c77  mov     r15, rax
0x180083c7a  test    rax, rax
0x180083c7d  jz      loc_180083D33
0x180083c83  mov     rbx, [rbp+70h+SecurityDescriptor]
0x180083c87  mov     rcx, rbx; pSecurityDescriptor
0x180083c8a  mov     [rax+0Ch], r12d
0x180083c8e  call    cs:__imp_GetSecurityDescriptorLength
0x180083c94  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180083c98  mov     [r15], rbx
0x180083c9b  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x180083c9f  mov     [r15+8], eax
0x180083ca3  mov     edx, r12d; StringSDRevision
0x180083ca6  mov     cs:?gpNoRegLaunchRestrictionsSD@@3PEAVCSecDescriptor@@EA, r15; CSecDescriptor * gpNoRegLaunchRestrictionsSD
0x180083cad  mov     rcx, r14; StringSecurityDescriptor
0x180083cb0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180083cb6  test    eax, eax
0x180083cb8  jnz     short loc_180083CEB
0x180083cba  call    cs:__imp_GetLastError
0x180083cc0  mov     esi, eax
0x180083cc2  mov     eax, cs:dword_18014E4B8
0x180083cc8  test    eax, eax
0x180083cca  jnz     short loc_180083CE0
  ... truncated ...
```
