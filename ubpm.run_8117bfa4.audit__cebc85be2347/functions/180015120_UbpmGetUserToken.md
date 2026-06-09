# UbpmGetUserToken

- ea: `0x180015120`
- end: `0x180015668`
- name: `UbpmGetUserToken`
- size: `1352`
- prototype: `__int64 __usercall@<rax>(ULONG SessionId@<ecx>, DWORD TokenInformationLength)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c270`

## callees

- `0x1800150c0`
- `0x180015120`
- `0x1800345cc`
- `0x1800347b0`
- `0x180034940`
- `0x1800351ec`
- `0x180036c60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015253`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015253`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800151bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015223`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800151bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015223`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001527c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001527c`
- `ntdll!RtlFreeHeap` at `0x1800152c0`
- `ntdll!RtlFreeHeap` at `0x1800152e8`
- `ntdll!RtlFreeHeap` at `0x180015646`
- `ntdll!RtlFreeHeap` at `0x1800152c0`
- `ntdll!RtlFreeHeap` at `0x1800152e8`
- `ntdll!RtlFreeHeap` at `0x180015646`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001556f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001556f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015657`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180015460`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180015460`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800154bd`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800154bd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180015167`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180015167`

## pseudocode

```c
__int64 __fastcall UbpmGetUserToken(ULONG SessionId, __int64 a2, HANDLE *a3, _QWORD *a4, DWORD TokenInformationLength)
{
  int UserToken; // eax
  unsigned int v10; // edi
  PSID *v11; // r14
  HANDLE v12; // rsi
  PSID *v13; // rdi
  PVOID *v14; // rcx
  DWORD LengthSid; // ebp
  void *v16; // rax
  void *v17; // rsi
  _QWORD *v18; // rcx
  unsigned int v20; // ebp
  __int64 v21; // rdx
  __int64 v22; // r9
  DWORD v23; // eax
  DWORD v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  DWORD LastError; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  HANDLE TokenHandle[2]; // [rsp+30h] [rbp-38h] BYREF

  TokenHandle[0] = 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    UserToken = UMgrQueryUserToken(a2, TokenHandle);
    if ( UserToken >= 0 )
      goto LABEL_3;
    v10 = (unsigned __int16)UserToken;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    v25 = 11;
    v26 = (unsigned __int16)UserToken;
LABEL_40:
    WPP_SF_d(v18[2], v25, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v26);
    goto LABEL_22;
  }
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( !WTSQueryUserToken(SessionId, TokenHandle) )
    {
      LastError = GetLastError();
      v10 = LastError;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v25 = 12;
      v26 = LastError;
      goto LABEL_40;
    }
    goto LABEL_3;
  }
  if ( (unsigned __int8)IsQueryActiveSessionPresent() )
  {
    if ( !(unsigned int)QueryUserToken(SessionId, TokenHandle) )
    {
      v28 = GetLastError();
      v10 = v28;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v25 = 13;
      v26 = v28;
      goto LABEL_40;
    }
    goto LABEL_3;
  }
  if ( SessionId == NtCurrentPeb()->SessionId )
  {
    if ( !OpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, TokenHandle) )
    {
      v29 = GetLastError();
      v10 = v29;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v25 = 15;
      v26 = v29;
      goto LABEL_40;
    }
LABEL_3:
    v10 = 0;
    v11 = 0;
    if ( !a4 )
      goto LABEL_14;
    v12 = TokenHandle[0];
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle[0], TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
    {
      v13 = (PSID *)UbpmAlloc(TokenInformationLength);
      if ( v13 )
      {
        if ( GetTokenInformation(v12, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
        {
          v11 = v13;
          v10 = 0;
          goto LABEL_11;
        }
        v31 = GetLastError();
        v20 = v31;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, v31);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        goto LABEL_9;
      }
      v30 = GetLastError();
      v20 = v30;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, v30);
LABEL_9:
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      v20 = 13;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 13);
        v14 = (PVOID *)WPP_GLOBAL_Control;
        v10 = 13;
        goto LABEL_28;
      }
    }
    v10 = v20;
    if ( !v20 )
    {
LABEL_11:
      LengthSid = GetLengthSid(*v11);
      v16 = UbpmAlloc(LengthSid);
      v17 = v16;
      if ( v16 )
      {
        if ( CopySid(LengthSid, v16, *v11) )
        {
          *a4 = v17;
LABEL_14:
          v17 = 0;
          if ( a3 )
          {
            *a3 = TokenHandle[0];
            TokenHandle[0] = 0;
          }
          goto LABEL_16;
        }
        v24 = GetLastError();
        v10 = v24;
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_16:
          if ( v11 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
          if ( v17 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
          goto LABEL_22;
        }
        v21 = 18;
        v22 = v24;
      }
      else
      {
        v23 = GetLastError();
        v10 = v23;
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v21 = 17;
        v22 = v23;
      }
LABEL_37:
      WPP_SF_d(v14[2], v21, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v22);
      goto LABEL_16;
    }
LABEL_28:
    v17 = 0;
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 1) == 0 )
      goto LABEL_16;
    v21 = 16;
    v22 = v20;
    goto LABEL_37;
  }
  v10 = 50;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_134408c016563692a0776b6ad2359b4f_Traceguids);
LABEL_22:
  if ( TokenHandle[0] )
    CloseHandle(TokenHandle[0]);
  return v10;
}

```

## disassembly

```asm
0x180015120  push    rdi
0x180015122  sub     rsp, 60h
0x180015126  mov     [rsp+68h+arg_0], rbx
0x18001512b  mov     edi, ecx
0x18001512d  mov     [rsp+68h+arg_8], rbp
0x180015132  mov     rbx, rdx
0x180015135  mov     [rsp+68h+var_10], r12
0x18001513a  mov     r12, r8
0x18001513d  mov     [rsp+68h+var_18], r13
0x180015142  xor     r13d, r13d
0x180015145  mov     [rsp+68h+var_28], r15
0x18001514a  mov     r15, r9
0x18001514d  mov     [rsp+68h+TokenHandle], r13
0x180015152  call    IsUMgrEnumerateSessionUsersPresent
0x180015157  test    al, al
0x180015159  jz      loc_180015450
0x18001515f  lea     rdx, [rsp+68h+TokenHandle]
0x180015164  mov     rcx, rbx
0x180015167  call    cs:__imp_UMgrQueryUserToken
0x18001516e  nop     dword ptr [rax+rax+00h]
0x180015173  test    eax, eax
0x180015175  js      loc_1800152FE
0x18001517b  mov     [rsp+68h+arg_10], rsi
0x180015183  mov     edi, r13d
0x180015186  mov     [rsp+68h+var_20], r14
0x18001518b  mov     r14, r13
0x18001518e  test    r15, r15
0x180015191  jz      loc_180015293
0x180015197  mov     rsi, [rsp+68h+TokenHandle]
0x18001519c  lea     rax, [rsp+68h+TokenInformationLength]
0x1800151a4  mov     rcx, rsi; TokenHandle
0x1800151a7  mov     [rsp+68h+TokenInformationLength], r13d
0x1800151af  xor     r9d, r9d; TokenInformationLength
0x1800151b2  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800151b7  xor     r8d, r8d; TokenInformation
0x1800151ba  mov     edx, 1; TokenInformationClass
0x1800151bf  call    cs:__imp_GetTokenInformation
0x1800151c6  nop     dword ptr [rax+rax+00h]
0x1800151cb  lea     rbx, WPP_GLOBAL_Control
0x1800151d2  test    eax, eax
0x1800151d4  jnz     short loc_1800151EB
0x1800151d6  call    cs:__imp_GetLastError
0x1800151dd  nop     dword ptr [rax+rax+00h]
0x1800151e2  cmp     eax, 7Ah ; 'z'
0x1800151e5  jnz     loc_180015348
0x1800151eb  mov     ecx, [rsp+68h+TokenInformationLength]; Size
0x1800151f2  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800151f7  mov     rdi, rax
0x1800151fa  test    rax, rax
0x1800151fd  jz      loc_1800155B7
0x180015203  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18001520b  lea     rax, [rsp+68h+TokenInformationLength]
0x180015213  mov     r8, rdi; TokenInformation
0x180015216  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18001521b  mov     edx, 1; TokenInformationClass
0x180015220  mov     rcx, rsi; TokenHandle
0x180015223  call    cs:__imp_GetTokenInformation
0x18001522a  nop     dword ptr [rax+rax+00h]
0x18001522f  test    eax, eax
0x180015231  jz      loc_1800155FC
0x180015237  mov     r14, rdi
0x18001523a  mov     edi, r13d
0x18001523d  jmp     short loc_180015250
0x18001523f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015246  mov     edi, ebp
0x180015248  test    ebp, ebp
0x18001524a  jnz     loc_180015388
0x180015250  mov     rcx, [r14]; pSid
0x180015253  call    cs:__imp_GetLengthSid
0x18001525a  nop     dword ptr [rax+rax+00h]
0x18001525f  mov     ecx, eax; Size
0x180015261  mov     ebp, eax
0x180015263  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180015268  mov     rsi, rax
0x18001526b  test    rax, rax
0x18001526e  jz      loc_1800153A8
0x180015274  mov     r8, [r14]; pSourceSid
0x180015277  mov     rdx, rax; pDestinationSid
0x18001527a  mov     ecx, ebp; nDestinationSidLength
0x18001527c  call    cs:__imp_CopySid
0x180015283  nop     dword ptr [rax+rax+00h]
0x180015288  test    eax, eax
0x18001528a  jz      loc_1800153DA
0x180015290  mov     [r15], rsi
0x180015293  mov     rsi, r13
0x180015296  test    r12, r12
0x180015299  jz      short loc_1800152A9
0x18001529b  mov     rax, [rsp+68h+TokenHandle]
0x1800152a0  mov     [r12], rax
0x1800152a4  mov     [rsp+68h+TokenHandle], r13
0x1800152a9  test    r14, r14
0x1800152ac  jz      short loc_1800152CC
0x1800152ae  mov     rcx, gs:60h
0x1800152b7  mov     r8, r14; P
0x1800152ba  xor     edx, edx; Flags
0x1800152bc  mov     rcx, [rcx+30h]; HeapHandle
0x1800152c0  call    cs:__imp_RtlFreeHeap
0x1800152c7  nop     dword ptr [rax+rax+00h]
0x1800152cc  mov     r14, [rsp+68h+var_20]
0x1800152d1  test    rsi, rsi
0x1800152d4  jz      short loc_1800152F4
0x1800152d6  mov     rcx, gs:60h
0x1800152df  mov     r8, rsi; P
0x1800152e2  xor     edx, edx; Flags
0x1800152e4  mov     rcx, [rcx+30h]; HeapHandle
0x1800152e8  call    cs:__imp_RtlFreeHeap
0x1800152ef  nop     dword ptr [rax+rax+00h]
0x1800152f4  mov     rsi, [rsp+68h+arg_10]
0x1800152fc  jmp     short loc_180015318
0x1800152fe  movzx   edi, ax
0x180015301  mov     rcx, cs:WPP_GLOBAL_Control
0x180015308  lea     rbx, WPP_GLOBAL_Control
0x18001530f  cmp     rcx, rbx
0x180015312  jnz     loc_18001541F
0x180015318  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18001531d  mov     r15, [rsp+68h+var_28]
0x180015322  mov     r13, [rsp+68h+var_18]
0x180015327  mov     r12, [rsp+68h+var_10]
0x18001532c  mov     rbp, [rsp+68h+arg_8]
0x180015331  mov     rbx, [rsp+68h+arg_0]
0x180015336  test    rcx, rcx
0x180015339  jnz     loc_180015657
0x18001533f  mov     eax, edi
0x180015341  add     rsp, 60h
0x180015345  pop     rdi
0x180015346  retn
0x180015348  mov     ebp, 0Dh
0x18001534d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015354  cmp     rcx, rbx
0x180015357  jz      loc_180015246
0x18001535d  test    byte ptr [rcx+1Ch], 1
0x180015361  jz      loc_180015246
0x180015367  mov     rcx, [rcx+10h]
0x18001536b  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180015372  mov     edx, 1Dh
0x180015377  mov     r9d, ebp
0x18001537a  call    WPP_SF_d
0x18001537f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015386  mov     edi, ebp
0x180015388  mov     rsi, r13
0x18001538b  cmp     rcx, rbx
0x18001538e  jz      loc_1800152A9
0x180015394  test    byte ptr [rcx+1Ch], 1
0x180015398  jz      loc_1800152A9
0x18001539e  mov     edx, 10h
0x1800153a3  mov     r9d, ebp
0x1800153a6  jmp     short loc_18001540A
0x1800153a8  call    cs:__imp_GetLastError
0x1800153af  nop     dword ptr [rax+rax+00h]
0x1800153b4  mov     edi, eax
0x1800153b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153bd  cmp     rcx, rbx
0x1800153c0  jz      loc_1800152A9
0x1800153c6  test    byte ptr [rcx+1Ch], 1
0x1800153ca  jz      loc_1800152A9
0x1800153d0  mov     edx, 11h
0x1800153d5  mov     r9d, eax
0x1800153d8  jmp     short loc_18001540A
0x1800153da  call    cs:__imp_GetLastError
0x1800153e1  nop     dword ptr [rax+rax+00h]
0x1800153e6  mov     edi, eax
0x1800153e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153ef  cmp     rcx, rbx
0x1800153f2  jz      loc_1800152A9
0x1800153f8  test    byte ptr [rcx+1Ch], 1
0x1800153fc  jz      loc_1800152A9
0x180015402  mov     edx, 12h
0x180015407  mov     r9d, eax
0x18001540a  mov     rcx, [rcx+10h]
0x18001540e  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180015415  call    WPP_SF_d
0x18001541a  jmp     loc_1800152A9
0x18001541f  test    byte ptr [rcx+1Ch], 1
0x180015423  jz      loc_180015318
0x180015429  mov     edx, 0Bh
0x18001542e  mov     r9d, edi
0x180015431  jmp     short loc_18001543B
0x180015433  mov     edx, 0Fh
0x180015438  mov     r9d, eax
0x18001543b  mov     rcx, [rcx+10h]
0x18001543f  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180015446  call    WPP_SF_d
0x18001544b  jmp     loc_180015318
0x180015450  call    IsWTSEnumerateSessionsWPresent
0x180015455  test    al, al
0x180015457  jz      short loc_1800154AD
0x180015459  lea     rdx, [rsp+68h+TokenHandle]; phToken
0x18001545e  mov     ecx, edi; SessionId
0x180015460  call    cs:__imp_WTSQueryUserToken
0x180015467  nop     dword ptr [rax+rax+00h]
0x18001546c  test    eax, eax
0x18001546e  jnz     loc_18001517B
0x180015474  call    cs:__imp_GetLastError
0x18001547b  nop     dword ptr [rax+rax+00h]
0x180015480  mov     edi, eax
0x180015482  mov     rcx, cs:WPP_GLOBAL_Control
0x180015489  lea     rbx, WPP_GLOBAL_Control
0x180015490  cmp     rcx, rbx
0x180015493  jz      loc_180015318
0x180015499  test    byte ptr [rcx+1Ch], 1
0x18001549d  jz      loc_180015318
0x1800154a3  mov     edx, 0Ch
0x1800154a8  mov     r9d, eax
0x1800154ab  jmp     short loc_18001543B
0x1800154ad  call    IsQueryActiveSessionPresent
0x1800154b2  test    al, al
0x1800154b4  jz      short loc_18001550D
0x1800154b6  lea     rdx, [rsp+68h+TokenHandle]
0x1800154bb  mov     ecx, edi
0x1800154bd  call    cs:__imp_QueryUserToken
0x1800154c4  nop     dword ptr [rax+rax+00h]
0x1800154c9  test    eax, eax
0x1800154cb  jnz     loc_18001517B
0x1800154d1  call    cs:__imp_GetLastError
0x1800154d8  nop     dword ptr [rax+rax+00h]
0x1800154dd  mov     edi, eax
0x1800154df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154e6  lea     rbx, WPP_GLOBAL_Control
0x1800154ed  cmp     rcx, rbx
0x1800154f0  jz      loc_180015318
0x1800154f6  test    byte ptr [rcx+1Ch], 1
0x1800154fa  jz      loc_180015318
0x180015500  mov     edx, 0Dh
0x180015505  mov     r9d, eax
0x180015508  jmp     loc_18001543B
0x18001550d  mov     rax, gs:60h
0x180015516  cmp     edi, [rax+2C0h]
0x18001551c  jz      short loc_18001555E
0x18001551e  mov     edi, 32h ; '2'
0x180015523  mov     rcx, cs:WPP_GLOBAL_Control
0x18001552a  lea     rbx, WPP_GLOBAL_Control
0x180015531  cmp     rcx, rbx
0x180015534  jz      loc_180015318
0x18001553a  test    byte ptr [rcx+1Ch], 1
0x18001553e  jz      loc_180015318
0x180015544  mov     rcx, [rcx+10h]
0x180015548  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x18001554f  mov     edx, 0Eh
0x180015554  call    WPP_SF_
0x180015559  jmp     loc_180015318
0x18001555e  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180015563  mov     edx, 8; DesiredAccess
0x180015568  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001556f  call    cs:__imp_OpenProcessToken
0x180015576  nop     dword ptr [rax+rax+00h]
0x18001557b  test    eax, eax
0x18001557d  jnz     loc_18001517B
0x180015583  call    cs:__imp_GetLastError
0x18001558a  nop     dword ptr [rax+rax+00h]
0x18001558f  mov     edi, eax
0x180015591  mov     rcx, cs:WPP_GLOBAL_Control
0x180015598  lea     rbx, WPP_GLOBAL_Control
0x18001559f  cmp     rcx, rbx
0x1800155a2  jz      loc_180015318
0x1800155a8  test    byte ptr [rcx+1Ch], 1
0x1800155ac  jz      loc_180015318
0x1800155b2  jmp     loc_180015433
0x1800155b7  call    cs:__imp_GetLastError
0x1800155be  nop     dword ptr [rax+rax+00h]
0x1800155c3  mov     ebp, eax
0x1800155c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155cc  cmp     rcx, rbx
0x1800155cf  jz      loc_180015246
0x1800155d5  test    byte ptr [rcx+1Ch], 1
0x1800155d9  jz      loc_180015246
0x1800155df  mov     rcx, [rcx+10h]
0x1800155e3  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x1800155ea  mov     edx, 1Eh
0x1800155ef  mov     r9d, eax
0x1800155f2  call    WPP_SF_d
0x1800155f7  jmp     loc_18001523F
0x1800155fc  call    cs:__imp_GetLastError
0x180015603  nop     dword ptr [rax+rax+00h]
0x180015608  mov     ebp, eax
0x18001560a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015611  cmp     rcx, rbx
0x180015614  jz      short loc_180015634
0x180015616  test    byte ptr [rcx+1Ch], 1
0x18001561a  jz      short loc_180015634
0x18001561c  mov     rcx, [rcx+10h]
0x180015620  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180015627  mov     edx, 1Fh
0x18001562c  mov     r9d, eax
0x18001562f  call    WPP_SF_d
0x180015634  mov     rcx, gs:60h
0x18001563d  mov     r8, rdi; P
0x180015640  xor     edx, edx; Flags
0x180015642  mov     rcx, [rcx+30h]; HeapHandle
0x180015646  call    cs:__imp_RtlFreeHeap
0x18001564d  nop     dword ptr [rax+rax+00h]
0x180015652  jmp     loc_18001523F
0x180015657  call    cs:__imp_CloseHandle
0x18001565e  nop     dword ptr [rax+rax+00h]
0x180015663  jmp     loc_18001533F
```
