# PfApRpcProcessCommand

- ea: `0x18005ffe4`
- end: `0x180060300`
- name: `PfApRpcProcessCommand`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006c5a0`

## callees

- `0x18003952c`
- `0x18003babc`
- `0x18003eaa0`
- `0x18003f8a4`
- `0x18003f974`
- `0x1800401e8`
- `0x1800523c8`
- `0x18005e674`
- `0x18005ffe4`
- `0x18006598c`
- `0x18006b948`
- `0x1800759b0`
- `0x180085860`
- `0x180085b04`
- `0x1800abe10`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800600c3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800600c3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180060216`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180060216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060077`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006006d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006006d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602ce`

## pseudocode

```c
__int64 __fastcall PfApRpcProcessCommand(__int64 a1, __int64 a2, void *a3)
{
  bool v3; // zf
  DWORD LastError; // eax
  unsigned int v8; // ebx
  DWORD TokenUserInfo; // eax
  _QWORD *v10; // r15
  __int64 v11; // rcx
  DWORD v12; // ecx
  __int64 AppNameHash; // rsi
  int v14; // ebx
  int v15; // r9d
  __int64 v16; // rcx
  unsigned int RpcProcessCommand; // eax
  unsigned __int16 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v20; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v21; // [rsp+48h] [rbp-B8h] BYREF
  DWORD ReturnLength; // [rsp+4Ch] [rbp-B4h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[144]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[256]; // [rsp+100h] [rbp+0h] BYREF

  v3 = *(_DWORD *)(a2 + 4) == 75497472;
  *(_OWORD *)v24 = 0;
  LODWORD(v24[1]) = -1;
  v21 = 0;
  ReturnLength = 0;
  lpMem = 0;
  if ( v3 )
  {
    LastError = PfApRpcProcessDeploymentCommand();
LABEL_3:
    v8 = LastError;
    goto LABEL_36;
  }
  if ( !GetTokenInformation(a3, TokenSessionId, &v21, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    goto LABEL_3;
  }
  TokenUserInfo = PfSvGetTokenUserInfo(a3, &lpMem);
  v10 = lpMem;
  v8 = TokenUserInfo;
  if ( !TokenUserInfo )
  {
    if ( *(_DWORD *)(a2 + 4) != 92274688 && *(_DWORD *)(a2 + 4) != 109051909 )
    {
      RtlAcquireSRWLockExclusive(a1 + 160);
      if ( !*(_QWORD *)(a1 + 168) || !(unsigned int)PfApUserInfoEqual(a1 + 168, *v10, v21) )
      {
        v8 = 1365;
        goto LABEL_22;
      }
      if ( *(_DWORD *)(a2 + 4) == 109051905 )
      {
        v11 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4072LL);
        if ( v11 )
        {
          v8 = PfApLaunchRpcProcessTerminationReport(v11, a2);
          goto LABEL_22;
        }
LABEL_13:
        v8 = 1058;
LABEL_22:
        RtlReleaseSRWLockExclusive(a1 + 160);
        goto LABEL_34;
      }
      if ( *(_DWORD *)(a2 + 4) == 109051907 )
      {
        if ( !*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4072LL) )
          goto LABEL_13;
        PfApLaunchLogAppStart(a2 + 24);
      }
      else
      {
        v12 = *(_DWORD *)(a2 + 24);
        v19 = 128;
        v20 = 65;
        v8 = PfsAppInfoGet(v12, (int)v26, (int)&v19, (int)v25, (__int64)&v20);
        if ( v8 )
          goto LABEL_22;
        AppNameHash = (unsigned int)PfsGetAppNameHash(v26, v19, v25);
        PfApLogAppUseCommand(AppNameHash, v26, *(unsigned int *)(a2 + 24));
        v14 = PfApUserTimeGet(a1 + 184);
        PfApUserTimeGetBias(a1 + 184);
        *(_WORD *)(a2 + 28) = (int)(PfApPredictorQuery(a1, AppNameHash, v14, v15, 14400000, 0, *(__int64 *)&DOUBLE_0_23)
                                  * 65535.0);
      }
      v8 = 0;
      goto LABEL_22;
    }
    v8 = PfApUserInfoStart((__int64)v24, *(void **)lpMem, v21);
    if ( !v8 )
    {
      if ( *(_DWORD *)(a2 + 4) == 92274688 )
      {
        if ( !*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4064LL) )
        {
LABEL_26:
          v8 = 1058;
          goto LABEL_34;
        }
        RpcProcessCommand = PfApFetchRpcProcessCommand(v16, a2, a3, v24);
      }
      else
      {
        if ( *(_DWORD *)(a2 + 4) != 109051909 )
          goto LABEL_34;
        if ( !*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4072LL) )
          goto LABEL_26;
        if ( (*(_BYTE *)(a2 + 544) & 2) != 0 )
        {
          v8 = 0;
          goto LABEL_34;
        }
        RpcProcessCommand = PfApLaunchRpcProcessDefaultAppCommand(v16, a2, v24);
      }
      v8 = RpcProcessCommand;
    }
  }
LABEL_34:
  if ( v10 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v10);
LABEL_36:
  if ( v24[0] )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v24[0]);
  return v8;
}

```

## disassembly

```asm
0x18005ffe4  mov     [rsp-8+arg_18], rbx
0x18005ffe9  push    rbp
0x18005ffea  push    rsi
0x18005ffeb  push    rdi
0x18005ffec  push    r12
0x18005ffee  push    r13
0x18005fff0  push    r14
0x18005fff2  push    r15
0x18005fff4  lea     rbp, [rsp-110h]
0x18005fffc  sub     rsp, 210h
0x180060003  mov     rax, cs:__security_cookie
0x18006000a  xor     rax, rsp
0x18006000d  mov     [rbp+140h+var_40], rax
0x180060014  xor     esi, esi
0x180060016  xorps   xmm0, xmm0
0x180060019  cmp     dword ptr [rdx+4], 4800000h
0x180060020  mov     rdi, r8
0x180060023  movups  xmmword ptr [rsp+240h+var_1E8], xmm0
0x180060028  mov     dword ptr [rsp+240h+var_1E8+8], 0FFFFFFFFh
0x180060030  mov     r14, rdx
0x180060033  mov     r13, rcx
0x180060036  mov     dword ptr [rsp+240h+var_1FC+4], esi
0x18006003a  mov     [rsp+240h+var_1F4], esi
0x18006003e  mov     [rsp+240h+lpMem], rsi
0x180060043  jnz     short loc_180060051
0x180060045  call    PfApRpcProcessDeploymentCommand
0x18006004a  mov     ebx, eax
0x18006004c  jmp     loc_1800602B7
0x180060051  mov     r9d, 4; TokenInformationLength
0x180060057  lea     rax, [rsp+240h+var_1F4]
0x18006005c  lea     r8, [rsp+240h+var_1FC+4]; TokenInformation
0x180060061  mov     [rsp+240h+ReturnLength], rax; ReturnLength
0x180060066  mov     rcx, rdi; TokenHandle
0x180060069  lea     edx, [r9+8]; TokenInformationClass
0x18006006d  call    cs:__imp_GetTokenInformation
0x180060073  test    eax, eax
0x180060075  jnz     short loc_18006007F
0x180060077  call    cs:__imp_GetLastError
0x18006007d  jmp     short loc_18006004A
0x18006007f  lea     rdx, [rsp+240h+lpMem]
0x180060084  mov     rcx, rdi; TokenHandle
0x180060087  call    PfSvGetTokenUserInfo
0x18006008c  mov     r15, [rsp+240h+lpMem]
0x180060091  mov     ebx, eax
0x180060093  test    eax, eax
0x180060095  jnz     loc_18006029C
0x18006009b  cmp     dword ptr [r14+4], 5800000h
0x1800600a3  mov     r12d, 6800005h
0x1800600a9  jz      loc_18006021E
0x1800600af  cmp     [r14+4], r12d
0x1800600b3  jz      loc_18006021E
0x1800600b9  lea     r12, [r13+0A0h]
0x1800600c0  mov     rcx, r12
0x1800600c3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800600c9  lea     rcx, [r13+0A8h]
0x1800600d0  cmp     [rcx], rsi
0x1800600d3  jz      loc_18006020E
0x1800600d9  mov     r8d, dword ptr [rsp+240h+var_1FC+4]
0x1800600de  mov     rdx, [r15]
0x1800600e1  call    PfApUserInfoEqual
0x1800600e6  test    eax, eax
0x1800600e8  jz      loc_18006020E
0x1800600ee  cmp     dword ptr [r14+4], 6800001h
0x1800600f6  jnz     short loc_180060124
0x1800600f8  mov     rax, cs:PfSvcGlobals
0x1800600ff  mov     rcx, [rax+0FE8h]
0x180060106  test    rcx, rcx
0x180060109  jnz     short loc_180060115
0x18006010b  mov     ebx, 422h
0x180060110  jmp     loc_180060213
0x180060115  mov     rdx, r14
0x180060118  call    PfApLaunchRpcProcessTerminationReport
0x18006011d  mov     ebx, eax
0x18006011f  jmp     loc_180060213
0x180060124  cmp     dword ptr [r14+4], 6800003h
0x18006012c  jnz     short loc_18006014E
0x18006012e  mov     rax, cs:PfSvcGlobals
0x180060135  cmp     [rax+0FE8h], rsi
0x18006013c  jz      short loc_18006010B
0x18006013e  lea     rcx, [r14+18h]
0x180060142  call    PfApLaunchLogAppStart
0x180060147  mov     ebx, esi
0x180060149  jmp     loc_180060213
0x18006014e  mov     ecx, [r14+18h]; dwProcessId
0x180060152  lea     r9, [rsp+240h+var_1D0]
0x180060157  mov     eax, 80h
0x18006015c  lea     r8, [rsp+240h+var_200]
0x180060161  mov     [rsp+240h+var_200], ax
0x180060166  lea     rdx, [rbp+140h+var_140]
0x18006016a  mov     eax, 41h ; 'A'
0x18006016f  mov     word ptr [rsp+240h+var_1FC], ax
0x180060174  lea     rax, [rsp+240h+var_1FC]
0x180060179  mov     [rsp+240h+ReturnLength], rax; __int64
0x18006017e  call    PfsAppInfoGet
0x180060183  mov     ebx, eax
0x180060185  test    eax, eax
0x180060187  jnz     loc_180060213
0x18006018d  movzx   edx, [rsp+240h+var_200]
0x180060192  lea     r8, [rsp+240h+var_1D0]
0x180060197  lea     rcx, [rbp+140h+var_140]
0x18006019b  call    PfsGetAppNameHash
0x1800601a0  mov     r8d, [r14+18h]
0x1800601a4  lea     rdx, [rbp+140h+var_140]
0x1800601a8  mov     ecx, eax
0x1800601aa  mov     esi, eax
0x1800601ac  call    PfApLogAppUseCommand
0x1800601b1  lea     rdi, [r13+0B8h]
0x1800601b8  mov     rcx, rdi
0x1800601bb  call    PfApUserTimeGet
0x1800601c0  mov     rcx, rdi
0x1800601c3  mov     rbx, rax
0x1800601c6  call    PfApUserTimeGetBias
0x1800601cb  movsd   xmm0, cs:__real@3fcd70a3d70a3d71
0x1800601d3  mov     r8, rbx
0x1800601d6  movsd   [rsp+240h+var_210], xmm0
0x1800601dc  mov     edx, esi
0x1800601de  mov     [rsp+240h+var_218], 0
0x1800601e6  mov     rcx, r13
0x1800601e9  mov     dword ptr [rsp+240h+ReturnLength], 0DBBA00h
0x1800601f1  call    PfApPredictorQuery
0x1800601f6  mulsd   xmm0, cs:__real@40efffe000000000
0x1800601fe  xor     esi, esi
0x180060200  cvttsd2si eax, xmm0
0x180060204  mov     [r14+1Ch], ax
0x180060209  jmp     loc_180060147
0x18006020e  mov     ebx, 555h
0x180060213  mov     rcx, r12
0x180060216  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18006021c  jmp     short loc_18006029C
0x18006021e  mov     r8d, dword ptr [rsp+240h+var_1FC+4]
0x180060223  lea     rcx, [rsp+240h+var_1E8]
0x180060228  mov     rdx, [r15]
0x18006022b  call    PfApUserInfoStart
0x180060230  mov     ebx, eax
0x180060232  test    eax, eax
0x180060234  jnz     short loc_18006029C
0x180060236  cmp     dword ptr [r14+4], 5800000h
0x18006023e  jnz     short loc_180060269
0x180060240  mov     rax, cs:PfSvcGlobals
0x180060247  cmp     [rax+0FE0h], rsi
0x18006024e  jnz     short loc_180060257
0x180060250  mov     ebx, 422h
0x180060255  jmp     short loc_18006029C
0x180060257  lea     r9, [rsp+240h+var_1E8]
0x18006025c  mov     r8, rdi
0x18006025f  mov     rdx, r14
0x180060262  call    PfApFetchRpcProcessCommand
0x180060267  jmp     short loc_18006029A
0x180060269  cmp     [r14+4], r12d
0x18006026d  jnz     short loc_18006029C
0x18006026f  mov     rax, cs:PfSvcGlobals
0x180060276  cmp     [rax+0FE8h], rsi
0x18006027d  jz      short loc_180060250
0x18006027f  test    byte ptr [r14+220h], 2
0x180060287  jz      short loc_18006028D
0x180060289  mov     ebx, esi
0x18006028b  jmp     short loc_18006029C
0x18006028d  lea     r8, [rsp+240h+var_1E8]
0x180060292  mov     rdx, r14
0x180060295  call    PfApLaunchRpcProcessDefaultAppCommand
0x18006029a  mov     ebx, eax
0x18006029c  test    r15, r15
0x18006029f  jz      short loc_1800602B7
0x1800602a1  mov     rcx, cs:PfSvcGlobals
0x1800602a8  mov     r8, r15; lpMem
0x1800602ab  xor     edx, edx; dwFlags
0x1800602ad  mov     rcx, [rcx+58h]; hHeap
0x1800602b1  call    cs:__imp_HeapFree
0x1800602b7  mov     r8, [rsp+240h+var_1E8]; lpMem
0x1800602bc  test    r8, r8
0x1800602bf  jz      short loc_1800602D4
0x1800602c1  mov     rcx, cs:PfSvcGlobals
0x1800602c8  xor     edx, edx; dwFlags
0x1800602ca  mov     rcx, [rcx+58h]; hHeap
0x1800602ce  call    cs:__imp_HeapFree
0x1800602d4  mov     eax, ebx
0x1800602d6  mov     rcx, [rbp+140h+var_40]
0x1800602dd  xor     rcx, rsp; StackCookie
0x1800602e0  call    __security_check_cookie
0x1800602e5  mov     rbx, [rsp+240h+arg_18]
0x1800602ed  add     rsp, 210h
0x1800602f4  pop     r15
0x1800602f6  pop     r14
0x1800602f8  pop     r13
0x1800602fa  pop     r12
0x1800602fc  pop     rdi
0x1800602fd  pop     rsi
0x1800602fe  pop     rbp
0x1800602ff  retn
```
