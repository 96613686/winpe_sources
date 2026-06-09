# CWdsTransportNamespaceScheduledCastAutoStart::CloneWorker(IWdsTransportNamespace *)

- ea: `0x180014110`
- end: `0x180014237`
- name: `?CloneWorker@CWdsTransportNamespaceScheduledCastAutoStart@@EEAAJPEAUIWdsTransportNamespace@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastAutoStart *__hidden this, struct IWdsTransportNamespace *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180014110`
- `0x18001470c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001414b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014212`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001414b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014212`

## string_xrefs

- `0x180014138`: `-> CWdsTransportNamespaceScheduledCastAutoStart::CloneWorker(0x%p)`
- `0x1800141ff`: `<- CWdsTransportNamespaceScheduledCastAutoStart::CloneWorker(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportNamespaceScheduledCastAutoStart::CloneWorker(
        CWdsTransportNamespaceScheduledCastAutoStart *this,
        struct IWdsTransportNamespace *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  int v12; // [rsp+20h] [rbp-28h]
  _BYTE v13[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v13, (char *)this + 64);
  v14 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastAutoStart::CloneWorker(0x%p)",
    this);
  v4 = ((__int64 (__fastcall *)(struct IWdsTransportNamespace *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IWdsTransportNamespaceScheduledCastAutoStart,
         &v14);
  if ( (int)ElValidateHr_8(v4, v5, v6, 331) >= 0 )
  {
    v4 = (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 240LL))(v14, *((unsigned int *)this + 57));
    if ( (int)ElValidateHr_8(v4, v7, v8, 337) >= 0 )
    {
      v4 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 256LL))(v14);
      ElValidateHr_8(v4, v9, v10, 340);
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  v12 = v4;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastAutoStart::CloneWorker(0x%p) =%x",
    this,
    v12);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014110  mov     [rsp+arg_8], rbx
0x180014115  push    rdi
0x180014116  sub     rsp, 40h
0x18001411a  mov     rbx, rdx
0x18001411d  mov     rdi, rcx
0x180014120  lea     rdx, [rcx+40h]
0x180014124  lea     rcx, [rsp+48h+var_18]
0x180014129  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18001412e  nop
0x18001412f  and     [rsp+48h+arg_0], 0
0x180014135  mov     r9, rdi
0x180014138  lea     r8, aCwdstransportn_51; "-> CWdsTransportNamespaceScheduledCastA"...
0x18001413f  mov     edx, 10000h
0x180014144  lea     rcx, qword_18003B770
0x18001414b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014152  nop     dword ptr [rax+rax+00h]
0x180014157  mov     rax, [rbx]
0x18001415a  lea     r8, [rsp+48h+arg_0]
0x18001415f  lea     rdx, IID_IWdsTransportNamespaceScheduledCastAutoStart
0x180014166  mov     rcx, rbx
0x180014169  mov     rax, [rax]
0x18001416c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014171  mov     ebx, eax
0x180014173  mov     r9d, 14Bh
0x180014179  mov     ecx, eax
0x18001417b  call    ElValidateHr_8
0x180014180  test    eax, eax
0x180014182  js      short loc_1800141DC
0x180014184  mov     rcx, [rsp+48h+arg_0]
0x180014189  mov     rax, [rcx]
0x18001418c  mov     edx, [rdi+0E4h]
0x180014192  mov     rax, [rax+0F0h]
0x180014199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001419e  mov     ebx, eax
0x1800141a0  mov     r9d, 151h
0x1800141a6  mov     ecx, eax
0x1800141a8  call    ElValidateHr_8
0x1800141ad  test    eax, eax
0x1800141af  js      short loc_1800141DC
0x1800141b1  mov     rcx, [rsp+48h+arg_0]
0x1800141b6  mov     rax, [rcx]
0x1800141b9  movsd   xmm1, qword ptr [rdi+0E8h]
0x1800141c1  mov     rax, [rax+100h]
0x1800141c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141cd  mov     ebx, eax
0x1800141cf  mov     r9d, 154h
0x1800141d5  mov     ecx, eax
0x1800141d7  call    ElValidateHr_8
0x1800141dc  mov     rcx, [rsp+48h+arg_0]
0x1800141e1  test    rcx, rcx
0x1800141e4  jz      short loc_1800141F8
0x1800141e6  mov     rax, [rcx]
0x1800141e9  mov     rax, [rax+10h]
0x1800141ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141f2  and     [rsp+48h+arg_0], 0
0x1800141f8  mov     [rsp+48h+var_28], ebx
0x1800141fc  mov     r9, rdi
0x1800141ff  lea     r8, aCwdstransportn_42; "<- CWdsTransportNamespaceScheduledCastA"...
0x180014206  mov     edx, 10000h
0x18001420b  lea     rcx, qword_18003B770
0x180014212  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014219  nop     dword ptr [rax+rax+00h]
0x18001421e  nop
0x18001421f  lea     rcx, [rsp+48h+var_18]
0x180014224  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180014229  mov     eax, ebx
0x18001422b  mov     rbx, [rsp+48h+arg_8]
0x180014230  add     rsp, 40h
0x180014234  pop     rdi
0x180014235  retn
```
