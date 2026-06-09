# ClipboardApartmentState::remove_ContentChanged(EventRegistrationToken)

- ea: `0x180072330`
- end: `0x180072474`
- name: `?remove_ContentChanged@ClipboardApartmentState@@UEAAJUEventRegistrationToken@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(ClipboardApartmentState *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180047164`
- `0x180048954`
- `0x180072330`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007242c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007242c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072405`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072405`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800723a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800723a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClipboardApartmentState::remove_ContentChanged(RTL_SRWLOCK *this, struct EventRegistrationToken a2)
{
  PVOID Ptr; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT Instance; // eax
  unsigned int v9; // edi
  _QWORD *v10; // rax
  __int64 v11; // rbx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Ptr = this[22].Ptr;
  if ( Ptr )
  {
    v5 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x54C,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      return v6;
    }
    return 0;
  }
  if ( !this[21].Ptr )
  {
    Instance = CoCreateInstance(
                 &GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac,
                 0,
                 1u,
                 &GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1,
                 &this[21].Ptr);
    v9 = Instance;
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
        (const char *)v9,
        ppva);
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x550,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
        (const char *)v9,
        ppv);
      return v9;
    }
  }
  v9 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
         &this[9],
         a2.value);
  if ( !this[9].Ptr )
    goto LABEL_14;
  AcquireSRWLockExclusive(this + 10);
  v10 = this[9].Ptr;
  v11 = v10 ? (__int64)(v10[3] - v10[2]) >> 3 : 0LL;
  if ( this != (RTL_SRWLOCK *)-80LL )
    ReleaseSRWLockExclusive(this + 10);
  if ( !v11 )
LABEL_14:
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[21].Ptr + 32LL))(this[21].Ptr);
  if ( (v9 & 0x80000000) != 0 )
    goto LABEL_16;
  return 0;
}

```

## disassembly

```asm
0x180072330  push    rbx
0x180072332  push    rbp
0x180072333  push    rsi
0x180072334  push    rdi
0x180072335  push    r14
0x180072337  sub     rsp, 30h
0x18007233b  mov     rbx, rdx
0x18007233e  mov     rsi, rcx
0x180072341  mov     rcx, [rcx+0B0h]
0x180072348  test    rcx, rcx
0x18007234b  jz      short loc_180072383
0x18007234d  mov     rax, [rcx]
0x180072350  mov     rax, [rax+10h]
0x180072354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072359  mov     ebx, eax
0x18007235b  test    eax, eax
0x18007235d  jns     loc_180072467
0x180072363  mov     rcx, [rsp+58h]; this
0x180072368  mov     r9d, eax; char *
0x18007236b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180072372  mov     edx, 54Ch; void *
0x180072377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007237c  mov     eax, ebx
0x18007237e  jmp     loc_180072469
0x180072383  lea     r14, [rsi+0A8h]
0x18007238a  cmp     qword ptr [r14], 0
0x18007238e  jnz     short loc_1800723E9
0x180072390  mov     qword ptr [rsp+58h+ppv], r14; int
0x180072395  lea     r9, _GUID_69f490d3_555d_4c08_8f93_b3b39246a3e1; riid
0x18007239c  xor     edx, edx; pUnkOuter
0x18007239e  lea     r8d, [rdx+1]; dwClsContext
0x1800723a2  lea     rcx, _GUID_c7d83ddf_ead2_4536_86f5_6e88b89213ac; rclsid
0x1800723a9  call    cs:__imp_CoCreateInstance
0x1800723af  mov     edi, eax
0x1800723b1  test    eax, eax
0x1800723b3  jns     short loc_1800723E9
0x1800723b5  mov     rcx, [rsp+58h]; this
0x1800723ba  mov     r9d, eax; char *
0x1800723bd  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800723c4  mov     edx, 5CEh; void *
0x1800723c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800723ce  mov     rcx, [rsp+58h]; this
0x1800723d3  mov     r9d, edi; char *
0x1800723d6  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800723dd  mov     edx, 5AFh; void *
0x1800723e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800723e7  jmp     short loc_18007244A
0x1800723e9  mov     rdx, rbx
0x1800723ec  lea     rcx, [rsi+48h]
0x1800723f0  call    ?Remove@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
0x1800723f5  mov     edi, eax
0x1800723f7  cmp     qword ptr [rsi+48h], 0
0x1800723fc  jz      short loc_180072437
0x1800723fe  lea     rbp, [rsi+50h]
0x180072402  mov     rcx, rbp; SRWLock
0x180072405  call    cs:__imp_AcquireSRWLockExclusive
0x18007240b  mov     rax, [rsi+48h]
0x18007240f  test    rax, rax
0x180072412  jnz     short loc_180072418
0x180072414  xor     ebx, ebx
0x180072416  jmp     short loc_180072424
0x180072418  mov     rbx, [rax+18h]
0x18007241c  sub     rbx, [rax+10h]
0x180072420  sar     rbx, 3
0x180072424  test    rbp, rbp
0x180072427  jz      short loc_180072432
0x180072429  mov     rcx, rbp; SRWLock
0x18007242c  call    cs:__imp_ReleaseSRWLockExclusive
0x180072432  test    rbx, rbx
0x180072435  jnz     short loc_180072446
0x180072437  mov     rcx, [r14]
0x18007243a  mov     rax, [rcx]
0x18007243d  mov     rax, [rax+20h]
0x180072441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072446  test    edi, edi
0x180072448  jns     short loc_180072467
0x18007244a  mov     rcx, [rsp+58h]; this
0x18007244f  mov     r9d, edi; char *
0x180072452  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180072459  mov     edx, 550h; void *
0x18007245e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072463  mov     eax, edi
0x180072465  jmp     short loc_180072469
0x180072467  xor     eax, eax
0x180072469  add     rsp, 30h
0x18007246d  pop     r14
0x18007246f  pop     rdi
0x180072470  pop     rsi
0x180072471  pop     rbp
0x180072472  pop     rbx
0x180072473  retn
```
