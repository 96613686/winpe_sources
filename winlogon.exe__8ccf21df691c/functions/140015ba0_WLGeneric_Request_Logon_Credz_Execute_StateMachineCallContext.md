# WLGeneric_Request_Logon_Credz_Execute(_StateMachineCallContext *)

- ea: `0x140015ba0`
- end: `0x1400160be`
- name: `?WLGeneric_Request_Logon_Credz_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `1310`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400057f4`
- `0x1400106bc`
- `0x140012cc0`
- `0x140013488`
- `0x140014470`
- `0x140015ba0`
- `0x1400160c4`
- `0x140016284`
- `0x140016850`
- `0x140016a30`
- `0x140016f30`
- `0x140016f60`
- `0x1400190c0`
- `0x14001a200`
- `0x1400333b0`
- `0x140041c34`
- `0x14004327c`
- `0x14004df08`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140015f83`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140015f83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015d28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015d28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d1a`
- `ntdll!EtwEventEnabled` at `0x140015bd3`
- `ntdll!EtwEventEnabled` at `0x140015bd3`
- `ntdll!EtwEventWrite` at `0x140015bf1`
- `ntdll!EtwEventWrite` at `0x140015bf1`
- `ntdll!RtlGetActiveConsoleId` at `0x140015c7b`
- `ntdll!RtlGetActiveConsoleId` at `0x140015c7b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreePropertyValue` at `0x140015cc0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreePropertyValue` at `0x140015cc0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetConnectionProperty` at `0x140015c9d`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetConnectionProperty` at `0x140015c9d`

## string_xrefs

- `0x1400160a8`: `clientcore\ds\security\umstartup\winlogon\core\welcome.cxx`

## pseudocode

```c
__int64 __fastcall WLGeneric_Request_Logon_Credz_Execute(struct _StateMachineCallContext *a1)
{
  __int64 v2; // rsi
  unsigned int v3; // r14d
  __int64 v4; // rbx
  unsigned int LockScreenIdleTimeout; // edi
  __int64 v6; // rcx
  _BYTE *v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // edi
  int started; // eax
  unsigned int v13; // ecx
  int v14[4]; // [rsp+50h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-98h] BYREF
  LPVOID v16; // [rsp+68h] [rbp-90h]
  __int64 v17; // [rsp+70h] [rbp-88h]
  __int64 v18; // [rsp+78h] [rbp-80h]
  __int128 v19; // [rsp+80h] [rbp-78h] BYREF
  __int64 v20; // [rsp+90h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  __int64 v22; // [rsp+118h] [rbp+20h] BYREF

  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_RequestCredentials_Start) )
    EtwEventWrite(g_TraceRegHandle, WLEvt_RequestCredentials_Start, 0, 0);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids);
  }
  v18 = *((_QWORD *)a1 + 1);
  v2 = v18;
  *(_OWORD *)v14 = 0;
  lpMem = 0;
  *((_DWORD *)a1 + 6) = 1;
  v3 = ((unsigned int)IsSASRequired((struct _WLSM_GLOBAL_CONTEXT *)v2) != 0) | 0x10;
  v4 = *(_QWORD *)(v2 + 16);
  LockScreenIdleTimeout = 30000;
  v22 = 0;
  LODWORD(v4) = *(_DWORD *)(v4 + 88);
  if ( (unsigned int)RtlGetActiveConsoleId(v6) == (_DWORD)v4 )
  {
    if ( (unsigned int)IsSASRequired((struct _WLSM_GLOBAL_CONTEXT *)v2) )
    {
      LockScreenIdleTimeout = 120000;
    }
    else if ( (unsigned int)IsLockScreenDisabled((struct _WLSM_GLOBAL_CONTEXT *)v2, 0) )
    {
      LockScreenIdleTimeout = -1;
    }
    else
    {
      LockScreenIdleTimeout = WluiGetLockScreenIdleTimeout();
    }
  }
  else if ( (unsigned __int8)WinStationGetConnectionProperty(0xFFFFFFFFLL, PROPERTY_TYPE_GET_LOGON_DIALOG_TIMEOUT, &v22) )
  {
    if ( *(_WORD *)v22 == 1 )
      LockScreenIdleTimeout = *(_DWORD *)(v22 + 8);
    WinStationFreePropertyValue();
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids,
      LockScreenIdleTimeout);
  }
  v19 = 0;
  v20 = 0;
  ToSetTimeout(LockScreenIdleTimeout, &v19);
  v9 = RequestCredentials(v2, *(_DWORD *)(*(_QWORD *)(v2 + 16) + 228LL) != 0 ? 3 : 0, v3);
  ToResetTimeout();
  if ( !v9 )
  {
    v9 = CGlobalStore::SetCredentials(*(CGlobalStore **)v2, (struct _CRED_PROV_CREDENTIAL *)v14);
    v8 = (unsigned int)v14[2];
    v17 = (unsigned int)v14[2];
    v7 = lpMem;
    v16 = lpMem;
    while ( v8 )
    {
      *v7++ = 0;
      v16 = v7;
      v17 = --v8;
    }
    UHHeapFree(&lpMem);
  }
  *(_DWORD *)(*(_QWORD *)(v2 + 16) + 248LL) = 0;
  if ( v9 != 995 )
  {
    if ( v9 )
    {
      if ( v9 == 1223 )
      {
        v9 = 13;
        if ( !qword_1400D30C8 )
          return v9;
        return (unsigned int)SignalManagerSetSignal(*(PRTL_CRITICAL_SECTION *)qword_1400D30C8);
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids, v9);
      }
      v13 = 38;
    }
    else
    {
      WLEventWrite(&WLDiagEvt_Logon_Start);
      started = CGlobalStore::StartGlobalTraceLoggingActivity(*(RTL_SRWLOCK **)v2, 0);
      if ( started < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4F5,
          (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\welcome.cxx",
          (const char *)(unsigned int)started,
          (int)v14);
      v13 = 37;
    }
    return WlStateMachineSetSignal(v13, 0);
  }
  return v9;
}

```

## disassembly

```asm
0x140015ba0  mov     rax, rsp
0x140015ba3  push    rbx
0x140015ba4  push    rsi
0x140015ba5  push    rdi
0x140015ba6  push    r12
0x140015ba8  push    r13
0x140015baa  push    r14
0x140015bac  push    r15
0x140015bae  sub     rsp, 0C0h
0x140015bb5  movaps  xmmword ptr [rax-48h], xmm6
0x140015bb9  movaps  xmmword ptr [rax-58h], xmm7
0x140015bbd  mov     r15, rcx
0x140015bc0  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140015bc7  test    rcx, rcx
0x140015bca  jz      short loc_140015BF7
0x140015bcc  lea     rdx, WLEvt_RequestCredentials_Start
0x140015bd3  call    cs:__imp_EtwEventEnabled
0x140015bd9  test    al, al
0x140015bdb  jz      short loc_140015BF7
0x140015bdd  xor     r9d, r9d
0x140015be0  xor     r8d, r8d
0x140015be3  lea     rdx, WLEvt_RequestCredentials_Start
0x140015bea  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140015bf1  call    cs:__imp_EtwEventWrite
0x140015bf7  lea     rax, WPP_GLOBAL_Control
0x140015bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c05  cmp     rcx, rax
0x140015c08  jnz     loc_14001603A
0x140015c0e  mov     rsi, [r15+8]
0x140015c12  mov     [rsp+0F8h+var_80], rsi
0x140015c17  xor     r12d, r12d
0x140015c1a  mov     r14d, r12d
0x140015c1d  xorps   xmm0, xmm0
0x140015c20  xor     eax, eax
0x140015c22  movups  xmmword ptr [rsp+0F8h+var_A8], xmm0
0x140015c27  mov     [rsp+0F8h+lpMem], rax
0x140015c2c  mov     [rsp+0F8h+arg_0], r12d
0x140015c34  mov     [rsp+0F8h+arg_10], r12d
0x140015c3c  mov     r13d, 1
0x140015c42  mov     [r15+18h], r13d
0x140015c46  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140015c49  call    ?IsSASRequired@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; IsSASRequired(_WLSM_GLOBAL_CONTEXT *)
0x140015c4e  test    eax, eax
0x140015c50  jz      short loc_140015C55
0x140015c52  mov     r14d, r13d
0x140015c55  or      r14d, 10h
0x140015c59  xorps   xmm6, xmm6
0x140015c5c  xor     eax, eax
0x140015c5e  movq    xmm7, rax
0x140015c63  mov     rbx, [rsi+10h]
0x140015c67  mov     edi, 7530h
0x140015c6c  mov     [rsp+0F8h+var_B4], edi
0x140015c70  mov     [rsp+0F8h+arg_18], r12
0x140015c78  mov     ebx, [rbx+58h]
0x140015c7b  call    cs:__imp_RtlGetActiveConsoleId
0x140015c81  cmp     eax, ebx
0x140015c83  jz      loc_140015E5D
0x140015c89  lea     r8, [rsp+0F8h+arg_18]
0x140015c91  lea     rdx, PROPERTY_TYPE_GET_LOGON_DIALOG_TIMEOUT
0x140015c98  mov     ecx, 0FFFFFFFFh
0x140015c9d  call    cs:__imp_WinStationGetConnectionProperty
0x140015ca3  test    al, al
0x140015ca5  jz      loc_140015D57
0x140015cab  mov     rcx, [rsp+0F8h+arg_18]
0x140015cb3  cmp     r13w, [rcx]
0x140015cb7  jnz     short loc_140015CC0
0x140015cb9  mov     edi, [rcx+8]
0x140015cbc  mov     [rsp+0F8h+var_B4], edi
0x140015cc0  call    cs:__imp_WinStationFreePropertyValue
0x140015cc6  jmp     loc_140015D57
0x140015ccb  lea     rdx, [rsp+0F8h+var_A8]; struct _CRED_PROV_CREDENTIAL *
0x140015cd0  mov     rcx, [rsi]; this
0x140015cd3  call    ?SetCredentials@CGlobalStore@@QEAAKPEAU_CRED_PROV_CREDENTIAL@@@Z; CGlobalStore::SetCredentials(_CRED_PROV_CREDENTIAL *)
0x140015cd8  mov     edi, eax
0x140015cda  mov     [rsp+0F8h+var_B8], eax
0x140015cde  mov     eax, [rsp+0F8h+var_A8+8]
0x140015ce2  mov     [rsp+0F8h+var_88], rax
0x140015ce7  mov     rcx, [rsp+0F8h+lpMem]
0x140015cec  mov     [rsp+0F8h+var_90], rcx
0x140015cf1  test    rax, rax
0x140015cf4  jz      short loc_140015D0B
0x140015cf6  mov     byte ptr [rcx], 0
0x140015cf9  inc     rcx
0x140015cfc  mov     [rsp+0F8h+var_90], rcx
0x140015d01  dec     rax
0x140015d04  mov     [rsp+0F8h+var_88], rax
0x140015d09  jmp     short loc_140015CF1
0x140015d0b  cmp     [rsp+0F8h+arg_10], 0
0x140015d13  jz      short loc_140015D3F
0x140015d15  mov     rbx, [rsp+0F8h+lpMem]
0x140015d1a  call    cs:__imp_GetProcessHeap
0x140015d20  mov     rcx, rax; hHeap
0x140015d23  mov     r8, rbx; lpMem
0x140015d26  xor     edx, edx; dwFlags
0x140015d28  call    cs:__imp_HeapFree
0x140015d2e  mov     [rsp+0F8h+lpMem], r12
0x140015d33  lea     rbx, WPP_GLOBAL_Control
0x140015d3a  jmp     loc_140015F92
0x140015d3f  lea     rcx, [rsp+0F8h+lpMem]
0x140015d44  call    UHHeapFree
0x140015d49  jmp     loc_140015F92
0x140015d4e  mov     edi, 0FFFFFFFFh
0x140015d53  mov     [rsp+0F8h+var_B4], edi
0x140015d57  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d5e  lea     rbx, WPP_GLOBAL_Control
0x140015d65  cmp     rcx, rbx
0x140015d68  jnz     loc_140015E91
0x140015d6e  movaps  [rsp+0F8h+var_78], xmm6
0x140015d76  movsd   [rsp+0F8h+var_68], xmm7
0x140015d7f  lea     rdx, [rsp+0F8h+var_78]
0x140015d87  mov     ecx, edi
0x140015d89  call    ?ToSetTimeout@@YAKKU_StateMachineSignalData@@@Z; ToSetTimeout(ulong,_StateMachineSignalData)
0x140015d8e  mov     rax, [rsi+10h]
0x140015d92  mov     ecx, [rax+0E4h]
0x140015d98  neg     ecx
0x140015d9a  sbb     edx, edx
0x140015d9c  and     edx, 3
0x140015d9f  lea     rax, [rsp+0F8h+arg_10]
0x140015da7  mov     [rsp+0F8h+var_C8], rax
0x140015dac  lea     rax, [rsp+0F8h+arg_0]
0x140015db4  mov     [rsp+0F8h+var_D0], rax
0x140015db9  lea     rax, [rsp+0F8h+var_A8]
0x140015dbe  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x140015dc3  mov     r8d, r14d
0x140015dc6  mov     rcx, rsi
0x140015dc9  call    ?RequestCredentials@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@W4_WLUI_REQUEST_REASON@@W4_WLUI_REQUEST_FLAGS@@PEAU_CRED_PROV_CREDENTIAL@@3PEAIPEAH@Z; RequestCredentials(_WLSM_GLOBAL_CONTEXT *,_WLUI_REQUEST_REASON,_WLUI_REQUEST_FLAGS,_CRED_PROV_CREDENTIAL *,_CRED_PROV_CREDENTIAL *,uint *,int *)
0x140015dce  mov     edi, eax
0x140015dd0  mov     [rsp+0F8h+var_B8], eax
0x140015dd4  call    ?ToResetTimeout@@YAKXZ; ToResetTimeout(void)
0x140015dd9  test    edi, edi
0x140015ddb  jnz     loc_140015F92
0x140015de1  mov     eax, [rsp+0F8h+arg_0]
0x140015de8  test    eax, eax
0x140015dea  jnz     short loc_140015DF9
0x140015dec  test    edi, edi
0x140015dee  jnz     loc_140015F92
0x140015df4  jmp     loc_140015CCB
0x140015df9  mov     [rsp+0F8h+arg_8], r13d
0x140015e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e08  cmp     rcx, rbx
0x140015e0b  jnz     loc_140015EC2
0x140015e11  lea     r9, [rsp+0F8h+arg_8]
0x140015e19  xor     r8d, r8d
0x140015e1c  mov     edx, eax
0x140015e1e  mov     rcx, rsi
0x140015e21  call    ?HandlePowerRequestFromLogonUI@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@IW4LogonUIPowerButtonSource@@PEAH@Z; HandlePowerRequestFromLogonUI(_WLSM_GLOBAL_CONTEXT *,uint,LogonUIPowerButtonSource,int *)
0x140015e26  mov     ebx, eax
0x140015e28  mov     [rsp+0F8h+var_B8], eax
0x140015e2c  test    eax, eax
0x140015e2e  jnz     loc_140015EFA
0x140015e34  test    ebx, ebx
0x140015e36  jz      loc_140015F4B
0x140015e3c  cmp     ebx, 4C7h
0x140015e42  jz      loc_140015F8D
0x140015e48  mov     edi, 4C7h
0x140015e4d  mov     [rsp+0F8h+var_B8], edi
0x140015e51  lea     rbx, WPP_GLOBAL_Control
0x140015e58  jmp     loc_140015F92
0x140015e5d  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140015e60  call    ?IsSASRequired@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; IsSASRequired(_WLSM_GLOBAL_CONTEXT *)
0x140015e65  test    eax, eax
0x140015e67  jnz     short loc_140015E87
0x140015e69  xor     edx, edx; int
0x140015e6b  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140015e6e  call    ?IsLockScreenDisabled@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; IsLockScreenDisabled(_WLSM_GLOBAL_CONTEXT *,int)
0x140015e73  test    eax, eax
0x140015e75  jnz     loc_140015D4E
0x140015e7b  call    WluiGetLockScreenIdleTimeout
0x140015e80  mov     edi, eax
0x140015e82  jmp     loc_140015D53
0x140015e87  mov     edi, 1D4C0h
0x140015e8c  jmp     loc_140015D53
0x140015e91  test    byte ptr [rcx+1Ch], 10h
0x140015e95  jz      loc_140015D6E
0x140015e9b  cmp     byte ptr [rcx+19h], 4
0x140015e9f  jb      loc_140015D6E
0x140015ea5  mov     edx, 3Eh ; '>'
0x140015eaa  mov     r9d, edi
0x140015ead  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x140015eb4  mov     rcx, [rcx+10h]
0x140015eb8  call    WPP_SF_d
0x140015ebd  jmp     loc_140015D6E
0x140015ec2  test    [rcx+1Ch], r13b
0x140015ec6  jz      loc_140015E11
0x140015ecc  cmp     byte ptr [rcx+19h], 4
0x140015ed0  jb      loc_140015E11
0x140015ed6  mov     edx, 32h ; '2'
0x140015edb  mov     r9d, eax
0x140015ede  lea     r8, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x140015ee5  mov     rcx, [rcx+10h]
0x140015ee9  call    WPP_SF_d
0x140015eee  mov     eax, [rsp+0F8h+arg_0]
0x140015ef5  jmp     loc_140015E11
0x140015efa  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f01  lea     rax, WPP_GLOBAL_Control
0x140015f08  cmp     rcx, rax
0x140015f0b  jz      loc_140015E34
0x140015f11  test    [rcx+1Ch], r13b
0x140015f15  jz      loc_140015E34
0x140015f1b  cmp     byte ptr [rcx+19h], 2
0x140015f1f  jb      loc_140015E34
0x140015f25  mov     edx, 33h ; '3'
0x140015f2a  mov     [rsp+0F8h+var_D8], ebx
0x140015f2e  mov     r9d, [rsp+0F8h+arg_0]
0x140015f36  lea     r8, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x140015f3d  mov     rcx, [rcx+10h]
0x140015f41  call    WPP_SF_DD
0x140015f46  jmp     loc_140015E34
0x140015f4b  cmp     [rsp+0F8h+arg_8], 0
0x140015f53  jnz     loc_140015E3C
0x140015f59  mov     ebx, r12d
0x140015f5c  mov     [rsp+0F8h+var_B0], ebx
0x140015f60  cmp     ebx, 0Ah
0x140015f63  jnb     short loc_140015F8D
0x140015f65  cmp     dword ptr [r15+18h], 0
0x140015f6a  jnz     short loc_140015F7E
0x140015f6c  mov     edi, 3E3h
0x140015f71  mov     [rsp+0F8h+var_B8], edi
0x140015f75  lea     rbx, WPP_GLOBAL_Control
0x140015f7c  jmp     short loc_140015F92
0x140015f7e  mov     ecx, 12Ch; dwMilliseconds
0x140015f83  call    cs:__imp_Sleep
0x140015f89  inc     ebx
0x140015f8b  jmp     short loc_140015F5C
0x140015f8d  jmp     loc_140015C59
0x140015f92  mov     rax, [rsi+10h]
0x140015f96  mov     [rax+0F8h], r12d
0x140015f9d  cmp     edi, 3E3h
0x140015fa3  jnz     short loc_140015FCA
0x140015fa5  mov     eax, edi
0x140015fa7  movaps  xmm6, [rsp+0F8h+var_48]
0x140015faf  movaps  xmm7, [rsp+0F8h+var_58]
0x140015fb7  add     rsp, 0C0h
0x140015fbe  pop     r15
0x140015fc0  pop     r14
0x140015fc2  pop     r13
0x140015fc4  pop     r12
0x140015fc6  pop     rdi
0x140015fc7  pop     rsi
0x140015fc8  pop     rbx
0x140015fc9  retn
0x140015fca  test    edi, edi
0x140015fcc  jz      short loc_14001600A
0x140015fce  cmp     edi, 4C7h
0x140015fd4  jnz     loc_14001606B
0x140015fda  mov     edi, 0Dh
0x140015fdf  mov     rcx, cs:qword_1400D30C8
0x140015fe6  test    rcx, rcx
0x140015fe9  jz      short loc_140015FA5
0x140015feb  mov     r8, [rcx+20h]
0x140015fef  xor     r9d, r9d
0x140015ff2  mov     r8, [r8+130h]
0x140015ff9  mov     edx, 26h ; '&'
0x140015ffe  mov     rcx, [rcx]; CriticalSection
0x140016001  call    SignalManagerSetSignal
0x140016006  mov     edi, eax
0x140016008  jmp     short loc_140015FA5
0x14001600a  lea     rcx, WLDiagEvt_Logon_Start; struct _EVENT_DESCRIPTOR *
0x140016011  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140016016  xor     edx, edx
0x140016018  mov     rcx, [rsi]
0x14001601b  call    ?StartGlobalTraceLoggingActivity@CGlobalStore@@QEAAJW4WinLogonActivityType@@@Z; CGlobalStore::StartGlobalTraceLoggingActivity(WinLogonActivityType)
0x140016020  mov     rcx, [rsp+0F8h]; this
0x140016028  test    eax, eax
0x14001602a  js      short loc_1400160A5
0x14001602c  mov     ecx, 25h ; '%'; unsigned int
0x140016031  xor     edx, edx; struct _StateMachineSignalData *
0x140016033  call    ?WlStateMachineSetSignal@@YAKKPEAU_StateMachineSignalData@@@Z; WlStateMachineSetSignal(ulong,_StateMachineSignalData *)
0x140016038  jmp     short loc_140016006
0x14001603a  test    dword ptr [rcx+1Ch], 100h
0x140016041  jz      loc_140015C0E
0x140016047  cmp     byte ptr [rcx+19h], 4
0x14001604b  jb      loc_140015C0E
0x140016051  mov     edx, 31h ; '1'
0x140016056  lea     r8, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x14001605d  mov     rcx, [rcx+10h]
0x140016061  call    WPP_SF_
0x140016066  jmp     loc_140015C0E
0x14001606b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016072  cmp     rcx, rbx
0x140016075  jz      short loc_14001609E
0x140016077  test    dword ptr [rcx+1Ch], 1000h
0x14001607e  jz      short loc_14001609E
0x140016080  cmp     byte ptr [rcx+19h], 2
0x140016084  jb      short loc_14001609E
0x140016086  mov     edx, 34h ; '4'
0x14001608b  mov     r9d, edi
0x14001608e  lea     r8, WPP_c0780f65e4fc3831fcb1cdf10948bc42_Traceguids
0x140016095  mov     rcx, [rcx+10h]
0x140016099  call    WPP_SF_d
0x14001609e  mov     ecx, 26h ; '&'
0x1400160a3  jmp     short loc_140016031
0x1400160a5  mov     r9d, eax; char *
0x1400160a8  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\umstartup\\wi"...
0x1400160af  mov     edx, 4F5h; void *
0x1400160b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400160b9  jmp     loc_14001602C
0x14009d780  push    rbp
0x14009d782  sub     rsp, 40h
0x14009d786  mov     rbp, rdx
  ... truncated ...
```
