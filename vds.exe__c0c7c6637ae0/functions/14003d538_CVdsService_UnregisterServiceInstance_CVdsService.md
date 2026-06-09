# CVdsService::UnregisterServiceInstance(CVdsService *)

- ea: `0x14003d538`
- end: `0x14003d604`
- name: `?UnregisterServiceInstance@CVdsService@@CAXPEAV1@@Z`
- size: `204`
- prototype: `void __fastcall(struct CVdsService *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x140036f88`

## callees

- `0x14000e2e0`
- `0x14003d538`
- `0x140052e46`

## import_xrefs

- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d571`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d571`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d58a`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d58a`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003d5b3`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003d5b3`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003d5c2`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003d5c2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003d558`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003d558`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003d5f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003d5f3`
- `vdsutil!?Remove@CRtlList@@QEAAXAEAVCRtlListIter@@@Z` at `0x14003d5d5`
- `vdsutil!?Remove@CRtlList@@QEAAXAEAVCRtlListIter@@@Z` at `0x14003d5d5`

## string_xrefs

- `0x14003d548`: `CVdsService::UnregisterServiceInstance()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsService::UnregisterServiceInstance(struct CVdsService *a1)
{
  CVdsServiceModule *v2; // rcx
  __int128 Buf1; // [rsp+20h] [rbp-40h] BYREF
  __int128 Buf2; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v5[16]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v6[16]; // [rsp+50h] [rbp-10h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v5, 0x5Eu, "CVdsService::UnregisterServiceInstance()");
  Buf1 = 0;
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstServiceInstances, &Buf2);
        ;
        CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstServiceInstances, v6);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    if ( CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1) == a1 )
    {
      CRtlList::Remove((CRtlList *)CVdsService::m_lstServiceInstances, (struct CRtlListIter *)&Buf1);
      break;
    }
  }
  if ( !dword_14009B150 )
    CVdsServiceModule::Handler(v2, 1);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v5);
}

```

## disassembly

```asm
0x14003d538  mov     [rsp-8+arg_0], rbx
0x14003d53d  push    rbp
0x14003d53e  mov     rbp, rsp
0x14003d541  sub     rsp, 60h
0x14003d545  mov     rbx, rcx
0x14003d548  lea     r8, aCvdsserviceUnr_0; "CVdsService::UnregisterServiceInstance("...
0x14003d54f  mov     edx, 5Eh ; '^'
0x14003d554  lea     rcx, [rbp+var_20]
0x14003d558  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003d55e  nop
0x14003d55f  xorps   xmm0, xmm0
0x14003d562  movups  [rbp+Buf1], xmm0
0x14003d566  lea     rdx, [rbp+Buf2]
0x14003d56a  lea     rcx, ?m_lstServiceInstances@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstServiceInstances
0x14003d571  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003d577  movups  xmm0, xmmword ptr [rax]
0x14003d57a  movdqu  [rbp+Buf1], xmm0
0x14003d57f  lea     rdx, [rbp+var_10]
0x14003d583  lea     rcx, ?m_lstServiceInstances@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstServiceInstances
0x14003d58a  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003d590  movups  xmm0, xmmword ptr [rax]
0x14003d593  movdqu  [rbp+Buf2], xmm0
0x14003d598  mov     r8d, 10h; Size
0x14003d59e  lea     rdx, [rbp+Buf2]; Buf2
0x14003d5a2  lea     rcx, [rbp+Buf1]; Buf1
0x14003d5a6  call    memcmp_0
0x14003d5ab  test    eax, eax
0x14003d5ad  jz      short loc_14003D5DB
0x14003d5af  lea     rcx, [rbp+Buf1]
0x14003d5b3  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003d5b9  cmp     rax, rbx
0x14003d5bc  jz      short loc_14003D5CA
0x14003d5be  lea     rcx, [rbp+Buf1]
0x14003d5c2  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003d5c8  jmp     short loc_14003D57F
0x14003d5ca  lea     rdx, [rbp+Buf1]
0x14003d5ce  lea     rcx, ?m_lstServiceInstances@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstServiceInstances
0x14003d5d5  call    cs:__imp_?Remove@CRtlList@@QEAAXAEAVCRtlListIter@@@Z; CRtlList::Remove(CRtlListIter &)
0x14003d5db  cmp     cs:dword_14009B150, 0
0x14003d5e2  jnz     short loc_14003D5EF
0x14003d5e4  mov     edx, 1; unsigned int
0x14003d5e9  call    ?Handler@CVdsServiceModule@@QEAAXK@Z; CVdsServiceModule::Handler(ulong)
0x14003d5ee  nop
0x14003d5ef  lea     rcx, [rbp+var_20]
0x14003d5f3  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003d5f9  mov     rbx, [rsp+60h+arg_0]
0x14003d5fe  add     rsp, 60h
0x14003d602  pop     rbp
0x14003d603  retn
```
