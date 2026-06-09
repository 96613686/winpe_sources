# GetReportLockHandle(void *,wchar_t *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18002091c`
- end: `0x180020dbd`
- name: `?GetReportLockHandle@@YAJPEAXPEA_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(HANDLE hTargetProcessHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a4cc`

## callees

- `0x1800029d0`
- `0x180006134`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x18002091c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020cf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d28`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180020c80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180020c80`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180020b94`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180020b94`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180020bf8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180020bf8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180020a12`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180020a78`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180020a12`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180020a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020991`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020991`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180020d1e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180020d1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020d8b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180020b38`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180020b38`

## pseudocode

```c
__int64 __fastcall GetReportLockHandle(HANDLE hTargetProcessHandle, __int64 a2, void **a3)
{
  char *v4; // rcx
  int v7; // eax
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  signed int LastError; // eax
  signed int v13; // eax
  HLOCAL v14; // rcx
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  HANDLE v18; // r15
  signed int v19; // eax
  HANDLE *v20; // rbx
  HANDLE CurrentProcess; // rax
  signed int v22; // eax
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pSecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+B0h] [rbp-50h]
  int v31; // [rsp+B4h] [rbp-4Ch]
  int v32; // [rsp+B8h] [rbp-48h]
  __int64 v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+D0h] [rbp-30h]
  _BYTE *v36; // [rsp+D8h] [rbp-28h]
  _BYTE pSid[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v38[80]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Name[64]; // [rsp+180h] [rbp+80h] BYREF

  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  v4 = (char *)*a3;
  v28 = 0;
  cbSid = 0;
  hMem = 0;
  *a3 = 0;
  *(_OWORD *)&MutexAttributes.nLength = 0;
  pSecurityDescriptor = 0;
  if ( v4 != (char *)-1LL && v4 + 1 != (char *)1 )
    CloseHandle(v4);
  *(_WORD *)(a2 + 126) = 0;
  v7 = StringCchPrintfW(Name, 0x40u, L"Global\\%s", a2);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 103;
      v11 = (unsigned int)v7;
LABEL_7:
      WPP_SF_d(v9[2], v10, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, v11);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinWorldSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 104;
    goto LABEL_16;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, v38, &cbSid) )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 105;
    goto LABEL_16;
  }
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  pListOfExplicitEntries.grfAccessPermissions = 270467073;
  pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  v35 = 5;
  v14 = hMem;
  *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
  v30 = 270467073;
  v31 = 1;
  v32 = 3;
  v33 = 0;
  v34 = 0;
  v36 = v38;
  hMem = 0;
  if ( v14 )
    LocalFree(v14);
  if ( SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, (PACL *)&hMem) )
  {
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 106;
    goto LABEL_16;
  }
  if ( !InitializeSecurityDescriptor(&pSecurityDescriptor, 1u) )
  {
    v16 = GetLastError();
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 107;
    goto LABEL_16;
  }
  if ( !SetSecurityDescriptorDacl(&pSecurityDescriptor, 1, (PACL)hMem, 0) )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v10 = 108;
LABEL_16:
    v11 = (unsigned int)v8;
    goto LABEL_7;
  }
  *(&MutexAttributes.bInheritHandle + 1) = 0;
  MutexAttributes.bInheritHandle = 0;
  *(&MutexAttributes.nLength + 1) = 0;
  MutexAttributes.nLength = 24;
  MutexAttributes.lpSecurityDescriptor = &pSecurityDescriptor;
  v18 = CreateMutexW(&MutexAttributes, 0, Name);
  if ( (unsigned __int64)v18 + 1 <= 1 )
  {
    v19 = GetLastError();
    v8 = v19;
    if ( v19 > 0 )
      v8 = (unsigned __int16)v19 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    if ( v8 != -2147024713 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_72;
      v10 = 110;
      goto LABEL_16;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
  }
  v20 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(a3);
  CurrentProcess = GetCurrentProcess();
  if ( DuplicateHandle(CurrentProcess, v18, hTargetProcessHandle, v20, 0x101F0001u, 0, 1u) )
  {
    v8 = 0;
    goto LABEL_72;
  }
  v22 = GetLastError();
  v8 = v22;
  if ( v22 > 0 )
    v8 = (unsigned __int16)v22 | 0x80070000;
  if ( v8 >= 0 )
    v8 = -2147467259;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 111;
    goto LABEL_16;
  }
LABEL_72:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002091c  mov     [rsp-8+arg_18], rbx
0x180020921  push    rbp
0x180020922  push    rsi
0x180020923  push    rdi
0x180020924  push    r12
0x180020926  push    r13
0x180020928  push    r14
0x18002092a  push    r15
0x18002092c  lea     rbp, [rsp-110h]
0x180020934  sub     rsp, 210h
0x18002093b  mov     rax, cs:__security_cookie
0x180020942  xor     rax, rsp
0x180020945  mov     [rbp+140h+var_40], rax
0x18002094c  xor     r13d, r13d
0x18002094f  xor     eax, eax
0x180020951  mov     r12, rcx
0x180020954  mov     qword ptr [rsp+240h+MutexAttributes.bInheritHandle], rax
0x180020959  mov     rcx, [r8]; hObject
0x18002095c  xorps   xmm0, xmm0
0x18002095f  mov     [rsp+240h+var_1C8], rax
0x180020964  xorps   xmm1, xmm1
0x180020967  lea     r15d, [r13+1]
0x18002096b  mov     [rsp+240h+cbSid], r13d
0x180020970  mov     r14, r8
0x180020973  mov     [rsp+240h+hMem], r13
0x180020978  lea     rax, [rcx+1]
0x18002097c  mov     [r8], r13
0x18002097f  mov     rbx, rdx
0x180020982  movups  xmmword ptr [rsp+240h+MutexAttributes.nLength], xmm0
0x180020987  movups  [rsp+240h+pSecurityDescriptor], xmm1
0x18002098c  cmp     rax, r15
0x18002098f  jbe     short loc_180020997
0x180020991  call    cs:__imp_CloseHandle
0x180020997  mov     r9, rbx
0x18002099a  mov     [rbx+7Eh], r13w
0x18002099f  lea     r8, aGlobalS
0x1800209a6  mov     edx, 40h ; '@'; unsigned __int64
0x1800209ab  lea     rcx, [rbp+140h+Name]; wchar_t *
0x1800209b2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ
0x1800209b7  mov     ebx, eax
0x1800209b9  test    eax, eax
0x1800209bb  jns     short loc_1800209FB
0x1800209bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209c4  lea     rdi, WPP_GLOBAL_Control
0x1800209cb  cmp     rcx, rdi
0x1800209ce  jz      loc_180020D81
0x1800209d4  test    [rcx+1Ch], r15b
0x1800209d8  jz      loc_180020D81
0x1800209de  mov     edx, 67h ; 'g'
0x1800209e3  mov     r9d, eax
0x1800209e6  mov     rcx, [rcx+10h]
0x1800209ea  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x1800209f1  call    WPP_SF_d
0x1800209f6  jmp     loc_180020D81
0x1800209fb  mov     ebx, 44h ; 'D'
0x180020a00  lea     r9, [rsp+240h+cbSid]; cbSid
0x180020a05  lea     r8, [rbp+140h+pSid]; pSid
0x180020a09  mov     [rsp+240h+cbSid], ebx
0x180020a0d  xor     edx, edx; DomainSid
0x180020a0f  mov     ecx, r15d; WellKnownSidType
0x180020a12  call    cs:__imp_CreateWellKnownSid
0x180020a18  test    eax, eax
0x180020a1a  jnz     short loc_180020A66
0x180020a1c  call    cs:__imp_GetLastError
0x180020a22  mov     ebx, eax
0x180020a24  test    eax, eax
0x180020a26  jle     short loc_180020A31
0x180020a28  movzx   ebx, ax
0x180020a2b  or      ebx, 80070000h
0x180020a31  test    ebx, ebx
0x180020a33  mov     esi, 80004005h
0x180020a38  cmovns  ebx, esi
0x180020a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a42  lea     rdi, WPP_GLOBAL_Control
0x180020a49  cmp     rcx, rdi
0x180020a4c  jz      loc_180020D81
0x180020a52  test    [rcx+1Ch], r15b
0x180020a56  jz      loc_180020D81
0x180020a5c  mov     edx, 68h ; 'h'
0x180020a61  mov     r9d, ebx
0x180020a64  jmp     short loc_1800209E6
0x180020a66  xor     edx, edx; DomainSid
0x180020a68  mov     [rsp+240h+cbSid], ebx
0x180020a6c  lea     r9, [rsp+240h+cbSid]; cbSid
0x180020a71  lea     r8, [rbp+140h+var_110]; pSid
0x180020a75  lea     ecx, [rdx+54h]; WellKnownSidType
0x180020a78  call    cs:__imp_CreateWellKnownSid
0x180020a7e  test    eax, eax
0x180020a80  jnz     short loc_180020AC9
0x180020a82  call    cs:__imp_GetLastError
0x180020a88  mov     ebx, eax
0x180020a8a  test    eax, eax
0x180020a8c  jle     short loc_180020A97
0x180020a8e  movzx   ebx, ax
0x180020a91  or      ebx, 80070000h
0x180020a97  test    ebx, ebx
0x180020a99  mov     esi, 80004005h
0x180020a9e  cmovns  ebx, esi
0x180020aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aa8  lea     rdi, WPP_GLOBAL_Control
0x180020aaf  cmp     rcx, rdi
0x180020ab2  jz      loc_180020D81
0x180020ab8  test    [rcx+1Ch], r15b
0x180020abc  jz      loc_180020D81
0x180020ac2  mov     edx, 69h ; 'i'
0x180020ac7  jmp     short loc_180020A61
0x180020ac9  mov     edx, 3
0x180020ace  mov     [rbp+140h+pListOfExplicitEntries.grfAccessMode], r15d
0x180020ad2  lea     rax, [rbp+140h+pSid]
0x180020ad6  mov     [rbp+140h+pListOfExplicitEntries.grfInheritance], edx
0x180020ad9  mov     r8d, 101F0001h
0x180020adf  mov     [rbp+140h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180020ae3  lea     rax, [rbp+140h+var_110]
0x180020ae7  mov     [rbp+140h+pListOfExplicitEntries.grfAccessPermissions], r8d
0x180020aeb  lea     ecx, [rdx+2]
0x180020aee  mov     [rbp+140h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r13
0x180020af2  mov     [rbp+140h+pListOfExplicitEntries.Trustee.TrusteeType], ecx
0x180020af5  mov     [rbp+140h+var_170], ecx
0x180020af8  mov     rcx, [rsp+240h+hMem]; hMem
0x180020afd  mov     qword ptr [rbp+140h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r13
0x180020b01  mov     [rbp+140h+var_190], r8d
0x180020b05  mov     [rbp+140h+var_18C], r15d
0x180020b09  mov     [rbp+140h+var_188], edx
0x180020b0c  mov     [rbp+140h+var_180], r13
0x180020b10  mov     [rbp+140h+var_178], r13
0x180020b14  mov     [rbp+140h+var_168], rax
0x180020b18  mov     [rsp+240h+hMem], r13
0x180020b1d  test    rcx, rcx
0x180020b20  jz      short loc_180020B28
0x180020b22  call    cs:__imp_LocalFree
0x180020b28  xor     r8d, r8d; OldAcl
0x180020b2b  lea     r9, [rsp+240h+hMem]; NewAcl
0x180020b30  lea     rdx, [rbp+140h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180020b34  lea     ecx, [r8+2]; cCountOfExplicitEntries
0x180020b38  call    cs:__imp_SetEntriesInAclW
0x180020b3e  test    eax, eax
0x180020b40  jz      short loc_180020B8C
0x180020b42  call    cs:__imp_GetLastError
0x180020b48  mov     ebx, eax
0x180020b4a  test    eax, eax
0x180020b4c  jle     short loc_180020B57
0x180020b4e  movzx   ebx, ax
0x180020b51  or      ebx, 80070000h
0x180020b57  test    ebx, ebx
0x180020b59  mov     esi, 80004005h
0x180020b5e  cmovns  ebx, esi
0x180020b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b68  lea     rdi, WPP_GLOBAL_Control
0x180020b6f  cmp     rcx, rdi
0x180020b72  jz      loc_180020D81
0x180020b78  test    [rcx+1Ch], r15b
0x180020b7c  jz      loc_180020D81
0x180020b82  mov     edx, 6Ah ; 'j'
0x180020b87  jmp     loc_180020A61
0x180020b8c  mov     edx, r15d; dwRevision
0x180020b8f  lea     rcx, [rsp+240h+pSecurityDescriptor]; pSecurityDescriptor
0x180020b94  call    cs:__imp_InitializeSecurityDescriptor
0x180020b9a  test    eax, eax
0x180020b9c  jnz     short loc_180020BE8
0x180020b9e  call    cs:__imp_GetLastError
0x180020ba4  mov     ebx, eax
0x180020ba6  test    eax, eax
0x180020ba8  jle     short loc_180020BB3
0x180020baa  movzx   ebx, ax
0x180020bad  or      ebx, 80070000h
0x180020bb3  test    ebx, ebx
0x180020bb5  mov     esi, 80004005h
0x180020bba  cmovns  ebx, esi
0x180020bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bc4  lea     rdi, WPP_GLOBAL_Control
0x180020bcb  cmp     rcx, rdi
0x180020bce  jz      loc_180020D81
0x180020bd4  test    [rcx+1Ch], r15b
0x180020bd8  jz      loc_180020D81
0x180020bde  mov     edx, 6Bh ; 'k'
0x180020be3  jmp     loc_180020A61
0x180020be8  mov     r8, [rsp+240h+hMem]; pDacl
0x180020bed  lea     rcx, [rsp+240h+pSecurityDescriptor]; pSecurityDescriptor
0x180020bf2  xor     r9d, r9d; bDaclDefaulted
0x180020bf5  mov     edx, r15d; bDaclPresent
0x180020bf8  call    cs:__imp_SetSecurityDescriptorDacl
0x180020bfe  test    eax, eax
0x180020c00  jnz     short loc_180020C4C
0x180020c02  call    cs:__imp_GetLastError
0x180020c08  mov     ebx, eax
0x180020c0a  test    eax, eax
0x180020c0c  jle     short loc_180020C17
0x180020c0e  movzx   ebx, ax
0x180020c11  or      ebx, 80070000h
0x180020c17  test    ebx, ebx
0x180020c19  mov     esi, 80004005h
0x180020c1e  cmovns  ebx, esi
0x180020c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c28  lea     rdi, WPP_GLOBAL_Control
0x180020c2f  cmp     rcx, rdi
0x180020c32  jz      loc_180020D81
0x180020c38  test    [rcx+1Ch], r15b
0x180020c3c  jz      loc_180020D81
0x180020c42  mov     edx, 6Ch ; 'l'
0x180020c47  jmp     loc_180020A61
0x180020c4c  xor     eax, eax
0x180020c4e  lea     r8, [rbp+140h+Name]; lpName
0x180020c55  mov     qword ptr [rsp+240h+MutexAttributes.bInheritHandle], rax
0x180020c5a  lea     rcx, [rsp+240h+MutexAttributes]; lpMutexAttributes
0x180020c5f  xorps   xmm0, xmm0
0x180020c62  mov     [rsp+240h+MutexAttributes.bInheritHandle], r13d
0x180020c67  movups  xmmword ptr [rsp+240h+MutexAttributes.nLength], xmm0
0x180020c6c  lea     rax, [rsp+240h+pSecurityDescriptor]
0x180020c71  mov     [rsp+240h+MutexAttributes.nLength], 18h
0x180020c79  xor     edx, edx; bInitialOwner
0x180020c7b  mov     [rsp+240h+MutexAttributes.lpSecurityDescriptor], rax
0x180020c80  call    cs:__imp_CreateMutexW
0x180020c86  lea     rdi, WPP_GLOBAL_Control
0x180020c8d  mov     esi, 80004005h
0x180020c92  mov     r15, rax
0x180020c95  lea     rcx, [rax+1]
0x180020c99  cmp     rcx, 1
0x180020c9d  ja      short loc_180020CEC
0x180020c9f  call    cs:__imp_GetLastError
0x180020ca5  mov     ebx, eax
0x180020ca7  test    eax, eax
0x180020ca9  jle     short loc_180020CB4
0x180020cab  movzx   ebx, ax
0x180020cae  or      ebx, 80070000h
0x180020cb4  test    ebx, ebx
0x180020cb6  cmovns  ebx, esi
0x180020cb9  cmp     ebx, 800700B7h
0x180020cbf  jnz     loc_180020D5E
0x180020cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ccc  cmp     rcx, rdi
0x180020ccf  jz      short loc_180020CEC
0x180020cd1  test    byte ptr [rcx+1Ch], 4
0x180020cd5  jz      short loc_180020CEC
0x180020cd7  mov     rcx, [rcx+10h]
0x180020cdb  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x180020ce2  mov     edx, 6Dh ; 'm'
0x180020ce7  call    WPP_SF_
0x180020cec  mov     rcx, r14
0x180020cef  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z
0x180020cf4  mov     rbx, rax
0x180020cf7  call    cs:__imp_GetCurrentProcess
0x180020cfd  mov     [rsp+240h+dwOptions], 1; dwOptions
0x180020d05  mov     r9, rbx; lpTargetHandle
0x180020d08  mov     rcx, rax; hSourceProcessHandle
0x180020d0b  mov     [rsp+240h+bInheritHandle], r13d; bInheritHandle
0x180020d10  mov     r8, r12; hTargetProcessHandle
0x180020d13  mov     [rsp+240h+dwDesiredAccess], 101F0001h; dwDesiredAccess
0x180020d1b  mov     rdx, r15; hSourceHandle
0x180020d1e  call    cs:__imp_DuplicateHandle
0x180020d24  test    eax, eax
0x180020d26  jnz     short loc_180020D7E
0x180020d28  call    cs:__imp_GetLastError
0x180020d2e  mov     ebx, eax
0x180020d30  test    eax, eax
0x180020d32  jle     short loc_180020D3D
0x180020d34  movzx   ebx, ax
0x180020d37  or      ebx, 80070000h
0x180020d3d  test    ebx, ebx
0x180020d3f  cmovns  ebx, esi
0x180020d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d49  cmp     rcx, rdi
0x180020d4c  jz      short loc_180020D81
0x180020d4e  test    byte ptr [rcx+1Ch], 1
0x180020d52  jz      short loc_180020D81
0x180020d54  mov     edx, 6Fh ; 'o'
0x180020d59  jmp     loc_180020A61
0x180020d5e  test    ebx, ebx
0x180020d60  jns     short loc_180020CEC
0x180020d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d69  cmp     rcx, rdi
0x180020d6c  jz      short loc_180020D81
0x180020d6e  test    byte ptr [rcx+1Ch], 1
0x180020d72  jz      short loc_180020D81
0x180020d74  mov     edx, 6Eh ; 'n'
0x180020d79  jmp     loc_180020A61
0x180020d7e  mov     ebx, r13d
0x180020d81  mov     rcx, [rsp+240h+hMem]; hMem
0x180020d86  test    rcx, rcx
0x180020d89  jz      short loc_180020D91
0x180020d8b  call    cs:__imp_LocalFree
0x180020d91  mov     eax, ebx
0x180020d93  mov     rcx, [rbp+140h+var_40]
0x180020d9a  xor     rcx, rsp; StackCookie
0x180020d9d  call    __security_check_cookie
0x180020da2  mov     rbx, [rsp+240h+arg_18]
0x180020daa  add     rsp, 210h
0x180020db1  pop     r15
0x180020db3  pop     r14
0x180020db5  pop     r13
0x180020db7  pop     r12
0x180020db9  pop     rdi
0x180020dba  pop     rsi
0x180020dbb  pop     rbp
0x180020dbc  retn
```
