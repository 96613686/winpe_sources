# CSdCommonImpl::_SetupStagingArea(CBsString *,CBsString *,CBsString *)

- ea: `0x18004f1c8`
- end: `0x18004f468`
- name: `?_SetupStagingArea@CSdCommonImpl@@CAJPEAVCBsString@@00@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct CBsString *this, struct CBsString *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004a300`

## callees

- `0x1800083e4`
- `0x180014eac`
- `0x18004e104`
- `0x18004f1c8`
- `0x18004fd38`
- `0x180072e08`
- `0x180072f14`
- `0x180089b20`
- `0x1800935fc`
- `0x18009dd0c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004f42d`
- `KERNEL32!LocalFree` at `0x18004f42d`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18004f3af`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18004f3af`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004f26e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004f26e`

## string_xrefs

- `0x18004f1f7`: `CSdCommonImpl::_SetupStagingArea`
- `0x18004f380`: `EnsureDirectoryExists( *pstrFullStagingPath, &sa, FALSE, FALSE )`
- `0x18004f3fd`: `::SetFileSecurity( *pstrFullStagingPath, DACL_SECURITY_INFORMATION, pSD)`

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
0x18004f1c8  mov     [rsp-8+arg_8], rbx
0x18004f1cd  mov     [rsp-8+arg_10], rsi
0x18004f1d2  push    rbp
0x18004f1d3  push    rdi
0x18004f1d4  push    r12
0x18004f1d6  lea     rbp, [rsp-47h]
0x18004f1db  sub     rsp, 90h
0x18004f1e2  mov     rsi, r8
0x18004f1e5  mov     rdi, rdx
0x18004f1e8  mov     rbx, rcx
0x18004f1eb  mov     r9d, 1; unsigned __int16
0x18004f1f1  mov     r8d, 92Eh; unsigned __int16
0x18004f1f7  lea     rdx, aCsdcommonimplS_0; "CSdCommonImpl::_SetupStagingArea"
0x18004f1fe  lea     rcx, [rbp+57h+var_48]; this
0x18004f202  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004f207  mov     [rbp+57h+SecurityDescriptor], 0
0x18004f20f  mov     [rbp+57h+SecurityDescriptorSize], 0
0x18004f216  xorps   xmm0, xmm0
0x18004f219  xor     eax, eax
0x18004f21b  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18004f21f  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18004f223  mov     eax, 933h
0x18004f228  test    rbx, rbx
0x18004f22b  jnz     short loc_18004F23E
0x18004f22d  mov     ebx, 80070057h
0x18004f232  mov     [rbp+57h+var_48], ebx
0x18004f235  mov     [rbp+57h+var_42], ax
0x18004f239  jmp     loc_18004F444
0x18004f23e  mov     [rbp+57h+var_44], ax
0x18004f242  mov     eax, 934h
0x18004f247  test    rdi, rdi
0x18004f24a  jz      short loc_18004F22D
0x18004f24c  mov     [rbp+57h+var_48], 0
0x18004f253  mov     [rbp+57h+var_44], ax
0x18004f257  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18004f25b  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18004f25f  mov     edx, 1; StringSDRevision
0x18004f264  lea     r12, c_wszSVISubDirSecurity; "D:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x18004f26b  mov     rcx, r12; StringSecurityDescriptor
0x18004f26e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004f275  nop     dword ptr [rax+rax+00h]
0x18004f27a  test    eax, eax
0x18004f27c  jnz     short loc_18004F296
0x18004f27e  call    GetLastFailureAsHRESULT
0x18004f283  mov     ebx, eax
0x18004f285  mov     [rbp+57h+var_48], eax
0x18004f288  mov     eax, 937h
0x18004f28d  mov     [rbp+57h+var_42], ax
0x18004f291  jmp     loc_18004F424
0x18004f296  mov     [rbp+57h+var_48], 0
0x18004f29d  mov     eax, 937h
0x18004f2a2  mov     [rbp+57h+var_44], ax
0x18004f2a6  mov     rdx, rdi; struct CBsString *
0x18004f2a9  mov     rcx, rbx; this
0x18004f2ac  call    ?_GetRootStagingPath@CSdCommonImpl@@CAJPEAVCBsString@@0@Z; CSdCommonImpl::_GetRootStagingPath(CBsString *,CBsString *)
0x18004f2b1  mov     ebx, eax
0x18004f2b3  mov     [rbp+57h+var_48], eax
0x18004f2b6  test    eax, eax
0x18004f2b8  mov     eax, 939h
0x18004f2bd  js      short loc_18004F28D
0x18004f2bf  mov     [rbp+57h+var_44], ax
0x18004f2c3  lea     r8, Str; "\\"
0x18004f2ca  mov     rdx, [rsi]; unsigned __int16 *
0x18004f2cd  mov     rcx, rdi; this
0x18004f2d0  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x18004f2d5  mov     ebx, eax
0x18004f2d7  mov     [rbp+57h+var_48], eax
0x18004f2da  test    eax, eax
0x18004f2dc  mov     eax, 93Ah
0x18004f2e1  js      short loc_18004F28D
0x18004f2e3  mov     [rbp+57h+var_44], ax
0x18004f2e7  lea     rsi, WPP_GLOBAL_Control
0x18004f2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f2f5  cmp     rcx, rsi
0x18004f2f8  jz      short loc_18004F318
0x18004f2fa  test    byte ptr [rcx+1Ch], 2
0x18004f2fe  jz      short loc_18004F318
0x18004f300  mov     edx, 2Ch ; ','
0x18004f305  mov     r9, [rdi]
0x18004f308  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004f30f  mov     rcx, [rcx+10h]
0x18004f313  call    WPP_SF_S
0x18004f318  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18004f31f  mov     rax, [rbp+57h+SecurityDescriptor]
0x18004f323  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18004f327  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18004f32e  xor     r9d, r9d; int
0x18004f331  xor     r8d, r8d; int
0x18004f334  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18004f338  mov     rcx, [rdi]; unsigned __int16 *
0x18004f33b  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x18004f340  mov     ebx, eax
0x18004f342  mov     [rbp+57h+var_48], eax
0x18004f345  test    eax, eax
0x18004f347  mov     eax, 942h
0x18004f34c  jns     short loc_18004F39F
0x18004f34e  mov     [rbp+57h+var_42], ax
0x18004f352  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f359  cmp     rcx, rsi
0x18004f35c  jz      loc_18004F424
0x18004f362  test    dword ptr [rcx+1Ch], 2000000h
0x18004f369  jz      loc_18004F424
0x18004f36f  mov     edx, 2Dh ; '-'
0x18004f374  mov     dword ptr [rsp+0A0h+var_78], ebx
0x18004f378  mov     rax, [rdi]
0x18004f37b  mov     [rsp+0A0h+var_80], rax
0x18004f380  lea     r9, aEnsuredirector; "EnsureDirectoryExists( *pstrFullStaging"...
0x18004f387  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004f38e  mov     rcx, [rcx+10h]
0x18004f392  call    WPP_SF_sSd
0x18004f397  mov     ebx, [rbp+57h+var_48]
0x18004f39a  jmp     loc_18004F424
0x18004f39f  mov     [rbp+57h+var_44], ax
0x18004f3a3  mov     r8, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004f3a7  mov     edx, 4; SecurityInformation
0x18004f3ac  mov     rcx, [rdi]; lpFileName
0x18004f3af  call    cs:__imp_SetFileSecurityW
0x18004f3b6  nop     dword ptr [rax+rax+00h]
0x18004f3bb  test    eax, eax
0x18004f3bd  jnz     short loc_18004F416
0x18004f3bf  call    GetLastFailureAsHRESULT
0x18004f3c4  mov     ebx, eax
0x18004f3c6  mov     [rbp+57h+var_48], eax
0x18004f3c9  mov     eax, 945h
0x18004f3ce  mov     [rbp+57h+var_42], ax
0x18004f3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f3d9  cmp     rcx, rsi
0x18004f3dc  jz      short loc_18004F424
0x18004f3de  test    dword ptr [rcx+1Ch], 2000000h
0x18004f3e5  jz      short loc_18004F424
0x18004f3e7  mov     edx, 2Eh ; '.'
0x18004f3ec  mov     dword ptr [rsp+0A0h+var_70], ebx; char
0x18004f3f0  mov     [rsp+0A0h+var_78], r12; __int64
0x18004f3f5  mov     rax, [rdi]
0x18004f3f8  mov     [rsp+0A0h+var_80], rax; __int64
0x18004f3fd  lea     r9, aSetfilesecurit; "::SetFileSecurity( *pstrFullStagingPath"...
0x18004f404  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004f40b  mov     rcx, [rcx+10h]; LoggerHandle
0x18004f40f  call    WPP_SF_sSSd
0x18004f414  jmp     short loc_18004F397
0x18004f416  xor     ebx, ebx
0x18004f418  mov     [rbp+57h+var_48], ebx
0x18004f41b  mov     eax, 945h
0x18004f420  mov     [rbp+57h+var_44], ax
0x18004f424  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18004f428  test    rcx, rcx
0x18004f42b  jz      short loc_18004F444
0x18004f42d  call    cs:__imp_LocalFree
0x18004f434  nop     dword ptr [rax+rax+00h]
0x18004f439  mov     [rbp+57h+SecurityDescriptor], 0
0x18004f441  mov     ebx, [rbp+57h+var_48]
0x18004f444  lea     rcx, [rbp+57h+var_48]; this
0x18004f448  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004f44d  mov     eax, ebx
0x18004f44f  lea     r11, [rsp+0A0h+var_10]
0x18004f457  mov     rbx, [r11+28h]
0x18004f45b  mov     rsi, [r11+30h]
0x18004f45f  mov     rsp, r11
0x18004f462  pop     r12
0x18004f464  pop     rdi
0x18004f465  pop     rbp
0x18004f466  retn
```
