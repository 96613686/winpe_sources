# ScUpdateServiceSidCache(ushort const *,int)

- ea: `0x14007bffc`
- end: `0x14007c862`
- name: `?ScUpdateServiceSidCache@@YAXPEBGH@Z`
- size: `2150`
- prototype: `void __fastcall(PCWSTR SourceString, int)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140067cb8`
- `0x14006a9e0`
- `0x1400709e0`
- `0x1400848e0`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140007960`
- `0x1400157bc`
- `0x14001f99c`
- `0x140020864`
- `0x140029228`
- `0x140042a80`
- `0x1400575b0`
- `0x140057844`
- `0x14007bffc`
- `0x14007e6c0`
- `0x1400866c4`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007c79d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007c7ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007c7db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007c79d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007c7ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007c7db`
- `ntdll!RtlInitUnicodeString` at `0x14007c14e`
- `ntdll!RtlInitUnicodeString` at `0x14007c16a`
- `ntdll!RtlInitUnicodeString` at `0x14007c186`
- `ntdll!RtlInitUnicodeString` at `0x14007c197`
- `ntdll!RtlInitUnicodeString` at `0x14007c236`
- `ntdll!RtlInitUnicodeString` at `0x14007c247`
- `ntdll!RtlInitUnicodeString` at `0x14007c2ff`
- `ntdll!RtlInitUnicodeString` at `0x14007c316`
- `ntdll!RtlInitUnicodeString` at `0x14007c355`
- `ntdll!RtlInitUnicodeString` at `0x14007c36c`
- `ntdll!RtlInitUnicodeString` at `0x14007c3c3`
- `ntdll!RtlInitUnicodeString` at `0x14007c3df`
- `ntdll!RtlInitUnicodeString` at `0x14007c422`
- `ntdll!RtlInitUnicodeString` at `0x14007c43e`
- `ntdll!RtlInitUnicodeString` at `0x14007c5ca`
- `ntdll!RtlInitUnicodeString` at `0x14007c5da`
- `ntdll!RtlInitUnicodeString` at `0x14007c63d`
- `ntdll!RtlInitUnicodeString` at `0x14007c64e`
- `ntdll!RtlInitUnicodeString` at `0x14007c6ac`
- `ntdll!RtlInitUnicodeString` at `0x14007c6bd`
- `ntdll!RtlInitUnicodeString` at `0x14007c14e`
- `ntdll!RtlInitUnicodeString` at `0x14007c16a`
- `ntdll!RtlInitUnicodeString` at `0x14007c186`
- `ntdll!RtlInitUnicodeString` at `0x14007c197`
- `ntdll!RtlInitUnicodeString` at `0x14007c236`
- `ntdll!RtlInitUnicodeString` at `0x14007c247`
- `ntdll!RtlInitUnicodeString` at `0x14007c2ff`
- `ntdll!RtlInitUnicodeString` at `0x14007c316`
- `ntdll!RtlInitUnicodeString` at `0x14007c355`
- `ntdll!RtlInitUnicodeString` at `0x14007c36c`
- `ntdll!RtlInitUnicodeString` at `0x14007c3c3`
- `ntdll!RtlInitUnicodeString` at `0x14007c3df`
- `ntdll!RtlInitUnicodeString` at `0x14007c422`
- `ntdll!RtlInitUnicodeString` at `0x14007c43e`
- `ntdll!RtlInitUnicodeString` at `0x14007c5ca`
- `ntdll!RtlInitUnicodeString` at `0x14007c5da`
- `ntdll!RtlInitUnicodeString` at `0x14007c63d`
- `ntdll!RtlInitUnicodeString` at `0x14007c64e`
- `ntdll!RtlInitUnicodeString` at `0x14007c6ac`
- `ntdll!RtlInitUnicodeString` at `0x14007c6bd`
- `ntdll!RtlFreeHeap` at `0x14007c7fa`
- `ntdll!RtlFreeHeap` at `0x14007c7fa`
- `ntdll!RtlSubAuthoritySid` at `0x14007c1fd`
- `ntdll!RtlSubAuthoritySid` at `0x14007c211`
- `ntdll!RtlSubAuthoritySid` at `0x14007c29e`
- `ntdll!RtlSubAuthoritySid` at `0x14007c2b2`
- `ntdll!RtlSubAuthoritySid` at `0x14007c1fd`
- `ntdll!RtlSubAuthoritySid` at `0x14007c211`
- `ntdll!RtlSubAuthoritySid` at `0x14007c29e`
- `ntdll!RtlSubAuthoritySid` at `0x14007c2b2`
- `ntdll!RtlAllocateHeap` at `0x14007c0fb`
- `ntdll!RtlAllocateHeap` at `0x14007c592`
- `ntdll!RtlAllocateHeap` at `0x14007c0fb`
- `ntdll!RtlAllocateHeap` at `0x14007c592`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x14007c6ce`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x14007c6ce`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14007c78e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14007c78e`

## string_xrefs

- `0x14007c144`: `NT SERVICE`
- `0x14007c177`: `NT SERVICE`
- `0x14007c2e7`: `NT SERVICE`
- `0x14007c3b6`: `NT SERVICE`
- `0x14007c5d0`: `NT SERVICE`
- `0x14007c6b2`: `NT SERVICE`
- `0x14007c15b`: `RESTRICTED SERVICES`
- `0x14007c222`: `RESTRICTED SERVICES`
- `0x14007c340`: `RESTRICTED SERVICES`
- `0x14007c40d`: `RESTRICTED SERVICES`
- `0x14007c643`: `RESTRICTED SERVICES`
- `0x14007c190`: `ALL SERVICES`
- `0x14007c240`: `ALL RESTRICTED SERVICES`

## pseudocode

```c
void __fastcall ScUpdateServiceSidCache(PCWSTR SourceString, int a2)
{
  unsigned int v2; // r15d
  char v3; // bl
  struct _UNICODE_STRING *v5; // r13
  PSID v6; // rdi
  __int64 v7; // r14
  unsigned int Win32Services; // eax
  unsigned int v9; // esi
  PVOID ProcessHeap; // rcx
  struct _UNICODE_STRING *v11; // rax
  PRPC_ASYNC_STATE v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r9
  PRPC_ASYNC_STATE v16; // rcx
  __int64 v17; // rdx
  PSID v18; // rbx
  PULONG v19; // rax
  int v20; // eax
  PSID v21; // rbx
  PULONG v22; // rax
  void **v23; // rbx
  _QWORD *v24; // rsi
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rcx
  int v27; // r8d
  const WCHAR *v28; // rdx
  const WCHAR *v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  const WCHAR *v32; // rax
  const WCHAR *v33; // rax
  int v34; // eax
  char v35; // di
  const WCHAR *v36; // rax
  const WCHAR *v37; // rax
  int v38; // eax
  int v39; // eax
  int v40; // edx
  PRPC_ASYNC_STATE v41; // rcx
  __int64 v42; // r9
  int v43; // edx
  struct _UNICODE_STRING *Heap; // rax
  int ServiceSidFromString; // eax
  char v46; // r8
  PRPC_ASYNC_STATE v47; // rcx
  int v48; // edx
  int RestrictedAccountSidFromString; // eax
  int v50; // r9d
  const wchar_t *v51; // rax
  __int64 i; // rbx
  void *v53; // rcx
  _QWORD *v54; // rbx
  _QWORD *v55; // rdx
  __int64 v56; // rax
  SmartPtrRef *v57; // rcx
  unsigned int v58; // [rsp+40h] [rbp-69h] BYREF
  PSID Sid; // [rsp+48h] [rbp-61h] BYREF
  void *v60; // [rsp+50h] [rbp-59h]
  int v61; // [rsp+58h] [rbp-51h]
  PVOID Buffer; // [rsp+60h] [rbp-49h] BYREF
  void *v63[3]; // [rsp+68h] [rbp-41h] BYREF
  struct _UNICODE_STRING v64; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-19h] BYREF
  HLOCAL hMem[2]; // [rsp+A0h] [rbp-9h]
  int v67; // [rsp+B0h] [rbp+7h] BYREF
  __int16 v68; // [rsp+B4h] [rbp+Bh]

  v61 = a2;
  v63[2] = 0;
  Buffer = 0;
  v63[0] = v63;
  v63[1] = v63;
  v2 = 1;
  v67 = 0;
  v3 = a2;
  v68 = 1280;
  v60 = 0;
  v5 = 0;
  Sid = 0;
  v6 = 0;
  v58 = 0;
  LODWORD(v7) = 0;
  v64 = 0;
  DestinationString = 0;
  *(_OWORD *)hMem = 0;
  if ( !a2 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlInitUnicodeString(&v64, L"NT SERVICE");
    goto LABEL_75;
  }
  if ( SourceString )
  {
    Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x60u);
    v5 = Heap;
    if ( !Heap )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_58;
      v13 = 213;
      goto LABEL_11;
    }
    RtlInitUnicodeString(Heap + 1, SourceString);
    RtlInitUnicodeString(v5, L"NT SERVICE");
    ServiceSidFromString = ScCreateServiceSidFromString(SourceString);
    v46 = ServiceSidFromString;
    if ( ServiceSidFromString )
    {
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_58;
      v48 = 214;
LABEL_68:
      WPP_SF_Sd(
        v47->StubInfo,
        v48,
        (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
        (_DWORD)SourceString,
        v46);
      goto LABEL_87;
    }
    RtlInitUnicodeString(v5 + 4, SourceString);
    RtlInitUnicodeString(v5 + 3, L"RESTRICTED SERVICES");
    RestrictedAccountSidFromString = ScCreateRestrictedAccountSidFromString(SourceString);
    v46 = RestrictedAccountSidFromString;
    if ( RestrictedAccountSidFromString )
    {
      LODWORD(v7) = 1;
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_58;
      v48 = 215;
      goto LABEL_68;
    }
    v2 = 2;
    v64.Buffer = &v5->Length;
    LODWORD(v7) = 2;
    *(_DWORD *)&v64.Length = 2;
LABEL_75:
    if ( (int)LsaLookupManageSidNameMapping(v2, &v64, &Buffer) >= 0 )
    {
      if ( v2 - 1 < 2 )
        v50 = *(_DWORD *)Buffer;
      else
        v50 = 13;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      {
        v51 = L"NULL";
        if ( SourceString )
          v51 = SourceString;
        WPP_SF_ddSd(
          WPP_GLOBAL_Control->StubInfo,
          217,
          (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
          v50,
          v7,
          (__int64)v51,
          v3);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_58;
      WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 216, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
    }
    goto LABEL_87;
  }
  Win32Services = ScGetWin32Services(v63, &v58);
  if ( Win32Services )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 205, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, Win32Services);
    goto LABEL_87;
  }
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v58 = 4 * v58 + 4;
  v9 = v58;
  v11 = (struct _UNICODE_STRING *)RtlAllocateHeap(ProcessHeap, 8u, 48LL * v58);
  v5 = v11;
  if ( !v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_87;
    v13 = 206;
LABEL_11:
    WPP_SF_(v12->StubInfo, v13, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
    goto LABEL_87;
  }
  RtlInitUnicodeString(v11, L"NT SERVICE");
  *(_QWORD *)&v5[2].Length = ServiceBaseSid;
  RtlInitUnicodeString(v5 + 3, L"RESTRICTED SERVICES");
  *(_QWORD *)&v5[5].Length = RestrictedServicesBaseSid;
  RtlInitUnicodeString(v5 + 6, L"NT SERVICE");
  RtlInitUnicodeString(v5 + 7, L"ALL SERVICES");
  v2 = 2;
  v14 = ScAllocateAndInitializeSid(&Sid, &v67, 2);
  v15 = (unsigned int)v14;
  if ( v14 < 0 )
  {
    LODWORD(v7) = 2;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_17;
    v17 = 207;
LABEL_16:
    WPP_SF_d(v16->StubInfo, v17, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v15);
LABEL_17:
    v6 = Sid;
    goto LABEL_87;
  }
  v18 = Sid;
  *RtlSubAuthoritySid(Sid, 0) = 80;
  v19 = RtlSubAuthoritySid(v18, 1u);
  Sid = 0;
  *v19 = 0;
  *(_QWORD *)&v5[8].Length = v18;
  RtlInitUnicodeString(v5 + 9, L"RESTRICTED SERVICES");
  RtlInitUnicodeString(v5 + 10, L"ALL RESTRICTED SERVICES");
  v20 = ScAllocateAndInitializeSid(&Sid, &v67, 2);
  v15 = (unsigned int)v20;
  if ( v20 < 0 )
  {
    LODWORD(v7) = 3;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_17;
    v17 = 208;
    goto LABEL_16;
  }
  v21 = Sid;
  *RtlSubAuthoritySid(Sid, 0) = 99;
  v22 = RtlSubAuthoritySid(v21, 1u);
  v60 = 0;
  *v22 = 0;
  LODWORD(v7) = 4;
  *(_QWORD *)&v5[11].Length = v21;
  v23 = (void **)v63[0];
  while ( 1 )
  {
    if ( v23 == v63 || (unsigned int)v7 >= v9 )
    {
      v6 = v60;
      v3 = v61;
      *(_DWORD *)&v64.Length = v7;
      v64.Buffer = &v5->Length;
      goto LABEL_75;
    }
    v24 = v23[2];
    RtlInitUnicodeString(&v5[3 * (unsigned int)v7], L"NT SERVICE");
    v25 = (const WCHAR *)v24[9];
    if ( !v25 )
      v25 = (const WCHAR *)v24[7];
    RtlInitUnicodeString(&v5[3 * (unsigned int)v7 + 1], v25);
    v26 = (const WCHAR *)v24[9];
    if ( !v26 )
      v26 = (const WCHAR *)v24[7];
    v27 = ScCreateServiceSidFromString(v26);
    if ( v27 < 0 )
      break;
    v7 = (unsigned int)(v7 + 1);
    RtlInitUnicodeString(&v5[3 * v7], L"RESTRICTED SERVICES");
    v28 = (const WCHAR *)v24[9];
    if ( !v28 )
      v28 = (const WCHAR *)v24[7];
    RtlInitUnicodeString(&v5[3 * v7 + 1], v28);
    v29 = (const WCHAR *)v24[9];
    if ( !v29 )
      v29 = (const WCHAR *)v24[7];
    v30 = ScCreateRestrictedAccountSidFromString(v29);
    LOBYTE(v27) = v30;
    if ( v30 < 0 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v42 = v24[9];
        if ( !v42 )
          v42 = v24[7];
        v43 = 210;
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    LODWORD(v7) = v7 + 1;
    if ( (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(*v24 + 32LL))(v24, v31, (unsigned int)v30) )
    {
      RtlInitUnicodeString(&v5[3 * (unsigned int)v7], L"NT SERVICE");
      v32 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v24 + 32LL))(v24);
      RtlInitUnicodeString(&v5[3 * (unsigned int)v7 + 1], v32);
      v33 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v24 + 32LL))(v24);
      v34 = ScCreateServiceSidFromString(v33);
      v35 = v34;
      if ( v34 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_58;
        }
        v39 = (*(__int64 (__fastcall **)(_QWORD *))(*v24 + 32LL))(v24);
        v40 = 211;
      }
      else
      {
        v7 = (unsigned int)(v7 + 1);
        RtlInitUnicodeString(&v5[3 * v7], L"RESTRICTED SERVICES");
        v36 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v24 + 32LL))(v24);
        RtlInitUnicodeString(&v5[3 * v7 + 1], v36);
        v37 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v24 + 32LL))(v24);
        v38 = ScCreateRestrictedAccountSidFromString(v37);
        v35 = v38;
        if ( v38 >= 0 )
        {
          LODWORD(v7) = v7 + 1;
          goto LABEL_39;
        }
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_58;
        }
        v39 = (*(__int64 (__fastcall **)(_QWORD *))(*v24 + 32LL))(v24);
        v40 = 212;
      }
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        v40,
        (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
        v39,
        v35);
      goto LABEL_58;
    }
LABEL_39:
    v23 = (void **)*v23;
    v9 = v58;
  }
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v42 = v24[9];
    if ( !v42 )
      v42 = v24[7];
    v43 = 209;
LABEL_57:
    WPP_SF_Sd(v41->StubInfo, v43, (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v42, v27);
  }
LABEL_58:
  v6 = v60;
LABEL_87:
  if ( Buffer )
    LsaLookupFreeMemory(Buffer);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v6 )
    LocalFree(v6);
  if ( v5 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
    {
      v53 = *(void **)&v5[3 * i + 2].Length;
      if ( v53 != (void *)ServiceBaseSid && v53 != (void *)RestrictedServicesBaseSid )
        LocalFree(v53);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  while ( 1 )
  {
    v54 = v63[0];
    if ( v63[0] == v63 )
      break;
    v55 = (_QWORD *)*((_QWORD *)v63[0] + 1);
    v56 = *(_QWORD *)v63[0];
    *v55 = *(_QWORD *)v63[0];
    *(_QWORD *)(v56 + 8) = v55;
    v57 = (SmartPtrRef *)v54[2];
    if ( v57 )
    {
      v54[2] = 0;
      SmartPtrRef::Release(v57);
    }
    operator delete(v54, (const struct std::nothrow_t *)std::nothrow);
  }
}

```

## disassembly

```asm
0x14007bffc  push    rbp
0x14007bffe  push    rbx
0x14007bfff  push    rsi
0x14007c000  push    rdi
0x14007c001  push    r12
0x14007c003  push    r13
0x14007c005  push    r14
0x14007c007  push    r15
0x14007c009  lea     rbp, [rsp-1Fh]
0x14007c00e  sub     rsp, 0C8h
0x14007c015  mov     rax, cs:__security_cookie
0x14007c01c  xor     rax, rsp
0x14007c01f  mov     [rbp+57h+var_48], rax
0x14007c023  xor     esi, esi
0x14007c025  mov     [rbp+57h+var_A8], edx
0x14007c028  mov     [rbp+57h+var_88], rsi
0x14007c02c  xorps   xmm0, xmm0
0x14007c02f  mov     [rbp+57h+Buffer], rsi
0x14007c033  lea     rax, [rbp+57h+var_98]
0x14007c037  mov     [rbp+57h+var_98], rax
0x14007c03b  lea     rax, [rbp+57h+var_98]
0x14007c03f  mov     [rbp+57h+var_90], rax
0x14007c043  lea     r15d, [rsi+1]
0x14007c047  mov     [rbp+57h+var_50], esi
0x14007c04a  mov     ebx, edx
0x14007c04c  mov     [rbp+57h+var_4C], 500h
0x14007c052  mov     r12, rcx
0x14007c055  mov     [rbp+57h+var_B0], rsi
0x14007c059  mov     r13d, esi
0x14007c05c  mov     [rbp+57h+Sid], rsi
0x14007c060  mov     edi, esi
0x14007c062  mov     [rbp+57h+var_C0], esi
0x14007c065  mov     r14d, esi
0x14007c068  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x14007c06c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14007c070  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x14007c074  test    edx, edx
0x14007c076  jz      loc_14007C6A5
0x14007c07c  test    rcx, rcx
0x14007c07f  jnz     loc_14007C57C
0x14007c085  lea     rdx, [rbp+57h+var_C0]
0x14007c089  lea     rcx, [rbp+57h+var_98]
0x14007c08d  call    ?ScGetWin32Services@@YAKAEAV?$list@V?$ComPtr@VCWin32ServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCWin32ServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@AEAK@Z; ScGetWin32Services(utl::list<Microsoft::WRL::ComPtr<CWin32ServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CWin32ServiceRecord>>> &,ulong &)
0x14007c092  mov     r9d, eax
0x14007c095  test    eax, eax
0x14007c097  jz      short loc_14007C0D4
0x14007c099  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c0a0  lea     rax, WPP_GLOBAL_Control
0x14007c0a7  cmp     rcx, rax
0x14007c0aa  jz      loc_14007C785
0x14007c0b0  test    [rcx+1Ch], r15b
0x14007c0b4  jz      loc_14007C785
0x14007c0ba  mov     rcx, [rcx+10h]
0x14007c0be  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007c0c5  mov     edx, 0CDh
0x14007c0ca  call    WPP_SF_d
0x14007c0cf  jmp     loc_14007C785
0x14007c0d4  mov     eax, [rbp+57h+var_C0]
0x14007c0d7  mov     edx, 8; Flags
0x14007c0dc  mov     rcx, gs:60h
0x14007c0e5  lea     esi, ds:4[rax*4]
0x14007c0ec  mov     rcx, [rcx+30h]; HeapHandle
0x14007c0f0  lea     r8, [rsi+rsi*2]
0x14007c0f4  shl     r8, 4; Size
0x14007c0f8  mov     [rbp+57h+var_C0], esi
0x14007c0fb  call    cs:__imp_RtlAllocateHeap
0x14007c101  mov     r13, rax
0x14007c104  test    rax, rax
0x14007c107  jnz     short loc_14007C144
0x14007c109  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c110  lea     rax, WPP_GLOBAL_Control
0x14007c117  cmp     rcx, rax
0x14007c11a  jz      loc_14007C785
0x14007c120  test    [rcx+1Ch], r15b
0x14007c124  jz      loc_14007C785
0x14007c12a  mov     edx, 0CEh
0x14007c12f  mov     rcx, [rcx+10h]
0x14007c133  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007c13a  call    WPP_SF_
0x14007c13f  jmp     loc_14007C785
0x14007c144  lea     rdx, aNtService; "NT SERVICE"
0x14007c14b  mov     rcx, r13; DestinationString
0x14007c14e  call    cs:__imp_RtlInitUnicodeString
0x14007c154  mov     rax, cs:ServiceBaseSid
0x14007c15b  lea     rdx, aRestrictedServ; "RESTRICTED SERVICES"
0x14007c162  lea     rcx, [r13+30h]; DestinationString
0x14007c166  mov     [r13+20h], rax
0x14007c16a  call    cs:__imp_RtlInitUnicodeString
0x14007c170  mov     rax, cs:RestrictedServicesBaseSid
0x14007c177  lea     rdx, aNtService; "NT SERVICE"
0x14007c17e  lea     rcx, [r13+60h]; DestinationString
0x14007c182  mov     [r13+50h], rax
0x14007c186  call    cs:__imp_RtlInitUnicodeString
0x14007c18c  lea     rcx, [r13+70h]; DestinationString
0x14007c190  lea     rdx, aAllServices; "ALL SERVICES"
0x14007c197  call    cs:__imp_RtlInitUnicodeString
0x14007c19d  mov     r15d, 2
0x14007c1a3  lea     rdx, [rbp+57h+var_50]
0x14007c1a7  mov     r8d, r15d
0x14007c1aa  lea     rcx, [rbp+57h+Sid]
0x14007c1ae  call    ScAllocateAndInitializeSid
0x14007c1b3  mov     r9d, eax
0x14007c1b6  test    eax, eax
0x14007c1b8  jns     short loc_14007C1F4
0x14007c1ba  mov     r14d, r15d
0x14007c1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c1c4  lea     rax, WPP_GLOBAL_Control
0x14007c1cb  cmp     rcx, rax
0x14007c1ce  jz      short loc_14007C1EB
0x14007c1d0  test    byte ptr [rcx+1Ch], 1
0x14007c1d4  jz      short loc_14007C1EB
0x14007c1d6  mov     edx, 0CFh
0x14007c1db  mov     rcx, [rcx+10h]
0x14007c1df  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007c1e6  call    WPP_SF_d
0x14007c1eb  mov     rdi, [rbp+57h+Sid]
0x14007c1ef  jmp     loc_14007C785
0x14007c1f4  mov     rbx, [rbp+57h+Sid]
0x14007c1f8  xor     edx, edx; SubAuthority
0x14007c1fa  mov     rcx, rbx; Sid
0x14007c1fd  call    cs:__imp_RtlSubAuthoritySid
0x14007c203  mov     edx, 1; SubAuthority
0x14007c208  mov     rcx, rbx; Sid
0x14007c20b  mov     dword ptr [rax], 50h ; 'P'
0x14007c211  call    cs:__imp_RtlSubAuthoritySid
0x14007c217  lea     rdi, [r13+90h]
0x14007c21e  mov     [rbp+57h+Sid], r14
0x14007c222  lea     rdx, aRestrictedServ; "RESTRICTED SERVICES"
0x14007c229  mov     rcx, rdi; DestinationString
0x14007c22c  mov     [rax], r14d
0x14007c22f  mov     [r13+80h], rbx
0x14007c236  call    cs:__imp_RtlInitUnicodeString
0x14007c23c  lea     rcx, [rdi+10h]; DestinationString
0x14007c240  lea     rdx, aAllRestrictedS; "ALL RESTRICTED SERVICES"
0x14007c247  call    cs:__imp_RtlInitUnicodeString
0x14007c24d  mov     r8d, r15d
0x14007c250  lea     rdx, [rbp+57h+var_50]
0x14007c254  lea     rcx, [rbp+57h+Sid]
0x14007c258  call    ScAllocateAndInitializeSid
0x14007c25d  mov     r9d, eax
0x14007c260  test    eax, eax
0x14007c262  jns     short loc_14007C295
0x14007c264  mov     r14d, 3
0x14007c26a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c271  lea     rax, WPP_GLOBAL_Control
0x14007c278  cmp     rcx, rax
0x14007c27b  jz      loc_14007C1EB
0x14007c281  test    byte ptr [rcx+1Ch], 1
0x14007c285  jz      loc_14007C1EB
0x14007c28b  mov     edx, 0D0h
0x14007c290  jmp     loc_14007C1DB
0x14007c295  mov     rbx, [rbp+57h+Sid]
0x14007c299  xor     edx, edx; SubAuthority
0x14007c29b  mov     rcx, rbx; Sid
0x14007c29e  call    cs:__imp_RtlSubAuthoritySid
0x14007c2a4  mov     edx, 1; SubAuthority
0x14007c2a9  mov     rcx, rbx; Sid
0x14007c2ac  mov     dword ptr [rax], 63h ; 'c'
0x14007c2b2  call    cs:__imp_RtlSubAuthoritySid
0x14007c2b8  mov     [rbp+57h+var_B0], r14
0x14007c2bc  mov     [rax], r14d
0x14007c2bf  mov     r14d, 4
0x14007c2c5  mov     [rdi+20h], rbx
0x14007c2c9  mov     rbx, [rbp+57h+var_98]
0x14007c2cd  lea     rax, [rbp+57h+var_98]
0x14007c2d1  cmp     rbx, rax
0x14007c2d4  jz      loc_14007C568
0x14007c2da  cmp     r14d, esi
0x14007c2dd  jnb     loc_14007C568
0x14007c2e3  mov     rsi, [rbx+10h]
0x14007c2e7  lea     rdx, aNtService; "NT SERVICE"
0x14007c2ee  mov     eax, r14d
0x14007c2f1  lea     rdi, [rax+rax*2]
0x14007c2f5  shl     rdi, 4
0x14007c2f9  add     rdi, r13
0x14007c2fc  mov     rcx, rdi; DestinationString
0x14007c2ff  call    cs:__imp_RtlInitUnicodeString
0x14007c305  mov     rdx, [rsi+48h]
0x14007c309  test    rdx, rdx
0x14007c30c  jnz     short loc_14007C312
0x14007c30e  mov     rdx, [rsi+38h]; SourceString
0x14007c312  lea     rcx, [rdi+10h]; DestinationString
0x14007c316  call    cs:__imp_RtlInitUnicodeString
0x14007c31c  mov     rcx, [rsi+48h]
0x14007c320  test    rcx, rcx
0x14007c323  jnz     short loc_14007C329
0x14007c325  mov     rcx, [rsi+38h]; SourceString
0x14007c329  lea     rdx, [rdi+20h]
0x14007c32d  call    ScCreateServiceSidFromString
0x14007c332  mov     r8d, eax
0x14007c335  test    eax, eax
0x14007c337  js      loc_14007C51F
0x14007c33d  inc     r14d
0x14007c340  lea     rdx, aRestrictedServ; "RESTRICTED SERVICES"
0x14007c347  lea     rdi, [r14+r14*2]
0x14007c34b  shl     rdi, 4
0x14007c34f  add     rdi, r13
0x14007c352  mov     rcx, rdi; DestinationString
0x14007c355  call    cs:__imp_RtlInitUnicodeString
0x14007c35b  mov     rdx, [rsi+48h]
0x14007c35f  test    rdx, rdx
0x14007c362  jnz     short loc_14007C368
0x14007c364  mov     rdx, [rsi+38h]; SourceString
0x14007c368  lea     rcx, [rdi+10h]; DestinationString
0x14007c36c  call    cs:__imp_RtlInitUnicodeString
0x14007c372  mov     rcx, [rsi+48h]
0x14007c376  test    rcx, rcx
0x14007c379  jnz     short loc_14007C37F
0x14007c37b  mov     rcx, [rsi+38h]; SourceString
0x14007c37f  lea     rdx, [rdi+20h]
0x14007c383  call    ScCreateRestrictedAccountSidFromString
0x14007c388  mov     r8d, eax
0x14007c38b  test    eax, eax
0x14007c38d  js      loc_14007C4F2
0x14007c393  mov     rax, [rsi]
0x14007c396  mov     rcx, rsi
0x14007c399  inc     r14d
0x14007c39c  mov     rax, [rax+20h]
0x14007c3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c3a5  test    rax, rax
0x14007c3a8  jz      loc_14007C468
0x14007c3ae  lea     rdi, [r14+r14*2]
0x14007c3b2  shl     rdi, 4
0x14007c3b6  lea     rdx, aNtService; "NT SERVICE"
0x14007c3bd  add     rdi, r13
0x14007c3c0  mov     rcx, rdi; DestinationString
0x14007c3c3  call    cs:__imp_RtlInitUnicodeString
0x14007c3c9  mov     rax, [rsi]
0x14007c3cc  mov     rcx, rsi
0x14007c3cf  mov     rax, [rax+20h]
0x14007c3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c3d8  mov     rdx, rax; SourceString
0x14007c3db  lea     rcx, [rdi+10h]; DestinationString
0x14007c3df  call    cs:__imp_RtlInitUnicodeString
0x14007c3e5  mov     rax, [rsi]
0x14007c3e8  mov     rcx, rsi
0x14007c3eb  mov     rax, [rax+20h]
0x14007c3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c3f4  mov     rcx, rax; SourceString
0x14007c3f7  lea     rdx, [rdi+20h]
0x14007c3fb  call    ScCreateServiceSidFromString
0x14007c400  mov     edi, eax
0x14007c402  test    eax, eax
0x14007c404  js      loc_14007C4BB
0x14007c40a  inc     r14d
0x14007c40d  lea     rdx, aRestrictedServ; "RESTRICTED SERVICES"
0x14007c414  lea     rdi, [r14+r14*2]
0x14007c418  shl     rdi, 4
0x14007c41c  add     rdi, r13
0x14007c41f  mov     rcx, rdi; DestinationString
0x14007c422  call    cs:__imp_RtlInitUnicodeString
0x14007c428  mov     rax, [rsi]
0x14007c42b  mov     rcx, rsi
0x14007c42e  mov     rax, [rax+20h]
0x14007c432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c437  mov     rdx, rax; SourceString
0x14007c43a  lea     rcx, [rdi+10h]; DestinationString
0x14007c43e  call    cs:__imp_RtlInitUnicodeString
0x14007c444  mov     rax, [rsi]
0x14007c447  mov     rcx, rsi
0x14007c44a  mov     rax, [rax+20h]
0x14007c44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c453  mov     rcx, rax; SourceString
0x14007c456  lea     rdx, [rdi+20h]
0x14007c45a  call    ScCreateRestrictedAccountSidFromString
0x14007c45f  mov     edi, eax
0x14007c461  test    eax, eax
0x14007c463  js      short loc_14007C473
0x14007c465  inc     r14d
0x14007c468  mov     rbx, [rbx]
0x14007c46b  mov     esi, [rbp+57h+var_C0]
0x14007c46e  jmp     loc_14007C2CD
0x14007c473  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c47a  lea     rax, WPP_GLOBAL_Control
0x14007c481  cmp     rcx, rax
0x14007c484  jz      loc_14007C55F
0x14007c48a  test    byte ptr [rcx+1Ch], 1
0x14007c48e  jz      loc_14007C55F
0x14007c494  mov     rax, [rsi]
0x14007c497  mov     rcx, rsi
0x14007c49a  mov     rax, [rax+20h]
0x14007c49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4a3  mov     edx, 0D4h
0x14007c4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c4af  mov     r9, rax
0x14007c4b2  mov     [rsp+100h+var_E0], edi
0x14007c4b6  jmp     loc_14007C54F
0x14007c4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c4c2  lea     rax, WPP_GLOBAL_Control
0x14007c4c9  cmp     rcx, rax
0x14007c4cc  jz      loc_14007C55F
0x14007c4d2  test    byte ptr [rcx+1Ch], 1
0x14007c4d6  jz      loc_14007C55F
0x14007c4dc  mov     rax, [rsi]
0x14007c4df  mov     rcx, rsi
0x14007c4e2  mov     rax, [rax+20h]
0x14007c4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c4eb  mov     edx, 0D3h
0x14007c4f0  jmp     short loc_14007C4A8
0x14007c4f2  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
