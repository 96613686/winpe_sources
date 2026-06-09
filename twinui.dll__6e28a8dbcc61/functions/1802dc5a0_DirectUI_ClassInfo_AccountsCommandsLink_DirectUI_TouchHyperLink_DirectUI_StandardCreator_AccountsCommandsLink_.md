# DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x1802dc5a0`
- end: `0x1802dc6bf`
- name: `?Register@?$ClassInfo@VAccountsCommandsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VAccountsCommandsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1802dc6d0`

## callees

- `0x1802dc35c`
- `0x1802dc5a0`
- `0x1803a3010`

## import_xrefs

- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802dc5c3`
- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802dc5c3`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802dc5b8`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802dc5d4`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802dc608`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802dc5b8`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802dc5d4`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802dc608`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802dc5f9`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802dc5f9`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802dc5eb`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802dc5eb`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802dc6ac`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802dc6ac`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802dc638`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802dc638`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802dc673`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802dc673`

## string_xrefs

- `0x1802dc60e`: `AccountsCommandsLink`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Register(
        __int64 a1,
        struct DirectUI::IClassInfo *a2,
        DirectUI::ClassInfoBase *a3)
{
  int v3; // ebx
  void (__fastcall ***ClassInfoPtr)(_QWORD); // rax
  struct _RTL_CRITICAL_SECTION *FactoryLock; // rax
  struct DirectUI::IClassInfo *v6; // rax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  struct DirectUI::IClassInfo *v11; // rdi
  int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::IClassInfo *v15; // [rsp+58h] [rbp+10h] BYREF
  DirectUI::ClassInfoBase *v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  v15 = a2;
  v14 = a1;
  if ( DirectUI::TouchHyperLink::GetClassInfoPtr() )
  {
    ClassInfoPtr = (void (__fastcall ***)(_QWORD))DirectUI::TouchHyperLink::GetClassInfoPtr();
    (**ClassInfoPtr)(ClassInfoPtr);
  }
  else
  {
    v3 = DirectUI::TouchHyperLink::Register();
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  FactoryLock = (struct _RTL_CRITICAL_SECTION *)DirectUI::Element::GetFactoryLock();
  DirectUI::CritSecLock::CritSecLock((DirectUI::CritSecLock *)&v14, FactoryLock);
  v15 = 0;
  v6 = (struct DirectUI::IClassInfo *)DirectUI::TouchHyperLink::GetClassInfoPtr();
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"AccountsCommandsLink", 0) )
  {
    v3 = 0;
    AccountsCommandsLink::Class = v15;
  }
  else
  {
    AccountsCommandsLink::Class = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Create(
           v8,
           v7,
           v9,
           v10,
           v13,
           (__int64)&v16);
    if ( v3 >= 0 )
    {
      v11 = v16;
      v3 = DirectUI::ClassInfoBase::Register(v16);
      if ( v3 < 0 )
        (*(void (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)v11 + 88LL))(v11);
      else
        AccountsCommandsLink::Class = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802dc5a0  mov     rax, rsp
0x1802dc5a3  mov     [rax+20h], rbx
0x1802dc5a7  mov     [rax+18h], r8
0x1802dc5ab  mov     [rax+10h], rdx
0x1802dc5af  mov     [rax+8], rcx
0x1802dc5b3  push    rdi
0x1802dc5b4  sub     rsp, 40h
0x1802dc5b8  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802dc5be  test    rax, rax
0x1802dc5c1  jnz     short loc_1802DC5D4
0x1802dc5c3  call    cs:__imp_?Register@TouchHyperLink@DirectUI@@SAJXZ; DirectUI::TouchHyperLink::Register(void)
0x1802dc5c9  mov     ebx, eax
0x1802dc5cb  test    eax, eax
0x1802dc5cd  jns     short loc_1802DC5EB
0x1802dc5cf  jmp     loc_1802DC6B2
0x1802dc5d4  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802dc5da  mov     rdx, rax
0x1802dc5dd  mov     rcx, [rax]
0x1802dc5e0  mov     rax, [rcx]
0x1802dc5e3  mov     rcx, rdx
0x1802dc5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802dc5eb  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x1802dc5f1  mov     rdx, rax
0x1802dc5f4  lea     rcx, [rsp+48h+arg_0]
0x1802dc5f9  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x1802dc5ff  mov     [rsp+48h+arg_8], 0
0x1802dc608  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802dc60e  lea     rcx, aAccountscomman_0; "AccountsCommandsLink"
0x1802dc615  mov     [rsp+48h+var_18], 0
0x1802dc61a  mov     [rsp+48h+var_20], rcx
0x1802dc61f  mov     r9, rax
0x1802dc622  lea     rcx, __ImageBase
0x1802dc629  xor     r8d, r8d
0x1802dc62c  mov     [rsp+48h+var_28], rcx
0x1802dc631  xor     edx, edx
0x1802dc633  lea     rcx, [rsp+48h+arg_8]
0x1802dc638  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x1802dc63e  test    al, al
0x1802dc640  jnz     short loc_1802DC699
0x1802dc642  lea     rax, [rsp+48h+arg_10]
0x1802dc647  mov     cs:?Class@AccountsCommandsLink@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * AccountsCommandsLink::Class
0x1802dc652  mov     [rsp+48h+var_20], rax
0x1802dc657  mov     [rsp+48h+arg_10], 0
0x1802dc660  call    ?Create@?$ClassInfo@VAccountsCommandsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VAccountsCommandsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<AccountsCommandsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<AccountsCommandsLink>> * *)
0x1802dc665  mov     ebx, eax
0x1802dc667  test    eax, eax
0x1802dc669  js      short loc_1802DC6A7
0x1802dc66b  mov     rdi, [rsp+48h+arg_10]
0x1802dc670  mov     rcx, rdi
0x1802dc673  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x1802dc679  mov     ebx, eax
0x1802dc67b  test    eax, eax
0x1802dc67d  js      short loc_1802DC688
0x1802dc67f  mov     cs:?Class@AccountsCommandsLink@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * AccountsCommandsLink::Class
0x1802dc686  jmp     short loc_1802DC6A7
0x1802dc688  mov     rax, [rdi]
0x1802dc68b  mov     rcx, rdi
0x1802dc68e  mov     rax, [rax+58h]
0x1802dc692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802dc697  jmp     short loc_1802DC6A7
0x1802dc699  mov     rax, [rsp+48h+arg_8]
0x1802dc69e  xor     ebx, ebx
0x1802dc6a0  mov     cs:?Class@AccountsCommandsLink@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * AccountsCommandsLink::Class
0x1802dc6a7  lea     rcx, [rsp+48h+arg_0]
0x1802dc6ac  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x1802dc6b2  mov     eax, ebx
0x1802dc6b4  mov     rbx, [rsp+48h+arg_18]
0x1802dc6b9  add     rsp, 40h
0x1802dc6bd  pop     rdi
0x1802dc6be  retn
```
