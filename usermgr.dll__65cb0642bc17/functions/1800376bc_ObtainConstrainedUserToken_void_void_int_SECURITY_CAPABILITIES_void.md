# ObtainConstrainedUserToken(void *,void *,int,_SECURITY_CAPABILITIES *,void * *)

- ea: `0x1800376bc`
- end: `0x180037c24`
- name: `?ObtainConstrainedUserToken@@YAKPEAX0HPEAU_SECURITY_CAPABILITIES@@PEAPEAX@Z`
- size: `1384`
- prototype: `unsigned int __usercall@<eax>(HANDLE TokenHandle@<rcx>, HANDLE@<rdx>, int@<r8d>, struct _SECURITY_CAPABILITIES *@<r9>, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003734c`

## callees

- `0x18000c4f0`
- `0x1800376bc`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800378ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003791c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003798c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800379bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800379e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037a1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037a4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037aa4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037b09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037b96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800378ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003791c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003798c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800379bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800379e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037a1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037a4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037aa4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037b09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180037b96`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180037c0f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180037c0f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180037958`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180037958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800377c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800377c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800377d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800377d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003784d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003784d`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x180037ae2`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x180037ae2`
- `ntdll!RtlAllocateHeap` at `0x180037a77`
- `ntdll!RtlAllocateHeap` at `0x180037b48`
- `ntdll!RtlAllocateHeap` at `0x180037bca`
- `ntdll!RtlAllocateHeap` at `0x180037a77`
- `ntdll!RtlAllocateHeap` at `0x180037b48`
- `ntdll!RtlAllocateHeap` at `0x180037bca`
- `ntdll!RtlFreeHeap` at `0x180037810`
- `ntdll!RtlFreeHeap` at `0x18003783d`
- `ntdll!RtlFreeHeap` at `0x18003786f`
- `ntdll!RtlFreeHeap` at `0x180037810`
- `ntdll!RtlFreeHeap` at `0x18003783d`
- `ntdll!RtlFreeHeap` at `0x18003786f`
- `ntdll!RtlEqualSid` at `0x18003792e`
- `ntdll!RtlEqualSid` at `0x1800379f8`
- `ntdll!RtlEqualSid` at `0x180037b67`
- `ntdll!RtlEqualSid` at `0x18003792e`
- `ntdll!RtlEqualSid` at `0x1800379f8`
- `ntdll!RtlEqualSid` at `0x180037b67`
- `RPCRT4!RpcRevertToSelf` at `0x1800377ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800378b0`
- `RPCRT4!RpcRevertToSelf` at `0x1800377ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800378b0`
- `RPCRT4!RpcImpersonateClient` at `0x180037774`
- `RPCRT4!RpcImpersonateClient` at `0x180037774`

## pseudocode

```c
__int64 __fastcall ObtainConstrainedUserToken(
        HANDLE TokenHandle,
        HANDLE a2,
        int a3,
        struct _SECURITY_CAPABILITIES *a4,
        void **a5)
{
  struct _SECURITY_CAPABILITIES *v5; // rdi
  DWORD CapabilityCount; // eax
  _DWORD *Heap; // r14
  _DWORD *v12; // r15
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  BOOL v15; // eax
  HANDLE v16; // rax
  int v17; // eax
  __int64 i; // r8
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v20[4]; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandlea; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp-A0h] BYREF
  void **v25; // [rsp+70h] [rbp-90h]
  __int128 v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h]
  PSID Sid2[12]; // [rsp+90h] [rbp-70h] BYREF
  PSID TokenInformation[12]; // [rsp+F0h] [rbp-10h] BYREF
  PSID Sid1[10]; // [rsp+150h] [rbp+50h] BYREF

  v25 = a5;
  v22 = 0;
  v5 = a4;
  TokenInformationLength = 0;
  v20[0] = 0;
  v27 = 0;
  v26 = 0;
  TokenHandlea = 0;
  hObject = 0;
  *(_OWORD *)P = 0;
  if ( !SuccessfulInit )
    return 50;
  if ( a3 )
    goto LABEL_8;
  if ( !a4 || !a4->AppContainerSid )
    goto LABEL_28;
  CapabilityCount = a4->CapabilityCount;
  if ( a4->Capabilities )
  {
    if ( !CapabilityCount )
      goto LABEL_28;
LABEL_8:
    Heap = 0;
    v12 = 0;
    LastError = RpcImpersonateClient(0);
    if ( LastError )
      goto LABEL_15;
    LastError = CheckTokenForAccessThroughCapability(
                  0,
                  0,
                  &CapConstrainedImpersonationGroupSidBuffer,
                  &CapConstrainedImpersonationSidBuffer,
                  1u,
                  0,
                  v20);
    if ( LastError )
      goto LABEL_14;
    if ( a3 )
    {
      if ( !TokenHandle )
      {
        CurrentThread = GetCurrentThread();
        if ( !OpenThreadToken(CurrentThread, LastError + 10, LastError + 1, &TokenHandlea) )
        {
          LastError = GetLastError();
LABEL_14:
          RpcRevertToSelf();
          goto LABEL_15;
        }
      }
    }
    RpcRevertToSelf();
    if ( a3 && !TokenHandle )
      TokenHandle = TokenHandlea;
    if ( !v20[0] )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &TokenInformationLength)
        || !GetTokenInformation(a2, TokenUser, Sid2, 0x54u, &TokenInformationLength) )
      {
        goto LABEL_34;
      }
      if ( !RtlEqualSid(TokenInformation[0], Sid2[0]) )
      {
LABEL_39:
        v16 = hObject;
        hObject = 0;
        *v25 = v16;
        goto LABEL_15;
      }
      goto LABEL_37;
    }
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &v22, 4u, &TokenInformationLength) )
      goto LABEL_34;
    if ( !v22 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &TokenInformationLength)
        || !GetTokenInformation(a2, TokenUser, Sid2, 0x54u, &TokenInformationLength) )
      {
        goto LABEL_34;
      }
      if ( RtlEqualSid(TokenInformation[0], Sid2[0]) )
      {
LABEL_37:
        v15 = DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenImpersonation, &hObject);
        goto LABEL_38;
      }
      LastError = 50;
LABEL_15:
      if ( !a3 )
      {
LABEL_20:
        if ( v12 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
        goto LABEL_22;
      }
      if ( Heap )
        goto LABEL_17;
LABEL_18:
      if ( TokenHandlea )
        CloseHandle(TokenHandlea);
      goto LABEL_20;
    }
    if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, Sid1, 0x4Cu, &TokenInformationLength) )
      goto LABEL_34;
    if ( a3 )
    {
      GetTokenInformation(TokenHandle, TokenCapabilities, 0, 0, &TokenInformationLength);
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_18;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
      if ( !Heap )
      {
        LastError = 14;
        goto LABEL_18;
      }
      if ( !GetTokenInformation(TokenHandle, TokenCapabilities, Heap, TokenInformationLength, &TokenInformationLength) )
      {
        LastError = GetLastError();
LABEL_17:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        goto LABEL_18;
      }
      v5 = (struct _SECURITY_CAPABILITIES *)&v26;
      *(PSID *)&v26 = Sid1[0];
      LODWORD(v27) = *Heap;
      *((_QWORD *)&v26 + 1) = Heap + 2;
    }
    else if ( !RtlEqualSid(Sid1[0], v5->AppContainerSid) )
    {
      LastError = 5;
LABEL_22:
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_24;
    }
    if ( !(unsigned int)CreateAppContainerToken(a2, v5, &hObject) )
      goto LABEL_34;
    if ( !GetTokenInformation(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_15;
      LastError = 0;
      if ( !TokenInformationLength )
        goto LABEL_39;
      v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
      if ( !v12 )
        goto LABEL_59;
      if ( !GetTokenInformation(
              TokenHandle,
              TokenSecurityAttributes,
              v12,
              TokenInformationLength,
              &TokenInformationLength) )
        goto LABEL_34;
      v17 = v12[1];
      if ( v17 )
      {
        TokenInformationLength = 4 * v17;
        P[0] = v12;
        P[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(4 * v17));
        if ( P[1] )
        {
          for ( i = 0; (unsigned int)i < v12[1]; i = (unsigned int)(i + 1) )
            *((_DWORD *)P[1] + i) = 4;
          v15 = SetTokenInformation(hObject, TokenSecurityAttributes, P, 0x10u);
LABEL_38:
          if ( v15 )
            goto LABEL_39;
LABEL_34:
          LastError = GetLastError();
          goto LABEL_15;
        }
LABEL_59:
        LastError = 14;
        goto LABEL_15;
      }
    }
    LastError = 315;
    goto LABEL_15;
  }
  if ( !CapabilityCount )
    goto LABEL_8;
LABEL_28:
  LastError = 87;
LABEL_24:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return LastError;
}

```

## disassembly

```asm
0x1800376bc  mov     [rsp-8+arg_10], rbx
0x1800376c1  push    rbp
0x1800376c2  push    rsi
0x1800376c3  push    rdi
0x1800376c4  push    r12
0x1800376c6  push    r13
0x1800376c8  push    r14
0x1800376ca  push    r15
0x1800376cc  lea     rbp, [rsp-0B0h]
0x1800376d4  sub     rsp, 1B0h
0x1800376db  mov     rax, cs:__security_cookie
0x1800376e2  xor     rax, rsp
0x1800376e5  mov     [rbp+0E0h+var_40], rax
0x1800376ec  mov     rax, [rbp+0E0h+arg_20]
0x1800376f3  xor     ebx, ebx
0x1800376f5  xorps   xmm0, xmm0
0x1800376f8  mov     [rsp+1E0h+var_170], rax
0x1800376fd  xor     eax, eax
0x1800376ff  mov     [rsp+1E0h+var_190], ebx
0x180037703  cmp     cs:?SuccessfulInit@@3KA, ebx; ulong SuccessfulInit
0x180037709  mov     rdi, r9
0x18003770c  mov     r12d, r8d
0x18003770f  mov     [rsp+1E0h+TokenInformationLength], ebx
0x180037713  mov     r13, rdx
0x180037716  mov     [rsp+1E0h+var_19C], bl
0x18003771a  mov     rsi, rcx
0x18003771d  mov     [rbp+0E0h+var_158], rax
0x180037721  movups  [rsp+1E0h+var_168], xmm0
0x180037726  mov     [rsp+1E0h+TokenHandle], rbx
0x18003772b  mov     [rsp+1E0h+hObject], rbx
0x180037730  movups  xmmword ptr [rsp+1E0h+P], xmm0
0x180037735  jnz     short loc_18003773F
0x180037737  lea     eax, [rbx+32h]
0x18003773a  jmp     loc_180037877
0x18003773f  test    r12d, r12d
0x180037742  jnz     short loc_18003776C
0x180037744  test    rdi, rdi
0x180037747  jz      loc_1800378A9
0x18003774d  cmp     [r9], rbx
0x180037750  jz      loc_1800378A9
0x180037756  mov     eax, [r9+10h]
0x18003775a  cmp     [r9+8], rbx
0x18003775e  jnz     loc_1800378A1
0x180037764  test    eax, eax
0x180037766  jnz     loc_1800378A9
0x18003776c  xor     ecx, ecx; BindingHandle
0x18003776e  mov     r14, rbx
0x180037771  mov     r15, rbx
0x180037774  call    cs:__imp_RpcImpersonateClient
0x18003777a  mov     ebx, eax
0x18003777c  test    eax, eax
0x18003777e  jnz     short loc_1800377F4
0x180037780  lea     rax, [rsp+1E0h+var_19C]
0x180037785  xor     edx, edx; void *
0x180037787  mov     [rsp+1E0h+var_1B0], rax; unsigned __int8 *
0x18003778c  lea     r9, ?CapConstrainedImpersonationSidBuffer@@3PAEA; void *
0x180037793  mov     byte ptr [rsp+1E0h+phNewToken], r14b; unsigned __int8
0x180037798  lea     r8, ?CapConstrainedImpersonationGroupSidBuffer@@3PAEA; void *
0x18003779f  xor     ecx, ecx; ClientToken
0x1800377a1  mov     byte ptr [rsp+1E0h+ReturnLength], 1; unsigned __int8
0x1800377a6  call    ?CheckTokenForAccessThroughCapability@@YAKPEAX000EEPEAE@Z; CheckTokenForAccessThroughCapability(void *,void *,void *,void *,uchar,uchar,uchar *)
0x1800377ab  mov     ebx, eax
0x1800377ad  test    eax, eax
0x1800377af  jnz     short loc_1800377EE
0x1800377b1  test    r12d, r12d
0x1800377b4  jz      loc_1800378B0
0x1800377ba  test    rsi, rsi
0x1800377bd  jnz     loc_1800378B0
0x1800377c3  call    cs:__imp_GetCurrentThread
0x1800377c9  mov     rcx, rax; ThreadHandle
0x1800377cc  lea     r9, [rsp+1E0h+TokenHandle]; TokenHandle
0x1800377d1  lea     edx, [rbx+0Ah]; DesiredAccess
0x1800377d4  lea     r8d, [rbx+1]; OpenAsSelf
0x1800377d8  call    cs:__imp_OpenThreadToken
0x1800377de  test    eax, eax
0x1800377e0  jnz     loc_1800378B0
0x1800377e6  call    cs:__imp_GetLastError
0x1800377ec  mov     ebx, eax
0x1800377ee  call    cs:__imp_RpcRevertToSelf
0x1800377f4  test    r12d, r12d
0x1800377f7  jz      short loc_180037826
0x1800377f9  test    r14, r14
0x1800377fc  jz      short loc_180037816
0x1800377fe  mov     rcx, gs:60h
0x180037807  mov     r8, r14; P
0x18003780a  xor     edx, edx; Flags
0x18003780c  mov     rcx, [rcx+30h]; HeapHandle
0x180037810  call    cs:__imp_RtlFreeHeap
0x180037816  mov     rcx, [rsp+1E0h+TokenHandle]; hObject
0x18003781b  test    rcx, rcx
0x18003781e  jz      short loc_180037826
0x180037820  call    cs:__imp_CloseHandle
0x180037826  test    r15, r15
0x180037829  jz      short loc_180037843
0x18003782b  mov     rcx, gs:60h
0x180037834  mov     r8, r15; P
0x180037837  xor     edx, edx; Flags
0x180037839  mov     rcx, [rcx+30h]; HeapHandle
0x18003783d  call    cs:__imp_RtlFreeHeap
0x180037843  mov     rcx, [rsp+1E0h+hObject]; hObject
0x180037848  test    rcx, rcx
0x18003784b  jz      short loc_180037853
0x18003784d  call    cs:__imp_CloseHandle
0x180037853  cmp     [rsp+1E0h+P+8], 0
0x180037859  jz      short loc_180037875
0x18003785b  mov     rcx, gs:60h
0x180037864  xor     edx, edx; Flags
0x180037866  mov     r8, [rsp+1E0h+P+8]; P
0x18003786b  mov     rcx, [rcx+30h]; HeapHandle
0x18003786f  call    cs:__imp_RtlFreeHeap
0x180037875  mov     eax, ebx
0x180037877  mov     rcx, [rbp+0E0h+var_40]
0x18003787e  xor     rcx, rsp; StackCookie
0x180037881  call    __security_check_cookie
0x180037886  mov     rbx, [rsp+1E0h+arg_10]
0x18003788e  add     rsp, 1B0h
0x180037895  pop     r15
0x180037897  pop     r14
0x180037899  pop     r13
0x18003789b  pop     r12
0x18003789d  pop     rdi
0x18003789e  pop     rsi
0x18003789f  pop     rbp
0x1800378a0  retn
0x1800378a1  test    eax, eax
0x1800378a3  jnz     loc_18003776C
0x1800378a9  mov     ebx, 57h ; 'W'
0x1800378ae  jmp     short loc_180037853
0x1800378b0  call    cs:__imp_RpcRevertToSelf
0x1800378b6  test    r12d, r12d
0x1800378b9  jz      short loc_1800378C5
0x1800378bb  test    rsi, rsi
0x1800378be  jnz     short loc_1800378C5
0x1800378c0  mov     rsi, [rsp+1E0h+TokenHandle]
0x1800378c5  lea     rax, [rsp+1E0h+TokenInformationLength]
0x1800378ca  mov     rcx, rsi; TokenHandle
0x1800378cd  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x1800378d2  cmp     [rsp+1E0h+var_19C], r14b
0x1800378d7  jnz     loc_18003797D
0x1800378dd  mov     edi, 54h ; 'T'
0x1800378e2  lea     r8, [rbp+0E0h+TokenInformation]; TokenInformation
0x1800378e6  mov     r9d, edi; TokenInformationLength
0x1800378e9  lea     edx, [rdi-53h]; TokenInformationClass
0x1800378ec  call    cs:__imp_GetTokenInformation
0x1800378f2  test    eax, eax
0x1800378f4  jnz     short loc_180037903
0x1800378f6  call    cs:__imp_GetLastError
0x1800378fc  mov     ebx, eax
0x1800378fe  jmp     loc_1800377F4
0x180037903  lea     rax, [rsp+1E0h+TokenInformationLength]
0x180037908  mov     r9d, edi; TokenInformationLength
0x18003790b  lea     r8, [rbp+0E0h+Sid2]; TokenInformation
0x18003790f  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x180037914  mov     edx, 1; TokenInformationClass
0x180037919  mov     rcx, r13; TokenHandle
0x18003791c  call    cs:__imp_GetTokenInformation
0x180037922  test    eax, eax
0x180037924  jz      short loc_1800378F6
0x180037926  mov     rdx, [rbp+0E0h+Sid2]; Sid2
0x18003792a  mov     rcx, [rbp+0E0h+TokenInformation]; Sid1
0x18003792e  call    cs:__imp_RtlEqualSid
0x180037934  test    al, al
0x180037936  jz      short loc_180037962
0x180037938  lea     rax, [rsp+1E0h+hObject]
0x18003793d  mov     r9d, 2; ImpersonationLevel
0x180037943  mov     [rsp+1E0h+phNewToken], rax; phNewToken
0x180037948  xor     r8d, r8d; lpTokenAttributes
0x18003794b  mov     edx, 0F01FFh; dwDesiredAccess
0x180037950  mov     dword ptr [rsp+1E0h+ReturnLength], r9d; TokenType
0x180037955  mov     rcx, rsi; hExistingToken
0x180037958  call    cs:__imp_DuplicateTokenEx
0x18003795e  test    eax, eax
0x180037960  jz      short loc_1800378F6
0x180037962  mov     rax, [rsp+1E0h+hObject]
0x180037967  mov     rcx, [rsp+1E0h+var_170]
0x18003796c  mov     [rsp+1E0h+hObject], 0
0x180037975  mov     [rcx], rax
0x180037978  jmp     loc_1800377F4
0x18003797d  mov     r9d, 4; TokenInformationLength
0x180037983  lea     r8, [rsp+1E0h+var_190]; TokenInformation
0x180037988  lea     edx, [r9+19h]; TokenInformationClass
0x18003798c  call    cs:__imp_GetTokenInformation
0x180037992  test    eax, eax
0x180037994  jz      loc_1800378F6
0x18003799a  lea     rax, [rsp+1E0h+TokenInformationLength]
0x18003799f  mov     rcx, rsi; TokenHandle
0x1800379a2  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x1800379a7  cmp     [rsp+1E0h+var_190], r14d
0x1800379ac  jnz     short loc_180037A0E
0x1800379ae  mov     edi, 54h ; 'T'
0x1800379b3  lea     r8, [rbp+0E0h+TokenInformation]; TokenInformation
0x1800379b7  mov     r9d, edi; TokenInformationLength
0x1800379ba  lea     edx, [rdi-53h]; TokenInformationClass
0x1800379bd  call    cs:__imp_GetTokenInformation
0x1800379c3  test    eax, eax
0x1800379c5  jz      loc_1800378F6
0x1800379cb  lea     rax, [rsp+1E0h+TokenInformationLength]
0x1800379d0  mov     r9d, edi; TokenInformationLength
0x1800379d3  lea     r8, [rbp+0E0h+Sid2]; TokenInformation
0x1800379d7  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x1800379dc  lea     edx, [rdi-53h]; TokenInformationClass
0x1800379df  mov     rcx, r13; TokenHandle
0x1800379e2  call    cs:__imp_GetTokenInformation
0x1800379e8  test    eax, eax
0x1800379ea  jz      loc_1800378F6
0x1800379f0  mov     rdx, [rbp+0E0h+Sid2]; Sid2
0x1800379f4  mov     rcx, [rbp+0E0h+TokenInformation]; Sid1
0x1800379f8  call    cs:__imp_RtlEqualSid
0x1800379fe  test    al, al
0x180037a00  jnz     loc_180037938
0x180037a06  lea     ebx, [rdi-22h]
0x180037a09  jmp     loc_1800377F4
0x180037a0e  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180037a14  lea     r8, [rbp+0E0h+Sid1]; TokenInformation
0x180037a18  lea     edx, [r9-2Dh]; TokenInformationClass
0x180037a1c  call    cs:__imp_GetTokenInformation
0x180037a22  test    eax, eax
0x180037a24  jz      loc_1800378F6
0x180037a2a  test    r12d, r12d
0x180037a2d  jz      loc_180037B60
0x180037a33  xor     r9d, r9d; TokenInformationLength
0x180037a36  lea     rax, [rsp+1E0h+TokenInformationLength]
0x180037a3b  xor     r8d, r8d; TokenInformation
0x180037a3e  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x180037a43  mov     rcx, rsi; TokenHandle
0x180037a46  lea     edi, [r9+1Eh]
0x180037a4a  mov     edx, edi; TokenInformationClass
0x180037a4c  call    cs:__imp_GetTokenInformation
0x180037a52  call    cs:__imp_GetLastError
0x180037a58  mov     ebx, eax
0x180037a5a  cmp     eax, 7Ah ; 'z'
0x180037a5d  jnz     loc_180037816
0x180037a63  mov     rcx, gs:60h
0x180037a6c  xor     edx, edx; Flags
0x180037a6e  mov     r8d, [rsp+1E0h+TokenInformationLength]; Size
0x180037a73  mov     rcx, [rcx+30h]; HeapHandle
0x180037a77  call    cs:__imp_RtlAllocateHeap
0x180037a7d  mov     r14, rax
0x180037a80  test    rax, rax
0x180037a83  jnz     short loc_180037A8D
0x180037a85  lea     ebx, [rdi-10h]
0x180037a88  jmp     loc_180037816
0x180037a8d  mov     r9d, [rsp+1E0h+TokenInformationLength]; TokenInformationLength
0x180037a92  lea     rax, [rsp+1E0h+TokenInformationLength]
0x180037a97  mov     r8, r14; TokenInformation
0x180037a9a  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x180037a9f  mov     edx, edi; TokenInformationClass
0x180037aa1  mov     rcx, rsi; TokenHandle
0x180037aa4  call    cs:__imp_GetTokenInformation
0x180037aaa  test    eax, eax
0x180037aac  jnz     short loc_180037ABB
0x180037aae  call    cs:__imp_GetLastError
0x180037ab4  mov     ebx, eax
0x180037ab6  jmp     loc_1800377FE
0x180037abb  mov     rax, [rbp+0E0h+Sid1]
0x180037abf  lea     rdi, [rsp+1E0h+var_168]
0x180037ac4  mov     qword ptr [rsp+1E0h+var_168], rax
0x180037ac9  mov     eax, [r14]
0x180037acc  mov     dword ptr [rbp+0E0h+var_158], eax
0x180037acf  lea     rax, [r14+8]
0x180037ad3  mov     qword ptr [rbp+0E0h+var_168+8], rax
0x180037ad7  lea     r8, [rsp+1E0h+hObject]
0x180037adc  mov     rdx, rdi
0x180037adf  mov     rcx, r13
0x180037ae2  call    cs:__imp_CreateAppContainerToken
0x180037ae8  test    eax, eax
0x180037aea  jz      loc_1800378F6
0x180037af0  xor     r9d, r9d; TokenInformationLength
0x180037af3  lea     rax, [rsp+1E0h+TokenInformationLength]
0x180037af8  xor     r8d, r8d; TokenInformation
0x180037afb  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x180037b00  mov     rcx, rsi; TokenHandle
0x180037b03  lea     edi, [r9+27h]
0x180037b07  mov     edx, edi; TokenInformationClass
0x180037b09  call    cs:__imp_GetTokenInformation
0x180037b0f  test    eax, eax
0x180037b11  jnz     loc_180037C1A
0x180037b17  call    cs:__imp_GetLastError
0x180037b1d  mov     ebx, eax
0x180037b1f  cmp     eax, 7Ah ; 'z'
0x180037b22  jnz     loc_1800377F4
0x180037b28  mov     eax, [rsp+1E0h+TokenInformationLength]
0x180037b2c  xor     ebx, ebx
0x180037b2e  test    eax, eax
0x180037b30  jz      loc_180037962
0x180037b36  mov     rcx, gs:60h
0x180037b3f  mov     r8d, eax; Size
0x180037b42  xor     edx, edx; Flags
0x180037b44  mov     rcx, [rcx+30h]; HeapHandle
0x180037b48  call    cs:__imp_RtlAllocateHeap
0x180037b4e  mov     r15, rax
0x180037b51  test    rax, rax
0x180037b54  jnz     short loc_180037B7F
0x180037b56  mov     ebx, 0Eh
0x180037b5b  jmp     loc_1800377F4
0x180037b60  mov     rdx, [rdi]; Sid2
0x180037b63  mov     rcx, [rbp+0E0h+Sid1]; Sid1
0x180037b67  call    cs:__imp_RtlEqualSid
0x180037b6d  test    al, al
0x180037b6f  jnz     loc_180037AD7
  ... truncated ...
```
