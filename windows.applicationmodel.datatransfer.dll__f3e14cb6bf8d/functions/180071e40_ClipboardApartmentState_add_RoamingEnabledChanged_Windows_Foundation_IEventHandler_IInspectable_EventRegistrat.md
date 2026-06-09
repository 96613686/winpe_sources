# ClipboardApartmentState::add_RoamingEnabledChanged(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180071e40`
- end: `0x180071fb3`
- name: `?add_RoamingEnabledChanged@ClipboardApartmentState@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180048954`
- `0x18006a0a8`
- `0x180071e40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071efd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071efd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071ed6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071ed6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071e83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071e83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::add_RoamingEnabledChanged(__int64 a1, __int64 a2, _QWORD *a3)
{
  RTL_SRWLOCK *v5; // rdi
  _QWORD *v6; // r14
  HRESULT Instance; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _QWORD *Ptr; // rax
  __int64 v11; // rbx
  int v12; // eax
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  int ppvb; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = (RTL_SRWLOCK *)(a1 - 16);
  *a3 = 0;
  v6 = (_QWORD *)(a1 - 16 + 168);
  if ( !*v6 )
  {
    Instance = CoCreateInstance(
                 &GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac,
                 0,
                 1u,
                 &GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1,
                 (LPVOID *)(a1 - 16 + 168));
    v8 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v9 = 1445;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v8,
        ppv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56F,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v8,
        ppvb);
      return v8;
    }
  }
  if ( !v5[15].Ptr )
    goto LABEL_19;
  AcquireSRWLockExclusive(v5 + 16);
  Ptr = v5[15].Ptr;
  v11 = Ptr ? (__int64)(Ptr[3] - Ptr[2]) >> 3 : 0LL;
  if ( v5 != (RTL_SRWLOCK *)-128LL )
    ReleaseSRWLockExclusive(v5 + 16);
  if ( !v11 )
  {
LABEL_19:
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v6 + 56LL))(
            *v6,
            (unsigned __int64)&v5[5] & -(__int64)(v5 != 0));
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FA,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)v12,
        ppv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DD,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v8,
        ppva);
      v9 = 1446;
      goto LABEL_15;
    }
  }
  v8 = Windows::Internal::GitEventSourceSupportsAgile<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
         &v5[15],
         a2,
         a3);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = 1448;
    goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x180071e40  push    rbx
0x180071e42  push    rbp
0x180071e43  push    rsi
0x180071e44  push    rdi
0x180071e45  push    r12
0x180071e47  push    r14
0x180071e49  push    r15
0x180071e4b  sub     rsp, 30h
0x180071e4f  mov     r15, r8
0x180071e52  mov     r12, rdx
0x180071e55  lea     rdi, [rcx-10h]
0x180071e59  xor     eax, eax
0x180071e5b  mov     [r8], rax
0x180071e5e  lea     r14, [rdi+0A8h]
0x180071e65  cmp     [r14], rax
0x180071e68  jnz     short loc_180071EB5
0x180071e6a  mov     qword ptr [rsp+68h+ppv], r14; int
0x180071e6f  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x180071e76  xor     edx, edx; pUnkOuter
0x180071e78  lea     r8d, [rax+1]; dwClsContext
0x180071e7c  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x180071e83  call    cs:__imp_CoCreateInstance
0x180071e89  mov     ebx, eax
0x180071e8b  test    eax, eax
0x180071e8d  jns     short loc_180071EB5
0x180071e8f  mov     rcx, [rsp+68h]; this
0x180071e94  mov     r9d, eax; char *
0x180071e97  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071e9e  mov     r8, rdi; unsigned int
0x180071ea1  mov     edx, 5CEh; void *
0x180071ea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071eab  mov     edx, 5A5h
0x180071eb0  jmp     loc_180071F79
0x180071eb5  mov     rax, rdi
0x180071eb8  lea     rcx, [rdi+28h]
0x180071ebc  neg     rax
0x180071ebf  sbb     rbp, rbp
0x180071ec2  and     rbp, rcx
0x180071ec5  cmp     qword ptr [rdi+78h], 0
0x180071eca  jz      short loc_180071F08
0x180071ecc  lea     rsi, [rdi+80h]
0x180071ed3  mov     rcx, rsi; SRWLock
0x180071ed6  call    cs:__imp_AcquireSRWLockExclusive
0x180071edc  mov     rax, [rdi+78h]
0x180071ee0  test    rax, rax
0x180071ee3  jnz     short loc_180071EE9
0x180071ee5  xor     ebx, ebx
0x180071ee7  jmp     short loc_180071EF5
0x180071ee9  mov     rbx, [rax+18h]
0x180071eed  sub     rbx, [rax+10h]
0x180071ef1  sar     rbx, 3
0x180071ef5  test    rsi, rsi
0x180071ef8  jz      short loc_180071F03
0x180071efa  mov     rcx, rsi; SRWLock
0x180071efd  call    cs:__imp_ReleaseSRWLockExclusive
0x180071f03  test    rbx, rbx
0x180071f06  jnz     short loc_180071F58
0x180071f08  mov     rcx, [r14]
0x180071f0b  mov     rax, [rcx]
0x180071f0e  mov     rdx, rbp
0x180071f11  mov     rax, [rax+38h]
0x180071f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f1a  mov     ebx, eax
0x180071f1c  test    eax, eax
0x180071f1e  jns     short loc_180071F58
0x180071f20  mov     rcx, [rsp+68h]; this
0x180071f25  mov     r9d, eax; char *
0x180071f28  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071f2f  mov     r8, rdi; unsigned int
0x180071f32  mov     edx, 5FAh; void *
0x180071f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071f3c  mov     rcx, [rsp+68h]; this
0x180071f41  mov     r9d, ebx; char *
0x180071f44  mov     r8, rdi; unsigned int
0x180071f47  mov     edx, 5DDh; void *
0x180071f4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071f51  mov     edx, 5A6h
0x180071f56  jmp     short loc_180071F79
0x180071f58  mov     r8, r15
0x180071f5b  mov     rdx, r12
0x180071f5e  lea     rcx, [rdi+78h]
0x180071f62  call    ?Add@?$GitEventSourceSupportsAgile@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@Internal@Windows@@QEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@3@PEAUEventRegistrationToken@@@Z; Windows::Internal::GitEventSourceSupportsAgile<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)
0x180071f67  mov     ebx, eax
0x180071f69  test    eax, eax
0x180071f6b  jns     short loc_180071FA2
0x180071f6d  mov     edx, 5A8h; void *
0x180071f72  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071f79  mov     rcx, [rsp+68h]; this
0x180071f7e  mov     r8, rdi; unsigned int
0x180071f81  mov     r9d, ebx; char *
0x180071f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071f89  mov     rcx, [rsp+68h]; this
0x180071f8e  mov     r9d, ebx; char *
0x180071f91  mov     r8, rdi; unsigned int
0x180071f94  mov     edx, 56Fh; void *
0x180071f99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071f9e  mov     eax, ebx
0x180071fa0  jmp     short loc_180071FA4
0x180071fa2  xor     eax, eax
0x180071fa4  add     rsp, 30h
0x180071fa8  pop     r15
0x180071faa  pop     r14
0x180071fac  pop     r12
0x180071fae  pop     rdi
0x180071faf  pop     rsi
0x180071fb0  pop     rbp
0x180071fb1  pop     rbx
0x180071fb2  retn
```
