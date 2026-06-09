# ReadPolicySettings(void)

- ea: `0x1800955b0`
- end: `0x180095967`
- name: `?ReadPolicySettings@@YAJXZ`
- size: `951`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800258b4`

## callees

- `0x1800955b0`
- `0x180095970`
- `0x1800b6af0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800955f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800955f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800957bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800957bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095653`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800956c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095707`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095751`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095794`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095840`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095883`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095653`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800956c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095707`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095751`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095794`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095840`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095883`

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
0x1800955b0  push    rbp
0x1800955b2  push    rbx
0x1800955b3  push    rsi
0x1800955b4  push    rdi
0x1800955b5  push    r14
0x1800955b7  push    r15
0x1800955b9  mov     rbp, rsp
0x1800955bc  sub     rsp, 48h
0x1800955c0  xor     esi, esi
0x1800955c2  lea     rax, [rbp+hkey]
0x1800955c6  mov     r9d, 20019h; samDesired
0x1800955cc  mov     [rbp+hkey], rsi
0x1800955d0  xor     r8d, r8d; ulOptions
0x1800955d3  mov     [rbp+arg_0], esi
0x1800955d6  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800955dd  mov     [rbp+arg_10], esi
0x1800955e0  lea     r14d, [rsi+4]
0x1800955e4  mov     [rsp+48h+phkResult], rax; phkResult
0x1800955e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800955f0  mov     [rbp+arg_8], r14d
0x1800955f4  call    cs:__imp_RegOpenKeyExW
0x1800955fb  nop     dword ptr [rax+rax+00h]
0x180095600  test    eax, eax
0x180095602  jz      short loc_180095626
0x180095604  lea     edi, [rsi+2]
0x180095607  cmp     eax, edi
0x180095609  jnz     loc_1800958D6
0x18009560f  mov     ecx, edi
0x180095611  call    ?SetAutoPolicySettings@@YAXW4tagStateInformationPolicyValues@@@Z; SetAutoPolicySettings(tagStateInformationPolicyValues)
0x180095616  xor     eax, eax
0x180095618  add     rsp, 48h
0x18009561c  pop     r15
0x18009561e  pop     r14
0x180095620  pop     rdi
0x180095621  pop     rsi
0x180095622  pop     rbx
0x180095623  pop     rbp
0x180095624  retn
0x180095626  mov     rcx, [rbp+hkey]; hkey
0x18009562a  lea     rax, [rbp+arg_8]
0x18009562e  mov     [rsp+48h+pcbData], rax; pcbData
0x180095633  lea     r8, aStateinformati; "StateInformation"
0x18009563a  lea     rax, [rbp+arg_0]
0x18009563e  mov     r15d, 18h
0x180095644  mov     [rsp+48h+pvData], rax; pvData
0x180095649  mov     r9d, r15d; dwFlags
0x18009564c  xor     edx, edx; lpSubKey
0x18009564e  mov     [rsp+48h+phkResult], rsi; pdwType
0x180095653  call    cs:__imp_RegGetValueW
0x18009565a  nop     dword ptr [rax+rax+00h]
0x18009565f  lea     edi, [r15-16h]
0x180095663  lea     ebx, [rdi-1]
0x180095666  test    eax, eax
0x180095668  jz      loc_1800957CE
0x18009566e  cmp     eax, edi
0x180095670  jnz     loc_1800957B2
0x180095676  mov     ecx, edi
0x180095678  call    ?SetAutoPolicySettings@@YAXW4tagStateInformationPolicyValues@@@Z; SetAutoPolicySettings(tagStateInformationPolicyValues)
0x18009567d  mov     rax, gs:60h
0x180095686  mov     rcx, [rax+20h]
0x18009568a  cmp     [rcx+8], esi
0x18009568d  jge     short loc_180095695
0x18009568f  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, esi; int g_fServerSideDebugInfoEnabled
0x180095695  mov     rcx, [rbp+hkey]; hkey
0x180095699  lea     rax, [rbp+arg_8]
0x18009569d  mov     [rsp+48h+pcbData], rax; pcbData
0x1800956a2  lea     r8, aExterrorinform; "ExtErrorInformation"
0x1800956a9  lea     rax, [rbp+arg_0]
0x1800956ad  mov     [rbp+arg_8], r14d
0x1800956b1  mov     [rsp+48h+pvData], rax; pvData
0x1800956b6  mov     r9d, r15d; dwFlags
0x1800956b9  xor     edx, edx; lpSubKey
0x1800956bb  mov     [rsp+48h+phkResult], rsi; pdwType
0x1800956c0  call    cs:__imp_RegGetValueW
0x1800956c7  nop     dword ptr [rax+rax+00h]
0x1800956cc  test    eax, eax
0x1800956ce  jz      loc_180095902
0x1800956d4  cmp     eax, edi
0x1800956d6  jnz     loc_1800957B2
0x1800956dc  mov     rcx, [rbp+hkey]; hkey
0x1800956e0  lea     rax, [rbp+arg_8]
0x1800956e4  mov     [rsp+48h+pcbData], rax; pcbData
0x1800956e9  lea     r8, aIgnoredelegati; "IgnoreDelegationFailure"
0x1800956f0  lea     rax, [rbp+arg_0]
0x1800956f4  mov     [rbp+arg_8], r14d
0x1800956f8  mov     [rsp+48h+pvData], rax; pvData
0x1800956fd  mov     r9d, r15d; dwFlags
0x180095700  xor     edx, edx; lpSubKey
0x180095702  mov     [rsp+48h+phkResult], rsi; pdwType
0x180095707  call    cs:__imp_RegGetValueW
0x18009570e  nop     dword ptr [rax+rax+00h]
0x180095713  test    eax, eax
0x180095715  jnz     loc_1800957AA
0x18009571b  cmp     [rbp+arg_0], esi
0x18009571e  jz      short loc_180095726
0x180095720  mov     cs:?g_fIgnoreDelegationFailure@@3HA, ebx; int g_fIgnoreDelegationFailure
0x180095726  mov     rcx, [rbp+hkey]; hkey
0x18009572a  lea     rax, [rbp+arg_8]
0x18009572e  mov     [rsp+48h+pcbData], rax; pcbData
0x180095733  lea     r8, aRestrictremote; "RestrictRemoteClients"
0x18009573a  lea     rax, [rbp+arg_0]
0x18009573e  mov     [rbp+arg_8], r14d
0x180095742  mov     [rsp+48h+pvData], rax; pvData
0x180095747  mov     r9d, r15d; dwFlags
0x18009574a  xor     edx, edx; lpSubKey
0x18009574c  mov     [rsp+48h+phkResult], rsi; pdwType
0x180095751  call    cs:__imp_RegGetValueW
0x180095758  nop     dword ptr [rax+rax+00h]
0x18009575d  test    eax, eax
0x18009575f  jz      loc_1800958A7
0x180095765  cmp     eax, edi
0x180095767  jnz     short loc_1800957B2
0x180095769  mov     rcx, [rbp+hkey]; hkey
0x18009576d  lea     rax, [rbp+arg_8]
0x180095771  mov     [rsp+48h+pcbData], rax; pcbData
0x180095776  lea     r8, aEnableauthepre; "EnableAuthEpResolution"
0x18009577d  lea     rax, [rbp+arg_0]
0x180095781  mov     [rbp+arg_8], r14d
0x180095785  mov     [rsp+48h+pvData], rax; pvData
0x18009578a  mov     r9d, r15d; dwFlags
0x18009578d  xor     edx, edx; lpSubKey
0x18009578f  mov     [rsp+48h+phkResult], rsi; pdwType
0x180095794  call    cs:__imp_RegGetValueW
0x18009579b  nop     dword ptr [rax+rax+00h]
0x1800957a0  test    eax, eax
0x1800957a2  jz      short loc_18009580C
0x1800957a4  cmp     eax, edi
0x1800957a6  jnz     short loc_1800957B2
0x1800957a8  jmp     short loc_180095815
0x1800957aa  cmp     eax, edi
0x1800957ac  jz      loc_180095726
0x1800957b2  mov     ebx, 0Eh
0x1800957b7  mov     rcx, [rbp+hkey]; hKey
0x1800957bb  call    cs:__imp_RegCloseKey
0x1800957c2  nop     dword ptr [rax+rax+00h]
0x1800957c7  mov     eax, ebx
0x1800957c9  jmp     loc_180095618
0x1800957ce  mov     ecx, [rbp+arg_0]
0x1800957d1  mov     eax, ecx
0x1800957d3  test    ecx, ecx
0x1800957d5  jz      loc_18009567D
0x1800957db  sub     eax, ebx
0x1800957dd  jz      loc_180095678
0x1800957e3  sub     eax, ebx
0x1800957e5  jz      loc_180095678
0x1800957eb  sub     eax, ebx
0x1800957ed  jz      loc_1800958F7
0x1800957f3  cmp     eax, ebx
0x1800957f5  jnz     loc_180095919
0x1800957fb  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, ebx; int g_fServerSideDebugInfoEnabled
0x180095801  mov     cs:?g_fClientSideDebugInfoEnabled@@3HA, ebx; int g_fClientSideDebugInfoEnabled
0x180095807  jmp     loc_18009567D
0x18009580c  mov     eax, [rbp+arg_0]
0x18009580f  mov     cs:?g_fAuthenticatedEpResolution@@3HA, eax; int g_fAuthenticatedEpResolution
0x180095815  mov     rcx, [rbp+hkey]; hkey
0x180095819  lea     rax, [rbp+arg_8]
0x18009581d  mov     [rsp+48h+pcbData], rax; pcbData
0x180095822  lea     r8, aMaxnonpagedpoo; "MaxNonPagedPoolPerConnection"
0x180095829  lea     rax, [rbp+arg_0]
0x18009582d  mov     [rbp+arg_8], r14d
0x180095831  mov     [rsp+48h+pvData], rax; pvData
0x180095836  mov     r9d, r15d; dwFlags
0x180095839  xor     edx, edx; lpSubKey
0x18009583b  mov     [rsp+48h+phkResult], rsi; pdwType
0x180095840  call    cs:__imp_RegGetValueW
0x180095847  nop     dword ptr [rax+rax+00h]
0x18009584c  test    eax, eax
0x18009584e  jz      short loc_1800958CB
0x180095850  cmp     eax, edi
0x180095852  jnz     loc_1800957B2
0x180095858  mov     rcx, [rbp+hkey]; hkey
0x18009585c  lea     rax, [rbp+arg_8]
0x180095860  mov     [rsp+48h+pcbData], rax; pcbData
0x180095865  lea     r8, aEnabletcpports; "EnableTcpPortScaling"
0x18009586c  lea     rax, [rbp+arg_0]
0x180095870  mov     [rbp+arg_8], r14d
0x180095874  mov     [rsp+48h+pvData], rax; pvData
0x180095879  mov     r9d, r15d; dwFlags
0x18009587c  xor     edx, edx; lpSubKey
0x18009587e  mov     [rsp+48h+phkResult], rsi; pdwType
0x180095883  call    cs:__imp_RegGetValueW
0x18009588a  nop     dword ptr [rax+rax+00h]
0x18009588f  mov     ebx, eax
0x180095891  test    eax, eax
0x180095893  jz      short loc_1800958BD
0x180095895  sub     ebx, edi
0x180095897  neg     ebx
0x180095899  mov     ebx, 0Eh
0x18009589e  sbb     eax, eax
0x1800958a0  and     ebx, eax
0x1800958a2  jmp     loc_1800957B7
0x1800958a7  mov     eax, [rbp+arg_0]
0x1800958aa  cmp     eax, edi
0x1800958ac  ja      loc_180095769
0x1800958b2  mov     cs:?g_fRestrictRemoteClients@@3IA, eax; uint g_fRestrictRemoteClients
0x1800958b8  jmp     loc_180095769
0x1800958bd  mov     eax, [rbp+arg_0]
0x1800958c0  mov     cs:?gEnableTcpPortScaling@@3KA, eax; ulong gEnableTcpPortScaling
0x1800958c6  jmp     loc_1800957B7
0x1800958cb  mov     eax, [rbp+arg_0]
0x1800958ce  mov     cs:?gMaxSendBufferSizeLimit@@3KA, eax; ulong gMaxSendBufferSizeLimit
0x1800958d4  jmp     short loc_180095858
0x1800958d6  cmp     eax, 5
0x1800958d9  jnz     short loc_1800958ED
0x1800958db  mov     ecx, edi
0x1800958dd  call    ?SetAutoPolicySettings@@YAXW4tagStateInformationPolicyValues@@@Z; SetAutoPolicySettings(tagStateInformationPolicyValues)
0x1800958e2  mov     cs:?g_fRestrictRemoteClients@@3IA, edi; uint g_fRestrictRemoteClients
0x1800958e8  jmp     loc_180095616
0x1800958ed  mov     eax, 0Eh
0x1800958f2  jmp     loc_180095618
0x1800958f7  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, ebx; int g_fServerSideDebugInfoEnabled
0x1800958fd  jmp     loc_18009567D
0x180095902  mov     eax, [rbp+arg_0]
0x180095905  test    eax, eax
0x180095907  jz      loc_1800956DC
0x18009590d  sub     eax, ebx
0x18009590f  jz      short loc_180095942
0x180095911  sub     eax, ebx
0x180095913  jz      short loc_180095923
0x180095915  cmp     eax, ebx
0x180095917  jz      short loc_18009595C
0x180095919  mov     ebx, 6E6h
0x18009591e  jmp     loc_1800957B7
0x180095923  mov     rcx, [rbp+hkey]; hkey
0x180095927  lea     rdx, [rbp+arg_10]; int *
0x18009592b  call    ?IsThisProcessAnException@@YAJPEAUHKEY__@@PEAH@Z; IsThisProcessAnException(HKEY__ *,int *)
0x180095930  test    eax, eax
0x180095932  jnz     loc_1800956DC
0x180095938  cmp     [rbp+arg_10], ebx
0x18009593b  jz      short loc_18009595C
0x18009593d  jmp     loc_1800956DC
0x180095942  mov     rcx, [rbp+hkey]; hkey
0x180095946  lea     rdx, [rbp+arg_10]; int *
0x18009594a  call    ?IsThisProcessAnException@@YAJPEAUHKEY__@@PEAH@Z; IsThisProcessAnException(HKEY__ *,int *)
0x18009594f  test    eax, eax
0x180095951  jnz     short loc_18009595C
0x180095953  cmp     [rbp+arg_10], esi
0x180095956  jnz     loc_1800956DC
0x18009595c  mov     cs:?g_fSendEEInfo@@3HA, ebx; int g_fSendEEInfo
0x180095962  jmp     loc_1800956DC
```
