# CUserProfile::VerifyThePath(IUserName *,ushort *,ulong)

- ea: `0x18006b704`
- end: `0x18006b82f`
- name: `?VerifyThePath@CUserProfile@@CAJPEAUIUserName@@PEAGK@Z`
- size: `299`
- prototype: `static int(struct IUserName *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006a9d0`

## callees

- `0x18000a210`
- `0x1800148d0`
- `0x18006ac5c`
- `0x18006b704`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b79e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006b768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006b768`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006b794`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006b794`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006b7f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006b7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b80f`

## string_xrefs

- `0x18006b7ba`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x18006b741`: `pUserName->GetUserSid failed: 0x%x in %s`
- `0x18006b74b`: `CUserProfile::VerifyThePath`
- `0x18006b786`: `ptrUserName->DuplicateTokenInPid failed: 0x%x in %s`

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
0x18006b704  mov     r11, rsp
0x18006b707  mov     [r11+10h], rbx
0x18006b70b  push    rbp
0x18006b70c  push    rsi
0x18006b70d  push    rdi
0x18006b70e  sub     rsp, 20h
0x18006b712  mov     ebp, r8d
0x18006b715  mov     rdi, rdx
0x18006b718  mov     rsi, rcx
0x18006b71b  mov     qword ptr [r11+20h], 0
0x18006b723  mov     qword ptr [r11+8], 0
0x18006b72b  mov     rax, [rcx]
0x18006b72e  lea     rdx, [r11+8]
0x18006b732  mov     rax, [rax+48h]
0x18006b736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b73b  mov     ebx, eax
0x18006b73d  test    eax, eax
0x18006b73f  jns     short loc_18006B761
0x18006b741  lea     rdx, aPusernameGetus; "pUserName->GetUserSid failed: 0x%x in %"...
0x18006b748  mov     r8d, eax
0x18006b74b  lea     r9, aCuserprofileVe; "CUserProfile::VerifyThePath"
0x18006b752  mov     ecx, 8; int
0x18006b757  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b75c  jmp     loc_18006B805
0x18006b761  mov     rax, [rsi]
0x18006b764  mov     rbx, [rax+50h]
0x18006b768  call    cs:__imp_GetCurrentProcessId
0x18006b76e  lea     r8, [rsp+38h+hToken]
0x18006b773  mov     edx, eax
0x18006b775  mov     rcx, rsi
0x18006b778  mov     rax, rbx
0x18006b77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b780  mov     ebx, eax
0x18006b782  test    eax, eax
0x18006b784  jns     short loc_18006B78F
0x18006b786  lea     rdx, aPtrusernameDup; "ptrUserName->DuplicateTokenInPid failed"...
0x18006b78d  jmp     short loc_18006B748
0x18006b78f  mov     rcx, [rsp+38h+hToken]; hToken
0x18006b794  call    cs:__imp_ImpersonateLoggedOnUser
0x18006b79a  test    eax, eax
0x18006b79c  jnz     short loc_18006B7C3
0x18006b79e  call    cs:__imp_GetLastError
0x18006b7a4  mov     ebx, eax
0x18006b7a6  test    eax, eax
0x18006b7a8  jle     short loc_18006B7B3
0x18006b7aa  movzx   ebx, ax
0x18006b7ad  or      ebx, 80070000h
0x18006b7b3  test    ebx, ebx
0x18006b7b5  jns     short loc_18006B7C3
0x18006b7b7  mov     r8d, ebx
0x18006b7ba  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x18006b7c1  jmp     short loc_18006B74B
0x18006b7c3  mov     rdx, rdi; lpFileName
0x18006b7c6  mov     rcx, [rsp+38h+pv]; pSid2
0x18006b7cb  call    ?CheckAccessToDirectory@CUserProfile@@CAJPEAXPEBG@Z; CUserProfile::CheckAccessToDirectory(void *,ushort const *)
0x18006b7d0  mov     ebx, eax
0x18006b7d2  test    eax, eax
0x18006b7d4  jz      short loc_18006B7F5
0x18006b7d6  xor     eax, eax
0x18006b7d8  mov     [rdi+rbp*2], ax
0x18006b7dc  mov     rdx, rdi; lpFileName
0x18006b7df  mov     rcx, [rsp+38h+pv]; pSid2
0x18006b7e4  call    ?CheckAccessToDirectory@CUserProfile@@CAJPEAXPEBG@Z; CUserProfile::CheckAccessToDirectory(void *,ushort const *)
0x18006b7e9  test    eax, eax
0x18006b7eb  jz      short loc_18006B7F3
0x18006b7ed  mov     word ptr [rdi+rbp*2], 2Eh ; '.'
0x18006b7f3  xor     ebx, ebx
0x18006b7f5  call    cs:__imp_RevertToSelf
0x18006b7fb  mov     ecx, 80070005h
0x18006b800  test    eax, eax
0x18006b802  cmovz   ebx, ecx
0x18006b805  mov     rcx, [rsp+38h+pv]; pv
0x18006b80a  test    rcx, rcx
0x18006b80d  jz      short loc_18006B816
0x18006b80f  call    cs:__imp_CoTaskMemFree
0x18006b815  nop
0x18006b816  lea     rcx, [rsp+38h+hToken]; this
0x18006b81b  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18006b820  mov     eax, ebx
0x18006b822  mov     rbx, [rsp+38h+arg_8]
0x18006b827  add     rsp, 20h
0x18006b82b  pop     rdi
0x18006b82c  pop     rsi
0x18006b82d  pop     rbp
0x18006b82e  retn
```
