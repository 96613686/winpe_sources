# DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Register(ushort const *,DirectUI::PropertyInfo const * const *,uint)

- ea: `0x180018a00`
- end: `0x180018b91`
- name: `?Register@?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@SAJPEBGPEBQEBUPropertyInfo@2@I@Z`
- size: `401`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a20`
- `0x180013a04`
- `0x180018b98`
- `0x18001bccc`

## callees

- `0x180018a00`
- `0x180018d20`
- `0x18001e010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180018b2c`
- `KERNEL32!HeapFree` at `0x180018b2c`
- `KERNEL32!GetProcessHeap` at `0x180018aa3`
- `KERNEL32!GetProcessHeap` at `0x180018b1e`
- `KERNEL32!GetProcessHeap` at `0x180018aa3`
- `KERNEL32!GetProcessHeap` at `0x180018b1e`
- `KERNEL32!EnterCriticalSection` at `0x180018a4d`
- `KERNEL32!EnterCriticalSection` at `0x180018a4d`
- `KERNEL32!HeapAlloc` at `0x180018ab5`
- `KERNEL32!HeapAlloc` at `0x180018ab5`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180018aca`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180018aca`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180018af7`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180018af7`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x180018b39`
- `DUI70!?Register@ClassInfoBase@DirectUI@@QEAAJXZ` at `0x180018b39`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x180018a8a`
- `DUI70!?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z` at `0x180018a8a`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x180018b79`
- `DUI70!??1CritSecLock@DirectUI@@QEAA@XZ` at `0x180018b79`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x180018a3f`
- `DUI70!?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ` at `0x180018a3f`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Register(
        struct _RTL_CRITICAL_SECTION *a1,
        struct DirectUI::IClassInfo *a2)
{
  int v2; // ebx
  HANDLE ProcessHeap; // rax
  DirectUI::ClassInfoBase *v4; // rax
  DirectUI::ClassInfoBase *v5; // rsi
  DirectUI::ClassInfoBase *v6; // rdi
  HANDLE v7; // rax
  LPCRITICAL_SECTION FactoryLock; // [rsp+50h] [rbp+8h] BYREF
  struct DirectUI::IClassInfo *v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = a2;
  FactoryLock = a1;
  if ( CElementWithIUnknown::Class )
  {
    (**(void (__fastcall ***)(struct DirectUI::IClassInfo *))CElementWithIUnknown::Class)(CElementWithIUnknown::Class);
  }
  else
  {
    v2 = CElementWithIUnknown::Register();
    if ( v2 < 0 )
      return (unsigned int)v2;
  }
  FactoryLock = (LPCRITICAL_SECTION)DirectUI::Element::GetFactoryLock();
  EnterCriticalSection(FactoryLock);
  v10 = 0;
  if ( DirectUI::ClassInfoBase::ClassExist(
         &v10,
         0,
         0,
         CElementWithIUnknown::Class,
         (HINSTANCE)&_ImageBase,
         L"CElementWithSite",
         0) )
  {
    v2 = 0;
    CElementWithSite::Class = v10;
  }
  else
  {
    CElementWithSite::Class = 0;
    ProcessHeap = GetProcessHeap();
    v4 = (DirectUI::ClassInfoBase *)HeapAlloc(ProcessHeap, 8u, 0x10u);
    v5 = v4;
    if ( v4 )
    {
      DirectUI::ClassInfoBase::ClassInfoBase(v4);
      *(_QWORD *)v5 = &DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::`vftable';
      v2 = DirectUI::ClassInfoBase::Initialize(v5, (HINSTANCE)&_ImageBase, L"CElementWithSite", 0, 0, 0);
      if ( v2 < 0 )
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
      if ( v2 >= 0 )
      {
        v2 = DirectUI::ClassInfoBase::Register(v6);
        if ( v2 < 0 )
          (*(void (__fastcall **)(DirectUI::ClassInfoBase *))(*(_QWORD *)v6 + 88LL))(v6);
        else
          CElementWithSite::Class = v6;
      }
    }
    else
    {
      v2 = -2147024882;
    }
  }
  DirectUI::CritSecLock::~CritSecLock((DirectUI::CritSecLock *)&FactoryLock);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018a00  mov     rax, rsp
0x180018a03  mov     [rax+18h], rbx
0x180018a07  mov     [rax+20h], rsi
0x180018a0b  mov     [rax+10h], rdx
0x180018a0f  mov     [rax+8], rcx
0x180018a13  push    rdi
0x180018a14  sub     rsp, 40h
0x180018a18  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180018a1f  test    rcx, rcx
0x180018a22  jnz     short loc_180018A34
0x180018a24  call    ?Register@CElementWithIUnknown@@SAJXZ; CElementWithIUnknown::Register(void)
0x180018a29  mov     ebx, eax
0x180018a2b  test    eax, eax
0x180018a2d  jns     short loc_180018A3F
0x180018a2f  jmp     loc_180018B7F
0x180018a34  mov     rax, [rcx]
0x180018a37  mov     rax, [rax]
0x180018a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a3f  call    cs:__imp_?GetFactoryLock@Element@DirectUI@@SAPEAU_RTL_CRITICAL_SECTION@@XZ; DirectUI::Element::GetFactoryLock(void)
0x180018a45  mov     rcx, rax; lpCriticalSection
0x180018a48  mov     [rsp+48h+arg_0], rax
0x180018a4d  call    cs:__imp_EnterCriticalSection
0x180018a53  mov     r9, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180018a5a  lea     rbx, aCelementwithsi; "CElementWithSite"
0x180018a61  mov     [rsp+48h+var_18], 0
0x180018a66  lea     rdi, __ImageBase
0x180018a6d  mov     [rsp+48h+var_20], rbx
0x180018a72  lea     rcx, [rsp+48h+arg_8]
0x180018a77  xor     r8d, r8d
0x180018a7a  mov     [rsp+48h+var_28], rdi
0x180018a7f  xor     edx, edx
0x180018a81  mov     [rsp+48h+arg_8], 0
0x180018a8a  call    cs:__imp_?ClassExist@ClassInfoBase@DirectUI@@SA_NPEAPEAUIClassInfo@2@PEBQEBUPropertyInfo@2@IPEAU32@PEAUHINSTANCE__@@PEBG_N@Z; DirectUI::ClassInfoBase::ClassExist(DirectUI::IClassInfo * *,DirectUI::PropertyInfo const * const *,uint,DirectUI::IClassInfo *,HINSTANCE__ *,ushort const *,bool)
0x180018a90  test    al, al
0x180018a92  jnz     loc_180018B66
0x180018a98  mov     cs:?Class@CElementWithSite@@2PEAUIClassInfo@DirectUI@@EA, 0; DirectUI::IClassInfo * CElementWithSite::Class
0x180018aa3  call    cs:__imp_GetProcessHeap
0x180018aa9  mov     edx, 8; dwFlags
0x180018aae  mov     rcx, rax; hHeap
0x180018ab1  lea     r8d, [rdx+8]; dwBytes
0x180018ab5  call    cs:__imp_HeapAlloc
0x180018abb  mov     rsi, rax
0x180018abe  test    rax, rax
0x180018ac1  jz      loc_180018B5F
0x180018ac7  mov     rcx, rax
0x180018aca  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180018ad0  lea     rax, ??_7?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::`vftable'
0x180018ad7  mov     dword ptr [rsp+48h+var_20], 0
0x180018adf  xor     r9d, r9d
0x180018ae2  mov     [rsi], rax
0x180018ae5  mov     r8, rbx
0x180018ae8  mov     [rsp+48h+var_28], 0
0x180018af1  mov     rdx, rdi
0x180018af4  mov     rcx, rsi
0x180018af7  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180018afd  mov     ebx, eax
0x180018aff  test    eax, eax
0x180018b01  js      short loc_180018B08
0x180018b03  mov     rdi, rsi
0x180018b06  jmp     short loc_180018B32
0x180018b08  mov     rax, [rsi]
0x180018b0b  xor     edx, edx
0x180018b0d  mov     rcx, rsi
0x180018b10  xor     edi, edi
0x180018b12  mov     rax, [rax+90h]
0x180018b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b1e  call    cs:__imp_GetProcessHeap
0x180018b24  mov     r8, rsi; lpMem
0x180018b27  xor     edx, edx; dwFlags
0x180018b29  mov     rcx, rax; hHeap
0x180018b2c  call    cs:__imp_HeapFree
0x180018b32  test    ebx, ebx
0x180018b34  js      short loc_180018B74
0x180018b36  mov     rcx, rdi
0x180018b39  call    cs:__imp_?Register@ClassInfoBase@DirectUI@@QEAAJXZ; DirectUI::ClassInfoBase::Register(void)
0x180018b3f  mov     ebx, eax
0x180018b41  test    eax, eax
0x180018b43  js      short loc_180018B4E
0x180018b45  mov     cs:?Class@CElementWithSite@@2PEAUIClassInfo@DirectUI@@EA, rdi; DirectUI::IClassInfo * CElementWithSite::Class
0x180018b4c  jmp     short loc_180018B74
0x180018b4e  mov     rax, [rdi]
0x180018b51  mov     rcx, rdi
0x180018b54  mov     rax, [rax+58h]
0x180018b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b5d  jmp     short loc_180018B74
0x180018b5f  mov     ebx, 8007000Eh
0x180018b64  jmp     short loc_180018B74
0x180018b66  mov     rax, [rsp+48h+arg_8]
0x180018b6b  xor     ebx, ebx
0x180018b6d  mov     cs:?Class@CElementWithSite@@2PEAUIClassInfo@DirectUI@@EA, rax; DirectUI::IClassInfo * CElementWithSite::Class
0x180018b74  lea     rcx, [rsp+48h+arg_0]
0x180018b79  call    cs:__imp_??1CritSecLock@DirectUI@@QEAA@XZ; DirectUI::CritSecLock::~CritSecLock(void)
0x180018b7f  mov     rsi, [rsp+48h+arg_18]
0x180018b84  mov     eax, ebx
0x180018b86  mov     rbx, [rsp+48h+arg_10]
0x180018b8b  add     rsp, 40h
0x180018b8f  pop     rdi
0x180018b90  retn
```
