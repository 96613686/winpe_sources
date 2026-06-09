# CreateWellKnownSids(void)

- ea: `0x18005096c`
- end: `0x180050b16`
- name: `?CreateWellKnownSids@@YAKXZ`
- size: `426`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050c60`

## callees

- `0x18004f008`
- `0x18005096c`
- `0x180050b1c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180050aba`
- `KERNEL32!LocalFree` at `0x180050ace`
- `KERNEL32!LocalFree` at `0x180050ae8`
- `KERNEL32!LocalFree` at `0x180050afc`
- `KERNEL32!LocalFree` at `0x180050aba`
- `KERNEL32!LocalFree` at `0x180050ace`
- `KERNEL32!LocalFree` at `0x180050ae8`
- `KERNEL32!LocalFree` at `0x180050afc`
- `KERNEL32!LocalAlloc` at `0x18005099e`
- `KERNEL32!LocalAlloc` at `0x180050a78`
- `KERNEL32!LocalAlloc` at `0x18005099e`
- `KERNEL32!LocalAlloc` at `0x180050a78`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800509c1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800509c1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050aa0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050aa0`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180050991`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180050991`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800509dc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800509dc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050a6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050a92`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050a6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050a92`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x180050a5e`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x180050a5e`

## pseudocode

```c
unsigned int CreateWellKnownSids(void)
{
  __int64 v0; // rdi
  _QWORD *v1; // rbx
  DWORD SidLengthRequired; // eax
  HLOCAL v3; // rax
  int v4; // ebx
  PDWORD SidSubAuthority; // rax
  void *v6; // rcx
  unsigned int v7; // ebx
  unsigned int result; // eax
  __int64 v9; // rdx
  DWORD LengthSid; // eax
  HLOCAL v11; // rdi
  PSID v12; // rbx
  DWORD v13; // eax
  HLOCAL *v14; // rax
  __int64 i; // rbx
  HLOCAL *v16; // rax
  __int64 j; // rbx
  unsigned int v18; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+68h] [rbp+38h] BYREF
  HLOCAL v20; // [rsp+70h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+48h] BYREF

  v0 = 0;
  do
  {
    v1 = (_QWORD *)*((_QWORD *)&SidData.Revision + 3 * v0);
    SidLengthRequired = GetSidLengthRequired(1u);
    v3 = LocalAlloc(0x40u, SidLengthRequired);
    *v1 = v3;
    if ( !v3 )
      return 8;
    InitializeSid(v3, (PSID_IDENTIFIER_AUTHORITY)&SidData.SubAuthority[6 * v0], 1u);
    v4 = dword_1800AE340[6 * v0];
    SidSubAuthority = GetSidSubAuthority(**((PSID **)&SidData.Revision + 3 * v0), 0);
    v0 = (unsigned int)(v0 + 1);
    *SidSubAuthority = v4;
  }
  while ( (unsigned int)v0 < 6 );
  v7 = 0;
  while ( 1 )
  {
    result = DomainIdToSid(v6, dword_1800AE3C8[4 * v7], (&off_1800AE3C0)[2 * v7]);
    if ( result )
      break;
    if ( ++v7 >= 9 )
    {
      LOBYTE(v9) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
        v9);
      hMem = 0;
      v18 = 0;
      v20 = 0;
      v19 = 0;
      DeriveCapabilitySidsFromName(L"isolatedWin32-scanner", &hMem, &v18, &v20, &v19);
      LengthSid = GetLengthSid(*(PSID *)v20);
      v11 = LocalAlloc(0x40u, LengthSid);
      psidScanner = v11;
      v12 = *(PSID *)v20;
      v13 = GetLengthSid(*(PSID *)v20);
      CopySid(v13, v11, v12);
      v14 = (HLOCAL *)hMem;
      if ( hMem )
      {
        for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
        {
          LocalFree(v14[i]);
          v14 = (HLOCAL *)hMem;
        }
        LocalFree(v14);
      }
      v16 = (HLOCAL *)v20;
      if ( v20 )
      {
        for ( j = 0; (unsigned int)j < v19; j = (unsigned int)(j + 1) )
        {
          LocalFree(v16[j]);
          v16 = (HLOCAL *)v20;
        }
        LocalFree(v16);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005096c  push    rbp
0x18005096e  push    rbx
0x18005096f  push    rsi
0x180050970  push    rdi
0x180050971  push    r15
0x180050973  mov     rbp, rsp
0x180050976  sub     rsp, 30h
0x18005097a  xor     edi, edi
0x18005097c  lea     r15, __ImageBase
0x180050983  lea     rsi, [rdi+rdi*2]
0x180050987  mov     cl, 1; nSubAuthorityCount
0x180050989  mov     rbx, qword ptr rva ?SidData@@3PAU_SID_DATA@@A.Revision[r15+rsi*8]; _SID_DATA near * SidData ...
0x180050991  call    cs:__imp_GetSidLengthRequired
0x180050997  mov     edx, eax; uBytes
0x180050999  mov     ecx, 40h ; '@'; uFlags
0x18005099e  call    cs:__imp_LocalAlloc
0x1800509a4  mov     [rbx], rax
0x1800509a7  test    rax, rax
0x1800509aa  jz      loc_180050B06
0x1800509b0  lea     rdx, rva ?SidData@@3PAU_SID_DATA@@A.SubAuthority[r15]; _SID_DATA near * SidData ...
0x1800509b7  mov     r8b, 1; nSubAuthorityCount
0x1800509ba  lea     rdx, [rdx+rsi*8]; pIdentifierAuthority
0x1800509be  mov     rcx, rax; Sid
0x1800509c1  call    cs:__imp_InitializeSid
0x1800509c7  mov     rcx, qword ptr rva ?SidData@@3PAU_SID_DATA@@A.Revision[r15+rsi*8]; _SID_DATA near * SidData ...
0x1800509cf  xor     edx, edx; nSubAuthority
0x1800509d1  mov     ebx, rva dword_1800AE340[r15+rsi*8]
0x1800509d9  mov     rcx, [rcx]; pSid
0x1800509dc  call    cs:__imp_GetSidSubAuthority
0x1800509e2  inc     edi
0x1800509e4  mov     [rax], ebx
0x1800509e6  cmp     edi, 6
0x1800509e9  jb      short loc_180050983
0x1800509eb  xor     ebx, ebx
0x1800509ed  mov     edx, ebx
0x1800509ef  add     rdx, rdx
0x1800509f2  mov     r8, rva off_1800AE3C0[r15+rdx*8]; void **
0x1800509fa  mov     edx, rva dword_1800AE3C8[r15+rdx*8]; unsigned int
0x180050a02  call    ?DomainIdToSid@@YAKPEAXKPEAPEAX@Z; DomainIdToSid(void *,ulong,void * *)
0x180050a07  test    eax, eax
0x180050a09  jnz     loc_180050B0B
0x180050a0f  inc     ebx
0x180050a11  cmp     ebx, 9
0x180050a14  jb      short loc_1800509ED
0x180050a16  mov     dl, 1
0x180050a18  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x180050a1f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180050a24  lea     rax, [rbp+arg_8]
0x180050a28  mov     [rbp+hMem], 0
0x180050a30  lea     r9, [rbp+arg_10]
0x180050a34  mov     [rsp+30h+var_10], rax
0x180050a39  lea     r8, [rbp+arg_0]
0x180050a3d  mov     [rbp+arg_0], 0
0x180050a44  lea     rdx, [rbp+hMem]
0x180050a48  mov     [rbp+arg_10], 0
0x180050a50  lea     rcx, aIsolatedwin32S; "isolatedWin32-scanner"
0x180050a57  mov     [rbp+arg_8], 0
0x180050a5e  call    cs:__imp_DeriveCapabilitySidsFromName
0x180050a64  mov     rcx, [rbp+arg_10]
0x180050a68  mov     rcx, [rcx]; pSid
0x180050a6b  call    cs:__imp_GetLengthSid
0x180050a71  mov     edx, eax; uBytes
0x180050a73  mov     ecx, 40h ; '@'; uFlags
0x180050a78  call    cs:__imp_LocalAlloc
0x180050a7e  mov     rcx, [rbp+arg_10]
0x180050a82  mov     rdi, rax
0x180050a85  mov     cs:?psidScanner@@3PEAXEA, rax; void * psidScanner
0x180050a8c  mov     rbx, [rcx]
0x180050a8f  mov     rcx, rbx; pSid
0x180050a92  call    cs:__imp_GetLengthSid
0x180050a98  mov     r8, rbx; pSourceSid
0x180050a9b  mov     rdx, rdi; pDestinationSid
0x180050a9e  mov     ecx, eax; nDestinationSidLength
0x180050aa0  call    cs:__imp_CopySid
0x180050aa6  mov     rax, [rbp+hMem]
0x180050aaa  test    rax, rax
0x180050aad  jz      short loc_180050AD4
0x180050aaf  xor     ebx, ebx
0x180050ab1  cmp     [rbp+arg_0], ebx
0x180050ab4  jbe     short loc_180050ACB
0x180050ab6  mov     rcx, [rax+rbx*8]; hMem
0x180050aba  call    cs:__imp_LocalFree
0x180050ac0  mov     rax, [rbp+hMem]
0x180050ac4  inc     ebx
0x180050ac6  cmp     ebx, [rbp+arg_0]
0x180050ac9  jb      short loc_180050AB6
0x180050acb  mov     rcx, rax; hMem
0x180050ace  call    cs:__imp_LocalFree
0x180050ad4  mov     rax, [rbp+arg_10]
0x180050ad8  test    rax, rax
0x180050adb  jz      short loc_180050B02
0x180050add  xor     ebx, ebx
0x180050adf  cmp     [rbp+arg_8], ebx
0x180050ae2  jbe     short loc_180050AF9
0x180050ae4  mov     rcx, [rax+rbx*8]; hMem
0x180050ae8  call    cs:__imp_LocalFree
0x180050aee  mov     rax, [rbp+arg_10]
0x180050af2  inc     ebx
0x180050af4  cmp     ebx, [rbp+arg_8]
0x180050af7  jb      short loc_180050AE4
0x180050af9  mov     rcx, rax; hMem
0x180050afc  call    cs:__imp_LocalFree
0x180050b02  xor     eax, eax
0x180050b04  jmp     short loc_180050B0B
0x180050b06  mov     eax, 8
0x180050b0b  add     rsp, 30h
0x180050b0f  pop     r15
0x180050b11  pop     rdi
0x180050b12  pop     rsi
0x180050b13  pop     rbx
0x180050b14  pop     rbp
0x180050b15  retn
```
