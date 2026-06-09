# CSecurityAttributes::InitFromSecurityElements(SECURITY_ELEMENT const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> const *,ulong,SECURITY_ELEMENT const *)

- ea: `0x18001c9cc`
- end: `0x18001d0c0`
- name: `?InitFromSecurityElements@CSecurityAttributes@@QEAAJPEBUSECURITY_ELEMENT@@KPEBV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@K0@Z`
- size: `1780`
- prototype: `__int64 __fastcall(PACL *this, __int64, unsigned int, __int64, unsigned int, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d128`
- `0x18003d990`
- `0x180044230`
- `0x180076e94`
- `0x18007b268`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c650`
- `0x18001c9cc`
- `0x18001d0c8`
- `0x18001daa8`
- `0x18001fe24`
- `0x18002cdd0`
- `0x18003bf14`
- `0x180040f38`
- `0x180050db0`
- `0x180051380`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cc87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cc87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cc58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cc58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001cf26`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001cf26`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001cf77`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001cf77`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cb6b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cdc2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cb6b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cdc2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001cb83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ce0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001cb83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ce0b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001cca4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001ce4a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001cca4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001ce4a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001cd0d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001cd0d`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x18001cea6`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x18001cea6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18001cfce`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18001cfce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d091`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d091`

## pseudocode

```c
__int64 __fastcall CSecurityAttributes::InitFromSecurityElements(
        PACL *this,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority)
{
  __int64 v7; // r12
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r14
  DWORD v16; // r15d
  __int64 v17; // rbx
  __int64 v18; // r10
  PSID *v19; // r12
  char v20; // al
  DWORD v21; // r9d
  DWORD nSubAuthority2; // r8d
  BYTE v23; // dl
  DWORD LastError; // eax
  PACL *v25; // r14
  DWORD v26; // eax
  __int64 i; // rbx
  DWORD v28; // eax
  BYTE v29; // bl
  PSID *pSid; // rax
  DWORD v31; // eax
  DWORD v32; // edi
  __int64 unique_oversize_for; // rax
  DWORD v34; // eax
  DWORD v35; // eax
  DWORD v36; // eax
  DWORD v37; // eax
  struct _ACL *v38; // r8
  DWORD v39; // eax
  __int64 j; // rdi
  PSID v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  PSID pLabelSid; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  PSID hMem[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v50; // [rsp+100h] [rbp+0h]

  v48 = a4;
  v7 = a2;
  v47 = a2;
  memset_0(hMem, 0, sizeof(hMem));
  v50 = 0;
  pLabelSid = 0;
  if ( v7 )
  {
    if ( a3 <= 0x10 )
    {
      v15 = 0;
      v16 = 0;
      LODWORD(lpMem) = 0;
      CSecurityAttributes::ReleaseResources((CSecurityAttributes *)this);
      v17 = 0;
      while ( (unsigned int)v17 < a3 )
      {
        v18 = v7 + 28LL * (unsigned int)v17;
        if ( *(_DWORD *)(v18 + 8) == -1 )
        {
          if ( !v48 )
          {
            v9 = -2147024809;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v11 = 14;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
          if ( (unsigned int)v15 >= a5 )
          {
            v9 = -2147316575;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v11 = 15;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
          v19 = &hMem[v17];
          *v19 = *(PSID *)(v48 + 8 * v15);
          if ( (unsigned int)v17 >= 0x10 )
            _report_rangecheckfailure();
          v15 = (unsigned int)(v15 + 1);
          v20 = 0;
        }
        else
        {
          v21 = *(_DWORD *)(v18 + 12);
          nSubAuthority2 = *(_DWORD *)(v18 + 16);
          v19 = &hMem[v17];
          v23 = (v21 != 0) + 2;
          if ( !nSubAuthority2 )
            v23 = (v21 != 0) + 1;
          if ( !AllocateAndInitializeSid(
                  (PSID_IDENTIFIER_AUTHORITY)v18,
                  v23,
                  *(_DWORD *)(v18 + 8),
                  v21,
                  nSubAuthority2,
                  0,
                  0,
                  0,
                  0,
                  0,
                  &hMem[v17]) )
          {
            LastError = GetLastError();
            v9 = ERROR_HR_FROM_WIN32(LastError);
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v13 = 16;
LABEL_32:
              v14 = (unsigned int)v9;
              goto LABEL_9;
            }
            goto LABEL_84;
          }
          v20 = 1;
        }
        *((_BYTE *)&v50 + v17) = v20;
        v16 = GetLengthSid(*v19) + (_DWORD)lpMem;
        LODWORD(lpMem) = v16;
        v17 = (unsigned int)(v17 + 1);
        v7 = v47;
      }
      lpMem = HeapAlloc(g_hWerheap, 0, v16 + 8 * (a3 + 1));
      v25 = this + 8;
      utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
        this + 8,
        &lpMem);
      if ( lpMem )
        HeapFree(g_hWerheap, 0, lpMem);
      if ( *v25 )
      {
        if ( InitializeAcl(*v25, v16 + 8 * (a3 + 1), 2u) )
        {
          for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
          {
            if ( !AddAccessAllowedAceEx(
                    *v25,
                    2u,
                    *(_DWORD *)(28LL * (unsigned int)i + v7 + 24),
                    *(_DWORD *)(28LL * (unsigned int)i + v7 + 20),
                    hMem[i]) )
            {
              v28 = GetLastError();
              v9 = ERROR_HR_FROM_WIN32(v28);
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 19;
                goto LABEL_32;
              }
              goto LABEL_84;
            }
          }
          if ( pIdentifierAuthority )
          {
            v29 = (*(_DWORD *)pIdentifierAuthority[2].Value != 0) + 2;
            if ( !*(_DWORD *)&pIdentifierAuthority[2].Value[4] )
              v29 = (*(_DWORD *)pIdentifierAuthority[2].Value != 0) + 1;
            pSid = (PSID *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&pLabelSid);
            if ( !AllocateAndInitializeSid(
                    pIdentifierAuthority,
                    v29,
                    *(_DWORD *)&pIdentifierAuthority[1].Value[2],
                    *(_DWORD *)pIdentifierAuthority[2].Value,
                    *(_DWORD *)&pIdentifierAuthority[2].Value[4],
                    0,
                    0,
                    0,
                    0,
                    0,
                    pSid) )
            {
              v31 = GetLastError();
              v9 = ERROR_HR_FROM_WIN32(v31);
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 20;
                goto LABEL_32;
              }
              goto LABEL_84;
            }
            v32 = GetLengthSid(pLabelSid) + 16;
            unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v47, v32);
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              this + 9,
              unique_oversize_for);
            utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v47);
            if ( !this[9] )
            {
              v9 = -2147024882;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v11 = 21;
                goto LABEL_83;
              }
              goto LABEL_84;
            }
            if ( !InitializeAcl(this[9], v32, 2u) )
            {
              v34 = GetLastError();
              v9 = ERROR_HR_FROM_WIN32(v34);
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 22;
                goto LABEL_32;
              }
              goto LABEL_84;
            }
            if ( !AddMandatoryAce(
                    this[9],
                    2u,
                    *(_DWORD *)pIdentifierAuthority[4].Value,
                    *(_DWORD *)&pIdentifierAuthority[3].Value[2],
                    pLabelSid) )
            {
              v35 = GetLastError();
              v9 = ERROR_HR_FROM_WIN32(v35);
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 23;
                goto LABEL_32;
              }
              goto LABEL_84;
            }
          }
          if ( InitializeSecurityDescriptor(this + 3, 1u) )
          {
            if ( SetSecurityDescriptorDacl(this + 3, 1, *v25, 0) )
            {
              v38 = this[9];
              if ( !v38 || SetSecurityDescriptorSacl(this + 3, 1, v38, 0) )
              {
                this[1] = (PACL)(this + 3);
                v9 = 0;
              }
              else
              {
                v39 = GetLastError();
                v9 = ERROR_HR_FROM_WIN32(v39);
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v13 = 26;
                  goto LABEL_32;
                }
              }
            }
            else
            {
              v37 = GetLastError();
              v9 = ERROR_HR_FROM_WIN32(v37);
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 25;
                goto LABEL_32;
              }
            }
          }
          else
          {
            v36 = GetLastError();
            v9 = ERROR_HR_FROM_WIN32(v36);
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v13 = 24;
              goto LABEL_32;
            }
          }
        }
        else
        {
          v26 = GetLastError();
          v9 = ERROR_HR_FROM_WIN32(v26);
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v13 = 18;
            goto LABEL_32;
          }
        }
      }
      else
      {
        v9 = -2147024882;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 17;
          goto LABEL_83;
        }
      }
    }
    else
    {
      v9 = -2147023507;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 13;
        v14 = a3;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_206b68d1819537d575b2f07e92cd871a_Traceguids, v14);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 12;
LABEL_83:
      WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_206b68d1819537d575b2f07e92cd871a_Traceguids);
    }
  }
LABEL_84:
  for ( j = 0; j != 16; ++j )
  {
    v41 = hMem[j];
    if ( v41 && *((_BYTE *)&v50 + j) )
    {
      if ( LocalFree(v41) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v43, v42);
      hMem[j] = 0;
    }
  }
  if ( v9 < 0 )
    CSecurityAttributes::ReleaseResources((CSecurityAttributes *)this);
  if ( pLabelSid )
    LocalFree(pLabelSid);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c9cc  mov     [rsp-8+arg_18], rbx
0x18001c9d1  push    rbp
0x18001c9d2  push    rsi
0x18001c9d3  push    rdi
0x18001c9d4  push    r12
0x18001c9d6  push    r13
0x18001c9d8  push    r14
0x18001c9da  push    r15
0x18001c9dc  lea     rbp, [rsp-20h]
0x18001c9e1  sub     rsp, 120h
0x18001c9e8  mov     rax, cs:__security_cookie
0x18001c9ef  xor     rax, rsp
0x18001c9f2  mov     [rbp+50h+var_40], rax
0x18001c9f6  mov     [rsp+150h+var_D8], r9
0x18001c9fb  mov     edi, r8d
0x18001c9fe  mov     r12, rdx
0x18001ca01  mov     [rsp+150h+var_E0], rdx
0x18001ca06  mov     r13, rcx
0x18001ca09  mov     rsi, [rbp+50h+pIdentifierAuthority]
0x18001ca10  xor     edx, edx; Val
0x18001ca12  mov     r8d, 80h; Size
0x18001ca18  lea     rcx, [rbp+50h+hMem]; void *
0x18001ca1c  call    memset_0
0x18001ca21  xorps   xmm0, xmm0
0x18001ca24  movups  [rbp+50h+var_50], xmm0
0x18001ca28  mov     [rsp+150h+pLabelSid], 0
0x18001ca31  test    r12, r12
0x18001ca34  jnz     short loc_18001CA66
0x18001ca36  mov     ebx, 80070057h
0x18001ca3b  lea     rax, WPP_GLOBAL_Control
0x18001ca42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca49  cmp     rcx, rax
0x18001ca4c  jz      loc_18001D045
0x18001ca52  test    byte ptr [rcx+1Ch], 1
0x18001ca56  jz      loc_18001D045
0x18001ca5c  lea     edx, [r12+0Ch]
0x18001ca61  jmp     loc_18001D035
0x18001ca66  cmp     edi, 10h
0x18001ca69  jbe     short loc_18001CAAE
0x18001ca6b  mov     ebx, 8007056Dh
0x18001ca70  lea     rax, WPP_GLOBAL_Control
0x18001ca77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca7e  cmp     rcx, rax
0x18001ca81  jz      loc_18001D045
0x18001ca87  test    byte ptr [rcx+1Ch], 1
0x18001ca8b  jz      loc_18001D045
0x18001ca91  mov     edx, 0Dh
0x18001ca96  mov     r9d, edi
0x18001ca99  lea     r8, WPP_206b68d1819537d575b2f07e92cd871a_Traceguids
0x18001caa0  mov     rcx, [rcx+10h]
0x18001caa4  call    WPP_SF_d
0x18001caa9  jmp     loc_18001D045
0x18001caae  xor     r14d, r14d
0x18001cab1  xor     r15d, r15d
0x18001cab4  mov     dword ptr [rsp+150h+lpMem], r15d
0x18001cab9  mov     rcx, r13; this
0x18001cabc  call    ?ReleaseResources@CSecurityAttributes@@IEAAXXZ; CSecurityAttributes::ReleaseResources(void)
0x18001cac1  xor     ebx, ebx
0x18001cac3  cmp     ebx, edi
0x18001cac5  jnb     loc_18001CC45
0x18001cacb  mov     r15d, ebx
0x18001cace  imul    r10, r15, 1Ch
0x18001cad2  add     r10, r12
0x18001cad5  cmp     dword ptr [r10+8], 0FFFFFFFFh
0x18001cada  jnz     short loc_18001CB17
0x18001cadc  mov     rcx, [rsp+150h+var_D8]
0x18001cae1  test    rcx, rcx
0x18001cae4  jz      loc_18001CBD8
0x18001caea  cmp     r14d, [rbp+50h+arg_20]
0x18001caf1  jnb     loc_18001CBA8
0x18001caf7  lea     r12, [rbp+50h+hMem]
0x18001cafb  lea     r12, [r12+rbx*8]
0x18001caff  mov     rcx, [rcx+r14*8]
0x18001cb03  mov     [r12], rcx
0x18001cb07  cmp     ebx, 10h
0x18001cb0a  jnb     loc_18001CBA2
0x18001cb10  inc     r14d
0x18001cb13  xor     al, al
0x18001cb15  jmp     short loc_18001CB7B
0x18001cb17  mov     r9d, [r10+0Ch]; nSubAuthority1
0x18001cb1b  xor     r11d, r11d
0x18001cb1e  test    r9d, r9d
0x18001cb21  setnz   al
0x18001cb24  inc     al
0x18001cb26  movzx   ecx, al
0x18001cb29  mov     r8d, [r10+10h]
0x18001cb2d  lea     r12, [rbp+50h+hMem]
0x18001cb31  lea     r12, [r12+rbx*8]
0x18001cb35  lea     eax, [rcx+1]
0x18001cb38  movzx   edx, al
0x18001cb3b  test    r8d, r8d
0x18001cb3e  cmovz   edx, ecx; nSubAuthorityCount
0x18001cb41  mov     [rsp+150h+pSid], r12; pSid
0x18001cb46  mov     [rsp+150h+nSubAuthority7], r11d; nSubAuthority7
0x18001cb4b  mov     [rsp+150h+nSubAuthority6], r11d; nSubAuthority6
0x18001cb50  mov     [rsp+150h+nSubAuthority5], r11d; nSubAuthority5
0x18001cb55  mov     [rsp+150h+nSubAuthority4], r11d; nSubAuthority4
0x18001cb5a  mov     [rsp+150h+nSubAuthority3], r11d; nSubAuthority3
0x18001cb5f  mov     [rsp+150h+nSubAuthority2], r8d; nSubAuthority2
0x18001cb64  mov     r8d, [r10+8]; nSubAuthority0
0x18001cb68  mov     rcx, r10; pIdentifierAuthority
0x18001cb6b  call    cs:__imp_AllocateAndInitializeSid
0x18001cb71  test    eax, eax
0x18001cb73  jz      loc_18001CC08
0x18001cb79  mov     al, 1
0x18001cb7b  mov     byte ptr [rbp+rbx+50h+var_50], al
0x18001cb7f  mov     rcx, [r12]; pSid
0x18001cb83  call    cs:__imp_GetLengthSid
0x18001cb89  mov     r15d, dword ptr [rsp+150h+lpMem]
0x18001cb8e  add     r15d, eax
0x18001cb91  mov     dword ptr [rsp+150h+lpMem], r15d
0x18001cb96  inc     ebx
0x18001cb98  mov     r12, [rsp+150h+var_E0]
0x18001cb9d  jmp     loc_18001CAC3
0x18001cba2  call    __report_rangecheckfailure
0x18001cba8  mov     ebx, 80028CA1h
0x18001cbad  lea     rax, WPP_GLOBAL_Control
0x18001cbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbbb  cmp     rcx, rax
0x18001cbbe  jz      loc_18001D045
0x18001cbc4  test    byte ptr [rcx+1Ch], 1
0x18001cbc8  jz      loc_18001D045
0x18001cbce  mov     edx, 0Fh
0x18001cbd3  jmp     loc_18001D035
0x18001cbd8  mov     ebx, 80070057h
0x18001cbdd  lea     rax, WPP_GLOBAL_Control
0x18001cbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbeb  cmp     rcx, rax
0x18001cbee  jz      loc_18001D045
0x18001cbf4  test    byte ptr [rcx+1Ch], 1
0x18001cbf8  jz      loc_18001D045
0x18001cbfe  mov     edx, 0Eh
0x18001cc03  jmp     loc_18001D035
0x18001cc08  call    cs:__imp_GetLastError
0x18001cc0e  mov     ecx, eax; unsigned int
0x18001cc10  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001cc15  mov     ebx, eax
0x18001cc17  lea     rax, WPP_GLOBAL_Control
0x18001cc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc25  cmp     rcx, rax
0x18001cc28  jz      loc_18001D045
0x18001cc2e  test    byte ptr [rcx+1Ch], 1
0x18001cc32  jz      loc_18001D045
0x18001cc38  mov     edx, 10h
0x18001cc3d  mov     r9d, ebx
0x18001cc40  jmp     loc_18001CA99
0x18001cc45  lea     ebx, [rdi+1]
0x18001cc48  lea     ebx, [r15+rbx*8]
0x18001cc4c  mov     r8d, ebx; dwBytes
0x18001cc4f  xor     edx, edx; dwFlags
0x18001cc51  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001cc58  call    cs:__imp_HeapAlloc
0x18001cc5e  mov     [rsp+150h+lpMem], rax
0x18001cc63  lea     r14, [r13+40h]
0x18001cc67  lea     rdx, [rsp+150h+lpMem]
0x18001cc6c  mov     rcx, r14
0x18001cc6f  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18001cc74  mov     r8, [rsp+150h+lpMem]; lpMem
0x18001cc79  test    r8, r8
0x18001cc7c  jz      short loc_18001CC8D
0x18001cc7e  xor     edx, edx; dwFlags
0x18001cc80  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001cc87  call    cs:__imp_HeapFree
0x18001cc8d  mov     rcx, [r14]; pAcl
0x18001cc90  test    rcx, rcx
0x18001cc93  jz      loc_18001D012
0x18001cc99  mov     r15d, 2
0x18001cc9f  mov     r8d, r15d; dwAclRevision
0x18001cca2  mov     edx, ebx; nAclLength
0x18001cca4  call    cs:__imp_InitializeAcl
0x18001ccaa  test    eax, eax
0x18001ccac  jnz     short loc_18001CCE7
0x18001ccae  call    cs:__imp_GetLastError
0x18001ccb4  mov     ecx, eax; unsigned int
0x18001ccb6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001ccbb  mov     ebx, eax
0x18001ccbd  lea     rax, WPP_GLOBAL_Control
0x18001ccc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cccb  cmp     rcx, rax
0x18001ccce  jz      loc_18001D045
0x18001ccd4  test    byte ptr [rcx+1Ch], 1
0x18001ccd8  jz      loc_18001D045
0x18001ccde  lea     edx, [r15+10h]
0x18001cce2  jmp     loc_18001CC3D
0x18001cce7  xor     ebx, ebx
0x18001cce9  cmp     ebx, edi
0x18001cceb  jnb     short loc_18001CD55
0x18001cced  mov     eax, ebx
0x18001ccef  imul    r8, rax, 1Ch
0x18001ccf3  mov     rax, [rbp+rbx*8+50h+hMem]
0x18001ccf8  mov     qword ptr [rsp+150h+nSubAuthority2], rax; pSid
0x18001ccfd  mov     r9d, [r8+r12+14h]; AccessMask
0x18001cd02  mov     r8d, [r8+r12+18h]; AceFlags
0x18001cd07  mov     edx, r15d; dwAceRevision
0x18001cd0a  mov     rcx, [r14]; pAcl
0x18001cd0d  call    cs:__imp_AddAccessAllowedAceEx
0x18001cd13  test    eax, eax
0x18001cd15  jz      short loc_18001CD1B
0x18001cd17  inc     ebx
0x18001cd19  jmp     short loc_18001CCE9
0x18001cd1b  call    cs:__imp_GetLastError
0x18001cd21  mov     ecx, eax; unsigned int
0x18001cd23  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001cd28  mov     ebx, eax
0x18001cd2a  lea     rax, WPP_GLOBAL_Control
0x18001cd31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd38  cmp     rcx, rax
0x18001cd3b  jz      loc_18001D045
0x18001cd41  test    byte ptr [rcx+1Ch], 1
0x18001cd45  jz      loc_18001D045
0x18001cd4b  mov     edx, 13h
0x18001cd50  jmp     loc_18001CC3D
0x18001cd55  test    rsi, rsi
0x18001cd58  jz      loc_18001CF1A
0x18001cd5e  cmp     dword ptr [rsi+0Ch], 0
0x18001cd62  setnz   al
0x18001cd65  inc     al
0x18001cd67  movzx   ecx, al
0x18001cd6a  lea     eax, [rcx+1]
0x18001cd6d  movzx   ebx, al
0x18001cd70  cmp     dword ptr [rsi+10h], 0
0x18001cd74  cmovz   ebx, ecx
0x18001cd77  lea     rcx, [rsp+150h+pLabelSid]
0x18001cd7c  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001cd81  mov     [rsp+150h+pSid], rax; pSid
0x18001cd86  mov     [rsp+150h+nSubAuthority7], 0; nSubAuthority7
0x18001cd8e  mov     [rsp+150h+nSubAuthority6], 0; nSubAuthority6
0x18001cd96  mov     [rsp+150h+nSubAuthority5], 0; nSubAuthority5
0x18001cd9e  mov     [rsp+150h+nSubAuthority4], 0; nSubAuthority4
0x18001cda6  mov     [rsp+150h+nSubAuthority3], 0; nSubAuthority3
0x18001cdae  mov     eax, [rsi+10h]
0x18001cdb1  mov     [rsp+150h+nSubAuthority2], eax; nSubAuthority2
0x18001cdb5  mov     r9d, [rsi+0Ch]; nSubAuthority1
0x18001cdb9  mov     r8d, [rsi+8]; nSubAuthority0
0x18001cdbd  mov     dl, bl; nSubAuthorityCount
0x18001cdbf  mov     rcx, rsi; pIdentifierAuthority
0x18001cdc2  call    cs:__imp_AllocateAndInitializeSid
0x18001cdc8  test    eax, eax
0x18001cdca  jnz     short loc_18001CE06
0x18001cdcc  call    cs:__imp_GetLastError
0x18001cdd2  mov     ecx, eax; unsigned int
0x18001cdd4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001cdd9  mov     ebx, eax
0x18001cddb  lea     rax, WPP_GLOBAL_Control
0x18001cde2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cde9  cmp     rcx, rax
0x18001cdec  jz      loc_18001D045
0x18001cdf2  test    byte ptr [rcx+1Ch], 1
0x18001cdf6  jz      loc_18001D045
0x18001cdfc  mov     edx, 14h
0x18001ce01  jmp     loc_18001CC3D
0x18001ce06  mov     rcx, [rsp+150h+pLabelSid]; pSid
0x18001ce0b  call    cs:__imp_GetLengthSid
0x18001ce11  lea     edi, [rax+10h]
0x18001ce14  mov     edx, edi
0x18001ce16  lea     rcx, [rsp+150h+var_E0]
0x18001ce1b  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x18001ce20  lea     rbx, [r13+48h]
0x18001ce24  mov     rdx, rax
0x18001ce27  mov     rcx, rbx
0x18001ce2a  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18001ce2f  lea     rcx, [rsp+150h+var_E0]; void *
0x18001ce34  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18001ce39  mov     rcx, [rbx]; pAcl
0x18001ce3c  test    rcx, rcx
0x18001ce3f  jz      loc_18001CEEA
0x18001ce45  mov     r8d, r15d; dwAclRevision
0x18001ce48  mov     edx, edi; nAclLength
0x18001ce4a  call    cs:__imp_InitializeAcl
0x18001ce50  test    eax, eax
0x18001ce52  jnz     short loc_18001CE8E
0x18001ce54  call    cs:__imp_GetLastError
0x18001ce5a  mov     ecx, eax; unsigned int
0x18001ce5c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001ce61  mov     ebx, eax
0x18001ce63  lea     rax, WPP_GLOBAL_Control
0x18001ce6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce71  cmp     rcx, rax
0x18001ce74  jz      loc_18001D045
0x18001ce7a  test    byte ptr [rcx+1Ch], 1
0x18001ce7e  jz      loc_18001D045
0x18001ce84  mov     edx, 16h
0x18001ce89  jmp     loc_18001CC3D
0x18001ce8e  mov     rax, [rsp+150h+pLabelSid]
0x18001ce93  mov     qword ptr [rsp+150h+nSubAuthority2], rax; pLabelSid
0x18001ce98  mov     r9d, [rsi+14h]; MandatoryPolicy
0x18001ce9c  mov     r8d, [rsi+18h]; AceFlags
0x18001cea0  mov     edx, r15d; dwAceRevision
0x18001cea3  mov     rcx, [rbx]; pAcl
0x18001cea6  call    cs:__imp_AddMandatoryAce
0x18001ceac  test    eax, eax
0x18001ceae  jnz     short loc_18001CF1A
0x18001ceb0  call    cs:__imp_GetLastError
0x18001ceb6  mov     ecx, eax; unsigned int
0x18001ceb8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001cebd  mov     ebx, eax
0x18001cebf  lea     rax, WPP_GLOBAL_Control
0x18001cec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cecd  cmp     rcx, rax
0x18001ced0  jz      loc_18001D045
  ... truncated ...
```
