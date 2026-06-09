# GetEnclaveConfiguration

- ea: `0x100415f50`
- end: `0x100416181`
- name: `GetEnclaveConfiguration`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1004162d0`

## callees

- `0x100415f50`
- `0x1004403d0`
- `0x100440760`
- `0x10044cf40`

## import_xrefs

- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100415f7d`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100415f87`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100415ffc`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041601d`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100416090`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x1004160a6`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041612d`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100415f7d`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100415f87`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100415ffc`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041601d`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100416090`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x1004160a6`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041612d`
- `sqlTsEs!?GetEnclaveSetupConfigurationFromEnclaveType@CTrustedMachineHost@@SA?AUEnclaveConfiguration@@W4EAeEnclaveType@@_N@Z` at `0x1004160d4`
- `sqlTsEs!?GetEnclaveSetupConfigurationFromEnclaveType@CTrustedMachineHost@@SA?AUEnclaveConfiguration@@W4EAeEnclaveType@@_N@Z` at `0x1004160d4`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100415fc4`

## string_xrefs

- `0x100415fe3`: `Server enclave configuration has to be either SGX or VBS`
- `0x100415f9a`: `Server enclave configuration has to be either SGX or VBS or nothing`
- `0x100416121`: `Always Encrypted Enclave thread count exceeds max allowed for the enclave type\n`

## pseudocode

```c
__int64 __fastcall GetEnclaveConfiguration(__int64 a1)
{
  int v1; // r14d
  unsigned int v2; // ebx
  char v4; // si
  char v5; // cl
  bool v6; // bp
  bool v7; // al
  __int64 v8; // r8
  __int64 EnclaveSetupConfigurationFromEnclaveType; // rax
  __int64 v10; // xmm0_8
  int v12; // ecx
  _BYTE v13[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = 0;
  v2 = 0;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    v4 = *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 123);
    v5 = *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 121);
    if ( v4 == v5 && v5 )
    {
      scierrlog(0x91B9u, L"Server enclave configuration has to be either SGX or VBS or nothing");
    }
    else if ( v4 )
    {
      v2 = 1;
    }
    else if ( v5 )
    {
      v2 = 2;
    }
  }
  else
  {
    v2 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf)
                            + 1344);
    if ( v2 >= 3 )
    {
      scierrlog(0x91B9u, L"Server enclave configuration has to be either SGX or VBS");
      v2 = 0;
    }
  }
  v6 = *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 125) || (*(_BYTE *)(qword_10049F340 + 15) & 0x10) != 0;
  v7 = *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 122) || (*(_BYTE *)(qword_10049F340 + 22) & 4) != 0;
  if ( v2 )
  {
    if ( !v7 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( v6 )
  {
    if ( !v7 )
    {
      v2 = 3;
      goto LABEL_29;
    }
LABEL_26:
    scierrlog(0x91B9u, L"SGX Simulator traceflag overridden");
LABEL_27:
    if ( v6 )
      scierrlog(0x91B9u, L"VSM Simulator traceflag overridden");
    goto LABEL_29;
  }
  if ( v7 )
    v2 = 4;
LABEL_29:
  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 124) )
  {
    LOBYTE(v8) = (*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 118)
               || (*(_BYTE *)(qword_10049F340 + 15) & 8) != 0)
              && (*(_BYTE *)(qword_10049F340 + 16) & 0x40) == 0;
    EnclaveSetupConfigurationFromEnclaveType = CTrustedMachineHost::GetEnclaveSetupConfigurationFromEnclaveType(
                                                 v13,
                                                 v2,
                                                 v8);
    v10 = *(_QWORD *)EnclaveSetupConfigurationFromEnclaveType;
    LODWORD(EnclaveSetupConfigurationFromEnclaveType) = *(_DWORD *)(EnclaveSetupConfigurationFromEnclaveType + 8);
    *(_QWORD *)a1 = v10;
    *(_DWORD *)(a1 + 8) = EnclaveSetupConfigurationFromEnclaveType;
    return a1;
  }
  else
  {
    *(_DWORD *)a1 = v2;
    *(_BYTE *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 4) = 4;
    if ( v2 )
    {
      v12 = *((_DWORD *)qword_10045A690 + v2);
      if ( v12 < 4 )
      {
        *(_DWORD *)(a1 + 4) = v12;
        LogSystemMetadata(L"Always Encrypted Enclave thread count exceeds max allowed for the enclave type\n");
      }
      if ( !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 118)
        && (*(_BYTE *)(qword_10049F340 + 15) & 8) == 0
        || (*(_BYTE *)(qword_10049F340 + 16) & 0x40) != 0 )
      {
        *(_DWORD *)(a1 + 4) = 1;
      }
    }
    LOBYTE(v1) = SOS_OS::GetCPUCorePercentCap() > 100.0;
    if ( !v1 )
      *(_BYTE *)(a1 + 8) = 1;
    return a1;
  }
}

```

## disassembly

```asm
0x100415f50  mov     [rsp+arg_10], rbx
0x100415f55  mov     [rsp+arg_18], rdi
0x100415f5a  push    r14
0x100415f5c  sub     rsp, 30h
0x100415f60  mov     rax, cs:qword_10049F360
0x100415f67  xor     r14d, r14d
0x100415f6a  mov     ebx, r14d
0x100415f6d  mov     [rsp+38h+arg_8], rsi
0x100415f72  mov     rdi, rcx
0x100415f75  cmp     [rax+38A8h], ebx
0x100415f7b  jz      short loc_100415FC4
0x100415f7d  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100415f83  movzx   esi, byte ptr [rax+7Bh]
0x100415f87  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100415f8d  movzx   ecx, byte ptr [rax+79h]
0x100415f91  cmp     sil, cl
0x100415f94  jnz     short loc_100415FAD
0x100415f96  test    cl, cl
0x100415f98  jz      short loc_100415FAD
0x100415f9a  lea     rdx, aServerEnclaveC; "Server enclave configuration has to be "...
0x100415fa1  mov     ecx, 91B9h; unsigned int
0x100415fa6  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100415fab  jmp     short loc_100415FF7
0x100415fad  test    sil, sil
0x100415fb0  jz      short loc_100415FB9
0x100415fb2  mov     ebx, 1
0x100415fb7  jmp     short loc_100415FF7
0x100415fb9  test    cl, cl
0x100415fbb  jz      short loc_100415FF7
0x100415fbd  mov     ebx, 2
0x100415fc2  jmp     short loc_100415FF7
0x100415fc4  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100415fcb  mov     rcx, [rax]
0x100415fce  mov     rax, [rcx]
0x100415fd1  call    qword ptr [rax+1F8h]
0x100415fd7  movzx   ebx, byte ptr [rax+540h]
0x100415fde  cmp     ebx, 3
0x100415fe1  jb      short loc_100415FF7
0x100415fe3  lea     rdx, aServerEnclaveC_0; "Server enclave configuration has to be "...
0x100415fea  mov     ecx, 91B9h; unsigned int
0x100415fef  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100415ff4  mov     ebx, r14d
0x100415ff7  mov     [rsp+38h+arg_0], rbp
0x100415ffc  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100416002  cmp     [rax+7Dh], r14b
0x100416006  jnz     short loc_10041601A
0x100416008  mov     rax, cs:qword_10049F340
0x10041600f  test    byte ptr [rax+0Fh], 10h
0x100416013  jnz     short loc_10041601A
0x100416015  xor     bpl, bpl
0x100416018  jmp     short loc_10041601D
0x10041601a  mov     bpl, 1
0x10041601d  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100416023  cmp     [rax+7Ah], r14b
0x100416027  jnz     short loc_10041603A
0x100416029  mov     rax, cs:qword_10049F340
0x100416030  test    byte ptr [rax+16h], 4
0x100416034  jnz     short loc_10041603A
0x100416036  xor     al, al
0x100416038  jmp     short loc_10041603C
0x10041603a  mov     al, 1
0x10041603c  test    ebx, ebx
0x10041603e  jnz     short loc_10041605B
0x100416040  test    bpl, bpl
0x100416043  jz      short loc_100416050
0x100416045  test    al, al
0x100416047  jnz     short loc_100416064
0x100416049  mov     ebx, 3
0x10041604e  jmp     short loc_100416090
0x100416050  test    al, al
0x100416052  jz      short loc_100416090
0x100416054  mov     ebx, 4
0x100416059  jmp     short loc_100416090
0x10041605b  test    al, al
0x10041605d  jz      short loc_100416075
0x10041605f  cmp     ebx, 4
0x100416062  jz      short loc_100416075
0x100416064  lea     rdx, aSgxSimulatorTr; "SGX Simulator traceflag overridden"
0x10041606b  mov     ecx, 91B9h; unsigned int
0x100416070  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100416075  test    bpl, bpl
0x100416078  jz      short loc_100416090
0x10041607a  cmp     ebx, 3
0x10041607d  jz      short loc_100416090
0x10041607f  lea     rdx, aVsmSimulatorTr; "VSM Simulator traceflag overridden"
0x100416086  mov     ecx, 91B9h; unsigned int
0x10041608b  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100416090  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100416096  mov     rsi, [rsp+38h+arg_8]
0x10041609b  mov     rbp, [rsp+38h+arg_0]
0x1004160a0  cmp     [rax+7Ch], r14b
0x1004160a4  jz      short loc_1004160FC
0x1004160a6  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x1004160ac  mov     rcx, cs:qword_10049F340
0x1004160b3  cmp     [rax+76h], r14b
0x1004160b7  jnz     short loc_1004160BF
0x1004160b9  test    byte ptr [rcx+0Fh], 8
0x1004160bd  jz      short loc_1004160CA
0x1004160bf  test    byte ptr [rcx+10h], 40h
0x1004160c3  jnz     short loc_1004160CA
0x1004160c5  mov     r8b, 1
0x1004160c8  jmp     short loc_1004160CD
0x1004160ca  xor     r8b, r8b
0x1004160cd  mov     edx, ebx
0x1004160cf  lea     rcx, [rsp+38h+var_18]
0x1004160d4  call    cs:__imp_?GetEnclaveSetupConfigurationFromEnclaveType@CTrustedMachineHost@@SA?AUEnclaveConfiguration@@W4EAeEnclaveType@@_N@Z; CTrustedMachineHost::GetEnclaveSetupConfigurationFromEnclaveType(EAeEnclaveType,bool)
0x1004160da  movsd   xmm0, qword ptr [rax]
0x1004160de  mov     eax, [rax+8]
0x1004160e1  movsd   qword ptr [rdi], xmm0
0x1004160e5  mov     [rdi+8], eax
0x1004160e8  mov     rax, rdi
0x1004160eb  mov     rbx, [rsp+38h+arg_10]
0x1004160f0  mov     rdi, [rsp+38h+arg_18]
0x1004160f5  add     rsp, 30h
0x1004160f9  pop     r14
0x1004160fb  retn
0x1004160fc  mov     [rdi], ebx
0x1004160fe  mov     [rdi+8], r14b
0x100416102  mov     dword ptr [rdi+4], 4
0x100416109  test    ebx, ebx
0x10041610b  jz      short loc_100416153
0x10041610d  mov     eax, ebx
0x10041610f  lea     rcx, qword_10045A690
0x100416116  mov     ecx, [rcx+rax*4]
0x100416119  cmp     ecx, 4
0x10041611c  jge     short loc_10041612D
0x10041611e  mov     [rdi+4], ecx
0x100416121  lea     rcx, aAlwaysEncrypte; "Always Encrypted Enclave thread count e"...
0x100416128  call    ?LogSystemMetadata@@YAXPEB_WZZ; LogSystemMetadata(wchar_t const *,...)
0x10041612d  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100416133  mov     rcx, cs:qword_10049F340
0x10041613a  cmp     [rax+76h], r14b
0x10041613e  jnz     short loc_100416146
0x100416140  test    byte ptr [rcx+0Fh], 8
0x100416144  jz      short loc_10041614C
0x100416146  test    byte ptr [rcx+10h], 40h
0x10041614a  jz      short loc_100416153
0x10041614c  mov     dword ptr [rdi+4], 1
0x100416153  call    ?GetCPUCorePercentCap@SOS_OS@@SANXZ; SOS_OS::GetCPUCorePercentCap(void)
0x100416158  comisd  xmm0, cs:__real@4059000000000000
0x100416160  setnbe  r14b
0x100416164  test    r14d, r14d
0x100416167  jnz     short loc_10041616D
0x100416169  mov     byte ptr [rdi+8], 1
0x10041616d  mov     rbx, [rsp+38h+arg_10]
0x100416172  mov     rax, rdi
0x100416175  mov     rdi, [rsp+38h+arg_18]
0x10041617a  add     rsp, 30h
0x10041617e  pop     r14
0x100416180  retn
```
