# CSpObjectToken::OpenFilesKey(_GUID const &,int,ISpDataKey * *)

- ea: `0x1800ef834`
- end: `0x1800efa19`
- name: `?OpenFilesKey@CSpObjectToken@@AEAAJAEBU_GUID@@HPEAPEAUISpDataKey@@@Z`
- size: `485`
- prototype: `int(CSpObjectToken *__hidden this, const struct _GUID *, int, struct ISpDataKey **)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ef150`
- `0x1800efbc4`
- `0x1800efce0`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000e518`
- `0x1800ee01c`
- `0x1800ef834`
- `0x180264460`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef8c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef8c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef927`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef8b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef8b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef89f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef89f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ef8d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ef8d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ef8df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ef8df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef933`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef933`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800ef877`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800ef877`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ef913`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ef913`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSpObjectToken::OpenFilesKey(
        CSpObjectToken *this,
        const struct _GUID *a2,
        int a3,
        struct ISpDataKey **a4)
{
  int LastError; // ebx
  int v8; // edi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *v11; // r8
  struct IUnknown *v12; // rsi
  __int64 v13; // rax
  int v14; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v16; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v19; // [rsp+38h] [rbp-18h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-8h] BYREF
  struct IUnknown *TokenInformation; // [rsp+98h] [rbp+48h] BYREF

  *a4 = 0;
  v19 = 0;
  lpsz = 0;
  LastError = StringFromCLSID(a2, &lpsz);
  if ( LastError < 0 )
    goto LABEL_30;
  LODWORD(TokenInformation) = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  v8 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_33;
  LastError = GetLastError();
  if ( LastError != 1008 )
    goto LABEL_12;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_33:
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( (_DWORD)TokenInformation )
        v8 = 1;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_12:
  if ( LastError < 0 )
    goto LABEL_30;
  if ( !v8 )
  {
LABEL_20:
    if ( (unsigned __int8)v8 == 1 )
      goto LABEL_25;
    goto LABEL_21;
  }
  TokenInformation = 0;
  LastError = ATL::CComObject<CSpLocalSettingsDataKey>::CreateInstance(&TokenInformation);
  if ( LastError >= 0 )
  {
    v12 = TokenInformation;
    LastError = CSpLocalSettingsDataKey::Initialize((CSpLocalSettingsDataKey *)TokenInformation, lpsz, v11);
    if ( LastError >= 0 )
    {
      if ( v19 != v12 )
        ATL::AtlComPtrAssign(&v19, v12);
      goto LABEL_20;
    }
  }
  if ( LastError != -2147009196 && LastError != -2147467263 )
    goto LABEL_20;
LABEL_21:
  v13 = *(_QWORD *)this;
  if ( a3 )
    v14 = (*(__int64 (__fastcall **)(CSpObjectToken *, LPOLESTR, struct IUnknown **))(v13 + 80))(this, lpsz, &v19);
  else
    v14 = (*(__int64 (__fastcall **)(CSpObjectToken *, LPOLESTR, struct IUnknown **))(v13 + 72))(this, lpsz, &v19);
  LastError = v14;
LABEL_25:
  if ( LastError >= 0 )
  {
    lpVtbl = v19->lpVtbl;
    if ( a3 )
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, struct ISpDataKey **))lpVtbl[3].AddRef)(
              v19,
              L"Files",
              a4);
    else
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, struct ISpDataKey **))lpVtbl[3].QueryInterface)(
              v19,
              L"Files",
              a4);
    LastError = v16;
  }
LABEL_30:
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpsz);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800ef834  mov     [rsp-28h+arg_0], rbx
0x1800ef839  mov     [rsp-28h+arg_8], rsi
0x1800ef83e  push    rbp
0x1800ef83f  push    rdi
0x1800ef840  push    r12
0x1800ef842  push    r14
0x1800ef844  push    r15
0x1800ef846  mov     rbp, rsp
0x1800ef849  sub     rsp, 50h
0x1800ef84d  mov     r12, r9
0x1800ef850  mov     r14d, r8d
0x1800ef853  mov     rax, rdx
0x1800ef856  mov     r15, rcx
0x1800ef859  mov     qword ptr [r9], 0
0x1800ef860  mov     [rbp+var_18], 0
0x1800ef868  mov     [rbp+lpsz], 0
0x1800ef870  lea     rdx, [rbp+lpsz]; lplpsz
0x1800ef874  mov     rcx, rax; rclsid
0x1800ef877  call    cs:__imp_StringFromCLSID
0x1800ef87d  mov     ebx, eax
0x1800ef87f  test    eax, eax
0x1800ef881  js      loc_1800EF9EB
0x1800ef887  mov     dword ptr [rbp+TokenInformation], 0
0x1800ef88e  mov     [rbp+TokenHandle], 0
0x1800ef896  mov     [rbp+var_20], 0
0x1800ef89d  xor     edi, edi
0x1800ef89f  call    cs:__imp_GetCurrentThread
0x1800ef8a5  mov     rcx, rax; ThreadHandle
0x1800ef8a8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ef8ac  lea     ebx, [rdi+1]
0x1800ef8af  mov     r8d, ebx; OpenAsSelf
0x1800ef8b2  lea     esi, [rdi+8]
0x1800ef8b5  mov     edx, esi; DesiredAccess
0x1800ef8b7  call    cs:__imp_OpenThreadToken
0x1800ef8bd  test    eax, eax
0x1800ef8bf  jnz     short loc_1800EF8F8
0x1800ef8c1  call    cs:__imp_GetLastError
0x1800ef8c7  mov     ebx, eax
0x1800ef8c9  cmp     eax, 3F0h
0x1800ef8ce  jnz     short loc_1800EF939
0x1800ef8d0  call    cs:__imp_GetCurrentProcess
0x1800ef8d6  mov     rcx, rax; ProcessHandle
0x1800ef8d9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800ef8dd  mov     edx, esi; DesiredAccess
0x1800ef8df  call    cs:__imp_OpenProcessToken
0x1800ef8e5  test    eax, eax
0x1800ef8e7  jnz     short loc_1800EF8F3
0x1800ef8e9  call    cs:__imp_GetLastError
0x1800ef8ef  mov     ebx, eax
0x1800ef8f1  jmp     short loc_1800EF939
0x1800ef8f3  mov     ebx, 1
0x1800ef8f8  lea     rax, [rbp+var_20]
0x1800ef8fc  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800ef901  mov     r9d, 4; TokenInformationLength
0x1800ef907  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800ef90b  lea     edx, [r9+19h]; TokenInformationClass
0x1800ef90f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ef913  call    cs:__imp_GetTokenInformation
0x1800ef919  test    eax, eax
0x1800ef91b  jz      short loc_1800EF927
0x1800ef91d  cmp     dword ptr [rbp+TokenInformation], edi
0x1800ef920  cmovnz  edi, ebx
0x1800ef923  xor     ebx, ebx
0x1800ef925  jmp     short loc_1800EF92F
0x1800ef927  call    cs:__imp_GetLastError
0x1800ef92d  mov     ebx, eax
0x1800ef92f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ef933  call    cs:__imp_CloseHandle
0x1800ef939  test    ebx, ebx
0x1800ef93b  js      loc_1800EF9EB
0x1800ef941  test    edi, edi
0x1800ef943  jz      short loc_1800EF996
0x1800ef945  mov     [rbp+TokenInformation], 0
0x1800ef94d  lea     rcx, [rbp+TokenInformation]
0x1800ef951  call    ?CreateInstance@?$CComObject@VCSpLocalSettingsDataKey@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSpLocalSettingsDataKey>::CreateInstance(ATL::CComObject<CSpLocalSettingsDataKey> * *)
0x1800ef956  mov     ebx, eax
0x1800ef958  test    eax, eax
0x1800ef95a  js      short loc_1800EF986
0x1800ef95c  mov     rdx, [rbp+lpsz]; unsigned __int16 *
0x1800ef960  mov     rsi, [rbp+TokenInformation]
0x1800ef964  mov     rcx, rsi; this
0x1800ef967  call    ?Initialize@CSpLocalSettingsDataKey@@QEAAJPEBG0@Z; CSpLocalSettingsDataKey::Initialize(ushort const *,ushort const *)
0x1800ef96c  mov     ebx, eax
0x1800ef96e  test    eax, eax
0x1800ef970  js      short loc_1800EF986
0x1800ef972  cmp     [rbp+var_18], rsi
0x1800ef976  jz      short loc_1800EF996
0x1800ef978  mov     rdx, rsi; struct IUnknown *
0x1800ef97b  lea     rcx, [rbp+var_18]; struct IUnknown **
0x1800ef97f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ef984  jmp     short loc_1800EF996
0x1800ef986  cmp     ebx, 80073D54h
0x1800ef98c  jz      short loc_1800EF99C
0x1800ef98e  cmp     ebx, 80004001h
0x1800ef994  jz      short loc_1800EF99C
0x1800ef996  xor     dil, 1
0x1800ef99a  jz      short loc_1800EF9C0
0x1800ef99c  mov     rax, [r15]
0x1800ef99f  lea     r8, [rbp+var_18]
0x1800ef9a3  mov     rdx, [rbp+lpsz]
0x1800ef9a7  mov     rcx, r15
0x1800ef9aa  test    r14d, r14d
0x1800ef9ad  jz      short loc_1800EF9B5
0x1800ef9af  mov     rax, [rax+50h]
0x1800ef9b3  jmp     short loc_1800EF9B9
0x1800ef9b5  mov     rax, [rax+48h]
0x1800ef9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef9be  mov     ebx, eax
0x1800ef9c0  test    ebx, ebx
0x1800ef9c2  js      short loc_1800EF9EB
0x1800ef9c4  mov     rcx, [rbp+var_18]
0x1800ef9c8  mov     r8, r12
0x1800ef9cb  lea     rdx, aFiles; "Files"
0x1800ef9d2  mov     rax, [rcx]
0x1800ef9d5  test    r14d, r14d
0x1800ef9d8  jz      short loc_1800EF9E0
0x1800ef9da  mov     rax, [rax+50h]
0x1800ef9de  jmp     short loc_1800EF9E4
0x1800ef9e0  mov     rax, [rax+48h]
0x1800ef9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef9e9  mov     ebx, eax
0x1800ef9eb  lea     rcx, [rbp+lpsz]; this
0x1800ef9ef  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ef9f4  nop
0x1800ef9f5  lea     rcx, [rbp+var_18]
0x1800ef9f9  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800ef9fe  mov     eax, ebx
0x1800efa00  lea     r11, [rsp+50h+var_s0]
0x1800efa05  mov     rbx, [r11+30h]
0x1800efa09  mov     rsi, [r11+38h]
0x1800efa0d  mov     rsp, r11
0x1800efa10  pop     r15
0x1800efa12  pop     r14
0x1800efa14  pop     r12
0x1800efa16  pop     rdi
0x1800efa17  pop     rbp
0x1800efa18  retn
```
