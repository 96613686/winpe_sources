# EnterpriseFeatureControl::IsFeatureEnabled(ulong)

- ea: `0x1800359e4`
- end: `0x180035c77`
- name: `?IsFeatureEnabled@EnterpriseFeatureControl@@SA_NK@Z`
- size: `659`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e7a0`

## callees

- `0x180007660`
- `0x1800183d4`
- `0x1800183f4`
- `0x1800239c4`
- `0x180031980`
- `0x180031a9c`
- `0x1800325c8`
- `0x180032834`
- `0x1800359e4`
- `0x180036ac8`
- `0x180036dd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035bbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035c0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035bbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035c0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035baf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035baf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035c34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035a8a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035a8a`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x180035be1`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x180035be1`

## string_xrefs

- `0x180035a67`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180035af7`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180035a43`: `ActiveConfig`
- `0x180035a51`: `SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls\Active`

## pseudocode

```c
char __fastcall EnterpriseFeatureControl::IsFeatureEnabled(unsigned int a1)
{
  unsigned int v1; // ecx
  int DwordFromRegistry; // eax
  int IsValidFeatureID; // ebx
  __int64 v4; // rdx
  char v5; // si
  __int64 v6; // rcx
  char v7; // al
  int PolicyState; // eax
  unsigned int v9; // ebx
  int SkuUpdateManagementGroup; // eax
  int ProcessEnvName; // eax
  int LastError; // edi
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  void *v15; // rbx
  const WCHAR *v16; // rdx
  const char *v17; // r9
  HANDLE v18; // rax
  HANDLE v19; // rax
  int v21; // [rsp+20h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  LOWORD(v21) = 256;
  if ( (int)EnterpriseFeatureControl::GetFeatureStatusCache(a1, (bool *)&v21, (bool *)&v21 + 1) >= 0 && (_BYTE)v21 )
    return BYTE1(v21);
  if ( _InterlockedCompareExchange(&dword_180095C50, 1, 0) == 1 )
  {
    while ( _InterlockedCompareExchange(&dword_180095C50, 1, 0) == 1 )
      Sleep(0x64u);
    if ( dword_180095C50 == 1 )
      _InterlockedExchange(&dword_180095C50, 0);
    if ( (int)EnterpriseFeatureControl::GetFeatureStatusCache(v1, (bool *)&v21, (bool *)&v21 + 1) >= 0 && (_BYTE)v21 )
      return BYTE1(v21);
  }
  LOBYTE(v21) = 0;
  LODWORD(lpMem) = 0;
  DwordFromRegistry = ETCpGetDwordFromRegistry(
                        L"SYSTEM\\CurrentControlSet\\Control\\FeatureManagement\\EnterpriseTempControls\\Active",
                        L"ActiveConfig",
                        (BYTE *)&lpMem);
  IsValidFeatureID = DwordFromRegistry;
  if ( DwordFromRegistry >= 0 )
  {
    IsValidFeatureID = ETCpIsValidFeatureID(0xF6F9948D, (unsigned int)lpMem, (bool *)&v21);
    if ( IsValidFeatureID >= 0 )
    {
      v7 = v21;
      goto LABEL_17;
    }
    v4 = 161;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
      (const char *)(unsigned int)DwordFromRegistry,
      v21);
    v4 = 158;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
    (const char *)(unsigned int)IsValidFeatureID,
    v21);
  v7 = 0;
LABEL_17:
  if ( v7 )
  {
    PolicyState = EnterpriseFeatureControl::ReadPolicyState((bool *)&v21 + 1);
    v9 = PolicyState;
    if ( PolicyState < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)(unsigned int)PolicyState,
        v21);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)v9,
        v21);
      SkuUpdateManagementGroup = EnterpriseFeatureControl::ReadSkuUpdateManagementGroup((bool *)&v21 + 1);
      if ( SkuUpdateManagementGroup < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
          (const char *)(unsigned int)SkuUpdateManagementGroup,
          v21);
    }
  }
  lpMem = 0;
  ProcessEnvName = EnterpriseFeatureControl::GetProcessEnvName(v6, &lpMem);
  v5 = BYTE1(v21);
  LastError = ProcessEnvName;
  if ( ProcessEnvName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)(unsigned int)ProcessEnvName,
      v21);
    v13 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
    }
LABEL_30:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)(unsigned int)LastError,
      v21);
    goto LABEL_33;
  }
  v15 = lpMem;
  v16 = L"1";
  if ( !BYTE1(v21) )
    v16 = L"0";
  if ( SetEnvironmentVariableW((LPCWSTR)lpMem, v16) )
  {
    if ( v15 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v15);
    }
    goto LABEL_33;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x31,
                (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                v17);
  if ( v15 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v15);
  }
  if ( LastError < 0 )
    goto LABEL_30;
LABEL_33:
  if ( dword_180095C50 == 1 )
    _InterlockedExchange(&dword_180095C50, 0);
  return v5;
}

```

## disassembly

```asm
0x1800359e4  push    rbp
0x1800359e6  push    rbx
0x1800359e7  push    rsi
0x1800359e8  push    rdi
0x1800359e9  push    r12
0x1800359eb  push    r15
0x1800359ed  mov     rbp, rsp
0x1800359f0  sub     rsp, 48h
0x1800359f4  mov     rax, cs:__security_cookie
0x1800359fb  xor     rax, rsp
0x1800359fe  mov     [rbp+var_18], rax
0x180035a02  mov     r15d, 1
0x180035a08  mov     [rbp+var_28], 0
0x180035a0c  lea     r8, [rbp+var_27]; bool *
0x180035a10  mov     [rbp+var_27], r15b
0x180035a14  lea     rdx, [rbp+var_28]; bool *
0x180035a18  call    ?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z; EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)
0x180035a1d  test    eax, eax
0x180035a1f  js      short loc_180035A2B
0x180035a21  cmp     [rbp+var_28], 0
0x180035a25  jnz     loc_180035AD2
0x180035a2b  xor     eax, eax
0x180035a2d  lock cmpxchg cs:dword_180095C50, r15d
0x180035a36  cmp     eax, r15d
0x180035a39  jz      short loc_180035A90
0x180035a3b  lea     r8, [rbp+lpMem]; unsigned int *
0x180035a3f  mov     [rbp+var_28], 0
0x180035a43  lea     rdx, aActiveconfig; "ActiveConfig"
0x180035a4a  mov     dword ptr [rbp+lpMem], 0
0x180035a51  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x180035a58  call    ?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z; ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x180035a5d  mov     ebx, eax
0x180035a5f  test    eax, eax
0x180035a61  jns     short loc_180035ADB
0x180035a63  mov     rcx, [rbp+30h]; this
0x180035a67  lea     rdi, aOnecoreInterna_7; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180035a6e  mov     r8, rdi; unsigned int
0x180035a71  mov     r9d, eax; char *
0x180035a74  mov     edx, 72h ; 'r'; void *
0x180035a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a7e  mov     edx, 9Eh
0x180035a83  jmp     short loc_180035AFE
0x180035a85  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180035a8a  call    cs:__imp_Sleep
0x180035a90  xor     eax, eax
0x180035a92  lock cmpxchg cs:dword_180095C50, r15d
0x180035a9b  cmp     eax, r15d
0x180035a9e  jz      short loc_180035A85
0x180035aa0  mov     eax, cs:dword_180095C50
0x180035aa6  cmp     eax, r15d
0x180035aa9  jnz     short loc_180035AB3
0x180035aab  xor     eax, eax
0x180035aad  xchg    eax, cs:dword_180095C50
0x180035ab3  lea     r8, [rbp+var_27]; bool *
0x180035ab7  lea     rdx, [rbp+var_28]; bool *
0x180035abb  call    ?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z; EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)
0x180035ac0  test    eax, eax
0x180035ac2  js      loc_180035A3B
0x180035ac8  cmp     [rbp+var_28], 0
0x180035acc  jz      loc_180035A3B
0x180035ad2  mov     sil, [rbp+var_27]
0x180035ad6  jmp     loc_180035C5B
0x180035adb  mov     edx, dword ptr [rbp+lpMem]; unsigned int
0x180035ade  lea     r8, [rbp+var_28]; bool *
0x180035ae2  mov     ecx, 0F6F9948Dh; unsigned int
0x180035ae7  call    ?ETCpIsValidFeatureID@@YAJKKPEA_N@Z; ETCpIsValidFeatureID(ulong,ulong,bool *)
0x180035aec  mov     ebx, eax
0x180035aee  test    eax, eax
0x180035af0  jns     short loc_180035B11
0x180035af2  mov     edx, 0A1h; void *
0x180035af7  lea     rdi, aOnecoreInterna_7; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180035afe  mov     rcx, [rbp+30h]; this
0x180035b02  mov     r9d, ebx; char *
0x180035b05  mov     r8, rdi; unsigned int
0x180035b08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b0d  xor     al, al
0x180035b0f  jmp     short loc_180035B14
0x180035b11  mov     al, [rbp+var_28]
0x180035b14  lea     r12, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180035b1b  test    al, al
0x180035b1d  jz      short loc_180035B77
0x180035b1f  lea     rcx, [rbp+var_27]; bool *
0x180035b23  call    ?ReadPolicyState@EnterpriseFeatureControl@@CAJPEA_N@Z; EnterpriseFeatureControl::ReadPolicyState(bool *)
0x180035b28  mov     ebx, eax
0x180035b2a  test    eax, eax
0x180035b2c  jns     short loc_180035B77
0x180035b2e  mov     rcx, [rbp+30h]; this
0x180035b32  mov     r9d, eax; char *
0x180035b35  mov     r8, r12; unsigned int
0x180035b38  mov     edx, 0EFh; void *
0x180035b3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b42  mov     rcx, [rbp+30h]; this
0x180035b46  mov     r9d, ebx; char *
0x180035b49  mov     r8, r12; unsigned int
0x180035b4c  mov     edx, 0F3h; void *
0x180035b51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b56  lea     rcx, [rbp+var_27]; bool *
0x180035b5a  call    ?ReadSkuUpdateManagementGroup@EnterpriseFeatureControl@@CAJPEA_N@Z; EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *)
0x180035b5f  test    eax, eax
0x180035b61  jns     short loc_180035B77
0x180035b63  mov     rcx, [rbp+30h]; this
0x180035b67  mov     r9d, eax; char *
0x180035b6a  mov     r8, r12; unsigned int
0x180035b6d  mov     edx, 0F6h; void *
0x180035b72  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b77  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x180035b7b  mov     [rbp+lpMem], 0
0x180035b83  call    ?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z; EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)
0x180035b88  mov     sil, [rbp+var_27]
0x180035b8c  mov     edi, eax
0x180035b8e  test    eax, eax
0x180035b90  jns     short loc_180035BC5
0x180035b92  mov     rcx, [rbp+30h]; this
0x180035b96  mov     r9d, eax; char *
0x180035b99  mov     r8, r12; unsigned int
0x180035b9c  mov     edx, 2Fh ; '/'; void *
0x180035ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ba6  mov     rbx, [rbp+lpMem]
0x180035baa  test    rbx, rbx
0x180035bad  jz      short loc_180035C19
0x180035baf  call    cs:__imp_GetProcessHeap
0x180035bb5  mov     r8, rbx; lpMem
0x180035bb8  xor     edx, edx; dwFlags
0x180035bba  mov     rcx, rax; hHeap
0x180035bbd  call    cs:__imp_HeapFree
0x180035bc3  jmp     short loc_180035C19
0x180035bc5  mov     rbx, [rbp+lpMem]
0x180035bc9  lea     rax, Value; "0"
0x180035bd0  test    sil, sil
0x180035bd3  lea     rdx, String2; "1"
0x180035bda  mov     rcx, rbx; lpName
0x180035bdd  cmovz   rdx, rax; lpValue
0x180035be1  call    cs:__imp_SetEnvironmentVariableW
0x180035be7  test    eax, eax
0x180035be9  jnz     short loc_180035C2F
0x180035beb  mov     rcx, [rbp+30h]; this
0x180035bef  lea     edx, [rax+31h]; void *
0x180035bf2  mov     r8, r12; unsigned int
0x180035bf5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035bfa  mov     edi, eax
0x180035bfc  test    rbx, rbx
0x180035bff  jz      short loc_180035C15
0x180035c01  call    cs:__imp_GetProcessHeap
0x180035c07  mov     r8, rbx; lpMem
0x180035c0a  xor     edx, edx; dwFlags
0x180035c0c  mov     rcx, rax; hHeap
0x180035c0f  call    cs:__imp_HeapFree
0x180035c15  test    edi, edi
0x180035c17  jns     short loc_180035C48
0x180035c19  mov     rcx, [rbp+30h]; this
0x180035c1d  mov     r9d, edi; char *
0x180035c20  mov     r8, r12; unsigned int
0x180035c23  mov     edx, 0F9h; void *
0x180035c28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035c2d  jmp     short loc_180035C48
0x180035c2f  test    rbx, rbx
0x180035c32  jz      short loc_180035C48
0x180035c34  call    cs:__imp_GetProcessHeap
0x180035c3a  mov     r8, rbx; lpMem
0x180035c3d  xor     edx, edx; dwFlags
0x180035c3f  mov     rcx, rax; hHeap
0x180035c42  call    cs:__imp_HeapFree
0x180035c48  mov     ecx, cs:dword_180095C50
0x180035c4e  cmp     ecx, r15d
0x180035c51  jnz     short loc_180035C5B
0x180035c53  xor     ecx, ecx
0x180035c55  xchg    ecx, cs:dword_180095C50
0x180035c5b  mov     al, sil
0x180035c5e  mov     rcx, [rbp+var_18]
0x180035c62  xor     rcx, rsp; StackCookie
0x180035c65  call    __security_check_cookie
0x180035c6a  add     rsp, 48h
0x180035c6e  pop     r15
0x180035c70  pop     r12
0x180035c72  pop     rdi
0x180035c73  pop     rsi
0x180035c74  pop     rbx
0x180035c75  pop     rbp
0x180035c76  retn
```
