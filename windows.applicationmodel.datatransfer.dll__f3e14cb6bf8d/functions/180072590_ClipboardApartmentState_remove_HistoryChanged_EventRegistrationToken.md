# ClipboardApartmentState::remove_HistoryChanged(EventRegistrationToken)

- ea: `0x180072590`
- end: `0x180072692`
- name: `?remove_HistoryChanged@ClipboardApartmentState@@UEAAJUEventRegistrationToken@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(ClipboardApartmentState *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180047164`
- `0x180048954`
- `0x180072590`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007264a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007264a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072623`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072623`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800725c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800725c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::remove_HistoryChanged(RTL_SRWLOCK *this, struct EventRegistrationToken a2)
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
        (void *)0x569,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v6,
        ppv);
      return v6;
    }
  }
  v6 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
         &this[10],
         a2.value);
  if ( !this[10].Ptr )
    goto LABEL_11;
  AcquireSRWLockExclusive(this + 11);
  Ptr = this[10].Ptr;
  v8 = Ptr ? (__int64)(Ptr[3] - Ptr[2]) >> 3 : 0LL;
  if ( this != (RTL_SRWLOCK *)-88LL )
    ReleaseSRWLockExclusive(this + 11);
  if ( !v8 )
LABEL_11:
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v4->Ptr + 48LL))(v4->Ptr);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_13;
  return 0;
}

```

## disassembly

```asm
0x180072590  push    rbx
0x180072592  push    rbp
0x180072593  push    rsi
0x180072594  push    rdi
0x180072595  push    r14
0x180072597  sub     rsp, 30h
0x18007259b  mov     rbx, rdx
0x18007259e  mov     rsi, rcx
0x1800725a1  lea     r14, [rcx+98h]
0x1800725a8  cmp     qword ptr [r14], 0
0x1800725ac  jnz     short loc_180072607
0x1800725ae  mov     qword ptr [rsp+58h+ppv], r14; int
0x1800725b3  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x1800725ba  xor     edx, edx; pUnkOuter
0x1800725bc  lea     r8d, [rdx+1]; dwClsContext
0x1800725c0  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x1800725c7  call    cs:__imp_CoCreateInstance
0x1800725cd  mov     edi, eax
0x1800725cf  test    eax, eax
0x1800725d1  jns     short loc_180072607
0x1800725d3  mov     rcx, [rsp+58h]; this
0x1800725d8  mov     r9d, eax; char *
0x1800725db  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800725e2  mov     edx, 5CEh; void *
0x1800725e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800725ec  mov     rcx, [rsp+58h]; this
0x1800725f1  mov     r9d, edi; char *
0x1800725f4  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800725fb  mov     edx, 5AFh; void *
0x180072600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072605  jmp     short loc_180072668
0x180072607  mov     rdx, rbx
0x18007260a  lea     rcx, [rsi+50h]
0x18007260e  call    ?Remove@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x180072613  mov     edi, eax
0x180072615  cmp     qword ptr [rsi+50h], 0
0x18007261a  jz      short loc_180072655
0x18007261c  lea     rbp, [rsi+58h]
0x180072620  mov     rcx, rbp; SRWLock
0x180072623  call    cs:__imp_AcquireSRWLockExclusive
0x180072629  mov     rax, [rsi+50h]
0x18007262d  test    rax, rax
0x180072630  jnz     short loc_180072636
0x180072632  xor     ebx, ebx
0x180072634  jmp     short loc_180072642
0x180072636  mov     rbx, [rax+18h]
0x18007263a  sub     rbx, [rax+10h]
0x18007263e  sar     rbx, 3
0x180072642  test    rbp, rbp
0x180072645  jz      short loc_180072650
0x180072647  mov     rcx, rbp; SRWLock
0x18007264a  call    cs:__imp_ReleaseSRWLockExclusive
0x180072650  test    rbx, rbx
0x180072653  jnz     short loc_180072664
0x180072655  mov     rcx, [r14]
0x180072658  mov     rax, [rcx]
0x18007265b  mov     rax, [rax+30h]
0x18007265f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072664  test    edi, edi
0x180072666  jns     short loc_180072685
0x180072668  mov     rcx, [rsp+58h]; this
0x18007266d  mov     r9d, edi; char *
0x180072670  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180072677  mov     edx, 569h; void *
0x18007267c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072681  mov     eax, edi
0x180072683  jmp     short loc_180072687
0x180072685  xor     eax, eax
0x180072687  add     rsp, 30h
0x18007268b  pop     r14
0x18007268d  pop     rdi
0x18007268e  pop     rsi
0x18007268f  pop     rbp
0x180072690  pop     rbx
0x180072691  retn
```
