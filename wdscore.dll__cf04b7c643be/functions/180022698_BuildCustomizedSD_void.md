# BuildCustomizedSD(void *)

- ea: `0x180022698`
- end: `0x180022b79`
- name: `?BuildCustomizedSD@@YAPEAXPEAX@Z`
- size: `1249`
- prototype: `void *__fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022bf8`
- `0x180022ca8`
- `0x180022d74`

## callees

- `0x180022698`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800228d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022989`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800228d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022989`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029699`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029699`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022972`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022afb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029685`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022972`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022afb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002282c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002282c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022800`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022859`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022859`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002281c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002281c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029665`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800226fd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800226fd`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800229b6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800229b6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022923`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022939`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002294c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002295d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022923`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022939`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002294c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002295d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180022a38`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180022a38`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022a72`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022a72`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800229dc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180022a00`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180022a20`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180022a53`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800229dc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180022a00`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180022a20`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180022a53`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002288d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002290a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002288d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002290a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002274d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002279e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800227ec`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002274d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002279e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800227ec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022a8e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022aac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022aca`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029608`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029628`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029648`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022a8e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022aac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022aca`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029608`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029628`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029648`

## pseudocode

```c
struct _ACL *__fastcall BuildCustomizedSD(PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  int v2; // r15d
  struct _ACL *v3; // rdi
  PSID *v4; // r14
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  DWORD LengthSid; // esi
  DWORD v10; // edi
  DWORD v11; // ebx
  DWORD v12; // esi
  HANDLE v13; // rax
  struct _ACL *v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD ReturnLength; // [rsp+60h] [rbp-78h] BYREF
  PSID pSid1; // [rsp+68h] [rbp-70h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-68h] BYREF
  PSID pSid; // [rsp+78h] [rbp-60h] BYREF
  PSID v22; // [rsp+80h] [rbp-58h] BYREF
  PSID *v23; // [rsp+88h] [rbp-50h]
  struct _ACL *v24; // [rsp+90h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-40h] BYREF

  v2 = 0;
  pSid = 0;
  v22 = 0;
  pSid1 = 0;
  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  TokenHandle = 0;
  ReturnLength = 0;
  v4 = 0;
  v23 = 0;
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v22) )
      {
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
            || GetLastError() == 1008
            && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
          {
            if ( TokenHandle )
            {
              if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength) && GetLastError() == 122 )
              {
                v7 = ReturnLength;
                ProcessHeap = GetProcessHeap();
                v4 = (PSID *)HeapAlloc(ProcessHeap, 8u, v7);
                v23 = v4;
                if ( v4 )
                {
                  if ( GetTokenInformation(TokenHandle, TokenUser, v4, ReturnLength, &ReturnLength) )
                  {
                    LengthSid = GetLengthSid(pSid);
                    v10 = GetLengthSid(v22);
                    v11 = GetLengthSid(pSid1);
                    v12 = v10 + 52 + v11 + GetLengthSid(*v4) + LengthSid;
                    v13 = GetProcessHeap();
                    v14 = (struct _ACL *)HeapAlloc(v13, 8u, v12);
                    v3 = v14;
                    v24 = v14;
                    if ( v14 )
                    {
                      if ( InitializeAcl(v14, v12, 2u)
                        && AddAccessAllowedAce(v3, 2u, 0xC01F0000, pSid)
                        && AddAccessAllowedAce(v3, 2u, 0xC01F0000, v22)
                        && AddAccessAllowedAce(v3, 2u, 0xC0110000, pSid1)
                        && (EqualSid(pSid1, *v4) || AddAccessAllowedAce(v3, 2u, 0xC01F0000, *v4)) )
                      {
                        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v3, 0) )
                          v2 = 1;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( v22 )
  {
    FreeSid(v22);
    v22 = 0;
  }
  if ( pSid1 )
  {
    FreeSid(pSid1);
    pSid1 = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v4 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v4);
  }
  if ( !v2 && v3 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180022698  mov     r11, rsp
0x18002269b  mov     [r11+10h], rbx
0x18002269f  mov     [r11+18h], rsi
0x1800226a3  push    rdi
0x1800226a4  push    r12
0x1800226a6  push    r13
0x1800226a8  push    r14
0x1800226aa  push    r15
0x1800226ac  sub     rsp, 0B0h
0x1800226b3  mov     rax, cs:__security_cookie
0x1800226ba  xor     rax, rsp
0x1800226bd  mov     [rsp+0D8h+var_38], rax
0x1800226c5  mov     r12, rcx
0x1800226c8  xor     r13d, r13d
0x1800226cb  mov     r15d, r13d
0x1800226ce  mov     [r11-60h], r13
0x1800226d2  mov     [r11-58h], r13
0x1800226d6  mov     [r11-70h], r13
0x1800226da  mov     edi, r13d
0x1800226dd  mov     [r11-40h], r13d
0x1800226e1  mov     word ptr [r11-3Ch], 500h
0x1800226e8  mov     [r11-68h], r13
0x1800226ec  mov     [r11-78h], r13d
0x1800226f0  mov     r14d, r13d
0x1800226f3  mov     [r11-50h], r13
0x1800226f7  lea     esi, [r13+1]
0x1800226fb  mov     edx, esi; dwRevision
0x1800226fd  call    cs:__imp_InitializeSecurityDescriptor
0x180022704  nop     dword ptr [rax+rax+00h]
0x180022709  test    eax, eax
0x18002270b  jz      loc_180022A84
0x180022711  lea     rax, [rsp+0D8h+var_60]
0x180022716  mov     [rsp+0D8h+pSid], rax; pSid
0x18002271b  mov     [rsp+0D8h+nSubAuthority7], r13d; nSubAuthority7
0x180022720  mov     [rsp+0D8h+nSubAuthority6], r13d; nSubAuthority6
0x180022725  mov     [rsp+0D8h+nSubAuthority5], r13d; nSubAuthority5
0x18002272a  mov     [rsp+0D8h+nSubAuthority4], r13d; nSubAuthority4
0x18002272f  mov     [rsp+0D8h+nSubAuthority3], r13d; nSubAuthority3
0x180022734  mov     [rsp+0D8h+nSubAuthority2], r13d; nSubAuthority2
0x180022739  mov     r9d, 220h; nSubAuthority1
0x18002273f  lea     r8d, [r13+20h]; nSubAuthority0
0x180022743  mov     dl, 2; nSubAuthorityCount
0x180022745  lea     rcx, [rsp+0D8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002274d  call    cs:__imp_AllocateAndInitializeSid
0x180022754  nop     dword ptr [rax+rax+00h]
0x180022759  test    eax, eax
0x18002275b  jz      loc_180022A84
0x180022761  lea     rax, [rsp+0D8h+var_58]
0x180022769  mov     [rsp+0D8h+pSid], rax; pSid
0x18002276e  mov     [rsp+0D8h+nSubAuthority7], r13d; nSubAuthority7
0x180022773  mov     [rsp+0D8h+nSubAuthority6], r13d; nSubAuthority6
0x180022778  mov     [rsp+0D8h+nSubAuthority5], r13d; nSubAuthority5
0x18002277d  mov     [rsp+0D8h+nSubAuthority4], r13d; nSubAuthority4
0x180022782  mov     [rsp+0D8h+nSubAuthority3], r13d; nSubAuthority3
0x180022787  mov     [rsp+0D8h+nSubAuthority2], r13d; nSubAuthority2
0x18002278c  xor     r9d, r9d; nSubAuthority1
0x18002278f  lea     r8d, [r13+12h]; nSubAuthority0
0x180022793  mov     dl, sil; nSubAuthorityCount
0x180022796  lea     rcx, [rsp+0D8h+pIdentifierAuthority]; pIdentifierAuthority
0x18002279e  call    cs:__imp_AllocateAndInitializeSid
0x1800227a5  nop     dword ptr [rax+rax+00h]
0x1800227aa  test    eax, eax
0x1800227ac  jz      loc_180022A84
0x1800227b2  lea     rax, [rsp+0D8h+pSid1]
0x1800227b7  mov     [rsp+0D8h+pSid], rax; pSid
0x1800227bc  mov     [rsp+0D8h+nSubAuthority7], r13d; nSubAuthority7
0x1800227c1  mov     [rsp+0D8h+nSubAuthority6], r13d; nSubAuthority6
0x1800227c6  mov     [rsp+0D8h+nSubAuthority5], r13d; nSubAuthority5
0x1800227cb  mov     [rsp+0D8h+nSubAuthority4], r13d; nSubAuthority4
0x1800227d0  mov     [rsp+0D8h+nSubAuthority3], r13d; nSubAuthority3
0x1800227d5  mov     [rsp+0D8h+nSubAuthority2], r13d; nSubAuthority2
0x1800227da  xor     r9d, r9d; nSubAuthority1
0x1800227dd  lea     r8d, [r13+13h]; nSubAuthority0
0x1800227e1  mov     dl, sil; nSubAuthorityCount
0x1800227e4  lea     rcx, [rsp+0D8h+pIdentifierAuthority]; pIdentifierAuthority
0x1800227ec  call    cs:__imp_AllocateAndInitializeSid
0x1800227f3  nop     dword ptr [rax+rax+00h]
0x1800227f8  test    eax, eax
0x1800227fa  jz      loc_180022A84
0x180022800  call    cs:__imp_GetCurrentThread
0x180022807  nop     dword ptr [rax+rax+00h]
0x18002280c  mov     rcx, rax; ThreadHandle
0x18002280f  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x180022814  mov     r8d, esi; OpenAsSelf
0x180022817  lea     ebx, [rsi+7]
0x18002281a  mov     edx, ebx; DesiredAccess
0x18002281c  call    cs:__imp_OpenThreadToken
0x180022823  nop     dword ptr [rax+rax+00h]
0x180022828  test    eax, eax
0x18002282a  jnz     short loc_18002286D
0x18002282c  call    cs:__imp_GetLastError
0x180022833  nop     dword ptr [rax+rax+00h]
0x180022838  cmp     eax, 3F0h
0x18002283d  jnz     loc_180022A84
0x180022843  call    cs:__imp_GetCurrentProcess
0x18002284a  nop     dword ptr [rax+rax+00h]
0x18002284f  mov     rcx, rax; ProcessHandle
0x180022852  lea     r8, [rsp+0D8h+TokenHandle]; TokenHandle
0x180022857  mov     edx, ebx; DesiredAccess
0x180022859  call    cs:__imp_OpenProcessToken
0x180022860  nop     dword ptr [rax+rax+00h]
0x180022865  test    eax, eax
0x180022867  jz      loc_180022A84
0x18002286d  mov     rcx, [rsp+0D8h+TokenHandle]; TokenHandle
0x180022872  test    rcx, rcx
0x180022875  jz      loc_180022A84
0x18002287b  lea     rax, [rsp+0D8h+ReturnLength]
0x180022880  mov     qword ptr [rsp+0D8h+nSubAuthority2], rax; ReturnLength
0x180022885  xor     r9d, r9d; TokenInformationLength
0x180022888  xor     r8d, r8d; TokenInformation
0x18002288b  mov     edx, esi; TokenInformationClass
0x18002288d  call    cs:__imp_GetTokenInformation
0x180022894  nop     dword ptr [rax+rax+00h]
0x180022899  test    eax, eax
0x18002289b  jnz     loc_180022A84
0x1800228a1  call    cs:__imp_GetLastError
0x1800228a8  nop     dword ptr [rax+rax+00h]
0x1800228ad  cmp     eax, 7Ah ; 'z'
0x1800228b0  jnz     loc_180022A84
0x1800228b6  mov     ebx, [rsp+0D8h+ReturnLength]
0x1800228ba  call    cs:__imp_GetProcessHeap
0x1800228c1  nop     dword ptr [rax+rax+00h]
0x1800228c6  mov     r8d, ebx; dwBytes
0x1800228c9  mov     edx, 8; dwFlags
0x1800228ce  mov     rcx, rax; hHeap
0x1800228d1  call    cs:__imp_HeapAlloc
0x1800228d8  nop     dword ptr [rax+rax+00h]
0x1800228dd  mov     r14, rax
0x1800228e0  mov     [rsp+0D8h+var_50], rax
0x1800228e8  test    rax, rax
0x1800228eb  jz      loc_180022A84
0x1800228f1  lea     rax, [rsp+0D8h+ReturnLength]
0x1800228f6  mov     qword ptr [rsp+0D8h+nSubAuthority2], rax; ReturnLength
0x1800228fb  mov     r9d, [rsp+0D8h+ReturnLength]; TokenInformationLength
0x180022900  mov     r8, r14; TokenInformation
0x180022903  mov     edx, esi; TokenInformationClass
0x180022905  mov     rcx, [rsp+0D8h+TokenHandle]; TokenHandle
0x18002290a  call    cs:__imp_GetTokenInformation
0x180022911  nop     dword ptr [rax+rax+00h]
0x180022916  test    eax, eax
0x180022918  jz      loc_180022A84
0x18002291e  mov     rcx, [rsp+0D8h+var_60]; pSid
0x180022923  call    cs:__imp_GetLengthSid
0x18002292a  nop     dword ptr [rax+rax+00h]
0x18002292f  mov     esi, eax
0x180022931  mov     rcx, [rsp+0D8h+var_58]; pSid
0x180022939  call    cs:__imp_GetLengthSid
0x180022940  nop     dword ptr [rax+rax+00h]
0x180022945  mov     edi, eax
0x180022947  mov     rcx, [rsp+0D8h+pSid1]; pSid
0x18002294c  call    cs:__imp_GetLengthSid
0x180022953  nop     dword ptr [rax+rax+00h]
0x180022958  mov     ebx, eax
0x18002295a  mov     rcx, [r14]; pSid
0x18002295d  call    cs:__imp_GetLengthSid
0x180022964  nop     dword ptr [rax+rax+00h]
0x180022969  add     eax, ebx
0x18002296b  add     edi, 34h ; '4'
0x18002296e  add     eax, edi
0x180022970  add     esi, eax
0x180022972  call    cs:__imp_GetProcessHeap
0x180022979  nop     dword ptr [rax+rax+00h]
0x18002297e  mov     rcx, rax; hHeap
0x180022981  mov     r8d, esi; dwBytes
0x180022984  mov     edx, 8; dwFlags
0x180022989  call    cs:__imp_HeapAlloc
0x180022990  nop     dword ptr [rax+rax+00h]
0x180022995  mov     rdi, rax
0x180022998  mov     [rsp+0D8h+var_48], rax
0x1800229a0  test    rax, rax
0x1800229a3  jz      loc_180022A84
0x1800229a9  mov     ebx, 2
0x1800229ae  mov     r8d, ebx; dwAclRevision
0x1800229b1  mov     edx, esi; nAclLength
0x1800229b3  mov     rcx, rax; pAcl
0x1800229b6  call    cs:__imp_InitializeAcl
0x1800229bd  nop     dword ptr [rax+rax+00h]
0x1800229c2  test    eax, eax
0x1800229c4  jz      loc_180022A84
0x1800229ca  mov     r9, [rsp+0D8h+var_60]; pSid
0x1800229cf  mov     esi, 0C01F0000h
0x1800229d4  mov     r8d, esi; AccessMask
0x1800229d7  mov     edx, ebx; dwAceRevision
0x1800229d9  mov     rcx, rdi; pAcl
0x1800229dc  call    cs:__imp_AddAccessAllowedAce
0x1800229e3  nop     dword ptr [rax+rax+00h]
0x1800229e8  test    eax, eax
0x1800229ea  jz      loc_180022A84
0x1800229f0  mov     r9, [rsp+0D8h+var_58]; pSid
0x1800229f8  mov     r8d, esi; AccessMask
0x1800229fb  mov     edx, ebx; dwAceRevision
0x1800229fd  mov     rcx, rdi; pAcl
0x180022a00  call    cs:__imp_AddAccessAllowedAce
0x180022a07  nop     dword ptr [rax+rax+00h]
0x180022a0c  test    eax, eax
0x180022a0e  jz      short loc_180022A84
0x180022a10  mov     r9, [rsp+0D8h+pSid1]; pSid
0x180022a15  mov     r8d, 0C0110000h; AccessMask
0x180022a1b  mov     edx, ebx; dwAceRevision
0x180022a1d  mov     rcx, rdi; pAcl
0x180022a20  call    cs:__imp_AddAccessAllowedAce
0x180022a27  nop     dword ptr [rax+rax+00h]
0x180022a2c  test    eax, eax
0x180022a2e  jz      short loc_180022A84
0x180022a30  mov     rdx, [r14]; pSid2
0x180022a33  mov     rcx, [rsp+0D8h+pSid1]; pSid1
0x180022a38  call    cs:__imp_EqualSid
0x180022a3f  nop     dword ptr [rax+rax+00h]
0x180022a44  test    eax, eax
0x180022a46  jnz     short loc_180022A63
0x180022a48  mov     r9, [r14]; pSid
0x180022a4b  mov     r8d, esi; AccessMask
0x180022a4e  mov     edx, ebx; dwAceRevision
0x180022a50  mov     rcx, rdi; pAcl
0x180022a53  call    cs:__imp_AddAccessAllowedAce
0x180022a5a  nop     dword ptr [rax+rax+00h]
0x180022a5f  test    eax, eax
0x180022a61  jz      short loc_180022A84
0x180022a63  xor     r9d, r9d; bDaclDefaulted
0x180022a66  mov     r8, rdi; pDacl
0x180022a69  lea     ebx, [r9+1]
0x180022a6d  mov     edx, ebx; bDaclPresent
0x180022a6f  mov     rcx, r12; pSecurityDescriptor
0x180022a72  call    cs:__imp_SetSecurityDescriptorDacl
0x180022a79  nop     dword ptr [rax+rax+00h]
0x180022a7e  test    eax, eax
0x180022a80  cmovnz  r15d, ebx
0x180022a84  mov     rcx, [rsp+0D8h+var_60]; pSid
0x180022a89  test    rcx, rcx
0x180022a8c  jz      short loc_180022A9F
0x180022a8e  call    cs:__imp_FreeSid
0x180022a95  nop     dword ptr [rax+rax+00h]
0x180022a9a  mov     [rsp+0D8h+var_60], r13
0x180022a9f  mov     rcx, [rsp+0D8h+var_58]; pSid
0x180022aa7  test    rcx, rcx
0x180022aaa  jz      short loc_180022AC0
0x180022aac  call    cs:__imp_FreeSid
0x180022ab3  nop     dword ptr [rax+rax+00h]
0x180022ab8  mov     [rsp+0D8h+var_58], r13
0x180022ac0  mov     rcx, [rsp+0D8h+pSid1]; pSid
0x180022ac5  test    rcx, rcx
0x180022ac8  jz      short loc_180022ADB
0x180022aca  call    cs:__imp_FreeSid
0x180022ad1  nop     dword ptr [rax+rax+00h]
0x180022ad6  mov     [rsp+0D8h+pSid1], r13
0x180022adb  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180022ae0  test    rcx, rcx
0x180022ae3  jz      short loc_180022AF6
0x180022ae5  call    cs:__imp_CloseHandle
0x180022aec  nop     dword ptr [rax+rax+00h]
0x180022af1  mov     [rsp+0D8h+TokenHandle], r13
0x180022af6  test    r14, r14
0x180022af9  jz      short loc_180022B1B
0x180022afb  call    cs:__imp_GetProcessHeap
0x180022b02  nop     dword ptr [rax+rax+00h]
0x180022b07  mov     rcx, rax; hHeap
0x180022b0a  mov     r8, r14; lpMem
0x180022b0d  xor     edx, edx; dwFlags
0x180022b0f  call    cs:__imp_HeapFree
0x180022b16  nop     dword ptr [rax+rax+00h]
0x180022b1b  test    r15d, r15d
0x180022b1e  jnz     short loc_180022B48
0x180022b20  test    rdi, rdi
0x180022b23  jz      short loc_180022B48
0x180022b25  call    cs:__imp_GetProcessHeap
0x180022b2c  nop     dword ptr [rax+rax+00h]
0x180022b31  mov     rcx, rax; hHeap
0x180022b34  mov     r8, rdi; lpMem
0x180022b37  xor     edx, edx; dwFlags
0x180022b39  call    cs:__imp_HeapFree
0x180022b40  nop     dword ptr [rax+rax+00h]
0x180022b45  mov     rdi, r13
0x180022b48  mov     rax, rdi
0x180022b4b  mov     rcx, [rsp+0D8h+var_38]
0x180022b53  xor     rcx, rsp; StackCookie
0x180022b56  call    __security_check_cookie
0x180022b5b  lea     r11, [rsp+0D8h+var_28]
0x180022b63  mov     rbx, [r11+38h]
0x180022b67  mov     rsi, [r11+40h]
0x180022b6b  mov     rsp, r11
0x180022b6e  pop     r15
0x180022b70  pop     r14
0x180022b72  pop     r13
0x180022b74  pop     r12
0x180022b76  pop     rdi
0x180022b77  retn
0x1800295f5  push    rbx
0x1800295f7  push    rbp
0x1800295f8  sub     rsp, 68h
0x1800295fc  mov     rbp, rdx
0x1800295ff  mov     rcx, [rbp+78h]; pSid
0x180029603  test    rcx, rcx
0x180029606  jz      short loc_18002961C
0x180029608  call    cs:__imp_FreeSid
0x18002960f  nop     dword ptr [rax+rax+00h]
0x180029614  mov     qword ptr [rbp+78h], 0
0x18002961c  mov     rcx, [rbp+80h]; pSid
0x180029623  test    rcx, rcx
0x180029626  jz      short loc_18002963F
0x180029628  call    cs:__imp_FreeSid
  ... truncated ...
```
