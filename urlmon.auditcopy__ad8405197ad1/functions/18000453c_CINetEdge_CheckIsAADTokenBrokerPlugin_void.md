# CINetEdge::CheckIsAADTokenBrokerPlugin(void)

- ea: `0x18000453c`
- end: `0x1800046ea`
- name: `?CheckIsAADTokenBrokerPlugin@CINetEdge@@AEAA_NXZ`
- size: `430`
- prototype: `char __fastcall(WCHAR *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004384`

## callees

- `0x18000453c`
- `0x1800046f0`
- `0x1800a4318`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004629`
- `msvcrt!_wcsicmp` at `0x180004644`
- `msvcrt!_wcsicmp` at `0x180004629`
- `msvcrt!_wcsicmp` at `0x180004644`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000456d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000456d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004602`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800046af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800046af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800045b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800045b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000465d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000465d`

## pseudocode

```c
char __fastcall CINetEdge::CheckIsAADTokenBrokerPlugin(WCHAR *this)
{
  char v1; // si
  HANDLE CurrentProcess; // rax
  bool v3; // di
  void *v4; // rbx
  int Error; // ebx
  char *v6; // rcx
  HANDLE v7; // rax
  unsigned __int16 **v8; // r8
  signed int LastError; // eax
  LPWSTR TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenInformation = this;
  v1 = 0;
  CurrentProcess = GetCurrentProcess();
  v3 = 0;
  TokenHandle = 0;
  v4 = CurrentProcess;
  if ( CurrentProcess == GetCurrentProcess() )
  {
    TokenHandle = (HANDLE)-4LL;
LABEL_3:
    Error = 0;
    goto LABEL_4;
  }
  if ( OpenProcessToken(v4, 8u, &TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
  if ( Error < 0 )
    goto LABEL_8;
  ReturnLength = 0;
  LODWORD(TokenInformation) = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    Error = 0;
LABEL_7:
    v3 = (_DWORD)TokenInformation != 0;
    goto LABEL_8;
  }
  Error = ResultFromKnownLastError();
  if ( Error >= 0 )
    goto LABEL_7;
LABEL_8:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  if ( Error >= 0 && v3 )
  {
    TokenInformation = 0;
    v7 = GetCurrentProcess();
    if ( (int)CallerIdentity::GetPackageSidStringFromProcessHandle(v7, &TokenInformation, v8) >= 0
      && (!_wcsicmp(
             L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
             TokenInformation)
       || !_wcsicmp(
             L"S-1-15-2-2867405820-2738857118-4021800865-410975764-3768480088-1705603374-2243483066",
             TokenInformation)) )
    {
      v1 = 1;
    }
    if ( TokenInformation )
      CoTaskMemFree(TokenInformation);
  }
  return v1;
}

```

## disassembly

```asm
0x18000453c  mov     [rsp-18h+arg_18], rbx
0x180004541  mov     [rsp-18h+TokenInformation], rcx
0x180004546  push    rbp
0x180004547  push    rsi
0x180004548  push    rdi
0x180004549  mov     rbp, rsp
0x18000454c  sub     rsp, 30h
0x180004550  xor     sil, sil
0x180004553  call    cs:__imp_GetCurrentProcess
0x18000455a  nop     dword ptr [rax+rax+00h]
0x18000455f  xor     dil, dil
0x180004562  mov     [rbp+TokenHandle], 0
0x18000456a  mov     rbx, rax
0x18000456d  call    cs:__imp_GetCurrentProcess
0x180004574  nop     dword ptr [rax+rax+00h]
0x180004579  cmp     rbx, rax
0x18000457c  jnz     loc_1800046A3
0x180004582  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18000458a  xor     ebx, ebx
0x18000458c  test    ebx, ebx
0x18000458e  js      short loc_1800045D7
0x180004590  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180004594  lea     rax, [rbp+arg_8]
0x180004598  mov     r9d, 4; TokenInformationLength
0x18000459e  mov     [rbp+arg_8], 0
0x1800045a5  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800045a9  mov     dword ptr [rbp+TokenInformation], 0
0x1800045b0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800045b5  lea     edx, [r9+19h]; TokenInformationClass
0x1800045b9  call    cs:__imp_GetTokenInformation
0x1800045c0  nop     dword ptr [rax+rax+00h]
0x1800045c5  test    eax, eax
0x1800045c7  jz      loc_1800046C5
0x1800045cd  xor     ebx, ebx
0x1800045cf  cmp     dword ptr [rbp+TokenInformation], 0
0x1800045d3  setnz   dil
0x1800045d7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800045db  mov     [rbp+TokenHandle], 0
0x1800045e3  lea     rax, [rcx-1]
0x1800045e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800045eb  jbe     loc_1800046D9
0x1800045f1  test    ebx, ebx
0x1800045f3  js      short loc_180004669
0x1800045f5  test    dil, dil
0x1800045f8  jz      short loc_180004669
0x1800045fa  mov     [rbp+TokenInformation], 0
0x180004602  call    cs:__imp_GetCurrentProcess
0x180004609  nop     dword ptr [rax+rax+00h]
0x18000460e  mov     rcx, rax; ProcessHandle
0x180004611  lea     rdx, [rbp+TokenInformation]; StringSid
0x180004615  call    ?GetPackageSidStringFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageSidStringFromProcessHandle(void *,ushort * *)
0x18000461a  test    eax, eax
0x18000461c  js      short loc_180004654
0x18000461e  mov     rdx, [rbp+TokenInformation]; String2
0x180004622  lea     rcx, aS1152191009188; "S-1-15-2-1910091885-1573563583-11049412"...
0x180004629  call    cs:__imp__wcsicmp
0x180004630  nop     dword ptr [rax+rax+00h]
0x180004635  test    eax, eax
0x180004637  jz      short loc_18000467A
0x180004639  mov     rdx, [rbp+TokenInformation]; String2
0x18000463d  lea     rcx, aS1152286740582; "S-1-15-2-2867405820-2738857118-40218008"...
0x180004644  call    cs:__imp__wcsicmp
0x18000464b  nop     dword ptr [rax+rax+00h]
0x180004650  test    eax, eax
0x180004652  jz      short loc_18000467A
0x180004654  mov     rcx, [rbp+TokenInformation]; pv
0x180004658  test    rcx, rcx
0x18000465b  jz      short loc_180004669
0x18000465d  call    cs:__imp_CoTaskMemFree
0x180004664  nop     dword ptr [rax+rax+00h]
0x180004669  mov     rbx, [rsp+30h+arg_18]
0x18000466e  mov     al, sil
0x180004671  add     rsp, 30h
0x180004675  pop     rdi
0x180004676  pop     rsi
0x180004677  pop     rbp
0x180004678  retn
0x18000467a  mov     sil, 1
0x18000467d  jmp     short loc_180004654
0x18000467f  call    cs:__imp_GetLastError
0x180004686  nop     dword ptr [rax+rax+00h]
0x18000468b  mov     ebx, eax
0x18000468d  test    eax, eax
0x18000468f  jle     loc_18000458C
0x180004695  movzx   ebx, ax
0x180004698  or      ebx, 80070000h
0x18000469e  jmp     loc_18000458C
0x1800046a3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800046a7  mov     edx, 8; DesiredAccess
0x1800046ac  mov     rcx, rbx; ProcessHandle
0x1800046af  call    cs:__imp_OpenProcessToken
0x1800046b6  nop     dword ptr [rax+rax+00h]
0x1800046bb  test    eax, eax
0x1800046bd  jnz     loc_18000458A
0x1800046c3  jmp     short loc_18000467F
0x1800046c5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800046ca  mov     ebx, eax
0x1800046cc  test    eax, eax
0x1800046ce  js      loc_1800045D7
0x1800046d4  jmp     loc_1800045CF
0x1800046d9  call    cs:__imp_CloseHandle
0x1800046e0  nop     dword ptr [rax+rax+00h]
0x1800046e5  jmp     loc_1800045F1
```
