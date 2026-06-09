# CSdCommonImpl::_SetupStagingArea(CBsString *,CBsString *,CBsString *)

- ea: `0x18004d448`
- end: `0x18004d6d2`
- name: `?_SetupStagingArea@CSdCommonImpl@@CAJPEAVCBsString@@00@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct CBsString *this, struct CBsString *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800486f0`

## callees

- `0x180008240`
- `0x1800145f4`
- `0x18004c3c4`
- `0x18004d448`
- `0x18004df38`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086220`
- `0x18008f5d0`
- `0x1800996f4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004d69e`
- `KERNEL32!LocalFree` at `0x18004d69e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18004d626`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18004d626`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d4ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d4ee`

## string_xrefs

- `0x18004d477`: `CSdCommonImpl::_SetupStagingArea`
- `0x18004d5fa`: `EnsureDirectoryExists( *pstrFullStagingPath, &sa, FALSE, FALSE )`
- `0x18004d66e`: `::SetFileSecurity( *pstrFullStagingPath, DACL_SECURITY_INFORMATION, pSD)`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::_SetupStagingArea(
        struct CBsString *this,
        struct CBsString *a2,
        const unsigned __int16 **a3)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v8; // rcx
  __int16 v9; // ax
  __int64 v10; // rcx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-9h] BYREF
  int v13; // [rsp+58h] [rbp+Fh] BYREF
  __int16 v14; // [rsp+5Ch] [rbp+13h]
  __int16 v15; // [rsp+5Eh] [rbp+15h]
  ULONG SecurityDescriptorSize; // [rsp+B0h] [rbp+67h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C8h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CSdCommonImpl::_SetupStagingArea", 0x92Eu, 1u);
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v6 = 2355;
  if ( !this || (v14 = 2355, v6 = 2356, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
    v13 = -2147024809;
    v15 = v6;
    goto LABEL_24;
  }
  v13 = 0;
  v14 = 2356;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v13 = LastFailureAsHRESULT;
    v9 = 2359;
LABEL_6:
    v15 = v9;
    goto LABEL_22;
  }
  v13 = 0;
  v14 = 2359;
  LastFailureAsHRESULT = CSdCommonImpl::_GetRootStagingPath(this, a2);
  v13 = LastFailureAsHRESULT;
  v9 = 2361;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v14 = 2361;
  LastFailureAsHRESULT = CBsString::Append(a2, *a3, L"\\");
  v13 = LastFailureAsHRESULT;
  v9 = 2362;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v14 = 2362;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids, *(_QWORD *)a2);
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.bInheritHandle = 0;
  LastFailureAsHRESULT = EnsureDirectoryExists(*(const unsigned __int16 **)a2, &SecurityAttributes, 0, 0);
  v13 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v14 = 2370;
    if ( SetFileSecurityW(*(LPCWSTR *)a2, 4u, SecurityDescriptor) )
    {
      LastFailureAsHRESULT = 0;
      v13 = 0;
      v14 = 2373;
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v13 = LastFailureAsHRESULT;
      v15 = 2373;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_QWORD *)a2,
          (__int64)L"D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
          LastFailureAsHRESULT);
        goto LABEL_16;
      }
    }
  }
  else
  {
    v15 = 2370;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids,
        (unsigned int)"EnsureDirectoryExists( *pstrFullStagingPath, &sa, FALSE, FALSE )",
        *(_QWORD *)a2,
        LastFailureAsHRESULT);
LABEL_16:
      LastFailureAsHRESULT = v13;
    }
  }
LABEL_22:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
    LastFailureAsHRESULT = v13;
  }
LABEL_24:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18004d448  mov     [rsp-8+arg_8], rbx
0x18004d44d  mov     [rsp-8+arg_10], rsi
0x18004d452  push    rbp
0x18004d453  push    rdi
0x18004d454  push    r12
0x18004d456  lea     rbp, [rsp-47h]
0x18004d45b  sub     rsp, 90h
0x18004d462  mov     rsi, r8
0x18004d465  mov     rdi, rdx
0x18004d468  mov     rbx, rcx
0x18004d46b  mov     r9d, 1; unsigned __int16
0x18004d471  mov     r8d, 92Eh; unsigned __int16
0x18004d477  lea     rdx, aCsdcommonimplS_0; "CSdCommonImpl::_SetupStagingArea"
0x18004d47e  lea     rcx, [rbp+57h+var_48]; this
0x18004d482  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004d487  mov     [rbp+57h+SecurityDescriptor], 0
0x18004d48f  mov     [rbp+57h+SecurityDescriptorSize], 0
0x18004d496  xorps   xmm0, xmm0
0x18004d499  xor     eax, eax
0x18004d49b  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18004d49f  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18004d4a3  mov     eax, 933h
0x18004d4a8  test    rbx, rbx
0x18004d4ab  jnz     short loc_18004D4BE
0x18004d4ad  mov     ebx, 80070057h
0x18004d4b2  mov     [rbp+57h+var_48], ebx
0x18004d4b5  mov     [rbp+57h+var_42], ax
0x18004d4b9  jmp     loc_18004D6AF
0x18004d4be  mov     [rbp+57h+var_44], ax
0x18004d4c2  mov     eax, 934h
0x18004d4c7  test    rdi, rdi
0x18004d4ca  jz      short loc_18004D4AD
0x18004d4cc  mov     [rbp+57h+var_48], 0
0x18004d4d3  mov     [rbp+57h+var_44], ax
0x18004d4d7  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18004d4db  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18004d4df  mov     edx, 1; StringSDRevision
0x18004d4e4  lea     r12, c_wszSVISubDirSecurity; "D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x18004d4eb  mov     rcx, r12; StringSecurityDescriptor
0x18004d4ee  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d4f4  test    eax, eax
0x18004d4f6  jnz     short loc_18004D510
0x18004d4f8  call    GetLastFailureAsHRESULT
0x18004d4fd  mov     ebx, eax
0x18004d4ff  mov     [rbp+57h+var_48], eax
0x18004d502  mov     eax, 937h
0x18004d507  mov     [rbp+57h+var_42], ax
0x18004d50b  jmp     loc_18004D695
0x18004d510  mov     [rbp+57h+var_48], 0
0x18004d517  mov     eax, 937h
0x18004d51c  mov     [rbp+57h+var_44], ax
0x18004d520  mov     rdx, rdi; struct CBsString *
0x18004d523  mov     rcx, rbx; this
0x18004d526  call    ?_GetRootStagingPath@CSdCommonImpl@@CAJPEAVCBsString@@0@Z; CSdCommonImpl::_GetRootStagingPath(CBsString *,CBsString *)
0x18004d52b  mov     ebx, eax
0x18004d52d  mov     [rbp+57h+var_48], eax
0x18004d530  test    eax, eax
0x18004d532  mov     eax, 939h
0x18004d537  js      short loc_18004D507
0x18004d539  mov     [rbp+57h+var_44], ax
0x18004d53d  lea     r8, Str; "\\"
0x18004d544  mov     rdx, [rsi]; unsigned __int16 *
0x18004d547  mov     rcx, rdi; this
0x18004d54a  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x18004d54f  mov     ebx, eax
0x18004d551  mov     [rbp+57h+var_48], eax
0x18004d554  test    eax, eax
0x18004d556  mov     eax, 93Ah
0x18004d55b  js      short loc_18004D507
0x18004d55d  mov     [rbp+57h+var_44], ax
0x18004d561  lea     rsi, WPP_GLOBAL_Control
0x18004d568  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d56f  cmp     rcx, rsi
0x18004d572  jz      short loc_18004D592
0x18004d574  test    byte ptr [rcx+1Ch], 2
0x18004d578  jz      short loc_18004D592
0x18004d57a  mov     edx, 2Ch ; ','
0x18004d57f  mov     r9, [rdi]
0x18004d582  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004d589  mov     rcx, [rcx+10h]
0x18004d58d  call    WPP_SF_S
0x18004d592  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18004d599  mov     rax, [rbp+57h+SecurityDescriptor]
0x18004d59d  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18004d5a1  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18004d5a8  xor     r9d, r9d; int
0x18004d5ab  xor     r8d, r8d; int
0x18004d5ae  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18004d5b2  mov     rcx, [rdi]; unsigned __int16 *
0x18004d5b5  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x18004d5ba  mov     ebx, eax
0x18004d5bc  mov     [rbp+57h+var_48], eax
0x18004d5bf  test    eax, eax
0x18004d5c1  mov     eax, 942h
0x18004d5c6  jns     short loc_18004D616
0x18004d5c8  mov     [rbp+57h+var_42], ax
0x18004d5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5d3  cmp     rcx, rsi
0x18004d5d6  jz      loc_18004D695
0x18004d5dc  test    dword ptr [rcx+1Ch], 2000000h
0x18004d5e3  jz      loc_18004D695
0x18004d5e9  mov     edx, 2Dh ; '-'
0x18004d5ee  mov     dword ptr [rsp+0A0h+var_78], ebx
0x18004d5f2  mov     rax, [rdi]
0x18004d5f5  mov     [rsp+0A0h+var_80], rax
0x18004d5fa  lea     r9, aEnsuredirector; "EnsureDirectoryExists( *pstrFullStaging"...
0x18004d601  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004d608  mov     rcx, [rcx+10h]
0x18004d60c  call    WPP_SF_sSd
0x18004d611  mov     ebx, [rbp+57h+var_48]
0x18004d614  jmp     short loc_18004D695
0x18004d616  mov     [rbp+57h+var_44], ax
0x18004d61a  mov     r8, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004d61e  mov     edx, 4; SecurityInformation
0x18004d623  mov     rcx, [rdi]; lpFileName
0x18004d626  call    cs:__imp_SetFileSecurityW
0x18004d62c  test    eax, eax
0x18004d62e  jnz     short loc_18004D687
0x18004d630  call    GetLastFailureAsHRESULT
0x18004d635  mov     ebx, eax
0x18004d637  mov     [rbp+57h+var_48], eax
0x18004d63a  mov     eax, 945h
0x18004d63f  mov     [rbp+57h+var_42], ax
0x18004d643  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d64a  cmp     rcx, rsi
0x18004d64d  jz      short loc_18004D695
0x18004d64f  test    dword ptr [rcx+1Ch], 2000000h
0x18004d656  jz      short loc_18004D695
0x18004d658  mov     edx, 2Eh ; '.'
0x18004d65d  mov     dword ptr [rsp+0A0h+var_70], ebx; char
0x18004d661  mov     [rsp+0A0h+var_78], r12; __int64
0x18004d666  mov     rax, [rdi]
0x18004d669  mov     [rsp+0A0h+var_80], rax; __int64
0x18004d66e  lea     r9, aSetfilesecurit; "::SetFileSecurity( *pstrFullStagingPath"...
0x18004d675  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004d67c  mov     rcx, [rcx+10h]; LoggerHandle
0x18004d680  call    WPP_SF_sSSd
0x18004d685  jmp     short loc_18004D611
0x18004d687  xor     ebx, ebx
0x18004d689  mov     [rbp+57h+var_48], ebx
0x18004d68c  mov     eax, 945h
0x18004d691  mov     [rbp+57h+var_44], ax
0x18004d695  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18004d699  test    rcx, rcx
0x18004d69c  jz      short loc_18004D6AF
0x18004d69e  call    cs:__imp_LocalFree
0x18004d6a4  mov     [rbp+57h+SecurityDescriptor], 0
0x18004d6ac  mov     ebx, [rbp+57h+var_48]
0x18004d6af  lea     rcx, [rbp+57h+var_48]; this
0x18004d6b3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004d6b8  mov     eax, ebx
0x18004d6ba  lea     r11, [rsp+0A0h+var_10]
0x18004d6c2  mov     rbx, [r11+28h]
0x18004d6c6  mov     rsi, [r11+30h]
0x18004d6ca  mov     rsp, r11
0x18004d6cd  pop     r12
0x18004d6cf  pop     rdi
0x18004d6d0  pop     rbp
0x18004d6d1  retn
```
