# CElementWithIUnknown::Register(void)

- ea: `0x180018d20`
- end: `0x180018eb6`
- name: `?Register@CElementWithIUnknown@@SAJXZ`
- size: `406`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a20`
- `0x180013a04`
- `0x180018a00`
- `0x180018b98`
- `0x18001bccc`

## callees

- `0x180018d20`
- `0x18001e010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180018e51`
- `KERNEL32!HeapFree` at `0x180018e51`
- `KERNEL32!GetProcessHeap` at `0x180018dc8`
- `KERNEL32!GetProcessHeap` at `0x180018e43`
- `KERNEL32!GetProcessHeap` at `0x180018dc8`
- `KERNEL32!GetProcessHeap` at `0x180018e43`
- `KERNEL32!EnterCriticalSection` at `0x180018d70`
- `KERNEL32!EnterCriticalSection` at `0x180018d70`
- `KERNEL32!HeapAlloc` at `0x180018dda`
- `KERNEL32!HeapAlloc` at `0x180018dda`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180018def`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180018def`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180018e1c`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180018e1c`
- `DUI70!?Register@Element@DirectUI@@SAJXZ` at `0x180018d3a`
- `DUI70!?Register@Element@DirectUI@@SAJXZ` at `0x180018d3a`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x180018e5e`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x180018e5e`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x180018daf`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x180018daf`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x180018e9e`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x180018e9e`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x180018d62`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x180018d62`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180018d2f`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180018d4b`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180018d7f`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180018d2f`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180018d4b`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180018d7f`

## pseudocode

```c
__int64 CElementWithIUnknown::Register(void)
{
  int v0; // ebx
  void (__fastcall ***ClassInfoPtr)(_QWORD); // rax
  struct DirectUI::IClassInfo *v2; // rax
  HANDLE ProcessHeap; // rax
  DirectUI::ClassInfoBase *v4; // rax
  DirectUI::ClassInfoBase *v5; // rsi
  DirectUI::ClassInfoBase *v6; // rdi
  HANDLE v7; // rax
  struct DirectUI::IClassInfo *v9; // [rsp+50h] [rbp+8h] BYREF
  LPCRITICAL_SECTION FactoryLock; // [rsp+58h] [rbp+10h] BYREF

  if ( DirectUI::Element::GetClassInfoPtr() )
  {
    ClassInfoPtr = (void (__fastcall ***)(_QWORD))DirectUI::Element::GetClassInfoPtr();
    (**ClassInfoPtr)(ClassInfoPtr);
  }
  else
  {
    v0 = DirectUI::Element::Register();
    if ( v0 < 0 )
      return (unsigned int)v0;
  }
  FactoryLock = (LPCRITICAL_SECTION)DirectUI::Element::GetFactoryLock();
  EnterCriticalSection(FactoryLock);
  v9 = 0;
  v2 = (struct DirectUI::IClassInfo *)DirectUI::Element::GetClassInfoPtr();
  if ( DirectUI::ClassInfoBase::ClassExist(&v9, 0, 0, v2, (HINSTANCE)&_ImageBase, L"CElementWithIUnknown", 0) )
  {
    v0 = 0;
    CElementWithIUnknown::Class = v9;
  }
  else
  {
    CElementWithIUnknown::Class = 0;
    ProcessHeap = GetProcessHeap();
    v4 = (DirectUI::ClassInfoBase *)HeapAlloc(ProcessHeap, 8u, 0x10u);
    v5 = v4;
    if ( v4 )
    {
      DirectUI::ClassInfoBase::ClassInfoBase(v4);
      *(_QWORD *)v5 = &DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::`vftable';
      v0 = DirectUI::ClassInfoBase::Initialize(v5, (HINSTANCE)&_ImageBase, L"CElementWithIUnknown", 0, 0, 0);
      if ( v0 < 0 )
      {
        v6 = 0;
        (*(void (__fastcall **)(DirectUI::ClassInfoBase *, _QWORD))(*(_QWORD *)v5 + 144LL))(v5, 0);
        v7 = GetProcessHeap();
        HeapFree(v7, 0, v5);
      }
      else
      {
        v6 = v5;
      }
      if ( v0 >= 0 )
      {
        v0 = DirectUI::ClassInfoBase::Register(v6);
        if ( v0 < 0 )
          (*(void (__fastcall **)(DirectUI::ClassInfoBase *))(*(_QWORD *)v6 + 88LL))(v6);
        else
          CElementWithIUnknown::Class = v6;
      }
    }
    else
    {
      v0 = -2147024882;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&FactoryLock);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180018d20  mov     [rsp+arg_10], rbx
0x180018d25  mov     [rsp+arg_18], rsi
0x180018d2a  push    rdi
0x180018d2b  sub     rsp, 40h
0x180018d2f  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x180018d35  test    rax, rax
0x180018d38  jnz     short loc_180018D4B
0x180018d3a  call    cs:__imp_?Register@Element@DirectUI@@SAJXZ; DirectUI::Element::Register(void)
0x180018d40  mov     ebx, eax
0x180018d42  test    eax, eax
0x180018d44  jns     short loc_180018D62
0x180018d46  jmp     loc_180018EA4
0x180018d4b  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x180018d51  mov     rdx, rax
0x180018d54  mov     rcx, [rax]
0x180018d57  mov     rax, [rcx]
0x180018d5a  mov     rcx, rdx
0x180018d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d62  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x180018d68  mov     rcx, rax; lpCriticalSection
0x180018d6b  mov     [rsp+48h+arg_8], rax
0x180018d70  call    cs:__imp_EnterCriticalSection
0x180018d76  mov     [rsp+48h+arg_0], 0
0x180018d7f  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x180018d85  mov     [rsp+48h+var_18], 0
0x180018d8a  lea     rbx, aCelementwithiu; "CElementWithIUnknown"
0x180018d91  lea     rdi, __ImageBase
0x180018d98  mov     [rsp+48h+var_20], rbx
0x180018d9d  mov     r9, rax
0x180018da0  mov     [rsp+48h+var_28], rdi
0x180018da5  xor     r8d, r8d
0x180018da8  lea     rcx, [rsp+48h+arg_0]
0x180018dad  xor     edx, edx
0x180018daf  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x180018db5  test    al, al
0x180018db7  jnz     loc_180018E8B
0x180018dbd  mov     cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180018dc8  call    cs:__imp_GetProcessHeap
0x180018dce  mov     edx, 8; dwFlags
0x180018dd3  mov     rcx, rax; hHeap
0x180018dd6  lea     r8d, [rdx+8]; dwBytes
0x180018dda  call    cs:__imp_HeapAlloc
0x180018de0  mov     rsi, rax
0x180018de3  test    rax, rax
0x180018de6  jz      loc_180018E84
0x180018dec  mov     rcx, rax
0x180018def  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180018df5  lea     rax, ??_7?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::`vftable'
0x180018dfc  mov     dword ptr [rsp+48h+var_20], 0
0x180018e04  xor     r9d, r9d
0x180018e07  mov     [rsi], rax
0x180018e0a  mov     r8, rbx
0x180018e0d  mov     [rsp+48h+var_28], 0
0x180018e16  mov     rdx, rdi
0x180018e19  mov     rcx, rsi
0x180018e1c  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180018e22  mov     ebx, eax
0x180018e24  test    eax, eax
0x180018e26  js      short loc_180018E2D
0x180018e28  mov     rdi, rsi
0x180018e2b  jmp     short loc_180018E57
0x180018e2d  mov     rax, [rsi]
0x180018e30  xor     edx, edx
0x180018e32  mov     rcx, rsi
0x180018e35  xor     edi, edi
0x180018e37  mov     rax, [rax+90h]
0x180018e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e43  call    cs:__imp_GetProcessHeap
0x180018e49  mov     r8, rsi; lpMem
0x180018e4c  xor     edx, edx; dwFlags
0x180018e4e  mov     rcx, rax; hHeap
0x180018e51  call    cs:__imp_HeapFree
0x180018e57  test    ebx, ebx
0x180018e59  js      short loc_180018E99
0x180018e5b  mov     rcx, rdi
0x180018e5e  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x180018e64  mov     ebx, eax
0x180018e66  test    eax, eax
0x180018e68  js      short loc_180018E73
0x180018e6a  mov     cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180018e71  jmp     short loc_180018E99
0x180018e73  mov     rax, [rdi]
0x180018e76  mov     rcx, rdi
0x180018e79  mov     rax, [rax+58h]
0x180018e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e82  jmp     short loc_180018E99
0x180018e84  mov     ebx, 8007000Eh
0x180018e89  jmp     short loc_180018E99
0x180018e8b  mov     rax, [rsp+48h+arg_0]
0x180018e90  xor     ebx, ebx
0x180018e92  mov     cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180018e99  lea     rcx, [rsp+48h+arg_8]
0x180018e9e  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x180018ea4  mov     rsi, [rsp+48h+arg_18]
0x180018ea9  mov     eax, ebx
0x180018eab  mov     rbx, [rsp+48h+arg_10]
0x180018eb0  add     rsp, 40h
0x180018eb4  pop     rdi
0x180018eb5  retn
```
