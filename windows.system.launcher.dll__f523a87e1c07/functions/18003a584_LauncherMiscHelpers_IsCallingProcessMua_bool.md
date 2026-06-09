# LauncherMiscHelpers::IsCallingProcessMua(bool &)

- ea: `0x18003a584`
- end: `0x18003a6f9`
- name: `?IsCallingProcessMua@LauncherMiscHelpers@@YAJAEA_N@Z`
- size: `373`
- prototype: `__int64 __fastcall(LauncherMiscHelpers *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f01c`
- `0x18003a3b8`
- `0x1800e82a4`

## callees

- `0x180010c04`
- `0x18003a584`
- `0x18003a700`
- `0x18003a8d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18003a5eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18003a5eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a60c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a65b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a6a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a6d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a60c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a65b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a6a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003a6d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6e1`

## string_xrefs

- `0x18003a61d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LauncherMiscHelpers::IsCallingProcessMua(LauncherMiscHelpers *this, unsigned __int16 **a2)
{
  int CallingProcessPackageFullName; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rbx
  int IsEffectiveSupportedUsersMultiple; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-20h]
  __int64 v13; // [rsp+28h] [rbp-18h] BYREF
  char v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v16; // [rsp+50h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+18h] BYREF

  *(_BYTE *)this = 0;
  pv = 0;
  CallingProcessPackageFullName = UserAwareCallerIdentity::GetCallingProcessPackageFullName(
                                    (UserAwareCallerIdentity *)&pv,
                                    a2);
  if ( CallingProcessPackageFullName < 0 )
  {
LABEL_2:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)CallingProcessPackageFullName;
  }
  v16 = 0;
  v13 = 0;
  v14 = 1;
  CallingProcessPackageFullName = SRCacheManager_Open(0, &v13);
  if ( v14 )
  {
    v5 = v16;
    v16 = v13;
    if ( v5 )
      SRCacheManager_Close(v5);
  }
  if ( CallingProcessPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      (int)&v16);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecoreuap\\shell\\inc\\LauncherMiscHelpers.h",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      v12);
    v6 = v16;
    v16 = 0;
    if ( v6 )
      SRCacheManager_Close(v6);
    goto LABEL_2;
  }
  v7 = pv;
  IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                        (struct StateRepository::Cache::Manager_NoThrow *)&v16,
                                        (const unsigned __int16 *)pv,
                                        (bool *)this);
  v9 = IsEffectiveSupportedUsersMultiple;
  if ( IsEffectiveSupportedUsersMultiple >= 0 )
  {
    v11 = v16;
    v16 = 0;
    if ( v11 )
      SRCacheManager_Close(v11);
    if ( v7 )
      CoTaskMemFree(v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\shell\\inc\\LauncherMiscHelpers.h",
      (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
      (int)&v16);
    v10 = v16;
    v16 = 0;
    if ( v10 )
      SRCacheManager_Close(v10);
    if ( v7 )
      CoTaskMemFree(v7);
    return v9;
  }
}

```

## disassembly

```asm
0x18003a584  mov     [rsp-8+arg_10], rbx
0x18003a589  mov     [rsp-8+arg_18], rdi
0x18003a58e  push    rbp
0x18003a58f  mov     rbp, rsp
0x18003a592  sub     rsp, 40h
0x18003a596  mov     rdi, rcx
0x18003a599  mov     byte ptr [rcx], 0
0x18003a59c  mov     [rbp+pv], 0
0x18003a5a4  lea     rcx, [rbp+pv]; this
0x18003a5a8  call    ?GetCallingProcessPackageFullName@UserAwareCallerIdentity@@YAJPEAPEAG@Z; UserAwareCallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x18003a5ad  mov     ebx, eax
0x18003a5af  test    eax, eax
0x18003a5b1  jns     short loc_18003A5C9
0x18003a5b3  mov     rcx, [rbp+pv]; pv
0x18003a5b7  test    rcx, rcx
0x18003a5ba  jz      short loc_18003A5C2
0x18003a5bc  call    cs:__imp_CoTaskMemFree
0x18003a5c2  mov     eax, ebx
0x18003a5c4  jmp     loc_18003A6E9
0x18003a5c9  mov     [rbp+arg_0], 0
0x18003a5d1  lea     rax, [rbp+arg_0]
0x18003a5d5  mov     [rbp+var_20], rax
0x18003a5d9  mov     [rbp+var_18], 0
0x18003a5e1  mov     [rbp+var_10], 1
0x18003a5e5  lea     rdx, [rbp+var_18]
0x18003a5e9  xor     ecx, ecx
0x18003a5eb  call    cs:__imp_SRCacheManager_Open
0x18003a5f1  mov     ebx, eax
0x18003a5f3  cmp     [rbp+var_10], 0
0x18003a5f7  jz      short loc_18003A612
0x18003a5f9  mov     r8, [rbp+var_20]
0x18003a5fd  mov     rcx, [r8]
0x18003a600  mov     rdx, [rbp+var_18]
0x18003a604  mov     [r8], rdx
0x18003a607  test    rcx, rcx
0x18003a60a  jz      short loc_18003A612
0x18003a60c  call    cs:__imp_SRCacheManager_Close
0x18003a612  test    ebx, ebx
0x18003a614  jns     short loc_18003A666
0x18003a616  mov     rcx, [rbp+8]; this
0x18003a61a  mov     r9d, ebx; char *
0x18003a61d  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003a624  mov     edx, 0A5h; void *
0x18003a629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a62e  mov     rcx, [rbp+8]; this
0x18003a632  mov     r9d, ebx; char *
0x18003a635  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\inc\\LauncherMiscHel"...
0x18003a63c  mov     edx, 75h ; 'u'; void *
0x18003a641  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a646  mov     rcx, [rbp+arg_0]
0x18003a64a  mov     [rbp+arg_0], 0
0x18003a652  test    rcx, rcx
0x18003a655  jz      loc_18003A5B3
0x18003a65b  call    cs:__imp_SRCacheManager_Close
0x18003a661  jmp     loc_18003A5B3
0x18003a666  mov     r8, rdi; bool *
0x18003a669  mov     rbx, [rbp+pv]
0x18003a66d  mov     rdx, rbx; unsigned __int16 *
0x18003a670  lea     rcx, [rbp+arg_0]; struct StateRepository::Cache::Manager_NoThrow *
0x18003a674  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18003a679  mov     edi, eax
0x18003a67b  test    eax, eax
0x18003a67d  jns     short loc_18003A6C1
0x18003a67f  mov     rcx, [rbp+8]; this
0x18003a683  mov     r9d, eax; char *
0x18003a686  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\inc\\LauncherMiscHel"...
0x18003a68d  mov     edx, 76h ; 'v'; void *
0x18003a692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a697  mov     rcx, [rbp+arg_0]
0x18003a69b  mov     [rbp+arg_0], 0
0x18003a6a3  test    rcx, rcx
0x18003a6a6  jz      short loc_18003A6AF
0x18003a6a8  call    cs:__imp_SRCacheManager_Close
0x18003a6ae  nop
0x18003a6af  test    rbx, rbx
0x18003a6b2  jz      short loc_18003A6BD
0x18003a6b4  mov     rcx, rbx; pv
0x18003a6b7  call    cs:__imp_CoTaskMemFree
0x18003a6bd  mov     eax, edi
0x18003a6bf  jmp     short loc_18003A6E9
0x18003a6c1  mov     rcx, [rbp+arg_0]
0x18003a6c5  mov     [rbp+arg_0], 0
0x18003a6cd  test    rcx, rcx
0x18003a6d0  jz      short loc_18003A6D9
0x18003a6d2  call    cs:__imp_SRCacheManager_Close
0x18003a6d8  nop
0x18003a6d9  test    rbx, rbx
0x18003a6dc  jz      short loc_18003A6E7
0x18003a6de  mov     rcx, rbx; pv
0x18003a6e1  call    cs:__imp_CoTaskMemFree
0x18003a6e7  xor     eax, eax
0x18003a6e9  mov     rbx, [rsp+40h+arg_10]
0x18003a6ee  mov     rdi, [rsp+40h+arg_18]
0x18003a6f3  add     rsp, 40h
0x18003a6f7  pop     rbp
0x18003a6f8  retn
```
