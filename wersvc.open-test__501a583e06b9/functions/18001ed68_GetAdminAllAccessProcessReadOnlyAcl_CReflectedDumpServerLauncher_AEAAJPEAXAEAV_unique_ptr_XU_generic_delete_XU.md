# ?GetAdminAllAccessProcessReadOnlyAcl@CReflectedDumpServerLauncher@@AEAAJPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@PEAU_SECURITY_ATTRIBUTES@@@Z

- ea: `0x18001ed68`
- end: `0x18001f038`
- name: `?GetAdminAllAccessProcessReadOnlyAcl@CReflectedDumpServerLauncher@@AEAAJPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001f040`

## callees

- `0x1800029d0`
- `0x180002a00`
- `0x180002ff0`
- `0x180006134`
- `0x180007cf8`
- `0x18000caf0`
- `0x18000cb10`
- `0x180013f54`
- `0x18001ed68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001edd7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001edd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee23`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ee19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ee78`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ee19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ee78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eeb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001efdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f016`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eeb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001efdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f016`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eeff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ef4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001efc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eeff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ef4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001efc0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001eed1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001eed1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001ef9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001ef9b`

## pseudocode

```c
__int64 __fastcall CReflectedDumpServerLauncher::GetAdminAllAccessProcessReadOnlyAcl(
        __int64 a1,
        void *a2,
        _QWORD *a3,
        __int64 a4)
{
  void **v7; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  PSID *v11; // rbx
  __int64 v12; // rdx
  const char *v13; // r9
  unsigned int v14; // edi
  const char *v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // esi
  PSECURITY_DESCRIPTOR *v20; // rax
  LPWSTR v21; // rcx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  HANDLE TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR StringSecurityDescriptor[128]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !a2 || !a4 )
  {
    LastError = -2147024809;
    v12 = 252;
    goto LABEL_34;
  }
  *(_OWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  v7 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( !OpenProcessToken(a2, 8u, v7) )
  {
    v9 = 256;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                  v8);
LABEL_35:
    if ( (unsigned __int64)TokenHandle + 1 > 1 )
      CloseHandle(TokenHandle);
    return LastError;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    v9 = 260;
    goto LABEL_5;
  }
  v11 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    LastError = -2147024882;
    v12 = 265;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)LastError,
      ReturnLength);
    goto LABEL_35;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x10F,
            (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
            v13);
LABEL_13:
    operator delete(v11);
    if ( (unsigned __int64)TokenHandle + 1 > 1 )
      CloseHandle(TokenHandle);
    return v14;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*v11, &StringSid) )
  {
    v17 = 275;
    goto LABEL_18;
  }
  v18 = StringCchPrintfW(
          StringSecurityDescriptor,
          0x80u,
          L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GR;;;%s)",
          StringSid);
  v19 = v18;
  if ( v18 >= 0 )
  {
    *(_DWORD *)a4 = 24;
    *(_DWORD *)(a4 + 16) = 0;
    v20 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(a3);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, v20, 0) )
    {
      v17 = 292;
LABEL_18:
      v14 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)v17,
              (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
              v16);
      if ( StringSid )
        LocalFree(StringSid);
      goto LABEL_13;
    }
    v21 = StringSid;
    *(_QWORD *)(a4 + 8) = *a3;
    if ( v21 )
      LocalFree(v21);
    operator delete(v11);
    if ( (unsigned __int64)TokenHandle + 1 > 1 )
      CloseHandle(TokenHandle);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)(unsigned int)v18,
      ReturnLengtha);
    if ( StringSid )
      LocalFree(StringSid);
    operator delete(v11);
    if ( (unsigned __int64)TokenHandle + 1 > 1 )
      CloseHandle(TokenHandle);
    return v19;
  }
}

```

## disassembly

```asm
0x18001ed68  push    rbp
0x18001ed6a  push    rbx
0x18001ed6b  push    rsi
0x18001ed6c  push    rdi
0x18001ed6d  push    r14
0x18001ed6f  lea     rbp, [rsp-60h]
0x18001ed74  sub     rsp, 160h
0x18001ed7b  mov     rax, cs:__security_cookie
0x18001ed82  xor     rax, rsp
0x18001ed85  mov     [rbp+80h+var_30], rax
0x18001ed89  mov     [rsp+180h+TokenHandle], 0
0x18001ed92  mov     rdi, r9
0x18001ed95  mov     [rsp+180h+TokenInformationLength], 0
0x18001ed9d  mov     r14, r8
0x18001eda0  mov     rbx, rdx
0x18001eda3  test    rdx, rdx
0x18001eda6  jz      loc_18001EFE7
0x18001edac  test    r9, r9
0x18001edaf  jz      loc_18001EFE7
0x18001edb5  xorps   xmm0, xmm0
0x18001edb8  lea     rcx, [rsp+180h+TokenHandle]
0x18001edbd  xor     eax, eax
0x18001edbf  movups  xmmword ptr [r9], xmm0
0x18001edc3  mov     [r9+10h], rax
0x18001edc7  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001edcc  mov     r8, rax; TokenHandle
0x18001edcf  mov     edx, 8; DesiredAccess
0x18001edd4  mov     rcx, rbx; ProcessHandle
0x18001edd7  call    cs:__imp_OpenProcessToken
0x18001eddd  test    eax, eax
0x18001eddf  jnz     short loc_18001EE00
0x18001ede1  mov     edx, 100h; void *
0x18001ede6  mov     rcx, [rbp+88h]; this
0x18001eded  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001edf4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001edf9  mov     ebx, eax
0x18001edfb  jmp     loc_18001F007
0x18001ee00  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x18001ee05  lea     rax, [rsp+180h+TokenInformationLength]
0x18001ee0a  xor     r9d, r9d; TokenInformationLength
0x18001ee0d  mov     qword ptr [rsp+180h+ReturnLength], rax; ReturnLength
0x18001ee12  xor     r8d, r8d; TokenInformation
0x18001ee15  lea     edx, [r9+1]; TokenInformationClass
0x18001ee19  call    cs:__imp_GetTokenInformation
0x18001ee1f  test    eax, eax
0x18001ee21  jnz     short loc_18001EE35
0x18001ee23  call    cs:__imp_GetLastError
0x18001ee29  cmp     eax, 7Ah ; 'z'
0x18001ee2c  jz      short loc_18001EE35
0x18001ee2e  mov     edx, 104h
0x18001ee33  jmp     short loc_18001EDE6
0x18001ee35  mov     ecx, [rsp+180h+TokenInformationLength]; unsigned __int64
0x18001ee39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ee40  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ee45  mov     rbx, rax
0x18001ee48  test    rax, rax
0x18001ee4b  jnz     short loc_18001EE5C
0x18001ee4d  mov     ebx, 8007000Eh
0x18001ee52  mov     edx, 109h
0x18001ee57  jmp     loc_18001EFF1
0x18001ee5c  mov     r9d, [rsp+180h+TokenInformationLength]; TokenInformationLength
0x18001ee61  lea     rax, [rsp+180h+TokenInformationLength]
0x18001ee66  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x18001ee6b  mov     r8, rbx; TokenInformation
0x18001ee6e  mov     edx, 1; TokenInformationClass
0x18001ee73  mov     qword ptr [rsp+180h+ReturnLength], rax; int
0x18001ee78  call    cs:__imp_GetTokenInformation
0x18001ee7e  test    eax, eax
0x18001ee80  jnz     short loc_18001EEC0
0x18001ee82  mov     rcx, [rbp+88h]; this
0x18001ee89  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001ee90  mov     edx, 10Fh; void *
0x18001ee95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ee9a  mov     edi, eax
0x18001ee9c  mov     rcx, rbx; Block
0x18001ee9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eea4  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x18001eea9  lea     rdx, [rcx+1]
0x18001eead  cmp     rdx, 1
0x18001eeb1  jbe     short loc_18001EEB9
0x18001eeb3  call    cs:__imp_CloseHandle
0x18001eeb9  mov     eax, edi
0x18001eebb  jmp     loc_18001F01E
0x18001eec0  mov     [rsp+180h+StringSid], 0
0x18001eec9  lea     rdx, [rsp+180h+StringSid]; StringSid
0x18001eece  mov     rcx, [rbx]; Sid
0x18001eed1  call    cs:__imp_ConvertSidToStringSidW
0x18001eed7  test    eax, eax
0x18001eed9  jnz     short loc_18001EF07
0x18001eedb  mov     edx, 113h; void *
0x18001eee0  mov     rcx, [rbp+88h]; this
0x18001eee7  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001eeee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001eef3  mov     rcx, [rsp+180h+StringSid]; hMem
0x18001eef8  mov     edi, eax
0x18001eefa  test    rcx, rcx
0x18001eefd  jz      short loc_18001EE9C
0x18001eeff  call    cs:__imp_LocalFree
0x18001ef05  jmp     short loc_18001EE9C
0x18001ef07  mov     r9, [rsp+180h+StringSid]
0x18001ef0c  lea     r8, aDPAOiciGaBaAOi_0; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;O"...
0x18001ef13  mov     edx, 80h; unsigned __int64
0x18001ef18  lea     rcx, [rsp+180h+StringSecurityDescriptor]; wchar_t *
0x18001ef1d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001ef22  mov     esi, eax
0x18001ef24  test    eax, eax
0x18001ef26  jns     short loc_18001EF77
0x18001ef28  mov     rcx, [rbp+88h]; this
0x18001ef2f  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001ef36  mov     r9d, eax; char *
0x18001ef39  mov     edx, 11Bh; void *
0x18001ef3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef43  mov     rcx, [rsp+180h+StringSid]; hMem
0x18001ef48  test    rcx, rcx
0x18001ef4b  jz      short loc_18001EF53
0x18001ef4d  call    cs:__imp_LocalFree
0x18001ef53  mov     rcx, rbx; Block
0x18001ef56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ef5b  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x18001ef60  lea     rax, [rcx+1]
0x18001ef64  cmp     rax, 1
0x18001ef68  jbe     short loc_18001EF70
0x18001ef6a  call    cs:__imp_CloseHandle
0x18001ef70  mov     eax, esi
0x18001ef72  jmp     loc_18001F01E
0x18001ef77  mov     rcx, r14
0x18001ef7a  mov     dword ptr [rdi], 18h
0x18001ef80  mov     dword ptr [rdi+10h], 0
0x18001ef87  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001ef8c  xor     r9d, r9d; SecurityDescriptorSize
0x18001ef8f  lea     rcx, [rsp+180h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001ef94  mov     r8, rax; SecurityDescriptor
0x18001ef97  lea     edx, [r9+1]; StringSDRevision
0x18001ef9b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001efa1  test    eax, eax
0x18001efa3  jnz     short loc_18001EFAF
0x18001efa5  mov     edx, 124h
0x18001efaa  jmp     loc_18001EEE0
0x18001efaf  mov     rcx, [rsp+180h+StringSid]; hMem
0x18001efb4  mov     rax, [r14]
0x18001efb7  mov     [rdi+8], rax
0x18001efbb  test    rcx, rcx
0x18001efbe  jz      short loc_18001EFC6
0x18001efc0  call    cs:__imp_LocalFree
0x18001efc6  mov     rcx, rbx; Block
0x18001efc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001efce  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x18001efd3  lea     rax, [rcx+1]
0x18001efd7  cmp     rax, 1
0x18001efdb  jbe     short loc_18001EFE3
0x18001efdd  call    cs:__imp_CloseHandle
0x18001efe3  xor     eax, eax
0x18001efe5  jmp     short loc_18001F01E
0x18001efe7  mov     ebx, 80070057h
0x18001efec  mov     edx, 0FCh; void *
0x18001eff1  mov     rcx, [rbp+88h]; this
0x18001eff8  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001efff  mov     r9d, ebx; char *
0x18001f002  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f007  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x18001f00c  lea     rdx, [rcx+1]
0x18001f010  cmp     rdx, 1
0x18001f014  jbe     short loc_18001F01C
0x18001f016  call    cs:__imp_CloseHandle
0x18001f01c  mov     eax, ebx
0x18001f01e  mov     rcx, [rbp+80h+var_30]
0x18001f022  xor     rcx, rsp; StackCookie
0x18001f025  call    __security_check_cookie
0x18001f02a  add     rsp, 160h
0x18001f031  pop     r14
0x18001f033  pop     rdi
0x18001f034  pop     rsi
0x18001f035  pop     rbx
0x18001f036  pop     rbp
0x18001f037  retn
```
