# ReadPolicySettings(void)

- ea: `0x180091010`
- end: `0x18009138c`
- name: `?ReadPolicySettings@@YAJXZ`
- size: `892`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002499c`

## callees

- `0x180091010`
- `0x180091394`
- `0x1800b2c08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091054`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800911f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800911f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800910ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091113`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091154`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091198`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800911d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091271`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800912ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800910ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091113`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091154`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091198`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800911d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091271`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800912ae`

## pseudocode

```c
__int64 ReadPolicySettings(void)
{
  LSTATUS v0; // eax
  LSTATUS ValueW; // eax
  __int64 v3; // rcx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  unsigned int pvData; // [rsp+80h] [rbp+38h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+40h] BYREF
  int v12; // [rsp+90h] [rbp+48h] BYREF
  HKEY hkey; // [rsp+98h] [rbp+50h] BYREF

  hkey = 0;
  pvData = 0;
  v12 = 0;
  pcbData = 4;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Rpc", 0, 0x20019u, &hkey);
  switch ( v0 )
  {
    case 0:
      ValueW = RegGetValueW(hkey, 0, L"StateInformation", 0x18u, 0, &pvData, &pcbData);
      if ( ValueW )
      {
        if ( ValueW != 2 )
          goto LABEL_22;
        v3 = 2;
        goto LABEL_8;
      }
      v3 = pvData;
      if ( pvData )
      {
        switch ( pvData )
        {
          case 1u:
          case 2u:
LABEL_8:
            SetAutoPolicySettings(v3);
            break;
          case 3u:
            g_fServerSideDebugInfoEnabled = 1;
            break;
          case 4u:
            g_fServerSideDebugInfoEnabled = 1;
            g_fClientSideDebugInfoEnabled = 1;
            break;
          default:
LABEL_47:
            v8 = 1766;
            goto LABEL_23;
        }
      }
      if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x80000000) != 0 )
        g_fServerSideDebugInfoEnabled = 0;
      pcbData = 4;
      v4 = RegGetValueW(hkey, 0, L"ExtErrorInformation", 0x18u, 0, &pvData, &pcbData);
      if ( v4 )
      {
        if ( v4 != 2 )
          goto LABEL_22;
        goto LABEL_13;
      }
      if ( pvData )
      {
        switch ( pvData )
        {
          case 1u:
            if ( !(unsigned int)IsThisProcessAnException(hkey, &v12) && v12 )
              goto LABEL_13;
            break;
          case 2u:
            if ( (unsigned int)IsThisProcessAnException(hkey, &v12) || v12 != 1 )
              goto LABEL_13;
            break;
          case 3u:
            break;
          default:
            goto LABEL_47;
        }
        g_fSendEEInfo = 1;
      }
LABEL_13:
      pcbData = 4;
      v5 = RegGetValueW(hkey, 0, L"IgnoreDelegationFailure", 0x18u, 0, &pvData, &pcbData);
      if ( v5 )
      {
        if ( v5 != 2 )
          goto LABEL_22;
      }
      else if ( pvData )
      {
        g_fIgnoreDelegationFailure = 1;
      }
      pcbData = 4;
      v6 = RegGetValueW(hkey, 0, L"RestrictRemoteClients", 0x18u, 0, &pvData, &pcbData);
      if ( v6 )
      {
        if ( v6 != 2 )
          goto LABEL_22;
      }
      else if ( pvData <= 2 )
      {
        g_fRestrictRemoteClients = pvData;
      }
      pcbData = 4;
      v7 = RegGetValueW(hkey, 0, L"EnableAuthEpResolution", 0x18u, 0, &pvData, &pcbData);
      if ( !v7 )
      {
        g_fAuthenticatedEpResolution = pvData;
LABEL_31:
        pcbData = 4;
        v9 = RegGetValueW(hkey, 0, L"MaxNonPagedPoolPerConnection", 0x18u, 0, &pvData, &pcbData);
        if ( !v9 )
        {
          gMaxSendBufferSizeLimit = pvData;
LABEL_33:
          pcbData = 4;
          v8 = RegGetValueW(hkey, 0, L"EnableTcpPortScaling", 0x18u, 0, &pvData, &pcbData);
          if ( v8 )
            v8 = v8 != 2 ? 0xE : 0;
          else
            gEnableTcpPortScaling = pvData;
          goto LABEL_23;
        }
        if ( v9 == 2 )
          goto LABEL_33;
        goto LABEL_22;
      }
      if ( v7 == 2 )
        goto LABEL_31;
LABEL_22:
      v8 = 14;
LABEL_23:
      RegCloseKey(hkey);
      return v8;
    case 2:
      SetAutoPolicySettings(2);
      return 0;
    case 5:
      SetAutoPolicySettings(2);
      g_fRestrictRemoteClients = 2;
      return 0;
  }
  return 14;
}

```

## disassembly

```asm
0x180091010  push    rbp
0x180091012  push    rbx
0x180091013  push    rsi
0x180091014  push    rdi
0x180091015  push    r14
0x180091017  push    r15
0x180091019  mov     rbp, rsp
0x18009101c  sub     rsp, 48h
0x180091020  xor     esi, esi
0x180091022  lea     rax, [rbp+hkey]
0x180091026  mov     r9d, 20019h; samDesired
0x18009102c  mov     [rbp+hkey], rsi
0x180091030  xor     r8d, r8d; ulOptions
0x180091033  mov     [rbp+arg_0], esi
0x180091036  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18009103d  mov     [rbp+arg_10], esi
0x180091040  lea     r14d, [rsi+4]
0x180091044  mov     [rsp+48h+phkResult], rax; phkResult
0x180091049  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091050  mov     [rbp+arg_8], r14d
0x180091054  call    cs:__imp_RegOpenKeyExW
0x18009105a  test    eax, eax
0x18009105c  jz      short loc_18009107F
0x18009105e  lea     edi, [rsi+2]
0x180091061  cmp     eax, edi
0x180091063  jnz     loc_1800912FB
0x180091069  mov     ecx, edi
0x18009106b  call    ?SetAutoPolicySettings@@YAXW4tagStateInformationPolicyValues@@@Z; SetAutoPolicySettings(tagStateInformationPolicyValues)
0x180091070  xor     eax, eax
0x180091072  add     rsp, 48h
0x180091076  pop     r15
0x180091078  pop     r14
0x18009107a  pop     rdi
0x18009107b  pop     rsi
0x18009107c  pop     rbx
0x18009107d  pop     rbp
0x18009107e  retn
0x18009107f  mov     rcx, [rbp+hkey]; hkey
0x180091083  lea     rax, [rbp+arg_8]
0x180091087  mov     [rsp+48h+pcbData], rax; pcbData
0x18009108c  lea     r8, aStateinformati; "StateInformation"
0x180091093  lea     rax, [rbp+arg_0]
0x180091097  mov     r15d, 18h
0x18009109d  mov     [rsp+48h+pvData], rax; pvData
0x1800910a2  mov     r9d, r15d; dwFlags
0x1800910a5  xor     edx, edx; lpSubKey
0x1800910a7  mov     [rsp+48h+phkResult], rsi; pdwType
0x1800910ac  call    cs:__imp_RegGetValueW
0x1800910b2  lea     edi, [r15-16h]
0x1800910b6  lea     ebx, [rdi-1]
0x1800910b9  test    eax, eax
0x1800910bb  jz      loc_1800911FF
0x1800910c1  cmp     eax, edi
0x1800910c3  jnz     loc_1800911E9
0x1800910c9  mov     ecx, edi
0x1800910cb  call    ?SetAutoPolicySettings@@YAXW4tagStateInformationPolicyValues@@@Z; SetAutoPolicySettings(tagStateInformationPolicyValues)
0x1800910d0  mov     rax, gs:60h
0x1800910d9  mov     rcx, [rax+20h]
0x1800910dd  cmp     [rcx+8], esi
0x1800910e0  jge     short loc_1800910E8
0x1800910e2  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, esi; int g_fServerSideDebugInfoEnabled
0x1800910e8  mov     rcx, [rbp+hkey]; hkey
0x1800910ec  lea     rax, [rbp+arg_8]
0x1800910f0  mov     [rsp+48h+pcbData], rax; pcbData
0x1800910f5  lea     r8, aExterrorinform; "ExtErrorInformation"
0x1800910fc  lea     rax, [rbp+arg_0]
0x180091100  mov     [rbp+arg_8], r14d
0x180091104  mov     [rsp+48h+pvData], rax; pvData
0x180091109  mov     r9d, r15d; dwFlags
0x18009110c  xor     edx, edx; lpSubKey
0x18009110e  mov     [rsp+48h+phkResult], rsi; pdwType
0x180091113  call    cs:__imp_RegGetValueW
0x180091119  test    eax, eax
0x18009111b  jz      loc_180091327
0x180091121  cmp     eax, edi
0x180091123  jnz     loc_1800911E9
0x180091129  mov     rcx, [rbp+hkey]; hkey
0x18009112d  lea     rax, [rbp+arg_8]
0x180091131  mov     [rsp+48h+pcbData], rax; pcbData
0x180091136  lea     r8, aIgnoredelegati; "IgnoreDelegationFailure"
0x18009113d  lea     rax, [rbp+arg_0]
0x180091141  mov     [rbp+arg_8], r14d
0x180091145  mov     [rsp+48h+pvData], rax; pvData
0x18009114a  mov     r9d, r15d; dwFlags
0x18009114d  xor     edx, edx; lpSubKey
0x18009114f  mov     [rsp+48h+phkResult], rsi; pdwType
0x180091154  call    cs:__imp_RegGetValueW
0x18009115a  test    eax, eax
0x18009115c  jnz     loc_1800911E5
0x180091162  cmp     [rbp+arg_0], esi
0x180091165  jz      short loc_18009116D
0x180091167  mov     cs:?g_fIgnoreDelegationFailure@@3HA, ebx; int g_fIgnoreDelegationFailure
0x18009116d  mov     rcx, [rbp+hkey]; hkey
0x180091171  lea     rax, [rbp+arg_8]
0x180091175  mov     [rsp+48h+pcbData], rax; pcbData
0x18009117a  lea     r8, aRestrictremote; "RestrictRemoteClients"
0x180091181  lea     rax, [rbp+arg_0]
0x180091185  mov     [rbp+arg_8], r14d
0x180091189  mov     [rsp+48h+pvData], rax; pvData
0x18009118e  mov     r9d, r15d; dwFlags
0x180091191  xor     edx, edx; lpSubKey
0x180091193  mov     [rsp+48h+phkResult], rsi; pdwType
0x180091198  call    cs:__imp_RegGetValueW
0x18009119e  test    eax, eax
0x1800911a0  jz      loc_1800912CC
0x1800911a6  cmp     eax, edi
0x1800911a8  jnz     short loc_1800911E9
0x1800911aa  mov     rcx, [rbp+hkey]; hkey
0x1800911ae  lea     rax, [rbp+arg_8]
0x1800911b2  mov     [rsp+48h+pcbData], rax; pcbData
0x1800911b7  lea     r8, aEnableauthepre; "EnableAuthEpResolution"
0x1800911be  lea     rax, [rbp+arg_0]
0x1800911c2  mov     [rbp+arg_8], r14d
0x1800911c6  mov     [rsp+48h+pvData], rax; pvData
0x1800911cb  mov     r9d, r15d; dwFlags
0x1800911ce  xor     edx, edx; lpSubKey
0x1800911d0  mov     [rsp+48h+phkResult], rsi; pdwType
0x1800911d5  call    cs:__imp_RegGetValueW
0x1800911db  test    eax, eax
0x1800911dd  jz      short loc_18009123D
0x1800911df  cmp     eax, edi
0x1800911e1  jnz     short loc_1800911E9
0x1800911e3  jmp     short loc_180091246
0x1800911e5  cmp     eax, edi
0x1800911e7  jz      short loc_18009116D
0x1800911e9  mov     ebx, 0Eh
0x1800911ee  mov     rcx, [rbp+hkey]; hKey
0x1800911f2  call    cs:__imp_RegCloseKey
0x1800911f8  mov     eax, ebx
0x1800911fa  jmp     loc_180091072
0x1800911ff  mov     ecx, [rbp+arg_0]
0x180091202  mov     eax, ecx
0x180091204  test    ecx, ecx
0x180091206  jz      loc_1800910D0
0x18009120c  sub     eax, ebx
0x18009120e  jz      loc_1800910CB
0x180091214  sub     eax, ebx
0x180091216  jz      loc_1800910CB
0x18009121c  sub     eax, ebx
0x18009121e  jz      loc_18009131C
0x180091224  cmp     eax, ebx
0x180091226  jnz     loc_18009133E
0x18009122c  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, ebx; int g_fServerSideDebugInfoEnabled
0x180091232  mov     cs:?g_fClientSideDebugInfoEnabled@@3HA, ebx; int g_fClientSideDebugInfoEnabled
0x180091238  jmp     loc_1800910D0
0x18009123d  mov     eax, [rbp+arg_0]
0x180091240  mov     cs:?g_fAuthenticatedEpResolution@@3HA, eax; int g_fAuthenticatedEpResolution
0x180091246  mov     rcx, [rbp+hkey]; hkey
0x18009124a  lea     rax, [rbp+arg_8]
0x18009124e  mov     [rsp+48h+pcbData], rax; pcbData
0x180091253  lea     r8, aMaxnonpagedpoo; "MaxNonPagedPoolPerConnection"
0x18009125a  lea     rax, [rbp+arg_0]
0x18009125e  mov     [rbp+arg_8], r14d
0x180091262  mov     [rsp+48h+pvData], rax; pvData
0x180091267  mov     r9d, r15d; dwFlags
0x18009126a  xor     edx, edx; lpSubKey
0x18009126c  mov     [rsp+48h+phkResult], rsi; pdwType
0x180091271  call    cs:__imp_RegGetValueW
0x180091277  test    eax, eax
0x180091279  jz      short loc_1800912F0
0x18009127b  cmp     eax, edi
0x18009127d  jnz     loc_1800911E9
0x180091283  mov     rcx, [rbp+hkey]; hkey
0x180091287  lea     rax, [rbp+arg_8]
0x18009128b  mov     [rsp+48h+pcbData], rax; pcbData
0x180091290  lea     r8, aEnabletcpports; "EnableTcpPortScaling"
0x180091297  lea     rax, [rbp+arg_0]
0x18009129b  mov     [rbp+arg_8], r14d
0x18009129f  mov     [rsp+48h+pvData], rax; pvData
0x1800912a4  mov     r9d, r15d; dwFlags
0x1800912a7  xor     edx, edx; lpSubKey
0x1800912a9  mov     [rsp+48h+phkResult], rsi; pdwType
0x1800912ae  call    cs:__imp_RegGetValueW
0x1800912b4  mov     ebx, eax
0x1800912b6  test    eax, eax
0x1800912b8  jz      short loc_1800912E2
0x1800912ba  sub     ebx, edi
0x1800912bc  neg     ebx
0x1800912be  mov     ebx, 0Eh
0x1800912c3  sbb     eax, eax
0x1800912c5  and     ebx, eax
0x1800912c7  jmp     loc_1800911EE
0x1800912cc  mov     eax, [rbp+arg_0]
0x1800912cf  cmp     eax, edi
0x1800912d1  ja      loc_1800911AA
0x1800912d7  mov     cs:?g_fRestrictRemoteClients@@3IA, eax; uint g_fRestrictRemoteClients
0x1800912dd  jmp     loc_1800911AA
0x1800912e2  mov     eax, [rbp+arg_0]
0x1800912e5  mov     cs:?gEnableTcpPortScaling@@3KA, eax; ulong gEnableTcpPortScaling
0x1800912eb  jmp     loc_1800911EE
0x1800912f0  mov     eax, [rbp+arg_0]
0x1800912f3  mov     cs:?gMaxSendBufferSizeLimit@@3KA, eax; ulong gMaxSendBufferSizeLimit
0x1800912f9  jmp     short loc_180091283
0x1800912fb  cmp     eax, 5
0x1800912fe  jnz     short loc_180091312
0x180091300  mov     ecx, edi
0x180091302  call    ?SetAutoPolicySettings@@YAXW4tagStateInformationPolicyValues@@@Z; SetAutoPolicySettings(tagStateInformationPolicyValues)
0x180091307  mov     cs:?g_fRestrictRemoteClients@@3IA, edi; uint g_fRestrictRemoteClients
0x18009130d  jmp     loc_180091070
0x180091312  mov     eax, 0Eh
0x180091317  jmp     loc_180091072
0x18009131c  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, ebx; int g_fServerSideDebugInfoEnabled
0x180091322  jmp     loc_1800910D0
0x180091327  mov     eax, [rbp+arg_0]
0x18009132a  test    eax, eax
0x18009132c  jz      loc_180091129
0x180091332  sub     eax, ebx
0x180091334  jz      short loc_180091367
0x180091336  sub     eax, ebx
0x180091338  jz      short loc_180091348
0x18009133a  cmp     eax, ebx
0x18009133c  jz      short loc_180091381
0x18009133e  mov     ebx, 6E6h
0x180091343  jmp     loc_1800911EE
0x180091348  mov     rcx, [rbp+hkey]; hkey
0x18009134c  lea     rdx, [rbp+arg_10]; int *
0x180091350  call    ?IsThisProcessAnException@@YAJPEAUHKEY__@@PEAH@Z; IsThisProcessAnException(HKEY__ *,int *)
0x180091355  test    eax, eax
0x180091357  jnz     loc_180091129
0x18009135d  cmp     [rbp+arg_10], ebx
0x180091360  jz      short loc_180091381
0x180091362  jmp     loc_180091129
0x180091367  mov     rcx, [rbp+hkey]; hkey
0x18009136b  lea     rdx, [rbp+arg_10]; int *
0x18009136f  call    ?IsThisProcessAnException@@YAJPEAUHKEY__@@PEAH@Z; IsThisProcessAnException(HKEY__ *,int *)
0x180091374  test    eax, eax
0x180091376  jnz     short loc_180091381
0x180091378  cmp     [rbp+arg_10], esi
0x18009137b  jnz     loc_180091129
0x180091381  mov     cs:?g_fSendEEInfo@@3HA, ebx; int g_fSendEEInfo
0x180091387  jmp     loc_180091129
```
