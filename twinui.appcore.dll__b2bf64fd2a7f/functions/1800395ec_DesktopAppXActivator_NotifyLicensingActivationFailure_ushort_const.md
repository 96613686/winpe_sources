# DesktopAppXActivator::NotifyLicensingActivationFailure(ushort const *)

- ea: `0x1800395ec`
- end: `0x18003968e`
- name: `?NotifyLicensingActivationFailure@DesktopAppXActivator@@AEAAXPEBG@Z`
- size: `162`
- prototype: `void __fastcall(DesktopAppXActivator *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180023544`

## callees

- `0x18001e1a4`
- `0x18002b5b0`
- `0x18002d89c`
- `0x1800395ec`
- `0x18003a1a8`
- `0x18003a1c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180039626`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180039626`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039619`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039619`
- `ext-ms-win-core-storelicensing-l1-1-0!PackageRundownNotificationForStoreLicense` at `0x180039655`
- `ext-ms-win-core-storelicensing-l1-1-0!PackageRundownNotificationForStoreLicense` at `0x180039655`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DesktopAppXActivator::NotifyLicensingActivationFailure(
        DesktopAppXActivator *this,
        const unsigned __int16 *a2)
{
  char v3; // al
  const char *v4; // r9
  DWORD CurrentProcessId; // eax
  const char *v6; // r9
  int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  void *v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DesktopAppXActivator *pSessionId; // [rsp+30h] [rbp+8h] BYREF
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  pSessionId = this;
  v3 = IsBeginAcquireStoreLicenseForPackageActivationPresent();
  try
  {
    if ( v3 )
    {
      wil::get_token_information<_TOKEN_USER>(&Block);
      LODWORD(pSessionId) = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( !ProcessIdToSessionId(CurrentProcessId, (DWORD *)&pSessionId) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x171,
          (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
          v6);
      v7 = PackageRundownNotificationForStoreLicense(a2, (unsigned int)pSessionId, *(_QWORD *)Block);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(retaddr, v8, v9, (const char *)(unsigned int)v7, v11);
      v10 = Block;
      Block = 0;
      if ( v10 )
        operator delete(v10);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x1800395ec  mov     [rsp+pSessionId], rcx
0x1800395f1  push    rbx; int
0x1800395f2  sub     rsp, 20h
0x1800395f6  mov     rbx, rdx
0x1800395f9  call    IsBeginAcquireStoreLicenseForPackageActivationPresent
0x1800395fe  test    al, al
0x180039600  jz      loc_180039686
0x180039606  lea     rcx, [rsp+28h+Block]
0x18003960b  call    ??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z
0x180039610  nop
0x180039611  mov     dword ptr [rsp+28h+pSessionId], 0
0x180039619  call    cs:__imp_GetCurrentProcessId
0x18003961f  mov     ecx, eax; dwProcessId
0x180039621  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x180039626  call    cs:__imp_ProcessIdToSessionId
0x18003962c  mov     rcx, [rsp+28h]; this
0x180039631  test    eax, eax
0x180039633  jnz     short loc_180039646
0x180039635  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x18003963c  mov     edx, 171h; void *
0x180039641  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180039646  mov     r8, [rsp+28h+Block]
0x18003964b  mov     r8, [r8]
0x18003964e  mov     edx, dword ptr [rsp+28h+pSessionId]
0x180039652  mov     rcx, rbx
0x180039655  call    cs:__imp_PackageRundownNotificationForStoreLicense
0x18003965b  mov     rcx, [rsp+28h]; this
0x180039660  test    eax, eax
0x180039662  jns     short loc_18003966D
0x180039664  mov     r9d, eax; char *
0x180039667  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003966d  mov     rcx, [rsp+28h+Block]; Block
0x180039672  mov     [rsp+28h+Block], 0
0x18003967b  test    rcx, rcx
0x18003967e  jz      short loc_180039686
0x180039680  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039685  nop
0x180039686  jmp     short $+2
0x180039688  add     rsp, 20h
0x18003968c  pop     rbx
0x18003968d  retn
```
