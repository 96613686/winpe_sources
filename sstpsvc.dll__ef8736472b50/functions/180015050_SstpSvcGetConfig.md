# SstpSvcGetConfig

- ea: `0x180015050`
- end: `0x1800151d3`
- name: `SstpSvcGetConfig`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x180015050`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180015157`
- `RPCRT4!RpcRevertToSelf` at `0x180015157`
- `RPCRT4!RpcImpersonateClient` at `0x1800150a8`
- `RPCRT4!RpcImpersonateClient` at `0x1800150a8`
- `sstpcfg!GetSstpProxyConfig` at `0x18001510a`
- `sstpcfg!GetSstpProxyConfig` at `0x18001510a`
- `sstpcfg!GetSstpConfiguration` at `0x180015122`
- `sstpcfg!GetSstpConfiguration` at `0x180015122`

## string_xrefs

- `0x180015172`: `SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d`
- `0x1800150c9`: `SstpSvcGetConfig: RpcImpersonateClient failed with error %d`
- `0x18001513f`: `SstpSvcGetConfig: GetSstpConfiguration failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcGetConfig(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax
  unsigned int SstpConfiguration; // ebx
  int v6; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v7[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  v3 = RpcImpersonateClient(0);
  SstpConfiguration = v3;
  if ( v3 )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_10;
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"SstpSvcGetConfig: RpcImpersonateClient failed with error %d", v3);
    goto LABEL_4;
  }
  GetSstpProxyConfig(0, a2);
  SstpConfiguration = GetSstpConfiguration(0, 0, a2 + 16, a2 + 4, v6);
  if ( !SstpConfiguration )
  {
    *(_DWORD *)(a2 + 8) = 32780;
    goto LABEL_10;
  }
  if ( (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"SstpSvcGetConfig: GetSstpConfiguration failed with error %d", SstpConfiguration);
LABEL_4:
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
  }
LABEL_10:
  if ( RpcRevertToSelf() )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(
        &v6,
        L"SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d",
        SstpConfiguration);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
  }
  return SstpConfiguration;
}

```

## disassembly

```asm
0x180015050  mov     [rsp-8+arg_0], rbx
0x180015055  mov     [rsp-8+arg_10], rdi
0x18001505a  push    rbp
0x18001505b  lea     rbp, [rsp-730h]
0x180015063  sub     rsp, 830h
0x18001506a  mov     rax, cs:__security_cookie
0x180015071  xor     rax, rsp
0x180015074  mov     [rbp+730h+var_10], rax
0x18001507b  mov     rdi, rdx
0x18001507e  lea     rcx, [rsp+830h+var_80C]; void *
0x180015083  xor     eax, eax
0x180015085  xor     edx, edx; Val
0x180015087  mov     r8d, 7FCh; Size
0x18001508d  mov     [rsp+830h+var_810], eax
0x180015091  call    memset_0
0x180015096  xorps   xmm0, xmm0
0x180015099  xor     eax, eax
0x18001509b  movups  xmmword ptr [rdi], xmm0
0x18001509e  xor     ecx, ecx; BindingHandle
0x1800150a0  movups  xmmword ptr [rdi+10h], xmm0
0x1800150a4  mov     [rdi+20h], rax
0x1800150a8  call    cs:__imp_RpcImpersonateClient
0x1800150af  nop     dword ptr [rax+rax+00h]
0x1800150b4  mov     ebx, eax
0x1800150b6  test    eax, eax
0x1800150b8  jz      short loc_180015105
0x1800150ba  test    cs:byte_18002E903, 8
0x1800150c1  jz      loc_180015157
0x1800150c7  xor     ecx, ecx
0x1800150c9  lea     rdx, aSstpsvcgetconf_1; "SstpSvcGetConfig: RpcImpersonateClient "...
0x1800150d0  mov     word ptr [rsp+830h+var_810], cx
0x1800150d5  mov     r8d, eax
0x1800150d8  lea     rcx, [rsp+830h+var_810]
0x1800150dd  call    FormatRRASErrorString
0x1800150e2  test    cs:byte_18002E903, 8
0x1800150e9  jz      short loc_180015157
0x1800150eb  lea     r8, [rsp+830h+var_810]
0x1800150f0  lea     rdx, RasSSTPSvcTraceError
0x1800150f7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800150fe  call    McTemplateU0z_EventWriteTransfer
0x180015103  jmp     short loc_180015157
0x180015105  mov     rdx, rdi
0x180015108  xor     ecx, ecx
0x18001510a  call    cs:__imp_GetSstpProxyConfig
0x180015111  nop     dword ptr [rax+rax+00h]
0x180015116  lea     r9, [rdi+4]
0x18001511a  xor     edx, edx
0x18001511c  lea     r8, [rdi+10h]
0x180015120  xor     ecx, ecx
0x180015122  call    cs:__imp_GetSstpConfiguration
0x180015129  nop     dword ptr [rax+rax+00h]
0x18001512e  mov     ebx, eax
0x180015130  test    eax, eax
0x180015132  jz      short loc_180015150
0x180015134  test    cs:byte_18002E903, 8
0x18001513b  jz      short loc_180015157
0x18001513d  xor     eax, eax
0x18001513f  lea     rdx, aSstpsvcgetconf; "SstpSvcGetConfig: GetSstpConfiguration "...
0x180015146  mov     word ptr [rsp+830h+var_810], ax
0x18001514b  mov     r8d, ebx
0x18001514e  jmp     short loc_1800150D8
0x180015150  mov     dword ptr [rdi+8], 800Ch
0x180015157  call    cs:__imp_RpcRevertToSelf
0x18001515e  nop     dword ptr [rax+rax+00h]
0x180015163  test    eax, eax
0x180015165  jz      short loc_1800151AC
0x180015167  test    cs:byte_18002E903, 8
0x18001516e  jz      short loc_1800151AC
0x180015170  xor     eax, eax
0x180015172  lea     rdx, aSstpsvcgetconf_0; "SstpSvcGetConfig: FATAL ERROR. RpcRever"...
0x180015179  mov     r8d, ebx
0x18001517c  mov     word ptr [rsp+830h+var_810], ax
0x180015181  lea     rcx, [rsp+830h+var_810]
0x180015186  call    FormatRRASErrorString
0x18001518b  test    cs:byte_18002E903, 8
0x180015192  jz      short loc_1800151AC
0x180015194  lea     r8, [rsp+830h+var_810]
0x180015199  lea     rdx, RasSSTPSvcTraceError
0x1800151a0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800151a7  call    McTemplateU0z_EventWriteTransfer
0x1800151ac  mov     eax, ebx
0x1800151ae  mov     rcx, [rbp+730h+var_10]
0x1800151b5  xor     rcx, rsp; StackCookie
0x1800151b8  call    __security_check_cookie
0x1800151bd  lea     r11, [rsp+830h+var_s0]
0x1800151c5  mov     rbx, [r11+10h]
0x1800151c9  mov     rdi, [r11+20h]
0x1800151cd  mov     rsp, r11
0x1800151d0  pop     rbp
0x1800151d1  retn
```
