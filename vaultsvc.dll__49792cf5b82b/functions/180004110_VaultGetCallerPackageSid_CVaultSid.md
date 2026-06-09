# VaultGetCallerPackageSid(CVaultSid * *)

- ea: `0x180004110`
- end: `0x180004791`
- name: `?VaultGetCallerPackageSid@@YAKPEAPEAVCVaultSid@@@Z`
- size: `1665`
- prototype: `unsigned int __fastcall(struct CVaultSid **)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005690`
- `0x180006324`
- `0x1800135d0`
- `0x1800358a0`
- `0x180041524`
- `0x18004a4d8`

## callees

- `0x180003140`
- `0x180004110`
- `0x18002b6f0`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180004643`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180004657`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000466b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180004643`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180004657`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000466b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004136`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800044b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800044b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800044a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800044a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004770`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18000447c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180004585`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800045fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800046dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18000474d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18000447c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180004585`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800045fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800046dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18000474d`
- `ntdll!NtQueryInformationToken` at `0x1800041ea`
- `ntdll!NtQueryInformationToken` at `0x180004272`
- `ntdll!NtQueryInformationToken` at `0x180004360`
- `ntdll!NtQueryInformationToken` at `0x1800043cb`
- `ntdll!NtQueryInformationToken` at `0x180004537`
- `ntdll!NtQueryInformationToken` at `0x1800041ea`
- `ntdll!NtQueryInformationToken` at `0x180004272`
- `ntdll!NtQueryInformationToken` at `0x180004360`
- `ntdll!NtQueryInformationToken` at `0x1800043cb`
- `ntdll!NtQueryInformationToken` at `0x180004537`
- `ntdll!NtOpenThreadToken` at `0x180004168`
- `ntdll!NtOpenThreadToken` at `0x180004168`
- `ntdll!RtlNtStatusToDosError` at `0x1800041a4`
- `ntdll!RtlNtStatusToDosError` at `0x180004229`
- `ntdll!RtlNtStatusToDosError` at `0x1800042b4`
- `ntdll!RtlNtStatusToDosError` at `0x180004324`
- `ntdll!RtlNtStatusToDosError` at `0x1800043a3`
- `ntdll!RtlNtStatusToDosError` at `0x180004422`
- `ntdll!RtlNtStatusToDosError` at `0x1800044fb`
- `ntdll!RtlNtStatusToDosError` at `0x18000457a`
- `ntdll!RtlNtStatusToDosError` at `0x1800041a4`
- `ntdll!RtlNtStatusToDosError` at `0x180004229`
- `ntdll!RtlNtStatusToDosError` at `0x1800042b4`
- `ntdll!RtlNtStatusToDosError` at `0x180004324`
- `ntdll!RtlNtStatusToDosError` at `0x1800043a3`
- `ntdll!RtlNtStatusToDosError` at `0x180004422`
- `ntdll!RtlNtStatusToDosError` at `0x1800044fb`
- `ntdll!RtlNtStatusToDosError` at `0x18000457a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall VaultGetCallerPackageSid(struct CVaultSid **a1)
{
  int v2; // ebx
  NTSTATUS v3; // eax
  unsigned int v4; // eax
  ULONG v5; // ebx
  PSID *v7; // rbx
  ULONG v8; // ebx
  NTSTATUS v9; // eax
  NTSTATUS v10; // edi
  ULONG v11; // ebx
  unsigned int v12; // ebx
  ULONG v13; // edi
  _BYTE *v14; // rbx
  __int64 v15; // rax
  SIZE_T v16; // rax
  _BYTE *v17; // rcx
  NTSTATUS v18; // eax
  NTSTATUS v19; // edi
  ULONG v20; // edi
  SIZE_T v21; // rax
  PSID *v22; // rcx
  _BYTE *v23; // rbx
  __int64 v24; // rax
  SIZE_T v25; // rax
  _BYTE *v26; // rcx
  PSID v27; // rdi
  bool v28; // zf
  int v29; // eax
  void *v30; // rcx
  unsigned int v31; // edi
  SIZE_T v32; // rax
  PSID *v33; // rdx
  _BYTE *v34; // rbx
  __int64 v35; // rax
  SIZE_T v36; // rax
  _BYTE *v37; // rcx
  BOOL (__stdcall *v38)(HANDLE); // [rsp+30h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v40; // [rsp+40h] [rbp-40h]
  __int64 v41; // [rsp+48h] [rbp-38h] BYREF
  PSID *v42; // [rsp+50h] [rbp-30h]
  int v43; // [rsp+58h] [rbp-28h]
  __int64 (__fastcall *v44)(); // [rsp+60h] [rbp-20h] BYREF
  struct CVaultSid *v45; // [rsp+68h] [rbp-18h] BYREF
  int v46; // [rsp+70h] [rbp-10h]
  ULONG TokenInformationLength; // [rsp+A8h] [rbp+28h] BYREF
  int TokenInformation; // [rsp+B0h] [rbp+30h] BYREF

  TokenHandle = 0;
  v40 = 0;
  v38 = CloseHandle;
  v42 = 0;
  v43 = 0;
  v41 = 0;
  TokenInformationLength = 0;
  TokenInformation = 0;
  v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
LABEL_16:
    v5 = RtlNtStatusToDosError(v2);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
    return v5;
  }
  TokenInformationLength = 4;
  v3 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength);
  v2 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
        (unsigned int)v3);
    goto LABEL_16;
  }
  TokenInformationLength = 0;
  if ( TokenInformation )
  {
    v4 = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength);
    v2 = v4;
    if ( v4 != -1073741789 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, v4);
      goto LABEL_16;
    }
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    v42 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
LABEL_21:
      v8 = RtlNtStatusToDosError(-1073741670);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
      return v8;
    }
    v9 = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
          (unsigned int)v9);
      v11 = RtlNtStatusToDosError(v10);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
      return v11;
    }
    goto LABEL_69;
  }
  v12 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -1073741789 )
  {
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    v42 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
      goto LABEL_21;
    }
    v18 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength);
    v19 = v18;
    if ( v18 >= 0 )
    {
LABEL_69:
      v27 = *v7;
      if ( !*v7
        || EqualSid(*v7, pSid2)
        || EqualSid(v27, qword_18005F730)
        || (v28 = !EqualSid(v27, qword_18005F728), v29 = 0, !v28) )
      {
        v29 = 1;
      }
      v30 = 0;
      if ( !v29 )
        v30 = v27;
      v45 = 0;
      v46 = 0;
      v44 = AutoDereference<IVaultKeyManager>;
      v31 = CVaultSid::CreateVaultSid(v30, &v45);
      if ( v31 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v44);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v41);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
        return v31;
      }
      else
      {
        *a1 = v45;
        v32 = LocalSize(v7);
        if ( v32 )
        {
          v33 = v7;
          do
          {
            *(_BYTE *)v33 = 0;
            v33 = (PSID *)((char *)v33 + 1);
            --v32;
          }
          while ( v32 );
        }
        LocalFree(v7);
        v34 = TokenHandle;
        if ( TokenHandle )
        {
          v35 = v40;
          if ( v40 )
          {
            do
            {
              *v34++ = 0;
              --v35;
            }
            while ( v35 );
            v34 = TokenHandle;
          }
          if ( v38 )
          {
            ((void (__fastcall *)(_BYTE *))v38)(v34);
          }
          else if ( v34 )
          {
            v36 = LocalSize(v34);
            if ( v36 )
            {
              v37 = v34;
              do
              {
                *v37++ = 0;
                --v36;
              }
              while ( v36 );
            }
            LocalFree(v34);
          }
        }
        return 0;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
        (unsigned int)v18);
    v20 = RtlNtStatusToDosError(v19);
    v21 = LocalSize(v7);
    if ( v21 )
    {
      v22 = v7;
      do
      {
        *(_BYTE *)v22 = 0;
        v22 = (PSID *)((char *)v22 + 1);
        --v21;
      }
      while ( v21 );
    }
    LocalFree(v7);
    v23 = TokenHandle;
    if ( TokenHandle )
    {
      v24 = v40;
      if ( v40 )
      {
        do
        {
          *v23++ = 0;
          --v24;
        }
        while ( v24 );
        v23 = TokenHandle;
      }
      if ( v38 )
      {
        ((void (__fastcall *)(_BYTE *))v38)(v23);
      }
      else if ( v23 )
      {
        v25 = LocalSize(v23);
        if ( v25 )
        {
          v26 = v23;
          do
          {
            *v26++ = 0;
            --v25;
          }
          while ( v25 );
        }
        LocalFree(v23);
      }
    }
    return v20;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, v12);
    v13 = RtlNtStatusToDosError(v12);
    v14 = TokenHandle;
    if ( TokenHandle )
    {
      if ( v40 )
      {
        v15 = v40;
        do
        {
          *v14++ = 0;
          --v15;
        }
        while ( v15 );
        v14 = TokenHandle;
      }
      if ( v38 )
      {
        ((void (__fastcall *)(_BYTE *))v38)(v14);
      }
      else if ( v14 )
      {
        v16 = LocalSize(v14);
        if ( v16 )
        {
          v17 = v14;
          do
          {
            *v17++ = 0;
            --v16;
          }
          while ( v16 );
        }
        LocalFree(v14);
      }
    }
    return v13;
  }
}

```

## disassembly

```asm
0x180004110  mov     [rsp-18h+arg_0], rbx
0x180004115  mov     [rsp-18h+arg_18], rsi
0x18000411a  push    rbp
0x18000411b  push    rdi
0x18000411c  push    r14
0x18000411e  mov     rbp, rsp
0x180004121  sub     rsp, 80h
0x180004128  mov     rsi, rcx
0x18000412b  xor     r14d, r14d
0x18000412e  mov     [rbp+TokenHandle], r14
0x180004132  mov     [rbp+var_40], r14d
0x180004136  mov     rax, cs:__imp_CloseHandle
0x18000413d  mov     [rbp+var_50], rax
0x180004141  mov     [rbp+var_30], r14
0x180004145  mov     [rbp+var_28], r14d
0x180004149  mov     [rbp+var_38], r14
0x18000414d  mov     [rbp+TokenInformationLength], r14d
0x180004151  mov     [rbp+TokenInformation], r14d
0x180004155  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180004159  mov     r8b, 1; OpenAsSelf
0x18000415c  mov     edx, 8; DesiredAccess
0x180004161  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180004168  call    cs:__imp_NtOpenThreadToken
0x18000416e  mov     ebx, eax
0x180004170  test    eax, eax
0x180004172  jns     short loc_1800041C7
0x180004174  lea     rdx, WPP_GLOBAL_Control
0x18000417b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004182  cmp     rcx, rdx
0x180004185  jz      short loc_1800041A2
0x180004187  test    byte ptr [rcx+1Ch], 2
0x18000418b  jz      short loc_1800041A2
0x18000418d  mov     edx, 1Eh
0x180004192  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180004199  mov     rcx, [rcx+10h]
0x18000419d  call    WPP_SF_
0x1800041a2  mov     ecx, ebx; Status
0x1800041a4  call    cs:__imp_RtlNtStatusToDosError
0x1800041aa  mov     ebx, eax
0x1800041ac  lea     rcx, [rbp+var_38]
0x1800041b0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800041b5  nop
0x1800041b6  lea     rcx, [rbp+var_50]
0x1800041ba  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800041bf  nop
0x1800041c0  mov     eax, ebx
0x1800041c2  jmp     loc_180004779
0x1800041c7  mov     [rbp+TokenInformationLength], 4
0x1800041ce  lea     rax, [rbp+TokenInformationLength]
0x1800041d2  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800041d7  mov     r9d, 4; TokenInformationLength
0x1800041dd  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800041e1  mov     edx, 1Dh; TokenInformationClass
0x1800041e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800041ea  call    cs:__imp_NtQueryInformationToken
0x1800041f0  mov     ebx, eax
0x1800041f2  test    eax, eax
0x1800041f4  jns     short loc_18000424C
0x1800041f6  lea     rdx, WPP_GLOBAL_Control
0x1800041fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004204  cmp     rcx, rdx
0x180004207  jz      short loc_180004227
0x180004209  test    byte ptr [rcx+1Ch], 2
0x18000420d  jz      short loc_180004227
0x18000420f  mov     edx, 1Fh
0x180004214  mov     r9d, eax
0x180004217  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18000421e  mov     rcx, [rcx+10h]
0x180004222  call    WPP_SF_d
0x180004227  mov     ecx, ebx; Status
0x180004229  call    cs:__imp_RtlNtStatusToDosError
0x18000422f  mov     ebx, eax
0x180004231  lea     rcx, [rbp+var_38]
0x180004235  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000423a  nop
0x18000423b  lea     rcx, [rbp+var_50]
0x18000423f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004244  nop
0x180004245  mov     eax, ebx
0x180004247  jmp     loc_180004779
0x18000424c  mov     [rbp+TokenInformationLength], r14d
0x180004250  lea     rax, [rbp+TokenInformationLength]
0x180004254  xor     r9d, r9d; TokenInformationLength
0x180004257  xor     r8d, r8d; TokenInformation
0x18000425a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000425e  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180004263  cmp     [rbp+TokenInformation], r8d
0x180004267  jz      loc_1800043C6
0x18000426d  mov     edx, 1Fh; TokenInformationClass
0x180004272  call    cs:__imp_NtQueryInformationToken
0x180004278  mov     ebx, eax
0x18000427a  cmp     eax, 0C0000023h
0x18000427f  jz      short loc_1800042D7
0x180004281  lea     rdx, WPP_GLOBAL_Control
0x180004288  mov     rcx, cs:WPP_GLOBAL_Control
0x18000428f  cmp     rcx, rdx
0x180004292  jz      short loc_1800042B2
0x180004294  test    byte ptr [rcx+1Ch], 2
0x180004298  jz      short loc_1800042B2
0x18000429a  mov     edx, 20h ; ' '
0x18000429f  mov     r9d, eax
0x1800042a2  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x1800042a9  mov     rcx, [rcx+10h]
0x1800042ad  call    WPP_SF_d
0x1800042b2  mov     ecx, ebx; Status
0x1800042b4  call    cs:__imp_RtlNtStatusToDosError
0x1800042ba  mov     ebx, eax
0x1800042bc  lea     rcx, [rbp+var_38]
0x1800042c0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800042c5  nop
0x1800042c6  lea     rcx, [rbp+var_50]
0x1800042ca  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800042cf  nop
0x1800042d0  mov     eax, ebx
0x1800042d2  jmp     loc_180004779
0x1800042d7  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800042da  mov     ecx, 40h ; '@'; uFlags
0x1800042df  call    cs:__imp_LocalAlloc
0x1800042e5  mov     rbx, rax
0x1800042e8  mov     [rbp+var_30], rax
0x1800042ec  test    rax, rax
0x1800042ef  jnz     short loc_180004347
0x1800042f1  lea     rdx, WPP_GLOBAL_Control
0x1800042f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042ff  cmp     rcx, rdx
0x180004302  jz      short loc_18000431F
0x180004304  test    byte ptr [rcx+1Ch], 2
0x180004308  jz      short loc_18000431F
0x18000430a  mov     edx, 21h ; '!'
0x18000430f  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180004316  mov     rcx, [rcx+10h]
0x18000431a  call    WPP_SF_
0x18000431f  mov     ecx, 0C000009Ah; Status
0x180004324  call    cs:__imp_RtlNtStatusToDosError
0x18000432a  mov     ebx, eax
0x18000432c  lea     rcx, [rbp+var_38]
0x180004330  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004335  nop
0x180004336  lea     rcx, [rbp+var_50]
0x18000433a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000433f  nop
0x180004340  mov     eax, ebx
0x180004342  jmp     loc_180004779
0x180004347  lea     rax, [rbp+TokenInformationLength]
0x18000434b  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180004350  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180004354  mov     r8, rbx; TokenInformation
0x180004357  mov     edx, 1Fh; TokenInformationClass
0x18000435c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180004360  call    cs:__imp_NtQueryInformationToken
0x180004366  mov     edi, eax
0x180004368  test    eax, eax
0x18000436a  jns     loc_18000462E
0x180004370  lea     rdx, WPP_GLOBAL_Control
0x180004377  mov     rcx, cs:WPP_GLOBAL_Control
0x18000437e  cmp     rcx, rdx
0x180004381  jz      short loc_1800043A1
0x180004383  test    byte ptr [rcx+1Ch], 2
0x180004387  jz      short loc_1800043A1
0x180004389  mov     edx, 22h ; '"'
0x18000438e  mov     r9d, eax
0x180004391  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180004398  mov     rcx, [rcx+10h]
0x18000439c  call    WPP_SF_d
0x1800043a1  mov     ecx, edi; Status
0x1800043a3  call    cs:__imp_RtlNtStatusToDosError
0x1800043a9  mov     ebx, eax
0x1800043ab  lea     rcx, [rbp+var_38]
0x1800043af  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800043b4  nop
0x1800043b5  lea     rcx, [rbp+var_50]
0x1800043b9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800043be  nop
0x1800043bf  mov     eax, ebx
0x1800043c1  jmp     loc_180004779
0x1800043c6  mov     edx, 19h; TokenInformationClass
0x1800043cb  call    cs:__imp_NtQueryInformationToken
0x1800043d1  mov     ebx, eax
0x1800043d3  mov     eax, 80000000h
0x1800043d8  lea     ecx, [rbx+rax]
0x1800043db  test    eax, ecx
0x1800043dd  jnz     loc_1800044AE
0x1800043e3  cmp     ebx, 0C0000023h
0x1800043e9  jz      loc_1800044AE
0x1800043ef  lea     rdx, WPP_GLOBAL_Control
0x1800043f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043fd  cmp     rcx, rdx
0x180004400  jz      short loc_180004420
0x180004402  test    byte ptr [rcx+1Ch], 2
0x180004406  jz      short loc_180004420
0x180004408  mov     edx, 23h ; '#'
0x18000440d  mov     r9d, ebx
0x180004410  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180004417  mov     rcx, [rcx+10h]
0x18000441b  call    WPP_SF_d
0x180004420  mov     ecx, ebx; Status
0x180004422  call    cs:__imp_RtlNtStatusToDosError
0x180004428  mov     edi, eax
0x18000442a  mov     rbx, [rbp+TokenHandle]
0x18000442e  test    rbx, rbx
0x180004431  jz      short loc_1800044A7
0x180004433  mov     ecx, [rbp+var_40]
0x180004436  test    ecx, ecx
0x180004438  jz      short loc_180004461
0x18000443a  test    rbx, rbx
0x18000443d  jz      short loc_180004461
0x18000443f  mov     eax, ecx
0x180004441  test    ecx, ecx
0x180004443  jz      short loc_180004461
0x180004445  nop     word ptr [rax+rax+00000000h]
0x180004450  mov     byte ptr [rbx], 0
0x180004453  lea     rbx, [rbx+1]
0x180004457  sub     rax, 1
0x18000445b  jnz     short loc_180004450
0x18000445d  mov     rbx, [rbp+TokenHandle]
0x180004461  mov     rax, [rbp+var_50]
0x180004465  test    rax, rax
0x180004468  jz      short loc_180004474
0x18000446a  mov     rcx, rbx
0x18000446d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004472  jmp     short loc_1800044A7
0x180004474  test    rbx, rbx
0x180004477  jz      short loc_1800044A7
0x180004479  mov     rcx, rbx; hMem
0x18000447c  call    cs:__imp_LocalSize
0x180004482  test    rax, rax
0x180004485  jz      short loc_18000449D
0x180004487  mov     rcx, rbx
0x18000448a  nop     word ptr [rax+rax+00h]
0x180004490  mov     byte ptr [rcx], 0
0x180004493  lea     rcx, [rcx+1]
0x180004497  sub     rax, 1
0x18000449b  jnz     short loc_180004490
0x18000449d  mov     rcx, rbx; hMem
0x1800044a0  call    cs:__imp_LocalFree
0x1800044a6  nop
0x1800044a7  mov     eax, edi
0x1800044a9  jmp     loc_180004779
0x1800044ae  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800044b1  mov     ecx, 40h ; '@'; uFlags
0x1800044b6  call    cs:__imp_LocalAlloc
0x1800044bc  mov     rbx, rax
0x1800044bf  mov     [rbp+var_30], rax
0x1800044c3  test    rax, rax
0x1800044c6  jnz     short loc_18000451E
0x1800044c8  lea     rdx, WPP_GLOBAL_Control
0x1800044cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044d6  cmp     rcx, rdx
0x1800044d9  jz      short loc_1800044F6
0x1800044db  test    byte ptr [rcx+1Ch], 2
0x1800044df  jz      short loc_1800044F6
0x1800044e1  mov     edx, 24h ; '$'
0x1800044e6  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x1800044ed  mov     rcx, [rcx+10h]
0x1800044f1  call    WPP_SF_
0x1800044f6  mov     ecx, 0C000009Ah; Status
0x1800044fb  call    cs:__imp_RtlNtStatusToDosError
0x180004501  mov     ebx, eax
0x180004503  lea     rcx, [rbp+var_38]
0x180004507  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000450c  nop
0x18000450d  lea     rcx, [rbp+var_50]
0x180004511  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004516  nop
0x180004517  mov     eax, ebx
0x180004519  jmp     loc_180004779
0x18000451e  lea     rax, [rbp+TokenInformationLength]
0x180004522  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180004527  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000452b  mov     r8, rbx; TokenInformation
0x18000452e  mov     edx, 19h; TokenInformationClass
0x180004533  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180004537  call    cs:__imp_NtQueryInformationToken
0x18000453d  mov     edi, eax
0x18000453f  test    eax, eax
0x180004541  jns     loc_18000462E
0x180004547  lea     rdx, WPP_GLOBAL_Control
0x18000454e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004555  cmp     rcx, rdx
0x180004558  jz      short loc_180004578
0x18000455a  test    byte ptr [rcx+1Ch], 2
0x18000455e  jz      short loc_180004578
0x180004560  mov     edx, 25h ; '%'
0x180004565  mov     r9d, eax
0x180004568  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18000456f  mov     rcx, [rcx+10h]
0x180004573  call    WPP_SF_d
0x180004578  mov     ecx, edi; Status
0x18000457a  call    cs:__imp_RtlNtStatusToDosError
0x180004580  mov     edi, eax
0x180004582  mov     rcx, rbx; hMem
0x180004585  call    cs:__imp_LocalSize
0x18000458b  test    rax, rax
0x18000458e  jz      short loc_1800045A0
0x180004590  mov     rcx, rbx
0x180004593  mov     byte ptr [rcx], 0
0x180004596  lea     rcx, [rcx+1]
0x18000459a  sub     rax, 1
0x18000459e  jnz     short loc_180004593
0x1800045a0  mov     rcx, rbx; hMem
  ... truncated ...
```
