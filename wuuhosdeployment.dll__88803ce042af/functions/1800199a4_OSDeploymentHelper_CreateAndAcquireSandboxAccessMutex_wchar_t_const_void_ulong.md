# OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(wchar_t const *,void * *,ulong)

- ea: `0x1800199a4`
- end: `0x180019c5b`
- name: `?CreateAndAcquireSandboxAccessMutex@OSDeploymentHelper@@YAJPEB_WPEAPEAXK@Z`
- size: `695`
- prototype: `__int64 __fastcall(wchar_t *this, const wchar_t *, void **, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001981c`
- `0x180019d44`
- `0x18002d114`

## callees

- `0x180003950`
- `0x180003974`
- `0x180005f64`
- `0x18000aecc`
- `0x18000c0b4`
- `0x18000e05c`
- `0x1800199a4`
- `0x18001a8f4`
- `0x18002fe70`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180019b7a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180019b7a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019b98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019bf1`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180019ab0`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180019ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(wchar_t *this, wchar_t *a2, void **a3)
{
  DWORD v3; // r13d
  unsigned int v6; // ebx
  __int64 v7; // rdx
  WCHAR *v8; // rdi
  void *v9; // rsi
  int CombinedPath; // r15d
  LPWSTR v11; // r14
  __int64 v12; // rdx
  wchar_t *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdi
  int v16; // eax
  HANDLE v17; // rax
  const char *v18; // r9
  HANDLE v19; // rbx
  __int64 v20; // rdx
  DWORD v21; // eax
  LPCWSTR lpName; // [rsp+20h] [rbp-40h] BYREF
  LPWSTR lpsz[2]; // [rsp+28h] [rbp-38h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v3 = (unsigned int)a3;
  if ( !this || !*this )
  {
    v6 = -2147024809;
    v7 = 257;
    goto LABEL_42;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    v7 = 258;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)v6,
      (int)lpName);
    return v6;
  }
  lpsz[0] = 0;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  v8 = 0;
  lpName = 0;
  v9 = 0;
  lpsz[1] = 0;
  CombinedPath = AllocAbsoluteSDFromString(0, lpsz);
  v11 = lpsz[0];
  if ( CombinedPath < 0 )
  {
    v12 = 266;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)(unsigned int)CombinedPath,
      (int)lpName);
    goto LABEL_34;
  }
  if ( !lpsz[0] )
  {
    CombinedPath = -2145120257;
    v12 = 267;
    goto LABEL_32;
  }
  MutexAttributes.nLength = 24;
  MutexAttributes.lpSecurityDescriptor = lpsz[0];
  MutexAttributes.bInheritHandle = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UAMutexSynchronization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UAMutexSynchronization>::GetImpl'::`2'::impl) )
  {
    lpsz[0] = 0;
    CombinedPath = DuplicateString<wchar_t const *,wchar_t *>(this, lpsz);
    v13 = lpsz[0];
    if ( CombinedPath < 0 )
    {
      v14 = 276;
      goto LABEL_18;
    }
    v15 = -1;
    do
      ++v15;
    while ( lpsz[0][v15] );
    if ( CharUpperBuffW(lpsz[0], v15) != (_DWORD)v15 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)lpName);
    CombinedPath = CreateCombinedPath(L"Global", v13, (wchar_t **)&lpName);
    if ( CombinedPath < 0 )
    {
      v14 = 281;
      v8 = (WCHAR *)lpName;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
        (const char *)(unsigned int)CombinedPath,
        (int)lpName);
      if ( v13 )
        CSusBaseAllocTag<942762101>::operator delete(v13);
      goto LABEL_34;
    }
    CombinedPath = 0;
    if ( v13 )
      CSusBaseAllocTag<942762101>::operator delete(v13);
  }
  else
  {
    v16 = CreateCombinedPath(L"Global", this, (wchar_t **)&lpName);
    CombinedPath = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
        (const char *)(unsigned int)v16,
        (int)lpName);
      v8 = (WCHAR *)lpName;
      goto LABEL_34;
    }
    CombinedPath = 0;
  }
  v8 = (WCHAR *)lpName;
  v17 = CreateMutexW(&MutexAttributes, 0, lpName);
  v19 = v17;
  v9 = v17;
  if ( v17 )
  {
    v21 = WaitForSingleObject(v17, v3);
    if ( v21 != -1 )
    {
      if ( v21 != 258 )
      {
        v9 = 0;
        *(_QWORD *)a2 = v19;
        goto LABEL_34;
      }
      CombinedPath = -2147024638;
      v12 = 294;
      goto LABEL_32;
    }
    v20 = 293;
  }
  else
  {
    v20 = 289;
  }
  CombinedPath = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)v20,
                   (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
                   v18);
LABEL_34:
  if ( v9 )
    CloseHandle(v9);
  if ( v8 )
    CSusBaseAllocTag<942762101>::operator delete(v8);
  if ( v11 )
    CSusBaseAllocTag<942762101>::operator delete(v11);
  return (unsigned int)CombinedPath;
}

```

## disassembly

```asm
0x1800199a4  mov     [rsp-38h+arg_18], rbx
0x1800199a9  push    rbp
0x1800199aa  push    rsi
0x1800199ab  push    rdi
0x1800199ac  push    r12
0x1800199ae  push    r13
0x1800199b0  push    r14
0x1800199b2  push    r15
0x1800199b4  mov     rbp, rsp
0x1800199b7  sub     rsp, 60h
0x1800199bb  mov     rax, cs:__security_cookie
0x1800199c2  xor     rax, rsp
0x1800199c5  mov     [rbp+var_10], rax
0x1800199c9  mov     r13d, r8d
0x1800199cc  mov     r12, rdx
0x1800199cf  mov     rbx, rcx
0x1800199d2  xor     ecx, ecx
0x1800199d4  test    rbx, rbx
0x1800199d7  jz      loc_180019C18
0x1800199dd  cmp     [rbx], cx
0x1800199e0  jz      loc_180019C18
0x1800199e6  test    rdx, rdx
0x1800199e9  jnz     short loc_1800199FA
0x1800199eb  mov     ebx, 80004003h
0x1800199f0  mov     edx, 102h
0x1800199f5  jmp     loc_180019C22
0x1800199fa  mov     [rbp+lpsz], rcx
0x1800199fe  xorps   xmm0, xmm0
0x180019a01  xor     eax, eax
0x180019a03  movups  xmmword ptr [rbp+MutexAttributes.nLength], xmm0
0x180019a07  mov     qword ptr [rbp+MutexAttributes.bInheritHandle], rax
0x180019a0b  mov     rdi, rcx
0x180019a0e  mov     [rbp+lpName], rcx
0x180019a12  mov     rsi, rcx
0x180019a15  mov     [rbp+var_30], rcx
0x180019a19  lea     rdx, [rbp+lpsz]
0x180019a1d  call    AllocAbsoluteSDFromString
0x180019a22  mov     r15d, eax
0x180019a25  mov     r14, [rbp+lpsz]
0x180019a29  test    eax, eax
0x180019a2b  jns     short loc_180019A37
0x180019a2d  mov     edx, 10Ah
0x180019a32  jmp     loc_180019BCD
0x180019a37  xor     r15d, r15d
0x180019a3a  test    r14, r14
0x180019a3d  jnz     short loc_180019A4F
0x180019a3f  mov     r15d, 80240FFFh
0x180019a45  mov     edx, 10Bh
0x180019a4a  jmp     loc_180019BCD
0x180019a4f  mov     [rbp+MutexAttributes.nLength], 18h
0x180019a56  mov     [rbp+MutexAttributes.lpSecurityDescriptor], r14
0x180019a5a  mov     [rbp+MutexAttributes.bInheritHandle], 1
0x180019a61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UAMutexSynchronization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UAMutexSynchronization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UAMutexSynchronization> `wil::Feature<__WilFeatureTraits_Feature_UAMutexSynchronization>::GetImpl(void)'::`2'::impl
0x180019a68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UAMutexSynchronization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UAMutexSynchronization>::__private_IsEnabled(void)
0x180019a6d  test    al, al
0x180019a6f  jz      loc_180019B32
0x180019a75  mov     [rbp+lpsz], r15
0x180019a79  lea     rdx, [rbp+lpsz]
0x180019a7d  mov     rcx, rbx
0x180019a80  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180019a85  mov     r15d, eax
0x180019a88  mov     rbx, [rbp+lpsz]
0x180019a8c  xor     eax, eax
0x180019a8e  test    r15d, r15d
0x180019a91  jns     short loc_180019A9A
0x180019a93  mov     edx, 114h
0x180019a98  jmp     short loc_180019AF7
0x180019a9a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180019a9e  inc     rdi
0x180019aa1  cmp     [rbx+rdi*2], ax
0x180019aa5  jnz     short loc_180019A9E
0x180019aa7  mov     r15, [rbp+38h]
0x180019aab  mov     edx, edi; cchLength
0x180019aad  mov     rcx, rbx; lpsz
0x180019ab0  call    cs:__imp_CharUpperBuffW
0x180019ab6  cmp     eax, edi
0x180019ab8  jz      short loc_180019AD4
0x180019aba  mov     r9d, 8000FFFFh; char *
0x180019ac0  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180019ac7  mov     edx, 116h; void *
0x180019acc  mov     rcx, r15; this
0x180019acf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019ad4  lea     r8, [rbp+lpName]; wchar_t **
0x180019ad8  mov     rdx, rbx; wchar_t *
0x180019adb  lea     rcx, aGlobal; "Global"
0x180019ae2  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x180019ae7  mov     r15d, eax
0x180019aea  test    eax, eax
0x180019aec  jns     short loc_180019B20
0x180019aee  mov     edx, 119h; void *
0x180019af3  mov     rdi, [rbp+lpName]
0x180019af7  mov     rcx, [rbp+38h]; this
0x180019afb  mov     r9d, r15d; char *
0x180019afe  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180019b05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b0a  test    rbx, rbx
0x180019b0d  jz      loc_180019BE9
0x180019b13  mov     rcx, rbx; lpMem
0x180019b16  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180019b1b  jmp     loc_180019BE9
0x180019b20  xor     r15d, r15d
0x180019b23  test    rbx, rbx
0x180019b26  jz      short loc_180019B6D
0x180019b28  mov     rcx, rbx; lpMem
0x180019b2b  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180019b30  jmp     short loc_180019B6D
0x180019b32  lea     r8, [rbp+lpName]; wchar_t **
0x180019b36  mov     rdx, rbx; wchar_t *
0x180019b39  lea     rcx, aGlobal; "Global"
0x180019b40  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x180019b45  mov     r15d, eax
0x180019b48  test    eax, eax
0x180019b4a  jns     short loc_180019B6A
0x180019b4c  mov     rcx, [rbp+38h]; this
0x180019b50  mov     r9d, eax; char *
0x180019b53  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180019b5a  mov     edx, 11Dh; void *
0x180019b5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b64  mov     rdi, [rbp+lpName]
0x180019b68  jmp     short loc_180019BE9
0x180019b6a  xor     r15d, r15d
0x180019b6d  mov     rdi, [rbp+lpName]
0x180019b71  mov     r8, rdi; lpName
0x180019b74  xor     edx, edx; bInitialOwner
0x180019b76  lea     rcx, [rbp+MutexAttributes]; lpMutexAttributes
0x180019b7a  call    cs:__imp_CreateMutexW
0x180019b80  mov     rbx, rax
0x180019b83  mov     rsi, rax
0x180019b86  test    rax, rax
0x180019b89  jnz     short loc_180019B92
0x180019b8b  mov     edx, 121h
0x180019b90  jmp     short loc_180019BA8
0x180019b92  mov     edx, r13d; dwMilliseconds
0x180019b95  mov     rcx, rbx; hHandle
0x180019b98  call    cs:__imp_WaitForSingleObject
0x180019b9e  cmp     eax, 0FFFFFFFFh
0x180019ba1  jnz     short loc_180019BBD
0x180019ba3  mov     edx, 125h; void *
0x180019ba8  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180019baf  mov     rcx, [rbp+38h]; this
0x180019bb3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019bb8  mov     r15d, eax
0x180019bbb  jmp     short loc_180019BE9
0x180019bbd  cmp     eax, 102h
0x180019bc2  jnz     short loc_180019BE2
0x180019bc4  mov     r15d, 80070102h
0x180019bca  lea     edx, [rax+24h]; void *
0x180019bcd  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180019bd4  mov     r9d, r15d; char *
0x180019bd7  mov     rcx, [rbp+38h]; this
0x180019bdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019be0  jmp     short loc_180019BE9
0x180019be2  mov     rsi, r15
0x180019be5  mov     [r12], rbx
0x180019be9  test    rsi, rsi
0x180019bec  jz      short loc_180019BF8
0x180019bee  mov     rcx, rsi; hObject
0x180019bf1  call    cs:__imp_CloseHandle
0x180019bf7  nop
0x180019bf8  test    rdi, rdi
0x180019bfb  jz      short loc_180019C06
0x180019bfd  mov     rcx, rdi; lpMem
0x180019c00  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180019c05  nop
0x180019c06  test    r14, r14
0x180019c09  jz      short loc_180019C13
0x180019c0b  mov     rcx, r14; lpMem
0x180019c0e  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180019c13  mov     eax, r15d
0x180019c16  jmp     short loc_180019C37
0x180019c18  mov     ebx, 80070057h
0x180019c1d  mov     edx, 101h; void *
0x180019c22  mov     r9d, ebx; char *
0x180019c25  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180019c2c  mov     rcx, [rbp+38h]; this
0x180019c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c35  mov     eax, ebx
0x180019c37  mov     rcx, [rbp+var_10]
0x180019c3b  xor     rcx, rsp; StackCookie
0x180019c3e  call    __security_check_cookie
0x180019c43  mov     rbx, [rsp+60h+arg_18]
0x180019c4b  add     rsp, 60h
0x180019c4f  pop     r15
0x180019c51  pop     r14
0x180019c53  pop     r13
0x180019c55  pop     r12
0x180019c57  pop     rdi
0x180019c58  pop     rsi
0x180019c59  pop     rbp
0x180019c5a  retn
```
