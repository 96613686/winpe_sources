# CipUpdateCiSettingsFromPolicies

- ea: `0x180049860`
- end: `0x180049ad2`
- name: `CipUpdateCiSettingsFromPolicies`
- size: `626`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048344`
- `0x1800492f8`

## callees

- `0x18001919c`
- `0x18001920c`
- `0x180019220`
- `0x18001967c`
- `0x180019c78`
- `0x180019cbc`
- `0x180019ee0`
- `0x180019ef0`
- `0x180019f80`
- `0x18001ab6c`
- `0x18001b328`
- `0x18001c668`
- `0x18001ca7c`
- `0x18001cc3c`
- `0x18001d15c`
- `0x18002056c`
- `0x180049860`
- `0x18004e45c`

## pseudocode

```c
__int64 CipUpdateCiSettingsFromPolicies()
{
  __int64 result; // rax
  __int64 i; // rsi
  __int64 v2; // r8
  int PolicyOptions; // edi
  int v4; // edx
  __int64 v5; // r8
  int v6; // edx
  unsigned int v7; // edx
  int v8; // edx
  __int64 v9; // r8
  int v10; // edx
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 ActiveState; // [rsp+30h] [rbp+8h] BYREF

  g_CiPolicyState = 6144;
  g_CiPolicyState = ((SIPolicyAuthRootAuthorized() & 1) << 13) | 0x41800;
  ActiveState = SIPolicyGetActiveState();
  g_CiPolicyState = g_CiPolicyState & 0xFFBFFFFF
                  | ((unsigned __int8)SIPolicyStateAreHotpatchRulesPresent(ActiveState) != 0 ? 0x400000 : 0);
  result = SIPolicyReleaseState(&ActiveState);
  for ( i = 0; (unsigned int)i < g_NumberOfSiPolicies; i = (unsigned int)(i + 1) )
  {
    result = SIPolicyIsEndpointSecurityPolicy(*(_QWORD *)(g_SiPolicyHandles + 8 * i));
    if ( !(_BYTE)result )
    {
      g_CiPolicyState |= 1u;
      PolicyOptions = SIPolicyGetPolicyOptions(*(_QWORD *)(v2 + 8 * i));
      if ( (unsigned __int8)SIPolicyShouldUmciRulesBeEvaluated() )
      {
        g_CiPolicyState = v4 | 2;
        if ( !(unsigned __int8)SIPolicyIsAuditModeEnabled(*(_QWORD *)(v5 + 8 * i)) )
        {
          v7 = v6 & 0xFFFFF7FF;
          g_CiPolicyState = v7;
          if ( (PolicyOptions & 0x2000) == 0 )
            g_CiPolicyState = v7 & 0xFFFFEFFF;
        }
      }
      if ( (unsigned __int8)SIPolicyIsAuditModeEnabled(*(_QWORD *)(v5 + 8 * i)) )
      {
        v8 |= 4u;
        g_CiPolicyState = v8;
      }
      if ( (PolicyOptions & 0x80u) != 0 )
      {
        v8 |= 8u;
        g_CiPolicyState = v8;
      }
      if ( (PolicyOptions & 0x200000) != 0 )
      {
        v8 |= 0x10u;
        g_CiPolicyState = v8;
      }
      if ( (PolicyOptions & 0x20) != 0 )
      {
        v8 |= 0x20u;
        g_CiPolicyState = v8;
      }
      if ( (PolicyOptions & 0x100000) != 0 )
      {
        v8 |= 0x100u;
        g_CiPolicyState = v8;
      }
      if ( (PolicyOptions & 0x100) != 0 )
        g_CiPolicyState = v8 | 0x200;
      if ( (unsigned __int8)SIPolicyIsOEMIDRequired(*(_QWORD *)(v9 + 8 * i)) )
        g_CiPolicyState = v10 | 0x10000;
      if ( (unsigned __int8)SIPolicyHasPerAppPolicy(*(_QWORD *)(v11 + 8 * i)) )
        g_CiPolicyState |= 0x80040u;
      if ( (unsigned __int8)SIPolicyFilePathRulesPresent(*(_QWORD *)(v12 + 8 * i)) )
        g_CiPolicyState |= 0x400u;
      if ( (unsigned __int8)SIPolicyNightsWatchEnabled(*(_QWORD *)(v13 + 8 * i)) )
      {
        g_CiPolicyState |= 0x4000u;
      }
      else if ( (unsigned __int8)SIPolicyIsBasePolicy(*(_QWORD *)(g_SiPolicyHandles + 8 * i), v14, v15, v16)
             && (PolicyOptions & 4) != 0 )
      {
        g_CiPolicyState &= ~0x40000u;
      }
      if ( (unsigned __int8)SIPolicySmartlockerEnabled(*(_QWORD *)(g_SiPolicyHandles + 8 * i)) )
        g_CiPolicyState |= 0x20000u;
      if ( (unsigned __int8)SIPolicyAppIdTaggingPresent(*(_QWORD *)(v17 + 8 * i)) )
      {
        g_CiPolicyState |= 0x8040u;
        if ( (unsigned __int8)SIPolicyAppIdTaggingEnforceDLL(*(_QWORD *)(v18 + 8 * i)) )
          g_CiPolicyState |= 0x200000u;
      }
      result = *(_QWORD *)(g_SiPolicyHandles + 8 * i);
      if ( (*(_DWORD *)(result + 672) & 0x40) != 0 )
        g_CiPolicyState |= 0x100000u;
    }
  }
  if ( (g_CiDeveloperMode & 0x2000) != 0 )
  {
    v19 = (unsigned int)g_CiDeveloperMode >> 10;
    LOBYTE(v19) = (g_CiDeveloperMode & 0x400) != 0;
    result = g_CiPolicyState & 0xFF7FFFFF | ((SIPolicyAreCustomKernelSignersAllowed(v19) & 1) << 23);
    g_CiPolicyState = result;
  }
  return result;
}

```

## disassembly

```asm
0x180049860  mov     [rsp+arg_8], rbx
0x180049865  mov     [rsp+arg_10], rsi
0x18004986a  push    rdi
0x18004986b  sub     rsp, 20h
0x18004986f  mov     cs:g_CiPolicyState, 1800h
0x180049879  call    SIPolicyAuthRootAuthorized
0x18004987e  and     eax, 1
0x180049881  shl     eax, 0Dh
0x180049884  or      eax, 41800h
0x180049889  mov     cs:g_CiPolicyState, eax
0x18004988f  call    SIPolicyGetActiveState
0x180049894  mov     rcx, rax
0x180049897  mov     [rsp+28h+arg_0], rax
0x18004989c  call    SIPolicyStateAreHotpatchRulesPresent
0x1800498a1  neg     al
0x1800498a3  mov     eax, cs:g_CiPolicyState
0x1800498a9  sbb     ecx, ecx
0x1800498ab  btr     eax, 16h
0x1800498af  and     ecx, 400000h
0x1800498b5  or      ecx, eax
0x1800498b7  mov     cs:g_CiPolicyState, ecx
0x1800498bd  lea     rcx, [rsp+28h+arg_0]
0x1800498c2  call    SIPolicyReleaseState
0x1800498c7  xor     esi, esi
0x1800498c9  cmp     cs:g_NumberOfSiPolicies, esi
0x1800498cf  jz      loc_180049A92
0x1800498d5  mov     r8, cs:g_SiPolicyHandles
0x1800498dc  mov     rcx, [r8+rsi*8]
0x1800498e0  call    SIPolicyIsEndpointSecurityPolicy
0x1800498e5  test    al, al
0x1800498e7  jnz     loc_180049A84
0x1800498ed  mov     edx, cs:g_CiPolicyState
0x1800498f3  or      edx, 1
0x1800498f6  mov     cs:g_CiPolicyState, edx
0x1800498fc  mov     rcx, [r8+rsi*8]
0x180049900  call    SIPolicyGetPolicyOptions
0x180049905  mov     edi, eax
0x180049907  call    SIPolicyShouldUmciRulesBeEvaluated
0x18004990c  test    al, al
0x18004990e  jz      short loc_180049940
0x180049910  or      edx, 2
0x180049913  mov     cs:g_CiPolicyState, edx
0x180049919  mov     rcx, [r8+rsi*8]
0x18004991d  call    SIPolicyIsAuditModeEnabled
0x180049922  test    al, al
0x180049924  jnz     short loc_180049940
0x180049926  btr     edx, 0Bh
0x18004992a  mov     cs:g_CiPolicyState, edx
0x180049930  bt      edi, 0Dh
0x180049934  jb      short loc_180049940
0x180049936  btr     edx, 0Ch
0x18004993a  mov     cs:g_CiPolicyState, edx
0x180049940  mov     rcx, [r8+rsi*8]
0x180049944  call    SIPolicyIsAuditModeEnabled
0x180049949  test    al, al
0x18004994b  jz      short loc_180049956
0x18004994d  or      edx, 4
0x180049950  mov     cs:g_CiPolicyState, edx
0x180049956  test    dil, dil
0x180049959  jns     short loc_180049964
0x18004995b  or      edx, 8
0x18004995e  mov     cs:g_CiPolicyState, edx
0x180049964  bt      edi, 15h
0x180049968  jnb     short loc_180049973
0x18004996a  or      edx, 10h
0x18004996d  mov     cs:g_CiPolicyState, edx
0x180049973  test    dil, 20h
0x180049977  jz      short loc_180049982
0x180049979  or      edx, 20h
0x18004997c  mov     cs:g_CiPolicyState, edx
0x180049982  bt      edi, 14h
0x180049986  jnb     short loc_180049992
0x180049988  bts     edx, 8
0x18004998c  mov     cs:g_CiPolicyState, edx
0x180049992  bt      edi, 8
0x180049996  jnb     short loc_1800499A2
0x180049998  bts     edx, 9
0x18004999c  mov     cs:g_CiPolicyState, edx
0x1800499a2  mov     rcx, [r8+rsi*8]
0x1800499a6  call    SIPolicyIsOEMIDRequired
0x1800499ab  test    al, al
0x1800499ad  jz      short loc_1800499B9
0x1800499af  bts     edx, 10h
0x1800499b3  mov     cs:g_CiPolicyState, edx
0x1800499b9  mov     rcx, [r8+rsi*8]
0x1800499bd  call    SIPolicyHasPerAppPolicy
0x1800499c2  test    al, al
0x1800499c4  jz      short loc_1800499D0
0x1800499c6  or      cs:g_CiPolicyState, 80040h
0x1800499d0  mov     rcx, [r8+rsi*8]
0x1800499d4  call    SIPolicyFilePathRulesPresent
0x1800499d9  test    al, al
0x1800499db  jz      short loc_1800499E5
0x1800499dd  bts     cs:g_CiPolicyState, 0Ah
0x1800499e5  mov     rcx, [r8+rsi*8]
0x1800499e9  call    SIPolicyNightsWatchEnabled
0x1800499ee  test    al, al
0x1800499f0  jz      short loc_1800499FC
0x1800499f2  bts     cs:g_CiPolicyState, 0Eh
0x1800499fa  jmp     short loc_180049A1E
0x1800499fc  mov     rcx, cs:g_SiPolicyHandles
0x180049a03  mov     rcx, [rcx+rsi*8]
0x180049a07  call    SIPolicyIsBasePolicy
0x180049a0c  test    al, al
0x180049a0e  jz      short loc_180049A1E
0x180049a10  test    dil, 4
0x180049a14  jz      short loc_180049A1E
0x180049a16  btr     cs:g_CiPolicyState, 12h
0x180049a1e  mov     rdx, cs:g_SiPolicyHandles
0x180049a25  mov     rcx, [rdx+rsi*8]
0x180049a29  call    SIPolicySmartlockerEnabled
0x180049a2e  test    al, al
0x180049a30  jz      short loc_180049A3A
0x180049a32  bts     cs:g_CiPolicyState, 11h
0x180049a3a  mov     rcx, [rdx+rsi*8]
0x180049a3e  call    SIPolicyAppIdTaggingPresent
0x180049a43  test    al, al
0x180049a45  jz      short loc_180049A66
0x180049a47  or      cs:g_CiPolicyState, 8040h
0x180049a51  mov     rcx, [rdx+rsi*8]
0x180049a55  call    SIPolicyAppIdTaggingEnforceDLL
0x180049a5a  test    al, al
0x180049a5c  jz      short loc_180049A66
0x180049a5e  bts     cs:g_CiPolicyState, 15h
0x180049a66  mov     r8, cs:g_SiPolicyHandles
0x180049a6d  mov     rax, [r8+rsi*8]
0x180049a71  mov     ecx, [rax+2A0h]
0x180049a77  test    cl, 40h
0x180049a7a  jz      short loc_180049A84
0x180049a7c  bts     cs:g_CiPolicyState, 14h
0x180049a84  inc     esi
0x180049a86  cmp     esi, cs:g_NumberOfSiPolicies
0x180049a8c  jb      loc_1800498D5
0x180049a92  mov     ecx, cs:g_CiDeveloperMode
0x180049a98  bt      ecx, 0Dh
0x180049a9c  jnb     short loc_180049AC1
0x180049a9e  shr     ecx, 0Ah
0x180049aa1  and     cl, 1
0x180049aa4  call    SIPolicyAreCustomKernelSignersAllowed
0x180049aa9  mov     ecx, cs:g_CiPolicyState
0x180049aaf  and     eax, 1
0x180049ab2  shl     eax, 17h
0x180049ab5  btr     ecx, 17h
0x180049ab9  or      eax, ecx
0x180049abb  mov     cs:g_CiPolicyState, eax
0x180049ac1  mov     rbx, [rsp+28h+arg_8]
0x180049ac6  mov     rsi, [rsp+28h+arg_10]
0x180049acb  add     rsp, 20h
0x180049acf  pop     rdi
0x180049ad0  retn
```
