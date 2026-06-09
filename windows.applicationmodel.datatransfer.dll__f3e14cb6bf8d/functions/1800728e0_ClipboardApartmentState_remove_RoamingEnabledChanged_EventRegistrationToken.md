# ClipboardApartmentState::remove_RoamingEnabledChanged(EventRegistrationToken)

- ea: `0x1800728e0`
- end: `0x1800729e2`
- name: `?remove_RoamingEnabledChanged@ClipboardApartmentState@@UEAAJUEventRegistrationToken@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(ClipboardApartmentState *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180047164`
- `0x180048954`
- `0x1800728e0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007299a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007299a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072973`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072973`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072917`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072917`

## pseudocode

```c
__int64 __fastcall ClipboardApartmentState::remove_RoamingEnabledChanged(
        RTL_SRWLOCK *this,
        struct EventRegistrationToken a2)
{
  RTL_SRWLOCK *v4; // r14
  HRESULT Instance; // eax
  unsigned int v6; // edi
  _QWORD *Ptr; // rax
  __int64 v8; // rbx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = this + 19;
  if ( !this[19].Ptr )
  {
    Instance = CoCreateInstance(
                 &GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac,
                 0,
                 1u,
                 &GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1,
                 &this[19].Ptr);
    v6 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AF,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v6,
        ppva);
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x575,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v6,
        ppv);
      return v6;
    }
  }
  v6 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
         &this[13],
         a2.value);
  if ( !this[13].Ptr )
    goto LABEL_11;
  AcquireSRWLockExclusive(this + 14);
  Ptr = this[13].Ptr;
  v8 = Ptr ? (__int64)(Ptr[3] - Ptr[2]) >> 3 : 0LL;
  if ( this != (RTL_SRWLOCK *)-112LL )
    ReleaseSRWLockExclusive(this + 14);
  if ( !v8 )
LABEL_11:
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v4->Ptr + 64LL))(v4->Ptr);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_13;
  return 0;
}

```

## disassembly

```asm
0x1800728e0  push    rbx
0x1800728e2  push    rbp
0x1800728e3  push    rsi
0x1800728e4  push    rdi
0x1800728e5  push    r14
0x1800728e7  sub     rsp, 30h
0x1800728eb  mov     rbx, rdx
0x1800728ee  mov     rsi, rcx
0x1800728f1  lea     r14, [rcx+98h]
0x1800728f8  cmp     qword ptr [r14], 0
0x1800728fc  jnz     short loc_180072957
0x1800728fe  mov     qword ptr [rsp+58h+ppv], r14; int
0x180072903  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x18007290a  xor     edx, edx; pUnkOuter
0x18007290c  lea     r8d, [rdx+1]; dwClsContext
0x180072910  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x180072917  call    cs:__imp_CoCreateInstance
0x18007291d  mov     edi, eax
0x18007291f  test    eax, eax
0x180072921  jns     short loc_180072957
0x180072923  mov     rcx, [rsp+58h]; this
0x180072928  mov     r9d, eax; char *
0x18007292b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180072932  mov     edx, 5CEh; void *
0x180072937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007293c  mov     rcx, [rsp+58h]; this
0x180072941  mov     r9d, edi; char *
0x180072944  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18007294b  mov     edx, 5AFh; void *
0x180072950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072955  jmp     short loc_1800729B8
0x180072957  mov     rdx, rbx
0x18007295a  lea     rcx, [rsi+68h]
0x18007295e  call    ?Remove@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180072963  mov     edi, eax
0x180072965  cmp     qword ptr [rsi+68h], 0
0x18007296a  jz      short loc_1800729A5
0x18007296c  lea     rbp, [rsi+70h]
0x180072970  mov     rcx, rbp; SRWLock
0x180072973  call    cs:__imp_AcquireSRWLockExclusive
0x180072979  mov     rax, [rsi+68h]
0x18007297d  test    rax, rax
0x180072980  jnz     short loc_180072986
0x180072982  xor     ebx, ebx
0x180072984  jmp     short loc_180072992
0x180072986  mov     rbx, [rax+18h]
0x18007298a  sub     rbx, [rax+10h]
0x18007298e  sar     rbx, 3
0x180072992  test    rbp, rbp
0x180072995  jz      short loc_1800729A0
0x180072997  mov     rcx, rbp; SRWLock
0x18007299a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800729a0  test    rbx, rbx
0x1800729a3  jnz     short loc_1800729B4
0x1800729a5  mov     rcx, [r14]
0x1800729a8  mov     rax, [rcx]
0x1800729ab  mov     rax, [rax+40h]
0x1800729af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729b4  test    edi, edi
0x1800729b6  jns     short loc_1800729D5
0x1800729b8  mov     rcx, [rsp+58h]; this
0x1800729bd  mov     r9d, edi; char *
0x1800729c0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800729c7  mov     edx, 575h; void *
0x1800729cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800729d1  mov     eax, edi
0x1800729d3  jmp     short loc_1800729D7
0x1800729d5  xor     eax, eax
0x1800729d7  add     rsp, 30h
0x1800729db  pop     r14
0x1800729dd  pop     rdi
0x1800729de  pop     rsi
0x1800729df  pop     rbp
0x1800729e0  pop     rbx
0x1800729e1  retn
```
