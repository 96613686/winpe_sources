# RpcCanDeleteProfile

- ea: `0x18003d630`
- end: `0x18003dd2c`
- name: `RpcCanDeleteProfile`
- size: `1788`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180011b98`
- `0x18003c4b0`
- `0x18003d630`
- `0x18003e4c0`
- `0x18003efb0`
- `0x1800ba438`
- `0x1800c6774`
- `0x180103e24`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d9ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003da8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d9ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003da8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d840`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d95f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d840`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d95f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d9e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d9e2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d76c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003d76c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d792`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d74e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d74e`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18003d8a9`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18003d8a9`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18003d8f4`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18003da69`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18003d8f4`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18003da69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcCanDeleteProfile(__int64 a1, const struct _GUID *a2, unsigned __int16 *a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  PSID v9; // r15
  PVOID *v10; // rcx
  DWORD RpcClientToken; // edi
  HANDLE v12; // rbx
  BOOL v13; // r12d
  volatile signed __int32 *v14; // rdi
  std::_Ref_count_base *v15; // rdx
  signed __int32 v16; // eax
  signed __int32 v17; // ett
  struct _RTL_CRITICAL_SECTION *v18; // r14
  __int64 v19; // rdx
  __int64 v20; // r8
  PVOID *v21; // rcx
  __int64 *v22; // rbp
  __int64 *i; // rbx
  __int64 v24; // rsi
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // ebx
  unsigned int v28; // esi
  PVOID *v29; // rcx
  int v30; // eax
  unsigned int v32; // [rsp+20h] [rbp-78h]
  unsigned int v33; // [rsp+20h] [rbp-78h]
  PSID Sid; // [rsp+50h] [rbp-48h] BYREF
  HANDLE TokenHandle[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  WINBOOL IsMember; // [rsp+A0h] [rbp+8h] BYREF
  unsigned __int16 *v38; // [rsp+B0h] [rbp+18h]
  _DWORD *v39; // [rsp+B8h] [rbp+20h]

  v39 = a4;
  v38 = a3;
  Sid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 155, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  }
  v8 = LocalQueryRpcClientToken(&Sid);
  v9 = Sid;
  if ( v8 )
    goto LABEL_104;
  if ( !a2 || !a3 )
  {
    v8 = 87;
LABEL_104:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_58;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( !byte_1802A2E08 )
  {
    v8 = 1722;
    goto LABEL_58;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      156,
      &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids,
      *(unsigned int *)(a1 + 388));
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  IsMember = 0;
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 105) >= 4u && (*((_BYTE *)v10 + 108) & 1) != 0 )
  {
    WPP_SF_(v10[12], 51, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle[0] = 0;
  Sid = 0;
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 105) >= 4u && (*((_BYTE *)v10 + 108) & 1) != 0 )
    WPP_SF_(v10[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  IsMember = 0;
  RpcClientToken = LocalQueryRpcClientToken(TokenHandle);
  v12 = TokenHandle[0];
  if ( !RpcClientToken
    && (ConvertStringSidToSidW(L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142", &Sid)
     || (RpcClientToken = GetLastError()) == 0)
    && !CheckTokenMembership(v12, Sid, &IsMember) )
  {
    RpcClientToken = GetLastError();
  }
  if ( v12 )
    CloseHandle(v12);
  if ( Sid )
    LocalFree(Sid);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        48,
        &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids,
        RpcClientToken);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 105) >= 4u && (*((_BYTE *)v10 + 108) & 1) != 0 )
    {
      WPP_SF_d(v10[12], 52, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, RpcClientToken);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v13 = IsMember != 0;
  v14 = 0;
  v15 = qword_1802A4AB0;
  if ( !qword_1802A4AB0 )
    goto LABEL_63;
  LODWORD(Sid) = *(_DWORD *)(a1 + 384);
  v16 = *((_DWORD *)qword_1802A4AB0 + 2);
  do
  {
    if ( !v16 )
      goto LABEL_62;
    v17 = v16;
    v16 = _InterlockedCompareExchange((volatile signed __int32 *)v15 + 2, v16 + 1, v16);
  }
  while ( v17 != v16 );
  v18 = qword_1802A4AA8;
  v14 = (volatile signed __int32 *)qword_1802A4AB0;
  if ( !qword_1802A4AA8 )
  {
LABEL_62:
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
    if ( v14 )
    {
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 21;
    goto LABEL_58;
  }
  *a4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 176, &WPP_4a89edc6aa003b2ebcc3c52f0a6942a6_Traceguids);
  }
  EnterCriticalSection(&CriticalSection);
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 103, &WPP_4a89edc6aa003b2ebcc3c52f0a6942a6_Traceguids);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  v22 = 0;
  for ( i = (__int64 *)qword_1802A1968; i != &qword_1802A1968; i = (__int64 *)*i )
  {
    v24 = i[3];
    TokenHandle[0] = 0;
    if ( !v24 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v21, v19, v20);
    v25 = HtReferenceHandleWithTag(g_hHandleTable, v24, 0, 0, 1, TokenHandle);
    if ( !v25 )
    {
      v26 = *(_QWORD *)&a2->Data1 - *((_QWORD *)TokenHandle[0] + 1);
      if ( *(_QWORD *)&a2->Data1 == *((_QWORD *)TokenHandle[0] + 1) )
        v26 = *(_QWORD *)a2->Data4 - *((_QWORD *)TokenHandle[0] + 2);
      if ( !v26 && (*((_BYTE *)TokenHandle[0] + 24) & 0x25) != 0 )
      {
        HtDereferenceHandleWithTag(g_hHandleTable, v24, 0, 1);
        v22 = i;
        v21 = (PVOID *)WPP_GLOBAL_Control;
        break;
      }
      HtDereferenceHandleWithTag(g_hHandleTable, v24, 0, 1);
      goto LABEL_70;
    }
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 101, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v25);
LABEL_70:
      v21 = (PVOID *)WPP_GLOBAL_Control;
      continue;
    }
  }
  if ( v21 != &WPP_GLOBAL_Control && *((_BYTE *)v21 + 105) >= 4u && (*((_BYTE *)v21 + 108) & 1) != 0 )
    WPP_SF_d(v21[12], 106, &WPP_4a89edc6aa003b2ebcc3c52f0a6942a6_Traceguids, 0);
  if ( v22 )
  {
    v27 = 0;
    v28 = *((_DWORD *)v22 + 5);
    LeaveCriticalSection(&CriticalSection);
    v29 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_50;
  }
  LeaveCriticalSection(&CriticalSection);
  v29 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_102;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 177, &WPP_4a89edc6aa003b2ebcc3c52f0a6942a6_Traceguids, a2);
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  v27 = 1168;
  v28 = 0;
LABEL_50:
  if ( v29 != &WPP_GLOBAL_Control && *((_BYTE *)v29 + 105) >= 4u && (*((_BYTE *)v29 + 108) & 1) != 0 )
    WPP_SF_d(v29[12], 178, &WPP_4a89edc6aa003b2ebcc3c52f0a6942a6_Traceguids, v27);
  if ( v27 )
  {
LABEL_102:
    v8 = 87;
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
      (const char *)0x57,
      v32);
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0xE9D,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
      (const char *)0x57,
      v33);
  }
  else
  {
    EnterCriticalSection(v18);
    v30 = ProfileManager::CanDeleteProfileHelper((ProfileManager *)v18, v9, (unsigned int)Sid, a2, v38, v13, v28, 0, 0);
    *v39 = v30 == 0;
    LeaveCriticalSection(v18);
    v8 = 0;
  }
  if ( v14 && _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v14);
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_58:
  if ( v9 )
  {
    CloseHandle(v9);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 105) >= 4u && (*((_BYTE *)v10 + 108) & 1) != 0 )
    WPP_SF_d(v10[12], 157, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18003d630  mov     [rsp+arg_8], rbx
0x18003d635  mov     [rsp+arg_18], r9
0x18003d63a  mov     [rsp+arg_10], r8
0x18003d63f  push    rbp
0x18003d640  push    rsi
0x18003d641  push    rdi
0x18003d642  push    r12
0x18003d644  push    r13
0x18003d646  push    r14
0x18003d648  push    r15
0x18003d64a  sub     rsp, 60h
0x18003d64e  mov     rbp, r9
0x18003d651  mov     rdi, r8
0x18003d654  mov     r13, rdx
0x18003d657  mov     rsi, rcx
0x18003d65a  xor     r14d, r14d
0x18003d65d  mov     [rsp+98h+Sid], r14
0x18003d662  lea     r12, WPP_GLOBAL_Control
0x18003d669  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d670  cmp     rcx, r12
0x18003d673  jz      short loc_18003D67F
0x18003d675  cmp     byte ptr [rcx+69h], 4
0x18003d679  jnb     loc_18003DAE8
0x18003d67f  lea     rcx, [rsp+98h+Sid]; void **
0x18003d684  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003d689  mov     ebx, eax
0x18003d68b  mov     r15, [rsp+98h+Sid]
0x18003d690  test    eax, eax
0x18003d692  jnz     loc_18003DD20
0x18003d698  test    r13, r13
0x18003d69b  jz      loc_18003DD1B
0x18003d6a1  test    rdi, rdi
0x18003d6a4  jz      loc_18003DD1B
0x18003d6aa  movzx   eax, cs:byte_1802A2E08
0x18003d6b1  nop
0x18003d6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d6b9  test    al, al
0x18003d6bb  jz      loc_18003DA85
0x18003d6c1  cmp     rcx, r12
0x18003d6c4  jz      short loc_18003D6F5
0x18003d6c6  cmp     byte ptr [rcx+69h], 3
0x18003d6ca  jb      short loc_18003D6F5
0x18003d6cc  test    byte ptr [rcx+6Ch], 1
0x18003d6d0  jz      short loc_18003D6F5
0x18003d6d2  mov     edx, 9Ch
0x18003d6d7  mov     r9d, [rsi+184h]
0x18003d6de  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003d6e5  mov     rcx, [rcx+60h]
0x18003d6e9  call    WPP_SF_d
0x18003d6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d6f5  mov     [rsp+98h+IsMember], r14d
0x18003d6fd  cmp     rcx, r12
0x18003d700  jz      short loc_18003D70C
0x18003d702  cmp     byte ptr [rcx+69h], 4
0x18003d706  jnb     loc_18003DB0C
0x18003d70c  mov     [rsp+98h+TokenHandle], r14
0x18003d711  mov     [rsp+98h+Sid], r14
0x18003d716  cmp     rcx, r12
0x18003d719  jz      short loc_18003D725
0x18003d71b  cmp     byte ptr [rcx+69h], 4
0x18003d71f  jnb     loc_18003DB37
0x18003d725  mov     [rsp+98h+IsMember], r14d
0x18003d72d  lea     rcx, [rsp+98h+TokenHandle]; void **
0x18003d732  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003d737  mov     edi, eax
0x18003d739  mov     rbx, [rsp+98h+TokenHandle]
0x18003d73e  test    eax, eax
0x18003d740  jnz     short loc_18003D77A
0x18003d742  lea     rdx, [rsp+98h+Sid]; Sid
0x18003d747  lea     rcx, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x18003d74e  call    cs:__imp_ConvertStringSidToSidW
0x18003d754  test    eax, eax
0x18003d756  jz      loc_18003DB5B
0x18003d75c  lea     r8, [rsp+98h+IsMember]; IsMember
0x18003d764  mov     rdx, [rsp+98h+Sid]; SidToCheck
0x18003d769  mov     rcx, rbx; TokenHandle
0x18003d76c  call    cs:__imp_CheckTokenMembership
0x18003d772  test    eax, eax
0x18003d774  jz      loc_18003DB70
0x18003d77a  test    rbx, rbx
0x18003d77d  jz      short loc_18003D788
0x18003d77f  mov     rcx, rbx; hObject
0x18003d782  call    cs:__imp_CloseHandle
0x18003d788  mov     rcx, [rsp+98h+Sid]; hMem
0x18003d78d  test    rcx, rcx
0x18003d790  jz      short loc_18003D798
0x18003d792  call    cs:__imp_LocalFree
0x18003d798  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d79f  cmp     rcx, r12
0x18003d7a2  jz      short loc_18003D7BD
0x18003d7a4  cmp     byte ptr [rcx+69h], 4
0x18003d7a8  jnb     loc_18003DB7D
0x18003d7ae  cmp     rcx, r12
0x18003d7b1  jz      short loc_18003D7BD
0x18003d7b3  cmp     byte ptr [rcx+69h], 4
0x18003d7b7  jnb     loc_18003DBAB
0x18003d7bd  mov     r12d, r14d
0x18003d7c0  cmp     [rsp+98h+IsMember], r14d
0x18003d7c8  setnz   r12b
0x18003d7cc  mov     rdi, r14
0x18003d7cf  mov     rdx, cs:qword_1802A4AB0
0x18003d7d6  test    rdx, rdx
0x18003d7d9  jz      loc_18003DA15
0x18003d7df  mov     eax, [rsi+180h]
0x18003d7e5  mov     dword ptr [rsp+98h+Sid], eax
0x18003d7e9  mov     eax, [rdx+8]
0x18003d7ec  test    eax, eax
0x18003d7ee  jz      loc_18003DA0E
0x18003d7f4  lea     ecx, [rax+1]
0x18003d7f7  lock cmpxchg [rdx+8], ecx
0x18003d7fc  jnz     short loc_18003D7EC
0x18003d7fe  mov     r14, cs:qword_1802A4AA8
0x18003d805  mov     rdi, cs:qword_1802A4AB0
0x18003d80c  test    r14, r14
0x18003d80f  jz      loc_18003DA0E
0x18003d815  mov     dword ptr [rbp+0], 0
0x18003d81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d823  lea     rsi, WPP_GLOBAL_Control
0x18003d82a  cmp     rcx, rsi
0x18003d82d  jz      short loc_18003D839
0x18003d82f  cmp     byte ptr [rcx+69h], 4
0x18003d833  jnb     loc_18003DBD9
0x18003d839  lea     rcx, CriticalSection; lpCriticalSection
0x18003d840  call    cs:__imp_EnterCriticalSection
0x18003d846  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d84d  cmp     rcx, rsi
0x18003d850  jz      short loc_18003D85C
0x18003d852  cmp     byte ptr [rcx+69h], 4
0x18003d856  jnb     loc_18003DBFD
0x18003d85c  xor     ebp, ebp
0x18003d85e  mov     rbx, cs:qword_1802A1968
0x18003d865  lea     rax, qword_1802A1968
0x18003d86c  cmp     rbx, rax
0x18003d86f  jz      loc_18003D90B
0x18003d875  mov     rsi, [rbx+18h]
0x18003d879  mov     [rsp+98h+TokenHandle], rbp
0x18003d87e  test    rsi, rsi
0x18003d881  jz      loc_18003DADE
0x18003d887  lea     rax, [rsp+98h+TokenHandle]
0x18003d88c  mov     qword ptr [rsp+98h+var_70], rax
0x18003d891  mov     dword ptr [rsp+98h+var_78], 1; unsigned int
0x18003d899  xor     r9d, r9d
0x18003d89c  xor     r8d, r8d
0x18003d89f  mov     rdx, rsi
0x18003d8a2  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18003d8a9  call    cs:__imp_HtReferenceHandleWithTag
0x18003d8af  test    eax, eax
0x18003d8b1  jnz     loc_18003DC28
0x18003d8b7  mov     rcx, [rsp+98h+TokenHandle]
0x18003d8bc  mov     rax, [r13+0]
0x18003d8c0  sub     rax, [rcx+8]
0x18003d8c4  jnz     short loc_18003D8CE
0x18003d8c6  mov     rax, [r13+8]
0x18003d8ca  sub     rax, [rcx+10h]
0x18003d8ce  test    rax, rax
0x18003d8d1  jnz     loc_18003DA56
0x18003d8d7  test    byte ptr [rcx+18h], 25h
0x18003d8db  jz      loc_18003DA56
0x18003d8e1  mov     r9d, 1
0x18003d8e7  xor     r8d, r8d
0x18003d8ea  mov     rdx, rsi
0x18003d8ed  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18003d8f4  call    cs:__imp_HtDereferenceHandleWithTag
0x18003d8fa  mov     rbp, rbx
0x18003d8fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d904  lea     rsi, WPP_GLOBAL_Control
0x18003d90b  cmp     rcx, rsi
0x18003d90e  jz      short loc_18003D91A
0x18003d910  cmp     byte ptr [rcx+69h], 4
0x18003d914  jnb     loc_18003DC70
0x18003d91a  lea     rcx, CriticalSection; lpCriticalSection
0x18003d921  test    rbp, rbp
0x18003d924  jz      loc_18003DA8F
0x18003d92a  xor     ebx, ebx
0x18003d92c  mov     esi, [rbp+14h]
0x18003d92f  call    cs:__imp_LeaveCriticalSection
0x18003d935  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d93c  xor     ebp, ebp
0x18003d93e  lea     rax, WPP_GLOBAL_Control
0x18003d945  cmp     rcx, rax
0x18003d948  jz      short loc_18003D954
0x18003d94a  cmp     byte ptr [rcx+69h], 4
0x18003d94e  jnb     loc_18003DC97
0x18003d954  test    ebx, ebx
0x18003d956  jnz     loc_18003DCBE
0x18003d95c  mov     rcx, r14; lpCriticalSection
0x18003d95f  call    cs:__imp_EnterCriticalSection
0x18003d965  mov     [rsp+98h+var_58], rbp; struct PM_PCB **
0x18003d96a  mov     [rsp+98h+var_60], rbp; struct PM_PCB_LIST **
0x18003d96f  mov     [rsp+98h+var_68], esi; unsigned int
0x18003d973  mov     [rsp+98h+var_70], r12d; int
0x18003d978  mov     rax, [rsp+98h+arg_10]
0x18003d980  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18003d985  mov     r9, r13; struct _GUID *
0x18003d988  mov     r8d, dword ptr [rsp+98h+Sid]; unsigned int
0x18003d98d  mov     rdx, r15; void *
0x18003d990  mov     rcx, r14; this
0x18003d993  call    ?CanDeleteProfileHelper@ProfileManager@@AEAAKPEAXKPEBU_GUID@@PEBGHKPEAPEAUPM_PCB_LIST@@PEAPEAUPM_PCB@@@Z; ProfileManager::CanDeleteProfileHelper(void *,ulong,_GUID const *,ushort const *,int,ulong,PM_PCB_LIST * *,PM_PCB * *)
0x18003d998  mov     edx, ebp
0x18003d99a  test    eax, eax
0x18003d99c  setz    dl
0x18003d99f  mov     rax, [rsp+98h+arg_18]
0x18003d9a7  mov     [rax], edx
0x18003d9a9  mov     rcx, r14; lpCriticalSection
0x18003d9ac  call    cs:__imp_LeaveCriticalSection
0x18003d9b2  mov     ebx, ebp
0x18003d9b4  test    rdi, rdi
0x18003d9b7  jz      short loc_18003D9CC
0x18003d9b9  mov     eax, 0FFFFFFFFh
0x18003d9be  lock xadd [rdi+8], eax
0x18003d9c3  cmp     eax, 1
0x18003d9c6  jz      loc_18003DD00
0x18003d9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9d3  lea     r12, WPP_GLOBAL_Control
0x18003d9da  test    r15, r15
0x18003d9dd  jz      short loc_18003D9EF
0x18003d9df  mov     rcx, r15; hObject
0x18003d9e2  call    cs:__imp_CloseHandle
0x18003d9e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9ef  cmp     rcx, r12
0x18003d9f2  jnz     short loc_18003DA30
0x18003d9f4  mov     eax, ebx
0x18003d9f6  mov     rbx, [rsp+98h+arg_8]
0x18003d9fe  add     rsp, 60h
0x18003da02  pop     r15
0x18003da04  pop     r14
0x18003da06  pop     r13
0x18003da08  pop     r12
0x18003da0a  pop     rdi
0x18003da0b  pop     rsi
0x18003da0c  pop     rbp
0x18003da0d  retn
0x18003da0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da15  test    rdi, rdi
0x18003da18  jz      short loc_18003DA29
0x18003da1a  mov     rcx, rdi; this
0x18003da1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003da22  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da29  mov     ebx, 15h
0x18003da2e  jmp     short loc_18003D9D3
0x18003da30  cmp     byte ptr [rcx+69h], 4
0x18003da34  jb      short loc_18003D9F4
0x18003da36  test    byte ptr [rcx+6Ch], 1
0x18003da3a  jz      short loc_18003D9F4
0x18003da3c  mov     edx, 9Dh
0x18003da41  mov     r9d, ebx
0x18003da44  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003da4b  mov     rcx, [rcx+60h]
0x18003da4f  call    WPP_SF_d
0x18003da54  jmp     short loc_18003D9F4
0x18003da56  mov     r9d, 1
0x18003da5c  xor     r8d, r8d
0x18003da5f  mov     rdx, rsi
0x18003da62  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18003da69  call    cs:__imp_HtDereferenceHandleWithTag
0x18003da6f  lea     rsi, WPP_GLOBAL_Control
0x18003da76  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da7d  mov     rbx, [rbx]
0x18003da80  jmp     loc_18003D865
0x18003da85  mov     ebx, 6BAh
0x18003da8a  jmp     loc_18003D9DA
0x18003da8f  call    cs:__imp_LeaveCriticalSection
0x18003da95  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da9c  cmp     rcx, rsi
0x18003da9f  jz      loc_18003DCBE
0x18003daa5  cmp     byte ptr [rcx+69h], 2
0x18003daa9  jb      short loc_18003DAD0
0x18003daab  test    byte ptr [rcx+6Ch], 1
0x18003daaf  jz      short loc_18003DAD0
0x18003dab1  mov     edx, 0B1h
0x18003dab6  mov     r9, r13
0x18003dab9  lea     r8, WPP_4a89edc6aa003b2ebcc3c52f0a6942a6_Traceguids
0x18003dac0  mov     rcx, [rcx+60h]
0x18003dac4  call    WPP_SF__guid_
0x18003dac9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dad0  xor     ebp, ebp
0x18003dad2  mov     ebx, 490h
0x18003dad7  mov     esi, ebp
0x18003dad9  jmp     loc_18003D93E
0x18003dade  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hInterfaceContext != nullptr")
0x18003dae3  jmp     loc_18003D887
0x18003dae8  test    byte ptr [rcx+6Ch], 1
0x18003daec  jz      loc_18003D67F
0x18003daf2  mov     edx, 9Bh
0x18003daf7  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003dafe  mov     rcx, [rcx+60h]
0x18003db02  call    WPP_SF_
0x18003db07  jmp     loc_18003D67F
0x18003db0c  test    byte ptr [rcx+6Ch], 1
0x18003db10  jz      loc_18003D70C
0x18003db16  mov     edx, 33h ; '3'
0x18003db1b  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003db22  mov     rcx, [rcx+60h]
0x18003db26  call    WPP_SF_
0x18003db2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db32  jmp     loc_18003D70C
0x18003db37  test    byte ptr [rcx+6Ch], 1
0x18003db3b  jz      loc_18003D725
0x18003db41  mov     edx, 2Fh ; '/'
0x18003db46  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
  ... truncated ...
```
