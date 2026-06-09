# CRegAccount::RemoveReg(ushort const *,int)

- ea: `0x1800260d4`
- end: `0x1800263bb`
- name: `?RemoveReg@CRegAccount@@CAJPEBGH@Z`
- size: `743`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800269c8`

## callees

- `0x18001c550`
- `0x1800214a4`
- `0x180023c24`
- `0x180025afc`
- `0x180025ff4`
- `0x180026060`
- `0x1800260d4`
- `0x18003aba8`
- `0x18004c3cb`
- `0x18004d754`
- `0x18004eaa8`
- `0x18004ef84`

## import_xrefs

- `ucrtbase_clr0400!_wcsicmp` at `0x180026170`
- `ucrtbase_clr0400!_wcsicmp` at `0x180026170`

## string_xrefs

- `0x180026196`: `GetPrincipalSID`
- `0x1800261c3`: `GetPrincipalSID`
- `0x180026277`: `ACLAllDirs`
- `0x18002629c`: `ACLAllDirs`
- `0x18002618f`: `Getting Machine Account SID`
- `0x1800261b9`: `Getting Machine Account SID`
- `0x18002626d`: `Setting ACLs for the ASPNET account`
- `0x180026292`: `Setting ACLs for the ASPNET account`
- `0x180026357`: `Removing ASPNET account from registry`
- `0x180026378`: `Removing ASPNET account from registry`
- `0x180026361`: `RemoveAccountFromRegistry`
- `0x180026382`: `RemoveAccountFromRegistry`

## pseudocode

```c
__int64 __fastcall CRegAccount::RemoveReg(wchar_t *a1, int a2)
{
  unsigned int PrincipalSID; // ebx
  int v5; // eax
  int v6; // ecx
  int v7; // esi
  int v8; // eax
  int v9; // eax
  int v10; // ebx
  signed int v11; // eax
  int v13; // [rsp+50h] [rbp+8h] BYREF
  void *lpMem; // [rsp+60h] [rbp+18h] BYREF

  lpMem = 0;
  v13 = 0;
  PrincipalSID = 0;
  if ( a1 && *a1 )
  {
    if ( !(unsigned int)IsVista() )
    {
      CSetupLogging::Log(1, "IsDomainController", 0, "Determining if we are running on a domain controller");
      PrincipalSID = IsDomainController(&v13);
      CSetupLogging::Log(PrincipalSID, "IsDomainController", 0, "Determining if we are running on a domain controller");
      if ( PrincipalSID )
      {
        v13 = 0;
        PrincipalSID = 0;
      }
      v5 = _wcsicmp(a1, L"ASPNET");
      v6 = 0;
      if ( v5 || !v13 )
      {
        LOBYTE(v6) = v5 == 0;
        v7 = v6 != 0 ? a2 : 0;
        CSetupLogging::Log(1, "GetPrincipalSID", 0, "Getting Machine Account SID");
        PrincipalSID = GetPrincipalSID((char *)a1, &lpMem);
        CSetupLogging::Log(PrincipalSID, "GetPrincipalSID", 0, "Getting Machine Account SID");
        if ( lpMem )
        {
          if ( v7 )
          {
            CSetupLogging::Log(1, "RegisterAccountToLocalGroup", 0, "Removing Machine account from Guests group");
            v8 = CRegAccount::RegisterAccountToLocalGroup(a1, L"Guests", 0, lpMem);
            CSetupLogging::Log(v8, "RegisterAccountToLocalGroup", 0, "Removing Machine account from Guests group");
            CSetupLogging::Log(1, "RegisterAccountToLocalGroup", 0, "Removing Machine account from Users group");
            v9 = CRegAccount::RegisterAccountToLocalGroup(a1, L"Users", 0, lpMem);
            CSetupLogging::Log(v9, "RegisterAccountToLocalGroup", 0, "Removing Machine account from Users group");
          }
          CSetupLogging::Log(1, "ACLAllDirs", 0, "Setting ACLs for the ASPNET account");
          PrincipalSID = CRegAccount::ACLAllDirs(lpMem, 0);
          CSetupLogging::Log(PrincipalSID, "ACLAllDirs", 0, "Setting ACLs for the ASPNET account");
        }
        if ( v7 )
        {
          CSetupLogging::Log(1, "EnableUserAccount", 0, "Disabling ASPNET account");
          v10 = CRegAccount::EnableUserAccount(a1, 0);
          CSetupLogging::Log(v10, "EnableUserAccount", 0, "Disabling ASPNET account");
          CRegAccount::RemoveMachineAccountFromSpecialAccountsUserList();
          if ( !v10 )
            goto LABEL_21;
          CSetupLogging::Log(1, "NetUserDel", 0, "Deleting ASPNET account");
          v11 = NetUserDel_0(0, a1);
          if ( !v11 || v11 == 2221 )
          {
            PrincipalSID = 0;
          }
          else
          {
            PrincipalSID = (unsigned __int16)v11 | 0x80070000;
            if ( v11 <= 0 )
              PrincipalSID = v11;
          }
          CSetupLogging::Log(PrincipalSID, "NetUserDel", 0, "Deleting ASPNET account");
          if ( !PrincipalSID )
          {
LABEL_21:
            CSetupLogging::Log(1, "RemoveAccountFromRegistry", 0, "Removing ASPNET account from registry");
            PrincipalSID = CRegAccount::RemoveAccountFromRegistry(a1);
            CSetupLogging::Log(PrincipalSID, "RemoveAccountFromRegistry", 0, "Removing ASPNET account from registry");
          }
        }
      }
    }
  }
  else
  {
    PrincipalSID = -2147024809;
  }
  if ( lpMem )
    MemFree(lpMem);
  return PrincipalSID;
}

```

## disassembly

```asm
0x1800260d4  mov     [rsp+arg_8], rbx
0x1800260d9  push    rbp
0x1800260da  push    rsi
0x1800260db  push    rdi
0x1800260dc  push    r14
0x1800260de  push    r15
0x1800260e0  sub     rsp, 20h
0x1800260e4  xor     r14d, r14d
0x1800260e7  mov     ebp, edx
0x1800260e9  mov     [rsp+48h+lpMem], r14
0x1800260ee  mov     rdi, rcx
0x1800260f1  mov     [rsp+48h+arg_0], r14d
0x1800260f6  mov     ebx, r14d
0x1800260f9  test    rcx, rcx
0x1800260fc  jz      loc_180026394
0x180026102  cmp     [rcx], r14w
0x180026106  jz      loc_180026394
0x18002610c  call    ?IsVista@@YAHXZ; IsVista(void)
0x180026111  test    eax, eax
0x180026113  jnz     loc_180026399
0x180026119  lea     r15d, [r14+1]
0x18002611d  xor     r8d, r8d; unsigned int
0x180026120  mov     ecx, r15d; int
0x180026123  lea     r9, aDeterminingIfW; "Determining if we are running on a doma"...
0x18002612a  lea     rdx, aIsdomaincontro; "IsDomainController"
0x180026131  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026136  lea     rcx, [rsp+48h+arg_0]; int *
0x18002613b  call    ?IsDomainController@@YAJPEAH@Z; IsDomainController(int *)
0x180026140  lea     r9, aDeterminingIfW; "Determining if we are running on a doma"...
0x180026147  xor     r8d, r8d; unsigned int
0x18002614a  lea     rdx, aIsdomaincontro; "IsDomainController"
0x180026151  mov     ecx, eax; int
0x180026153  mov     ebx, eax
0x180026155  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18002615a  test    ebx, ebx
0x18002615c  jz      short loc_180026166
0x18002615e  mov     [rsp+48h+arg_0], r14d
0x180026163  mov     ebx, r14d
0x180026166  lea     rdx, aAspnet; "ASPNET"
0x18002616d  mov     rcx, rdi; String1
0x180026170  call    cs:__imp__wcsicmp
0x180026176  test    eax, eax
0x180026178  mov     ecx, r14d
0x18002617b  setz    cl
0x18002617e  test    eax, eax
0x180026180  jnz     short loc_18002618D
0x180026182  cmp     [rsp+48h+arg_0], r14d
0x180026187  jnz     loc_180026399
0x18002618d  neg     ecx
0x18002618f  lea     r9, aGettingMachine_0; "Getting Machine Account SID"
0x180026196  lea     rdx, aGetprincipalsi; "GetPrincipalSID"
0x18002619d  mov     ecx, r15d; int
0x1800261a0  sbb     esi, esi
0x1800261a2  xor     r8d, r8d; unsigned int
0x1800261a5  and     esi, ebp
0x1800261a7  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800261ac  lea     rdx, [rsp+48h+lpMem]; void **
0x1800261b1  mov     rcx, rdi; unsigned __int16 *
0x1800261b4  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x1800261b9  lea     r9, aGettingMachine_0; "Getting Machine Account SID"
0x1800261c0  xor     r8d, r8d; unsigned int
0x1800261c3  lea     rdx, aGetprincipalsi; "GetPrincipalSID"
0x1800261ca  mov     ecx, eax; int
0x1800261cc  mov     ebx, eax
0x1800261ce  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800261d3  cmp     [rsp+48h+lpMem], r14
0x1800261d8  jz      loc_1800262AC
0x1800261de  test    esi, esi
0x1800261e0  jz      loc_18002626D
0x1800261e6  lea     rbx, aRegisteraccoun; "RegisterAccountToLocalGroup"
0x1800261ed  xor     r8d, r8d; unsigned int
0x1800261f0  mov     rdx, rbx; char *
0x1800261f3  lea     r9, aRemovingMachin_0; "Removing Machine account from Guests gr"...
0x1800261fa  mov     ecx, r15d; int
0x1800261fd  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026202  mov     r9, [rsp+48h+lpMem]; void *
0x180026207  lea     rdx, aGuests; "Guests"
0x18002620e  xor     r8d, r8d; int
0x180026211  mov     rcx, rdi; unsigned __int16 *
0x180026214  call    ?RegisterAccountToLocalGroup@CRegAccount@@SAJPEBG0HPEAX@Z; CRegAccount::RegisterAccountToLocalGroup(ushort const *,ushort const *,int,void *)
0x180026219  lea     r9, aRemovingMachin_0; "Removing Machine account from Guests gr"...
0x180026220  xor     r8d, r8d; unsigned int
0x180026223  mov     rdx, rbx; char *
0x180026226  mov     ecx, eax; int
0x180026228  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18002622d  lea     r9, aRemovingMachin; "Removing Machine account from Users gro"...
0x180026234  xor     r8d, r8d; unsigned int
0x180026237  mov     rdx, rbx; char *
0x18002623a  mov     ecx, r15d; int
0x18002623d  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026242  mov     r9, [rsp+48h+lpMem]; void *
0x180026247  lea     rdx, aUsers_0; "Users"
0x18002624e  xor     r8d, r8d; int
0x180026251  mov     rcx, rdi; unsigned __int16 *
0x180026254  call    ?RegisterAccountToLocalGroup@CRegAccount@@SAJPEBG0HPEAX@Z; CRegAccount::RegisterAccountToLocalGroup(ushort const *,ushort const *,int,void *)
0x180026259  lea     r9, aRemovingMachin; "Removing Machine account from Users gro"...
0x180026260  xor     r8d, r8d; unsigned int
0x180026263  mov     rdx, rbx; char *
0x180026266  mov     ecx, eax; int
0x180026268  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18002626d  lea     r9, aSettingAclsFor; "Setting ACLs for the ASPNET account"
0x180026274  xor     r8d, r8d; unsigned int
0x180026277  lea     rdx, aAclalldirs; "ACLAllDirs"
0x18002627e  mov     ecx, r15d; int
0x180026281  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026286  mov     rcx, [rsp+48h+lpMem]; pSid1
0x18002628b  xor     edx, edx; int
0x18002628d  call    ?ACLAllDirs@CRegAccount@@SAJPEAXH@Z; CRegAccount::ACLAllDirs(void *,int)
0x180026292  lea     r9, aSettingAclsFor; "Setting ACLs for the ASPNET account"
0x180026299  xor     r8d, r8d; unsigned int
0x18002629c  lea     rdx, aAclalldirs; "ACLAllDirs"
0x1800262a3  mov     ecx, eax; int
0x1800262a5  mov     ebx, eax
0x1800262a7  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800262ac  test    esi, esi
0x1800262ae  jz      loc_180026399
0x1800262b4  lea     r9, aDisablingAspne_0; "Disabling ASPNET account"
0x1800262bb  xor     r8d, r8d; unsigned int
0x1800262be  lea     rdx, aEnableuseracco; "EnableUserAccount"
0x1800262c5  mov     ecx, r15d; int
0x1800262c8  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800262cd  xor     edx, edx; int
0x1800262cf  mov     rcx, rdi; unsigned __int16 *
0x1800262d2  call    ?EnableUserAccount@CRegAccount@@SAJPEBGH@Z; CRegAccount::EnableUserAccount(ushort const *,int)
0x1800262d7  lea     r9, aDisablingAspne_0; "Disabling ASPNET account"
0x1800262de  xor     r8d, r8d; unsigned int
0x1800262e1  lea     rdx, aEnableuseracco; "EnableUserAccount"
0x1800262e8  mov     ecx, eax; int
0x1800262ea  mov     ebx, eax
0x1800262ec  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x1800262f1  call    ?RemoveMachineAccountFromSpecialAccountsUserList@CRegAccount@@CAJXZ; CRegAccount::RemoveMachineAccountFromSpecialAccountsUserList(void)
0x1800262f6  test    ebx, ebx
0x1800262f8  jz      short loc_180026357
0x1800262fa  lea     r9, aDeletingAspnet; "Deleting ASPNET account"
0x180026301  xor     r8d, r8d; unsigned int
0x180026304  lea     rdx, aNetuserdel_0; "NetUserDel"
0x18002630b  mov     ecx, r15d; int
0x18002630e  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026313  mov     rdx, rdi; username
0x180026316  xor     ecx, ecx; servername
0x180026318  call    NetUserDel_0
0x18002631d  test    eax, eax
0x18002631f  jz      short loc_180026338
0x180026321  cmp     eax, 8ADh
0x180026326  jz      short loc_180026338
0x180026328  movzx   ebx, ax
0x18002632b  or      ebx, 80070000h
0x180026331  test    eax, eax
0x180026333  cmovle  ebx, eax
0x180026336  jmp     short loc_18002633B
0x180026338  mov     ebx, r14d
0x18002633b  lea     r9, aDeletingAspnet; "Deleting ASPNET account"
0x180026342  xor     r8d, r8d; unsigned int
0x180026345  lea     rdx, aNetuserdel_0; "NetUserDel"
0x18002634c  mov     ecx, ebx; int
0x18002634e  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026353  test    ebx, ebx
0x180026355  jnz     short loc_180026399
0x180026357  lea     r9, aRemovingAspnet_0; "Removing ASPNET account from registry"
0x18002635e  xor     r8d, r8d; unsigned int
0x180026361  lea     rdx, aRemoveaccountf; "RemoveAccountFromRegistry"
0x180026368  mov     ecx, r15d; int
0x18002636b  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026370  mov     rcx, rdi; lpValueName
0x180026373  call    ?RemoveAccountFromRegistry@CRegAccount@@CAJPEBG@Z; CRegAccount::RemoveAccountFromRegistry(ushort const *)
0x180026378  lea     r9, aRemovingAspnet_0; "Removing ASPNET account from registry"
0x18002637f  xor     r8d, r8d; unsigned int
0x180026382  lea     rdx, aRemoveaccountf; "RemoveAccountFromRegistry"
0x180026389  mov     ecx, eax; int
0x18002638b  mov     ebx, eax
0x18002638d  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x180026392  jmp     short loc_180026399
0x180026394  mov     ebx, 80070057h
0x180026399  mov     rcx, [rsp+48h+lpMem]; lpMem
0x18002639e  test    rcx, rcx
0x1800263a1  jz      short loc_1800263A8
0x1800263a3  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800263a8  mov     eax, ebx
0x1800263aa  mov     rbx, [rsp+48h+arg_8]
0x1800263af  add     rsp, 20h
0x1800263b3  pop     r15
0x1800263b5  pop     r14
0x1800263b7  pop     rdi
0x1800263b8  pop     rsi
0x1800263b9  pop     rbp
0x1800263ba  retn
```
