# CSyncClientCore::FinalConstruct(ushort const *)

- ea: `0x1800bfb64`
- end: `0x1800c0036`
- name: `?FinalConstruct@CSyncClientCore@@IEAAJPEBG@Z`
- size: `1234`
- prototype: `int(CSyncClientCore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800be6f4`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180007b9c`
- `0x180007e10`
- `0x180007f1c`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180021508`
- `0x180061674`
- `0x1800aac64`
- `0x1800bfb64`
- `0x1800c1154`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800bfc9e`
- `KERNEL32!GetCurrentProcess` at `0x1800bfc9e`
- `KERNEL32!GetCurrentThread` at `0x1800bfc20`
- `KERNEL32!GetCurrentThread` at `0x1800bfc45`
- `KERNEL32!GetCurrentThread` at `0x1800bfc20`
- `KERNEL32!GetCurrentThread` at `0x1800bfc45`
- `KERNEL32!GetLastError` at `0x1800bfc7b`
- `KERNEL32!GetLastError` at `0x1800bfc7b`
- `ADVAPI32!OpenThreadToken` at `0x1800bfc37`
- `ADVAPI32!OpenThreadToken` at `0x1800bfc59`
- `ADVAPI32!OpenThreadToken` at `0x1800bfc37`
- `ADVAPI32!OpenThreadToken` at `0x1800bfc59`
- `ADVAPI32!OpenProcessToken` at `0x1800bfcae`
- `ADVAPI32!OpenProcessToken` at `0x1800bfcae`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800bfe32`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800bfe32`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800bfd36`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800bfd36`
- `USERENV!GetUserProfileDirectoryW` at `0x1800bfcf9`
- `USERENV!GetUserProfileDirectoryW` at `0x1800bfcf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncClientCore::FinalConstruct(CSyncClientCore *this, const unsigned __int16 *a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  HANDLE CurrentThread; // rax
  HANDLE v7; // rax
  HANDLE CurrentProcess; // rax
  HRESULT LastFailureAsHRESULT; // ebx
  __int16 v10; // ax
  unsigned __int16 *v11; // rsi
  bool v12; // sf
  struct CFileSyncMetadataStore **v13; // rbx
  int Instance; // r14d
  int v15; // edi
  int v16; // eax
  __int64 v17; // rdx
  int v18; // ecx
  __int64 v19; // rdx
  int v20; // ecx
  __int64 *v21; // rdx
  __int64 v22; // rdx
  int v23; // ecx
  __int64 v25; // rdx
  int *dwFlags; // [rsp+20h] [rbp-E0h]
  int *dwFlagsa; // [rsp+20h] [rbp-E0h]
  DWORD cchSize; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+3Ch] [rbp-C4h]
  char v31; // [rsp+40h] [rbp-C0h]
  const char *v32; // [rsp+48h] [rbp-B8h]
  __int64 v33; // [rsp+50h] [rbp-B0h]
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v35; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v36[2046]; // [rsp+62h] [rbp-9Eh] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 0x20) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  v29 = 0;
  v30 = 90;
  v31 = v5;
  v32 = "CSyncClientCore::FinalConstruct";
  v33 = 0;
  TokenHandle = 0;
  if ( a2 )
  {
    v11 = (unsigned __int16 *)((char *)this + 32);
    *((_WORD *)this + 16) = 0;
    LastFailureAsHRESULT = PathCchCombineEx(
                             (PWSTR)this + 16,
                             0x104u,
                             a2,
                             L"AppData\\Local\\Microsoft\\Windows\\WorkFolders\\Metadata",
                             1u);
    v29 = LastFailureAsHRESULT;
    v12 = LastFailureAsHRESULT < 0;
    v10 = 120;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      v7 = GetCurrentThread();
      if ( !OpenThreadToken(v7, 8u, 1, &TokenHandle) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids);
        }
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        {
          LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
          v10 = 109;
LABEL_18:
          HIWORD(v30) = v10;
          goto LABEL_53;
        }
        v29 = 0;
        LOWORD(v30) = 109;
      }
    }
    cchSize = 260;
    v11 = (unsigned __int16 *)((char *)this + 32);
    if ( !GetUserProfileDirectoryW(TokenHandle, (LPWSTR)this + 16, &cchSize) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v10 = 114;
      goto LABEL_18;
    }
    v29 = 0;
    LOWORD(v30) = 114;
    LastFailureAsHRESULT = PathCchAppendEx(
                             (PWSTR)this + 16,
                             0x104u,
                             L"AppData\\Local\\Microsoft\\Windows\\WorkFolders\\Metadata",
                             1u);
    v29 = LastFailureAsHRESULT;
    v12 = LastFailureAsHRESULT < 0;
    v10 = 115;
  }
  if ( v12 )
    goto LABEL_18;
  LOWORD(v30) = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids, v11);
  }
  v13 = (struct CFileSyncMetadataStore **)((char *)this + 552);
  Instance = CFileSyncMetadataStore::CreateInstance(v11, 3u, 0, (struct CFileSyncMetadataStore **)this + 69, dwFlags);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids);
    }
    if ( Instance == -2147024894 )
    {
      v15 = CFileSyncMetadataStore::CreateInstance(v11, 2u, 0, (struct CFileSyncMetadataStore **)this + 69, dwFlagsa);
      goto LABEL_35;
    }
    if ( Instance != -2147216759 )
    {
      v15 = Instance;
      if ( Instance != -2147216749 )
        goto LABEL_35;
    }
    v16 = CFileSyncMetadataStore::CreateInstance(v11, 2u, 0, v13, dwFlagsa);
    v15 = v16;
    LastFailureAsHRESULT = v16;
    if ( Instance == -2147216759 )
    {
      if ( v16 >= 0 )
      {
        if ( (Microsoft_Windows_WorkFoldersEnableBits & 2) != 0 )
        {
          v35 = 0;
          memset_0(v36, 0, sizeof(v36));
          CEcsFunctionTracer::GetErrorText(LastFailureAsHRESULT, v17, &v35);
          McTemplateU0zzd_EventWriteTransfer(
            v18,
            (unsigned int)ECSHOST_EVENT_CORESYNC_DATABASE_CORRUPTION,
            (_DWORD)v11,
            (unsigned int)&v35,
            LastFailureAsHRESULT);
          v29 = LastFailureAsHRESULT;
LABEL_50:
          LOWORD(v30) = 175;
          goto LABEL_51;
        }
LABEL_35:
        LastFailureAsHRESULT = v15;
        v29 = v15;
        if ( v15 < 0 )
          goto LABEL_59;
        goto LABEL_50;
      }
      if ( (Microsoft_Windows_WorkFoldersEnableBits & 2) == 0 )
        goto LABEL_35;
      v35 = 0;
      memset_0(v36, 0, sizeof(v36));
      CEcsFunctionTracer::GetErrorText(v15, v19, &v35);
      v21 = ECSHOST_EVENT_CORESYNC_DATABASE_CORRUPTION_RECOVERY_FAILED;
    }
    else
    {
      if ( v16 >= 0 )
      {
        if ( (Microsoft_Windows_WorkFoldersEnableBits & 2) != 0 )
        {
          v35 = 0;
          memset_0(v36, 0, sizeof(v36));
          CEcsFunctionTracer::GetErrorText(v15, v22, &v35);
          McTemplateU0zzd_EventWriteTransfer(
            v23,
            (unsigned int)ECSHOST_EVENT_CORESYNC_DATABASE_VERSION_INCOMPATIBLE,
            (_DWORD)v11,
            (unsigned int)&v35,
            v15);
        }
        v29 = LastFailureAsHRESULT;
        goto LABEL_50;
      }
      if ( (Microsoft_Windows_WorkFoldersEnableBits & 2) == 0 )
      {
LABEL_59:
        v10 = 175;
        goto LABEL_18;
      }
      v35 = 0;
      memset_0(v36, 0, sizeof(v36));
      CEcsFunctionTracer::GetErrorText(v15, v25, &v35);
      v21 = ECSHOST_EVENT_CORESYNC_DATABASE_VERSION_INCOMPATIBLE_RECOVERY_FAILED;
    }
    McTemplateU0zzd_EventWriteTransfer(v20, (_DWORD)v21, (_DWORD)v11, (unsigned int)&v35, v15);
    goto LABEL_59;
  }
LABEL_51:
  LastFailureAsHRESULT = s_GrantWorkFoldersSvcAccessToMetadataDirectory(v11);
  v10 = 178;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_18;
  LOWORD(v30) = 178;
LABEL_53:
  if ( (LastFailureAsHRESULT & 0x1FFF0000) == 0xE5E0000 )
    LastFailureAsHRESULT = -2134375657;
  v29 = LastFailureAsHRESULT;
  CAutoHandle<void *>::~CAutoHandle<void *>(&TokenHandle);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v29);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800bfb64  mov     [rsp-8+arg_10], rbx
0x1800bfb69  mov     [rsp-8+arg_18], rsi
0x1800bfb6e  push    rbp
0x1800bfb6f  push    rdi
0x1800bfb70  push    r14
0x1800bfb72  lea     rbp, [rsp-770h]
0x1800bfb7a  sub     rsp, 870h
0x1800bfb81  mov     rax, cs:__security_cookie
0x1800bfb88  xor     rax, rsp
0x1800bfb8b  mov     [rbp+780h+var_20], rax
0x1800bfb92  mov     rbx, rdx
0x1800bfb95  mov     rdi, rcx
0x1800bfb98  lea     r14, WPP_GLOBAL_Control
0x1800bfb9f  mov     rax, cs:WPP_GLOBAL_Control
0x1800bfba6  cmp     rax, r14
0x1800bfba9  jz      short loc_1800BFBD3
0x1800bfbab  test    byte ptr [rax+44h], 20h
0x1800bfbaf  jz      short loc_1800BFBE3
0x1800bfbb1  cmp     byte ptr [rax+41h], 6
0x1800bfbb5  jb      short loc_1800BFBD3
0x1800bfbb7  mov     edx, 0Bh
0x1800bfbbc  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bfbc3  mov     rcx, [rax+38h]
0x1800bfbc7  call    WPP_SF_
0x1800bfbcc  mov     rax, cs:WPP_GLOBAL_Control
0x1800bfbd3  test    byte ptr [rax+44h], 20h
0x1800bfbd7  jz      short loc_1800BFBE3
0x1800bfbd9  cmp     byte ptr [rax+41h], 6
0x1800bfbdd  jb      short loc_1800BFBE3
0x1800bfbdf  mov     cl, 1
0x1800bfbe1  jmp     short loc_1800BFBE5
0x1800bfbe3  xor     cl, cl
0x1800bfbe5  mov     [rsp+880h+var_848], 0
0x1800bfbed  mov     [rsp+880h+var_844], 5Ah ; 'Z'
0x1800bfbf5  mov     [rsp+880h+var_840], cl
0x1800bfbf9  lea     rax, aCsyncclientcor_13; "CSyncClientCore::FinalConstruct"
0x1800bfc00  mov     [rsp+880h+var_838], rax
0x1800bfc05  mov     [rsp+880h+var_830], 0
0x1800bfc0e  mov     [rsp+880h+TokenHandle], 0
0x1800bfc17  test    rbx, rbx
0x1800bfc1a  jnz     loc_1800BFE0F
0x1800bfc20  call    cs:__imp_GetCurrentThread
0x1800bfc26  lea     r9, [rsp+880h+TokenHandle]; TokenHandle
0x1800bfc2b  xor     r8d, r8d; OpenAsSelf
0x1800bfc2e  lea     ebx, [r8+8]
0x1800bfc32  mov     edx, ebx; DesiredAccess
0x1800bfc34  mov     rcx, rax; ThreadHandle
0x1800bfc37  call    cs:__imp_OpenThreadToken
0x1800bfc3d  test    eax, eax
0x1800bfc3f  jnz     loc_1800BFCE0
0x1800bfc45  call    cs:__imp_GetCurrentThread
0x1800bfc4b  lea     r9, [rsp+880h+TokenHandle]; TokenHandle
0x1800bfc50  lea     r8d, [rbx-7]; OpenAsSelf
0x1800bfc54  mov     edx, ebx; DesiredAccess
0x1800bfc56  mov     rcx, rax; ThreadHandle
0x1800bfc59  call    cs:__imp_OpenThreadToken
0x1800bfc5f  test    eax, eax
0x1800bfc61  jnz     short loc_1800BFCE0
0x1800bfc63  mov     rax, cs:WPP_GLOBAL_Control
0x1800bfc6a  cmp     rax, r14
0x1800bfc6d  jz      short loc_1800BFC9E
0x1800bfc6f  test    byte ptr [rax+44h], 20h
0x1800bfc73  jz      short loc_1800BFC9E
0x1800bfc75  cmp     byte ptr [rax+41h], 4
0x1800bfc79  jb      short loc_1800BFC9E
0x1800bfc7b  call    cs:__imp_GetLastError
0x1800bfc81  lea     edx, [rbx+4]
0x1800bfc84  mov     r9d, eax
0x1800bfc87  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bfc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfc95  mov     rcx, [rcx+38h]
0x1800bfc99  call    WPP_SF_d
0x1800bfc9e  call    cs:__imp_GetCurrentProcess
0x1800bfca4  lea     r8, [rsp+880h+TokenHandle]; TokenHandle
0x1800bfca9  mov     edx, ebx; DesiredAccess
0x1800bfcab  mov     rcx, rax; ProcessHandle
0x1800bfcae  call    cs:__imp_OpenProcessToken
0x1800bfcb4  test    eax, eax
0x1800bfcb6  jnz     short loc_1800BFCCE
0x1800bfcb8  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800bfcbd  mov     ebx, eax
0x1800bfcbf  mov     eax, 6Dh ; 'm'
0x1800bfcc4  mov     word ptr [rsp+880h+var_844+2], ax
0x1800bfcc9  jmp     loc_1800BFF8F
0x1800bfcce  mov     [rsp+880h+var_848], 0
0x1800bfcd6  mov     eax, 6Dh ; 'm'
0x1800bfcdb  mov     word ptr [rsp+880h+var_844], ax
0x1800bfce0  mov     [rsp+880h+cchSize], 104h
0x1800bfce8  lea     rsi, [rdi+20h]
0x1800bfcec  lea     r8, [rsp+880h+cchSize]; lpcchSize
0x1800bfcf1  mov     rdx, rsi; lpProfileDir
0x1800bfcf4  mov     rcx, [rsp+880h+TokenHandle]; hToken
0x1800bfcf9  call    cs:__imp_GetUserProfileDirectoryW
0x1800bfcff  test    eax, eax
0x1800bfd01  jnz     short loc_1800BFD11
0x1800bfd03  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800bfd08  mov     ebx, eax
0x1800bfd0a  mov     eax, 72h ; 'r'
0x1800bfd0f  jmp     short loc_1800BFCC4
0x1800bfd11  mov     [rsp+880h+var_848], 0
0x1800bfd19  mov     eax, 72h ; 'r'
0x1800bfd1e  mov     word ptr [rsp+880h+var_844], ax
0x1800bfd23  lea     r9d, [rax-71h]; dwFlags
0x1800bfd27  lea     r8, pszMore; "AppData\\Local\\Microsoft\\Windows\\Wor"...
0x1800bfd2e  mov     edx, 104h; cchPath
0x1800bfd33  mov     rcx, rsi; pszPath
0x1800bfd36  call    cs:__imp_PathCchAppendEx
0x1800bfd3c  mov     ebx, eax
0x1800bfd3e  mov     [rsp+880h+var_848], eax
0x1800bfd42  test    eax, eax
0x1800bfd44  mov     eax, 73h ; 's'
0x1800bfd49  js      loc_1800BFCC4
0x1800bfd4f  mov     word ptr [rsp+880h+var_844], ax
0x1800bfd54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfd5b  cmp     rcx, r14
0x1800bfd5e  jz      short loc_1800BFD84
0x1800bfd60  test    byte ptr [rcx+44h], 20h
0x1800bfd64  jz      short loc_1800BFD84
0x1800bfd66  cmp     byte ptr [rcx+41h], 4
0x1800bfd6a  jb      short loc_1800BFD84
0x1800bfd6c  mov     edx, 0Dh
0x1800bfd71  mov     r9, rsi
0x1800bfd74  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bfd7b  mov     rcx, [rcx+38h]
0x1800bfd7f  call    WPP_SF_S
0x1800bfd84  lea     rbx, [rdi+228h]
0x1800bfd8b  mov     r9, rbx; struct CFileSyncMetadataStore **
0x1800bfd8e  xor     r8d, r8d; int
0x1800bfd91  lea     edx, [r8+3]; unsigned int
0x1800bfd95  mov     rcx, rsi; unsigned __int16 *
0x1800bfd98  call    ?CreateInstance@CFileSyncMetadataStore@@SAJPEBGKHPEAPEAV1@PEAH@Z; CFileSyncMetadataStore::CreateInstance(ushort const *,ulong,int,CFileSyncMetadataStore * *,int *)
0x1800bfd9d  mov     r14d, eax
0x1800bfda0  test    eax, eax
0x1800bfda2  jns     loc_1800BFF73
0x1800bfda8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfdaf  lea     rax, WPP_GLOBAL_Control
0x1800bfdb6  cmp     rcx, rax
0x1800bfdb9  jz      short loc_1800BFDDF
0x1800bfdbb  test    byte ptr [rcx+44h], 20h
0x1800bfdbf  jz      short loc_1800BFDDF
0x1800bfdc1  cmp     byte ptr [rcx+41h], 4
0x1800bfdc5  jb      short loc_1800BFDDF
0x1800bfdc7  mov     edx, 0Eh
0x1800bfdcc  mov     r9d, r14d
0x1800bfdcf  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800bfdd6  mov     rcx, [rcx+38h]
0x1800bfdda  call    WPP_SF_d
0x1800bfddf  cmp     r14d, 80070002h
0x1800bfde6  jnz     short loc_1800BFE4A
0x1800bfde8  mov     r9, rbx; struct CFileSyncMetadataStore **
0x1800bfdeb  xor     r8d, r8d; int
0x1800bfdee  lea     edx, [r8+2]; unsigned int
0x1800bfdf2  mov     rcx, rsi; unsigned __int16 *
0x1800bfdf5  call    ?CreateInstance@CFileSyncMetadataStore@@SAJPEBGKHPEAPEAV1@PEAH@Z; CFileSyncMetadataStore::CreateInstance(ushort const *,ulong,int,CFileSyncMetadataStore * *,int *)
0x1800bfdfa  mov     edi, eax
0x1800bfdfc  mov     ebx, edi
0x1800bfdfe  mov     [rsp+880h+var_848], ebx
0x1800bfe02  test    edi, edi
0x1800bfe04  jns     loc_1800BFF69
0x1800bfe0a  jmp     loc_1800C002C
0x1800bfe0f  lea     rsi, [rdi+20h]
0x1800bfe13  xor     eax, eax
0x1800bfe15  mov     [rsi], ax
0x1800bfe18  mov     [rsp+880h+dwFlags], 1; dwFlags
0x1800bfe20  lea     r9, pszMore; "AppData\\Local\\Microsoft\\Windows\\Wor"...
0x1800bfe27  mov     r8, rbx; pszPathIn
0x1800bfe2a  mov     edx, 104h; cchPathOut
0x1800bfe2f  mov     rcx, rsi; pszPathOut
0x1800bfe32  call    cs:__imp_PathCchCombineEx
0x1800bfe38  mov     ebx, eax
0x1800bfe3a  mov     [rsp+880h+var_848], eax
0x1800bfe3e  test    eax, eax
0x1800bfe40  mov     eax, 78h ; 'x'
0x1800bfe45  jmp     loc_1800BFD49
0x1800bfe4a  cmp     r14d, 80041289h
0x1800bfe51  jz      short loc_1800BFE5F
0x1800bfe53  mov     edi, r14d
0x1800bfe56  cmp     r14d, 80041293h
0x1800bfe5d  jnz     short loc_1800BFDFC
0x1800bfe5f  mov     r9, rbx; struct CFileSyncMetadataStore **
0x1800bfe62  xor     r8d, r8d; int
0x1800bfe65  lea     edx, [r8+2]; unsigned int
0x1800bfe69  mov     rcx, rsi; unsigned __int16 *
0x1800bfe6c  call    ?CreateInstance@CFileSyncMetadataStore@@SAJPEBGKHPEAPEAV1@PEAH@Z; CFileSyncMetadataStore::CreateInstance(ushort const *,ulong,int,CFileSyncMetadataStore * *,int *)
0x1800bfe71  mov     edi, eax
0x1800bfe73  mov     ebx, eax
0x1800bfe75  cmp     r14d, 80041289h
0x1800bfe7c  jnz     loc_1800BFF17
0x1800bfe82  test    eax, eax
0x1800bfe84  js      short loc_1800BFED9
0x1800bfe86  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 2
0x1800bfe8d  jz      loc_1800BFDFC
0x1800bfe93  xor     eax, eax
0x1800bfe95  mov     [rsp+880h+var_820], ax
0x1800bfe9a  xor     edx, edx; Val
0x1800bfe9c  mov     r8d, 7FEh; Size
0x1800bfea2  lea     rcx, [rsp+880h+var_81E]; void *
0x1800bfea7  call    memset_0
0x1800bfeac  lea     r8, [rsp+880h+var_820]; unsigned __int16 *
0x1800bfeb1  mov     ecx, ebx; dwMessageId
0x1800bfeb3  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x1800bfeb8  mov     [rsp+880h+dwFlags], ebx
0x1800bfebc  lea     r9, [rsp+880h+var_820]
0x1800bfec1  mov     r8, rsi
0x1800bfec4  lea     rdx, ECSHOST_EVENT_CORESYNC_DATABASE_CORRUPTION
0x1800bfecb  call    McTemplateU0zzd_EventWriteTransfer
0x1800bfed0  mov     [rsp+880h+var_848], ebx
0x1800bfed4  jmp     loc_1800BFF69
0x1800bfed9  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 2
0x1800bfee0  jz      loc_1800BFDFC
0x1800bfee6  xor     eax, eax
0x1800bfee8  mov     [rsp+880h+var_820], ax
0x1800bfeed  xor     edx, edx; Val
0x1800bfeef  mov     r8d, 7FEh; Size
0x1800bfef5  lea     rcx, [rsp+880h+var_81E]; void *
0x1800bfefa  call    memset_0
0x1800bfeff  lea     r8, [rsp+880h+var_820]; unsigned __int16 *
0x1800bff04  mov     ecx, edi; dwMessageId
0x1800bff06  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x1800bff0b  lea     rdx, ECSHOST_EVENT_CORESYNC_DATABASE_CORRUPTION_RECOVERY_FAILED
0x1800bff12  jmp     loc_1800C001B
0x1800bff17  test    edi, edi
0x1800bff19  js      loc_1800BFFE6
0x1800bff1f  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 2
0x1800bff26  jz      short loc_1800BFF65
0x1800bff28  xor     eax, eax
0x1800bff2a  mov     [rsp+880h+var_820], ax
0x1800bff2f  xor     edx, edx; Val
0x1800bff31  mov     r8d, 7FEh; Size
0x1800bff37  lea     rcx, [rsp+880h+var_81E]; void *
0x1800bff3c  call    memset_0
0x1800bff41  lea     r8, [rsp+880h+var_820]; unsigned __int16 *
0x1800bff46  mov     ecx, edi; dwMessageId
0x1800bff48  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x1800bff4d  mov     [rsp+880h+dwFlags], edi
0x1800bff51  lea     r9, [rsp+880h+var_820]
0x1800bff56  mov     r8, rsi
0x1800bff59  lea     rdx, ECSHOST_EVENT_CORESYNC_DATABASE_VERSION_INCOMPATIBLE
0x1800bff60  call    McTemplateU0zzd_EventWriteTransfer
0x1800bff65  mov     [rsp+880h+var_848], ebx
0x1800bff69  mov     eax, 0AFh
0x1800bff6e  mov     word ptr [rsp+880h+var_844], ax
0x1800bff73  mov     rcx, rsi; pObjectName
0x1800bff76  call    s_GrantWorkFoldersSvcAccessToMetadataDirectory
0x1800bff7b  mov     ebx, eax
0x1800bff7d  test    eax, eax
0x1800bff7f  mov     eax, 0B2h
0x1800bff84  js      loc_1800BFCC4
0x1800bff8a  mov     word ptr [rsp+880h+var_844], ax
0x1800bff8f  mov     ecx, ebx
0x1800bff91  and     ecx, 1FFF0000h
0x1800bff97  mov     eax, 80C80317h
0x1800bff9c  cmp     ecx, 0E5E0000h
0x1800bffa2  cmovz   ebx, eax
0x1800bffa5  mov     [rsp+880h+var_848], ebx
0x1800bffa9  lea     rcx, [rsp+880h+TokenHandle]
0x1800bffae  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800bffb3  lea     rcx, [rsp+880h+var_848]; this
0x1800bffb8  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bffbd  mov     eax, ebx
0x1800bffbf  mov     rcx, [rbp+780h+var_20]
0x1800bffc6  xor     rcx, rsp; StackCookie
0x1800bffc9  call    __security_check_cookie
0x1800bffce  lea     r11, [rsp+880h+var_10]
0x1800bffd6  mov     rbx, [r11+30h]
0x1800bffda  mov     rsi, [r11+38h]
0x1800bffde  mov     rsp, r11
0x1800bffe1  pop     r14
0x1800bffe3  pop     rdi
0x1800bffe4  pop     rbp
0x1800bffe5  retn
0x1800bffe6  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 2
0x1800bffed  jz      short loc_1800C002C
0x1800bffef  xor     eax, eax
0x1800bfff1  mov     [rsp+880h+var_820], ax
0x1800bfff6  xor     edx, edx; Val
0x1800bfff8  mov     r8d, 7FEh; Size
0x1800bfffe  lea     rcx, [rsp+880h+var_81E]; void *
0x1800c0003  call    memset_0
0x1800c0008  lea     r8, [rsp+880h+var_820]; unsigned __int16 *
0x1800c000d  mov     ecx, edi; dwMessageId
0x1800c000f  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x1800c0014  lea     rdx, ECSHOST_EVENT_CORESYNC_DATABASE_VERSION_INCOMPATIBLE_RECOVERY_FAILED
0x1800c001b  mov     [rsp+880h+dwFlags], edi
0x1800c001f  lea     r9, [rsp+880h+var_820]
0x1800c0024  mov     r8, rsi
0x1800c0027  call    McTemplateU0zzd_EventWriteTransfer
0x1800c002c  mov     eax, 0AFh
0x1800c0031  jmp     loc_1800BFCC4
```
