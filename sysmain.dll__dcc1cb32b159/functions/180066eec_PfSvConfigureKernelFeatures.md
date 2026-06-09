# PfSvConfigureKernelFeatures

- ea: `0x180066eec`
- end: `0x1800671c7`
- name: `PfSvConfigureKernelFeatures`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006a020`

## callees

- `0x1800382e0`
- `0x18006168c`
- `0x180066eec`
- `0x180086a74`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x180067022`
- `ntdll!NtQueryLicenseValue` at `0x180067022`
- `ntdll!NtQuerySystemInformation` at `0x180067137`
- `ntdll!NtQuerySystemInformation` at `0x180067137`
- `ntdll!NtSetSystemInformation` at `0x1800670e0`
- `ntdll!NtSetSystemInformation` at `0x180067195`
- `ntdll!NtSetSystemInformation` at `0x1800670e0`
- `ntdll!NtSetSystemInformation` at `0x180067195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800671a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800671a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006709e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006709e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006708a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006708a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180067073`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180067073`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800671b1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800671b1`

## string_xrefs

- `0x180066f06`: `System-ConfigurePagefileForLowStorage-Enabled`
- `0x180066fbb`: `MemCompressionOptions`

## pseudocode

```c
__int64 PfSvConfigureKernelFeatures()
{
  char v0; // si
  bool v1; // zf
  int v2; // edi
  BOOL v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // edi
  HANDLE CurrentThread; // rax
  __int64 v8; // rdx
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-59h] BYREF
  int SystemInformation; // [rsp+38h] [rbp-51h] BYREF
  int v14; // [rsp+3Ch] [rbp-4Dh]
  __int128 *v15; // [rsp+40h] [rbp-49h]
  __int64 v16; // [rsp+48h] [rbp-41h]
  unsigned __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v18[2]; // [rsp+58h] [rbp-31h] BYREF
  _OWORD v19[2]; // [rsp+68h] [rbp-21h] BYREF
  __int128 v20; // [rsp+88h] [rbp-1h] BYREF
  __int128 v21; // [rsp+98h] [rbp+Fh]
  __int128 v22; // [rsp+A8h] [rbp+1Fh]
  BOOL v23; // [rsp+F0h] [rbp+67h] BYREF
  int v24; // [rsp+F8h] [rbp+6Fh] BYREF
  int v25; // [rsp+100h] [rbp+77h] BYREF
  int v26; // [rsp+108h] [rbp+7Fh] BYREF

  v18[1] = L"System-ConfigurePagefileForLowStorage-Enabled";
  v0 = 0;
  v23 = 0;
  v18[0] = 6029402;
  v1 = (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 320LL) & 0x200) == 0;
  memset(v19, 0, sizeof(v19));
  v24 = 0;
  v20 = 0;
  v26 = 0;
  v21 = 0;
  v25 = 0;
  v22 = 0;
  v17 = 0;
  TokenHandle = 0;
  v16 = 32;
  SystemInformation = 1;
  v14 = 19;
  v15 = v19;
  LODWORD(v19[0]) = 9;
  if ( !v1 && (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x8000000) == 0 )
  {
    v2 = *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 332LL);
    if ( (unsigned int)PfsRegQueryValue(
                         *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL),
                         (unsigned int)L"MemCompressionOptions",
                         4,
                         4,
                         (__int64)&v23) )
    {
      v3 = v2 == 2;
      v23 = v3;
    }
    else
    {
      v3 = v23;
    }
    if ( (v3 & 0xFFFFFFFE) != 0 )
    {
      LOBYTE(v3) = v2 == 2;
      v23 = v2 == 2;
    }
    v4 = 32 * v3 + 2442;
    v5 = v4 | 0x40;
    if ( v2 != 7 )
      v5 = v4;
    if ( (int)NtQueryLicenseValue(v18, &v24, &v26, 4, &v25) >= 0 && v24 == 4 && v25 == 4 && v26 )
    {
      v6 = PfsQueryTotalMaxPagefileSize(&v17);
      if ( v6 < 0 )
        goto LABEL_32;
      if ( v17 <= 0x4000000 && v17 )
      {
        if ( !ImpersonateSelf(SecurityImpersonation)
          || (v0 = 1, CurrentThread = GetCurrentThread(), !OpenThreadToken(CurrentThread, 0x20u, 0, &TokenHandle)) )
        {
          v6 = -1073741732;
          goto LABEL_32;
        }
        if ( !(unsigned int)PfSvSetPrivilege(TokenHandle, v8, 4) )
        {
          v6 = -1073741728;
          goto LABEL_32;
        }
        v5 = v5 & 0xFFFFFFC1 | 0x14;
      }
    }
    LODWORD(v19[0]) &= 0xFFFFFFu;
    DWORD1(v19[0]) = v5;
    v6 = NtSetSystemInformation(SystemVerifierFaultsInformation|SystemLocksInformation, &SystemInformation, 0x18u);
    if ( v6 < 0 )
      goto LABEL_32;
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 324LL) |= 0x200u;
  }
  v14 = 22;
  LODWORD(v16) = 48;
  v20 = 0;
  LODWORD(v20) = 4;
  v15 = &v20;
  v21 = 0;
  v22 = 0;
  v9 = NtQuerySystemInformation(SystemVerifierFaultsInformation|SystemLocksInformation, &SystemInformation, 0x18u, 0);
  v10 = *(_QWORD *)&PfSvcGlobals;
  v6 = v9;
  if ( v9 < 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 324LL) & 0x200) != 0 && v9 != -1073741399 )
      goto LABEL_32;
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 4144LL) = DWORD1(v20);
  }
  if ( (*(_DWORD *)(v10 + 380) & 0x18000) != 0 )
  {
    DWORD1(v19[0]) = 4;
    LODWORD(v19[0]) = v19[0] & 0xFFFFFF | 0x2000000;
    NtSetSystemInformation(SystemVerifierFaultsInformation|SystemLocksInformation, &SystemInformation, 0x18u);
  }
  v6 = 0;
LABEL_32:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v0 )
    RevertToSelf();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180066eec  push    rbp
0x180066eee  push    rbx
0x180066eef  push    rsi
0x180066ef0  push    rdi
0x180066ef1  push    r15
0x180066ef3  lea     rbp, [rsp-37h]
0x180066ef8  sub     rsp, 0C0h
0x180066eff  mov     rcx, cs:PfSvcGlobals
0x180066f06  lea     rax, aSystemConfigur; "System-ConfigurePagefileForLowStorage-E"...
0x180066f0d  xorps   xmm0, xmm0
0x180066f10  mov     [rbp+57h+var_80], rax
0x180066f14  xor     sil, sil
0x180066f17  mov     [rbp+57h+arg_0], 0
0x180066f1e  lea     rax, [rbp+57h+var_78]
0x180066f22  mov     [rbp+57h+var_88], 5C005Ah
0x180066f2a  test    dword ptr [rcx+140h], 200h
0x180066f34  mov     r15d, 4
0x180066f3a  movups  [rbp+57h+var_78], xmm0
0x180066f3e  mov     [rbp+57h+arg_8], 0
0x180066f45  movups  [rbp+57h+var_58], xmm0
0x180066f49  mov     [rbp+57h+arg_18], 0
0x180066f50  movups  [rbp+57h+var_48], xmm0
0x180066f54  mov     [rbp+57h+arg_10], 0
0x180066f5b  movups  [rbp+57h+var_38], xmm0
0x180066f5f  mov     [rbp+57h+var_90], 0
0x180066f67  mov     [rbp+57h+TokenHandle], 0
0x180066f6f  mov     [rbp+57h+var_98], 20h ; ' '
0x180066f77  mov     [rbp+57h+SystemInformation], 1
0x180066f7e  mov     [rbp+57h+var_A4], 13h
0x180066f85  mov     [rbp+57h+var_A0], rax
0x180066f89  movups  [rbp+57h+var_68], xmm0
0x180066f8d  mov     dword ptr [rbp+57h+var_78], 9
0x180066f94  jz      loc_1800670FF
0x180066f9a  test    dword ptr [rcx+0F4h], 8000000h
0x180066fa4  jnz     loc_1800670FF
0x180066faa  mov     edi, [rcx+14Ch]
0x180066fb0  lea     rax, [rbp+57h+arg_0]
0x180066fb4  mov     rcx, [rcx+598h]
0x180066fbb  lea     rdx, aMemcompression; "MemCompressionOptions"
0x180066fc2  xor     ebx, ebx
0x180066fc4  mov     [rsp+0E0h+var_C0], rax
0x180066fc9  cmp     edi, 2
0x180066fcc  mov     r9d, r15d
0x180066fcf  mov     r8d, r15d
0x180066fd2  setz    bl
0x180066fd5  call    PfsRegQueryValue
0x180066fda  test    eax, eax
0x180066fdc  jz      short loc_180066FE5
0x180066fde  mov     eax, ebx
0x180066fe0  mov     [rbp+57h+arg_0], ebx
0x180066fe3  jmp     short loc_180066FE8
0x180066fe5  mov     eax, [rbp+57h+arg_0]
0x180066fe8  test    eax, 0FFFFFFFEh
0x180066fed  jz      short loc_180066FF4
0x180066fef  mov     eax, ebx
0x180066ff1  mov     [rbp+57h+arg_0], ebx
0x180066ff4  and     eax, 1
0x180066ff7  lea     r8, [rbp+57h+arg_18]
0x180066ffb  shl     eax, 5
0x180066ffe  lea     rdx, [rbp+57h+arg_8]
0x180067002  add     eax, 98Ah
0x180067007  lea     rcx, [rbp+57h+var_88]
0x18006700b  mov     ebx, eax
0x18006700d  mov     r9d, r15d
0x180067010  or      ebx, 40h
0x180067013  cmp     edi, 7
0x180067016  cmovnz  ebx, eax
0x180067019  lea     rax, [rbp+57h+arg_10]
0x18006701d  mov     [rsp+0E0h+var_C0], rax
0x180067022  call    cs:__imp_NtQueryLicenseValue
0x180067028  test    eax, eax
0x18006702a  js      loc_1800670C8
0x180067030  cmp     [rbp+57h+arg_8], r15d
0x180067034  jnz     loc_1800670C8
0x18006703a  cmp     [rbp+57h+arg_10], r15d
0x18006703e  jnz     loc_1800670C8
0x180067044  cmp     [rbp+57h+arg_18], 0
0x180067048  jz      short loc_1800670C8
0x18006704a  lea     rcx, [rbp+57h+var_90]
0x18006704e  call    PfsQueryTotalMaxPagefileSize
0x180067053  mov     edi, eax
0x180067055  test    eax, eax
0x180067057  js      loc_18006719D
0x18006705d  mov     rax, [rbp+57h+var_90]
0x180067061  cmp     rax, 4000000h
0x180067067  ja      short loc_1800670C8
0x180067069  test    rax, rax
0x18006706c  jz      short loc_1800670C8
0x18006706e  mov     ecx, 2; ImpersonationLevel
0x180067073  call    cs:__imp_ImpersonateSelf
0x180067079  test    eax, eax
0x18006707b  jnz     short loc_180067087
0x18006707d  mov     edi, 0C000005Ch
0x180067082  jmp     loc_18006719D
0x180067087  mov     sil, 1
0x18006708a  call    cs:__imp_GetCurrentThread
0x180067090  xor     r8d, r8d; OpenAsSelf
0x180067093  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180067097  mov     rcx, rax; ThreadHandle
0x18006709a  lea     edx, [r8+20h]; DesiredAccess
0x18006709e  call    cs:__imp_OpenThreadToken
0x1800670a4  test    eax, eax
0x1800670a6  jz      short loc_18006707D
0x1800670a8  mov     rcx, [rbp+57h+TokenHandle]
0x1800670ac  mov     r8d, r15d
0x1800670af  call    PfSvSetPrivilege
0x1800670b4  test    eax, eax
0x1800670b6  jnz     short loc_1800670C2
0x1800670b8  mov     edi, 0C0000060h
0x1800670bd  jmp     loc_18006719D
0x1800670c2  and     ebx, 0FFFFFFD5h
0x1800670c5  or      ebx, 14h
0x1800670c8  and     dword ptr [rbp+57h+var_78], 0FFFFFFh
0x1800670cf  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1800670d3  mov     r8d, 18h; SystemInformationLength
0x1800670d9  mov     dword ptr [rbp+57h+var_78+4], ebx
0x1800670dc  lea     ecx, [r8+55h]; SystemInformationClass
0x1800670e0  call    cs:__imp_NtSetSystemInformation
0x1800670e6  mov     edi, eax
0x1800670e8  test    eax, eax
0x1800670ea  js      loc_18006719D
0x1800670f0  mov     rax, cs:PfSvcGlobals
0x1800670f7  bts     dword ptr [rax+144h], 9
0x1800670ff  xorps   xmm0, xmm0
0x180067102  mov     [rbp+57h+var_A4], 16h
0x180067109  xor     r9d, r9d; ReturnLength
0x18006710c  mov     dword ptr [rbp+57h+var_98], 30h ; '0'
0x180067113  lea     rax, [rbp+57h+var_58]
0x180067117  movups  [rbp+57h+var_58], xmm0
0x18006711b  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18006711f  mov     dword ptr [rbp+57h+var_58], r15d
0x180067123  lea     r8d, [r9+18h]; SystemInformationLength
0x180067127  mov     [rbp+57h+var_A0], rax
0x18006712b  lea     ecx, [r9+6Dh]; SystemInformationClass
0x18006712f  movups  [rbp+57h+var_48], xmm0
0x180067133  movups  [rbp+57h+var_38], xmm0
0x180067137  call    cs:__imp_NtQuerySystemInformation
0x18006713d  mov     rcx, cs:PfSvcGlobals
0x180067144  mov     edi, eax
0x180067146  test    eax, eax
0x180067148  js      short loc_180067155
0x18006714a  mov     eax, dword ptr [rbp+57h+var_58+4]
0x18006714d  mov     [rcx+1030h], eax
0x180067153  jmp     short loc_180067168
0x180067155  test    dword ptr [rcx+144h], 200h
0x18006715f  jz      short loc_180067168
0x180067161  cmp     eax, 0C00001A9h
0x180067166  jnz     short loc_18006719D
0x180067168  test    dword ptr [rcx+17Ch], 18000h
0x180067172  jz      short loc_18006719B
0x180067174  mov     eax, dword ptr [rbp+57h+var_78]
0x180067177  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18006717b  mov     r8d, 18h; SystemInformationLength
0x180067181  mov     dword ptr [rbp+57h+var_78+4], r15d
0x180067185  and     eax, 0FFFFFFh
0x18006718a  bts     eax, 19h
0x18006718e  mov     dword ptr [rbp+57h+var_78], eax
0x180067191  lea     ecx, [r8+55h]; SystemInformationClass
0x180067195  call    cs:__imp_NtSetSystemInformation
0x18006719b  xor     edi, edi
0x18006719d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800671a1  test    rcx, rcx
0x1800671a4  jz      short loc_1800671AC
0x1800671a6  call    cs:__imp_CloseHandle
0x1800671ac  test    sil, sil
0x1800671af  jz      short loc_1800671B7
0x1800671b1  call    cs:__imp_RevertToSelf
0x1800671b7  mov     eax, edi
0x1800671b9  add     rsp, 0C0h
0x1800671c0  pop     r15
0x1800671c2  pop     rdi
0x1800671c3  pop     rsi
0x1800671c4  pop     rbx
0x1800671c5  pop     rbp
0x1800671c6  retn
```
