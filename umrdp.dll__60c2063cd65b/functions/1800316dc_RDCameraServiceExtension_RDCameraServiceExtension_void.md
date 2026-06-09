# RDCameraServiceExtension::~RDCameraServiceExtension(void)

- ea: `0x1800316dc`
- end: `0x1800317d1`
- name: `??1RDCameraServiceExtension@@MEAA@XZ`
- size: `245`
- prototype: `void __fastcall(RDCameraServiceExtension *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180031370`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x18002ebe0`
- `0x180030e48`
- `0x180031308`
- `0x1800316dc`
- `0x180049010`

## import_xrefs

- `KERNEL32!CloseThreadpool` at `0x180031716`
- `KERNEL32!CloseThreadpool` at `0x180031716`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180031704`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180031704`

## pseudocode

```c
void __fastcall RDCameraServiceExtension::~RDCameraServiceExtension(RDCameraServiceExtension *this, __int64 a2)
{
  struct _TP_CLEANUP_GROUP *v3; // rcx
  struct _TP_POOL *v4; // rcx
  __int64 v5; // rcx
  int v6; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  utl::_RefCountBase *v8; // rcx
  utl::_RefCountBase *v9[2]; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)this = &RDCameraServiceExtension::`vftable';
  v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 18);
  if ( v3 )
    CloseThreadpoolCleanupGroup(v3);
  v4 = (struct _TP_POOL *)*((_QWORD *)this + 17);
  if ( v4 )
    CloseThreadpool(v4);
  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    LOBYTE(a2) = 1;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, a2);
    if ( v6 < 0
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        10,
        WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
        CurrentThreadActivityIdPrefix,
        v6);
    }
    *(_OWORD *)v9 = 0;
    utl::shared_ptr<ITsBusDevice>::operator=((char *)this + 16, v9);
    if ( v9[1] )
      utl::_RefCountBase::_DecStrong(v9[1]);
  }
  SmartArray<RDCameraDeviceManager,unsigned long>::~SmartArray<RDCameraDeviceManager,unsigned long>((char *)this + 32);
  v8 = (utl::_RefCountBase *)*((_QWORD *)this + 3);
  if ( v8 )
    utl::_RefCountBase::_DecStrong(v8);
}

```

## disassembly

```asm
0x1800316dc  mov     [rsp+arg_0], rbx
0x1800316e1  mov     [rsp+arg_8], rsi
0x1800316e6  push    rdi
0x1800316e7  sub     rsp, 40h
0x1800316eb  lea     rax, ??_7RDCameraServiceExtension@@6B@; const RDCameraServiceExtension::`vftable'
0x1800316f2  mov     rbx, rcx
0x1800316f5  mov     [rcx], rax
0x1800316f8  mov     rcx, [rcx+90h]; ptpcg
0x1800316ff  test    rcx, rcx
0x180031702  jz      short loc_18003170A
0x180031704  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18003170a  mov     rcx, [rbx+88h]; ptpp
0x180031711  test    rcx, rcx
0x180031714  jz      short loc_18003171C
0x180031716  call    cs:__imp_CloseThreadpool
0x18003171c  mov     rcx, [rbx+10h]
0x180031720  test    rcx, rcx
0x180031723  jz      loc_1800317AA
0x180031729  mov     rax, [rcx]
0x18003172c  mov     dl, 1
0x18003172e  mov     rax, [rax+18h]
0x180031732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031737  mov     esi, eax
0x180031739  test    eax, eax
0x18003173b  jns     short loc_180031784
0x18003173d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031744  lea     rax, WPP_GLOBAL_Control
0x18003174b  cmp     rcx, rax
0x18003174e  jz      short loc_180031784
0x180031750  test    byte ptr [rcx+1Ch], 1
0x180031754  jz      short loc_180031784
0x180031756  cmp     byte ptr [rcx+19h], 2
0x18003175a  jb      short loc_180031784
0x18003175c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031761  mov     rcx, cs:WPP_GLOBAL_Control
0x180031768  lea     r8, WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids
0x18003176f  mov     edx, 0Ah
0x180031774  mov     [rsp+48h+var_28], esi
0x180031778  mov     r9d, eax
0x18003177b  mov     rcx, [rcx+10h]
0x18003177f  call    WPP_SF_Dd
0x180031784  xorps   xmm0, xmm0
0x180031787  lea     rdx, [rsp+48h+var_18]
0x18003178c  lea     rcx, [rbx+10h]
0x180031790  movdqu  xmmword ptr [rsp+48h+var_18], xmm0
0x180031796  call    ??4?$shared_ptr@VITsBusDevice@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<ITsBusDevice>::operator=(utl::shared_ptr<ITsBusDevice> &&)
0x18003179b  mov     rcx, [rsp+48h+var_18+8]; this
0x1800317a0  test    rcx, rcx
0x1800317a3  jz      short loc_1800317AA
0x1800317a5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800317aa  lea     rcx, [rbx+20h]
0x1800317ae  call    ??1?$SmartArray@VRDCameraDeviceManager@@K@@QEAA@XZ; SmartArray<RDCameraDeviceManager,ulong>::~SmartArray<RDCameraDeviceManager,ulong>(void)
0x1800317b3  mov     rcx, [rbx+18h]; this
0x1800317b7  test    rcx, rcx
0x1800317ba  jz      short loc_1800317C1
0x1800317bc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800317c1  mov     rbx, [rsp+48h+arg_0]
0x1800317c6  mov     rsi, [rsp+48h+arg_8]
0x1800317cb  add     rsp, 40h
0x1800317cf  pop     rdi
0x1800317d0  retn
```
