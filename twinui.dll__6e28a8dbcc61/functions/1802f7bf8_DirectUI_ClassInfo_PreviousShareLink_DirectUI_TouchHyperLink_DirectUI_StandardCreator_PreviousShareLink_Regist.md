# DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)

- ea: `0x1802f7bf8`
- end: `0x1802f7d17`
- name: `?Register@?$ClassInfo@VPreviousShareLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VPreviousShareLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1802f8360`

## callees

- `0x1802f5d5c`
- `0x1802f7bf8`
- `0x1803a3010`

## import_xrefs

- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802f7c1b`
- `DUI70!?Register@TouchHyperLink@DirectUI@@SAJXZ` at `0x1802f7c1b`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7c10`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7c2c`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7c60`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7c10`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7c2c`
- `DUI70!?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1802f7c60`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802f7c51`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1802f7c51`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802f7c43`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x1802f7c43`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802f7d04`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x1802f7d04`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802f7c90`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x1802f7c90`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802f7ccb`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x1802f7ccb`

## string_xrefs

- `0x1802f7c66`: `PreviousShareLink`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Register(
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
  if ( DirectUI::ClassInfoBase::ClassExist(&v15, 0, 0, v6, (HINSTANCE)&_ImageBase, L"PreviousShareLink", 0) )
  {
    v3 = 0;
    PreviousShareLink::s_pClassInfo = v15;
  }
  else
  {
    PreviousShareLink::s_pClassInfo = 0;
    v16 = 0;
    v3 = DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Create(
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
        PreviousShareLink::s_pClassInfo = v11;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802f7bf8  mov     rax, rsp
0x1802f7bfb  mov     [rax+20h], rbx
0x1802f7bff  mov     [rax+18h], r8
0x1802f7c03  mov     [rax+10h], rdx
0x1802f7c07  mov     [rax+8], rcx
0x1802f7c0b  push    rdi
0x1802f7c0c  sub     rsp, 40h
0x1802f7c10  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802f7c16  test    rax, rax
0x1802f7c19  jnz     short loc_1802F7C2C
0x1802f7c1b  call    cs:__imp_?Register@TouchHyperLink@DirectUI@@SAJXZ; DirectUI::TouchHyperLink::Register(void)
0x1802f7c21  mov     ebx, eax
0x1802f7c23  test    eax, eax
0x1802f7c25  jns     short loc_1802F7C43
0x1802f7c27  jmp     loc_1802F7D0A
0x1802f7c2c  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802f7c32  mov     rdx, rax
0x1802f7c35  mov     rcx, [rax]
0x1802f7c38  mov     rax, [rcx]
0x1802f7c3b  mov     rcx, rdx
0x1802f7c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f7c43  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x1802f7c49  mov     rdx, rax
0x1802f7c4c  lea     rcx, [rsp+48h+arg_0]
0x1802f7c51  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x1802f7c57  mov     [rsp+48h+arg_8], 0
0x1802f7c60  call    cs:__imp_?GetClassInfoPtr@TouchHyperLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::TouchHyperLink::GetClassInfoPtr(void)
0x1802f7c66  lea     rcx, aPrevioussharel; "PreviousShareLink"
0x1802f7c6d  mov     [rsp+48h+var_18], 0
0x1802f7c72  mov     [rsp+48h+var_20], rcx
0x1802f7c77  mov     r9, rax
0x1802f7c7a  lea     rcx, __ImageBase
0x1802f7c81  xor     r8d, r8d
0x1802f7c84  mov     [rsp+48h+var_28], rcx
0x1802f7c89  xor     edx, edx
0x1802f7c8b  lea     rcx, [rsp+48h+arg_8]
0x1802f7c90  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x1802f7c96  test    al, al
0x1802f7c98  jnz     short loc_1802F7CF1
0x1802f7c9a  lea     rax, [rsp+48h+arg_10]
0x1802f7c9f  mov     cs:?s_pClassInfo@PreviousShareLink@@0PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * PreviousShareLink::s_pClassInfo
0x1802f7caa  mov     [rsp+48h+var_20], rax
0x1802f7caf  mov     [rsp+48h+arg_10], 0
0x1802f7cb8  call    ?Create@?$ClassInfo@VPreviousShareLink@@VTouchHyperLink@DirectUI@@V?$StandardCreator@VPreviousShareLink@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<PreviousShareLink,DirectUI::TouchHyperLink,DirectUI::StandardCreator<PreviousShareLink>> * *)
0x1802f7cbd  mov     ebx, eax
0x1802f7cbf  test    eax, eax
0x1802f7cc1  js      short loc_1802F7CFF
0x1802f7cc3  mov     rdi, [rsp+48h+arg_10]
0x1802f7cc8  mov     rcx, rdi
0x1802f7ccb  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x1802f7cd1  mov     ebx, eax
0x1802f7cd3  test    eax, eax
0x1802f7cd5  js      short loc_1802F7CE0
0x1802f7cd7  mov     cs:?s_pClassInfo@PreviousShareLink@@0PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * PreviousShareLink::s_pClassInfo
0x1802f7cde  jmp     short loc_1802F7CFF
0x1802f7ce0  mov     rax, [rdi]
0x1802f7ce3  mov     rcx, rdi
0x1802f7ce6  mov     rax, [rax+58h]
0x1802f7cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f7cef  jmp     short loc_1802F7CFF
0x1802f7cf1  mov     rax, [rsp+48h+arg_8]
0x1802f7cf6  xor     ebx, ebx
0x1802f7cf8  mov     cs:?s_pClassInfo@PreviousShareLink@@0PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * PreviousShareLink::s_pClassInfo
0x1802f7cff  lea     rcx, [rsp+48h+arg_0]
0x1802f7d04  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x1802f7d0a  mov     eax, ebx
0x1802f7d0c  mov     rbx, [rsp+48h+arg_18]
0x1802f7d11  add     rsp, 40h
0x1802f7d15  pop     rdi
0x1802f7d16  retn
```
