# SamIReplaceDownlevelDatabase

- ea: `0x1800722d0`
- end: `0x180072800`
- name: `SamIReplaceDownlevelDatabase`
- size: `1328`
- prototype: `__int64 __fastcall(struct _POLICY_ACCOUNT_DOMAIN_INFO *, PCWSTR SourceString, ULONG *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x1800372ac`
- `0x180039ef8`
- `0x180041430`
- `0x18006d850`
- `0x18006fdbc`
- `0x180070910`
- `0x1800722d0`
- `0x180073370`
- `0x18007bd40`
- `0x1800bb788`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724f6`
- `ntdll!RtlNtStatusToDosError` at `0x180072766`
- `ntdll!RtlNtStatusToDosError` at `0x180072772`
- `ntdll!RtlNtStatusToDosError` at `0x180072766`
- `ntdll!RtlNtStatusToDosError` at `0x180072772`
- `ntdll!RtlAdjustPrivilege` at `0x180072613`
- `ntdll!RtlAdjustPrivilege` at `0x18007263b`
- `ntdll!RtlAdjustPrivilege` at `0x18007265d`
- `ntdll!RtlAdjustPrivilege` at `0x180072692`
- `ntdll!RtlAdjustPrivilege` at `0x180072613`
- `ntdll!RtlAdjustPrivilege` at `0x18007263b`
- `ntdll!RtlAdjustPrivilege` at `0x18007265d`
- `ntdll!RtlAdjustPrivilege` at `0x180072692`
- `ntdll!RtlInitUnicodeStringEx` at `0x18007273a`
- `ntdll!RtlInitUnicodeStringEx` at `0x18007273a`
- `ntdll!NtFlushKey` at `0x180072563`
- `ntdll!NtFlushKey` at `0x180072563`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800725f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800725f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072646`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800723c4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800723c4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007249b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800724ec`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007249b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800724ec`
- `api-ms-win-core-registry-l2-1-0!RegReplaceKeyW` at `0x18007267d`
- `api-ms-win-core-registry-l2-1-0!RegReplaceKeyW` at `0x18007267d`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180072626`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180072626`

## string_xrefs

- `0x180072414`: `\system32\config\SAM.UPG`
- `0x180072464`: `\system32\config\SAM.SAV`
- `0x180072593`: `\Registry\Machine\SOFTWARE\TEMPSAM`
- `0x1800725bf`: `\Registry\Machine\SOFTWARE\TEMPSAM`
- `0x1800726dd`: `\Registry\Machine\SOFTWARE\TEMPSAM`
- `0x1800725e8`: `SOFTWARE\TEMPSAM`

## pseudocode

```c
__int64 __fastcall SamIReplaceDownlevelDatabase(struct _POLICY_ACCOUNT_DOMAIN_INFO *a1, PCWSTR SourceString, ULONG *a3)
{
  PUNICODE_STRING v6; // rcx
  int inited; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rcx
  WCHAR *v11; // rax
  DWORD EnvironmentVariableW; // eax
  size_t v13; // rbx
  DWORD LastError; // eax
  DWORD v15; // eax
  int v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  unsigned int v19; // eax
  ULONG v20; // edi
  PUNICODE_STRING v21; // rcx
  __int64 v22; // rdx
  unsigned __int8 OldValue[4]; // [rsp+30h] [rbp-D0h] BYREF
  enum _POLICY_LSA_SERVER_ROLE v25; // [rsp+34h] [rbp-CCh] BYREF
  enum _NT_PRODUCT_TYPE v26; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR File[8]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v30[32]; // [rsp+70h] [rbp-90h]
  WCHAR FileName[8]; // [rsp+270h] [rbp+170h] BYREF
  _OWORD v32[32]; // [rsp+280h] [rbp+180h]
  wchar_t Buffer[264]; // [rsp+480h] [rbp+380h] BYREF

  hKey = 0;
  v26 = NtProductServer;
  v25 = PolicyServerRolePrimary;
  OldValue[0] = 0;
  DestinationString = 0;
  if ( !a1 )
  {
    *a3 = 87;
    v6 = WPP_GLOBAL_Control;
    inited = -1073741811;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 53;
      v9 = 3221225485LL;
LABEL_60:
      WPP_SF_Dd(v6[3].Buffer, v8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v9, inited);
      return (unsigned int)inited;
    }
    return (unsigned int)inited;
  }
  if ( SampIsDownlevelDcUpgrade() )
  {
    v10 = 522;
    v11 = Buffer;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (WCHAR *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
    EnvironmentVariableW = GetEnvironmentVariableW(L"systemroot", Buffer, 0x105u);
    if ( EnvironmentVariableW - 1 > 0x81 )
    {
      EnvironmentVariableW = 10;
      wcscpy(Buffer, L"c:\\winows");
    }
    v13 = 2LL * EnvironmentVariableW;
    memcpy_0(FileName, Buffer, v13);
    *(_OWORD *)&FileName[v13 / 2] = *(_OWORD *)L"\\system32\\config\\SAM.UPG";
    *(_OWORD *)((char *)v32 + v13) = *(_OWORD *)L"2\\config\\SAM.UPG";
    *(_OWORD *)((char *)&v32[1] + v13) = *(_OWORD *)L"\\SAM.UPG";
    *(_WORD *)((char *)&v32[2] + v13) = aSystem32Config[24];
    memcpy_0(File, Buffer, v13);
    *(_OWORD *)&File[v13 / 2] = *(_OWORD *)L"\\system32\\config\\SAM.SAV";
    *(_OWORD *)((char *)v30 + v13) = *(_OWORD *)L"2\\config\\SAM.SAV";
    *(_OWORD *)((char *)&v30[1] + v13) = *(_OWORD *)L"\\SAM.SAV";
    *(_WORD *)((char *)&v30[2] + v13) = aSystem32Config_1[24];
    if ( !DeleteFileW(FileName) )
    {
      LastError = GetLastError();
      if ( LastError != 2
        && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x80) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control[3].Buffer,
          55,
          (unsigned int)WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          (unsigned int)FileName,
          LastError);
      }
    }
    if ( !DeleteFileW(File) )
    {
      v15 = GetLastError();
      if ( v15 != 2
        && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x80) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control[3].Buffer,
          56,
          (unsigned int)WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          (unsigned int)File,
          v15);
      }
    }
    v16 = SampRenameKrbtgtAccount();
    if ( v16 < 0
      && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x80) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 57, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v16);
    }
    v17 = NtFlushKey(SampKey);
    if ( v17 < 0
      && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x80) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 58, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v17);
    }
    SampRegistryDelnode(L"\\Registry\\Machine\\SOFTWARE\\TEMPSAM");
    v18 = SampInitializeRegistry(
            L"\\Registry\\Machine\\SOFTWARE\\TEMPSAM",
            &v26,
            &v25,
            a1,
            0,
            SampSecretEncryptionEnabled);
    inited = v18;
    if ( v18 < 0 )
    {
      v20 = RtlNtStatusToDosError(v18);
      v6 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          62,
          WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          (unsigned int)inited);
LABEL_55:
        v6 = WPP_GLOBAL_Control;
      }
LABEL_56:
      if ( a3 )
      {
        *a3 = v20;
        v6 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v6[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v8 = 63;
        v9 = (unsigned int)inited;
        goto LABEL_60;
      }
      return (unsigned int)inited;
    }
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\TEMPSAM", 0, 0xF003Fu, &hKey);
    v20 = v19;
    if ( v19 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 61, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v19);
        v6 = WPP_GLOBAL_Control;
      }
LABEL_45:
      inited = -1073741823;
LABEL_46:
      if ( inited >= 0 && SourceString )
      {
        inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
        if ( inited >= 0 )
        {
          inited = SampSetAdminPasswordInRegistry(0, &DestinationString);
          if ( inited >= 0 )
            inited = SampCreateKeyForPostBootPromote(0x200u);
        }
        v20 = RtlNtStatusToDosError(inited);
        goto LABEL_55;
      }
      goto LABEL_56;
    }
    RtlAdjustPrivilege(0x11u, 1u, 0, OldValue);
    v20 = RegSaveKeyW(hKey, File, 0);
    RtlAdjustPrivilege(0x11u, 0, 0, OldValue);
    RegCloseKey(hKey);
    if ( v20 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v22 = 60;
        goto LABEL_39;
      }
    }
    else
    {
      RtlAdjustPrivilege(0x12u, 1u, 0, OldValue);
      v20 = RegReplaceKeyW(HKEY_LOCAL_MACHINE, L"SAM", File, FileName);
      RtlAdjustPrivilege(0x12u, 0, 0, OldValue);
      if ( v20 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          v22 = 59;
LABEL_39:
          WPP_SF_d(v21[3].Buffer, v22, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v20);
        }
      }
    }
    SampRegistryDelnode(L"\\Registry\\Machine\\SOFTWARE\\TEMPSAM");
    v6 = WPP_GLOBAL_Control;
    if ( !v20 )
      goto LABEL_46;
    goto LABEL_45;
  }
  *a3 = 1352;
  v6 = WPP_GLOBAL_Control;
  inited = -1073741604;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v8 = 54;
    v9 = 3221225692LL;
    goto LABEL_60;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800722d0  mov     [rsp-8+arg_18], rbx
0x1800722d5  push    rbp
0x1800722d6  push    rsi
0x1800722d7  push    rdi
0x1800722d8  push    r14
0x1800722da  push    r15
0x1800722dc  lea     rbp, [rsp-5A0h]
0x1800722e4  sub     rsp, 6A0h
0x1800722eb  mov     rax, cs:__security_cookie
0x1800722f2  xor     rax, rsp
0x1800722f5  mov     [rbp+5C0h+var_30], rax
0x1800722fc  mov     [rsp+6C0h+hKey], 0
0x180072305  mov     eax, 3
0x18007230a  mov     [rsp+6C0h+var_688], eax
0x18007230e  xorps   xmm0, xmm0
0x180072311  mov     [rsp+6C0h+var_68C], eax
0x180072315  mov     r14, r8
0x180072318  mov     [rsp+6C0h+OldValue], 0
0x18007231d  mov     r15, rdx
0x180072320  mov     rdi, rcx
0x180072323  movups  xmmword ptr [rsp+6C0h+DestinationString.Length], xmm0
0x180072328  test    rcx, rcx
0x18007232b  jnz     short loc_180072362
0x18007232d  mov     dword ptr [r8], 57h ; 'W'
0x180072334  mov     rcx, cs:WPP_GLOBAL_Control
0x18007233b  mov     ebx, 0C000000Dh
0x180072340  test    dword ptr [rcx+44h], 20000h
0x180072347  jz      loc_1800727D8
0x18007234d  lea     edx, [rdi+35h]
0x180072350  mov     r9d, 0C000000Dh
0x180072356  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18007235d  jmp     loc_1800727CB
0x180072362  call    ?SampIsDownlevelDcUpgrade@@YAEXZ; SampIsDownlevelDcUpgrade(void)
0x180072367  test    al, al
0x180072369  jnz     short loc_180072398
0x18007236b  mov     dword ptr [r14], 548h
0x180072372  mov     rcx, cs:WPP_GLOBAL_Control
0x180072379  mov     ebx, 0C00000DCh
0x18007237e  test    dword ptr [rcx+44h], 20000h
0x180072385  jz      loc_1800727D8
0x18007238b  mov     edx, 36h ; '6'
0x180072390  mov     r9d, 0C00000DCh
0x180072396  jmp     short loc_180072356
0x180072398  mov     ecx, 20Ah
0x18007239d  lea     rax, [rbp+5C0h+Buffer]
0x1800723a4  mov     byte ptr [rax], 0
0x1800723a7  inc     rax
0x1800723aa  sub     rcx, 1
0x1800723ae  jnz     short loc_1800723A4
0x1800723b0  mov     r8d, 105h; nSize
0x1800723b6  lea     rdx, [rbp+5C0h+Buffer]; lpBuffer
0x1800723bd  lea     rcx, Name; "systemroot"
0x1800723c4  call    cs:__imp_GetEnvironmentVariableW
0x1800723ca  lea     ecx, [rax-1]
0x1800723cd  cmp     ecx, 81h
0x1800723d3  jbe     short loc_1800723F8
0x1800723d5  movups  xmm0, xmmword ptr cs:aCWindows; "c:\\windows"
0x1800723dc  mov     eax, 0Ah
0x1800723e1  movsd   xmm1, qword ptr cs:aCWindows+0Eh; "ows"
0x1800723e9  movaps  xmmword ptr [rbp+5C0h+Buffer], xmm0
0x1800723f0  movsd   qword ptr [rbp+5C0h+Buffer+0Eh], xmm1
0x1800723f8  mov     eax, eax
0x1800723fa  lea     rdx, [rbp+5C0h+Buffer]; Src
0x180072401  lea     rcx, [rbp+5C0h+FileName]; void *
0x180072408  lea     rbx, [rax+rax]
0x18007240c  mov     r8, rbx; Size
0x18007240f  call    memcpy_0
0x180072414  movups  xmm0, xmmword ptr cs:aSystem32Config; "\\system32\\config\\SAM.UPG"
0x18007241b  movzx   eax, word ptr cs:aSystem32Config+30h; ""
0x180072422  mov     r8, rbx; Size
0x180072425  movups  xmm1, xmmword ptr cs:aSystem32Config+10h; "2\\config\\SAM.UPG"
0x18007242c  lea     rdx, [rbp+5C0h+Buffer]; Src
0x180072433  movups  xmmword ptr [rbp+rbx+5C0h+FileName], xmm0
0x18007243b  lea     rcx, [rsp+6C0h+File]; void *
0x180072440  movups  xmm0, xmmword ptr cs:aSystem32Config+20h; "\\SAM.UPG"
0x180072447  movups  [rbp+rbx+5C0h+var_440], xmm1
0x18007244f  movups  [rbp+rbx+5C0h+var_430], xmm0
0x180072457  mov     [rbp+rbx+5C0h+var_420], ax
0x18007245f  call    memcpy_0
0x180072464  movups  xmm0, xmmword ptr cs:aSystem32Config_1; "\\system32\\config\\SAM.SAV"
0x18007246b  movzx   eax, word ptr cs:aSystem32Config_1+30h; ""
0x180072472  lea     rcx, [rbp+5C0h+FileName]; lpFileName
0x180072479  movups  xmm1, xmmword ptr cs:aSystem32Config_1+10h; "2\\config\\SAM.SAV"
0x180072480  movups  xmmword ptr [rsp+rbx+6C0h+File], xmm0
0x180072485  movups  xmm0, xmmword ptr cs:aSystem32Config_1+20h; "\\SAM.SAV"
0x18007248c  movups  [rsp+rbx+6C0h+var_650], xmm1
0x180072491  movups  [rbp+rbx+5C0h+var_640], xmm0
0x180072496  mov     [rbp+rbx+5C0h+var_630], ax
0x18007249b  call    cs:__imp_DeleteFileW
0x1800724a1  lea     rsi, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x1800724a8  mov     bl, 80h
0x1800724aa  test    eax, eax
0x1800724ac  jnz     short loc_1800724E7
0x1800724ae  call    cs:__imp_GetLastError
0x1800724b4  cmp     eax, 2
0x1800724b7  jz      short loc_1800724E7
0x1800724b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724c0  test    [rcx+44h], bl
0x1800724c3  jz      short loc_1800724E7
0x1800724c5  cmp     byte ptr [rcx+41h], 2
0x1800724c9  jb      short loc_1800724E7
0x1800724cb  mov     rcx, [rcx+38h]
0x1800724cf  lea     r9, [rbp+5C0h+FileName]
0x1800724d6  mov     edx, 37h ; '7'
0x1800724db  mov     dword ptr [rsp+6C0h+phkResult], eax
0x1800724df  mov     r8, rsi
0x1800724e2  call    WPP_SF_Sd
0x1800724e7  lea     rcx, [rsp+6C0h+File]; lpFileName
0x1800724ec  call    cs:__imp_DeleteFileW
0x1800724f2  test    eax, eax
0x1800724f4  jnz     short loc_18007252D
0x1800724f6  call    cs:__imp_GetLastError
0x1800724fc  cmp     eax, 2
0x1800724ff  jz      short loc_18007252D
0x180072501  mov     rcx, cs:WPP_GLOBAL_Control
0x180072508  test    [rcx+44h], bl
0x18007250b  jz      short loc_18007252D
0x18007250d  cmp     byte ptr [rcx+41h], 2
0x180072511  jb      short loc_18007252D
0x180072513  mov     rcx, [rcx+38h]
0x180072517  lea     r9, [rsp+6C0h+File]
0x18007251c  mov     edx, 38h ; '8'
0x180072521  mov     dword ptr [rsp+6C0h+phkResult], eax
0x180072525  mov     r8, rsi
0x180072528  call    WPP_SF_Sd
0x18007252d  call    SampRenameKrbtgtAccount
0x180072532  test    eax, eax
0x180072534  jns     short loc_18007255C
0x180072536  mov     rcx, cs:WPP_GLOBAL_Control
0x18007253d  test    [rcx+44h], bl
0x180072540  jz      short loc_18007255C
0x180072542  cmp     byte ptr [rcx+41h], 2
0x180072546  jb      short loc_18007255C
0x180072548  mov     rcx, [rcx+38h]
0x18007254c  mov     edx, 39h ; '9'
0x180072551  mov     r9d, eax
0x180072554  mov     r8, rsi
0x180072557  call    WPP_SF_d
0x18007255c  mov     rcx, cs:SampKey; KeyHandle
0x180072563  call    cs:__imp_NtFlushKey
0x180072569  test    eax, eax
0x18007256b  jns     short loc_180072593
0x18007256d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072574  test    [rcx+44h], bl
0x180072577  jz      short loc_180072593
0x180072579  cmp     byte ptr [rcx+41h], 2
0x18007257d  jb      short loc_180072593
0x18007257f  mov     rcx, [rcx+38h]
0x180072583  mov     edx, 3Ah ; ':'
0x180072588  mov     r9d, eax
0x18007258b  mov     r8, rsi
0x18007258e  call    WPP_SF_d
0x180072593  lea     rcx, aRegistryMachin_10; "\\Registry\\Machine\\SOFTWARE\\TEMPSAM"
0x18007259a  call    ?SampRegistryDelnode@@YAJPEBG@Z; SampRegistryDelnode(ushort const *)
0x18007259f  mov     al, cs:?SampSecretEncryptionEnabled@@3EA; uchar SampSecretEncryptionEnabled
0x1800725a5  lea     r8, [rsp+6C0h+var_68C]; enum _POLICY_LSA_SERVER_ROLE *
0x1800725aa  mov     [rsp+6C0h+var_698], al; unsigned __int8
0x1800725ae  lea     rdx, [rsp+6C0h+var_688]; enum _NT_PRODUCT_TYPE *
0x1800725b3  mov     r9, rdi; struct _POLICY_ACCOUNT_DOMAIN_INFO *
0x1800725b6  mov     [rsp+6C0h+phkResult], 0; struct _POLICY_PRIMARY_DOMAIN_INFO *
0x1800725bf  lea     rcx, aRegistryMachin_10; "\\Registry\\Machine\\SOFTWARE\\TEMPSAM"
0x1800725c6  call    ?SampInitializeRegistry@@YAJPEBGPEAW4_NT_PRODUCT_TYPE@@PEAW4_POLICY_LSA_SERVER_ROLE@@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@PEAU_POLICY_PRIMARY_DOMAIN_INFO@@E@Z; SampInitializeRegistry(ushort const *,_NT_PRODUCT_TYPE *,_POLICY_LSA_SERVER_ROLE *,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_PRIMARY_DOMAIN_INFO *,uchar)
0x1800725cb  mov     ebx, eax
0x1800725cd  test    eax, eax
0x1800725cf  js      loc_180072770
0x1800725d5  lea     rax, [rsp+6C0h+hKey]
0x1800725da  mov     r9d, 0F003Fh; samDesired
0x1800725e0  xor     r8d, r8d; ulOptions
0x1800725e3  mov     [rsp+6C0h+phkResult], rax; phkResult
0x1800725e8  lea     rdx, aSoftwareTempsa; "SOFTWARE\\TEMPSAM"
0x1800725ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800725f6  call    cs:__imp_RegOpenKeyExW
0x1800725fc  mov     edi, eax
0x1800725fe  test    eax, eax
0x180072600  jnz     loc_1800726F6
0x180072606  lea     r9, [rsp+6C0h+OldValue]; OldValue
0x18007260b  xor     r8d, r8d; ForThread
0x18007260e  mov     dl, 1; NewValue
0x180072610  lea     ecx, [rax+11h]; Privilege
0x180072613  call    cs:__imp_RtlAdjustPrivilege
0x180072619  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18007261e  lea     rdx, [rsp+6C0h+File]; lpFile
0x180072623  xor     r8d, r8d; lpSecurityAttributes
0x180072626  call    cs:__imp_RegSaveKeyW
0x18007262c  xor     edx, edx; NewValue
0x18007262e  lea     r9, [rsp+6C0h+OldValue]; OldValue
0x180072633  xor     r8d, r8d; ForThread
0x180072636  mov     edi, eax
0x180072638  lea     ecx, [rdx+11h]; Privilege
0x18007263b  call    cs:__imp_RtlAdjustPrivilege
0x180072641  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180072646  call    cs:__imp_RegCloseKey
0x18007264c  test    edi, edi
0x18007264e  jnz     short loc_1800726B6
0x180072650  lea     r9, [rsp+6C0h+OldValue]; OldValue
0x180072655  xor     r8d, r8d; ForThread
0x180072658  mov     dl, 1; NewValue
0x18007265a  lea     ecx, [rdi+12h]; Privilege
0x18007265d  call    cs:__imp_RtlAdjustPrivilege
0x180072663  lea     r9, [rbp+5C0h+FileName]; lpOldFile
0x18007266a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072671  lea     r8, [rsp+6C0h+File]; lpNewFile
0x180072676  lea     rdx, aSam; "SAM"
0x18007267d  call    cs:__imp_RegReplaceKeyW
0x180072683  xor     edx, edx; NewValue
0x180072685  lea     r9, [rsp+6C0h+OldValue]; OldValue
0x18007268a  xor     r8d, r8d; ForThread
0x18007268d  mov     edi, eax
0x18007268f  lea     ecx, [rdx+12h]; Privilege
0x180072692  call    cs:__imp_RtlAdjustPrivilege
0x180072698  test    edi, edi
0x18007269a  jz      short loc_1800726DD
0x18007269c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726a3  test    byte ptr [rcx+44h], 80h
0x1800726a7  jz      short loc_1800726DD
0x1800726a9  cmp     byte ptr [rcx+41h], 2
0x1800726ad  jb      short loc_1800726DD
0x1800726af  mov     edx, 3Bh ; ';'
0x1800726b4  jmp     short loc_1800726CE
0x1800726b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726bd  test    byte ptr [rcx+44h], 80h
0x1800726c1  jz      short loc_1800726DD
0x1800726c3  cmp     byte ptr [rcx+41h], 2
0x1800726c7  jb      short loc_1800726DD
0x1800726c9  mov     edx, 3Ch ; '<'
0x1800726ce  mov     rcx, [rcx+38h]
0x1800726d2  mov     r9d, edi
0x1800726d5  mov     r8, rsi
0x1800726d8  call    WPP_SF_d
0x1800726dd  lea     rcx, aRegistryMachin_10; "\\Registry\\Machine\\SOFTWARE\\TEMPSAM"
0x1800726e4  call    ?SampRegistryDelnode@@YAJPEBG@Z; SampRegistryDelnode(ushort const *)
0x1800726e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726f0  test    edi, edi
0x1800726f2  jnz     short loc_180072724
0x1800726f4  jmp     short loc_180072729
0x1800726f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726fd  test    byte ptr [rcx+44h], 80h
0x180072701  jz      short loc_180072724
0x180072703  cmp     byte ptr [rcx+41h], 2
0x180072707  jb      short loc_180072724
0x180072709  mov     rcx, [rcx+38h]
0x18007270d  mov     edx, 3Dh ; '='
0x180072712  mov     r9d, eax
0x180072715  mov     r8, rsi
0x180072718  call    WPP_SF_d
0x18007271d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072724  mov     ebx, 0C0000001h
0x180072729  test    ebx, ebx
0x18007272b  js      short loc_1800727A8
0x18007272d  test    r15, r15
0x180072730  jz      short loc_1800727A8
0x180072732  mov     rdx, r15; SourceString
0x180072735  lea     rcx, [rsp+6C0h+DestinationString]; DestinationString
0x18007273a  call    cs:__imp_RtlInitUnicodeStringEx
0x180072740  mov     ebx, eax
0x180072742  test    eax, eax
0x180072744  js      short loc_180072764
0x180072746  lea     rdx, [rsp+6C0h+DestinationString]; struct _UNICODE_STRING *
0x18007274b  xor     ecx, ecx; unsigned __int8
0x18007274d  call    ?SampSetAdminPasswordInRegistry@@YAJEPEAU_UNICODE_STRING@@@Z; SampSetAdminPasswordInRegistry(uchar,_UNICODE_STRING *)
0x180072752  mov     ebx, eax
0x180072754  test    eax, eax
0x180072756  js      short loc_180072764
0x180072758  mov     ecx, 200h; unsigned int
0x18007275d  call    ?SampCreateKeyForPostBootPromote@@YAJK@Z; SampCreateKeyForPostBootPromote(ulong)
0x180072762  mov     ebx, eax
0x180072764  mov     ecx, ebx; Status
0x180072766  call    cs:__imp_RtlNtStatusToDosError
0x18007276c  mov     edi, eax
0x18007276e  jmp     short loc_1800727A1
0x180072770  mov     ecx, ebx; Status
0x180072772  call    cs:__imp_RtlNtStatusToDosError
0x180072778  mov     edi, eax
0x18007277a  mov     rcx, cs:WPP_GLOBAL_Control
0x180072781  test    byte ptr [rcx+44h], 80h
0x180072785  jz      short loc_1800727A8
0x180072787  cmp     byte ptr [rcx+41h], 2
0x18007278b  jb      short loc_1800727A8
0x18007278d  mov     rcx, [rcx+38h]
0x180072791  mov     edx, 3Eh ; '>'
0x180072796  mov     r9d, ebx
0x180072799  mov     r8, rsi
0x18007279c  call    WPP_SF_d
0x1800727a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800727a8  test    r14, r14
0x1800727ab  jz      short loc_1800727B7
0x1800727ad  mov     [r14], edi
0x1800727b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800727b7  test    dword ptr [rcx+44h], 20000h
0x1800727be  jz      short loc_1800727D8
0x1800727c0  mov     edx, 3Fh ; '?'
0x1800727c5  mov     r9d, ebx
0x1800727c8  mov     r8, rsi
0x1800727cb  mov     rcx, [rcx+38h]
0x1800727cf  mov     dword ptr [rsp+6C0h+phkResult], ebx
0x1800727d3  call    WPP_SF_Dd
0x1800727d8  mov     eax, ebx
0x1800727da  mov     rcx, [rbp+5C0h+var_30]
0x1800727e1  xor     rcx, rsp; StackCookie
0x1800727e4  call    __security_check_cookie
  ... truncated ...
```
