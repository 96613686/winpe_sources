# InitializeSystemSecurityDescriptors(void)

- ea: `0x1800881a4`
- end: `0x1800887d9`
- name: `?InitializeSystemSecurityDescriptors@@YAKXZ`
- size: `1589`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f4c18`

## callees

- `0x180034260`
- `0x18004a3f4`
- `0x18006bdc4`
- `0x1800881a4`
- `0x1800a7388`
- `0x1800b7ac0`
- `0x1800f0dd4`
- `0x180112d00`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800881f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800881f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008850a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800885b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008865c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800886ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008850a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800885b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008865c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800886ff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008852d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800885d8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008867f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008871e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008852d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800885d8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008867f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008871e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800884ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180088559`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180088600`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800886a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800884ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180088559`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180088600`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800886a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800881e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180088264`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800881e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180088264`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180088763`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180088773`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180088763`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180088773`

## string_xrefs

- `0x180088248`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x180088241`: `InitializeSystemSecurityDescriptors`

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
                  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v3 = 340;
                    goto LABEL_6;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                {
                  v3 = 329;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v3 = 318;
                goto LABEL_6;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v3 = 235;
        goto LABEL_6;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x1800881a4  push    rbp
0x1800881a6  push    rbx
0x1800881a7  push    rsi
0x1800881a8  push    rdi
0x1800881a9  push    r12
0x1800881ab  push    r13
0x1800881ad  push    r14
0x1800881af  push    r15
0x1800881b1  sub     rsp, 68h
0x1800881b5  lea     rbp, [rsp+30h]
0x1800881ba  mov     rax, cs:__security_cookie
0x1800881c1  xor     rax, rbp
0x1800881c4  mov     [rbp+70h+var_48], rax
0x1800881c8  mov     rcx, cs:?gSidDCOMUsers@@3PEAXEA; Sid
0x1800881cf  lea     rdx, [rbp+70h+StringSid]; StringSid
0x1800881d3  xor     r13d, r13d
0x1800881d6  mov     r14d, r13d
0x1800881d9  mov     [rbp+70h+StringSid], r13
0x1800881dd  mov     edi, r13d
0x1800881e0  mov     [rbp+70h+var_58], r13
0x1800881e4  call    cs:__imp_ConvertSidToStringSidW
0x1800881eb  nop     dword ptr [rax+rax+00h]
0x1800881f0  test    eax, eax
0x1800881f2  jnz     short loc_180088259
0x1800881f4  call    cs:__imp_GetLastError
0x1800881fb  nop     dword ptr [rax+rax+00h]
0x180088200  mov     esi, eax
0x180088202  mov     eax, cs:dword_1801574B8
0x180088208  test    eax, eax
0x18008820a  jnz     short loc_180088228
0x18008820c  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180088213  jz      loc_18008875F
0x180088219  xor     ecx, ecx
0x18008821b  call    IsWppLevelEnabled
0x180088220  test    al, al
0x180088222  jz      loc_18008875F
0x180088228  mov     r8d, 0E3h
0x18008822e  lea     rax, aWinerror; "%!WINERROR!"
0x180088235  mov     dword ptr [rsp+0A0h+var_78], esi
0x180088239  xor     r9d, r9d
0x18008823c  mov     [rsp+0A0h+var_80], rax
0x180088241  lea     rdx, aInitializesyst; "InitializeSystemSecurityDescriptors"
0x180088248  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18008824f  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180088254  jmp     loc_18008875F
0x180088259  mov     rcx, cs:?gSidPerfLoggingUsers@@3PEAXEA; Sid
0x180088260  lea     rdx, [rbp+70h+var_58]; StringSid
0x180088264  call    cs:__imp_ConvertSidToStringSidW
0x18008826b  nop     dword ptr [rax+rax+00h]
0x180088270  test    eax, eax
0x180088272  jnz     short loc_1800882B3
0x180088274  call    cs:__imp_GetLastError
0x18008827b  nop     dword ptr [rax+rax+00h]
0x180088280  mov     esi, eax
0x180088282  mov     eax, cs:dword_1801574B8
0x180088288  test    eax, eax
0x18008828a  jnz     short loc_1800882A8
0x18008828c  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180088293  jz      loc_18008875F
0x180088299  xor     ecx, ecx
0x18008829b  call    IsWppLevelEnabled
0x1800882a0  test    al, al
0x1800882a2  jz      loc_18008875F
0x1800882a8  mov     r8d, 0EBh
0x1800882ae  jmp     loc_18008822E
0x1800882b3  mov     rdx, [rbp+70h+StringSid]
0x1800882b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800882bb  mov     rcx, rax
0x1800882be  mov     esi, 0Eh
0x1800882c3  inc     rcx
0x1800882c6  cmp     [rdx+rcx*2], r13w
0x1800882cb  jnz     short loc_1800882C3
0x1800882cd  mov     rdx, [rbp+70h+var_58]
0x1800882d1  inc     rax
0x1800882d4  cmp     [rdx+rax*2], r13w
0x1800882d9  jnz     short loc_1800882D1
0x1800882db  add     eax, ecx
0x1800882dd  mov     rdi, 0FFFFFFFFFFFFFF0h
0x1800882e7  add     eax, eax
0x1800882e9  lea     r15d, [rax+2DAh]
0x1800882f0  lea     r12d, [rax+2E6h]
0x1800882f7  test    r15d, r15d
0x1800882fa  jz      short loc_18008835A
0x1800882fc  mov     ebx, r15d
0x1800882ff  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180088306  ja      short loc_18008835A
0x180088308  mov     rcx, cs:g_ulAdditionalProbeSize
0x18008830f  add     rcx, 8
0x180088313  add     rcx, rbx
0x180088316  cmp     rcx, rbx
0x180088319  jb      short loc_18008835A
0x18008831b  call    VerifyStackAvailable
0x180088320  test    eax, eax
0x180088322  jz      short loc_18008835A
0x180088324  lea     rax, [r15+8]
0x180088328  lea     rcx, [rax+0Fh]
0x18008832c  cmp     rcx, rax
0x18008832f  ja      short loc_180088334
0x180088331  mov     rcx, rdi
0x180088334  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180088338  mov     rax, rcx
0x18008833b  call    _alloca_probe
0x180088340  sub     rsp, rcx
0x180088343  lea     r14, [rsp+0A0h+SecurityDescriptorSize]
0x180088348  test    r14, r14
0x18008834b  jz      short loc_18008835A
0x18008834d  mov     dword ptr [r14], 6B637453h
0x180088354  add     r14, 8
0x180088358  jnz     short loc_180088384
0x18008835a  mov     eax, r15d
0x18008835d  lea     rcx, [r15+8]
0x180088361  cmp     rcx, rax
0x180088364  jb      short loc_180088384
0x180088366  mov     rax, cs:g_pfnAllocate
0x18008836d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088372  mov     r14, rax
0x180088375  test    rax, rax
0x180088378  jz      short loc_180088384
0x18008837a  mov     dword ptr [rax], 70616548h
0x180088380  add     r14, 8
0x180088384  mov     rdi, r13
0x180088387  test    r12d, r12d
0x18008838a  jz      short loc_1800883F1
0x18008838c  mov     ebx, r12d
0x18008838f  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180088396  ja      short loc_1800883F1
0x180088398  mov     rcx, cs:g_ulAdditionalProbeSize
0x18008839f  add     rcx, 8
0x1800883a3  add     rcx, rbx
0x1800883a6  cmp     rcx, rbx
0x1800883a9  jb      short loc_1800883F1
0x1800883ab  call    VerifyStackAvailable
0x1800883b0  test    eax, eax
0x1800883b2  jz      short loc_1800883F1
0x1800883b4  lea     rax, [r12+8]
0x1800883b9  lea     rcx, [rax+0Fh]
0x1800883bd  cmp     rcx, rax
0x1800883c0  ja      short loc_1800883CC
0x1800883c2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800883cc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800883d0  mov     rax, rcx
0x1800883d3  call    _alloca_probe
0x1800883d8  sub     rsp, rcx
0x1800883db  lea     rdi, [rsp+0A0h+SecurityDescriptorSize]
0x1800883e0  test    rdi, rdi
0x1800883e3  jz      short loc_1800883F1
0x1800883e5  mov     dword ptr [rdi], 6B637453h
0x1800883eb  add     rdi, 8
0x1800883ef  jnz     short loc_18008841C
0x1800883f1  mov     eax, r12d
0x1800883f4  lea     rcx, [r12+8]
0x1800883f9  cmp     rcx, rax
0x1800883fc  jb      short loc_18008841C
0x1800883fe  mov     rax, cs:g_pfnAllocate
0x180088405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008840a  mov     rdi, rax
0x18008840d  test    rax, rax
0x180088410  jz      short loc_18008841C
0x180088412  mov     dword ptr [rax], 70616548h
0x180088418  add     rdi, 8
0x18008841c  test    r14, r14
0x18008841f  jz      loc_18008875F
0x180088425  test    rdi, rdi
0x180088428  jz      loc_18008875F
0x18008842e  mov     ebx, r15d
0x180088431  call    ?IsWorkstationOS@@YAHXZ; IsWorkstationOS(void)
0x180088436  mov     r9, [rbp+70h+StringSid]
0x18008843a  lea     r8, aOBagBadA0x7WdA_0; "O:BAG:BAD:(A;;0x7;;;WD)(A;;0x3;;;AN)(A;"...
0x180088441  test    eax, eax
0x180088443  mov     edx, ebx; unsigned __int64
0x180088445  mov     rax, [rbp+70h+var_58]
0x180088449  mov     rcx, r14; unsigned __int16 *
0x18008844c  mov     [rsp+0A0h+var_80], rax
0x180088451  jnz     short loc_18008845A
0x180088453  lea     r8, aOBagBadA0x7WdA; "O:BAG:BAD:(A;;0x7;;;WD)(A;;0x7;;;AN)(A;"...
0x18008845a  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008845f  test    eax, eax
0x180088461  js      loc_18008875F
0x180088467  mov     rax, [rbp+70h+var_58]
0x18008846b  lea     r8, aOBagBadA0x1fBa; "O:BAG:BAD:(A;;0x1f;;;BA)(A;;0xb;;;WD)(A"...
0x180088472  mov     r9, [rbp+70h+StringSid]
0x180088476  mov     rcx, rdi; unsigned __int16 *
0x180088479  mov     edx, r12d; unsigned __int64
0x18008847c  mov     [rsp+0A0h+var_80], rax
0x180088481  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180088486  test    eax, eax
0x180088488  js      loc_18008875F
0x18008848e  mov     r12d, 1
0x180088494  mov     [rbp+70h+SecurityDescriptor], r13
0x180088498  mov     edx, r12d; StringSDRevision
0x18008849b  mov     [rbp+70h+SecurityDescriptorSize], r13d
0x18008849f  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800884a3  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x1800884a7  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1f;;;BA)(A;;0xb;;;IU)(A"...
0x1800884ae  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800884b5  nop     dword ptr [rax+rax+00h]
0x1800884ba  test    eax, eax
0x1800884bc  jnz     short loc_1800884FD
0x1800884be  call    cs:__imp_GetLastError
0x1800884c5  nop     dword ptr [rax+rax+00h]
0x1800884ca  mov     esi, eax
0x1800884cc  mov     eax, cs:dword_1801574B8
0x1800884d2  test    eax, eax
0x1800884d4  jnz     short loc_1800884F2
0x1800884d6  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800884dd  jz      loc_18008875F
0x1800884e3  xor     ecx, ecx
0x1800884e5  call    IsWppLevelEnabled
0x1800884ea  test    al, al
0x1800884ec  jz      loc_18008875F
0x1800884f2  mov     r8d, 133h
0x1800884f8  jmp     loc_18008822E
0x1800884fd  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180088504  xor     edx, edx; dwFlags
0x180088506  lea     r8d, [rdx+10h]; dwBytes
0x18008850a  call    cs:__imp_HeapAlloc
0x180088511  nop     dword ptr [rax+rax+00h]
0x180088516  mov     r15, rax
0x180088519  test    rax, rax
0x18008851c  jz      loc_180088758
0x180088522  mov     rbx, [rbp+70h+SecurityDescriptor]
0x180088526  mov     rcx, rbx; pSecurityDescriptor
0x180088529  mov     [rax+0Ch], r12d
0x18008852d  call    cs:__imp_GetSecurityDescriptorLength
0x180088534  nop     dword ptr [rax+rax+00h]
0x180088539  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18008853d  mov     [r15], rbx
0x180088540  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x180088544  mov     [r15+8], eax
0x180088548  mov     edx, r12d; StringSDRevision
0x18008854b  mov     cs:?gpNoRegLaunchPermissionsSD@@3PEAVCSecDescriptor@@EA, r15; CSecDescriptor * gpNoRegLaunchPermissionsSD
0x180088552  lea     rcx, aOBagBadA0x7PsA; "O:BAG:BAD:(A;;0x7;;;PS)(A;;0x3;;;SY)(A;"...
0x180088559  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180088560  nop     dword ptr [rax+rax+00h]
0x180088565  test    eax, eax
0x180088567  jnz     short loc_1800885A8
0x180088569  call    cs:__imp_GetLastError
0x180088570  nop     dword ptr [rax+rax+00h]
0x180088575  mov     esi, eax
0x180088577  mov     eax, cs:dword_1801574B8
0x18008857d  test    eax, eax
0x18008857f  jnz     short loc_18008859D
0x180088581  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180088588  jz      loc_18008875F
0x18008858e  xor     ecx, ecx
0x180088590  call    IsWppLevelEnabled
0x180088595  test    al, al
0x180088597  jz      loc_18008875F
0x18008859d  mov     r8d, 13Eh
0x1800885a3  jmp     loc_18008822E
0x1800885a8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800885af  xor     edx, edx; dwFlags
0x1800885b1  lea     r8d, [rdx+10h]; dwBytes
0x1800885b5  call    cs:__imp_HeapAlloc
0x1800885bc  nop     dword ptr [rax+rax+00h]
0x1800885c1  mov     r15, rax
0x1800885c4  test    rax, rax
0x1800885c7  jz      loc_18008874F
0x1800885cd  mov     rbx, [rbp+70h+SecurityDescriptor]
0x1800885d1  mov     rcx, rbx; pSecurityDescriptor
0x1800885d4  mov     [rax+0Ch], r12d
0x1800885d8  call    cs:__imp_GetSecurityDescriptorLength
0x1800885df  nop     dword ptr [rax+rax+00h]
0x1800885e4  lea     r9, [rbp+70h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800885e8  mov     [r15], rbx
0x1800885eb  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x1800885ef  mov     [r15+8], eax
0x1800885f3  mov     edx, r12d; StringSDRevision
0x1800885f6  mov     cs:?gpNoRegAccessPermissionsSD@@3PEAVCSecDescriptor@@EA, r15; CSecDescriptor * gpNoRegAccessPermissionsSD
0x1800885fd  mov     rcx, rdi; StringSecurityDescriptor
0x180088600  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180088607  nop     dword ptr [rax+rax+00h]
0x18008860c  test    eax, eax
0x18008860e  jnz     short loc_18008864F
0x180088610  call    cs:__imp_GetLastError
0x180088617  nop     dword ptr [rax+rax+00h]
0x18008861c  mov     esi, eax
0x18008861e  mov     eax, cs:dword_1801574B8
0x180088624  test    eax, eax
0x180088626  jnz     short loc_180088644
0x180088628  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18008862f  jz      loc_18008875F
0x180088635  xor     ecx, ecx
0x180088637  call    IsWppLevelEnabled
0x18008863c  test    al, al
0x18008863e  jz      loc_18008875F
0x180088644  mov     r8d, 149h
0x18008864a  jmp     loc_18008822E
0x18008864f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180088656  xor     edx, edx; dwFlags
0x180088658  lea     r8d, [rdx+10h]; dwBytes
0x18008865c  call    cs:__imp_HeapAlloc
0x180088663  nop     dword ptr [rax+rax+00h]
0x180088668  mov     r15, rax
0x18008866b  test    rax, rax
0x18008866e  jz      loc_180088746
0x180088674  mov     rbx, [rbp+70h+SecurityDescriptor]
0x180088678  mov     rcx, rbx; pSecurityDescriptor
0x18008867b  mov     [rax+0Ch], r12d
0x18008867f  call    cs:__imp_GetSecurityDescriptorLength
  ... truncated ...
```
