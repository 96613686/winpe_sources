# ClipboardApartmentState::remove_HistoryEnabledChanged(EventRegistrationToken)

- ea: `0x180072730`
- end: `0x18007283e`
- name: `?remove_HistoryEnabledChanged@ClipboardApartmentState@@UEAAJUEventRegistrationToken@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(ClipboardApartmentState *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180047164`
- `0x180048954`
- `0x180072730`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800727f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800727f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800727cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800727cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072767`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072767`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::remove_HistoryEnabledChanged(
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
        (void *)0x581,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v6,
        ppv);
      return v6;
    }
  }
  v6 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
         &this[16],
         a2.value);
  if ( !this[16].Ptr )
    goto LABEL_11;
  AcquireSRWLockExclusive(this + 17);
  Ptr = this[16].Ptr;
  v8 = Ptr ? (__int64)(Ptr[3] - Ptr[2]) >> 3 : 0LL;
  if ( this != (RTL_SRWLOCK *)-136LL )
    ReleaseSRWLockExclusive(this + 17);
  if ( !v8 )
LABEL_11:
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v4->Ptr + 80LL))(v4->Ptr);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_13;
  return 0;
}

```

## disassembly

```asm
0x180072730  push    rbx
0x180072732  push    rbp
0x180072733  push    rsi
0x180072734  push    rdi
0x180072735  push    r14
0x180072737  sub     rsp, 30h
0x18007273b  mov     rbx, rdx
0x18007273e  mov     rsi, rcx
0x180072741  lea     r14, [rcx+98h]
0x180072748  cmp     qword ptr [r14], 0
0x18007274c  jnz     short loc_1800727A7
0x18007274e  mov     qword ptr [rsp+58h+ppv], r14; int
0x180072753  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x18007275a  xor     edx, edx; pUnkOuter
0x18007275c  lea     r8d, [rdx+1]; dwClsContext
0x180072760  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x180072767  call    cs:__imp_CoCreateInstance
0x18007276d  mov     edi, eax
0x18007276f  test    eax, eax
0x180072771  jns     short loc_1800727A7
0x180072773  mov     rcx, [rsp+58h]; this
0x180072778  mov     r9d, eax; char *
0x18007277b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180072782  mov     edx, 5CEh; void *
0x180072787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007278c  mov     rcx, [rsp+58h]; this
0x180072791  mov     r9d, edi; char *
0x180072794  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18007279b  mov     edx, 5AFh; void *
0x1800727a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800727a5  jmp     short loc_180072814
0x1800727a7  mov     rdx, rbx
0x1800727aa  lea     rcx, [rsi+80h]
0x1800727b1  call    ?Remove@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x1800727b6  mov     edi, eax
0x1800727b8  cmp     qword ptr [rsi+80h], 0
0x1800727c0  jz      short loc_180072801
0x1800727c2  lea     rbp, [rsi+88h]
0x1800727c9  mov     rcx, rbp; SRWLock
0x1800727cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800727d2  mov     rax, [rsi+80h]
0x1800727d9  test    rax, rax
0x1800727dc  jnz     short loc_1800727E2
0x1800727de  xor     ebx, ebx
0x1800727e0  jmp     short loc_1800727EE
0x1800727e2  mov     rbx, [rax+18h]
0x1800727e6  sub     rbx, [rax+10h]
0x1800727ea  sar     rbx, 3
0x1800727ee  test    rbp, rbp
0x1800727f1  jz      short loc_1800727FC
0x1800727f3  mov     rcx, rbp; SRWLock
0x1800727f6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800727fc  test    rbx, rbx
0x1800727ff  jnz     short loc_180072810
0x180072801  mov     rcx, [r14]
0x180072804  mov     rax, [rcx]
0x180072807  mov     rax, [rax+50h]
0x18007280b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072810  test    edi, edi
0x180072812  jns     short loc_180072831
0x180072814  mov     rcx, [rsp+58h]; this
0x180072819  mov     r9d, edi; char *
0x18007281c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180072823  mov     edx, 581h; void *
0x180072828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007282d  mov     eax, edi
0x18007282f  jmp     short loc_180072833
0x180072831  xor     eax, eax
0x180072833  add     rsp, 30h
0x180072837  pop     r14
0x180072839  pop     rdi
0x18007283a  pop     rsi
0x18007283b  pop     rbp
0x18007283c  pop     rbx
0x18007283d  retn
```
