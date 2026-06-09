# ClipboardApartmentState::add_ContentChanged(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180071640`
- end: `0x1800717dd`
- name: `?add_ContentChanged@ClipboardApartmentState@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180048954`
- `0x18006a0a8`
- `0x180071640`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071738`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071738`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071711`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071711`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800716c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800716c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::add_ContentChanged(RTL_SRWLOCK *a1, __int64 a2, _QWORD *a3)
{
  PVOID Ptr; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  HRESULT Instance; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Ptr = a1[22].Ptr;
  if ( !Ptr )
  {
    *a3 = 0;
    if ( a1[21].Ptr
      || (Instance = CoCreateInstance(
                       &GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac,
                       0,
                       1u,
                       &GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1,
                       &a1[21].Ptr),
          v7 = Instance,
          Instance >= 0) )
    {
      if ( a1[9].Ptr )
      {
        AcquireSRWLockExclusive(a1 + 10);
        v12 = a1[9].Ptr;
        v13 = v12 ? (__int64)(v12[3] - v12[2]) >> 3 : 0LL;
        if ( a1 != (RTL_SRWLOCK *)-80LL )
          ReleaseSRWLockExclusive(a1 + 10);
        if ( v13 )
          goto LABEL_17;
      }
      v14 = (*(__int64 (__fastcall **)(PVOID, unsigned __int64))(*(_QWORD *)a1[21].Ptr + 24LL))(
              a1[21].Ptr,
              (unsigned __int64)&a1[3] & -(__int64)(a1 != 0));
      v7 = v14;
      if ( v14 >= 0 )
      {
LABEL_17:
        v7 = Windows::Internal::GitEventSourceSupportsAgile<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
               &a1[9],
               a2,
               a3);
        if ( v7 >= 0 )
          return 0;
        v11 = 1448;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5EC,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v14,
          ppv);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5DD,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v7,
          ppva);
        v11 = 1446;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v11 = 1445;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    v8 = 1346;
    goto LABEL_4;
  }
  v7 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
  if ( v7 < 0 )
  {
    v8 = 1342;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    return (unsigned int)v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180071640  push    rbx
0x180071642  push    rbp
0x180071643  push    rsi
0x180071644  push    rdi
0x180071645  push    r12
0x180071647  push    r14
0x180071649  push    r15
0x18007164b  sub     rsp, 30h
0x18007164f  mov     r15, r8
0x180071652  mov     r12, rdx
0x180071655  mov     rdi, rcx
0x180071658  mov     rcx, [rcx+0B0h]
0x18007165f  test    rcx, rcx
0x180071662  jz      short loc_18007169A
0x180071664  mov     rax, [rcx]
0x180071667  mov     rax, [rax+8]
0x18007166b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071670  mov     ebx, eax
0x180071672  test    eax, eax
0x180071674  jns     loc_1800717CC
0x18007167a  mov     edx, 53Eh; void *
0x18007167f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071686  mov     r9d, ebx; char *
0x180071689  mov     rcx, [rsp+68h]; this
0x18007168e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071693  mov     eax, ebx
0x180071695  jmp     loc_1800717CE
0x18007169a  xor     eax, eax
0x18007169c  mov     [r8], rax
0x18007169f  lea     r14, [rdi+0A8h]
0x1800716a6  cmp     [r14], rax
0x1800716a9  jnz     short loc_1800716F3
0x1800716ab  mov     qword ptr [rsp+68h+ppv], r14; int
0x1800716b0  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x1800716b7  xor     edx, edx; pUnkOuter
0x1800716b9  lea     r8d, [rax+1]; dwClsContext
0x1800716bd  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x1800716c4  call    cs:__imp_CoCreateInstance
0x1800716ca  mov     ebx, eax
0x1800716cc  test    eax, eax
0x1800716ce  jns     short loc_1800716F3
0x1800716d0  mov     rcx, [rsp+68h]; this
0x1800716d5  mov     r9d, eax; char *
0x1800716d8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800716df  mov     edx, 5CEh; void *
0x1800716e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800716e9  mov     edx, 5A5h
0x1800716ee  jmp     loc_1800717AE
0x1800716f3  mov     rax, rdi
0x1800716f6  lea     rcx, [rdi+18h]
0x1800716fa  neg     rax
0x1800716fd  sbb     rbp, rbp
0x180071700  and     rbp, rcx
0x180071703  cmp     qword ptr [rdi+48h], 0
0x180071708  jz      short loc_180071743
0x18007170a  lea     rsi, [rdi+50h]
0x18007170e  mov     rcx, rsi; SRWLock
0x180071711  call    cs:__imp_AcquireSRWLockExclusive
0x180071717  mov     rax, [rdi+48h]
0x18007171b  test    rax, rax
0x18007171e  jnz     short loc_180071724
0x180071720  xor     ebx, ebx
0x180071722  jmp     short loc_180071730
0x180071724  mov     rbx, [rax+18h]
0x180071728  sub     rbx, [rax+10h]
0x18007172c  sar     rbx, 3
0x180071730  test    rsi, rsi
0x180071733  jz      short loc_18007173E
0x180071735  mov     rcx, rsi; SRWLock
0x180071738  call    cs:__imp_ReleaseSRWLockExclusive
0x18007173e  test    rbx, rbx
0x180071741  jnz     short loc_180071794
0x180071743  mov     rcx, [r14]
0x180071746  mov     rax, [rcx]
0x180071749  mov     rdx, rbp
0x18007174c  mov     rax, [rax+18h]
0x180071750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071755  mov     ebx, eax
0x180071757  test    eax, eax
0x180071759  jns     short loc_180071794
0x18007175b  mov     rcx, [rsp+68h]; this
0x180071760  mov     r9d, eax; char *
0x180071763  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18007176a  mov     edx, 5ECh; void *
0x18007176f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071774  mov     rcx, [rsp+68h]; this
0x180071779  mov     r9d, ebx; char *
0x18007177c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071783  mov     edx, 5DDh; void *
0x180071788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007178d  mov     edx, 5A6h
0x180071792  jmp     short loc_1800717AE
0x180071794  mov     r8, r15
0x180071797  mov     rdx, r12
0x18007179a  lea     rcx, [rdi+48h]
0x18007179e  call    ?Add@?$GitEventSourceSupportsAgile@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@Internal@Windows@@QEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@3@PEAUEventRegistrationToken@@@Z; Windows::Internal::GitEventSourceSupportsAgile<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)
0x1800717a3  mov     ebx, eax
0x1800717a5  test    eax, eax
0x1800717a7  jns     short loc_1800717CC
0x1800717a9  mov     edx, 5A8h; void *
0x1800717ae  mov     rcx, [rsp+68h]; this
0x1800717b3  mov     r9d, ebx; char *
0x1800717b6  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800717bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800717c2  mov     edx, 542h
0x1800717c7  jmp     loc_18007167F
0x1800717cc  xor     eax, eax
0x1800717ce  add     rsp, 30h
0x1800717d2  pop     r15
0x1800717d4  pop     r14
0x1800717d6  pop     r12
0x1800717d8  pop     rdi
0x1800717d9  pop     rsi
0x1800717da  pop     rbp
0x1800717db  pop     rbx
0x1800717dc  retn
```
