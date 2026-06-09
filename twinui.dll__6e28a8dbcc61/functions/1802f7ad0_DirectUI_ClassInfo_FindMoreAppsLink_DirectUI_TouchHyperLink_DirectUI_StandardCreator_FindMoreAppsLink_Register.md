# DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x1802f7ad0`
- end: `0x1802f7bef`
- name: `?Register@?$ClassInfo@VFindMoreAppsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VFindMoreAppsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1802f8340`

## callees

- `0x1802f5cbc`
- `0x1802f7ad0`
- `0x1803a3010`

## import_xrefs

- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802f7af3`
- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802f7af3`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7ae8`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7b04`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7b38`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7ae8`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7b04`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7b38`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802f7b29`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802f7b29`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802f7b1b`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802f7b1b`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802f7bdc`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802f7bdc`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802f7b68`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802f7b68`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802f7ba3`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802f7ba3`

## string_xrefs

- `0x1802f7b3e`: `FindMoreAppsLink`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Register(
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
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"FindMoreAppsLink", 0) )
  {
    v3 = 0;
    FindMoreAppsLink::s_pClassInfo = v15;
  }
  else
  {
    FindMoreAppsLink::s_pClassInfo = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Create(
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
        FindMoreAppsLink::s_pClassInfo = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802f7ad0  mov     rax, rsp
0x1802f7ad3  mov     [rax+20h], rbx
0x1802f7ad7  mov     [rax+18h], r8
0x1802f7adb  mov     [rax+10h], rdx
0x1802f7adf  mov     [rax+8], rcx
0x1802f7ae3  push    rdi
0x1802f7ae4  sub     rsp, 40h
0x1802f7ae8  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802f7aee  test    rax, rax
0x1802f7af1  jnz     short loc_1802F7B04
0x1802f7af3  call    cs:__imp_?Register@TouchHyperLink@DirectUI@@SAJXZ; DirectUI::TouchHyperLink::Register(void)
0x1802f7af9  mov     ebx, eax
0x1802f7afb  test    eax, eax
0x1802f7afd  jns     short loc_1802F7B1B
0x1802f7aff  jmp     loc_1802F7BE2
0x1802f7b04  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802f7b0a  mov     rdx, rax
0x1802f7b0d  mov     rcx, [rax]
0x1802f7b10  mov     rax, [rcx]
0x1802f7b13  mov     rcx, rdx
0x1802f7b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f7b1b  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x1802f7b21  mov     rdx, rax
0x1802f7b24  lea     rcx, [rsp+48h+arg_0]
0x1802f7b29  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x1802f7b2f  mov     [rsp+48h+arg_8], 0
0x1802f7b38  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802f7b3e  lea     rcx, aFindmoreappsli; "FindMoreAppsLink"
0x1802f7b45  mov     [rsp+48h+var_18], 0
0x1802f7b4a  mov     [rsp+48h+var_20], rcx
0x1802f7b4f  mov     r9, rax
0x1802f7b52  lea     rcx, __ImageBase
0x1802f7b59  xor     r8d, r8d
0x1802f7b5c  mov     [rsp+48h+var_28], rcx
0x1802f7b61  xor     edx, edx
0x1802f7b63  lea     rcx, [rsp+48h+arg_8]
0x1802f7b68  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x1802f7b6e  test    al, al
0x1802f7b70  jnz     short loc_1802F7BC9
0x1802f7b72  lea     rax, [rsp+48h+arg_10]
0x1802f7b77  mov     cs:?s_pClassInfo@FindMoreAppsLink@@0PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * FindMoreAppsLink::s_pClassInfo
0x1802f7b82  mov     [rsp+48h+var_20], rax
0x1802f7b87  mov     [rsp+48h+arg_10], 0
0x1802f7b90  call    ?Create@?$ClassInfo@VFindMoreAppsLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VFindMoreAppsLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<FindMoreAppsLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<FindMoreAppsLink>> * *)
0x1802f7b95  mov     ebx, eax
0x1802f7b97  test    eax, eax
0x1802f7b99  js      short loc_1802F7BD7
0x1802f7b9b  mov     rdi, [rsp+48h+arg_10]
0x1802f7ba0  mov     rcx, rdi
0x1802f7ba3  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x1802f7ba9  mov     ebx, eax
0x1802f7bab  test    eax, eax
0x1802f7bad  js      short loc_1802F7BB8
0x1802f7baf  mov     cs:?s_pClassInfo@FindMoreAppsLink@@0PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * FindMoreAppsLink::s_pClassInfo
0x1802f7bb6  jmp     short loc_1802F7BD7
0x1802f7bb8  mov     rax, [rdi]
0x1802f7bbb  mov     rcx, rdi
0x1802f7bbe  mov     rax, [rax+58h]
0x1802f7bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f7bc7  jmp     short loc_1802F7BD7
0x1802f7bc9  mov     rax, [rsp+48h+arg_8]
0x1802f7bce  xor     ebx, ebx
0x1802f7bd0  mov     cs:?s_pClassInfo@FindMoreAppsLink@@0PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * FindMoreAppsLink::s_pClassInfo
0x1802f7bd7  lea     rcx, [rsp+48h+arg_0]
0x1802f7bdc  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x1802f7be2  mov     eax, ebx
0x1802f7be4  mov     rbx, [rsp+48h+arg_18]
0x1802f7be9  add     rsp, 40h
0x1802f7bed  pop     rdi
0x1802f7bee  retn
```
