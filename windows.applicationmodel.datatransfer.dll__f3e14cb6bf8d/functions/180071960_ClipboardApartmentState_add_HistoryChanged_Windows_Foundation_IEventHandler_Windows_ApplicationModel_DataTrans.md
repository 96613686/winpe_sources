# ClipboardApartmentState::add_HistoryChanged(Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *> *,EventRegistrationToken *)

- ea: `0x180071960`
- end: `0x180071b3d`
- name: `?add_HistoryChanged@ClipboardApartmentState@@UEAAJPEAU?$IEventHandler@PEAVClipboardHistoryChangedEventArgs@DataTransfer@ApplicationModel@Windows@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001e788`
- `0x180048954`
- `0x18006839c`
- `0x180071960`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071a23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071a23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800719fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800719fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800719aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800719aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::add_HistoryChanged(__int64 a1, __int64 a2, _QWORD *a3)
{
  RTL_SRWLOCK *v5; // rdi
  _QWORD *v6; // r15
  HRESULT Instance; // eax
  int v8; // ebx
  __int64 v9; // rdx
  RTL_SRWLOCK *v10; // rsi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  int ppvb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF

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
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)v8,
        ppv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x563,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)v8,
        ppvb);
      return (unsigned int)v8;
    }
  }
  v10 = v5 + 12;
  if ( !v5[12].Ptr )
    goto LABEL_27;
  AcquireSRWLockExclusive(v5 + 13);
  if ( v10->Ptr )
    v11 = (__int64)(*((_QWORD *)v10->Ptr + 3) - *((_QWORD *)v10->Ptr + 2)) >> 3;
  else
    v11 = 0;
  if ( v5 != (RTL_SRWLOCK *)-104LL )
    ReleaseSRWLockExclusive(v5 + 13);
  if ( !v11 )
  {
LABEL_27:
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v6 + 40LL))(
            *v6,
            (unsigned __int64)&v5[4] & -(__int64)(v5 != 0));
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F3,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)v12,
        ppv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DD,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)v8,
        ppva);
      v9 = 1446;
      goto LABEL_23;
    }
  }
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_22:
    v9 = 1448;
    goto LABEL_23;
  }
  v19 = 0;
  v8 = Windows::Internal::Details::CreateGitHelper<Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *>>>(
         a2,
         &v19);
  if ( v8 >= 0 )
  {
    if ( v19 )
      v8 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
             v10,
             v19,
             *(_QWORD *)(*(_QWORD *)a2 + 24LL),
             a3);
    else
      v8 = -2147024809;
  }
  v13 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v8 < 0 )
    goto LABEL_22;
  return 0;
}

```

## disassembly

```asm
0x180071960  mov     [rsp+arg_8], rbx
0x180071965  mov     [rsp+arg_10], rbp
0x18007196a  push    rsi
0x18007196b  push    rdi
0x18007196c  push    r12
0x18007196e  push    r14
0x180071970  push    r15
0x180071972  sub     rsp, 30h
0x180071976  mov     r12, r8
0x180071979  mov     r14, rdx
0x18007197c  lea     rdi, [rcx-10h]
0x180071980  xor     eax, eax
0x180071982  mov     [r8], rax
0x180071985  lea     r15, [rdi+0A8h]
0x18007198c  cmp     [r15], rax
0x18007198f  jnz     short loc_1800719DC
0x180071991  mov     qword ptr [rsp+58h+ppv], r15; int
0x180071996  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x18007199d  xor     edx, edx; pUnkOuter
0x18007199f  lea     r8d, [rax+1]; dwClsContext
0x1800719a3  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x1800719aa  call    cs:__imp_CoCreateInstance
0x1800719b0  mov     ebx, eax
0x1800719b2  test    eax, eax
0x1800719b4  jns     short loc_1800719DC
0x1800719b6  mov     rcx, [rsp+58h]; this
0x1800719bb  mov     r9d, eax; char *
0x1800719be  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800719c5  mov     r8, rdi; unsigned int
0x1800719c8  mov     edx, 5CEh; void *
0x1800719cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800719d2  mov     edx, 5A5h
0x1800719d7  jmp     loc_180071AFB
0x1800719dc  mov     rax, rdi
0x1800719df  lea     rcx, [rdi+20h]
0x1800719e3  neg     rax
0x1800719e6  sbb     rbp, rbp
0x1800719e9  and     rbp, rcx
0x1800719ec  lea     rsi, [rdi+60h]
0x1800719f0  cmp     qword ptr [rsi], 0
0x1800719f4  jz      short loc_180071A2E
0x1800719f6  lea     rdi, [rsi+8]
0x1800719fa  mov     rcx, rdi; SRWLock
0x1800719fd  call    cs:__imp_AcquireSRWLockExclusive
0x180071a03  mov     rax, [rsi]
0x180071a06  test    rax, rax
0x180071a09  jnz     short loc_180071A0F
0x180071a0b  xor     ebx, ebx
0x180071a0d  jmp     short loc_180071A1B
0x180071a0f  mov     rbx, [rax+18h]
0x180071a13  sub     rbx, [rax+10h]
0x180071a17  sar     rbx, 3
0x180071a1b  test    rdi, rdi
0x180071a1e  jz      short loc_180071A29
0x180071a20  mov     rcx, rdi; SRWLock
0x180071a23  call    cs:__imp_ReleaseSRWLockExclusive
0x180071a29  test    rbx, rbx
0x180071a2c  jnz     short loc_180071A7E
0x180071a2e  mov     rcx, [r15]
0x180071a31  mov     rax, [rcx]
0x180071a34  mov     rdx, rbp
0x180071a37  mov     rax, [rax+28h]
0x180071a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a40  mov     ebx, eax
0x180071a42  test    eax, eax
0x180071a44  jns     short loc_180071A7E
0x180071a46  mov     rcx, [rsp+58h]; this
0x180071a4b  mov     r9d, eax; char *
0x180071a4e  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071a55  mov     r8, rdi; unsigned int
0x180071a58  mov     edx, 5F3h; void *
0x180071a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071a62  mov     rcx, [rsp+58h]; this
0x180071a67  mov     r9d, ebx; char *
0x180071a6a  mov     r8, rdi; unsigned int
0x180071a6d  mov     edx, 5DDh; void *
0x180071a72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071a77  mov     edx, 5A6h
0x180071a7c  jmp     short loc_180071AFB
0x180071a7e  test    r14, r14
0x180071a81  jnz     short loc_180071A8A
0x180071a83  mov     ebx, 80070057h
0x180071a88  jmp     short loc_180071AEF
0x180071a8a  mov     [rsp+58h+arg_0], 0
0x180071a93  lea     rdx, [rsp+58h+arg_0]
0x180071a98  mov     rcx, r14
0x180071a9b  call    ??$CreateGitHelper@U?$IEventHandler@PEAVClipboardHistoryChangedEventArgs@DataTransfer@ApplicationModel@Windows@@@Foundation@Windows@@V?$GitPtrSupportsAgile@U?$IEventHandler@PEAVClipboardHistoryChangedEventArgs@DataTransfer@ApplicationModel@Windows@@@Foundation@Windows@@@Internal@3@@Details@Internal@Windows@@YAJPEAU?$IEventHandler@PEAVClipboardHistoryChangedEventArgs@DataTransfer@ApplicationModel@Windows@@@Foundation@2@PEAPEAU342@@Z; Windows::Internal::Details::CreateGitHelper<Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *>>>(Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *> *,Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *> * *)
0x180071aa0  mov     ebx, eax
0x180071aa2  test    eax, eax
0x180071aa4  js      short loc_180071ACB
0x180071aa6  mov     rdx, [rsp+58h+arg_0]
0x180071aab  test    rdx, rdx
0x180071aae  jnz     short loc_180071AB7
0x180071ab0  mov     ebx, 80070057h
0x180071ab5  jmp     short loc_180071ACB
0x180071ab7  mov     r8, [r14]
0x180071aba  mov     r9, r12
0x180071abd  mov     r8, [r8+18h]
0x180071ac1  mov     rcx, rsi
0x180071ac4  call    ?AddInternal@?$EventSource@U?$IEventHandler@PEAVClipboardHistoryChangedEventArgs@DataTransfer@ApplicationModel@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$IEventHandler@PEAVClipboardHistoryChangedEventArgs@DataTransfer@ApplicationModel@Windows@@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::IEventHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryChangedEventArgs *> *,void *,EventRegistrationToken *)
0x180071ac9  mov     ebx, eax
0x180071acb  mov     rcx, [rsp+58h+arg_0]
0x180071ad0  test    rcx, rcx
0x180071ad3  jz      short loc_180071AEB
0x180071ad5  mov     [rsp+58h+arg_0], 0
0x180071ade  mov     rax, [rcx]
0x180071ae1  mov     rax, [rax+10h]
0x180071ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071aea  nop
0x180071aeb  test    ebx, ebx
0x180071aed  jns     short loc_180071B24
0x180071aef  mov     edx, 5A8h; void *
0x180071af4  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071afb  mov     rcx, [rsp+58h]; this
0x180071b00  mov     r8, rdi; unsigned int
0x180071b03  mov     r9d, ebx; char *
0x180071b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071b0b  mov     rcx, [rsp+58h]; this
0x180071b10  mov     r9d, ebx; char *
0x180071b13  mov     r8, rdi; unsigned int
0x180071b16  mov     edx, 563h; void *
0x180071b1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071b20  mov     eax, ebx
0x180071b22  jmp     short loc_180071B26
0x180071b24  xor     eax, eax
0x180071b26  mov     rbx, [rsp+58h+arg_8]
0x180071b2b  mov     rbp, [rsp+58h+arg_10]
0x180071b30  add     rsp, 30h
0x180071b34  pop     r15
0x180071b36  pop     r14
0x180071b38  pop     r12
0x180071b3a  pop     rdi
0x180071b3b  pop     rsi
0x180071b3c  retn
```
