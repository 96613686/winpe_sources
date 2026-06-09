# UbpmGetUserToken

- ea: `0x18001bb20`
- end: `0x18001bfef`
- name: `UbpmGetUserToken`
- size: `1231`
- prototype: `__int64 __usercall@<rax>(ULONG SessionId@<ecx>, DWORD TokenInformationLength)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b190`

## callees

- `0x18000f9a0`
- `0x18001bb20`
- `0x18003226c`
- `0x180032450`
- `0x1800325e0`
- `0x180032e38`
- `0x1800347bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001bc3b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001bc3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bbb9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bc11`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bbb9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bc11`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001bc5e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001bc5e`
- `ntdll!RtlFreeHeap` at `0x18001bc9c`
- `ntdll!RtlFreeHeap` at `0x18001bcbe`
- `ntdll!RtlFreeHeap` at `0x18001bfd9`
- `ntdll!RtlFreeHeap` at `0x18001bc9c`
- `ntdll!RtlFreeHeap` at `0x18001bcbe`
- `ntdll!RtlFreeHeap` at `0x18001bfd9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bf1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bfe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bfe4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001be23`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001be23`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18001be74`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18001be74`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001bb67`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001bb67`

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
0x18001bb20  push    rdi
0x18001bb22  sub     rsp, 60h
0x18001bb26  mov     [rsp+68h+arg_0], rbx
0x18001bb2b  mov     edi, ecx
0x18001bb2d  mov     [rsp+68h+arg_8], rbp
0x18001bb32  mov     rbx, rdx
0x18001bb35  mov     [rsp+68h+var_10], r12
0x18001bb3a  mov     r12, r8
0x18001bb3d  mov     [rsp+68h+var_18], r13
0x18001bb42  xor     r13d, r13d
0x18001bb45  mov     [rsp+68h+var_28], r15
0x18001bb4a  mov     r15, r9
0x18001bb4d  mov     [rsp+68h+TokenHandle], r13
0x18001bb52  call    IsUMgrEnumerateSessionUsersPresent
0x18001bb57  test    al, al
0x18001bb59  jz      loc_18001BE13
0x18001bb5f  lea     rdx, [rsp+68h+TokenHandle]
0x18001bb64  mov     rcx, rbx
0x18001bb67  call    cs:__imp_UMgrQueryUserToken
0x18001bb6d  test    eax, eax
0x18001bb6f  js      loc_18001BCCE
0x18001bb75  mov     [rsp+68h+arg_10], rsi
0x18001bb7d  mov     edi, r13d
0x18001bb80  mov     [rsp+68h+var_20], r14
0x18001bb85  mov     r14, r13
0x18001bb88  test    r15, r15
0x18001bb8b  jz      loc_18001BC6F
0x18001bb91  mov     rsi, [rsp+68h+TokenHandle]
0x18001bb96  lea     rax, [rsp+68h+TokenInformationLength]
0x18001bb9e  mov     rcx, rsi; TokenHandle
0x18001bba1  mov     [rsp+68h+TokenInformationLength], r13d
0x18001bba9  xor     r9d, r9d; TokenInformationLength
0x18001bbac  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18001bbb1  xor     r8d, r8d; TokenInformation
0x18001bbb4  mov     edx, 1; TokenInformationClass
0x18001bbb9  call    cs:__imp_GetTokenInformation
0x18001bbbf  lea     rbx, WPP_GLOBAL_Control
0x18001bbc6  test    eax, eax
0x18001bbc8  jnz     short loc_18001BBD9
0x18001bbca  call    cs:__imp_GetLastError
0x18001bbd0  cmp     eax, 7Ah ; 'z'
0x18001bbd3  jnz     loc_18001BD17
0x18001bbd9  mov     ecx, [rsp+68h+TokenInformationLength]; Size
0x18001bbe0  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001bbe5  mov     rdi, rax
0x18001bbe8  test    rax, rax
0x18001bbeb  jz      loc_18001BF56
0x18001bbf1  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18001bbf9  lea     rax, [rsp+68h+TokenInformationLength]
0x18001bc01  mov     r8, rdi; TokenInformation
0x18001bc04  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18001bc09  mov     edx, 1; TokenInformationClass
0x18001bc0e  mov     rcx, rsi; TokenHandle
0x18001bc11  call    cs:__imp_GetTokenInformation
0x18001bc17  test    eax, eax
0x18001bc19  jz      loc_18001BF95
0x18001bc1f  mov     r14, rdi
0x18001bc22  mov     edi, r13d
0x18001bc25  jmp     short loc_18001BC38
0x18001bc27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc2e  mov     edi, ebp
0x18001bc30  test    ebp, ebp
0x18001bc32  jnz     loc_18001BD57
0x18001bc38  mov     rcx, [r14]; pSid
0x18001bc3b  call    cs:__imp_GetLengthSid
0x18001bc41  mov     ecx, eax; Size
0x18001bc43  mov     ebp, eax
0x18001bc45  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001bc4a  mov     rsi, rax
0x18001bc4d  test    rax, rax
0x18001bc50  jz      loc_18001BD77
0x18001bc56  mov     r8, [r14]; pSourceSid
0x18001bc59  mov     rdx, rax; pDestinationSid
0x18001bc5c  mov     ecx, ebp; nDestinationSidLength
0x18001bc5e  call    cs:__imp_CopySid
0x18001bc64  test    eax, eax
0x18001bc66  jz      loc_18001BDA3
0x18001bc6c  mov     [r15], rsi
0x18001bc6f  mov     rsi, r13
0x18001bc72  test    r12, r12
0x18001bc75  jz      short loc_18001BC85
0x18001bc77  mov     rax, [rsp+68h+TokenHandle]
0x18001bc7c  mov     [r12], rax
0x18001bc80  mov     [rsp+68h+TokenHandle], r13
0x18001bc85  test    r14, r14
0x18001bc88  jz      short loc_18001BCA2
0x18001bc8a  mov     rcx, gs:60h
0x18001bc93  mov     r8, r14; P
0x18001bc96  xor     edx, edx; Flags
0x18001bc98  mov     rcx, [rcx+30h]; HeapHandle
0x18001bc9c  call    cs:__imp_RtlFreeHeap
0x18001bca2  mov     r14, [rsp+68h+var_20]
0x18001bca7  test    rsi, rsi
0x18001bcaa  jz      short loc_18001BCC4
0x18001bcac  mov     rcx, gs:60h
0x18001bcb5  mov     r8, rsi; P
0x18001bcb8  xor     edx, edx; Flags
0x18001bcba  mov     rcx, [rcx+30h]; HeapHandle
0x18001bcbe  call    cs:__imp_RtlFreeHeap
0x18001bcc4  mov     rsi, [rsp+68h+arg_10]
0x18001bccc  jmp     short loc_18001BCE8
0x18001bcce  movzx   edi, ax
0x18001bcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcd8  lea     rbx, WPP_GLOBAL_Control
0x18001bcdf  cmp     rcx, rbx
0x18001bce2  jnz     loc_18001BDE2
0x18001bce8  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18001bced  mov     r15, [rsp+68h+var_28]
0x18001bcf2  mov     r13, [rsp+68h+var_18]
0x18001bcf7  mov     r12, [rsp+68h+var_10]
0x18001bcfc  mov     rbp, [rsp+68h+arg_8]
0x18001bd01  mov     rbx, [rsp+68h+arg_0]
0x18001bd06  test    rcx, rcx
0x18001bd09  jnz     loc_18001BFE4
0x18001bd0f  mov     eax, edi
0x18001bd11  add     rsp, 60h
0x18001bd15  pop     rdi
0x18001bd16  retn
0x18001bd17  mov     ebp, 0Dh
0x18001bd1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd23  cmp     rcx, rbx
0x18001bd26  jz      loc_18001BC2E
0x18001bd2c  test    byte ptr [rcx+1Ch], 1
0x18001bd30  jz      loc_18001BC2E
0x18001bd36  mov     rcx, [rcx+10h]
0x18001bd3a  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001bd41  mov     edx, 1Dh
0x18001bd46  mov     r9d, ebp
0x18001bd49  call    WPP_SF_d
0x18001bd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd55  mov     edi, ebp
0x18001bd57  mov     rsi, r13
0x18001bd5a  cmp     rcx, rbx
0x18001bd5d  jz      loc_18001BC85
0x18001bd63  test    byte ptr [rcx+1Ch], 1
0x18001bd67  jz      loc_18001BC85
0x18001bd6d  mov     edx, 10h
0x18001bd72  mov     r9d, ebp
0x18001bd75  jmp     short loc_18001BDCD
0x18001bd77  call    cs:__imp_GetLastError
0x18001bd7d  mov     edi, eax
0x18001bd7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd86  cmp     rcx, rbx
0x18001bd89  jz      loc_18001BC85
0x18001bd8f  test    byte ptr [rcx+1Ch], 1
0x18001bd93  jz      loc_18001BC85
0x18001bd99  mov     edx, 11h
0x18001bd9e  mov     r9d, eax
0x18001bda1  jmp     short loc_18001BDCD
0x18001bda3  call    cs:__imp_GetLastError
0x18001bda9  mov     edi, eax
0x18001bdab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdb2  cmp     rcx, rbx
0x18001bdb5  jz      loc_18001BC85
0x18001bdbb  test    byte ptr [rcx+1Ch], 1
0x18001bdbf  jz      loc_18001BC85
0x18001bdc5  mov     edx, 12h
0x18001bdca  mov     r9d, eax
0x18001bdcd  mov     rcx, [rcx+10h]
0x18001bdd1  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x18001bdd8  call    WPP_SF_d
0x18001bddd  jmp     loc_18001BC85
0x18001bde2  test    byte ptr [rcx+1Ch], 1
0x18001bde6  jz      loc_18001BCE8
0x18001bdec  mov     edx, 0Bh
0x18001bdf1  mov     r9d, edi
0x18001bdf4  jmp     short loc_18001BDFE
0x18001bdf6  mov     edx, 0Fh
0x18001bdfb  mov     r9d, eax
0x18001bdfe  mov     rcx, [rcx+10h]
0x18001be02  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x18001be09  call    WPP_SF_d
0x18001be0e  jmp     loc_18001BCE8
0x18001be13  call    IsWTSEnumerateSessionsWPresent
0x18001be18  test    al, al
0x18001be1a  jz      short loc_18001BE64
0x18001be1c  lea     rdx, [rsp+68h+TokenHandle]; phToken
0x18001be21  mov     ecx, edi; SessionId
0x18001be23  call    cs:__imp_WTSQueryUserToken
0x18001be29  test    eax, eax
0x18001be2b  jnz     loc_18001BB75
0x18001be31  call    cs:__imp_GetLastError
0x18001be37  mov     edi, eax
0x18001be39  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be40  lea     rbx, WPP_GLOBAL_Control
0x18001be47  cmp     rcx, rbx
0x18001be4a  jz      loc_18001BCE8
0x18001be50  test    byte ptr [rcx+1Ch], 1
0x18001be54  jz      loc_18001BCE8
0x18001be5a  mov     edx, 0Ch
0x18001be5f  mov     r9d, eax
0x18001be62  jmp     short loc_18001BDFE
0x18001be64  call    IsQueryActiveSessionPresent
0x18001be69  test    al, al
0x18001be6b  jz      short loc_18001BEB8
0x18001be6d  lea     rdx, [rsp+68h+TokenHandle]
0x18001be72  mov     ecx, edi
0x18001be74  call    cs:__imp_QueryUserToken
0x18001be7a  test    eax, eax
0x18001be7c  jnz     loc_18001BB75
0x18001be82  call    cs:__imp_GetLastError
0x18001be88  mov     edi, eax
0x18001be8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be91  lea     rbx, WPP_GLOBAL_Control
0x18001be98  cmp     rcx, rbx
0x18001be9b  jz      loc_18001BCE8
0x18001bea1  test    byte ptr [rcx+1Ch], 1
0x18001bea5  jz      loc_18001BCE8
0x18001beab  mov     edx, 0Dh
0x18001beb0  mov     r9d, eax
0x18001beb3  jmp     loc_18001BDFE
0x18001beb8  mov     rax, gs:60h
0x18001bec1  cmp     edi, [rax+2C0h]
0x18001bec7  jz      short loc_18001BF09
0x18001bec9  mov     edi, 32h ; '2'
0x18001bece  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bed5  lea     rbx, WPP_GLOBAL_Control
0x18001bedc  cmp     rcx, rbx
0x18001bedf  jz      loc_18001BCE8
0x18001bee5  test    byte ptr [rcx+1Ch], 1
0x18001bee9  jz      loc_18001BCE8
0x18001beef  mov     rcx, [rcx+10h]
0x18001bef3  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x18001befa  mov     edx, 0Eh
0x18001beff  call    WPP_SF_
0x18001bf04  jmp     loc_18001BCE8
0x18001bf09  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x18001bf0e  mov     edx, 8; DesiredAccess
0x18001bf13  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001bf1a  call    cs:__imp_OpenProcessToken
0x18001bf20  test    eax, eax
0x18001bf22  jnz     loc_18001BB75
0x18001bf28  call    cs:__imp_GetLastError
0x18001bf2e  mov     edi, eax
0x18001bf30  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf37  lea     rbx, WPP_GLOBAL_Control
0x18001bf3e  cmp     rcx, rbx
0x18001bf41  jz      loc_18001BCE8
0x18001bf47  test    byte ptr [rcx+1Ch], 1
0x18001bf4b  jz      loc_18001BCE8
0x18001bf51  jmp     loc_18001BDF6
0x18001bf56  call    cs:__imp_GetLastError
0x18001bf5c  mov     ebp, eax
0x18001bf5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf65  cmp     rcx, rbx
0x18001bf68  jz      loc_18001BC2E
0x18001bf6e  test    byte ptr [rcx+1Ch], 1
0x18001bf72  jz      loc_18001BC2E
0x18001bf78  mov     rcx, [rcx+10h]
0x18001bf7c  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001bf83  mov     edx, 1Eh
0x18001bf88  mov     r9d, eax
0x18001bf8b  call    WPP_SF_d
0x18001bf90  jmp     loc_18001BC27
0x18001bf95  call    cs:__imp_GetLastError
0x18001bf9b  mov     ebp, eax
0x18001bf9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfa4  cmp     rcx, rbx
0x18001bfa7  jz      short loc_18001BFC7
0x18001bfa9  test    byte ptr [rcx+1Ch], 1
0x18001bfad  jz      short loc_18001BFC7
0x18001bfaf  mov     rcx, [rcx+10h]
0x18001bfb3  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001bfba  mov     edx, 1Fh
0x18001bfbf  mov     r9d, eax
0x18001bfc2  call    WPP_SF_d
0x18001bfc7  mov     rcx, gs:60h
0x18001bfd0  mov     r8, rdi; P
0x18001bfd3  xor     edx, edx; Flags
0x18001bfd5  mov     rcx, [rcx+30h]; HeapHandle
0x18001bfd9  call    cs:__imp_RtlFreeHeap
0x18001bfdf  jmp     loc_18001BC27
0x18001bfe4  call    cs:__imp_CloseHandle
0x18001bfea  jmp     loc_18001BD0F
```
