# ComboBoxEx::Register(void)

- ea: `0x180010acc`
- end: `0x180010c15`
- name: `?Register@ComboBoxEx@@SAJXZ`
- size: `329`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180039470`

## callees

- `0x180010410`
- `0x180010acc`
- `0x180057010`

## import_xrefs

- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x180010b1b`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x180010b1b`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x180010b7b`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x180010b7b`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x180010bbc`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x180010bbc`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x180010bfb`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x180010bfb`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180010b2f`
- `DUI70!??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180010b2f`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010ad6`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010afe`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010b45`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010ad6`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010afe`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180010b45`
- `DUI70!?Register@Combobox@DirectUI@@SAJXZ` at `0x180010ae7`
- `DUI70!?Register@Combobox@DirectUI@@SAJXZ` at `0x180010ae7`

## string_xrefs

- `0x180010b56`: `ComboBoxEx`

## pseudocode

```c
__int64 ComboBoxEx::Register(void)
{
  int v0; // ebx
  void (__fastcall ***ClassInfoPtr)(_QWORD); // rax
  struct _RTL_CRITICAL_SECTION *FactoryLock; // rax
  struct DirectUI::IClassInfo *v3; // rax
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  struct DirectUI::IClassInfo *v8; // rdi
  int v10; // [rsp+20h] [rbp-28h]
  DirectUI::ClassInfoBase *v11; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::IClassInfo *v12; // [rsp+58h] [rbp+10h] BYREF
  char v13; // [rsp+60h] [rbp+18h] BYREF

  if ( DirectUI::Combobox::GetClassInfoPtr() )
  {
    ClassInfoPtr = (void (__fastcall ***)(_QWORD))DirectUI::Combobox::GetClassInfoPtr();
    (**ClassInfoPtr)(ClassInfoPtr);
  }
  else
  {
    v0 = DirectUI::Combobox::Register();
    if ( v0 < 0 )
      return (unsigned int)v0;
  }
  FactoryLock = (struct _RTL_CRITICAL_SECTION *)DirectUI::Element::GetFactoryLock();
  DirectUI::CritSecLock::CritSecLock((DirectUI::CritSecLock *)&v13, FactoryLock);
  v12 = 0;
  v3 = (struct DirectUI::IClassInfo *)DirectUI::Combobox::GetClassInfoPtr();
  if ( DirectUI::ClassInfoBase::ClassExist(&v12, 0, 0, v3, &_ImageBase, L"ComboBoxEx", 0) )
  {
    ComboBoxEx::Class = v12;
    v0 = 0;
  }
  else
  {
    ComboBoxEx::Class = 0;
    v11 = 0;
    v0 = DirectUI::ClassInfo<ComboBoxEx,DirectUI::Combobox,DirectUI::StandardCreator<ComboBoxEx>>::Create(
           v5,
           v4,
           v6,
           v7,
           v10,
           (__int64)&v11);
    if ( v0 >= 0 )
    {
      v8 = v11;
      v0 = DirectUI::ClassInfoBase::Register(v11);
      if ( v0 < 0 )
        (*(void (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)v8 + 88LL))(v8);
      else
        ComboBoxEx::Class = v8;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&v13);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180010acc  mov     [rsp+arg_18], rbx
0x180010ad1  push    rdi
0x180010ad2  sub     rsp, 40h
0x180010ad6  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x180010add  nop     dword ptr [rax+rax+00h]
0x180010ae2  test    rax, rax
0x180010ae5  jnz     short loc_180010AFE
0x180010ae7  call    cs:__imp_?Register@Combobox@DirectUI@@SAJXZ; DirectUI::Combobox::Register(void)
0x180010aee  nop     dword ptr [rax+rax+00h]
0x180010af3  mov     ebx, eax
0x180010af5  test    eax, eax
0x180010af7  jns     short loc_180010B1B
0x180010af9  jmp     loc_180010C07
0x180010afe  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x180010b05  nop     dword ptr [rax+rax+00h]
0x180010b0a  mov     rdx, rax
0x180010b0d  mov     rcx, [rax]
0x180010b10  mov     rax, [rcx]
0x180010b13  mov     rcx, rdx
0x180010b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b1b  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x180010b22  nop     dword ptr [rax+rax+00h]
0x180010b27  mov     rdx, rax
0x180010b2a  lea     rcx, [rsp+48h+arg_10]
0x180010b2f  call    cs:__imp_??0CritSecLock@DirectUI@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; DirectUI::CritSecLock::CritSecLock(_RTL_CRITICAL_SECTION *)
0x180010b36  nop     dword ptr [rax+rax+00h]
0x180010b3b  nop
0x180010b3c  mov     [rsp+48h+arg_8], 0
0x180010b45  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x180010b4c  nop     dword ptr [rax+rax+00h]
0x180010b51  mov     [rsp+48h+var_18], 0
0x180010b56  lea     rcx, aComboboxex; "ComboBoxEx"
0x180010b5d  mov     [rsp+48h+var_20], rcx
0x180010b62  lea     rcx, __ImageBase
0x180010b69  mov     [rsp+48h+var_28], rcx
0x180010b6e  mov     r9, rax
0x180010b71  xor     r8d, r8d
0x180010b74  xor     edx, edx
0x180010b76  lea     rcx, [rsp+48h+arg_8]
0x180010b7b  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x180010b82  nop     dword ptr [rax+rax+00h]
0x180010b87  test    al, al
0x180010b89  jnz     short loc_180010BE8
0x180010b8b  mov     cs:?Class@ComboBoxEx@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * ComboBoxEx::Class
0x180010b96  mov     [rsp+48h+arg_0], 0
0x180010b9f  lea     rax, [rsp+48h+arg_0]
0x180010ba4  mov     [rsp+48h+var_20], rax
0x180010ba9  call    ?Create@?$ClassInfo@VComboBoxEx@@VCombobox@DirectUI@@V?$StandardCreator@VComboBoxEx@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z; DirectUI::ClassInfo<ComboBoxEx,DirectUI::Combobox,DirectUI::StandardCreator<ComboBoxEx>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<ComboBoxEx,DirectUI::Combobox,DirectUI::StandardCreator<ComboBoxEx>> * *)
0x180010bae  mov     ebx, eax
0x180010bb0  test    eax, eax
0x180010bb2  js      short loc_180010BF6
0x180010bb4  mov     rdi, [rsp+48h+arg_0]
0x180010bb9  mov     rcx, rdi
0x180010bbc  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x180010bc3  nop     dword ptr [rax+rax+00h]
0x180010bc8  mov     ebx, eax
0x180010bca  test    eax, eax
0x180010bcc  js      short loc_180010BD7
0x180010bce  mov     cs:?Class@ComboBoxEx@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * ComboBoxEx::Class
0x180010bd5  jmp     short loc_180010BF6
0x180010bd7  mov     rax, [rdi]
0x180010bda  mov     rcx, rdi
0x180010bdd  mov     rax, [rax+58h]
0x180010be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be6  jmp     short loc_180010BF6
0x180010be8  mov     rax, [rsp+48h+arg_8]
0x180010bed  mov     cs:?Class@ComboBoxEx@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * ComboBoxEx::Class
0x180010bf4  xor     ebx, ebx
0x180010bf6  lea     rcx, [rsp+48h+arg_10]
0x180010bfb  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x180010c02  nop     dword ptr [rax+rax+00h]
0x180010c07  mov     eax, ebx
0x180010c09  mov     rbx, [rsp+48h+arg_18]
0x180010c0e  add     rsp, 40h
0x180010c12  pop     rdi
0x180010c13  retn
```
