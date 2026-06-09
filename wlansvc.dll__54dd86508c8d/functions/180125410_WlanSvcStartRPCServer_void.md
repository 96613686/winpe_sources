# WlanSvcStartRPCServer(void)

- ea: `0x180125410`
- end: `0x180125ab3`
- name: `?WlanSvcStartRPCServer@@YAKXZ`
- size: `1699`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180117260`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180106340`
- `0x180108798`
- `0x180125410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801255a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801255e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801255a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801255e1`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180125700`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180125765`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1801257ab`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180125700`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180125765`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1801257ab`
- `RPCRT4!RpcEpRegisterW` at `0x1801258dc`
- `RPCRT4!RpcEpRegisterW` at `0x180125938`
- `RPCRT4!RpcEpRegisterW` at `0x1801258dc`
- `RPCRT4!RpcEpRegisterW` at `0x180125938`
- `RPCRT4!RpcEpUnregister` at `0x180125986`
- `RPCRT4!RpcEpUnregister` at `0x180125986`
- `RPCRT4!RpcBindingVectorFree` at `0x180125a44`
- `RPCRT4!RpcBindingVectorFree` at `0x180125a44`
- `RPCRT4!RpcServerInqBindings` at `0x180125688`
- `RPCRT4!RpcServerInqBindings` at `0x180125688`
- `RPCRT4!RpcServerUseProtseqW` at `0x18012563c`
- `RPCRT4!RpcServerUseProtseqW` at `0x18012563c`
- `RPCRT4!RpcServerRegisterIf3` at `0x18012581e`
- `RPCRT4!RpcServerRegisterIf3` at `0x18012588c`
- `RPCRT4!RpcServerRegisterIf3` at `0x18012581e`
- `RPCRT4!RpcServerRegisterIf3` at `0x18012588c`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1801256d2`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1801256d2`
- `RPCRT4!RpcStringFreeW` at `0x180125a5e`
- `RPCRT4!RpcStringFreeW` at `0x180125a5e`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1801259a4`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1801259c2`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1801259a4`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1801259c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180125a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180125a2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180125a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180125a2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180125596`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801255d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180125596`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801255d7`

## string_xrefs

- `0x1801258c8`: `Wlan Service`
- `0x180125927`: `Wlan Service LowPriv`

## pseudocode

```c
__int64 WlanSvcStartRPCServer(void)
{
  DWORD v0; // ebx
  WCHAR *v1; // rax
  const wchar_t *v2; // rcx
  __int64 v3; // rdx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int64 v12; // rdx
  __int128 v13; // xmm1
  WCHAR *v14; // rcx
  const wchar_t *v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int v25; // eax
  char v26; // di
  char v27; // si
  DWORD LastError; // eax
  PVOID *v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // rdx
  char v33; // al
  RPC_STATUS v34; // eax
  char v35; // al
  char v36; // al
  unsigned int v37; // eax
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp-C0h] BYREF
  RPC_WSTR PrincName; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v46[160]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR StringSecurityDescriptor[208]; // [rsp+1A0h] [rbp+A0h] BYREF

  v0 = 0;
  v1 = StringSecurityDescriptor;
  BindingVector = 0;
  v2 = L"O:SYG:SYD:AI(A;;CCRC;;;AN)(A;ID;CCRC;;;WD)(A;ID;CCRC;;;RC)(A;ID;0x1f0001;;;BA)(A;ID;0x1f0001;;;SY)(A;;GR;;;S-1-15"
        "-3-1024-440652535-2732821954-2967096804-2743102374-560164511-4036865778-1144947683-2219429793)";
  PrincName = 0;
  SecurityDescriptor = 0;
  v3 = 3;
  hMem = 0;
  do
  {
    v4 = *((_OWORD *)v2 + 1);
    *(_OWORD *)v1 = *(_OWORD *)v2;
    v5 = *((_OWORD *)v2 + 2);
    *((_OWORD *)v1 + 1) = v4;
    v6 = *((_OWORD *)v2 + 3);
    *((_OWORD *)v1 + 2) = v5;
    v7 = *((_OWORD *)v2 + 4);
    *((_OWORD *)v1 + 3) = v6;
    v8 = *((_OWORD *)v2 + 5);
    *((_OWORD *)v1 + 4) = v7;
    v9 = *((_OWORD *)v2 + 6);
    *((_OWORD *)v1 + 5) = v8;
    v10 = *((_OWORD *)v2 + 7);
    v2 += 64;
    *((_OWORD *)v1 + 6) = v9;
    *((_OWORD *)v1 + 7) = v10;
    v1 += 64;
    --v3;
  }
  while ( v3 );
  v11 = *(_OWORD *)v2;
  v12 = 2;
  v13 = *((_OWORD *)v2 + 1);
  v14 = v46;
  *(_OWORD *)v1 = v11;
  *((_OWORD *)v1 + 1) = v13;
  v15 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;S-1-15-2-1)(A;;GA;;;S-1-15-3-1)(A;;GA;;;S-1-1"
         "5-3-2)(A;;GA;;;S-1-15-3-3)S:(ML;;NW;;;LW)";
  do
  {
    v16 = *((_OWORD *)v15 + 1);
    *(_OWORD *)v14 = *(_OWORD *)v15;
    v17 = *((_OWORD *)v15 + 2);
    *((_OWORD *)v14 + 1) = v16;
    v18 = *((_OWORD *)v15 + 3);
    *((_OWORD *)v14 + 2) = v17;
    v19 = *((_OWORD *)v15 + 4);
    *((_OWORD *)v14 + 3) = v18;
    v20 = *((_OWORD *)v15 + 5);
    *((_OWORD *)v14 + 4) = v19;
    v21 = *((_OWORD *)v15 + 6);
    *((_OWORD *)v14 + 5) = v20;
    v22 = *((_OWORD *)v15 + 7);
    v15 += 64;
    *((_OWORD *)v14 + 6) = v21;
    *((_OWORD *)v14 + 7) = v22;
    v14 += 64;
    --v12;
  }
  while ( v12 );
  v23 = *((_OWORD *)v15 + 1);
  *(_OWORD *)v14 = *(_OWORD *)v15;
  v24 = *((_OWORD *)v15 + 2);
  v25 = *((_DWORD *)v15 + 12);
  *((_OWORD *)v14 + 1) = v23;
  *((_OWORD *)v14 + 2) = v24;
  *((_DWORD *)v14 + 12) = v25;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 65, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  }
  if ( byte_1802A2E08 )
    goto LABEL_84;
  v26 = 0;
  v27 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v0 = LastError;
    v29 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v30 = 66;
LABEL_20:
      WPP_SF_d(v29[12], v30, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
      v29 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v46, 1u, &hMem, 0) )
  {
    LastError = GetLastError();
    v0 = LastError;
    v29 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v30 = 67;
      goto LABEL_20;
    }
LABEL_21:
    if ( !v0 )
      goto LABEL_85;
LABEL_75:
    if ( !v26 )
    {
LABEL_77:
      if ( !v27 )
        goto LABEL_85;
      RpcServerUnregisterIfEx(qword_180238940, 0, 1);
      goto LABEL_84;
    }
LABEL_76:
    RpcServerUnregisterIfEx(qword_180238A00, 0, 1);
    v29 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_77;
  }
  v31 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, hMem);
  v0 = v31;
  if ( v31 )
  {
    v29 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v32 = 68;
LABEL_28:
      WPP_SF_d(v29[12], v32, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v31);
      goto LABEL_84;
    }
  }
  else
  {
    v31 = RpcServerInqBindings(&BindingVector);
    v0 = v31;
    if ( v31 )
    {
      v29 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v32 = 69;
        goto LABEL_28;
      }
    }
    else
    {
      v33 = IsKerberosPresent();
      v34 = RpcServerInqDefaultPrincNameW(v33 != 0 ? 16 : 10, &PrincName);
      v0 = v34;
      if ( v34 == 1749 )
      {
        PrincName = 0;
      }
      else if ( v34 )
      {
        PrincName = 0;
        goto LABEL_84;
      }
      v35 = IsKerberosPresent();
      v31 = RpcServerRegisterAuthInfoW(0, v35 != 0 ? 16 : 10, 0, 0);
      v0 = v31;
      if ( v31 )
      {
        v29 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          v32 = 70;
          goto LABEL_28;
        }
      }
      else
      {
        v36 = IsKerberosPresent();
        v31 = RpcServerRegisterAuthInfoW(PrincName, v36 != 0 ? 16 : 10, 0, 0);
        v0 = v31;
        if ( v31 )
        {
          v29 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            v32 = 71;
            goto LABEL_28;
          }
        }
        else
        {
          v31 = RpcServerRegisterAuthInfoW(0, 9u, 0, 0);
          v0 = v31;
          if ( v31 )
          {
            v29 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              v32 = 72;
              goto LABEL_28;
            }
          }
          else
          {
            v31 = RpcServerRegisterIf3(
                    qword_180238A00,
                    0,
                    0,
                    41,
                    1234,
                    0,
                    LocalSecurityCheckCallback,
                    SecurityDescriptor);
            v0 = v31;
            if ( !v31 )
            {
              v37 = RpcServerRegisterIf3(qword_180238940, 0, 0, 41, 1234, 0, LocalSecurityCheckCallback, hMem);
              v0 = v37;
              if ( v37 )
              {
                v38 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105)
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
                {
                  goto LABEL_76;
                }
                v39 = 74;
              }
              else
              {
                v27 = 1;
                v37 = RpcEpRegisterW(qword_180238A00, BindingVector, 0, (RPC_WSTR)L"Wlan Service");
                v0 = v37;
                if ( !v37 )
                {
                  v40 = RpcEpRegisterW(qword_180238940, BindingVector, 0, (RPC_WSTR)L"Wlan Service LowPriv");
                  v0 = v40;
                  if ( v40 )
                  {
                    v26 = 1;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 105)
                      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 12),
                        76,
                        &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids,
                        v40);
                    }
                    RpcEpUnregister(qword_180238A00, BindingVector, 0);
                    v29 = (PVOID *)WPP_GLOBAL_Control;
                    goto LABEL_75;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
                    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 77, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
                  }
                  byte_1802A2E08 = 1;
LABEL_84:
                  v29 = (PVOID *)WPP_GLOBAL_Control;
                  goto LABEL_85;
                }
                v38 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105)
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
                {
                  goto LABEL_76;
                }
                v39 = 75;
              }
              WPP_SF_d(v38[12], v39, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v37);
              goto LABEL_76;
            }
            v29 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              v32 = 73;
              goto LABEL_28;
            }
          }
        }
      }
    }
  }
LABEL_85:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( BindingVector )
  {
    RpcBindingVectorFree(&BindingVector);
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( PrincName )
  {
    RpcStringFreeW(&PrincName);
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v29 != &WPP_GLOBAL_Control && *((_BYTE *)v29 + 105) >= 4u && (*((_BYTE *)v29 + 108) & 1) != 0 )
    WPP_SF_d(v29[12], 78, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x180125410  push    rbp
0x180125412  push    rbx
0x180125413  push    rsi
0x180125414  push    rdi
0x180125415  push    r12
0x180125417  push    r13
0x180125419  push    r14
0x18012541b  lea     rbp, [rsp-250h]
0x180125423  sub     rsp, 350h
0x18012542a  mov     rax, cs:__security_cookie
0x180125431  xor     rax, rsp
0x180125434  mov     [rbp+280h+var_40], rax
0x18012543b  xor     ebx, ebx
0x18012543d  lea     rax, [rbp+280h+StringSecurityDescriptor]
0x180125444  mov     [rsp+380h+BindingVector], rbx
0x180125449  lea     rcx, aOSygSydAiACcrc; "O:SYG:SYD:AI(A;;CCRC;;;AN)(A;ID;CCRC;;;"...
0x180125450  mov     [rsp+380h+PrincName], rbx
0x180125455  mov     [rsp+380h+SecurityDescriptor], rbx
0x18012545a  lea     edx, [rbx+3]
0x18012545d  mov     [rsp+380h+hMem], rbx
0x180125462  lea     r8d, [rdx+7Dh]
0x180125466  movups  xmm0, xmmword ptr [rcx]
0x180125469  movups  xmm1, xmmword ptr [rcx+10h]
0x18012546d  movups  xmmword ptr [rax], xmm0
0x180125470  movups  xmm0, xmmword ptr [rcx+20h]
0x180125474  movups  xmmword ptr [rax+10h], xmm1
0x180125478  movups  xmm1, xmmword ptr [rcx+30h]
0x18012547c  movups  xmmword ptr [rax+20h], xmm0
0x180125480  movups  xmm0, xmmword ptr [rcx+40h]
0x180125484  movups  xmmword ptr [rax+30h], xmm1
0x180125488  movups  xmm1, xmmword ptr [rcx+50h]
0x18012548c  movups  xmmword ptr [rax+40h], xmm0
0x180125490  movups  xmm0, xmmword ptr [rcx+60h]
0x180125494  movups  xmmword ptr [rax+50h], xmm1
0x180125498  movups  xmm1, xmmword ptr [rcx+70h]
0x18012549c  add     rcx, r8
0x18012549f  movups  xmmword ptr [rax+60h], xmm0
0x1801254a3  movups  xmmword ptr [rax+70h], xmm1
0x1801254a7  add     rax, r8
0x1801254aa  sub     rdx, 1
0x1801254ae  jnz     short loc_180125466
0x1801254b0  movups  xmm0, xmmword ptr [rcx]
0x1801254b3  mov     edx, 2
0x1801254b8  movups  xmm1, xmmword ptr [rcx+10h]
0x1801254bc  lea     rcx, [rsp+380h+var_320]
0x1801254c1  movups  xmmword ptr [rax], xmm0
0x1801254c4  movups  xmmword ptr [rax+10h], xmm1
0x1801254c8  lea     rax, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1801254cf  movups  xmm0, xmmword ptr [rax]
0x1801254d2  movups  xmm1, xmmword ptr [rax+10h]
0x1801254d6  movups  xmmword ptr [rcx], xmm0
0x1801254d9  movups  xmm0, xmmword ptr [rax+20h]
0x1801254dd  movups  xmmword ptr [rcx+10h], xmm1
0x1801254e1  movups  xmm1, xmmword ptr [rax+30h]
0x1801254e5  movups  xmmword ptr [rcx+20h], xmm0
0x1801254e9  movups  xmm0, xmmword ptr [rax+40h]
0x1801254ed  movups  xmmword ptr [rcx+30h], xmm1
0x1801254f1  movups  xmm1, xmmword ptr [rax+50h]
0x1801254f5  movups  xmmword ptr [rcx+40h], xmm0
0x1801254f9  movups  xmm0, xmmword ptr [rax+60h]
0x1801254fd  movups  xmmword ptr [rcx+50h], xmm1
0x180125501  movups  xmm1, xmmword ptr [rax+70h]
0x180125505  add     rax, r8
0x180125508  movups  xmmword ptr [rcx+60h], xmm0
0x18012550c  movups  xmmword ptr [rcx+70h], xmm1
0x180125510  add     rcx, r8
0x180125513  sub     rdx, 1
0x180125517  jnz     short loc_1801254CF
0x180125519  movups  xmm0, xmmword ptr [rax]
0x18012551c  movups  xmm1, xmmword ptr [rax+10h]
0x180125520  movups  xmmword ptr [rcx], xmm0
0x180125523  movups  xmm0, xmmword ptr [rax+20h]
0x180125527  mov     eax, [rax+30h]
0x18012552a  movups  xmmword ptr [rcx+10h], xmm1
0x18012552e  movups  xmmword ptr [rcx+20h], xmm0
0x180125532  mov     [rcx+30h], eax
0x180125535  mov     rcx, cs:WPP_GLOBAL_Control
0x18012553c  lea     r12, WPP_GLOBAL_Control
0x180125543  lea     r14d, [rdx+1]
0x180125547  lea     r13, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18012554e  cmp     rcx, r12
0x180125551  jz      short loc_18012556F
0x180125553  cmp     byte ptr [rcx+69h], 4
0x180125557  jb      short loc_18012556F
0x180125559  test    [rcx+6Ch], r14b
0x18012555d  jz      short loc_18012556F
0x18012555f  mov     rcx, [rcx+60h]
0x180125563  lea     edx, [r14+40h]
0x180125567  mov     r8, r13
0x18012556a  call    WPP_SF_
0x18012556f  mov     al, cs:byte_1802A2E08
0x180125575  nop
0x180125576  test    al, al
0x180125578  jnz     loc_1801259FC
0x18012557e  xor     r9d, r9d; SecurityDescriptorSize
0x180125581  lea     r8, [rsp+380h+SecurityDescriptor]; SecurityDescriptor
0x180125586  mov     edx, r14d; StringSDRevision
0x180125589  lea     rcx, [rbp+280h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180125590  xor     dil, dil
0x180125593  xor     sil, sil
0x180125596  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18012559c  test    eax, eax
0x18012559e  jnz     short loc_1801255C7
0x1801255a0  call    cs:__imp_GetLastError
0x1801255a6  mov     ebx, eax
0x1801255a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801255af  cmp     rcx, r12
0x1801255b2  jz      short loc_18012561C
0x1801255b4  cmp     [rcx+69h], r14b
0x1801255b8  jb      short loc_18012561C
0x1801255ba  test    [rcx+6Ch], r14b
0x1801255be  jz      short loc_18012561C
0x1801255c0  mov     edx, 42h ; 'B'
0x1801255c5  jmp     short loc_180125606
0x1801255c7  xor     r9d, r9d; SecurityDescriptorSize
0x1801255ca  lea     r8, [rsp+380h+hMem]; SecurityDescriptor
0x1801255cf  mov     edx, r14d; StringSDRevision
0x1801255d2  lea     rcx, [rsp+380h+var_320]; StringSecurityDescriptor
0x1801255d7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801255dd  test    eax, eax
0x1801255df  jnz     short loc_180125629
0x1801255e1  call    cs:__imp_GetLastError
0x1801255e7  mov     ebx, eax
0x1801255e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801255f0  cmp     rcx, r12
0x1801255f3  jz      short loc_18012561C
0x1801255f5  cmp     [rcx+69h], r14b
0x1801255f9  jb      short loc_18012561C
0x1801255fb  test    [rcx+6Ch], r14b
0x1801255ff  jz      short loc_18012561C
0x180125601  mov     edx, 43h ; 'C'
0x180125606  mov     rcx, [rcx+60h]
0x18012560a  mov     r9d, eax
0x18012560d  mov     r8, r13
0x180125610  call    WPP_SF_d
0x180125615  mov     rcx, cs:WPP_GLOBAL_Control
0x18012561c  test    ebx, ebx
0x18012561e  jz      loc_180125A03
0x180125624  jmp     loc_180125993
0x180125629  mov     r8, [rsp+380h+hMem]; SecurityDescriptor
0x18012562e  lea     rcx, aNcalrpc; "ncalrpc"
0x180125635  mov     edi, 0Ah
0x18012563a  mov     edx, edi; MaxCalls
0x18012563c  call    cs:__imp_RpcServerUseProtseqW
0x180125642  mov     ebx, eax
0x180125644  test    eax, eax
0x180125646  jz      short loc_180125683
0x180125648  mov     rcx, cs:WPP_GLOBAL_Control
0x18012564f  cmp     rcx, r12
0x180125652  jz      loc_180125A03
0x180125658  cmp     [rcx+69h], r14b
0x18012565c  jb      loc_180125A03
0x180125662  test    [rcx+6Ch], r14b
0x180125666  jz      loc_180125A03
0x18012566c  lea     edx, [rdi+3Ah]
0x18012566f  mov     rcx, [rcx+60h]
0x180125673  mov     r9d, eax
0x180125676  mov     r8, r13
0x180125679  call    WPP_SF_d
0x18012567e  jmp     loc_1801259FC
0x180125683  lea     rcx, [rsp+380h+BindingVector]; BindingVector
0x180125688  call    cs:__imp_RpcServerInqBindings
0x18012568e  mov     ebx, eax
0x180125690  test    eax, eax
0x180125692  jz      short loc_1801256BF
0x180125694  mov     rcx, cs:WPP_GLOBAL_Control
0x18012569b  cmp     rcx, r12
0x18012569e  jz      loc_180125A03
0x1801256a4  cmp     [rcx+69h], r14b
0x1801256a8  jb      loc_180125A03
0x1801256ae  test    [rcx+6Ch], r14b
0x1801256b2  jz      loc_180125A03
0x1801256b8  mov     edx, 45h ; 'E'
0x1801256bd  jmp     short loc_18012566F
0x1801256bf  call    IsKerberosPresent
0x1801256c4  neg     al
0x1801256c6  lea     rdx, [rsp+380h+PrincName]; PrincName
0x1801256cb  sbb     ecx, ecx
0x1801256cd  and     ecx, 6
0x1801256d0  add     ecx, edi; AuthnSvc
0x1801256d2  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x1801256d8  mov     ebx, eax
0x1801256da  cmp     eax, 6D5h
0x1801256df  jnz     short loc_18012573A
0x1801256e1  mov     [rsp+380h+PrincName], 0
0x1801256ea  call    IsKerberosPresent
0x1801256ef  neg     al
0x1801256f1  sbb     edx, edx
0x1801256f3  xor     r9d, r9d; Arg
0x1801256f6  and     edx, 6
0x1801256f9  xor     r8d, r8d; GetKeyFn
0x1801256fc  add     edx, edi; AuthnSvc
0x1801256fe  xor     ecx, ecx; ServerPrincName
0x180125700  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180125706  mov     ebx, eax
0x180125708  test    eax, eax
0x18012570a  jz      short loc_18012574C
0x18012570c  mov     rcx, cs:WPP_GLOBAL_Control
0x180125713  cmp     rcx, r12
0x180125716  jz      loc_180125A03
0x18012571c  cmp     [rcx+69h], r14b
0x180125720  jb      loc_180125A03
0x180125726  test    [rcx+6Ch], r14b
0x18012572a  jz      loc_180125A03
0x180125730  mov     edx, 46h ; 'F'
0x180125735  jmp     loc_18012566F
0x18012573a  test    eax, eax
0x18012573c  jz      short loc_1801256EA
0x18012573e  mov     [rsp+380h+PrincName], 0
0x180125747  jmp     loc_1801259FC
0x18012574c  call    IsKerberosPresent
0x180125751  mov     rcx, [rsp+380h+PrincName]; ServerPrincName
0x180125756  neg     al
0x180125758  sbb     edx, edx
0x18012575a  xor     r9d, r9d; Arg
0x18012575d  and     edx, 6
0x180125760  xor     r8d, r8d; GetKeyFn
0x180125763  add     edx, edi; AuthnSvc
0x180125765  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18012576b  mov     ebx, eax
0x18012576d  test    eax, eax
0x18012576f  jz      short loc_18012579F
0x180125771  mov     rcx, cs:WPP_GLOBAL_Control
0x180125778  cmp     rcx, r12
0x18012577b  jz      loc_180125A03
0x180125781  cmp     [rcx+69h], r14b
0x180125785  jb      loc_180125A03
0x18012578b  test    [rcx+6Ch], r14b
0x18012578f  jz      loc_180125A03
0x180125795  mov     edx, 47h ; 'G'
0x18012579a  jmp     loc_18012566F
0x18012579f  xor     r9d, r9d; Arg
0x1801257a2  xor     r8d, r8d; GetKeyFn
0x1801257a5  xor     ecx, ecx; ServerPrincName
0x1801257a7  lea     edx, [r9+9]; AuthnSvc
0x1801257ab  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1801257b1  mov     ebx, eax
0x1801257b3  test    eax, eax
0x1801257b5  jz      short loc_1801257E5
0x1801257b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801257be  cmp     rcx, r12
0x1801257c1  jz      loc_180125A03
0x1801257c7  cmp     [rcx+69h], r14b
0x1801257cb  jb      loc_180125A03
0x1801257d1  test    [rcx+6Ch], r14b
0x1801257d5  jz      loc_180125A03
0x1801257db  mov     edx, 48h ; 'H'
0x1801257e0  jmp     loc_18012566F
0x1801257e5  mov     rax, [rsp+380h+SecurityDescriptor]
0x1801257ea  lea     rcx, qword_180238A00
0x1801257f1  mov     [rsp+380h+var_348], rax
0x1801257f6  mov     edi, 4D2h
0x1801257fb  lea     rax, ?LocalSecurityCheckCallback@@YAJPEAPEAXPEAX@Z; LocalSecurityCheckCallback(void * *,void *)
0x180125802  mov     r9d, 29h ; ')'
0x180125808  mov     [rsp+380h+var_350], rax
0x18012580d  xor     r8d, r8d
0x180125810  mov     [rsp+380h+var_358], 0
0x180125818  xor     edx, edx
0x18012581a  mov     [rsp+380h+var_360], edi
0x18012581e  call    cs:__imp_RpcServerRegisterIf3
0x180125824  mov     ebx, eax
0x180125826  test    eax, eax
0x180125828  jz      short loc_180125858
0x18012582a  mov     rcx, cs:WPP_GLOBAL_Control
0x180125831  cmp     rcx, r12
0x180125834  jz      loc_180125A03
0x18012583a  cmp     [rcx+69h], r14b
0x18012583e  jb      loc_180125A03
0x180125844  test    [rcx+6Ch], r14b
0x180125848  jz      loc_180125A03
0x18012584e  mov     edx, 49h ; 'I'
0x180125853  jmp     loc_18012566F
0x180125858  mov     rax, [rsp+380h+hMem]
0x18012585d  lea     rcx, qword_180238940
0x180125864  mov     [rsp+380h+var_348], rax
0x180125869  mov     r9d, 29h ; ')'
0x18012586f  lea     rax, ?LocalSecurityCheckCallback@@YAJPEAPEAXPEAX@Z; LocalSecurityCheckCallback(void * *,void *)
0x180125876  xor     r8d, r8d
0x180125879  mov     [rsp+380h+var_350], rax
0x18012587e  xor     edx, edx
0x180125880  mov     [rsp+380h+var_358], 0
0x180125888  mov     [rsp+380h+var_360], edi
0x18012588c  call    cs:__imp_RpcServerRegisterIf3
0x180125892  mov     ebx, eax
0x180125894  test    eax, eax
0x180125896  jz      short loc_1801258C3
0x180125898  mov     rcx, cs:WPP_GLOBAL_Control
0x18012589f  cmp     rcx, r12
0x1801258a2  jz      loc_180125998
0x1801258a8  cmp     [rcx+69h], r14b
0x1801258ac  jb      loc_180125998
0x1801258b2  test    [rcx+6Ch], r14b
0x1801258b6  jz      loc_180125998
0x1801258bc  mov     edx, 4Ah ; 'J'
0x1801258c1  jmp     short loc_180125911
0x1801258c3  mov     rdx, [rsp+380h+BindingVector]; BindingVector
0x1801258c8  lea     r9, Annotation; "Wlan Service"
0x1801258cf  xor     r8d, r8d; UuidVector
0x1801258d2  lea     rcx, qword_180238A00; IfSpec
0x1801258d9  mov     sil, r14b
  ... truncated ...
```
