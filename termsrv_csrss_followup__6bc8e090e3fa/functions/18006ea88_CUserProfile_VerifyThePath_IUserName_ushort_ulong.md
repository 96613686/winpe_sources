# CUserProfile::VerifyThePath(IUserName *,ushort *,ulong)

- ea: `0x18006ea88`
- end: `0x18006ebd5`
- name: `?VerifyThePath@CUserProfile@@CAJPEAUIUserName@@PEAGK@Z`
- size: `333`
- prototype: `static int(struct IUserName *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006dc90`

## callees

- `0x180009940`
- `0x180015020`
- `0x18006df3c`
- `0x18006ea88`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006eaec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006eaec`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006eb1e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006eb1e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006eb8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006eb8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ebae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ebae`

## string_xrefs

- `0x18006eb50`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x18006eac5`: `pUserName->GetUserSid failed: 0x%x in %s`
- `0x18006eacf`: `CUserProfile::VerifyThePath`
- `0x18006eb10`: `ptrUserName->DuplicateTokenInPid failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserProfile::VerifyThePath(struct IUserName *a1, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v3; // rbp
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // rdx
  __int64 (__fastcall *v9)(struct IUserName *, _QWORD, HANDLE *); // rbx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp+20h] BYREF

  v3 = a3;
  hToken = 0;
  pv = 0;
  v6 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a1 + 72LL))(a1, &pv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "pUserName->GetUserSid failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v8, (unsigned int)v6, "CUserProfile::VerifyThePath");
    goto LABEL_18;
  }
  v9 = *(__int64 (__fastcall **)(struct IUserName *, _QWORD, HANDLE *))(*(_QWORD *)a1 + 80LL);
  CurrentProcessId = GetCurrentProcessId();
  v6 = v9(a1, CurrentProcessId, &hToken);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "ptrUserName->DuplicateTokenInPid failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( ImpersonateLoggedOnUser(hToken) )
    goto LABEL_12;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( (v7 & 0x80000000) == 0 )
  {
LABEL_12:
    v7 = CUserProfile::CheckAccessToDirectory(pv, a2);
    if ( v7 )
    {
      a2[v3] = 0;
      if ( (unsigned int)CUserProfile::CheckAccessToDirectory(pv, a2) )
        a2[v3] = 46;
      v7 = 0;
    }
    if ( !RevertToSelf() )
      v7 = -2147024891;
  }
  else
  {
    _DbgPrintMessage(8, "ImpersonateLoggedOnUser failed: 0x%x in %s", v7, "CUserProfile::VerifyThePath");
  }
LABEL_18:
  if ( pv )
    CoTaskMemFree(pv);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&hToken);
  return v7;
}

```

## disassembly

```asm
0x18006ea88  mov     r11, rsp
0x18006ea8b  mov     [r11+10h], rbx
0x18006ea8f  push    rbp
0x18006ea90  push    rsi
0x18006ea91  push    rdi
0x18006ea92  sub     rsp, 20h
0x18006ea96  mov     ebp, r8d
0x18006ea99  mov     rdi, rdx
0x18006ea9c  mov     rsi, rcx
0x18006ea9f  mov     qword ptr [r11+20h], 0
0x18006eaa7  mov     qword ptr [r11+8], 0
0x18006eaaf  mov     rax, [rcx]
0x18006eab2  lea     rdx, [r11+8]
0x18006eab6  mov     rax, [rax+48h]
0x18006eaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eabf  mov     ebx, eax
0x18006eac1  test    eax, eax
0x18006eac3  jns     short loc_18006EAE5
0x18006eac5  lea     rdx, aPusernameGetus; "pUserName->GetUserSid failed: 0x%x in %"...
0x18006eacc  mov     r8d, eax
0x18006eacf  lea     r9, aCuserprofileVe; "CUserProfile::VerifyThePath"
0x18006ead6  mov     ecx, 8; int
0x18006eadb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006eae0  jmp     loc_18006EBA4
0x18006eae5  mov     rax, [rsi]
0x18006eae8  mov     rbx, [rax+50h]
0x18006eaec  call    cs:__imp_GetCurrentProcessId
0x18006eaf3  nop     dword ptr [rax+rax+00h]
0x18006eaf8  lea     r8, [rsp+38h+hToken]
0x18006eafd  mov     edx, eax
0x18006eaff  mov     rcx, rsi
0x18006eb02  mov     rax, rbx
0x18006eb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb0a  mov     ebx, eax
0x18006eb0c  test    eax, eax
0x18006eb0e  jns     short loc_18006EB19
0x18006eb10  lea     rdx, aPtrusernameDup; "ptrUserName->DuplicateTokenInPid failed"...
0x18006eb17  jmp     short loc_18006EACC
0x18006eb19  mov     rcx, [rsp+38h+hToken]; hToken
0x18006eb1e  call    cs:__imp_ImpersonateLoggedOnUser
0x18006eb25  nop     dword ptr [rax+rax+00h]
0x18006eb2a  test    eax, eax
0x18006eb2c  jnz     short loc_18006EB5C
0x18006eb2e  call    cs:__imp_GetLastError
0x18006eb35  nop     dword ptr [rax+rax+00h]
0x18006eb3a  mov     ebx, eax
0x18006eb3c  test    eax, eax
0x18006eb3e  jle     short loc_18006EB49
0x18006eb40  movzx   ebx, ax
0x18006eb43  or      ebx, 80070000h
0x18006eb49  test    ebx, ebx
0x18006eb4b  jns     short loc_18006EB5C
0x18006eb4d  mov     r8d, ebx
0x18006eb50  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x18006eb57  jmp     loc_18006EACF
0x18006eb5c  mov     rdx, rdi; lpFileName
0x18006eb5f  mov     rcx, [rsp+38h+pv]; pSid2
0x18006eb64  call    ?CheckAccessToDirectory@CUserProfile@@CAJPEAXPEBG@Z; CUserProfile::CheckAccessToDirectory(void *,ushort const *)
0x18006eb69  mov     ebx, eax
0x18006eb6b  test    eax, eax
0x18006eb6d  jz      short loc_18006EB8E
0x18006eb6f  xor     eax, eax
0x18006eb71  mov     [rdi+rbp*2], ax
0x18006eb75  mov     rdx, rdi; lpFileName
0x18006eb78  mov     rcx, [rsp+38h+pv]; pSid2
0x18006eb7d  call    ?CheckAccessToDirectory@CUserProfile@@CAJPEAXPEBG@Z; CUserProfile::CheckAccessToDirectory(void *,ushort const *)
0x18006eb82  test    eax, eax
0x18006eb84  jz      short loc_18006EB8C
0x18006eb86  mov     word ptr [rdi+rbp*2], 2Eh ; '.'
0x18006eb8c  xor     ebx, ebx
0x18006eb8e  call    cs:__imp_RevertToSelf
0x18006eb95  nop     dword ptr [rax+rax+00h]
0x18006eb9a  mov     ecx, 80070005h
0x18006eb9f  test    eax, eax
0x18006eba1  cmovz   ebx, ecx
0x18006eba4  mov     rcx, [rsp+38h+pv]; pv
0x18006eba9  test    rcx, rcx
0x18006ebac  jz      short loc_18006EBBB
0x18006ebae  call    cs:__imp_CoTaskMemFree
0x18006ebb5  nop     dword ptr [rax+rax+00h]
0x18006ebba  nop
0x18006ebbb  lea     rcx, [rsp+38h+hToken]; this
0x18006ebc0  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18006ebc5  mov     eax, ebx
0x18006ebc7  mov     rbx, [rsp+38h+arg_8]
0x18006ebcc  add     rsp, 20h
0x18006ebd0  pop     rdi
0x18006ebd1  pop     rsi
0x18006ebd2  pop     rbp
0x18006ebd3  retn
```
