# AutoProxyServiceInitialize(void)

- ea: `0x18007311c`
- end: `0x1800734c6`
- name: `?AutoProxyServiceInitialize@@YAKXZ`
- size: `938`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180072a78`

## callees

- `0x18007311c`
- `0x1800734cc`
- `0x1800a1d10`
- `0x1800db6b0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180073349`
- `RPCRT4!RpcStringFreeW` at `0x180073349`
- `RPCRT4!RpcStringBindingComposeW` at `0x18007318a`
- `RPCRT4!RpcStringBindingComposeW` at `0x18007318a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800731b9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18007327c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800731b9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18007327c`
- `RPCRT4!RpcBindingFree` at `0x18007343c`
- `RPCRT4!RpcBindingFree` at `0x180073486`
- `RPCRT4!RpcBindingFree` at `0x1800734ac`
- `RPCRT4!RpcBindingFree` at `0x1800734bb`
- `RPCRT4!RpcBindingFree` at `0x18007343c`
- `RPCRT4!RpcBindingFree` at `0x180073486`
- `RPCRT4!RpcBindingFree` at `0x1800734ac`
- `RPCRT4!RpcBindingFree` at `0x1800734bb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180073215`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800732d0`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180073215`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800732d0`
- `RPCRT4!RpcBindingSetOption` at `0x18007322f`
- `RPCRT4!RpcBindingSetOption` at `0x1800732ea`
- `RPCRT4!RpcBindingSetOption` at `0x18007322f`
- `RPCRT4!RpcBindingSetOption` at `0x1800732ea`

## pseudocode

```c
__int64 AutoProxyServiceInitialize(void)
{
  unsigned int v0; // eax
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  RPC_WSTR Options; // [rsp+20h] [rbp-59h]
  RPC_WSTR Optionsa; // [rsp+20h] [rbp-59h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-39h] BYREF
  RPC_BINDING_HANDLE v14; // [rsp+48h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE v15; // [rsp+50h] [rbp-29h] BYREF
  RPC_WSTR String; // [rsp+58h] [rbp-21h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+60h] [rbp-19h] BYREF
  __int128 v18; // [rsp+70h] [rbp-9h]
  __int128 v19; // [rsp+80h] [rbp+7h]

  String = 0;
  v14 = 0;
  v15 = 0;
  v0 = CheckProcessIsLowBox();
  if ( (xmmword_180107A50 & 2) != 0 )
    WPP_SF_d(513, 26, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v0, Options);
  v1 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v2 = v1;
  if ( v1 )
  {
    if ( (xmmword_180107A50 & 2) == 0 )
      goto LABEL_20;
    v6 = 27;
    v7 = v1;
    goto LABEL_37;
  }
  Binding = 0;
  SecurityQOS = 0;
  v14 = 0;
  v18 = 0;
  v19 = 0;
  v2 = RpcBindingFromStringBindingW(String, &Binding);
  if ( v2 )
  {
    if ( (xmmword_180107A50 & 2) == 0 )
      goto LABEL_8;
    v8 = 10;
    v9 = v2;
    goto LABEL_31;
  }
  *(_QWORD *)&v19 = c_rgbLocalServiceSid;
  SecurityQOS.Version = 4;
  SecurityQOS.Capabilities = 17;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = 2;
  v3 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0x14u, 0, 0, &SecurityQOS);
  v2 = v3;
  if ( v3 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v8 = 11;
LABEL_40:
      v9 = v3;
LABEL_31:
      WPP_SF_d(513, v8, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v9, Optionsa);
    }
  }
  else
  {
    v3 = RpcBindingSetOption(Binding, 9u, 1u);
    v2 = v3;
    if ( !v3 )
    {
      v14 = Binding;
      Binding = 0;
      goto LABEL_8;
    }
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v8 = 12;
      goto LABEL_40;
    }
  }
LABEL_8:
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v2 )
  {
    if ( (xmmword_180107A50 & 2) == 0 )
      goto LABEL_20;
    v6 = 28;
LABEL_36:
    v7 = v2;
LABEL_37:
    WPP_SF_d(513, v6, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v7, Optionsa);
    goto LABEL_20;
  }
  Binding = 0;
  SecurityQOS = 0;
  v15 = 0;
  v18 = 0;
  v19 = 0;
  v4 = RpcBindingFromStringBindingW(String, &Binding);
  v2 = v4;
  if ( v4 )
  {
    if ( (xmmword_180107A50 & 2) == 0 )
      goto LABEL_15;
    v10 = 10;
    goto LABEL_43;
  }
  *(_QWORD *)&v19 = c_rgbLocalServiceSid;
  SecurityQOS.Version = 4;
  SecurityQOS.Capabilities = 17;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = 3;
  v4 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0x14u, 0, 0, &SecurityQOS);
  v2 = v4;
  if ( v4 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v10 = 11;
LABEL_43:
      WPP_SF_d(513, v10, WPP_d20135cef7e33325d83cff35dd261285_Traceguids, v4, Optionsa);
    }
  }
  else
  {
    v4 = RpcBindingSetOption(Binding, 9u, 1u);
    v2 = v4;
    if ( !v4 )
    {
      v15 = Binding;
      Binding = 0;
      goto LABEL_15;
    }
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v10 = 12;
      goto LABEL_43;
    }
  }
LABEL_15:
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v2 )
  {
    if ( (xmmword_180107A50 & 2) == 0 )
      goto LABEL_20;
    v6 = 29;
    goto LABEL_36;
  }
  if ( !g_hApAnonymousBinding )
  {
    g_hApAnonymousBinding = v14;
    g_hAPImpersonationBinding = v15;
    v14 = 0;
    v15 = 0;
  }
LABEL_20:
  if ( String )
    RpcStringFreeW(&String);
  if ( v14 )
    RpcBindingFree(&v14);
  if ( v15 )
    RpcBindingFree(&v15);
  return v2;
}

```

## disassembly

```asm
0x18007311c  push    rbp
0x18007311e  push    rbx
0x18007311f  push    rdi
0x180073120  push    r12
0x180073122  push    r14
0x180073124  push    r15
0x180073126  lea     rbp, [rsp-2Fh]
0x18007312b  sub     rsp, 0A8h
0x180073132  mov     rax, cs:__security_cookie
0x180073139  xor     rax, rsp
0x18007313c  mov     [rbp+57h+var_40], rax
0x180073140  xor     edi, edi
0x180073142  mov     [rbp+57h+String], rdi
0x180073146  mov     [rbp+57h+var_88], rdi
0x18007314a  mov     [rbp+57h+var_80], rdi
0x18007314e  call    ?CheckProcessIsLowBox@@YAKXZ; CheckProcessIsLowBox(void)
0x180073153  test    byte ptr cs:xmmword_180107A50, 2
0x18007315a  lea     r15, WPP_d20135cef7e33325d83cff35dd261285_Traceguids
0x180073161  mov     r14d, 201h
0x180073167  jnz     loc_1800733F3
0x18007316d  lea     rax, [rbp+57h+String]
0x180073171  xor     r9d, r9d; Endpoint
0x180073174  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x180073179  lea     rdx, Protseq; "ncalrpc"
0x180073180  xor     r8d, r8d; NetworkAddr
0x180073183  mov     [rsp+0D0h+Options], rdi; Options
0x180073188  xor     ecx, ecx; ObjUuid
0x18007318a  call    cs:__imp_RpcStringBindingComposeW
0x180073190  mov     ebx, eax
0x180073192  test    eax, eax
0x180073194  jnz     loc_180073382
0x18007319a  mov     rcx, [rbp+57h+String]; StringBinding
0x18007319e  lea     rdx, [rbp+57h+Binding]; Binding
0x1800731a2  xorps   xmm0, xmm0
0x1800731a5  mov     [rbp+57h+Binding], rdi
0x1800731a9  movups  xmmword ptr [rbp+57h+var_70.Version], xmm0
0x1800731ad  mov     [rbp+57h+var_88], rdi
0x1800731b1  movups  [rbp+57h+var_60], xmm0
0x1800731b5  movups  [rbp+57h+var_50], xmm0
0x1800731b9  call    cs:__imp_RpcBindingFromStringBindingW
0x1800731bf  mov     ebx, eax
0x1800731c1  mov     r12d, 1
0x1800731c7  lea     rax, c_rgbLocalServiceSid
0x1800731ce  test    ebx, ebx
0x1800731d0  jnz     loc_180073395
0x1800731d6  mov     rcx, [rbp+57h+Binding]; Binding
0x1800731da  lea     r9d, [r12+13h]; AuthnSvc
0x1800731df  mov     qword ptr [rbp+57h+var_50], rax
0x1800731e3  lea     r8d, [r12+5]; AuthnLevel
0x1800731e8  lea     rax, [rbp+57h+var_70]
0x1800731ec  mov     [rbp+57h+var_70.Version], 4
0x1800731f3  mov     [rsp+0D0h+SecurityQOS], rax; SecurityQOS
0x1800731f8  xor     edx, edx; ServerPrincName
0x1800731fa  mov     dword ptr [rsp+0D0h+StringBinding], edi; AuthzSvc
0x1800731fe  mov     [rsp+0D0h+Options], rdi; AuthIdentity
0x180073203  mov     [rbp+57h+var_70.Capabilities], 11h
0x18007320a  mov     [rbp+57h+var_70.IdentityTracking], r12d
0x18007320e  mov     [rbp+57h+var_70.ImpersonationType], 2
0x180073215  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18007321b  mov     ebx, eax
0x18007321d  test    eax, eax
0x18007321f  jnz     loc_18007340B
0x180073225  mov     rcx, [rbp+57h+Binding]; hBinding
0x180073229  lea     edx, [rax+9]; option
0x18007322c  mov     r8d, r12d; optionValue
0x18007322f  call    cs:__imp_RpcBindingSetOption
0x180073235  mov     ebx, eax
0x180073237  test    eax, eax
0x180073239  jnz     loc_180073429
0x18007323f  mov     rax, [rbp+57h+Binding]
0x180073243  mov     [rbp+57h+var_88], rax
0x180073247  mov     [rbp+57h+Binding], rdi
0x18007324b  cmp     [rbp+57h+Binding], rdi
0x18007324f  jnz     loc_180073438
0x180073255  test    ebx, ebx
0x180073257  jnz     loc_1800733CE
0x18007325d  mov     rcx, [rbp+57h+String]; StringBinding
0x180073261  lea     rdx, [rbp+57h+Binding]; Binding
0x180073265  xorps   xmm0, xmm0
0x180073268  mov     [rbp+57h+Binding], rdi
0x18007326c  movups  xmmword ptr [rbp+57h+var_70.Version], xmm0
0x180073270  mov     [rbp+57h+var_80], rdi
0x180073274  movups  [rbp+57h+var_60], xmm0
0x180073278  movups  [rbp+57h+var_50], xmm0
0x18007327c  call    cs:__imp_RpcBindingFromStringBindingW
0x180073282  mov     ebx, eax
0x180073284  test    eax, eax
0x180073286  jnz     loc_1800733BA
0x18007328c  mov     rcx, [rbp+57h+Binding]; Binding
0x180073290  lea     rax, c_rgbLocalServiceSid
0x180073297  mov     qword ptr [rbp+57h+var_50], rax
0x18007329b  lea     r9d, [rbx+14h]; AuthnSvc
0x18007329f  lea     rax, [rbp+57h+var_70]
0x1800732a3  mov     [rbp+57h+var_70.Version], 4
0x1800732aa  mov     [rsp+0D0h+SecurityQOS], rax; SecurityQOS
0x1800732af  lea     r8d, [rbx+6]; AuthnLevel
0x1800732b3  mov     dword ptr [rsp+0D0h+StringBinding], edi; AuthzSvc
0x1800732b7  xor     edx, edx; ServerPrincName
0x1800732b9  mov     [rsp+0D0h+Options], rdi; AuthIdentity
0x1800732be  mov     [rbp+57h+var_70.Capabilities], 11h
0x1800732c5  mov     [rbp+57h+var_70.IdentityTracking], r12d
0x1800732c9  mov     [rbp+57h+var_70.ImpersonationType], 3
0x1800732d0  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800732d6  mov     ebx, eax
0x1800732d8  test    eax, eax
0x1800732da  jnz     loc_18007345F
0x1800732e0  mov     rcx, [rbp+57h+Binding]; hBinding
0x1800732e4  lea     edx, [rax+9]; option
0x1800732e7  mov     r8, r12; optionValue
0x1800732ea  call    cs:__imp_RpcBindingSetOption
0x1800732f0  mov     ebx, eax
0x1800732f2  test    eax, eax
0x1800732f4  jnz     loc_180073473
0x1800732fa  mov     rax, [rbp+57h+Binding]
0x1800732fe  mov     [rbp+57h+var_80], rax
0x180073302  mov     [rbp+57h+Binding], rdi
0x180073306  cmp     [rbp+57h+Binding], rdi
0x18007330a  jnz     loc_180073482
0x180073310  test    ebx, ebx
0x180073312  jnz     loc_180073491
0x180073318  cmp     cs:?g_hApAnonymousBinding@@3PEAXEA, rdi; void * g_hApAnonymousBinding
0x18007331f  jnz     short loc_18007333F
0x180073321  mov     rax, [rbp+57h+var_88]
0x180073325  mov     cs:?g_hApAnonymousBinding@@3PEAXEA, rax; void * g_hApAnonymousBinding
0x18007332c  mov     rax, [rbp+57h+var_80]
0x180073330  mov     cs:?g_hAPImpersonationBinding@@3PEAXEA, rax; void * g_hAPImpersonationBinding
0x180073337  mov     [rbp+57h+var_88], rdi
0x18007333b  mov     [rbp+57h+var_80], rdi
0x18007333f  cmp     [rbp+57h+String], rdi
0x180073343  jz      short loc_18007334F
0x180073345  lea     rcx, [rbp+57h+String]; String
0x180073349  call    cs:__imp_RpcStringFreeW
0x18007334f  cmp     [rbp+57h+var_88], rdi
0x180073353  jnz     loc_1800734A8
0x180073359  cmp     [rbp+57h+var_80], rdi
0x18007335d  jnz     loc_1800734B7
0x180073363  mov     eax, ebx
0x180073365  mov     rcx, [rbp+57h+var_40]
0x180073369  xor     rcx, rsp; StackCookie
0x18007336c  call    __security_check_cookie
0x180073371  add     rsp, 0A8h
0x180073378  pop     r15
0x18007337a  pop     r14
0x18007337c  pop     r12
0x18007337e  pop     rdi
0x18007337f  pop     rbx
0x180073380  pop     rbp
0x180073381  retn
0x180073382  test    byte ptr cs:xmmword_180107A50, 2
0x180073389  jz      short loc_18007333F
0x18007338b  mov     edx, 1Bh
0x180073390  mov     r9d, eax
0x180073393  jmp     short loc_1800733E3
0x180073395  test    byte ptr cs:xmmword_180107A50, 2
0x18007339c  jz      loc_18007324B
0x1800733a2  mov     edx, 0Ah
0x1800733a7  mov     r9d, ebx
0x1800733aa  mov     ecx, r14d
0x1800733ad  mov     r8, r15
0x1800733b0  call    WPP_SF_d
0x1800733b5  jmp     loc_18007324B
0x1800733ba  test    byte ptr cs:xmmword_180107A50, 2
0x1800733c1  jz      loc_180073306
0x1800733c7  mov     edx, 0Ah
0x1800733cc  jmp     short loc_18007344C
0x1800733ce  test    byte ptr cs:xmmword_180107A50, 2
0x1800733d5  jz      loc_18007333F
0x1800733db  mov     edx, 1Ch
0x1800733e0  mov     r9d, ebx
0x1800733e3  mov     ecx, r14d
0x1800733e6  mov     r8, r15
0x1800733e9  call    WPP_SF_d
0x1800733ee  jmp     loc_18007333F
0x1800733f3  mov     edx, 1Ah
0x1800733f8  mov     ecx, r14d
0x1800733fb  mov     r9d, eax
0x1800733fe  mov     r8, r15
0x180073401  call    WPP_SF_d
0x180073406  jmp     loc_18007316D
0x18007340b  test    byte ptr cs:xmmword_180107A50, 2
0x180073412  jz      loc_18007324B
0x180073418  mov     edx, 0Bh
0x18007341d  jmp     short loc_180073424
0x18007341f  mov     edx, 0Ch
0x180073424  mov     r9d, eax
0x180073427  jmp     short loc_1800733AA
0x180073429  test    byte ptr cs:xmmword_180107A50, 2
0x180073430  jz      loc_18007324B
0x180073436  jmp     short loc_18007341F
0x180073438  lea     rcx, [rbp+57h+Binding]; Binding
0x18007343c  call    cs:__imp_RpcBindingFree
0x180073442  jmp     loc_180073255
0x180073447  mov     edx, 0Ch
0x18007344c  mov     ecx, r14d
0x18007344f  mov     r9d, eax
0x180073452  mov     r8, r15
0x180073455  call    WPP_SF_d
0x18007345a  jmp     loc_180073306
0x18007345f  test    byte ptr cs:xmmword_180107A50, 2
0x180073466  jz      loc_180073306
0x18007346c  mov     edx, 0Bh
0x180073471  jmp     short loc_18007344C
0x180073473  test    byte ptr cs:xmmword_180107A50, 2
0x18007347a  jz      loc_180073306
0x180073480  jmp     short loc_180073447
0x180073482  lea     rcx, [rbp+57h+Binding]; Binding
0x180073486  call    cs:__imp_RpcBindingFree
0x18007348c  jmp     loc_180073310
0x180073491  test    byte ptr cs:xmmword_180107A50, 2
0x180073498  jz      loc_18007333F
0x18007349e  mov     edx, 1Dh
0x1800734a3  jmp     loc_1800733E0
0x1800734a8  lea     rcx, [rbp+57h+var_88]; Binding
0x1800734ac  call    cs:__imp_RpcBindingFree
0x1800734b2  jmp     loc_180073359
0x1800734b7  lea     rcx, [rbp+57h+var_80]; Binding
0x1800734bb  call    cs:__imp_RpcBindingFree
0x1800734c1  jmp     loc_180073363
```
