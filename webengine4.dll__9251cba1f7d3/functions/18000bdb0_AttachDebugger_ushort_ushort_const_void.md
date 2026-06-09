# AttachDebugger(ushort *,ushort const *,void *)

- ea: `0x18000bdb0`
- end: `0x18000c030`
- name: `?AttachDebugger@@YAJPEAGPEBGPEAX@Z`
- size: `640`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000bdb0`
- `0x18000c0c4`
- `0x18000c148`
- `0x18001c338`
- `0x18004d030`
- `0x18004d350`
- `0x18004d854`
- `0x180065b60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000bfef`
- `KERNEL32!CloseHandle` at `0x18000bfef`
- `KERNEL32!GetCurrentProcessId` at `0x18000bf75`
- `KERNEL32!GetCurrentProcessId` at `0x18000bf75`
- `KERNEL32!GetCurrentThread` at `0x18000bdea`
- `KERNEL32!GetCurrentThread` at `0x18000bdea`
- `ADVAPI32!SetThreadToken` at `0x18000be9f`
- `ADVAPI32!SetThreadToken` at `0x18000bfd5`
- `ADVAPI32!SetThreadToken` at `0x18000be9f`
- `ADVAPI32!SetThreadToken` at `0x18000bfd5`
- `ADVAPI32!OpenThreadToken` at `0x18000be35`
- `ADVAPI32!OpenThreadToken` at `0x18000be35`
- `ADVAPI32!RevertToSelf` at `0x18000be44`
- `ADVAPI32!RevertToSelf` at `0x18000bfc0`
- `ADVAPI32!RevertToSelf` at `0x18000be44`
- `ADVAPI32!RevertToSelf` at `0x18000bfc0`
- `ole32!CoUninitialize` at `0x18000c00a`
- `ole32!CoUninitialize` at `0x18000c00a`
- `ole32!CoSetProxyBlanket` at `0x18000bf62`
- `ole32!CoSetProxyBlanket` at `0x18000bf62`
- `ole32!CoCreateInstance` at `0x18000bec6`
- `ole32!CoCreateInstance` at `0x18000bec6`
- `ole32!IIDFromString` at `0x18000be15`
- `ole32!IIDFromString` at `0x18000be15`
- `ole32!CoTaskMemFree` at `0x18000bffe`
- `ole32!CoTaskMemFree` at `0x18000bffe`
- `ole32!CoQueryProxyBlanket` at `0x18000bf0a`
- `ole32!CoQueryProxyBlanket` at `0x18000bf0a`

## pseudocode

```c
__int64 __fastcall AttachDebugger(LPCOLESTR lpsz, const unsigned __int16 *a2, void *a3)
{
  int v6; // r14d
  HANDLE CurrentThread; // r15
  unsigned int v8; // ebx
  BOOL v9; // eax
  unsigned int LastWin32Error; // eax
  HRESULT v11; // eax
  int CurrentPlatform; // eax
  DWORD v13; // ecx
  struct IUnknownVtbl *lpVtbl; // rbx
  DWORD CurrentProcessId; // eax
  IUnknown *pProxy; // [rsp+40h] [rbp-39h] BYREF
  DWORD pCapabilites; // [rsp+48h] [rbp-31h] BYREF
  int v19; // [rsp+4Ch] [rbp-2Dh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-29h] BYREF
  WINBOOL IsMember; // [rsp+58h] [rbp-21h] BYREF
  int v22; // [rsp+5Ch] [rbp-1Dh] BYREF
  DWORD pImpLevel; // [rsp+60h] [rbp-19h] BYREF
  DWORD pAuthnLevel; // [rsp+64h] [rbp-15h] BYREF
  DWORD pAuthzSvc; // [rsp+68h] [rbp-11h] BYREF
  DWORD pwAuthnSvc; // [rsp+6Ch] [rbp-Dh] BYREF
  LPOLESTR pServerPrincName; // [rsp+70h] [rbp-9h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+78h] [rbp-1h] BYREF
  GUID iid; // [rsp+80h] [rbp+7h] BYREF

  v19 = 0;
  pProxy = 0;
  v6 = 0;
  TokenHandle = 0;
  pServerPrincName = 0;
  CurrentThread = GetCurrentThread();
  v8 = EnsureCoInitialized(&v19);
  if ( v8 )
    goto LABEL_19;
  v8 = IIDFromString(lpsz, &iid);
  if ( v8 )
    goto LABEL_19;
  v9 = OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
  TokenHandle = (void *)(-(__int64)v9 & (unsigned __int64)TokenHandle);
  if ( !RevertToSelf() )
    goto LABEL_4;
  v8 = IsTokenAdmin(a3, &IsMember);
  if ( !v8 )
  {
    if ( IsMember )
      goto LABEL_10;
    v8 = IsTokenSameAsProcessToken(a3, &v22);
    if ( !v8 )
    {
      if ( !v22 )
      {
        v8 = -2147024891;
        goto LABEL_19;
      }
LABEL_10:
      if ( SetThreadToken(0, a3) )
      {
        v6 = 1;
        v8 = CoCreateInstance(&iid, 0, 5u, &GUID_e9958f1f_0a56_424a_a300_530ebb2e9865, (LPVOID *)&pProxy);
        if ( v8 )
          goto LABEL_19;
        v11 = CoQueryProxyBlanket(
                pProxy,
                &pwAuthnSvc,
                &pAuthzSvc,
                &pServerPrincName,
                &pAuthnLevel,
                &pImpLevel,
                &pAuthInfo,
                &pCapabilites);
        v8 = v11;
        if ( v11 != -2147467262 )
        {
          if ( v11 )
            goto LABEL_19;
          CurrentPlatform = GetCurrentPlatform();
          v13 = pCapabilites;
          if ( CurrentPlatform == 5 )
            v13 = v8 + 32;
          pCapabilites = v13;
          pImpLevel = v8 + 3;
          v8 = CoSetProxyBlanket(pProxy, pwAuthnSvc, pAuthzSvc, pServerPrincName, pAuthnLevel, v8 + 3, pAuthInfo, v13);
          if ( v8 )
            goto LABEL_19;
        }
        lpVtbl = pProxy->lpVtbl;
        CurrentProcessId = GetCurrentProcessId();
        LastWin32Error = ((__int64 (__fastcall *)(IUnknown *, GUID *, _QWORD, __int64, _DWORD, const unsigned __int16 *))lpVtbl[1].QueryInterface)(
                           pProxy,
                           &GUID_NULL,
                           CurrentProcessId,
                           2,
                           0,
                           a2);
        goto LABEL_18;
      }
LABEL_4:
      LastWin32Error = GetLastWin32Error();
LABEL_18:
      v8 = LastWin32Error;
    }
  }
LABEL_19:
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v6 )
  {
    if ( !RevertToSelf() )
      goto LABEL_25;
    if ( !TokenHandle )
      goto LABEL_28;
    if ( !SetThreadToken(0, TokenHandle) )
LABEL_25:
      v8 = GetLastWin32Error();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
LABEL_28:
  if ( pServerPrincName )
    CoTaskMemFree(pServerPrincName);
  if ( v19 )
    CoUninitialize();
  return v8;
}

```

## disassembly

```asm
0x18000bdb0  push    rbp
0x18000bdb2  push    rbx
0x18000bdb3  push    rsi
0x18000bdb4  push    rdi
0x18000bdb5  push    r12
0x18000bdb7  push    r14
0x18000bdb9  push    r15
0x18000bdbb  lea     rbp, [rsp-27h]
0x18000bdc0  sub     rsp, 0A0h
0x18000bdc7  mov     rax, cs:__security_cookie
0x18000bdce  xor     rax, rsp
0x18000bdd1  mov     [rbp+57h+var_40], rax
0x18000bdd5  and     [rbp+57h+var_84], 0
0x18000bdd9  mov     rdi, r8
0x18000bddc  and     [rbp+57h+pProxy], 0
0x18000bde1  mov     r12, rdx
0x18000bde4  mov     rsi, rcx
0x18000bde7  xor     r14d, r14d
0x18000bdea  call    cs:__imp_GetCurrentThread
0x18000bdf0  and     [rbp+57h+TokenHandle], r14
0x18000bdf4  lea     rcx, [rbp+57h+var_84]; int *
0x18000bdf8  and     [rbp+57h+pServerPrincName], r14
0x18000bdfc  mov     r15, rax
0x18000bdff  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x18000be04  mov     ebx, eax
0x18000be06  test    eax, eax
0x18000be08  jnz     loc_18000BFA5
0x18000be0e  lea     rdx, [rbp+57h+iid]; lpiid
0x18000be12  mov     rcx, rsi; lpsz
0x18000be15  call    cs:__imp_IIDFromString
0x18000be1b  mov     ebx, eax
0x18000be1d  test    eax, eax
0x18000be1f  jnz     loc_18000BFA5
0x18000be25  lea     esi, [rax+1]
0x18000be28  mov     rcx, r15; ThreadHandle
0x18000be2b  mov     r8d, esi; OpenAsSelf
0x18000be2e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000be32  lea     edx, [rax+4]; DesiredAccess
0x18000be35  call    cs:__imp_OpenThreadToken
0x18000be3b  neg     eax
0x18000be3d  sbb     rcx, rcx
0x18000be40  and     [rbp+57h+TokenHandle], rcx
0x18000be44  call    cs:__imp_RevertToSelf
0x18000be4a  test    eax, eax
0x18000be4c  jnz     short loc_18000BE58
0x18000be4e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000be53  jmp     loc_18000BFA3
0x18000be58  lea     rdx, [rbp+57h+IsMember]; IsMember
0x18000be5c  mov     rcx, rdi; TokenHandle
0x18000be5f  call    ?IsTokenAdmin@@YAJPEAXPEAH@Z; IsTokenAdmin(void *,int *)
0x18000be64  mov     ebx, eax
0x18000be66  test    eax, eax
0x18000be68  jnz     loc_18000BFA5
0x18000be6e  cmp     [rbp+57h+IsMember], r14d
0x18000be72  jnz     short loc_18000BE9A
0x18000be74  lea     rdx, [rbp+57h+var_74]; int *
0x18000be78  mov     rcx, rdi; void *
0x18000be7b  call    ?IsTokenSameAsProcessToken@@YAJPEAXPEAH@Z; IsTokenSameAsProcessToken(void *,int *)
0x18000be80  mov     ebx, eax
0x18000be82  test    eax, eax
0x18000be84  jnz     loc_18000BFA5
0x18000be8a  cmp     [rbp+57h+var_74], r14d
0x18000be8e  jnz     short loc_18000BE9A
0x18000be90  mov     ebx, 80070005h
0x18000be95  jmp     loc_18000BFA5
0x18000be9a  mov     rdx, rdi; Token
0x18000be9d  xor     ecx, ecx; Thread
0x18000be9f  call    cs:__imp_SetThreadToken
0x18000bea5  test    eax, eax
0x18000bea7  jz      short loc_18000BE4E
0x18000bea9  xor     edx, edx; pUnkOuter
0x18000beab  lea     rax, [rbp+57h+pProxy]
0x18000beaf  lea     r9, _GUID_e9958f1f_0a56_424a_a300_530ebb2e9865; riid
0x18000beb6  mov     [rsp+0D0h+ppv], rax; ppv
0x18000bebb  lea     rcx, [rbp+57h+iid]; rclsid
0x18000bebf  mov     r14d, esi
0x18000bec2  lea     r8d, [rdx+5]; dwClsContext
0x18000bec6  call    cs:__imp_CoCreateInstance
0x18000becc  mov     ebx, eax
0x18000bece  test    eax, eax
0x18000bed0  jnz     loc_18000BFA5
0x18000bed6  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18000beda  lea     rax, [rbp+57h+var_88]
0x18000bede  mov     [rsp+0D0h+pCapabilites], rax; pCapabilites
0x18000bee3  lea     r9, [rbp+57h+pServerPrincName]; pServerPrincName
0x18000bee7  lea     rax, [rbp+57h+var_58]
0x18000beeb  mov     [rsp+0D0h+pAuthInfo], rax; pAuthInfo
0x18000bef0  lea     r8, [rbp+57h+pAuthzSvc]; pAuthzSvc
0x18000bef4  lea     rax, [rbp+57h+var_70]
0x18000bef8  mov     [rsp+0D0h+pImpLevel], rax; pImpLevel
0x18000befd  lea     rdx, [rbp+57h+pwAuthnSvc]; pwAuthnSvc
0x18000bf01  lea     rax, [rbp+57h+pAuthnLevel]
0x18000bf05  mov     [rsp+0D0h+ppv], rax; pAuthnLevel
0x18000bf0a  call    cs:__imp_CoQueryProxyBlanket
0x18000bf10  mov     ebx, eax
0x18000bf12  cmp     eax, 80004002h
0x18000bf17  jz      short loc_18000BF6E
0x18000bf19  test    eax, eax
0x18000bf1b  jnz     loc_18000BFA5
0x18000bf21  call    ?GetCurrentPlatform@@YA?AW4ASPX_PLATFORM@@XZ; GetCurrentPlatform(void)
0x18000bf26  mov     ecx, [rbp+57h+var_88]
0x18000bf29  lea     edx, [rbx+20h]
0x18000bf2c  mov     r9, [rbp+57h+pServerPrincName]; pServerPrincName
0x18000bf30  cmp     eax, 5
0x18000bf33  mov     rax, [rbp+57h+var_58]
0x18000bf37  mov     r8d, [rbp+57h+pAuthzSvc]; dwAuthzSvc
0x18000bf3b  cmovz   ecx, edx
0x18000bf3e  mov     dword ptr [rsp+0D0h+pCapabilites], ecx; dwCapabilities
0x18000bf42  lea     edx, [rbx+3]
0x18000bf45  mov     [rsp+0D0h+pAuthInfo], rax; pAuthInfo
0x18000bf4a  mov     eax, [rbp+57h+pAuthnLevel]
0x18000bf4d  mov     dword ptr [rsp+0D0h+pImpLevel], edx; dwImpLevel
0x18000bf51  mov     [rbp+57h+var_88], ecx
0x18000bf54  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18000bf58  mov     [rbp+57h+var_70], edx
0x18000bf5b  mov     edx, [rbp+57h+pwAuthnSvc]; dwAuthnSvc
0x18000bf5e  mov     dword ptr [rsp+0D0h+ppv], eax; dwAuthnLevel
0x18000bf62  call    cs:__imp_CoSetProxyBlanket
0x18000bf68  mov     ebx, eax
0x18000bf6a  test    eax, eax
0x18000bf6c  jnz     short loc_18000BFA5
0x18000bf6e  mov     rax, [rbp+57h+pProxy]
0x18000bf72  mov     rbx, [rax]
0x18000bf75  call    cs:__imp_GetCurrentProcessId
0x18000bf7b  mov     rcx, [rbp+57h+pProxy]
0x18000bf7f  lea     rdx, GUID_NULL
0x18000bf86  mov     r8d, eax
0x18000bf89  mov     [rsp+0D0h+pImpLevel], r12
0x18000bf8e  mov     rax, [rbx+18h]
0x18000bf92  mov     r9d, 2
0x18000bf98  and     dword ptr [rsp+0D0h+ppv], 0
0x18000bf9d  call    cs:__guard_dispatch_icall_fptr
0x18000bfa3  mov     ebx, eax
0x18000bfa5  mov     rcx, [rbp+57h+pProxy]
0x18000bfa9  test    rcx, rcx
0x18000bfac  jz      short loc_18000BFBB
0x18000bfae  mov     rax, [rcx]
0x18000bfb1  mov     rax, [rax+10h]
0x18000bfb5  call    cs:__guard_dispatch_icall_fptr
0x18000bfbb  test    r14d, r14d
0x18000bfbe  jz      short loc_18000BFE6
0x18000bfc0  call    cs:__imp_RevertToSelf
0x18000bfc6  test    eax, eax
0x18000bfc8  jz      short loc_18000BFDF
0x18000bfca  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18000bfce  test    rdx, rdx
0x18000bfd1  jz      short loc_18000BFF5
0x18000bfd3  xor     ecx, ecx; Thread
0x18000bfd5  call    cs:__imp_SetThreadToken
0x18000bfdb  test    eax, eax
0x18000bfdd  jnz     short loc_18000BFE6
0x18000bfdf  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000bfe4  mov     ebx, eax
0x18000bfe6  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000bfea  test    rcx, rcx
0x18000bfed  jz      short loc_18000BFF5
0x18000bfef  call    cs:__imp_CloseHandle
0x18000bff5  mov     rcx, [rbp+57h+pServerPrincName]; pv
0x18000bff9  test    rcx, rcx
0x18000bffc  jz      short loc_18000C004
0x18000bffe  call    cs:__imp_CoTaskMemFree
0x18000c004  cmp     [rbp+57h+var_84], 0
0x18000c008  jz      short loc_18000C010
0x18000c00a  call    cs:__imp_CoUninitialize
0x18000c010  mov     eax, ebx
0x18000c012  mov     rcx, [rbp+57h+var_40]
0x18000c016  xor     rcx, rsp; StackCookie
0x18000c019  call    __security_check_cookie
0x18000c01e  add     rsp, 0A0h
0x18000c025  pop     r15
0x18000c027  pop     r14
0x18000c029  pop     r12
0x18000c02b  pop     rdi
0x18000c02c  pop     rsi
0x18000c02d  pop     rbx
0x18000c02e  pop     rbp
0x18000c02f  retn
```
