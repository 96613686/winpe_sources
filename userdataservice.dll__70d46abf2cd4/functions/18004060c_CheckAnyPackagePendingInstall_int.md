# CheckAnyPackagePendingInstall(int *)

- ea: `0x18004060c`
- end: `0x180040753`
- name: `?CheckAnyPackagePendingInstall@@YAJPEAH@Z`
- size: `327`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004038c`

## callees

- `0x180008f0c`
- `0x180012988`
- `0x18004060c`
- `0x180041994`
- `0x1800977a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040683`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004070c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004070c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040679`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040679`
- `AppXDeploymentClient!__imp_ClientGetAllPackagesToBeInstalledForUser` at `0x1800406de`
- `AppXDeploymentClient!__imp_ClientGetAllPackagesToBeInstalledForUser` at `0x1800406de`
- `AppXDeploymentClient!__imp_ClientDeleteAllPackagesFromMainPackageArray` at `0x180040722`
- `AppXDeploymentClient!__imp_ClientDeleteAllPackagesFromMainPackageArray` at `0x180040722`

## string_xrefs

- `0x18004063e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x18004069e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800406f0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall CheckAnyPackagePendingInstall(int *a1, __int64 a2)
{
  int token_information; // eax
  unsigned int v4; // ebx
  void *v5; // rcx
  void *v7; // rdi
  signed int LastError; // eax
  int AllPackagesToBeInstalledForUser; // eax
  unsigned int v10; // [rsp+60h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+30h] BYREF
  void *Block; // [rsp+70h] [rbp+38h] BYREF
  __int64 v13; // [rsp+78h] [rbp+40h] BYREF

  *a1 = 1;
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a2);
  v4 = token_information;
  if ( token_information < 0 )
  {
    Log_HREvent(
      (unsigned int)token_information,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      541);
    v5 = Block;
    if ( !Block )
      return v4;
LABEL_3:
    operator delete(v5);
    return v4;
  }
  v7 = Block;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      v4,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      544);
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&StringSid);
LABEL_9:
    if ( !v7 )
      return v4;
    v5 = v7;
    goto LABEL_3;
  }
  v13 = 0;
  v10 = 0;
  AllPackagesToBeInstalledForUser = ClientGetAllPackagesToBeInstalledForUser(StringSid, 0, &v13, &v10);
  v4 = AllPackagesToBeInstalledForUser;
  if ( AllPackagesToBeInstalledForUser < 0 )
  {
    Log_HREvent(
      (unsigned int)AllPackagesToBeInstalledForUser,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      553);
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_9;
  }
  if ( v13 )
    ClientDeleteAllPackagesFromMainPackageArray(v10, &v13);
  *a1 = v10 != 0;
  auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&StringSid);
  if ( v7 )
    operator delete(v7);
  return 0;
}

```

## disassembly

```asm
0x18004060c  push    rbp
0x18004060e  push    rbx
0x18004060f  push    rsi
0x180040610  push    rdi
0x180040611  mov     rbp, rsp
0x180040614  sub     rsp, 38h
0x180040618  mov     rsi, rcx
0x18004061b  mov     dword ptr [rcx], 1
0x180040621  lea     rcx, [rbp+Block]
0x180040625  mov     [rbp+Block], 0
0x18004062d  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180040632  mov     ebx, eax
0x180040634  test    eax, eax
0x180040636  jns     short loc_180040666
0x180040638  mov     r9d, 21Dh
0x18004063e  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040645  mov     edx, 1
0x18004064a  mov     ecx, eax
0x18004064c  call    Log_HREvent
0x180040651  mov     rcx, [rbp+Block]; Block
0x180040655  test    rcx, rcx
0x180040658  jz      short loc_18004065F
0x18004065a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004065f  mov     eax, ebx
0x180040661  jmp     loc_18004074A
0x180040666  mov     rdi, [rbp+Block]
0x18004066a  lea     rdx, [rbp+StringSid]; StringSid
0x18004066e  mov     [rbp+StringSid], 0
0x180040676  mov     rcx, [rdi]; Sid
0x180040679  call    cs:__imp_ConvertSidToStringSidW
0x18004067f  test    eax, eax
0x180040681  jnz     short loc_1800406C1
0x180040683  call    cs:__imp_GetLastError
0x180040689  mov     ebx, eax
0x18004068b  test    eax, eax
0x18004068d  jle     short loc_180040698
0x18004068f  movzx   ebx, ax
0x180040692  or      ebx, 80070000h
0x180040698  mov     r9d, 220h
0x18004069e  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800406a5  xor     edx, edx
0x1800406a7  mov     ecx, ebx
0x1800406a9  call    Log_HREvent
0x1800406ae  lea     rcx, [rbp+StringSid]
0x1800406b2  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800406b7  test    rdi, rdi
0x1800406ba  jz      short loc_18004065F
0x1800406bc  mov     rcx, rdi
0x1800406bf  jmp     short loc_18004065A
0x1800406c1  mov     rcx, [rbp+StringSid]
0x1800406c5  lea     r9, [rbp+arg_0]
0x1800406c9  lea     r8, [rbp+arg_18]
0x1800406cd  mov     [rbp+arg_18], 0
0x1800406d5  xor     edx, edx
0x1800406d7  mov     [rbp+arg_0], 0
0x1800406de  call    cs:__imp_ClientGetAllPackagesToBeInstalledForUser
0x1800406e4  mov     ebx, eax
0x1800406e6  test    eax, eax
0x1800406e8  jns     short loc_180040714
0x1800406ea  mov     r9d, 229h
0x1800406f0  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800406f7  mov     edx, 1
0x1800406fc  mov     ecx, eax
0x1800406fe  call    Log_HREvent
0x180040703  mov     rcx, [rbp+StringSid]; hMem
0x180040707  test    rcx, rcx
0x18004070a  jz      short loc_1800406B7
0x18004070c  call    cs:__imp_LocalFree
0x180040712  jmp     short loc_1800406B7
0x180040714  cmp     [rbp+arg_18], 0
0x180040719  jz      short loc_180040728
0x18004071b  mov     ecx, [rbp+arg_0]
0x18004071e  lea     rdx, [rbp+arg_18]
0x180040722  call    cs:__imp_ClientDeleteAllPackagesFromMainPackageArray
0x180040728  xor     eax, eax
0x18004072a  lea     rcx, [rbp+StringSid]
0x18004072e  cmp     [rbp+arg_0], eax
0x180040731  setnz   al
0x180040734  mov     [rsi], eax
0x180040736  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x18004073b  test    rdi, rdi
0x18004073e  jz      short loc_180040748
0x180040740  mov     rcx, rdi; Block
0x180040743  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040748  xor     eax, eax
0x18004074a  add     rsp, 38h
0x18004074e  pop     rdi
0x18004074f  pop     rsi
0x180040750  pop     rbx
0x180040751  pop     rbp
0x180040752  retn
```
