# Pca::MergeSdb::Utils::CopyAclsFromParentDir(ushort *)

- ea: `0x14002a044`
- end: `0x14002a1a3`
- name: `?CopyAclsFromParentDir@Utils@MergeSdb@Pca@@YAKPEAG@Z`
- size: `351`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140024958`
- `0x14002ce68`

## callees

- `0x14001008c`
- `0x140020f9c`
- `0x14002a044`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x14002a0f6`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x14002a0f6`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14002a13c`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14002a13c`
- `KERNEL32!LocalFree` at `0x14002a171`
- `KERNEL32!LocalFree` at `0x14002a171`
- `KERNEL32!GetProcessHeap` at `0x14002a17d`
- `KERNEL32!GetProcessHeap` at `0x14002a17d`
- `KERNEL32!HeapFree` at `0x14002a18b`
- `KERNEL32!HeapFree` at `0x14002a18b`
- `msvcrt!wcsrchr` at `0x14002a063`
- `msvcrt!wcsrchr` at `0x14002a063`

## string_xrefs

- `0x14002a159`: `Pca::MergeSdb::Utils::CopyAclsFromParentDir`
- `0x14002a102`: `Unable to get security info (%d)`
- `0x14002a148`: `Unable to set security info (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::CopyAclsFromParentDir(LPWSTR pObjectName, unsigned __int16 *a2)
{
  WCHAR *v3; // rbx
  wchar_t *v4; // rax
  unsigned int v5; // edi
  WCHAR *v6; // rsi
  DWORD NamedSecurityInfoW; // eax
  const char *v8; // r9
  __int64 v9; // r8
  HANDLE ProcessHeap; // rax
  PSID *ppsidGroup; // [rsp+20h] [rbp-40h]
  PSID ppsidOwner; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR pObjectNamea[2]; // [rsp+50h] [rbp-10h] BYREF
  PACL pSacl; // [rsp+88h] [rbp+28h] BYREF
  PACL pDacl; // [rsp+90h] [rbp+30h] BYREF
  PSID psidGroup; // [rsp+98h] [rbp+38h] BYREF

  hMem = 0;
  v3 = 0;
  v4 = wcsrchr(pObjectName, 0x5Cu);
  if ( !v4 )
  {
    v5 = 87;
    v6 = 0;
    goto LABEL_11;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    pObjectNamea,
    pObjectName,
    v4 - pObjectName);
  v3 = (WCHAR *)pObjectNamea[0];
  if ( pObjectNamea[0] )
  {
    ppsidOwner = 0;
    psidGroup = 0;
    pDacl = 0;
    pSacl = 0;
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           pObjectNamea[0],
                           SE_FILE_OBJECT,
                           7u,
                           &ppsidOwner,
                           &psidGroup,
                           &pDacl,
                           &pSacl,
                           &hMem);
    v5 = NamedSecurityInfoW;
    if ( NamedSecurityInfoW )
    {
      v8 = "Unable to get security info (%d)";
      v9 = 3387;
    }
    else
    {
      NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, ppsidOwner, psidGroup, pDacl, pSacl);
      v5 = NamedSecurityInfoW;
      if ( !NamedSecurityInfoW )
        goto LABEL_10;
      v8 = "Unable to set security info (%d)";
      v9 = 3403;
    }
    LODWORD(ppsidGroup) = NamedSecurityInfoW;
    AslLogCallPrintf(1, "Pca::MergeSdb::Utils::CopyAclsFromParentDir", v9, v8, ppsidGroup);
    goto LABEL_10;
  }
  v5 = 14;
LABEL_10:
  v6 = v3;
LABEL_11:
  LocalFree(hMem);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  return v5;
}

```

## disassembly

```asm
0x14002a044  mov     [rsp-18h+arg_0], rbx
0x14002a049  push    rbp
0x14002a04a  push    rsi
0x14002a04b  push    rdi
0x14002a04c  mov     rbp, rsp
0x14002a04f  sub     rsp, 60h
0x14002a053  mov     rsi, rcx
0x14002a056  mov     [rbp+hMem], 0
0x14002a05e  xor     ebx, ebx
0x14002a060  lea     edx, [rbx+5Ch]; Ch
0x14002a063  call    cs:__imp_wcsrchr
0x14002a069  test    rax, rax
0x14002a06c  jnz     short loc_14002A078
0x14002a06e  lea     edi, [rbx+57h]
0x14002a071  xor     esi, esi
0x14002a073  jmp     loc_14002A16D
0x14002a078  sub     rax, rsi
0x14002a07b  sar     rax, 1
0x14002a07e  mov     r8, rax
0x14002a081  mov     rdx, rsi
0x14002a084  lea     rcx, [rbp+pObjectName]
0x14002a088  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002a08d  mov     rbx, [rbp+pObjectName]
0x14002a091  mov     [rbp+pObjectName], rbx
0x14002a095  test    rbx, rbx
0x14002a098  jnz     short loc_14002A0A2
0x14002a09a  lea     edi, [rbx+0Eh]
0x14002a09d  jmp     loc_14002A16A
0x14002a0a2  mov     [rbp+ppsidOwner], 0
0x14002a0aa  mov     [rbp+psidGroup], 0
0x14002a0b2  mov     [rbp+pDacl], 0
0x14002a0ba  mov     [rbp+pSacl], 0
0x14002a0c2  lea     rax, [rbp+hMem]
0x14002a0c6  mov     [rsp+60h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x14002a0cb  lea     rax, [rbp+pSacl]
0x14002a0cf  mov     [rsp+60h+ppSacl], rax; ppSacl
0x14002a0d4  lea     rax, [rbp+pDacl]
0x14002a0d8  mov     [rsp+60h+ppDacl], rax; ppDacl
0x14002a0dd  lea     rax, [rbp+psidGroup]
0x14002a0e1  mov     [rsp+60h+ppsidGroup], rax; ppsidGroup
0x14002a0e6  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x14002a0ea  mov     edx, 1; ObjectType
0x14002a0ef  lea     r8d, [rdx+6]; SecurityInfo
0x14002a0f3  mov     rcx, rbx; pObjectName
0x14002a0f6  call    cs:__imp_GetNamedSecurityInfoW
0x14002a0fc  mov     edi, eax
0x14002a0fe  test    eax, eax
0x14002a100  jz      short loc_14002A111
0x14002a102  lea     r9, aUnableToGetSec; "Unable to get security info (%d)"
0x14002a109  mov     r8d, 0D3Bh
0x14002a10f  jmp     short loc_14002A155
0x14002a111  mov     rax, [rbp+pSacl]
0x14002a115  mov     [rsp+60h+ppSacl], rax; pSacl
0x14002a11a  mov     rax, [rbp+pDacl]
0x14002a11e  mov     [rsp+60h+ppDacl], rax; pDacl
0x14002a123  mov     rax, [rbp+psidGroup]
0x14002a127  mov     [rsp+60h+ppsidGroup], rax; psidGroup
0x14002a12c  mov     r9, [rbp+ppsidOwner]; psidOwner
0x14002a130  mov     edx, 1; ObjectType
0x14002a135  lea     r8d, [rdx+3]; SecurityInfo
0x14002a139  mov     rcx, rsi; pObjectName
0x14002a13c  call    cs:__imp_SetNamedSecurityInfoW
0x14002a142  mov     edi, eax
0x14002a144  test    eax, eax
0x14002a146  jz      short loc_14002A16A
0x14002a148  lea     r9, aUnableToSetSec; "Unable to set security info (%d)"
0x14002a14f  mov     r8d, 0D4Bh
0x14002a155  mov     dword ptr [rsp+60h+ppsidGroup], eax
0x14002a159  lea     rdx, aPcaMergesdbUti; "Pca::MergeSdb::Utils::CopyAclsFromParen"...
0x14002a160  mov     ecx, 1
0x14002a165  call    AslLogCallPrintf
0x14002a16a  mov     rsi, rbx
0x14002a16d  mov     rcx, [rbp+hMem]; hMem
0x14002a171  call    cs:__imp_LocalFree
0x14002a177  nop
0x14002a178  test    rsi, rsi
0x14002a17b  jz      short loc_14002A191
0x14002a17d  call    cs:__imp_GetProcessHeap
0x14002a183  mov     rcx, rax; hHeap
0x14002a186  mov     r8, rbx; lpMem
0x14002a189  xor     edx, edx; dwFlags
0x14002a18b  call    cs:__imp_HeapFree
0x14002a191  mov     eax, edi
0x14002a193  mov     rbx, [rsp+60h+arg_0]
0x14002a19b  add     rsp, 60h
0x14002a19f  pop     rdi
0x14002a1a0  pop     rsi
0x14002a1a1  pop     rbp
0x14002a1a2  retn
```
