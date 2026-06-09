# TetheringService::InitializeCellularWnfSubscriptions(void)

- ea: `0x180019ec0`
- end: `0x180019fd5`
- name: `?InitializeCellularWnfSubscriptions@TetheringService@@AEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001e4a4`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x1800162dc`
- `0x18001650c`
- `0x18001670c`
- `0x180019ec0`
- `0x180020bd8`
- `0x180029c10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TetheringService::InitializeCellularWnfSubscriptions(TetheringService *this)
{
  unsigned int v2; // ebx
  int CanConfigurationSubscription; // eax
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v2 = 1;
  if ( IsMobile() )
  {
    CanConfigurationSubscription = TetheringService::ConfigureCellularDataSubscription(this);
    v2 = CanConfigurationSubscription;
    if ( CanConfigurationSubscription >= 0 )
    {
      CanConfigurationSubscription = TetheringService::ConfigureCellularCanConfigurationSubscription(this);
      v2 = CanConfigurationSubscription;
      if ( CanConfigurationSubscription >= 0 )
      {
        CanConfigurationSubscription = TetheringService::ConfigureCellularImsiSubscription(this);
        v2 = CanConfigurationSubscription;
        if ( CanConfigurationSubscription >= 0 )
        {
          *((_BYTE *)this + 1665) = 1;
          goto LABEL_20;
        }
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_18;
        }
        v5 = 327;
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_18;
        }
        v5 = 326;
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_18;
      }
      v5 = 325;
    }
    WPP_SF_d(
      *((_QWORD *)v4 + 2),
      v5,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)CanConfigurationSubscription);
LABEL_18:
    TetheringService::UninitializeCellularWnfSubscriptions(this);
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180019ec0  push    rbx
0x180019ec2  push    rbp
0x180019ec3  push    rdi
0x180019ec4  push    r14
0x180019ec6  sub     rsp, 28h
0x180019eca  mov     rdi, rcx
0x180019ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ed4  lea     rbp, WPP_GLOBAL_Control
0x180019edb  lea     r14, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019ee2  cmp     rcx, rbp
0x180019ee5  jz      short loc_180019EFE
0x180019ee7  test    byte ptr [rcx+1Ch], 8
0x180019eeb  jz      short loc_180019EFE
0x180019eed  mov     rcx, [rcx+10h]
0x180019ef1  mov     edx, 144h
0x180019ef6  mov     r8, r14
0x180019ef9  call    WPP_SF_
0x180019efe  mov     ebx, 1
0x180019f03  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x180019f08  test    al, al
0x180019f0a  jz      loc_180019FA3
0x180019f10  mov     rcx, rdi; this
0x180019f13  call    ?ConfigureCellularDataSubscription@TetheringService@@AEAAJXZ; TetheringService::ConfigureCellularDataSubscription(void)
0x180019f18  mov     ebx, eax
0x180019f1a  test    eax, eax
0x180019f1c  jns     short loc_180019F37
0x180019f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f25  cmp     rcx, rbp
0x180019f28  jz      short loc_180019F92
0x180019f2a  test    byte ptr [rcx+1Ch], 1
0x180019f2e  jz      short loc_180019F92
0x180019f30  mov     edx, 145h
0x180019f35  jmp     short loc_180019F83
0x180019f37  mov     rcx, rdi; this
0x180019f3a  call    ?ConfigureCellularCanConfigurationSubscription@TetheringService@@AEAAJXZ; TetheringService::ConfigureCellularCanConfigurationSubscription(void)
0x180019f3f  mov     ebx, eax
0x180019f41  test    eax, eax
0x180019f43  jns     short loc_180019F5E
0x180019f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f4c  cmp     rcx, rbp
0x180019f4f  jz      short loc_180019F92
0x180019f51  test    byte ptr [rcx+1Ch], 1
0x180019f55  jz      short loc_180019F92
0x180019f57  mov     edx, 146h
0x180019f5c  jmp     short loc_180019F83
0x180019f5e  mov     rcx, rdi; this
0x180019f61  call    ?ConfigureCellularImsiSubscription@TetheringService@@AEAAJXZ; TetheringService::ConfigureCellularImsiSubscription(void)
0x180019f66  mov     ebx, eax
0x180019f68  test    eax, eax
0x180019f6a  jns     short loc_180019F9C
0x180019f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f73  cmp     rcx, rbp
0x180019f76  jz      short loc_180019F92
0x180019f78  test    byte ptr [rcx+1Ch], 1
0x180019f7c  jz      short loc_180019F92
0x180019f7e  mov     edx, 147h
0x180019f83  mov     rcx, [rcx+10h]
0x180019f87  mov     r9d, eax
0x180019f8a  mov     r8, r14
0x180019f8d  call    WPP_SF_d
0x180019f92  mov     rcx, rdi; this
0x180019f95  call    ?UninitializeCellularWnfSubscriptions@TetheringService@@AEAAXXZ; TetheringService::UninitializeCellularWnfSubscriptions(void)
0x180019f9a  jmp     short loc_180019FA3
0x180019f9c  mov     byte ptr [rdi+681h], 1
0x180019fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180019faa  cmp     rcx, rbp
0x180019fad  jz      short loc_180019FC9
0x180019faf  test    byte ptr [rcx+1Ch], 8
0x180019fb3  jz      short loc_180019FC9
0x180019fb5  mov     rcx, [rcx+10h]
0x180019fb9  mov     edx, 148h
0x180019fbe  mov     r9d, ebx
0x180019fc1  mov     r8, r14
0x180019fc4  call    WPP_SF_d
0x180019fc9  mov     eax, ebx
0x180019fcb  add     rsp, 28h
0x180019fcf  pop     r14
0x180019fd1  pop     rdi
0x180019fd2  pop     rbp
0x180019fd3  pop     rbx
0x180019fd4  retn
```
