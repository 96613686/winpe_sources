# GetProcessElevationStates(LuaElevationStates *)

- ea: `0x180171514`
- end: `0x1801718b8`
- name: `?GetProcessElevationStates@@YAJPEAW4LuaElevationStates@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(enum LuaElevationStates *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801711b0`

## callees

- `0x18007ea3c`
- `0x180171514`
- `0x180359760`
- `0x18035fa60`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18017155a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18017155a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180171543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180171543`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180171789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801718a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180171789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801718a7`
- `ntdll!NtQueryInformationToken` at `0x1801715aa`
- `ntdll!NtQueryInformationToken` at `0x1801716a2`
- `ntdll!NtQueryInformationToken` at `0x1801716e2`
- `ntdll!NtQueryInformationToken` at `0x180171731`
- `ntdll!NtQueryInformationToken` at `0x1801715aa`
- `ntdll!NtQueryInformationToken` at `0x1801716a2`
- `ntdll!NtQueryInformationToken` at `0x1801716e2`
- `ntdll!NtQueryInformationToken` at `0x180171731`
- `ntdll!RtlCompareUnicodeString` at `0x1801717b1`
- `ntdll!RtlCompareUnicodeString` at `0x1801717db`
- `ntdll!RtlCompareUnicodeString` at `0x180171801`
- `ntdll!RtlCompareUnicodeString` at `0x180171838`
- `ntdll!RtlCompareUnicodeString` at `0x1801717b1`
- `ntdll!RtlCompareUnicodeString` at `0x1801717db`
- `ntdll!RtlCompareUnicodeString` at `0x180171801`
- `ntdll!RtlCompareUnicodeString` at `0x180171838`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180171703`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180171703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180171611`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180171611`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProcessElevationStates(enum LuaElevationStates *a1)
{
  BOOL v2; // r14d
  HANDLE CurrentProcess; // rax
  wil::details *v4; // rcx
  void *v5; // rsi
  int v6; // r15d
  int v7; // r12d
  int v8; // r13d
  NTSTATUS v9; // edi
  unsigned int LastErrorFailHr; // ebx
  bool v12; // zf
  __int64 v13; // rsi
  HLOCAL v14; // r15
  int v15; // eax
  int ReturnLength; // [rsp+20h] [rbp-48h]
  int TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+34h] [rbp-34h] BYREF
  int v19; // [rsp+38h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  ULONG v21; // [rsp+48h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v2 = 0;
  *(_DWORD *)a1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastErrorFailHr;
  }
  v5 = TokenHandle;
  TokenInformationLength = 0;
  v6 = 0;
  v19 = 0;
  v21 = 0;
  LODWORD(v20) = 0;
  TokenInformation = 1;
  v7 = 1;
  v8 = 0;
  v9 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &v21);
  if ( v9 < 0 )
    goto LABEL_5;
  if ( TokenInformation != 2 )
  {
    if ( TokenInformation == 1 )
    {
      v7 = 0;
      v9 = NtQueryInformationToken(v5, TokenElevation, &v20, 4u, &v21);
      if ( v9 >= 0 )
      {
        if ( (_DWORD)v20 )
        {
          LODWORD(v13) = 0;
          goto LABEL_12;
        }
      }
    }
LABEL_5:
    if ( v9 < 0 )
      goto LABEL_6;
    LODWORD(v13) = 0;
    goto LABEL_11;
  }
  v9 = NtQueryInformationToken(v5, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v9 == -1073741789 )
  {
    v14 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v14 )
    {
      v9 = -1073741801;
      goto LABEL_6;
    }
    v9 = NtQueryInformationToken(v5, TokenSecurityAttributes, v14, TokenInformationLength, &TokenInformationLength);
    v13 = 0;
    if ( v9 < 0 )
    {
      v8 = 1;
      v7 = 1;
    }
    else
    {
      v7 = 1;
      while ( 1 )
      {
        if ( (unsigned int)v13 >= *((_DWORD *)v14 + 1) )
        {
          v15 = v19;
          goto LABEL_34;
        }
        v20 = 5 * v13;
        if ( !RtlCompareUnicodeString(&stru_180697428, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 40 * v13), 1u) )
          break;
        if ( !RtlCompareUnicodeString(&stru_180697438, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * v20), 1u) )
          goto LABEL_47;
        if ( RtlCompareUnicodeString(&stru_180697448, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * v20), 1u) )
        {
          if ( !RtlCompareUnicodeString(&stru_180697470, (PCUNICODE_STRING)(*((_QWORD *)v14 + 1) + 8 * v20), 1u) )
            v2 = 1;
        }
        else
        {
          v8 = 1;
          v2 = 1;
        }
        v13 = (unsigned int)(v13 + 1);
      }
      v8 = 1;
LABEL_47:
      v15 = 1;
      v19 = 1;
LABEL_34:
      LODWORD(v13) = 0;
      if ( v2 )
        LODWORD(v13) = v15 == 0;
      v12 = v8 == 0;
      v8 = 1;
      v2 = !v12;
    }
    LocalFree(v14);
    v6 = v19;
  }
  else
  {
    LODWORD(v13) = 0;
    v8 = 1;
    v7 = 1;
  }
  if ( v9 < 0 )
  {
LABEL_6:
    LastErrorFailHr = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x16B2,
                        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\util.cpp",
                        (const char *)(unsigned int)v9,
                        ReturnLength);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastErrorFailHr;
  }
LABEL_11:
  if ( v8 )
LABEL_12:
    *(_DWORD *)a1 |= 1u;
  if ( v7 )
    *(_DWORD *)a1 |= 2u;
  if ( v6 )
    *(_DWORD *)a1 |= 4u;
  if ( (_DWORD)v13 )
    *(_DWORD *)a1 |= 8u;
  if ( v2 )
    *(_DWORD *)a1 |= 0x10u;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180171514  push    rbp
0x180171516  push    rbx
0x180171517  push    rsi
0x180171518  push    rdi
0x180171519  push    r12
0x18017151b  push    r13
0x18017151d  push    r14
0x18017151f  push    r15
0x180171521  mov     rbp, rsp
0x180171524  sub     rsp, 68h
0x180171528  mov     rax, cs:__security_cookie
0x18017152f  xor     rax, rsp
0x180171532  mov     [rbp+var_10], rax
0x180171536  mov     rbx, rcx
0x180171539  xor     r14d, r14d
0x18017153c  mov     [rcx], r14d
0x18017153f  mov     [rbp+TokenHandle], r14
0x180171543  call    cs:__imp_GetCurrentProcess
0x18017154a  nop     dword ptr [rax+rax+00h]
0x18017154f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180171553  lea     edx, [r14+8]; DesiredAccess
0x180171557  mov     rcx, rax; ProcessHandle
0x18017155a  call    cs:__imp_OpenProcessToken
0x180171561  nop     dword ptr [rax+rax+00h]
0x180171566  test    eax, eax
0x180171568  jz      loc_180171770
0x18017156e  mov     rsi, [rbp+TokenHandle]
0x180171572  mov     [rbp+TokenInformationLength], r14d
0x180171576  mov     r15d, r14d
0x180171579  mov     [rbp+var_30], r14d
0x18017157d  mov     [rbp+var_20], r14d
0x180171581  mov     dword ptr [rbp+var_28], r14d
0x180171585  lea     eax, [r14+1]
0x180171589  mov     [rbp+TokenInformation], eax
0x18017158c  mov     r12d, eax
0x18017158f  mov     r13d, r14d
0x180171592  lea     rax, [rbp+var_20]
0x180171596  mov     qword ptr [rsp+68h+ReturnLength], rax; int
0x18017159b  lea     r9d, [r14+4]; TokenInformationLength
0x18017159f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1801715a3  lea     edx, [r14+12h]; TokenInformationClass
0x1801715a7  mov     rcx, rsi; TokenHandle
0x1801715aa  call    cs:__imp_NtQueryInformationToken
0x1801715b1  nop     dword ptr [rax+rax+00h]
0x1801715b6  mov     edi, eax
0x1801715b8  test    eax, eax
0x1801715ba  js      short loc_1801715D0
0x1801715bc  cmp     [rbp+TokenInformation], 2
0x1801715c0  jz      loc_1801716C9
0x1801715c6  cmp     [rbp+TokenInformation], r12d
0x1801715ca  jz      loc_180171685
0x1801715d0  test    edi, edi
0x1801715d2  jns     loc_180171681
0x1801715d8  mov     rcx, [rbp+40h]; this
0x1801715dc  mov     r9d, edi; char *
0x1801715df  lea     r8, aOnecoreuapShel_50; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801715e6  mov     edx, 16B2h; void *
0x1801715eb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801715f0  mov     ebx, eax
0x1801715f2  lea     rcx, [rbp+TokenHandle]
0x1801715f6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801715fb  mov     eax, ebx
0x1801715fd  jmp     short loc_180171663
0x1801715ff  xor     r14d, r14d
0x180171602  test    r13d, r13d
0x180171605  mov     r13d, r12d
0x180171608  jnz     loc_180171877
0x18017160e  mov     rcx, r15; hMem
0x180171611  call    cs:__imp_LocalFree
0x180171618  nop     dword ptr [rax+rax+00h]
0x18017161d  mov     r15d, [rbp+var_30]
0x180171621  test    edi, edi
0x180171623  js      short loc_1801715D8
0x180171625  test    r13d, r13d
0x180171628  jz      short loc_18017162D
0x18017162a  or      dword ptr [rbx], 1
0x18017162d  test    r12d, r12d
0x180171630  jz      short loc_180171635
0x180171632  or      dword ptr [rbx], 2
0x180171635  test    r15d, r15d
0x180171638  jnz     loc_18017184C
0x18017163e  test    esi, esi
0x180171640  jnz     loc_18017189F
0x180171646  test    r14d, r14d
0x180171649  jnz     loc_180171854
0x18017164f  mov     rcx, [rbp+TokenHandle]; hObject
0x180171653  lea     rax, [rcx-1]
0x180171657  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18017165b  jbe     loc_1801718A7
0x180171661  xor     eax, eax
0x180171663  mov     rcx, [rbp+var_10]
0x180171667  xor     rcx, rsp; StackCookie
0x18017166a  call    __security_check_cookie
0x18017166f  add     rsp, 68h
0x180171673  pop     r15
0x180171675  pop     r14
0x180171677  pop     r13
0x180171679  pop     r12
0x18017167b  pop     rdi
0x18017167c  pop     rsi
0x18017167d  pop     rbx
0x18017167e  pop     rbp
0x18017167f  retn
0x180171681  xor     esi, esi
0x180171683  jmp     short loc_180171625
0x180171685  mov     r12d, r14d
0x180171688  lea     rax, [rbp+var_20]
0x18017168c  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x180171691  mov     r9d, 4; TokenInformationLength
0x180171697  lea     r8, [rbp+var_28]; TokenInformation
0x18017169b  lea     edx, [r9+10h]; TokenInformationClass
0x18017169f  mov     rcx, rsi; TokenHandle
0x1801716a2  call    cs:__imp_NtQueryInformationToken
0x1801716a9  nop     dword ptr [rax+rax+00h]
0x1801716ae  mov     edi, eax
0x1801716b0  test    eax, eax
0x1801716b2  js      loc_1801715D0
0x1801716b8  cmp     dword ptr [rbp+var_28], r14d
0x1801716bc  jz      loc_1801715D0
0x1801716c2  xor     esi, esi
0x1801716c4  jmp     loc_18017162A
0x1801716c9  lea     rax, [rbp+TokenInformationLength]
0x1801716cd  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x1801716d2  xor     r9d, r9d; TokenInformationLength
0x1801716d5  xor     r8d, r8d; TokenInformation
0x1801716d8  lea     r12d, [r9+27h]
0x1801716dc  mov     edx, r12d; TokenInformationClass
0x1801716df  mov     rcx, rsi; TokenHandle
0x1801716e2  call    cs:__imp_NtQueryInformationToken
0x1801716e9  nop     dword ptr [rax+rax+00h]
0x1801716ee  mov     edi, eax
0x1801716f0  cmp     eax, 0C0000023h
0x1801716f5  jnz     loc_18017188F
0x1801716fb  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1801716fe  lea     ecx, [r12+19h]; uFlags
0x180171703  call    cs:__imp_LocalAlloc
0x18017170a  nop     dword ptr [rax+rax+00h]
0x18017170f  mov     r15, rax
0x180171712  test    rax, rax
0x180171715  jz      loc_18017186D
0x18017171b  lea     rax, [rbp+TokenInformationLength]
0x18017171f  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x180171724  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180171728  mov     r8, r15; TokenInformation
0x18017172b  mov     edx, r12d; TokenInformationClass
0x18017172e  mov     rcx, rsi; TokenHandle
0x180171731  call    cs:__imp_NtQueryInformationToken
0x180171738  nop     dword ptr [rax+rax+00h]
0x18017173d  mov     edi, eax
0x18017173f  xor     esi, esi
0x180171741  test    eax, eax
0x180171743  js      loc_18017187F
0x180171749  lea     r8d, [r12-26h]; CaseInsensitive
0x18017174e  mov     r12d, r8d
0x180171751  cmp     esi, [r15+4]
0x180171755  jb      short loc_18017179A
0x180171757  mov     eax, [rbp+var_30]
0x18017175a  xor     esi, esi
0x18017175c  test    r14d, r14d
0x18017175f  jz      loc_1801715FF
0x180171765  test    eax, eax
0x180171767  cmovz   esi, r8d
0x18017176b  jmp     loc_1801715FF
0x180171770  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180171775  mov     ebx, eax
0x180171777  mov     rcx, [rbp+TokenHandle]; hObject
0x18017177b  lea     rdx, [rcx-1]
0x18017177f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180171783  ja      loc_1801715FB
0x180171789  call    cs:__imp_CloseHandle
0x180171790  nop     dword ptr [rax+rax+00h]
0x180171795  jmp     loc_1801715FB
0x18017179a  lea     rcx, [rsi+rsi*4]
0x18017179e  mov     [rbp+var_28], rcx
0x1801717a2  mov     rax, [r15+8]
0x1801717a6  lea     rdx, [rax+rcx*8]; String2
0x1801717aa  lea     rcx, stru_180697428; String1
0x1801717b1  call    cs:__imp_RtlCompareUnicodeString
0x1801717b8  nop     dword ptr [rax+rax+00h]
0x1801717bd  test    eax, eax
0x1801717bf  jz      loc_18017185C
0x1801717c5  mov     rax, [r15+8]
0x1801717c9  mov     rcx, [rbp+var_28]
0x1801717cd  lea     rdx, [rax+rcx*8]; String2
0x1801717d1  mov     r8b, r12b; CaseInsensitive
0x1801717d4  lea     rcx, stru_180697438; String1
0x1801717db  call    cs:__imp_RtlCompareUnicodeString
0x1801717e2  nop     dword ptr [rax+rax+00h]
0x1801717e7  test    eax, eax
0x1801717e9  jz      short loc_18017185F
0x1801717eb  mov     rax, [r15+8]
0x1801717ef  mov     rcx, [rbp+var_28]
0x1801717f3  lea     rdx, [rax+rcx*8]; String2
0x1801717f7  mov     r8b, r12b; CaseInsensitive
0x1801717fa  lea     rcx, stru_180697448; String1
0x180171801  call    cs:__imp_RtlCompareUnicodeString
0x180171808  nop     dword ptr [rax+rax+00h]
0x18017180d  test    eax, eax
0x18017180f  jnz     short loc_180171822
0x180171811  mov     r13d, r12d
0x180171814  mov     r14d, r12d
0x180171817  mov     r8d, r12d
0x18017181a  add     esi, r12d
0x18017181d  jmp     loc_180171751
0x180171822  mov     rax, [r15+8]
0x180171826  mov     rcx, [rbp+var_28]
0x18017182a  lea     rdx, [rax+rcx*8]; String2
0x18017182e  mov     r8b, r12b; CaseInsensitive
0x180171831  lea     rcx, stru_180697470; String1
0x180171838  call    cs:__imp_RtlCompareUnicodeString
0x18017183f  nop     dword ptr [rax+rax+00h]
0x180171844  test    eax, eax
0x180171846  cmovz   r14d, r12d
0x18017184a  jmp     short loc_180171817
0x18017184c  or      dword ptr [rbx], 4
0x18017184f  jmp     loc_18017163E
0x180171854  or      dword ptr [rbx], 10h
0x180171857  jmp     loc_18017164F
0x18017185c  mov     r13d, r12d
0x18017185f  mov     r8d, r12d
0x180171862  mov     eax, r12d
0x180171865  mov     [rbp+var_30], eax
0x180171868  jmp     loc_18017175A
0x18017186d  mov     edi, 0C0000017h
0x180171872  jmp     loc_1801715D8
0x180171877  mov     r14d, r8d
0x18017187a  jmp     loc_18017160E
0x18017187f  mov     eax, 1
0x180171884  mov     r13d, eax
0x180171887  mov     r12d, eax
0x18017188a  jmp     loc_18017160E
0x18017188f  xor     esi, esi
0x180171891  lea     eax, [rsi+1]
0x180171894  mov     r13d, eax
0x180171897  mov     r12d, eax
0x18017189a  jmp     loc_180171621
0x18017189f  or      dword ptr [rbx], 8
0x1801718a2  jmp     loc_180171646
0x1801718a7  call    cs:__imp_CloseHandle
0x1801718ae  nop     dword ptr [rax+rax+00h]
0x1801718b3  jmp     loc_180171661
```
