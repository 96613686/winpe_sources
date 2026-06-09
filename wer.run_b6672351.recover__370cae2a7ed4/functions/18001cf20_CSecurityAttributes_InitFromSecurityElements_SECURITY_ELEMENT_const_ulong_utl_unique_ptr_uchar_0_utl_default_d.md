# CSecurityAttributes::InitFromSecurityElements(SECURITY_ELEMENT const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> const *,ulong,SECURITY_ELEMENT const *)

- ea: `0x18001cf20`
- end: `0x18001d6a5`
- name: `?InitFromSecurityElements@CSecurityAttributes@@QEAAJPEBUSECURITY_ELEMENT@@KPEBV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@K0@Z`
- size: `1925`
- prototype: `__int64 __usercall@<rax>(CSecurityAttributes *this@<rcx>, int, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d718`
- `0x18003f9a0`
- `0x180046150`
- `0x18007a3b4`
- `0x18007e9ac`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x18001cf20`
- `0x18001d6ac`
- `0x18001e0d0`
- `0x18001e100`
- `0x180020680`
- `0x18002e94c`
- `0x18003de9c`
- `0x180042ecc`
- `0x180053300`
- `0x1800538d0`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d1f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d1f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d1be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5aa`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d4da`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d4da`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d537`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d537`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d0bf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d34c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d0bf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d34c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d0dd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3a1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d0dd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d3a1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d216`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d3e6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d216`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d3e6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d28b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d28b`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x18001d44e`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x18001d44e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18001d59a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18001d59a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d630`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d66f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d630`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d66f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v44; // r8
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  PSID pLabelSid; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h]
  PSID hMem[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v51; // [rsp+100h] [rbp+0h]

  v49 = a4;
  v7 = a2;
  v48 = a2;
  memset_0(hMem, 0, sizeof(hMem));
  v51 = 0;
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
          if ( !v49 )
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
          *v19 = *(PSID *)(v49 + 8 * v15);
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
        *((_BYTE *)&v51 + v17) = v20;
        v16 = GetLengthSid(*v19) + (_DWORD)lpMem;
        LODWORD(lpMem) = v16;
        v17 = (unsigned int)(v17 + 1);
        v7 = v48;
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
            unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v48, v32);
            utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
              this + 9,
              unique_oversize_for);
            utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v48);
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
    if ( v41 && *((_BYTE *)&v51 + j) )
    {
      if ( LocalFree(v41) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v43, v42, v44);
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
0x18001cf20  mov     [rsp-8+arg_18], rbx
0x18001cf25  push    rbp
0x18001cf26  push    rsi
0x18001cf27  push    rdi
0x18001cf28  push    r12
0x18001cf2a  push    r13
0x18001cf2c  push    r14
0x18001cf2e  push    r15
0x18001cf30  lea     rbp, [rsp-20h]
0x18001cf35  sub     rsp, 120h
0x18001cf3c  mov     rax, cs:__security_cookie
0x18001cf43  xor     rax, rsp
0x18001cf46  mov     [rbp+50h+var_40], rax
0x18001cf4a  mov     [rsp+150h+var_D8], r9
0x18001cf4f  mov     edi, r8d
0x18001cf52  mov     r12, rdx
0x18001cf55  mov     [rsp+150h+var_E0], rdx
0x18001cf5a  mov     r13, rcx
0x18001cf5d  mov     rsi, [rbp+50h+pIdentifierAuthority]
0x18001cf64  xor     edx, edx; Val
0x18001cf66  mov     r8d, 80h; Size
0x18001cf6c  lea     rcx, [rbp+50h+hMem]; void *
0x18001cf70  call    memset_0
0x18001cf75  xorps   xmm0, xmm0
0x18001cf78  movups  [rbp+50h+var_50], xmm0
0x18001cf7c  mov     [rsp+150h+pLabelSid], 0
0x18001cf85  test    r12, r12
0x18001cf88  jnz     short loc_18001CFBA
0x18001cf8a  mov     ebx, 80070057h
0x18001cf8f  lea     rax, WPP_GLOBAL_Control
0x18001cf96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf9d  cmp     rcx, rax
0x18001cfa0  jz      loc_18001D61D
0x18001cfa6  test    byte ptr [rcx+1Ch], 1
0x18001cfaa  jz      loc_18001D61D
0x18001cfb0  lea     edx, [r12+0Ch]
0x18001cfb5  jmp     loc_18001D60D
0x18001cfba  cmp     edi, 10h
0x18001cfbd  jbe     short loc_18001D002
0x18001cfbf  mov     ebx, 8007056Dh
0x18001cfc4  lea     rax, WPP_GLOBAL_Control
0x18001cfcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfd2  cmp     rcx, rax
0x18001cfd5  jz      loc_18001D61D
0x18001cfdb  test    byte ptr [rcx+1Ch], 1
0x18001cfdf  jz      loc_18001D61D
0x18001cfe5  mov     edx, 0Dh
0x18001cfea  mov     r9d, edi
0x18001cfed  lea     r8, WPP_206b68d1819537d575b2f07e92cd871a_Traceguids
0x18001cff4  mov     rcx, [rcx+10h]
0x18001cff8  call    WPP_SF_d
0x18001cffd  jmp     loc_18001D61D
0x18001d002  xor     r14d, r14d
0x18001d005  xor     r15d, r15d
0x18001d008  mov     dword ptr [rsp+150h+lpMem], r15d
0x18001d00d  mov     rcx, r13; this
0x18001d010  call    ?ReleaseResources@CSecurityAttributes@@IEAAXXZ; CSecurityAttributes::ReleaseResources(void)
0x18001d015  xor     ebx, ebx
0x18001d017  cmp     ebx, edi
0x18001d019  jnb     loc_18001D1AB
0x18001d01f  mov     r15d, ebx
0x18001d022  imul    r10, r15, 1Ch
0x18001d026  add     r10, r12
0x18001d029  cmp     dword ptr [r10+8], 0FFFFFFFFh
0x18001d02e  jnz     short loc_18001D06B
0x18001d030  mov     rcx, [rsp+150h+var_D8]
0x18001d035  test    rcx, rcx
0x18001d038  jz      loc_18001D138
0x18001d03e  cmp     r14d, [rbp+50h+arg_20]
0x18001d045  jnb     loc_18001D108
0x18001d04b  lea     r12, [rbp+50h+hMem]
0x18001d04f  lea     r12, [r12+rbx*8]
0x18001d053  mov     rcx, [rcx+r14*8]
0x18001d057  mov     [r12], rcx
0x18001d05b  cmp     ebx, 10h
0x18001d05e  jnb     loc_18001D102
0x18001d064  inc     r14d
0x18001d067  xor     al, al
0x18001d069  jmp     short loc_18001D0D5
0x18001d06b  mov     r9d, [r10+0Ch]; nSubAuthority1
0x18001d06f  xor     r11d, r11d
0x18001d072  test    r9d, r9d
0x18001d075  setnz   al
0x18001d078  inc     al
0x18001d07a  movzx   ecx, al
0x18001d07d  mov     r8d, [r10+10h]
0x18001d081  lea     r12, [rbp+50h+hMem]
0x18001d085  lea     r12, [r12+rbx*8]
0x18001d089  lea     eax, [rcx+1]
0x18001d08c  movzx   edx, al
0x18001d08f  test    r8d, r8d
0x18001d092  cmovz   edx, ecx; nSubAuthorityCount
0x18001d095  mov     [rsp+150h+pSid], r12; pSid
0x18001d09a  mov     [rsp+150h+nSubAuthority7], r11d; nSubAuthority7
0x18001d09f  mov     [rsp+150h+nSubAuthority6], r11d; nSubAuthority6
0x18001d0a4  mov     [rsp+150h+nSubAuthority5], r11d; nSubAuthority5
0x18001d0a9  mov     [rsp+150h+nSubAuthority4], r11d; nSubAuthority4
0x18001d0ae  mov     [rsp+150h+nSubAuthority3], r11d; nSubAuthority3
0x18001d0b3  mov     [rsp+150h+nSubAuthority2], r8d; nSubAuthority2
0x18001d0b8  mov     r8d, [r10+8]; nSubAuthority0
0x18001d0bc  mov     rcx, r10; pIdentifierAuthority
0x18001d0bf  call    cs:__imp_AllocateAndInitializeSid
0x18001d0c6  nop     dword ptr [rax+rax+00h]
0x18001d0cb  test    eax, eax
0x18001d0cd  jz      loc_18001D168
0x18001d0d3  mov     al, 1
0x18001d0d5  mov     byte ptr [rbp+rbx+50h+var_50], al
0x18001d0d9  mov     rcx, [r12]; pSid
0x18001d0dd  call    cs:__imp_GetLengthSid
0x18001d0e4  nop     dword ptr [rax+rax+00h]
0x18001d0e9  mov     r15d, dword ptr [rsp+150h+lpMem]
0x18001d0ee  add     r15d, eax
0x18001d0f1  mov     dword ptr [rsp+150h+lpMem], r15d
0x18001d0f6  inc     ebx
0x18001d0f8  mov     r12, [rsp+150h+var_E0]
0x18001d0fd  jmp     loc_18001D017
0x18001d102  call    __report_rangecheckfailure
0x18001d108  mov     ebx, 80028CA1h
0x18001d10d  lea     rax, WPP_GLOBAL_Control
0x18001d114  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d11b  cmp     rcx, rax
0x18001d11e  jz      loc_18001D61D
0x18001d124  test    byte ptr [rcx+1Ch], 1
0x18001d128  jz      loc_18001D61D
0x18001d12e  mov     edx, 0Fh
0x18001d133  jmp     loc_18001D60D
0x18001d138  mov     ebx, 80070057h
0x18001d13d  lea     rax, WPP_GLOBAL_Control
0x18001d144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d14b  cmp     rcx, rax
0x18001d14e  jz      loc_18001D61D
0x18001d154  test    byte ptr [rcx+1Ch], 1
0x18001d158  jz      loc_18001D61D
0x18001d15e  mov     edx, 0Eh
0x18001d163  jmp     loc_18001D60D
0x18001d168  call    cs:__imp_GetLastError
0x18001d16f  nop     dword ptr [rax+rax+00h]
0x18001d174  mov     ecx, eax; unsigned int
0x18001d176  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d17b  mov     ebx, eax
0x18001d17d  lea     rax, WPP_GLOBAL_Control
0x18001d184  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d18b  cmp     rcx, rax
0x18001d18e  jz      loc_18001D61D
0x18001d194  test    byte ptr [rcx+1Ch], 1
0x18001d198  jz      loc_18001D61D
0x18001d19e  mov     edx, 10h
0x18001d1a3  mov     r9d, ebx
0x18001d1a6  jmp     loc_18001CFED
0x18001d1ab  lea     ebx, [rdi+1]
0x18001d1ae  lea     ebx, [r15+rbx*8]
0x18001d1b2  mov     r8d, ebx; dwBytes
0x18001d1b5  xor     edx, edx; dwFlags
0x18001d1b7  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001d1be  call    cs:__imp_HeapAlloc
0x18001d1c5  nop     dword ptr [rax+rax+00h]
0x18001d1ca  mov     [rsp+150h+lpMem], rax
0x18001d1cf  lea     r14, [r13+40h]
0x18001d1d3  lea     rdx, [rsp+150h+lpMem]
0x18001d1d8  mov     rcx, r14
0x18001d1db  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18001d1e0  mov     r8, [rsp+150h+lpMem]; lpMem
0x18001d1e5  test    r8, r8
0x18001d1e8  jz      short loc_18001D1FF
0x18001d1ea  xor     edx, edx; dwFlags
0x18001d1ec  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001d1f3  call    cs:__imp_HeapFree
0x18001d1fa  nop     dword ptr [rax+rax+00h]
0x18001d1ff  mov     rcx, [r14]; pAcl
0x18001d202  test    rcx, rcx
0x18001d205  jz      loc_18001D5EA
0x18001d20b  mov     r15d, 2
0x18001d211  mov     r8d, r15d; dwAclRevision
0x18001d214  mov     edx, ebx; nAclLength
0x18001d216  call    cs:__imp_InitializeAcl
0x18001d21d  nop     dword ptr [rax+rax+00h]
0x18001d222  test    eax, eax
0x18001d224  jnz     short loc_18001D265
0x18001d226  call    cs:__imp_GetLastError
0x18001d22d  nop     dword ptr [rax+rax+00h]
0x18001d232  mov     ecx, eax; unsigned int
0x18001d234  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d239  mov     ebx, eax
0x18001d23b  lea     rax, WPP_GLOBAL_Control
0x18001d242  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d249  cmp     rcx, rax
0x18001d24c  jz      loc_18001D61D
0x18001d252  test    byte ptr [rcx+1Ch], 1
0x18001d256  jz      loc_18001D61D
0x18001d25c  lea     edx, [r15+10h]
0x18001d260  jmp     loc_18001D1A3
0x18001d265  xor     ebx, ebx
0x18001d267  cmp     ebx, edi
0x18001d269  jnb     short loc_18001D2DF
0x18001d26b  mov     eax, ebx
0x18001d26d  imul    r8, rax, 1Ch
0x18001d271  mov     rax, [rbp+rbx*8+50h+hMem]
0x18001d276  mov     qword ptr [rsp+150h+nSubAuthority2], rax; pSid
0x18001d27b  mov     r9d, [r8+r12+14h]; AccessMask
0x18001d280  mov     r8d, [r8+r12+18h]; AceFlags
0x18001d285  mov     edx, r15d; dwAceRevision
0x18001d288  mov     rcx, [r14]; pAcl
0x18001d28b  call    cs:__imp_AddAccessAllowedAceEx
0x18001d292  nop     dword ptr [rax+rax+00h]
0x18001d297  test    eax, eax
0x18001d299  jz      short loc_18001D29F
0x18001d29b  inc     ebx
0x18001d29d  jmp     short loc_18001D267
0x18001d29f  call    cs:__imp_GetLastError
0x18001d2a6  nop     dword ptr [rax+rax+00h]
0x18001d2ab  mov     ecx, eax; unsigned int
0x18001d2ad  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d2b2  mov     ebx, eax
0x18001d2b4  lea     rax, WPP_GLOBAL_Control
0x18001d2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2c2  cmp     rcx, rax
0x18001d2c5  jz      loc_18001D61D
0x18001d2cb  test    byte ptr [rcx+1Ch], 1
0x18001d2cf  jz      loc_18001D61D
0x18001d2d5  mov     edx, 13h
0x18001d2da  jmp     loc_18001D1A3
0x18001d2df  test    rsi, rsi
0x18001d2e2  jz      loc_18001D4CE
0x18001d2e8  cmp     dword ptr [rsi+0Ch], 0
0x18001d2ec  setnz   al
0x18001d2ef  inc     al
0x18001d2f1  movzx   ecx, al
0x18001d2f4  lea     eax, [rcx+1]
0x18001d2f7  movzx   ebx, al
0x18001d2fa  cmp     dword ptr [rsi+10h], 0
0x18001d2fe  cmovz   ebx, ecx
0x18001d301  lea     rcx, [rsp+150h+pLabelSid]
0x18001d306  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001d30b  mov     [rsp+150h+pSid], rax; pSid
0x18001d310  mov     [rsp+150h+nSubAuthority7], 0; nSubAuthority7
0x18001d318  mov     [rsp+150h+nSubAuthority6], 0; nSubAuthority6
0x18001d320  mov     [rsp+150h+nSubAuthority5], 0; nSubAuthority5
0x18001d328  mov     [rsp+150h+nSubAuthority4], 0; nSubAuthority4
0x18001d330  mov     [rsp+150h+nSubAuthority3], 0; nSubAuthority3
0x18001d338  mov     eax, [rsi+10h]
0x18001d33b  mov     [rsp+150h+nSubAuthority2], eax; nSubAuthority2
0x18001d33f  mov     r9d, [rsi+0Ch]; nSubAuthority1
0x18001d343  mov     r8d, [rsi+8]; nSubAuthority0
0x18001d347  mov     dl, bl; nSubAuthorityCount
0x18001d349  mov     rcx, rsi; pIdentifierAuthority
0x18001d34c  call    cs:__imp_AllocateAndInitializeSid
0x18001d353  nop     dword ptr [rax+rax+00h]
0x18001d358  test    eax, eax
0x18001d35a  jnz     short loc_18001D39C
0x18001d35c  call    cs:__imp_GetLastError
0x18001d363  nop     dword ptr [rax+rax+00h]
0x18001d368  mov     ecx, eax; unsigned int
0x18001d36a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d36f  mov     ebx, eax
0x18001d371  lea     rax, WPP_GLOBAL_Control
0x18001d378  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d37f  cmp     rcx, rax
0x18001d382  jz      loc_18001D61D
0x18001d388  test    byte ptr [rcx+1Ch], 1
0x18001d38c  jz      loc_18001D61D
0x18001d392  mov     edx, 14h
0x18001d397  jmp     loc_18001D1A3
0x18001d39c  mov     rcx, [rsp+150h+pLabelSid]; pSid
0x18001d3a1  call    cs:__imp_GetLengthSid
0x18001d3a8  nop     dword ptr [rax+rax+00h]
0x18001d3ad  lea     edi, [rax+10h]
0x18001d3b0  mov     edx, edi
0x18001d3b2  lea     rcx, [rsp+150h+var_E0]
0x18001d3b7  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x18001d3bc  lea     rbx, [r13+48h]
0x18001d3c0  mov     rdx, rax
0x18001d3c3  mov     rcx, rbx
0x18001d3c6  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18001d3cb  lea     rcx, [rsp+150h+var_E0]; void *
0x18001d3d0  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18001d3d5  mov     rcx, [rbx]; pAcl
0x18001d3d8  test    rcx, rcx
0x18001d3db  jz      loc_18001D49E
0x18001d3e1  mov     r8d, r15d; dwAclRevision
0x18001d3e4  mov     edx, edi; nAclLength
0x18001d3e6  call    cs:__imp_InitializeAcl
0x18001d3ed  nop     dword ptr [rax+rax+00h]
0x18001d3f2  test    eax, eax
0x18001d3f4  jnz     short loc_18001D436
0x18001d3f6  call    cs:__imp_GetLastError
0x18001d3fd  nop     dword ptr [rax+rax+00h]
0x18001d402  mov     ecx, eax; unsigned int
0x18001d404  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001d409  mov     ebx, eax
0x18001d40b  lea     rax, WPP_GLOBAL_Control
0x18001d412  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d419  cmp     rcx, rax
0x18001d41c  jz      loc_18001D61D
0x18001d422  test    byte ptr [rcx+1Ch], 1
0x18001d426  jz      loc_18001D61D
0x18001d42c  mov     edx, 16h
0x18001d431  jmp     loc_18001D1A3
0x18001d436  mov     rax, [rsp+150h+pLabelSid]
0x18001d43b  mov     qword ptr [rsp+150h+nSubAuthority2], rax; pLabelSid
0x18001d440  mov     r9d, [rsi+14h]; MandatoryPolicy
  ... truncated ...
```
