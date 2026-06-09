# ClipboardApartmentState::add_HistoryEnabledChanged(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180071c00`
- end: `0x180071d7c`
- name: `?add_HistoryEnabledChanged@ClipboardApartmentState@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180048954`
- `0x18006a0a8`
- `0x180071c00`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071cc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071cc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071c99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071c99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071c43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071c43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::add_HistoryEnabledChanged(__int64 a1, __int64 a2, _QWORD *a3)
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
        (void *)0x57B,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v8,
        ppvb);
      return v8;
    }
  }
  if ( !v5[18].Ptr )
    goto LABEL_19;
  AcquireSRWLockExclusive(v5 + 19);
  Ptr = v5[18].Ptr;
  v11 = Ptr ? (__int64)(Ptr[3] - Ptr[2]) >> 3 : 0LL;
  if ( v5 != (RTL_SRWLOCK *)-152LL )
    ReleaseSRWLockExclusive(v5 + 19);
  if ( !v11 )
  {
LABEL_19:
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v6 + 72LL))(
            *v6,
            (unsigned __int64)&v5[6] & -(__int64)(v5 != 0));
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x601,
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
         &v5[18],
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
0x180071c00  push    rbx
0x180071c02  push    rbp
0x180071c03  push    rsi
0x180071c04  push    rdi
0x180071c05  push    r12
0x180071c07  push    r14
0x180071c09  push    r15
0x180071c0b  sub     rsp, 30h
0x180071c0f  mov     r15, r8
0x180071c12  mov     r12, rdx
0x180071c15  lea     rdi, [rcx-10h]
0x180071c19  xor     eax, eax
0x180071c1b  mov     [r8], rax
0x180071c1e  lea     r14, [rdi+0A8h]
0x180071c25  cmp     [r14], rax
0x180071c28  jnz     short loc_180071C75
0x180071c2a  mov     qword ptr [rsp+68h+ppv], r14; int
0x180071c2f  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x180071c36  xor     edx, edx; pUnkOuter
0x180071c38  lea     r8d, [rax+1]; dwClsContext
0x180071c3c  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x180071c43  call    cs:__imp_CoCreateInstance
0x180071c49  mov     ebx, eax
0x180071c4b  test    eax, eax
0x180071c4d  jns     short loc_180071C75
0x180071c4f  mov     rcx, [rsp+68h]; this
0x180071c54  mov     r9d, eax; char *
0x180071c57  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071c5e  mov     r8, rdi; unsigned int
0x180071c61  mov     edx, 5CEh; void *
0x180071c66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071c6b  mov     edx, 5A5h
0x180071c70  jmp     loc_180071D42
0x180071c75  mov     rax, rdi
0x180071c78  lea     rcx, [rdi+30h]
0x180071c7c  neg     rax
0x180071c7f  sbb     rbp, rbp
0x180071c82  and     rbp, rcx
0x180071c85  cmp     qword ptr [rdi+90h], 0
0x180071c8d  jz      short loc_180071CCE
0x180071c8f  lea     rsi, [rdi+98h]
0x180071c96  mov     rcx, rsi; SRWLock
0x180071c99  call    cs:__imp_AcquireSRWLockExclusive
0x180071c9f  mov     rax, [rdi+90h]
0x180071ca6  test    rax, rax
0x180071ca9  jnz     short loc_180071CAF
0x180071cab  xor     ebx, ebx
0x180071cad  jmp     short loc_180071CBB
0x180071caf  mov     rbx, [rax+18h]
0x180071cb3  sub     rbx, [rax+10h]
0x180071cb7  sar     rbx, 3
0x180071cbb  test    rsi, rsi
0x180071cbe  jz      short loc_180071CC9
0x180071cc0  mov     rcx, rsi; SRWLock
0x180071cc3  call    cs:__imp_ReleaseSRWLockExclusive
0x180071cc9  test    rbx, rbx
0x180071ccc  jnz     short loc_180071D1E
0x180071cce  mov     rcx, [r14]
0x180071cd1  mov     rax, [rcx]
0x180071cd4  mov     rdx, rbp
0x180071cd7  mov     rax, [rax+48h]
0x180071cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ce0  mov     ebx, eax
0x180071ce2  test    eax, eax
0x180071ce4  jns     short loc_180071D1E
0x180071ce6  mov     rcx, [rsp+68h]; this
0x180071ceb  mov     r9d, eax; char *
0x180071cee  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071cf5  mov     r8, rdi; unsigned int
0x180071cf8  mov     edx, 601h; void *
0x180071cfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071d02  mov     rcx, [rsp+68h]; this
0x180071d07  mov     r9d, ebx; char *
0x180071d0a  mov     r8, rdi; unsigned int
0x180071d0d  mov     edx, 5DDh; void *
0x180071d12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071d17  mov     edx, 5A6h
0x180071d1c  jmp     short loc_180071D42
0x180071d1e  mov     r8, r15
0x180071d21  mov     rdx, r12
0x180071d24  lea     rcx, [rdi+90h]
0x180071d2b  call    ?Add@?$GitEventSourceSupportsAgile@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@Internal@Windows@@QEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@3@PEAUEventRegistrationToken@@@Z; Windows::Internal::GitEventSourceSupportsAgile<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)
0x180071d30  mov     ebx, eax
0x180071d32  test    eax, eax
0x180071d34  jns     short loc_180071D6B
0x180071d36  mov     edx, 5A8h; void *
0x180071d3b  lea     rdi, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180071d42  mov     rcx, [rsp+68h]; this
0x180071d47  mov     r8, rdi; unsigned int
0x180071d4a  mov     r9d, ebx; char *
0x180071d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071d52  mov     rcx, [rsp+68h]; this
0x180071d57  mov     r9d, ebx; char *
0x180071d5a  mov     r8, rdi; unsigned int
0x180071d5d  mov     edx, 57Bh; void *
0x180071d62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071d67  mov     eax, ebx
0x180071d69  jmp     short loc_180071D6D
0x180071d6b  xor     eax, eax
0x180071d6d  add     rsp, 30h
0x180071d71  pop     r15
0x180071d73  pop     r14
0x180071d75  pop     r12
0x180071d77  pop     rdi
0x180071d78  pop     rsi
0x180071d79  pop     rbp
0x180071d7a  pop     rbx
0x180071d7b  retn
```
