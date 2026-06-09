# CredentialManager::DeleteCredentialByEntryId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001b2ac`
- end: `0x18001b3ab`
- name: `?DeleteCredentialByEntryId@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800159e0`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x18001b2ac`
- `0x18001b560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b2f6`
- `ADVAPI32!CredDeleteW` at `0x18001b2e8`
- `ADVAPI32!CredDeleteW` at `0x18001b2e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CredentialManager::DeleteCredentialByEntryId(__int64 a1, const WCHAR *a2)
{
  DWORD LastError; // eax
  DWORD v4; // ebx
  char v6[8]; // [rsp+20h] [rbp-50h] BYREF
  void (__fastcall *v7)(HANDLE); // [rsp+28h] [rbp-48h]
  void *CurrentThreadTokenAndRevertToSelf; // [rsp+30h] [rbp-40h]
  void **pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  char v10; // [rsp+40h] [rbp-30h]
  const char *v11; // [rsp+48h] [rbp-28h]
  __int64 v12; // [rsp+50h] [rbp-20h]
  __int64 v13; // [rsp+58h] [rbp-18h]
  DWORD v14; // [rsp+60h] [rbp-10h]
  int v15; // [rsp+64h] [rbp-Ch]
  int v16; // [rsp+68h] [rbp-8h]

  v6[0] = 0;
  v7 = RestoreAndCloseThreadToken;
  CurrentThreadTokenAndRevertToSelf = GetCurrentThreadTokenAndRevertToSelf();
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const WCHAR **)a2;
  if ( !CredDeleteW(a2, 1u, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError != 1168 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, LastError);
        }
        v10 = 0;
        v11 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
        v12 = 0;
        v13 = 0;
        v14 = v4;
        v15 = -1;
        v16 = 419;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
  }
  return wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v6);
}

```

## disassembly

```asm
0x18001b2ac  mov     [rsp-8+arg_0], rbx
0x18001b2b1  push    rbp
0x18001b2b2  mov     rbp, rsp
0x18001b2b5  sub     rsp, 70h
0x18001b2b9  mov     rbx, rdx
0x18001b2bc  call    GetCurrentThreadTokenAndRevertToSelf
0x18001b2c1  mov     [rbp+var_50], 0
0x18001b2c5  lea     rcx, RestoreAndCloseThreadToken
0x18001b2cc  mov     [rbp+var_48], rcx
0x18001b2d0  mov     [rbp+var_40], rax
0x18001b2d4  cmp     qword ptr [rbx+18h], 8
0x18001b2d9  jb      short loc_18001B2DE
0x18001b2db  mov     rbx, [rbx]
0x18001b2de  xor     r8d, r8d; Flags
0x18001b2e1  lea     edx, [r8+1]; Type
0x18001b2e5  mov     rcx, rbx; TargetName
0x18001b2e8  call    cs:__imp_CredDeleteW
0x18001b2ee  test    eax, eax
0x18001b2f0  jnz     loc_18001B394
0x18001b2f6  call    cs:__imp_GetLastError
0x18001b2fc  mov     ebx, eax
0x18001b2fe  test    eax, eax
0x18001b300  jz      loc_18001B394
0x18001b306  cmp     eax, 490h
0x18001b30b  jz      loc_18001B394
0x18001b311  lea     rax, WPP_GLOBAL_Control
0x18001b318  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b31f  cmp     rcx, rax
0x18001b322  jz      short loc_18001B348
0x18001b324  test    byte ptr [rcx+1Ch], 40h
0x18001b328  jz      short loc_18001B348
0x18001b32a  cmp     byte ptr [rcx+19h], 2
0x18001b32e  jb      short loc_18001B348
0x18001b330  mov     edx, 1Bh
0x18001b335  mov     r9d, ebx
0x18001b338  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b33f  mov     rcx, [rcx+10h]
0x18001b343  call    WPP_SF_D
0x18001b348  mov     [rbp+var_30], 0
0x18001b34c  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b353  mov     [rbp+var_28], rax
0x18001b357  mov     [rbp+var_20], 0
0x18001b35f  mov     [rbp+var_18], 0
0x18001b367  mov     [rbp+var_10], ebx
0x18001b36a  mov     [rbp+var_C], 0FFFFFFFFh
0x18001b371  mov     [rbp+var_8], 1A3h
0x18001b378  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b37f  mov     [rbp+pExceptionObject], rax
0x18001b383  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b38a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001b38e  call    _CxxThrowException_0
0x18001b394  lea     rcx, [rbp+var_50]
0x18001b398  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001b39d  mov     rbx, [rsp+70h+arg_0]
0x18001b3a5  add     rsp, 70h
0x18001b3a9  pop     rbp
0x18001b3aa  retn
```
